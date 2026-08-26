# Sunday Jime

### Full-Stack Software Engineer | EMEA Time Zone Contractor | Web Systems & Backend Architecture

I design and build production-oriented web systems with a focus on **backend architecture, REST APIs, relational databases, authentication, access control, and scalable frontend applications**.

I work across the full development lifecycle — from requirements analysis and system design to implementation, testing, deployment, and operational considerations.

My current engineering work includes building a **real-estate marketplace platform** and a **multi-role school management system**, with particular attention to data integrity, API design, security boundaries, relational modelling, and maintainable architecture.

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

- HTML5
- CSS3
- JavaScript
- React
- Vite
- Tailwind CSS
- Bootstrap
- Responsive UI architecture
- Component-based development
- REST API integration
- Client-side state and data management

## Backend

- Node.js
- Express.js
- REST API architecture
- API versioning
- Authentication & authorization
- Middleware architecture
- Request validation
- Error handling
- Rate limiting
- Security middleware
- Backend service architecture
- CRUD and resource-oriented API design

## Databases

- PostgreSQL
- Supabase
- SQL
- PL/pgSQL
- Relational database modelling
- Foreign keys & relational integrity
- Constraints & validation
- Query filtering
- Pagination
- Multi-parameter queries
- Database access control
- Row Level Security (RLS)

## Engineering & Development Tools

- Git
- GitHub
- VS Code
- Postman
- Figma
- npm
- REST APIs
- Vercel
- Cloudflare
- Railway
- Supabase
- Netlify

---

# 🏗️ Production Infrastructure Projects

## 🏠 Real Estate Marketplace Platform

**Full-Stack Web Application | React + Vite + Node.js + Express + Supabase + PostgreSQL**

A property discovery and marketplace system designed to help users discover, evaluate, and interact with rental properties while providing structured data and controlled access for property managers.

### Engineering Focus

- Designed the system around a **React/Vite frontend and versioned Express REST API**
- Implemented a backend architecture separating routing, controllers, business logic, and data access
- Integrated **Supabase Authentication** for token-based user sessions
- Designed authenticated API flows around access tokens and authorization boundaries
- Built the data layer on **PostgreSQL**
- Designed relational structures for properties, units, amenities, users, locations, and related entities
- Used SQL/PLpgSQL-oriented database logic for complex filtering and multi-parameter property queries
- Designed query patterns around location, property type, unit type, price range, amenities, and other search parameters
- Considered pagination and response-size control for scalable catalogue queries
- Designed public/private data boundaries to avoid exposing unrestricted database records
- Implemented API security considerations including CORS, security headers, request validation, and rate limiting
- Evaluated deployment architecture based on database/API geographic proximity and latency
- Frontend deployment designed around **Cloudflare's global edge/CDN infrastructure**

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
                              │ Auth + Database  │
                              └────────┬─────────┘
                                       ▼
                                PostgreSQL
