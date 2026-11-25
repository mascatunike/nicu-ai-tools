# nicu-ai-tools

Personal Claude plugins and skills maintained by **mascatunike**.

## Included plugins

| Plugin | Purpose |
|---|---|
| `teach-me` | Adaptive tutoring with diagnosis, guided practice, and mastery checks |
| `interview` | Requirements discovery and structured project specifications |
| `android-reverse-engineering` | Android APK/XAPK/JAR/AAR decompilation and API analysis (upstream Apache-2.0) |
| `superpowers` | Development methodology, TDD, debugging and subagents (upstream MIT) |
| `mattpocock-skills` | Engineering, requirements, TDD, code review and productivity (upstream MIT) |
| `ecc` | Everything Claude Code: agents, skills, hooks and workflows (official upstream source, MIT) |
| `ui-ux-pro-max` | UI/UX design intelligence and frontend guidance (upstream MIT) |
| `backend-development` | Backend API design, GraphQL, Temporal workflows, TDD backend (local curated) |
| `frontend-mobile-development` | Frontend UI and mobile app implementation across platforms (local curated) |
| `security-scanning` | SAST, dependency vulnerabilities, OWASP checks, defensive hardening (local curated) |
| `anthropic-engineering` | Engineering workflows: standups, code review, architecture, incidents, docs (local curated) |
| `esp32-arduino-dev` | ESP32 DevKit V1 firmware workflow: GPIO safety, reproducible builds, serial diagnostics (local) |
| `esp32-arduino-cli` | ESP32 Arduino CLI: compile, flash, debug, board detection, serial diagnostics (adapted) |
| `esp-expert` | ESP32/ESP8266 firmware engineering with MCP diagnostics (upstream MIT) |
| `arduino-cli` | Arduino CLI plugin: board detection, sketch creation, libraries, compile, upload (upstream) |
| `wokwi` | Wokwi embedded firmware simulation for ESP32 testing, debugging, CI (upstream MIT) |
| `academic-research-skills` | **Full academic research pipeline**: deep research, paper writing, peer review, systematic reviews, PRISMA screening, citation verification (58.5k ⭐, CC-BY-NC-4.0) |
| `claude-trading-skills` | **Structured trading workflows**: market regime, portfolio review, swing trading, risk management, journaling, backtesting (8.4k ⭐, MIT) |
| `claude-red` | **100+ offensive security skills**: SQLi, XSS, SSRF, RCE, AD, EDR evasion, exploit dev, wireless, cloud, IoT (11.5k ⭐, MIT) |
| `awesome-claude-skills` | **Curated 1000+ skills catalog** across all domains: docs, dev, data, business, creative, productivity, security, 78 SaaS automations (80.3k ⭐, Apache-2.0) |

## Install with Claude Code

In Claude Code, add this marketplace:

```text
/plugin marketplace add mascatunike/nicu-ai-tools
```

Then install any plugin from the catalog:

```text
/plugin install teach-me@nicu-ai-tools
/plugin install interview@nicu-ai-tools
/plugin install android-reverse-engineering@nicu-ai-tools
/plugin install superpowers@nicu-ai-tools
/plugin install mattpocock-skills@nicu-ai-tools
/plugin install ecc@nicu-ai-tools
/plugin install ui-ux-pro-max@nicu-ai-tools
/plugin install backend-development@nicu-ai-tools
/plugin install frontend-mobile-development@nicu-ai-tools
/plugin install security-scanning@nicu-ai-tools
/plugin install anthropic-engineering@nicu-ai-tools
/plugin install esp32-arduino-dev@nicu-ai-tools
/plugin install esp32-arduino-cli@nicu-ai-tools
/plugin install esp-expert@nicu-ai-tools
/plugin install arduino-cli@nicu-ai-tools
/plugin install wokwi@nicu-ai-tools
/plugin install academic-research-skills@nicu-ai-tools
/plugin install claude-trading-skills@nicu-ai-tools
/plugin install claude-red@nicu-ai-tools
/plugin install awesome-claude-skills@nicu-ai-tools
```

## Install in Claude Desktop

Open **Customize → Plugins → Add marketplace** and enter:

```text
mascatunike/nicu-ai-tools
```

If your Desktop version does not offer GitHub marketplace installation, use the plugin installation options available in that version or install through Claude Code.

## External upstream plugins and marketplaces

The repositories below are registered directly as GitHub plugin sources in this marketplace. Their code is not copied here; updates remain controlled by the original maintainers, and each project retains its own license and notices. ECC is linked to its official source; review its setup options and hook permissions before enabling automation.

Anthropic's `anthropics/skills` repository is itself a separate marketplace, not a single plugin repository. Add it separately to Claude Code to access its five official entries; they are intentionally not represented as five broken GitHub-root plugin entries in this catalog:

```text
/plugin marketplace add anthropics/skills
/plugin install document-skills@anthropic-agent-skills
/plugin install example-skills@anthropic-agent-skills
/plugin install claude-api@anthropic-agent-skills
/plugin install academy-guide@anthropic-agent-skills
/plugin install discernment-nudge@anthropic-agent-skills
```

**Registered upstream plugins in this marketplace:**

- [obra/superpowers](https://github.com/obra/superpowers) — development methodology
- [mattpocock/skills](https://github.com/mattpocock/skills) — engineering workflows
- [affaan-m/ECC](https://github.com/affaan-m/ECC) — agents, skills, hooks (curated subset)
- [nextlevelbuilder/ui-ux-pro-max-skill](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill) — UI/UX design
- [f2daz/esp-expert-mcp](https://github.com/f2daz/esp-expert-mcp) — ESP32/ESP8266 MCP diagnostics
- [lookfwd/arduino-cli-claude-plugin](https://github.com/lookfwd/arduino-cli-claude-plugin) — Arduino CLI commands
- [wokwi/skills](https://github.com/wokwi/skills) — embedded firmware simulation
- [Imbad0202/academic-research-skills](https://github.com/Imbad0202/academic-research-skills) — academic research pipeline
- [tradermonty/claude-trading-skills](https://github.com/tradermonty/claude-trading-skills) — trading workflows
- [SnailSploit/Claude-Red](https://github.com/SnailSploit/Claude-Red) — offensive security skills
- [ComposioHQ/awesome-claude-skills](https://github.com/ComposioHQ/awesome-claude-skills) — 1000+ skills catalog

## Third-party attribution

The Android reverse-engineering plugin is based on [SimoneAvogadro/android-reverse-engineering-skill](https://github.com/SimoneAvogadro/android-reverse-engineering-skill), version 1.1.0. Original author and license notices are retained. See the plugin's `UPSTREAM.md` and repository `LICENSE`.

The `esp32-arduino-cli` plugin is adapted from [doeslater/esp32-arduino](https://github.com/doeslater/esp32-arduino).

The `backend-development`, `frontend-mobile-development`, `security-scanning` plugins are curated adaptations from [wshobson/agents](https://github.com/wshobson/agents).

The `anthropic-engineering` plugin is a curated adaptation from [anthropics/knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins).

The `ecc` plugin is a curated subset of [affaan-m/ECC](https://github.com/affaan-m/ECC).

## Safety and scope

- These are community-maintained plugins, not official Anthropic products.
- Review plugin contents before installing.
- No API keys, access tokens, private learner records, or session logs belong in this repository.
- Android reverse-engineering is redistributed from Simone Avogadro's upstream project under Apache-2.0. See `plugins/android-reverse-engineering/UPSTREAM.md`.
- Its installer scripts can download software, alter PATH/profile settings, and replace installation directories. Review them and obtain user confirmation before execution.
- The upstream PowerShell scripts are documented as experimental.
- `claude-red` is for authorized security testing only. Ensure you have proper authorization before using offensive security skills.
- `academic-research-skills` is CC-BY-NC-4.0 (non-commercial use only).