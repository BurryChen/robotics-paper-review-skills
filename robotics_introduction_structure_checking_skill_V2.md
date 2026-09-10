---
name: robotics-introduction-five-paragraph-review
description: Review and revise robotics paper Introductions using a five-paragraph structure covering motivation, bottleneck, prior approaches and root causes, insight and method, and evidence-backed contributions. Use for five-paragraph Introduction restructuring, especially for ICRA, RSS, CoRL, and IROS papers.
---

# Robotics Introduction Structure Checking Skill — V2

## Purpose and Scope

Review and improve a robotics paper Introduction using **five paragraphs with a complete scientific argument**. Prioritize narrative structure and evidence alignment before sentence polishing.

Use the following default architecture:

| Paragraph | Primary role | Essential question |
|---|---|---|
| P1 | Broad robotics capability / broad motivation | What meaningful robotics capability motivates this work? |
| P2 | Specific bottleneck | What precise technical difficulty prevents that capability in the target setting? |
| P3 | Existing approaches and limitations, with deeper diagnosis | What has been tried, where does it fall short, and why? |
| P4 | Key insight & proposed method | What design principle addresses the root cause, and how is it implemented? |
| P5 | Experiments and contributions | What does the paper contribute, and what evidence supports those contributions? |

Treat this as an editorial framework, not an official conference requirement. Follow explicit user requirements for paragraph count, length, language, or contribution formatting. Do not impose this structure on unrelated sections.

## Core Principle

Build the argument in this order:

> Robotics capability → target-setting bottleneck → limitations of existing approaches → root-cause diagnosis → key insight → method response → experimental evidence → scoped contributions.

Compress adjacent functions without deleting them. In particular:

- Integrate **deeper diagnosis into P3**, normally near its end.
- State **the key insight before the implementation in P4**.
- Integrate **experimental validation into P5**, even when the paragraph is titled “Contributions.”

Distinguish four levels of reasoning:

| Level | What to establish | What does not suffice |
|---|---|---|
| Failure observation | The condition under which the robot fails | “The task is challenging” |
| Root-cause diagnosis | The assumption, representation, or feedback limitation explaining the failure | Repeating the observed performance deficit |
| Key insight | A principle that responds to that diagnosis | A list of modules or a new method name |
| Implementation | The operations that realize the principle | “We propose a novel framework” |

Frame an unverified root cause as a hypothesis or motivation, not a demonstrated fact.

## Inputs and Review Modes

Accept a complete paper, an Introduction draft, a partial draft, or an abstract with a proposed outline. When supplied, inspect Method and Experiments to verify what the Introduction can claim.

- **Review request:** Diagnose structure, score it, and suggest targeted edits. Do not replace the whole Introduction unless requested.
- **Rewrite request:** Diagnose briefly, then provide a complete five-paragraph revision and explain the major changes.
- **Outline request:** Provide the five-paragraph plan and identify missing evidence; do not invent a completed paper.
- **Incomplete source:** Make useful edits from the available material and identify what cannot be verified.

Use the user's language for explanations. For an English manuscript, retain English in the revised Introduction unless requested otherwise.

## Five-Paragraph Specification

### P1 — Broad Robotics Capability / Broad Motivation

**Goal:** Establish a relevant robotics capability and the physical or operational requirements that make it meaningful.

Include:

1. The capability or real-world need.
2. The target task or environment at an appropriate level of specificity.
3. A closing requirement that prepares the technical bottleneck in P2.

Start with robotics rather than a generic AI trend. Introduce geometry, contact, embodiment, uncertainty, perception-action coupling, or another task-specific requirement when relevant. Do not force physical-grounding terminology onto papers about a different bottleneck.

Keep broad motivation selective: every sentence should help explain this paper's problem. Avoid method names, module inventories, and lengthy application lists here.

**Transition test:** Does the end of P1 make the difficulty in P2 feel necessary?

### P2 — Specific Bottleneck

**Goal:** Define the failure or unresolved requirement before reviewing solutions.

Specify:

- The target operating regime: relevant variations, deployment conditions, or resource constraints.
- What becomes difficult or fails in that regime.
- Why the failure matters for task execution or evaluation.
- The requirement a successful solution must satisfy.

Prefer observable descriptions over adjectives. For example, identify loss of contact-state information under occlusion rather than merely claiming poor robustness.

If two bottlenecks are essential, state their relationship and why addressing either alone is insufficient. Do not introduce unrelated challenges simply because the method contains multiple components.

Keep detailed prior-work comparisons in P3. A short citation-backed context sentence is acceptable in P2 when needed to establish the bottleneck.

**Transition test:** Is the reader ready to ask which existing approaches address this difficulty?

### P3 — Existing Approaches and Limitations + Deeper Diagnosis

**Goal:** Explain why available approaches leave the P2 requirement unresolved.

Group the most relevant approaches by mechanism, assumption, or limitation. Two or three groups often suffice, but use only the groups the paper needs.

For each group, synthesize:

> What it enables → what it assumes → where that assumption limits it in the target regime.

Then close with a supported root-cause diagnosis that motivates P4. Possible causes include missing feedback, an unsuitable representation, dependence on task-specific models, or a mismatch between training and deployment. Choose from the paper's evidence rather than inserting a preferred explanation.

Distinguish **not evaluated** from **unable to perform**. A paper that does not test a setting has not necessarily failed in that setting.

Keep this paragraph selective. Move a detailed survey to Related Work when that section exists. If it does not, retain the comparisons essential to the central claim, especially the closest work.

**Transition test:** Does the final diagnosis identify a design requirement that P4 actually addresses?

### P4 — Key Insight & Proposed Method

**Goal:** Connect the diagnosis to a principled, understandable technical response.

Use this internal order:

1. State the key insight or hypothesis in a clear sentence.
2. Introduce the method and its central operation.
3. Explain the essential mechanisms in relation to the diagnosed requirements.
4. Clarify the relevant input-output relationship or system flow where needed.

The insight should remain meaningful if the exact implementation changes. It may be a representation choice, decomposition principle, feedback strategy, modeling hypothesis, or other technical reframing; it need not be a grand scientific claim.

Explain each major component as a response to a problem, rather than listing components without reasons. Include implementation detail only when needed to distinguish the contribution. Move training recipes, architecture minutiae, equations, and secondary modules to Method.

If the draft lacks an explicit insight, offer two or three candidate formulations supported by the manuscript. Identify them as editorial interpretations for author verification; do not manufacture novelty.

**Transition test:** Has P4 stated a claim that the experiments in P5 can test?

### P5 — Experiments and Contributions

**Goal:** Close with concrete contributions supported by an appropriate preview of the evaluation.

Combine:

- **Evaluation scope:** Task types, relevant platform or simulation setting, and variations that test the claim.
- **Comparison or mechanism evidence:** Relevant baselines, ablations, or other tests, when present in the paper.
- **Headline finding:** A verified quantitative result or a precise qualitative finding.
- **Contributions:** The specific formulation, method, system capability, dataset, benchmark, or empirical finding the paper actually provides.

Choose the ordering that reads naturally. An evidence-first paragraph may preview evaluation and then summarize contributions. A contribution-first paragraph may pair each contribution with its validation. Neither order should repeat the complete method description.

For a strict five-paragraph deliverable, write P5 as **one prose paragraph**. Inline enumeration such as “(i) …; (ii) …; and (iii) …” is optional. Use separate contribution bullets only when the user permits that formatting, and explain that it is a five-part layout rather than five prose paragraphs.

Do not equate conducting experiments with a scientific contribution. Identify what the evaluation establishes. Use a broader implication only when supported, and do not end with an unrelated future-work promise.

When results are unavailable, use explicit author-facing placeholders or flag the missing evidence outside the draft. Do not present a draft with unresolved placeholders as submission-ready.

**Closure test:** Can a reader state what was contributed, what supports it, and under which conditions it holds?

## Review and Revision Procedure

### Step 1 — Recover the Central Claim and Evidence Boundary

Write a one-sentence working claim:

> This paper investigates whether [principle/method] enables [capability] under [target conditions] by addressing [specific limitation].

Separate the paper's stated claim from your interpretation. Record the actual method, evaluation setting, headline results, and unresolved facts. If only the Introduction is available, mark claims that require checking against the rest of the paper.

### Step 2 — Map the Original Paragraphs

Number the original paragraphs O1, O2, and so on, keeping these identifiers distinct from target paragraphs P1–P5.

| Original paragraph | Current function | Main issue | Proposed action | Target paragraph |
|---|---|---|---|---|
| O# | Motivation / bottleneck / prior work / diagnosis / insight / method / evidence / contribution | Structural or language issue | Keep / merge / split / move / shorten / rewrite | P# |

Explain why each significant restructuring improves the argument. Do not assume the original paragraph count is five.

### Step 3 — Check the Argument Links

Audit these connections:

| Link | Check |
|---|---|
| P1 → P2 | The capability requires solving the stated bottleneck. |
| P2 → P3 | The selected prior approaches address the same problem and operating regime. |
| P3 → P4 | The insight responds to the diagnosed limitation. |
| Within P4 | The method implements the insight through concrete mechanisms. |
| P4 → P5 | The evaluation tests the claim made for the method. |

Where evidence is available, construct a compact correspondence table:

| Bottleneck / diagnosis | Insight | Method response | Evidence or required test | Status |
|---|---|---|---|---|
| Manuscript-grounded issue | Supported design principle | Actual mechanism | Existing baseline, ablation, result, or proposed test | Supported / partial / not verifiable / missing |

Clearly label proposed tests. Do not imply that every claim requires an ablation; select evidence appropriate to the claim. For example, a performance comparison alone may not establish a causal explanation for improvement.

### Step 4 — Plan the Five Paragraphs

Give a sentence-level content plan for P1–P5. Place diagnosis in P3, insight before method in P4, and evidence with contributions in P5.

Apply the user's word limit first. When no limit is given, use the shortest length that preserves technical meaning and essential evidence. Allocate more space to P3 or P4 if the comparison or mechanism requires it. Do not treat a fixed word count or equal paragraph lengths as a conference rule.

### Step 5 — Revise According to the Requested Mode

For a rewrite:

1. Restructure the scientific argument.
2. Remove repeated motivation, repeated limitations, and repeated method summaries.
3. Preserve technical meaning, scope, and valid citations.
4. Improve topic sentences, transitions, and concrete language.
5. Deliver exactly five prose paragraphs unless the user explicitly chooses another layout.

Do not place P1–P5 headings, reviewer comments, or diagnostic labels inside the clean manuscript text. Provide the annotated map separately.

### Step 6 — Verify the Revision

Check paragraph count, retained meaning, citation placement, evidence fidelity, and claim scope. Confirm that combining functions has not eliminated the root cause, insight, or experiment preview.

When a sentence moves, move its supporting citation with it. Do not attach an existing citation to a new or stronger claim without verification. Do not invent bibliography entries or citation keys.

## Scoring Rubric

Score the original Introduction on nine dimensions, each from 1 to 5. Use 2 and 4 for intermediate performance. Report a total out of **45** when all dimensions can be assessed.

| Dimension | 1 — Weak | 3 — Adequate | 5 — Strong |
|---|---|---|---|
| P1: Robotics motivation | Generic or disconnected | Relevant capability | Specific capability and requirements motivate the paper |
| P2: Bottleneck clarity | Vague difficulty | Recognizable limitation | Concrete failure, conditions, and unresolved requirement |
| P3: Prior-work synthesis | Paper list or unfair dismissal | Some grouping and comparison | Selective, fair, target-setting comparison |
| P3: Deeper diagnosis | Missing or unsupported | Plausible but weakly connected | Supported diagnosis or clearly bounded hypothesis motivates design |
| P4: Key insight | Method name or module list | Understandable design idea | Clear principle responds directly to diagnosis |
| P4: Method alignment | Unmotivated components | Mostly understandable response | Mechanisms implement the insight and address stated requirements |
| P5: Experimental evidence | Generic effectiveness claim | Tasks or results mentioned | Relevant scope and comparisons support the central claim |
| P5: Contributions and scope | Generic or inflated | Concrete but incompletely bounded | Distinct contributions with appropriate evidential boundaries |
| Overall: Flow and compression | Disconnected or repetitive | Mostly coherent | Five paragraphs preserve the full argument with little redundancy |

If a dimension cannot be assessed because the supplied text is partial, mark it N/A and report the subtotal over the assessable maximum; do not silently convert it to /45. For a complete Introduction, an absent narrative function is a weakness, not N/A.

Distinguish rhetorical quality from factual verification: a clearly written result may still be unverified without access to Experiments. Do not use a high score to imply publication readiness or acceptance probability.

Report the three highest-priority revisions. If scoring the rewritten version too, label the two scores separately and retain unresolved evidence limitations.

## Required Output Format

Adapt detail to the request while retaining the relevant parts below:

1. **Overall verdict and central claim:** Identify the main structural issue and the manuscript's aim.
2. **Original-paragraph diagnosis:** Use the O# mapping table; distinguish structural issues from language issues and explain modification logic.
3. **Missing functions and correspondence audit:** Highlight absent diagnosis, weak insight, unsupported claims, or evidence mismatches.
4. **Scores and priorities:** Apply the nine-dimension rubric and identify the three most consequential changes.
5. **Revised five-paragraph plan:** State the purpose and intended content of P1–P5.
6. **Revised Introduction, when requested:** Provide five clean prose paragraphs, preserving the paper's technical claims and citation support.
7. **Revision rationale and author checks:** Explain major moves or merges and list missing evidence or claims needing confirmation.

For targeted review, replace the complete rewrite with concrete edits to the most important bottleneck, diagnosis, insight, transition, and contribution sentences. For an outline-only request, omit full prose and unsupported scoring.

## Common Failure Modes and Fixes

| Failure mode | Corrective action |
|---|---|
| Five paragraphs achieved by deleting key reasoning | Restore diagnosis in P3, insight in P4, and evidence in P5; remove repetition elsewhere. |
| P1 begins with general AI progress | Begin with the robotics capability and its requirements. |
| P2 and P3 repeat the same limitations | Use P2 to define the task-level failure; use P3 to compare mechanisms and explain causes. |
| P3 dismisses all earlier work as non-generalizable | Specify the generalization axis and distinguish untested settings from demonstrated failure. |
| P3 becomes an exhaustive survey | Retain research lines and closest comparisons needed to motivate the contribution. |
| P4 jumps from a gap to a module inventory | State the design insight first, then connect mechanisms to requirements. |
| The diagnosis claims more than the evidence shows | Present it as a hypothesis or narrow it to what the paper establishes. |
| P5 repeats P4 | Summarize contributions by novelty and evidence rather than architecture. |
| P5 says only “extensive experiments” | State relevant tasks, conditions, comparisons, and verified findings. |
| Contribution bullets create extra paragraphs | Use a single prose paragraph or inline enumeration for strict five-paragraph output. |
| Compression changes a technical claim | Restore scope and terminology; move detail only when it is not needed to interpret the claim. |

## Five-Paragraph Drafting Scaffold

Use this scaffold as a planning aid, not text to copy mechanically. Bracketed content must come from the paper or remain explicitly unresolved.

**P1 — Motivation:** Establish [robotics capability] in [relevant setting], identify [physical or operational requirements], and close with the requirement that motivates P2.

**P2 — Bottleneck:** Explain how [specific condition] causes [observable difficulty or failure], why this matters for [task outcome], and what [missing capability] is required.

**P3 — Existing approaches and diagnosis:** Compare [relevant approach families] by their strengths and assumptions, locate their limitations in [target regime], and conclude with [supported root cause or stated hypothesis].

**P4 — Insight and method:** State [design principle] as a response to that diagnosis, introduce [method], and explain how [essential mechanisms] address [specific requirements].

**P5 — Evidence and contributions:** Identify [evaluation scope], [relevant comparisons or tests], and [verified finding]; summarize [distinct contributions] within [demonstrated scope].

## Evidence and Reusability Rules

- Preserve the author's intended technical contribution; do not create a more impressive but different paper.
- Do not invent results, trial counts, datasets, platforms, baselines, citations, or causal explanations.
- Do not claim “first,” “general,” “safe,” or “state of the art” without support for the precise scope.
- Distinguish observations, hypotheses, design motivations, and established findings.
- Treat missing literature categories as suggestions unless an omission has been verified.
- Keep unpublished project details in the private paper review, outside reusable versions of this skill.
- Follow explicit user requirements over default editorial preferences.

## Final Acceptance Checklist

- [ ] The clean rewrite contains exactly five prose paragraphs, unless the user specified another format.
- [ ] P1 motivates a robotics capability relevant to the actual paper.
- [ ] P2 defines a concrete bottleneck and target regime.
- [ ] P3 fairly synthesizes relevant prior approaches and includes a deeper diagnosis.
- [ ] P4 states the insight before explaining the method.
- [ ] Major mechanisms respond to the stated requirements.
- [ ] P5 includes evaluation evidence and specific, bounded contributions.
- [ ] Every transition advances the central argument.
- [ ] Citations, quantitative statements, and technical meanings remain faithful to the source.
- [ ] Unknown facts and author-facing placeholders are clearly identified.

## Source and Adaptation

Adapted from [Robotics Introduction Structure Checking Skill](https://github.com/kai-zhang-er/robotics-paper-review-skills/blob/main/robotics_introduction_structure_checking_skill.md) in the [robotics-paper-review-skills repository](https://github.com/kai-zhang-er/robotics-paper-review-skills).

V2 specializes the original framework for five-paragraph rewriting: deeper diagnosis is integrated into P3, insight and method into P4, and experimental evidence and contributions into P5. It retains the original nine-dimension, 45-point evaluation structure while clarifying paragraph counting, source-to-revision mapping, and evidence boundaries. This is an adapted document, not a claim of an upstream repository update.
