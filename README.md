# GigLocal

A two-sided marketplace connecting local music venues with musicians and bands.

> This is a project overview. The source lives in a private repository. Happy to walk through the code and architecture on request.

## What it does

- **Venues** create profiles, post availability, and search for musicians.
- **Musicians** build profiles, showcase performance video, and get discovered.
- **Connection model:** a small unlock fee from both sides exchanges contact info, so the marketplace only charges when a real match happens.

## How it is built

- Next.js 14 (App Router) frontend with TypeScript and Tailwind.
- Supabase for the backend: PostgreSQL, Auth, Storage, and Edge Functions.
- Stripe for the two-sided payment unlock, driven by webhook-backed Edge Functions.
- Transactional email through Resend, form validation with Zod, end-to-end tests in Playwright.
- Deployed on Vercel.

## Payment flow

1. Venue initiates contact and pays the unlock fee.
2. Musician is notified and reviews the venue.
3. Musician accepts and pays their side.
4. Both paid, so contact info and messaging unlock for both parties.

## Status

Built solo under NerdJoy LLC.
