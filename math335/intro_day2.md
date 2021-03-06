---
title: ""
params:
  day: 3
  ptitle: true
  pbackground: true
  dtype: "none"
---

# Welcome to class! {data-background=#e8c35d}

## Any questions?

## Are we all on Slack?

# Programming in R {data-background=#e8c35d}

## [Data Types](https://www.geeksforgeeks.org/r-data-types/)

- Each variable in R has an associated data type
- Each data type requires different amounts of memory
- Each data type has some specific operations which can be performed over it

<br>

- There are four primary types of data:
  - **Double:** Set of all real numbers (might also called "numeric")
  - **Integer:** Set of all integers
  - **Logical:** TRUE and FALSE
  - **Character:** "a", "BYU-Idaho", "@", "3", etc. (also called "string")

## [Vectors](http://adv-r.had.co.nz/Data-structures.html)

- The basic data structure in R is the vector. 
- Vectors come in two flavors: **atomic vectors** and **lists**.

<br>

- Atomic vectors and lists have three common properties:
  - **Type:** typeof(), what it is.
  - **Length:** length(), how many elements it contains.
  - **Attributes:** attributes(), additional arbitrary metadata.

<br>

- They differ in the types of their elements: 
  - All elements of an atomic vector **must be the same type**.
  - The elements of a list can have **different types!**

## [Creating a Vector or a List](https://adv-r.hadley.nz/vectors-chap.html)

- Atomic vectors (or just "vectors") are created using the combine function `c()`
- Lists are created using using the funcion `list()`

<br>

- If you try to create a list using `c()`, the values will be coerced, in this order: 
  - character -> double -> integer -> logical.
- Mathematical functions will coerce to numeric. This is very handy for logical vectors! `TRUE` becomes 1 and `FALSE` becomes 0.

## [Data Frames](https://adv-r.hadley.nz/vectors-chap.html#lists)

"If you do data analysis in R, you're going to be using data frames. A data frame is a named list of vectors with attributes for column names, row.names, and its class 'data.frame'."

"In contrast to a regular list, a data frame has an additional constraint: the length of each of its vectors must be the same."

<br>

```
iris

attributes(iris)
```

## [Special Data Types and Structures](https://r4ds.had.co.nz/vectors.html?q=factor#factors-1)

"Factors are designed to represent categorical data that can take a fixed set of possible values. Factors are built on top of integers, and have a levels attribute."


```
x <- factor(c("brown","blue","blue","brown","blue"))
x
attributes(x)
as.integer(x)
```

<br>

Later in the semester we'll learn about tibbles, dates, date-times, and spatial data.
