---
layout: page
title: Sorting in descending order
menubar: r_menu
toc: true
---

# Sorting in descending order

-------------------------------------------------------------------

## Introduction	

We have already covered basic of sorting [here]({{"/r/data_transformation/sort_rows/Basic Sorting Operation"|prepend:site.baseurl}}). If we want to sort in descending order we use the desc(..) function.


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

We will explore sorting in descending order using single column and multiple columns.

### Code

{% highlight r %} 
# package for creating dataframe
library(tibble) 
library(dplyr)
df <- tibble(col1 = c(2,5,3,NA,3,1,NA), 
             col2 = c(10,7,9,28,6,12,23), 
             )

# sort using single row
sorted_single_desc <- arrange(df, desc(col1))
View(sorted_single_desc)
{% endhighlight %}

The output of above code is:

![single_sort_desc](single_sort_desc.png)


{% highlight r %} 
# package for creating dataframe
library(tibble) 
library(dplyr)
df <- tibble(col1 = c(2,5,3,NA,3,1,NA), 
             col2 = c(10,7,9,28,6,12,23), 
             )

# sort using multiple column
sorted_multiple_desc <- arrange(df, desc(col1), col2)
View(sorted_multiple_desc)
{% endhighlight %}

The output of above code is:

![multiple_sort_desc](multiple_sort_desc.png)

We are sorting col1 in descending order and sorting col2 in ascending order.

## Conclusion

Thus we have successfully sorted in descending order.

## References
- https://r4ds.had.co.nz/