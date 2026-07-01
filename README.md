# Executive Sales & Logistics Optimization Dashboard (Power BI Case Study)

## 📌 Business Overview & Challenge
[cite_start]A large multinational distributor operating in the US and global markets faced stagnant net profit growth despite generating millions in revenue[cite: 324, 673]. [cite_start]The goal of this project was to clean raw transactional data [cite: 360, 927][cite_start], build a resilient data model using a Star Schema architecture [cite: 350, 390][cite_start], and design an interactive multi-page Power BI dashboard to diagnose leaks in operational profitability[cite: 325, 373].

## 🛠️ Tech Stack & Skills Demonstrated
* [cite_start]**Data Modeling:** Star Schema design, custom surrogate keys creation (`Location_Key` via `[Postal Code] & "-" & [City]`) to resolve disconnected dimensions[cite: 363, 364, 392].
* [cite_start]**ETL (Power Query):** M-code column transformations, handling null text values, and proper table formatting[cite: 347, 348, 362].
* [cite_start]**DAX (Data Analysis Expressions):** Strict, clean corporate naming convention (e.g., `Total sales`, `Profit after shipping`, `Profit_margin_%`)[cite: 406, 445]. [cite_start]Time-intelligence mechanisms (YoY comparisons) and advanced filtering isolation[cite: 336, 411].
* [cite_start]**UI/UX & Business Storytelling:** Clean layout with a persistent navigation side-menu [cite: 373, 396][cite_start], synchronized data filtering [cite: 548][cite_start], and conditional formatting tailored to highlight business risks[cite: 408, 506].

## 📊 Dashboard Architecture & Insights

### Page 1. Executive overview
* [cite_start]**Core Elements:** C-level summary KPI cards (`Total sales`, `Orders`), Sales and profit trend (Line and stacked column chart using dynamic twin Y-axes), and Top 10 products ranking with native DAX dense ranking[cite: 331, 333, 396, 397, 939].
* [cite_start]**Key Insight:** Successfully handled multi-scale data parsing by cleanly isolating top-level revenue patterns from strict profit trends on a unified trend chart[cite: 444, 939].

### Page 2. Monthly analysis
* [cite_start]**Core Elements:** Deep-dive financial Matrix grid (Years ➡️ Months) augmented with conditional Data Bars[cite: 334, 336, 408].
* [cite_start]**Key Insight:** Implemented `IF(ISINSCOPE(...))` filtering to automatically hide deceptive YoY anomalies on the initial periods where historical comparison data was unavailable[cite: 411, 943].

### Page 3. Discount analysis (The Profit Leaks)
* [cite_start]**Core Elements:** Corporate group-sorted Matrix (`No Discount` serving as a baseline at index 0), Sales and profit margin by discount group (Combo chart), and a granular transaction-level Scatter plot[cite: 412, 448, 471, 477].
* [cite_start]**Key Insight:** Designed a custom DAX error band (`Zero_Line_Loss`) that dynamically highlights structural losses in a warning shade *only* when the margin drops below 0%[cite: 611, 624]. [cite_start]This visually proves to management that discount tiers exceeding 16-20% completely destroy company net profit[cite: 413, 624, 659].

### Page 4. Operational efficiency
* [cite_start]**Core Elements:** Matrix mapped with regional hierarchy (`Market` ➡️ `Region` ➡️ `Person`) connected via a transited bridge relation (`Dim_SalesReps` ➡️ `Dim_Adress` ➡️ `Fact_Orders`)[cite: 678, 741].
* [cite_start]**Key Insight:** Uncovered that massive sales regions like APAC and LATAM are running in a net deficit[cite: 761]. [cite_start]The combination chart exposes that urgent fulfillment via `First Class` shipping drives logstical expenses up to 17-18% of revenue, completely devouring the business margin[cite: 767, 769].

### Page 5. Hidden detail page with orders (Technical Audit)
* [cite_start]**Core Elements:** End-to-end technical table with row-level transaction auditing (Order ID, Product Name, exact Discount, Ship Mode)[cite: 791].
* [cite_start]**Key Insight:** Hidden from default view and strictly accessible via native `Drill-through` filtering from analytical dashboards to prevent clutter while allowing deep operational deep-dives[cite: 782, 798, 802].

---
*Developed as part of a professional Freelance Data Analytics Portfolio.*
