# TechPulse - Automated Content System

## What's Included

### 1. Auto-Deploy (GitHub Actions)
- Every push to `main` automatically deploys to Cloudflare Pages
- No manual deployment needed!

### 2. Weekly Content Ideas
- Every Monday at 8:00 AM (UTC), a new article idea is created as a GitHub Issue
- 15 pre-researched topics in rotation
- Category tags for organization

---

## Setup Instructions

### Step 1: Configure Cloudflare Secrets

1. Get your Cloudflare API Token:
   - Go to: https://dash.cloudflare.com/profile/api-tokens
   - Create a token with "Edit Cloudflare Pages" template

2. Get your Account ID:
   - Found in Cloudflare Dashboard URL: `https://dash.cloudflare.com/YOUR_ACCOUNT_ID`

3. Add secrets to GitHub:
   - Go to: https://github.com/zaneven/techpulse/settings/secrets/actions
   - Add:
     - `CLOUDFLARE_API_TOKEN`: Your API token
     - `CLOUDFLARE_ACCOUNT_ID`: Your account ID

### Step 2: Test the Workflow

```bash
# Make a small change and push
echo "# Test" >> README.md
git add .
git commit -m "test: trigger auto-deploy"
git push
```

---

## Content Workflow

### Manual Article Creation

1. Create a new Markdown file in `src/pages/posts/`
2. Use the template below:

```markdown
---
layout: ../../layouts/BlogPost.astro
title: "Your Title"
description: "Your description"
date: "2026-03-11"
category: "Category"
---

# Your Content Here

## Section 1

Content...

## Section 2

More content...

---

👉 **[Affiliate Link](https://amazon.com)**
```

3. Push to deploy!

---

## Automated Content Generation (Advanced)

### Option A: AI-Powered (Requires OpenAI API Key)

Add to workflow:
```yaml
- name: Generate with AI
  run: |
    npx openai-api generate \
      --topic "Best VS Code Extensions" \
      --output src/pages/posts/vscode-extensions-2026.md
```

### Option B: Scheduled Auto-Publish

Set up a scheduled workflow to auto-publish from a draft folder.

---

## Current Schedule

| Day | Content Type | Status |
|-----|--------------|--------|
| Monday | Tutorial | Auto-generated |
| Wednesday | Review | Auto-generated |
| Friday | Career/Tips | Auto-generated |

---

## Troubleshooting

### Deployment Failed
- Check GitHub Actions logs
- Verify Cloudflare secrets are correct
- Ensure `wrangler.toml` is valid

### Content Not Updated
- Make sure to push to `main` branch
- Check that build completes successfully

---

## Next Steps

1. ☐ Configure Cloudflare secrets
2. ☐ Test auto-deploy
3. ☐ Enable weekly content workflow
4. ☐ Add more topics to `content-ideas/topics.json`
5. ☐ (Optional) Set up AI content generation
