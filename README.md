<div align="center">

<p>
  <strong>English</strong> · <a href="README.zh-CN.md">简体中文</a>
</p>

![RootTrail — Every bug leaves a trail.](assets/roottrail-hero.png)

# RootTrail

### Every bug should leave a trail of evidence.

**Turn complex failures into verifiable chains of evidence.**

A local-first AI investigation workbench for Electron / JavaScript developers.

**Evidence-Driven Debugging · Cross-Process Investigation · Human-in-the-Loop**

[Capabilities](#evidence-driven-investigation) · [Target problems](#built-for-the-hard-to-find-bugs) · [The experience](#from-problem-to-evidence-to-verification) · [Deliverables](#one-investigation-leaves-results-you-can-carry-forward)

</div>

> This is a product concept preview: the capabilities described below are planned, not implemented, and the images are brand and experience illustrations.

## A clear path through complex troubleshooting

A single click that does nothing may involve page events, bridge interfaces, inter-process communication, the main process and the file system. The symptom appears in one place, while the clues are scattered across code, logs, version changes and developer experience.

RootTrail organises **scenario reproduction, behaviour correlation, evidence provenance, human collaboration and regression verification** into one continuous investigation around a specific bug. You can see what has been found so far, which judgements are supported, and what is still unresolved — and step in at the key moments.

**Make the symptom reproducible, the clues traceable, the judgements reviewable, and the results re-runnable.**

## Evidence-driven investigation

### 🔍 Root Cause Analysis

Build the investigation context from "what actually happened" and "what should have happened", then check candidate causes along the relevant modules, interfaces and run records to narrow the search.

Every candidate explanation can carry its supporting material, counter-evidence and open questions. **Reproduction status and root-cause judgement are presented separately**, so you can judge how reliable the current conclusion is.

### 🧭 Cross-Process Investigation

For Electron applications, relevant code and collected runtime observations are organised around **Renderer → Preload → IPC → Main**, bringing clues that were spread across several processes into one investigation context.

Follow a page action to the bridge interface, then check the corresponding behaviour on the main-process side. Where a link has not been observed, the coverage gap stays explicit so you can decide where to look next.

### ⚖️ Differential Analysis

"It worked in the previous version and fails in the new one" is an important entry point. RootTrail compares the two versions using the same steps, inputs and expected behaviour, and shows the actual results together with the key environment differences.

Useful after dependency upgrades, interface migrations, IPC refactors and changes to export functionality. With only one version available, single-version reproduction and investigation still work.

### 🧩 Evidence Provenance

Code references, logs, run records and human notes each keep their own source, linked to the relevant version and investigation step. Through the investigation graph and the timeline, you can move from a conclusion back to the material behind it.

**Direct observations, derived results, candidate inferences and unknowns are labelled separately.** When evidence is incomplete, its limitations are shown alongside the conclusion, which keeps the investigation explainable and reviewable.

### 💬 Human-in-the-Loop

You know the business; the agent is good at organising clues. When an investigation stalls on a private interface, a historical convention or special business logic, you can add context, reject a hypothesis or ask for further verification.

Human input keeps its source. Affected earlier conclusions move back to pending review, while the original evidence and history remain available. Project knowledge genuinely enters the investigation, and changes of judgement stay traceable.

### 🔁 Reproducible Verification

Build reproduction scenarios around an explicit business expectation, keeping the inputs, results and preconditions of every run. Where applicable, investigation results become re-runnable reproduction scripts and regression tests.

The problem you just investigated leaves an entry point for verifying it again. Exported cases aim to run without the model and without the workbench, and ship with their preconditions stated: the target application, dependencies and required data.

## Built for the hard-to-find bugs

| The problem you have | What RootTrail organises |
| --- | --- |
| **A feature breaks after an upgrade** | Compare the same operation on the old and new versions; check behavioural differences, environment differences and the supporting evidence. |
| **A button does nothing, logs are scattered** | Correlate page events, bridge interfaces, IPC and main-process clues; check which steps were actually observed. |
| **Chinese filenames or unusual inputs trigger failures** | Fix the inputs and expected results, keep the reproduction record, and form an applicable regression case. |
| **You inherited an unfamiliar project and don't know where to start** | Start from the concrete failure and build the problem context along the relevant code and runtime observations. |
| **You need to hand a half-finished investigation to a colleague** | Deliver the evidence you have, the run records, the candidate causes and the questions still to verify. |

## From problem to evidence to verification

![RootTrail investigation experience: describe the failure and the expectation, investigate along the evidence, add clues, and keep a report plus re-runnable results.](assets/roottrail-workflow.png)

1. **State the problem.** Select a local project and provide the symptom, the trigger steps and the expected behaviour; add a working older version for comparison when you have one.
2. **Take part in the investigation.** Review the timeline, the evidence relationships and the candidate causes; add business context or correct a hypothesis at the key moments.
3. **Carry the results away.** Check the findings, then export the report, the evidence index and the applicable verification cases.

For example: "the new version cannot export a file whose name contains Chinese characters, while the old version could." Around the same input and expectation, compare the behaviour of both versions step by step, inspect the relevant code paths, and keep the actual run results. This is an experience example, not a completed real case.

## One investigation leaves results you can carry forward

| Deliverable | What it gives you |
| --- | --- |
| **Investigation Report** | Reproduction status, candidate causes, supporting evidence and the boundaries of the conclusion. |
| **Evidence Index** | A way back to specific code, versions and run records for review and handover. |
| **Reproduction Artifacts** | Steps, inputs, environment preconditions and applicable scripts, so the problem does not have to be described from scratch again. |
| **Regression Tests** | Where a clear assertion can be defined, a check that later versions can execute again. |
| **Open Questions** | Which links remain unverified, and what material is needed next. |

Even a problem that has not been located yet keeps the work that was already done. Every investigation can become part of ongoing maintenance and knowledge handover.

## Local-first, with clear boundaries

Investigation records and evidence are designed to be stored locally. When a remote model service is used, the context you select may be sent to that service.

The current scope covers Electron / JavaScript projects with runnable source or a debuggable build; how much can actually be observed and reproduced depends on the target application and the run conditions.

Analysis capabilities build on [REA](https://github.com/morluto/rea); RootTrail is an independent product.

---

<div align="center">

**RootTrail · Follow the evidence. Find the cause.**

Make this investigation the starting point for the next one.

</div>
