---
title: Frontend Architecture
nav_order: ""
description: Overview of frontend architecture in the Vibe Coding Iceberg, focusing on UI frameworks, components, and tooling.
tags:
  - frontend
  - architecture
  - vibe coding
layout: default
---
# 🎨 Frontend Architecture

The **frontend** is everything the user sees and interacts with — the visible tip of the iceberg. It's where design meets code, and structure meets storytelling.

---

## 🧱 What It Includes

- **UI Frameworks** – React, Vue, Svelte, Solid
- **CSS Systems** – Tailwind, CSS Modules, Styled Components
- **Component Systems** – Atomic design, reusable UI libraries, shadcn/ui
- **Routing** – Next.js App Router, React Router
- **Animations & Interactions** – Framer Motion, GSAP, CSS transitions
- **Build Tools** – Vite, Webpack, Parcel

---

## 🎯 Core Responsibilities

- Rendering data to the user
- Managing layout and responsiveness
- Handling UI state and navigation
- Communicating with APIs (fetch, axios)
- Managing assets (images, fonts, icons)

---

## 🧠 Design Decisions

| Consideration      | Options                                             | Questions to Ask                                             |
|--------------------|-----------------------------------------------------|---------------------------------------------------------------|
| UI Framework       | React, Vue, Svelte, Solid                          | What ecosystem do you want to be part of?                    |
| Styling System     | Tailwind, CSS Modules, Chakra, raw CSS             | Do you need utility-first speed or scoped component styles?  |
| Components         | Build your own, or use something like shadcn/ui?   | Do you need accessibility, theming, or animations?           |
| Routing            | File-based or manually mapped?                     | Will this be an SPA, MPA, or server-rendered app?            |
| Tooling            | Vite, Webpack, Turbopack                           | Do you need blazing-fast hot reload or advanced config?      |

---

## 🔌 AI Prompt Examples

Use these with tools like **Cursor, Bolt, v0.dev**, or **Subframe**.
💡 “Generate a responsive React component using Tailwind that includes a navbar, hero section, and CTA.”

💡 “Scaffold a Next.js app with shadcn/ui and App Router, styled using Tailwind. Add a homepage and a login screen.”

💡 “Add framer-motion animations to this React component: [paste code].”
➡️ [See more frontend-specific prompts →](../prompts/frontend-prompts.md)

---

## 🧰 Tools That Affect This Layer

| Tool         | How It Helps                                                             |
|--------------|--------------------------------------------------------------------------|
| **v0.dev**   | Generates React + Tailwind UI from prompts                               |
| **Subframe** | Visual UI editor with clean React export                                 |
| **Cursor**   | Code refactoring, UI generation via AI inside VS Code                    |
| **Bolt**     | UI prototyping + instant app scaffolding                                 |
| **Framer**   | Design-first app builder with export to React (limited interactivity)    |
| **shadcn/ui**| Prebuilt, accessible components using Tailwind and Radix primitives      |

---

## ## 📌 Frontend Layers in Practice

Here is an overview of how the frontend architecture is structured in practice, reformatted as a table.

| Layer | Key Concepts & Examples |
| :--- | :--- |
| **User Interface (UI)** | Components, Layouts, Buttons, Forms, Modals |
| **State & Navigation** | `React`, `Next.js`, Local State, Global Context, Router |
| **Styling** | `CSS`, `Tailwind`, Design Tokens, Responsive Design, Dark/Light Modes |
| **API/Backend Integration**| `fetch`, `axios`, JSON, GraphQL, REST, Edge Functions |