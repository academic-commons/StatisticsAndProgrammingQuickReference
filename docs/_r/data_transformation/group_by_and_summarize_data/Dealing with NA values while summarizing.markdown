---
layout: page
title: Dealing with NA values while summarizing
menubar: r_menu
toc: true
---

# Dealing with NA values while summarizing

-------------------------------------------------------------------

## Introduction	

*NA* are missing values or not applicable columns in data. You can read more about NA [here]({{"/r/miscellaneous/Missing Values or NAs"|prepend:site.baseurl}}). We need to handle the NA values before summarizing or else the summarized outputs will be NA as well. 

We set the **na.rm** argument to TRUE while summarizing. By setting this argument we remove all the NA values from our dataframe and then perform summarization function.

## Procedure

We will be working with a custom dataframe.
{% highlight r %} 
# package for creating dataframe
library(tibble) 

# tibble or dataframe 
df <- tibble(col1 = as.integer(c(1,2,3,4,5, 6)), 
             col2 = c(11,12,13,14,15, NA)
             )
View(df)
{% endhighlight %}

Few rows of the data are:

![deal na custom](deal na custom.png)

We will perform summarization while setting the na.rm argument to TRUE and FALSE and analyze the results.

### Code

- #### When na.rm = FALSE:

{% highlight r %} 
# refer procedure for definition of df
library(dplyr)

# summarize col1 and col2 while setting na.rm = FALSE
result <- summarize(df, mean_col1=mean(col1, na.rm = FALSE), mean_col2=mean(col2, na.rm = FALSE))
View(result)
{% endhighlight %}

The output of above code is:

![na.rm = FALSE](na.rm = FALSE.png)

When na.rm = FALSE, which is the default value for na.rm, the summarized value is NA.

- #### When na.rm = TRUE:

{% highlight r %} 
# refer procedure for definition of df
library(dplyr)

# summarize col1 and col2 while setting na.rm = TRUE
result <- summarize(df, mean_col1=mean(col1, na.rm = TRUE), mean_col2=mean(col2, na.rm = TRUE))
View(result)
{% endhighlight %}

The output of above code is:

![na.rm = TRUE](na.rm = TRUE.png)

When na.rm = TRUE, the NA values are removed and then the summarization is performed, thus we get the mean value of 13 for col2.

## Conclusion

Thus we have successfully handled NA values while summarizing data.

## References
- https://r4ds.had.co.nz/