---
layout: page
title: Create a basic Stacked Bar graph
menubar: r_menu
toc: true
---

# Create a basic Stacked Bar graph

-------------------------------------------------------------------


## Introduction	

We have already covered creating basic bar graphs [here]({{"/r/Plotting_Charts/bar_graph/Create basic bar graph"|prepend:site.baseurl}}) and how to color a bar chart [here]({{"/r/Plotting_Charts/bar_graph/Color a Bar Graph"|prepend:site.baseurl}}). 

If we want to create stacked bar chart we will make use of the **fill="\<categorical variable\>"** argument in aes.


## Procedure

We will be working with the ggplot2::diamonds dataset, few rows of the data are:

![diamond](diamond.png)

We will create bar graph which shows the count for each category of diamond **cut** and create stacks based on **clarity** of diamond.

### Code

{% highlight r %} 
library(ggplot2)
# stack based on clarity
ggplot(data = diamonds) + geom_bar(mapping = aes(x = cut, fill = clarity))
{% endhighlight %}

And the output of above code is:
![stack basic bar](stack basic bar.png)


## Conclusion

Thus we have successfully created basic stacked bar chart.

## References
- https://r4ds.had.co.nz/