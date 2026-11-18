# Spotify Music Analytics Dashboard 🎵

[![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![DAX](https://img.shields.io/badge/DAX-Measures-4F5B93)](https://learn.microsoft.com/dax/)
[![CSV](https://img.shields.io/badge/Data-CSV-217346)](https://en.wikipedia.org/wiki/Comma-separated_values)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

An interactive Spotify music analytics project built in Microsoft Power BI to explore chart positions, song popularity, artist performance, album types, explicit-content mix, and music duration trends across a 2023–2024 chart dataset.

> **Repository snapshot:** 27,800 chart records, 794 distinct songs, 343 distinct artists, and 556 unique chart dates are present in the CSV.

---

## 📚 Table of Contents

- [Project Overview](#-project-overview)
- [Project Objectives](#-project-objectives)
- [Business Problem](#-business-problem)
- [Dashboard Preview](#-dashboard-preview)
- [Key Performance Indicators](#-key-performance-indicators-kpis)
- [Key Features](#-key-features)
- [Dashboard Pages / Analysis](#-dashboard-pages--analysis)
- [Tools & Technologies](#-tools--technologies)
- [Dataset Information](#-dataset-information)
- [Data Cleaning & Transformation](#-data-cleaning--transformation)
- [Data Analysis & Insights](#-data-analysis--insights)
- [Business Insights / Findings](#-business-insights--findings)
- [Project Folder Structure](#-project-folder-structure)
- [How to Run This Project](#-how-to-run-this-project)
- [Installation / Usage](#-installation--usage)
- [Future Improvements](#-future-improvements)
- [Skills Demonstrated](#-skills-demonstrated)
- [Author Information](#-author-information)
- [Connect With Me](#-connect-with-me)

---

## 🎯 Project Overview

This project converts Spotify chart data into an interactive analytical dashboard. It gives users a consolidated view of song rankings and popularity while enabling drill-down analysis by artist, album type, chart position, release year, release month, and explicit-content status.

The PBIX report contains four pages: **Index/Home, Overview, Artist, and Songs**. The repository also provides separate exported screenshots for every dashboard page.

## 🎯 Project Objectives

- Analyze the popularity and chart performance of songs and artists.
- Compare explicit and non-explicit tracks.
- Identify top artists and songs by song count, popularity, and position-one appearances.
- Compare album, single, and compilation performance.
- Explore music duration and release-date patterns.
- Provide a recruiter-ready interactive Power BI portfolio project.

## 💼 Business Problem

Spotify-style catalog and chart data can contain many rows spanning artists, albums, dates, and rankings. Raw tabular data makes it difficult to quickly answer questions such as:

- Which artists repeatedly appear in the charts?
- Which tracks have the highest popularity?
- Do singles or albums perform differently?
- How does explicit-content status relate to popularity?
- How many tracks reach chart position one?
- How does popularity change across time?

This dashboard addresses that problem with filters, KPI cards, rankings, and visual comparisons.

## 🖼️ Dashboard Preview

### Home

![Spotify Music Analytics - Home](Home.png)

### Overview

![Spotify Music Analytics - Overview](Overview.png)

### Artists

![Spotify Music Analytics - Artists](Artists.png)

### Songs

![Spotify Music Analytics - Songs](Songs.png)

## 📈 Key Performance Indicators (KPIs)

The repository's DAX measure file defines the following KPIs:

| KPI | DAX measure |
|---|---|
| Total songs / chart records | `Total Songs` |
| Distinct songs | `Distinct Songs` |
| Distinct artists | `Distinct Artists` |
| Average popularity | `Avg Popularity` |
| Maximum popularity | `Max Popularity` |
| Minimum popularity | `Min Popularity` |
| Average duration | `Avg Duration Minutes` |
| Explicit songs | `Explicit Songs` |
| Non-explicit songs | `Non-Explicit Songs` |
| Explicit-song percentage | `Pct Explicit Songs` |
| Average position | `Avg Position` |
| Position-one songs | `Position 1 Songs` |
| Position-one artists | `Position 1 Artists` |
| Singles count | `Singles Count` |
| Albums count | `Albums Count` |
| Average tracks per album | `Avg Tracks per Album` |

Verified against the CSV:

| Metric | Result |
|---|---:|
| Chart records | 27,800 |
| Distinct songs | 794 |
| Distinct artists | 343 |
| Average popularity | 89.62 |
| Average duration | 3.28 minutes |
| Explicit records | 11,172 (40.19%) |
| Position-one records | 556 |
| Chart date range | 2023-05-18 to 2024-11-27 |

## ⭐ Key Features

- Interactive navigation buttons across the four report pages.
- KPI cards for song, artist, popularity, duration, explicit-content, and ranking measures.
- Artist and song ranking visuals.
- Chart-position and popularity comparisons.
- Album-type and explicit/non-explicit distribution analysis.
- Monthly and yearly trend views.
- Advanced slicers for interactive filtering.
- Album-cover and Spotify-style visual elements.
- Detailed artist and song tables for drill-down.

## 📊 Dashboard Pages / Analysis

| Page | Purpose |
|---|---|
| Index / Home | Portfolio-style entry page with navigation to Overview, Artists, and Songs. |
| Overview | High-level KPIs, artist and song rankings, album-type mix, explicit-content mix, and monthly trends. |
| Artist | Artist-level comparisons covering distinct songs, popularity, chart hits, and position-one performance. |
| Songs | Song-level table and charts for artist, album type, popularity, chart hits, and track details. |

The PBIX file contains action-button navigation, cards, bar charts, column charts, area charts, donut charts, 100% stacked bars, slicers, tables, and images.

## 🛠️ Tools & Technologies

| Technology | Usage |
|---|---|
| Microsoft Power BI | Report design and interactive dashboard development |
| DAX | Calculated measures and analytical aggregations |
| CSV | Source data format |
| Power BI visualizations | KPI cards, slicers, rankings, tables, and charts |

SQL and a Microsoft Excel `.xlsx` source are **not present** in this repository, so they are not listed as project technologies.

## 🗂️ Dataset Information

**File:** [`Dataset of top_50_spotify_songs.csv`](Dataset%20of%20top_50_spotify_songs.csv)

| Column | Description |
|---|---|
| `date` | Chart observation date |
| `position` | Chart position for the song |
| `song` | Track name |
| `artist` | Artist or collaborating artists |
| `popularity` | Spotify popularity value |
| `duration_ms` | Track duration in milliseconds |
| `album_type` | Album, single, or compilation classification |
| `total_tracks` | Number of tracks associated with the album/release |
| `release_date` | Track or release date |
| `is_explicit` | Explicit-content flag |
| `album_cover_url` | Spotify album-cover image URL |

The original source and its licensing/refresh policy are not documented in the repository. The exact meaning of the `popularity` values should be validated against the original data provider before public presentation.

## 🔧 Data Cleaning & Transformation

The repository does not include a separate Power Query script or documented transformation log. Observable preparation in the report and dataset includes:

- Loading the CSV into the Power BI data model.
- Converting `duration_ms` to duration in minutes with DAX (`duration_ms / 60000`).
- Explicit/non-explicit grouping using the `is_explicit` Boolean field.
- Distinct counts for songs and artists.
- Aggregations for ranking, popularity, track count, and chart position.
- Time analysis using chart and release-date fields.

Power Query transformation steps could not be confirmed from the repository files and should not be described as completed work unless supplied by the report author.

## 🔍 Data Analysis & Insights

The following results were calculated directly from the repository CSV and DAX definitions:

- The source spans 556 unique chart dates, each initially represented as one 50-row chart snapshot.
- There are 794 distinct songs and 343 distinct artists.
- Taylor Swift has 85 distinct songs, the highest observed artist count.
- Album-type counts are 17,261 album records, 10,496 single records, and 43 compilation records.
- Average popularity is highest for singles (91.86), followed by albums (88.30) and compilations (76.26).
- Explicit records have an average popularity of 89.49; non-explicit records have an average popularity of 89.71.
- The average track duration is 3.28 minutes.
- The longest recorded duration in the CSV is 7.62 minutes.
- Position-one records include 37 unique songs.

## 💡 Business Insights / Findings

- **Artist representation:** Taylor Swift has the largest number of distinct song entries in the source dataset.
- **Release format:** Singles have the highest average popularity in the observed records.
- **Content classification:** Explicit and non-explicit records have nearly the same average popularity; the CSV does not show a meaningful explicit-content advantage.
- **Chart concentration:** 556 position-one observations map to 37 unique songs, showing that repeated number-one appearances are concentrated among a smaller set of tracks.
- **Typical duration:** The average track duration is approximately 3.28 minutes, but some tracks extend well beyond the most common range.
- **Trend reporting:** The dashboard supports time-based analysis, while chart-date and release-date fields should be distinguished clearly in reporting.

These findings describe the supplied dataset only and do not establish causal relationships or current Spotify trends.

## 📁 Project Folder Structure

```text
Spotify-Music-Analytics-PowerBI/
├── Spotify_Dashboard.pbix                 # Power BI report
├── Dataset of top_50_spotify_songs.csv    # Source dataset
├── dax/
│   └── Measures.txt                       # DAX measures and DAX query
├── Home.png                               # Exported Home page
├── Overview.png                           # Exported Overview page
├── Artists.png                            # Exported Artists page
├── Songs.png                              # Exported Songs page
├── README.md                              # Project documentation
└── LICENSE                                # MIT License
```

## ▶️ How to Run This Project

1. Install **Microsoft Power BI Desktop** on a Windows PC.
2. Download or clone this repository.
3. Open `Spotify_Dashboard.pbix`.
4. If prompted to refresh, verify that the CSV source path is available on your computer.
5. Use the navigation buttons to open Home, Overview, Artist, and Songs pages.
6. Apply slicers and select chart elements to filter the report.

## 💻 Installation / Usage

### Clone the repository

```bash
git clone https://github.com/Rahulsharma2006/Spotify-Music-Analytics-PowerBI.git
cd Spotify-Music-Analytics-PowerBI
```

### Open in Power BI

```text
Power BI Desktop → File → Open → Spotify_Dashboard.pbix
```

No package installation or API credentials are required for the static CSV dataset.

## 🚀 Future Improvements

- Publish the report to Power BI Service and provide a public or scheduled refresh setup.
- Add a documented, reproducible Power Query transformation layer.
- Replace relative local CSV assumptions with a clearly documented data source path.
- Add drill-through pages for selected song and artist details.
- Add a refresh date and data-source provenance section.
- Add a date table for more robust time intelligence.
- Add a dataset source citation and data dictionary.
- Extend analysis with a real streaming-history or larger Spotify catalog dataset.
- Improve accessibility with descriptive alt text and stronger keyboard navigation.

## 🧠 Skills Demonstrated

- Power BI dashboard development
- Data modeling and measure creation
- DAX calculation design
- KPI definition and validation
- Data visualization and dashboard layout
- CSV data analysis
- Business insight communication
- Recruiter-focused GitHub documentation

## 👤 Author Information

**Rahul Sharma**

- Role: CSE (Data Science) Student | Aspiring Data Analyst
- GitHub: [@Rahulsharma2006](https://github.com/Rahulsharma2006)

## 🤝 Connect With Me

- GitHub: [https://github.com/Rahulsharma2006](https://github.com/Rahulsharma2006)
- LinkedIn: Add your LinkedIn profile URL
- Portfolio: Add your portfolio URL

---

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
