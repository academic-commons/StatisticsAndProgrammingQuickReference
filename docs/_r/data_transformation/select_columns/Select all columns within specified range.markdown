---
layout: page
title: Select all columns within specified range
menubar: r_menu
toc: true
---

# Select all columns within specified range

-------------------------------------------------------------------

## Introduction	

We have already covered basics of selecting columns from dataframe [here]({{"/r/data_transformation/select_columns/Basic Select Operation"|prepend:site.baseurl}}). If we want to select 10 columns, then instead of explicitly specifying the column names, we can instead specify the column range.


## Procedure

We will be working with the nycflights13::flights dataframe. The first few rows are as follows:
![flights](flights.png)

The columns in flight dataframe are:
- "year"
- "month"
- "day"
- "dep_time"
- "sched_dep_time"
- "dep_delay"
- "arr_time"
- "sched_arr_time"
- "arr_delay"
- "carrier"
- "flight"
- "tailnum"
- "origin"
- "dest"
- "air_time"
- "distance"
- "hour"
- "minute"
- "time_hour"    

We want to select all the columns between dep_time and arr_time, both inclusive.

### Code

{% highlight r %} 
library(dplyr)
library(nycflights13)

# Select all columns between year and day (inclusive)
View(select(flights, dep_time:arr_time))
{% endhighlight %}

The output of above code is:

![column_range](column_range.png)

## Conclusion

Thus we have successfully selected columns from specified range.

## References
- https://r4ds.had.co.nz/