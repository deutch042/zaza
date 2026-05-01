# AGENTS.md

## Commands
- `npm run dev` - Dev server on port 3000, logs to dev.log
- `npm run build` - Production build
- `npm run lint` - ESLint
- `npm run db:push` / `db:generate` / `db:migrate` / `db:reset` - Prisma

## Stack
- Next.js 16 + React 19 + TypeScript
- Tailwind CSS 4 + shadcn/ui (Radix UI)
- Prisma + SQLite
- Zustand (state), next-intl (i18n), web-push (notifications)

## Deployment

- Netlify-ready (Recommended)
- Cloudflare Pages ready

## Stack
- Next.js 16 + React 19 + TypeScript
- Tailwind CSS 4 + shadcn/ui (Radix UI)
- Prisma + SQLite
- Zustand (state), next-intl (i18n), web-push (notifications)

## Notes
- For both Netlify and Cloudflare: use external DB (Turso) for production
- Set env vars: `DATABASE_URL`, `NEXT_PUBLIC_VAPID_PUBLIC_KEY`, `VAPID_PRIVATE_KEY`, `VAPID_SUBJECT`

## Netlify Deployment
1. Push code to GitHub
2. Go to https://netlify.com → Add new site → Import from Git
3. Set env vars in Netlify dashboard:
   ```
   DATABASE_URL=libsql://...
   NEXT_PUBLIC_VAPID_PUBLIC_KEY=BDfKkya975WhlfmZAkyxvBaiInsvJ-RyqNIZXyhPWTIemqB8nfmrhLruP2r1Yizaw915G_qSZG8pMl6-f0xUIM8
   VAPID_PRIVATE_KEY=6IDB6Vntsb7D9yTa18iCLP8KWsd4CzUL1IBc9pTl66I
   VAPID_SUBJECT=mailto:zad-muslim@app.com
   ```
4. Deploy

## Cloudflare Pages Deployment
1. Push code to GitHub
2. Go to https://dash.cloudflare.com → Pages → Connect GitHub repo
3. Set environment variables:
   ```
   DATABASE_URL=libsql://...
   NEXT_PUBLIC_VAPID_PUBLIC_KEY=BDfKkya975WhlfmZAkyxvBaiInsvJ-RyqNIZXyhPWTIemqB8nfmrhLruP2r1Yizaw915G_qSZG8pMl6-f0xUIM8
   VAPID_PRIVATE_KEY=6IDB6Vntsb7D9yTa18iCLP8KWsd4CzUL1IBc9pTl66I
   VAPID_SUBJECT=mailto:zad-muslim@app.com
   ```
4. Deploy

## Notes
- No test suite configured (no test script in package.json)
- Notifications work offline via Service Worker
- Postinstall runs `prisma generate`