# AI Elements – Agent Rules

**Comprehensive rules for building accessible, fast, and delightful AI-native applications using ▲ AI Elements, AI SDK, and Workflow DevKit. This file covers both technical requirements and interface guidelines using MUST/SHOULD/NEVER language.**

---

## Core Requirements

### MUST - Foundation
- **MUST**: Use only AI Elements components for all AI interfaces
- **MUST**: Install all required packages from the complete ecosystem
- **MUST**: Follow component registry: `https://registry.ai-sdk.dev/registry.json`
- **MUST**: Implement 31 AI Elements components exactly as specified
- **MUST**: Use AI SDK Core (`ai`) for unified LLM interactions
- **MUST**: Use Workflow DevKit primitives for orchestration

---

## Mandatory Package Installation

### MUST - Complete Package Setup

Install the following core packages:

```bash
# Core AI Elements
npm i ai-elements

# AI SDK Core
npm i ai

# AI SDK Framework Integration
npm install @ai-sdk/react
npm install @ai-sdk/svelte

# Workflow DevKit
npm i workflow

# Vercel Storage Suite
npm i @vercel/kv
npm i @vercel/postgres
npm i @vercel/blob
npm i @vercel/edge-config
npm i @vercel/postgres-kysely

# Additional UI and Tools
npm i @vercel/ai-tsconfig
npm i zod
```

### Required Runtime Dependencies

**AI SDK Core Dependencies**
- `@ai-sdk/gateway`
- `@ai-sdk/provider`
- `@ai-sdk/provider-utils`
- `@opentelemetry/api`

**AI SDK Provider Packages (Choose based on needs)**
- `@ai-sdk/openai` (OpenAI models)
- `@ai-sdk/anthropic` (Anthropic models)
- `@ai-sdk/google` (Google Generative AI)
- `@ai-sdk/vercel` (Vercel v0 API)
- `@ai-sdk/azure` (Azure OpenAI)
- `@ai-sdk/grok` (xAI Grok models)
- `@ai-sdk/mistral` (Mistral models)
- `@ai-sdk/cohere` (Cohere models)
- `@ai-sdk/fireworks` (Fireworks models)
- `@ai-sdk/deepseek` (DeepSeek models)
- `@ai-sdk/cerebras` (Cerebras models)
- `@ai-sdk/bedrock` (Amazon Bedrock)
- `@ai-sdk/groq` (Groq models)
- `@ai-sdk/fal` (Fal AI models)
- `@ai-sdk/deepinfra` (DeepInfra models)
- `@ai-sdk/together` (Together.ai models)
- `@ai-sdk/perplexity` (Perplexity models)
- `@ai-sdk/baseten` (Baseten models)
- `@ai-sdk/luma` (Luma AI models)
- `@ai-sdk/huggingface` (Hugging Face models)

**Additional Runtime Dependencies**
- `zod` (Schema validation)
- `undici` (HTTP client for Vercel storage)

### Required Dev Dependencies

**Core Development Tools**
- `typescript`
- `@types/node`
- `@types/json-schema`
- `esbuild`
- `tsup`
- `tsx`

**AI SDK Development**
- `@ai-sdk/test-server`
- `@edge-runtime/vm`

**Code Quality & Formatting**
- `eslint`
- `eslint-config-vercel-ai`
- `prettier`
- `@typescript-eslint/eslint-plugin`
- `@typescript-eslint/parser`

**Testing**
- `vitest`
- `@vitest/ui`
- `@testing-library/react`
- `@testing-library/jest-dom`
- `@testing-library/svelte`
- `happy-dom`

**Build & Bundle Tools**
- `rollup`
- `vite`

**Additional Development Dependencies**
- `pnpm` (recommended package manager)
- `npm-check-updates`
- `cross-env`

---

## Explicit Component Usage Requirements

### MUST USE ONLY AVAILABLE AI ELEMENTS COMPONENTS

**THERE ARE NO EXCEPTIONS** to using AI Elements components. Custom implementations, non-AI Elements components, or component substitutes are **STRICTLY PROHIBITED**.

The following **31 AI Elements components** MUST be used for their designated purposes:

### Chatbot Components (22 components)

**MUST use these exact components:**

- **`actions`** — MUST be used for interactive action buttons for AI responses
- **`branch`** — MUST be used for branch visualization for conversation flows
- **`chain-of-thought`** — MUST be used to display AI reasoning and thought processes
- **`code-block`** — MUST be used for syntax-highlighted code display with copy functionality
- **`context`** — MUST be used to display Context consumption
- **`conversation`** — MUST be used as the container for chat conversations
- **`image`** — MUST be used for AI-generated image display
- **`inline-citation`** — MUST be used for inline source citations
- **`loader`** — MUST be used for loading states for AI operations
- **`message`** — MUST be used for individual chat messages with avatars
- **`open-in-chat`** — MUST be used for "open in chat" button for messages
- **`plan`** — MUST be used for plan and task planning display
- **`prompt-input`** — MUST be used for advanced input with model selection
- **`queue`** — MUST be used for with attachments
- message and todo queue **`reasoning`** — MUST be used to display AI reasoning and thought processes
- **`response`** — MUST be used for formatted AI response display
- **`shimmer`** — MUST be used for text shimmer animation effect
- **`sources`** — MUST be used for source attribution
- **`suggestion`** — MUST be used for quick action suggestions
- **`task`** — MUST be used for task completion tracking
- **`tool`** — MUST be used for tool usage visualization
- **`confirmation`** — MUST be used for tool execution approval workflows

### Vibe-Coding Components (2 components)

**MUST use these exact components:**

- **`artifact`** — MUST be used to display code or document
- **`web-preview`** — MUST be used for embedded web page previews

### Workflow Components (7 components)

**MUST use these exact components:**

- **`canvas`** — MUST be used for ReactFlow canvas for workflow visualizations
- **`connection`** — MUST be used for connection line component for workflow edges
- **`controls`** — MUST be used for flow controls for canvas (zoom, fit view, etc.)
- **`edge`** — MUST be used for edge component for connections between workflow nodes
- **`node`** — MUST be used for node component for workflow graphs
- **`panel`** — MUST be used for panel component for canvas overlays
- **`toolbar`** — MUST be used for node toolbar for workflow elements

---

## Workflow DevKit Usage Rules

### MUST

Use Workflow DevKit primitives for orchestration, not custom glue code. Workflow DevKit makes async workflows reliable, durable, fault-tolerant, and portable across any cloud.

### Workflow Package Architecture

- **`workflow`** (Core Framework)
  MUST be used for core workflow primitives:
  - `"use workflow"` directive for durable functions
  - `"use step"` directive for isolated work units
  - `sleep(duration)` for pausing workflows without resource consumption
  - `createWebhook()` for handling external events
  - Context management and state persistence
  - Automatic retry logic and error handling
  - Streaming support for real-time updates

- **`workflow/api`**
  MUST be used for runtime API functions:
  - Exposing workflow endpoints
  - Handling webhook responses
  - Managing workflow state APIs

- **`workflow/next`**
  MUST be used for Next.js projects:
  - Ensures correct bundling for serverless deployment
  - Optimizes for Edge Runtime compatibility
  - Handles Next.js-specific routing and SSR

- **`@workflow/ai`**
  MUST be used for AI SDK integration:
  - Bridges AI SDK functions with workflow durability
  - Handles AI agent state persistence
  - Manages long-running AI operations

### Workflow-Compatible Dependencies

**Vercel Storage Suite**
- **`@vercel/kv`** — Durable Redis-compatible Key-Value storage
- **`@vercel/postgres`** — Serverless Postgres database (Edge-compatible)
- **`@vercel/blob`** — Fast object storage for large files
- **`@vercel/edge-config`** — Ultra-low latency data at the edge
- **`@vercel/postgres-kysely`** — Kysely ORM wrapper for Postgres

**Additional Vercel Ecosystem**
- **`@vercel/ai-sdk-gateway`** — AI Gateway provider for AI SDK
- **`ai`** — AI SDK core for workflow AI integration
- **`@workflow/ai`** — Workflow-AI integration package

---

## Interface Guidelines

## Keyboard & Interaction

### MUST - Keyboard Navigation
- **MUST**: Full keyboard support per [WAI-ARIA APG](https://www.w3.org/WAI/ARIA/apg/patterns/)
- **MUST**: Visible focus rings (`:focus-visible`; group with `:focus-within`)
- **MUST**: Manage focus (trap, move, and return) per APG patterns
- **MUST**: Hit target ≥24px (mobile ≥44px). If visual <24px, expand hit area
- **MUST**: Enter submits focused text input. In `<textarea>`, ⌘/Ctrl+Enter submits; Enter adds newline
- **MUST**: Keep submit enabled until request starts; then disable, show spinner, use idempotency key
- **MUST**: Don't block typing; accept free text and validate after
- **MUST**: Errors inline next to fields; on submit, focus first error
- **MUST**: Warn on unsaved changes before navigation
- **MUST**: Links are links—use `<a>/<Link>` for navigation (support Cmd/Ctrl/middle-click)

### SHOULD - Interaction Patterns
- **SHOULD**: Autofocus on desktop when there's a single primary input; rarely on mobile
- **SHOULD**: Disable spellcheck for emails/codes/usernames
- **SHOULD**: Placeholders end with ellipsis and show example pattern

### NEVER - Interaction Violations
- **NEVER**: Disable browser zoom
- **NEVER**: Block paste in `<input>/<textarea>`
- **NEVER**: Create "dead-looking" interactive zones—if it looks clickable, it is

---

## Mobile & Touch

### MUST - Mobile Requirements
- **MUST**: Mobile `<input>` font-size ≥16px or set:
  ```html
  <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, viewport-fit=cover">
  ```
- **MUST**: `touch-action: manipulation` to prevent double-tap zoom; set `-webkit-tap-highlight-color`
- **MUST**: Design forgiving interactions (generous targets, clear affordances)
- **MUST**: Respect safe areas (use env(safe-area-inset-*))

### SHOULD - Touch Best Practices
- **SHOULD**: Delay first tooltip in a group; subsequent peers no delay
- **SHOULD**: During drag, disable text selection and set `inert` on dragged element

---

## Animation

### MUST - Animation Standards
- **MUST**: Honor `prefers-reduced-motion` (provide reduced variant)
- **MUST**: Animate compositor-friendly props (`transform`, `opacity`); avoid layout/repaint props
- **MUST**: Animations are interruptible and input-driven (avoid autoplay)
- **MUST**: Correct `transform-origin` (motion starts where it "physically" should)

### SHOULD - Animation Patterns
- **SHOULD**: Prefer CSS > Web Animations API > JS libraries
- **SHOULD**: Animate only to clarify cause/effect or add deliberate delight
- **SHOULD**: Choose easing to match the change (size/distance/trigger)

### NEVER - Animation Violations
- **NEVER**: Use `left`, `top`, `width`, `height` for animations
- **NEVER**: Implement animations longer than 1 second
- **NEVER**: Block user interactions during animations

---

## Layout & Design

### MUST - Layout Requirements
- **MUST**: Deliberate alignment to grid/baseline/edges/optical centers—no accidental placement
- **MUST**: Verify mobile, laptop, ultra-wide (simulate ultra-wide at 50% zoom)
- **MUST**: Avoid unwanted scrollbars; fix overflows
- **MUST**: URL reflects state (deep-link filters/tabs/pagination/expanded panels)

### SHOULD - Visual Design
- **SHOULD**: Layered shadows (ambient + direct)
- **SHOULD**: Crisp edges via semi-transparent borders + shadows
- **SHOULD**: Nested radii: child ≤ parent; concentric
- **SHOULD**: Hue consistency: tint borders/shadows/text toward bg hue
- **SHOULD**: Match browser UI to background
- **SHOULD**: Avoid gradient banding (use masks when needed)
- **SHOULD**: Optical alignment; adjust by ±1px when perception beats geometry
- **SHOULD**: Balance icon/text lockups (stroke/weight/size/spacing/color)

### MUST - Color & Contrast
- **MUST**: Accessible charts (color-blind-friendly palettes)
- **MUST**: Meet contrast—prefer [APCA](https://apcacontrast.com/) over WCAG 2
- **MUST**: Increase contrast on `:hover/:active/:focus`

---

## Content & Accessibility

### MUST - Content Standards
- **MUST**: Skeletons mirror final content to avoid layout shift
- **MUST**: `<title>` matches current context
- **MUST**: No dead ends; always offer next step/recovery
- **MUST**: Design empty/sparse/dense/error states
- **MUST**: Use the ellipsis character `…` (not three dots)
- **MUST**: `scroll-margin-top` on headings for anchored links; include "Skip to content" link
- **MUST**: Hierarchical `<h1–h6>` structure
- **MUST**: Resilient to user-generated content (short/avg/very long)
- **MUST**: Locale-aware dates/times/numbers/currency
- **MUST**: Accurate names (`aria-label`), decorative elements `aria-hidden`
- **MUST**: Icon-only buttons have descriptive `aria-label`
- **MUST**: Use non-breaking spaces: `10&nbsp;MB`, `⌘&nbsp;+&nbsp;K`, `Vercel&nbsp;SDK`

### SHOULD - Content Best Practices
- **SHOULD**: Inline help first; tooltips last resort
- **SHOULD**: Curly quotes (" "); avoid widows/orphans
- **SHOULD**: Tabular numbers for comparisons (`font-variant-numeric: tabular-nums`)
- **SHOULD**: Redundant status cues (not color-only); icons have text labels

### MUST - Accessibility Requirements
- **MUST**: Use semantic structure provided by AI Elements components
- **MUST**: Support keyboard navigation for all interactions
- **MUST**: Provide visible focus states
- **MUST**: Meet WCAG AA contrast requirements
- **MUST**: Redundant status cues (not color-only)
- **MUST**: Don't ship the schema—visuals may omit labels but accessible names exist

### NEVER - Accessibility Violations
- **NEVER**: Replace accessible components with custom implementations
- **NEVER**: Hide essential functionality behind hover-only interactions
- **NEVER**: Rely solely on color to convey meaning
- **NEVER**: Remove focus indicators without replacement

---

## Performance

### MUST - Performance Standards
- **MUST**: Test iOS Low Power Mode and macOS Safari
- **MUST**: Measure reliably (disable extensions that skew runtime)
- **MUST**: Track and minimize re-renders (React DevTools/React Scan)
- **MUST**: Profile with CPU/network throttling
- **MUST**: Batch layout reads/writes; avoid unnecessary reflows/repaints
- **MUST**: Mutations (`POST/PATCH/DELETE`) target <500 ms
- **MUST**: Virtualize large lists (eg, `virtua`)
- **MUST**: Preload only above-the-fold images; lazy-load the rest
- **MUST**: Prevent CLS from images (explicit dimensions or reserved space)

### SHOULD - Performance Patterns
- **SHOULD**: Prefer uncontrolled inputs; make controlled loops cheap

### NEVER - Performance Violations
- **NEVER**: Block the UI during AI generation
- **NEVER**: Re-render entire conversations for incremental updates
- **NEVER**: Ship unused AI Elements components

---

## AI SDK Integration

### MUST - AI Interface Standards
- **MUST**: Stream AI responses whenever possible
- **MUST**: Lazy-load AI components when not immediately needed
- **MUST**: Minimize client-side computation
- **MUST**: Clearly label AI-generated content
- **MUST**: Sanitize AI output before rendering
- **MUST**: Provide retry and correction paths

### SHOULD - AI Patterns
- **SHOULD**: Use AI Elements `loader` components for loading states
- **SHOULD**: Implement progressive disclosure for complex AI responses
- **SHOULD**: Use `conversation` component as the main container
- **SHOULD**: Implement message threading with proper indentation
- **SHOULD**: Use `suggestion` components for quick follow-up actions

### NEVER - AI Violations
- **NEVER**: Assume AI output is correct by default
- **NEVER**: Expose system prompts or internal logic
- **NEVER**: Trigger AI actions without explicit user intent
- **NEVER**: Implement custom chat interfaces without AI Elements

---

## Feedback & State

### MUST - Feedback Requirements
- **MUST**: Loading buttons show spinner and keep original label
- **MUST**: Confirm destructive actions or provide Undo window
- **MUST**: Use polite `aria-live` for toasts/inline validation
- **MUST**: Optimistic UI; reconcile on response; on failure show error and rollback or offer Undo
- **MUST**: During drag, disable text selection and set `inert` on dragged element/containers
- **MUST**: Intentional `overscroll-behavior: contain` in modals/drawers

### SHOULD - Feedback Patterns
- **SHOULD**: Ellipsis (`…`) for options that open follow-ups and loading states
- **SHOULD**: Allow submitting incomplete forms to surface validation
- **SHOULD**: Disable spellcheck for appropriate input types

---

## Forms & Inputs

### MUST - Form Standards
- **MUST**: Hydration-safe inputs (no lost focus/value)
- **MUST**: `autocomplete` + meaningful `name`; correct `type` and `inputmode`
- **MUST**: Compatible with password managers & 2FA; allow pasting one-time codes
- **MUST**: Trim values to handle text expansion trailing spaces
- **MUST**: No dead zones on checkboxes/radios; label+control share one generous hit target

### SHOULD - Form Patterns
- **SHOULD**: Placeholders end with ellipsis and show example pattern
- **SHOULD**: Disable spellcheck for emails/codes/usernames

---

## Environment Requirements

### MUST
- **Node.js**: Version 18 or later (LTS recommended)
- **Package Manager**: pnpm (recommended) or npm/yarn
- **React**: React 19 (no `forwardRef` usage)
- **Tailwind CSS**: Tailwind CSS 4
- **TypeScript**: Latest stable version
- **Next.js**: For Next.js projects with AI SDK installed
- **AI Gateway**: Set `AI_GATEWAY_API_KEY` environment variable

### Framework Compatibility
- **React**: 19+ (with Next.js App Router or Pages Router)
- **Svelte**: Latest version with `@ai-sdk/svelte`
- **Vue.js**: Latest version with AI SDK framework integration
- **Node.js**: 18+ for server-side operations
- **Edge Runtime**: Compatible with Vercel Edge Functions

---

## Complete Installation Script

### One-Command Setup

Run this script to install all required packages:

```bash
#!/bin/bash
# AI Elements Complete Setup Script

echo "🚀 Installing AI Elements and Vercel AI Ecosystem..."

# Core packages
npm install ai-elements ai @ai-sdk/react @ai-sdk/svelte

# Workflow DevKit
npm install workflow

# Vercel Storage Suite
npm install @vercel/kv @vercel/postgres @vercel/blob @vercel/edge-config @vercel/postgres-kysely

# Development dependencies
npm install -D typescript @types/node @vercel/ai-tsconfig zod @ai-sdk/test-server @edge-runtime/vm

# Quality tools
npm install -D eslint eslint-config-vercel-ai prettier @typescript-eslint/eslint-plugin @typescript-eslint/parser

# Testing framework
npm install -D vitest @vitest/ui @testing-library/react @testing-library/jest-dom happy-dom

# Build tools
npm install -D tsup esbuild rollup vite

# Additional tools
npm install -D cross-env npm-check-updates

echo "✅ All packages installed successfully!"
echo "📝 Don't forget to set AI_GATEWAY_API_KEY in your environment"
```

### Environment Variables Setup

Create `.env.local` file with:

```bash
# AI Gateway (Required - $5/month credit included)
AI_GATEWAY_API_KEY=your_ai_gateway_key_here

# Optional: Direct provider keys (if not using AI Gateway)
OPENAI_API_KEY=your_openai_key
ANTHROPIC_API_KEY=your_anthropic_key
GOOGLE_API_KEY=your_google_key

# Vercel Storage (Required for database/storage features)
POSTGRES_URL=your_postgres_url
KV_URL=your_kv_url
BLOB_READ_WRITE_TOKEN=your_blob_token
EDGE_CONFIG=your_edge_config_url
```

---

## Decision Priority

**Accessibility > Performance > Visual polish**  
**Clarity > Cleverness**  
**User control > AI autonomy**  
**Consistency > Customization**

---

## Zero Tolerance Policy

**ANY DEVIATION** from these component requirements **CONSTITUTES A RULE VIOLATION**. There are no exceptions, no "temporary" workarounds, and no "just this once" scenarios.

**The 31 AI Elements components listed above are the ONLY permitted components for AI-native application interfaces.**

---

**This comprehensive AGENTS.md file ensures that all AI-generated interfaces maintain high standards for accessibility, performance, and user experience while leveraging the full power of the AI Elements component library and the complete Vercel AI ecosystem.**
