---
layout: page
title: Creating Basic Dataframe or Tibble
menubar: r_menu
toc: true
---

# Creating Basic Dataframe or Tibble

-------------------------------------------------------------------

## What are dataframes?

data.frames are R's inbuilt data structure used to represent rectangular data like csv file. The data.frame data structure is present in R's base package and is available without loading external libraries.

## What are tibbles?	

tibbles are dataframes but with some modifications which make it easier to work with over traditional data.frames data structure. We need to load the tidyverse package since tibbles are part of tidyverse package.

## Dataframe vs Tibble

Tibbles never changes the type of the inputs (e.g., it never converts strings to factors!), it never changes the names of variables, and it never creates row names.

It’s possible for a tibble to have column names that are not valid R variable names, aka nonsyntactic names. For example, they might not start with a letter, or they might contain unusual characters like a space. To refer to these variables, you need to surround them with backticks, `.

Tibbles are preferred over traditional data.frame due to:

1. [Printing]({{"/r/dataframe_or_tibbles/printing_dataframes_or_tibbles/home"|prepend:site.baseurl}})
2. [Subsetting]({{"/r/dataframe_or_tibbles/subsetting_dataframes_or_tibbles/home"|prepend:site.baseurl}})

## Procedure

We will create a basic data frame using *tibbles* and the following raw data:

![raw_data](raw_data.png)


### Code

{% highlight r %} 
# package for creating tibble
library(tibble)

# create tibble
basic_tibble <- tibble(
  Name = c("Anthony Stark", "Steve Rogers","Bruce Banner","Carol Denvers"),
  Age = c(45,115,47,80),
  Alias = c("Ironman","Captain America","Hulk","Captain Marvel")
  )

# view tibble
View(basic_tibble)
{% endhighlight %}

The output of above code is:

![basic](basic.png)


## Conclusion

Thus we have successfully created basic dataframe or tibble.

## References
- https://r4ds.had.co.nz/