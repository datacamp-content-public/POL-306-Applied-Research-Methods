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


---

## Final check

```yaml
type: NormalExercise 
xp: 100 
key: 5ed4fe6b3d   
```


And finally, R also can do exponentiation as well as all the other trig functions that you might remember (sine, cosine, tangent). R even has a lot of a standard variables like pi. We won't use most of these, but just so you see how it works lets try a few.


`@instructions`
You are going to square 3, take the square root of 2 and then finally just double pi.

`@hint`


`@pre_exercise_code`

```{r}

```


`@sample_code`

```{r}
### To exponentiate you use the ^ symbol (shift+6 on your keyboard). 
### Also square roots are the same as exponentiating by (1/2) so the square root of 5 is..
5^(1/2) 

### Now square 3

### Take the square root of 2

### To use pi, all you have to write is pi
pi

### You can use this just like a regular number, so double pi below


```


`@solution`

```{r}
### To exponentiate you use the ^ symbol (shift+6 on your keyboard). 
### Also square roots are the same as exponentiating by (1/2) so the square root of 5 is..
5^(1/2) 

### Now square 3
3^2
### Take the square root of 2
2^(1/2)
### To use pi, all you have to write is pi
pi

### You can use this just like a regular number, so double pi below
2*pi

```


`@sct`

```{r}
ex() %>% check_output_expr("3^2") %>% check_output_expr("2^(1/2)") %>% check_output_expr("2*pi")
```


`@possible_answers`


`@feedback`

