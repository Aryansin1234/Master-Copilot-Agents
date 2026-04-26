# 🤖 Adaptive Copilot Agent Team

A team of 6 specialized GitHub Copilot agents that automatically adapt to any tech stack, UI style, and deployment target — without rewriting their instructions.

## How It Works

Every agent uses a **3-layer architecture**:

```
Layer 1 — PRINCIPLES (universal, never change)
  Separation of concerns, error handling, security fundamentals.
  Apply to every project, regardless of stack.

Layer 2 — PATTERNS (stack-aware, conditional)
  "If React → use these patterns. If Vue → use these."
  "If Postgres → Prisma. If Mongo → Mongoose."
  Agents contain multiple pattern sets and switch based on context.

Layer 3 — PROJECT CONTEXT (per-project, lives in copilot-instructions.md)
  "This app uses Next.js 14, MongoDB, deploys on Railway."
  One file. All agents read it. Everyone stays in sync.
```

## The Single File That Changes Everything

`copilot-instructions.md` at your repo root is the **shared brain**. It defines:

- What your app does
- Which UI framework and style
- Which backend runtime and database
- Where it deploys

All 6 agents read this file before acting. Switching stacks means **updating one file** — not rewriting six agent instruction files.

### Example: Switching from Next.js → Vue

```yaml
# Before:
UI_FRAMEWORK: react
STYLING: tailwind
DEPLOY_TARGET: vercel

# After:
UI_FRAMEWORK: vue
STYLING: scss
DEPLOY_TARGET: railway
```

The UI Agent now generates Vue Composition API components with SCSS/BEM.  
The DevOps Agent now generates Railway configs instead of vercel.json.  
No agent instruction files were touched.

---

## The Agents

| Agent | File | Activates On |
|-------|------|-------------|
| 🏛️ **Architect** | `architect.instructions.md` | `*.md`, architecture docs |
| 🎨 **UI/UX Designer** | `ui-ux-designer.instructions.md` | `*.tsx`, `*.jsx`, `*.vue`, `*.css`, `*.scss` |
| ⚙️ **Backend Engineer** | `backend-engineer.instructions.md` | `api/**`, `services/**`, `*.service.*` |
| 🔒 **Security Engineer** | `security-engineer.instructions.md` | `auth/**`, `middleware/**`, `.env*` |
| 🚀 **DevOps Engineer** | `devops-engineer.instructions.md` | `Dockerfile`, `*.yml`, `infra/**` |
| 🧪 **QA Engineer** | `qa-engineer.instructions.md` | `*.test.*`, `*.spec.*`, `e2e/**` |

---

## Setup

### 1. Copy these files into your repo

```
your-project/
├── copilot-instructions.md          ← Fill this in first
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

### 2. Fill in copilot-instructions.md

Open `copilot-instructions.md` and set your stack. At minimum:

```yaml
UI_FRAMEWORK: react        # or vue, svelte, vanilla
STYLING: tailwind          # or scss, css-modules
UI_STYLE: minimal-clean    # or brutalist, glassmorphism, material, corporate, playful
PRIMARY_DB: postgresql     # or mongodb, supabase, mysql
AUTH: jwt                  # or clerk, nextauth, session-cookies
DEPLOY_TARGET: vercel      # or railway, fly-io, kubernetes, cloud-foundry, kyma, aws
TEST_RUNNER: vitest        # or jest, pytest
```

### 3. Enable GitHub Copilot agent mode

In VS Code: open the Copilot chat panel and switch to **Agent** mode (not Ask/Edit).

---

## What Each Agent Can Adapt To

### 🎨 UI Agent
- **Framework:** React, Vue, Svelte, Vanilla
- **Styling:** Tailwind, SCSS/BEM, CSS Modules, Styled Components
- **UI Style:** Minimal, Brutalist, Glassmorphism, Material, Corporate, Playful
- **Animation:** Framer Motion, GSAP, CSS-only, None
- **Component libs:** shadcn, Radix, Headless UI, Chakra, Ant Design

### ⚙️ Backend Agent
- **Runtime:** Node.js, Python, Go
- **Framework:** Express, FastAPI, NestJS, Hono, Django, Next.js API
- **API Style:** REST, GraphQL, tRPC, gRPC
- **Database:** PostgreSQL (Prisma/Drizzle), MongoDB (Mongoose), Supabase, SQLite

### 🔒 Security Agent
- **Auth:** JWT, Session Cookies, Clerk, NextAuth, Auth0, Supabase Auth
- **Compliance:** GDPR, HIPAA, PCI-DSS, SOC2

### 🚀 DevOps Agent
- **Platforms:** Vercel, Railway, Fly.io, Kubernetes, Cloud Foundry, Kyma/SAP BTP, AWS, GCP, Azure
- **CI/CD:** GitHub Actions, GitLab CI

### 🧪 QA Agent
- **Test runners:** Vitest, Jest, Pytest
- **E2E:** Playwright, Cypress, None
- **Component testing:** React Testing Library, Vue Test Utils

---

## Starting a New Project

1. Copy the files into your new repo
2. Update `copilot-instructions.md` with your choices
3. Open any file and ask an agent for help — it reads the context automatically

## Switching Stacks Mid-Project

1. Update `copilot-instructions.md` with the new choices
2. All agents adapt immediately on next request
3. No agent instruction files need to change

---

## Tips

**Be specific in project context.** The more accurately `copilot-instructions.md` reflects reality, the better the agents perform. If you added Redis, update `CACHE: redis`. If you switched from Vercel to Fly, update `DEPLOY_TARGET`.

**The Architect orchestrates.** When starting a large feature, open any `*.md` file and ask the Architect to break it down first. It routes work to the right agents with the right context.

**Agents hand off to each other.** When a backend agent recognizes the need for a security review, it says so explicitly. Follow the handoffs — they're intentional.
