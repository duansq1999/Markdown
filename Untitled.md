[TOC]

## Data foundation

```mermaid
graph TD
	id1[Variable type] --> id2[quantitative]
	id1-->id3[qualitative]
	id2-->id4[continuous]
	id2-->id5[descret]
	id3-->id6[order]
	id3-->id7[unorder]
	id7---id8[not comparable]
	id6---id9[order meaningful]
```



## Characterization and visualization of numerical variables

- measures of center 

  - mean, median, mode

- measures of spread

  - range: max- min
  - variance


$$
\text{vanriance}=\frac{\sum_{n=1}^{n}(x_i-\bar x)^2}{n-1}
$$
  -	standard variance
$$
  \text{sd}=\sqrt{\text{vanriance}}
$$
  -	interquartile range

		robust statistics

  - yes: median, interquartile range(smallly affected by extreme value)
  - no: mean, sd, range(affected by extreme value)

		visualization of **a value**

  - histogram, dot plot
  - box plot(mode, interquartile range, extreme value)

		relationship of **two values**

  - scatter plot: direction, shape, strength, extreme value

## Characterization and visualization of qualitative

- Visualization of **a categorical variable**
  - frequency table, bar plot
- relationship of **two categorical variables**
  - contingency table, relative frequencies