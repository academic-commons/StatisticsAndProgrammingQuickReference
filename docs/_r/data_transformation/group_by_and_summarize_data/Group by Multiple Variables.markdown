---
layout: page
title: Group by Multiple Variables
menubar: r_menu
toc: true
---

# Group by Multiple Variables

-------------------------------------------------------------------

## Introduction	

We have already covered basics of group by operation [here]({{"/r/data_transformation/group_by_and_summarize_data/Basic Group by operation"|prepend:site.baseurl}}). We can perform group by using multiple columns.


## Procedure

We will be working with a custom dataframe.
{% highlight r %} 
# package for creating dataframe
library(tibble) 

# tibble or dataframe 
df <- tibble(col1 = as.integer(c(1,2,3,4,5)), 
             col2 = c(11,12,13,14,15),
             col3 = c("A", "B", "A", "B", "C"),
             col4 = c("X", "X", "Y", "Y", "Y")
             )
View(df)
{% endhighlight %}

Few rows of the data are:

![custom group by multiple](custom group by multiple.png)

We will use the group by and summarize operation to:

- group by col3 and col4 and then:

	- find mean for col1 
	- fnd median for col2
	
Thus the group by col3 and col4 operation will create intermediate results of:

Group "AX":

![AX](AX.png)

Group "BX":

![BX](BX.png)

Group "AY":

![AY](AY.png)

Group "BY":

![BY](BY.png)

Group "CY":

![CY](CY.png)


And then we perform summarization on each of these groups.

### Code

{% highlight r %} 
# refer procedure for definition of df
library(dplyr)

# group by col3 and col4
grouped_data <- dplyr::group_by(df, col3, col4)

# then summarize
result <- summarize(grouped_data, mean_value=mean(col1), median_value=median(col2))
View(result)
{% endhighlight %}

The output of above code is:

![custom group by multiple output](custom group by multiple output.png)

We first grouped by col3 and col4, thus we got groups of AX, BX, AY, BY and CY. Then we performed summarization on each group to get final result.

## Conclusion

Thus we have successfully implemented group by with multiple variables in tidyverse.

## References
- https://r4ds.had.co.nz/