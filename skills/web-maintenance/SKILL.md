---
name: web-maintenance
description: Audit, maintain, debug and improve existing websites, including accessibility, SEO, performance, security and deployment readiness.
---
# Web maintenance
1. Inspect the repository, framework, package manager, scripts, deployment target and conventions before changing code.
2. Reproduce the issue and identify its root cause. Establish a baseline with build, tests, lint and typecheck.
3. Make the smallest coherent change; preserve architecture and avoid unrelated rewrites.
4. Validate with targeted tests and relevant full checks. Report changed files, cause, validation, risks and rollback notes.
## Review checklist
- Functionality: routes, forms, links, API calls, loading/error/empty states and responsive behavior.
- Accessibility: semantic HTML, keyboard navigation, focus, labels, contrast, alt text and reduced motion.
- Performance: image sizing/formats, lazy loading, caching, bundle size and Core Web Vitals.
- SEO: titles, descriptions, canonical URLs, robots, sitemap, structured data, redirects and indexability.
- Security: dependency advisories, unsafe HTML, secrets, auth/authorization, CSRF/CORS, headers and input validation.
- Operations: environment variables, logs, health checks, backups, migrations, deployment and rollback.
## Constraints
Never expose secrets. Do not deploy, alter DNS, run destructive migrations or delete user data without approval. Do not claim rankings, compliance or security certification from superficial scans. Prefer official version-specific documentation.
