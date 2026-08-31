+++
title = "How I Built My First Hugo Website Using Gemini & Vibecoding"
date = 2026-08-31
tags = ["hugo", "vibecoding", "webdev", "ai"]
draft = false
+++

Building websites used to mean spending hours configuring complex templates, wrestling with build tools, and manually debugging CSS layouts. But when you lean into **vibecoding**—focusing entirely on the high-level architecture, user experience, and aesthetic while letting AI write the boilerplate—you can ship things at lightning speed.

Here is the exact breakdown of how I built my new minimalist, dark-themed, monospaced portfolio and blog using Hugo, Node.js, and Gemini.

---

## The Stack: Why Hugo + Monospaced Minimalism?

As a graphic designer and developer, I wanted something lightweight, lightning-fast, and unapologetically terminal-vibed.

* **Hugo:** A blazing-fast static site generator built in Go that compiles Markdown files into raw HTML instantly.
* **Node.js (`hugo-extended`):** Managed locally via npm so the correct binary downloads straight into project dependencies without global system pollution.
* **Aesthetics:** A dark Tokyo Night-inspired color palette (`#0d1117`), clean glassmorphism touches, and the crisp typography of **JetBrains Mono**.

---

## Step 1: Initialize the Project via Node.js

Instead of installing system-wide binaries, I set up a local Node project to handle Hugo cleanly inside the repository:

```bash
mkdir najah-blog
cd najah-blog
npm init -y
npm install hugo-extended --save-dev

```

Next, I configured shortcut scripts in `package.json` to make running and building the local server seamless:

```json
{
  "scripts": {
    "hugo": "hugo-extended",
    "dev": "hugo-extended server -D",
    "build": "hugo-extended --minify"
  }
}

```

Then, I scaffolded the Hugo structure using:

```cmd
npx hugo-extended new site . --format yaml --force

```

---

## Step 2: Crafting the Custom Terminal Theme

Instead of fighting bloated third-party themes, I had Gemini generate a custom, hyper-minimalist layout using Go templates.

1. Created the layout directories:
```cmd
mkdir layouts\_default
mkdir layouts\partials

```


2. **The Meta Head (`layouts/partials/head.meta.html`):** Injected Google Fonts (`JetBrains Mono`) and setup custom CSS variables for the dark theme.
3. **The Base Shell (`layouts/_default/baseof.html`):** Configured the global frame with a terminal-style header (`> ~ /home`), navigation menus pointing to blogs, tags, and search, and a clean footer.
4. **The Homepage (`layouts/_default/home.html`):** Designed an introductory landing page showcasing a bio, quick social links (GitHub, Twitter, Portfolio), and an automated list of recent blog posts.

---

## Step 3: Writing and Adding New Content

Adding a new post is a single command away using the local npm script or `npx`:

```cmd
npx hugo-extended new posts/hello-world.md

```

This creates a markdown file inside `content/posts/hello-world.md`. Open it up, fill out the front matter, and write your thoughts:

```markdown
---
title: "Hello World"
date: 2026-08-31
draft: false
---

This is my first post on my new Hugo blog built entirely with AI assistance. Fast, clean, and zero bloat.

```

---

## Step 4: Fire Up the Local Server

To see the site live with instant hot-reloading as you type, run:

```cmd
npm run dev

```

Head over to `http://localhost:1313` in your browser, and your terminal-inspired dark theme is ready to go. Vibecoding at its finest—architecture planned, code generated, and shipped in minutes.