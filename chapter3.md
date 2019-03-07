---
title: 'Plots and Distributions'
description: ""
---

## Histogram

```yaml
type: NormalExercise
key: cbdcac27ae
xp: 100
```

First we will briefly explore histograms in R. 

Histograms are done by using the function `hist()`. Like most of our functions it expects that the first thing it encounters will be the variable you want a histogram of. It also has a lot of other attributes:

- `xlab = "something"` *changes the x axis label*
- `ylab = "something"` *changes the y axis label*
- `main = "something"` *changes the the main label*
- `break = ...` *this argument can take a lot of options, most common though is the number of boxes you want. To make your histogram have 5 boxes you set break=5*

`@instructions`
Make a histogram of either `democrat` or `republican` and change the xaxis and the main title.

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

---

## Density Plots

```yaml
type: NormalExercise
key: 1b22036269
xp: 100
```

Now we will explore density plots in R. 

Density plots require using two functions at once `density()` and `plot()`. You can nest them so that they happen at the same time like: `plot(density(x))` where x is what you want to plot the the density of. You can change attributes of the plot using the same attributes from the `hist()` function as long as they are outside the first set of parentheses: `plot(density(x), xlab="X Label")`. 

You can see how different weighting schemes impact the density plot by setting `adjust=` to something. The default would be: `plot(density(x, adjust=1))`.

`@instructions`
Make a density plot of either `democrat` or `republican` and change the `adjust` argument to something other than 1.

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


plot(density(df$republican, adjust=.5))
```

`@sct`
```{r}
ex() %>% check_function("density") %>% {
  check_arg(., "adjust")
 }
```

---

## Standard Deviation

```yaml
type: NormalExercise
key: ed9703cc7f
xp: 100
```

Next, you can use `sd()` to find the standard deviation of a vector.

Along with the percentage of Democrats/Republicans in a state the data has the percentage of state legislators that are Democratic and Republican. These variables are called `hs_dem_prop_all` and `hs_rep_prop_all`

`@instructions`
For this assignment using the proportion of Democrats: 
1. Find the mean.
2. Find the standard deviation.
3. Plot the histogram. 

Also note, Nebraska (which is in the data) has a non-partisan legislature so it does not have a value for Republicans and Democrats. You will need to tell R to ignore this when you calculate the mean and standard deviation.

`@hint`
Remember to ignore missing observations use `na.rm=T`

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

mean(df$hs_dem_prop_all, na.rm=T)
sd(df$hs_dem_prop_all, na.rm=T)
hist(df$hs_dem_prop_all)


```

`@sct`
```{r}
ex() %>% {
  check_function(., "mean") %>% check_arg("na.rm") %>% check_equal()
  check_function(., "sd") %>% check_arg("na.rm") %>% check_equal()
  check_function(., "hist") 
  check_output_expr(., "sd(df$hs_dem_prop_all, na.rm=T)")
  check_output_expr(., "mean(df$hs_dem_prop_all, na.rm=T)")


}
```

---

## Frequency Tables

```yaml
type: NormalExercise
key: bffca44ed6
xp: 100
```

Up until now we've been focusing on interval variables, but many of you are using nominal or ordinal variables. 

Creating frequency tables and crosstabs is really simple in R. All you have to use is the `table()` function. The tables function expects either 1 or 2 vectors. If you do `table(x)` then it will show the frequency of all the values that `x` takes on. If you do `table(x, y)` then it creates a frequency crosstab between `x` and `y`.

`@instructions`
I've loaded a new dataset for you all in this assignment. There is now a csv called "ANES_Lim.csv" that comes from the survey data some of you are using. It includes three variables: gender, employment status, and how interested they are in the news. You can use `names()` to see what the different variables are in the dataset.  

For this assignment you just need to load the data and create a frequency table and a crosstab. You can use whatever variables you want.

`@hint`


`@pre_exercise_code`
```{r}
tmp.df <- read.csv("https://assets.datacamp.com/production/repositories/3406/datasets/5a4effcd07538b8b70830dd27e57ed8d97e39c22/ANES_Lim.csv")

write.csv(tmp.df, "ANES_Lim.csv", row.names=F)
rm(list=ls())
```

`@sample_code`
```{r}

```

`@solution`
```{r}
df <- read.csv("ANES_Lim.csv")

table(df$gender)

table(df$gender, df$newsint)

```

`@sct`
```{r}
ex() %>% check_function("table")  

```

---

## Proportions

```yaml
type: NormalExercise
key: 165fbe52f5
xp: 100
```

The `table()` function only creates frequency tables and does not show proportions. To calculate that we need to run another function: `prop.table()`

The easiest way to do this is to nest functions. We do this by putting another function around our first function so instead of `table(x)` we would do `prop.table(table(x))`. This calculates a frequency table for `x`, then returns it to `prop.table` which calculates the cells as a proportion. 

`prop.table()` also needs to be told if you want to calculate proportions for rows or columns. It does this through the margin argument. Remember to use an argument you put it in the function call separating arguments with a comma. So: `prop.table(table(x), margin=1)`. Margin can be set to 1, 2, or left empty.

`@instructions`
Create crosstabs of the relationship between interest in news and gender. Assume that gender is your independent variable and that news interest is your dependent variable. You'll have to figure out if margin should be 1 or 2 to ensure that you have column proportions.

`@hint`


`@pre_exercise_code`
```{r}
tmp.df <- read.csv("https://assets.datacamp.com/production/repositories/3406/datasets/5a4effcd07538b8b70830dd27e57ed8d97e39c22/ANES_Lim.csv")

write.csv(tmp.df, "ANES_Lim.csv", row.names=F)
rm(list=ls())
```

`@sample_code`
```{r}

```

`@solution`
```{r}
df <- read.csv("ANES_Lim.csv")


prop.table(table(df$newsint, df$gender), margin=2)

```

`@sct`
```{r}
ex() %>% {
  check_function(., "table")
  check_function(., "prop.table") %>% check_arg("margin") %>% check_equal()
  check_output_expr(., "prop.table(table(df$newsint, df$gender), margin=2)" )
}
```

---

## Finding Number of Observations and Dealing with Missing Values

```yaml
type: NormalExercise
key: a89bdff145
xp: 100
```

One last things. You may have noticed that you didn't directly see the number of observations in the tables we created. You'll have to check those yourself. The easiest way is to again use a function within a function by calling `sum(table(x))`. This will add up all the individual frequencies. 

For interval variables you can calculate this by seeing which of your observations are not missing and then adding up that. This first step is done using `is.na()` which checks to see if an observation is missing and returns true or false. You want the opposite of that so you add an exclamation point in front and then sum it up: `sum(!is.na(x))`

`@instructions`
No assignment here. Click next after looking at the code to be done.

`@hint`


`@pre_exercise_code`
```{r}
tmp.df <- read.csv("https://assets.datacamp.com/production/repositories/3406/datasets/5a4effcd07538b8b70830dd27e57ed8d97e39c22/ANES_Lim.csv")

write.csv(tmp.df, "ANES_Lim.csv", row.names=F)
rm(list=ls())

tmp.df <- read.csv("https://assets.datacamp.com/production/repositories/3406/datasets/f4fba345dc08afca82b97fc821143163783daaa8/state_party.csv")

write.csv(tmp.df, "state_party.csv", row.names=F)
rm(list=ls())
```

`@sample_code`
```{r}
df <- read.csv("ANES_Lim.csv")

table(df$newsint)

sum(table(df$newsint))


df <- read.csv("state_party.csv")

is.na(df$hs_rep_prop_all)

sum(!is.na(df$hs_rep_prop_all))
```

`@solution`
```{r}

```

`@sct`
```{r}

```
