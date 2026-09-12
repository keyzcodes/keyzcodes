# Sunday Jime

### Full-Stack Software Engineer | EMEA Time Zone Contractor | Backend Architecture & Data Security

I design and build production-oriented web systems with a focus on **backend architecture, REST APIs, relational database security, access control, and scalable frontend applications**.

I work across the full development lifecycle — from requirements analysis and system design to implementation, automated testing, deployment, and operational hardening.

My core strength is **security-first backend engineering**: enforcing access control at the database layer (Row Level Security, PL/pgSQL triggers), then proving it holds under change with automated test suites (pgTAP, Jest, Supertest) wired directly into CI/CD.

---

## 🎯 Core Strengths

- **Database-layer security** — Row Level Security (RLS) policies, PL/pgSQL triggers, least-privilege grants
- **Automated security testing** — pgTAP assertions run in CI on every push, not just at write-time
- **REST API architecture** — versioned APIs, middleware design, authentication & authorization boundaries
- **Relational database design** — normalized schemas, foreign key integrity, CHECK constraints, complex multi-parameter queries
- **Full-stack delivery** — React/Vite frontends fully wired to tested, secured backends

---

## 🌍 Global Positioning

**Available for remote software engineering opportunities and international contract engagements across EMEA-friendly time zones.**

- Remote-first engineering
- EMEA-compatible working hours
- Async-friendly communication
- Git-based development workflows
- Comfortable working independently and collaborating across distributed teams
- Available for project-based, contract, internship, and early-career engineering opportunities

---

# ⚙️ Technical Ecosystem

## Frontend
HTML5 · CSS3 · JavaScript · React · Vite · Tailwind CSS · Bootstrap · Responsive UI Architecture · Component-Based Development · REST API Integration · Client-Side State Management

## Backend
Node.js · Express.js · REST API Architecture · API Versioning · Authentication & Authorization · Middleware Architecture · Request Validation · Rate Limiting · Security Middleware · CRUD & Resource-Oriented API Design

## Databases & Security
PostgreSQL · Supabase · SQL · PL/pgSQL · Row Level Security (RLS) · Database Triggers · Least-Privilege Grants · Relational Modelling · Foreign Keys & Constraints · Query Filtering & Pagination

## Testing & DevOps
Jest · Supertest · Vitest · pgTAP · GitHub Actions (CI/CD) · Docker · Git

## Tools
GitHub · VS Code · Postman · Figma · Vercel · Cloudflare · Railway · Netlify

---

# 🏗️ Production Infrastructure Projects

## 🏠 Real Estate Marketplace Platform
**[View Repository →](https://github.com/keyzcodes/real-estate-platform)**
**React 19 + Vite + Node.js + Express 5 + PostgreSQL + Supabase**

A property discovery and marketplace system built around zero-trust data access — no unauthenticated visitor can retrieve sensitive property data (exact coordinates, contact details) through any endpoint, enforced at the database layer, not just the application layer.

### Engineering Focus
- Enforced multi-tier API and database access using **Supabase Row Level Security (RLS)** on a normalized PostgreSQL schema, structurally preventing exposure of restricted fields regardless of application-layer bugs
- Authored custom **PL/pgSQL triggers** (BEFORE INSERT/UPDATE) enforcing domain-level data integrity: currency-consistency checks, tour panorama protection, publication-readiness validation
- Built a **GitHub Actions CI/CD pipeline** running **27 automated pgTAP assertions** against disposable Supabase containers on every push, continuously verifying RLS row visibility and column permissions
- Wrote recursive Jest/Supertest contract tests that scan entire nested API response trees, guaranteeing zero leakage of forbidden database attributes at any depth
- Delivered a fully tested React frontend (Vitest, React Testing Library) with URL-synchronized, shareable search/filter state and AbortController-based race-condition handling

### Architecture
```text
                    ┌──────────────────────┐
                    │   React + Vite UI    │
                    └──────────┬───────────┘
                               │ HTTPS
                               ▼
                    ┌──────────────────────┐
                    │    Express REST API  │
                    │       /api/v1        │
                    └──────────┬───────────┘
                               │
             ┌─────────────────┼─────────────────┐
             ▼                 ▼                 ▼
        Authentication     Controllers       Services
             │                 │                 │
             └─────────────────┴────────┬────────┘
                                         ▼
                              ┌──────────────────┐
                              │     Supabase     │
                              │  Auth + RLS +    │
                              │     Database     │
                              └────────┬─────────┘
                                       ▼
                             PostgreSQL (RLS-Enforced)
                                       │
                                       ▼
                        27 pgTAP Assertions (CI/CD Gate)
```

---

## 🏫 School Management Platform
**[View Repository →](https://github.com/keyzcodes/school-management-system)**
**React + Node.js + Express.js + PostgreSQL + Supabase**

A multi-role academic management system handling the full lifecycle of student records — enrollment, attendance, grading, and fees — with strict role-based access control between students, teachers, and administrators.

### Engineering Focus
- Architected a **10-table normalized PostgreSQL schema** with strict foreign keys and CHECK constraints spanning users, students, classes, enrollment, attendance, and fees
- Automated grade computation at the **database layer** using PL/pgSQL procedures and triggers, eliminating manual calculation errors and ensuring results can never be manually falsified through the application layer
- Designed an **8-endpoint academic workflow** governing teacher submission → administrative approval → publication → student access, including full state-reversal handling for corrections
- Enforced **resource-ownership security middleware**, returning 403 Forbidden on any attempt to access another student's records via manipulated route parameters, tested directly against adversarial request patterns
- Structured the API around clear separation of roles (student, teacher, admin), so authorization logic lives in one consistent, auditable layer rather than scattered across routes

### Architecture
```text
                    ┌──────────────────────┐
                    │      React UI        │
                    │  (Role-Based Views)   │
                    └──────────┬───────────┘
                               │ HTTPS
                               ▼
                    ┌──────────────────────┐
                    │   Express REST API   │
                    │  Ownership Middleware │
                    └──────────┬───────────┘
                               │
             ┌─────────────────┼─────────────────┐
             ▼                 ▼                 ▼
          Student           Teacher            Admin
          Routes            Routes             Routes
             │                 │                 │
             └─────────────────┴────────┬────────┘
                                         ▼
                              ┌──────────────────┐
                              │     Supabase     │
                              │     Database     │
                              └────────┬─────────┘
                                       ▼
                         PostgreSQL (10-Table Schema)
                          Grade Automation via Triggers
```

---

## 🧬 AI Clinical Decision Support Prototype
**[View Repository →](https://github.com/keyzcodes/breast-cancer-diagnostic-tool)**
**Python + Scikit-Learn + Docker**

A containerized breast cancer risk-assessment prototype, taken through the full Software Development Life Cycle from requirements gathering to validated, reproducible deployment.

### Engineering Focus
- Containerized the full ML prototype in **Docker**, eliminating environment drift and guaranteeing reproducible execution across any system
- Applied structured **SDLC discipline**: requirements gathering, model development, validation, and deployment, rather than an ad-hoc notebook experiment

---

## 🏛️ Mikkel College Website
**[View Repository →](https://github.com/keyzcodes/mikkel-college-website)**
**HTML5 + CSS3 + Vanilla JavaScript + Formspree**

A production website built and shipped for a real client — a Nigerian secondary school — giving them a professional online presence for the first time.

### Engineering Focus
- Delivered a fully responsive marketing site with **zero frameworks or build tools**, using custom Intersection Observer-based scroll animations instead of external animation libraries
- Connected the contact form directly to the school owner's inbox via automated email delivery (Formspree), with zero backend infrastructure required
- Per the client's own feedback, the site directly contributed to increased inquiries and new student enrollment

---

## 📫 Let's Connect

- **Email:** sundayjime1@gmail.com
- **LinkedIn:** [linkedin.com/in/sunday-jime-612a27420](https://linkedin.com/in/sunday-jime-612a27420)
