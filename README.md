# Deloitte Australia – Data Analytics Job Simulation (Forage)

This repo contains my work from Deloitte Australia's **Data Analytics Job Simulation** on Forage. The simulation is framed around two fictional clients — **Daikibo Industrials** (an industrial manufacturer) and **Nicora Industries** — and covers two tasks: manufacturing downtime analysis in Tableau, and a gender pay equity audit in Excel.

> This is a self-guided virtual job simulation, not a paid internship or Deloitte-issued assessment of client work. Company names and datasets are simulation material provided by Forage.

---

## Task 1: Manufacturing Downtime Analysis (Tableau)

**Business question:** Daikibo collects IIoT telemetry from 4 factories (Tokyo, Osaka, Berlin, Shenzhen), each with 9 machine types reporting status every 10 minutes. Leadership wanted to know: *which factory has the most machine downtime, and which machine type is driving it?*

**What I did:**
- Imported and flattened nested JSON telemetry data (~160K records) into Tableau, expanding all schema levels (device, location, status).
- Created a calculated field `Unhealthy` (10 minutes of downtime per "unhealthy" status ping).
- Built two linked bar charts: **Down Time per Factory** and **Down Time per Device Type**.
- Connected them with a filter action so selecting a factory drills into which machines caused its downtime.

**Key finding:** Daikibo Factory Seiko had the highest downtime (480 minutes), almost entirely driven by a single machine type — the LaserWelder. Shenzhen followed at 420 minutes. Berlin had the least downtime (20 minutes), suggesting stronger preventive maintenance practices worth replicating elsewhere.

📊 **Dashboard screenshot:**
`/tableau-downtime-analysis/dashboard-screenshot.png`

*(Optional: publish the interactive version to Tableau Public and link it here.)*

---

## Task 2: Gender Pay Equity Analysis (Excel)

**Business question:** Following internal complaints, Daikibo's forensic tech team built an algorithm producing an "Equality Score" (-100 to +100, 0 = ideal) for each job role per factory. Negative scores indicate disparity against women; positive scores indicate disparity against men. The task was to classify every role into **Fair**, **Unfair**, or **Highly Discriminative**.

**Classification logic applied:**
| Category | Range |
|---|---|
| Fair | \|score\| ≤ 10 |
| Unfair | 10 < \|score\| ≤ 20 |
| Highly Discriminative | \|score\| > 20 |

**Key findings:**
- Across all 36 roles / 4 factories: 19 Fair, 11 Unfair, 7 Highly Discriminative.
- Every Unfair or Highly Discriminative score skewed in the same direction — against women — indicating a systemic, company-wide pattern rather than isolated or random variance.
- Disparities were concentrated in senior roles (C-Level, VP, Director, Manager), while junior/technical roles (Jr. Engineer, Machine Operator) stayed close to Fair.
- Daikibo Factory Meiyo had the most severe cases (VP: -26, C-Level: -25). Berlin was the most equitable factory, with no Highly Discriminative roles.

📄 **Output file:** `/gender-pay-equity-analysis/Equality_Table_Updated.xlsx`

---

## Skills demonstrated
- Data wrangling & schema flattening (nested JSON → tabular)
- Tableau: calculated fields, dashboard actions, cross-filtering
- Excel-based classification logic and conditional analysis
- Translating raw data into business-relevant, decision-ready insights
- Handling sensitive workplace equity data with care and precision

## Certificate
Completed via [Forage](https://www.theforage.com/) — Deloitte Australia Data Analytics Job Simulation.
