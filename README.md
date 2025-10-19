#  World Energy Consumption Analysis — Power BI Dashboard

##  Project Overview
This Power BI dashboard provides an analytical view of **global energy consumption trends** from 1960 to 2022.  
It focuses on total energy production and usage, renewable energy adoption, and regional comparisons.  
The goal is to explore **how countries and regions have evolved** in their energy consumption over time.

---

##  Tools & Technologies
- **Power BI**
- **Power Query** — Data cleaning and transformation  
- **DAX** — Custom measures and calculated fields  
- **Kaggle Dataset** — Global Energy Data  
- **Microsoft Bing Maps** — For geographic visualizations  

---

##  Data Preparation
Performed in **Power Query**:
- Removed unnecessary columns  
- Renamed and standardized key fields (country, year, energy type, etc.)  
- Handled missing values and ensured consistent data formats  
- Created new calculated columns for energy per capita and renewable share  

---
## Dashboard Sections & Insights
 1. Total Energy by Country: An interactive world map showing how energy consumption differs by country.

 2. Energy per GDP by Country: A donut chart comparing energy efficiency across nations — highlighting which economies consume more energy per unit of GDP.

 3. Total Energy by Year: A line chart visualizing the global energy growth trend since 1960 — showing steady growth with small fluctuations.

 4. Hydro vs Renewable Energy Consumption: A bar chart comparing hydroelectric consumption with total renewable energy consumption by region.

 5. Energy per Capita by Country: A geographical heatmap representing how energy use per person varies globally.
    
##  DAX Measures
Some of the key DAX measures created for analysis:
```DAX
Total Energy = SUM(Energy[energy_consumption])
Total Renewable Energy = SUM(Energy[renewables_consumption])
Energy per Capita = DIVIDE([Total Energy], SUM(Energy[population]))
Energy per GDP = DIVIDE([Total Energy], SUM(Energy[gdp]))
Energy Growth % = DIVIDE([Total Energy] - CALCULATE([Total Energy], PREVIOUSYEAR(Energy[year])), CALCULATE([Total Energy], PREVIOUSYEAR(Energy[year])))




