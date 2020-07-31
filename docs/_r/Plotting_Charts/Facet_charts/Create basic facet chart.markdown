---
layout: page
title: Create basic facets chart
menubar: r_menu
toc: true
---

# Create basic facets chart

-------------------------------------------------------------------

## What are Facets Charts?

Facets are "one side of something many-sided". In ggplot2 Facet charts are subplots that plot the dataset based on categorical variable's levels. 

Facet charts are very useful when working with a categorical variable.

But these are not practical when the categorical variable has too many levels. At that point, it is better to use colors for each level, find more about it [here]({{"/r/Plotting_Charts/Scatter_plot/Change color of points in scatter plot"|prepend:site.baseurl}}) .

## Procedure

We will be working with the MPG data set present in-built in ggplot2. Few of the rows of the dataset are as follows:

![MPG head](MPG_head.png)


We have already looked at creating a basic scatterplot [here]({{"/r/Plotting_Charts/Scatter_plot/Create basic scatter plot using ggplot2"|prepend:site.baseurl}}). We plotted the car's engine displacement (displ) with the fuel efficiency (hwy) variable.

<h6> Additionally if we wanted to visualize the displacement of the car and the fuel efficiency based on the class of the car, we can use facets chart for this.</h6>

Note: The unique levels of the class variable are:
{% highlight r %} 
library(ggplot2)
unique(mpg$class)
{% endhighlight %}

- "compact"    
- "midsize"    
- "suv"        
- "2seater"    
- "minivan"  
- "pickup"     
- "subcompact"


### Code

The code below creates a basic facets chart. Here we use the **facet_wrap(...)** function, where we specify the categorical variable on which we want to facet. 'class' is our selected variable.

{% highlight r %} 
library(ggplot2)
# here we facet on single categorical variable
ggplot(data = mpg) + geom_point(mapping = aes(x = displ, y = hwy)) + facet_wrap(~ class)
{% endhighlight %}

And the output of above code is:

![basic facet](basic facet.jpg)

We can also facet on *multiple categorical variables*, but facet_wrap(..) is best suited for single categorical variable, since it utilizes the space efficiently. 

{% highlight r %} 
library(ggplot2)

# here we facet on multiple categorical variable
# drv is the type of drive train, where f = front-wheel drive, r = rear wheel drive, 4 = 4wd
ggplot(data = mpg) + geom_point(mapping = aes(x = displ, y = hwy)) + facet_wrap(drv ~ class)
{% endhighlight %}

The output of code is:

![basic multiple facet](basic multiple facet.jpg)

It is better to use [facet_grid(...)]({{"/r/Plotting_Charts/Facet_charts/Create facet grid charts"|prepend:site.baseurl}}) when we want to plot multiple categorical variables using facet charts.


## Conclusion

Thus we have successfully created basic facet chart using ggplot2. 
