# Najah's Blog & Portfolio

> Minimalist, dark-themed, monospaced portfolio and blog built with **Hugo**, **Node.js**, and custom Go templates.

## 🚀 Tech Stack & Tools

* **Static Site Generator:** Hugo (via `hugo-extended` npm package)
* **Design & Aesthetics:** Dark Tokyo Night theme (`#0d1117`), glassmorphic touches, and **JetBrains Mono** typography.
* **Hosting & Deployment:** GitHub & Netlify/Vercel

## 📂 Project Structure

```text
├── archetypes/        # Default front matter templates
├── assets/            # Styles and asset files
├── content/           # Markdown blog posts and pages (_index.md, search/, posts/)
├── data/              # Data configuration files
├── layouts/           # Custom Go HTML templates (baseof, partials, terms, search)
├── static/            # Static assets (images, icons)
├── hugo.yaml          # Site configuration and menu links
└── package.json       # Node dependencies and scripts
```

## 🛠️ Getting Started Locally

1. **Clone the repository:**
   ```bash
   git clone https://github.com/najah-pktr/najahsblog.git
   cd thottingal
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Run the development server:**
   ```bash
   npm run dev
   ```
   Open your browser and navigate to `http://localhost:1313`.

## ✍️ Adding a New Post

Create a new markdown blog post using the Hugo CLI script:

```bash
npx hugo-extended new posts/my-new-post.md
```

Open the generated file in `content/posts/my-new-post.md`, set `draft = false`, and write your content!

---
&copy; 2026 Najah P. All rights reserved.
