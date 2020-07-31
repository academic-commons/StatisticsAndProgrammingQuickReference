---
layout: page
title: Basic mutate operation
menubar: r_menu
toc: true
---

# Basic mutate operation

-------------------------------------------------------------------

## Introduction	

We can add new columns that are functions of existing columns. We use the mutate(...) function to achieve this. Basic syntax of mutate is:
```
mutate(<dataframe>, <new_column> = <function_applied_to_old_column>)
```

**The mutate operation does not modify the current input, instead it returns a new dataframe which is a result of the operation performed.**

## Procedure

We will be working with a custom dataframe.
{% highlight r %} 
# package for creating dataframe
library(tibble) 

# tibble or dataframe with column names to rename
df <- tibble(col1 = as.integer(c(1,2,3)), 
             col2 = c(5.0,6.3,9.7), 
             col3 = c("string1", "string2","string3"),
             col4 = c(FALSE, TRUE, FALSE),
             col5 = as.factor(c("A","B","A")),
             )
View(df)
{% endhighlight %}

Few rows of the data are:

![custom](custom.png)

We will use the mutate operation to:

- double all values in col1 to create new col6
- concatenate strings in col3 with new string "new_string" to create  new col7
- create new col8 which is addition of col1 and col2

### Code

{% highlight r %} 
# refer procedure for definition of df
library(dplyr)

result <- mutate(df, 
                 # double all values in col1 to create new col6
                 col6 = 2 * col1,
                 # concatenate strings in col3 with new string "new_string" to create  new col7
                 col7 = paste(col3,"new_string"),
                 # create new col8 which is addition of col1 and col2
                 col8 = col1 + col2
                 )
View(result)
{% endhighlight %}

The output of above code is:

![basic mutate](basic mutate.png)


## Conclusion

Thus we have successfully implemented basic mutate function in tidyverse.

## References
- https://r4ds.had.co.nz/