---
title: "Wrangling with dplyr"
author: ""
params:
  day: 5
  ptitle: true
  pbackground: true
  dtype: "none"
---



# Becoming the Critic. {data-background=#e8d725}



## {data-background-iframe="http://www.perceptualedge.com/example4.php"}

[Visualization of the Day](http://www.perceptualedge.com/example4.php)


## My Attempt at a graphic

![](day_5_palmer_files/figure-revealjs/fewfix-1.png)

## Review Team Lead Responsibilities


## Present Case Studies

- Put a link to the .md file in an issue specific to that Case Study on your repository
  -   This signifies that you believe it is "complete" and ready for review
- Reviewers will go to your repository and click the link in the issues during the review
  -   Do NOT simply share your screen
- Each person should review 2 other Case Studies. 
  -   Leave comments on the issue. Coordinate during the group meeting who will be reviewing who (probably won't have time to review them all)
  -   You should respond to the issues left on yours: either fix it or explain why you didn't
  _   Then, close the issue
  
## Tracking Task Completion

- Put a link to the .md file in an issue for that task
  -   This signifies that you believe it is "complete" and ready for review
  -   Myself or TA's will either "close" the issue - meaning it is complete -  or leave feedback about what remains incomplete

## Special Request

Please indicate the number of hours it took you to complete the Task or Case Study in the issue where you post the link (or in the readme.md file?)

Don't forget to push all past homeworks to github

# Being Readings {data-background=#e8d725}



<!-- ## How does data change belief? -->

<!-- ## To understand God's thoughts we must study statistics, for these are the measure of His purpose. -->

<!-- -Florence Nightingale ([Coxcomb graph](https://en.wikiquote.org/wiki/Florence_Nightingale#/media/File:Nightingale-mortality.jpg)) -->

<!-- <small> -->
<!-- Her most famous graph, displayed at the top of this article, shows the number of soldier deaths per month from various causes. Each pie slice represents a different month, from April 1854 through March 1856, and each color stands for a different cause of death. It takes just a quick glance to achieve the two main takeaways: that disease, colored blue, killed far more soldiers than either "wounds" (red) or "other" (black), and that it was reduced greatly in 1855. -->
<!-- </small> -->

<!-- ## What changed Britian's mind? -->

<!-- After she completed her report, Nightingale worked hard to turn its conclusions into common knowledge, privately distributing it to influential people and writing several more reports, many of which included coxcombs. When she received push back from Army doctors, who thought sanitary measures a waste of money, she even leaked some of her charts to the press. -->

<!-- ## Hans -->

<!-- **It is only by measuring that we can cross the river of myths.** -->

<!-- > - [Hans Rosling](https://youtu.be/OwII-dwh-bk) -->
<!-- <!-- Don't watch this one, just ask: what does this mean? -->

# Checking-in / getting help {data-background=#e8d725}

## Virtual Questions and Support

Build skills and experience from classes. Don't just take classes!

* How is slack working?

* Stack Overflow for general coding questions

* Github working correctly?


## Getting the Routine Down

- **You should push at least three times a week**
- Being Readings in Perusall/Ilearn
- Writing issues in Github will take place on Tuesday
    - You should address and close the issues within a week so you don't fall behind (the sooner the better)


# Data Wrangling with dplyr {data-background=#e8d725}

## Data Manipulation Verbs

> - `filter`  - 
> - `sort` - 
> - `select`  - 
> - `mutate`  - 

## Data Manipulation Verbs

> - `filter`  - filter your data to a smaller set of important rows.
> - `sort` - Organize the row order of my data
> - `select`  - select specific columns to keep or remove 
> - `mutate`  - add new mutated (changed) variables as columns to my data.

## Data Manipulation Verbs for Summaries

> - `summarise` - 
> - `group by`  - 

## Data Manipulation Verbs for Summaries

> - `summarise` - build summaries of the columns specified
> - `group by`  - divide your data into groups. Often used with `summarise`

## Class Activity #1: Data verbs

![](../images/data_verbs_activity1_start.PNG)

![](../images/data_verbs_activity1_end.PNG)

## Class Activity #2: Data verbs
<!--Changing size of the end table image so it fits easily on the slide-->

![](../images/data_verbs_activity2_start.PNG){width=55%}
![](../images/data_verbs_activity2_end.PNG){width=33%}


## Practice reading code

With your group, write this code out in an English paragraph.


```r
delays <- flights %>% 
  group_by(dest) %>% 
  summarise(
    count = n(),
    dist = mean(distance, na.rm = TRUE),
    delay = mean(arr_delay, na.rm = TRUE)
  ) %>% 
  filter(count > 20, dest != "HNL")
```

## Practice writing code using dplyr package

Use `filter()`, `arrange()`, `select()`, `mutate()`, `group_by()`, and `summarise()`. With `library(tidyverse)` tackle the following challenges.

Take turns in the driver's seat.

> 1. Arrange the `iris` data by `Sepal.Length` and display the first six rows.
> 2. Select the `Species` and `Petal.Width` columns and put them into a new data set called `testdat`.
> 3. Create a new table that has the mean and standard deviation for petal width for each Species.
> 4. Read about the `?summarise_all()` function and get a new table with the means and standard deviations for all the variables for each Species.
> 5. Look at the examples in the `summarise_all()` help file and see if you can find other use cases for the `summarise_` or `mutate_` functions.



# Additional functions I often use in mutate {data-background=#e8d725}

## Changing the type of variable

Discuss with your table, what does this code do?
```
?mtcars
as.factor(mtcars$am)
```

## Changing the type of variable (2)

Use this code to create the `money` object

```
money <- c('4,554,25', '$45', '8025.33cents', '288f45')
```

* Apply `as.numeric(money)` and talk with your table about the output.
* Apply `parse_number(money)` and compare the results.

## Scan the dplyr cheatsheet

https://github.com/rstudio/cheatsheets/blob/master/data-transformation.pdf

Learn about the following functions using the cheat sheet and `?`.  Try to create a working example

- lag()
- distinct() and n_distinct()
- min_rank()
- pull()



# The Grammar of Graphics {data-background=#e8d725}

## Class Activity, 30 minutes

Run this code to open a fill-in-the-blank file to be completed with your team
<!-- In the future, rewrite the class activity to use the nyc flights data instead of iris. The whole idea of zooming becomes more relevant and it preps them well for next lesson -->


```r
#install.packages("downloader")
downloader::download("https://byuistats.github.io/M335/presentations_class_palmer/day_5_files/day_5_class_practice.R", destfil = "script5.R", mode="wb")
file.edit('script5.R')
```

This is also available in I-learn, this week's module

## Zooming in on the data

- filter the dataset prior to graphing
- scale_*_continuous(limits = c(min, max))
- coord_cartesian()

- coord_cartesian adjusting the window but keeps all data when calculating stats (like a regression line)

## coord_flip()

Especially helpful for making vertically oriented barplots or boxplots horizontal




<!-- ## Putting the legend on the inside -->

<!-- > * `library(directlabels)` -->
<!-- >    * http://directlabels.r-forge.r-project.org/examples.html -->
<!-- >    * `geom_dl()` and `direct.label()` -->

<!-- > Complete the following  -->

<!-- >    1) **Color the points of `fl_sc` by `origin` using the brewer scale** -->
<!-- >    2) **and use the directlabel package to move the labels into the plotting region.** -->




<!-- ## Labelling Elements inside the graphic -->

<!-- `library(directlabels)` can be helpful. The `library(ggrepel)` package is a must for our work.  -->
<!-- Here is the [book's graphic](http://r4ds.had.co.nz/communicate-plots_files/figure-html/unnamed-chunk-9-1.png).  -->

<!-- - What are some concerns you have with this graphic? -->

<!-- - Start with the [code from 28.3](http://r4ds.had.co.nz/graphics-for-communication.html) and update / tweak it to match mine on the next slide. -->

<!-- ## My Code Solution -->



## ggplot2 Cheat sheets

# Data Ingestion (Task 5) {data-background=#e8d725}


## Data formats

R can read in data from any format. The following packages will provide most of the functionality we need.

- `library(readr)` (loaded with tidyverse)
- `library(readxls)`
- `library(haven)`

## Data Import (task 5)

* What are the key differences between `read.csv()` from base R and `read_csv()` from readr in the tidyverse?

* read_csv is much faster
* read_csv doesn't convert strings to factor
* read_csv doesn't use row names or munge column names
* [Good Image](https://csgillespie.github.io/efficientR/_main_files/figure-html/readr-vs-base-1.png)

## `parse_` commands

Use this code 

```
money <- c('4,554,25', '$45', '8025.33cents', '288f45')
```

* Apply `as.numeric(money)` and talk with your table about the output.
* Apply `parse_number(money)` and compare the results.

## Using `read_csv()` with parsers

> 1. Run this line of code below
> 2. Look at the errors (`problems(challenge)`), the `head()`, and `tail()` of your `challenge` object.  What formats should they be?
> 3. Now review [11.4.2 of our textbook](http://r4ds.had.co.nz/data-import.html#problems) and `?read_csv()` to fix the read in.


```r
challenge <- read_csv(readr_example("challenge.csv"))
problems(challenge)
```


## Scripts (used in Task 6)

.rmd files are for reports that also include Rcode. It is reproducible and easily updated

script files (.R) are simply code and comments. 

You should be familiar with both.

Bonus: So what's an .md file?


# Work on Task 5 and Case Study 3