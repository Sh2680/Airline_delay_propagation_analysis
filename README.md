# Airline_delay_propagation_analysis

📌 Project Overview

An end-to-end airline network analytics project that identifies airports associated with delay propagation by tracing aircraft movements using aircraft tail numbers.

The project analyzes how delays propagate from one flight to the next and identifies airports with higher network-level propagation risk.

Dataset: Kaggle — giovamata/airlinedelaycauses
Source: U.S. DOT / Bureau of Transportation Statistics (BTS)

Dataset size: 1,936,758 raw rows × 30 columns 

🎯 Business Problem

Flight delays can propagate when an aircraft arriving late operates its next scheduled flight.

This project answers:

Which airports are associated with higher delay propagation?
How frequently do delays propagate between consecutive aircraft legs?
Which delay causes contribute most to total delay?
How does propagation differ between Full-Service Carriers and Low-Cost Carriers?

📊 Key Results
269 airports scored for propagation risk using a minimum threshold of 100 flights.
Highest propagation scores were observed at:
HHH — 0.76
SPI — 0.75
CEC — 0.74
Major hubs such as IAH and DAL scored 0.41.
Late Aircraft Delay accounted for 39.97% of total delay minutes (~31.56M of ~79M minutes).
49.70% of flights with a known previous aircraft leg were identified as propagation events.
Propagation score:
FSC: 0.48
LCC: 0.44


Detailed findings, statistical results, business insights, and recommendations are available in the Project Report.

🛠️ Tools & Technologies

Python: Pandas, NumPy, SciPy
Visualization: Matplotlib, Seaborn
SQL: DuckDB
BI: Power BI
Documentation: Microsoft Word

🔄 Workflow
DelayedFlights.csv
        ↓
Python
Cleaning + Feature Engineering + EDA + Statistical Testing
        ↓
cleaned_flights.csv
        ↓
DuckDB SQL
Tail-number tracing + Propagation Scoring
        ↓
airline_delay_analysis.csv
        ↓
Power BI
3-page Executive / Operational / Manager Dashboard
        ↓
Business Report


The CSV files are generated during the analysis workflow.

📊 Dashboard

The project includes a 3-page Power BI dashboard covering:

Executive Summary
Operational Analysis
Manager Analysis

See the dashboard screenshots and detailed analysis in the project report.




