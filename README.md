# 夜秣小说生成器

> 一句灵感进去，一整章能打的成稿出来。

![Version](https://img.shields.io/badge/version-2.1.0-blue) ![Platform](https://img.shields.io/badge/平台-WorkBuddy-purple) ![Store](https://img.shields.io/badge/SkillHub-已上架-green) ![License](https://img.shields.io/badge/license-GPL--3.0-orange)

**夜秣小说生成器**是一个中文小说创作技能，跑在 [WorkBuddy](https://www.workbuddy.cn) 里。它把"写一篇小说"拆成了一座流水线：立根基 → 锁人设 → 卡质量 → 收伏笔，专治 AI 写长篇的三大绝症——**人设崩、伏笔断、水字数**。

## ✨ 它解决什么

| AI 写长篇的绝症 | 本技能的解法 |
|---|---|
| 写到 20 章主角性格变了 | **角色边界卡**：人设刚性约束，防 OOC 崩坏 |
| 前面埋的雷后面全忘了 | **伏笔台账 + 角色活档案**：长篇连贯性全流程管控 |
| 章章注水、毫无爽点 | **硬卡点门禁**：低质章节直接拦截，过不了闸不发车 |
| 句子干瘪、AI 味十足 | **行文质感校对表**：逐段校句子读感 |
| 换个题材就不会写了 | **可插拔风格包** + 9 份网文知识库（技法/桥段/爽点/命名/裁决） |

## 🚀 快速开始

**方式一：SkillHub 一键装（推荐）**

在 WorkBuddy 的 SkillHub 技能市场搜索 `yemo-novel-generator`，或直接下载：

```
https://api.skillhub.cn/api/v1/download?slug=yemo-novel-generator
```

**方式二：手动安装**

把本仓库克隆到 WorkBuddy 技能目录：

```bash
git clone https://github.com/mcm369568095-hash/yemo-novel-generator.git
```

## 📖 怎么用

对 WorkBuddy 说一句就行：

- 「帮我写一篇都市修仙小说，第一章」
- 「续写上一章，主角要打脸」
- 「生成一个玄幻故事大纲」
- 「把这段文笔精修一下」

## 📁 目录结构

```
夜秣小说生成器/
├── SKILL.md                  # 技能主流程
├── styles/                   # 可插拔风格包
└── references/               # 方法论参考（边界卡/伏笔台账/质量闸门…）
    └── knowledge/            # 9 份网文写作知识库（CSV）
```

## 📜 License 与致谢

本技能整体以 [GPL-3.0](./LICENSE) 协议开源。

`references/knowledge/` 下的 9 份 CSV 写作知识库改编自开源项目 [webnovel-writer](https://github.com/lingfengQAQ)（作者 lingfengQAQ，GPL-3.0），特此致谢。

---

**作者**：夜秣 ｜ 更多 AI 实战技能，微信公众号搜「**夜秣AI创业**」
