---
title: UI Prompts
nav_order: ""
description: Prompts specifically focused on frontend UI design, including components, styling, animations, and user interactions.
tags:
  - ui
  - frontend
  - prompts
  - vibe coding
layout: default
---
```markdown
# 🎨 UI Prompts

This guide focuses specifically on prompts for generating the **User Interface (UI)**—the visual and interactive elements that your users see and touch. Effective UI prompting is an art of descriptive precision. It involves clearly articulating not just an element's base appearance, but also its various states, responsive behaviors, and animations.

The goal is to provide the AI with a detailed visual and interactive specification, turning your abstract design ideas into tangible, production-ready code.

---
### 🧱 1. Atomic Components

These are the smallest, fundamental building blocks of any design system. Think buttons, inputs, labels, and avatars. Getting these right is the foundation for a consistent UI.

* #### Basic Prompt:
    > Make a button component.

* #### Specific Prompt:
    > Generate a reusable **React** component named `PrimaryButton`. It must accept `children` for the label and an `onClick` event handler as props. Using **Tailwind CSS**, style it with a blue background (`bg-blue-600`), white text, medium font weight, standard padding (`py-2 px-4`), and rounded corners (`rounded-md`).

* #### Why It's Better:
    The specific prompt defines the **technology** (React), the **component's API** (its props), and the **exact styling recipe** (Tailwind classes). This leaves no room for ambiguity and results in a predictable, reusable component.

* #### 🛠️ Tool Examples:
    `v0.dev`, `Cursor`, `GitHub Copilot`

---
### 🧩 2. Composite Components (Molecules)

These are created by combining several atomic components into a single, functional unit. Examples include a search bar (an input + a button) or a user profile card.

* #### Basic Prompt:
    > I need a search bar.

* #### Specific Prompt:
    > Create a `SearchBar` React component that visually combines a text `input` field and an SVG `magnifying-glass-icon` button. The icon must be positioned **inside the input field, on the right-hand side**. When a user starts typing, a small 'X' icon should appear inside the input to clear the text. The entire component should be wrapped in a `div` with a single, light-gray border to make it look like one element.

* #### Why It's Better:
    The specific prompt describes the **composition of smaller elements**, their **exact spatial relationship**, and the **conditional logic** for its interactive parts (the 'X' icon).

* #### 🛠️ Tool Examples:
    `v0.dev`, `Subframe.com`, `Galileo AI`

---
### 📏 3. Responsive Layout & Spacing

This involves prompting for the arrangement of components on the page and, crucially, how that arrangement adapts to different screen sizes.

* #### Basic Prompt:
    > Put these three cards on the page.

* #### Specific Prompt:
    > Create a responsive grid layout using **CSS Grid** or **Tailwind CSS Grid classes**. On large screens (desktops, `lg` breakpoint and up), it must display three `ProductCard` components in a **single row with 3 equal columns** and a `gap` of 6 units. On medium screens (tablets, `md` breakpoint), it should switch to a **two-column grid**. On small screens (mobile, `sm` breakpoint), the cards must **stack vertically in a single column**.

* #### Why It's Better:
    This prompt provides explicit rules for the layout at **different device breakpoints** (`lg`, `md`, `sm`), which is the core principle of responsive web design.

* #### 🛠️ Tool Examples:
    `GitHub Copilot`, `Cursor`

---
### ✨ 4. Visual States & Interactions

A professional UI provides clear visual feedback to the user. This involves defining how components look in different states, such as when they are hovered, focused, disabled, or active.

* #### Basic Prompt:
    > Style the form input.

* #### Specific Prompt:
    > For this HTML `input` field, apply the following styles using **Tailwind CSS**: The default state should have a light gray border. When the user clicks into the field (the **`:focus` state**), the border color must change to a primary blue (`border-blue-500`) and show a subtle blue outer glow (`ring-2`). If the input has the **`disabled` attribute**, its background must be a light gray (`bg-gray-100`) and the text color should be muted (`text-gray-400`).

* #### Why It's Better:
    It clearly defines the styling for **three distinct visual states** (default, focus, disabled), which is essential for creating an intuitive and accessible user experience.

* #### 🛠️ Tool Examples:
    `v0.dev`, `GitHub Copilot`

---
### 💫 5. Micro-animations & Transitions

These are small, purposeful animations that provide feedback, guide the user's attention, and make the interface feel more polished and alive.

* #### Basic Prompt:
    > Animate this modal.

* #### Specific Prompt:
    > When this `Modal` component appears, it should not just pop into view. Instead, the modal's backdrop overlay should **fade in from 0% to 100% opacity** over `200ms`. The modal panel itself should simultaneously **scale up from 95% to 100% size** and **fade in**. Use **CSS transitions** to create this effect with an `ease-in-out` timing function.

* #### Why It's Better:
    The specific prompt breaks the animation down into multiple parts (backdrop + panel) and defines the **exact properties to animate** (`opacity`, `scale`), the **duration**, and the **timing function**.

* #### 🛠️ Tool Examples:
    `GitHub Copilot`, `Cursor`

---
### ✅ Summary Cheat Sheet

| Prompting For... | Key Details to Include in Your Prompt | Example Tools |
| :--- | :--- | :--- |
| **Atomic Components** | Component name, technology stack, API (props), specific styling details. | `v0.dev`, `Cursor` |
| **Composite Components**| The smaller components being combined, their spatial layout, and conditional logic. | `v0.dev`, `Subframe.com` |
| **Responsive Layouts** | The grid/flex system, number of columns, spacing, and behavior at different breakpoints (mobile, tablet, desktop). | `GitHub Copilot`, `Cursor`|
| **Visual States** | Specific styles for each state: default, hover, focus, active, disabled, etc. | `v0.dev`, `GitHub Copilot` |
| **Animations** | The element to animate, the properties to change (opacity, transform), the duration, and the timing function. | `GitHub Copilot`, `Cursor` |
```