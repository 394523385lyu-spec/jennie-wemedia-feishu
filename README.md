# Jennie- wemedia-feishu

Codex skill for turning Douyin and Xiaohongshu links into structured Feishu Bitable topic-library records.

## What It Does

- Detects Douyin and Xiaohongshu links.
- Extracts public metadata, cover images, visible stats, comments, and keyframes when available.
- Analyzes cover, title, opening hook, content structure, comment signals, reusable templates, and follow-up topics.
- Writes records into separate Feishu Bitable libraries:
  - `抖音选题库`
  - `小红书选题库`
- Stores at least the cover image for every record, and 3-6 keyframes when available.

## Install

Copy this folder into your Codex skills directory:

```bash
mkdir -p "$HOME/.codex/skills"
cp -R jennie-wemedia-feishu "$HOME/.codex/skills/"
```

Then restart Codex or reload skills.

## Feishu Setup

This skill expects Feishu document/bitable access through an existing Feishu tool or an authorized Feishu Open API workflow. It does not include credentials.

When available, the local Bitable configuration is read from:

```text
$HOME/Desktop/短视频多维表格配置.json
```

The file should contain app/table identifiers for the Douyin and Xiaohongshu topic libraries. Do not commit private tokens, app secrets, or user access tokens.

## Skill Name

Internal Codex skill name:

```text
jennie-wemedia-feishu
```

UI display name:

```text
Jennie- wemedia-feishu
```

## License

MIT
