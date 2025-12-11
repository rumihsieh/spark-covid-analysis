# COVID-19 Data Analysis with Apache Spark (New York State)

This project demonstrates how to use Apache Spark (RDD API) and Scala to process, aggregate, and analyze COVID-19 case and testing data from the New York State Health Department. The analysis includes data cleaning, key-value aggregation, positivity rate calculations, and time-based trend exploration across counties and months. The notebook is structured to resemble a real-world Spark-based data engineering workflow, covering data ingestion, transformation, and computation of summary metrics.

## Project Overview
Using Spark RDD transformations, this project fetches JSON data for all New York counties, parses the records into an RDD of `(date, county, positive_cases, total_tests)`, and performs several analyses including:  
- Total statewide cases and tests  
- Total cases/tests by county  
- Monthly positivity rate across the state  
- Daily positivity per county using safe division with `Option[Double]`  
- Highest positivity day in the dataset  
- Monthly positivity rate for each county, sorted by county and date  

The dataset covers the period **2020-12-04 to 2023-08-30**.

## Technologies Used
- Scala  
- Apache Spark (RDD API)  
- JSON data parsing  
- Functional programming (map, reduce, reduceByKey, pattern matching)  
- Option type for safe computations  

## Repository Structure
spark-covid-analysis/
│
├── spark-covid-data-analysis.ipynb # Main analysis notebook
└── README.md # Documentation

## Key Analysis Steps
1. **Data Acquisition** – Construct API URLs for each county, download JSON records, and convert the raw data into an RDD.  
2. **Data Cleaning and Transformation** – Extract relevant fields, validate date ranges, and create filtered RDDs.  
3. **Aggregation** – Use `reduce` and `reduceByKey` to compute totals statewide and by county, and to group records by month.  
4. **Trend Analysis** – Compute statewide monthly positivity rates, daily positivity rates per county, and identify the highest positivity day.

## Sample Results
**Monthly positivity rate (statewide):**
(2022-01, 15.09)
(2023-08, 14.12)
(2021-12, 10.54)
(2022-07, 9.54)

**Highest positivity day:**
(2023-07-02, Tompkins, 100.0)

These results highlight county-level variations and periods of elevated transmission.

## How to Run
1. Open the notebook using JupyterLab or Jupyter Notebook.  
2. Ensure Scala and Spark are available in your environment.  
3. Run the notebook cells to reproduce all computations.

## Future Improvements
- Rewrite analysis using Spark DataFrame API for improved optimization  
- Add data visualizations for trends  
- Export results to CSV/Parquet  
- Build an interactive dashboard  

## License
This project is for educational and portfolio purposes.
