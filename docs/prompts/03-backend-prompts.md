---
title: Backend Prompts
nav_order: ""
description: Prompts focused on backend development tasks, including database interactions, API creation, authentication, and server setup.
tags:
  - backend
  - prompts
  - vibe coding
layout: default
---
```markdown
# ⚙️ Backend Prompts

This guide is a cheat sheet for writing effective prompts to build the **backend** of your application. The backend is the engine room—it handles your application's data, business logic, and security. Prompting for backend tasks requires being explicit about data structures, business rules, and the desired behavior of your APIs.

A clear backend prompt gives the AI a precise architectural and logical specification, resulting in code that is secure, efficient, and reliable.

---
### 💾 1. Database Schema & Migrations

This is about defining the "nouns" of your application—the tables, columns, and relationships that structure your data.

* #### Basic Prompt:
    > Make a posts table.

* #### Specific Prompt:
    > Using **Prisma schema syntax**, define a `Post` model. It must have the following fields: `id` (autoincrementing Integer), `title` (String), `content` (String, optional), `published` (Boolean, with a default value of `false`), and `createdAt` (DateTime, defaulting to `now()`). Crucially, add a **many-to-one relationship** to a `User` model, linking them via an `authorId` foreign key.

* #### Why It's Better:
    The specific prompt defines the **technology** (Prisma), the **exact fields**, their **data types**, their **constraints** (optional, default values), and, most importantly, the critical **relationship** to another data model.

* #### 🛠️ Tool Examples:
    `Cursor`, `GitHub Copilot` (for writing Prisma/Drizzle schema files).

---
### 🔌 2. API Endpoint Creation (CRUD)

This is about creating the API "verbs"—the specific URLs your frontend will call to Create, Read, Update, and Delete (CRUD) data.

* #### Basic Prompt:
    > API to get posts.

* #### Specific Prompt:
    > Create a **Next.js API route** at `/api/posts/[id]` that handles a `GET` request to fetch a single post. Use **Prisma** to find the post in the database by its `id`. If the post is not found, return a **404 error**. If found, return the post data as JSON. This endpoint should be public and not require authentication.

* #### Why It's Better:
    The specific prompt defines the **framework and routing pattern** (Next.js), the **HTTP method** (GET), the **success case** (return post), the **error handling** (return 404), and the **security policy** (public).

* #### 🛠️ Tool Examples:
    `Cursor`, `GitHub Copilot`.

---
### 🔐 3. Authentication & Authorization

This is about managing user identity (who someone is) and permissions (what they are allowed to do).

* #### Basic Prompt:
    > Add user login.

* #### Specific Prompt:
    > Integrate **Supabase Auth** to allow users to sign up and log in with an email and password. After a successful login, securely create a **JWT** and store it in an httpOnly cookie. Also, create a protected API endpoint that can only be accessed by authenticated users.

* #### Why It's Better:
    It names the **specific auth provider** (Supabase), the **login method**, the **session management strategy** (JWT in a secure cookie), and the **authorization requirement** (a protected endpoint), providing a complete recipe for a secure system.

* #### 🛠️ Tool Examples:
    `GitHub Copilot`, `Cursor`.

---
### 🧠 4. Business Logic & Serverless Functions

This covers custom server-side logic that goes beyond simple data fetching, such as processing a payment, sending a notification, or running a scheduled job.

* #### Basic Prompt:
    > Process a new user signup.

* #### Specific Prompt:
    > Create a **serverless function** that is triggered whenever a new user is added to the **Supabase Auth** system. The function should take the new user's `email` and `id`, and use the official **Stripe Node.js SDK** to create a new Stripe customer. Store the returned `stripe_customer_id` in our `User` table in the database, associating it with the new user.

* #### Why It's Better:
    The specific prompt defines the **trigger event** (new user), the **services to connect** (Supabase and Stripe), the **exact sequence of actions**, and the **data to be stored**, outlining a complete business process.

* #### 🛠️ Tool Examples:
    `GitHub Copilot`, `Cursor` (within Vercel, Netlify, or Supabase Functions).

---
### 🔗 5. Connecting to External, Third-Party APIs

This is about making your backend talk to other services on the internet to pull in external data or functionality.

* #### Basic Prompt:
    > Get stock price data.

* #### Specific Prompt:
    > Create a backend function that accepts a stock `ticker` symbol. Inside the function, make a `GET` request to the **Financial Modeling Prep API** to get the latest stock quote. Use the `axios` library for the request. The API key must be read securely from an **environment variable**, not hardcoded. From the full API response, extract and return only the `symbol` and `price` as a clean JSON object.

* #### Why It's Better:
    It specifies the **third-party API provider**, the **HTTP library** to use (`axios`), the **security best practice** (environment variables), and the **data transformation logic** (extracting specific fields), resulting in a clean and secure function.

* #### 🛠️ Tool Examples:
    `GitHub Copilot`, `Cursor`.

---
### ✅ Summary Cheat Sheet

| Prompting For... | Key Details to Include in Your Prompt | Example Tools |
| :--- | :--- | :--- |
| **Database Schema** | Technology (Prisma, etc.), model names, field names, data types, constraints (unique, default), and relationships. | `GitHub Copilot`, `Cursor` |
| **API Endpoints** | Framework (Next.js, etc.), route path, HTTP method (GET, POST), success case, error handling, security policy. | `GitHub Copilot`, `Cursor` |
| **Authentication** | Auth provider (Supabase, Clerk), login methods (password, social), session strategy (JWT, cookies), access rules. | `GitHub Copilot`, `Cursor` |
| **Business Logic** | The trigger event, the sequence of actions, the specific SDKs or libraries to use, and data handling. | `GitHub Copilot`, `Cursor` |
| **External APIs** | The third-party provider, the specific endpoint, the request library (axios, fetch), security, and data transformation. | `GitHub Copilot`, `Cursor` |
```


# Backend Prompt Cheat Sheet

## Example Prompt
> Add Supabase Auth with email/password login and magic link.
