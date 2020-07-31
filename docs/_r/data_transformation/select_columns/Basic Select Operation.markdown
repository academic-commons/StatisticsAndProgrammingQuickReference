---
layout: page
title: Basic Select Operation
menubar: r_menu
toc: true
---

# Basic Select Operation

-------------------------------------------------------------------

## Introduction	

If we want only a subset of columns from the entire dataframe, then we make use of the select(..) function. Select operation has the following syntax:
```
select(<dataframe>, <columns>)
```

**The operation of selecting columns does not modify the current input, instead it returns a new dataframe which is a result of the operation performed.**


## Procedure

We will be working with the nycflights13::flights dataframe. The first few rows are as follows:
![flights](flights.png)

We will select the year, month, and day columns from the flights dataframe.

### Code

{% highlight r %} 
library(dplyr)
library(nycflights13)

# select the year, month, day column
View(select(flights, year, month, day))
{% endhighlight %}

The output of above code is:

![basic_select](basic_select.png)

## Conclusion

Thus we have successfully implemented basic selection of columns.

## References
- https://r4ds.had.co.nz/