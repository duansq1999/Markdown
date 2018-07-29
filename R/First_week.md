[TOC]

## R Objects and Attributes

### Objects

The five basic or "atomic" classes of objects:

- character
- numeric
- complex
- logical
- integer

The most basic object is *vector*

- A vector can only contain objects of same class
- Empty vector can be created with the `vector()`function

### Numbers 

- If you explicitly want an integer, you need to specify the `L` suffix
- There is a special **number** `Inf`  which represents **infinity**
- The value `NaN` represents an undefined value("**not a number**"), it can also be thought of as a **missing value**

### Attributes

R objects can have attributes:

- names, dimnames
- dimensions(e.g. matrices, arrays)
- class
- lengh
- other user-defined attributes/metadata

Attributes of an object can be accessed using the `attributes()` function



## Data Types - Vectors and Lists

### Creating Vectors

- Using the  `c()` function
- Using the `vector()` function

### Explicit Coercion

Objects can be explicitly coerced from one class to another using the `as.*` functions, if available.

Nonsensical coercion results in `NA`

### Lists

Lists are a special vector that **can contain elements of different classes**. 

- Using the `list()` functions to create
- Lists have index



## Data Types - Matrices

### Matrices

Matrices are vectors with **dimension** attribute. The dimension attribute is itself an integer vector of length 2 (nrow, ncol).

- Using the `matrix(nrow, ncol)` to create an empty matrices
- Matrices are constructed *column-wise*

```R
>m <- matrix(1:6, nrow = 2, ncol = 3)
>m
	[,1] [,2] [,3]
[1,]   1    3    5
[2,]   2    4    6
```

- Matrices can also created directly from vectors by adding a dimension attribute.

```R
>m <- 1:6
>m
[1] 1 2 3 4 5 6
>dim(m) <- c(2,3)
>m
	[,1] [,2] [,3]
[1,]   1    3    5
[2,]   2    4    6
```

