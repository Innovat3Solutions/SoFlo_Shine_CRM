# SoFlo Shine Detailing — CRM

Internal CRM prototype for **SoFlo Shine Detailing**, a mobile auto-detailing business in South Florida.
Single-file front end, no build step: open `index.html` (or `soflo-shine-crm.dc.html` directly) and it runs. Deploys as a static site — no framework, no build command, output directory is the repo root.

## What's in it

| Area | What it does |
| --- | --- |
| Dashboard | Month revenue, expenses, net profit, pipeline value; expense breakdown, income-vs-expense trend, Q3 budget, plan members |
| Requests | Online quote submissions (website form, Instagram DM, Facebook, TikTok) with vehicle, service, preferred day, customer photos → one click builds a quote |
| Pipeline | Multiple pipelines (Sales, Recurring plans), custom phases, advance/move cards |
| Customers | List + profile: vehicles, contact, notes, quote history, job history, communication log |
| Quotes | Quote builder priced per vehicle (year/make/model, size class, condition), auto-priced upsells, packages, plan discounts, live customer-facing preview |
| Customer quote view | Interactive sheet the client receives: pick a package, toggle add-ons, choose a plan, deposit + accept flow |
| Jobs | Job list and job profile: revenue / materials / labor / profit, documents & signed agreements, before/after vehicle documentation with on-site camera flow and pre-existing damage record |
| Calendar | Day / week / month views, per-provider filtering and colors, add jobs and visits |
| Team | Add and edit employees (name, role, email, phone), per-provider calendars |
| Financials | Month P&L, overhead, profit by job, receipt-camera expense capture with line-item authorization |
| Settings | Service pricing (name, description, rate, unit), package builder, plan discounts, job minimum |

## Pricing model

Services are either **per vehicle** (scaled by size class and condition) or **flat rate**.

- Size class: Coupe/Sedan ×1.0 · Crossover/Mid SUV ×1.15 · Full-size SUV/Truck ×1.3 · 3-Row/Van ×1.45
- Condition: Light/Average ×1.0 · Heavy soil or pet hair +15% · Extreme +30%
- Add-on prices come from the shop's published sheet (ceramic 1-step $799 / 2-step $1,199, headlight restoration $100, engine bay $60, pet hair from $50, paint correction $450 / $750, odor removal from $100, clay bar $75, leather conditioning from $40, stain removal from $75).
- Base service prices (express $65, interior $185, exterior $225, full detail $350) are placeholders pending the owner's sheet — all editable in Settings.

## Files

```
index.html                 entry point (required by GitHub Pages / Vercel)
soflo-shine-crm.dc.html    the app (markup + logic in one file)
support.js                 runtime that mounts the component
soflo-logo.png             brand logo
vercel.json                static hosting config (no build step)
```

## Notes

- All data is in-memory sample data; there is no backend, auth, or persistence yet.
- Dark UI shell throughout; the customer-facing quote stays a white document with a dark header band.
- Photos, receipts and camera capture are simulated placeholders — wire to real device camera / storage when a backend exists.
