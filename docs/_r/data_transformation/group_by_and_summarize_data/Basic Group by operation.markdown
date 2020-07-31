---
layout: page
title: Basic Group by operation
menubar: r_menu
toc: true
---

# Basic Group by operation

-------------------------------------------------------------------

## Introduction	

Group by operation is used with [summarize(..)]({{"/r/data_transformation/group_by_and_summarize_data/Basic Summarization operation"|prepend:site.baseurl}}) function. It helps to summarize data based on *desired groups instead on the entire dataset*.

The syntax for group by is:
```
grouped_data <- group_by(<dataframe>, <columns_to_group_by>)
summarize(grouped_data, <variable_name)> = <function_applied_to_column_to_summarize>)
```


## Procedure

We will be working with a custom dataframe.
{% highlight r %} 
# package for creating dataframe
library(tibble) 

# tibble or dataframe 
df <- tibble(col1 = as.integer(c(1,2,3,4,5)), 
             col2 = c(11,12,13,14,15),
             col3 = c("A", "B", "A", "B", "C")
             )
View(df)
{% endhighlight %}

Few rows of the data are:

![custom basic groupby](custom basic groupby.png)

We will use the group by and summarize operation to:

- group by col3 and then:

	- find mean for col1 
	- fnd median for col2
	
Thus the group by col3 operation will create intermediate results of:

Group "A":

![A](A.png)

Group "B":

![B](B.png)

Group "C":

![C](C.png)


And then we perform summarization on each of these groups.

### Code

{% highlight r %} 
# refer procedure for definition of df
library(dplyr)

grouped_data <- dplyr::group_by(df, col3)
result <- summarize(grouped_data, mean_value=mean(col1), median_value=median(col2))
View(result)
{% endhighlight %}

The output of above code is:

![custom basic groupby output](custom basic groupby output.png)

We first grouped by col3, thus we got groups based on column value A, B and C. Then we performed summarization on each group to get final result.

## Conclusion

Thus we have successfully implemented basic group by function in tidyverse.

## References
- https://r4ds.had.co.nz/