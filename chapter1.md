---
title: 'Introduction to R'
description: 'Today we are going to learn the basics of R. '
---

## R Addition

```yaml
type: NormalExercise 
xp: 100 
key: 9ed7531164   
```


We will start off seeing how R can be used as a calculator.


`@instructions`
Add together 7 and 11

`@hint`


`@pre_exercise_code`

```{r}

```


`@sample_code`

```{r}
#### To add 3 and 5 type
3 + 5

### Now add 7 and 11
```


`@solution`

```{r}
#### To add 3 and 5 type
3 + 5

### Now add 7 and 11 
7 + 11
```


`@sct`

```{r}
ex() %>% check_output_expr("7+11")
```


`@possible_answers`


`@feedback`


---

## More R calculator functions

```yaml
type: NormalExercise 
xp: 100 
key: c02ebefc9d   
```


R can do more than just addition but can also do subtraction, multiplication and division.


`@instructions`
Do the following problems:

- Subtract 3 from 8. 
- Multiply 2 by 6
- Divide 9 by 2

`@hint`


`@pre_exercise_code`

```{r}

```


`@sample_code`

```{r}
### subtraction uses -

## multiplication uses *

## division uses /
```


`@solution`

```{r}
### subtraction uses -
8 - 3

## multiplication uses *
6 * 2

## division uses / 
9 / 2
```


`@sct`

```{r}
ex() %>% check_output_expr("8-3") %>% check_output_expr("6*2")  %>% check_output_expr("9/2")
```


`@possible_answers`


`@feedback`


---

## Multiple Operations

```yaml
type: NormalExercise 
xp: 100 
key: e4625d4c47   
```


You do not have to do everything in one line. You can also chain operations together just like you would in math. 

Just like you should, R follows PEMDAS rules of operation.


`@instructions`
Type in two different operations. 

- Multiply 3 by 4 and then subtract 1 from it (your answer should be 11).
- Add 3 and 2 together and then multiple that by 5 (your answer should be 25).

`@hint`


`@pre_exercise_code`

```{r}

```


`@sample_code`

```{r}
### Remember you want to keep PEMDAS in mind.
### For example:
3 + 4 * 2
### is different from
(3 + 4) * 2
```


`@solution`

```{r}
### Remember you want to keep PEMDAS in mind.
### For example:
3 + 4 * 2
### is different from
(3 + 4) * 2

3 * 4 - 1
(2 + 3) * 5
```


`@sct`

```{r}
ex() %>% check_output_expr("3*4-1") %>% check_output_expr("(2+3)*5")
```


`@possible_answers`


`@feedback`

