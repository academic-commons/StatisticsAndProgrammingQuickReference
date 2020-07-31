---
layout: page
title: Rearrange and keep all columns
menubar: r_menu
toc: true
---

# Rearrange and keep all columns

-------------------------------------------------------------------

## Introduction	

We have already covered basics of rearrange operations [here]({{"/r/data_transformation/rearrange_columns/Basic rearrange column operation"|prepend:site.baseurl}}). If we want to rearrange and keep all columns then we make use of **everything(..)** helper function.


## Procedure

We will be working with a custom dataframe. 
{% highlight r %} 
# package for creating dataframe
library(tibble) 

# tibble or dataframe with column names to rename
df <- tibble(col1 = as.integer(c(1,2,3)), 
             col2 = c(5.0,6.3,9.7), 
             col3 = c("string1", "string2","string3"),
             col4 = c(FALSE, TRUE, FALSE),
             col5 = as.factor(c("A","B","A")),
             )
View(df)
{% endhighlight %}

The first few rows are as follows:

![custom](custom.png)

We will rearrange the columns such that the new order is: col1, col4, col2 and *retain all the columns*.

### Code

{% highlight r %} 
# refer procedure for definition of df
library(dplyr)

# rearrange the columns to col1, col4, col2 and retain all other columns
results <- dplyr::select(df, col1, col4, col2, dplyr::everything())
View(results)
{% endhighlight %}

The output of above code is:

![retain rearrange](retain rearrange.png)

## Conclusion

Thus we have successfully rearranged columns and retained all the columns in a dataframe.

## References
- https://r4ds.had.co.nz/