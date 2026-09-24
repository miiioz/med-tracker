# med-tracker

**MediLog** is a lightweight, mobile-first personal medication tracker built as an installable PWA.

The project started as a simple way to track Dupixent (达必妥) stock and injection dates, but the data model is intentionally generic so it can later support other injections, tablets, capsules, inhalers, supplements and related health records.

## Current MVP

- Add and manage multiple medications
- Track current stock and unit (支 / 片 / 粒 etc.)
- Set quantity used per dose
- Set planned interval in days
- Optional initial last-dose date
- Record a dose and automatically deduct stock
- Restock medication inventory
- Calculate last dose and next expected dose date
- Calculate historical average dosing interval
- Low-stock indicator
- Recent history and full event history
- Local-only storage using `localStorage`
- Export/import JSON backup
- Installable PWA manifest
- Offline service worker
- Responsive iPhone/Android-friendly interface

## Privacy model

Personal medication data is **not stored in this GitHub repository**. The repository contains application code only.

Medication names, stock levels and dosing history are stored in the browser's local storage on the user's device. Clearing browser/site data can remove those records, so periodic JSON backup is recommended.

## Files

- `index.html` — application UI and logic
- `manifest.json` — PWA configuration
- `sw.js` — offline service worker
- `icon.svg` — application icon
- `README.md` — project record and roadmap

## Roadmap

### Near term

- Improve calendar/history view
- Add stock adjustment event instead of direct stock editing
- Add medication archive rather than delete-only workflow
- Add CSV export
- Add calendar (`.ics`) export for next planned dose
- Better iOS home-screen icon support
- Add automated tests for date/stock calculations

### Later possibilities

- Optional reminder notifications where supported
- Optional encrypted/cloud sync across devices
- Symptoms / side-effects log
- Appointment and prescription refill tracking
- Photos / prescription documents
- Health measurements such as glucose or peak flow

## Product principle

MediLog is a **personal record-keeping tool**, not a prescribing or treatment-decision tool. It should display what the user entered and simple date/inventory calculations without recommending dose changes or changing treatment intervals.

## Deployment

The app is static and can be deployed directly to Cloudflare Pages, GitHub Pages, Netlify or any HTTPS static host. No server or database is required for the current local-only version.
