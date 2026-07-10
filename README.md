# gdp-vs-life-expectancy
Linear Regression: Life Expectancy vs GDP per Capita
A beginner-friendly machine learning demo using scikit-learn to predict life expectancy from GDP per capita, based on World Bank data via Our World in Data.

Files in This Project
File	Description
ML_LR_Demo.ipynb	Main Colab notebook (all 10 cells)
README.md	Setup and running instructions (this file)
Dataset
Source: Our World in Data — Life Expectancy vs GDP per Capita (World Bank)
URL: https://ourworldindata.org/grapher/life-expectancy-un-vs-gdp-per-capita-wb

The dataset is downloaded automatically inside the notebook (Cell 2) — no manual download is needed. If the auto-download fails (e.g., due to network restrictions), manually install the csv file and add to google collab via the folder symbol.

About the Data
Countries covered: ~180+ countries
Time span: 1950–2024 (we use the 2023 data available)
Key columns used:
gdp_per_capita — GDP per capita in USD (World Bank)
life_expectancy — Life expectancy at birth in years (UN)
Setup Instructions
Option A: Google Colab (Recommended — Zero Setup)
Go to https://colab.research.google.com
Click File → Upload notebook → switch to the Upload tab
Upload ML_LR_Demo.ipynb
Click Runtime → Restart session and Run all (or run cells one by one with Shift + Enter)
All libraries (pandas, numpy, matplotlib, scikit-learn) are pre-installed in Colab
Option B: Run as a Plain Python Script
python ML_LR_Demo.py
All outputs (plots, metrics) will be printed and saved as .png files.

Manual Dataset Download
If the automatic download of the dataset in Cell 2 fails:

Visit: https://ourworldindata.org/grapher/life-expectancy-un-vs-gdp-per-capita-wb?tab=table
Scroll down and click the Download button (bottom-right of the chart)
Select "Full data (CSV)"
Save the file as data.csv
In Cell 2, replace the auto-download block with:
raw_df = pd.read_csv('data.csv')
print(f"Dataset loaded! Shape: {raw_df.shape}")
In Google Colab: upload the file first via Files → Upload to session storage
Running the Notebook — Cell by Cell
Cell	What It Does
Cell 1	Import all libraries
Cell 2	Download dataset from Our World in Data using URL
Cell 3	Explore raw data (shape, types, missing values)
Cell 4	Preprocess: rename, filter, remove outliers, log-transform GDP
Cell 5	Exploratory plots (raw vs log GDP, distributions)
Cell 6	Prepare features, train/test split, scale
Cell 7	Train the Linear Regression model
Cell 8	Evaluate with R², RMSE, MAE
Cell 9	Plot regression line and residuals
Cell 10	Predict life expectancy for custom GDP values
Dependencies
pandas>=1.3.0
numpy>=1.21.0
matplotlib>=3.4.0
seaborn>=0.11.0
scikit-learn>=1.0.0
requests>=2.26.0
io
All of these are available by default in Google Colab. For local setups, install via the pip install <dependency name> or directly import the libraries in your code.

Expected Outputs
After running all cells, you should see:

Console: Dataset shape, preprocessing steps, model equation, R²/RMSE/MAE table, predictions
eda_plots.png: Three EDA charts (raw GDP, log GDP, histogram)
regression_results.png: Regression fit line + residual plot
Common Issues
Problem	Solution
ModuleNotFoundError	Run pip install <module> in a cell: !pip install scikit-learn
Download fails (Cell 2)	Use manual download (see above)
Column not found error	The CSV column names may have changed; print raw_df.columns and update col_map in Cell 4
Plots not showing	check your matplotlib library's import statement
