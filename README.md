# Surfs Up Statistical Analysis

## Overview

The purpose of this analysis was to utilize SQLite and SQLAlchemy to analyze temperature data and analyze the statistical summaries for the month of June and December.

## Results

Looking at the summary statistics for both June and December we can see some key differences:

-- For June there were 1700 data points, while in December there were only 1517 data points.

-- Across the board, June had higher temperatures. 

-- The standard deviation for June was 3.26 while for December it was 3.75. 


| June Statistical Summary  | December Statistical Summary |
| ------------- | ------------- |
| <img src="https://github.com/kimcheese33/surfs_up/blob/main/Images/june_temps.png"/>  | <img src="https://github.com/kimcheese33/surfs_up/blob/main/Images/dec_temps.png"/>  |


## Summary

By looking at the statistical summaries for June and December we can see that June had higher temperatures, which makes sense as June is a summer month. In addition, we can see that June's data is a little more reliable since the standard deviation is lower. This might be because June also had about 2,000 more data points than December. If we wanted to gather more weather data for June and December we could write two more queries to get how much it rained in either month.

Getting precipitation for June:

```python
june_rain = session.query(Measurement.prcp).filter(extract('month', Measurement.date) == 6).all()
```

Getting precipitation for December:

```python
dec_rain = session.query(Measurement.prcp).filter(extract('month', Measurement.date) == 12).all()
```


