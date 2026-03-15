# arxivsub-skill
arxivsub-skill (a Claude Code Skill) helps you find papers on arXivSub effortlessly

# API Key

- Get your API Key from the Skills page (after signing in) on [arXivSub](https://arxivsub.comfyai.app/).
- Use it to authenticate with the ArxivSub Skill API when using Claude Code.

# Claude Code Configuration Tutorial

Follow the steps below to set up the skill in Claude Code.

## Step 1: Create workspace and folder structure

Create a folder as your workspace, then create the path `.claude/skills/arxivsub-skill` (and `scripts` under it). Expected structure:

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

### Quick Start
You don’t need to create the structure manually.
Simply download the workspace zip file from this repository and extract it. The archive already contains the correct directory layout.

⚠️ Note:
- The files .env and .claude are hidden files.
- Make sure your system is configured to show hidden files, otherwise you may not see them after extraction.

## Step 2: Set API key

Create a .env file (recommended) in the workspace root, or use export in your shell.

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
```
