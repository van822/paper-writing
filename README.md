# Paper Writing

一个手动启用的 Codex skill，帮助起草、修改和检查学术论文，让研究问题、方法设计与贡献证据保持一致。默认使用中文沟通，论文正文沿用你指定的语言。

A manually invoked Codex skill for evidence-grounded academic writing and figure planning.

## 功能

| 任务 | 关注内容 |
| --- | --- |
| 摘要 | 具体问题、核心思想、量化结果与贡献 |
| 引言 | 研究背景、已有进展、研究缺口与本文工作 |
| 相关工作 | 研究路线分类、技术比较与贡献定位 |
| 方法 | 总体流程、问题定义、模块、公式与伪代码 |
| 实验 | 公平比较、主结果、消融、不确定性与适用范围 |
| 图表 | 动机图、方法图、结果表、曲线与图注的信息组织 |

skill 按当前任务读取对应指南，保留已有事实、数值、术语与结果边界，并标明尚缺少的证据。它提供写作和信息组织指导；文档排版、绘图与格式转换使用所在环境中合适的工具。

## 安装

在 Codex 对话中输入：

```text
$skill-installer 安装 https://github.com/van822/paper-writing/tree/main/skills/paper-writing
```

安装后可在后续对话中选择 `paper-writing`，或输入 `$paper-writing` 调用。如果技能列表尚未更新，重启 Codex 后再查看。

这是由 Markdown 和 YAML 构成的 skill，本身无需额外运行依赖。关于 skill 的安装与发现方式，可参考 [OpenAI 官方说明](https://learn.chatgpt.com/docs/build-skills)。

## 使用

本 skill 仅在主动选择或明确调用时启用，配置中保留 `allow_implicit_invocation: false`。

修改摘要：

```text
$paper-writing 请修改以下摘要，保留所有数值与结论范围，让问题、方法思想和实验结果的对应关系更清楚：

[粘贴摘要]
```

检查已有稿件：

```text
$paper-writing 请检查当前稿件的引言和实验部分，指出主要贡献缺少哪些证据，并给出具体位置与改法。
```

规划方法图：

```text
$paper-writing 请依据现有方法章节规划一张方法图，说明输入、输出、关键模块和信息流，并起草图注。
```

为获得准确结果，请提供相关原文、图表或可访问的文件，并说明目标章节、投稿要求和需要保留的结果边界。

## 目录

```text
skills/paper-writing/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── abstract.md
    ├── introduction.md
    ├── related-work.md
    ├── methods.md
    ├── experiments.md
    ├── figures.md
    └── sources.md
```

## 来源与许可

本 skill 依据六份论文写作与配图指南整理。来源文件名、页码、整理取舍与 SHA-256 校验值记录在 [来源说明](skills/paper-writing/references/sources.md) 中。原始 PDF 未随本仓库分发，使用 skill 无需这些 PDF。

整理后的 skill 文件采用 [MIT 许可证](LICENSE)。原始资料的权利归各自权利人所有。
