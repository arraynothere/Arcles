<div align="center">

# ☕ Arcles

[![Hugo Version](https://img.shields.io/badge/Hugo-Static%20Site%20Generator-blue?style=flat-square&logo=hugo&logoColor=white)](https://gohugo.io/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg?style=flat-square)](LICENSE)
[![GitHub Pages](https://img.shields.io/badge/Deployment-GitHub%20Pages-orange?style=flat-square&logo=github)](https://pages.github.com/)

</div>

---

## 🔍 Overview

**Arcles** is an open-source static documentation site and technical archive dedicated to compiling source code, system analysis, cyber security insights, and computer science concepts. Engineered for developers and low-level enthusiasts, featuring a high-performance, clutter-free IDE-dark aesthetic.

- **Core Topics**: Source Code Architecture, Cyber Security, Reverse Engineering, Low-Level Programming, and Computer Science logs.
- **Live Site**: [arcles (GitHub Pages)](https://username.github.io/arcles/)

---

## 🛠️ Tech Stack

- **Generator**: [Hugo](https://gohugo.io/) (Fast Static Site Generator)
- **Styling**: Custom CSS (Terminal/IDE Theme, smooth lightweight animations, no bloat)
- **Hosting**: GitHub Pages

---

## 📂 Structure

```text
arcles/
├── archetypes/         # Default content templates
├── content/
│   ├── posts/          # Markdown articles & code snippets (.md)
│   ├── about.md        # About page information
│   └── donate.md       # Support / donation page
├── themes/
│   └── arcles/         # Custom responsive theme (layouts, partials, CSS)
└── hugo.toml           # Main site configuration
```

---

## 🚀 Getting Started Locally

If you want to run, test, or contribute to this repository locally:

### Prerequisites
Make sure you have [Hugo](https://gohugo.io/getting-started/installing/) installed on your machine.

### Installation & Execution
1. Clone this repository:
   ```bash
   git clone https://github.com/arraynothere/arcles.git
   cd arcles
   ```
2. Start the local development server:
   ```bash
   hugo server
   ```
3. Open your browser and navigate to `http://localhost:1313`.

---

## ✍️ How to Add a New Article

Adding a new post is straightforward. Create a new markdown file inside the `content/posts/` directory (e.g., `my-new-snippet.md`) with the following front matter structure:

```markdown
---
title: "Your Article Title Here"
date: 2026-10-28T12:00:00+07:00
draft: false
tags: ["tag1", "tag2"]
categories: ["Engineering"]
---

Write your technical content and code snippets in Markdown here.
```

---

## 📄 License

© 2026 - Arcles. Developed and maintained by [@arraydeveloper](https://github.com/arraynothere).
