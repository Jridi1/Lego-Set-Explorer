
# LEGO Set Explorer – Power BI Dashboard

Interactive Power BI report that lets you browse, filter, and analyse **4 385** official LEGO® sets.  
The project demonstrates end-to-end BI workflow: data cleansing, calculated columns & DAX measures, custom parameters, bookmarks, and multi-page report design.

---

## Table of Contents
1. [Project Goals](#project-goals)
2. [Dataset](#dataset)
3. [Data Preparation](#data-preparation)
4. [Report Pages & Key Features](#report-pages--key-features)
5. [How to Run](#how-to-run)
6. [Repository Structure](#repository-structure)
7. [Next Steps](#next-steps)
8. [License](#license)

---

## Project Goals
| # | Objective | Outcome |
|---|-----------|---------|
| **1** | **Load & prepare the data** | Cleaned CSV, added Age Range & Price Range columns, plus core DAX measures (totals & averages). |
| **2** | **Design report layout & visuals** | Card KPIs, dynamic slicers, detailed table, and single-set callout with image & metadata. |
| **3** | **Add interactive components** | Numeric range parameter (Max Price), custom tooltips, bookmark-based “Reset Filters”, and page navigation. |

---

## Dataset
* **Source:** `lego_sets.csv` From Maven Analytics website.
* Original columns removed: `minifigs`, `bricksetURL`, `thumbnailURL`.
* Records without **price USD**, **age**, **pieces**, **imageURL** were filtered out.  
  *➡ Remaining rows: <span id="total-sets">4 385</span>; Price range: **$1 - $849.99**.*

---

## Data Preparation
| Step | Detail |
|------|--------|
| **Profiling** | Verified data types (numeric vs. text, date parsing). |
| **Calculated Columns** | `Age Range` → “Over 18”, “10 - 17”, “5 - 9”, “1 - 4”  •  `Price Range` → \$ / \$ \$ / \$ \$ \$ / \$ \$ \$ \$ / \$ \$ \$ \$ \$. |
| **Core Measures** | `Total Sets`, `Total Groups`, `Avg Age`, `Avg Price`, `Avg Pieces`. |
| **Parameter** | `Max Price` numeric range (0 - 850, step = 5) used to filter visuals on the fly. |

---

## Report Pages & Key Features

| Page | Highlights |
|------|------------|
| **1 · LEGO Set Finder** | KPI cards, theme/age slicers, priced table, single-set callout with image & metadata. |
| **2 · Thumbnail Gallery** | Responsive image grid for quick visual browsing (synced filters). |
| **3 · Set Explorer** | Decomposition Tree (category → theme group → theme → name) + navigation buttons. |
| **Global UX** | *Tooltips* show set image on hover • *Bookmarks* reset all filters • Visual interactions tuned so the data table never hides top-level KPIs. |

*(Screenshots live in `/assets`; embed them here once pushed).*

---

## How to Run
1. **Clone** the repo:  
   ```bash
   git clone https://github.com/jridi1/lego-set.git
   cd lego-set-explorer
   ```

2. Press **Ctrl + R** (Refresh) to load the CSV file.
