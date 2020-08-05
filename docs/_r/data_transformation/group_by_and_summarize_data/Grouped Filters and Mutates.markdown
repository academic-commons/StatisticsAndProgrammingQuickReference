---
layout: page
title: Grouped Filters and Mutates
menubar: r_menu
toc: true
---

# Grouped Filters and Mutates

-------------------------------------------------------------------

## Introduction	

We have already covered basics of group by operation [here]({{"/r/data_transformation/group_by_and_summarize_data/Basic Group by operation"|prepend:site.baseurl}}) and covered basics of filter [here]({{"/r/data_transformation/filter_rows/Basic Filter Operation"|prepend:site.baseurl}}) and mutate [here]({{"/r/data_transformation/adding_new_columns_using_existing_data/Basic mutate operation"|prepend:site.baseurl}}). Mutate operation creates new columns from existing columns.

We can combine the group by operation with filter and mutate operation.

## Procedure

We will be working with a custom dataframe.
{% highlight r %} 
# package for creating dataframe
library(tibble) 

# tibble or dataframe 
df <- tibble(col1 = as.integer(c(1,2,3,4,5,21,22,23)), 
             col2 = c(11,12,13,14,15,31,32,33),
             col3 = c("A", "B", "A", "B", "C","A", "B", "A"),
             col4 = c("X", "X", "Y", "Y", "Y","X", "X", "Y")
             )
View(df)
{% endhighlight %}

Few rows of the data are:

![custom group filter](custom group filter.png)

We will use the group by and filter operation to:
- group by col3 and col4 and then:
	- apply filter for each group to keep only those rows which have col1 > 20
	
We will use the group by and mutate operation to:
- group by col3 and col4 and then:
	- create new column col5, for each row group such that col5 = col1 + 100

### Code

- Group by Filter:

{% highlight r %} 
# refer procedure for definition of df
library(dplyr)

# group by col3 and col4
grouped_data <- dplyr::group_by(df, col3, col4)

# filter
result <- filter(grouped_data, col1>20)
View(result)
{% endhighlight %}

The output of above code is:

![group by filter](group by filter.png)

We first grouped by col3 and col4, thus we got groups of AX, BX, AY, BY and CY. Then we applied filter on each group to get final result.

- Group by Mutate:

{% highlight r %} 
# refer procedure for definition of df
library(dplyr)

# group by col3 and col4
grouped_data <- dplyr::group_by(df, col3, col4)

# mutate
result <- mutate(grouped_data, col5 = col1 + 100)
View(result)
{% endhighlight %}

The output of above code is:

![group by mutate](group by mutate.png)

We first grouped by col3 and col4, thus we got groups of AX, BX, AY, BY and CY. Then we applied mutate operation on each group to get final result.

## Conclusion

Thus we have successfully implemented group by with filter and mutate.

## References
- https://r4ds.had.co.nz/