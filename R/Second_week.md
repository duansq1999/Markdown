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

Sometimes there will be more than one condition in the test.

```R
z <- 5

while(z >=3 && z <= 10) {
  print(z)
  coin <- rbinom(1,1,0.5)
  
  if(coin == 1) {
    z <- z + 1
  } else {
    z <- z-1
  }
}
```



## Repeat, Next, Break

### Repeat 

Repeat initiates an infinite loop. these are not commonly used in statistical applications but they do have their uses. The only way to exit a repeat loop is to call `break`.

```R
x0 <- 1
tol <- 1e-8

repeat {
  x1 <- computeEstimate()
  
  if(abs(x1 - x0) < tol) {
    break
  } else {
    x0 <- x1
  }
}
```

### next, return

```R
for(i in 1:100) {
  if(i > 20) {
    next
  }
}
```

## Functions

```R
f <- function(<arquments>) {
    ## do something interesting
}
```

### Function Arguments

Functions have **named arguments** which potentially have **default values**.

- The formal arguments are the arguments included in the function definition
- The formals function returns a list of all the formal arguments of a function 
- Not every function call in  R makes use of all the formal arguments
- Function arguments can be missing or might have default values

