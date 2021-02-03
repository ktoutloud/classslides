---
title: ""
params:
  ptitle: true
  pbackground: true
  dtype: "none"
---

# Welcome to class! {data-background=#e8c35d}

Tidy Data: Day 2

## Task 9

<br>

Anyone want to share your table and/or chart?

## tidyr Functions: Character vectors

<br>

- `separate()` separates a character column into multiple columns with a regular expression or numeric locations
- `extract()` extracts a character column into multiple columns using regular expression groups
- `unite()` unites multiple columns into one by pasting strings together

## Data frame vs Tibble

<br>

What are the [main differences](https://r4ds.had.co.nz/tibbles.html#tibbles)?

Compare the output:

```r
library(tidyverse)

iris
as_tibble(iris)
```

## Attributes

<br>

Attributes are used to store [metadata](https://www.google.com/search?q=metadata&rlz=1C1GCEJ_enUS882US882&oq=metadata&aqs=chrome.0.0i67i131i433j0i67l4j69i60l3.694j0j7&sourceid=chrome&ie=UTF-8) about an object.

```r
attributes(iris)

comment(iris) <- "This is my favorite data."
attributes(iris)

attr(iris, "my_attribute") <- 42
attributes(iris)
```
## readr package

<br>

The [readr package](https://readr.tidyverse.org/) provides "a fast and friendly way to read rectangular data."

How is `read.csv()` different from `read_csv()`? And [why do we care](https://r4ds.had.co.nz/data-import.html#compared-to-base-r)?

## Sign up to lead

<br>

In Slack: Who wants to be a lead for this Friday's reading discussion?

4 online, 3 face-to-face

## Task 10!







<!-----------
## regular expressions

A **regular expression** is a sequence of characters that define a search pattern.

Usually such patterns are used by string-searching algorithms for "find" or "find and replace" operations on strings, or for input validation.

[regex101.com](https://regex101.com/)
------------->