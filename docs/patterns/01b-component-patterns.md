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
Understood. Let’s fix this now.

What I see is:

You want the **Component Patterns page** to follow the **exact form and tone** of your **Foundations Introduction** sample — not just “list known React patterns,” but:

* Define clearly **what a component is** in this system
* Define **what a pattern is** and **why patterns exist in component design**
* Connect component patterns to the broader **stack and system architecture**
* Clarify **why these distinctions matter** in practice, especially with AI tools or in a modular design context
* Provide **clean structure**, not tutorial writing
* Serve as a **conceptual lens**, not a library

Let me now rewrite the **Component Patterns** page from the ground up in that format — full-page, standalone, structured, and flat in tone — as a **foundational reference page**, not a lesson.

Coming up next.


```markdown
# 🧱 Component Patterns

The `component-patterns/` file defines the structural logic behind how interface components are organized, named, and used within the broader Vibe Coding system. It outlines common architectural roles components may take on, independent of framework, and describes how they function across layers of a modern, AI-assisted development stack.

This page is not a style guide or tutorial. It exists to clarify what component patterns are, why they matter, and how they interact with the larger system when designing, prompting, or assembling interface logic at scale.

---

## 📌 What Are Components in Vibe Coding?

In modern frontend systems, a **component** is a unit of UI that may include markup, logic, and behavior. Components can represent:

- A layout region (e.g. `Header`, `Sidebar`, `Grid`)
- A reusable element (e.g. `Button`, `Card`, `InputField`)
- A feature-specific structure (e.g. `UserAvatar`, `CommentForm`, `SessionBanner`)

Components may be pure-presentational, logic-bound, or hybrid structures. Vibe Coding treats components as **discrete units in a larger composable architecture**, not as fixed building blocks or isolated files.

---

## 📦 What Are Component Patterns?

**Component patterns** define how components are structured, where logic lives, and how behavior and UI are separated or combined.

They are not visual styles. They are **structural roles** that allow components to:

- Be composed into layouts
- Share state across views
- Expose functionality without prescribing design
- Support clarity in AI prompt generation or code scaffolding

Each pattern solves a specific constraint related to **state management, reuse, testing, or composability**.

---

## 🧱 Common Component Patterns

This section defines structural roles that components often follow in modern frontend frameworks (especially React, Vue, and Svelte). These patterns also appear in component libraries (e.g. shadcn/ui, Radix UI), AI tools (e.g. v0.dev, Locofy, Cursor), and headless CMS/frontends (e.g. Builder.io, Webflow Logic).

Each pattern solves a particular problem in layout, state management, reusability, or design-handling.

---

### ▸ Presentational Component

**Definition**  
A stateless component responsible only for rendering visual output. Receives all data and callbacks via props.

**Tool Context**  
- Found in most React-based UIs (Next.js, Remix, etc.)  
- Common in design systems (e.g. `Button`, `Avatar`, `Badge`)  
- Frequently scaffolded by AI tools that generate "dumb" UI shells

**Use Case**  
- Pure UI without logic
- Easily styled or themed
- Reusable across contexts

**Vibe Coding Layers**  
- `frontend-architecture`  
- `design-systems`  
- `ai-assistance` (UI-only scaffolds)

---

### ▸ Container Component

**Definition**  
A logic-holding wrapper that fetches data, manages state, or computes derived values—then passes them into a presentational child.

**Tool Context**  
- Used in stateful React logic (Next.js server/client boundary)  
- Cursor AI often scaffolds containers around async functions  
- Common pattern in Redux, React Query, and data-fetch-heavy components

**Use Case**  
- Separate business logic from layout  
- Simplify testing and reuse  
- Compose data flows cleanly

**Vibe Coding Layers**  
- `state-management`  
- `hooks-and-logic`  
- `ai-assistance` (logic-first generation)

---

### ▸ Compound Component

**Definition**  
A parent component manages shared state; its children are declarative subcomponents that consume that state via context or scoped slots.

**Tool Context**  
- Radix UI (e.g. `Tabs`, `Accordion`)  
- shadcn/ui’s complex components  
- Pattern recommended in design system scaffolds like Modulz or Ark UI

**Use Case**  
- Tabs, menus, step flows, grouped forms  
- Consistent layout with multiple parts  
- Declarative usage in JSX or component DSLs

**Vibe Coding Layers**  
- `design-systems`  
- `ui-patterns`  
- `component-patterns`

---

### ▸ Headless Component

**Definition**  
Encapsulates logic, state, and accessibility behavior, but renders nothing. Caller supplies the markup/render.

**Tool Context**  
- Radix UI is fully headless  
- Ark UI and Headless UI by Tailwind Labs  
- Used in AI-assisted libraries like v0.dev, which generate wrappers around logic

**Use Case**  
- Maintain logic/UI separation  
- Allow flexible rendering  
- Reuse behavior without enforcing structure

**Vibe Coding Layers**  
- `logic-abstraction`  
- `prompt-design`  
- `component-patterns`

---

### ▸ Slot-Based Component

**Definition**  
Component accepts named subregions via children (e.g. `<Card.Header>`, `<Card.Body>`). No explicit props passed for layout—structure emerges from nesting.

**Tool Context**  
- Used in shadcn/ui, Chakra UI, Bootstrap JSX  
- Design tools like Webflow mimic this pattern visually  
- Helpful in AI prompt flows for layout scaffolds

**Use Case**  
- Create repeatable layout patterns  
- Support flexible content injection  
- Promote consistency without rigid templates

**Vibe Coding Layers**  
- `frontend-architecture`  
- `design-systems`  
- `component-patterns`

---

### ▸ Hook-Driven Component

**Definition**  
Component logic (e.g. state, effects, validation, open/close toggles) is extracted to a hook. The component becomes a consumer of shared logic.

**Tool Context**  
- Native in React (`useX`)  
- Scaffolding tools like Codium, Cursor frequently extract logic to hooks  
- Design system behavior often lives in hook packages (`useDialogState()`)

**Use Case**  
- Reuse state/behavior across components  
- Simplify testing  
- Isolate concerns

**Vibe Coding Layers**  
- `hooks-and-logic`  
- `state-management`  
- `component-abstraction`



---

## 💡 Why This Matters

Without component patterns, frontend codebases become difficult to navigate, test, or scale. Component logic mixes with layout, internal state leaks across unrelated features, and AI-generated scaffolds become unpredictable.

Using patterns provides:

- **Predictability** when using or prompting component scaffolds
- **Separation of concerns** for more modular state and layout
- **Reusability** across different UI contexts or brands
- **Replaceability** for faster iteration and testing
- **Clarity** when sharing logic between projects or systems

Component patterns are not mandatory. They are composable constraints that **create architectural consistency** across AI-generated, designer-authored, or hand-coded UI systems.

---

## 🔗 How This Connects to the Vibe Coding System

| Layer                     | Connection to Component Patterns                                        |
|---------------------------|-------------------------------------------------------------------------|
| `frontend-architecture`   | Component patterns define how UI elements are composed and rendered     |
| `hooks-and-logic`         | Hook-driven patterns isolate logic for reuse and testability            |
| `state-management`        | Controlled/uncontrolled components define how state is lifted or shared |
| `naming-patterns`         | File names and exports often encode the role of a component (`XCard`, `useX`) |
| `ai-assistance`           | Consistent structure improves promptability and generation stability    |
| `design-systems`          | Presentational and slot-based patterns support design token consistency |

---

## 🎯 What This Reference Helps Clarify

- What kinds of structural roles components can play
- How logic and UI can be separated or combined
- Which patterns support scalable, promptable UIs
- What to name and export when structuring components
- How design and behavior systems remain flexible but organized

---

## 📁 How to Use These Files

This reference serves as a foundation for interpreting, generating, or modularizing UI logic in an AI-assisted development environment. Each sub-pattern may appear across projects and should be named consistently in prompts, files, and logic layers.

Use this page to align component scaffolds with clear intent and repeatable structure.
```
