# Adaptive Copilot Agent Team

> **One config file. Six specialized agents. Any stack.**  
> Change a single value and your entire AI team instantly rewires itself.

---

## The Idea

Most AI coding setups break when you switch frameworks, change your DB, or pivot the deploy target. You end up rewriting prompts, fixing outdated instructions, and playing telephone between tools that don't share context.

This repo solves that with a **3-layer architecture** — universal principles at the core, stack-aware patterns in the middle, and a single project config that all agents read before doing anything:

```
┌─────────────────────────────────────────────────┐
│  Layer 3 — PROJECT CONTEXT                      │
│  copilot-instructions.md  ← your one source of  │
│  "Next.js 14, MongoDB, deploys on Railway"         truth │
├─────────────────────────────────────────────────┤
│  Layer 2 — PATTERNS (conditional, stack-aware)  │
│  "If React → hooks. If Vue → Composition API."  │
│  "If Postgres → Prisma. If Mongo → Mongoose."   │
├─────────────────────────────────────────────────┤
│  Layer 1 — PRINCIPLES (universal, never change) │
│  Separation of concerns. Error handling.        │
│  Security fundamentals. Always applied.         │
└─────────────────────────────────────────────────┘
```

---

## The One File That Drives Everything

`copilot-instructions.md` is the **shared brain**. It lives at your repo root and every agent reads it before acting.

Switching stacks means editing **one file** — not rewriting six instruction files.

```yaml
# Before: Next.js on Vercel
UI_FRAMEWORK: react
STYLING: tailwind
DEPLOY_TARGET: vercel

# After: Vue on Railway
UI_FRAMEWORK: vue
STYLING: scss
DEPLOY_TARGET: railway
```

That's it. The UI Agent now generates Vue Composition API components with SCSS/BEM. The DevOps Agent now outputs Railway configs. Zero instruction files touched.

---

## The Team

| Agent | Instruction File | Auto-activates On |
|---|---|---|
| 🏛️ **Architect** | `architect.instructions.md` | `*.md`, architecture docs |
| 🎨 **UI/UX Designer** | `ui-ux-designer.instructions.md` | `*.tsx`, `*.jsx`, `*.vue`, `*.css`, `*.scss` |
| ⚙️ **Backend Engineer** | `backend-engineer.instructions.md` | `api/**`, `services/**`, `*.service.*` |
| 🔒 **Security Engineer** | `security-engineer.instructions.md` | `auth/**`, `middleware/**`, `.env*` |
| 🚀 **DevOps Engineer** | `devops-engineer.instructions.md` | `Dockerfile`, `*.yml`, `infra/**` |
| 🧪 **QA Engineer** | `qa-engineer.instructions.md` | `*.test.*`, `*.spec.*`, `e2e/**` |

Agents are context-aware and hand off to each other. The Architect orchestrates. The Security Engineer audits. The QA Engineer validates. They know when to escalate.

---

## What Each Agent Adapts To

<details>
<summary>🎨 UI Agent</summary>

| Dimension | Options |
|---|---|
| Framework | React, Vue, Svelte, Vanilla |
| Styling | Tailwind, SCSS/BEM, CSS Modules, Styled Components |
| UI Style | Minimal, Brutalist, Glassmorphism, Material, Corporate, Playful |
| Animation | Framer Motion, GSAP, CSS-only, None |
| Component Lib | shadcn, Radix, Headless UI, Chakra, Ant Design |
</details>

<details>
<summary>⚙️ Backend Agent</summary>

| Dimension | Options |
|---|---|
| Runtime | Node.js, Python, Go |
| Framework | Express, FastAPI, NestJS, Hono, Django, Next.js API |
| API Style | REST, GraphQL, tRPC, gRPC |
| Database | PostgreSQL (Prisma/Drizzle), MongoDB (Mongoose), Supabase, SQLite |
</details>

<details>
<summary>🔒 Security Agent</summary>

| Dimension | Options |
|---|---|
| Auth | JWT, Session Cookies, Clerk, NextAuth, Auth0, Supabase Auth |
| Compliance | GDPR, HIPAA, PCI-DSS, SOC2 |
</details>

<details>
<summary>🚀 DevOps Agent</summary>

| Dimension | Options |
|---|---|
| Platform | Vercel, Railway, Fly.io, Kubernetes, Cloud Foundry, Kyma/SAP BTP, AWS, GCP, Azure |
| CI/CD | GitHub Actions, GitLab CI |
</details>

<details>
<summary>🧪 QA Agent</summary>

| Dimension | Options |
|---|---|
| Test Runner | Vitest, Jest, Pytest |
| E2E | Playwright, Cypress, None |
| Component | React Testing Library, Vue Test Utils |
</details>

---

## Setup

### 1. Drop these files into your repo

```
your-project/
├── copilot-instructions.md              ← fill this in first
├── .github/
│   └── copilot-instructions/
│       ├── architect.instructions.md
│       ├── ui-ux-designer.instructions.md
│       ├── backend-engineer.instructions.md
│       ├── security-engineer.instructions.md
│       ├── devops-engineer.instructions.md
│       └── qa-engineer.instructions.md
└── .vscode/
    ├── settings.json
    └── extensions.json
```

### 2. Set your stack in `copilot-instructions.md`

```yaml
UI_FRAMEWORK: react        # react | vue | svelte | vanilla
STYLING: tailwind          # tailwind | scss | css-modules | styled-components
UI_STYLE: minimal-clean    # minimal-clean | brutalist | glassmorphism | material | corporate | playful
PRIMARY_DB: postgresql     # postgresql | mongodb | supabase | mysql
AUTH: jwt                  # jwt | clerk | nextauth | session-cookies
DEPLOY_TARGET: vercel      # vercel | railway | fly-io | kubernetes | cloud-foundry | kyma | aws
TEST_RUNNER: vitest        # vitest | jest | pytest
```

### 3. Switch VS Code Copilot to Agent mode

Open the Copilot chat panel → switch to **Agent** (not Ask or Edit).

Now open any file and ask away. The right agent activates automatically.

---

## Workflow Tips

**Start big features with the Architect.** Open any `*.md` file, describe the feature, and let it decompose the work and route it to the right agents with the right context.

**Keep `copilot-instructions.md` accurate.** Added Redis? Set `CACHE: redis`. Moved from Vercel to Fly? Update `DEPLOY_TARGET`. The agents are only as sharp as the context they're given.

**Trust the handoffs.** When the Backend Agent flags something for a security review, it's not being cautious for its own sake — follow the handoff. That's the system working as designed.

**Switching stacks mid-project is fine.** Update the config, open a file, ask for help. Agents adapt on the next request. No migration, no re-prompting, no broken context.
