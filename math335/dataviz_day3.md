---
title: ""
author: ""
params:
  day: 2
  ptitle: true
  pbackground: true
  dtype: "none"
---



# Visualizations for Presentation: Day 3 {data-background=#e8c35d}

Welcome to class!

## Reading Discussion

<!-----------------------------------

## [The Two Questions](https://hbr.org/2016/06/visualizations-that-really-work)

>- Is the information conceptual or data-driven?
>- Am I declaring something or exploring something?

## This class is data-driven.

>- "Exploring" = trying to figure something out = EDA
>- "Delcaring" = communicating information = visualizations for presentations

![](images/dataviz/R1606H_BERINATO_B.png)

## Everyday Dataviz

>- Simple, simple, simple
>- Communicate a single message
>- Generate discussion about the ideas in the chart, not the chart itself

## Sister Larson's Favorite Quotes

> "A poorly designed chart will waste that time by provoking questions that require the presenter to interpret information that's meant to be obvious. If an everyday dataviz can't speak for itself, it has failed-just like a joke whose punch line has to be explained."

## Sister Larson's Favorite Quotes

> "Busy charts communicate the idea that you've been just that-busy."

## Sister Larson's Favorite Quotes

> "What we actually do when we make a good chart is get at some truth and move people to feel it-to see what couldn't be seen before. To change minds. To cause action."

--------------------------------------------->

## Next Week

- Class on Tuesday, Wednesday, and Friday
- Task 13: Find data for your semester project
- No Task 14
- Coding challenge on Friday
- Case study due Saturday



# Case Study: Gun Deaths {data-background=#e8c35d}

##  Case Study

> - What is the end goal?
> - What is a "seasonal trend"?
> - What types of variables do we have?
> - What do we expect to see?

## A few helpful things

>- I think you will use a lot of `group_by()` and `summarise()`
>- Use `mutate()` and `case_when()` to create new variables/groups
>- `lubridate::days_in_month(1:12)` could be interesting/fun


<!-----------------
## What is a "seasonal trend"?

## What is a "target audience"?

## What is "pseudo code"?

[A silly example.](https://www.khanacademy.org/computing/computer-programming/programming/good-practices/pt/planning-with-pseudo-code)

## **Reducing Gun Deaths**

I've given you the instructions in English. 

You'll end with a report full of code and images

>- Pseudo code is a bridge between the start and the end
>- Pseudo code helps with the "structured thinking" we read about last week
>- Pseudo code is the recipe for our lasagna (ingredients/layers)

## **Reducing Gun Deaths**

Read over the case study. 

Then, in slack, write pseudo code for the entire project.

## A few helpful things

>- I think you will use a lot of `group_by()` and `summarise()`
>- Use `mutate()` and `case_when()` to create new variables/groups
>- `lubridate::days_in_month(1:12)` could be interesting/fun

## What does this code do?

```
data %>% 
  select_if(is.numeric) %>% 
  pivot_longer(cols = everything()) %>% 
  ggplot() +
  geom_histogram(aes(value)) +
  facet_wrap(~name, scales = "free")
```

## Free Time
------------------------>
