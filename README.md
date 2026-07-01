# Executive Sales & Logistics Optimization Dashboard (Power BI Case Study)

## 📌 Business Overview & Challenge
[cite_start]A large multinational distributor operating in the US and global markets faced stagnant net profit growth despite generating millions in revenue[cite: 324, 673]. [cite_start]The goal of this project was to clean raw transactional data [cite: 360, 927][cite_start], build a resilient data model using a Star Schema architecture [cite: 350, 390][cite_start], and design an interactive multi-page Power BI dashboard to diagnose leaks in operational profitability[cite: 325, 373].

## 🛠️ Tech Stack & Skills Demonstrated
* [cite_start]**Data Modeling:** Star Schema design, custom surrogate keys creation (`Location_Key` via `[Postal Code] & "-" & [City]`) to resolve disconnected dimensions[cite: 363, 364, 392].
* [cite_start]**ETL (Power Query):** M-code column transformations, handling null text values, and proper table formatting[cite: 347, 348, 362].
* [cite_start]**DAX (Data Analysis Expressions):** Strict, clean corporate naming convention (e.g., `Total sales`, `Profit after shipping`, `Profit_margin_%`)[cite: 406, 445]. [cite_start]Time-intelligence mechanisms (YoY comparisons) and advanced filtering isolation[cite: 336, 411].
* [cite_start]**UI/UX & Business Storytelling:** Clean layout with a persistent navigation side-menu [cite: 373, 396][cite_start], synchronized data filtering [cite: 548][cite_start], and conditional formatting tailored to highlight business risks[cite: 408, 506].

## 📊 Dashboard Architecture & Insights

<img width="1414" height="787" alt="Page1" src="https://github.com/user-attachments/assets/a87b42f5-c6d5-4ded-bc64-7f58422490ce" />
### Page 1. Executive overview
* [cite_start]**Core Elements:** C-level summary KPI cards (`Total sales`, `Orders`), Sales and profit trend (Line and stacked column chart using dynamic twin Y-axes), and Top 10 products ranking with native DAX dense ranking[cite: 331, 333, 396, 397, 939].
* [cite_start]**Key Insight:** Successfully handled multi-scale data parsing by cleanly isolating top-level revenue patterns from strict profit trends on a unified trend chart[cite: 444, 939].

<img width="1413" height="793" alt="Page2" src="https://github.com/user-attachments/assets/b4a9d5dc-1c0a-42a4-813d-dc7613766d3d" />
### Page 2. Monthly analysis
* [cite_start]**Core Elements:** Deep-dive financial Matrix grid (Years ➡️ Months) augmented with conditional Data Bars[cite: 334, 336, 408].
* [cite_start]**Key Insight:** Implemented `IF(ISINSCOPE(...))` filtering to automatically hide deceptive YoY anomalies on the initial periods where historical comparison data was unavailable[cite: 411, 943].

<img width="1447" height="790" alt="Page3" src="https://github.com/user-attachments/assets/83526299-31a4-4a3b-aaa3-af10db9723ef" />
### Page 3. Discount analysis (The Profit Leaks)
* [cite_start]**Core Elements:** Corporate group-sorted Matrix (`No Discount` serving as a baseline at index 0), Sales and profit margin by discount group (Combo chart), and a granular transaction-level Scatter plot[cite: 412, 448, 471, 477].
* [cite_start]**Key Insight:** Designed a custom DAX error band (`Zero_Line_Loss`) that dynamically highlights structural losses in a warning shade *only* when the margin drops below 0%[cite: 611, 624]. [cite_start]This visually proves to management that discount tiers exceeding 16-20% completely destroy company net profit[cite: 413, 624, 659].

<img width="1413" height="787" alt="Page4" src="https://github.com/user-attachments/assets/e2d8fc63-d0a6-40ff-96a0-6f4d983c8f87" />
### Page 4. Operational efficiency
* [cite_start]**Core Elements:** Matrix mapped with regional hierarchy (`Market` ➡️ `Region` ➡️ `Person`) connected via a transited bridge relation (`Dim_SalesReps` ➡️ `Dim_Adress` ➡️ `Fact_Orders`)[cite: 678, 741].
* [cite_start]**Key Insight:** Uncovered that massive sales regions like APAC and LATAM are running in a net deficit[cite: 761]. [cite_start]The combination chart exposes that urgent fulfillment via `First Class` shipping drives logstical expenses up to 17-18% of revenue, completely devouring the business margin[cite: 767, 769].

<img width="1410" height="799" alt="page5" src="https://github.com/user-attachments/assets/26b79f55-9fc5-491b-a5ee-bf0622ecc9c3" />
### Page 5. Hidden detail page with orders (Technical Audit)
* [cite_start]**Core Elements:** End-to-end technical table with row-level transaction auditing (Order ID, Product Name, exact Discount, Ship Mode)[cite: 791].
* [cite_start]**Key Insight:** Hidden from default view and strictly accessible via native `Drill-through` filtering from analytical dashboards to prevent clutter while allowing deep operational deep-dives[cite: 782, 798, 802].

## 📐 Data Modeling & Architecture

To ensure high performance, scalar query speed, and strict data integrity, the relationship architecture was designed using a classic **Star Schema** approach.

* **Fact Table:** `Fact_Orders` containing high-granularity transactional metrics (Sales, Profit, Quantity, Shipping costs).
* **Dimension Tables:** `Dim_Customers`, `Dim_Products`, `Dim_Adress` (Geography Data), `Dim_SalesReps` (Managers), and a custom auto-generated `Dim_Calendar` for time-intelligence reporting.
* **Bridge Relations:** Implemented a single-direction filter transit routing from `Dim_SalesReps` ➡️ `Dim_Adress` via `Region` parameters to isolate local sales manager metrics without data duplication.

<img width="1287" height="753" alt="model" src="https://github.com/user-attachments/assets/d8062ba2-3fb6-4767-94bb-4a2c64d9d809" />

---
*Developed as part of a professional Freelance Data Analytics Portfolio.*
