# Sunday Jime

### Full-Stack Software Engineer | Backend Architecture, Data Security & Cloud Delivery

I build and deploy secure, database-backed web systems across property technology, financial simulation, education, and AI-assisted operations.

My work spans the full engineering lifecycle—from requirements analysis and system architecture to frontend and backend implementation, automated testing, cloud deployment, monitoring, and operational hardening.

My core strength is **security-first backend engineering**: designing versioned REST APIs, modelling relational and document databases, enforcing authorization close to the data through PostgreSQL Row Level Security and database functions, and verifying those controls with automated frontend, API, privacy-contract, and pgTAP tests integrated into CI/CD.

I work primarily with **React, TypeScript, Node.js, Express, PostgreSQL, Supabase, MongoDB Atlas, and GitHub Actions**, with deployment experience across **Cloudflare Workers, Render, Netlify, and Vercel**.

**Available for remote backend, full-stack, internship, contract, and collaborative engineering opportunities across EMEA-compatible time zones.**

---

## 🎯 Core Strengths

- **Backend and REST API architecture** — versioned endpoints, modular middleware, request validation, authentication, authorization, rate limiting, and controlled error responses
- **Database security and access control** — PostgreSQL Row Level Security, least-privilege column grants, database-authoritative roles, ownership policies, and protected RPC functions
- **Relational and document data modelling** — normalized PostgreSQL schemas, MongoDB/Mongoose models, foreign keys, CHECK constraints, indexes, triggers, and lifecycle state validation
- **Automated security and regression testing** — frontend, API, privacy-contract, middleware, PostgreSQL, RLS, and pgTAP assertions integrated into CI/CD
- **Authentication and privacy engineering** — Google OAuth, Supabase Auth, bearer-token validation, protected workspaces, session lifecycle handling, and explicit public-data projection
- **Transaction and concurrency controls** — database row locking, balance validation, integer-based financial calculations, replay handling, and race-condition-aware frontend requests
- **Full-stack product delivery** — responsive React, TypeScript, and Vite applications connected to secured Node.js, Express, PostgreSQL, Supabase, and MongoDB backends
- **Cloud operations and reliability** — automated deployments, production smoke checks, bounded network retries, health endpoints, continuity monitoring, and Telegram failure alerts

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

## Languages
JavaScript (ES6+, ESM & CommonJS) · TypeScript · SQL · PL/pgSQL · Python · HTML5 · CSS3

## Frontend Engineering
React · Vite · React Router · Tailwind CSS · Responsive Design · Accessible UI · Component-Based Architecture · Client-Side State Management · Fetch API · AbortController · REST API Integration

## Backend Engineering
Node.js · Express.js · Versioned REST APIs · Resource-Oriented API Design · Modular Middleware · Request Validation · Authentication & Authorization · Bearer-Token Validation · Rate Limiting · Security Headers · CORS · Controlled Error Handling

## Databases & Data Access
PostgreSQL · Supabase · MongoDB Atlas · Mongoose · PostgREST · Relational Modelling · Document Modelling · Foreign Keys · CHECK Constraints · Indexes · Query Filtering · Sorting · Pagination

## Data Security & Integrity
Row Level Security (RLS) · Least-Privilege Column Grants · Database-Authoritative Roles · Ownership Policies · PL/pgSQL Functions and Triggers · Protected RPCs · Row Locking · Schema Validation · Explicit Public-Data Projection

## Authentication & External Integrations
Supabase Auth · Google OAuth · Session Lifecycle Management · Telegram Bot API · grammY · Gemini API · Formspree

## Testing & Quality Engineering
Jest · Supertest · Vitest · React Testing Library · jsdom · pgTAP · API Contract Testing · Privacy-Contract Testing · Middleware Testing · PostgreSQL Security Testing · TypeScript Static Checking · ESLint

## DevOps, Deployment & Reliability
GitHub Actions · CI/CD · Docker · Supabase CLI · Cloudflare Workers · Render · Netlify · Vercel · Production Smoke Tests · Health Checks · Scheduled Monitoring · Bounded Retries · Telegram Failure Alerts

## Development & Design Tools
Git · GitHub · VS Code · Postman · PowerShell · Figma · Chrome DevTools · Lighthouse

---

# 🏗️ Production Infrastructure Projects

## 🏠 Real Estate Marketplace Platform
### Kudu — Real Estate Marketplace

**[View Repository →](https://github.com/keyzcodes/real-estate-platform)**  
**[View Live Application →](https://real-estate-platform.sundayjime1.workers.dev/)**
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
### School Management Platform

**[View Repository →](https://github.com/keyzcodes/school-management-system)**  
**[View Live Application →](https://school-management-system-amber-two.vercel.app/)**
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

## 🏨 Hotel Guest Operations & Task Automation System
Hotel repository: https://github.com/keyzcodes/hotel-guest-automation

**Node.js + Express.js + React + MongoDB Atlas + Mongoose + grammY + Gemini API**

An AI-assisted hotel operations system that converts natural-language Telegram guest requests into structured task tickets for hotel staff.

### Engineering Focus

- Architected a four-layer workflow connecting Telegram guest intake, AI intent classification, an Express REST API, and MongoDB Atlas persistence
- Integrated the Gemini API to classify unstructured guest messages into structured JSON tickets containing operational category, urgency, and request details
- Implemented exponential-backoff retries for transient AI failures and an environment-controlled mock layer for quota-safe development and integration testing
- Developed REST endpoints for retrieving and updating tickets across four human-controlled lifecycle states: Pending, In Progress, Resolved, and Escalated
- Built a responsive React staff dashboard using five-second HTTP polling to display and update active requests
- Diagnosed and resolved MongoDB Atlas SRV/DNS failures, Telegram long-polling conflicts, and Gemini rate-limit errors

> **Current status:** Functional local prototype connected to a live MongoDB Atlas database. Public frontend and backend deployment is not yet available.

---

## 💳 Reen Bank — Banking Simulation

**[View Repository →](https://github.com/keyzcodes/reen-bank-demo)**  
**[View Live Application →](https://reen-bank-demo.netlify.app/)**  
**React 19 + TypeScript + Vite + Tailwind CSS + Supabase Auth + PostgreSQL + Netlify**

A deployed educational banking simulation with authenticated, persistent user-specific demo accounts and transaction records. The application simulates banking workflows and does not process real money.

### Engineering Focus

- Built four coordinated, responsive dashboard views using reusable React components and typed account and transaction state
- Integrated Supabase email/password authentication with persistent user-specific records across three PostgreSQL application tables
- Implemented six ownership-based Row Level Security policies to prevent users from accessing another account holder’s records
- Restricted simulated deposit and withdrawal writes to an authenticated PostgreSQL RPC with ownership checks, per-account row locking, insufficient-balance validation, and same-ID replay handling
- Used integer-kobo calculations and transaction-history pagination to keep balances, history, and reporting statistics consistent
- Provisioned three zero-balance starter accounts for every authenticated user while supporting additional named accounts
- Deployed the Vite SPA through GitHub-connected Netlify builds and verified strict TypeScript compilation and production builds

## 🧬 AI Clinical Decision Support Prototype
### AI Clinical Decision Support Prototype

**[View Repository →](https://github.com/keyzcodes/breast-cancer-diagnostic-tool)**  
**[View Live Application →](https://implementation-breast-cancer-3.onrender.com/predict)**
**Python + Scikit-Learn + Docker**

A containerized breast cancer risk-assessment prototype, taken through the full Software Development Life Cycle from requirements gathering to validated, reproducible deployment.

### Engineering Focus
- Containerized the full ML prototype in **Docker**, eliminating environment drift and guaranteeing reproducible execution across any system
- Applied structured **SDLC discipline**: requirements gathering, model development, validation, and deployment, rather than an ad-hoc notebook experiment

---

## 🏛️ Mikkel College Website
### Mikkel College Website

**[View Repository →](https://github.com/keyzcodes/mikkel-college-website)**  
**[View Live Website →](https://delightful-platypus-fff026.netlify.app/)**
**HTML5 + CSS3 + Vanilla JavaScript + Formspree**

A production website built and shipped for a real client — a Nigerian secondary school — giving them a professional online presence for the first time.

### Engineering Focus
- Delivered a fully responsive marketing site with **zero frameworks or build tools**, using custom Intersection Observer-based scroll animations instead of external animation libraries
- Connected the contact form directly to the school owner's inbox via automated email delivery (Formspree), with zero backend infrastructure required
- Per the client's own feedback, the site directly contributed to increased inquiries and new student enrollment

---

## Contact
- Email: sundayjime1@gmail.com
- LinkedIn: linkedin.com/in/sundayjime
- GitHub: github.com/keyzcodes
