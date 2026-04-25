# Deloitte-Data-Analytics-Job-Simulation-
An end-to-end data analytics project using Power BI and Excel to analyze factory failure data. This repository includes data cleaning steps for nested JSON telemetry and a classification system for employee compensation equality scores to identify operational inefficiencies and pay gaps.



# Daikibo Factory: Telemetry & Downtime Analysis

[cite_start]This project was developed as part of a **Deloitte** simulation to address operational inefficiencies at Daikibo's global manufacturing sites[cite: 2, 250]. [cite_start]The analysis identifies key bottlenecks in production by quantifying "unhealthy" machine statuses into measurable downtime[cite: 251].

## 📊 Project Overview
[cite_start]Daikibo operates four global factories (Tokyo, Osaka, Berlin, and Shenzhen)[cite: 252]. [cite_start]Each factory tracks 9 machine types, sending telemetry pings every 10 minutes[cite: 253]. The goal was to identify:
1. [cite_start]Which location experienced the highest downtime[cite: 254].
2. [cite_start]Which specific machines were the primary drivers of failure[cite: 255].

## 🛠️ Technical Workflow

### 1. Data Transformation (Power BI / Power Query)
[cite_start]The raw telemetry data was provided in a nested JSON format[cite: 256]. The following steps were taken to "flatten" the data for analysis:
* [cite_start]**Schema Expansion:** Expanded nested `location` and `data` records to expose fields like `factory`, `deviceType`, and `status`[cite: 258].
* [cite_start]**Data Type Calibration:** Converted Unix timestamps (milliseconds) into human-readable Date/Time formats using custom DAX/M formulas[cite: 259].
* [cite_start]**Measure Creation:** Developed a calculated column, `Unhealthy`, which assigns a value of **10** to any "unhealthy" status to represent 10 minutes of downtime[cite: 260].

### 2. Visualization & Interactivity
A dynamic dashboard was constructed featuring:
* [cite_start]**Down Time per Factory:** A bar chart identifying the site with the highest cumulative failure minutes[cite: 262].
* [cite_start]**Down Time per Device Type:** A granular view of machine-specific errors[cite: 263].
* [cite_start]**Cross-Filtering:** Selecting a factory bar automatically filters the device chart to show only the machines at that specific location[cite: 264].

### 3. Equality Score Classification (Excel)
[cite_start]In addition to telemetry, the project includes an analysis of employee compensation data[cite: 265]:
* **Classification Logic:** Applied a nested `IF` and `ABS` formula to categorize equality scores:
    * [cite_start]**Fair:** $\pm10$[cite: 266].
    * [cite_start]**Unfair:** $>\pm10$ and $\le\pm20$[cite: 267].
    * [cite_start]**Highly Discriminative:** $>\pm20$[cite: 267].

## 🔑 Key Insights
* [cite_start]**Top Offender:** **Daikibo Factory Seiko** was identified as having the most downtime (480 minutes)[cite: 268].
* [cite_start]**Critical Asset:** Within the Seiko factory, the **Laser Welder** was the primary cause of production loss[cite: 269].
* [cite_start]**Strategic Recommendation:** Conduct a maintenance audit on specific high-failure machinery and high-level roles to align with global performance and equality standards[cite: 270].

## 📂 Repository Contents
* `/data`: Sample telemetry and equality tables (placeholders).
* [cite_start]`/screenshots`: Final Power BI Dashboard captures[cite: 271].
* [cite_start]`/docs`: Step-by-step data cleaning guide[cite: 271].

---
