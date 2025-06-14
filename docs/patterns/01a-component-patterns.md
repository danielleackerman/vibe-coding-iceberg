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
````markdown
# 🧱 Component Patterns

Components are the building blocks of modern interfaces—and in **Vibe Coding**, components are treated like **instruments**: modular, reusable, expressive, and built for remix.

But without structure, components can quickly become messy, rigid, or hard to share. That’s where **component patterns** come in.

These patterns help you build components that are:
- Easy to understand
- Easy to test
- Easy to reuse across projects and screens
- Flexible enough to evolve with your app

This page introduces the most useful component patterns in Vibe Coding and shows how they connect to the larger system.

---

## 🎛️ What Is a Component?

A **component** is a piece of UI logic bundled with its behavior and styling.  
In React (or similar frameworks), it’s usually a function that returns JSX.

```tsx
function Button({ label }) {
  return <button>{label}</button>;
}
````

But in Vibe Coding, we go a step further:

* Components express **intent** (not just visuals)
* They’re **composable** (built to plug into bigger flows)
* They use **clear boundaries** between structure, logic, and style

---

## 🧩 Key Component Patterns

| Pattern Name                    | Purpose & Use Case                                       |
| ------------------------------- | -------------------------------------------------------- |
| **Presentational vs Container** | Separate UI (presentational) from logic (container)      |
| **Compound Component**          | Share internal state across nested components            |
| **Headless Component**          | Provide logic without rendering UI                       |
| **Slot / Children-as-Prop**     | Pass layout/content through children or render props     |
| **Hook-Driven State**           | Move logic to custom hooks for reuse and testing         |
| **Smart Wrapper / Dumb Child**  | One component handles config/context; the other displays |

Each of these solves a specific problem of **readability, reuse, or scalability**.

---

## 🔍 Pattern Details

### 1. Presentational vs Container

**Split components into:**

* **Presentational**: only concerned with how things look
* **Container**: handles data, state, and side effects

```tsx
// Presentational
export function UserCard({ name, avatar }) {
  return <div><img src={avatar} /> <p>{name}</p></div>;
}

// Container
export function CurrentUserCard() {
  const { user } = useCurrentUser();
  return <UserCard name={user.name} avatar={user.avatar} />;
}
```

> Benefit: Makes components easy to test, theme, or reuse with different data sources.

---

### 2. Compound Components

Use when multiple components need to share implicit context (like Tabs, Accordion, Form steps).

```tsx
<Tabs>
  <Tabs.List>
    <Tabs.Trigger value="a">A</Tabs.Trigger>
    <Tabs.Trigger value="b">B</Tabs.Trigger>
  </Tabs.List>
  <Tabs.Panel value="a">Tab A</Tabs.Panel>
  <Tabs.Panel value="b">Tab B</Tabs.Panel>
</Tabs>
```

> Benefit: Looks declarative in JSX, but powered by shared internal logic.

---

### 3. Headless Components

A **headless** component manages state/logic but doesn't dictate appearance.
You supply the render UI.

```tsx
<Popover>
  {({ open, toggle }) => (
    <>
      <button onClick={toggle}>Toggle</button>
      {open && <div className="popover">Menu</div>}
    </>
  )}
</Popover>
```

> Benefit: Fully customizable UI with baked-in logic.

---

### 4. Slot Pattern / Children-as-Prop

Lets you inject content/layout into a reusable wrapper.

```tsx
<Card>
  <Card.Header>Title</Card.Header>
  <Card.Body>Content goes here.</Card.Body>
  <Card.Footer>Actions</Card.Footer>
</Card>
```

> Benefit: Encourages structured, reusable layouts.

---

### 5. Hook-Driven State

Move complex logic out of components and into **custom hooks**.

```tsx
function useTimer(initial = 0) {
  const [time, setTime] = useState(initial);
  useEffect(() => {
    const id = setInterval(() => setTime(t => t + 1), 1000);
    return () => clearInterval(id);
  }, []);
  return time;
}

function TimerDisplay() {
  const time = useTimer();
  return <div>{time}s</div>;
}
```

> Benefit: Keeps components clean and logic testable.

---

## 🧠 How These Patterns Connect

| Vibe Layer             | How Component Patterns Help                               |
| ---------------------- | --------------------------------------------------------- |
| **Design Systems**     | Components become design tokens—predictable and reusable  |
| **State Management**   | Patterns like hooks + context manage shared state cleanly |
| **UI/UX Patterns**     | Layouts and interactivity made modular and composable     |
| **Team Collaboration** | Clear boundaries reduce conflict and speed handoff        |
| **AI Assistance**      | AI can scaffold reusable components if patterns are clear |

Component patterns create structure without stifling creativity.
They let you remix faster, test confidently, and scale with clarity.

---

## 🚫 Common Anti-Patterns

| Anti-Pattern             | Pattern Fix                                        |
| ------------------------ | -------------------------------------------------- |
| **All-in-one component** | Split into container + presentational              |
| **Prop explosion**       | Use object props, context, or slots                |
| **Hard-coded layout**    | Use children-as-prop or compound component pattern |
| **Tangled logic**        | Extract state to a custom hook                     |
| **Duplicate UI logic**   | Create headless component for shared state mgmt    |

---

## 💬 AI Prompt Examples

* “Generate a headless React accordion component with render prop pattern.”
* “Create a presentational button and a container button with loading state.”
* “Write a compound component pattern for Tabs with shared context.”
* “Refactor this monolithic component into container + UI split.”

➡️ [Explore more prompt ideas →](../prompts/component-pattern-prompts.md)

---

## 🧬 Summary

Component patterns help you build **interfaces that scale**.

Start by:

* Splitting logic from layout
* Using hooks for state
* Wrapping UI into smart layouts with children-as-prop

Then:

* Practice composition with compound components
* Refactor large pieces into smaller, testable units
* Document shared patterns so others can riff on them

**A component should be like a chord: complete, playable, and reusable.**
Component patterns are how you write them.

```
```
