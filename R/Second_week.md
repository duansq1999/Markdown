[TOC]

## Introduce

Control structures in R allow you to control the flow of execution of the program, depending on runtime conditions. Common structures are

- `if, else` : testing a condition
- `for` : execute a loop a **fixed** number of times
- `while` : execute a loop while **condition is true**
- `repeat` : execute an infinite loop
- `break` : break the execution of a loop
- `next` : skip an iteration of a loop
- `return` : exit a function



## If-else

```R
if(<condition>) {
    ## do something
} else {
    ## do somethong else
}
```

or

```R
if(<condition>) {
    ## do something
} else if(<condition) {
    ## do somethong different
} else {
    ## do something different
}
```



## For loops

For loops take an iterator variable and assign it successive values from a **sequence** or **vector**. For loops are most commonly used for iterating over the elements of an objects.

```R
for(i in 1:10) {
    print(i)
}
```

### Nested for loops

for loops can be nested.

```R
x <- matrix(1:6, 2, 3)

for(i in seq_len(nrow(x))) {
  for(j in seq_len(ncol(x))) {
    print(x[i, j])
  }
}
```



## While Loops

While loops begin by testing a condition. If true, then they execute the loop body. Once the loop body is executed, the condition is tested again, and so forth.

```R
while(count < 10) {
  print(count)
  count <- count + 1
}
```

