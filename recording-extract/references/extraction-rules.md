# Extraction Rules

## Input Scope

This skill handles text-only transcript materials:

- Feishu/Lark Minutes text records
- Feishu/Lark documents
- Word documents
- TXT or Markdown transcripts
- Pasted transcript text

It does not handle audio/video transcription.

## Rule Maintenance

When the user adds a new reusable extraction requirement, update the skill files:

- Put extraction logic, classification rules, source-handling rules, and output-format rules in this file.
- Put reusable misrecognition corrections and knowledge-base lookup rules in `keyword-corrections.md`.
- Keep single-document instructions out of the skill unless the user says the instruction should become a general rule.
- Keep rules portable for GitHub teammates. Prefer configurable examples over personal local paths.

## Content Classification

Classify the transcript before extracting.

### Internal Problem-Discussion Meeting

Prioritize:

- The problem itself
- Background and causes
- Constraints and disagreements
- Improvement direction
- Next actions, owners, and time nodes when stated

### Internal Review or Summary Meeting

Prioritize:

- Review facts and data
- Conclusions
- Lessons learned
- Improvement plans
- Replicable methods or cases

### External Dialogue

Prioritize:

- Market information
- Customer feedback
- Competitor information
- Cooperation demands
- Business opportunities
- Suggestions for products, sales, service, operations, or management

## Extraction Style

- Stay faithful to the transcript.
- Do not over-summarize key content.
- Do not add unsupported speculation.
- Reorder and structure content for readability without changing meaning.
- Remove obvious repetition and low-value chatter.
- Preserve context that helps the reader understand why a point matters.

## Numbers

Keep important numbers in context, including:

- Amounts
- Prices
- Quantities
- Dates and times
- Ratios
- Targets
- Completion rates
- Frequency and cycles
- Growth or decline ranges

Do not create a separate number-summary section unless the user asks.

## Improvements, Suggestions, and Plans

Record these carefully when present:

- Improvement direction
- Problem correction
- Suggestions
- Next plans
- To-do items
- Responsibilities
- Follow-up items
- Explicit time nodes

If the transcript does not explicitly mention next plans or follow-up arrangements, omit that section instead of inventing one.

## Suggested Markdown Structure

Use this structure flexibly:

```markdown
# <Title>｜内容萃取

## 基本信息

- 来源：
- 资料依据：
- 内容类型判断：

## 核心主线

...

## 重点内容

...

## 问题与原因

...

## 改善建议与后续安排

...

## 核心结论

...
```

Only include sections supported by the transcript.
