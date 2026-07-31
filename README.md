# Peak Performance PT — Client Dashboard

A live, functional weekly dashboard for Sarah Mitchell (Peak Performance PT) to check her
lead-gen and booking performance at a glance.

Built for the Undeniable Mentoring "Lead Automation & Systems Engineer" practical test — Task 3.

## What it shows

- **System health banner** — a single green/amber/red readout so a non-technical owner knows
  instantly whether anything needs attention, plus a plain-English reason why.
- **KPI cards** — leads this week/month/all-time, discovery calls booked vs. the monthly target,
  clients won.
- **Pipeline funnel** — contacts at each of the 7 acquisition stages, with the conversion rate
  between each stage and the weakest link flagged automatically.
- **Weekly trend** — leads captured vs. calls booked over the last 8 weeks.

## Stack

Single-file static HTML/CSS/JS + [Chart.js](https://www.chartjs.org/) via CDN. No build step,
no backend — deliberately minimal so it deploys in seconds and is trivial to hand off or embed
inside a GHL custom page later.

## Data

All numbers live in one `DATA` object at the top of the `<script>` in `index.html`. Every KPI,
the health-check thresholds (green ≥80% of goal, amber 50–79%, red <50%), the funnel bars, and
the trend chart are derived from that object — swap it for a live feed (GHL API / Google Sheets)
without touching the rest of the app.

## Run locally

```bash
python3 -m http.server 8787
# open http://localhost:8787
```

No dependencies to install.
