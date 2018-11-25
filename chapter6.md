---
title: Correlations
description: ""
---

## Correlations

```yaml
type: NormalExercise
key: ec6271019a
xp: 100
```

In R we use `cor()` to calculate the correlations between variables. It expects that the first two arguments will be the vectors you want to calculate the correlation between, and then has several additional arguments: 

- `use =`: `cor()` has a different way to include or exclude missing variables then the previous functions we have used. `use = "everything"` (the default) will include ALL observations and so will not provide results if there are missing variables. You will want to set it to `use = "complete.obs"` to use only the observations that are non-missing. 
- `method=`: This controls what type of correlation it estimates. The default is `"pearson"` but it can also be `"spearman"` or `"kendall"`. 


If you want to estimate a correlation between `var1` and `var2` of the dataset `df` you'd write:
```
cor(df$var1, df$var2)
```

To change the method and drop missing observations you'd write:
```
cor(df$var1, df$var2, method="kendall", use="complete.obs")
```

`@instructions`
Calculate the **spearman** correlation between `age` and and `marches`. Be sure to exclude missing observations or else you will get `NA` as a result.

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

cor(df$age, df$marches, method="spearman", use="complete.obs")

```

`@sct`
```{r}
ex() %>% {
  check_function(., "cor" ) %>% check_arg("method") %>% check_equal()
  check_function(., "cor" ) %>% check_arg("use") %>% check_equal()
  check_output_expr(., "cor(df$age, df$marches, method='spearman', use='complete.obs')")
}
```

---

## Correlation Hypothesis Testing

```yaml
type: NormalExercise
key: d7ef4af9ae
xp: 100
```

To calculate a hypothesis test of a correlation you use `cor.test()` instead of `cor()`. It takes all the arguments that `cor()` does as well as several of the arguments that we used with `t.test()`. In particular you can use `conf.level=` and `alternative=` to change the confidence level and the alternative hypothesis. 

The one difference between `cor()` and `cor.test()` is that `cor.test()` automatically drops any observation with missing values.

`@instructions`
Calculate a hypothesis test for the correlation we did in the last exercise (the spearman correlation between `age` and `marches`). This should use a two-sided alternative and a 95% confidence interval (the defaults).

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

cor.test(df$age, df$marches, method="spearman")


```

`@sct`
```{r}
ex() %>% {
  check_function(., "cor.test" ) %>% check_arg("method") %>% check_equal()
  check_output_expr(., "cor.test(df$age, df$marches, method='spearman')")
}
```

---

## Scatter Plots

```yaml
type: NormalExercise
key: 9faf742bf2
xp: 100
```

Plots in R can be highly customized. Scatter plots all use the same function though: `plot()`. `plot()` expects one or two vectors that it will plot. If you want to ensure which one is on the y axis, and which is on the x axis you can explicitly identify them: `plot(y=, x=)`. Beyond this there are additional arguments you can call:

- `xlab=` or `ylab=`: Will change the label used for the y or x axis. Be sure to put whatever you want it to be in quotes: `xlab="Unemployment Rate"`
- `main=`: Will change the main title in a similar way to `xlab` or `ylab`
- `pch=`: Can be used to changes the symbol used for points. You can set it to any integer between 0 and 25. For example `pch=2` makes the symbols into open triangles. The default is `pch=1`. 
- `col=`: Will set the color used for the points. You can pick from a lot of basic colors like: red, green, blue, yellow, orange, etc. Be sure to put the color name in quotes. 
- `type=`: Will change the type of plot. The default `type="p"` will make a scatter plot, while `type="l"` will make a line plot. 

Putting this all together would look something like:
```
plot(x=df$var1, y=df$var2, pch=2, col="red", main="Var 2 vs Var 1", xlab="Var 1",ylab="Var 2") 
```

`@instructions`
Make a plot between `age` and `marches`. Change `pch`, `col`, and `main`.

`@hint`


`@pre_exercise_code`
```{r}
tmp.df <- read.csv("http://assets.datacamp.com/production/repositories/3406/datasets/41ae7a219de8ed396ebf3d49e6561a03fe27541a/protest_survey.csv")
tmp.df <- tmp.df[tmp.df$marches < 100,]
tmp.df <- tmp.df[tmp.df$age < 100,]

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

plot(x=df$age, y=df$marches, pch=2, col="red", main="Age vs Marches")
```

`@sct`
```{r}
ex() %>% {
  check_function(., "plot" ) %>% {
    check_arg(., "pch")
    check_arg(., "col")
    check_arg(., "main")
  } 
}
```
