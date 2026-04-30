# Analytix Intake Schema Reference

Live in Supabase project: `Web App Development Course - Supabase/Netlify`
Schema: `analytix`

---

## Tables

| Table | Purpose | RLS |
|---|---|---|
| `intake_sessions` | One row per prospect interaction; tracks tier + status | anon insert, token-based update |
| `intake_contacts` | Step 1: Who they are | anon insert |
| `intake_business` | Step 2: Their business | anon insert |
| `intake_project_scope` | Step 3: What they want built | anon insert |
| `intake_content_readiness` | Step 4: What assets they have | anon insert |
| `intake_notes` | Step 5: Open-ended responses | anon insert |

## View

`analytix.intake_summary` — Joins all 6 tables into one flat row per session.
Use this for admin review and BI exports.

## Enums

| Type | Values |
|---|---|
| `service_tier` | `discovery`, `consultation` |
| `intake_status` | `started`, `submitted`, `reviewed`, `converted`, `archived` |
| `project_type` | `business_blueprint`, `training_portal`, `service_portal`, `community_site`, `custom` |
| `industry_sector` | `landscaping`, `education`, `nonprofit`, `health_wellness`, `food_beverage`, `retail`, `professional_services`, `real_estate`, `tech`, `other` |
| `business_stage` | `concept`, `pre_revenue`, `operating`, `scaling` |

---

*Migration applied: 2026-04-30*
