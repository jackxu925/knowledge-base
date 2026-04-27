# Slack 消息归档到本地知识库 — 方案总结

**日期**: 2026-04-26
**场景**: 无 Admin 权限，macOS，输出到 raw/ 目录供下游 skill 消费，附件只存 URL

---

## 一、核心工具

| 工具 | 作用 | 为什么选它 |
|------|------|-----------|
| **slackdump** | 拉取 Slack 全量数据（Public + Private + DM + 附件元数据） | 无需 Workspace Admin 权限，支持增量 resume，输出 SQLite |
| **sqlite_to_raw.py** | 将 SQLite 转为标准化 Markdown | 按日期分目录，frontmatter 结构化，标准 Markdown 无 Obsidian 语法 |
| **daily_slack_backup.sh** | 每日定时执行 | macOS 兼容，支持 cron 或 launchd |

---

## 二、最终目录结构

```
~/SlackArchive/
├── archive/                      # slackdump 原始 SQLite（增量追加）
│   └── slackdump.sqlite
├── raw/                          # ⬅️ 下游 skill 消费目录
│   ├── 2026-04-25/
│   │   ├── general.md
│   │   ├── product-discussion.md
│   │   └── dm-alice-wang.md
│   ├── 2026-04-26/
│   │   ├── general.md
│   │   └── ...
│   └── 2026-04-27/
│       └── ...
└── scripts/
    ├── sqlite_to_raw.py
    └── daily_slack_backup.sh
```

---

## 三、每个 .md 文件的格式

```markdown
---
channel: general
channel_id: C12345678
date: 2026-04-26
type: channel
participants: ["alice", "bob", "charlie"]
message_count: 42
thread_count: 3
file_count: 2
---

# general / 2026-04-26

## 09:23:15 @alice
消息正文，支持 **加粗**、*斜体*、[链接](https://example.com)

> **Thread Reply** 09:24:00 @bob: 回复内容
> **Thread Reply** 09:25:00 @charlie: 另一条回复

_Reactions: :thumbsup: x3 :eyes: x1_

**Attachments:**
- [report.pdf](https://files.slack.com/files-pri/.../report.pdf)
- [screenshot.png](https://files.slack.com/files-pri/.../screenshot.png)

---

## 10:15:00 @bob
...
```

**设计要点**:
- frontmatter 包含完整结构化元数据，方便下游过滤/聚合
- 标准 Markdown，无 Obsidian 特有语法
- Thread reply 用引用块折叠
- 附件只保留 Slack 原始 url_private 链接，不下载到本地

---

## 四、macOS 实施步骤

### 1. 安装 slackdump
```bash
brew install rusq/tap/slackdump
slackdump version
```

### 2. 认证（一次性，无需 Admin）
```bash
slackdump workspace new <你的工作区名称>
```
按提示从浏览器复制 d-cookie 和 token。

### 3. 创建目录并放置脚本
```bash
mkdir -p ~/SlackArchive/archive ~/SlackArchive/raw ~/SlackArchive/scripts
```
将 sqlite_to_raw.py 和 daily_slack_backup.sh 放到 scripts/ 目录。

编辑 daily_slack_backup.sh，修改 WORKSPACE_NAME 为实际工作区名。

### 4. 首次全量运行
```bash
slackdump archive --workspace <工作区名> -o ~/SlackArchive/archive

python3 ~/SlackArchive/scripts/sqlite_to_raw.py \
  ~/SlackArchive/archive/slackdump.sqlite \
  ~/SlackArchive/raw
```

### 5. 设置每日定时任务

**方式 A: cron（简单）**
```bash
chmod +x ~/SlackArchive/scripts/daily_slack_backup.sh
crontab -e
# 添加：
0 3 * * * /Users/YOURNAME/SlackArchive/scripts/daily_slack_backup.sh
```

**方式 B: launchd（更原生）**
创建 ~/Library/LaunchAgents/com.slackbackup.daily.plist，配置 ProgramArguments 指向脚本，StartCalendarInterval 设为每天 3:00，然后 launchctl load。

---

## 五、增量逻辑

| 层级 | 机制 |
|------|------|
| **SQLite 层** | slackdump resume 只拉取上次之后的新消息，断网后重新 resume 不会重复 |
| **Markdown 层** | 脚本判断 raw/YYYY-MM-DD/channel.md 是否已存在。历史日期（非今天）且文件已存在 → 跳过。只有当天的文件会被覆盖更新 |

---

## 六、关键注意事项

1. **企业 Workspace 安全告警**: 部分 Enterprise Grid 会检测自动化访问并通知 Admin。建议先在非关键频道小范围测试。
2. **Free 计划 90 天限制**: slackdump 无法突破 Slack 服务端限制，只能归档当前可见消息。尽早开始每日跑，避免数据过期。
3. **附件 URL 有效期**: url_private 链接需要有效 Slack 认证才能访问。下游 skill 如需读取附件内容，需带上同样的认证 cookie。
4. **存储空间**: 只存消息文本 + URL，不下载附件，空间占用很小（日均几 MB 级别）。

---

## 七、脚本文件

- sqlite_to_raw.py — 核心转换脚本
- daily_slack_backup.sh — macOS 定时备份脚本
