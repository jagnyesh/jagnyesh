# Jagnyesh Patra

Clinical informatics, moving from product into building. Since 2019 I've worked on healthcare data at providers, a payer and its pharmacy benefit manager, and the CDC, with FHIR, HL7 v2, OMOP and Epic data. These days I mostly test whether LLM output holds up against clinical data standards before it reaches a workflow.

I came up through product: requirements interviews with PIs and clinicians, backlogs, MVP launches. I still start there, and now I write the code and the evals too.

Everything here runs on synthetic or public data. No PHI.

## Projects

**[rcm-ai](https://github.com/jagnyesh/rcm-ai)**: Can a small terminology-and-policy graph decide Medicare medical-necessity denials better than an LLM reading the same policy? The graph decides, the model extracts evidence and drafts the appeal, and a deterministic checker fails any letter that cites a code the graph didn't establish. On 20 synthetic cases the premise was falsified on accuracy: the LLM-only baseline scored 19/20 against the graph's 16–17/20 on extracted evidence. The graph still made no false upholds, sent every miss to a human, and named a source row for every step of its justifications. The labels are awaiting human review. [Architecture explorer](https://jagnyesh.github.io/rcm-ai/architecture/rcm-ai-explorer.html)

**[researchflow](https://github.com/jagnyesh/researchflow)**: Can AI agents absorb the coordination overhead in research data requests while routing technical decisions to the people who should make them? A LangGraph multi-agent workflow over a FHIR server, with four human-in-the-loop gates. One finding: a projected 73% cut in LLM cost measured 0%, which I traced to three bugs, including `cache_control` being silently dropped in langchain-anthropic. [Architecture](https://jagnyesh.github.io/researchflow/architecture.html)

**[omop-kumo-bench](https://github.com/jagnyesh/omop-kumo-bench)**: Does a graph neural network trained straight on OMOP tables beat tuned LightGBM with about 260 hand-built features? Both models get the same rows, labels and patient-level split on the 100,000-patient Synthea OMOP release. It doesn't: AUROC 0.957 against 0.952 on 30-day readmission, and 0.814 against 0.809 on ED visits within 90 days. The readmission scores are inflated, because 97.6% of readmissions come from 1,168 patients whom Synthea readmits every 21 to 30 days.

**[field-guide](https://github.com/jagnyesh/field-guide)**: A Claude Code plugin that shows a developer new to agentic coding what the agent did: what's in its context, each step of the loop, whether the tests really went green, and what a compaction kept. It only watches; it never blocks a tool call or calls a model.

**[merge-works](https://github.com/jagnyesh/merge-works)**: An interactive machine that explains git merges, parallel agent work and the AI-native SDLC, with a safety lens for regulated engineering. [Live](https://jagnyesh.github.io/merge-works/)

## How I work

- Measure the claim against a baseline, and publish the result when it goes the other way.
- Keep every fact traceable to the source row it came from.
- Put the human gate where a wrong answer costs the most.

## Background

Tufts CTSI · UIC Center for Clinical and Translational Sciences · Optum / UnitedHealth Group · CDC · [LinkedIn](https://linkedin.com/in/jagnyesh)
