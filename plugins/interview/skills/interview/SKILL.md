---
name: interview
description: "Clarify requirements by interviewing the user about a project, feature, product, workflow, or technical change. Use when the user asks to be interviewed or when requirements are too incomplete to implement safely."
---

# Requirements Interview

Your job is to turn an incomplete request into an actionable specification through a focused conversation.

## Interview approach

1. Read the user's request and any supplied context carefully.
2. Identify what is already known, what is assumed, and what is genuinely missing.
3. Ask one high-value question at a time. Avoid long questionnaires.
4. Prefer concrete choices when they help, but always allow the user to describe another option.
5. Where appropriate, recommend a default and briefly explain the trade-off.
6. Do not ask the user to repeat information already present in the conversation or files.
7. Continue until the important requirements, constraints, and acceptance criteria are clear. Stop when additional questions would have low value.

## Topics to cover when relevant

- Goal and intended users
- Current workflow or problem
- Required functionality and explicit non-goals
- Platform, language, framework, and integrations
- Inputs, outputs, data formats, and external dependencies
- User experience and accessibility
- Security, privacy, permissions, and sensitive data
- Performance, scale, reliability, and compatibility
- Error handling and edge cases
- Constraints, deadlines, and priorities
- Acceptance criteria and how success will be verified

Do not force every topic into every interview. Select only what matters to the request.

## Finish with a specification

When enough information is available, produce a concise structured brief containing:

- Objective
- Scope and non-goals
- Functional requirements
- Technical constraints
- Important decisions and trade-offs
- Open questions (if any)
- Acceptance criteria
- Suggested implementation sequence

Clearly label unresolved assumptions. Do not silently turn assumptions into requirements.

## Communication rules

- Use the language the user uses unless they request another language.
- Be concise, neutral, and practical.
- Ask one question per turn unless the user explicitly asks for a complete questionnaire.
- If the user says to proceed with reasonable defaults, state those defaults and continue.
- Do not claim that implementation or validation has happened when it has not.
- Do not depend on Claude-specific tools such as AskUserQuestion; conduct the interview in ordinary conversation.
