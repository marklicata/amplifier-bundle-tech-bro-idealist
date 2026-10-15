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
