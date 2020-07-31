---
layout: page
title: Multiple arguments to filter
menubar: r_menu
toc: true
---

# Multiple arguments to filter

-------------------------------------------------------------------

## Introduction	

We have already covered basic of filter [here]({{"/r/data_transformation/filter_rows/Basic Filter Operation"|prepend:site.baseurl}}). If we want to use multiple filters then we use boolean operators.

The basic boolean operators are:
- & is "and"
- \| is "or"
- ! is "not"

The boolean operators can be used as follows:
![boolean](boolean.png)

source: https://r4ds.had.co.nz/transform.html


Additionally we will also explore the **%in%** operator. It is used to check whether the column contains the values specified in vector.


## Procedure

We will be working with the nycflights13::flights dataset, few rows of the data are:

![flights](flights.png)

We will explore some of the boolean operators and the %in% operator below.

### Code

{% highlight r %} 
library(dplyr)
library(nycflights13)

# & operator
# Amount of time spent in the air, in minutes > 300 and carrier is UA
and_operator <- filter(flights, air_time>300 & carrier == "UA")
View(and_operator)
{% endhighlight %}

The output of above code is:

![and](and.png)

All the other boolean operators work in the same way. 

We will now discuss about the %in% operator. We want to find the flights for the month of 7, 8, 9, 12. Instead of using multiple & operators we will make use of %in% operator.

{% highlight r %} 
library(dplyr)
library(nycflights13)

# %in% operator
# flights for the month of 7, 8, 9, 12
in_operator <- filter(flights, month %in% c(7,8,9,12))
View(in_operator)
{% endhighlight %}

The output of above code is:

![in](in.png)

## Conclusion

Thus we have successfully applied multiple filters using boolean operators.

## References
- https://r4ds.had.co.nz/