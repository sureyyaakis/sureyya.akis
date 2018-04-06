---
layout: post
title: "GCD and LCM Euclid’s Algorithm"
date: 2/4/2018
excerpt: "GCD and LCM Euclid’s Algorithm"
tags: [sample post, readability, test]
---
**GCD and LCM Euclid’s Algorithm**
===
**What is GCD** 

+	The greatest common divisor of two integers is the largest integer that can divide both integers
+	The integer 1 has only one divisor, itself. 
+	Any positive integer has at least two divisors, 1 and itself (but it can have more)
+	360 = 2 x 2 x 2 x 3 x 3 x 5
+	42 = 2 x 3 x 7
+	The gcd(360, 42) =  6

**Modulo Operation** 

+	Given two positive numbers, a (the dividend) and b (the divisor), a modulo b (abbreviated as a mod b) is the remainder of Euclidean division of a by b.
+	Ex: “5 mod 2” evaluate t o1 because 5 divided by 2 leaves a quotient of 2 and a remainder of 1, while “9 mod 3” would evaluate to 0 because the division of 9 by 3 has a quotient of 3 and leaves a remainder of 0; there is nothing to subtract from 9 after multiplying 3 times 3.

**Euclid’s Algorithm for Finding GCD**

+	Idea: Given to integers n and m 
-	If n != 0, gcd(m, n) = gcd(n, m mod n);
-	If n = 0, gcd(m,n)= m
+	Euclid’s algorithm for computing gcd(m,n)
-	Step 1: if n=0, return the value of m as the answer and stop; otherwise proceed to Step 2.
-	Step 2: Divide m by n and assign the value of the remainder to r (i.e. r= m %(mod) n).
-	Step 3: Replace m with n and with r (i.e. m = n, n = r  gcd(n,r)). Go to Step 1

>![gcd-lcm](/assets/img/gcd-lcm.png)

> There is a example for python 3.6 

```python
def gcd(a,b): # With subtract 
  
  while(a != b):
    if (a>b):
      a = a-b
    else:
      b = b-a
  return a
  
def nwd(g,d): # recursive func
  while(d!= 0):
    r = g%d
    g=d
    d=r
  return g

print(nwd(360, 42))
print(gcd(360, 42))
```
