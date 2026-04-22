Indian Bike Sales — Data Analytics Project

A complete end-to-end data analytics project analyzing 10,000 Indian motorcycle records using Excel, SQL, Python, and Power BI.


Project Overview
This project performs a full data analysis on the Indian two-wheeler market, covering sales trends, pricing patterns, resale depreciation, and performance efficiency across 8 major brands and 4 city tiers.
AttributeDetailsDataset10,000 Indian bike sales recordsTools UsedMicrosoft Excel · SQLite (DB Browser) · Python (Jupyter) · Power BIBrands CoveredRoyal Enfield, Bajaj, KTM, Kawasaki, Yamaha, Hero, TVS, HondaFuel TypesPetrol · Hybrid · ElectricCity TiersMetro · Tier 1 · Tier 2 · Tier 3Analysis AreasSales & Market · Price · Resale & Depreciation · Performance & Efficiency


Dataset — Column Reference
ColumnDescriptionExampleStateIndian state of registrationKarnatakaAvg Daily Distance (km)Average km ridden per day68.84BrandManufacturer nameRoyal EnfieldModelSpecific bike modelHunter 350Price (INR)Original purchase price2,52,816Year of ManufactureYear bike was manufactured2021Engine Capacity (cc)Engine displacement672Fuel TypePetrol / Hybrid / ElectricElectricMileage (km/l)Fuel efficiency78.41Owner TypeFirst / Second / Third ownerSecondRegistration YearYear of registration2024Insurance StatusActive / Expired / Not AvailableActiveSeller TypeDealer or IndividualIndividualResale Price (INR)Current resale market value1,49,934City TierMetro / Tier 1 / Tier 2 / Tier 3

🔧 Tools & Technologies
Microsoft Excel

Explored all 15 columns and understood data structure
Added calculated columns: Depreciation (INR) and Depreciation %
Built bar charts for brand distribution

SQL (SQLite — DB Browser)

Imported CSV into bikes table
Ran 10 analytical queries covering market share, pricing, depreciation, mileage, and insurance status
Exported results as CSV for reporting

Python (Jupyter Notebook)

Libraries: pandas, matplotlib, seaborn, scipy, numpy
Cleaned data: fixed column types, removed duplicates, added calculated columns
Generated 7 analysis charts (PNG exports)
Ran independent samples T-test: Dealer vs Individual prices

Power BI

3-page interactive dashboard with dark theme
Cross-page synced slicers (Brand, Fuel Type, City Tier)
Conditional formatting matrix (Brand × Owner Type heat map)


Key Analysis Areas
1. Sales & Market Insights

Market share by brand (Kawasaki leads at ~12.9%)
Fuel type distribution: Hybrid (33.6%) · Petrol (33.6%) · Electric (32.8%)
City tier breakdown across all 4 tiers
Dealer vs Individual seller split (~50/50)

2. Price Analysis

Bajaj has the highest average price (₹2,30,663)
Honda has the lowest average price (₹2,21,077)
Price difference between city tiers is minimal (<1%)
Bikes manufactured in 2021 peaked in average price

3. Resale Value & Depreciation

Overall average depreciation: 40.4%
Best resale brand: Kawasaki (39.9% depreciation)
Worst resale brand: Bajaj (41.0% depreciation)
Petrol bikes depreciate slightly more (40.7%) than Hybrid (40.0%)
Third-owner bikes show slightly lower depreciation %

4. Performance vs Efficiency

Best mileage brand: TVS (67.9 km/l average)
Worst mileage brand: Royal Enfield (66.7 km/l average)
Average engine capacity across all brands: 553 cc
Tier 2 cities record the highest avg daily distance (43.2 km/day)
Correlation between engine CC and mileage is near-zero (−0.007)


SQL Queries Summary
#QueryPurposeQ1SELECT * FROM bikes LIMIT 10Preview raw dataQ2COUNT(*)Total record countQ3GROUP BY Brand ORDER BY Units DESCBrand market shareQ4AVG(Price), AVG(Resale) GROUP BY BrandPrice vs resale by brandQ5GROUP BY Fuel Type + share %Fuel type distributionQ6AVG(Depreciation) GROUP BY Owner TypeDepreciation by ownershipQ7AVG(Mileage), AVG(Engine CC) GROUP BY BrandPerformance rankingQ8AVG(Daily Distance) GROUP BY City TierUsage by city tierQ9GROUP BY Insurance StatusInsurance health checkQ10MAX(Price) GROUP BY Brand, ModelTop 10 most expensive models

Python Analysis — Charts Generated
ChartTypeWhat It ShowsChart 1Bar ChartUnits sold per brandChart 2Horizontal BarAverage price by brandChart 3Bar ChartAverage depreciation % by brandChart 4Grouped BarPrice vs Resale by fuel typeChart 5Scatter PlotEngine CC vs Mileage (coloured by brand)Chart 6HeatmapCorrelation matrix of numeric variablesChart 7T-test resultDealer vs Individual price significance test
T-test Result:

Dealer avg price: ₹2,24,XXX
Individual avg price: ₹2,24,XXX
If p < 0.05 → statistically significant price difference between sellers


Power BI Dashboard — 3 Pages
Page 1 — Sales & Market Overview

4 KPI cards (Total Bikes, Avg Price, Avg Resale, Avg Depreciation)
Clustered bar: Units by brand (each brand = unique colour)
Donut chart: Fuel type share %
Stacked bar: City tier distribution
Slicers: Brand · City Tier · Fuel Type

Page 2 — Price & Depreciation Analysis

Line chart: Avg price trend by year (2015–2024)
Clustered column: Avg Price vs Avg Resale side by side per brand
Bar chart: Depreciation % with overall average reference line
Matrix: Brand × Owner Type heat map (green = low dep, red = high dep)
Slicers: Owner Type · Year of Manufacture slider

Page 3 — Performance & Efficiency Analysis

Bar chart: Avg mileage by brand with mean reference line
Scatter plot: Engine CC vs Mileage (bubble size = unit count)
Column chart: Avg daily distance by city tier
Donut: Engine CC distribution (350cc+ dominates at 88.7%)
Bar chart: Efficiency score ranking (mileage per ₹1000)
Slicers: Fuel Type · Insurance Status



Key Insights

Market is evenly distributed — All 8 brands hold roughly equal market share (~12–13% each), suggesting no single brand monopoly in the dataset.
Depreciation is consistent across brands — All brands depreciate between 39.9%–41.0%, a very tight range. Buyer brand preference cannot be justified by resale value alone.
Electric bikes hold value slightly better — Hybrid fuel type shows the lowest avg depreciation (40.0%) vs Petrol (40.7%), suggesting growing resale demand for cleaner fuel bikes.
Mileage differences between brands are minimal — TVS tops at 67.9 km/l vs Royal Enfield at 66.7 km/l — less than 2% difference. Engine CC has near-zero correlation with mileage.
City tier has minimal impact on price or usage — Prices across Metro, Tier 1, Tier 2, and Tier 3 differ by less than 1%, showing the Indian bike market is nationally price-standardised.


How to Run This Project
Prerequisites
bashpip install pandas matplotlib seaborn scipy jupyter openpyxl
Run Python Analysis
bashcd BikeSalesProject
jupyter notebook
# Open bike_analysis.ipynb and run all cells
Run SQL Queries
1. Open DB Browser for SQLite
2. Open / create bike_sales.db
3. Import indian_bike_sales.csv as table: bikes
4. Open Execute SQL tab
5. Copy-paste queries from bike_queries.sql
View Power BI Dashboard
1. Open Power BI Desktop
2. File → Open → BikeSalesDashboard.pbix
3. Use slicers on each page to filter interactively

Requirements
ToolVersionPurposePython3.8+Data cleaning & visualisationpandas1.3+Data manipulationmatplotlib3.4+Chart generationseaborn0.11+Statistical chartsscipy1.7+T-testopenpyxl3.0+Excel file handlingDB Browser for SQLite3.12+SQL queriesPower BI DesktopLatestInteractive dashboardMicrosoft Excel2016+Pivot tables & exploration

Author
GAAYATHRI KG

Email: kggaayathri@gmail.com
LinkedIn: https://www.linkedin.com/in/gaayathrikg/
Github: https://github.com/gaayathri26/Indian_Bike_Sales_Analysis


📄 License
This project is for educational purposes. Dataset used for learning and portfolio demonstration only.

Built as part of a Data Analytics learning project — Phase 1 (Excel) → Phase 2 (SQL) → Phase 3 (Python) → Phase 4 (Power BI)
