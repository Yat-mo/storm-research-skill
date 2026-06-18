---
name: storm-research
description: Run a STORM-inspired multi-perspective research workflow for fast but nuanced understanding. Use this whenever the user asks to research a topic, prepare a briefing, understand a field, evaluate a decision, write a report/article, prepare for an interview, map disagreements, or asks for "STORM", "multi-perspective research", "contradiction map", "PhD-level briefing", or "5 expert perspectives". Prefer this skill even when the user only says they want to "quickly understand" a complex topic.
---

# STORM Research

Use this skill to turn a topic into a multi-perspective research briefing. The goal is not to sound comprehensive after one prompt; the goal is to surface blind spots, contradictions, incentives, evidence quality, and action implications.

This skill adapts the STORM idea: synthesize topic outlines through retrieval and multi-perspective question asking. It does not require Stanford STORM software. You execute the workflow directly.

## When Triggered

Proceed when the user wants to research, understand, brief, decide, write, prepare, compare, or evaluate a non-trivial topic.

If the topic is ambiguous, infer the most likely meaning from context and state the assumption. Ask at most two clarifying questions only when the topic, audience, or decision context is truly unknowable and would change the output.

If the user asks for reusable prompts rather than research output, provide a prompt pack. Otherwise, perform the research workflow.

## Inputs To Extract

Identify these from the user request:

- `topic`: the subject to research.
- `user_role`: who will use the answer, such as founder, investor, student, writer, manager, researcher, job candidate, or general reader.
- `decision_context`: what the user is trying to decide or produce.
- `depth`: quick scan, standard briefing, or deep research. Default to standard briefing.
- `source_mode`: whether external retrieval is available or requested.

If `user_role` is missing, use "informed generalist". If `decision_context` is missing, optimize for understanding and next-step judgment.

## Source Discipline

Use available retrieval tools when the user requests sources, when the topic is current, when factual claims are high-stakes, or when the output will support external publication or decisions.

When retrieval is available:

- Prefer primary sources, peer-reviewed literature, official documentation, high-quality institutional reports, and reputable domain publications.
- Track claims in a compact evidence ledger: claim, source type, date if relevant, and reliability note.
- Do not invent citations. If a claim is plausible but unsourced, label it as such.

When retrieval is not available or not needed:

- Make the output explicitly provisional.
- Separate "well-established", "likely", and "needs verification".
- Recommend exactly what to verify next.

## Workflow

### 1. Multi-Perspective Scan

Simulate five expert perspectives. Keep them concrete and domain-aware.

Default perspectives:

1. `The Practitioner`: works with the topic daily. They notice operational reality, implementation friction, tacit knowledge, and what theory misses.
2. `The Academic`: studies the evidence base. They notice peer-reviewed findings, definitions, causal claims, measurement limits, and where popular belief diverges from evidence.
3. `The Skeptic`: challenges the mainstream framing. They notice weak assumptions, adverse evidence, failure modes, and claims that benefit from selective attention.
4. `The Economist`: follows incentives. They notice who profits, who pays, market structure, principal-agent problems, funding bias, and distributional effects.
5. `The Historian`: compares patterns over time. They notice precedents, cycles, path dependence, and what happened when similar claims or technologies matured.

Adapt the personas when the topic calls for it. For example:

- Health: add or substitute clinician, patient advocate, regulator, biostatistician.
- Technology: add or substitute security engineer, product operator, standards expert.
- Public policy: add or substitute legal scholar, implementer, affected community.
- Investing: add or substitute bull analyst, bear analyst, operator, capital allocator.

For each perspective, produce:

- Core position in 2 sentences.
- Strongest supporting evidence or reasoning.
- Practical reality or blind spot that other perspectives may miss.
- What they would ask next.

### 2. Contradiction Map

Find the conflicts. Real understanding often lives where strong perspectives disagree.

Map:

- Direct contradictions: which claims clash, and which perspectives hold them.
- Evidence strength: strongest, weakest, and why.
- Crux question: the one question that would resolve the biggest disagreement.
- Consensus: what every perspective agrees on or at least does not dispute.
- Unaddressed gap: what none of the perspectives covered, and why it may matter.

Do not force conflict when there is none. If there is broad agreement, explain whether that reflects strong evidence, shared assumptions, or lack of imagination in the available perspectives.

### 3. Synthesis Briefing

Synthesize the scan and contradiction map into a usable briefing.

Use this structure by default:

```markdown
# Research Briefing: [Topic]

## One-Paragraph Summary
[A nuanced 60-second briefing for the specified audience.]

## Perspective Scan
| Perspective | Core Position | Strongest Evidence/Reasoning | Unique Blind Spot Caught |
|---|---|---|---|

## Contradiction Map
| Conflict | Claims That Clash | Best Current Read | What Would Resolve It |
|---|---|---|---|

## Key Findings, Ranked By Reliability
1. **[Finding]**  
   Reliability: [High/Medium/Low]  
   Supported by: [perspectives/sources]  
   Challenged by: [perspectives/sources]  
   Why it matters: [brief implication]

## Hidden Connection
[A non-obvious link that appears only after comparing perspectives.]

## Actionable Insight
[What someone in the user's role should do differently. Be specific.]

## Frontier Question
[The question that would most change understanding or strategy.]
```

If the user needs a shorter answer, compress the same logic rather than skipping the contradiction and reliability steps.

### 4. Peer Review

Critique the briefing before finalizing. This step protects against source bias, fact misassociation, overconfident synthesis, and one perspective dominating the answer.

Include a concise peer review section:

```markdown
## Peer Review
| Item | Assessment |
|---|---|
| Confidence scores | [Score each key finding from 1-10 with a short reason] |
| Weakest link | [Least certain claim and what would verify it] |
| Bias check | [Which perspective may be overrepresented] |
| Missing perspective | [A sixth angle that could change the conclusion] |
| Overall grade | [A-F or 1-10, with what to improve] |
```

Be candid. A useful briefing is allowed to say "we do not know yet."

## Output Rules

- Lead with the answer, not process narration.
- Make disagreements explicit instead of smoothing them into bland consensus.
- Rank reliability. Do not give all findings equal weight.
- Name incentives where relevant, but do not reduce every explanation to incentives.
- Avoid fake precision. Use ranges, confidence labels, and verification notes when needed.
- If external sources were used, include a short source list or evidence ledger.
- If no external sources were used, add: "This is an analytical briefing, not a source-verified literature review."

## Quick Mode

When the user asks for a very fast answer, use this compact structure:

```markdown
## Five Perspectives
## Biggest Contradictions
## Best Synthesis
## What To Do
## What To Verify
```

## Prompt-Pack Mode

When the user asks for prompts to paste into another model, provide four prompts:

1. Multi-perspective scan.
2. Contradiction map.
3. Synthesis briefing.
4. Peer review.

Customize placeholders for their topic, role, desired depth, and whether they want sources.

