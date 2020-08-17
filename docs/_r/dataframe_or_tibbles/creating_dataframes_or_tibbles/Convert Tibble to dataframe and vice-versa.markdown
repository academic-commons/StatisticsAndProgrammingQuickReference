---
layout: page
title: Convert Tibble to dataframe and vice-versa
menubar: r_menu
toc: true
---

# Convert Tibble to dataframe and vice-versa

-------------------------------------------------------------------

## Introduction	

We have already covered the basics of tibble and dataframes [here]({{"/r/dataframe_or_tibbles/creating_dataframes_or_tibbles/Creating Basic Dataframe or Tibble"|prepend:site.baseurl}}). We know how to create dataframe using tibble, we will now convert tibble to data.frame and vice-versa. This might be useful when we encounter compatibility issues.

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

# view tibble
View(basic_tibble)
{% endhighlight %}

The tibble is as follows:

![basic tibble](basic.png)

And we will be working with the following data.frame:

{% highlight r %} 
# create data.frame
basic_dataframe <- data.frame(
  Name = c("Anthony Stark", "Steve Rogers","Bruce Banner","Carol Denvers"),
  Age = c(45,115,47,80),
  `Alias Name` = c("Ironman","Captain America","Hulk","Captain Marvel")
  )

# view data.frame
View(basic_dataframe)
{% endhighlight %}

The data.frame is as follows:

![basic dataframe](basic dataframe.png)

We will convert basic_tibble to data.frame and basic_dataframe to tibble using the **as.data.frame(...)** and **as_tibble(..)** functions respectively.

### Code

The basic_dataframe is converted to tibble and stored in dataframe_to_tibble.

{% highlight r %} 
# refer procedure for definition of basic_dataframe
dataframe_to_tibble <- as_tibble(basic_dataframe)
View(dataframe_to_tibble)
{% endhighlight %}


The basic_tibble is converted to data.frame and stored in tibble_to_dataframe.

{% highlight r %} 
# refer procedure for definition of basic_tibble
tibble_to_dataframe <- as.data.frame(basic_tibble)
View(tibble_to_dataframe)
{% endhighlight %}



## Conclusion

Thus we have successfully converted tibble to data.frame and vice-versa.

## References
- https://r4ds.had.co.nz/