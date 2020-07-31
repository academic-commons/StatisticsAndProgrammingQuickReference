---
layout: page
title: Basic rearrange column operation
menubar: r_menu
toc: true
---

# Basic rearrange column operation

-------------------------------------------------------------------

## Introduction	

If we want to rearrange columns in a dataframe, we use the select(...) function :
```
select(<dataframe>, <new_column_order>)
```

We have already covered basics of select operations [here]({{"/r/data_transformation/select_columns/Basic Select Operation"|prepend:site.baseurl}})

**The operation of rearranging columns does not modify the current input, instead it returns a new dataframe which is a result of the operation performed.**


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

We will rearrange the columns such that the new order is: col1, col4, col2.

### Code

{% highlight r %} 
# refer procedure for definition of df
library(dplyr)

# rearrange the columns to col1, col4, col2.
results <- dplyr::select(df, col1, col4, col2)
View(results)
{% endhighlight %}

The output of above code is:

![basic rearrange](basic rearrange.png)

## Conclusion

Thus we have successfully rearranged columns for dataframe.

## References
- https://r4ds.had.co.nz/