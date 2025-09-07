# Finance App — Chit Fund Starter (Next.js + Prisma + SQLite)

This repository is a starter web app for the Finance (chit fund) system:
- 20 fixed members
- ₹5,000 due by the 10th each month
- ₹500 late fee after the 10th
- Monthly draw on the 15th; selected member may request withdrawal

## What is included
- Next.js frontend (pages/)
- API routes under /pages/api to manage members, payments, and withdrawals
- Prisma schema using SQLite (dev.db) so you can run locally without external DB
- Placeholder for Razorpay checkout integration (you'll need to add keys)

## Quick start (local)

1. Extract the project and `cd finance-app`
2. Copy `.env.example` to `.env.local` and update values if needed:
   ```
   cp .env.example .env.local
   ```
3. Install dependencies:
   ```
   npm install
   ```
4. Generate Prisma client and run migration:
   ```
   npx prisma generate
   npx prisma migrate dev --name init
   ```
   This creates `dev.db` SQLite file.
5. Seed initial 20 members (optional step included via API) or use the web UI.
6. Run the dev server:
   ```
   npm run dev
   ```
7. Open http://localhost:3000

## Deploy to Vercel
- Push this repo to GitHub.
- Import project in Vercel.
- Add env variables in Vercel (DATABASE_URL, RAZORPAY keys).
- For production, consider moving to Postgres (Supabase or Railway) rather than SQLite.

## Notes about payments
- Razorpay integration in this starter is a placeholder. For real money transactions you'll need to:
  1. Sign up for Razorpay and get API keys.
  2. Replace placeholder server-side logic with proper order creation and webhook verification.
  3. Use HTTPS endpoints and secure storage for secrets.

## Files to inspect
- pages/index.js — main dashboard + payment simulation
- pages/api/members.js — add/list members
- pages/api/payments.js — mark payment as paid and list payments
- prisma/schema.prisma — database schema

If you'd like, I can:
1) Push this repo to a GitHub repo for you (I can't do that automatically without your GitHub credentials), or
2) Walk you through deploying to Vercel step-by-step, or
3) Prepare a zipped project you can download and run locally.

Tell me which one you prefer and I will provide the next step.
