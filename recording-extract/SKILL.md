---
name: recording-extract
description: Extract structured notes from already-transcribed recording text. Use when the user provides a Feishu/Lark Minutes link with a text record, a Feishu/Lark doc, a Word/TXT/Markdown transcript, or pasted transcript text, and asks to extract key content, summarize meeting records, organize customer/market feedback, or produce a structured extraction document. This skill does not perform audio or video transcription.
---

# Recording Extract

## Overview

Use this skill to turn recording transcripts into structured extraction notes. The input is assumed to already be text: a Feishu/Lark Minutes text record, Feishu/Lark document, Word/TXT/Markdown file, or pasted transcript.

Do not transcribe audio or video in this skill. If the user provides media files, ask for the transcript or use another workflow outside this skill.

## Workflow

1. **Acquire text**
   - Feishu/Lark Minutes: obtain the text record / transcript when available. If an API transcript download fails, use the visible "text record" page content when accessible.
   - Feishu/Lark documents: use the Lark document tools when available.
   - Word/TXT/Markdown/local documents: read the document text directly.
   - Pasted text: use the pasted content directly.

2. **Classify the content type**
   - Internal problem-discussion meeting: focus on the problem, background/reasons, improvement direction, and next actions.
   - Internal review/summary meeting: focus on review content, conclusions, lessons, and improvement plans.
   - External dialogue: focus on market information, customer feedback, cooperation needs, business opportunities, and suggestions for product/sales/service/operations.

3. **Correct obvious transcript errors**
   - First check `references/keyword-corrections.md`.
   - If the user has an Obsidian vault, Logseq vault, Markdown knowledge base, entity index, product index, customer list, or similar source, search it for candidate brands, products, customers, concepts, and model names.
   - Correct only errors with clear semantic evidence. Do not mechanically replace all similar-sounding words.

4. **Extract key content**
   - Preserve the original meaning and useful context.
   - Record important content in relatively detailed form; do not over-compress.
   - Keep important numbers inside their relevant context; do not create a separate number summary unless the user asks.
   - Emphasize improvements, suggestions, plans, responsibilities, follow-up items, and clear time nodes.
   - If no explicit next plan exists, do not force a "next steps" section.

5. **Output**
   - Default to Markdown with a clear title and sections.
   - Save locally when the user expects a file. Use a filename like `<source-title>_内容萃取.md`.
   - Export Word or PDF only when requested.

## Detailed Rules

Read `references/extraction-rules.md` when performing an extraction.

Read `references/keyword-corrections.md` when correcting transcript terms or when the text contains brands, product names, model numbers, customer names, or domain-specific vocabulary.

## Maintenance

When the user gives a new reusable requirement for transcript extraction, update this skill instead of relying only on conversation memory.

- Update `references/extraction-rules.md` for extraction scope, content focus, output structure, source-handling rules, or formatting rules.
- Update `references/keyword-corrections.md` for reusable term corrections, brand names, product names, model names, customer names, or knowledge-base lookup rules.
- Do not add one-off instructions that apply only to a single transcript unless the user explicitly says they should become a general rule.
- Keep the skill text portable for teammates. Avoid hard-coding one user's local paths, account names, or private project assumptions unless they are examples.
- Preserve the current scope: this skill handles text records and transcript documents, not audio/video transcription.

## Failure Handling

- If full transcript access fails but AI notes/chapters are available, produce a limited extraction only when useful and clearly mark the source limitation in the output.
- If a Feishu/Lark text record requires login or permission, ask the user to provide access, the text record link, or copied transcript text.
- Do not invent missing details, speaker identities, timelines, or action items.
