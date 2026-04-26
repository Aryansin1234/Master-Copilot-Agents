# 📋 PROJECT CONTEXT
# ==========================================
# Every agent reads this file before doing anything.
# Fill in your choices by DELETING the options you don't want.
# Example:  UI_FRAMEWORK: react | vue | svelte
# Becomes:  UI_FRAMEWORK: react
# ==========================================

# ──────────────────────────────────────────
# 1. WHAT IS THIS APP?
# ──────────────────────────────────────────

APP_NAME: 
APP_PURPOSE:
# Write one sentence. Who uses it and what does it do?
# Example: "A dashboard that helps freelancers track invoices and client payments"

PHASE: greenfield | active-development | maintenance | refactor
# greenfield      = starting from scratch
# active-development = building new features on existing code
# maintenance     = fixing bugs, small improvements only
# refactor        = restructuring existing code

SCALE: prototype | startup | growth | enterprise
# prototype  = just testing the idea, < 1k users
# startup    = building for real, up to 10k users
# growth     = scaling up, 10k–1M users
# enterprise = large scale, 1M+ users


# ──────────────────────────────────────────
# 2. FRONTEND
# ──────────────────────────────────────────

UI_FRAMEWORK: react | vue | svelte | vanilla
# react   = React / Next.js
# vue     = Vue 3 / Nuxt
# svelte  = SvelteKit
# vanilla = plain HTML/CSS/JS

STYLING: tailwind | scss | css-modules | styled-components
# tailwind        = utility classes (most common with React)
# scss            = Sass with BEM naming (good for Vue/Svelte)
# css-modules     = scoped CSS files per component
# styled-components = CSS-in-JS

UI_STYLE: minimal-clean | brutalist | glassmorphism | material | corporate | playful
# minimal-clean  = lots of white space, simple, modern
# brutalist      = bold borders, stark, high contrast, no rounded corners
# glassmorphism  = frosted glass cards, dark backgrounds, blur effects
# material       = Google Material Design, elevation shadows
# corporate      = dense, professional, data-heavy layouts
# playful        = colorful, rounded, fun micro-animations

ANIMATION: framer-motion | gsap | css-only | none
# framer-motion = best for React component animations
# gsap          = best for complex timelines and scroll effects
# css-only      = simple transitions, no JS library needed
# none          = no animations

COMPONENT_LIB: shadcn | radix | headlessui | chakra | antd | none
# shadcn    = copy-paste components, fully customizable (works with Tailwind)
# radix     = unstyled accessible primitives (build your own look)
# headlessui = unstyled, made by Tailwind team
# chakra    = pre-styled, easy to use
# antd      = enterprise-grade, data-heavy UIs (Ant Design)
# none      = building everything from scratch


# ──────────────────────────────────────────
# 3. BACKEND
# ──────────────────────────────────────────

BACKEND_RUNTIME: nodejs | python | go
# nodejs  = JavaScript/TypeScript on the server
# python  = great if you need AI/ML features
# go      = high performance, compiled

BACKEND_FRAMEWORK: express | fastapi | nextjs-api | nestjs | hono | django
# express    = minimal, flexible (Node)
# fastapi    = modern, fast, auto-docs (Python)
# nextjs-api = API routes inside your Next.js app
# nestjs     = structured, enterprise-style (Node)
# hono       = ultra-fast, edge-ready (Node)
# django     = batteries-included (Python)

API_STYLE: rest | graphql | trpc | grpc
# rest     = standard HTTP endpoints (most common, easiest)
# graphql  = flexible queries, good for complex data relationships
# trpc     = end-to-end type safety, only works with TypeScript
# grpc     = high-performance binary protocol, good for microservices

BACKEND_LANG: typescript | javascript | python | go


# ──────────────────────────────────────────
# 4. DATABASE
# ──────────────────────────────────────────

PRIMARY_DB: postgresql | mysql | mongodb | sqlite | supabase
# postgresql = most powerful open-source relational DB (recommended)
# mysql      = widely used relational DB
# mongodb    = document-based, flexible schema (good for unstructured data)
# sqlite     = file-based, great for prototypes and small apps
# supabase   = hosted Postgres with built-in auth and storage

ORM: prisma | drizzle | mongoose | sqlalchemy | raw-sql
# prisma      = type-safe, great DX, works with Postgres/MySQL/SQLite
# drizzle     = lightweight, SQL-like syntax, TypeScript
# mongoose    = for MongoDB only
# sqlalchemy  = for Python projects
# raw-sql     = no ORM, writing queries manually

CACHE: redis | upstash | none
# redis   = self-hosted in-memory cache (sessions, rate limiting, queues)
# upstash = serverless Redis, no infra needed (good for Vercel/Railway)
# none    = no caching layer

FILE_STORAGE: s3 | cloudinary | supabase-storage | local | none
# s3               = AWS S3 or any S3-compatible storage
# cloudinary       = images and videos with automatic optimization
# supabase-storage = built-in storage if you're using Supabase
# local            = store files on the server disk (only for prototypes)
# none             = no file uploads


# ──────────────────────────────────────────
# 5. DEPLOYMENT
# ──────────────────────────────────────────

DEPLOY_TARGET: vercel | railway | fly-io | aws | gcp | azure | kubernetes | cloud-foundry | kyma | render | docker-only
# vercel        = best for Next.js, serverless, zero config
# railway       = simple container deploys, great DX
# fly-io        = containers close to users, global edge
# render        = Heroku alternative, easy deploys
# aws           = full control, most services, steeper learning curve
# gcp           = Google Cloud, good for AI/ML workloads
# azure         = Microsoft ecosystem, enterprise-friendly
# kubernetes    = container orchestration, large-scale production
# cloud-foundry = SAP / enterprise PaaS
# kyma          = SAP BTP Kubernetes runtime
# docker-only   = just Docker, you manage the server yourself

CONTAINERS: docker-compose | kubernetes | none
# docker-compose = local dev + simple single-server deploys
# kubernetes     = production-grade container orchestration
# none           = no containers (e.g. Vercel handles it for you)

CI_CD: github-actions | gitlab-ci | jenkins | none
# github-actions = built into GitHub, easiest to set up
# gitlab-ci      = built into GitLab
# jenkins        = self-hosted, highly customizable
# none           = deploying manually for now

ENVIRONMENTS: local, staging, production
# Add or remove environments that actually exist in your project


# ──────────────────────────────────────────
# 6. SECURITY & AUTH
# ──────────────────────────────────────────

AUTH: jwt | session-cookies | clerk | auth0 | nextauth | supabase-auth | none
# jwt             = JSON Web Tokens, you build and manage auth yourself
# session-cookies = traditional server-side sessions
# clerk           = fully managed auth service, drop-in UI components
# auth0           = managed auth, enterprise features
# nextauth        = auth library for Next.js (supports many providers)
# supabase-auth   = built-in auth if you're using Supabase
# none            = no auth yet

SENSITIVE_DATA: yes | no
# yes = app handles payments, health data, personal info, etc.
# no  = no sensitive user data

COMPLIANCE: none | gdpr | hipaa | pci-dss | soc2
# none    = no specific compliance requirements
# gdpr    = European data privacy law (affects most apps with EU users)
# hipaa   = US healthcare data regulations
# pci-dss = payment card industry standards
# soc2    = security/availability standards for SaaS


# ──────────────────────────────────────────
# 7. TESTING
# ──────────────────────────────────────────

TEST_RUNNER: vitest | jest | pytest | go-test
# vitest  = fast, modern, works great with Vite projects
# jest    = battle-tested, most popular for JavaScript/TypeScript
# pytest  = standard for Python
# go-test = built into Go

E2E: playwright | cypress | none
# playwright = cross-browser, fast, modern (recommended)
# cypress    = popular, great developer experience
# none       = no end-to-end tests yet

UNIT_COVERAGE: 80%
# Target percentage for unit test coverage. 80% is a good default.

E2E_COVERAGE: critical-paths-only
# critical-paths-only = test signup, login, and core user journeys
# full                = test every user-facing feature


# ──────────────────────────────────────────
# 8. CURRENT STATE
# ──────────────────────────────────────────
# Keep this updated as the project progresses.
# Agents use this to avoid rebuilding what's already done.

CURRENT_FOCUS:
# What is the team actively building RIGHT NOW?
# Example: "Building the user dashboard and email notification system"

ALREADY_BUILT:
# List what's done. Delete items that aren't built yet.
- [ ] Project scaffold / folder structure
- [ ] Database schema
- [ ] Authentication (login, signup, logout)
- [ ] Core API endpoints
- [ ] Frontend scaffold
- [ ] CI/CD pipeline
- [ ] Staging environment

CONSTRAINTS:
# Hard limits agents must respect. Examples:
# - "Must use Node 18 (company policy, cannot upgrade)"
# - "No paid third-party services"
# - "API must stay backwards compatible with v1"
# - "Team only knows TypeScript, no Python"
