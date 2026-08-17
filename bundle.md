---
bundle:
  name: product-bundle
  version: 1.0.0
  description: A specialized bundle for creating product-related content with research and file management capabilities

includes:
  - bundle: git+https://github.com/microsoft/amplifier-bundle-stories@main#subdirectory=behaviors/stories.yaml
  - bundle: git+https://github.com/microsoft/amplifier-bundle-design-intelligence@main#subdirectory=behaviors/design-intelligence.yaml
  - bundle: git+https://github.com/microsoft/amplifier-bundle-dot-graph@main#subdirectory=behaviors/dot-graph.yaml

###########################################################################################
# Foundation already provides: providers, tools (filesystem, web, bash), session config   #
###########################################################################################
# session:
#   orchestrator:
#     module: loop-streaming
#     source: git+https://github.com/microsoft/amplifier-module-loop-streaming@main
#   context:
#     module: context-simple
#     source: git+https://github.com/microsoft/amplifier-module-context-simple@main
# tools:
#   - module: tool-filesystem
#     source: git+https://github.com/microsoft/amplifier-module-tool-filesystem@main
#   - module: tool-bash
#     source: git+https://github.com/microsoft/amplifier-module-tool-bash@main
#   - module: tool-web
#     source: git+https://github.com/microsoft/amplifier-module-tool-web@main
# hooks:
#   - module: hooks-logging
#     source: git+https://github.com/microsoft/amplifier-module-hooks-logging@main

agents:
  include:
    - product-bundle:data-analyst
    - product-bundle:roadmap-planner
    - product-bundle:functional-requirements-architect
    - product-bundle:roadmap-readiness-watchdog
    - product-bundle:product-experiment-designer
    - product-bundle:product-growth-planner
    - product-bundle:product-metrics-architect
    - product-bundle:product-strategist
    - product-bundle:product-watchdog

tools:
  - module: tool-skills
    config:
      skills:
        - "@product-bundle:skills"
---

# Product Management Bundle

A comprehensive bundle for product managers, providing specialized AI agents for strategic planning, metrics design, experimentation, and growth analysis.

## Overview

This bundle extends Amplifier Foundation with product management capabilities, including:

- **Strategic Planning**: High-level product strategy and roadmap development
- **Metrics & Analytics**: Design and analyze product metrics and KPIs
- **Experimentation**: Design and analyze product experiments
- **Growth Planning**: Identify and prioritize growth opportunities
- **Data Analysis**: Analyze product data and generate insights
- **Product Monitoring**: Track product health and user behavior

## Included Agents

### Product Management

| Agent | Purpose |
|-------|---------|
| `product-strategist` | Strategic product planning and roadmap development |
| `product-metrics-architect` | Design metrics frameworks and KPIs |
| `product-experiment-designer` | Design A/B tests and experiments |
| `product-growth-planner` | Identify growth levers and opportunities |
| `product-watchdog` | Monitor product health and anomalies |

### Data Science

| Agent | Purpose |
|-------|---------|
| `data-analyst` | Analyze product data and generate insights |

## Usage

Add this bundle to your Amplifier configuration:

```bash
# Add as app-level bundle (available in all sessions)
amplifier bundle add git+https://github.com/microsoft-amplifier/amplifier-shared@main --app

# Or use in a specific session
amplifier run --bundle git+https://github.com/microsoft-amplifier/amplifier-shared@main
```

### Example: Strategic Planning

```
"I need help with product strategy. Use the product-strategist agent to analyze our market position and competitive landscape."
```

### Example: Metrics Design

```
"Use the product-metrics-architect to design a metrics framework for our new feature launch."
```

### Example: Experiment Design

```
"Help me design an A/B test for our pricing page using the product-experiment-designer."
```

## Requirements

- Amplifier Foundation (included automatically)
- GitHub CLI (`gh`) authenticated
- Access to microsoft-amplifier/amplifier-shared repository

## Development

To add new agents or modify this bundle:

1. Clone the repository
2. Add agent definitions to `agents/product-management/` or `agents/data-science/`
3. Update the `agents.include` list in this bundle.md
4. Test locally: `amplifier run --bundle ./bundle.md`
5. Push changes and sync will propagate to users

## License

MIT License - See repository for details
