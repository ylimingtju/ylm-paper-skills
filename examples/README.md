# 自编示例与行为检查 / Synthetic examples and behavior checks

这些材料用于演示编辑流程，不含真实论文、实验结果或外部文献。`input.tex` 与 `revised.tex` 是可独立编译的简短英文示例；后者是一次遵守模块边界的人工可审阅修订，不是对未来模型输出的保证。

These materials demonstrate an editing workflow. They contain no real manuscript, experimental results, or external references. `input.tex` and `revised.tex` are short standalone LaTeX examples. The revision is an inspectable example that follows the module boundaries, not a guarantee about future model responses.

## 1. 语言 / Language

```text
$ylm-paper-language 只修正下面一句的语法，保留科学含义：The heuristic do not guarantees optimality.
$ylm-paper-language Fix only the grammar in this sentence, preserving the scientific claim: The heuristic do not guarantees optimality.
```

修订 / Revision: `The heuristic does not guarantee optimality.`

无最优性保证仍然保留，不增加性能评价。The absence of an optimality guarantee is preserved; no performance claim is added.

## 2. 去模板表达 / Formulaic wording

```text
$ylm-paper-deai 检查 input.tex 的空泛表达，只给建议，不修改文件。
$ylm-paper-deai Review empty claims in input.tex. Suggest edits only; do not edit files.
```

发现 / Finding: `The analysis offers valuable insights.` 没有给出可核查内容，建议删除；不能补造具体结论来替代。The sentence supplies no checkable content. Suggest deletion without inventing a result to replace it. A review-only request must leave the file unchanged.

## 3. 信息顺序 / Information order

```text
$ylm-paper-flow 允许调整本节内的信息顺序，把符号解释放到公式之前。保持数学条件与结论。
$ylm-paper-flow Move the notation definition before the equation within this section. Preserve all mathematical conditions and claims.
```

修订示例将 $\OPT$ 的解释移到界之前。没有调整章节，没有更改有效下界、可行解上界或最小化条件。

The revision moves the definition of $\OPT$ before the bound. It does not reorder sections or change the valid lower bound, feasible-solution upper bound, or minimization condition.

## 4. 一致性与科学疑问 / Consistency and scientific ambiguity

```text
$ylm-paper-check 只审查这两句：A) The heuristic does not guarantee optimality. B) The heuristic always returns an optimal solution.
$ylm-paper-check Review only these two statements: A) The heuristic does not guarantee optimality. B) The heuristic always returns an optimal solution.
```

应报告两句的保证强度存在冲突，给出双方原文并交由作者判断。不能自行删掉一句或选择一种结论。

Report the conflicting guarantee claims, quote both statements, and ask the author to resolve them. Do not delete a statement or choose a conclusion on the author's behalf.

缺少工程的片段请求无法覆盖全文与编译；缺 TeX 引擎应报告环境限制。对 `The proposed rule improves the bound.`，需要先确认界的含义，不能猜测增大还是减小。`\cite{provided_key}` 仅作为标识符保留示例，不指向真实文献；缺外部材料时不宣称已验证引文支持关系。

A fragment without a project does not support claims about full-manuscript or compilation coverage. A missing TeX engine is an environment limit. In `The proposed rule improves the bound.`, the type and meaning of the bound need clarification. `\cite{provided_key}` is only an example of a protected identifier, not a real reference. Without external sources, do not claim to have checked citation support.

## 5. 综合修订 / Coordinated editing

```text
$ylm-paper-polish 直接在隔离副本中修订 input.tex 的语言、空泛表达和信息顺序，保存为 revised.tex。保持公式、宏、标签、交叉引用与结论。
$ylm-paper-polish Edit an isolated copy of input.tex for grammar, empty wording, and information order. Save revised.tex. Preserve equations, macros, labels, cross-references, and claims.
```

`revised.tex` 给出示例结果。改动只有语法修正、删除无内容评价、前移符号定义。公式、宏定义、标签、交叉引用、无最优性保证及界成立条件均保留。综合入口只协调相关模块；未获得编辑授权时先交诊断与方案。

`revised.tex` shows the example result. Changes are limited to grammar, removal of an empty evaluation, and moving a notation definition earlier. The equation, macro definition, label, cross-reference, absence of an optimality guarantee, and conditions for the bound are preserved. The coordinator selects the relevant modules; without editing authorization, it first supplies a diagnosis and plan.

## 本地编译 / Local compilation

在本目录中运行 / From this directory:

```sh
latexmk -pdf -interaction=nonstopmode -halt-on-error -outdir=/absolute/temp/input input.tex
latexmk -pdf -interaction=nonstopmode -halt-on-error -outdir=/absolute/temp/revised revised.tex
```

输出目录应事先创建且位于隔离工作目录。编译用于核对示例的 TeX 与交叉引用，不证明 skill 的全部行为正确；语言任务的结果仍需人读。

Create the isolated output directories first. Compilation checks the example's TeX and cross-references. It does not establish that every skill behavior is correct; editing results still need human review.
