# 📊 Social Media Ad Campaign Performance Analytics

> An end-to-end **Power BI** dashboard analyzing Meta (Facebook & Instagram) ad campaign performance — built on a **Star Schema** data model with dynamic DAX measures, audience segmentation, and multi-platform KPI tracking.

🔗 **[View Live Dashboard](https://app.powerbi.com/groups/me/reports/a598e58c-a636-4eaa-9510-ae8a25e6dddb/9777a38c9b4384394b2b?experience=power-bi)**

---

## 🗺️ Dashboard Preview

[![Social Media Campaign Dashboard](https://github.com/ChanakyaSreeHarshaG/Social_Media_Ad_Campaign_Dashboard/raw/main/Resources/Social_media_campaign_dashboard.png)](https://github.com/ChanakyaSreeHarshaG/Social_Media_Ad_Campaign_Dashboard/blob/main/Resources/Social_media_campaign_dashboard.png)

---

## 🎬 Dashboard Walkthrough
[![Social Media Campaign Dashboard Walkthrough](https://github.com/ChanakyaSreeHarshaG/Social_Media_Ad_Campaign_Dashboard/blob/main/Resources/social_media_campaign_rec.gif)]
(https://github.com/ChanakyaSreeHarshaG/Social_Media_Ad_Campaign_Dashboard/blob/main/Resources/social_media_campaign_rec.gif)

---

## 📖 Project Overview

This project demonstrates end-to-end **Business Intelligence** skills — from data modeling to interactive reporting — for a simulated Meta ads environment spanning Facebook and Instagram.

**What's built:**

- A clean **Star Schema** data model with 5 relational tables
- **10+ DAX measures** for marketing KPIs (CTR, Engagement Rate, Conversion Rate, Purchase Rate)
- A fully interactive Power BI dashboard with slicers, drill-downs, and dynamic measures
- Audience insights by gender, age, country, and interests
- Creative performance comparison across ad types (Carousel, Image, Stories, Video)

---

## 🏗️ Data Architecture — Star Schema

[![Data Model](https://github.com/ChanakyaSreeHarshaG/Social_Media_Ad_Campaign_Dashboard/raw/main/Resources/Data_Modeling.png)](https://github.com/ChanakyaSreeHarshaG/Social_Media_Ad_Campaign_Dashboard/blob/main/Resources/Data_Modeling.png)

| Layer | Table | Type | Description |
|---|---|---|---|
| 📋 Dimension | `campaigns` | Dim | Campaign metadata — name, budget, start/end dates, duration |
| 📋 Dimension | `ads` | Dim | Ad-level details — platform, type, target age group & gender |
| 📋 Dimension | `users` | Dim | User profile — age, gender, country, interests |
| 📅 Date | `Calendar Table` | Date Dim | Time intelligence — Day, Week, Month, Day Name, Week Number |
| 📊 Fact | `ad_events` | Fact | Event-level grain — impressions, clicks, shares, purchases, comments |

**Relationships:**
- `campaigns` → `ads` (1 : *)
- `ads` → `ad_events` (1 : *)
- `users` → `ad_events` (1 : *)
- `Calendar Table` → `ad_events` (1 : *) via Event Date

---

## 📐 DAX Measures

```dax
-- Click Through Rate
CTR = DIVIDE([Total Clicks], [Total Impressions])

-- Engagement Rate
Engagement Rate = DIVIDE([Total Clicks] + [Total Shares] + [Total Comments], [Total Impressions])

-- Conversion Rate
Conversion Rate = DIVIDE([Total Purchases], [Total Clicks])

-- Purchase Rate
Purchase Rate = DIVIDE([Total Purchases], [Total Impressions])

-- Average Budget Per Campaign
Avg Budget Per Campaign = DIVIDE([Total Budget], DISTINCTCOUNT(campaigns[campaign_id]))

-- Dynamic Measures (Field Parameter)
-- Allows switching between Impressions, Clicks, Shares, Comments, Purchases via slicer
```

---

## 📊 Dashboard KPIs

| Metric | Value |
|---|---|
| Impressions | 216.0K |
| Clicks | 25.4K |
| Shares | 1.3K |
| Comments | 2.6K |
| Purchases | 1.3K |
| Engagements | 29.3K |
| CTR (Click Through Rate) | 11.76% |
| Engagement Rate | 13.56% |
| Conversion Rate | 5.21% |
| Purchase Rate | 0.61% |
| Total Budget | 2.54M |
| Avg Budget / Campaign | 50.72K |

---

## 🖼️ Dashboard Visuals

| Visual | Description |
|---|---|
| 🍩 Clicks by Gender | Donut chart — All / Male / Female breakdown |
| 📊 Clicks by Age | Histogram — engagement distribution across age groups |
| 📈 Weekly Clicks Trend | Stacked bar — clicks by week, split by ad type |
| 🗺️ Clicks by Country | Bing Maps — geographic distribution of ad engagement |
| 🗓️ Analysis by Month | Calendar matrix — day-level drill-down per month |
| 📋 Ad Type Performance Table | CTR, Engagement Rate, Purchase Rate, Conversion Rate by ad format |
| 🎛️ Dynamic Measure Slicer | Field parameter — toggle any KPI across all visuals instantly |

---

## 💡 Key Insights

1. **Stories ads** are the top-performing format with a **5.63% Conversion Rate** — best ROI creative type
2. **Female audience** drives nearly **2× more clicks** than male — a significant targeting signal
3. **Ages 25–35** are the peak converting demographic across all campaigns
4. **Carousel ads** have the lowest Purchase Rate (0.58%) — candidate for creative refresh or budget reallocation
5. **Weeks 25–26** show consistent engagement spikes — ideal windows for future campaign scheduling

---

## 📂 Repository Structure

```
Social_Media_Ad_Campaign_Dashboard/
│
├── Datasets/                          # Source CSV data files
│   ├── campaigns.csv
│   ├── ads.csv
│   ├── ad_events.csv
│   └── users.csv
│
├── Resources/                         # Visual assets & media
│   ├── Social_media_campaign_dashboard.png   # Dashboard screenshot
│   ├── Data_Modeling.png                     # Star schema diagram
│   └── social_media_campaign_recording.mp4   # Dashboard walkthrough video
│
├── power_bi_file/                     # Power BI project file
│   └── social_media_campaign.pbix
│
└── README.md
```

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| **Power BI Desktop** | Dashboard development & publishing |
| **DAX** | KPI measures, time intelligence, dynamic field parameters |
| **Power Query (M)** | Data transformation and loading |
| **Star Schema** | Dimensional modeling for query performance |
| **Bing Maps Visual** | Geographic audience analysis |
| **Field Parameters** | Dynamic metric switching across visuals |
| **Git / GitHub** | Version control |

---

## 🚀 How to Run

1. **Clone the repo**
   ```bash
   git clone https://github.com/ChanakyaSreeHarshaG/Social_Media_Ad_Campaign_Dashboard.git
   ```

2. **Open the Power BI file** — Open `power_bi_file/social_media_campaign.pbix` in Power BI Desktop

3. **Update data source paths** — If prompted, point to the local `Datasets/` folder

4. **Explore the dashboard** — Use slicers to filter by campaign, platform, gender, age, or interest group

5. **View live** — Access the published dashboard via the link at the top of this README

---

## 🛡️ License

This project is licensed under the [MIT License](LICENSE).

---

## 🙋 About Me

Hi, I'm **Chanakya Sree Harsha G** — a data analyst passionate about turning raw data into actionable business insights through clean data models and compelling visualizations.

Feel free to connect with me on [LinkedIn](https://www.linkedin.com/in/chanakyasreeharsha) or explore more of my work on [GitHub](https://github.com/ChanakyaSreeHarshaG).

---

*If you found this useful, please ⭐ star the repo — it means a lot!*
