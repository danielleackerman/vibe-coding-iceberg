---
title: Database Prompts
nav_order: ""
description: Prompt examples and patterns for working with databases, including queries, schema design, and data management.
tags:
  - database
  - prompts
  - vibe coding
layout: default
---
```markdown
# 🗃️ Database Prompts

This guide is a cheat sheet for writing effective prompts related to the **database**—the persistent, long-term memory of your application. The database is the foundational source of truth, and prompting for it requires a high degree of precision to ensure data is structured correctly, queried efficiently, and modified safely.

A clear database prompt specifies the data models, the relationships between them, and the exact logic for reading or writing information. This precision is critical for maintaining data integrity and building a high-performance application.

---
### 1. Schema Design & Creation

This is about defining the blueprint for your data: the tables, the columns within them, their data types, and how they relate to each other.

* #### Basic Prompt:
    > I need a users table and a posts table.

* #### Specific Prompt:
    > Using **Prisma schema syntax**, define two related models: `User` and `Post`. A **User can have many Posts**.
    > - The `User` model needs fields for `id` (UUID, default to `uuid()`), `email` (String, unique), and `name` (String, optional).
    > - The `Post` model needs `id`, `title`, `content`, and an `authorId` that creates a **foreign key relationship** to the `User`'s `id`.
    > - Add a database **index** to the `authorId` column for faster query performance.

* #### Why It's Better:
    The specific prompt dictates the **schema language** (Prisma), the **exact models and fields**, the **critical relationship** between them, and a **performance optimization** (indexing). This provides a complete and robust data blueprint.

* #### 🛠️ Tool Examples:
    * **AI Assistants:** `GitHub Copilot`, `Cursor` (excellent for writing schema files)
    * **Database Design Tools:** `dbdiagram.io`, `Lucidchart` (for visual modeling)
    * **Database GUIs with AI:** `DbVisualizer`, `DataGrip`

---
### 2. Writing Basic Read Queries

This covers prompting for common `SELECT` queries to retrieve data from one or more tables.

* #### Basic Prompt:
    > Get all users.

* #### Specific Prompt:
    > Write a **Prisma** query to find the **first 50** users. From the `User` table, select **only their `id`, `name`, and `email` fields**. The results must be **ordered by the `name` field** in ascending alphabetical order.

* #### Why It's Better:
    It specifies the **ORM** (Prisma), the **exact fields to select** (a technique called projection), the **ordering of results** (sorting), and the **number of records to return** (pagination). This results in a much more efficient and predictable query.

* #### 🛠️ Tool Examples:
    * **AI Assistants:** `Cursor`, `GitHub Copilot`, `Phind`
    * **Data Analysis Tools:** `Hex's Magic AI`, `Databricks Assistant`

---
### 3. Writing Complex Read Queries (Joins & Filtering)

This is about answering more advanced questions by combining data from multiple tables and applying complex filtering logic.

* #### Basic Prompt:
    > Find posts from certain users.

* #### Specific Prompt:
    > Write a **raw SQL query** to find all posts written by users whose email addresses end in `@example.com`.
    > - The query must **JOIN** the `posts` table with the `users` table on the author's ID.
    > - It should return only three columns: the post's `title`, the post's `created_at` date, and the author's `name`.
    > - Filter the results using a `WHERE` clause with the `LIKE` operator.

* #### Why It's Better:
    It asks for **raw SQL** (a different skill than using an ORM), specifies a **complex filter condition** (`LIKE`), defines the **exact join logic**, and details the **specific fields to return** from both tables.

* #### 🛠️ Tool Examples:
    * **AI Assistants:** `Cursor` (can generate and explain complex SQL)
    * **SQL Optimization Tools:** `EverSQL`, `Metis`
    * **BI & Data Platforms:** `Looker`, `Tableau` (have their own query generation interfaces)

---
### 4. Writing Data Mutations (Write Operations)

These are prompts for creating (`INSERT`), updating (`UPDATE`), or deleting (`DELETE`) data. These are critical to get right to avoid data corruption or loss.

* #### Basic Prompt:
    > Update a user's name.

* #### Specific Prompt:
    > Write a function using the **Drizzle ORM** that accepts a `userId` and a `newName` as arguments. The function must **update the `name` field** of the user with the matching ID. Crucially, the function must also **return the complete, updated user object** after the change has been successfully saved to the database.

* #### Why It's Better:
    It specifies the **ORM** (Drizzle), the **function's inputs**, the **exact operation**, and the **required return value**, which is a common and important pattern for keeping an application's state in sync.

* #### 🛠️ Tool Examples:
    * **AI Assistants:** `GitHub Copilot`, `Cursor`
    * **ORMs:** `Prisma`, `Drizzle ORM`, `TypeORM`

---
### 5. Database Migration Generation

After you change your schema file, you need to generate a "migration"—an executable script that safely applies those changes to your live database.

* #### Basic Prompt:
    > How do I update my database schema?

* #### Specific Prompt:
    > I have added an optional `bio` text field to my `User` model in my `schema.prisma` file. Tell me the **exact Prisma CLI command** I need to run to **generate a new database migration file** for this change. The migration should be named `add-user-bio`.

* #### Why It's Better:
    It describes the **change that was made**, specifies the **tool to use** (Prisma CLI), and provides the **desired name for the migration**. This is exactly what a developer needs to do in a real-world workflow to manage their database evolution safely.

* #### 🛠️ Tool Examples:
    * **Migration CLIs:** `Prisma Migrate`, `Drizzle Kit`, `Flyway`, `Alembic`
    * **AI Assistants:** `GitHub Copilot` and `Cursor` are excellent at predicting and suggesting these CLI commands.

---
### ✅ Summary Cheat Sheet

| Prompting For... | Key Details to Include in Your Prompt | Specialized Tool Examples |
| :--- | :--- | :--- |
| **Schema Design** | Schema language (Prisma, etc.), model names, field details (type, constraints), and relationships. | `dbdiagram.io`, `Cursor` |
| **Basic Queries** | The ORM/language, specific fields to select, sorting order, and pagination limits. | `Phind`, `GitHub Copilot`|
| **Complex Queries**| The join logic, advanced filtering conditions (`WHERE`), and the final combined data shape. | `EverSQL`, `Cursor` |
| **Data Mutations** | The operation (insert, update, delete), the data to be changed, and the expected return value. | `Prisma`, `Drizzle ORM` |
| **Migrations** | The schema change made, the migration tool being used (Prisma CLI, etc.), and the desired migration name. | `Prisma Migrate`, `Drizzle Kit` |
```