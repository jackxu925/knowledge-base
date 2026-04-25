# Knowledge - 个人知识库

基于 Andrej Karpathy 的 LLM Wiki 方法论构建。

## 目录结构

```
knowledge-base/
├── CLAUDE.md              # 操作蓝图（L3 模式层）
├── VAULT-INDEX.md         # 实时仪表盘
├── README.md              # 本文件
│
├── raw/                   # L1 原始层（人类写入，LLM 只读）
│   ├── articles/          # 网页剪藏文章
│   ├── papers/            # PDF、学术论文
│   ├── repos/             # 代码仓库笔记
│   ├── transcripts/       # 会议记录、播客转录
│   ├── data/              # CSV、JSON、基准测试结果
│   └── assets/            # 图片附件
│
├── wiki/                  # L2 维基层（LLM 写入，人类只读）
│   ├── index.md           # 主目录
│   ├── log.md             # 活动日志
│   ├── hot.md             # 热缓存
│   ├── overview.md        # 总览
│   ├── sources/           # 来源摘要
│   ├── entities/          # 人物、公司、产品、组织
│   ├── concepts/          # 思想、方法、技术、理论
│   ├── comparisons/       # 分析性比较
│   └── syntheses/         # 综合分析
│
└── .obsidian/             # Obsidian 配置
    ├── app.json
    ├── templates/         # 模板文件
    └── plugins/           # 插件配置
```

## 使用方法

### 1. 投放原始资料
将文章、PDF、笔记等放入 `raw/` 对应目录。

### 2. 摄取（Ingest）
对 Claude 说：`ingest raw/articles/xxx.md`

Claude 会：
- 读取原始资料
- 创建来源摘要（`wiki/sources/`）
- 更新概念/实体页（`wiki/concepts/`、`wiki/entities/`）
- 追加日志（`wiki/log.md`）

### 3. 查询（Query）
直接提问，Claude 会：
- 读取 `wiki/index.md`
- 定位相关页面
- 带 `[[链接]]` 引用回答

### 4. 检查（Lint）
对 Claude 说：`lint`

Claude 会扫描知识库健康状况。

## 关键规则

1. **人类写 `raw/`，LLM 写 `wiki/`**
2. **使用 Wikilink `[[页面名]]`**，不要用 Markdown 链接
3. **所有 wiki 页面必须包含 YAML Frontmatter**
4. **每次摄取后提交 Git**

## 推荐的 Obsidian 插件

- **Dataview**：将 frontmatter 作为数据库查询
- **Templater**：使用标准模板创建新页面
- **Graph View**：可视化知识网络
- **Obsidian Git**：自动备份到 Git

## 开始使用

1. 打开 Obsidian，选择 `C:\Users\徐衡\SynologyDrive\knowledge-base` 作为仓库
2. 安装社区插件：Dataview、Templater
3. 将资料放入 `raw/` 目录
4. 对 Claude 说 `ingest raw/xxx.md`
