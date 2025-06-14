---
title: Frontend Prompts
nav_order: ""
description: A collection of prompts to aid frontend development, including frameworks, libraries, and UI components.
tags:
  - frontend
  - tools
  - vibe coding
layout: default
---

# 🎯 01 Frontend Prompt Patterns

A collection of prompt starters designed to help AI tools like **Cursor**, **v0**, **Bolt**, or **Subframe** generate UI code, components, and interactivity faster.

Use these with AI-enhanced dev tools or even ChatGPT coding workflows.

---

## 🧱 Layouts & Structure

💡 “Generate a responsive React layout using Tailwind that includes a navbar, hero section, and feature grid.”

💡 “Create a two-column layout with a sidebar and main content. Make it mobile-friendly.”

💡 “Build a landing page with a header, signup CTA, and pricing cards.”

---

## 🎨 Styling & Theming

💡 “Add dark mode toggle support to this Tailwind-styled React component.”

💡 “Convert this plain HTML form into a styled React form using shadcn/ui components.”

💡 “Style this page with Tailwind to match a sleek SaaS marketing theme.”

---

## ⚙️ Interactivity & Motion

💡 “Add hover and tap animations using framer-motion to these buttons.”

💡 “Make this menu component open and close with smooth animations.”

💡 “Animate the hero section to fade in with a slight upward motion on load.”

---

## 🧠 AI Scaffolding Prompts

💡 “Scaffold a Next.js 14 app using App Router, Tailwind, and shadcn/ui. Add a homepage and login page.”

💡 “Set up a React app with Tailwind and a reusable layout system.”

💡 “Generate a full React component file with props for title, image, and action button.”

---

## 🔌 API Integration (Frontend)

💡 “Create a component that fetches blog posts from a Supabase table and displays them in cards.”

💡 “Build a React search bar that queries an API endpoint as the user types (debounced).”

💡 “Display data from a public JSON API in a responsive table using Tailwind.”

---

## 🧪 Developer Experience Prompts

💡 “Add TypeScript types to this React component and its props.”

💡 “Explain how this component's useEffect hook works.”

💡 “Refactor this component to use cleaner logic and avoid re-renders.”

---

Let me know if you want versions of this prompt set tailored for:

- Framer
- Subframe
- v0.dev
- Webflow’s Custom Code blocks

Or if you want this converted into a visual prompt matrix/grid for your repo!


```markdown
# 🎨 Frontend Prompts

This document is a practical guide to writing effective prompts for AI assistants when building the **frontend**—the visual, interactive part of your application. The quality of the AI's output is a direct reflection of the quality of your input. The key is to move from simple, vague requests to structured, specific instructions.

A good prompt tells the AI not only *what* to build, but *how* to build it, using which tools, and with what behaviors. This guide provides a cheat sheet for generating layouts, components, logic, and styles.

---
### 🧱 1. Scaffolding Page Layouts

This is about creating the high-level structure or "skeleton" of a page or screen.

* #### Basic Prompt:
    > Make a dashboard layout.

* #### Specific Prompt:
    > Scaffold a new page component for a user dashboard using **Next.js App Router**. The layout must be a **two-column grid**: a fixed **250px sidebar** on the left (for navigation) and a main content area on the right. Make it responsive so the sidebar collapses on mobile screens. Use **Tailwind CSS** for all styling.

* #### Why It's Better:
    The specific prompt defines the **technology** (Next.js, Tailwind), the **architectural pattern** (two-column grid), and the **responsive behavior**, giving the AI a clear blueprint to follow.

* #### 🛠️ Tool Examples:
    `v0.dev`, `Cursor`, `GitHub Copilot`

---
### 🧩 2. Generating Specific Components

This is about creating the individual, reusable "Lego bricks" of your user interface, like buttons, cards, and forms.

* #### Basic Prompt:
    > I need a user profile card.

* #### Specific Prompt:
    > Generate a reusable **React component** named `UserProfileCard`. It must accept **props** for `avatarUrl`, `name`, `username`, and `bio`. Inside the component, display an image for the avatar, the name, the username (prefixed with '@'), and the bio text. Include a "Follow" button. Style the card with a **border, rounded corners, and a subtle box shadow** using **Tailwind CSS**.

* #### Why It's Better:
    The specific prompt dictates the **component name**, its **API (the props)**, the **internal structure**, and the **visual style**. This ensures the generated component is immediately usable and fits your project's needs.

* #### 🛠️ Tool Examples:
    `v0.dev`, `Galileo AI`, `Subframe.com`

---
### 🧠 3. Implementing State & Interactivity

This is about adding the logic that makes your components "come alive," such as handling user input, managing state, and calling APIs.

* #### Basic Prompt:
    > Add a form that works.

* #### Specific Prompt:
    > In this existing React component, add a login form with "email" and "password" input fields. Use the `useState` hook to manage the state of each input. Implement a `handleSubmit` function that prevents the default form submission. Add simple **validation**: the email must be a valid format, and the password must be at least 8 characters long. The "Submit" button should be **disabled** until both fields are valid.

* #### Why It's Better:
    The specific prompt defines the **state management strategy** (`useState`), the **event handler** (`handleSubmit`), the **validation rules**, and the **conditional UI logic** (the disabled button). This results in a secure and user-friendly form.

* #### 🛠️ Tool Examples:
    `Cursor`, `GitHub Copilot` (within an editor like VS Code or Replit)

---
### ✨ 4. Applying Styles & Animations

This focuses on the visual polish and user experience details that make an application feel great to use.

* #### Basic Prompt:
    > Make this button look better.

* #### Specific Prompt:
    > For this button component, apply the following **Tailwind CSS** classes: `bg-blue-600`, `hover:bg-blue-700`, `text-white`, `font-bold`, `py-2`, `px-4`, `rounded`. Additionally, use the **Framer Motion** library to add an animation: when hovered, the button should scale to `1.05`. The transition should be a gentle "ease-in-out" over `0.2` seconds.

* #### Why It's Better:
    The specific prompt provides exact styling details and names the **specific animation library** to use (`Framer Motion`), along with the desired animation properties. This gives the AI precise instructions for visual execution.

* #### 🛠️ Tool Examples:
    `GitHub Copilot`, `Cursor`

---
### 🔧 5. Refactoring & Debugging Code

This is about using AI not to create, but to improve and fix existing code. This is one of the most powerful use cases for modern AI editors.

* #### Basic Prompt:
    > This code is broken, fix it.

* #### Specific Prompt:
    > This React component is throwing a "TypeError: Cannot read properties of undefined" error when the `user` prop is not yet loaded from the API. **Refactor the code** to add a **conditional render**: while the `user` prop is null or undefined, display a `LoadingSpinner` component instead of trying to render the user's details. Explain the fix.

* #### Why It's Better:
    The specific prompt describes the **error**, identifies the **likely cause**, and prescribes the **exact solution** (conditional rendering). It also asks for an explanation, which is crucial for learning. This turns the AI into a powerful debugging partner and tutor.

* #### 🛠️ Tool Examples:
    `Cursor`, `GitHub Copilot Chat`, `Sourcegraph Cody`

---
### ✅ Summary Cheat Sheet

| Prompting For... | Key Details to Include in Your Prompt | Example Tools |
| :--- | :--- | :--- |
| **Page Layouts** | Framework (Next.js, etc.), structural pattern (grid, flexbox), responsiveness, styling library (Tailwind). | `v0.dev`, `Cursor` |
| **Components** | Component name, API (props), internal elements, stateful behavior, styling details. | `v0.dev`, `Subframe.com` |
| **State & Logic**| State management hook (`useState`), event handlers, validation rules, conditional logic (e.g., disabling a button). | `GitHub Copilot`, `Cursor` |
| **Styling** | Exact library (Tailwind, Framer Motion), specific values (colors, sizes), desired animation behavior and timing. | `GitHub Copilot`, `Cursor` |
| **Debugging** | The specific error message, the suspected cause, and a suggested pattern for the fix (e.g., "add a conditional render"). | `Cursor`, `Sourcegraph Cody`|
```