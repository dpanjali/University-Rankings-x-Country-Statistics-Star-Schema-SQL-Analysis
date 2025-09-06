# 🌍 University Rankings x Country Statistics – SQL Data Warehouse

📊 A SQL-based analytical project combining university rankings and UN country statistics to explore how national factors like GDP, literacy, and development status influence education performance.

---

## 📦 Project Overview

This project integrates two datasets:
- `World University Rankings` (THE)
- `UN Country Statistics` (GDP, literacy, income groups, etc.)

The goal is to build a **star-schema data warehouse** in SQLite and run analytical SQL queries to answer questions like:
- Do wealthier countries perform better in university rankings?
- Is there a relationship between literacy rate and teaching scores?
- How has development status impacted education performance over time?

---

## 🗂️ Star Schema Design

The dimensional model includes:
- 📐 `Dim_University`: University names
- 🌍 `Dim_Location`: Country, continent, ISO codes
- 🕒 `Dim_Year`: Year of ranking/statistics
- 📈 `ScoreDimension`: Contains score types like teaching, research, citations
- 🏆 `UniversityRankingFact`: Fact table storing scores, ranks, and country-level indicators

📌 **Attribute Hierarchies**  
- `Dim_Location`: Continent → Country  
- `Dim_Year`: Year (supports time-based slicing)

📊 **Fact Table Measures**  
- Teaching score  
- Overall rank  
- GDP per capita, literacy rate, development status

---

## 🛠️ Technologies Used

- **SQLite** for database modeling and queries  
- **DB Browser for SQLite** for interface  
- **Draw.io** for star schema design  
- **Excel** and **Power Query** for initial data cleaning  
- **SQL** (INNER JOIN, subqueries, CASE WHEN, GROUP BY, HAVING)

---

## 📌 Key SQL Features

- `JOIN` across multiple dimension tables  
- `GROUP BY` and `HAVING` for grouped insights  
- `CASE WHEN` for development classification  
- Data filtering with `WHERE`, `LIKE`, and subqueries  
- Derived columns using calculations (e.g., log(GDP))

---

## 📊 Sample Research Questions

1. 📉 **Does GDP per capita influence university teaching scores?**  
   → Join `Fact` and `Dim_Location` tables and aggregate teaching scores by GDP bands.

2. 🌍 **Which regions consistently produce the top 100 universities?**  
   → Use `Dim_Location` with rankings filtered by `rank < 100`.

3. 🕒 **Has educational performance improved in developing nations between 2012–2016?**  
   → Use `Dim_Year` to perform year-wise analysis by development status.

---

## 📈 Insights

- High GDP and literacy rates correlate with stronger teaching scores.
- Developing nations show gradual improvement but are underrepresented in top-tier rankings.
- Regional disparities highlight global inequity in access to world-class education.

---

## 📁 Project Structure

