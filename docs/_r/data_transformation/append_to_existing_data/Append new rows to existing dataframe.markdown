---
layout: page
title: Append new rows to existing dataframe
menubar: r_menu
toc: true
---

# Append new rows to existing dataframe

-------------------------------------------------------------------

## Introduction	

We can append new rows to existing dataframe in multiple ways - 



## Procedure

We will be working with a custom dataframe:

{% highlight r %} 
# package for creating dataframe
library(tibble) 

# tibble or dataframe 
df <- tibble(col1 = as.integer(c(1,2,3,4,5)), 
             col2 = c(11,12,13,14,15)
             )
View(df)
{% endhighlight %}

Few rows of the dataframe are as follows:

![custom](custom.png)

We will append a new row with values 6 and 16.

### Code

{% highlight r %} 
# refer procedure for definition of df
library(dplyr)

# add new column to dataframe using mutate
result <- mutate(df, col3 = c("A","B","C","D","E"))
View(result)
{% endhighlight %}

The output of above code is:

![append new column](append new column.png)


## Conclusion

Thus we have successfully appended new column to existing dataframe.

## References

- https://stackoverflow.com/questions/20689650/how-to-append-rows-to-an-r-data-frame