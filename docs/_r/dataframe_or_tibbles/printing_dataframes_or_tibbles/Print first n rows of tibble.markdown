---
layout: page
title: Print first n rows of tibble
menubar: r_menu
toc: true
---

# Print first n rows of tibble

-------------------------------------------------------------------

## Introduction

We have already covered the basics of printing tibble [here]({{"/r/dataframe_or_tibbles/printing_dataframes_or_tibbles/Basic Printing of Tibbles"|prepend:site.baseurl}}). If we wanted to print only the first n rows of tibble then we use the **n** option while printing. 

Alternatively we can print first n rows of tibble using **head(...)** function. We will cover both methods. 


## Procedure

We will be working with the following tibble:

{% highlight r %} 
# package for creating tibble
library(tibble)

# create tibble
huge_tibble <- tibble(
  col1 = 1:1e3
  )
{% endhighlight %}

The defined tibble contains following data:

![huge_tibble](huge_tibble.png)

We will print the first 5 rows of the tibble.

### Code

Using the **n** option we can print the first 5 rows.

{% highlight r %} 
# refer procedure for definition of huge_tibble
print(huge_tibble, n = 5)
{% endhighlight %}

The output of above code is:

![n](n.png)

Alternatively using the **head(..)** function we can print the first 5 rows.

{% highlight r %} 
# refer procedure for definition of huge_tibble
print(head(huge_tibble, 5))
{% endhighlight %}

The output of above code is:

![head](head.png)


## Conclusion

Thus we have successfully printed the first n rows of tibble.

## References
- https://r4ds.had.co.nz/