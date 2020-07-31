---
layout: page
title: Create basic scatter plot using ggplot2
menubar: r_menu
toc: true
---

# Create basic scatter plot using ggplot2

-------------------------------------------------------------------

## Introduction	

We will be creating basic scatter plots using ggplot2. ggplot2 works based on grammar of language which you can learn more [here](https://ggplot2.tidyverse.org/)

## Procedure

We will be working with MPG data set present in-built in ggplot2. Few of the rows of the dataset are as follows:

![MPG head](MPG_head.png)

ggplot2 has the following basic formula :
```
ggplot(data = <DATA>) + <GEOM_FUNCTION>(mapping = aes(<MAPPINGS>))
```
where,

**\<DATA\>** is our dataframe. A dataframe is a rectangular collection of variables (in the columns) and observations (in the rows).

**\<GEOM_FUNCTION\>** is the type of plot we want to display. All possible types of plots we can create can be viewed [here](https://ggplot2.tidyverse.org/reference/). 

_Note_: We can add more components to the graph using the '+' operator. Learn more about it [here]({{"/r/Plotting_Charts/combine_many_graphs_in_same_chart/home"|prepend:site.baseurl}})

**\<MAPPINGS\>** is where we specify the X axis data, Y axis data, color, etc.

We will create basic scatterplot which plots the displ (engine displacement) column with the hwy(fuel efficiency on the highway) column. 

Thus our \<DATA\> is ggplot2::mpg and \<GEOM_FUNCTION\> is geom_point since we are creating scatterplot and \<MAPPINGS\> is aes(x=displ, y=hwy) where we specify the x axis data as displ and y axis data as hwy.

### Code

The code below creates basic scatter plot.

{% highlight r %} 
library(ggplot2)

# create basic scatter plot for displ and hwy columns
ggplot(data = ggplot2::mpg) + geom_point(mapping = aes(x=displ, y=hwy))

{% endhighlight %}

And the output of above code is:

![basic scatterplot](basic_scatterplot.png)


## Conclusion

Thus we have successfully created basic scatter plot using ggplot2. 

## References

- https://ggplot2.tidyverse.org/
- https://ggplot2.tidyverse.org/reference/