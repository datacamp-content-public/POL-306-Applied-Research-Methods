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
