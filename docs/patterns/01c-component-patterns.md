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
# 🧱 Component Patterns

The `component-patterns/` page defines the structural logic behind how components function and interconnect within modern frontend development systems. It is not a coding guide—it is a **structural reference**. It exists to help you understand how different types of components are designed, how they separate concerns, and how they scale across AI-assisted and modular ecosystems.

This reference is meant to clarify what component patterns are, **where they show up in real tools**, **what problems they solve**, and **how they interact with the other architectural layers of Vibe Coding**.

---

## 🧩 What Are Components?

In modern frameworks (especially React, Vue, and Svelte), a **component** is a unit of user interface logic. Components can represent:

- A visual element (`Button`, `Avatar`, `Badge`)
- A layout region (`Sidebar`, `Container`, `Stack`)
- A reusable logic + UI package (`FormField`, `SessionGuard`, `Tabs`)

Components are **modular architectural units** that can be composed, reused, and understood in the context of system architecture. Components are part of the **frontend layer**, but interact with logic, data, and state layers.

---

## 🧱 Common Component Patterns

This section defines structural roles that components follow in modern frontend systems. These patterns are visible in frameworks (React, Svelte), design systems (Radix UI, shadcn/ui), AI code tools (Cursor, v0.dev), and web IDEs (Replit, Builder.io).

Each pattern describes how a component is structured, where state and logic live, and how it can be reused or composed.

---

### ▸ Presentational Component

**Definition**  
A stateless component responsible only for rendering visual output. Receives all data and callbacks via props.

**Tool Context**  
- Common in React-based UI libraries (Next.js, Remix)  
- Scaffolded by v0.dev, Locofy, and other low-code tools  
- Used in design systems (`Button`, `Badge`, `Heading`)

**Use Case**  
- Modular UI  
- Theming and layout  
- Swappable display layers

**Vibe Coding Layers**  
- `frontend-architecture`  
- `design-systems`  
- `ai-assistance` (UI-only scaffolds)

---

---

### ▸ Container Component

**Definition**  
Wraps logic, data fetching, or computed values. Delegates rendering to a child component.

**Tool Context**  
- Found in React, Vue, and Svelte routing/data frameworks  
- Used in Cursor scaffolds and state libraries like Zustand, Jotai  
- Separates data access from layout

**Use Case**  
- Server-client handoff  
- State abstraction  
- Composable logic wrappers

**Vibe Coding Layers**  
- `state-management`  
- `hooks-and-logic`  
- `ai-assistance`

---

### ▸ Compound Component

**Definition**  
A parent component manages state and context, while subcomponents access and render parts of that state.

**Tool Context**  
- Used in Radix UI, Ark UI, and headless design systems  
- Enabled by React context or slots in other frameworks  
- Pattern encouraged in step forms, tabs, dropdowns

**Use Case**  
- Declarative multi-part UI  
- Reusable grouped logic  
- Design system structuring

**Vibe Coding Layers**  
- `design-systems`  
- `ui-patterns`  
- `component-patterns`

---

### ▸ Headless Component

**Definition**  
Component holds state/logic but renders nothing. Consumer supplies all markup.

**Tool Context**  
- Radix UI, Headless UI (Tailwind Labs), Ark UI  
- AI-generated logic wrappers (Cursor, v0.dev)  
- Often implemented as render props or hooks

**Use Case**  
- Full design control  
- Accessibility compliance  
- Behavior reuse without visual constraints

**Vibe Coding Layers**  
- `logic-abstraction`  
- `prompt-design`  
- `component-patterns`

---

### ▸ Slot-Based Component

**Definition**  
Layout is defined by structured children. Named slots (e.g. `Card.Header`, `Card.Footer`) create flexible layout templates.

**Tool Context**  
- Used in shadcn/ui, Radix, and theme-driven component libraries  
- Also supported visually in Builder.io or Webflow  
- Matches the mental model of “content zones”

**Use Case**  
- Custom layout inside shared wrapper  
- Flexible content zones  
- Consistent page structures

**Vibe Coding Layers**  
- `frontend-architecture`  
- `design-systems`  
- `component-patterns`

---

### ▸ Hook-Driven Component

**Definition**  
All internal state, effects, and computed logic are extracted into a custom hook. The component handles layout only.

**Tool Context**  
- Core pattern in React (`useX`)  
- Used in AI-generated scaffolds that extract logic  
- Common in form libraries, state containers, modal flows

**Use Case**  
- Reuse logic across multiple components  
- Simplify testing and composition  
- Reduce prop drilling

**Vibe Coding Layers**  
- `hooks-and-logic`  
- `state-management`  
- `component-abstraction`

---

## 🔗 How Component Patterns Relate to Other Layers

| Layer                     | Pattern Interaction                                                                 |
|---------------------------|--------------------------------------------------------------------------------------|
| `frontend-architecture`   | Patterns define how UI elements are composed, structured, and tested                |
| `hooks-and-logic`         | Hook-based patterns isolate behavior from view components                          |
| `design-systems`          | Slot-based and compound patterns support token-based design systems                 |
| `state-management`        | Container and controlled patterns define where state is held and how it's reused    |
| `ai-assistance`           | Predictable patterns allow AI tools to generate or refactor logic more consistently |

Patterns define **structure**, not style. They allow human and AI agents to reason about a component's role without relying on naming guesswork.

---

## 🧠 Summary

Component patterns help answer the question:  
**"What role does this component play in the system?"**

Understanding and naming component patterns correctly enables:

- Composable interface logic  
- Predictable and scalable UI structures  
- Better prompt design for AI coding tools  
- Clearer frontend architecture across views, layouts, and behaviors

Use these patterns to define structure.  
Then layer on styling, theming, and interactivity from design systems or external libraries.



