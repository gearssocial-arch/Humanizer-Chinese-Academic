---
name: writing-anti-ai
description: >
  以 Humanizer 为内核，审校或改写中英文文本中的 AI 式套话、虚假强调、机械节奏、格式模板、
  聊天残留和面向错误读者的重复解释，同时保持原意、事实、引文和作者声音。用于用户明确要求
  去除 AI 写作痕迹、humanize、改善机械感或进行终稿自然度审校。中文哲学与规范性学术文本
  只做表达层清理，不负责重建论证、贡献或证据；普通论文写作和一般润色不自动触发。
license: MIT
metadata:
  version: "2.0.0+humanizer.3.1.0"
  upstream: "blader/humanizer@0ef9fe5bc3572734fd3ae6c448fe00a30cd5dcf0"
---

# Writing Anti-AI

以 Humanizer 3.1.0 为通用内核，并增加中文表达与中文哲学学术文本的保护层。目标是让文本对读者更自然、具体和直接，不是规避 AI 检测器。

## 规则优先级

发生冲突时按以下顺序处理：

1. 用户明确意图、原文事实和给定来源；
2. 中文学术文本的论证、证据和术语保护；
3. Humanizer 的通用识别与改写规则；
4. 中文常见模式提示。

任何低层风格规则都不能推翻更高层约束。不得为了“更像真人”新增事实、反应、立场、引文、例子或作者没有表达的判断。

## 参考文件路由

- 每次使用本 Skill，先完整读取 [references/humanizer-core-v3.1.0.md](references/humanizer-core-v3.1.0.md)。这是主体工作流和 26 类模式的权威版本。
- 文本主要为中文时，再读取 [references/chinese-prose-adaptation.md](references/chinese-prose-adaptation.md)。
- 文本属于中文哲学、伦理学、科技伦理学或其他规范性学术写作时，必须再读取 [references/chinese-academic-guardrails.md](references/chinese-academic-guardrails.md)。
- Humanizer 上游许可证保存在 [references/LICENSE-humanizer.txt](references/LICENSE-humanizer.txt)。

不要加载与当前语言或文体无关的参考文件。

## 工作边界

本 Skill 可以：

- 删除没有信息增量的铺垫、重复结尾和聊天残留；
- 把虚假抬高、宣传语言和模糊权威改成来源允许的直接陈述；
- 修正由规则驱动的排比、破折号、标题、粗体和句段节奏；
- 在用户提供样文时匹配其稳定表达习惯；
- 在不改变含义的前提下合并、拆分或重排句子。

本 Skill 不可以：

- 替论文选择研究问题、中心论点、贡献叙事或规范立场；
- 把“检测到某个词”直接当成必须修改的证据；
- 删除真实异议、必要限定、概念区分、法律或安全提示；
- 改写直接引文，或擅自改变脚注、参考文献、数据和链接目标；
- 声称改写能够绕过 AI 检测器。

如果自然度问题实际来自论证缺口、来源不足或概念混乱，指出问题并停止在表达层，不用流畅文字掩盖实质缺陷。中文规范性学术文本需要实质修改时，交由 `chinese-normative-academic-writing` 处理。

## 交付

沿用 Humanizer 的 pasted、file 和 embedded 三种模式。学术文本默认同时报告：

- 做了哪些表达层修改；
- 哪些看似 AI 模式的结构因承担真实论证职责而保留；
- 是否发现超出本 Skill 权限的实质问题。

文件模式只修改正文表达，保留代码、路径、元数据、数据、引文、脚注标记和链接目标。嵌入其他写作流程时只返回该流程需要的最终文本，不重复展示审校过程。

## 来源与维护

通用内核来自 [blader/humanizer](https://github.com/blader/humanizer) 3.1.0，MIT License。中文适配与学术保护是本地扩展。更新上游时先比较版本差异，再迁移本地覆盖层；不得用整仓覆盖破坏中文学术边界。
