English | [简体中文](README_CN.md)

# arxivsub-skill

A suite of three Claude Code Skills for **arXivSub** — search papers, analyze the literature, and manage your personal library, all in plain language without leaving your terminal. arXivSub aggregates arXiv and 15+ leading conferences (CVPR, NeurIPS, ICLR, ICML, EMNLP, and more) with AI-generated summaries.

| Skill | What it does |
|-------|--------------|
| **arxivsub-skill** (search) | Find and read the latest papers across arXiv and top conferences by topic. |
| **arxivsub-insight** (analytics) | Build trend charts, rankings, and breakdowns over the corpus — the same pivot engine as the website's Custom Chart. |
| **arxivsub-library** (library) | Save/bookmark papers, add notes, set reading status, and organize them into collections. |

All three are driven by natural language and share a single API key.

# Demo

[Watch the demo video](https://www.xiaohongshu.com/discovery/item/69b6575500000000210071b1?source=webshare&xhsshare=pc_web&xsec_token=AB4EGI1n2ItI7bd0MDv1JOFfRH1JfHkjRA--QS2hdaaAk=&xsec_source=pc_share)

# What you can ask

Once configured, just describe what you want in natural language:

- **Search** — "Find the latest papers on GNN + LLM" · "Any recent work on 3D Gaussian Splatting?"
- **Insight** — "How has interest in diffusion models trended over the past 3 years?" · "Top institutions in reinforcement learning"
- **Library** — "Save this paper to my to-read collection" · "What have I saved so far?"

# API Key

- Get your API Key from the Skills page (after signing in) on [arXivSub](https://arxivsub.comfyai.app/).
- The **same key** authenticates all three skills (`ARXIVSUB_SKILL_KEY`).

# Claude Code Configuration Tutorial

Follow the steps below to set up the skills in Claude Code.

## Step 1: Create workspace and folder structure

Create a folder as your workspace, then create the skill folders under `.claude/skills/`. Expected structure:

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

### Quick Start
You don’t need to create the structure manually.
Simply download the workspace zip file from this repository (or from the Skills page on arXivSub) and extract it. The archive already contains the correct directory layout.

⚠️ Note:
- The files .env and .claude are hidden files.
- Make sure your system is configured to show hidden files, otherwise you may not see them after extraction.

## Step 2: Set API key

Create a .env file (recommended) in the workspace root, or use export in your shell. The same key works for all three skills.

Option A .env (recommended):
```
ARXIVSUB_SKILL_KEY=your_key_here
```

Option B export:
```
export ARXIVSUB_SKILL_KEY=your_key_here
```

## Step 3: Start Claude and ask
Open Claude Code in this workspace, then ask in natural language. For example:
```
"Help me find the latest papers on GNN+LLM"
"How has interest in diffusion models trended over the last 3 years?"
"Save that first paper to my to-read collection"
```
