---
title: Environment Configuration
nav_order: ""
description: How to configure development, staging, and production environments for Vibe Coding projects.
tags:
  - environment
  - configuration
  - vibe coding
layout: default
---
````markdown
# 🌱 Environment Configuration

If you're building a creative tool, website, or app—even just experimenting—you’ll soon face this moment:

> “Why does this work on my computer, but break when I share it or put it online?”

That’s where **environment configuration** comes in.

You may not know the term yet, but it’s the foundation that lets your project **work in different places without falling apart**—on your laptop, in a test space, or out in the world with real users.

Think of it like packing for a trip.  
You bring different clothes for:
- your home (sweats)
- a rehearsal (studio gear)
- a public performance (stage outfit)

Your app also needs to “dress” differently for different **environments**. You do that by configuring what it *knows*, *connects to*, and *shows* based on **where** it’s running.

---

## 💡 What’s an “Environment”?

An **environment** is the situation your app is running in. It's everything around your code—settings, secrets, tools, and permissions.

| Environment     | What It's For                             | Real-Life Analogy            |
|------------------|--------------------------------------------|-------------------------------|
| **Development**  | Just for you. You’re building & testing.   | Studio or home practice       |
| **Staging**      | A safe way to preview before going live    | Dress rehearsal               |
| **Production**   | Public-facing. Users are here.             | Opening night performance     |

Each space has its own rules, safety gear, and lighting. Environment config sets those up.

---

## 🛠️ What Gets Configured?

When you move between these environments, you need to change:
- **Secrets** like passwords or API keys  
- **URLs** to connect to the right database or service  
- **Feature flags** that turn things on/off for testing  
- **Logging or debug tools** so you can troubleshoot without showing private info to users

Rather than editing your code each time (which is risky), you’ll set up **a flexible config system** that adjusts automatically.

---

## 📁 Meet the `.env` File

The `.env` file is where you **store settings outside of your code**—things that might change depending on where the app runs.

```dotenv
# .env (used in development)
SUPABASE_URL=http://localhost:54321
SUPABASE_KEY=dev-secret-key
````

```dotenv
# .env.production (used in live deploy)
SUPABASE_URL=https://mysite.supabase.co
SUPABASE_KEY=live-secret-key
```

You never upload these to GitHub. Instead, they stay local or get set securely on platforms like **Vercel** or **Netlify**.

---

## 🔁 How It Works in Real Projects

Let’s say you’re building a **web app** with user accounts and some AI tools.

| Layer             | Without Config                      | With Environment Config                                 |
| ----------------- | ----------------------------------- | ------------------------------------------------------- |
| 🖥️ Frontend      | Always connects to live server      | Connects to local server in dev, live one in prod       |
| 🧠 AI Integration | Uses real OpenAI keys in every mode | Uses free/test key in dev, full-power key in production |
| 🔐 Auth / Login   | Breaks in local testing             | Uses fake accounts or sandbox mode locally              |
| 💾 Database       | Accidentally deletes real data      | Works on a local copy during testing                    |
| 🚀 Deployment     | Manually updated or breaks often    | Automatically loads the right settings per environment  |

The *same code* runs differently depending on where it lives.
That’s the power of environment configuration.

---

## 🔗 Why It Matters for Vibe Coding

Environment config is the *glue* that holds your creative systems together.

| Connected Layer                | What It Gains with Environment Config                           |
| ------------------------------ | --------------------------------------------------------------- |
| **Piano / Songwriting Matrix** | Can load a different database or API in dev vs prod             |
| **Auth Systems**               | Lets you test logins without exposing real users                |
| **AI Assistance**              | Prevents cost spikes by using sandboxed API keys in development |
| **Deployment Flow**            | Makes CI/CD safe and reliable across platforms                  |
| **Frontend Debugging**         | Enables verbose logs locally, clean output for real users       |

Without this layer, every experiment risks breaking the live site—or worse, leaking something sensitive.

---

## 🧠 Smart Defaults to Start With

You don’t need to know everything. Just follow these best practices:

| Goal                       | What to Do                                                             |
| -------------------------- | ---------------------------------------------------------------------- |
| Keep secrets safe          | Put them in a `.env.local` file (never commit to Git)                  |
| Switch behavior by context | Use `process.env.NODE_ENV` to check where your app is running          |
| Preview before going live  | Use platforms like Vercel with a separate “Preview” environment        |
| Separate data sources      | Use different URLs or keys per environment (`.env`, `.env.prod`, etc.) |

Example:

```js
const API_URL = process.env.NODE_ENV === "production"
  ? "https://api.mysite.com"
  : "http://localhost:3000";
```

---

## 💬 AI Prompt Examples

Let AI help set this up with natural-language prompts:

* “Create a `.env` file for a web app using Supabase, OpenAI, and Stripe with safe defaults.”
* “How can I check what environment I’m in and load different values?”
* “Write a Vite config file that uses different `.env` files for dev and prod.”
* “Generate a basic `.env` template for an app with login, database, and email services.”

➡️ [More prompt examples →](../prompts/07-env-config-prompts.md)

---

## 🧬 Summary

You don’t need to be an expert to set this up.

Start simple:

* Use `.env` files to separate private info from your code
* Let platforms like **Vercel**, **Netlify**, or **Railway** manage secrets for you
* Set your app up to **detect where it’s running** and behave accordingly

This gives you:

* Confidence to share your code
* Freedom to test safely
* A clear path to going live

**Environment configuration is your backstage crew.**
Invisible when done right—essential when things go wrong.

```

---
Crystal clear now: ✅ **Just the Markdown section** — no extra commentary, no alternation, no prose outside the code block.

Here you go:

````markdown
# 🌱 Environment Configuration

If you're building a creative tool, website, or app—even just experimenting—you’ll soon face this moment:

> “Why does this work on my computer, but break when I share it or put it online?”

That’s where **environment configuration** comes in.

You may not know the term yet, but it’s the foundation that lets your project **work in different places without falling apart**—on your laptop, in a test space, or out in the world with real users.

Think of it like packing for a trip.  
You bring different clothes for:
- your home (sweats)
- a rehearsal (studio gear)
- a public performance (stage outfit)

Your app also needs to “dress” differently for different **environments**. You do that by configuring what it *knows*, *connects to*, and *shows* based on **where** it’s running.

---

## 💡 What’s an “Environment”?

An **environment** is the situation your app is running in. It's everything around your code—settings, secrets, tools, and permissions.

| Environment     | What It's For                             | Real-Life Analogy            |
|------------------|--------------------------------------------|-------------------------------|
| **Development**  | Just for you. You’re building & testing.   | Studio or home practice       |
| **Staging**      | A safe way to preview before going live    | Dress rehearsal               |
| **Production**   | Public-facing. Users are here.             | Opening night performance     |

Each space has its own rules, safety gear, and lighting. Environment config sets those up.

---

## 🛠️ What Gets Configured?

When you move between these environments, you need to change:
- **Secrets** like passwords or API keys  
- **URLs** to connect to the right database or service  
- **Feature flags** that turn things on/off for testing  
- **Logging or debug tools** so you can troubleshoot without showing private info to users

Rather than editing your code each time (which is risky), you’ll set up **a flexible config system** that adjusts automatically.

---

## 📁 Meet the `.env` File

The `.env` file is where you **store settings outside of your code**—things that might change depending on where the app runs.

```dotenv
# .env (used in development)
SUPABASE_URL=http://localhost:54321
SUPABASE_KEY=dev-secret-key
````

```dotenv
# .env.production (used in live deploy)
SUPABASE_URL=https://mysite.supabase.co
SUPABASE_KEY=live-secret-key
```

You never upload these to GitHub. Instead, they stay local or get set securely on platforms like **Vercel** or **Netlify**.

---

## 🔁 How It Works in Real Projects

Let’s say you’re building a **web app** with user accounts and some AI tools.

| Layer             | Without Config                      | With Environment Config                                 |
| ----------------- | ----------------------------------- | ------------------------------------------------------- |
| 🖥️ Frontend      | Always connects to live server      | Connects to local server in dev, live one in prod       |
| 🧠 AI Integration | Uses real OpenAI keys in every mode | Uses free/test key in dev, full-power key in production |
| 🔐 Auth / Login   | Breaks in local testing             | Uses fake accounts or sandbox mode locally              |
| 💾 Database       | Accidentally deletes real data      | Works on a local copy during testing                    |
| 🚀 Deployment     | Manually updated or breaks often    | Automatically loads the right settings per environment  |

The *same code* runs differently depending on where it lives.
That’s the power of environment configuration.

---

## 🔗 Why It Matters for Vibe Coding

Environment config is the *glue* that holds your creative systems together.

| Connected Layer                | What It Gains with Environment Config                           |
| ------------------------------ | --------------------------------------------------------------- |
| **Piano / Songwriting Matrix** | Can load a different database or API in dev vs prod             |
| **Auth Systems**               | Lets you test logins without exposing real users                |
| **AI Assistance**              | Prevents cost spikes by using sandboxed API keys in development |
| **Deployment Flow**            | Makes CI/CD safe and reliable across platforms                  |
| **Frontend Debugging**         | Enables verbose logs locally, clean output for real users       |

Without this layer, every experiment risks breaking the live site—or worse, leaking something sensitive.

---

## 🧠 Smart Defaults to Start With

You don’t need to know everything. Just follow these best practices:

| Goal                       | What to Do                                                             |
| -------------------------- | ---------------------------------------------------------------------- |
| Keep secrets safe          | Put them in a `.env.local` file (never commit to Git)                  |
| Switch behavior by context | Use `process.env.NODE_ENV` to check where your app is running          |
| Preview before going live  | Use platforms like Vercel with a separate “Preview” environment        |
| Separate data sources      | Use different URLs or keys per environment (`.env`, `.env.prod`, etc.) |

Example:

```js
const API_URL = process.env.NODE_ENV === "production"
  ? "https://api.mysite.com"
  : "http://localhost:3000";
```

---

## 💬 AI Prompt Examples

Let AI help set this up with natural-language prompts:

* “Create a `.env` file for a web app using Supabase, OpenAI, and Stripe with safe defaults.”
* “How can I check what environment I’m in and load different values?”
* “Write a Vite config file that uses different `.env` files for dev and prod.”
* “Generate a basic `.env` template for an app with login, database, and email services.”

➡️ [More prompt examples →](../prompts/07-env-config-prompts.md)

---

## 🧬 Summary

You don’t need to be an expert to set this up.

Start simple:

* Use `.env` files to separate private info from your code
* Let platforms like **Vercel**, **Netlify**, or **Railway** manage secrets for you
* Set your app up to **detect where it’s running** and behave accordingly

This gives you:

* Confidence to share your code
* Freedom to test safely
* A clear path to going live

**Environment configuration is your backstage crew.**
Invisible when done right—essential when things go wrong.

```
```

```
