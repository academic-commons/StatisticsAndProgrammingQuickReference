---
layout: page
title: Sorting logical values, factors, strings, and date objects
menubar: r_menu
toc: true
---

# Sorting logical values, factors, strings, and date objects

-------------------------------------------------------------------

## Introduction	

We have already covered basic of sorting [here]({{"/r/data_transformation/sort_rows/Basic Sorting Operation"|prepend:site.baseurl}}). We will now discuss how logical values, factors, strings and date objects are sorted.


## Procedure

We will be working with the following dataframe:

{% highlight r %} 
# package for creating dataframe
library(tibble) 
# package for creating date object in R
library(lubridate)

# tibble or dataframe with different types of variables
df <- tibble(col1 = as.integer(c(1,2,3)), 
             col2 = c(5.0,6.3,9.7), 
             col3 = c("string1", "string2","string3"),
             col4 = c(FALSE, TRUE, FALSE),
             col5 = as.factor(c("A","B","A")),
             col6 = c(             
               make_date(year = 2020L, month = 1L, day = 15L),
               make_date(year = 2020L, month = 6L, day =29L),
               make_date(year = 2020L, month = 9L, day = 16L)
             ),
             
             )
View(df)
{% endhighlight %}

![custom2](custom2.png)

### Code


#### Logical Values: 

For logical values, FALSE comes before TRUE.

{% highlight r %} 
# df is defined in procedure
# sort the logical values
logical_values_sort <- arrange(df, col4)
View(logical_values_sort)
{% endhighlight %}

The output of above code is:

![logical_values_sort](logical_values_sort.png)

#### Factors: 

For factors, values are sorted based on how they were defined.

{% highlight r %} 
# df is defined in procedure
# sort the factor column
factor_sort <- arrange(df, col5)
View(factor_sort)
{% endhighlight %}

The output of above code is:

![factor_sort](factor_sort.png)


#### Strings: 

For strings, values are sorted based [Lexicographic Order](https://chortle.ccsu.edu/java5/Notes/chap92/ch92_2.html).

{% highlight r %} 
# df is defined in procedure
# sort the string column in descending order
string_sort <- arrange(df, desc(col3))
View(string_sort)
{% endhighlight %}

The output of above code is:

![string_sort](string_sort.png)


#### Dates: 

For dates, values are sorted based calendar order.

{% highlight r %} 
# df is defined in procedure
# sort the date column in descending order
date_sort <- arrange(df, desc(col6))
View(date_sort)
{% endhighlight %}

The output of above code is:

![date_sort](date_sort.png)


## Conclusion

Thus we have successfully applied sorting to logical values, factors, strings and date objects.

## References
- https://r4ds.had.co.nz/
- https://chortle.ccsu.edu/java5/Notes/chap92/ch92_2.html