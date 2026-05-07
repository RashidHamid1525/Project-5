# Project #5 – North Dakota Pipeline Water Quality Analysis

## Project Overview

This project analyzes water quality data for the North Dakota Pipeline Water Quality project. The main goal is to determine whether water quality changes as water moves from Lake Sakakawea through the McClusky Canal system and toward the Sheyenne River / Lake Ashtabula area.

The project focuses on important water quality parameters such as Total Dissolved Solids (TDS), sulfate, calcium, magnesium, pH, and other major ions. Python was used to clean the dataset, organize the data, create summary statistics, generate graphs, and calculate predicted mixed TDS values using a dynamic function.

## Client

Garrison Diversion Project and Red River Valley Water Supply Project (RRVWSP)

## Project Goals

The goals of this project are to:

- Determine whether water quality appears to degrade along the canal system
- Identify which water quality parameters may be most concerning
- Calculate summary statistics for important water quality parameters
- Create boxplots for selected parameters by location
- Create a graph showing average TDS trends
- Build a dynamic TDS mixing function
- Test different flow and concentration scenarios
- Discuss coding choices and possible sources of bias


## Python Packages Used

This project uses the following Python packages:

- pandas
- numpy
- matplotlib
- seaborn

## Methods

The analysis follows these steps:

1. Import the water quality dataset
2. Clean the dataset by converting measurement values to numeric values
3. Remove rows missing important analysis information
4. Filter the dataset to selected water quality parameters
5. Filter the dataset to the main project locations
6. Calculate summary statistics by location and parameter
7. Create boxplots for key water quality parameters
8. Create a line graph showing average TDS by location
9. Define a mass loading function
10. Define a TDS mixing function
11. Run scenario testing for low flow, base case, and high flow conditions
12. Create a bar chart showing predicted mixed TDS by scenario

## Parameters Analyzed

The project focuses on several important water quality parameters, including:

- Total dissolved solids
- Sulfate
- Calcium
- Magnesium
- pH
- Bicarbonate
- Chloride
- Sodium
- Carbonate
- Hardness
- Sodium adsorption ratio

## Locations Analyzed

The main locations used in the analysis are:

- Lake Sakakawea
- Sheyenne River - Lisbon
- Lake Ashtabula

These locations were ordered from source to destination so the graphs show the water system in the correct direction.

## Summary Statistics

The project calculates the following statistics for each selected parameter at each location:

- Mean
- Median
- Minimum
- Maximum
- Count

These statistics help compare how water quality changes across locations.

## Visualizations

The notebook includes three main graphs.

### Graph 1 – Boxplots of Key Parameters by Location

This graph compares four important water quality parameters across the selected locations:

- Total dissolved solids
- Sulfate
- Calcium
- Magnesium

The boxplots help show the spread, median, and possible outliers in the data.

### Graph 2 – Average TDS Trend Along the System

This graph shows how average TDS changes between the selected locations. TDS is important because it represents dissolved solids in the water.

### Graph 3 – Predicted Mixed TDS by Scenario

This graph shows the predicted mixed TDS values for different flow and concentration scenarios.

## TDS Mixing Function

A dynamic function was created to calculate mixed TDS concentration after canal water mixes with river water.

```python
def tds_mixing(pipe_flow, pipe_tds, river_flow, river_tds):
    mixed_tds = (pipe_flow * pipe_tds + river_flow * river_tds) / (pipe_flow + river_flow)
    return round(mixed_tds, 2)
```

This function allows the user to change:

- Pipe flow
- Pipe TDS
- River flow
- River TDS

The result is the predicted mixed TDS concentration.

## Scenario Testing

Three scenarios were tested:

| Scenario | Description |
|---|---|
| Low Flow | Lower river flow and lower pipe TDS |
| Base Case | Middle-condition example |
| High Flow | Higher river flow and higher pipe TDS |

Scenario testing helps show how changes in flow rate and concentration affect the final mixed TDS value.

## How to Run the Notebook

1. Download or clone this repository
2. Make sure `Project5.csv` is in the same folder as the notebook
3. Open `Project5_Water_Quality_Code_Only.ipynb` in Jupyter Notebook or JupyterLab
4. Run the notebook from top to bottom
5. Review the summary statistics, graphs, and scenario testing results

## Coding Choices and Bias

Several coding choices may affect the results:

- Missing values were removed from important analysis columns
- Only selected project locations were used
- Only selected water quality parameters were analyzed
- Graphs were chosen to make trends easier to understand
- The TDS mixing function assumes complete mixing

These choices make the analysis easier to understand, but they may also simplify the real water quality system.

## Project Team

- Rashid Hamid
- Abbas Bashir
- Abdi Aden
