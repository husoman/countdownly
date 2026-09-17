# Countdownly

A tool for creating shareable countdown pages — for a wedding, a launch, a deadline, a birthday, anything with a date attached. No signup, no app, no backend. The event data lives entirely in the link.

**[Live demo](https://countdownly-liard.vercel.app/)**

## What it does

- Type an event name, pick an icon, set a date and time — get redirected to a countdown page whose URL *is* the shareable link.
- The page shows a live-ticking days/hours/minutes/seconds countdown.
- When the date arrives, it shows a confetti burst and a "It's here!" message instead of the countdown.
- Copy-link button, plus the native share sheet on mobile.
- Every countdown page has a "Create your own →" link, so anyone who receives one can make their own.

## How it works

There's no database and no server-side logic. The event title, date, and emoji are encoded as query parameters in the URL itself (e.g. `?t=My+Event&d=2026-12-25T00:00:00.000Z&e=🎉`). Opening a link with those parameters renders the countdown; opening the bare URL renders the creation form. This keeps the whole thing a single static file.

## Known limitation

Social preview cards (the title/image shown when a link is pasted into iMessage, Slack, or Twitter) aren't personalized per countdown — they show generic Countdownly text rather than the specific event, since that would require server-side rendering per link. The countdown itself still works fine; only the preview thumbnail is generic.

## Tech

Single self-contained HTML file — no framework, no build step, no backend.

## Running locally

Open `index.html` in a browser.

## Deploying

Any static host works. Connected to Vercel or Cloudflare Pages, every push to `main` auto-deploys.
