# PR Platform — Phase 2

This is the real, hosted version of the Purchase Requisition workflow, replacing the browser prototype. No coding needed to deploy it — follow these steps in order.

## 1. Database (Supabase)

If you haven't already:
1. In your Supabase project, go to **SQL Editor → New query**
2. Paste and run `schema.sql` (from the first message)
3. Paste and run `schema-part2-signup-trigger.sql`

## 2. Put this code on GitHub

1. Create a new empty repository on github.com (no README/license needed)
2. On the repo page, click **Add file → Upload files**
3. Drag this entire `pr-platform` folder in (or its contents) and commit

## 3. Deploy on Vercel

1. On vercel.com, click **Add New → Project**
2. Choose the GitHub repo you just created
3. Before clicking Deploy, open **Environment Variables** and add:
   - `NEXT_PUBLIC_SUPABASE_URL` — from Supabase → Project Settings → API
   - `NEXT_PUBLIC_SUPABASE_ANON_KEY` — same page, the "anon public" key
4. Click **Deploy**

You'll get a live URL like `pr-platform-xyz.vercel.app` within a minute or two.

## 4. Make yourself Administrator

1. Open your deployed URL, create your account (sign up)
2. In Supabase → **Table Editor → profiles**, find your row
3. Edit it: set `is_admin` to `true`
4. Reload the app — you're now Administrator

## What's built so far

- Sign up / sign in (real, secure — Supabase Auth)
- Home page confirming the database connection works

## What's next

The Admin setup screens, the requisition workflow, the dashboard, and file uploads all get added in the same repo — each update just needs re-uploading the changed files to GitHub, and Vercel redeploys automatically.
