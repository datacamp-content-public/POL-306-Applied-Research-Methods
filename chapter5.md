---
title: T-Tests
description: ""
---

## T-Tests

```yaml
type: NormalExercise
key: ea755615df
xp: 100
```

t-tests in R use the function t.test(). They use formulas to identify what the interval variable is and what the variable is the indicates groups. You will be using formulas a lot later on when doing regressions. The important part of formulas is ~. This is called a tilde and is on the top left of your keyboard (near the number 1). 

A formula for a t.test will look something like: interval.variable~group.variable. 

t.test() expects the first argument to be a formula and you can include the dataframe as the second argument. If you include the dataframe as the second argument you don't have to worry about doing df$ for each variable. For example if you have a dataset, df with two variables X (your grouping variable) and Y (your interval variable) you can do a t.test like this: 

t.test(Y~X, df) 

You could also do it like this:

t.test(df$Y~df$X)

Both will give you the same results.   


t.test() can take a third argument called alternative that sets the alternative hypothesis. This can be "two.sided" (the default), "greater", or "less". There are also several other arguments for t.test() and if you want you can check them by calling ?t.test

`@instructions`
We are going to keep using the protest dataset. You will do a t.test on if the people that protested the DNC are younger than protesters at the RNC. I want you to call t.test() three times once with each different alternative choice. Look at how the p-value and the confidence intervals change.

`@hint`


`@pre_exercise_code`
```{r}
tmp.df <- read.csv("http://assets.datacamp.com/production/repositories/3406/datasets/41ae7a219de8ed396ebf3d49e6561a03fe27541a/protest_survey.csv")

write.csv(tmp.df, "Protest_Survey.csv", row.names=F)
rm(list=ls())

```

`@sample_code`
```{r}
df <- read.csv("Protest_Survey.csv")
names(df) 


```

`@solution`
```{r}
df <- read.csv("Protest_Survey.csv")
names(df) 

t.test(age~convention, data=df, alternative="greater")
t.test(age~convention, data=df, alternative="two.sided")
t.test(age~convention, data=df, alternative="less")
```

`@sct`
```{r}
ex() %>% {
  check_function(., "t.test" ) %>% check_arg("alternative")
}
```
