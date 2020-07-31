---
layout: page
title: Create facet grid charts
menubar: r_menu
toc: true
---

# Create facet grid charts

-------------------------------------------------------------------

## Introduction

Details about basic facet chart can be found [here]({{"/r/Plotting_Charts/Facet_charts/Create basic facet chart"|prepend:site.baseurl}}) which uses facet_wrap(..). When we want to create facets based on single categorical variable then facet_wrap(..) is ideal. But when we want to create facets based on multiple categorical variable then facet_grid(..) is best, since it utilizes space more efficiently.

## Procedure

We will be working with the MPG data set present in-built in ggplot2. Few of the rows of the dataset are as follows:

![MPG head](MPG_head.png)


We have already looked at creating a basic scatterplot [here]({{"/r/Plotting_Charts/Scatter_plot/Create basic scatter plot using ggplot2"|prepend:site.baseurl}}). We plotted the car's engine displacement (displ) with the fuel efficiency (hwy) variable.

<h6> Additionally if we wanted to visualize the displacement of the car and the fuel efficiency based on the class and type of drive train of the car, we can use facet_grid(...) for this.</h6>


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

The drv variable which is the type of drive train for a car has the following levels: f = front-wheel drive, r = rear wheel drive, 4 = 4wd.


### Code

The code below creates a facet grid chart. Here we use the **facet_grid(...)** function, where we specify the categorical variable on which we want to facet. 'class' and 'drv' are our selected variables.

{% highlight r %} 
library(ggplot2)
# multiple categorical variables drv and class
ggplot(data = mpg) + geom_point(mapping = aes(x = displ, y = hwy)) + facet_grid(drv ~ class)
{% endhighlight %}

The output of code is:

![facet grid](multiple facet_grid.jpg)

The column headers are class of car and row headers are train drive type.

## Conclusion

Thus we have successfully created facet grid chart. 
