# 🏈 RFL Fantasy League – 2025

This repository powers the **RFL Fantasy League** website. It uses open NFL data to generate live fantasy standings for our league.

![RFL Standings Screenshot](<img width="528" height="692" alt="image" src="https://github.com/user-attachments/assets/64e39925-9100-4496-a2d4-4ed6f71dae4d" />)

---

## 📖 Overview

- **Data Source**:  
  Pulls player and team statistics from [nflverse](https://nflverse.nflverse.com/) (Football Reference data).  
- **Processing**:  
  A Jupyter Notebook ingests the raw stats into a [DuckDB](https://duckdb.org/) database for efficient querying.  
- **Export**:  
  Results are exported as structured **JSON files**.  
- **Frontend**:  
  The JSON data is loaded into the website (via jsTree and custom UI) to display standings, rosters, and player performance.

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

## 📊 Example

A portion of the standings as displayed on the site:

```
Denny [Vikings] (175 pts)
  QB (Top 2)
    JALEN HURTS (21 pts)
    LAMAR JACKSON (21 pts)
    SAM DARNOLD (10 pts)

Mass [Bengals] (162 pts)
Jumps [Packers] (157 pts)
...
```

---

## 🚀 Getting Started

### Prerequisites
- Python 3.11+
- Jupyter Notebook
- DuckDB
- Pandas

### Installation
```bash
git clone https://github.com/<your-username>/rfl-fantasy-league.git
cd rfl-fantasy-league
pip install -r requirements.txt
```

### Run Notebook
```bash
jupyter notebook
# Open and execute `rfl_pipeline.ipynb`
```

### Export Data
The notebook generates output files in `/outputs/`:
- `*.json` → For website ingestion  
- `*.csv`, `*.duckdb` → Optional for deeper analysis  

---

## 🌐 Website

The website loads the generated JSON files and renders the league standings.  
Features include:
- Expand/Collapse rosters  
- Player point breakdowns  
- Team totals  

---

## 📅 Updates

- The pipeline is automated using GitHub Actions.  
- Data refreshes occur on scheduled runs (e.g., every Monday, Tuesday, Friday morning at 8 AM EST).  

---

## 🤝 Contributing

This repo is primarily for RFL league tracking, but PRs and suggestions are welcome.

---

## 📜 License

MIT License – see [LICENSE](./LICENSE) for details.
