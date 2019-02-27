---
title: Variables
description: ""
---

## Intro to variables

```yaml
type: NormalExercise
key: f870f1cdb4
xp: 100
```

Today we are going to see how variables work in R and how to explore them in a dataset. 

When we talk about a variable in R, we don't necessarily mean the exact same thing as a variable in general. In R when we say variable we just mean something that we've stored in R and can recall. In the below example you will see two types of things you can store and how to get them back.

`@instructions`
Variables are created in R by assigning something to a word or letter. The word or letter is the variable. You use `<-` to assign something to it. So if you want to assign the number `4` to the variable `kevin` you would write: `kevin <- 4`. This assigns `4` to `kevin`. You can then recall `kevin`, by typing `kevin` and hitting enter (this is often refered to as _calling a variable_). 

For this assignment I want you to create a variable named `pol` and assign it the value `25` and then call that variable to show what it is.

`@hint`


`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}
##### again we can start by assigning 4 to kevin

kevin <- 4

#### If you just run the above then there will be no output. 
#### If you want to see what the variable kevin is, then you can call it by just writing it out:
kevin 


#### now assign 25 to pol, and then call it again
```

`@solution`
```{r}
##### again we can start by assigning 4 to kevin

kevin <- 4

#### If you just run the above then there will be no output. 
#### If you want to see what the variable kevin is, then you can call it by just writing it out:
kevin 


#### now assign 25 to pol, and then call it again
pol <- 25
pol
```

`@sct`
```{r}
ex() %>% check_object("pol") %>% check_equal()
```

---

## More than just numbers

```yaml
type: NormalExercise
key: 3661b50a7d
xp: 100
```

Variables don't just have to store numbers, they can also store words or sentences (called **strings**) or a list of numbers (called **vectors**). See the code to the right to see how you create these two types of variables.

`@instructions`
Create one vector called `x` with the value `"Political Science"` and another vector called `y` that is a list of the numbers `1` through `5`.

`@hint`


`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}
### Creating a variable that is a word or sentence is just like doing it with a number
### but you need to suround the word(s) with quotation marks.

miami <- "Oxford Ohio"
miami

### Creating a vector (a list of numbers) is more complicated. 
### you need to surround them with paranthesis and put a c infront of the
### first paranthesis. Each number should be separated by a comma

primes <- c(1, 3, 5, 7, 11)

### now put your code for x and y below
```

`@solution`
```{r}
### Creating a variable that is a word or sentence is just like doing it with a number
### but you need to suround the word(s) with quotation marks.

miami <- "Oxford Ohio"
miami

### Creating a vector (a list of numbers) is more complicated. 
### you need to surround them with paranthesis and put a c infront of the
### first paranthesis. Each number should be separated by a comma

primes <- c(1, 3, 5, 7, 11)

### now put your code for x and y below
x <- "Political Science"
y <- c(1, 2, 3, 4, 5)
```

`@sct`
```{r}
ex() %>% {
  check_object(., "x") %>% check_equal()
  check_object(., "y") %>% check_equal()
}
```

---

## So what?

```yaml
type: NormalExercise
key: d601fc6c6b
xp: 100
```

Variables are useful in R because we can easily manipulate vectors without having to type them over and over again. You can do all the same sort of operations we did last week, but on variables. 

For example, the current population of Ohio is 11,658,609 if you want to figure out what 10% or 20% of the population is you can store the population as a variable and then multiply it by .1 and .25.

`@instructions`
The Pennsylvania population is 12,805,537. Store it as the variable `pa.pop` and then figure out what 10%, 25% and 50% of the population of Pennsylvania is by multiplying that variable.

`@hint`


`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}
## store the population of ohio:
ohio.pop <- 11658609

## multiply it by .25 to figure out what 25% of the population is:
.25 * ohio.pop

## multiple it by .10 to figure out what 10% of the population is:
.10 * ohio.pop

```

`@solution`
```{r}
## store the population of ohio:
ohio.pop <- 11658609 ### note that you can't include commas in the numbers

## multiply it by .25 to figure out what 25% of the population is:
.25 * ohio.pop

## multiple it by .10 to figure out what 10% of the population is:
.10 * ohio.pop

pa.pop <- 12805537
pa.pop * .25
pa.pop * .10
pa.pop * .50
```

`@sct`
```{r}
ex() %>% check_correct(
  {
    check_output_expr(., "pa.pop * .25")
    check_output_expr(.,"pa.pop * .5")
    check_output_expr(.,"pa.pop * .1")
   },
  check_object(., "pa.pop") %>% check_equal()
)

```

---

## Functions

```yaml
type: NormalExercise
key: 4459f12500
xp: 100
```

Along with variables, R has **functions** which take in one or more variables and return a result (just like a function in math). There are thousands of functions that have been written for R, and you can download more of them for specialized tasks as well. Right now we are just going to see how functions work, and how to find out more about them.

We are going to start by looking at just three functions: `sum`, `range`, and `sort`. Each function is run by writing `function(x)` where `function` is the name of the function and `x` is the variable you are running it on. You can also save the output of a function as a new variable just like you would store another variable: `y <- function(x)`

The functions that we will use here are relatively simple:
- sum: returns the summation of all the numbers in the vector you give it. 
- range: returns the minimum and maximum value present in the vector you give it. 
- sort: returns the vector you gave it but reordered from highest to lowest.

`@instructions`
1. ) Start by defining a variable called `x` that is a vector that contains the numbers 12, 4, 3, 2, 5, and -4. 
2. ) Next calculate the sum of all the numbers in `x` and store it as `tot`. 
3. ) Then find the minimum and maximum of `x` (you do not need to store these as anything). 
4. ) Finally use the `sort` function to rewrite `x` so that it is in order from highest to lowest (you will have to save this new `x` overtop of the old `x`).

`@hint`


`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}
##### Remember to run a function on something you write it like:
sort(c(4,2,5,1,2))
#### You can run functions on stored variables or directly on the numbers like I did above


```

`@solution`
```{r}
x <- c(12,4,3,2,5,-4)
tot <- sum(x)
range(x)
x <- sort(x)
```

`@sct`
```{r}
ex() %>% {
  check_object(., "x") %>% check_equal()
  check_object(., "tot") %>% check_equal()
  check_function(., "sum")
  check_function(., "range")
  check_function(., "sort")
}
```

---

## Getting help with functions

```yaml
type: NormalExercise
key: 71bee9060e
xp: 100
```

In general R is not often very helpful (at least when it produces errors). It can be helpful though if you need to understand **what** you can do with a function. R has its own baked in help that you can access by running `?function` where function is the function you want help about. This will open up something (if you are in RStudio it will open a page on the lower right) that explains:

- A short description of the function
- How you can call the function (this sometimes includes related functions as well), including how to set different options (arguments)
- A description of the different options that the function has. These are called arguments and they can include a lot of different things depending on the function.
- A more detailed description of the function
- Examples of how the function is used (not often helpful examples though)

`@instructions`
This will be a simple assignment. All I want is for you to take a vector used in the previous assignment and sort it but instead of having it go from low to high it should go from high to low. To do this you'll need to look up the help page of sort and look for an argument that you think will change the direction of the ordering.

Note that a lot of arguments take the form of `something = FALSE` this means that the default is for this argument to be off. To turn it on, change it to `something = TRUE` when you call it.

`@hint`


`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}
### to start, lets look at another function, seq
### seq creates a sequence of a numbers as a vector
seq(1, 10) ## will output a sequence from 1 to 10

### but what if you want to create one with only even numbers?
?seq #calls up the help 

### you should see that seq has several arguments and several related functions
### right now we are using just from and to in the seq call but we aren't 
### explicity naming them. There is also an argument called by 
### this changes the increment of the sequence so if we do
seq(2, 10, by=2)

### we get only even numbers from 2 to 10
### you can also make all arguments explicit:
seq(from=2, to=10, by=10)

### now take x from the previous example and sort it in the opposite direction
x <- c(12,4,3,2,5,-4)

```

`@solution`
```{r}
### to start, lets look at another function, seq
### seq creates a sequence of a numbers as a vector
seq(1, 10) ## will output a sequence from 1 to 10

### but what if you want to create one with only even numbers?
?seq #calls up the help 

### you should see that seq has several arguments and several related functions
### right now we are using just from and to in the seq call but we aren't 
### explicity naming them. There is also an argument called by 
### this changes the increment of the sequence so if we do
seq(2, 10, by=2)

### we get only even numbers from 2 to 10
### you can also make all arguments explicit:
seq(from=2, to=10, by=10)

### now take x from the previous example and sort it in the opposite direction
x <- c(12,4,3,2,5,-4)
sort(x, decreasing=T)
```

`@sct`
```{r}
ex() %>% check_function("sort") %>% check_arg("decreasing") %>% check_equal()
```

---

## Variables and Datasets

```yaml
type: NormalExercise
key: 7d54c3d304
xp: 100
```

We usually do not build all of our variables by hand. Instead we use saved files to import them as datasets. 

Datasets are like excel sheets where each column is a different variable and each row is a different unit. Often you will actually load a dataset from an excel file or from a "csv" file. You will have to store the dataset as its own "variable" just like you stored the numbers, strings, and vectors previously. Then you will be able to access different variables and units on the dataset. 

To load a dataset you need to use the function: `read.csv `this takes the name of the file as an argument and returns the dataset.

Once you load the dataset you can access particular variables in it using `$variablename`. If you had a variable named gender in the dataset df then you'd access it by calling `df$gender`

`@instructions`
There is a dataset named `"state_party.csv"` which contains data for 2010 on the estimated proportion of Republican and Democratic voters as well a the percentage of Democrats and Republicans in the state legislature (just the lower chamber). 

You are going to load it, and then calculate the range of democrats and republican voters and store them (separately) as dem.range and rep.range.

`@hint`


`@pre_exercise_code`
```{r}
tmp.df <- read.csv("https://assets.datacamp.com/production/repositories/3406/datasets/f4fba345dc08afca82b97fc821143163783daaa8/state_party.csv")

write.csv(tmp.df, "state_party.csv", row.names=F)
rm(list=ls())
```

`@sample_code`
```{r}
### The file is named "state_party.csv" so to load it use read.csv("state_party.csv") 
### to manpulate it you need to store it as something (I suggest using df)

### to figure out what variables are called pass the dataset you made to the function names()
### names(df) this will display the names of each column
### the one we are interested in are just called democrat and republican
### you can also call head(df) to see the first few rows of the dataset

### Once you created the dataset you can the pass variables to a function
### just like we did previously, but write out the whole thing: df$democrat
```

`@solution`
```{r}
### The file is named "state_party.csv" so to load it use read.csv("state_party.csv") 
### to manpulate it you need to store it as something (I suggest using df)

df <- read.csv("state_party.csv")

### to figure out what variables are called pass the dataset you made to the
### function names(): names(df) this will display the names of each column
### the one we are interested in are just called democrats and republicans

names(df)

### Once you created the dataset you can the pass variables to a function
### just like we did previously, but write out the whole thing: df$democrats

dem.range <- range(df$democrat)
rep.range <- range(df$republican)


```

`@sct`
```{r}
ex() %>% {
  check_object(., "dem.range") %>% check_equal()
  check_object(., "rep.range") %>% check_equal()
}
```

---

## Mean and Median

```yaml
type: NormalExercise
key: 51ff613b00
xp: 100
```

R has functions that can easily compute the mean and median of a vector. The function for the mean is `mean()` and the function for median is `median()`.

`@instructions`
For this assignment you will have to load the dataset `"state_party.csv"` again and then calculate the mean and median of the percentage of democrats in a state (the variables are called democrat and republican).

Remember to load data you need to call read.csv and save the output: `df <- read.csv("state_party.csv")` and then you can access the variables in the dataset using the `$`.

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

## Final Note

```yaml
type: NormalExercise
key: f3fec926b7
xp: 100
```

A final few notes. 

1) In order to load a file using `read.csv()` you first have to tell R where to look on your computer. To do this you will need to use `setwd()`. In `setwd()` you need to place the path to your file. This might look like: `"/users/kevinreuning/dropbox"` or `"C:/users/kevinreuning/dropbox"`. 

2) Sometimes vectors in datasets have missing values. Theses show up as `NA` when you call them. A lot of R functions do not know what to do with missing values so you have to tell it what to do. To do this you _usually_ add `, na.rm=T` to a function call. Below I demonstrate both of these.

`@instructions`
No assignment for this one, just look at what I did to `setwd()` and to use a function on a vector with missing values. 

After you run the code just hit submit answer to finish this chapter.

`@hint`


`@pre_exercise_code`
```{r}
tmp.df <- read.csv("https://assets.datacamp.com/production/repositories/3406/datasets/f4fba345dc08afca82b97fc821143163783daaa8/state_party.csv")

write.csv(tmp.df, "state_party.csv", row.names=F)
rm(list=ls())
```

`@sample_code`
```{r}
### Sets the working directory (this is actually the default so you didn't have to do it last assignment)
setwd("/home/repl")
df <- read.csv("state_party.csv")

df$hs_dem_prop_all ## has a missing value


range(df$hs_dem_prop_all) ## doesn't provide a result


range(df$hs_dem_prop_all, na.rm=T) ## drops the missing value 
```

`@solution`
```{r}

```

`@sct`
```{r}

```
