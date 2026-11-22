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
| `document-skills`, `example-skills`, `claude-api`, `academy-guide`, `discernment-nudge` | Anthropic's official document, example and API skills (upstream source) |

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
/plugin install document-skills@nicu-ai-tools
/plugin install example-skills@nicu-ai-tools
/plugin install claude-api@nicu-ai-tools
/plugin install academy-guide@nicu-ai-tools
/plugin install discernment-nudge@nicu-ai-tools
```

## Install in Claude Desktop

Open **Customize → Plugins → Add marketplace** and enter:

```text
mascatunike/nicu-ai-tools
```

If your Desktop version does not offer GitHub marketplace installation, use the plugin installation options available in that version or install through Claude Code.

## External upstream plugins

The marketplace registers these five upstream repositories directly as GitHub sources; their code is not copied into this repository. Updates remain controlled by the original maintainers. Anthropic's skills repository contributes five separate entries. Each upstream project retains its own license and notices. ECC is linked directly to its official repository rather than re-uploaded; follow the upstream project's official-source warning and review its setup options before enabling hooks.

- [obra/superpowers](https://github.com/obra/superpowers)
- [mattpocock/skills](https://github.com/mattpocock/skills)
- [affaan-m/ECC](https://github.com/affaan-m/ECC)
- [anthropics/skills](https://github.com/anthropics/skills)
- [nextlevelbuilder/ui-ux-pro-max-skill](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill)

## Third-party attribution

The Android reverse-engineering plugin is based on [SimoneAvogadro/android-reverse-engineering-skill](https://github.com/SimoneAvogadro/android-reverse-engineering-skill), version 1.1.0. Original author and license notices are retained. See the plugin's `UPSTREAM.md` and repository `LICENSE`.

## Safety and scope

- These are community-maintained plugins, not official Anthropic products.
- Review plugin contents before installing.
- No API keys, access tokens, private learner records, or session logs belong in this repository.
- Android reverse-engineering is redistributed from Simone Avogadro's upstream project under Apache-2.0. See `plugins/android-reverse-engineering/UPSTREAM.md`.
- Its installer scripts can download software, alter PATH/profile settings, and replace installation directories. Review them and obtain user confirmation before execution.
- The upstream PowerShell scripts are documented as experimental.
