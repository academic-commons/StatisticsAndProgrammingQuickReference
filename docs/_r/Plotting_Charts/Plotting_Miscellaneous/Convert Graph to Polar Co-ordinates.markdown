---
layout: page
title: Convert Graph to Polar Co-ordinates
menubar: r_menu
toc: true
---

# Convert Graph to Polar Co-ordinates

-------------------------------------------------------------------

## Introduction

The default coordinate system is the Cartesian coordinate system where the x and y position act independently to find the location of each point. We can change the co-ordinate system to polar co-ordinate, which will help to comprehend the data effectively.

## Procedure

We will be working with the diamonds data set present in-built in ggplot2. Few of the rows of the dataset are as follows:

![diamond](diamond.png)

We have already looked at creating a basic bar chart [here]({{"/r/Plotting_Charts/bar_graph/Create basic bar graph"|prepend:site.baseurl}}). We will convert the bar chart into polar co-ordinate system which will give us Coxcomb chart.


### Code

{% highlight r %} 
library(ggplot2)
# bar chart
ggplot(data = ggplot2::diamonds) + geom_bar(mapping = aes(x = cut, fill=cut))
{% endhighlight %}

The output of code is:

![basic bar](basic bar.png)


{% highlight r %} 
library(ggplot2)
# coxcomb chart by converting to polar coordinates
ggplot(data = ggplot2::diamonds) + geom_bar(mapping = aes(x = cut, fill=cut)) + coord_polar()
{% endhighlight %}

The output of code is:

![polar](polar.png)



## Conclusion

Thus we have successfully converted the Cartesian co-ordinate system to polar co-ordinate system.


## References
- https://r4ds.had.co.nz/