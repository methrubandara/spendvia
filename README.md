# Spendvia

**Decision-intelligence platform for SMBs — spend smarter before costs are locked in.**

🔗 [spendvia.vercel.app](https://spendvia.vercel.app)

---

## What is Spendvia?

Spendvia is a SaaS platform that helps small and mid-sized businesses reduce unnecessary spending by providing asset lifecycle visibility, depreciation tracking, and cost-saving recommendations **before** purchases are approved.

Most SMBs track expenses after the fact. Spendvia sits between the purchase request and approval — giving decision-makers the context they need to spend smarter.

---

## The Problem

- Inventory data is fragmented across spreadsheets and disconnected tools
- Assets get replaced too early or unnecessarily
- Purchase requests lack context — no depreciation data, no alternatives, no lifecycle visibility
- Finance teams approve spending reactively with no decision support

---

## How Spendvia Works

**Inventory Intelligence** — Import existing asset data via CSV. Spendvia normalizes it into structured categories, tracks purchase history, and monitors depreciation and lifecycle status across the organization.

**Decision Intelligence** — When a purchase request comes in, Spendvia cross-references existing inventory, flags premature replacements, and surfaces lower-cost alternatives (refurbished options, bulk discounts, existing assets in storage).

**Purchase Workflows** — Multi-step approval flows with full context at every stage. Managers see asset age, book value, remaining useful life, and recommended alternatives before approving.

**Asset Disposition** — End-of-life assets are routed to certified recyclers or secondary-market buyers, recovering salvage value while reducing e-waste.

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Framework | Next.js 16 (App Router) |
| Language | TypeScript |
| Styling | Tailwind CSS v3 |
| Database | Supabase (PostgreSQL + Row Level Security) |
| Auth | Supabase Auth |
| Email | Resend |

---

## Features

- **Admin Dashboard** — 7-tab interface (Overview, Inventory, Depreciation, Requests, Receipts, Reports, Intelligence)
- **User Portal** — Employee-facing interface for submitting requests and viewing assigned assets
- **Super Admin Panel** — Platform-level management for onboarding companies
- **5-Step Onboarding Wizard** — Company setup with CSV bulk import and automatic column mapping
- **3-Level Inventory Drill-Down** — Categories → Products → Individual Assets
- **Depreciation Engine** — Configurable policies (straight-line, declining balance) with per-asset tracking
- **Purchase Request Workflows** — Multi-stage approvals with email notifications
- **AI Recommendations** — Cost-saving opportunities through inventory utilization, refurbished alternatives, and bulk discounts
- **Asset Disposition** — End-of-life recovery through recycler and secondary-market connections
- **Role-Based Access Control** — Company-scoped multi-tenancy with RLS

---

## Architecture

```
├── Super Admin Dashboard    (/admin)
│   └── Company management, platform analytics
│
├── Company Admin Dashboard  (/dashboard)
│   ├── Overview — KPIs, lifecycle distribution, alerts
│   ├── Inventory — Full asset tracking with drill-down
│   ├── Depreciation — Per-asset depreciation charts
│   ├── Requests — Approval workflows with alternatives
│   ├── Receipts — Upload + OCR extraction
│   ├── Reports — Spending summaries, forecasting
│   └── Intelligence — AI-powered savings recommendations
│
└── User Portal              (/user)
    ├── Overview — Quick stats, recent activity
    ├── My Requests — Submit and track purchase requests
    └── My Assets — View assigned equipment
```

---

## Database Schema

15+ tables including:

- `companies` / `users` — Multi-tenant organization structure
- `asset_categories` / `inventory_items` / `inventory_lots` — Three-level asset hierarchy
- `depreciation_policies` / `lot_depreciation_snapshots` — Lifecycle tracking
- `purchase_requests` — Multi-stage approval workflow
- `import_batches` / `category_suggestions` — CSV ingestion pipeline
- `activity_log` — Full audit trail

---

## Target Users

**Primary:** Operations Managers, Finance Managers, Budget Owners who approve purchases

**Secondary:** Inventory Managers, IT/Facilities Managers who submit requests

---

## Status

Early-stage — active development. Core platform is functional with real database integration. AI recommendation engine and production deployment in progress.

---

## Team

Built by [Methru Bandara](https://www.methrubandara.com/) and [Abhilash Gundala](https://www.notion.so/Abhi-s-Portfolio-1fff6066794880ff9193fc847cf99386)

---

## Disclaimer

This repository is the proprietary property of Spendvia LLC. The source code, documentation, and all associated materials are confidential and not intended for public use, distribution, or reproduction. Unauthorized copying, modification, or distribution of any part of this project is strictly prohibited. All rights reserved.
