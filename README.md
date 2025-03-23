# CAISO Data Analysis and Visualization

This repository provides a comprehensive analysis of electricity load and renewable generation data from CAISO (California Independent System Operator) for March 15, 2025. The analysis includes both statistical summaries and visualizations of key variables such as load and renewable energy generation from wind and solar sources.

### https://github.com/AniaSupady/Hourly-Energy-Load-Data-using-CAISO-API-Pull/blob/main/Energy_Load_Data_Pull_(Hourly_one_day)_using_CAISO.ipynb  


## Steps in the Analysis

1. **Data Fetching**:  
   Data is fetched from CAISO for the specified date, including:
   - Electricity load (demand)
   - Renewable generation forecasts (wind and solar)

2. **Data Merging**:  
   The individual datasets (load and renewable generation) are merged into a single dataframe based on the nearest timestamps using `merge_asof`. This ensures that all data points align correctly for further analysis.

3. **Data Cleaning**:  
   Missing values in the merged dataframe are forward-filled (`ffill()`), and timestamps are standardized. The 'Interval Start' column is converted to `datetime` format, and timezones are removed for consistency.

4. **Statistical Analysis**:  
   Basic statistics of the combined dataset are provided using `info()` and `describe()`, which show data types, non-null counts, and summary statistics (mean, min, max, etc.) of the numerical columns. The minimum and maximum date ranges are also printed for reference.

5. **Resampling and Aggregation**:  
   The data is resampled to hourly frequency, and the mean of all columns within each hour is calculated. The dataframe is then reset to have 'Interval Start' as a column again for easier manipulation.

6. **Visualization**:  
   Multiple visualizations are created to analyze trends over time:
   - A series of subplots is generated to visualize hourly data for wind generation, solar generation, and load.
   - Each plot is customized with titles, axis labels, and formatted x-axis ticks (showing hourly intervals).
   - The plots provide insights into how the variables change over time on the selected date.

The analysis helps understand how energy demand and renewable generation sources interact throughout the day, offering valuable insights into grid operation and forecasting.

## Key Libraries Used
- `pandas`: For data manipulation and analysis.
- `matplotlib`: For plotting and visualization.
- `gridstatus`: To fetch data from CAISO.

## Example Outputs
- Statistical summaries of the data.
- A set of visual plots showing the hourly variation in wind generation, solar generation, and load.
