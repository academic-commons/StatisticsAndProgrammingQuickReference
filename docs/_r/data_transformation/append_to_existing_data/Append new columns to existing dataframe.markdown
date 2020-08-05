---
layout: page
title: Append new columns to existing dataframe
menubar: r_menu
toc: true
---

# Append new columns to existing dataframe

-------------------------------------------------------------------

## Introduction	

We can append new columns to existing dataframe using the mutate operation.

**The mutate operation does not modify the current input, instead it returns a new dataframe which is a result of the operation performed.**

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

We will add a new column col3 with values "A","B","C","D","E".

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
- https://r4ds.had.co.nz/