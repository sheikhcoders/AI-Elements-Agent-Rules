# ⟁ AI Elements – Agent Rules

Authoritative ruleset for building **accessible**, **fast**, and **AI-native** applications using **AI Elements**, **AI SDK**, and **Workflow DevKit**.

This repository defines **non-negotiable architectural and UI rules** using **MUST / SHOULD / NEVER** language to ensure consistency, accessibility, performance, and long-term maintainability.

---

## Scope

This ruleset applies to projects that use:

- ▲ **AI Elements** (31 components across Chatbot, Vibe-Coding, and Workflow categories)
- **AI SDK v6 Beta** (@ai-sdk packages, ai core, providers)
- **Workflow DevKit (WDK)** (workflow, workflow/api, workflow/next, @workflow/ai)
- **Vercel Storage** (@vercel/kv, @vercel/postgres, @vercel/blob, @vercel/edge-config)
- **shadcn/ui** with Tailwind CSS 4
- **Next.js** (when applicable)
- **React 19** / **Svelte** / **Vue.js** (framework-agnostic)

---

## What This Repository Enforces

- Mandatory dependency installation
- Mandatory component usage
- Accessibility guarantees
- Performance constraints
- Workflow orchestration standards
- Explicit separation of responsibilities between UI, AI, and workflows

If a decision conflicts with this repository, **this repository wins**.

---

## Repository Structure

.
├── README.md      # Purpose, scope, and usage
└── agents.md      # Enforceable MUST / SHOULD / NEVER rules

---

## Who This Is For

- Teams building AI-native products
- Contributors who need clear constraints
- Reviewers enforcing architectural consistency
- Agents and tools that require deterministic rules

---

## License

MIT