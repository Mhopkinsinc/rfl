# 🏈 RFL Fantasy League – 2025

This repository powers the **RFL Fantasy League** website. It uses open NFL data to generate fantasy standings for the keeper league.

<img width="528" height="692" alt="image" src="https://github.com/user-attachments/assets/f639f48e-5192-4441-bebf-d77ed6b7931c" />

---

## 📖 Overview

- **Data Source**:  
  Pulls player and team statistics from [nflverse](https://nflverse.nflverse.com/) (Football Reference data).
- **Processing**:  
  A Jupyter Notebook ingests the raw stats into a [DuckDB](https://duckdb.org/) database for efficient querying.
- **Export**:  
  Results are exported as structured **JSON files**.  
- **Frontend**:  
  The JSON data is loaded into the website (via jsTree and custom UI) to display standings, rosters, and player points.

---

## ⚙️ Data Flow

1. **Fetch Data**  
   The notebook retrieves NFL player statistics from nflverse.

2. **Ingest into DuckDB**  
   Stats are cleaned and inserted into a local DuckDB database.

3. **Transform & Aggregate**  
   Custom fantasy scoring rules are applied (QB, RB, WR, TE, K, DL, LB, DB).

4. **Export JSON**  
   The processed results are exported as JSON files (e.g., `rfl_standings_2025.json`).

5. **Website Integration**  
   The exported JSON is consumed by the website, where standings and details update automatically.

---

## 🌐 Website

The Github pages website loads the generated JSON files and renders the league standings.
Features include:
- Expand/Collapse rosters  
- Player point breakdowns  
- Team totals  

---

## 📅 Updates

- The pipeline is automated using GitHub Actions.  
- Data refreshes occur on scheduled runs (e.g., every Monday, Tuesday, Friday morning at 8 AM EST).  
