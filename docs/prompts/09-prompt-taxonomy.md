---
title: Prompt Taxonomy
nav_order: ""
description: Categorization and classification of various prompt patterns for easy reference and organization.
tags:
  - prompts
  - taxonomy
  - vibe coding
layout: default
---
I understand completely. It's time to turn the lens on the process itself and codify what we've learned together. You are right to be frustrated with a process that often feels like speaking into the void. This guide is dedicated to fixing that.

The goal here isn't just to list prompts; it's to create a **playbook for communication**. It's about learning the language that turns an AI from a confusing black box into a powerful, effective creative partner. Let's break down the principles of writing prompts that actually work.

```markdown
# 📝 Prompt Taxonomy: A Guide to Effective AI Specification

Writing effective prompts for AI development is a new and essential skill. It's easy to get frustrated when a simple request yields a generic, useless, or broken result. The feeling that the AI "isn't listening" is a common, and valid, experience.

This guide codifies the principles of writing prompts that *work*. The fundamental shift is to stop thinking of prompts as simple questions and start thinking of them as **"Specification-as-Prompt."** An effective prompt is a blueprint. It doesn't just tell the AI *what* to build; it tells the AI *how* to build it, with which tools, and under what constraints.

This is the playbook for turning your ideas into functional code.

---
### 1. Generative Prompts: Creating From Scratch

This is the most common type of prompt, used to generate new code, components, or even entire pages. The core principle is to **move from a vague "what" to a specific "how."**

* #### Ineffective Prompt:
    > Make a testimonials section for my homepage.

* #### Effective Prompt (The Anatomy of a Specification):
    > Using **React** and **Tailwind CSS**, create a `Testimonials` component.
    >
    > - **[The Structure]:** It should be a grid that displays three customer testimonials side-by-side on desktop, and stacks vertically on mobile.
    > - **[The Child Component]:** Each testimonial should be a `TestimonialCard` component with props for `quote`, `authorName`, `authorTitle`, and `avatarImage`.
    > - **[The Styling]:** The cards should have a light gray background, rounded corners, and a subtle drop shadow. The author's name should be bold.
    > - **[The Data]:** For now, populate the component with placeholder data for three distinct testimonials.

* #### Why It's Better:
    The effective prompt provides a complete technical and visual specification. It defines the **technology stack**, the **component architecture** (a parent component with children), the **API of the components** (the props), the **visual design**, and the **data requirements**. The AI doesn't have to guess at anything; it can simply execute the blueprint.

---
### 2. Refactoring Prompts: Improving Existing Code

This type of prompt is for taking code that works but is inefficient, messy, or outdated, and improving it based on a specific goal. The core principle is to **provide the "before" context and describe the desired "after" state.**

* #### Ineffective Prompt:
    > Make this code better.

* #### Effective Prompt (The Anatomy of a Refactor):
    > Here is a React component that uses a long `if/else if/else` chain to render different icons based on a `status` prop.
    >
    > - **[The Context & The Code]:** `[Paste the existing code block here]`
    > - **[The Goal]:** Refactor this logic to be cleaner and more scalable.
    > - **[The Specific Instruction]:** Replace the `if/else` chain with a **JavaScript object or Map** that maps each status string (e.g., `'success'`, `'error'`, `'warning'`) to its corresponding icon component. This will make it easier to add new statuses in the future.

* #### Why It's Better:
    It provides the AI with the exact code to be improved, clearly states the high-level goal ("cleaner and more scalable"), and prescribes the **specific programming pattern** to use for the solution (a map/object lookup).

---
### 3. Debugging & Explanatory Prompts: Fixing and Understanding

This is for when things are broken. The goal is not just to get a fix, but to understand *why* the bug occurred in the first place. The core principle is: **show the error, state the goal, and always ask "why?"**

* #### Ineffective Prompt:
    > My code is broken and I don't know why.

* #### Effective Prompt (The Anatomy of a Debug Request):
    > I am getting a **"TypeError: Cannot read properties of undefined"** error in my application.
    >
    > - **[The Code Context]:** It's happening in this React component when I try to render `user.profile.name`. `[Paste the relevant component code here]`
    > - **[The Suspected Cause]:** I think the error occurs because the `user` object is being fetched from an API, and the component tries to render before the data has arrived.
    > - **[The Request]:** Show me how to fix this by adding a **conditional render** to display a "Loading..." message while the data is being fetched. **Most importantly, please explain *why* this type of error (a race condition) happens in asynchronous applications.**

* #### Why It's Better:
    It provides the **error message**, the **code**, and a **hypothesis**, which gives the AI tremendous context. Crucially, by asking for an explanation, it turns the AI from a simple code fixer into a powerful tutor, helping you avoid the same mistake in the future.

---
### 4. Workflow & Fullstack Prompts: Automating Processes

This is the most advanced category, where you instruct the AI to perform complex, multi-step tasks that span the entire application stack. The core principle is to **define the entire vertical slice of the feature.**

* #### Ineffective Prompt:
    > Build me a social media app.

* #### Effective Prompt (The Anatomy of a Fullstack Specification):
    > Scaffold a complete "like" feature for a post in my **Next.js/Supabase** application.
    >
    > 1.  **[Database Layer]:** Add a `likes` table to my **Supabase** database with `user_id` and `post_id` columns, creating a many-to-many relationship.
    > 2.  **[API Layer]:** Create a new **Next.js API route** at `/api/posts/[id]/like`. It should be a `POST` request that creates a new record in the `likes` table. It must be protected so only authenticated users can call it.
    > 3.  **[Frontend Layer]:** In my `Post` component, add a "Like" button next to a like count. When clicked, it should call the API endpoint. Implement an **optimistic update** on the frontend so the like count immediately increments, even before the API call completes.

* #### Why It's Better:
    It provides a step-by-step plan that clearly defines the required work for **each layer of the stack**: the database, the API, and the frontend. It even specifies an advanced user experience pattern (optimistic updates), giving the AI a complete feature blueprint.

---
### ✅ Summary Cheat Sheet: The Principles of Effective Prompting

| Prompt Type | Core Principle | Key Information to Include |
| :--- | :--- | :--- |
| **Generative** | Go from a vague "what" to a specific "how." | Technology Stack, Component API (props), Visual & Behavioral Specifications. |
| **Refactoring** | Provide the "before" and describe the desired "after." | The code to be changed, the high-level goal, and a specific pattern for the solution. |
| **Debugging** | Show the error, state the goal, and ask "why?" | The error message, the relevant code, a hypothesis, and a request for an explanation. |
| **Workflow** | Define the entire vertical slice of the feature. | Instructions for each layer of the stack (Database, API, Frontend, etc.). |