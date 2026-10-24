---
name: review-dimensions
purpose: 章节多维度审查清单；用于 Hook 12 硬卡点门禁 与 Hook 14 质量自查
---

# 多维度审查（review-dimensions）

> 解决「写完看着还行，细看全是漏洞」的问题。
> 事实审查维度借鉴自 webnovel-writer 的 reviewer agent（5 维），并补入文笔质感维度。
> 审查输出应为结构化问题清单，不写「总体好评」式空话。

<schema>

每条 issue 包含：
- `severity`：critical / high / medium / low
- `category`：setting / timeline / continuity / character / logic / prose / pacing
- `location`：第几段或具体引用
- `description`：问题描述
- `evidence`：原文引用或事实对比
- `fix_hint`：修复方向
- `blocking`：是否阻断（critical 默认 true）

阻断规则：存在任意 `blocking=true` 的 issue → 退回重写，不得输出。

</schema>

<dimensions>

## 1. 设定一致性（setting）
- 角色能力是否与当前境界/等级匹配
- 地点描述是否与已建立世界观一致
- 物品/货币/规则是否符合前文设定
- 新实体是否有明确名称与描写（便于后续识别）

## 2. 时间线（timeline）
- 本章时间是否与上章衔接（无回跳或有合理解释）
- 倒计时/截止日期是否正确推进
- 同一角色是否同时出现在两个地点

## 3. 叙事连贯（continuity）
- 上章钩子/未闭合问题是否在本章回应（允许部分兑现）
- 场景转换是否有过渡
- 情绪弧是否连续（上章愤怒 → 本章突然平静需有过渡）

## 4. 角色一致性（character）
- 对话风格是否符合角色声线
- 行为是否与已建立性格/动机一致
- 角色知识边界——是否使用了不该知道的信息
- 是否触发生成时加载的「角色刚性边界卡」红线
- 本章角色若有新侧面/新关系/暗线推进，是否回写进角色库活档案（见 `character-evolution.md`，红线只增不减）

## 5. 逻辑（logic）
- 因果关系是否成立
- 角色决策是否有合理动机
- 战斗/冲突结果是否符合已建立的力量对比

## 6. 文笔质感（prose）⭐ 融合新增
- 是否违反 `prose-quality.md`：连续 3 段同句式、情绪标签化、万能副词、章末安全着陆、大段纯解释
- 是否违反 `prose-polish-rules.md`：不是A而是B / 仿佛…又仿佛 / 某种意义上 / 与其说…不如说 / 装饰性破折号堆叠
- 感官锚点是否到位、节奏是否有变化

## 7. 节奏（pacing）
- 是否 800-1400 字一个脉冲（短章至少一次实质变化）
- 爽点/兑现密度是否达标（参考 `cool-points.md` 滚动窗口）
- 开头是否尽早进入冲突/风险/强情绪

## 8. 伏笔闭环（ledger）⭐ 新增
- 伏笔台账（`foreshadow-ledger.md`）中「待兑现+临近」项是否在近期章节安排兑现/推进
- 本章新埋伏笔是否登记、关联角色/暗线是否标清
- 红鲱鱼是否登记，避免与真伏笔混淆
- 角色库活档案是否随本章回写（新关系/新侧面留痕）

</dimensions>

<output_format>

逐维度给出结论，无问题也显式写 `pass`：

```json
{
  "chapter": 11,
  "issues": [
    {"severity": "high", "category": "continuity", "location": "第3段",
     "description": "上章钩子未回应", "evidence": "上章结尾承诺查铜扣，本章无提及",
     "fix_hint": "在伏笔场景补一句铜扣反应", "blocking": false}
  ],
  "dimension_results": [
    {"dimension": "setting", "conclusion": "pass"},
    {"dimension": "timeline", "conclusion": "pass"},
    {"dimension": "continuity", "conclusion": "发现1个问题：上章钩子未回应"},
    {"dimension": "character", "conclusion": "pass"},
    {"dimension": "logic", "conclusion": "pass"},
    {"dimension": "prose", "conclusion": "发现2个问题：连续同句式、万能副词"},
    {"dimension": "pacing", "conclusion": "pass"}
  ]
}
```

</output_format>
