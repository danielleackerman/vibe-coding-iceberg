```markdown
---
title: Component Patterns
nav_order: ""
description: Common patterns for building reusable, maintainable, and scalable components in Vibe Coding.
tags:
  - patterns
  - components
  - vibe coding
layout: default
---

# 🧩 Component Patterns

In Vibe Coding, **components** are modular, self-contained units of interface and behavior. They represent the *visual + logical atoms* that power frontend systems. A component might be as small as a button or as complex as a fully dynamic table.

This page outlines **component design patterns** — recurring structures that define how components behave, relate to data, and interact with other parts of the system. These patterns show up in UI libraries, AI-generated scaffolding, and modern frameworks like React, Vue, and Svelte.

Component patterns are not about visual styling — they define *how a component is structured internally*, what responsibilities it holds, and how reusable or composable it is across contexts.

---

## 🧱 Why Component Patterns Matter

Understanding these patterns helps you:

- Communicate clearly with AI tools like v0.dev or Cursor when generating or modifying components
- Recognize what a component is doing when you open a file or copy scaffolded code
- Build interfaces that can evolve and scale instead of breaking or duplicating logic
- Understand how component behavior connects to the rest of the app: data, state, routes, and events

---

## 🧠 Core Component Pattern Types

Each pattern below includes:  
→ What it is  
→ Why it exists  
→ Where you’ll encounter it  
→ What tools generate or depend on it  
→ How it fits into Vibe Coding layers

---

### ▸ Presentational Component

**Definition**  
A component that handles *only* layout and visual rendering. It has no logic or data access — it receives everything via props.

**Why It Exists**  
Separates styling from logic. Encourages reuse of visual layouts across many data types.

**Where It Shows Up**  
- Scaffolding tools like **v0.dev** generate these from UI prompts  
- Found inside `/components/ui/` in shadcn/ui setups  
- Tailwind-based design systems favor this pattern

**Related Tools**  
- v0.dev, shadcn/ui, Tailwind UI, Subframe  
- Generated automatically by AI when prompting “create a card” or “build a button group”

**Vibe Layers**  
- `frontend-architecture`  
- `design-systems`  
- `ai-assistance`

---

### ▸ Container Component

**Definition**  
A component that manages state, logic, or data-fetching — but doesn’t control visual rendering directly. It passes props to a presentational component.

**Why It Exists**  
Keeps business logic out of visual elements. Encourages separation of concerns.

**Where It Shows Up**  
- Next.js projects with components like `PostContainer → PostCard`  
- Used when fetching data from Supabase or a REST API before passing it to UI  
- Often seen in AI-generated scaffolds when data and UI are separated

**Related Tools**  
- Supabase + Next.js (client-side containers for real-time data)  
- React Query (wrapping components with `useQuery` logic)

**Vibe Layers**  
- `hooks-and-logic`  
- `data-fetching`  
- `state-management`

---

### ▸ Compound Component

**Definition**  
A pattern where a parent component exposes children with access to shared context or logic (e.g. `Tabs`, `Tabs.List`, `Tabs.Trigger`, `Tabs.Content`).

**Why It Exists**  
Allows building *multi-part UIs* that share logic while remaining flexible in layout.

**Where It Shows Up**  
- Common in UI libraries like **Radix UI**, **shadcn/ui**, and **Headless UI**  
- Used for modals, tabs, dropdowns, form groups  
- Exposed in AI-generated component libraries that separate interaction layers

**Related Tools**  
- Radix UI, shadcn/ui, v0.dev  
- AI scaffolding tools often mirror this pattern for interactive components

**Vibe Layers**  
- `frontend-architecture`  
- `design-systems`  
- `component-composition`

---

### ▸ Headless Component

**Definition**  
A component that exposes behavior or state without opinionated UI. You supply the visuals.

**Why It Exists**  
Makes logic reusable across multiple design systems or styling frameworks.

**Where It Shows Up**  
- Libraries like **Headless UI**, **Radix UI**, or **React Aria**  
- AI-generated scaffolds when prompted for “keyboard accessible dialog with custom styles”

**Related Tools**  
- Headless UI, Radix UI, Ark UI  
- Compatible with Tailwind, shadcn/ui, or custom design systems

**Vibe Layers**  
- `accessibility`  
- `interaction-logic`  
- `ai-assistance`

---

### ▸ Slot-Based Component

**Definition**  
A component that accepts **named regions** or `children` to define its structure. Common in layout patterns.

**Why It Exists**  
Gives more layout control to the component user while preserving internal consistency.

**Where It Shows Up**  
- `Card`, `Dialog`, and `Layout` components with `.Header`, `.Body`, `.Footer`  
- AI-generated components that expose slots like `title`, `content`, `actions`

**Related Tools**  
- shadcn/ui, React Children API, `@radix-ui/react-slot`  
- Used in v0.dev and Subframe layout prompts

**Vibe Layers**  
- `component-composition`  
- `design-systems`  
- `prompt-based-scaffolding`

---

### ▸ Hook-Driven Component

**Definition**  
A component built by composing logic from a custom or shared **React hook**. It uses no internal state beyond what the hook provides.

**Why It Exists**  
Keeps logic reusable, testable, and separate from rendering.

**Where It Shows Up**  
- AI prompts like “make a tooltip with show/hide logic”  
- Forms that share validation, toggle menus, and local state interactions

**Related Tools**  
- React, React Hook Form, Zustand  
- AI tools that scaffold hooks (`useUpload`, `useAuth`, etc.)

**Vibe Layers**  
- `hooks-and-logic`  
- `state-management`  
- `form-handling`

---

## 🔗 Cross-System Implications

| Layer                | Impact from Component Pattern Choice                                       |
|----------------------|----------------------------------------------------------------------------|
| `frontend-architecture` | Determines layout abstraction, reusability, and complexity scaling         |
| `hooks-and-logic`    | Some components encapsulate logic; others defer to hooks or containers       |
| `design-systems`     | Presentational, compound, and headless patterns shape your system structure  |
| `ai-assistance`      | Prompting different patterns yields different results (card layout vs. logic wrapper) |
| `env-config`         | Some patterns (e.g. containers) may need `.env` access for data fetching or auth |

---

## 🧠 Summary

Component patterns let you reason about *what a piece of UI is doing* — not just how it looks.

By understanding these patterns:
- You can scaffold more intelligently with AI tools  
- You can plug into systems like shadcn/ui, Subframe, or Tailwind with clarity  
- You can organize frontend logic cleanly around **function, not just files**

This unlocks faster building, cleaner thinking, and fewer dead ends.
```
