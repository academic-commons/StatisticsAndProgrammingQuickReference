---
layout: page
title: Select all columns except within specified range
menubar: r_menu
toc: true
---

# Select all columns except within specified range

-------------------------------------------------------------------

## Introduction	

We have already covered basics of selecting columns from dataframe [here]({{"/r/data_transformation/select_columns/Basic Select Operation"|prepend:site.baseurl}}) and how to select columns within specified range [here]({{"/r/data_transformation/select_columns/Select all columns within specified range"|prepend:site.baseurl}}).

If we want to invert our selection, i.e. select all columns except within specified range then we use the '-' operation.

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

We want to select all the columns except those columns between dep_time and arr_time.

### Code

{% highlight r %} 
library(dplyr)
library(nycflights13)

# Select all columns except those between dep_time and arr_time (inclusive)
View(select(flights, -(dep_time:arr_time)))
{% endhighlight %}

The output of above code is:

![column_range_except](column_range_except.png)

## Conclusion

Thus we have successfully selected all columns except those in the specified range.

## References
- https://r4ds.had.co.nz/