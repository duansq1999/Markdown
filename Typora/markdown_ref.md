## Contents

[TOC]

## Block Elements

### Paragraph and line breaks

### Headers

```markdown
# This is H1
###### This is H6
```

### Blockquotes

```markdown
>This is a blockquote.
```

> This is a blockquote.

### Lists 

```markdown
### un-order lists
* task1
* task2
## order lists
1. tast1
2. tast2
```

### Task Lists

```markdown
- [ ] incomplete
- [x] completed
```

- [ ] incomplete
- [x] completed

### Code Blocks

```markdown
This is an example:
​```python
import this
​```
```

This is an example:

```python
import this
```

### Math Blocks

```markdown
$$
\int x dx = \frac{1}{2}x^{2}+C
$$
or define $x_1$, $y_1$
```
$$
\int x dx = \frac{1}{2}x^{2}+C
$$
or define $x_1$, $y_1$

### Tables

```markdown
|Left-Name|Center-Age|Right-Sex|
|:---|:---:|---:|
|Duansq|18|Man|
|Duanmq|24|Man|
```

|Left-Name|Center-Age|Right-Sex|
|:---|:---:|---:|
|Duansq|18|Man|
|Duanmq|24|Man|

### Footnotes

```markdown
You can creat a footnotes like this[^1].
[^1]:Here
```

You can create footnotes like this[^1]. 

[^1]: Here

### Horizontal Rules

```markdown
***
or 
---
```

---

***

### YAML Front Matter

### Table of Contents

```markdown
[toc]
```

[TOC]

## Span Elements

### Links

```markdown
[zomath](https://zomath.github.io/ "Title)
[zomath](https://zomath.github.io/)
```

[zomath](https://zomath.github.io/ "Title)
[zomath](https://zomath.github.io/)

#### Internal Links

[Lists](## Contents)

#### Reference Links

```markdown
This is [an example][id] reference-style link.
Then, anywhere in the document, you define your link label like this, on a line by itself:
[id]: http://example.com/  "Optional Title Here"
```

This is [an example][id] reference-style link. 

Then, anywhere in the document, you define your link label like this, on a line by itself: 

[id]: http://example.com/  "Optional Title Here"

