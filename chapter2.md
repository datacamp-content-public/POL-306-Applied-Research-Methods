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

In class this week we started talking about variables. Today we are going to see how variables work in R and how to explore them in a dataset. 

When we talk about a variable in R, we don't necessarily mean the exact same thing as a variable in general. In R when we say variable we just mean something that we've stored in R and can recall. In the below example you will see two types of things you can store and how to get them back.

`@instructions`
Variables are created in R by assigning "something" to a word or letter. The word or letter is the variable. You use "<-" to assign something to it. So if you want to assign the number 4 to the variable "kevin" you would write: "kevin <- 4". This assigns "4" to "kevin". You can then recall kevin, by just typing kevin. 

For this assignment I want you to create a variable named pol and assign it the value 25 and then call that variable to show what it is.

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

Variables don't just have to store numbers, they can also store words or sentences (called **strings**) or a list of numbers (called **vectors**).

`@instructions`
Create one vector called x with the value "Political Science" and another vector called y that is a list of the numbers 1 through 5.

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
The Pennsylvania population is 12,805,537. Store it as the variable pa.pop and then figure out what 10%, 25% and 50% of the population of Pennsylvania is.

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

Along with variables, R has **functions** which are scripts that run on the variables you give them. There are thousands of functions that have been written for R, and you can download more of them for specialized tasks as well. Right now we are just going to see how functions work, and how to find out more about them.

`@instructions`
We are going to start by looking at just three functions: sum, range, and sort. Each function is run by writing function(x) where "function" is the name of the function and "x" is the variable you are running it on. You can also save the output of a function as a new variable just like you would store another variable: "y <- function(x)"

The functions that we will us here are relatively simple:
- sum: returns the summation of all the numbers in the vector you give it. 
- range: returns the minimum and maximum value present in the vector you give it. 
- sort: returns the vector you gave it but reordered from lowest to highest

Start by defining a variable called x that is a vector that contains the numbers 12, 4, 3, 2, 5, and -4. Next calculate the summation of all the numbers in x and store it as tot. Then find the minimum and maximum of x. Finally use the sort function to rewrite x so that it is in order from highest to lowest.

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
  check_object(., x) %>% check_equal()
  check_object(., tot) %>% check_equal()
  check_function(., "sum")
  check_function(., "range")
  check_function(., "sort")
}
```


---

## Variables and Datasets

```yaml
type: NormalExercise
key: 7d54c3d304
xp: 100
```

We usually do not build all of our variables by hand. Instead we use saved files to import them as datasets. 

Datasets are like excel sheets where each column is a different variable and each row is a different unit. Often you will actually load a dataset from an excel file or from a "csv" file. You will have to store the dataset as its own "variable" just like you stored the numbers, strings, and vectors previously. Then you will be able to access different variables and units on the dataset. Lets start though just by loading the dataset and looking at functions.

`@instructions`


`@hint`


`@pre_exercise_code`

```{r}

```


`@sample_code`

```{r}

```


`@solution`

```{r}

```


`@sct`

```{r}

```
