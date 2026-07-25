# youtube-trend-analysis-sheets
# YouTube India — Trending Video Analytics Dashboard

An end-to-end analytics project built entirely in Google Sheets from raw data cleaning to an interactive KPI dashboard analyzing what drives views vs. engagement across content categories, publish days, and channels in India's YouTube trending data.

**[View the live dashboard](https://docs.google.com/spreadsheets/d/1eHrM18mCumhuzPKRoGN0Au7XEy96TtxBlNxqlKjsAQg/edit?usp=sharing)**

---

## Dashboard Preview

![Dashboard Screenshot](YouTube%20Trend%20Analysis%20Dashboard.png)

---

## Overview

This project analyzes 37,000+ trending YouTube videos from India (Kaggle's "Trending YouTube Video Statistics" dataset) to answer a core question: **does the content that gets the most views also drive the most engagement and what does that mean for publishing strategy?**

The entire workflow data cleaning, transformation, analysis, hypothesis testing, and dashboard design was built natively in Google Sheets, without external BI tools.

---

## Tools & Skills Used

- **VLOOKUP** — mapped raw numeric category IDs to readable category names via a lookup table
- **QUERY** — replicated SQL-style `GROUP BY` / `ORDER BY` aggregation for category and weekday-level analysis
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

- Gaming leads in average views while Science & Technology leads in average engagement rate. This shows it is not necessary that a category driving more views drive the most engagement rate.
- Thursday has highest avg engagement rate followed by Friday, possible because these are pre-weekend days seeking content though it needs further data to confirm this. However, it is also notable that the highest avg view day is Wednesday. This shows peak viewership and engagement do not always align.
- Entertainment Category has the highest video volume, while Science & Technology is at the bottom (1.46%) category in Top 10 but it shows notably higher engagement rate suggesting smaller categories has high retention rate due to niche audiences.
- T-series is dominating the channel leaderboard by total views with more than 2Billions, suggesting that it has more trending appearances rather than one single viral video
- Like ratio and engagement rate shows positive but moderate correlation (r=0.35). It suggests that well-received videos (most liked videos) tend to generate more engagement as well.
- Saturday and Sunday show among the lowest average views, and engagement rate of the week, contrary to an assumption that weekend leisure time will boost the video performance and virality.


## Recommendations

- Prioritizing Gaming & Entertainment Category would more profitable if one wants reach as they consistently draw the highest average views.
- For Community/Loyalty, one should explore less-saturated categories like Science & Technology as it has higher engagement rates, suggesting that it has a smaller but more invested audience.
- Creators should decide which metrics matter to them more before deciding publish date because peak engagement and peak viewership have different days.
- As entertainment has 44.7% share of trending videos, it worth tracking category concentration over time to look if its structural bias or algorithmic in what gets promoted to trending.
- For Channel growth, one should consider consistent high frequency publishing (as demonstrated by T-Series) rather than relying on one viral video.
- Tracking engagement rate and like ratio separately as they have moderate correlation, it shows the possibility that a video might be well-liked but might not have higher engagement rate.


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
