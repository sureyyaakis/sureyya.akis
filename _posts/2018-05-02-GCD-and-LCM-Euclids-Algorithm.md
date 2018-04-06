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

**Modulo operation** 

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


![GCF-LCM-list-method](/assets/img/GCF-LCM-list-method.png)

![GCD](/assets/img/GCD.jpg)

**Euclidean Algorithm**

The Euclidean Algorithm use of by rapidly reducing the problem into easier and easier problems. 

> This algorithm finds GCD by performing repeated division beginning from the two numbers we want to find the GCD of until we get a remainder of 0. 

For example, 24 and 60, below are the steps to find GCD using Euclid's algorithm.

+ Divide the larger number by the small one. In this case we divide 60 by 24 to get a quotient of 2 and remainder of 12.
+ Next we divide the smaller number (i.e. 24) by the remainder from the last division (i.e. 12). So 24 divide by 12, we get a quotient of 2 and remainder of 0.
+ Since we already get a remainder of zero, the last number that we used to divide is the GCD, i.e 12.

Let's look at another example, find GCD of 40 and 64.

64 ÷ 40 = 1 with a remainder of 24
40 ÷ 24 = 1 with a remainder of 16
24 ÷ 16 = 1 with a remainder of 8
16 ÷ 8 = 2 with a remainder of 0.
We stop here since we've already got a remainder of 0. The last number we used to divide is 8 so the GCD of 40 and 64 is 8

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

**What is LCM?**

The least common multiple (LCM) of two numbers is the smallest number (not zero) that is a multiple of both.
Also, you can list the prime factors of each one. For example,

<br /> 3: 3
<br /> 9: 3 x 3
<br /> 21: 3 x 7

Multiply each factor the greatest number of times it occurs in any of the numbers. 9 has two 3's, and 21 has one 7, so we multiply 3 two times, and 7 once. This gives us 63, the smallest number that can be divideed evenly by 3, 9, and 21.

> We check our work by verifying that 63, can be divided evenly by 3, 9, and 21.

First divide all the numbers by the smallest prime that can divide any of them. The smallest prime that divides 24 or 60 is 2. Stop when the numbers cannot divide. The LCM is 2 × 2 × 3 × 2 × 5 = 120

![LCM](/assets/img/LCM.jpg)

> Here is the example of python 3.6

```python
def lcm(x, y):  
  if x > y:
    z = x
  else:
    z = y
  while(True):  
    if(( z%x == 0 )and (z%y == 0)):
      lcm = z
      break
    z+=1  
  return lcm
  
print(lcm(3,7))
print(lcm(11,13))
```
