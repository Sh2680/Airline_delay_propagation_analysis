# Airline_delay_propagation_analysis

Identifying Source Airports That Create Network-Wide Disruptions

A completed data analytics project quantifying how delay propagates through an airline's network, using a genuine aircraft tail-number tracing methodology. Built and run end-to-end: Python cleaning → DuckDB SQL analysis → Power BI dashboard → business report.

Dataset
Source: Kaggle — giovamata/airlinedelaycauses ("Airlines Delay"), file DelayedFlights.csv
U.S. DOT / BTS on-time performance data, full year 
1,936,758 raw rows × 30 columns → cleaned to 1,928,369 rows × 41 columns

Results Summary 
269 origin airports scored for propagation risk (≥100 flights each)
Highest propagation scores belong to small regional stations (HHH 0.76, SPI 0.75, CEC 0.74), not major hubs (IAH 0.41, DAL 0.41) 
Late Aircraft Delay is the largest delay-cause category: 39.97% of total delay-minutes (31.56M of ~79M)
49.70% of flights with a known previous leg are propagation events
FSC carriers propagate more than LCC: 0.48 vs 0.44 propagation score
All three statistical tests (Pearson correlation, Welch's t-test, chi-square) came back statistically significant (p < 0.001)

Full findings, insights, and business recommendations are in Airline_analysis_project_report.docx

Tools Used

Python (Pandas, NumPy, SciPy)	---Cleaning, feature engineering, statistical testing
Matplotlib / Seaborn ---EDA visualizations
DuckDB	---In-process SQL — window functions, CTEs, joins directly on the Pandas DataFrame
Power BI	---3-page executive / operational / manager dashboard

Workflow 

DelayedFlights.csv (Kaggle, 1,936,758 rows)
       |
       v
[01_data_cleaning.ipynb]  --- cleaned, engineered, tested -> cleaned_flights.csv (1,928,369 rows)
       |
       v
[02_sql_analysis.ipynb]  --- DuckDB: propagation scoring, cohorts -> airline_delay_analysis.csv (1,928,366 rows)
       |
       v
[Power BI Dashboard]  --- 3 pages, built and screenshotted
       |
       v
[Airline_analysis_project_report.docx]  --- full findings, insights, recommendations, BA deliverables
File Structure
├── 01_data_cleaning.ipynb        # Python: cleaning, EDA, statistical tests (as run)
├── 02_sql_analysis.ipynb         # DuckDB SQL: true tail-number propagation scoring (as run)
├── 03_report.docx                # Final report: findings, insights, recommendations, BA deliverables
├── README.md                     # This file
└── (referenced, generated at runtime)
    ├── cleaned_flights.csv
    └── airline_delay_analysis.csv
