---
layout: page
title: Missing Values or NAs
menubar: r_menu
toc: true
---

# Missing Values or NAs

-----------------------------------------------------------------------------------------

## Introduction

Missing Values or NAs (Not Available) represent missing or unknown values in data set. These NAs need to be handled if not then they cause ambiguity while performing any operation. 

**Any operation involving an unknown value will also be unknown.**


## Explanation

- If we perform addition with NA, the output will also be NA.

![NA addition](NA addition.png)

- If we perform equality check with NA, the output will also be NA. Since if are comparing a number to unknown the output is unknown.

![NA compare1](NA compare1.png)

- If we compare NA to NA the output is NA itself! This is because when we are comparing 2 unknown numbers, it is unknown whether they are equal or not.

![NA compare2](NA compare2.png)


- We can check whether a variable contains NA or not using the **is.na()** function.

![is.na](is.na.png)


## Conclusion

Thus we have explored missing values or NA's in R and how to identify them.

## References

- https://r4ds.had.co.nz/