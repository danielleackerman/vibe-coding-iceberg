# ⚙️ Static Site Generators & Web Documentation Frameworks

These tools help transform structured content (like Markdown files) into full websites — perfect for documentation, knowledge bases, and developer portfolios.

---

## 🛠️ Tool Overview

### **MkDocs**
- **What it is**: A static site generator that converts Markdown files into clean, navigable websites.
- **Best for**: Documentation, knowledge bases, tech vaults.
- **Strengths**: Easy setup, supports themes like `material`, auto-generates navigation from folder structure.
- **Used by**: Python projects, AI notebooks, OpenAI Cookbook.

---

### **Jekyll**
- **What it is**: A static site generator built in Ruby; it powers GitHub Pages by default.
- **Best for**: Blogs, personal websites, basic documentation.
- **Strengths**: Works seamlessly with GitHub Pages (no deploy setup), good theming ecosystem.
- **Used by**: Many developer blogs, older documentation sites.

---

### **Docusaurus**
- **What it is**: A modern documentation builder from Meta that uses React.
- **Best for**: Developer portals, component libraries, docs-as-code systems.
- **Strengths**: Sidebar nav, versioning, dark mode, MDX (Markdown + React).
- **Used by**: Meta, Supabase, Redux, React Native.

---

### **Astro**
- **What it is**: A next-gen static site builder optimized for speed and component-based architecture.
- **Best for**: Jamstack-style sites, hybrid blogs/docs, UI-focused landing pages.
- **Strengths**: Ultra-fast loading, can integrate React/Vue/Svelte, uses `.astro` components.
- **Used by**: Design-centric devs and modern content sites.

---

### **Plain HTML/CSS/JS**
- **What it is**: Hand-built websites using core web technologies (no build tools).
- **Best for**: Full creative control, lightweight pages, teaching/learning HTML.
- **Strengths**: No frameworks or dependencies; runs anywhere.
- **Limitations**: Requires manual structure, harder to scale for content-heavy projects.

---

## ✨ How to Choose

| Use Case                         | Recommended Tool |
|----------------------------------|------------------|
| Developer docs + AI prompts      | MkDocs (Material) |
| Blog or personal site on GitHub  | Jekyll           |
| Component docs or UI libraries   | Docusaurus       |
| High-performance design portfolio| Astro            |
| Tiny one-page demo or prototype  | Plain HTML       |


| Tool                                  | Markdown-based? | Code Required?      | Visual Customization   | Best For...                         |
| ------------------------------------- | --------------- | ------------------- | ---------------------- | ----------------------------------- |
| **MkDocs**                            | ✅ Yes           | ⚠️ Minimal          | 🎨 Some (via Material) | Clean tech docs, fast setup         |
| **Jekyll**                            | ✅ Yes           | ⚠️ Medium           | 🎨 High (HTML/CSS)     | Blog-style sites on GitHub          |
| **Docusaurus**                        | ✅ Yes           | ✅ React-based       | 🎨 High                | Tech docs w/ React & tabs           |
| **Astro**                             | ✅ Yes + JSX     | ✅ Modern stack      | 🌈 Very high           | Gorgeous custom sites (like OpenAI) |
| **Plain HTML**                        | ❌ No            | ✅ Raw HTML/CSS      | 🎨 Unlimited           | Total freedom, no Markdown          |
| **Vibe Tools** (e.g. Webflow, Framer) | ❌ No\*          | ❌ No (drag + style) | 🌈 Pixel-perfect UI    | Designer/developer hybrid sites     |


---

## 🔍 Related Topics
- [Static site vs dynamic site](#)
- [Markdown → Website workflow](#)
- [How GitHub Pages works](#)
