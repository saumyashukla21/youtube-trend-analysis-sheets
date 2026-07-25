# youtube-trend-analysis-sheets
# YouTube India — Trending Video Analytics Dashboard

An end-to-end analytics project built entirely in Google Sheets from raw data cleaning to an interactive KPI dashboard analyzing what drives views vs. engagement across content categories, publish days, and channels in India's YouTube trending data.

**[View the live dashboard →](PASTE_YOUR_SHAREABLE_SHEET_LINK_HERE)**

---

## Dashboard Preview

![Dashboard Screenshot](dashboard-screenshot.png)

*(Replace `dashboard-screenshot.png` with your actual uploaded screenshot filename)*

---

## Overview

This project analyzes 37,000+ trending YouTube videos from India (Kaggle's "Trending YouTube Video Statistics" dataset) to answer a core question: **does the content that gets the most views also drive the most engagement — and what does that mean for publishing strategy?**

The entire workflow — data cleaning, transformation, analysis, hypothesis testing, and dashboard design — was built natively in Google Sheets, without external BI tools.

---

## Tools & Skills Used

- **VLOOKUP** — mapped raw numeric category IDs to readable category names via a lookup table
- **QUERY** — replicated SQL-style `GROUP BY` / `ORDER BY` aggregation for category- and weekday-level analysis
- **Pivot Tables** — cross-checked QUERY results and powered dashboard charts
- **CORREL()** — tested statistical relationships (title length vs. views, like ratio vs. engagement rate)
- **Conditional Formatting** — color-scaled views column to surface top/bottom performers at a glance
- **Combo, Pie, and Bar Charts** — dual-axis visualizations comparing views against engagement
- **IFERROR / data cleaning** — handled edge cases like division-by-zero in calculated ratios

---

## Approach

1. **Import & clean** — imported raw CSV data, mapped category IDs via VLOOKUP, extracted publish day-of-week
2. **Calculate metrics** — built engagement rate `(likes+comments)/views`, like ratio `likes/(likes+dislikes)`, and title length as derived columns
3. **Aggregate & analyze** — used pivot tables and QUERY to compare performance across categories, weekdays, and channels
4. **Test hypotheses** — ran correlation analysis to check whether title length or sentiment (like ratio) actually predict performance
5. **Visualize** — built a 4-chart dashboard (category combo chart, weekday combo chart, category share pie chart, channel leaderboard) with KPI summary cards
6. **Interpret** — translated every chart into a written insight and a corresponding recommendation

---

## Key Insights

- Gaming leads in average views while Science & Technology leads in average engagement rate — showing that a category driving more views doesn't necessarily drive the most engagement.
- Thursday shows the highest average engagement rate, followed by Friday — possibly because these are pre-weekend days when viewers seek out content, though this would need further data to confirm. Notably, Wednesday has the highest average views, showing that peak viewership and peak engagement don't always align.
- Entertainment has the highest video volume, while Science & Technology sits at the bottom (1.46%) among the top 10 categories — yet it shows a notably higher engagement rate, suggesting smaller categories may retain more engaged, niche audiences.
- T-Series dominates the channel leaderboard with over 2 billion total views — driven by consistent, frequent trending appearances rather than a single viral video.
- Like ratio and engagement rate show a positive but moderate correlation (r = 0.35), suggesting well-received videos tend to generate somewhat more engagement, though the two aren't the same thing.
- Saturday and Sunday show among the lowest average views and engagement rates of the week — contrary to the assumption that weekend leisure time would boost video performance.
- Title length showed virtually no correlation with views (r = -0.05), indicating that other factors — category, timing, thumbnail — likely matter far more than how long a title is.

## Recommendations

- Gaming and Entertainment are the strongest choices for maximizing reach, as they consistently draw the highest average views.
- For community/loyalty, explore less-saturated categories like Science & Technology, which show higher engagement rates despite smaller audiences.
- Creators should decide which metric matters most to them before choosing a publish day, since peak viewership and peak engagement fall on different days.
- Given Entertainment's 44.7% share of trending videos, it's worth tracking category concentration over time to assess whether this reflects a structural or algorithmic bias.
- For channel growth, consider consistent, high-frequency publishing (as demonstrated by T-Series) rather than relying on a single viral video.
- Track engagement rate and like ratio separately, as they show only a moderate correlation — a video can be well-liked without necessarily having a higher engagement rate.

---

## Dataset

- **Source:** [Kaggle — Trending YouTube Video Statistics](https://www.kaggle.com/datasets/datasnaek/youtube-new)
- **Scope:** India (IN) trending videos
- **Size:** ~37,000 rows

---

## Notes & Limitations

- This dataset reflects a fixed historical time window and one country only — findings may not generalize to other regions or time periods.
- The weekday-timing explanation (pre-weekend engagement) is a plausible hypothesis, not a confirmed causal finding — would need additional data (e.g., time-of-day, viewer demographics) to validate.
- Engagement rate is mechanically lower for videos with comments disabled, since comment count is part of the formula — a known limitation of this specific metric.
