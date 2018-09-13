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

```
