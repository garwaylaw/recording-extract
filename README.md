# recording-extract

这是一个用于 Codex 的录音文字萃取 Skill。

## 适用范围

当输入内容已经是文字时使用本 Skill，例如：

- 飞书妙记的【文字记录】
- 飞书文档
- Word、TXT、Markdown 等录音转写稿
- 用户直接粘贴的转写文本

本 Skill 不负责音频或视频转写。

## 能做什么

- 先判断内容类型，再进行萃取。
- 对重点内容作相对详细的记录，不做过度压缩。
- 忠于原文意思，不做无依据发散。
- 将重要数值保留在对应上下文中，不单独做数值汇总。
- 重点记录问题、改善建议、后续计划、责任分工和明确时间节点。
- 根据固定误词表，以及可选的 Obsidian/Markdown 知识库，纠正明显的转写误词。

## 安装方式

将 `recording-extract` 文件夹复制到 Codex 的 skills 目录中，例如：

```text
~/.codex/skills/recording-extract
```

复制完成后，重启 Codex 以加载 Skill。

## 文件结构

```text
recording-extract/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── extraction-rules.md
    └── keyword-corrections.md
```

## 维护方式

- 萃取规则、内容分类、输出结构等，维护在 `references/extraction-rules.md`。
- 常见误词、品牌名、产品名、型号名、客户名等校正规则，维护在 `references/keyword-corrections.md`。
- 如果使用者有 Obsidian 或类似 Markdown 知识库，可在处理时检索知识库中的实体、概念、产品和客户名称，用于辅助判断误词校正。
- 单个文件的临时要求不建议写入 Skill；只有可复用的通用要求才应维护进 Skill。
