[English](README.md) | 简体中文

# arxivsub-skill
arxivsub-skill（一款 Claude Code Skill）帮助你轻松在 arXivSub 上查找论文

# 演示

[观看演示视频](https://www.xiaohongshu.com/discovery/item/69b6575500000000210071b1?source=webshare&xhsshare=pc_web&xsec_token=AB4EGI1n2ItI7bd0MDv1JOFfRH1JfHkjRA--QS2hdaaAk=&xsec_source=pc_share)

# API Key

- 在 [arXivSub](https://arxivsub.comfyai.app/) 登录后，于 Skills 页面获取你的 API Key。
- 在使用 Claude Code 时，用该 Key 向 ArxivSub Skill API 进行认证。

# Claude Code 配置教程

按以下步骤在 Claude Code 中配置该 Skill。

## 第一步：创建工作区与目录结构

先创建一个文件夹作为工作区，再创建路径 `.claude/skills/arxivsub-skill`（以及其下的 `scripts` 目录）。期望结构如下：

```
claude-workspace
├── .claude
│   └── skills
│       └── arxivsub-skill
│           ├── SKILL.md
│           └── scripts
│               ├── fetch.py
│               └── search.py
└── .env
```

### 快速开始
无需手动创建上述结构。
直接从本仓库下载工作区 zip 并解压即可，压缩包内已包含正确的目录结构。

⚠️ 注意：
- `.env` 和 `.claude` 为隐藏文件/目录。
- 请确保系统已设置为显示隐藏文件，否则解压后可能看不到它们。

## 第二步：设置 API Key

在工作区根目录创建 `.env` 文件（推荐），或在当前 shell 中使用 export。

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
```
