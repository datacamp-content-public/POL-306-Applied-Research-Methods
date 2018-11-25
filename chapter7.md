---
title: Regression
description: ""
---

## Linear Regression

```yaml
type: NormalExercise
key: 4293374fdf
xp: 100
```

The most important function you will use for estimating linear regression models is `lm()'. This will expect a formula and will output something called a model object that you will want to save so you can then manipulate it. 

For example, if you have a dataframe called `data.frame` and three variables named: `var1`, `var2`, and `var3`. If you want to estimate a linear regression with `var1` as the dependent variable and the other two as independent variables you would write:

```
mod <- lm(var1 ~ var2 + var3, data=data.frame)
```

This won't output anything but you can look at the results using `summary()` like this:

`summary(mod)`

`@instructions`
We will start by just estimating a linear regression of the number of protests someone attended (the DV) as a function of the persons age and which convention they were at. The variables are all in the `df` dataset and are: `marches`, `age`, and `convention`. 

You should save the linear model as `mod` (like in the example above) and then output the results using the `summary()` function.

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

mod <- lm(marches~age + convention, data=df)
summary(mod)
```

`@sct`
```{r}
ex() %>% {
  check_function(., "mod" ) %>%
    check_arg("formula") %>% check_equal()
  check_function(., "summary") %>% check_arg("object") %>% check_equal()

}
```
