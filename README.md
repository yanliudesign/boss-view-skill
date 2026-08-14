[中文](./README.zh.md) · English

# 👔 Boss View

Turn messy work notes into an executive-ready update that makes progress, impact, risk, and asks clear.

[![Version](https://img.shields.io/badge/VERSION-1.0.0-2ea44f?style=flat-square&labelColor=333)]()
[![Stars](https://img.shields.io/github/stars/yanliudesign/boss-view?style=flat-square&label=STARS&color=e37f2c&labelColor=333)](https://github.com/yanliudesign/boss-view/stargazers)

[![Claude Code](https://img.shields.io/badge/Claude_Code-Skill-d97757?style=flat-square&labelColor=1a1a1a&logo=anthropic&logoColor=white)](https://claude.ai/code)
[![GitHub Copilot](https://img.shields.io/badge/GitHub_Copilot-Skill-8957e5?style=flat-square&labelColor=1a1a1a&logo=githubcopilot&logoColor=white)](https://github.com/features/copilot)
[![Codex](https://img.shields.io/badge/Codex-Skill-2ea44f?style=flat-square&labelColor=1a1a1a)]()

An agent skill for weekly updates, manager syncs, 1:1s, and project reporting. Drop in rough notes in any order. Boss View reorganizes them around what leaders actually need to know, then generates a polished, single-file HTML report with built-in PDF and Markdown export.

It does not inflate activity into impact or invent missing metrics. When evidence is missing, it says so.

```text
Raw notes                          Boss View
──────────────────────────────     ──────────────────────────────
"5 meetings, 3 design rounds"  →  Progress and outcome
"conversion is still low"      →  Business risk
"tutorial next week"           →  Next step
"need leadership alignment"    →  Executive ask
```

## Try it in 30 seconds

Once installed, paste rough notes into your Claude Code or VS Code chat:

> Turn this into an executive update: This week I worked with engineering on the onboarding flow, tested three versions, and found that many new users do not understand how to use Skills. We plan to add a tutorial next week.

You can also trigger it naturally:

- "Help me write my weekly update."
- "Rewrite this from my manager's perspective."
- "Turn these notes into a concise 1:1 update."
- "把这些零散记录整理成给老板看的周报。"

Name the audience to change what gets emphasized:

> Rewrite this update for the CPO.

## Choose the audience

Boss View supports six decision lenses. The selected lens changes priority, likely follow-up questions, risk framing, and the ask — never the underlying facts.

| Audience | What the update prioritizes |
| --- | --- |
| **CEO** | Strategy, growth, resource allocation, opportunity cost |
| **CPO** | User value, product judgment, learning velocity, adoption |
| **CTO** | Technical risk, dependencies, reliability, scalability |
| **VP Design** | User insight, experience quality, design rationale, cross-functional progress |
| **VP Product** | Product direction, prioritization, roadmap impact, market signal |
| **Direct Manager** | Execution progress, delivery risk, ownership, support needed |

If the audience is not specified and cannot be inferred reliably, Boss View defaults to **Direct Manager** and states the assumption outside the copy-ready update. It never blends all six lenses into one generic report.

## What you get

Every update is organized around a consistent executive narrative:

1. **Executive Summary** — progress, impact, and what comes next in 2–3 sentences
2. **Key Wins** — the few outcomes worth leadership attention
3. **Business Impact** — revenue, growth, adoption, efficiency, customer experience, or risk reduction when supported by evidence
4. **Challenges / Risks** — only meaningful blockers, risks, dependencies, and open questions
5. **Next Steps** — prioritized actions, owners, and timing when provided
6. **Ask** — the decision, resource, alignment, or unblock needed from leadership
7. **Manager Questions** — likely follow-up questions with answer guidance
8. **Copy-ready Version** — a concise final update for Slack, email, Notion, a weekly review, or a 1:1

The same content is assembled into an editorial HTML report using the Offer Toolkit visual system: cream paper, strong hierarchy, decision-first summary, print-safe cards, bilingual content, and a fixed export toolbar.

Sections without useful information can be omitted. If there is no ask, the skill says **No immediate action needed.**

## How it works

```text
1  Extract      What · Why · Result · Metrics · Challenge · Impact · Next · Ask
2  Reframe      Reorder the story around executive priorities
3  Structure    Build the Executive Update and separate signal from activity
4  Anticipate   Predict 3–5 likely manager questions
5  Deliver      Produce a concise, copy-ready version
```

The central transformation is simple:

> **"What did I do?" → "What moved, why does it matter, and what happens next?"**

## Before and after

**Raw input**

> This week I had five meetings, revised the design three times, and discussed many implementation details with engineering.

**Activity-only rewrite — not enough**

> Completed five meetings and three design iterations this week.

**Boss View**

> Aligned Design and Engineering on the new onboarding flow and moved the project toward implementation.

The number of meetings is not the story. The decision, movement, or business outcome is.

## Four principles

1. **Never fabricate** — numbers, results, customer feedback, and business impact must come from the user's input.
2. **Outcomes over activity** — meetings, documents, and iterations matter only when they explain what moved.
3. **Start with what exists** — even sparse or disorganized notes get a useful first draft; the skill asks at most three follow-up questions afterward.
4. **Keep the user's voice** — an ordinary team update should not sound like a CEO keynote. Clear > Concise > Impactful > Authentic.

## Language behavior

The copy-ready update defaults to English for international workplace contexts. If the input is clearly Chinese or the user asks for Chinese, the full update is generated in Chinese. Explanations and follow-up questions follow the user's language.

## Install

Copy this repository into your agent's skills directory:

```bash
git clone https://github.com/yanliudesign/boss-view.git
```

For Claude Code:

```bash
mkdir -p ~/.claude/skills
cp -R boss-view ~/.claude/skills/boss-view
```

For VS Code, place the folder in your prompts/skills location and invoke it from Copilot Chat. The exact skills directory can vary by setup.

## File structure

```text
boss-view/
├── SKILL.md                         # Workflow and output contract
├── examples/
│   └── executive-update-template.html # Single-file report template
├── references/
│   ├── executive-lenses.md          # Six audience decision lenses
│   └── executive-report-spec.md     # HTML generation and validation rules
├── README.md                        # English documentation
└── README.zh.md                     # 中文文档
```

## Good inputs

You do not need to pre-format anything. Useful raw material includes:

- weekly notes or a stream-of-consciousness project update
- launches, decisions, experiments, and customer feedback
- metrics with enough context to interpret them
- blockers, dependencies, open questions, and tradeoffs
- next steps, owners, timing, and requests for leadership

Missing information is marked for follow-up, never filled with invented facts.

## Related links

- [SKILL.md](./SKILL.md) — the complete workflow and output rules
- [Executive audience lenses](./references/executive-lenses.md) — priorities, questions, and asks by role
- [Executive report template](./examples/executive-update-template.html) — the self-contained HTML shell
- [yanliudesign on GitHub](https://github.com/yanliudesign) — more agent skills and design tools

Created by [Dreameryanyan](https://www.linkedin.com/in/yanliudesign/) · [LinkedIn](https://www.linkedin.com/in/yanliudesign/) · [X](https://x.com/yanliudreamer) · [Xiaohongshu](https://www.xiaohongshu.com/notification)