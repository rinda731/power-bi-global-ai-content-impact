# Global AI Content Impact Dashboard (Power BI)

An interactive 5-page Power BI dashboard analysing how AI adoption relates to trust, jobs, revenue and content volume across 10 countries and 10 industries from 2020 to 2025.

## Project objective

Explore how AI adoption varies by country, industry, tool and regulation level, and what that means for revenue gain, job loss and consumer trust.

## Dataset

- **File:** `data/Global_AI_Content_Impact_Dataset.csv` (200 rows, 12 columns)
- **Coverage:** 10 countries, 10 industries, 7 AI tools, 2020 to 2025
- **Source:** *https://www.kaggle.com/datasets/atharvasoundankar/impact-of-ai-on-digital-media-2020-2025*
- **Cleaned version:** `data/AI_Content_Impact_Cleaned.csv`

| Column | Description |
|---|---|
| Country, Year, Industry | Dimensions |
| AI Adoption Rate (%) | Share of adoption |
| AI-Generated Content Volume (TBs per year) | Content produced by AI |
| Job Loss Due to AI (%) | Reported job loss |
| Revenue Increase Due to AI (%) | Reported revenue gain |
| Human-AI Collaboration Rate (%) | Collaboration level |
| Top AI Tools Used | Most used AI tool |
| Regulation Status | Lenient, Moderate or Strict |
| Consumer Trust in AI (%) | Trust level |
| Market Share of AI Companies (%) | Market share |



## Data preparation (Power Query)

1. Renamed columns to short, DAX-friendly names.
2. Set correct data types and trimmed text fields.
3. Checked for duplicates, nulls and out-of-range percentages (none found).
4. Added `Record_ID`.
5. Created derived columns: `Region`, `Adoption_Band`, `Trust_Band`, `Net_Impact_Pct` (revenue increase minus job loss) and `Impact_Category` (High/Low Reward x High/Low Risk, split at the dataset medians).

## DAX measures

Average adoption, trust, job loss, revenue increase and collaboration; total content volume; net impact; adoption-trust gap; country and industry ranks; content volume share; and the share of records in each impact category.

## Dashboard pages

| Page | What it shows |
|---|---|
| Overview | KPI cards, adoption and trust trends by year, country and industry comparisons |
| Geography | Map, adoption vs trust scatter, adoption-trust gap, country table |
| Industry | Risk vs reward by industry, content volume, industry x country heatmap |
| Tools | Tool usage, tool performance, regulation impact, tool x regulation matrix |
| Risk vs Reward | Quadrant scatter, net impact by country and industry, regulation vs impact category |

## Key findings

- **UK** has the highest average adoption (about 65%) but the lowest consumer trust (about 50%). **Germany** has the highest trust (about 65%).
- **Automotive** has the highest revenue gain (about 46%), while **Manufacturing** has the highest job loss (about 33%).
- **Education** and **Legal** produce the most AI content (about 60 TB on average).
- **Stable Diffusion** has the lowest trust (about 52%), and **ChatGPT** the highest adoption (about 60%).
- **Australia** (+31 points) and **Media** (+21 points) have the highest net impact (revenue gain minus job loss).
- Lenient regulation has the largest share of "High Reward / Low Risk" records (27%).

## Limitations

- Each country-year combination has only about 3 records, so results are averages of small samples.
- Correlations between metrics are very weak (roughly between -0.15 and +0.15), so the findings describe patterns and do not show cause and effect.
- The dataset appears to be synthetic or sample data.

## Repository structure

```
.
├── README.md
├── AI_Content_Impact_Dashboard.pbix
├── data/
│   ├── Global_AI_Content_Impact_Dataset.csv
│   └── AI_Content_Impact_Cleaned.csv
├── images/
│   ├── 01_overview.png
│   ├── 02_geography.png
│   ├── 03_industry.png
│   ├── 04_tools.png
│   └── 05_risk_vs_reward.png

```

## Tools used

Power BI Desktop, Power Query (M), DAX

## Author

**Rinda Roy** | [LinkedIn](https://www.linkedin.com/in/rindaroy003/)
