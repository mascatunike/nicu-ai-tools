---
name: frontend-mobile-development
description: Build accessible, responsive web and mobile interfaces with maintainable component architecture.
---

# Frontend & Mobile Development

Use this skill when building or reviewing frontend and mobile application interfaces.

## Workflow
1. Inspect the existing framework, routing, state management, design system, and build tooling before changing architecture.
2. Clarify user flows, loading states, empty states, errors, offline behavior, and permission requirements.
3. Build reusable components with clear boundaries; keep business logic out of presentation components.
4. Use semantic HTML and accessible native controls. Support keyboard navigation, screen readers, focus management, and sufficient contrast.
5. Design responsive layouts for real device sizes and input methods. Avoid assuming hover, large screens, or a permanent network connection.
6. Minimize unnecessary state and effects. Derive values when possible and clean up subscriptions and listeners.
7. Test behavior, accessibility, and visual regressions across representative viewports and devices.
8. Measure performance before optimizing; watch bundle size, rendering, image loading, and expensive list operations.

## Review checklist
- Does the UI work on narrow screens and with keyboard/screen readers?
- Are loading, empty, error, and offline states handled?
- Are forms validated accessibly and errors announced?
- Are secrets and authorization enforced by the backend, not only the client?
- Are navigation and state transitions predictable?

Follow the repository's conventions and existing design tokens. Do not add a new UI framework without a clear reason.

Curated local skill inspired by the frontend-mobile-development plugin from https://github.com/wshobson/agents. This is not a verbatim mirror of the upstream plugin.