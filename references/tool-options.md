# Tool Options

Load this file when collecting source material from a Douyin or Xiaohongshu link.

## Local Skills First

- Use `feishu-skill` for Feishu document creation, updates, image uploads, and document search.
- Use `media-crawler` when the task is larger-scale public data collection and the user accepts crawler setup/login requirements.
- Do not use `xiaohongshu-upload` or `douyin-upload` for analysis; those skills are for publishing, not extraction.

## Xiaohongshu

Preferred capabilities:

- Read a single note URL.
- Extract title, body text, cover/images, author, publish time, visible stats, comments, and tags.
- Support viral/packaging analysis when available.

Candidate open-source tools to consider installing or using if already present:

- `lucasygu/redbook`: good fit for `read`, `analyze-viral`, and viral-template style analysis.
- `jobsonlook/xhs-mcp`: useful as an MCP extraction layer for note search, note details, comments, and cover URLs.
- `NanmiCoder/MediaCrawler`: useful for broader Xiaohongshu crawling and result export, but heavier than a single-link analysis.

If direct extraction fails, ask the user for a screenshot of the note, copied body text, and visible comments. Continue with evidence labels.

## Douyin

Preferred capabilities:

- Resolve short share links.
- Extract title/description, author, cover or first frame, visible stats, publish time, comments, and video transcript/OCR if available.
- Preserve source evidence for claims.

Candidate open-source tools to consider installing or using if already present:

- `Rimagination/dy-note`: useful for Codex-style evidence-based Douyin notes, transcript, metadata, comments, and keyframe/OCR workflows.
- `yzfly/douyin-mcp-server` or `@yc-w-cn/douyin-mcp-server`: useful as a Douyin MCP extraction/transcription layer.
- `NanmiCoder/MediaCrawler`: useful for broader Douyin crawling and result export, but heavier than a single-link analysis.

If transcript/OCR is unavailable, analyze the title, cover, visible metadata, and user-provided screenshots only. Do not invent spoken content.

## Installation Rule

When a required crawler/MCP package is missing and network installation is needed, request user approval before installing. Prefer the smallest tool that satisfies the current link and avoid setting up bulk crawlers for a one-link teardown.
