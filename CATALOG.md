# Curated external skill and plugin sources

This catalog links to upstream projects. The local folders created for some entries are curated adaptations, not full mirrors of upstream repositories. Original projects remain owned and licensed by their maintainers.

## Software engineering and web
- [obra/superpowers](https://github.com/obra/superpowers) — planning, TDD, debugging and review; registered as an upstream plugin.
- [mattpocock/skills](https://github.com/mattpocock/skills) — requirements and engineering workflow; registered as an upstream plugin.
- [affaan-m/ECC](https://github.com/affaan-m/ECC) — agents, skills, hooks, security and workflows. The local `plugins/ecc` entry is a curated subset, not the full ECC package.
- [nextlevelbuilder/ui-ux-pro-max-skill](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill) — UI/UX design systems; registered as an upstream plugin.
- [wshobson/agents](https://github.com/wshobson/agents) — source inspiration for local backend-development, frontend-mobile-development and security-scanning skills. These local folders are curated adaptations, not full copies.
- [anthropics/knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins) — source reference for the local engineering-workflows skill. The local folder is a curated adaptation, not a full copy.
- [vercel-labs/agent-skills](https://github.com/vercel-labs/agent-skills) — React best practices and web design guidelines.
- [WordPress/agent-skills](https://github.com/WordPress/agent-skills) — WordPress development and maintenance.
- [coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills) — SEO, CRO, analytics and growth workflows.
- [trailofbits/skills](https://github.com/trailofbits/skills) — application security and secure development; check per-skill license.
- [anthropics/skills](https://github.com/anthropics/skills) — official skill examples, frontend design, web app testing and document workflows.

## Research and academic
- [Imbad0202/academic-research-skills](https://github.com/Imbad0202/academic-research-skills) — full academic research pipeline: deep research, paper writing, peer review, systematic reviews, PRISMA screening, citation verification. **58.5k stars**. Ideal for medical/NICU research. CC-BY-NC-4.0.

## Finance and trading
- [tradermonty/claude-trading-skills](https://github.com/tradermonty/claude-trading-skills) — structured trading workflows: market regime analysis, portfolio review, swing trading, risk management, trade journaling, backtesting. **8.4k stars**. Workflow patterns adaptable to clinical protocols. MIT.

## Security
- [SnailSploit/Claude-Red](https://github.com/SnailSploit/Claude-Red) — 100+ offensive security skills: SQLi, XSS, SSRF, RCE, Active Directory, EDR evasion, exploit development, wireless, cloud, mobile, IoT, supply chain. **11.5k stars**. For authorized security testing of medical devices/IoT. MIT.
- [trailofbits/skills](https://github.com/trailofbits/skills) — application security and secure development; check per-skill license.

## Reference and discovery
- [ComposioHQ/awesome-claude-skills](https://github.com/ComposioHQ/awesome-claude-skills) — curated list of 1000+ production-ready Claude skills across all domains. **80.3k stars**. Includes document processing, development tools, data analysis, business, creative, productivity, security, and 78 SaaS app automations via Composio MCP. Apache-2.0.
- [alirezarezvani/claude-skills](https://github.com/alirezarezvani/claude-skills) — 410+ skills for Claude Code. **30.5k stars**.
- [Jeffallan/claude-skills](https://github.com/Jeffallan/claude-skills) — 71 specialized skills for full-stack developers. **12.5k stars**.

## Embedded systems and microcontrollers
- Local [esp32-arduino-dev](https://github.com/mascatunike/nicu-ai-tools/tree/main/plugins/esp32-arduino-dev) — project-specific workflow for ESP32 DevKit V1 + Arduino IDE/CLI, with hardware safety, version-aware APIs, reproducible builds and explicit approval before flashing.
- Local [esp32-arduino-cli](https://github.com/mascatunike/nicu-ai-tools/tree/main/plugins/esp32-arduino-cli) — adapted from [doeslater/esp32-arduino](https://github.com/doeslater/esp32-arduino); MIT-licensed skill for transparent compile/upload/monitor using Arduino CLI. Tested upstream on classic ESP32 DevKitC/WROOM-32; this is not evidence that every DevKit V1 clone was tested.
- [f2daz/esp-expert-mcp](https://github.com/f2daz/esp-expert-mcp) — upstream plugin and MCP server for ESP32/ESP8266 pin checks, partitions, panic logs and chip information. MIT; optional server requires Python 3.11+ and uv.
- [lookfwd/arduino-cli-claude-plugin](https://github.com/lookfwd/arduino-cli-claude-plugin) — upstream Arduino CLI commands for board detection, sketch creation, libraries, compile and upload. Registered as an upstream plugin; inspect its permissions and license before enabling.
- [wokwi/skills](https://github.com/wokwi/skills) — upstream MIT-licensed simulation skills for firmware testing, scripted peripherals, debugging and CI. Several workflows are ESP-IDF-oriented; Wokwi tooling may be required.
- Existing [esp32-arduino-dev](https://github.com/mascatunike/nicu-ai-tools/tree/main/plugins/esp32-arduino-dev) remains the main project-specific guidance for this user's classic ESP32 DevKit V1 + Arduino IDE workflow.

## Automotive and electronics
There is no single widely established Claude skill pack that can replace OEM service information or component datasheets. Original local skills are included for automotive diagnostics and electronics engineering. Pair them with authoritative service manuals, wiring diagrams, datasheets and applicable standards.

## Quality control
Stars indicate popularity, not quality or safety. Before installing an upstream project, check current stars, recent commits, issues, license, dependencies and permissions. Do not redistribute upstream files unless the license permits it and attribution requirements are met.