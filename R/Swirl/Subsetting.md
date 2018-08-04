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

