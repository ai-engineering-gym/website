---
title: "Positioning"
description: "Two stories, one product — sovereignty for industry, a training ground for research."
weight: 2
---

The AI Engineering Gym serves two audiences with one product. Both get the same core: a rigorous environment where autonomous agents learn real mechanical design, with full provenance on every output.

## Story A — Sovereignty (for industry)

OEMs and Tier-1 suppliers face a choice: hand their design data to a black-box AI vendor, or keep control. We build for the second option.

- **Your data stays yours.** Train and evaluate on your own parts, in your own environment.
- **Your models, your sign-off.** Bring your own LLM; the Gym provides the training loop and the evidence.
- **Compliance-ready.** Every output carries its audit trail — the provenance a regulator or customer will ask for.

The window is real: as EU AI Act obligations phase in (high-risk duties land **2 Dec 2027** and **2 Aug 2028**), the teams that can *show* their AI design process is controlled and auditable will have an edge. [What the timeline actually means]({{ relref "/blog/2026-10-17-compliance-window/" }}).

## Story B — Training ground (for research)

For labs and universities, the Gym is a reproducible environment for studying how LLMs acquire engineering capability.

- **A benchmark, not a demo.** Measurable tasks with ground truth — you can track capability over time and across models.
- **A published method.** The training loop, the validation steps, the sign-off criteria — all documented and reproducible.
- **Open by default.** Contribute tasks, models, and results; build on a shared foundation.

## What we are not selling

- Not another CAD tool — we don't compete with your design software.
- Not a black-box generator — no "prompt in, part out" with no evidence.
- Not a consulting service — we build the environment; you drive it.

We ship evidence, not just geometry.

## Frequently asked questions

**Is this a CAD tool?**
No. The Gym is the training and evaluation environment *for agents that use* CAD (CadQuery). It sits next to your design software, not in front of it — and it never replaces the engineer's sign-off.

**Do you train on my data?**
No. Bring your own LLM — local (e.g. via LM Studio) or hosted, in your environment. The Gym provides the loop, the validation gates and the audit trail; the model weights are yours to choose.

**Which models work with it?**
Any LLM that can emit CadQuery code. The loop is model-agnostic by design — that's what makes the benchmark comparable across models over time.

**What exactly is in the audit trail?**
For every generated part: which prompt version, which model (and weights/version), each validation result, the renders, and whose sign-off closed it. Immutable per-part provenance — the record an auditor or a customer will ask for.

**When will it be available?**
The open-core engine ships at launch; the benchmark index (v0.1) is in development; the university program is being formalized. We publish status on this site — including what isn't ready yet.

**How much will it cost?**
Free for students and open-source contributors at launch. Paid tiers (hosted runs, evolved prompt packs, enterprise) will be announced when they're real — we publish pricing at launch, not before.

**Is the Gym EU AI Act compliant?**
The Gym itself is a minimal-risk system under the Act — it's neither an Annex I product nor in any Annex III domain. It is built audit-first because *your downstream use* matters: the provenance, logging and human-in-the-loop review map one-to-one onto the Act's high-risk requirements. [The full timeline, with dates]({{ relref "/blog/2026-10-17-compliance-window/" }}).

{{< contact-cta >}}