---
layout: page
title: Create chart with multiple graphs overriding global aesthetics
menubar: r_menu
toc: true
---

# Create chart with multiple graphs overriding global aesthetics

-------------------------------------------------------------------

## Introduction

We have already covered how to create multiple graph charts by using global data [here]({{"/r/Plotting_Charts/combine_many_graphs_in_same_chart/Create chart with multiple graphs using global data"|prepend:site.baseurl}}). 

ggplot2 allows us to **override the global aesthetics with local aesthetics** for each geom function, which helps in customizing the charts further.

## Procedure

We will be working with the MPG data set present in-built in ggplot2. Few of the rows of the dataset are as follows:

![MPG head](MPG_head.png)


We have already looked at creating a multiple graph chart using global data [here]({{"/r/Plotting_Charts/combine_many_graphs_in_same_chart/Create chart with multiple graphs using global data#code"|prepend:site.baseurl}}). 

We will be customizing the aesthetics for a geom function which overrides the global aesthetics. The scatterplot is using the global aesthetics,  we will override it such that the color of the scatter points map to the class of the car.

### Code

{% highlight r %} 
library(ggplot2)
# overwrite global aesthetics with local aesthetics
ggplot(data = mpg, mapping = aes(x = displ, y = hwy)) + geom_point(mapping = aes(color = class)) + geom_smooth()
{% endhighlight %}

And the output of above code is:

![override aesthetics](multiple graphs override aesthetics.jpg)

## Conclusion

Thus we have successfully created chart with multiple graphs overriding global aesthetics. 

## References
- https://r4ds.had.co.nz/