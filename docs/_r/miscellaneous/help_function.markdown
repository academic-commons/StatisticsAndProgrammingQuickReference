---
layout: page
title: R Documentation
menubar: r_menu
toc: true
---

# View R function documentation

-----------------------------------------------------------------------------------------

## Introduction

Viewing the documentation of any function or object can really help us debug the code and understand the various options available for the function.

## Procedure

In R console type **?** followed by any function or object name to get its documentation.

### Code
{% highlight r %} 
library(ggplot2)

?ggplot2::geom_point

{% endhighlight %}

The output for above code is:
![r_documentation](r_documentation.png)

## Conclusion

Thus we have successfully viewed the documentation for any function or object

## References

- https://www.r-project.org/help.html