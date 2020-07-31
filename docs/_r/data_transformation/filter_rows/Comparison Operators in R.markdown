---
layout: page
title: Comparison Operators in R
menubar: r_menu
toc: true
---

# Comparison Operators in R

-------------------------------------------------------------------

## Introduction	

We have already covered basic of filter [here]({{"/r/data_transformation/filter_rows/Basic Filter Operation"|prepend:site.baseurl}}). If we want to use filters effectively, we have to know the basic comparison operators.

The basic comparison operators are:
- \>
- \>=
- <
- <=
- != (not equal)
- == (equal)
- near(..) for approximation when using floating numbers

## Procedure

We will be working with the nycflights13::flights dataset, few rows of the data are:

![flights](flights.png)

We will explore some of the comparison operators below.

### Code

{% highlight r %} 
library(dplyr)
library(nycflights13)

# >
# Amount of time spent in the air, in minutes > 300
greater <- filter(flights, air_time>300)
View(greater)
{% endhighlight %}

The output of above code is:

![greater](greater.png)

All the other comparison operators work in the same way. 

We will now discuss about the near(..) operator. The near operator is useful when we are working with floating numbers.

{% highlight r %} 
sqrt(2) ^ 2 == 2
#> [1] FALSE
1/49 * 49 == 1
#> [1] FALSE

near(sqrt(2) ^ 2, 2)
#> [1] TRUE
near(1 / 49 * 49, 1)
#> [1] TRUE
{% endhighlight %}


## Conclusion

Thus we have successfully explored the basic comparison operators in R.

## References
- https://r4ds.had.co.nz/