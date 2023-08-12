---
layout: post
author: Francesco Macrì
categories: Number_Theory
meta: "Python"
---

In this algorithm the input is a nonnegative integer $a$. The aim of this algorithm is to produce a sequence of binary digits $r[0],r[1],r[2], \dots , r[k]$ so that the binary representation of $n$ is: 

$$ a = 2^{k} \cdot r[k] + 2^{k-1} \cdot r[k-1] + \cdots + 2^{2} \cdot r[2] + 2^{1} \cdot r[1] + 2^{0} \cdot r[0].$$

(*From: Susanna S. Epp, Discrete Mathematics with Applications, Metric Version, 2020 Australia, pages 272-273.*)

*Sample solution in Python*:

```python
n = []

def decimal_to_binary_list(a):
    while a != 0:
        r = a % 2
        n.append(r)
        a = a // 2
    return n


def reverse_list_to_integer(n):
    reversed_string = "".join(str(element) for element in n[::-1])
    transformed = int(reversed_string)
    return transformed


def main():
    a = int(
        input("Please insert the decimal number you want to transform into binary: ")
    )
    print(
        f"{a} in binary notation is {reverse_list_to_integer(decimal_to_binary_list(a))}."
    )


if __name__ == "__main__":
    main()
```

_Output:_ 20 in binary notation is 10100.

<a href="https://github.com/francescomacri/Number_Theory_Into_Code/blob/main/decimal_to_binary.py" target="_blank">Here</a> you will find the code snippet in GitHub.

## Variation: Converting from decimal to hexadecimal

The same algorithm can be used with a different base in order to convert decimal numbers into numbers with other bases, for example into a hexadecimal number.

*Sample solution in Python:*

```python
def decimal_to_hexadecimal(decimal):
    if decimal == 0:
        return "0"

    hexadecimal = ""
    while decimal > 0:
        remainder = decimal % 16
        if remainder < 10:
            hexadecimal = str(remainder) + hexadecimal
        else:
            hexadecimal = chr(65 + remainder - 10) + hexadecimal
        decimal //= 16

    return hexadecimal


def main():
    a = int(
        input(
            "Please insert the decimal number you want to transform into hexadecimal: "
        )
    )
    print(f"{a} in hexadecimal notation is {decimal_to_hexadecimal(a)}.")


if __name__ == "__main__":
    main()
```


_Output:_ 287 in hexadecimal notation is 11F.

<a href="https://github.com/francescomacri/Number_Theory_Into_Code/blob/main/decimal_to_hexadecimal.py" target="_blank">Here</a> will find the code snippet in GitHub.