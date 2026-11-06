# Humanizer Chinese Academic

一个以 [blader/humanizer](https://github.com/blader/humanizer) 3.1.0 为主体内核的 Codex Skill。它保留 Humanizer 对 26 类 AI 写作模式的识别与改写流程，并增加两层本地扩展：

- 中文表达适配：处理中文背景式空转、抽象词堆叠、模板化并列、翻译腔和机械收束；
- 中文学术保护：保护哲学、伦理学与规范研究中的核心论证、必要限定、术语、引文、来源身份和作者立场。

它的目标是改善真实读者的阅读体验，不承诺规避 AI 检测器。

## 核心原则

1. 保持原意，不虚构事实、数字、日期、引文、来源或作者观点；
2. 一个模式只有在当前语境中造成信息空转、虚假抬高或机械重复时才构成修改理由；
3. 中文哲学论文中的真实概念区分、认识限定和规范限定优先于通用 Humanizer 规则；
4. 学术文本只做表达层清理，不用更流畅的文字掩盖论证缺口和来源不足；
5. 不为了“像真人”给学术文本添加情绪、幽默、第一人称或更强断言。

## 目录结构

```text
Humanizer-Chinese-Academic/
├── SKILL.md
├── LICENSE
├── NOTICE.md
├── agents/
│   └── openai.yaml
└── references/
    ├── humanizer-core-v3.1.0.md
    ├── chinese-prose-adaptation.md
    ├── chinese-academic-guardrails.md
    └── LICENSE-humanizer.txt
```

## 使用范围

适用于：

- 明确要求 humanize、去除 AI 写作痕迹或改善机械表达；
- 中英文终稿自然度审校；
- 中文哲学、伦理学、科技伦理学论文在论证稳定后的表达层清理。

不用于：

- 选择研究问题和中心论点；
- 重建论文论证、贡献或证据；
- 改写直接引文和参考文献；
- 规避 AI 检测器。

中文规范性学术文本需要实质修改时，应先使用领域学术写作流程，待论证与证据稳定后再调用本 Skill。

## 安装

将本仓库克隆或复制到 Codex Skills 目录，并确保文件夹名为 `writing-anti-ai`：

```text
~/.codex/skills/writing-anti-ai/
```

安装后可通过自然语言调用，例如：

```text
请在不改变事实、立场、必要限定和引文的前提下，清理这份文本的 AI 式套话与机械表达。
```

## 上游与许可证

通用内核来自 `blader/humanizer` 3.1.0，所用提交与本地扩展说明见 [NOTICE.md](NOTICE.md)。Humanizer 上游采用 MIT License，本仓库保留其版权和许可证文本。
