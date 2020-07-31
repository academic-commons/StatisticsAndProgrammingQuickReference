---
layout: page
title: Basic rename column operation
menubar: r_menu
toc: true
---

# Basic rename column operation

-------------------------------------------------------------------

## Introduction	

If we want to rename columns for a dataframe, use the rename(...) function :
```
rename(<dataframe>, <new_column_name>=<old_column_name>)
```

**The operation of renaming columns does not modify the current input, instead it returns a new dataframe which is a result of the operation performed.**


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

We will rename the col_old_1, col_old_2 and col_old_3 columns from the custom dataframe.

### Code

{% highlight r %} 
# refer procedure for definition of df
library(dplyr)

# rename the col_old_1, col_old_2, and col_old_3 columns
results <- dplyr::rename(df, 
                         col_new_1 = col_old_1, 
                         col_new_2 = col_old_2, 
                         col_new_3 = col_old_3)
View(results)
{% endhighlight %}

The output of above code is:

![basic rename](basic rename.png)

<b>Note:</b> When we renamed the columns all the original columns are preserved, if we want to rename columns and drop the other columns refer [this]({{"/r/data_transformation/rename_columns/Rename columns and dropping other irrelevant columns"|prepend:site.baseurl}}).

## Conclusion

Thus we have successfully renamed columns for dataframe.

## References
- https://r4ds.had.co.nz/