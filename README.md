# dsa210-project
# DSA210 Project – April 14 Progress

## Overview
This stage of the project focuses on data cleaning, exploratory data analysis (EDA), and hypothesis testing. The goal is to understand how macroeconomic indicators relate to global music trends.

---

## Data Sources
- Spotify Tracks Dataset (2015–2025)
- Global Economy Indicators Dataset
- World Bank Economic Data (2025 update)

---

## Data Cleaning
The datasets were cleaned and standardized before merging:

- Country names were standardized (e.g., "USA" → "United States")
- Release dates were converted to extract year information
- Numeric columns were safely converted to proper numeric types
- Missing and invalid values were handled
- Data was filtered to include years between 2015 and 2025
- Due to incomplete economic data for 2025, the main analysis focuses on **2015–2024**

---

## Data Integration
The datasets were merged using:
- `country`
- `year`

Economic indicators were combined using fallback logic:
- GDP and GNI values prioritize World Bank data
- Income per capita is constructed using available sources

---

## Country-Year Panel Construction
A country-year level dataset was created to improve statistical reliability.

For each country-year, the following metrics were computed:
- Average popularity
- Average danceability
- Average energy
- Average stream count
- Explicit content share
- Inflation rate
- Unemployment rate
- Income per capita

---

## Exploratory Data Analysis (EDA)

Several visualizations were created:

### Time Series Analysis
- Average inflation by year
- Average unemployment by year
- Average popularity by year
- Average stream count by year

**Insight:**  
Economic indicators fluctuate over time, while music popularity remains relatively stable.

---

### Cross-Sectional Analysis
- Average stream count by country
- Average stream count by genre (Top 10)

**Insight:**  
Music consumption varies significantly across countries and genres.

---

### Distribution Analysis
- Danceability by income-per-capita group

**Insight:**  
Higher-income country groups show slightly different danceability distributions.

---

## Hypothesis Testing

Three hypotheses were tested using:
- Welch t-test
- Mann-Whitney U test
- Cohen’s d (effect size)

---

### H1: Popularity vs Inflation
- Result: Not significant  
- p-value ≈ 0.512  

**Conclusion:**  
No evidence that inflation affects music popularity.

---

### H2: Explicit Content vs Unemployment
- Result: Not significant  
- p-value ≈ 0.102  

**Conclusion:**  
No strong relationship between unemployment and explicit content share.

---

### H3: Danceability vs Income per Capita
- Result: Significant  
- p-value ≈ 0.017  

**Conclusion:**  
There is a statistically significant difference in danceability between high-income and low-income groups, although the effect size is small.

---

## Summary
- Data cleaning and merging were successfully completed
- A structured country-year panel dataset was created
- EDA provided insights into economic and musical trends
- Hypothesis testing showed limited but meaningful relationships

---

## Outputs
All generated outputs are saved in the `/outputs` folder:
- Cleaned datasets
- Country-year panel data
- Hypothesis test results
- EDA visualizations