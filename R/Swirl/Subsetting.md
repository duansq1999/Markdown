---
abbrlink: '0'
---
In this lesson, we'll see how to extract elements from a vector based on some conditions that we specify.

For example, we may only be interested in the first 20 elements of a vector, or only the elements that are not NA, or only those that are positive or correspond to a specific variable of interest. By the end of this lesson, you'll know how to handle each of these scenarios.

I've created for you a vector called `x` that contains a random ordering of 20 numbers (from a standard normal distribution) and 20 NAs. Type x now to see what it looks like.

```R
> x
 [1] -0.17236255          NA          NA  0.13952760 -0.36608355          NA
 [7] -1.12927788 -1.32977863          NA -0.08171064          NA          NA
[13]          NA          NA -0.30462020          NA  0.99016845 -0.96313333
[19] -0.16652250  0.94698145  0.16434575          NA -0.91793976  2.69899787
[25]          NA          NA          NA  1.91435419          NA          NA
[31] -0.19231514          NA -1.05754007  0.44814034          NA          NA
[37] -0.74212343  0.79927213          NA          NA
```

The way you tell R that you want to select some particular elements (i.e. a 'subset') from a vector is by placing an 'index vector' in square brackets immediately following the name of the vector.

For a simple example, try `x[1:10]` to view the first ten elements of `x`.

```R
> x[1:10]
 [1] -0.17236255          NA          NA  0.13952760 -0.36608355          NA
 [7] -1.12927788 -1.32977863          NA -0.08171064
```

Index vectors come in four different flavors -- **logical vectors**, **vectors of positive integers**, **vectors of negative integers**, and **vectors of character strings** -- each of which we'll cover in this lesson.

```R
> x[is.na(x)]
 [1] NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA
```

Recall that `!` gives us the negation of a logical expression, so `!is.na(x)` can be read as 'is not NA'. Therefore, if we want to create a vector called `y` that contains all of the non-NA values from x, we can use `y <- x[!is.na(x)]`. Give it a try. 

```R
> y <- x[!is.na(x)]
> y
 [1] -0.17236255  0.13952760 -0.36608355 -1.12927788 -1.32977863 -0.08171064
 [7] -0.30462020  0.99016845 -0.96313333 -0.16652250  0.94698145  0.16434575
[13] -0.91793976  2.69899787  1.91435419 -0.19231514 -1.05754007  0.44814034
[19] -0.74212343  0.79927213
```

Type `y[y > 0]` to see that we get all of the positive elements of `y`, which are also the positive elements of our original vector `x`.

```R
> y[y > 0]
[1] 0.1395276 0.9901684 0.9469815 0.1643457 2.6989979 1.9143542 0.4481403
[8] 0.7992721
```

You might wonder why we didn't just start with `x[x > 0]` to isolate the positive elements of `x`. Try that now to see why.

```R
> x[x > 0]
 [1]        NA        NA 0.1395276        NA        NA        NA        NA
 [8]        NA        NA        NA 0.9901684 0.9469815 0.1643457        NA
[15] 2.6989979        NA        NA        NA 1.9143542        NA        NA
[22]        NA 0.4481403        NA        NA 0.7992721        NA        NA
```

Since `NA` is not a value, but rather a placeholder for an unknown quantity, the expression `NA > 0` evaluates to `NA`. Hence we get a bunch of NAs mixed in with our positive numbers when we do this.

```R
> NA > 0
[1] NA
```

Combining our knowledge of logical operators with our new knowledge of subsetting, we could do this -- `x[!is.na(x) & x > 0]`. Try it out.

```R
> x[!is.na(x) & x > 0]
[1] 0.1395276 0.9901684 0.9469815 0.1643457 2.6989979 1.9143542 0.4481403
[8] 0.7992721
```

In this case, we request only values of `x` that are both non-missing AND greater than zero.

I've already shown you how to subset just the first ten values of `x` using `x[1:10]`. In this case, we're providing a vector of positive integers inside of the square brackets, which tells R to return only the elements of `x` numbered 1 through 10.

Many programming languages use what's called '**zero-based indexing**', which means that the first element of a vector is considered element 0. R uses '**one-based indexing**', which (you guessed it!) means the first element of a vector is considered element 1.

Can you figure out how we'd subset the 3rd, 5th, and 7th elements of x?

**Hint** -- Use the `c()` function to specify the element numbers as a numeric vector.

```R
> x[c(3, 5, 7)]
[1]         NA -0.3660836 -1.1292779
```

It's important that when using integer vectors to subset our vector x, we stick with the set of indexes `{1, 2, ..., 40}` since `x` only has 40 elements. 

What happens if we ask for the zeroth element of `x` (i.e. x[0])? Give it a try.

```R
> x[0]
numeric(0)
```

As you might expect, we get nothing useful. Unfortunately, R doesn't prevent us from doing this. What if we ask for the 3000th element of x? Try it out.

```R
> x[3000]
[1] NA
```

Again, nothing useful, but R doesn't prevent us from asking for it. This should be a cautionary tale. You should always make sure that what you are asking for is within the bounds of the vector you're working with.

What if we're interested in all elements of x EXCEPT the 2nd and 10th? It would be pretty tedious to construct a vector containing all numbers 1 through 40 EXCEPT 2 and 10.

Luckily, R accepts negative integer indexes. Whereas `x[c(2, 10)]` gives us ONLY the 2nd and 10th elements of `x`, `x[c(-2, -10)]` gives us all elements of `x` **EXCEPT** for the 2nd and 10 elements.  Try `x[c(-2, -10)]` now to see this.

```R
> x[c(-2, -10)]
 [1] -0.1723626         NA  0.1395276 -0.3660836         NA -1.1292779
 [7] -1.3297786         NA         NA         NA         NA         NA
[13] -0.3046202         NA  0.9901684 -0.9631333 -0.1665225  0.9469815
[19]  0.1643457         NA -0.9179398  2.6989979         NA         NA
[25]         NA  1.9143542         NA         NA -0.1923151         NA
[31] -1.0575401  0.4481403         NA         NA -0.7421234  0.7992721
[37]         NA         NA
```

A shorthand way of specifying multiple negative numbers is to put the negative sign out in front of the vector of positive numbers. Type `x[-c(2, 10)]` to get the exact same result.

```R
> x[-c(2,10)]
 [1] -0.1723626         NA  0.1395276 -0.3660836         NA -1.1292779
 [7] -1.3297786         NA         NA         NA         NA         NA
[13] -0.3046202         NA  0.9901684 -0.9631333 -0.1665225  0.9469815
[19]  0.1643457         NA -0.9179398  2.6989979         NA         NA
[25]         NA  1.9143542         NA         NA -0.1923151         NA
[31] -1.0575401  0.4481403         NA         NA -0.7421234  0.7992721
[37]         NA         NA
```

So far, we've covered three types of index vectors -- logical, positive integer, and negative integer. The only remaining type requires us to introduce the concept of 'named' elements.

