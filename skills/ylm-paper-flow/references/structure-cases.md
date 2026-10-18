# 结构编辑：边界与例子

下面是合成案例。修改不得引入输入之外的科学信息。

## 限制与主张放在一起

原文结构：

1. `Method A reduced mean runtime from 4.1 s to 3.2 s on the tested instances.`
2. 一段有关实例生成方法的说明。
3. `The comparison used a 60 s budget per instance and covers only deterministic processing times.`

允许方案：在原节内将第 3 段的预算和范围放到比较结果附近，保持生成方法说明的完整性。若第 3 段还限定其他结果，不能整体搬走使那些结果失去限定。不能改成 A 普遍优于其他方法，也不能将时限实验说成所有实例均已证最优。

## 合并重复内容前核对范围

“算法不保证全局最优性”和“时间限制可能阻止精确算法完成最优性证明”不是重复命题。前者涉及算法保证，后者涉及本次求解状态；即使两者都谈最优性也不能合并为一句模糊的“没有最优解”。

英文同理：`heuristic without an optimality guarantee` 与 `exact method stopped at the time limit` 必须区分。

## 审稿补丁的职责划分

原文：

> We compare A and B on deterministic instances.
>
> To address this concern, we clarify that the comparison excludes stochastic processing times.

仅去掉 `To address this concern, we clarify that` 是表达清理。将范围说明吸收到比较定义附近、判断两处限定是否完全等价并处理重复，是结构编辑。本模块可以在组织调整中去掉不可分割的回复口吻，但不借此开始全文词语清洗。

保留新增假设、必要限定、失败情形、负面结果、实验设置及引用。不把限制段落归为“防御性内容”后整体删除。

## 逻辑跳步只能标记

原文：`Runtime increases with n in our experiments. Therefore, the worst-case complexity is O(n^2).`

问题：经验曲线不构成最坏情况复杂度证明。保持原文并说明需要理论分析或作者授权修改结论；不能通过改连接词使该推理看似成立。

## 保留合理结构

- 问题定义之后给出符号，再给出模型，即使各段长度相近也可能合理。
- 公平实验要求各方法按相同顺序说明预算与参数。不要为了自然感打乱一项报告。
- 技术证明反复使用相同的分情况句式，可能反映真实证明结构。
- 独立章节承担不同职责；不要强制所有章节都增加总结段，或删除确实帮助导航的章节导语。

## 验收时自问

读者是否能从修改后文本找回原来的每项条件、证据、结论和归属？移动是否改变限定词作用域？删掉的内容是否确实与保留项同义同范围？修改是否仅让已有论证更清楚，而没有替作者补上未知环节？
