---
layout: page
title: Basic Printing of Tibbles
menubar: r_menu
toc: true
---

# Basic Printing of Tibbles

-------------------------------------------------------------------

## Introduction

We have covered basics of dataframe or tibble [here]({{"/r/dataframe_or_tibbles/creating_dataframes_or_tibbles/Creating Basic Dataframe or Tibble"|prepend:site.baseurl}}). To print tibble in R console we use the **print(...)** function. To view tibble in an interactive fashion in *RStudio* we use the **view(...)** function.

## Procedure

We will be working with the following tibble:

{% highlight r %} 
# package for creating tibble
library(tibble)

# create tibble
basic_tibble <- tibble(
  Name = c("Anthony Stark", "Steve Rogers","Bruce Banner","Carol Denvers"),
  Age = c(45,115,47,80),
  Alias = c("Ironman","Captain America","Hulk","Captain Marvel")
  )
{% endhighlight %}

The tibble contains the following data:

![raw_data](raw_data.png)

We will print the basic_tibble tibble in console using the print(...) function and view the tibble in RStudio using view(..) function.

### Code

{% highlight r %} 
# refer procedure for definition of basic_tibble
print(basic_tibble)
{% endhighlight %}

The output of above code is:

![print_tibble](print_tibble.png)

{% highlight r %} 
# refer procedure for definition of basic_tibble
View(basic_tibble)
{% endhighlight %}

The output of above code is:

![view_tibble](view_tibble.png)


## Conclusion

Thus we have successfully covered basics of printing tibble.

## References
- https://r4ds.had.co.nz/