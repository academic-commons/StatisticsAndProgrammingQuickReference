---
layout: page
title: Find type of variable
menubar: r_menu
toc: true
---

# Find type of variable in R

-----------------------------------------------------------------------------------------

## Introduction

We have already covered basic types of 

## Procedure

We created a dataframe and put various types of variables in it.

### Code
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
print(df)
{% endhighlight %}

The output for above code is:
![variables](variables.png)

## Conclusion

Thus we have successfully viewed the different types of variables in R.

## References

- https://www.r-project.org/help.html