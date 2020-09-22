---
title: ""
author: ""
params:
  day: 2
  ptitle: true
  pbackground: true
  dtype: "none"
---



# Welcome to class! {data-background=#f7d754}

## Housekeeping

- You do not need to submit anything for task 2
- Are you in slack?
- Data Science Society
- Did you share your github name?
- Sign up for a one-on-one
- Sign up for presentations next week

# tidyverse {data-background=#f7d754}

## What is a package?

"In R, the fundamental unit of shareable code is the package. A package bundles together code, data, documentation, and tests, and is easy to share with others. As of June 2019, there were over 14,000 packages available on the Comprehensive R Archive Network, or CRAN, the public clearing house for R packages. This huge variety of packages is one of the reasons that R is so successful: **the chances are that someone has already solved a problem that you're working on**, and you can benefit from their work by downloading their package." 

[*source*](https://r-pkgs.org/intro.html)

## [tidyverse](https://www.tidyverse.org/)

This is a group of packages that are designed to work together all using a "tidy" framework (we'll learn about later). Loading the tidyverse loads all the packages at once.

It also loads many datasets. Find a dataset you are interested in: data()

## Viewing data

Compare these methods for your chosen dataset

> - simpling typing the dataset's name
> - head()
> - str()
> - glimpse() (only available in tidyverse)
> - View()

## The pipe `%>%`

You can read it as a series of imperative statements: group, then summarize, then filter. A good way to pronounce %>% when reading code is **"then"**.

* Behind the scenes, x %>% f(y) turns into f(x, y), and x %>% f(y) %>% g(z) turns into g(f(x, y), z) and so on. 
* You can use the pipe to rewrite multiple operations in a way that you can read left-to-right, top-to-bottom. 
* We'll use piping frequently from now on because it considerably improves the readability of code.

**Simple example: pipe your chosen dataset into one of the functions on the previous slide**

# Working in R {data-background=#f7d754}

## Shortcuts

- Make sure you note what `Alt + Shift + K` does?
<!-- I like ctrl + shift + c, to comment blocks of code and add comments in an Rmd file -->
<!-- I also like the command/control enter to run a line of code -->
- Your favorite shortcut keys?
- Edit the options in Tools

## The skill of debugging

## Newbie Coding Mistakes

> - [Which common mistake are you most guilty of?](https://jscomplete.com/learn/pro-programmer/beginner-programmers-mistakes)
> - [Common R Errors](https://www.r-bloggers.com/common-r-programming-errors-faced-by-beginners/)

## Interpret these error statements

Take some time at your table to work out what the error statement is saying about your code. Fix the error and get the code to run.


```r
ggplot(dota = mpg) + 
+   geom_point(mapping = aes(x = displ, y = hwy))
#> Error in structure(list(data = data, layers = list(), 
#> scales = scales_list(),  : 
#>  argument "data" is missing, with no default
```


```r
fliter(mpg, cyl = 8)
#> Error in fliter(mpg, cyl = 8) : could not find function "fliter"
```


```r
filter(diamond, carat > 3)
#> Error in filter(diamond, carat > 3) : object 'diamond' not found
```


```r
data.frame(1:10,10:1,)
#> Error in data.frame(1:10, 10:1, ) : argument is missing, with no default
```

## Learning and Debugging in the wild

> - Treating class like a team meeting
> - The expense of training and experts in the real world

![](http://i0.kym-cdn.com/photos/images/newsfeed/001/297/214/908.jpg)

## Remember:

"There are two ways to write error-free programs; only the third one works." *Alan Perlis*

![](images/frizzle.png)


# Let's Practice! {data-background=#f7d754}

## Idaho and COVID-19

- [Exploring the data](https://covidtracking.com/data/state/idaho) (.R)
- [Communicating results](https://rmarkdown.rstudio.com/lesson-2.html) (.Rmd, .md, .html)
- YAML headers and R chunks
- [Rmarkdown template](https://byuistats.github.io/M335/rpages.html#rmd_template)
- [Projects in R](https://r4ds.had.co.nz/workflow-projects.html)

## Looking ahead

- For Case Study 1, upload the **md** file to **our class** slack channel