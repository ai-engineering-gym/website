---
title: "Generative geometric engineering you can audit"
description: "Secure, explainable and auditable generative geometric engineering — EU AI Act ready. An open training ground where autonomous agents learn real mechanical design."
---

<!-- Hero (badge, subtitle, buttons) is rendered by layouts/index.html over the wireframe
     background; its copy lives in data/hero.yaml. The body below renders normally. -->

## How it works

```mermaid
flowchart LR
    A["Spec / prompt"] --> B["Generate geometry (CadQuery)"]
    B --> C["Validate &amp; render"]
    C --> D{"Inspect"}
    D -- "pass" --> E["Sign-off"]
    D -. "fail / inconclusive" .-> B
    B -. "prompt, model" .-> T[("Audit trail")]
    C -. "checks, renders" .-> T
    E -. "decision" .-> T
```

Every step is captured — the prompt, the model, each validation result, and the final sign-off. That audit trail is not a feature; **it's the product.**

And inspection is tri-state: every check returns *pass*, *fail* — or *inconclusive*. When the validator can't decide, we say so instead of guessing. Honest measurement is what makes a benchmark a benchmark — [why we score inconclusive](/blog/2026-10-17-tri-state/).

## Why now

Two forces are converging on engineering teams:

- **Cost pressure.** Design cycle time is a cost center. AI that drafts the first 80% of a part changes the math — *if* you can trust what it produces. The open question was never "can a model generate geometry?" but "who verifies it, and can you prove it?"
- **Compliance.** The EU AI Act's transparency duties have applied since August 2026, and the high-risk obligations land in December 2027 and August 2028. Teams that can *show* their AI design process is controlled, logged and auditable will have an edge — the boring documentation work is now a differentiator. [The compliance window, explained](/blog/2026-10-17-compliance-window/).

{{< hextra/hero-section heading="h3" >}}Two ways in{{< /hextra/hero-section >}}

{{< hextra/feature-grid cols="2" >}}
  {{< hextra/feature-card title="For industry (OEMs, Tier-1)" subtitle="Train and evaluate your own engineering agents on a benchmark that mirrors real design work — with the compliance evidence to show regulators and customers. Your data, your models, your sign-off." icon="office-building" link="/positioning/" >}}
  {{< hextra/feature-card title="For labs & universities" subtitle="A rigorous, open research environment for studying how LLMs acquire engineering capability — with reproducible benchmarks and a published method. Free academic access." icon="beaker" link="/university/" >}}
{{< /hextra/feature-grid >}}

{{< contact-cta >}}
