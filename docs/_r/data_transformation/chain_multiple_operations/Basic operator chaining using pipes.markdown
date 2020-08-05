---
layout: page
title: Basic operator chaining using pipes
menubar: r_menu
toc: true
---

# Basic operator chaining using pipes

-------------------------------------------------------------------

## Introduction	

We have already covered basic operations in tidyvers:

- filter rows
- mutate or add new columns using existing data
- group by and summarize
- rearrange columns
- rename columns
- select columns
- sort rows
- append new column to existing dataframe
- append new row to existing dataframe

We can combine these operations in a chain with the help of the Pipe operation **%>%**.

**The pipe operation does not modify the current input, instead it returns a new dataframe which is a result of the chained operation performed.**

## Procedure

We will be working with a custom dataframe:

![](.png)



### Code

{% highlight r %} 

{% endhighlight %}

The output of above code is:

![](.png)


## Conclusion

Thus we have successfully implemented basic chain operation using pipes.

## References
- https://r4ds.had.co.nz/