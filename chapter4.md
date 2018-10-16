---
title: 'Chi-Squared and Data Manipulation '
description: ""
---

## Chi-Squared

```yaml
type: NormalExercise
key: 45ef1d9d90
xp: 100
```

Today we are going to start by looking at how to do a chi-squared test and then we will look at some general data manipulation in R. 

The function to calculate the chi-squared test is chisq.test(). This expects the two variables as its input. The order of the variables does not matter (remember that from class the way the table is designed does not matter). 


`@instructions`
You are going to analyze the relationship between party identification and where a protester protested (either at the RNC or the DNC). This is the same data that is used as an example on this week's assignment. 

You should do two things in this assignment:

1. Create a cross-tab. Remember this can be done with prop.table() and table(). You'll want to set it up where party is the dependent variable and the location as the independent variable. You'll also want to use column percentages (margin=2). 
2. Calculate the chi-squared statistic. Remember chisq.test() expects just the two different vectors (you'll separate them with a comma).

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


prop.table(table(df$party, df$convention), margin=2)

chisq.test(df$party, df$convention)

```

`@sct`
```{r}
ex() %>% {
  check_function(., "table")
  check_function(., "prop.table") %>% check_arg("margin") %>% check_equal()
  check_output_expr(., "prop.table(table(df$party, df$convention), margin=2)" )
  check_function(., "chisq.test")
  check_output_expr(., "chisq.test(df$party, df$convention)")
}
```
