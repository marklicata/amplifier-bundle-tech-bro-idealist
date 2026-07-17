# PM Agent Suite - Implementation Plan

## Overview

This document outlines the PM agent suite designed to support Product-Led Growth (PLG) practices based on comprehensive PM documentation including Product 101-105 playbooks, Consumer Fundamentals Handbook, and P365 review templates.

## Agent Suite (6 agents)

### Core Implementation Agents (1-5)

These agents have deep domain knowledge and **create** the work products.

#### 1. product-strategist
**Coverage:** Product 101 (Ethos & User Needs) + Product 105 (Positioning & GTM)

**Role:** Helps define product ethos, identify user needs, and develop go-to-market strategy

**Responsibilities:**
- Product purpose, vision, mission, strategy
- User needs identification (research, feedback, trends)
- Competitive analysis and differentiation
- Value proposition and positioning
- Market analysis (TAM, SAM, SOM)
- GTM planning and launch readiness

**Tools needed:**
- ✅ tool-filesystem - Read/write strategy docs
- ✅ tool-search - Find existing strategies, research docs
- ✅ tool-web - Competitive research, market trends
- ⚠️ tool-data-query (optional) - Access high-level product metrics to inform strategy
[FEEDBACK] leverage the data analyst agent here instead of trying to query data directly. Give that agent a question, let it do it's job.

---

#### 2. product-growth-planner
**Coverage:** Product 102 (Growth Ideas)

**Role:** Identifies growth opportunities and prioritizes investments

**Responsibilities:**
- Assesses product lifecycle stage (incubation → PMF → hypergrowth → mature)
- Generates growth hypotheses based on data/research
- Estimates impact and sequences investments
- Balances portfolio (incremental vs big bets)
- "Finding smoke" - quick validation approaches
- Microsoft Plus integration opportunities
[FEEDBACK] Forget about Microsoft Plus. You can remove any/all references to it. We do not care about Mircosoft Plus.

**Tools needed:**
- ✅ tool-filesystem - Read/write growth plans
- ✅ tool-search - Find user research, past experiments
- ✅ tool-web - Research growth tactics, competitor analysis
- ⚠️ tool-calculator or tool-python-exec (medium priority) - Impact estimation calculations, prioritization scoring
[FEEDBACK] Apply sound logic and do this yourself. No need to call a tool.

---

#### 3. product-metrics-architect
**Coverage:** Product 104 (Metrics)

**Role:** Designs measurement systems and metrics hierarchies

**Responsibilities:**
- Builds metrics ladders (north star → output → input)
- Defines lifecycle metrics (acquisition, engagement, retention)
- Creates critical user journey funnels
- Designs re-engagement loops and flywheels
- Establishes guardrail metrics

**Tools needed:**
- ✅ tool-filesystem - Read/write metrics definitions
- ✅ tool-search - Find existing metrics, funnels
- 🟢 tool-visualization (nice-to-have) - Create funnel diagrams, metrics ladders (Mermaid markdown is acceptable workaround)

---

#### 4. product-experiment-designer
**Coverage:** Product 103 (Experiment Fundamentals)

**Role:** Turns growth ideas into rigorous A/B experiments

**Responsibilities:**
- Formulates falsifiable hypotheses
- Defines success metrics and guardrails
- Designs experiment parameters (exposure %, timing, variants)
- Statistical analysis planning
- Experiment documentation and templates

**Tools needed:**
- ✅ tool-filesystem - Write experiment specs
- ✅ tool-search - Find past experiments, learnings
- 🟠 tool-stats-calculator (medium priority) - Statistical power analysis, sample size calculations, confidence intervals
[FEEDBACK] Yes, this is good. Let's track this as a needed tool to be created.

---

#### 5. data-analyst
**Coverage:** Consumer Fundamentals Handbook (analysis sections)

**Role:** Analyzes existing product data to generate insights

**Responsibilities:**
- Cohort retention analysis
- Power user curve analysis
- Funnel drop-off identification
- Quick Ratio and lifecycle metrics
- Growth loop performance
- Identifies patterns in user behavior
- CAC, LTV, ARPU analysis

**Tools needed:**
- ✅ tool-filesystem - Write analysis reports
- 🔴 tool-data-query (CRITICAL!) - Connect to SQL databases, Kusto, Snowflake, BigQuery, etc.
- 🔴 tool-python-exec or tool-notebook (CRITICAL!) - Run Python for data manipulation (pandas, numpy)
[FEEDBACK] Instead of trying to define what tools we need right now for data retrieval. Let's have the agent look at what tools are availble in the session. And then select from the appropriate tools to retrieve data. If no tools can be found, tell the user that. Ask for the data directly.

- 🟡 tool-visualization (HIGH priority) - Create charts: retention curves, power user curves, funnels
[FEEDBACK] This is also a good tool to have. Track this as a tool to be created.

**Note:** Without the critical tools, data-analyst will be severely limited in capabilities.

---

### Quality Assurance Agent (6)

#### 6. product-watchdog
**Coverage:** PLG best practices + Consumer Fundamentals + P365 standards

**Role:** Pressure tests PM plans and ensures PLG best practices (like code-reviewer for PM work)

**IMPORTANT:** This agent REVIEWS work, it does NOT CREATE strategies. It delegates to specialized agents for creation.

**What it reviews:**
- Product strategies from product-strategist
- Growth plans from product-growth-planner
- Metrics designs from product-metrics-architect
- Experiment designs from product-experiment-designer
- Data interpretations from data-analyst

**How it reviews:**
- ✅ Best practices check - Aligns with PLG principles?
- ✅ Clarity assessment - Are hypotheses falsifiable? Metrics clear?
- ✅ Assumption challenge - What's being assumed? What if it's wrong?
- ✅ Completeness check - Missing critical elements? (guardrails, tradeoffs, etc.)
- ✅ Philosophy alignment - Ruthless simplicity? User-first?
- ✅ Gap identification - What's not addressed?
- ✅ Risk surfacing - What could go wrong?

**Tools needed:**
- ✅ tool-filesystem - Read plans/docs to review
- ✅ tool-search - Find relevant context, best practices
- None new (has deep @-mentioned context from all PLG docs)

**Output format:**
```markdown
## Review: [Plan Name]

### Strengths
- [What's working well]

### Concerns
- [Issues to address]
- [Assumptions to validate]
- [Missing elements]

### PLG Alignment
- [How well does this follow PLG principles]
- [Specific PLG patterns to leverage]

### Recommendations
- [Specific improvements]
- [Next steps]
```

---

## Workflow Pattern

### Correct Pattern (Review, Don't Build)

```
User: "Help me build a growth strategy"
  ↓
product-strategist: Creates strategy document
  ↓
product-watchdog: Reviews it, finds gaps, challenges assumptions
  ↓
product-strategist: Refines based on feedback
  ↓
product-watchdog: Validates improvements
  ↓
Done
```

### Incorrect Pattern ❌

```
User: "Help me build a growth strategy"
  ↓
product-watchdog: Tries to build strategy ❌ (Wrong! Not its job!)
```

---

## Tool Requirements Summary

### Existing Amplifier Tools (Available Now)
- ✅ tool-filesystem - File read/write operations
- ✅ tool-search - Grep/glob for finding content
- ✅ tool-web - Web search and fetch
- ✅ tool-bash - Shell command execution

### New Tools Needed

#### 🔴 CRITICAL (Agents won't be effective without these)

##### tool-data-query
**For:** data-analyst (blocker)

**Capabilities:**
- Connect to databases/warehouses (SQL, Kusto, Snowflake, BigQuery, etc.)
- Run queries on product data
- Return structured results (JSON, CSV)
- Handle authentication/credentials
- Support parameterized queries

**Why critical:** Without this, data-analyst can only analyze data already in files, severely limiting usefulness.

##### tool-python-exec
**For:** data-analyst (blocker)

**Capabilities:**
- Execute Python code in isolated environment
- Access to data science libraries: pandas, numpy, scipy, statsmodels
- Data manipulation and transformation
- Statistical calculations
- Return structured results

**Why critical:** Complex data analysis (cohort analysis, retention curves, statistical tests) requires computational capabilities beyond basic tools.

#### 🟡 HIGH (Significantly improves capabilities)

##### tool-visualization
**For:** data-analyst, product-metrics-architect

**Capabilities:**
- Create charts and graphs (line, bar, scatter, heatmap)
- Specialized PM charts: retention curves, power user curves, funnels
- Libraries: plotly, matplotlib, seaborn
- Output as images or interactive HTML
- Support for annotations and styling

**Why high priority:** Visual analysis is core to PM work. Text descriptions are inadequate substitutes.

#### 🟠 MEDIUM (Nice to have, can work around)

##### tool-calculator or tool-stats-calculator
**For:** product-growth-planner, product-experiment-designer

**Capabilities:**
- Complex mathematical calculations
- Statistical power analysis
- Sample size estimation
- Confidence interval calculations
- Impact modeling

**Why medium:** Can use Python thinking or tool-python-exec as workaround, but dedicated tool is cleaner.

#### 🟢 LOW (Can defer)

##### tool-diagramming
**For:** product-metrics-architect

**Capabilities:**
- Create flow diagrams, funnels
- Metrics ladder visualizations
- System diagrams

**Why low:** Mermaid markdown syntax is acceptable workaround.

---

## Implementation Phases

### Phase 1: Build Core Agents (Agents 1-4, 6)
**Timeline:** Immediate

**Agents to build:**
1. product-strategist
2. product-growth-planner
3. product-metrics-architect
4. product-experiment-designer
5. product-watchdog

**Why start here:** These agents can be effective with existing tools. They cover the majority of PM planning workflows.

**Dependencies:** 
- Existing Amplifier tools only
- PLG documentation context files

---

### Phase 2: Build Critical Data Tools
**Timeline:** Before building data-analyst

**Tools to build:**
1. tool-data-query - Database/warehouse connector
2. tool-python-exec - Python execution environment
3. tool-visualization - Chart generation

**Why critical:** data-analyst is severely limited without these tools.

**Technical considerations:**
- Security: Sandboxed Python execution
- Authentication: Credential management for data sources
- Performance: Query timeouts, result size limits
- Output formats: Structured data + visualization formats

---

### Phase 3: Build data-analyst
**Timeline:** After Phase 2 tools complete

**Agent to build:**
- data-analyst

**Why wait:** Building this agent without proper tools would create a poor experience and set wrong expectations.

---

## Alternative: Simplified data-analyst (Not Recommended)

We could build a **limited data-analyst** in Phase 1 that:
- Only analyzes data that's already in files (CSV, JSON)
- Uses tool-bash to run simple Python scripts
- Outputs text-based analysis

**However:**
- ❌ Severely limited compared to what it should do
- ❌ Sets wrong expectations about capabilities
- ❌ Requires rebuilding once proper tools exist
- ❌ Poor user experience

**Recommendation:** Wait for Phase 2 tools, build it right once.

---

## Agent Activation Patterns

### When to use core agents:
- **product-strategist:** "Help me define our product strategy" / "What should our value proposition be?"
- **product-growth-planner:** "What growth investments should we prioritize?" / "How do we sequence these experiments?"
- **product-metrics-architect:** "Help me design a metrics system" / "What should our north star metric be?"
- **product-experiment-designer:** "Turn this growth idea into an experiment" / "Design an A/B test for this feature"
- **data-analyst:** "Analyze retention for last month's cohort" / "What does our power user curve show?"

### When to use product-watchdog:
Use PROACTIVELY after any core agent completes work:
- After product-strategist creates a strategy → Review for PLG alignment
- After product-growth-planner creates a plan → Challenge assumptions
- After product-metrics-architect designs metrics → Check for guardrails
- After product-experiment-designer designs experiment → Validate hypothesis quality
- After data-analyst generates insights → Review interpretation quality

---

## Success Metrics

### Agent Quality Indicators
- Clear activation triggers in descriptions
- Well-defined workflows with step-by-step processes
- Concrete output formats with templates
- Philosophy alignment (PLG principles)
- Appropriate tool declarations

### Usage Metrics
- Frequency of agent invocations
- product-watchdog review coverage (% of plans reviewed)
- Iteration cycles (how many rounds before approval)
- User satisfaction with agent outputs

---

## Next Steps

1. ✅ Document agent plan (this file)
2. ⬜ Build Phase 1 agents (1-4, 6) using AGENT_TEMPLATE.md
3. ⬜ Define detailed specs for Phase 2 tools
4. ⬜ Build Phase 2 tools
5. ⬜ Build Phase 3 agent (data-analyst)
6. ⬜ Iterate based on usage patterns

---

## Questions to Resolve

1. **Tool priorities:** Should we build any Phase 2 tools in parallel with Phase 1 agents?
2. **Data sources:** What specific databases/warehouses need tool-data-query support?
3. **Python environment:** Sandboxed execution vs container-based vs cloud function?
4. **Visualization format:** Static images vs interactive HTML vs both?
5. **Calculator needs:** Separate tool-stats-calculator or fold into tool-python-exec?

---

**Version:** 1.0  
**Created:** 2026-01-13  
**Status:** Planning Phase
