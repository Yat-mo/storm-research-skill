# storm-research

A reusable Codex Skill for STORM-inspired multi-perspective research.

## 簡介

`storm-research` 是一個受 Stanford STORM 方法啟發的 Codex Skill，將「多視角提問、矛盾分析、綜合簡報、自我審稿」整理成可重複執行的研究流程。

使用者只要提供研究主題、角色與用途，agent 就會從實務者、學者、懷疑者、經濟誘因與歷史脈絡等角度拆解問題，找出盲點與關鍵分歧，最後產出帶有可靠性評分與行動建議的研究簡報。

它適合用於寫文章、做商業判斷、準備面試、投資研究、學習新領域，或任何不想停留在表面摘要的複雜主題。

## Overview

`storm-research` is a Codex Skill inspired by Stanford's STORM method. It turns multi-perspective questioning, contradiction mapping, synthesis, and self-review into a reusable research workflow.

Give the agent a topic, your role, and the purpose of the research, and it will examine the subject through practitioner, academic, skeptic, economic, and historical perspectives. It then surfaces blind spots, maps key disagreements, and produces a research briefing with reliability ratings and actionable insights.

It is useful for writing articles, preparing reports, making business decisions, interview prep, investment research, learning a new field, or any complex topic where a surface-level summary is not enough.

## Install

Copy the whole `storm-research-skill` folder into your skills directory, then rename the folder to `storm-research` if your agent expects the folder name to match the skill name.

Common locations:

- Codex: `~/.codex/skills/storm-research/`
- Claude-style local skills: `~/.agents/skills/storm-research/`

The required file is:

- `SKILL.md`

The optional eval prompts are:

- `evals/evals.json`

## Trigger Examples

- "用 STORM 方法研究一下這個話題。"
- "幫我從多個專家視角理解低空經濟。"
- "我要寫報告，先給我一個有矛盾地圖和可靠性評分的研究簡報。"
- "Give me a STORM-style research briefing on AI coding tools for solo founders."
- "Create a multi-perspective research prompt pack I can paste into Claude."
