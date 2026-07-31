---
name: product-1-pager
description: >
  Generate a concise product 1-pager for an engineering research project by pointing
  at a repository. Answers the seven questions senior leaders need to understand how
  the work connects to real products and users. Use when someone says "create a product
  1-pager", "analyze this project for product fit", "where does this fit in our
  product portfolio", or "what's the product story for this repo".
metadata:
  version: "1.0.0"
context: fork
---

# Product 1-Pager Generator

You are generating a product 1-pager for an engineering research project.

The user has given you a repo path. Your job is to explore it, apply the product
framework below, and return a concise 1-pager that a senior leader can read in
90 seconds.

---

## Step 1 — Explore the Repo

Delegate to `foundation:explorer` with the repo path from the user's message.

Ask the explorer to find and report (not interpret — just facts):

- **What the project does** in plain language (no jargon, no acronyms)
- **Maturity signals**: tests, CI/CD, deployment configs (Dockerfile, k8s, terraform),
  versioned releases, live URLs, hosted demos, published packages
- **The problem it solves**: what breaks without this, who feels that pain — quote the
  source (README, comments, commit message)
- **Users/customers/partners**: any named people, roles, teams, or orgs mentioned
  anywhere in the repo
- **Evidence of validation**: metrics, benchmarks, user feedback, papers, partner
  conversations, leadership interest, funding
- **Connected product teams**: any signal about which product org would consume this

Tell the explorer: **"NOT FOUND" is the right answer when something isn't there.
Do not infer or invent users, customers, or validation.**

---

## Step 2 — Apply the Framework

### Stage Classification

Pick EXACTLY ONE based on evidence — not on what the team hopes it will become:

| Stage | Signal | Value Delivered |
|---|---|---|
| **Research Idea** | No users, no deployment, early exploration | Insights that improve a product |
| **Prototype** | Working demo, some users, not production-ready | Insights + code that improve a product |
| **Product** | Deployed, real users, actively maintained | Complete capability we ship ourselves |

> **Be honest.** Most research repos are Research Idea or Prototype.
> Over-classifying destroys the document's credibility with senior leaders.

### The 7 Questions

Answer each with bullets or short phrases. Trace every claim to the repo findings.

**Two modes — know which applies to each question:**

For questions 1, 2, 3, and 7: if the answer isn't clear from the repo, write your best
framing hypothesis based on what the project does and its likely domain. These developers
won't have clear answers — help them think it through. But label every hypothesis clearly as
`[AI Recommendation — needs your review]` so they know it's a starting point, not a fact.

For questions 4 and 5: if the answer isn't there, write the specific "Unknown" label below
and stop. Do not invent evidence. Do not guess at a partner team. A blank is honest;
a fabricated signal is harmful.

1. **What is the problem?** — What breaks without this? Who suffers?
   If unclear: write `[AI Recommendation — needs your review]:` + your framing hypothesis.

2. **Who are the users?** — A specific role, team, or segment. Never "everyone."
   If unclear: write `[AI Recommendation — needs your review]:` + your framing hypothesis.

3. **What are their needs/wants?** — Needs = must-haves. Wants = nice-to-haves.
   If unclear: write `[AI Recommendation — needs your review]:` + your framing hypothesis.

4. **What evidence do we have that it matters?** — Data, feedback, partner ask, leadership signal.
   If none found: `Unknown — needs real data signal.` Do not invent.

5. **Which team owns this space?** — The product team or org that should consume this output.
   If unknown: `Unknown — needs a partner team.` Do not guess.

6. **Have we talked to them?** — Yes / No / Partial + what you learned (1 bullet if yes).

7. **What would success look like?** — A concrete outcome. Not "we ship a feature" —
   an actual change in the world.
   If unclear: write `[AI Recommendation — needs your review]:` + your framing hypothesis.

### Impact Path

Map the stage to the expected impact for this specific project:

- **Research Idea** → insights that improve [name the product/team if known]
- **Prototype** → insights + prototypes/code that improve [name the product/team if known]
- **Product** → entire capability we ship ourselves

---

## Step 3 — Write the 1-Pager

Output this format. Max 400 words. Bullets and phrases only — no prose paragraphs.

Use as many bullets as the content needs — some answers are one bullet, some need 2–3.
Don't pad to fill a slot, and don't compress a richer answer into one bullet just because
the template shows one. Structure serves the content, not the other way around.

```
## [Project Name] — Product 1-Pager

**Stage**: [Research Idea | Prototype | Product]

---

**The Problem**
- [1+ bullets — or "[AI Recommendation — needs your review]: [hypothesis]"]

**The Users**
- [1+ bullets — or "[AI Recommendation — needs your review]: [hypothesis]"]

**Needs / Wants**
- Needs: [1+ bullets — or "[AI Recommendation — needs your review]: [hypothesis]"]
- Wants: [1+ bullets — or "[AI Recommendation — needs your review]: [hypothesis]"]

**Evidence It Matters**
- [1+ bullets — or "Unknown — needs real data signal"]

**Who Owns This Space**
- [team/org — or "Unknown — needs a partner team"]

**Have We Talked to Them?**
- [Yes / No / Partial + key learnings in 1 bullet]

**What Success Looks Like**
- [1+ bullets — or "[AI Recommendation — needs your review]: [hypothesis]"]

---

**Impact Path**
[One sentence: this [stage] delivers [what] to [which product/team if known]]

**Open Questions**
1. [The question that would most change the project's direction if answered]
2. [Second most important]
3. [Third]
```

Replace [Project Name] with the actual project name from the repo.

The Open Questions are the most valuable section for a low-product-sense engineering
team — make them the questions that move the work forward, not trivia.

---

## Final Action

Write the completed 1-pager to `product-1-pager.md` in the **current working directory**
(wherever Amplifier is being run from — not necessarily inside the target repo).

> **Note for users:** If you run this from inside the repo you're analyzing, the file lands
> there. If you run it from another directory while pointing at a repo elsewhere, the file
> lands in your current directory. Either way, the full file path is printed so you can find it.

Then return the full file contents so the user can read it without opening it.
