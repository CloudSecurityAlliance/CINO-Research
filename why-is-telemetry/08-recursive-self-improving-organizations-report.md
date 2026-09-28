# Recursive Self-Improving Organizations - Design Dimensions

This report captures the broader framework that emerged during the conversation. It is not intended to be the Circle News column. It is Labs material, future-report material, and a source for later AI-native workflow design.

## Central shift

A mature AI-native organization should not merely optimize a single fixed workflow. It should govern a portfolio of workflows, judgments, objectives, variants, and improvement strategies under finite resources.

That changes what must be designed, measured, recorded, and governed.

## 1. Objective and outcome design

The objective should not be treated as permanently fixed.

Questions:

- What outcome are we trying to create?
- Why is that outcome valuable?
- For whom is it valuable?
- What quality dimensions matter?
- What is clearly unacceptable?
- What is mediocre but usable?
- Could the objective be extended rather than replaced?
- Are newly feasible outcomes available because capability or cost changed?

Example:

A general AI security report may also support sector-specific variants, customer-specific briefs, training materials, interactive tools, or APIs.

Design implication:

Governance must distinguish objective stability, objective expansion, and objective replacement.

## 2. Solution envelopes

Many knowledge-work outputs do not have one correct answer. They occupy an envelope:

- preferred;
- acceptable;
- ambiguous;
- rejected;
- forbidden.

The organization should understand both:

- what qualifies as acceptable;
- what makes an outcome unacceptable, and why.

The second may matter more. Explicit red lines allow experimentation inside the safe region.

## 3. Judgment as binding constraint

The deeper bottleneck is often not generation. It is whether the organization can judge outcomes.

Subproblems:

- evaluability;
- outcome ambiguity;
- calibration;
- borderline cases;
- evaluator drift;
- evaluator gaming;
- evaluator recursion.

Design implication:

Outcome measurement is a first-class system, not a final review step.

## 4. Variance tolerance

Different work permits different levels of variation.

Examples:

- security-control mapping: narrow tolerance;
- financial calculation: near-zero semantic variance;
- marketing slogan: high variation;
- strategic analysis: deliberate disagreement may be useful.

Design implication:

Variance tolerance should change branching depth, review requirements, evaluator diversity, and governance thresholds.

## 5. Complexity and interdependence

Some steps are independent. Others form long causal chains where a small early deviation compounds into a major later defect.

Distinguish:

- local quality: was this step acceptable by itself?
- trajectory quality: did this step put the process on a worse path?

Design implication:

Lineage matters. When a downstream result fails, trace back to where the trajectory first became materially worse.

## 6. Causal traceability

Links show that A referenced B. Causal traceability records why we believed A influenced B.

Possible causal claim object:

- claim ID;
- relationship;
- mechanism;
- evidence;
- confidence;
- applicable conditions;
- contradicting evidence;
- provenance;
- version;
- observed outcomes.

KnowledgeBOM can store causal claims. CognitiveBOM can record which causal claims a specific work product relied on.

## 7. Coverability and completeness

Some search spaces are finite enough that high recall is plausible. Others are open-ended.

Modes:

- **Coverage mode:** push toward exhaustiveness where the domain is bounded and completeness matters.
- **Sufficiency mode:** search until additional sampling stops changing the decision.

Example:

Finding every possible CSA grant may be a coverage-mode task. Finding every consequential AI security discussion is not.

## 8. Marginal information value and stopping rules

When the population is unknown, ask:

> Are additional samples still changing the decision?

Signals:

- top results stabilize;
- new sources repeat old findings;
- rankings stop moving;
- no new failure modes appear;
- evaluator judgments converge;
- another branch no longer changes the action.

Design implication:

Stopping rules should be based on marginal information value, not arbitrary sample size.

## 9. Multiple-path execution

AI makes it practical to generate and propagate multiple branches.

Patterns:

- generate several candidates;
- mutate along different dimensions;
- compare outcomes;
- prune weak branches;
- combine strong branches;
- preserve rejected paths and why.

More branches are valuable when:

- uncertainty is high;
- diversity is valuable;
- evaluation is cheap;
- downstream consequences are large;
- learning has reuse value.

Fewer branches are appropriate when:

- outcome is obvious;
- evaluation dominates generation cost;
- time matters;
- variance creates risk.

## 10. Diversity of attempts

Ten near-identical attempts do not equal ten independent attempts.

Diversity can include:

- model diversity;
- prompt diversity;
- source diversity;
- methodological diversity;
- decomposition diversity;
- evaluator diversity;
- assumption diversity.

Design implication:

The objective is independent coverage of plausible solution regions, not raw count.

## 11. Parallel variants instead of cutovers

Traditional change management often assumes:

> old process -> decide -> cut over -> new process.

AI-native workflows can use:

- champion/challenger;
- shadow execution;
- canaries;
- A/B testing;
- multi-armed bandits;
- fork-and-replay;
- case-type routing.

Design implication:

There may never be one universal winner. Different variants may dominate different case classes.

## 12. Exploration versus exploitation

Production and exploration should have different budgets and expectations.

Production:

- high in-envelope yield;
- stable cost;
- bounded variance.

Exploration:

- lower yield acceptable;
- information gain is part of the product;
- broader variation;
- explicit learning objective.

Design implication:

Do not judge exploration by production yield or production by exploration tolerance.

## 13. Exploration dividend

An extra attempt can create:

1. immediate production value;
2. learning value for future executions.

Traditional cost accounting often sees only the first.

Design implication:

Compute expenditure can be attributed to both production value and learning value.

## 14. Commissioning and golden runs

Early in a workflow's life, deeper experimentation is unusually valuable.

Sequence:

1. Walking skeleton.
2. Characterization.
3. Calibration.
4. Production.
5. Continuing probes.

Design implication:

Do not prematurely optimize a workflow you have not characterized.

## 15. Adaptive depth

Not every case deserves the same compute.

Spend more when:

- consequence is high;
- uncertainty is high;
- disagreement appears;
- case is near boundary;
- novelty is high;
- learning value is high.

Spend less when:

- routine case;
- strong prior evidence;
- low consequence;
- cheap reversal;
- stable evaluator confidence.

Design implication:

The system needs a meta-controller that asks what the next unit of cognition is worth.

## 16. Yield and defect regimes

Track:

- in-envelope yield;
- near misses;
- hard rejects;
- cost per accepted outcome;
- defect lineage;
- recurring defect class.

As defects become rarer, each defect becomes more valuable as a learning unit.

Design implication:

Production workflows need both scheduled sampling and exception-triggered deep probes.

## 17. Negative knowledge

Record:

- rejected alternatives;
- failed experiments;
- near misses;
- recurring discarded ideas;
- hypotheses disproven;
- unexplored branches and why.

Design implication:

Negative knowledge prevents repeated relitigation and reveals blind spots.

## 18. Foundational system properties

Critical properties:

- observability;
- provenance;
- versioning;
- addressability;
- linkability;
- replayability;
- reversibility;
- uncertainty;
- authority;
- containment.

Design implication:

If work cannot be traced, replayed, linked, or rolled back, it becomes a blind spot.

## 19. Evaluation governance

Questions:

- Who evaluates the evaluator?
- How do we detect evaluator drift?
- How do we prevent evaluator gaming?
- When do we change the rubric?
- Who has authority to change it?
- What happens when evaluators disagree?

Design implication:

The judge is part of the system and needs its own telemetry, testing, and governance.

## 20. Governance of governance

A recursive organization eventually improves the rules for improvement.

But this creates risk:

- thrashing;
- self-justifying changes;
- goal drift;
- local optimization;
- loss of institutional memory.

Design implication:

Governance changes need evidence thresholds, authority boundaries, versioning, and rollback.

## 21. Economics and resource allocation

The question is not token minimization. It is organizational value.

Ask:

- Which workflow deserves improvement effort?
- Where does another branch pay off?
- Which process has thin margins?
- Which expensive process creates large downstream value?
- Which optimization is theater?

Design implication:

The allocator of improvement effort should itself become observable and testable.

## 22. Security and adversarial robustness

Recursive systems can be gamed.

Risks:

- evaluator gaming;
- prompt or memory poisoning;
- metric manipulation;
- false learning from adversarial traces;
- overfitting to test cases;
- unsafe self-modification;
- governance bypass.

Design implication:

Improvement loops need boundaries, adversarial review, provenance checks, and failure containment.

## Summary

The mature version is not "let the AI improve itself." It is a governed control plane that decides what may vary, what must stay stable, what evidence counts, where to spend cognition, how to preserve negative knowledge, and when the improvement process itself may change.
