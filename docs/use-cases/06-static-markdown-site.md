---
title: Static Site with Markdown
nav_order: ""
description: A step-by-step guide to building a static website using Markdown and a Static Site Generator (SSG).
tags:
  - use cases
  - static site
  - markdown
  - vibe coding
layout: default
---
```markdown
# 📝 Blueprint: Building a Static Site with Markdown

This blueprint provides a complete, ten-step guide to building a modern **static website** using Markdown as the primary content source. A static site is one where the pages are pre-built as simple HTML files, making them incredibly fast, secure, and easy to host. This architecture is the professional standard for documentation sites, personal blogs, and knowledge bases where performance is a top priority. We will explore the entire process, from choosing a generator to deploying a live site, with a focus on how different tool choices impact the final product. This guide includes practical AI prompts for each step to accelerate your workflow and decision-making.

---
### Step 1: Choose Your Static Site Generator (SSG)

**The Goal:** To select the core **engine**, or Static Site Generator (SSG), that will transform your Markdown files into a functional website.

**The Action:** This is the most important initial decision, as your choice of SSG determines the features available to you, the development workflow, and the underlying programming language of the ecosystem.

* #### 🤖 AI Prompt Example:
    > "Create a comparison table of modern Static Site Generators. The table must compare **MkDocs**, **Docusaurus**, and **Hugo** on the following criteria: primary language, key features, and best use case."

* #### Technology Choices & Connections:

| Option | Language | When & Why to Choose It | Connects To... |
| :--- | :--- | :--- | :--- |
| **1. MkDocs** | Python | **For simplicity and documentation.** Choose MkDocs when you want a straightforward, configuration-driven tool for creating clean, professional documentation sites with minimal fuss. | It connects to the **Python** ecosystem and uses a simple `mkdocs.yml` file for configuration. It's often used for project or API documentation. |
| **2. Docusaurus** | TypeScript/JS | **For feature-rich, interactive sites.** Choose Docusaurus when you want to build a documentation site with the power of **React**, allowing for custom components and interactivity. | It connects to the entire **React** ecosystem. You can use **MDX** to embed components directly in your Markdown, connecting your content to your UI library. |
| **3. Hugo** | Go | **For maximum speed.** Choose Hugo when your primary concern is build speed, especially for very large sites with thousands of pages. It is renowned for being the fastest SSG available. | It connects to the **Go** templating engine for layouts. It is a self-contained binary, meaning it has no external dependencies, unlike Node.js-based tools. |

---
### Step 2: Project Scaffolding & Initial Setup

**The Goal:** To create the initial folder structure and install the necessary dependencies for your chosen SSG.

**The Action:** We will use the command-line interface (CLI) associated with our chosen tool to generate a new, ready-to-code project.

* #### 🤖 AI Prompt Example:
    > "Give me the standard command-line instruction to create a new project named `my-docs-site` using **[Chosen Tool's CLI]**."

* #### Technology Choices & Connections:

| Option | Language | When & Why to Choose It | Connects To... |
| :--- | :--- | :--- | :--- |
| **1. MkDocs CLI** | Python | **For a Python-based workflow.** This assumes you have Python and `pip` (its package manager) installed on your system. | This connects to your system's **Python** installation and uses `pip` to install the MkDocs package and its dependencies. |
| **2. Docusaurus CLI** | TypeScript/JS | **For a Node.js-based workflow.** This uses `npx`, the Node.js package runner, to scaffold a new site with a standard structure. | This connects to the **Node.js** ecosystem and uses `npm` or `yarn` for package management, just like a modern web application. |
| **3. Hugo CLI** | Go | **For a dependency-free workflow.** The `hugo` command is a single executable file with no external dependencies needed. | This connects directly to your operating system's command line. You simply download the Hugo binary and run it. |

---
### Step 3: Plan Your Content Structure

**The Goal:** To decide on a logical folder and file structure for your Markdown content, which will often dictate the final site's navigation.

**The Action:** We will create the initial directory structure inside our project to hold our content files.

* #### 🤖 AI Prompt Example:
    > "Generate a clear, nested folder structure for a documentation site covering three products: 'Product A', 'Product B', and 'Product C'. Each product needs a 'Getting Started' guide and an 'API Reference' section."

* #### Technology Choices & Connections:

| Option | Language | When & Why to Choose It | Connects To... |
| :--- | :--- | :--- | :--- |
| **1. Flat Structure** | Markdown | **For simple sites.** All your Markdown files live in a single `docs/` folder. The navigation is usually defined manually in a configuration file. | This connects your content files directly to a manually curated navigation structure in your SSG's main **Configuration File**. |
| **2. Nested Structure** | Markdown | **For organized, large sites.** You create sub-folders for each section (e.g., `/guides/getting-started.md`). Many SSGs can auto-generate navigation from this structure. | This connects your **File System Organization** directly to the rendered **Site Navigation**, creating an intuitive link between content and presentation. |
| **3. Content Collections** | Markdown | **For powerful, typed content.** Frameworks like **Astro** allow you to define a "collection" with a required schema, ensuring all blog posts have a title and date. | This connects your Markdown files to a **Schema Definition**, providing data validation and type safety for your content. |

---
### Step 4: Configure Your Site & Theme

**The Goal:** To customize your site's main settings, such as its title, navigation menu, and visual theme.

**The Action:** We will edit the main configuration file for our chosen Static Site Generator.

* #### 🤖 AI Prompt Example:
    > "Generate the content for a `mkdocs.yml` file. Set the site name to 'My Project Docs'. Create a navigation menu with a 'Home' page, a 'User Guide' section with two nested pages, and an 'About' page."

* #### Technology Choices & Connections:

| Option | Language | When & Why to Choose It | Connects To... |
| :--- | :--- | :--- | :--- |
| **1. `mkdocs.yml`** | YAML | **For MkDocs projects.** YAML is a human-readable data format that is excellent for configuration. | This file is the central "brain" that connects your **Markdown Content** to the **MkDocs** build engine and your chosen **Theme**. |
| **2. `docusaurus.config.js`**| JavaScript | **For Docusaurus projects.** Using a JavaScript file for configuration allows for dynamic logic, like reading from the file system to generate the navbar. | This connects your configuration to the full power of the **Node.js** ecosystem, allowing for programmatic customization. |
| **3. `hugo.toml`** | TOML | **For Hugo projects.** TOML is another straightforward configuration language, similar to YAML. | This file connects all your site-wide parameters to the **Hugo** build engine. |

---
### Step 5: Write Content with Advanced Markdown

**The Goal:** To write the actual content for your site's pages using Markdown.

**The Action:** We'll go beyond basic text and use extended Markdown syntax to create richer content like tables, code blocks, and callouts.

* #### 🤖 AI Prompt Example:
    > "Generate a sample Markdown document about a fictional API endpoint. It must include a main heading, a code block with **JavaScript** syntax highlighting, a bulleted list of parameters, and a bordered 'admonition' or 'callout' box of the 'info' type."

* #### Technology Choices & Connections:

| Option | Language | When & Why to Choose It | Connects To... |
| :--- | :--- | :--- | :--- |
| **1. GitHub Flavored MD**| Markdown | **The common standard.** Most modern SSGs support GFM, which includes useful features like tables, strikethrough, and task lists. | This connects your writing to a widely understood and portable **Markdown Specification**. |
| **2. MDX** | MDX | **For interactive content.** Choose MDX when you need to embed live **React Components** directly within your Markdown text. | This connects your Markdown content directly to your **React Component Library**, allowing you to create rich, interactive documentation. |
| **3. AsciiDoc** | AsciiDoc | **For highly structured documents.** A powerful alternative to Markdown, often used for writing entire books and complex technical documentation. | This connects your writing to a different markup ecosystem with more features for complex document structure. |

---
### Step 6: Add Custom Components or Pages

**The Goal:** To extend your site beyond the limits of standard Markdown by adding custom-designed elements.

**The Action:** Depending on our SSG, we will either create a custom React component or a custom layout template.

* #### 🤖 AI Prompt Example:
    > "I'm using **Docusaurus**. Create a custom React component called `VideoPlayer` that takes a `youtubeId` prop and renders an embedded YouTube iframe. Then, show me how to import and use this component inside an **MDX** file."

* #### Technology Choices & Connections:

| Option | Language | When & Why to Choose It | Connects To... |
| :--- | :--- | :--- | :--- |
| **1. React Components (Docusaurus)**| TypeScript/JS | **For interactive extensions.** The standard way to add custom functionality to a Docusaurus or Gatsby site. | This connects the full power of the **React** ecosystem directly into your Markdown-based site via **MDX**. |
| **2. Hugo Shortcodes** | Go/HTML | **For reusable HTML snippets.** Hugo's system allows you to create reusable templates (shortcodes) that you can call from your Markdown. | This connects your Markdown content to Hugo's powerful **Go Templating Engine**. |
| **3. CSS Theme Overrides (MkDocs)**| CSS | **For visual customization.** The simplest way to customize an MkDocs site is by providing an extra CSS file that overrides the theme's default styles. | This connects a custom **CSS Stylesheet** to the base **Theme**, allowing you to change the look and feel without altering the HTML structure. |

---
### Step 7: Implement Search Functionality

**The Goal:** To add a search bar so users can easily find information within your site.

**The Action:** We will configure a search solution. Most modern SSGs have excellent built-in or plugin-based options.

* #### 🤖 AI Prompt Example:
    > "Explain how to enable the built-in search plugin for **MkDocs**. Show me the required entry to add to the `plugins` section of the `mkdocs.yml` file."

* #### Technology Choices & Connections:

| Option | Language | When & Why to Choose It | Connects To... |
| :--- | :--- | :--- | :--- |
| **1. Built-in SSG Search** | JavaScript | **The simplest option.** Most SSGs, like **Docusaurus** and **MkDocs**, have official search plugins that are easy to set up. | This connects a pre-built search indexer to your **Build Process**. The SSG scans all your content and creates a search index file. |
| **2. Algolia** | API (JSON) | **The powerful, hosted option.** Algolia is a third-party search-as-a-service platform that provides an incredible search experience. | This connects your site's content to the powerful **Algolia Search API**. A script sends your content to Algolia during your build process. |
| **3. Pagefind** | Rust/WASM | **The modern, self-hosted option.** Pagefind is a tool that runs after your site is built, creating a high-performance search index that runs entirely in the user's browser. | This connects to the **Output Folder** of your build process, adding a static search capability without needing a server. |

---
### Step 8: Preview Your Site Locally

**The Goal:** To see a live, clickable preview of your website on your own machine before you deploy it to the world.

**The Action:** We will run a single command in our terminal to start a local development server.

* #### 🤖 AI Prompt Example:
    > "What is the standard CLI command to start the local development server for a **Hugo** project? Also, include the flag to show draft content."

* #### Technology Choices & Connections:

| Option | Language | When & Why to Choose It | Connects To... |
| :--- | :--- | :--- | :--- |
| **1. `mkdocs serve`** | Python | **The MkDocs command.** | Connects the **MkDocs** engine to your local file system, automatically rebuilding the site when you save a file. |
| **2. `npm run dev`** | JavaScript | **The Node.js standard.** The command for most JavaScript-based SSGs like **Docusaurus** and **Astro**. | Connects a development server (often powered by **Vite**) to your source files for a fast, live-reloading experience. |
| **3. `hugo server`** | Go | **The Hugo command.** | Connects the ultra-fast **Hugo** build engine to your content, often rebuilding your entire site in milliseconds. |

---
### Step 9: Automate Your Build & Deployment

**The Goal:** To create a CI/CD pipeline that automatically builds and deploys your site whenever you push changes to your Git repository.

**The Action:** We will create a workflow configuration file for a CI/CD platform like GitHub Actions.

* #### 🤖 AI Prompt Example:
    > "Generate a **GitHub Actions** workflow file to build my **Docusaurus** site. The workflow must trigger on a push to the `main` branch, set up Node.js, install dependencies with `npm ci`, and run the `npm run build` command."

* #### Technology Choices & Connections:

| Option | Language | When & Why to Choose It | Connects To... |
| :--- | :--- | :--- | :--- |
| **1. GitHub Actions** | YAML | **The GitHub-native choice.** Tightly integrated with your repository, making it the easiest and most common choice for GitHub-hosted projects. | This connects your **Git Repository** directly to an automated **Build and Deployment Process**. |
| **2. GitLab CI/CD** | YAML | **The GitLab-native choice.** If your code is hosted on GitLab, its built-in CI/CD is powerful and easy to set up. | This connects your **GitLab Repository** to its integrated CI/CD runners. |
| **3. Integrated Platform CI** | N/A | **The simplest choice.** Platforms like **Vercel** and **Netlify** have their own CI/CD built-in. You just connect your Git repo, and they handle the rest. | This connects your **Git Repository** directly to your **Hosting Platform**, abstracting away the need for a separate CI/CD configuration file. |

---
### Step 10: Choose a Hosting Platform

**The Goal:** To select the best place to host the final static HTML, CSS, and JavaScript files that your SSG generates.

**The Action:** We will connect our repository to a hosting service that is optimized for static sites.

* #### 🤖 AI Prompt Example:
    > "I need to host my static documentation site. Create a brief comparison of **GitHub Pages**, **Netlify**, and **Cloudflare Pages**, focusing on their key features for static hosting."

* #### Technology Choices & Connections:

| Option | Language | When & Why to Choose It | Connects To... |
| :--- | :--- | :--- | :--- |
| **1. GitHub Pages** | N/A | **For ultimate simplicity.** A free, easy way to host a public static site directly from your GitHub repository. | This connects your **Git Repository** directly to GitHub's own simple **Hosting Infrastructure**. It's perfect for project documentation. |
| **2. Vercel / Netlify** | N/A | **For power and features.** Choose these for production-grade hosting with features like deploy previews, analytics, and serverless functions. | These **Infrastructure Platforms** connect directly to your **Git Repository** and provide a seamless, automated build and deployment workflow. |
| **3. AWS S3 + CloudFront**| N/A | **For full control and integration.** The professional, enterprise-grade choice for hosting static assets with a global CDN. | This connects your static files to the foundational **AWS Infrastructure**, giving you ultimate control over configuration but requiring more expertise. |

---

This blueprint demonstrates the complete lifecycle of creating a modern, Markdown-based static site. While the core content is simple text, the surrounding ecosystem of tools for generation, theming, and deployment is powerful and sophisticated. The key to success is choosing a Static Site Generator that aligns with your technical comfort zone and the specific needs of your project. From there, a rich set of tools for search, customization, and automation allows you to build a world-class documentation or content site. This entire process, accelerated by AI prompting, makes creating these high-performance sites more accessible than ever before.