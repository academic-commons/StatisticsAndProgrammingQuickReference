---
layout: page
title: Rename columns and dropping other irrelevant columns
menubar: r_menu
toc: true
---

# Rename columns and dropping other irrelevant columns

-------------------------------------------------------------------

## Introduction	

We have already covered the basics of renaming columns [here]({{"/r/data_transformation/rename_columns/Basic rename column operation"|prepend:site.baseurl}}). If we want to rename columns and drop the irrelevant columns then we use the select(...) function.


## Procedure

We will be working with a custom dataframe. 
{% highlight r %} 
# package for creating dataframe
library(tibble) 

# tibble or dataframe with column names to rename
df <- tibble(col_old_1 = as.integer(c(1,2,3)), 
             col_old_2 = c(5.0,6.3,9.7), 
             col_old_3 = c("string1", "string2","string3"),
             col_old_4 = c(FALSE, TRUE, FALSE),
             col_old_5 = as.factor(c("A","B","A")),
             )
View(df)
{% endhighlight %}

The first few rows are as follows:
![custom](custom.png)

We will rename the col_old_1 and col_old_2 columns from the custom dataframe and drop the other columns.

### Code

{% highlight r %} 
# refer procedure for definition of df
library(dplyr)

# rename the col_old_1 and col_old_2 columns and drop the other columns
results <- dplyr::select(df, 
                         col_new_1 = col_old_1, 
                         col_new_2 = col_old_2)
View(results)
{% endhighlight %}

The output of above code is:

![rename with column drop](rename with column drop.png)

## Conclusion

Thus we have successfully renamed columns and dropped other columns for a dataframe.

## References
- https://r4ds.had.co.nz/