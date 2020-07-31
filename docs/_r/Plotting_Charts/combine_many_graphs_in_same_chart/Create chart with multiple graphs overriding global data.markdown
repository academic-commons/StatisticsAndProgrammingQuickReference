---
layout: page
title: Create chart with multiple graphs overriding global data
menubar: r_menu
toc: true
---

# Create chart with multiple graphs overriding global data

-------------------------------------------------------------------

## Introduction

We have already covered how to create multiple graph charts by using global data [here]({{"/r/Plotting_Charts/combine_many_graphs_in_same_chart/Create chart with multiple graphs using global data"|prepend:site.baseurl}}). 

ggplot2 allows us to **override the global data with local data** for each geom function, which helps in customizing the charts further.


## Procedure

We will be working with the MPG data set present in-built in ggplot2. Few of the rows of the dataset are as follows:

![MPG head](MPG_head.png)


We have already looked at creating a multiple graph chart using global data [here]({{"/r/Plotting_Charts/combine_many_graphs_in_same_chart/Create chart with multiple graphs using global data#code"|prepend:site.baseurl}}). 

We will be creating a subset of the original data and use that data to plot a line graph. The scatterplot is using the global data whereas the line graph uses the local data.

### Code

{% highlight r %} 
library(ggplot2)
library(dplyr)

# create a subset of global data
local_data <- filter(mpg, class == "subcompact")

# overwrite global data with local data
ggplot(data = mpg, mapping = aes(x = displ, y = hwy)) + geom_point() + geom_smooth(data = local_data, se = FALSE )
{% endhighlight %}

And the output of above code is:

![override data](multiple graphs override data.jpg)


## Conclusion

Thus we have successfully created chart with multiple graphs overriding global data. 

## References
- https://r4ds.had.co.nz/