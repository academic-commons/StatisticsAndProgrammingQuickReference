---
layout: page
title: Color a Bar Graph
menubar: r_menu
toc: true
---

# Color a Bar Graph

-------------------------------------------------------------------

## Introduction	

We have already covered creating basic bar graphs [here]({{"/r/Plotting_Charts/bar_graph/Create basic bar graph"|prepend:site.baseurl}}). 

If we want to color each individual bar with a color we will use the **"fill"** argument in aes(...) function.


## Procedure

We will be working with the ggplot2::diamonds dataset, few rows of the data are:

![diamond](diamond.png)

We will create basic bar graph which shows the count for each category of diamond **cut** and color each bar with different color.

### Code

{% highlight r %} 
library(ggplot2)
# create bar graph for cut and fill color based on cut variable
ggplot(data = diamonds) + geom_bar(mapping = aes(x = cut, fill = cut))
{% endhighlight %}

And the output of above code is:
![color bar](color bar.png)


## Conclusion

Thus we have successfully filled color for bar chart.

## References
- https://r4ds.had.co.nz/