# GLOBAL-BILLIONAIRES-ANALYSIS-PROJECT (# Global Billionaires Analysis — Power BI Dashboard)
## Project Overview

This project analyzes a dataset of 475 of the world's billionaires, exploring how wealth is distributed across industries, countries, age groups, and gender — and how it relates to macroeconomic factors like GDP and inflation (CPI). The result is a two-page interactive Power BI dashboard answering 10 core business questions about global wealth concentration.

## Objectives

- Clean and prepare raw billionaire data for analysis in Power Query
- Build core KPI measures using DAX
- Visualize wealth distribution by industry, country, region, gender, and age
- Investigate the relationship between billionaire wealth and economic indicators (GDP, CPI)
- Identify patterns in self-made vs. inherited wealth
- Summarize findings into actionable insights and recommendations

## Tools Used

- Microsoft Power BI Desktop (Power Query, DAX, report visuals)
- Microsoft Excel (data source)

## Files

- Billonaires_Dashboard.xlsx – Source workbook (raw dataset + cleaned table)
- Billionaires_Analysis.pdf – Exported dashboard pages and findings summary
- README.md – Project documentation

## Process

**1. Data Cleaning (Power Query)**
- Loaded the raw dataset (`Raw_datset` sheet) into Power BI via Get Data → Excel Workbook → Transform Data
- Replaced null values in the `Region` column with "NA"
- Added a custom column `Wealth_Billions` (`Finalworth / 1000`) to convert net worth into billions
- Created a conditional column `SelfMade_Label` to convert TRUE/FALSE values into readable "Self Made" / "Inherited" labels
- Added an `Age Group` conditional column bucketing ages into Under 40 / 40–59 / 60–79 / 80+

**2. DAX Measures**
| Measure | Formula |
|---|---|
| Total Billionaires | `COUNTROWS(Raw_datset)` |
| Total Wealth $B | `SUM(Raw_datset[Wealth_Billions])` |
| Avg Age | `AVERAGE(Raw_datset[Age])` |
| % Self Made | `DIVIDE(COUNTROWS(FILTER(Raw_datset,[Self Made]=TRUE)), COUNTROWS(Raw_datset))` |
| Avg Wealth $B | `AVERAGE(Raw_datset[Wealth_Billions])` |
| Avg GDP | `AVERAGE(Raw_datset[Gdp_Country])` |
| Avg CPI | `AVERAGE(Raw_datset[Cpi_Country])` |
| Youngest | `MIN(Raw_datset[Age])` |
| Oldest | `MAX(Raw_datset[Age])` |

**3. Visuals Built (by business question)**
| # | Question | Visual |
|---|---|---|
| Q1 | Which industry has the most billionaires? | Clustered bar chart |
| Q2 | Which country has the most billionaires? | Clustered bar chart + filled map |
| Q3 | Total vs average wealth by region | Dual clustered column charts |
| Q4 | Self-made vs inherited split | Donut chart |
| Q5 | Gender split across industries | Stacked bar chart (% stacked) |
| Q6 | Age distribution | Column chart with age buckets |
| Q7 | Does higher GDP mean wealthier billionaires? | Scatter/bubble chart |
| Q8 | Top 10 wealthiest individuals | Table with data bars |
| Q9 | Does CPI relate to billionaire wealth? | Scatter chart, color-coded by region |
| Q10 | Youngest vs oldest billionaire per industry | Clustered bar chart |

**4. Interactivity**
- Added 4 slicers (Region, Industries, Gender, Self-Made status) so all visuals filter together

## Key Skills Demonstrated

- Power Query data cleaning and transformation
- DAX measure creation
- Data visualization design (bar, donut, scatter, stacked, map)
- Dashboard interactivity (slicers, cross-filtering)
- Business question framing and data storytelling
- Insight generation and strategic recommendation writing

## Key Findings

- **475 billionaires** analyzed, worth a combined **$7.04 trillion**, average age **67**, **65% self-made**
- **Finance (77)** and **Technology (62)** produce the most billionaires, followed by Fashion & Retail (54)
- The **United States (190)** and **China (73)** together account for over 55% of all billionaires in the dataset
- Smaller economies (Spain, Belgium, Mexico, Chile, France) show disproportionately high *average* wealth per billionaire, despite far smaller GDPs than the US or China
- **CPI shows no consistent relationship** with billionaire wealth concentration
- **Technology has the widest age range** among billionaires (30–89), while Construction & Engineering and Healthcare represent slower, multi-decade wealth-building paths
- **Women are heavily underrepresented** across every industry

## Strategic Recommendations

1. Finance and Technology remain the most reliable paths to extreme wealth creation, but Fashion & Retail's strong third-place position shows consumer-facing, globally branded businesses are also a major wealth driver.
2. Countries or policies aiming to grow a billionaire class should study what the US and China share structurally — deep capital markets, large domestic consumer bases, and supportive business environments — rather than assuming smaller economies can replicate this differently.
3. Average wealth per country can be misleading without billionaire count alongside it — a single ultra-wealthy individual (e.g. Bernard Arnault in France, Carlos Slim in Mexico) skews the average. Total wealth and count together tell a fuller story.
4. CPI is not a strong predictor of where extreme wealth concentrates — high-inflation countries like Nigeria, Ukraine, and Egypt show some of the lowest average billionaire wealth.
5. Technology and Food & Beverage (youngest billionaires at 30 and 32 respectively) demonstrate the fastest paths to extreme wealth, while Construction & Engineering and Healthcare reflect slower, multi-decade wealth building.
6. Closing the gender wealth gap requires shifting focus from workforce participation to ownership and equity access — supporting women in acquiring capital, equity stakes, and founder/owner positions rather than only increasing representation as employees or consumers.

## Conclusion

This dataset shows that extreme wealth today is still predominantly self-made (65%), concentrated in a handful of industries (led by Finance and Technology), and dominated by the United States and China. Yet wealth intensity per capita tells a different story — smaller, capital-efficient economies can produce disproportionately wealthy individuals even without large billionaire populations.

## Author

Onyinyechi Onuoha
