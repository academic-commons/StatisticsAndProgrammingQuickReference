---
layout: page
title: Basic Sorting Operation
menubar: r_menu
toc: true
---

# Basic Sorting Operation

-------------------------------------------------------------------

## Introduction	

We sort rows in tidyverse using the arrange(..) function. Arrange operation has the following syntax:
```
arrange(<dataframe>, <columns>)
```

**The operation of sorting does not modify the current input, instead it returns a new dataframe which is a result of the operation performed.**

When we specify multiple columns the rows are sorted based on the columns specified in that order. If 2 rows have the same value for a column, then the **tie is broken** by checking the next column values.

All the missing values or [NA]({{"/r/miscellaneous/Missing Values or NAs"|prepend:site.baseurl}}) values are placed at the end.


## Procedure

We will be working with the following dataframe:

{% highlight r %} 
# package for creating dataframe
library(tibble) 

df <- tibble(col1 = c(2,5,3,NA,3,1,NA), 
             col2 = c(10,7,9,28,6,12,23), 
             )

View(df)
{% endhighlight %}

![custom](custom.png)

We will explore sorting using single column and also explore sorting to break ties.

### Code

{% highlight r %} 
# package for creating dataframe
library(tibble) 
library(dplyr)
df <- tibble(col1 = c(2,5,3,NA,3,1,NA), 
             col2 = c(10,7,9,28,6,12,23), 
             )

# sort using single row
sorted_single <- arrange(df, col1)
View(sorted_single)
{% endhighlight %}

The output of above code is:

![single_sort](single_sort.png)


{% highlight r %} 
# package for creating dataframe
library(tibble) 
library(dplyr)
df <- tibble(col1 = c(2,5,3,NA,3,1,NA), 
             col2 = c(10,7,9,28,6,12,23), 
             )

# sort using multiple column
sorted_multiple <- arrange(df, col1, col2)
View(sorted_multiple)
{% endhighlight %}

The output of above code is:

![multiple_sort](multiple_sort.png)

For col1, 3 was causing tie and it was broken using col2 values.

## Conclusion

Thus we have successfully implemented basic sorting in tidyverse.

## References
- https://r4ds.had.co.nz/