---
layout: page
title: Reorder Boxplot based on function
menubar: r_menu
toc: true
---

# Reorder Boxplot based on function

-------------------------------------------------------------------

## Introduction	

We have already discussed about basic boxplot [here]({{"/r/Plotting_Charts/boxplot/Create basic Boxplot"|prepend:site.baseurl}}). If we wanted to reorder the categorical variables of x axis based on any function such as increasing or decreasing order of median then we use the **reorder(..)** function.

The reorder function has the following syntax:
```
reorder(<categorical_variable>, <numerical_variable>, FUNCTION)
```

## Procedure

We will be working with the ggplot2::diamonds dataset, few rows of the data are:

![diamonds](diamonds.png)

We will create basic boxplot to compare price(continuous) of diamond based on its cut(categorical). We will order the cut (categorical) variable based on median price.

### Code

{% highlight r %} 
library(ggplot2)
# boxplot to compare the price of diamond based on its cut, order by median price
ggplot(data = diamonds) + geom_boxplot(mapping = 
                                         aes(
                                           x = reorder(cut, price, FUN=median), 
                                           y=price
                                           )
                                       )
{% endhighlight %}

The output of code is:

![reorder](reorder.png)

Here we can see that the cut is organized based on increasing median price.

## Conclusion

Thus we have successfully reordered a boxplot.

## References
- https://r4ds.had.co.nz/