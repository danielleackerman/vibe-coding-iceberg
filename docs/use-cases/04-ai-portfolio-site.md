---
title: AI Portfolio Site
nav_order: ""
description: A guide to building an AI-powered portfolio site that showcases work and integrates machine learning models.
tags:
  - use cases
  - AI
  - portfolio
  - vibe coding
layout: default
---
# 🤖 Blueprint: Building an AI-Powered Portfolio Site

This guide provides a comprehensive, 10-step blueprint for building an **AI-Powered Portfolio Site**. This is more than a standard portfolio; it's a dynamic site that not only showcases your work but also integrates a live machine learning model that visitors can interact with—for example, an image style transfer tool, a text summarizer, or a custom chatbot.

This blueprint breaks down the entire process, from initial setup to final deployment. Each step includes a practical AI prompt and, critically, **three distinct technology alternatives**, explaining when and why you would choose each one. This serves as a decision map for assembling your own unique tech stack.

---
### Step 1: Project Scaffolding

**The Goal:** Create the foundational file structure and development environment for the entire application.

* #### 🤖 AI Prompt Example:
    > "Generate the command to scaffold a new web project named `ai-portfolio` using its command-line tool. The project must be pre-configured with support for **TypeScript** and **Tailwind CSS**."

* #### Technology Choices & Connections:

| Option | Language | When & Why to Choose It | Connects To... |
| :--- | :--- | :--- | :--- |
| **1. Next.js** | TypeScript/JS | **The Balanced Choice.** Choose this if you want a powerful, all-around framework that can handle both a highly performant static portfolio and the complex backend API routes needed to run an AI model. | Its serverless functions connect directly to your **AI Model Backend** and it deploys seamlessly to **Vercel**. |
| **2. Astro** | TypeScript/JS | **The Performance Choice.** Choose this if your top priority is the fastest possible load time for your portfolio pages. Astro is designed to ship minimal JavaScript by default. | Your portfolio pages will be static HTML, but interactive AI components can be added as "islands." It connects to any **API Backend** for the AI logic. |
| **3. Gatsby** | TypeScript/JS | **The Plugin-Rich Choice.** Choose this if you want to leverage a massive ecosystem of plugins for sourcing data from different places (e.g., Markdown, various CMS platforms). | Its GraphQL data layer provides a structured way to pull content from your **Headless CMS** and into your **Frontend Components**. |

---
### Step 2: Styling & UI Foundation

**The Goal:** Establish the visual language and styling system for the entire site.

* #### 🤖 AI Prompt Example:
    > "Configure my project to use **[Chosen Tool]**. For **Tailwind CSS**, generate the necessary `tailwind.config.js` and `postcss.config.js` files. For **Mantine**, show me how to wrap my root layout with the `MantineProvider`."

* #### Technology Choices & Connections:

| Option | Language | When & Why to Choose It | Connects To... |
| :--- | :--- | :--- | :--- |
| **1. Tailwind CSS** | CSS | **For Custom Design.** Choose this when you have a unique design in mind and want a fast, utility-first workflow to build it directly in your code. | It directly styles your **React/Svelte/Vue Components**, providing a low-level but powerful way to implement your **Design System**. |
| **2. Mantine UI** | TypeScript/JS | **For Speed & Completeness.** Choose this when you want a beautiful, extensive, and pre-built library of components (buttons, modals, forms) out of the box. | It provides ready-made **Component Patterns** that you can immediately use in your project, accelerating UI development significantly. |
| **3. Framer Motion** | TypeScript/JS | **For an Animation-First Site.** Choose this when the "feel" of your portfolio is defined by fluid, complex animations and page transitions. | It connects directly to your **UI Components**, wrapping them in motion elements to control how they appear, disappear, and react to user interaction. |

---
### Step 3: Content Management for Projects

**The Goal:** Choose a system to store and manage the content for your portfolio case studies (text, images, descriptions).

* #### 🤖 AI Prompt Example:
    > "Generate the data schema for my portfolio projects using **[Chosen Tool's Syntax]**. The schema needs fields for `title`, `description` (rich text), `projectUrl`, `coverImage`, and a `tags` array."

* #### Technology Choices & Connections:

| Option | Language | When & Why to Choose It | Connects To... |
| :--- | :--- | :--- | :--- |
| **1. Headless CMS (Sanity.io)** | GROQ/JS | **For a Rich Editing Experience.** Choose this when you want a powerful, user-friendly web interface to manage your content, especially if it includes rich text or complex data. | Your **Fullstack Builder** fetches content from the Sanity **API**. It decouples your content from your code, allowing you to update your site without redeploying. |
| **2. Local Markdown Files** | Markdown | **For Simplicity & Portability.** Choose this when you want to keep your content directly alongside your code in your **Git Repository**. It's simple, fast, and version-controlled. | Your **Fullstack Builder** will use a library (like `gray-matter`) to read and parse the Markdown files from the local file system during the build process. |
| **3. Notion as a CMS** | N/A | **For Ultimate Convenience.** Choose this if you already manage your life and work in Notion and want to use its familiar interface to write your portfolio content. | This connects to your **Fullstack Builder** via the Notion **API**, turning your Notion pages into the data source for your live website. |

---
### Step 4: Building the Portfolio Showcase UI

**The Goal:** Create the frontend components that display your standard portfolio projects.

* #### 🤖 AI Prompt Example:
    > "Create a `ProjectCard` React component. It should accept props for a project's `title`, `coverImage`, and a `slug`. The entire card should be a link that navigates to `/projects/[slug]`. Use Tailwind CSS for styling."

* #### Technology Choices & Connections:

| Option | Language | When & Why to Choose It | Connects To... |
| :--- | :--- | :--- | :--- |
| **1. Server-Side Fetching** | TypeScript/JS| **The Default, Performant Choice.** Choose this when using a **Fullstack Builder** like Next.js. The data is fetched on the server when a user requests the page. | This is a core feature of your **Fullstack Builder**. It connects your **Frontend Components** to your backend data source (CMS or local files) before the page is even sent to the user's browser. |
| **2. Client-Side Fetching (SWR)**| TypeScript/JS | **For Highly Dynamic Data.** Choose this if the data changes frequently and you want to show the latest version without a page reload. | This connects your **Frontend Component** directly to an **API Endpoint**. The component will render a loading state, fetch the data in the browser, and then display it. |
| **3. GraphQL Client (Apollo)** | GraphQL/JS | **When Using a GraphQL CMS.** If your **Headless CMS** (like Hygraph) provides a GraphQL API, using a dedicated client simplifies data fetching. | It provides a strongly-typed connection between your **Frontend Components** and your GraphQL **API**, making queries safer and more declarative. |

---
### Step 5: Setting Up the AI Model Backend

**The Goal:** Create a way for your website to access and run a machine learning model.

* #### 🤖 AI Prompt Example:
    > "Create a Next.js API route at `/api/ai/style-transfer`. It should accept an image URL in a POST request. The route must then call the **[Chosen Tool's API]** with this image, and return the result from the AI model."

* #### Technology Choices & Connections:

| Option | Language | When & Why to Choose It | Connects To... |
| :--- | :--- | :--- | :--- |
| **1. Replicate** | API (JSON)| **For Open-Source Models.** Choose this when you want to easily run a popular, open-source model from the community without managing your own infrastructure. | This connects your **Backend API** to Replicate's powerful GPU-based **Infrastructure**. You are essentially outsourcing the AI processing. |
| **2. Hugging Face Inference API**| API (JSON) | **For a Huge Variety of Models.** Choose this to access the massive library of models available on the Hugging Face Hub. | This also connects your **Backend API** to external **Infrastructure**. It's an excellent way to experiment with many different models quickly. |
| **3. Custom Python Backend** | Python | **For a Proprietary Model.** Choose this when you have your own custom model that you need to host and run yourself. | This requires a more complex **Infrastructure** setup. Your **Next.js API** would make a request to this separate Python service (e.g., a Flask/FastAPI app) running on a platform like **Railway**. |

---
### Step 6: Creating the AI Interaction UI

**The Goal:** Build the frontend component that allows a visitor to provide input to your AI model (e.g., upload an image, type text).

* #### 🤖 AI Prompt Example:
    > "Create a React component named `ImageStyler`. It must include a file input that only accepts images. When a user selects an image, it should display a preview of that image on the page. Also include a 'Generate' button."

* #### Technology Choices & Connections:

| Option | Language | When & Why to Choose It | Connects To... |
| :--- | :--- | :--- | :--- |
| **1. React Dropzone** | TypeScript/JS| **For Robust File Handling.** Choose this library for a feature-rich, accessible, and easy-to-style file upload component. | This is a specialized **Frontend Component** that simplifies a complex UI task, providing a better user experience. |
| **2. Simple `<input type='file'>`**| HTML/JS | **For Utmost Simplicity.** Choose this if you just need the most basic browser functionality for file selection without any extra features. | This uses a native browser element, requiring no external libraries but more manual styling and state management. |
| **3. Vercel AI SDK Components** | TypeScript/JS| **For Chat Interfaces.** If your AI is a language model, choose this library for pre-built hooks and components for building chat UIs. | This connects your **Frontend UI** directly to the streaming capabilities of modern **Language Model APIs**. |

---
### Step 7: Connecting the UI to the AI Model

**The Goal:** Wire up the frontend interface to the backend API endpoint, so that user input is sent to the AI model and the result is displayed.

* #### 🤖 AI Prompt Example:
    > "In my `ImageStyler` component, create a function that triggers when the 'Generate' button is clicked. This function must take the selected image file, send it as a `POST` request to our `/api/ai/style-transfer` endpoint, and then display the returned AI-generated image in a results area."

* #### Technology Choices & Connections:

| Option | Language | When & Why to Choose It | Connects To... |
| :--- | :--- | :--- | :--- |
| **1. `useState` + `fetch`** | TypeScript/JS| **For Simple, One-Off Actions.** This is the most direct way to handle the state (e.g., `isLoading`, `error`, `result`) for a single API call. | This connects your **Frontend Component's State** directly to the browser's native **API** fetching capabilities. It's simple but requires manual state management. |
| **2. TanStack Query** | TypeScript/JS| **For Complex Interactions.** Choose this if you need more advanced features like caching the AI result, retrying on failure, or background polling. | It provides a robust cache and state management layer between your **UI Components** and your **Backend API**. |
| **3. Server Actions (Next.js)** | TypeScript/JS| **For a Tightly Integrated Approach.** Choose this modern Next.js feature to call server-side logic directly from a component, blurring the lines between frontend and backend. | This creates a direct, compiled connection between your **Frontend Component** and your **Backend Logic**, simplifying the data flow significantly. |

---
### Step 8: Adding a Contact Feature

**The Goal:** Provide a simple way for potential clients or collaborators to get in touch with you.

* #### 🤖 AI Prompt Example:
    > "Create a `ContactForm` component with fields for name, email, and message. When submitted, it should send the data to a Next.js API route that uses **[Chosen Tool]** to send me an email notification."

* #### Technology Choices & Connections:

| Option | Language | When & Why to Choose It | Connects To... |
| :--- | :--- | :--- | :--- |
| **1. Resend + React Email** | TypeScript/JS| **The Modern Coder's Choice.** Choose this to build and send beautiful, reliable emails using React components for templating. | This connects your **Backend API** to the Resend email service. The email templates themselves are written as **React Components**. |
| **2. Formspree / Getform** | API (JSON) | **The No-Backend Choice.** Choose this if you want to avoid writing any backend code for your form at all. | Your **Frontend Form Component** submits directly to the Formspree **External API**, which then handles the email notification for you. |
| **3. Custom Nodemailer Backend** | TypeScript/JS| **The Full-Control Choice.** Choose this if you need to send emails through your own SMTP server or have complex email logic. | This requires more **Backend** code and **Infrastructure** setup, but gives you complete control over the email sending process. |

---
### Step 9: Adding Site Analytics

**The Goal:** Add a tool to track how many visitors your site gets and what they are interested in.

* #### 🤖 AI Prompt Example:
    > "Show me how to integrate **[Chosen Tool]** into my Next.js application. I need the code for the tracking script and instructions on where to place it in my root layout."

* #### Technology Choices & Connections:

| Option | Language | When & Why to Choose It | Connects To... |
| :--- | :--- | :--- | :--- |
| **1. Vercel Analytics** | JS | **The Integrated Choice.** If you're deploying on **Vercel**, this is the easiest option. It's privacy-focused and requires zero configuration. | This connects your deployed site directly to Vercel's **Infrastructure**, providing analytics with no third-party scripts. |
| **2. Plausible / Fathom Analytics**| JS | **The Privacy-First Choice.** Choose these if respecting user privacy and avoiding cookies is a primary concern for you. | These are **External Services** that you integrate into your **Frontend** with a simple script, similar to Google Analytics but with a focus on privacy. |
| **3. Google Analytics** | JS | **The Industry-Standard Choice.** Choose this if you want the most powerful, feature-rich, and free analytics tool available. | This connects your site to the vast Google Marketing Platform, but comes with privacy trade-offs for your users. |

---
### Step 10: Deployment

**The Goal:** Push your completed site and its AI backend connections to the public internet.

* #### 🤖 AI Prompt Example:
    > "Generate a complete `.env.example` file for my AI portfolio. It must include placeholders for all the secrets I need for production deployment on **[Chosen Platform]**: my content management system keys, my AI model provider API key, and my analytics tracking ID."

* #### Technology Choices & Connections:

| Option | Language | When & Why to Choose It | Connects To... |
| :--- | :--- | :--- | :--- |
| **1. Vercel** | N/A | **For Next.js Applications.** This is the specialized, "best-in-class" choice for deploying a Next.js project. | Vercel is the **Infrastructure Platform** that is most tightly integrated with the **Next.js Fullstack Builder**. |
| **2. Netlify** | N/A | **For a Variety of Frontend Frameworks.** An excellent and powerful alternative to Vercel, especially if you chose Astro or another framework. | Like Vercel, it's a **Frontend Cloud** platform that connects to your **Git Repository** for automated deployments. |
| **3. Railway / Fly.io** | N/A | **If You Have a Custom Backend.** If you chose to build your AI backend as a separate Python server (Step 5), you need a platform like this to host it. | These platforms connect to your **Docker** containers, allowing you to deploy both your frontend and your custom, persistent **Backend Server** in the same place. |