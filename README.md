# recording-extract

这是一个面向 AI Agent 的录音文字萃取规则包，也兼容 Codex Skill 结构。

使用者可以在 Codex 中把它作为 Skill 安装；如果使用其他 Agent，也可以直接让 Agent 读取 `recording-extract/SKILL.md` 和 `recording-extract/references/` 下的规则文件。

## 适用范围

当输入内容已经是文字时使用本规则包，例如：

- 飞书妙记的【文字记录】
- 飞书文档
- Word、TXT、Markdown 等录音转写稿
- 用户直接粘贴的转写文本

本规则包不负责音频或视频转写。

## 能做什么

- 先判断内容类型，再进行萃取。
- 对重点内容作相对详细的记录，不做过度压缩。
- 忠于原文意思，不做无依据发散。
- 将重要数值保留在对应上下文中，不单独做数值汇总。
- 重点记录问题、改善建议、后续计划、责任分工和明确时间节点。
- 根据固定误词表，以及可选的 Obsidian/Markdown 知识库，纠正明显的转写误词。

## 使用方式

### Codex

将 `recording-extract` 文件夹复制到 Codex 的 skills 目录中，例如：

```text
~/.codex/skills/recording-extract
```

复制完成后，重启 Codex 以加载 Skill。

### 其他 Agent

如果使用的不是 Codex，可以采用以下方式：

1. 将本仓库下载到本地。
2. 在 Agent 的系统提示词、项目规则或知识文件中引用：
   - `recording-extract/SKILL.md`
   - `recording-extract/references/extraction-rules.md`
   - `recording-extract/references/keyword-corrections.md`
3. 要求 Agent 按这些规则处理录音转写稿、飞书妙记文字记录或文档内容。

可直接使用类似提示：

```text
请读取 recording-extract/SKILL.md，并按 references 中的萃取规则和误词校正规则，处理我提供的录音转写文字。
```

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
- 单个文件的临时要求不建议写入规则包；只有可复用的通用要求才应维护进规则文件。
