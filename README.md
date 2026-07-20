# recording-extract

Codex skill for extracting structured notes from already-transcribed recording text.

## Scope

Use this skill when the input is text, such as:

- Feishu/Lark Minutes text records
- Feishu/Lark documents
- Word, TXT, or Markdown transcript files
- Pasted transcript text

This skill does not transcribe audio or video.

## What It Does

- Classifies the transcript type before extraction.
- Preserves important content with useful context.
- Keeps important numbers in the relevant content instead of creating a separate number summary.
- Records improvement suggestions, action plans, responsibilities, and explicit time nodes when present.
- Corrects obvious transcript term errors using a maintained correction list and, when available, an Obsidian or similar knowledge base.

## Install

Copy the `recording-extract` folder into your Codex skills directory, for example:

```text
~/.codex/skills/recording-extract
```

Restart Codex after installing the skill.
