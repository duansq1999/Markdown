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

- The *formal arguments* are the arguments included in the function definition
- The formals function returns a list of all the formal arguments of a function 
- Not every function call in  R makes use of all the formal arguments
- Function arguments can be *missing* or might have default values

### Argument Matching

R functions arguments can be matched positionally or by name. So the following calls to `sd` are all equivalent

```R
> mydata <- rnorm(100)
> sd(mydata)
> sd(x = mydata)
> sd(x = mydata, na.rm = FALSE)
```

```R
> args(lm)
function (formula, data, subset, weights, na.action, method = "qr", 
    model = TRUE, x = FALSE, y = FALSE, qr = TRUE, singular.ok = TRUE, 
    contrasts = NULL, offset, ...) 
NULL
```



## Coding Standards

1. Always use text files / text editor
2. Indent your code
3. Limit the width of your code
4. Limit the length of individual function

## Dates and Times in R

R has developed a special representation of dates and times

- Dates are represented by `Data` class
- Times are represented by the `POSIXct` or `PODIClt` class
- Dates are stored internally as the number of days since 1970-01-01
- Time are stored internally as the number of seconds since 1970-01-01

### Dates in R

```R
> x <- as.Date("1970-01-01")
> x
[1] "1970-01-01"
> unclass(x)
[1] 0
> unclass(as.Date("1970-01-02"))
[1] 1
```

### Times in R

- `POSIXct`is just very large integer under the hood ; it use a useful class when you want to store times in something like a date frame

- `POSIXlt` is a list underneath and it stores as bunch of other useful information like the day of the week, day of the year , month, day of the month

There are a number of generic functions that work on dates and times

- `weekdays` : give the day of the week
- `months` : give the month name
- `quarters`: give the quarter number

```R
> x <- Sys.time()
> x
[1] "2018-08-04 08:26:58 CST"
> p <- as.POSIXlt(x)
> names(unclass(p))
 [1] "sec"    "min"    "hour"   "mday"   "mon"    "year"   "wday"   "yday"  
 [9] "isdst"  "zone"   "gmtoff"
> p$sec
[1] 58.0464
```

```R
> x <- Sys.time()
> x
[1] "2018-08-04 08:30:55 CST"
> unclass(x)
[1] 1533342655
> x$sec
Error in x$sec : $ operator is invalid for atomic vectors
> p <- as.POSIXlt(x)
> p$sec
[1] 55.44776
```

Finally, there is the `strptime` function in case your dates are written in a different format

```R
> datestring <- c("January 10, 2018 10:40", "December 9, 2017 9:10")
> x <- strptime(datestring, "%B %d, %Y %H:%M")
> x
[1] "2018-01-10 10:40:00 CST" "2017-12-09 09:10:00 CST"
```

### Operations on Dates and Times

You can use mathematical operations on dates and times,

```R
> x <- as.Date("1999-05-24")
> y <- strptime("January 10, 2018 10:40", "%B %d, %Y %H:%M")
> x - y
Error in x - y : non-numeric argument to binary operator
In addition: Warning message:
Incompatible methods ("-.Date", "-.POSIXt") for "-" 
> x <- as.POSIXlt(x)
> x - y
Time difference of -6806.111 days
```

