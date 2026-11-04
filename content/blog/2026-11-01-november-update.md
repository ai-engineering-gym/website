---
title: "M0 done — and what November is for"
description: "The website shipped on schedule. Since then: OS-level sandboxing for LLM code execution, a first multi-model probe (with an embarrassing result), and 1,105 tests."
date: 2026-11-01T09:00:00+01:00
tags: ["announcement", "benchmark"]
---

Milestone M0 — brand, website, newsletter, first market poll — closed on October 31. The public site shipped with four pages: the landing page, [positioning]({{ relref "/positioning/" }}), the [benchmark method]({{ relref "/benchmarks/" }}) and the [university program]({{ relref "/university/" }}), plus this blog. What's deliberately *not* on it yet: published benchmark results (M2) and pricing ("we publish pricing at launch, not before").

Since the site went up, the engineering side has been moving. Three things worth knowing:

## LLM code execution now runs in an OS sandbox

Every run in the Gym executes model-generated CadQuery code. Until now that trust was enforced by our own process boundaries; now it's also enforced by the operating system. The new sandbox (opt-in, off by default) wraps code execution in a deny-by-default policy — Seatbelt on macOS, Landlock on Linux — with network access off unless explicitly enabled. If the platform doesn't support it, we warn and fall back to the old behavior rather than silently pretending.

Alongside it: symlink-escape hardening across all persistence and serving paths, retry/backoff plumbing for slow or flaky model calls, and progress feedback so a 500-second inference no longer looks like a hang.

## First multi-model probe — including an embarrassing result

We built a reusable comparison probe: the same five-task suite (boat, bracket, gear fit, nozzle, hinge) run against each candidate model via OpenRouter, executing the generated code and reporting first-attempt success. First numbers (n=1 per task — a probe, not a benchmark):

| Model | First-attempt success (5 tasks) |
|---|---|
| Flint v1.0 (free tier) | 4/5 |
| Jev router | 3/5 |
| Qwen3.8-27B | 3/5 |
| Gemma 4 26B (our current default) | **0/5** |

That last row is the point. Our default model — the one this very Gym runs on — failed all five tasks when probed through OpenRouter, mostly with truncated code. A benchmark that only measures models you like would have missed that. The probe is now one command; the real benchmark (M2) will run it properly, with n>1 and tri-state scoring.

## The harness keeps growing

The test suite went from 671 tests in September to **1,105** today. The measurement instrument is getting as rigorous as the measurements it will produce.

## What October looked like from outside

Our monthly market monitor (first run in the new scope: coding agents, agent frameworks, ML evaluation) picked up a telling month:

- **AI code review became its own product category** — GitHub shipped multi-agent Copilot Review in preview, Claude Code Review went GA. The pattern is exactly our tri-state inspector: independent review agents with an explicit *inconclusive* state, not binary verdicts.
- **Model-agnostic orchestration went mainstream** — Copilot Fusion (GA) picks and combines models per task. Our plug-and-play model registry is built for this; cost-per-task is becoming the first evaluation dimension.
- **Generic coding benchmarks are saturating** — SWE-Bench Pro V2 now sees frontier agents at ~99%. Differentiation is moving to domain-specific evaluation. That's the Gym's lane: geometry that has to be *right*, not just code that runs.
- **The Linux Foundation's AAIF launched OpenEnv** — an open framework for RL environments as containerized services. It standardizes what the Gym does; we're evaluating it as an export/interoperability format.

## What November is for (M1)

- Repo polish: README, demo GIF
- Timelapse video v1 — watch an agent run the full loop
- Paper draft v1 — the method, written down properly
- Cheatsheet #1 live (the launch offer)
- Poll results published

We ship evidence, not just geometry.