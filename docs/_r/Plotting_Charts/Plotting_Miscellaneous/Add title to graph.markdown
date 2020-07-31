---
layout: page
title: Add title to graph
menubar: r_menu
toc: true
---

# Add title to graph

-------------------------------------------------------------------

## Introduction

We will add new title to this [graph]({{"/r/Plotting_Charts/bar_graph/Color a Bar Graph"|prepend:site.baseurl}}).

## Procedure

To add a new title in ggplot2, we use the *ggtitle(...)* command. If we want title on multiple lines then we break the lines using "\n" command.

### Code

{% highlight r %} 
library(ggplot2)
# ggtitle(...)
ggplot(data = ggplot2::diamonds) + geom_bar(mapping = aes(x = cut, fill=cut)) + ggtitle("The count of various diamond cuts")
{% endhighlight %}

The output of code is:

![title](title.png)


## Conclusion

Thus we have successfully added title to graph. 


## References
- https://r4ds.had.co.nz/
- https://www.datanovia.com/en/blog/ggplot-title-subtitle-and-caption/