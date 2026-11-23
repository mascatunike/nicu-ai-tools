---
name: security-scanning
description: Review application code, dependencies, infrastructure, and containers for security weaknesses.
---

# Security Scanning

Use this skill for defensive security reviews of systems the user owns or is authorized to assess.

## Workflow
1. Identify the application, deployment model, trust boundaries, sensitive data, and threat model.
2. Run available static analysis and dependency scanners using the repository's existing tooling.
3. Review authentication, authorization, input validation, output encoding, session handling, and secret storage.
4. Check common web risks including injection, broken access control, insecure deserialization, SSRF, path traversal, and unsafe file uploads.
5. Inspect container images and infrastructure configuration for excessive privileges, exposed services, weak defaults, and unpinned dependencies.
6. Triage findings by exploitability, impact, exposure, and confidence. Separate confirmed issues from scanner noise.
7. Recommend minimal fixes and add regression tests. Re-run scans after changes.
8. Report affected files, evidence, severity, remediation, and residual risk.

## Safety rules
- Limit testing to authorized assets and environments.
- Do not exploit vulnerabilities to access data, persist, disrupt service, or move laterally.
- Never print, copy, or commit credentials, tokens, private keys, or personal data.
- Do not claim a clean bill of health based only on automated scans.

Curated local skill inspired by the security-scanning plugin from https://github.com/wshobson/agents. This is not a verbatim mirror of the upstream plugin.