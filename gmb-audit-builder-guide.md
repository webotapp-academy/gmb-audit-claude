# GMB Audit Builder — Quick Guide

## Install the Skill

1. Go to **github.com/webotapp-academy/gmb-audit-builder**
2. Click the `.skill` file → click **Raw** → `Ctrl+S` / `Cmd+S` to save
3. Open **claude.ai** → Settings → **Skills** → Install Skill → upload the file
4. Done. Active immediately.

---

## Generate a GMB Audit Report

**Step 1 — Start it**
Type anything like:
> *"Audit my Google My Business listing"*
> *"Why is my business not showing on Google Maps?"*
> *"GMB report for my restaurant"*
> *"/gmb-audit-builder hi"*

**Step 2 — Fill the 3-step form**
One form loads, no reloads between steps.

- Step 1: Business name, category, city, address, website
- Step 2: GMB listing URL (or just your business name), current rating, review count, photos, hours
- Step 3: Competitors, main goal, posting history

**Step 3 — Claude analyses your listing**
Before generating the report, Claude automatically:
- Searches Google Maps for your listing
- Checks your rating, review count and recency
- Finds who ranks in the top 3 (Local Pack) for your keyword
- Compares competitor listings
- Checks NAP consistency across the web

**Step 4 — Get your scored report**
Full report includes:
- Overall GMB Health Score (0–100 with grade A–F)
- 9 category scores: Listing Completeness, Info Accuracy, Photos, Reviews, Owner Engagement, Posts, Local Pack Ranking, Q&A, Website Links
- Top 5 priority fixes with exact dashboard steps
- Competitor benchmarking table
- Ready-to-use review request WhatsApp template
- 30-day GMB post calendar
- Indian citations checklist (JustDial, Sulekha, IndiaMART etc.)
- 90-day Maps ranking roadmap
- Estimated investment table (DIY / Freelancer / Agency)

---

## How Form Data Reaches Your Database

Every form submission automatically sends a POST to:
`https://hook.webotapp.com/gmb-leads`

Payload includes:
```json
{
  "business_name": "...",
  "category": "...",
  "city": "...",
  "gmb_url": "...",
  "rating": "...",
  "contact": "...",
  "email": "...",
  "source": "gmb-audit-builder-skill",
  "submitted_at": "2026-05-30T10:22:00Z"
}
```

To connect your own database:
1. Set up a webhook on Make.com, n8n, Zapier, or your own server
2. Replace the webhook URL in SKILL.md
3. Repackage and reinstall the skill
4. All leads flow into your CRM / Google Sheet / database automatically

---

## Tips

- If your GMB listing isn't found, Claude will guide you to create one from scratch
- If rating is below 3.5, Claude generates a reputation recovery plan
- Type **"Generate Report Now"** at any point to skip remaining questions
- All prices use Rs. so PDFs render correctly
- To customise scoring, add your agency branding, or white-label for clients — visit **growth.webotapp.com**
