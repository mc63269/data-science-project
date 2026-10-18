# Airline Passenger Trends and Seasonality (1949–1960)

## Project Overview

This project explores historical monthly airline passenger numbers using Python. It extends the heatmap exercise completed in CISC7204 Activity 7.01 by adding a chronological line chart.

**Research question:** How did monthly airline passenger numbers change between 1949 and 1960, and what seasonal patterns can be observed?

**Status:** Completed exploratory analysis.

## Dataset Source and Usage Permissions

The original analysis uses `flight_details.csv`, provided through the CISC7204 course materials. The course notes identify Seaborn as the source.

Public reference dataset:
https://github.com/mwaskom/seaborn-data/blob/master/flights.csv

Background and units:
https://www.stat.ethz.ch/R-manual/R-devel/library/datasets/html/AirPassengers.html

The dataset contains 144 monthly observations from January 1949 to December 1960. Passenger numbers are measured in thousands.

The course file uses the columns `Years`, `Months`, and `Passengers`. The public Seaborn file uses `year`, `month`, and `passengers`.

The reviewed course materials and Seaborn data repository do not state an explicit redistribution license for this dataset. No ownership or additional permissions are claimed. The course CSV and course PDFs are not redistributed in this repository. Users should obtain the data from the original source and check applicable terms before reuse.

## Methods and Tools

- Python and Jupyter Notebook
- Pandas for loading, reshaping, and sorting data
- NumPy, imported in the original course exercise
- Seaborn for the heatmap
- Matplotlib for the line chart and image exports

The data is reshaped into a month-by-year table for the heatmap. A date column is created to arrange the observations chronologically for the line chart.

## Visualizations and Key Findings

### 1. Monthly Passenger Heatmap

![Monthly passenger heatmap](passengers_heatmap.png)

The heatmap shows higher passenger numbers in later years. July and August generally show relatively high values, revealing a recurring seasonal pattern.

### 2. Monthly Passenger Trend

![Monthly passenger trend](passengers_trend.png)

The line chart shows a rising long-term trend with repeated seasonal fluctuations. The absolute size of these fluctuations also generally increases over time.

Summing the monthly values gives annual totals of 1,520 thousand passengers in 1949 and 5,714 thousand in 1960, approximately a 3.76-fold increase.

## Limitation

This is a descriptive analysis of historical aggregate data. It does not explain the causes of passenger growth or seasonal changes, and the findings should not be assumed to represent current airline demand. No forecasting model or causal analysis is included.

## Repository Files

- `Activity7.01.ipynb`: analysis notebook
- `requirements.txt`: Python dependencies
- `passengers_heatmap.png`: month-by-year heatmap
- `passengers_trend.png`: chronological line chart

The input file `flight_details.csv` is obtained separately.

## How to Run the Analysis

The notebook was run successfully in the author's environment using Python 3.13.15. Package versions are recorded in `requirements.txt`.

1. Download this repository using **Code → Download ZIP**, then extract it.

2. Open a terminal in the airline-passengers folder:

   ```bash
   python -m pip install -r requirements.txt
   ```

3. Prepare the input data using either option below:

   - If you already have the course-provided `flight_details.csv`, place it in the same folder as `Activity7.01.ipynb`.
   - Otherwise, download `flights.csv` from the public Seaborn reference linked above. Run the following Python code from the project folder to convert its column names:

     ```python
     import pandas as pd

     flights = pd.read_csv("flights.csv")
     flights = flights.rename(columns={
         "year": "Years",
         "month": "Months",
         "passengers": "Passengers"
     })
     flights.to_csv("flight_details.csv", index=False)
     ```

4. Start Jupyter:

   ```bash
   jupyter notebook
   ```

5. Open `Activity7.01.ipynb`, restart the kernel, and run all cells from top to bottom.

6. The notebook displays both charts and saves `passengers_heatmap.png` and `passengers_trend.png` in the project folder.

## Acknowledgements

The initial heatmap analysis was completed as part of CISC7204 Tutorial 07-01, Activity 7.01. The portfolio version adds a chronological line chart, image exports, dependency documentation, and an explanation of the findings and limitation.

Data sources and course contributions are acknowledged above. AI assistance was used to support the portfolio preparation and additional code; details will be declared in the accompanying course forum submission.
