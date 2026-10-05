<h1 align="center">Product Aesthetics</h1>
<p align="center"><strong>Ship the product. Let your agent inspect the experience.</strong></p>
<p align="center">Browser-driven aesthetics audits for Codex &amp; Claude Code.<br/>0–100 scores · Evidence-backed issues · Prioritized fixes</p>
<p align="center"><a href="#quick-start">Quick start</a> · <a href="#how-it-works">Workflow</a> · <a href="#scoring">Scoring</a> · <a href="#requirements">Requirements</a></p>


## Your agent does the inspection

Give your agent a local project or a running URL. It starts or connects to the app, opens browser tools, inspects the experience, captures screenshots, and returns an actionable audit. **No manual screenshots required in the normal workflow.**

- Inspect representative pages, desktop/mobile layouts, and the primary journey.
- Check visible hierarchy, typography, component rules, feedback, and brand coherence.
- Score eight dimensions with explicit evidence and disclose untested areas.
- Deliver the highest-value fixes with priorities, estimated effort, and acceptance criteria.
- Implement changes when requested, then re-audit the same scope.

## Quick start

Clone this repository:

```bash
git clone https://github.com/kain26/product-aesthetics-skill.git
```

From the **product project you want to inspect**, copy the skill directory. Replace the source path below with your clone's actual location. Preserve any existing customized installation.

### Codex

```bash
mkdir -p .agents/skills
cp -R /path/to/product-aesthetics-skill/skills/product-aesthetics .agents/skills/
```

```text
$product-aesthetics Audit this project. Start the existing dev setup,
use browser tools to inspect desktop and mobile, test the main journey,
and capture screenshots yourself. Give a 0–100 score and prioritized
fixes with acceptance criteria. Audit only; do not modify the product.
```

For a personal installation, copy the same directory to `~/.agents/skills/`.

### Claude Code

```bash
mkdir -p .claude/skills
cp -R /path/to/product-aesthetics-skill/skills/product-aesthetics .claude/skills/
```

```text
/product-aesthetics Audit this project. Start the existing dev setup,
use browser tools to inspect desktop and mobile, test the main journey,
and capture screenshots yourself. Give a 0–100 score and prioritized
fixes with acceptance criteria. Audit only; do not modify the product.
```

For a personal installation, copy the same directory to `~/.claude/skills/`.

Both agents use the same `SKILL.md` and references. `agents/openai.yaml` provides Codex display metadata. Official installation guidance: [Codex](https://developers.openai.com/codex/skills) · [Claude Code](https://code.claude.com/docs/en/skills).

## How it works

![Agent-driven review workflow](assets/workflow.svg)

This is a Markdown Agent Skill: a reusable inspection procedure, rubric, and reporting contract loaded by your agent. The host supplies the language model, terminal, browser control, and screenshot inspection capabilities.

1. **Start or connect.** Read the existing project setup and reuse or start its dev server; connect directly to a running remote URL.
2. **Inspect.** Navigate representative pages, test the primary journey, and examine intended screen sizes and reachable states.
3. **Capture evidence.** Take and inspect screenshots; record route, viewport, state, and concrete observations.
4. **Evaluate.** Judge function, visual order, interaction, and brand together using fixed scoring anchors.
5. **Deliver.** Connect each problem to a location, user impact, concrete change, and acceptance check.
6. **Recheck.** After requested changes, repeat the same pages, viewports, and states.

The agent owns evidence collection. If startup, tools, or access are blocked, it reports the specific blocker and asks for the missing prerequisite rather than making manual screenshots the default.

## Scoring

### Eight dimensions · 100 points

| Dimension | Weight | Evaluate |
|---|---:|---|
| Purpose & task clarity | 15 | Clear purpose and next actions |
| Hierarchy & composition | 20 | Reading order, grouping, density, spacing |
| Typography & readability | 15 | Type roles, scale, reading comfort |
| Color & material logic | 10 | Semantic color, contrast, surface treatments |
| Component consistency | 15 | Stable rules within and across screens |
| Interaction & feedback | 10 | Focus, transitions, loading/error/success states |
| Responsive & inclusive presentation | 10 | Intended sizes and inspected access paths |
| Brand coherence | 5 | A visual language appropriate to the product |

Each observed dimension receives an integer rating from 0 to 5:
**0** fundamental breakdown · **1** widespread severe defects · **2** repeated inconsistency · **3** competent but unfinished · **4** strong with localized gaps · **5** exceptional coherence supported by evidence.

```text
Dimension contribution = weight × rating / 5
Score = round-half-up(100 × sum(contributions) / sum(observed weights))
Coverage = sum(observed weights) / 100
```

Unobserved dimensions are **U**, not zero. For example, observed weight 80 and contribution 50 yield a provisional score of **63/100**, with **80% rubric coverage**. Coverage does not measure the percentage of all product behavior tested.

| Score | Interpretation |
|---|---|
| 90–100 | Exceptional coherence |
| 80–89 | Polished with localized gaps |
| 70–79 | Coherent, visibly unfinished |
| 60–69 | Substantial inconsistency |
| 40–59 | Fragmented experience |
| 0–39 | Fundamental breakdown |

Every deduction needs evidence. Density can suit a trading terminal; whitespace can suit a reading product. Minimalism, gradients, glass, and dark mode never earn automatic bonuses or penalties.

## What you get

| Output | Contents |
|---|---|
| Scorecard | Overall score, dimension ratings, coverage, confidence |
| Diagnosis | The main pattern making the experience feel unfinished |
| Keep | 1–3 verified strengths |
| Fix first | 3–5 key issues, locations, impact, priorities, effort |
| Verification | Acceptance criteria for each proposed change |
| Agent handoff | A cohesive implementation prompt grounded in findings |

**P0:** observed primary-task blocker or unreadable essential content. **P1:** repeated, high-impact hierarchy/system issues. **P2:** localized polish. Optional taste preferences stay separate.

## More ways to use it

**Deployed product**

```text
Use product-aesthetics to audit https://your-product.example.
Use browser tools, inspect representative pages and the primary journey,
and capture the evidence yourself. Explain what to fix first and why.
```

**Implement and re-audit**

```text
Implement the P1 fixes from the audit. Preserve existing functionality
and brand direction. Recheck the same pages, viewports, and states
with browser tools. Report verified improvements and remaining issues.
```

**Compare versions**

```text
Use product-aesthetics to compare these two versions with the same
rubric, routes, viewports, and states. Explain comparability limits
if evidence scope differs. Do not predict an unverified future score.
```

## Requirements

Your agent needs a permitted runtime for local startup, browser tools, and screenshot inspection. This skill defines their use; it does not bundle a browser, provision hosting, or provide credentials. Dependency setup follows the project and host's authorization rules.

A full product score requires observations for every dimension, a tested primary journey, and the intended platform scope. Partial evidence produces an explicitly scoped provisional score. If no rendered evidence can be obtained after attempting startup, the agent reports implementation risks without inventing a visual score. User-supplied screenshots remain an optional, explicitly chosen fallback.

Scores are structured judgments, not objective measurements, conversion predictions, or launch certification. A high aesthetic score can coexist with a P0 interaction defect.

## Resources

- [Skill instructions](skills/product-aesthetics/SKILL.md)
- [Rubric v1.0](skills/product-aesthetics/references/rubric.md)
- [Report format](skills/product-aesthetics/references/report.md)
- [SVG workflow](assets/workflow.svg)

## Validation status

Skill structure has been validated. An earlier source-only scenario was independently checked to ensure no visual score was invented. The browser-led revision has not yet received an end-to-end product benchmark or a Claude Code runtime test. Shared format compatibility does not guarantee identical model scores.
