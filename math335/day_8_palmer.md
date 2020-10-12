---
title: "Exploratory Data Analysis"
author: ""
params:
  day: 9
  ptitle: true
  pbackground: true
  dtype: "none"
---


## Great Quotes

> 'There are no routine statistical questions, only questionable statistical routines.' 

— Sir David Cox

> 'Far better an approximate answer to the right question, which is often vague, than an exact answer to the wrong question, which can always be made precise.'

— John Tukey

## Github issues

> - Plots not rendering
>   - Not uploading everything to Github
>   - Changing .Rmd to .md
> - Issues, issues issues
> - In your group meeting:
>   - Each person pull it up on their own screen
>   - Write issues, don't just talk
>   - Everyone has time to present (3-4 per group)
> - Think workplace dynamics


## Socrative Hours Quiz

Mean hours per week outside of class for last 2 weeks?
[socrative.com](https://socrative.com)
Room#: PALMER4992



<!-- # Being Readings {data-background=#e8d725} -->

<!-- ## Structured Thinking  -->

<!-- > Structured thinking is a process of putting a framework to an unstructured problem. Having a structure not only helps an analyst understand the problem at a macro level, it also helps by identifying areas which require deeper understanding. -->

<!-- ## Structured Thinking (2) -->

<!-- ![](../images/time-required-project-completion.jpg) -->

<!-- **How can these articles help you perform better in this class and your future work?** -->


<!-- ## Hadley on Tidy Data -->

<!-- **Comments from the Tidy paper?** -->

<!-- ## "Happy families are all alike; every unhappy family is unhappy in its own way."  -->

<!-- **-- Leo Tolstoy** -->

<!-- ## "Tidy datasets are all alike, but every messy dataset is messy in its own way."  -->

<!-- **-- Hadley Wickham** -->

<!-- ## "There is one glory of the sun, and another glory of the moon, and another glory of the stars: for one star differeth from another star in glory." -->

<!-- **-- Paul (1 Corinthians 15:41)** -->

<!-- ## Really. How bad can it get? -->

<!-- > * [R for Data Science Case Study](http://r4ds.had.co.nz/tidy-data.html#case-study) -->
<!-- > * [Wrangling Cheat Sheet](https://www.rstudio.com/wp-content/uploads/2015/02/data-wrangling-cheatsheet.pdf) -->
<!-- > * [From a data request](../data/messy_data.xlsx):  -->
<!-- <!-- What is EDA? {data-background=#e8d725} --> -->

<!-- ## Socrative Quiz -->

<!-- > - [Socrative: Exploratory Analysis](https://socrative.com/) -->

# Exploratory Data Analysis

## Exploratory Data Analysis

EDA is fundamentally a creative process. And like most creative processes, the key to asking quality questions is to generate a large quantity of questions.
 
> - What type of variation occurs within my variables?

> - What type of covariation occurs between my variables?

## Understanding `case_when()`


> - case_when() is particularly useful inside mutate when you want to create a new variable that relies on a complex combination of existing variables. **Write a short sentence that says what this code is doing?**



```r
starwars %>%
  select(name:mass, gender, species) %>%
  mutate(
    type = case_when(
      height > 200 | mass > 200 ~ "large",
      species == "Droid"        ~ "robot",
      TRUE                      ~  "other"
    )
  )

#> # A tibble: 87 x 6
#>                  name height  mass gender species  type
#>                 <chr>  <int> <dbl>  <chr>   <chr> <chr>
#>  1     Luke Skywalker    172    77   male   Human other
#>  2              C-3PO    167    75   <NA>   Droid robot
#>  3              R2-D2     96    32   <NA>   Droid robot
#>  4        Darth Vader    202   136   male   Human large
```


# Pause to Look Ahead

## Task 8

- Read over Task 8.
- Read over the variables (this requires you to read in the data and even start exploring it a bit)
- Decide on what relationship/variables you would like to investigate
- Make a quick sketch of what you want your end plot to look like.

## Case Study: Gun Deaths

Any Questions



# Old Faithful

## Exploring Old Faithful goals

> 1. **Make the [histogram shown in the book](http://r4ds.had.co.nz/EDA_files/figure-html/unnamed-chunk-9-1.png) with the black and white theme and an improved x-axis label.**

## Exploring Old Faithful (1)


```r
faithful %>%
  ggplot(aes(x = eruptions)) + 
    geom_histogram(color = "white") +
    theme_bw() +
    labs(x = "Duration of eruption (minutes)", 
         y = "Number of Observations")
```

![](day_8_palmer_files/figure-revealjs/example2-1.png)



## Exploring Old Faithful goals (2)

> 1. Make the [histogram shown in the book](http://r4ds.had.co.nz/EDA_files/figure-html/unnamed-chunk-9-1.png) with the black and white theme and an improved x-axis label.
> 2. **Use the mutate function to modify our plot to fill the histogram for two groups of waiting times.**


```r
mutate(waiting_group = case_when(waiting < 67 ~ " < 67 min",
                                   waiting >= 67 ~ " > 67 min"))
```

## Exploring Old Faithful (3)



```r
faithful %>%
  mutate(waiting_group = case_when(waiting < 67 ~ " < 67 min",
                                   waiting >= 67 ~ " > 67 min")) %>%
  ggplot(aes(x = eruptions, fill = waiting_group)) + 
    geom_histogram(color = "white") +
    scale_fill_brewer(type = "qual") +
    theme_bw() + theme(legend.position = "bottom") +
    labs(x = "Duration of eruption (minutes)", 
         fill = "Duration\nof Wait", y = "Number of Observations")
```

![](day_8_palmer_files/figure-revealjs/thestuf33-1.png)

## Exploring Old Faithful goals (4)

> 1. Make the [histogram shown in the book](http://r4ds.had.co.nz/EDA_files/figure-html/unnamed-chunk-9-1.png) with the black and white theme and an improved x-axis label.
> 2. Use the mutate function to modify our plot to fill the histogram for two groups of waiting times.
> 3. **Use the waiting variable to make a hexbin plot of the relationship between waiting time and duration.**


## Exploring Old Faithful (5)


```r
faithful %>%
ggplot(aes(x = eruptions, y = waiting)) + 
  geom_hex() + theme_bw() +
  labs(x = "Duration of eruption (minutes)", 
       y = "Time between eruptions (minutes)", 
       fill = "Number of\nObservations")
```

![](day_8_palmer_files/figure-revealjs/realldkdjf-1.png)





