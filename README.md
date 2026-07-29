# 📈 Performance Marketing Analytics
**Power BI Analytics Project | Power BI · Power Query · DAX · Meta Ads · TikTok Ads · Creative Performance Analysis**

---

## 📌 Project Overview

Paid social teams can watch a dashboard full of green metrics — solid CTR, decent spend efficiency — and still not know why revenue isn't moving. Clicks don't always mean customers, and a "good-looking" creative can quietly be burning budget the whole time.

This project puts me in the seat of a **Performance Marketing Data Analyst** for a fast-growing feminine wellness brand running paid campaigns across **Meta** and **TikTok**, as part of the **Data Analyst Playbook (Cohort 2)** challenge. The brand was seeing a familiar but frustrating pattern: some campaigns generated clicks but no sales, some ads looked engaging but never scaled, and performance swung wildly from creative to creative with no clear explanation.

> **The goal:** turn 90,000 rows of creative-level ad data into a dashboard that tells the brand which platform actually performs better, which creative attributes drive real conversions (not just clicks), where users are dropping out of the funnel, and which creatives are fatigued versus ready to scale.

**Business questions guiding the analysis:**
- Which platform is truly performing better — not just on CTR, but across deeper metrics?
- Which creative attributes are consistently linked to high CTR, CVR, and ROAS?
- What creative combination (hook type, angle, copy tone, UGC) produces the best outcomes?
- Which campaigns or creatives *look* successful but are actually failing?
- Where in the funnel are users being lost — before the click, during the video, or after the click?
- Which creatives show signs of fatigue, and which are worth scaling?

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Power BI | Data modeling, DAX measures, dashboard build |
| Power Query | Data type validation, data quality checks, transformation |
| DAX | Twelve core KPI measures across spend, funnel, video, and fatigue metrics |
| Power BI Slicers | Platform (Meta/TikTok) and UGC flag filtering across all four pages |

---

## 📂 Repository Structure

```
PerformanceMarketing_Analytics/
│
├── assets/
│   ├── dashboard_overview.png
│   ├── pg_2.png
│   ├── pg_3.png
│   └── pg_4.png
│
├── data/
│   └── marketing_dataset.csv
|
├── Performance Marketing Analytics.pbix
|
└── README.md
```

---

## ⚙️ Project Pipeline

```
Phase 1 → Data Loading & Understanding (90,000 rows, 46 columns, single flat table)
Phase 2 → Data Quality Checks (Power Query — types, nulls, boolean flags, distributions)
Phase 3 → DAX Measures (12 measures across spend, funnel, video, fatigue)
Phase 4 → Dashboard Design — 4 pages (Funnel, Drivers, Data Traps, Attention)
Phase 5 → Insights & Recommendations
```

---

## 📊 Headline KPIs

| Metric | Value |
|---|---|
| Total Spend | $227.48M |
| Total Impressions | 2.29bn |
| Total Clicks | 228M |
| Total Purchases | 22.5M |
| Average ROAS | 3.25x |
| Average CTR | 4.24% |
| Average CVR | 5.25% |
| Average CPA | $77.63 |

---

## 🎯 Page 1 — What Is Really Driving Performance?
**Question:** *Which creative attributes are consistently linked to high CTR, CVR, and ROAS — and what combination wins?*

![Performance](<assets/dashboard_overview.png>)

- **Emotional** hooks lead on CVR (5.26%) and **Authority** hooks lead on hook rate (35.14%) — but the gaps between hook types are narrow. Hook type alone isn't the lever; it's the *combination* of hook + angle + tone that moves the needle.
- **Pain Point** and **Education** angles lead on ROAS (3.27x and 3.26x). **Social Proof** has the highest CVR (5.27%) but the *worst* ROAS (3.22x) — it converts, but at a cost that erodes return, likely due to pricier social-proof production formats.

**Top creative combinations by ROAS:**

| Hook Type | Creative Angle | Copy Tone | UGC | Avg CTR | Avg CVR | Avg ROAS |
|---|---|---|---|---|---|---|
| Curiosity | Education | Bold | No | 4.73% | 5.38% | **3.55x** |
| Authority | Transformation | Professional | Yes | 4.18% | 5.04% | 3.42x |
| Curiosity | Transformation | Friendly | Yes | 4.23% | 5.32% | 3.42x |
| Curiosity | Pain Point | Friendly | No | 4.29% | 5.07% | 3.37x |
| Problem-Solution | Transformation | Urgent | Yes | 4.17% | 5.22% | 3.37x |
| Emotional | Education | Bold | Yes | 4.22% | 5.07% | 3.36x |

**Insight:** The ROAS-vs-fatigue scalability scatter shows a clear cluster of top creatives sitting at moderate fatigue (~40–45) with strong ROAS — these are the safest to scale further. Creatives pushing past fatigue scores of 50+ show declining ROAS, marking them as candidates for refresh rather than continued spend.

---

## 🕵️ Page 2 — Find the Lies in the Data
**Question:** *Which campaigns or creatives appear successful but are actually failing?*

- **211 creatives** flagged as CTR traps and **195** as CPC traps — ads that look like they're winning on the surface-level metric but aren't converting efficiently.
- **Social Proof** again stands out: highest CVR (5.27%) but lowest ROAS (3.22x) among all creative angles — proof that conversions are happening at a cost that erodes overall return.
- **Pain Point** and **Education** drive the highest conversion *value*, while **Social Proof** attracts attention cheaply but returns the least.

**Insight:** CTR and CVR alone are misleading success signals in this account. A creative can look like a top performer on attention metrics while quietly being one of the most expensive angles to convert — ROAS is the metric that exposes the gap between "engaging" and "profitable."

---

## 👀 Page 3 — Attention vs Engagement vs Conversion
**Question:** *Where in the funnel are users being lost — before the click, during the video, or after the click?*

**Attention funnel (per 1,000 impressions):**

| Stage | Volume |
|---|---|
| Impressions | 1,000 |
| Hook (scroll stop) | 351 |
| Hold (3 sec) | 158 |
| Mid-video (50%) | 97 |
| Completion | 72 |
| Click (CTR) | 42 |

- The **biggest leak is mid-video**: hold rate drops from **45.0%** (3 seconds) to **27.6%** (50% mark) — a 40% drop-off among viewers who were already engaged. This is a narrative problem, not a landing page problem.
- Only **20.5%** of viewers reach completion, meaning most never see the CTA at all.
- Platform differences here are marginal: TikTok edges Meta on completion (20.52% vs 20.46%) and CTR (4.25% vs 4.23%) — likely reflecting TikTok's algorithm serving video to already-engaged users rather than the creative itself being stronger.

**Insight:** Video retention — not ad targeting or landing page experience — is where the funnel bleeds. Fixing mid-video narrative structure (or adding an earlier CTA) has more upside than any targeting or bidding change.

---

## 🧭 Page 4 — Funnel Breakdown: Which Platform Is Really Winning?
**Question:** *Which platform is truly performing better — not just on CTR, but across deeper metrics?*

- Meta generates **2.4x more volume** at every funnel stage than TikTok, but the platforms are near-identical on efficiency: TikTok's CTR (10.01%) edges out Meta's (9.93%), while Meta's CVR (9.91%) edges out TikTok's (9.78%).
- End-to-end, the funnel is healthy: **9.96% impression→click** and **9.87% click→purchase**. Neither top-of-funnel nor post-click conversion is the bottleneck.
- By creative angle, **Social Proof (0.9881%)** and **Pain Point (0.9847%)** convert impressions to purchases most efficiently; **Transformation (0.9734%)** is the weakest — it drives broad awareness but lower-intent traffic.
- **Education** is the volume trap: it pulls in 570M impressions (25% of total spend) but posts the *lowest* imp-to-purchase rate of any angle — attracting browsers, not buyers.

**Insight:** Scaling spend on Meta increases volume but doesn't improve efficiency — growth has to come from creative and angle optimization, not a platform shift. A flat 36-month ROAS (3.19x–3.31x) with no Q4 seasonal peak also shows the brand is leaving seasonal budget efficiency on the table.

---

## 🧱 Data Modeling

This marketing data arrived as a **single pre-joined creative-level table**, no star schema was required. Modeling effort went into validating and organizing the flat table so it could support multi-dimensional slicing across platform, creative attributes, hook categories, and fatigue stages.

**Schema Structure**
- **Primary Table:** `marketing_dataset` — 90,000 rows, 46 columns spanning creative, platform, and performance dimensions
- **Date Intelligence:** Week Number, Month, Quarter, and Year columns were already present and used directly for time-series analysis
- **Calculated Columns:** None required — all necessary dimensions existed in the raw data

**Analytical Segmentation**

| Dimension | Values |
|---|---|
| platform | Meta, TikTok |
| hook_type | Curiosity, Emotional, Authority, Problem-Solution |
| creative_angle | Education, Pain Point, Social Proof, Transformation |
| copy_tone | Bold, Friendly, Professional, Urgent |
| ad_format | Video, Image, Carousel |
| has_ugc | 0 (Non-UGC), 1 (UGC) |

---

## 🧮 DAX Measures

Twelve core DAX measures were created and stored in a dedicated `_Measures` table:

| Measure | DAX Formula | Purpose |
|---|---|---|
| Total Spend | `SUM(marketing_dataset[spend])` | Total ad spend across all records |
| Total Purchases | `SUM(marketing_dataset[purchases])` | Total conversions |
| Total Impressions | `SUM(marketing_dataset[impressions])` | Total ad impressions |
| Avg ROAS | `AVERAGE(marketing_dataset[roas])` | Average return on ad spend |
| Avg CTR | `AVERAGE(marketing_dataset[ctr])` | Average click-through rate |
| Avg CVR | `AVERAGE(marketing_dataset[cvr])` | Average conversion rate |
| Avg CPA | `AVERAGE(marketing_dataset[cpa])` | Average cost per acquisition |
| Avg CPC | `AVERAGE(marketing_dataset[cpc])` | Average cost per click |
| Avg Hook Rate | `AVERAGE(marketing_dataset[hook_rate])` | Scroll-stop rate |
| Avg Hold Rate 50% | `AVERAGE(marketing_dataset[hold_rate_50pct])` | Mid-video retention |
| Avg Completion Rate | `AVERAGE(marketing_dataset[completion_rate])` | Full video watch rate |
| Avg Fatigue Score | `AVERAGE(marketing_dataset[fatigue_score])` | Creative burnout indicator |

---

## 🧹 Data Transformation

All transformations were performed in **Power Query** within Power BI before loading the data model:

- Verified data types across all 46 columns — confirmed numeric fields (CTR, CVR, ROAS, CPA, fatigue_score) were correctly typed as decimals
- Validated `platform` values were limited to 'Meta' and 'TikTok' with no null entries
- Confirmed boolean flags (`has_ugc`, `has_celebrity`, `has_before_after`, `has_clinical_proof`) contained only 0/1 integer values
- Reviewed the `fatigue_score` distribution (0–100) before using it as a quadrant axis in the scalability scatter chart
- Confirmed `week_number`, `month`, `quarter`, and `year` were correctly populated for time-series analysis
- No missing values or referential integrity issues were detected — the dataset loaded cleanly into the model

---

## 🎯 What I Focused On

| Focus Area | Approach |
|---|---|
| Metric selection | Went beyond CTR to ROAS, CVR, and fatigue score to expose "fake" winners |
| Funnel diagnosis | Broke the funnel into pre-click, mid-video, and post-click stages to isolate the real leak point |
| Creative combinations | Cross-tabbed hook × angle × tone × UGC instead of analyzing attributes in isolation |
| Interactivity | Platform and UGC slicers on every page for self-serve stakeholder exploration |
| Storytelling | Each page answers one specific business question rather than displaying metrics for their own sake |

---

## 💡 Recommendations

1. **Reallocate budget from Education toward Pain Point and Social Proof angles** for imp-to-purchase efficiency, while capping Education spend given its high volume, low intent-to-purchase profile.
2. **Fix mid-video retention** (45% → 27.6% drop) before touching targeting or landing pages — this is the largest single leak in the funnel.
3. **Scale the identified low-fatigue, high-ROAS creative combinations** (e.g. Curiosity + Education + Bold, No UGC) rather than spreading spend evenly across all creatives.
4. **Audit the 211 CTR-trap and 195 CPC-trap creatives** individually — these are actively misleading performance reviews if judged on surface metrics alone.
5. **Introduce seasonal budget shifts** (e.g. Nov–Feb) — the current flat 36-month ROAS suggests the brand isn't capturing available seasonal upside.

---

## 📄 Deliverables

| Deliverable | Description |
|---|---|
| `Performance Marketing Analytics.pbix` | Full Power BI file with data model, DAX measures, and dashboard |
| `data/marketing_dataset.csv` | 90,000-row creative-level ad performance dataset |
| `assets/*.png` | Screenshots of all four dashboard pages |
| `README.md` | Full project documentation |

---

## 👤 Author

**Lawal Yusuf Gbolahan**
Data Analyst · Analytical Engineering

*An end-to-end Power BI analysis of Meta and TikTok creative-level ad performance data — from raw spend and funnel metrics to a fully interactive performance marketing dashboard.*
