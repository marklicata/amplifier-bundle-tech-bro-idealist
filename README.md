# amplifier-bundle-tech-bro-idealist

A product management bundle for [Amplifier](https://github.com/microsoft/amplifier) that adds a suite of PLG-focused agents and tools to your sessions. Built on opinionated product methodology: PLG fundamentals, evidence-first strategy, and the discipline to distinguish what users *need* vs. what they *want*.

## What's Included

### Product Management Agents (9)

| Agent | `meta.name` | Role |
|-------|-------------|------|
| `agents/product-strategist.md` | `product-strategist` | Vision, mission, ethos, TAM/SAM/SOM, GTM. Enforces the 4 failure mode framework (Vaporware, Fad, Passion Project, Useful-Not-Wanted). |
| `agents/product-growth-planner.md` | `product-growth-planner` | Growth hypotheses by lifecycle stage, 2×2 prioritization, "finding smoke" signals. |
| `agents/product-experiment-designer.md` | `product-experiment-designer` | Falsifiable A/B experiment design, guardrails, statistical planning. |
| `agents/product-metrics-architect.md` | `product-metrics-architect` | North star metrics, metrics ladders, CUJs, flywheel mapping. |
| `agents/data-analyst.md` | `data-analyst` | Cohort, retention, funnel, Quick Ratio, CAC/LTV analysis. Adapts to available tooling. |
| `agents/roadmap-planner.md` | `product-roadmap-planner` | Now/Next/Later roadmaps, RICE scoring, MoSCoW prioritization. |
| `agents/functional-requirements-architect.md` | `product-requirements-architect` | User stories, Given-When-Then specs, data models, API contracts. |
| `agents/product-watchdog.md` | `product-watchdog` | **Review-only** QA guardian — 7-dimension PLG audit. Refuses to create; only reviews. |
| `agents/roadmap-readiness-watchdog.md` | `delivery-readiness-validator` | **Review-only** — validates roadmaps and requirements for engineering feasibility, estimate sanity, and planning fallacy detection. |

All agents share a curated PLG knowledge base covering PLG fundamentals, growth methodology, experiment design, metrics frameworks, and consumer psychology.

### Product 1-Pager (Recipe + Skill)

Generates a structured product brief from any repository — local path, GitHub URL, or any Git URL. Independent of the 9 PM agents.

```bash
# Run as a recipe
amplifier tool invoke recipes operation=execute \
  recipe_path=product-bundle:recipes/product-1-pager.yaml \
  context='{"repo_path": "path/to/your/repo"}'
```

Or load the skill in a session:

```
/skill product-1-pager
```

Classifies the repo's maturity (Research Idea / Prototype / Product), answers 7 core product questions, and produces either a 600-word markdown brief or a schema-exact JSON output.

---

## Installation

### Option 1: Behavior Bundle — recommended for most projects

Adds only the PM agents and `product-1-pager` skill, without the full dependency chain
(no stories, design-intelligence, or dot-graph bundles). Use `--app` to scope it to
the current project:

```bash
amplifier bundle add \
  "git+https://github.com/marklicata/amplifier-bundle-tech-bro-idealist@main#subdirectory=behaviors/product-management.yaml" \
  --app
```

`--app` writes the bundle to your project's `.amplifier/settings.yaml`, making it
available for all Amplifier sessions run from this directory.

### Option 2: Full Bundle

Includes the behavior bundle contents plus the stories, design-intelligence-enhanced,
and dot-graph bundles:

```bash
amplifier bundle add git+https://github.com/marklicata/amplifier-bundle-tech-bro-idealist@main
```

### Option 3: Compose into another bundle

To pull the PM behaviors into your own `bundle.md` without the full dependency chain:

```yaml
includes:
  - bundle: git+https://github.com/marklicata/amplifier-bundle-tech-bro-idealist@main#subdirectory=behaviors/product-management.yaml
```

---

## Usage

Once installed, delegate to agents by `meta.name` in any Amplifier session:

```
Ask product-strategist to help me define a vision for my API-first developer tool
Ask product-metrics-architect to define a north star metric for a PLG SaaS
Ask product-experiment-designer to design an onboarding completion experiment
Ask product-watchdog to review this PRD for PLG alignment
Ask delivery-readiness-validator to review this sprint plan for engineering feasibility
```

### Suggested workflow

Chain the agents for a full product strategy cycle:

1. **`product-strategist`** — Define ethos, vision, mission, and positioning
2. **`product-growth-planner`** — Identify top growth hypotheses for the current lifecycle stage
3. **`product-metrics-architect`** — Define the north star metric and metrics ladder
4. **`product-experiment-designer`** — Design the first experiment to validate the top hypothesis
5. **`product-requirements-architect`** — Write user stories and specs for the top initiative
6. **`product-roadmap-planner`** — Build a Now/Next/Later roadmap with RICE scores
7. **`product-watchdog`** — PLG-lens review of the full body of work
8. **`delivery-readiness-validator`** — Engineering feasibility and planning fallacy review

---

## Knowledge Base

The agents are grounded in a curated PLG knowledge base at `context/product-management/`:

| File | Contents |
|------|----------|
| `Product-LedGrowth.txt` | PLG primer and core mechanics |
| `consumer-fundamentals-handbook.txt` | 546-line foundational PM theory (consumer psychology, user needs) |
| `product-101-ethos-and-user-needs.txt` | Ethos, vision, WANT vs NEED framework |
| `product-102-growth-ideas.md` | Growth hypotheses, lifecycle stages, "finding smoke" |
| `product-103-experiment-fundamentals.md` | Falsifiable experiment templates, statistical guardrails |
| `product-104-metrics.md` | North star metrics, CUJs, flywheel modeling, Quick Ratio |
| `product-105-positioning-and-gtm.md` | Positioning strategy, go-to-market planning |
| `product-review-templates/` | P365 product review deck templates (emerging and established products) |

> **Note:** `1-pagers/` (recipe output examples) and `skills-for-external-tools/` (portable SKILL.md exports for non-Amplifier AI tools) are gitignored and not included in the distributed bundle.

---

## Development

```bash
git clone https://github.com/marklicata/amplifier-bundle-tech-bro-idealist
cd amplifier-bundle-tech-bro-idealist
```

The bundle uses no Python packaging (`pyproject.toml`) — it is a pure content bundle distributed via Git URL.

---

## License

MIT
