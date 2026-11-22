# nicu-ai-tools

Personal Claude plugins and skills maintained by **mascatunike**.

## Included plugins

| Plugin | Purpose |
|---|---|
| `teach-me` | Adaptive tutoring with diagnosis, guided practice, and mastery checks |
| `interview` | Requirements discovery and structured project specifications |
| `android-reverse-engineering` | Android APK/XAPK/JAR/AAR decompilation and API analysis (upstream Apache-2.0) |

## Install with Claude Code

In Claude Code, add this marketplace:

```text
/plugin marketplace add mascatunike/nicu-ai-tools
```

Then install either plugin:

```text
/plugin install teach-me@nicu-ai-tools
/plugin install interview@nicu-ai-tools
/plugin install android-reverse-engineering@nicu-ai-tools
```

## Install in Claude Desktop

Open **Customize → Plugins → Add marketplace** and enter:

```text
mascatunike/nicu-ai-tools
```

If your Desktop version does not offer GitHub marketplace installation, use the plugin installation options available in that version or install through Claude Code.

## Third-party attribution

The Android reverse-engineering plugin is based on [SimoneAvogadro/android-reverse-engineering-skill](https://github.com/SimoneAvogadro/android-reverse-engineering-skill), version 1.1.0. Original author and license notices are retained. See the plugin's `UPSTREAM.md` and repository `LICENSE`.

## Safety and scope

- These are community-maintained plugins, not official Anthropic products.
- Review plugin contents before installing.
- No API keys, access tokens, private learner records, or session logs belong in this repository.
- Android reverse-engineering is redistributed from Simone Avogadro's upstream project under Apache-2.0. See `plugins/android-reverse-engineering/UPSTREAM.md`.
- Its installer scripts can download software, alter PATH/profile settings, and replace installation directories. Review them and obtain user confirmation before execution.
- The upstream PowerShell scripts are documented as experimental.
