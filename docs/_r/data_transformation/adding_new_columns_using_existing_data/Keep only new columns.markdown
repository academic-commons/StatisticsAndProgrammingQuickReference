---
layout: page
title: Keep only new columns
menubar: r_menu
toc: true
---

# Keep only new columns

-------------------------------------------------------------------

## Introduction	

We have already covered basics of mutate operation [here]({{"/r/data_transformation/adding_new_columns_using_existing_data/Basic mutate operation"|prepend:site.baseurl}}). If we only want to keep the new columns then we use the **transmute(..)** function.

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

Few rows of the data are:

![custom](custom.png)

We will use the transmute(..) operation to retain only below columns:

- col6: double all values of col1
- col7: concatenate strings in col3 with new string "new_string"
- col8: add col1 and col2

### Code

{% highlight r %} 
# refer procedure for definition of df
library(dplyr)

result <- transmute(df, 
                 # col6: double all values of col1
                 col6 = 2 * col1,
                 # col7: concatenate strings in col3 with new string "new_string"
                 col7 = paste(col3,"new_string"),
                 # col8: add col1 and col2
                 col8 = col1 + col2
                 )
View(result)
{% endhighlight %}

The output of above code is:

![transmute](transmute.png)


## Conclusion

Thus we have successfully implemented code which retains only the new columns.

## References
- https://r4ds.had.co.nz/