---
name: jennie-wemedia-feishu
description: Analyze Douyin or Xiaohongshu links and turn them into structured content teardown records in Feishu Bitable topic libraries. Use when the user pastes a Douyin/TikTok China or Xiaohongshu/RED note link and asks to拆解封面、标题、钩子、脚本结构、评论需求、爆款模板、选题复盘, or wants the analysis created/appended in Feishu. Prefer separate Feishu Bitable libraries for 抖音选题库 and 小红书选题库.
---

# Jennie Wemedia Feishu

## Overview

Use this skill to convert one or more Douyin or Xiaohongshu links into reusable content insight records in Feishu. The output should be practical for content production: extract observable material, separate evidence from inference, analyze hooks and structure, then write to the correct Feishu Bitable topic library.

## Workflow

1. Identify the platform and task scope.
   - Xiaohongshu: `xiaohongshu.com`, `xhslink.com`, `xhs.cn`, `小红书`.
   - Douyin: `douyin.com`, `v.douyin.com`, `iesdouyin.com`, `抖音`.
   - If the user supplies multiple links, process them as a batch and include a cross-case pattern summary.

2. Collect source material.
   - Prefer direct page/API extraction when available.
   - If a tool is already installed, follow [tool-options.md](references/tool-options.md).
   - Capture: original link, resolved link, author, title/caption, cover image or first frame, visible stats, publish time, body text, transcript or OCR, top comments, and downloadable image URLs only when allowed by the source and tool.
   - If login, anti-bot, expired links, or platform restrictions block extraction, ask the user for screenshots, exported text, or a copied share page. Do not pretend missing fields were observed.

3. Analyze the material.
   - Use the report structure in [report-template.md](references/report-template.md).
   - Label every point as one of: `原文/画面证据`, `评论证据`, `数据观察`, or `推断`.
   - Keep the analysis focused on repeatable creative mechanics, not generic praise.

4. Create or update the Feishu topic library.
   - Prefer Feishu Bitable, not a normal document table.
   - Use separate libraries: `抖音选题库` for Douyin links and `小红书选题库` for Xiaohongshu links.
   - Use the local config file `$HOME/Desktop/短视频多维表格配置.json` when present; it stores app/table IDs for the two libraries.
   - If the Bitable libraries do not exist, create them in the user's Feishu root folder and use matching schemas.
   - Every record must include at least the cover image. When possible, include 3-6 keyframes showing the opening hook, rhythm, turning points, and ending.
   - Use `feishu-skill` for available Feishu operations. If `feishu-tool` lacks Bitable support and the user has authorized direct Open API use, call Feishu Open API with the authorized cache and do not print tokens or secrets.
   - Keep source links in a field for traceability.

5. Return a short completion note with the Feishu link or token and any extraction gaps.

## Analysis Requirements

For each link, include:

- Basic metadata: platform, author, title/caption, publish time if visible, visible stats, source URL.
- Cover teardown: first-eye information, visual subject, text overlay, emotional promise, contrast point, and what the cover hides or reveals.
- Title teardown: curiosity gap, target audience, pain/benefit, specificity, numbers, conflict, and rewrite options.
- Hook teardown: first 3 seconds or first screen, opening question/claim/scene, why it stops scrolling, and risk of overclaiming.
- Content structure: sequence of beats, proof points, examples, CTA, pacing, and where attention may drop.
- Comment and audience signals: repeated questions, objections, desire language, alternate angles, and usable follow-up topics.
- Reusable template: `适合复刻的人群/场景`, `可复刻公式`, `替换变量`, `不建议照搬的部分`.
- Production recommendations: 3-5 next video/note angles, suggested covers, suggested titles, and a stronger opening hook.

For batch analysis, add:

- Common patterns across links.
- Differences between Douyin and Xiaohongshu packaging.
- A ranked list of the most reusable templates.
- A content calendar suggestion if the user asks for execution planning.

## Feishu Bitable Fields

Use these fields for both `抖音选题库` and `小红书选题库`:

- `选题标题`
- `状态` with options: `待选题`, `已制作`, `已发布`, `复盘完成`
- `采集日期`
- `封面/关键帧`
- `平台`
- `来源链接`
- `账号`
- `原文/标题`
- `发布时间`
- `时长秒`
- `点赞数`, `评论数`, `收藏数`, `分享数`
- `热点信息`
- `标签`
- `一句话判断`
- `封面拆解`
- `标题/钩子拆解`
- `开头钩子`
- `内容结构`
- `评论区信号`
- `可延展选题`
- `复刻模板`
- `下一步建议`
- `证据/采集状态`

## Safety And Boundaries

- Analyze public or user-provided content only.
- Do not bypass paywalls, private accounts, or access controls.
- Do not download or re-upload media unless the user has rights and the tool workflow permits it.
- Distinguish inspiration and structure analysis from copying. Recommend original rewrites and new angles.
- If platform data appears stale or incomplete, say so in the Feishu report.
