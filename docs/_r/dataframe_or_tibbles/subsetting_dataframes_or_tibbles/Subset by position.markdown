---
layout: page
title: Subset by position
menubar: r_menu
toc: true
---

# Subset by position

-------------------------------------------------------------------

## Introduction

We have covered basics of subsetting tibble [here]({{"/r/dataframe_or_tibbles/subsetting_dataframes_or_tibbles/Basic of subsetting dataframe"|prepend:site.baseurl}}). If we only want to select single column of tibble for further processing using position we use the **[[]]** operator.

## Procedure

We will be working with the following tibble:

{% highlight r %} 
# package for creating tibble
library(tibble)

# create tibble
basic_tibble <- tibble(
  Name = c("Anthony Stark", "Steve Rogers","Bruce Banner","Carol Denvers"),
  Age = c(45,115,47,80),
  `Alias Name` = c("Ironman","Captain America","Hulk","Captain Marvel")
  )
{% endhighlight %}

The tibble contains the following data:

![basic tibble](basic tibble.png)

We will select the 2nd column.

### Code

{% highlight r %} 
# refer procedure for definition of basic_tibble
View(basic_tibble[[2]])
{% endhighlight %}

The output of above code is:

![position](position.png)

## Conclusion

Thus we have successfully covered subsetting a tibble by position.

## References
- https://r4ds.had.co.nz/