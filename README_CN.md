[English](README.md) | 简体中文

# arxivsub-skill

面向 **arXivSub** 的三件套 Claude Code Skill —— 搜索论文、分析文献、管理个人库，全部用自然语言完成，不必离开终端。arXivSub 汇聚了 arXiv 与 15+ 顶级会议（CVPR、NeurIPS、ICLR、ICML、EMNLP 等）及其 AI 摘要。

| Skill | 作用 |
|-------|------|
| **arxivsub-skill**（搜索） | 按主题在 arXiv 与各大会议中查找并阅读最新论文。 |
| **arxivsub-insight**（分析） | 生成趋势图、排名、拆分统计 —— 与网页版 Custom Chart 同一套透视引擎。 |
| **arxivsub-library**（个人库） | 收藏论文、添加笔记、标记阅读状态、整理到合集中。 |

三者均由自然语言驱动，并共用同一个 API Key。

# 演示

[观看演示视频](https://www.xiaohongshu.com/discovery/item/69b6575500000000210071b1?source=webshare&xhsshare=pc_web&xsec_token=AB4EGI1n2ItI7bd0MDv1JOFfRH1JfHkjRA--QS2hdaaAk=&xsec_source=pc_share)

# 你可以这样问

配置完成后，用自然语言描述你想做什么即可：

- **搜索** —— “帮我找一下 GNN+LLM 相关的最新论文” · “最近有没有 3D Gaussian Splatting 的工作？”
- **分析** —— “扩散模型近三年的热度趋势如何？” · “强化学习方向发文最多的机构有哪些？”
- **个人库** —— “把这篇论文存到我的‘待读’合集” · “我到目前都收藏了哪些论文？”

# API Key

- 在 [arXivSub](https://arxivsub.comfyai.app/) 登录后，于 Skills 页面获取你的 API Key。
- **同一个 Key**（`ARXIVSUB_SKILL_KEY`）即可认证全部三个 Skill。

# Claude Code 配置教程

按以下步骤在 Claude Code 中配置这些 Skill。

## 第一步：创建工作区与目录结构

先创建一个文件夹作为工作区，再在 `.claude/skills/` 下创建各个 Skill 的目录。期望结构如下：

```
claude-workspace
├── .claude
│   └── skills
│       ├── arxivsub-skill
│       │   ├── SKILL.md
│       │   └── scripts
│       │       ├── fetch.py
│       │       └── search.py
│       ├── arxivsub-insight
│       │   ├── SKILL.md
│       │   └── scripts
│       │       └── insight.py
│       └── arxivsub-library
│           ├── SKILL.md
│           └── scripts
│               └── library.py
└── .env
```

### 快速开始
无需手动创建上述结构。
直接从本仓库（或 arXivSub 的 Skills 页面）下载工作区 zip 并解压即可，压缩包内已包含正确的目录结构。

⚠️ 注意：
- `.env` 和 `.claude` 为隐藏文件/目录。
- 请确保系统已设置为显示隐藏文件，否则解压后可能看不到它们。

## 第二步：设置 API Key

在工作区根目录创建 `.env` 文件（推荐），或在当前 shell 中使用 export。同一个 Key 对三个 Skill 都有效。

方式 A：.env（推荐）：
```
ARXIVSUB_SKILL_KEY=你的密钥
```

方式 B：export：
```
export ARXIVSUB_SKILL_KEY=你的密钥
```

## 第三步：启动 Claude 并提问
在本工作区中打开 Claude Code，然后用自然语言提问即可。例如：
```
"帮我找一下 GNN+LLM 相关的最新论文"
"扩散模型近三年的热度趋势如何？"
"把第一篇论文存到我的‘待读’合集"
```
