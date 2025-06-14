---
title: Vibe Coding Iceberg Cheat Sheet
nav_order: ""
description: A quick-reference cheat sheet for the Vibe Coding Iceberg, summarizing key concepts and tools used in vibe coding.
tags:
  - vibe coding
  - cheat sheet
  - reference
layout: default
---
# 🧊 Vibe Coding Iceberg Cheat Sheet — Specification-as-Prompt

Vibe coding thrives when you **tell the AI what to build AND how to build it**.  
The “spec” = the structured description of your **stack**, **architecture**, and **expected output**.

---

## 🧱 UI (Frontend Layer)

Prompt the AI to scaffold reusable interface components with behavior, styling, and layout logic.

### 🔹 Basic Prompt:
> Build a responsive dashboard UI using React and Tailwind CSS.

### 🔹 Specific Prompt:
> Create a React dashboard with a sidebar (collapsible), a top nav with search and avatar, and a grid of 3 cards for user stats using Tailwind classes. Add dark mode toggle.

### 🛠️ Tool Examples:
- `v0.dev` (React + Tailwind scaffolds)
- `Cursor` or `Replit` (edit + deploy)

---

## 🔌 Services (Backend + Auth + API Layer)

Prompt to integrate third-party tools or create backend services like authentication, email, storage, etc.

### 🔹 Basic Prompt:
> Add Firebase Auth to my app.

### 🔹 Specific Prompt:
> Add Supabase Auth with email/password login and magic link. Show logged-in user's name in the navbar and redirect unauthenticated users to /login.

### 🛠️ Tool Examples:
- `Bolt` (Supabase, Firebase built-in)
- `Cursor` or `Replit` (manual SDK + setup)

---

## 🧠 Data Modeling (Schema + State + Storage Layer)

Prompt to define what data exists, how it connects, and how it's used.

### 🔹 Basic Prompt:
> Add a table of blog posts.

### 🔹 Specific Prompt:
> In Supabase, create a `posts` table with fields: `id`, `title`, `content`, `author_id (FK)`, and `created_at`. In the frontend, render a dynamic table that shows all posts with title and author name. Add ability to delete posts.

### 🛠️ Tool Examples:
- `Supabase Studio` (GUI + promptable)
- `Prisma + PostgreSQL` (with Cursor or Replit)

---

## 🛰️ Infra & Shipping (Deployment + CI/CD + Secrets)

Prompt to configure hosting, deployment pipelines, and runtime secrets.

### 🔹 Basic Prompt:
> Deploy the app to Vercel.

### 🔹 Specific Prompt:
> Set up CI/CD for Vercel to deploy from GitHub main branch. Include `.env` secrets for Supabase URL and Key. Add a `POST /api/webhook` endpoint using serverless functions to handle Stripe events.

### 🛠️ Tool Examples:
- `Vercel`, `Netlify` (CI/CD + Functions)
- `Replit` (all-in-one host/deploy/dev)

---

## 🧩 Bonus: Full-Stack Specification Prompt

> Scaffold a Next.js + Tailwind web app using Supabase for auth and database. Include login/signup with email, a dashboard that lists `tasks` (Supabase table), and a serverless API endpoint to export tasks as JSON. Deploy to Vercel with CI from GitHub.

---

## ✅ Summary

| Layer           | Focus                          | Think in Terms Of...                          |
|----------------|-------------------------------|-----------------------------------------------|
| 🧱 UI           | Layout, Components, Styling    | Buttons, grids, modals, navbars               |
| 🔌 Services     | APIs, Auth, 3rd party tools     | Firebase, Supabase, Stripe, email, storage    |
| 🧠 Data Model   | Schema, State, Logic           | Tables, types, foreign keys, queries          |
| 🛰️ Infra        | Hosting, CI/CD, Secrets        | Vercel, Netlify, deployment triggers, .env    |

> 🧠 **Specification-as-prompt** = “Build me this thing, using these tools, wired this way, with these behaviors.”

