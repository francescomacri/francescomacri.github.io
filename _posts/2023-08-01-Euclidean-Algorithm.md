---
layout: post
author: Francesco Macrì
categories: Number_Theory
meta: "Python"
---


Given two integers $A$ and $B$ with $A > B \geqslant 0$, this algorithm computes gcd($A, B$). It is based on two facts: 

1. gcd($a, b$) = gcd($b, r$) if $a, b, q,$ and $r$ are integers with $a = b \cdot q + r$ and $0 \leqslant r < b$.
2. gcd($a, 0$) = $a$.

(*From: Susanna S. Epp, Discrete Mathematics with Applications, Metric Version, 2020 Australia, page 254.*)

*Here is a sample implementation of the algorithm in Python:*

```python
def euclid(a, b):
    while b != 0:
        r = a % b
        if r == 0:
            return b
        else:
            a = b
            b = r
    return    
```
<a href="https://github.com/francescomacri/Number_Theory_Into_Code/blob/main/euclidean_algorithm.py" target="_blank">Here</a> you will find the code in GitHub.