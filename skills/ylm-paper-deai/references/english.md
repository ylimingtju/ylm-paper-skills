# English: content-led academic expression

Use these as editorial decisions, not a blacklist. Every replacement must be supported by the supplied text. Examples below are synthetic demonstrations, not scientific findings.

## What to inspect

- **Interchangeable openings and endings:** repeated `In this section`, `It is worth noting`, or generic implications that do not identify the local object. Keep roadmaps where they reduce navigation effort.
- **Unsupported praise and vague summaries:** `powerful`, `robust`, `comprehensive`, `promising`, or `the results demonstrate effectiveness` without a clear referent. A meaningful evaluative claim needs author judgment, not silent removal or invented measurements.
- **Mechanical connective logic:** `Furthermore`, `Therefore`, `Moreover`, repeated first/second/finally lists, and ornamental contrast. Identify the actual relation; if it is not established, do not invent one.
- **Punctuation scaffolding:** repeated setup-colon-explanation or dash-led interpretations. Change only where the scaffold adds empty packaging; preserve colons introducing real definitions or lists and dashes serving a clear purpose.
- **Rebuttal residue:** `To address this concern`, `we have added`, or `as suggested by the reviewer` in manuscript prose. Preserve the added information and distinguish manuscript prose from an actual response letter.
- **Local echoes:** repeated statements within a paragraph. Technical nouns may need repetition; eliminating their repeated names can create ambiguity.
- **Unnecessary syntactic load:** a delayed main clause, stacked relative clauses, distant qualifications or heavy nominalization can hide a precise claim. Prefer clear subjects, direct verbs and familiar nontechnical words when equally accurate. A long sentence alone is not evidence of AI use; identify the actual reading burden.

Repeated paragraph functions, detached limitations or several sections using the same argument sequence are structural findings. Record evidence and the information to retain; do not move paragraphs under the deai role.

## Worked examples

### Readable academic prose with complete technical scope

Input:
> In the experiments on 24 deterministic instances, the heuristic obtained a mean makespan of 81.6 under a time limit of 60 s per instance, whereas the baseline obtained 84.2 under the same limit, although these results do not establish a worst-case approximation guarantee.

Candidate, within the same paragraph:
> In experiments on 24 deterministic instances, both methods used a time limit of 60 s per instance. The heuristic obtained a mean makespan of 81.6; the baseline obtained 84.2. These results do not establish a worst-case approximation guarantee.

The original combines setup, two results and a theoretical limitation. Separating these tasks makes the comparison easier to follow. The instance scope, time limit, statistic, values, method identities and lack of an established worst-case guarantee remain intact. This is an available repair when the surrounding prose benefits from it, not a mandate to split every sentence of similar length. Do not replace makespan with a looser everyday term or add claims of significance or general superiority.

### Keep conditional claims conditional

Input:
> If every selected batch satisfies the capacity constraint and processing times are deterministic, then the construction procedure returns a feasible schedule.

Action: retain this clear conditional sentence unless context reveals a genuine reading problem. Do not split it into `Every selected batch satisfies the capacity constraint. Processing times are deterministic. The construction procedure returns a feasible schedule.` That version asserts the antecedents and drops the conditional relation. If a more complex sentence must be split, explicitly carry its original conditions forward to the conclusion.

### Remove packaging, retain qualification

Input:
> It is worth noting that the heuristic does not guarantee optimality. This is an important point to note when interpreting its results.

Candidate:
> The heuristic does not guarantee optimality.

Preserved: heuristic status and absent optimality guarantee. Removed: repeated instruction to notice the same limitation. Do not add a claim about solution quality or speed.

### Preserve the complete comparison

Input:
> Overall, the results show that, on the 20 tested instances, method A has a mean runtime of 3.2 s, compared with 4.1 s for method B.

Candidate:
> On the 20 tested instances, method A has a mean runtime of 3.2 s, compared with 4.1 s for method B.

Preserved: sample scope, arithmetic statistic, values, units, methods and comparison. No causal mechanism, significance claim or universal ranking is inferred.

### Absorb manuscript response language

Input (manuscript body):
> To address this concern, we clarify that Proposition 2 applies only when the processing times are deterministic.

Candidate:
> Proposition 2 applies only when the processing times are deterministic.

Preserved: exact proposition and necessary scope condition. If the paragraph is in a response letter, the response framing may be appropriate. If the condition belongs elsewhere in the manuscript, report a flow issue separately.

### Evidence is missing: retain and flag

Input:
> Our method is robust and achieves superior performance in realistic settings.

Action: identify the undefined robustness, comparator and setting; request the evidence or intended scope. Do not replace this with fabricated sparse-graph conditions, favorable runtime values, or a weaker scientific conclusion just to close a style issue.

## Negative controls: keep these when appropriate

- `The algorithm is heuristic and does not guarantee optimality.` It is a necessary limitation, not disposable negativity.
- `First, assign each job to a machine. Second, sequence the jobs on each machine.` Enumeration reflects an actual ordered procedure; preserve algorithm order.
- Several baseline paragraphs report the same fields in the same order. Parallel reporting supports a fair comparison; stylistic asymmetry is not a goal.
- Repeated `lower bound` distinguishes the same mathematical object. Do not cycle through `estimate`, `limit`, and `bound` for variety.
- `These observations are consistent with the hypothesis.` Do not turn observational support into proof or causation.

## Final editorial check

Can a reader recover the same assumptions, claims, attribution and limitations? Has each changed sentence become clearer or more specific using only existing information? After splitting, do conditions and citations still qualify the same claims? Avoid inflating a clear sentence to sound more academic or fragmenting a coherent argument into choppy assertions. If the only argument for an edit is a common word, punctuation mark or sentence/paragraph length, retain it.
