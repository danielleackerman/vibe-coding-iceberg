---
title: SaaS App Skeleton
nav_order: ""
description: A skeleton structure for building a SaaS application, demonstrating fullstack development with Vibe Coding tools and patterns.
tags:
  - use cases
  - SaaS
  - vibe coding
layout: default
---
```markdown
# 📝 Blueprint: SaaS Application Skeleton

This document provides a step-by-step blueprint for building the skeleton of a **SaaS (Software as a Service)** application. A SaaS app is more complex than a static site or blog; it requires user accounts, protected data, and often, a payment system.

This guide will walk through the ten core phases of building such an application, demonstrating how modern tools are connected to create a secure, data-driven product. Each step will include a concrete AI prompt to illustrate how AI assistants can accelerate the workflow.

---
### The Recipe: Our Chosen Tech Stack

For this blueprint, we will assemble a professional-grade set of tools designed for building robust, scalable applications.

* **Fullstack Builder:** **Next.js**
* **Authentication:** **Clerk**
* **Database:** **Supabase** (for PostgreSQL hosting)
* **ORM:** **Prisma** (for database access)
* **Styling:** **Tailwind CSS**
* **Payments:** **Stripe**
* **Infrastructure:** **Vercel**

---
### Step 1: Scaffolding the Project

**The Goal:** Create the initial file structure and project setup on your local machine.

**The Action:** We'll begin by using the Next.js command-line tool to generate a new, ready-to-code project, pre-configured with the essential technologies for our stack.

* #### 🤖 AI Prompt Example:
    > "Generate the `npx` command to scaffold a new **Next.js** application named `my-saas-app`. During the setup, ensure that it is configured to use **TypeScript** and **Tailwind CSS**."

---
### Step 2: Integrating Authentication

**The Goal:** Set up the user identity system so people can sign up, log in, and have their own accounts.

**The Action:** We will integrate a dedicated authentication platform. This is a critical first step in a SaaS app, as almost all data will be tied to a user account.

* #### 🤖 AI Prompt Example:
    > "I'm using **Clerk** for authentication in my Next.js app. Generate the code for my `middleware.ts` file. This middleware should **protect all routes by default**, except for the homepage (`/`), the sign-in page (`/sign-in`), and the sign-up page (`/sign-up`)."

---
### Step 3: Designing the Database Schema

**The Goal:** Define the structure of our application's data, ensuring that data is correctly associated with individual users.

**The Action:** We will use the Prisma schema language to define our data models. A core requirement for a SaaS app is linking every piece of data back to a user.

* #### 🤖 AI Prompt Example:
    > "Using **Prisma schema syntax**, define a `Project` model. It needs standard fields like `id` and `name`. Most importantly, it must have a required `userId` field (of type `String`) that will store the ID from our Clerk authentication system. Add an index to the `userId` column for performance."

---
### Step 4: Connecting the Database

**The Goal:** Configure our Next.js application to be able to securely communicate with our hosted database.

**The Action:** This involves setting up our `.env` file with the database connection string and initializing the Prisma Client, which is the tool our code will use to talk to the database.

* #### 🤖 AI Prompt Example:
    > "I am using a **Supabase** project for my PostgreSQL database. Show me the correct format for the `DATABASE_URL` environment variable in my `.env` file, using the standard Supabase connection string. Make sure it's configured for connection pooling with Prisma."

---
### Step 5: Creating Protected API Endpoints

**The Goal:** Build a secure backend API that only allows logged-in users to access their own data.

**The Action:** We'll create a Next.js API route that fetches data from the database. The crucial part is adding logic to check the user's identity before returning any data.

* #### 🤖 AI Prompt Example:
    > "Create a protected **Next.js API route** at `/api/projects`. The `GET` handler for this route must first use the `auth()` function from **Clerk** to get the current `userId`. If there is no user, return a 401 Unauthorized error. If there is a user, use **Prisma** to fetch and return only the projects from the database where the `userId` column matches the authenticated user's ID."

---
### Step 6: Building the Main Dashboard UI

**The Goal:** Design the primary layout that users will see after they log in.

**The Action:** We'll create a main dashboard component that serves as the shell for our application, including navigation and user-specific elements.

* #### 🤖 AI Prompt Example:
    > "Create a `DashboardLayout` React component. It should have a vertical sidebar on the left for navigation links (e.g., 'Projects', 'Settings') and a main content area on the right where the page content will be displayed. In the top-right corner of the header, include the `<UserButton />` component from **Clerk** to automatically show the current user's avatar and a sign-out link."

---
### Step 7: Implementing a Core Feature (UI)

**The Goal:** Build the user interface for one of the application's core features—in this case, creating a new "project."

**The Action:** We'll create a simple form component that allows users to input data.

* #### 🤖 AI Prompt Example:
    > "Create a new React component named `CreateProjectForm`. It must contain a single text `input` field for the project's 'name' and a 'Submit' button. Use the `useState` hook to manage the form's input state."

---
### Step 8: Connecting the UI to the API

**The Goal:** Make the UI functional by wiring it up to our backend API so that user actions are saved to the database.

**The Action:** We will add a function to our form component that, upon submission, sends the user's data to the protected API endpoint we created in Step 5.

* #### 🤖 AI Prompt Example:
    > "In the `CreateProjectForm` component, create a `handleSubmit` function. When the form is submitted, it should make a `POST` request to our `/api/projects` endpoint, sending the new project's name in the request body. After a successful submission, it should automatically clear the form input and refresh the list of projects."

---
### Step 9: Integrating Payments for Subscriptions

**The Goal:** Add the ability for users to pay for a subscription using a third-party payment provider.

**The Action:** We will create a backend endpoint that uses the Stripe SDK to create a secure checkout session for the user.

* #### 🤖 AI Prompt Example:
    > "Create a **Next.js API route** at `/api/billing/checkout`. This route must use the **Stripe Node.js SDK** to create a new Checkout Session for a subscription product. The `client_reference_id` in the Stripe session must be set to the authenticated user's ID from **Clerk**. The function should return the checkout session URL."

---
### Step 10: Deployment & Secrets Management

**The Goal:** Deploy the application to the internet and ensure all our secret keys are configured securely for the production environment.

**The Action:** We'll prepare our project for deployment on Vercel, which involves identifying all the necessary environment variables that the live application will need.

* #### 🤖 AI Prompt Example:
    > "List all the necessary environment variables my Next.js SaaS application needs for a **Vercel** production deployment. The list must include all public and secret keys for **Clerk**, the full `DATABASE_URL` for my **Supabase/Prisma** connection, and the `STRIPE_SECRET_KEY` for payments."

---
### 🏁 Blueprint Summary

| Step | Phase | Primary Goal | Key Tools & Concepts Involved |
| :--- | :--- | :--- | :--- |
| 1 | **Scaffolding** | Create the initial project structure. | Next.js CLI, TypeScript, Tailwind CSS |
| 2 | **Authentication** | Set up the user identity system. | Clerk, Middleware, Protected Routes |
| 3 | **Data Design** | Define the database schema. | Prisma, SQL, Foreign Key Relationships |
| 4 | **DB Connection** | Configure the app to access the database. | Environment Variables (.env), Supabase |
| 5 | **API Creation** | Build secure backend endpoints. | API Routes, Authorization, ORM Queries |
| 6 | **UI Layout** | Design the main authenticated layout. | React Components, UI Libraries |
| 7 | **Feature UI** | Build the UI for a core feature. | Forms, Frontend State Management (`useState`) |
| 8 | **Fullstack Wire-up**| Connect the UI to the backend API. | `fetch` / `POST` requests, API consumption |
| 9 | **Monetization** | Integrate a payment provider. | Stripe SDK, Third-Party Service Integration |
| 10 | **Deployment** | Go live and manage production secrets. | Vercel, Environment Configuration, CI/CD |
```