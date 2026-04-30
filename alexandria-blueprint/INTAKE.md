# Project Intake Template
## Model: Alexandria Business Blueprint

This template is used to scope and build a **stakeholder-perspective web application** —
a rich, informational site where the same business content is experienced differently
depending on who is viewing it.

Use this intake when a client wants to:
- Present a business plan, pitch, or prospectus
- Serve multiple audiences from a single source of truth
- Create a GitHub Pages site backed by a Supabase content schema

---

## 1. Project Identity

```
Project / Business Name:
Tagline (one sentence):
Industry / Sector:
Stage (Concept / Pre-Revenue / Operating / Scaling):
Primary Language:
Desired URL / repo name:
Target Launch Date:
```

---

## 2. The Business (Source of Truth Content)

All content below becomes the shared database that every stakeholder views through their own lens.

### 2a. Mission & Philosophy
```
Why does this business exist?
What core belief drives the founders?
What problem does it solve?
What does success look like in 5 years?
```

### 2b. Business Model
```
How does the business make money?
Revenue streams (list each):
Pricing structure (if applicable):
Key partnerships or distribution channels:
Operating cost structure summary:
```

### 2c. The Team (Founders)
```
Founder 1 — Name, Role, Background, Personal Why:
Founder 2 — Name, Role, Background, Personal Why:
Founder 3 — Name, Role, Background, Personal Why:
(Add more as needed)
```

### 2d. Milestones & Expectations
```
Phase 1 (Month 1–6): Goals + Deliverables
Phase 2 (Month 7–12): Goals + Deliverables
Phase 3 (Year 2+): Goals + Deliverables
Key metrics the business will track:
```

### 2e. Risks
```
Risk 1 — Description | Likelihood | Mitigation strategy
Risk 2 — Description | Likelihood | Mitigation strategy
Risk 3 — Description | Likelihood | Mitigation strategy
(Repeat for all known risks)
```

### 2f. Rewards & Upside
```
Best-case scenario (financial):
Best-case scenario (impact):
Projected growth range (conservative / moderate / optimistic):
Any exit or liquidity scenarios:
```

### 2g. Community & Social Impact
```
Local employment potential:
Environmental commitments:
Community investment plans:
Philanthropic or non-profit components:
```

---

## 3. Stakeholder Personas

For each persona that will view this application, complete the following.
Every field shapes how content is framed and highlighted for that audience.

### Persona Template (copy for each)
```
Persona ID (slug, e.g. private_investor):
Display Label:
Icon / Emoji:
Tagline (shown on selection screen):
Accent Color (hex):

What does this persona MOST care about?
What is their primary fear or objection?
What do they want to walk away knowing?
What is the desired call-to-action for this persona?
  (e.g. Schedule a call / Make a donation / Sign a contract)

Section emphasis — for each content section, note:
  - Any sections to HIDE for this persona
  - Any sections to FEATURE prominently
  - Persona-specific headline for each section (if different from default)
  - Persona-specific summary paragraph (1–3 sentences)
  - Badge labels for highlighted facts (e.g. "Your ROI", "Key Risk", "Your Impact")
```

### Required Personas (minimum)
- [ ] Founder (repeat per founder if perspectives differ)
- [ ] Private Investor
- [ ] Philanthropic Donor
- [ ] Potential Client
- [ ] Active Client
- [ ] Local Community Member

---

## 4. Content Sections

Default navigation spine. Mark any that should be renamed, removed, or added.

| Section ID | Default Title | Include? | Custom Title |
|---|---|---|---|
| `philosophy` | Mission & Philosophy | ✅ | |
| `model` | Business Model | ✅ | |
| `team` | The Founding Team | ✅ | |
| `expectations` | Milestones & Timeline | ✅ | |
| `risks` | Risks & Mitigations | ✅ | |
| `rewards` | Upside & Rewards | ✅ | |
| `community` | Community Impact | ✅ | |
| `next_steps` | What's Next For You | ✅ | |

---

## 5. Design & Branding

```
Brand colors (primary, secondary, accent):
Font preferences (if any):
Existing logo? (Y/N — attach if yes)
Tone of voice (e.g. formal, warm, bold, technical):
Any visual references or inspiration sites:
Dark mode / light mode preference:
```

---

## 6. Technical Configuration

```
Supabase project to use (existing / new):
Schema name (default: alexandria):
GitHub username or org for Pages deployment:
Repo name:
Custom domain? (Y/N — if yes, domain name):
Anonymous visitor tracking needed? (Y/N)
Interest/lead capture form needed? (Y/N)
Password or gated access needed? (Y/N)
```

---

## 7. Content Delivery

Specify how the client will provide content for each section:

```
Philosophy/Mission copy: [ ] Client writes | [ ] We draft from interview
Business model detail:   [ ] Client writes | [ ] We draft from interview
Founder bios:            [ ] Client writes | [ ] We draft from interview
Risk register:           [ ] Client writes | [ ] We draft from interview
Milestone plan:          [ ] Client writes | [ ] We draft from interview
Photos / headshots:      [ ] Provided | [ ] Stock | [ ] Not needed
```

---

## 8. Stakeholder Interaction Notes

```
Should personas be able to leave their contact info? (Y/N)
Should visitor sessions be tracked anonymously? (Y/N)
Should the client receive lead notifications? (Y/N — if yes, email):
Should content be editable via a CMS/admin panel? (Y/N)
Is a print / PDF export version needed? (Y/N)
```

---

## 9. Scope Confirmation Checklist

Before development begins, confirm all items are complete:

- [ ] All persona definitions filled out (Section 3)
- [ ] All section copy provided or interview scheduled (Section 7)
- [ ] Branding assets delivered (Section 5)
- [ ] Supabase project confirmed (Section 6)
- [ ] GitHub repo name confirmed (Section 6)
- [ ] Launch date agreed (Section 1)
- [ ] Lead capture / CTA destinations confirmed (Section 8)

---

## 10. Deliverables (What We Build)

Upon intake completion, the following will be produced:

1. `seed.sql` — Supabase `alexandria` schema with all content + persona data
2. `index.html` — Stakeholder selection landing page
3. `blueprint.html` — Dynamic content experience
4. `app.js` — Supabase client + rendering engine
5. `style.css` — Base styles + per-persona CSS custom properties
6. GitHub Pages deployment
7. Supabase RLS policies for public read access

---

*Template version: 1.0 — modeled from the Alexandria Blueprint project, April 2026.*
