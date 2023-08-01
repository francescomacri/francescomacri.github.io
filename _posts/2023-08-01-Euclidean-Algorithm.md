---
layout: post
author: Francesco Macrì
---


Given two integers $A$ and $B$ with $A > B \geqslant 0$, this algorithm computes gcd($A, B$). It is based on two facts: 

1. gcd($a, b$) = gcd($b, r$) if $a, b, q,$ and $r$ are integers with $a = b \cdot q + r$ and $0 \leqslant r < b$.
2. gcd($a, 0$) = $a$.

_**From**: Susanna S. Epp, Discrete Mathematics with Applications, Metric Version, 2020 Australia, page 254._

_Sample solution in Python_. 

{% highlight python %}

def euclid(a, b):
    while b != 0:
        r = a % b
        if r == 0:
            return b
        else:
            a = b
            b = r
    return

def main():
    a = int(input("Integer a:"))
    b = int(input("Integer b:"))
    print(f"The gcd of {a} and {b} is {euclid(a, b)}.")

if __name__ == "__main__":
    main()
    
{% endhighlight %}

_Output:_ The gcd of 48 and 16 is 16.

[Here](https://github.com/francescomacri/Number_Theory_Into_Code/blob/main/euclidean_algorithm.py) you will find the code snippet in GitHub.