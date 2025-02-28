# Kolexx-FPL-Team-Composition-Performance-Analysis-Data-Extraction-Power-BI-Visualization


## Business Decision Support

### Problem Statement

Fantasy Premier League (FPL) managers face challenges in optimizing their team compositions for consistent success. Many rely on intuition rather than data-driven insights, leading to suboptimal decisions regarding formations, player transfers, and budget allocation. Key challenges include:

**i) Lack of Data-Driven Decision Making** – Many managers do not leverage analytics to guide player selection.

**ii) Unclear Impact of Team Composition** – Determining the optimal balance of forwards, midfielders, and defenders over time is difficult.

**iii) Tracking Player Value Changes** – Player prices fluctuate throughout the season, affecting budget management.

**iv) Understanding Transfer Impact** – Weekly transfers need to be analysed for their impact on overall rank.

**v) Bench Utilization Issues** – Players on the bench often contribute significant points that go unused.

## Objective

This project aims to analyse team composition trends and player selection strategies by tracking how different formations, transfers, and budget decisions influence overall ranking. Insights from this analysis will help FPL managers make data-driven decisions to improve their rankings.

## Primary Data Sources

The project uses real-time data from the Fantasy Premier League API, which includes [See Python Script Here](https://github.com/Kolexx/Kolexx-FPL-Team-Composition-Performance-Analysis-Data-Extraction-Power-BI-Visualization/blob/main/scripts/FPL.ipynb):

- Player Information – Names, positions, teams, initial prices, and performance metrics.

- Gameweek Data – Weekly points, rankings, and overall team performance.

- Transfer Data – History of transfers made, including buying and selling prices.

- Team Selection Data – Players selected for each gameweek, including starters and bench players.

# Data Storage & Processing

- Data is fetched using Python (requests and pandas).

- Cleaned and structured into CSV format [Download here](https://github.com/Kolexx/Kolexx-FPL-Team-Composition-Performance-Analysis-Data-Extraction-Power-BI-Visualization/blob/main/data/FPL_Team_Analysis.csv).

- Processed data is visualized using Power BI.

# Data Preparation

which are Data Cleaning & Transformation : A structured approach was taken to clean and transform the raw data into a format suitable for analysis. The steps included:

**Handling Missing Values:**

- Identified missing values in critical columns such as Buying Price and Selling Price.

- Used previous gameweek data to fill in missing prices where applicable.

- If a player’s price was missing and no historical data was available, their entry was flagged for further review.

**Standardizing Column Names:**

- Ensured all dataset headers followed a consistent naming convention.

- Renamed ambiguous column names to improve readability (e.g., element renamed to Player ID).

**Merging Datasets:**

- Combined multiple datasets, including player performance, team selection history, and rankings.

- Used Pandas' merge() function with Player ID as the common key.

- Resolved issues where the same player appeared multiple times in different datasets by using drop_duplicates().

**Removing Duplicates:**

- Used drop_duplicates(subset=['Player ID', 'Gameweek']) to ensure no duplicate records existed per gameweek.

- Verified that all unique Player ID entries had valid associated gameweek data.

**Creating Derived Features:**

- Formation Composition – Counted the number of Goalkeepers, Defenders, Midfielders, and Forwards per gameweek using groupby() and value_counts().

- Transfer Effectiveness – Computed the difference in points before and after transfers to assess their impact on overall ranking.

- Bench Contribution – Compared points earned by starting players versus those left on the bench, highlighting potential lost points.

- Captain Impact – Evaluated how captain and vice-captain choices influenced total team points using multipliers applied to selected players.










