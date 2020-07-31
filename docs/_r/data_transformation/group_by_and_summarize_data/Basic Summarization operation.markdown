---
layout: page
title: Basic Summarization operation
menubar: r_menu
toc: true
---

# Basic Summarization operation

-------------------------------------------------------------------

## Introduction	

Summarization operation is used to collapse a dataframe into a single value. The syntax for summarize is:
```
summarize(<dataframe>, <variable_name)> = <function_applied_to_column_to_summarize>)
```

**The summarize operation does not modify the current input, instead it returns a new dataframe which is a result of the operation performed.**

## Procedure

We will be working with a custom dataframe.
{% highlight r %} 
# package for creating dataframe
library(tibble) 

# tibble or dataframe 
df <- tibble(col1 = as.integer(c(1,2,3,4,5)), 
             col2 = c(11,12,13,14,15)
             )
View(df)
{% endhighlight %}

Few rows of the data are:

![custom basic](custom basic.png)

We will use the summarize operation to:

- find mean for col1
- find median for col2


### Code

{% highlight r %} 
# refer procedure for definition of df
library(dplyr)

result <- dplyr::summarize(df, mean_value = mean(col1), median_value = median(col2))
View(result)
{% endhighlight %}

The output of above code is:

![basic output](basic output.png)

Here 3 is the mean for col1 and 13 is median value for col2.

## Conclusion

Thus we have successfully implemented basic summarize function in tidyverse.

## References
- https://r4ds.had.co.nz/