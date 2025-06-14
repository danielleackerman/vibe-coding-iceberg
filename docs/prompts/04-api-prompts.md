---
title: API Prompts
nav_order: ""
description: Prompt examples and patterns for backend/API development using tools like Express, Django, and GraphQL.
tags:
  - backend
  - api
  - prompts
layout: default
---
```markdown
# 🔌 API Prompts

This guide provides a cheat sheet for writing effective prompts for building the **API (Application Programming Interface)**. The API is the critical "contract" that defines how your frontend and backend communicate. It's the menu of operations that the server offers to the client.

Effective API prompting is about being explicit with the structure of your endpoints, the shape of your data, the rules of interaction, and how to handle errors. A precise prompt leads to a well-structured, secure, and easy-to-use API.

---
### 🏗️ 1. REST API Scaffolding

This is about generating the complete set of standard endpoints for a single "resource" (like users, products, or posts) following the REST architectural style.

* #### Basic Prompt:
    > Make an API for products.

* #### Specific Prompt:
    > Using **Express.js** and **Prisma**, generate a complete set of RESTful CRUD endpoints for a 'product' resource. Create the following routes: `GET /api/products`, `GET /api/products/:id`, `POST /api/products`, `PUT /api/products/:id`, and `DELETE /api/products/:id`. The routes should be organized using an **Express Router**.

* #### Why It's Better:
    The specific prompt dictates the **framework** (Express), the **data access tool** (Prisma), the **architectural style** (RESTful), and the **exact five routes** required for standard Create, Read, Update, Delete (CRUD) operations.

* #### 🛠️ Tool Examples:
    `GitHub Copilot`, `Cursor`

---
### 📝 2. Defining Data Shapes & Validation

This is about being precise with the JSON data structure your API expects to receive in a request and what it sends back in a response.

* #### Basic Prompt:
    > Check the user's input.

* #### Specific Prompt:
    > In this `POST /api/products` Express route, use the **'zod'** library to validate the incoming request body. The body must be an object containing a `'name'` (string, minimum 3 characters), a `'price'` (positive number), and an optional `'description'` (string). If validation fails, the API must immediately respond with a **400 Bad Request** status code and a JSON object detailing the validation errors.

* #### Why It's Better:
    It specifies the **validation library** (`zod`), the **exact data schema** with types and constraints, and the **specific error handling behavior** (a 400 status with error details), which is crucial for a robust API.

* #### 🛠️ Tool Examples:
    `GitHub Copilot`, `Cursor`

---
### 🧠 3. Implementing Specific Endpoint Logic

This focuses on the detailed business logic inside a single API endpoint, which often involves multiple steps and conditional paths.

* #### Basic Prompt:
    > Handle a new order.

* #### Specific Prompt:
    > In this `POST /api/orders` route, implement the following logic:
    > 1.  Validate the incoming request body, which must contain `'productId'` and `'quantity'`.
    > 2.  In the database, check the current stock for the given `'productId'`.
    > 3.  **If stock is insufficient**, respond with a **409 Conflict** error and the message "Not enough stock available."
    > 4.  **If stock is sufficient**, decrease the product's stock count and create a new `'order'` record in the database.
    > 5.  Respond with a **201 Created** status code and the newly created order object.

* #### Why It's Better:
    The specific prompt provides a **step-by-step algorithm** for the business logic, including the **database checks**, the **specific error conditions** (409 Conflict), and the **correct success status code** (201 Created).

* #### 🛠️ Tool Examples:
    `Cursor`, `GitHub Copilot`

---
### 🕸️ 4. GraphQL API Scaffolding

This covers prompting for a different API architecture, GraphQL, which uses a single endpoint and a strongly-typed query language.

* #### Basic Prompt:
    > Make a GraphQL API for posts.

* #### Specific Prompt:
    > Using **Apollo Server** and **Prisma**, set up a basic GraphQL API.
    > - Define a `Post` **type** with `id`, `title`, and `content` fields.
    > - Create a **query** named `allPosts` that returns an array of all posts.
    > - Create another **query** named `postById` that accepts an `id` argument and returns a single post.
    > - Create a **mutation** named `createPost` that accepts `title` and `content` as arguments and creates a new post in the database.

* #### Why It's Better:
    It specifies the **technology** (Apollo Server), the **data types**, and the exact **queries** (for reading data) and **mutations** (for writing data), which are the fundamental building blocks of any GraphQL schema.

* #### 🛠️ Tool Examples:
    `GitHub Copilot`, `Cursor`

---
### 🚨 5. API Error Handling & Status Codes

This is about creating a consistent, predictable, and secure way for your API to communicate problems to the client.

* #### Basic Prompt:
    > Handle API errors.

* #### Specific Prompt:
    > Create a **centralized error handling middleware** for this Express.js application. It should catch all errors passed to `next()`.
    > - If the error is a specific, known custom error (e.g., `NotFoundError`), it should respond with the appropriate status code (e.g., 404).
    > - For all other unexpected, generic errors, it must log the full error details to the console for debugging but respond to the client with a generic **500 Internal Server Error** message to avoid leaking sensitive implementation details.

* #### Why It's Better:
    It describes a robust **architectural pattern** (centralized middleware) and defines the logic for handling **both known and unknown errors** with correct and secure responses.

* #### 🛠️ Tool Examples:
    `GitHub Copilot`, `Cursor`

---
### ✅ Summary Cheat Sheet

| Prompting For... | Key Details to Include in Your Prompt | Example Tools |
| :--- | :--- | :--- |
| **REST Scaffolding** | Framework (Express, etc.), data tool (Prisma), architectural style (RESTful), specific CRUD routes. | `GitHub Copilot`, `Cursor` |
| **Data Validation** | Validation library (Zod, etc.), exact data schema (types, constraints), and error response behavior (e.g., 400). | `GitHub Copilot`, `Cursor` |
| **Endpoint Logic** | A step-by-step algorithm of actions, including database checks, conditional logic, and specific error cases. | `GitHub Copilot`, `Cursor` |
| **GraphQL Scaffolding**| Technology (Apollo Server, etc.), data types, and the exact names and arguments for queries and mutations. | `GitHub Copilot`, `Cursor` |
| **Error Handling** | The architectural pattern (e.g., middleware), logic for known vs. unknown errors, and correct HTTP status codes. | `GitHub Copilot`, `Cursor` |
```