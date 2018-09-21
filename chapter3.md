---
title: 'Central Tendency'
description: ""
---

## Mean and Median

```yaml
type: NormalExercise
key: e987f3fbf1
xp: 100
```

R has functions that can easily compute the mean and median of a vector. The function for the mean is mean() and the function for median is median().

`@instructions`
For this assignment you will have to load the dataset "state_party.csv" again and then calculate the mean and median of the percentage of democrats in a state (the variables are called democrat and republican).

Remember to load data you need to call read.csv save the output: df <- read.csv("state_party.csv") and then you can access the variables in the dataset using the $.

`@hint`


`@pre_exercise_code`

```{r}
tmp.df <- read.csv("https://assets.datacamp.com/production/repositories/3406/datasets/f4fba345dc08afca82b97fc821143163783daaa8/state_party.csv")

write.csv(tmp.df, "state_party.csv", row.names=F)
rm(list=ls())
```


`@sample_code`

```{r}

```


`@solution`

```{r}
df <- read.csv("state_party.csv")

mean(df$democrat)
median(df$democrat)


mean(df$republican)
median(df$republican)
```


`@sct`

```{r}
ex() %>% {
  check_function(., "mean") 
  check_function(., "median") 
  check_output_expr(., "mean(df$democrat)")
  check_output_expr(., "median(df$democrat)")
  check_output_expr(., "mean(df$republican)")
  check_output_expr(., "median(df$republican)")

}
```


---

## Histogram

```yaml
type: NormalExercise
key: cbdcac27ae
xp: 100
```

Now we will briefly explore histograms in R. 

Histograms are done by using the function hist(). Like most of our functions it expects that the first thing it encounters will be the variable you want a histogram of. It also has a lot of other attributes:

- xlab = "something" *changes the x axis label*
- ylab = "something" *changes the y axis label*
- main = "something" *changes the the main label*
- break = ... *this argument can take a lot of options, most common though is the number of boxes you want. To make your histogram have 5 boxes you set break=5*

`@instructions`
Make a histogram of either democrat or republican and change the xaxis and the main title.

`@hint`


`@pre_exercise_code`

```{r}
tmp.df <- read.csv("https://assets.datacamp.com/production/repositories/3406/datasets/f4fba345dc08afca82b97fc821143163783daaa8/state_party.csv")

write.csv(tmp.df, "state_party.csv", row.names=F)
rm(list=ls())
```


`@sample_code`

```{r}
df <- read.csv("state_party.csv")

```


`@solution`

```{r}
df <- read.csv("state_party.csv")


hist(df$republican, xlab="Percentage of Democrats", main="Histogram of Democrats in a State") 

```


`@sct`

```{r}
ex() %>% check_function("hist") %>% {
  check_arg(., "xlab")
  check_arg(., "main")
}
```
