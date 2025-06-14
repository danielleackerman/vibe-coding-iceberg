---
title: API Patterns
nav_order: ""
description: Design patterns and best practices for building APIs, including REST, GraphQL, and other integration strategies.
tags:
  - patterns
  - api
  - vibe coding
layout: default
---
```markdown
# 🌐 API Patterns

This reference defines structural patterns for how applications expose and consume data. APIs (Application Programming Interfaces) are the layer where frontend systems communicate with backend logic, databases, or third-party services. API patterns describe how this interaction is **structured, versioned, and organized across environments and tools**.

These patterns are not code instructions. They are **system-level strategies** that appear consistently across frameworks, platforms, AI tooling, and low-code systems. They affect **how data flows through a system**, how it is **secured**, and how it is **made accessible to components or external apps**.

Different API patterns shape how other parts of a project function. In the **frontend**, the pattern you choose determines how data is requested—REST, GraphQL, or SDK—and whether components call URLs directly or rely on abstracted methods. The **auth system** is tightly linked: some patterns (like REST) expose routes that require tokens in headers, while others (like SDKs) manage sessions internally. Your **logic layer**—especially custom hooks—depends on how the API is structured; hooks often wrap REST calls, GraphQL queries, or SDK methods to create reusable behavior. **Environment configuration** plays a critical role: each pattern requires different keys, secrets, or endpoint structures that must be scoped to dev, preview, or production. Finally, the **AI tools** you use (like v0.dev, Cursor, or Replit) scaffold code differently depending on the pattern—knowing which structure you’re using improves the quality and reliability of AI-generated output.


---

## 🧩 What Is an API in This Context?

An **API** is any structured method of exposing or requesting data, logic, or operations between layers.

APIs appear in:
- Web applications (e.g. fetching user data)
- Internal logic layers (e.g. server functions triggered by UI)
- External integrations (e.g. calling Stripe, OpenAI, or Notion)

API patterns describe **how these interactions are organized**, both internally (within your project) and externally (between services or users).

---

## 🧱 Common API Patterns

---

### ▸ REST Pattern

**Definition**  
Each URL (or “endpoint”) represents a **resource** (e.g. a user, post, or session), and HTTP methods define the action (`GET`, `POST`, `DELETE`, etc.).

**Where It Shows Up**  
- Most backend frameworks by default (Node/Express, FastAPI, Laravel)
- Supabase, Firebase, and Hasura expose REST interfaces
- Tools like Postman or Insomnia are built for REST testing

**Why It Exists**  
REST provides a **uniform, stateless way** to expose data. It maps directly to CRUD actions.

**Structural Impact**  
- URL structure acts as a hierarchy (`/api/posts/123/comments`)
- Supports caching, pagination, filtering at the URL level

**Connected Vibe Layers**  
- `backend-architecture`: Standard structure for internal/external endpoints  
- `database-modeling`: Directly maps to rows, tables, resources  
- `auth-systems`: Often includes token-authenticated endpoints  
- `ai-assistance`: Prompts like “generate a RESTful user endpoint” scaffold this pattern

---

### ▸ GraphQL Pattern

**Definition**  
Instead of multiple endpoints, one single endpoint responds to **structured queries** where the client specifies exactly what data it needs.

**Where It Shows Up**  
- Platforms like Hasura, Apollo, Shopify  
- Tools like GraphiQL (exploration) or Relay (frontend binding)

**Why It Exists**  
Reduces over-fetching and under-fetching. Designed to allow frontends to **request exactly what they need**.

**Structural Impact**  
- Replaces URL hierarchy with schema-driven queries  
- Shifts complexity to the query layer, enabling tight control at the field level

**Connected Vibe Layers**  
- `frontend-architecture`: GraphQL patterns often replace REST entirely  
- `state-management`: Requires local cache (Apollo, Relay)  
- `ai-assistance`: Prompts like “write a query to fetch all published articles with author name” return GraphQL syntax  
- `env-config`: Requires token scopes and endpoint declaration

---

### ▸ Route + Function Pattern

**Definition**  
Each API route is a **file or function** in a specific folder (e.g. `/api/sendEmail.ts`). Common in serverless and hybrid frameworks.

**Where It Shows Up**  
- Next.js API routes (`/pages/api/*`)  
- Vercel / Netlify serverless functions  
- Tools like Clerk or Supabase Edge Functions follow this pattern

**Why It Exists**  
Enables lightweight backends where each route is self-contained. No central routing table or controller is needed.

**Structural Impact**  
- Encourages logic-by-feature or logic-by-action organization  
- Reduces boilerplate for scaffolding backends

**Connected Vibe Layers**  
- `ai-assistance`: Prompts like “make an API route to create a new contact record” yield single-file endpoints  
- `environment-config`: Tied closely to deploy environment (preview vs. prod)  
- `auth-systems`: Functions can be wrapped with middleware (Clerk, NextAuth)

---

### ▸ SDK Pattern

**Definition**  
Instead of calling raw URLs, clients use an **imported library** that handles requests internally (e.g. `supabase.auth.signIn()`).

**Where It Shows Up**  
- Supabase, Stripe, OpenAI, Firebase all offer SDKs  
- AI tools scaffold these automatically when asked for "connect to X"

**Why It Exists**  
Encapsulates URL, auth, and request logic. Lets developers work with functions, not HTTP.

**Structural Impact**  
- Abstracts network logic into callable methods  
- Promotes centralized, provider-based architecture

**Connected Vibe Layers**  
- `auth-systems`: Auth flows often require SDK for token/session sync  
- `hooks-and-logic`: Custom hooks wrap SDK calls (`useUserData`, `useCreatePost`)  
- `component-patterns`: SDKs are used inside containers or headless components  
- `ai-assistance`: Prompts like “sign in with Supabase” often return SDK usage

---

### ▸ Integration Proxy Pattern

**Definition**  
An internal route or function is used as a **middleware between frontend and third-party APIs** to manage secrets, shape payloads, or throttle usage.

**Where It Shows Up**  
- Common in OpenAI, Stripe, Airtable integrations  
- Required in AI tools when working with non-public endpoints

**Why It Exists**  
Prevents exposing secrets in the frontend. Also allows customization and control over requests.

**Structural Impact**  
- API route acts as a controlled middleman  
- Can normalize or validate inputs before reaching third-party

**Connected Vibe Layers**  
- `env-config`: API keys stored in `.env` are accessed here  
- `ai-assistance`: Prompts like “create a server route that wraps a call to the OpenAI API” trigger this structure  
- `deployment`: Must be deployed as server-side logic only

---

## 🔗 Cross-System Implications

| Layer                | Impact from API Pattern Choice                                               |
|----------------------|------------------------------------------------------------------------------|
| `frontend-architecture` | Determines how frontend fetches data (REST, GraphQL, SDK, etc.)           |
| `auth-systems`       | Token handling, session persistence, and protected routes rely on API pattern |
| `hooks-and-logic`    | API calls often live inside custom hooks or async logic wrappers              |
| `environment-config` | API endpoints, secrets, and access tokens must be set per environment         |
| `ai-assistance`      | Scaffolded code changes format depending on the API pattern used              |

---

## 🧠 Summary

API patterns define **how communication flows between parts of your system**.

Understanding these patterns helps you:
- Choose the right integration approach for a given tool or goal
- Prompt AI tools with structural clarity
- Avoid leaking secrets or misconfiguring endpoints
- Connect frontend components cleanly to backend data
```
