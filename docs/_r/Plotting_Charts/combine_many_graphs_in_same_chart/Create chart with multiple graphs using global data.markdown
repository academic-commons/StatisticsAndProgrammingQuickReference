---
layout: page
title: Create chart with multiple graphs using global data
menubar: r_menu
toc: true
---

# Create chart with multiple graphs using global data

-------------------------------------------------------------------

## Introduction

We have already covered how to create basic multiple graph charts [here]({{"/r/Plotting_Charts/combine_many_graphs_in_same_chart/Create basic chart with multiple graphs"|prepend:site.baseurl}}). 

The drawback of the previous method is that we were *explicitly* specifying mapping in each geom function:

... + geom_point(**mapping = aes(x = displ, y = hwy)**) + geom_smooth(**mapping = aes(x = displ, y = hwy)**)

It will be tedious to change the mapping individually for each geom function. Fortunately, ggplot2 supports global data which will be *implicitly* used by every geom function.

## Procedure

We will be working with the MPG data set present in-built in ggplot2. Few of the rows of the dataset are as follows:

![MPG head](MPG_head.png)


We have already looked at creating a basic multiple graph charts [here]({{"/r/Plotting_Charts/combine_many_graphs_in_same_chart/Create basic chart with multiple graphs#code"|prepend:site.baseurl}}). 

We will now setup a global data which can be used by all geom functions.

### Code

We specify the global data in the ggplot(...) function itself.

{% highlight r %} 
library(ggplot2)
# multiple geoms in same plot using global data
ggplot(data = mpg, mapping = aes(x = displ, y = hwy)) + geom_point() + geom_smooth()
{% endhighlight %}

And the output of above code is:

![global data](multiple graphs.jpg)

We can explicitly [override global data]({{"/r/Plotting_Charts/combine_many_graphs_in_same_chart/Create chart with multiple graphs overriding global data"|prepend:site.baseurl}}) and [override global aesthetics]({{"/r/Plotting_Charts/combine_many_graphs_in_same_chart/Create chart with multiple graphs overriding global aesthetics"|prepend:site.baseurl}}) also.

## Conclusion

Thus we have successfully created multiple graph on same charts using global data. 

## References
- https://r4ds.had.co.nz/