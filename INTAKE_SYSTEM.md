# 207 Analytix — Intake Form System

The intake form is a **front-end web application** that guides prospects through a structured
onboarding questionnaire. Every submission is stored as owned data in Supabase regardless
of whether it converts to a paid project.

---

## Service Tiers

### Tier 1 — Discovery (Free)
- Prospect fills out the 5-step intake form on their own
- No consultation time billed
- Data captured: contact info, business identity, project scope, content readiness, open notes
- Purpose: Lower the barrier to entry; increase pipeline conversion probability
- Value to 207 Analytix: Market intelligence, industry trends, lead scoring, content ideas

### Tier 2 — Consultation (Billable)
- Prospect engages directly with a 207 Analytix team member
- Intake form serves as pre-work / agenda for the session
- Interview time is billed at the consulting rate
- Output: A detailed, reviewed intake record + scoped project proposal
- Value to 207 Analytix: Deeper data, stronger conversion, client relationship established

---

## Data Strategy

> "The information to be parsed will improve our data positioning whether we charge for it or not."

Every completed intake — paid or free — contributes to:

| Data Asset | How It's Built | Future Use |
|---|---|---|
| **Industry Index** | `industry_sector` + `business_stage` + `budget_range` | Pricing benchmarks, market sizing |
| **Lead Scoring Model** | `completed_steps`, `has_branding_assets`, `interview_available` | Prioritize follow-up |
| **Content Readiness Benchmark** | `intake_content_readiness` table | Set accurate project timelines |
| **Conversion Funnel** | `intake_status` progression | Identify where prospects drop off |
| **Referral Source Map** | `referral_source` + `utm_campaign` | Know which channels drive real clients |
| **Project Type Demand** | `project_type` distribution | Inform service offering evolution |
| **Geographic Clustering** | `city` + `state` | Local vs. remote client segmentation |
| **Challenge Library** | `biggest_challenge` (free text) | Fuel sales copy, blog content, service positioning |

---

## Form Architecture (5 Steps)

```
Step 1 — Who Are You?         → analytix.intake_contacts
Step 2 — Your Business        → analytix.intake_business
Step 3 — Your Project         → analytix.intake_project_scope
Step 4 — Content Readiness    → analytix.intake_content_readiness
Step 5 — In Your Own Words    → analytix.intake_notes
```

Each step saves independently (no data lost if the user drops off).
A `session_token` cookie persists the session across steps and devices.

---

## Key Design Principles

- **Progressive disclosure**: Each step only asks what's needed at that moment
- **No login required**: Anonymous inserts via Supabase anon key + RLS
- **Resumable**: Session token in localStorage allows returning to an incomplete form
- **Tier selection at start**: Prospect chooses Discovery or Consultation before beginning
- **Save on blur**: Each field auto-saves so nothing is lost
- **Completion tracking**: `completed_steps[]` array updated after each step

---

## Tech Stack

| Layer | Tool |
|---|---|
| Front end | HTML/CSS/JS on GitHub Pages |
| Database | Supabase (`analytix` schema) |
| Auth | None — anonymous inserts with RLS |
| Session | `session_token` via localStorage |
| Admin view | Supabase Table Editor + `intake_summary` view |
| Notifications | Supabase webhook → email on `status = submitted` |

---

## Admin Workflow

When a prospect submits:
1. `status` updates from `started` → `submitted`
2. Supabase webhook fires → 207 Analytix receives email notification
3. Admin reviews `intake_summary` view in Supabase dashboard
4. Sets `status` to `reviewed` after reading
5. Marks `converted_at` when project is purchased
6. Archives cold leads with `status = archived`

---

## Metrics to Track (from `intake_summary` view)

- Intake start rate (sessions created)
- Intake completion rate (all 5 steps done)
- Discovery → Consultation conversion rate
- Intake → Project purchase conversion rate
- Average time from intake to conversion
- Most common `biggest_challenge` themes
- Most in-demand `project_type` by quarter
