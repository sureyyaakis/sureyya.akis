---
layout: post
title: "GCD and LCM Euclid’s Algorithm"
date: 2/4/2018
excerpt: "Mips ve assembly kodları giriş."
tags: [sample post, readability, test]
---
**GCD and LCM Euclid’s Algorithm**
===
When somebody ask what is gcd(36, 60) OR lcm(4, 6)  and you want to answer but you don’t know keep reading to this article.
**WHAT IS GCD**  
The Greatest Common Divisor is moreover known as the greatest common factor (gcf), highest common factor (hcf), greatest common measure (gcm), or highest common divisor, I chose to say GCD.  GCD is the largest number that divides the given numbers. The easy way to find GCD is to factorize both numbers and multiple common factors.


![GCD](/assets/img/GCD.jpg)

Time Complexity: O(Log min(x, y)) There is a example for python 3.6 

```python
def gcd(x, y):
    gcd = 1
    
    if x % y == 0:
        return y
    
    for k in range(int(y / 2), 0, -1): 
        if x % k == 0 and y % k == 0: # common divisor
            gcd = k
            break  
    return gcd

print(gcd(12, 17))
print(gcd(4, 6))
```

What is LCM?
--- 
The least common multiple (LCM) of two numbers is the smallest number (not zero) that is a multiple of both.

?
---

![LCM](/assets/img/LCM.jpg)
