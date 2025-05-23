# KAIM solar challenge 
Solar Dataset Analysis Project

Overview
This project profiles, cleans, and analyzes solar datasets from Benin, Sierra Leone, and Togo to evaluate solar potential and compare metrics GHI, DNI, DHI. It includes EDA in country-specific notebooks benin_eda.ipynb, sierraleone_eda.ipynb, togo_eda.ipynb and cross-country synthesis in compare_countries.ipynb on the compare-countries branch.

What the Code Does
EDA on eda-<country> branches: Loads raw CSVs from data/<country>.csv. Computes summary statistics and checks missing values. Flags outliers using Z-scores where |Z| > 3 for GHI, DNI, DHI, ModA, ModB, WS, WSgust. Clips unrealistic values, setting negatives to 0 and capping highs at 1200 W/m^2 for GHI, DNI, ModA, ModB and 300 W/m^2 for DHI. Generates time series, wind roses, histograms, correlation heatmaps, scatter plots, and bubble charts of GHI vs. Tamb with size based on RH and BP. Exports cleaned CSVs to data/<country>_clean.csv.
Synthesis on compare-countries branch: Loads cleaned CSVs from ../../data/<country>_clean.csv into dfs. Creates boxplots comparing GHI, DNI, DHI across countries with Benin in blue, Sierra Leone in orange, Togo in green. Produces a summary table of mean, median, std and a bar chart ranking average GHI.

How to Use
Prerequisites: Install dependencies with pip install pandas matplotlib seaborn numpy. Ensure Python 3.8+ and Jupyter Notebook. Place raw CSVs in data/, excluded via .gitignore.
Setup: Clone the repository and checkout branches using git clone [https://github.com/kalebb1/solar-challenge-week1.git], git checkout eda-<country> for EDA, or git checkout compare-countries for synthesis.
Run EDA: Open <country>_eda.ipynb in Jupyter. Execute cells to profile, clean, and visualize data. Output includes cleaned CSV data/<country>_clean.csv and plots.
Run Synthesis: Open compare_countries.ipynb in Jupyter. Ensure cleaned CSVs are in ../../data/. Run cells to load data, clean unrealistic values, and generate boxplots, summary table, and GHI bar chart.

Outputs
EDA: Cleaned datasets, visualizations including time series, wind roses, bubble charts.
Synthesis: Boxplots, summary table e.g., Benin GHI mean 241.94 W/m^2, GHI ranking Benin > Togo > Sierra Leone.

