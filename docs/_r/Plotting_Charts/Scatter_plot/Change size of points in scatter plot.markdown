---
layout: page
title: Size of Scatter plot
menubar: r_menu
toc: true
---

# Change size of points in scatter plot

-------------------------------------------------------------------

## Introduction	

Once we have created a [basic scatterplot]({{"/r/Plotting_Charts/Scatter_plot/Create basic scatter plot using ggplot2"|prepend:site.baseurl}}) we can change the size of the points based on the *size attribute of aes(...) function*. An aesthetic or aes(...) is a visual property of the objects in your plot. Aesthetics include things like the size, the shape, or the color of your points. 

We can change the size based on **categorical variable** in our data. We can also change the size of the points explicitly without using categorical variable. We will explore both in the below section.


## Procedure

We will be working with MPG data set present in-built in ggplot2. Few of the rows of the dataset are as follows:

![MPG head](MPG_head.png)

We will create scatter plot of displ vs hwy and the size of the points will be based on categorical variable *class*. We will also create same scatterplot but manually setting the size.

### Code

Change size of scatter plot point based on categorical variable:

{% highlight r %} 
library(ggplot2)
ggplot(data = mpg) + geom_point(mapping = aes(x = displ, y = hwy, size = class))
{% endhighlight %}

And the output of above code is:

![scatterplot size](scatterplot size categorical.png)


Change size of scatter plot manually:

{% highlight r %} 
library(ggplot2)
ggplot(data = mpg) + geom_point(mapping = aes(x = displ, y = hwy), size = 10.0)
{% endhighlight %}

And the output of above code is:
![scatterplot size manual](scatterplot size manually.png)

## Conclusion

Thus we have successfully changed the size of point in scatter plot. 

## References
- https://stackoverflow.com/questions/34638902/point-size-in-ggplot-2-0-0