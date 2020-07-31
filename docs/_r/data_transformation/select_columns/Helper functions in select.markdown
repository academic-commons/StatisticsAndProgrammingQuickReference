---
layout: page
title: Helper functions in select
menubar: r_menu
toc: true
---

# Helper functions in select

-------------------------------------------------------------------

## Introduction	

We have already covered basic select operation [here]({{"/r/data_transformation/select_columns/Basic Select Operation"|prepend:site.baseurl}}). There are certain helper functions which will help select columns conveniently.

Some of the helper functions are:

- starts_with(...)
- ends_with(...)
- contains(...)
- matches(...)
- num_range(...)

## Procedure

We will be working with the following custom dataframe. 
{% highlight r %} 
# package for creating dataframe
library(tibble) 

df <- tibble(col_end1 = as.integer(c(1,2,3)), 
             col_end2 = as.integer(c(4,5,6)), 
             col2 = c(5.0,6.3,9.7), 
             col3 = c("string1", "string2","string3"),
             col4 = c(FALSE, TRUE, FALSE),
             col5 = as.factor(c("A","B","A")),
             start_col1 = as.integer(c(11,22,33)), 
             start_col2 = as.integer(c(44,53,64)), 
             col_contain_1 = as.integer(c(101,228,303)), 
             col_contain_2 = as.integer(c(443,335,664)), 
             )
View(df)
{% endhighlight %}

The first few rows are as follows:
![custom](custom.png)

We will explore the following helper functions:

- starts_with(\<pattern\>): It will select the columns that start with the pattern specified.
- ends_with(\<pattern\>): It will select the columns that end with the pattern specified.
- contains(\<pattern\>):  It will select the columns that contain the pattern specified.
- matches(\<regex\>):  It will select the columns that match the specified regex.
- num_range(\<column_name\>, \<integer_range\>):  It will select the columns that satisfy the column_name+integer_range combinations.

### Code

#### 1. starts_with:

{% highlight r %} 
# refer procedure for definition of df
# select all columns that start with start
View(select(df, starts_with("start")))
{% endhighlight %}

The output of above code is:

![starts_with](starts_with.png)

Thus we have selected the columns that start with the pattern "start".

#### 2. ends_with:

{% highlight r %}
# refer procedure for definition of df
# select all columns that end with end1, end2
View(select(df, ends_with("end1"),ends_with("end2"))) 
{% endhighlight %}

The output of above code is:

![ends_with](ends_with.png)

Thus we have selected the columns that end with the pattern "end1" or "end2".

#### 3. contains:

{% highlight r %} 
# refer procedure for definition of df
# select all columns that contain "contain"
View(select(df, contains("contain")))
{% endhighlight %}

The output of above code is:

![contains](contains.png)

Thus we have selected the columns that contain the pattern "contain".

#### 4. matches:

{% highlight r %} 
# refer procedure for definition of df
# select columns that match the regex "^col"
View(select(df, matches("^col")))
{% endhighlight %}

The output of above code is:

![matches](matches.png)

Thus we have selected the columns that match the regex pattern "^col", which means starts with col.

#### 5. num_range:

{% highlight r %} 
# refer procedure for definition of df
# select columns col2, col3
View(select(df, num_range("col", 2:3)))
{% endhighlight %}

The output of above code is:

![num_range](num_range.png)

Thus we have selected the columns that form combinations of col with numbers 2 and 3 i.e. col2 and col3.

## Conclusion

Thus we have successfully explored helper function for select operation.

## References
- https://r4ds.had.co.nz/