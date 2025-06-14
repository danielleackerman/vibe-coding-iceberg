---
title: Fullstack Prompts
nav_order: ""
description: Prompt examples and patterns for full-stack development across frontend and backend technologies.
tags:
  - fullstack
  - prompts
  - vibe coding
layout: default
---
# 🚀 Fullstack Prompts

Fullstack prompts are the most powerful instructions you can give an AI assistant. They don't just ask for an isolated UI component or a single API endpoint; they describe an entire **feature slice**, connecting the user interface, the API, the database, and the business logic all in a single, comprehensive request.

Mastering fullstack prompts allows you to scaffold complete, end-to-end features with a single command. The key is to provide a clear blueprint that specifies the technologies to be used and the desired behavior for each layer of the application stack.

---
###  CRUD Feature Scaffolding

This is the most common fullstack task: generating all the connected parts needed to Create, Read, Update, and Delete (CRUD) a new type of data in your application.

* #### Basic Prompt:
    > Add a blog to my app.

* #### Specific Prompt:
    > Scaffold a complete blog feature for my **Next.js** and **Supabase** application. This must include:
    > 1.  A new `posts` table in the **Supabase database** with columns for `id`, `title`, `content`, and `created_at`.
    > 2.  A set of protected **Next.js API routes** to handle all CRUD operations for these posts.
    > 3.  A new page at `/dashboard/posts` that fetches and displays all posts in a table.
    > 4.  A form on that page to create a new post, plus buttons on each table row to edit or delete an existing post.

* #### Why It's Better:
    The specific prompt defines the **technologies** (Next.js, Supabase), the **database schema**, the **API requirements**, and the complete **frontend UI and functionality**. It describes the entire vertical slice of the feature.

* #### 🛠️ Tool Examples:
    `GitHub Copilot Workspace`, `Cursor`

---
### 🔐 User Authentication Flow

This involves creating the entire user identity system, from the UI forms on the frontend to the session management and protected routes on the backend.

* #### Basic Prompt:
    > Let users sign up.

* #### Specific Prompt:
    > Implement a complete authentication system using **Next.js** and **Clerk**. Create the following pages: `/sign-up`, `/sign-in`, and a protected `/dashboard` page. Use **Clerk's pre-built React components** for the UI forms. After a user signs in, their user ID must be available on both the client and server. The main navigation bar should conditionally display "Sign In" or a "Go to Dashboard" link based on the user's authentication state.

* #### Why It's Better:
    It names the **specific auth provider** (Clerk), lists all the **required pages**, specifies the **UI components** to use, and describes the desired **stateful changes** to the UI after a successful login.

* #### 🛠️ Tool Examples:
    `GitHub Copilot`, `Cursor`

---
### 🔗 Third-Party Service Integration

This covers features that require connecting to an external service (like a payment processor or email provider), which involves secure backend communication and a corresponding frontend interface.

* #### Basic Prompt:
    > Add Stripe payments.

* #### Specific Prompt:
    > Integrate **Stripe** payments into my **Next.js** application.
    > 1.  **Backend:** Create a new API route at `/api/checkout` that uses the `stripe` Node.js SDK to create a new Stripe Checkout Session. The Stripe secret key must be loaded securely from an **environment variable**.
    > 2.  **Frontend:** On the pricing page, create a "Purchase" button that, when clicked, makes a `POST` request to this `/api/checkout` endpoint. After getting a successful response, it must redirect the user to the Stripe Checkout URL.

* #### Why It's Better:
    It breaks the task into clear **backend** and **frontend** responsibilities. It specifies the **payment provider** (Stripe), the **exact API endpoint**, the **backend SDK**, the **frontend behavior**, and the **security best practice** (environment variables).

* #### 🛠️ Tool Examples:
    `GitHub Copilot`, `Cursor`

---
### ⚡ Real-Time Feature Implementation

This is for features that require instant updates without the user needing to refresh the page, such as a live chat application, notifications, or collaborative editing.

* #### Basic Prompt:
    > Make a real-time chat app.

* #### Specific Prompt:
    > Build a simple, real-time chat room using **Next.js** and **Supabase Realtime**.
    > 1.  **Database:** Create a `messages` table in Supabase with `id`, `text`, and `created_at` columns.
    > 2.  **Backend:** Enable Supabase's realtime functionality for the `messages` table.
    > 3.  **Frontend:** Create a React component that subscribes to all new inserts on the `messages` table using the Supabase client library. New messages must appear in the UI instantly. Include a form at the bottom for users to send new messages, which calls a function to insert them into the database.

* #### Why It's Better:
    It defines the **real-time technology** (Supabase Realtime), the **database schema**, the **frontend subscription logic**, and the **UI for sending messages**, describing the complete, bi-directional real-time loop.

* #### 🛠️ Tool Examples:
    `GitHub Copilot`, `Cursor`

---
### ✅ Summary Cheat Sheet

| Prompting For... | Key Details to Include in Your Prompt | Example Tools |
| :--- | :--- | :--- |
| **CRUD Feature** | Technologies (Next.js, Supabase), database schema, API route definitions, and the complete frontend UI/UX. | `GitHub Copilot Workspace`, `Cursor`|
| **Authentication** | Auth provider (Clerk, etc.), required pages, UI component library to use, post-login state changes. | `GitHub Copilot`, `Cursor` |
| **Third-Party Service** | The provider (Stripe, etc.), backend API endpoint logic, frontend trigger and behavior, security practices. | `GitHub Copilot`, `Cursor` |
| **Real-Time Feature**| Real-time technology (Supabase Realtime, etc.), database schema, frontend subscription logic, and UI for sending data. | `GitHub Copilot`, `Cursor` |



```markdown
# 🚀 Fullstack Prompts

This guide provides a reference for writing **fullstack prompts**: comprehensive instructions given to an AI assistant to generate an entire feature from end to end. Unlike prompts focused on a single layer, a fullstack prompt describes the complete "vertical slice" of a feature, connecting the **user interface**, the **API**, the **database**, and the **business logic** in a single, cohesive request.

Mastering fullstack prompts is the key to leveraging AI for maximum development velocity. A well-crafted prompt acts as a detailed architectural specification, enabling an AI to scaffold a complete, functional feature in a fraction of the time it would take to build manually.

---
### 1. Scaffolding a New CRUD Feature

This is the most common fullstack task: generating all the connected parts needed to Create, Read, Update, and Delete (CRUD) a new type of data in your application.

* #### Basic Prompt:
    > Add a blog to my site.

* #### Specific Prompt:
    > Scaffold a complete blog feature for my **Next.js** and **Supabase** application. This must include:
    > 1.  A new `posts` table in the **Supabase database** with columns for `id` (UUID), `title` (text), `content` (text), and `created_at` (timestamp).
    > 2.  A set of protected **Next.js API routes** to handle all CRUD operations for these posts.
    > 3.  A new page at `/dashboard/posts` that fetches and displays all posts in a table.
    > 4.  A form on that page to create a new post, plus buttons on each table row to edit or delete an existing post.

* #### Why It's Better:
    The specific prompt defines the **technologies** (Next.js, Supabase), the **database schema**, the **API requirements**, and the complete **frontend UI and functionality**, describing the entire vertical slice of the feature.

* #### 🛠️ Tool Examples:
    * **AI-Native Code Editors:** These are best for implementing the feature within an existing project.
        * **`Cursor`**: Can take the prompt and make the necessary edits across multiple files (schema, API routes, UI components).
        * **`GitHub Copilot Workspace`**: Designed to take such a prompt and generate the entire file structure and initial code for the new feature.
    * **Advanced AI Chat Assistants:** Can be used to generate the code for each step, which you then copy into your editor.
        * **`Claude 3` / `GPT-4o`**: Can produce all the necessary code blocks for the database schema, API routes, and React components when given the detailed prompt.
    * **Autonomous AI Software Engineers (Emerging):** These tools aim to take the prompt and execute the entire task independently.
        * **`Devin (by Cognition Labs)`**: Designed to interpret a high-level feature request and perform all the steps a human developer would.

---
### 2. Implementing User Authentication

This involves creating the entire user identity system, from the UI forms on the frontend to the session management and protected routes on the backend.

* #### Basic Prompt:
    > Let users sign up.

* #### Specific Prompt:
    > Implement a complete authentication system using **Next.js** and **Clerk**.
    > 1.  Create the following pages, protected by Clerk's middleware: `/sign-up`, `/sign-in`, and a user `/dashboard`.
    > 2.  Use **Clerk's pre-built React components** (`<SignUp />`, `<SignIn />`) for the UI forms.
    > 3.  After a user signs in, their `userId` must be available on both the client and server.
    > 4.  The main navigation bar should conditionally display a "Sign In" link or a "Dashboard" link based on the user's authentication state.

* #### Why It's Better:
    It names the **specific auth provider** (Clerk), lists all the **required pages**, specifies the exact **UI components** to use, and describes the desired **stateful changes** to the UI after a successful login.

* #### 🛠️ Tool Examples:
    * **AI-Native Code Editors (`Cursor`):** Excellent for integrating the provider's code snippets into your existing layout and components.
    * **Advanced AI Chat Assistants (`GitHub Copilot Chat`):** Can provide step-by-step guidance and code for setting up the provider's configuration files and middleware.

---
### 3. Integrating a Third-Party Service

This covers features that require connecting to an external API (like a payment processor), which involves secure backend communication and a corresponding frontend interface.

* #### Basic Prompt:
    > Add Stripe payments.

* #### Specific Prompt:
    > Integrate **Stripe** payments into my **Next.js** application to sell a single product.
    > 1.  **Backend:** Create a new API route at `/api/checkout` that uses the `stripe` Node.js SDK to create a new Stripe Checkout Session for a pre-defined price ID. The Stripe secret key must be loaded securely from an **environment variable**.
    > 2.  **Frontend:** On the pricing page, create a "Purchase" button. When clicked, it must make a `POST` request to the `/api/checkout` endpoint. Upon receiving the session URL, it must redirect the user to the Stripe Checkout page.

* #### Why It's Better:
    It breaks the task into clear **backend** and **frontend** responsibilities. It specifies the **payment provider** (Stripe), the **exact API endpoint**, the **backend SDK**, the **frontend behavior**, and the **security best practice** (environment variables).

* #### 🛠️ Tool Examples:
    * **AI-Native Code Editors (`Cursor`):** Can read your existing code and help you correctly implement the Stripe SDK on the backend and the `fetch` call on the frontend.
    * **Advanced AI Chat Assistants (`GitHub Copilot Chat`, `Claude 3`):** Excellent for generating the boilerplate code for both the Stripe API route and the frontend button handler.

---
### 4. Creating a Real-Time Feature

This is for features that require instant updates without the user refreshing the page, such as a live chat application, notifications, or collaborative editing.

* #### Basic Prompt:
    > Make a real-time chat app.

* #### Specific Prompt:
    > Build a simple real-time chat room using **Next.js** and **Supabase Realtime**.
    > 1.  **Database:** Create a `messages` table in Supabase with `id`, `text`, and `created_at` columns. Enable Row Level Security so users can only insert messages.
    > 2.  **Backend:** Enable Supabase's realtime functionality for the `messages` table via the dashboard.
    > 3.  **Frontend:** Create a React component that subscribes to all new inserts on the `messages` table using the Supabase client library. New messages must appear in the UI instantly. Include a form at the bottom for users to send new messages.

* #### Why It's Better:
    It defines the **real-time technology** (Supabase Realtime), the **database schema** with security considerations, the **frontend subscription logic**, and the **UI for sending messages**, describing the complete, bi-directional real-time loop.

* #### 🛠️ Tool Examples:
    * **AI-Native Code Editors (`Cursor`):** Can help implement the frontend subscription logic and the backend database interactions.
    * **Cloud IDEs (`Replit`):** A good environment for prototyping real-time features quickly.

---
### ✅ Summary Cheat Sheet

| Prompting For... | Key Details to Include in Your Prompt | Primary Tool Categories |
| :--- | :--- | :--- |
| **CRUD Feature** | Technologies (Next.js, Supabase), database schema, API route definitions, and the complete frontend UI/UX. | AI-Native Editors, Autonomous Agents |
| **Authentication** | Auth provider (Clerk, etc.), required pages, UI component library to use, post-login state changes. | AI-Native Editors, AI Chat Assistants |
| **Third-Party Service** | The provider (Stripe, etc.), backend API endpoint logic, frontend trigger and behavior, security practices. | AI-Native Editors, AI Chat Assistants |
| **Real-Time Feature**| Real-time technology (Supabase Realtime, etc.), database schema, frontend subscription logic, and UI for sending data. | AI-Native Editors, Cloud IDEs |
```