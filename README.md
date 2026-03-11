# TechPulse Blog

A simple tech blog built with Astro and deployed on Cloudflare Pages.

## Quick Start

```bash
# Install dependencies
npm install

# Run locally
npm run dev

# Build
npm run build

# Deploy to Cloudflare Pages
npx wrangler pages deploy dist
```

## Add New Posts

Create a new `.md` file in `src/pages/posts/`:

```markdown
---
title: "Your Title"
description: "Your description"
date: "2026-03-11"
category: "Category"
---

# Your Content
```

## Deploy

1. Connect this repo to Cloudflare Pages
2. Build command: `npm run build`
3. Output directory: `dist`
