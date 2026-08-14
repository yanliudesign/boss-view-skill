# Executive Update HTML Report Specification

Boss View's default deliverable is a shareable, single-file HTML report built from [../examples/executive-update-template.html](../examples/executive-update-template.html). The visual system intentionally matches Offer Toolkit: cream paper, editorial typography, strong hierarchy, yellow emphasis, print-safe atomic cards, and a fixed export toolbar.

The toolbar must provide language switching, Markdown download, and PDF export through the browser print dialog.

## When to generate

- Generate the HTML report after the user provides any usable work notes, even if they are incomplete.
- Do not delay the first draft to collect every missing field. Mark gaps and ask at most three follow-up questions after delivery.
- Skip HTML only when the user explicitly requests a text-only output such as “只给我一段 Slack 文案” or “email text only.”
- When the user supplies corrections, regenerate the same file unless they ask to preserve versions.

## File location and name

Default:

```text
~/Desktop/Claude skills/executive-update-<project-or-team-slug>-<YYYYMMDD>.html
```

If the project or team is unknown, use `general`. Create the directory if it does not exist. After writing, open the report with the operating system's standard command.

## Required report order

1. Header: project/team, reporting period, one-line context
2. Facts strip: audience, owner, status, decision deadline
3. Assumptions: every unsupported input dependency, independently correctable
4. Executive Summary: headline, 2–3 sentence summary, status signal
5. “If you only read three things”: exactly three takeaways
6. Audience Lens: priorities and intentionally deprioritized detail
7. Key Wins: 2–4 `Action → Result → Impact` items
8. Business Impact: supported impact plus explicit `Impact to quantify` gaps
9. Challenges / Risks: only Blocker, Risk, Dependency, or Open Question
10. Next Steps: 2–4 `Action · Owner · Timeline` items
11. Ask: one decision or support request; use `No immediate action needed` when absent
12. Manager Questions: 3–5 lens-specific questions with answer guidance
13. Copy-ready Version
14. Full branded footer

## Template filling rules

- Replace every `{{PLACEHOLDER}}`; no braces may remain in the final report.
- Repeated placeholders ending in `_HTML` must contain valid semantic HTML using the template's existing classes.
- User-visible generated copy must be bilingual using adjacent `<span data-lang="en">…</span><span data-lang="zh">…</span>` pairs. Names, dates, numbers, static labels, and URLs do not need translation.
- Never infer metrics, owner, timeline, status, deadline, results, or business impact. Use `[需要补充]` / `[To confirm]`.
- Do not create a numeric score when the input does not define a scoring system. `STATUS_SIGNAL` must be a factual word such as `ON TRACK`, `AT RISK`, `BLOCKED`, or `UPDATE`; otherwise use `UPDATE`.
- The selected audience lens changes emphasis and questions, never facts.

## Repeated component shapes

```html
<!-- KEY_WINS_HTML -->
<article class="win"><div><h3>Headline</h3><p>Action → Result → Impact</p></div></article>

<!-- IMPACT_CARDS_HTML -->
<article class="impact-card"><div class="label">Adoption</div><div class="value">5,000</div><p>Evidence and meaning</p></article>
<article class="impact-card to-quantify"><div class="label">Impact to quantify</div><div class="value">[TBD]</div><p>Metric needed</p></article>

<!-- RISKS_HTML -->
<article class="risk"><div class="type">Risk</div><p>Risk and consequence</p></article>
<article class="risk blocker"><div class="type">Blocker</div><p>Blocker and needed action</p></article>
<article class="risk dependency"><div class="type">Dependency</div><p>Dependency and owner if known</p></article>

<!-- NEXT_STEPS_HTML -->
<article class="step"><div class="index">01</div><div><h3>Action</h3><p>Expected outcome</p></div><div class="owner">Owner · Timeline</div></article>

<!-- MANAGER_QUESTIONS_HTML -->
<details class="question" open><summary>Likely question</summary><div class="answer">Answer guidance or missing evidence</div></details>
```

## Required validation

Before opening the file, verify:

1. No `{{PLACEHOLDER}}` remains.
2. All IDs exist: `lens`, `summary`, `wins`, `impact`, `risks`, `next`, `ask`, `questions`, `copy`.
3. Footer contains `Dreameryanyan`, `brand-mark`, `yanliudreamer`, and `xiaohongshu`.
4. The file contains `toggleLang`, `exportMarkdown`, `window.print`, and `@media print` for language, Markdown, and PDF export.
5. HTML parses without an unclosed tag error.

Do not remove the footer or export toolbar to shorten the report.