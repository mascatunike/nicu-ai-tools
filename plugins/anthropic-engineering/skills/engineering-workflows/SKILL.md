---
name: engineering-workflows
description: Structure engineering collaboration, technical decisions, code reviews, incident response, and documentation.
---

# Engineering Workflows

Use this skill to make engineering work explicit, reviewable, and repeatable.

## Standups and status
- Summarize completed work, current work, blockers, and next actions.
- Link status claims to tickets, pull requests, commits, or operational evidence.
- Surface dependencies and decisions needed from others.

## Code review
- Prioritize correctness, security, maintainability, and regression risk.
- Explain each finding with location, impact, and a concrete remediation.
- Distinguish blocking defects from optional improvements.
- Do not approve changes that have not been inspected or tested.

## Architecture decisions
- State the problem, constraints, options, trade-offs, and decision.
- Record consequences and revisit conditions.
- Prefer the simplest design that meets current requirements.

## Incident response
- Establish impact, scope, timeline, and an incident lead.
- Prioritize mitigation and service restoration before root-cause analysis.
- Preserve evidence and communicate verified facts.
- Finish with corrective actions, owners, and due dates.

## Technical documentation
- Keep instructions executable and version-aware.
- Document prerequisites, configuration, failure modes, and rollback.
- Update documentation alongside the implementation.

This is a locally curated workflow skill based on the public engineering plugin description. It is not a copy of Anthropic's complete upstream plugin: https://github.com/anthropics/knowledge-work-plugins/tree/main/engineering