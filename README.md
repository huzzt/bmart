# ✦ B&W Art Agent

AI-powered Black & White Art Generator — deployable on Vercel for free.

## Project Structure

```
bw-art-agent/
├── api/
│   └── generate.js       ← Serverless function (hides your API key)
├── public/
│   └── index.html        ← Frontend UI
├── vercel.json           ← Vercel routing config
└── README.md
```

---

## Deploy to Vercel (Step-by-Step)

### Step 1 — Get your Anthropic API Key
1. Go to https://console.anthropic.com
2. Sign up / log in
3. Click **API Keys** → **Create Key**
4. Copy the key (starts with `sk-ant-...`)

> New accounts get **$5 free credits** — enough for hundreds of artworks.

---

### Step 2 — Upload to GitHub
1. Go to https://github.com → click **New repository**
2. Name it `bw-art-agent`, set to **Public**
3. Upload all files from this folder (drag & drop or use GitHub Desktop)

---

### Step 3 — Deploy on Vercel
1. Go to https://vercel.com → sign up with GitHub
2. Click **Add New Project** → import your `bw-art-agent` repo
3. Click **Deploy** (leave all settings default)

---

### Step 4 — Add your API Key (IMPORTANT)
1. In Vercel dashboard → your project → **Settings** → **Environment Variables**
2. Add:
   - **Name:** `ANTHROPIC_API_KEY`
   - **Value:** `sk-ant-xxxxxxxxxxxx` (your key)
3. Click **Save**
4. Go to **Deployments** → click **Redeploy**

Done! Your app is live at `https://your-project.vercel.app` 🎉

---

## Optional: Limit Usage (Prevent Abuse)

In `api/generate.js`, you can add rate limiting using Vercel KV:
- Max requests per IP per day
- Only allow requests from your domain

See: https://vercel.com/docs/storage/vercel-kv

---

## Cost Estimate

| Usage | Estimated Cost |
|-------|---------------|
| 100 artworks | ~$0.30 |
| 1,000 artworks | ~$3.00 |
| Free credits | ~500–1,000 artworks |

---

## Tech Stack
- **Frontend:** Pure HTML + CSS + JavaScript (no framework)
- **Backend:** Vercel Serverless Function (Node.js)
- **AI:** Claude Sonnet via Anthropic API
- **Hosting:** Vercel (free tier)
