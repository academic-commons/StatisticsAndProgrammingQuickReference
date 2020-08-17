---
layout: page
title: Basic of subsetting dataframe
menubar: r_menu
toc: true
---

# Basic of subsetting dataframe

-------------------------------------------------------------------

## Introduction

We have covered basics of dataframe or tibble [here]({{"/r/dataframe_or_tibbles/creating_dataframes_or_tibbles/Creating Basic Dataframe or Tibble"|prepend:site.baseurl}}). If we only want to select single column of tibble for further processing we use the **$** operator.

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

We will select the Alias Name column.

### Code

{% highlight r %} 
# refer procedure for definition of basic_tibble
View(basic_tibble$`Alias Name`)
{% endhighlight %}

The output of above code is:

![alias](alias.png)

## Conclusion

Thus we have successfully covered basics of subsetting a tibble.

## References
- https://r4ds.had.co.nz/