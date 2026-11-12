# SteelBook – client demo (static web app)

Responsive web app: desktop sidebar layout, tablet layout, and a phone layout with a
bottom tab bar, card-style lists and full-screen forms. It can be installed on a phone's
home screen (Add to Home Screen) and opens like an app.

Demo data is generated in the browser and saved in that browser only (localStorage).
"Reset demo data" restores it. No backend is needed for this demo.

## Deploy on Vercel – option A: GitHub (recommended, auto-redeploys)
1. Create a new GitHub repo (e.g. `steelbook-demo`) and upload everything in this folder
   (`public/`, `vercel.json`, `package.json`, `README.md`).
2. Go to https://vercel.com/new, click **Import** next to the repo.
3. Framework preset: **Other**. Leave Build Command empty. Output Directory: `public`
   (already set in vercel.json).
4. Click **Deploy**. You get a URL like `https://steelbook-demo.vercel.app`.
5. Every push to the repo redeploys automatically.

## Option B: Vercel CLI (no GitHub)
```bash
npm i -g vercel
cd steelbook-vercel
vercel login
vercel          # preview deploy – answer the prompts, accept defaults
vercel --prod   # production URL
```

## Custom domain (optional)
Vercel dashboard → Project → Settings → Domains → add e.g. `app.bansalsteel.in`,
then add the CNAME record it shows at your domain registrar.

## Protect the demo link (optional)
Project → Settings → Deployment Protection → enable **Password Protection** (Pro plan)
or Vercel Authentication, so only Akshay can open it.

## Next step (Phase 1 production)
This folder is the clickable prototype. For production, the same screens move into a
Next.js app on Vercel with a PostgreSQL database (Neon / Supabase), login, and
server-side validation, so data is shared across all users and devices.
