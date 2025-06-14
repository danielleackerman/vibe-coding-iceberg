---
title: Authentication Prompts
nav_order: ""
description: Prompt examples and patterns for implementing authentication and authorization in web applications.
tags:
  - auth
  - prompts
  - vibe coding
layout: default
---
```markdown
# 🔐 Authentication & Authorization Prompts

This guide provides a cheat sheet for writing prompts to implement **Authentication** (verifying who a user is) and **Authorization** (defining what they are allowed to do). This is one of the most security-sensitive parts of any application, and prompting for it requires precision regarding the specific methods, providers, and security rules you want to enforce.

A well-crafted prompt for this layer ensures you build a secure and user-friendly identity system, specifying not just the login form, but the entire end-to-end flow from sign-up to session management and permissions.

---
### 1. User Signup & Login UI

This is about generating the user-facing forms and components that allow a user to create an account and sign in.

* #### Basic Prompt:
    > Make a login page.

* #### Specific Prompt:
    > In my **Next.js** application, use the pre-built **Clerk** React component `<SignUp />` to create the user interface for a sign-up page at the `/sign-up` route. Configure it to allow sign-ups via **email/password**, **Google**, and **GitHub** social logins. The component should redirect to `/dashboard` after a successful signup.

* #### Why It's Better:
    It specifies the **technology** (Next.js), the **specific UI component library** to use (Clerk), the **exact authentication methods** (password, Google, GitHub), and the **post-action behavior** (redirect). This avoids ambiguity and leverages a specialized tool for its intended purpose.

* #### 🛠️ Tool Examples:
    * **Pre-built UI Components:** `Clerk`, `Stytch`, `Supabase Auth UI`
    * **Generative UI Tools:** `v0.dev` (for custom form design)
    * **AI Assistants:** `GitHub Copilot` (for integrating the components)

---
### 2. Session Management & JWTs

This covers the backend logic for what happens after a user logs in: creating a "session" to keep them logged in and managing the secure tokens that represent that session.

* #### Basic Prompt:
    > Keep the user logged in.

* #### Specific Prompt:
    > Create a **Next.js API route** that handles a `POST` request from a login form. After validating the user's password, use the **`jose`** library to create a secure **JWT**. The JWT payload must contain the `userId` and `role`. The token should be signed with a secret key read from an **environment variable** (`JWT_SECRET`) and have an **expiration time of 24 hours**. Set this JWT in a secure, httpOnly cookie.

* #### Why It's Better:
    The specific prompt dictates the **session strategy** (JWT), the **specific library** for token handling (`jose`), the **exact token payload**, the **security best practices** (environment variable secret), and the **token's lifecycle** (expiration time).

* #### 🛠️ Tool Examples:
    * **AI Assistants:** `GitHub Copilot`, `Cursor`
    * **Specialized Libraries:** `jose`, `jsonwebtoken`
    * **All-in-One Platforms:** `Auth0`, `Clerk`, `Supabase` (which handle this automatically)

---
### 3. Social Logins (OAuth)

This is about integrating third-party login providers like Google, GitHub, or Twitter, which uses a standard called OAuth.

* #### Basic Prompt:
    > Add Google login.

* #### Specific Prompt:
    > Configure **Auth.js (formerly NextAuth.js)** in my **Next.js** application to add Google as an OAuth provider. Use the official `GoogleProvider`. The necessary `GOOGLE_CLIENT_ID` and `GOOGLE_CLIENT_SECRET` must be loaded from **environment variables**. After a successful login, the user's name, email, and profile image from their Google account should be stored in my `User` table using the Prisma adapter.

* #### Why It's Better:
    It specifies the **exact authentication library** (Auth.js), the **provider** (Google), the **security requirement** for keys, and the **data flow logic** (storing Google profile info in the local database via the Prisma adapter).

* #### 🛠️ Tool Examples:
    * **Auth Libraries:** `Auth.js (NextAuth.js)`
    * **All-in-One Platforms:** `Clerk`, `Auth0`, `Firebase Auth`, `Supabase Auth`
    * **AI Assistants:** `GitHub Copilot`, `Cursor` (for help with configuration)

---
### 4. Authorization & Permissions (Roles)

This is the logic that runs *after* a user is authenticated. It determines what a specific user is allowed to see or do based on their role or ownership of a resource.

* #### Basic Prompt:
    > Only admins should see this page.

* #### Specific Prompt:
    > Implement authorization logic using the **Oso** library. Define a policy in Polar syntax that specifies two roles: `'user'` and `'admin'`. Write a rule that only allows users with the `'admin'` role to access any API route beginning with `/api/admin/`. In the API middleware, check the current user's role against the Oso policy before allowing the request to proceed.

* #### Why It's Better:
    It defines a specific, powerful **authorization framework** (Oso), describes the **permission model** (roles), and specifies the **exact rule** to be enforced and **where to enforce it** (in the API middleware). This creates a robust and scalable permissions system.

* #### 🛠️ Tool Examples:
    * **Authorization Engines:** `Oso`, `Cerbos`, `Permit.io`
    * **AI Assistants:** `GitHub Copilot`, `Cursor` (for writing policy files and integration code)

    ### 5. Passwordless Login (Magic Links)

This covers a popular and user-friendly authentication method that doesn't require users to create or remember a password. The user provides their email, and they receive a single-use link to log in.

* #### Basic Prompt:
    > Let users log in with email links.

* #### Specific Prompt:
    > Implement a **magic link** login flow using **Supabase Auth**.
    > 1.  On the frontend, create a form with a single email input field.
    > 2.  When a user submits their email, call the `signInWithOtp` function from the Supabase client library, specifying `email_redirect_to` to our dashboard page.
    > 3.  Supabase will automatically send an email containing a secure, single-use login link.
    > 4.  When the user clicks this link, they must be redirected back to the `/dashboard` page and be fully authenticated.

* #### Why It's Better:
    It specifies the **exact provider and function** (`Supabase`, `signInWithOtp`), the complete **user flow** (form -> email -> click -> redirect), and the desired outcome (an authenticated session on the dashboard), providing a full end-to-end specification.

* #### 🛠️ Tool Examples:
    * **All-in-One Platforms:** `Supabase Auth`, `Stytch` (specializes in passwordless), `Auth0`, `Clerk`
    * **AI Assistants:** `GitHub Copilot` (for implementing the client-side form and function call)

---
### 6. Multi-Factor Authentication (2FA/MFA)

This is about adding a second layer of security to the login process, typically requiring a time-based one-time password (TOTP) from an authenticator app like Google Authenticator or Authy.

* #### Basic Prompt:
    > Add 2FA to my app.

* #### Specific Prompt:
    > For a user who is already logged in, implement a flow to **enable TOTP-based 2FA** using the `speakeasy` Node.js library.
    > 1.  Generate a new 2FA secret and a corresponding **QR code** for the user to scan with their authenticator app.
    > 2.  Securely save the user's encrypted 2FA secret to their record in the `User` table.
    > 3.  On subsequent logins, after the user provides their correct password, they must be redirected to a dedicated page where they must enter the current 6-digit code from their app to complete the login process.

* #### Why It's Better:
    This prompt defines the **timing** of the flow (for an already-logged-in user), a **specific library** (`speakeasy`), the standard **user setup mechanism** (QR code), the **database requirement**, and the complete, two-step **login verification flow**.

* #### 🛠️ Tool Examples:
    * **All-in-One Platforms:** `Clerk` and `Auth0` (provide this as a built-in, configurable feature)
    * **Specialized Libraries:** `speakeasy`, `2fa-node` (for DIY implementations)
    * **AI Assistants:** `Cursor`, `GitHub Copilot` (for implementing the multi-step logic)

---
### 7. Programmatic API Key Authentication

This is for securing API endpoints that will be accessed by other machines, scripts, or third-party services, not by a human user logged into a web interface.

* #### Basic Prompt:
    > Secure my API for other programs.

* #### Specific Prompt:
    > Implement an **API key authentication scheme** for my **Express.js** API to protect routes under `/api/v1/`.
    > 1.  Create a `ApiKeys` table in the database that stores **securely hashed** API keys associated with a `userId`.
    > 2.  Create a custom **Express middleware** that checks for an `Authorization: Bearer <API_KEY>` header on all incoming requests.
    > 3.  The middleware must look up the provided key in the database (comparing against the hashed versions).
    > 4.  If the key is valid, allow the request to proceed. If it is invalid, malformed, or missing, respond immediately with a **401 Unauthorized** error and a JSON message.

* #### Why It's Better:
    It describes a specific, standard **authentication scheme** (`Bearer` token), the **database schema** and **security best practice** (hashing keys), the **architectural pattern** (custom middleware), and the **exact error handling** (401 status code).

* #### 🛠️ Tool Examples:
    * **API Gateways:** `Amazon API Gateway`, `Cloudflare API Shield` (can manage API keys at the infrastructure level)
    * **AI Assistants:** `Cursor`, `GitHub Copilot` (excellent for generating the custom middleware and database logic for this common pattern)

---
### ✅ Summary Cheat Sheet

| Prompting For... | Key Details to Include in Your Prompt | Specialized Tool Examples |
| :--- | :--- | :--- |
| **Signup/Login UI** | The auth provider (Clerk, etc.), specific login methods (Google, password), and post-login behavior (redirects). | `Clerk`, `Stytch`, `v0.dev` |
| **Session Management** | The strategy (JWT, etc.), specific library (`jose`), token payload, expiration, and security practices (httpOnly cookies). | `jose`, `Auth.js`, `Supabase` |
| **Social Logins** | The auth library (Auth.js), the OAuth provider (Google, GitHub), and the logic for handling user profile data post-login. | `Auth.js`, `Auth0`, `Clerk` |
| **Authorization** | The framework (Oso, etc.), the permission model (roles, attributes), and the specific access rules to enforce. | `Oso`, `Cerbos`, `Permit.io` |
```