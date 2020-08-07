---
layout: page
title: Basic operator chaining using pipes
menubar: r_menu
toc: true
---

# Basic operator chaining using pipes

-------------------------------------------------------------------

## Introduction	

We have already covered basic operations in tidyverse:

- [filter rows]({{"/r/data_transformation/filter_rows/Basic Filter Operation"|prepend:site.baseurl}})
- [mutate or add new columns using existing data]({{"/r/data_transformation/adding_new_columns_using_existing_data/Basic mutate operation"|prepend:site.baseurl}})
- [group by]({{"/r/data_transformation/group_by_and_summarize_data/Basic Group by operation"|prepend:site.baseurl}}) and [summarize]({{"/r/data_transformation/group_by_and_summarize_data/Basic Summarization operation"|prepend:site.baseurl}})
- [rearrange columns]({{"/r/data_transformation/rearrange_columns/Basic rearrange column operation"|prepend:site.baseurl}})
- [rename columns]({{"/r/data_transformation/rename_columns/Basic rename column operation"|prepend:site.baseurl}})
- [select columns]({{"/r/data_transformation/select_columns/Basic Select Operation"|prepend:site.baseurl}})
- [sort rows]({{"/r/data_transformation/sort_rows/Basic Sorting Operation"|prepend:site.baseurl}})
- [append new column to existing dataframe]({{"/r/data_transformation/append_to_existing_data/Append new columns to existing dataframe"|prepend:site.baseurl}})
- [append new row to existing dataframe]({{"/r/data_transformation/append_to_existing_data/Append new rows to existing dataframe"|prepend:site.baseurl}})

We can combine these operations in a chain with the help of the Pipe operation **%>%**. The pipe operation has takes an input does the processing and gives an output.

**The pipe operation does not modify the current input, instead it returns a new dataframe which is a result of the chained operation performed.**

## Procedure

We will be working with a custom dataframe:

{% highlight r %} 
# package for creating dataframe
library(tibble) 

# tibble or dataframe 
df <- tibble(col1 = as.integer(c(1,2,3,4,5)), 
             col2 = c(11,12,13,14,15),
             )
View(df)
{% endhighlight %}

![custom](custom.png)

We will be applying the following operation on the dataframe:

1. add new column col3 with values 10, 20, 30, 40, 50, 60
2. rename the old column col1 to renamed_col1
3. filter to keep rows which have even values for renamed_col1
4. rearrange columns in dataframe to following order renamed_col1, col3, col2


### Code

{% highlight r %} 
# refer procedure for definition of df
library(dplyr)

result <- df %>% 
  # add new column col3
  mutate(col3 = c(10,20,30,40,50)) %>% 
  
  # rename old column col1 to renamed_col1
  rename(renamed_col1 = col1) %>% 
  
  # filter to keep rows which have even values for renamed_col1
  filter(renamed_col1 %% 2 == 0) %>% 
  
  # rearrange columns to order renamed_col1, col3, col2
  select(renamed_col1, col3, col2)

View(result)
{% endhighlight %}

The output of above code is:

![chain output](chain output.png)


## Conclusion

Thus we have successfully implemented basic chain operation using pipes.

## References
- https://r4ds.had.co.nz/