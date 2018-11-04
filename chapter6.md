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

- `use = "everything"`: `cor()` has a different way to include or exclude missing variables then the previous functions we have used. `use = "everything"` will include ALL observations and so will not provide results if there are missing variables. You will want to use this to `use = "complete.obs"' to only use observations that are non-missing. 
- `method= "pearson"`: This controls what type of correlation it estimates. The default is `"pearson"` but it can also be `"spearman"` or `"kendall"`. 


If you want to estimate a correlation between `var1` and `var2` of the dataset `df` you'd write:
```
cor(df$var1, df$var2)
```

To change the method and drop missing variables you'd write:
```
cor(df$var1, df$var2, method="kendall", use="complete.obs")
```



`@instructions`
Calculate the spearman correlation between `age` and and `marches`. Be sure to exclude missing observations or else you will get `NA` as a result.

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

To calculate a hypothesis test of a correlation you use `cor.test` instead of `cor`. It takes all the arguments that `cor` does as well as several of the arguments that we used with `t.test`. In particular you can use `conf.level=` and `alternative=` to change the confidence level and the alternative hypothesis. 

The one difference is that `cor.test` automatically drops any observation with missing values. 

`@instructions`
Calculate a hypothesis test for the correlation we did in the last exercise (the correlation between `age` and `marches`). This should use a two-sided alternative and a 95% confidence interval.

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
