---
layout: page
title: Append new rows to existing dataframe
menubar: r_menu
toc: true
---

# Append new rows to existing dataframe

-------------------------------------------------------------------

## Introduction	

We can append new rows to existing dataframe using the **rbind** function. The syntax for rbind is as follows:

```
rbind(existing_dataframe, dataframe_to_append)
```

**The rbind operation does not modify the current input, instead it returns a new dataframe which is a result of the operation performed.**

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
library(tibble)

# add new row to dataframe using rbind
result <- rbind(df, tibble(col1 = c(6), col2 = c(16)))
View(result)
{% endhighlight %}

The output of above code is:

![append new row](append new row.png)


## Conclusion

Thus we have successfully appended new row to existing dataframe.

## References

- https://stackoverflow.com/questions/20689650/how-to-append-rows-to-an-r-data-frame