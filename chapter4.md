---
title: 'Tables and Standard Deviaiton'
description: ""
---

## Standard Deviation

```yaml
type: NormalExercise
key: 19ff3997c3
xp: 100
```

Finally, you can use sd() to find the standard deviation of a vector.

`@instructions`
Along with the percentage of Democrats/Republicans in a state the data has the percentage of state legislators that are Democratic and Republican. 

For this last assignment find the mean, the standard deviation and plot the histogram of either the percentage of Democrats or Republicans in a state legislature. 

To find out what the variable is called use names(). Also note, Nebraska (which is in the data) has a non-partisan legislature so it does not have a value for Republicans and Democrats. You will need to tell R to ignore this when you calculate the mean and standard deviation.

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

mean(df$hs_dem_prop_all, na.rm=T)
sd(df$hs_dem_prop_all, na.rm=T)
hist(df$hs_dem_prop_all)


```


`@sct`

```{r}
ex() %>% {
  check_function("mean") %>% check_arg("na.rm") %>% check_equal()
  check_function("sd") %>% check_arg("na.rm") %>% check_equal()
  check_function("hist") 

}
```
