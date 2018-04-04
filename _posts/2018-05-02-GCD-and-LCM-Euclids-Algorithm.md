---
layout: post
title: "GCD and LCM Euclid’s Algorithm"
date: 2/4/2018
excerpt: "GCD and LCM Euclid’s Algorithm"
tags: [sample post, readability, test]
---
**GCD and LCM Euclid’s Algorithm**
===
<figure>
	<a href="https://1.bp.blogspot.com/-h-prblk_jS4/V42nOJiYdVI/AAAAAAAAGp4/6UslrxeQ-tA020ksRbz0UQSiCMOpywWlwCLcB/s1600/Euclids%2Balgorihtm%2Bto%2Bfind%2BGCD.jpg"><img src="http://farm9.staticflickr.com/8426/7758832526_cc8f681e48_c.jpg"></a>
</figure>

![GCF-LCM-list-method](/assets/img/GCF-LCM-list-method.png)

When somebody ask what is gcd(36, 60) OR lcm(4, 6) and you want to answer but you don’t know, keep reading to this post.

**What is GCD** 

The Greatest Common Divisor is moreover known as the greatest common factor (gcf), highest common factor (hcf), greatest common measure (gcm), or highest common divisor, I chose to say GCD. GCD is the largest number that divides the given numbers. The easy way to find GCD is to factorize both numbers and multiple common factors.

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
#Time Complexity: O(Log min(x, y))

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
