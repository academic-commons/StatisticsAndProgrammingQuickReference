---
layout: page
title: Basic Filter Operation
menubar: r_menu
toc: true
---

# Basic Filter Operation

-------------------------------------------------------------------

## Introduction	

Filter in tidyverse allows you to subset dataframe based on specified conditions. Filter operation has the following syntax:
```
filter(<dataframe>, <conditions>)
```

filter() only includes rows where the condition is TRUE; it excludes both FALSE and [NA]({{"/r/miscellaneous/Missing Values or NAs"|prepend:site.baseurl}}) values. **The operation of filtering does not modify the current input, instead it returns a new dataframe which is a result of the operation performed.**

## Procedure

We will be working with the nycflights13::flights dataset, few rows of the data are:

![flights](flights.png)

We want to filter rows based on flights which are on 1st January, thus dataframe is flights and condition is month == 1, day == 1.

### Code

{% highlight r %} 
library(dplyr)
library(nycflights13)

# filter flights for 1st January
result <- filter(flights, month == 1, day == 1)
View(result)
{% endhighlight %}

And the output of above code is:

![basic filter](basic filter.png)


## Conclusion

Thus we have successfully implemented basic filter in tidyverse.

## References
- https://r4ds.had.co.nz/