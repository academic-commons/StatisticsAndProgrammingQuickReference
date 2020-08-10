---
layout: page
title: Create boxplot from multiple numerical columns
menubar: r_menu
toc: true
---

# Create boxplot from multiple numerical columns

-------------------------------------------------------------------

## Introduction	

We have looked at basic boxplot using categorical and continous variables [here]({{"/r/Plotting_Charts/boxplot/Create basic Boxplot"|prepend:site.baseurl}}). If we had multiple numerical columns from which we want to create boxplot then we make use of the **reshape2 package**.

We will perform the following steps:

1. create a unique identifier column
2. pivot the columns into rows using melt(..) function from reshape2 package
3. create boxplot


## Procedure

We will be working with a custom dataframe.

{% highlight r %} 
# package for creating dataframe
library(tibble) 

# 100 random numbers with mean = 100 and standard deviation = 50
seed <- rnorm(100, mean=100, sd=50)

df <- tibble(col1 = seed * 2.88,
             col2 = seed * 1.22,
             col3 = seed * 2.21)
View(df)
{% endhighlight %}

Few rows of the custom dataframe are:

![custom](custom.png)

We want to create boxplot for col1, col2, and col3 to compare these continuous variables. We will first create a unique identifier which will be used during the pivot operation, perform pivot and then generate the boxplot.

### Code

#### Step 1: Create unique identifier for pivot operation:

{% highlight r %} 
# refer procedure for definition of df
# create unique identifier
df$id <- seq(1:nrow(df))
View(df)
{% endhighlight %}

The output of code is:

![id](id.png)

#### Step 2: We pivot the columns into rows using the melt(..) function and unique identifier

{% highlight r %} 
library(reshape2)

# pivot the columns col1, col2, col3 into rows
result <- reshape2::melt(df,
                         id.vars='id',
                         measure.vars=c('col1','col2','col3'))
						 
View(result)
{% endhighlight %}

The output of code is:

![pivot](pivot.png)

When the melt operation is performed, it returns dataframe with columns id, variable and value.

#### Step 3: Create boxplot

{% highlight r %} 
# refer step 2 for result
library(dplyr)
ggplot(result) + geom_boxplot(
  aes(
    x = variable, 
    y = value))
{% endhighlight %}

The output of code is:

![pivotted boxplot](pivotted boxplot.png)

## Conclusion

Thus we have successfully created boxplot from multiple numerical columns.

## References

- https://stackoverflow.com/questions/14785530/ggplot-boxplot-of-multiple-column-values