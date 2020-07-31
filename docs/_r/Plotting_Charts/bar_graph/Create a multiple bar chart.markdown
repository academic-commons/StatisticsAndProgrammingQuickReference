---
layout: page
title: Create a multiple bar chart
menubar: r_menu
toc: true
---

# Create a multiple bar chart

-------------------------------------------------------------------

## Introduction	

We have already covered creating basic bar graphs [here]({{"/r/Plotting_Charts/bar_graph/Create basic bar graph"|prepend:site.baseurl}}). 

If we want to create multiple bar chart then we will use the **position="dodge"** argument in geom_bar(..) function. We also specify the category for creating multiple bars using **fill=\<categorical variable\>** in the aes(...) function.


## Procedure

We will be working with the ggplot2::diamonds dataset, few rows of the data are:

![diamond](diamond.png)

We will create bar graph which shows the count for each category of diamond **cut** and create multiple bars based on **clarity** of diamond.

### Code

{% highlight r %} 
library(ggplot2)
# multiple bar based on clarity
ggplot(data = diamonds) + geom_bar(mapping = aes(x = cut, fill = clarity), position = "dodge")
{% endhighlight %}

And the output of above code is:
![multiple bars](multiple bars.png)


## Conclusion

Thus we have successfully created multiple bar chart.

## References
- https://r4ds.had.co.nz/