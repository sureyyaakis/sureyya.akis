---
layout: post
title: "GCD and LCM Euclid’s Algorithm"
date: 4/2/2018
excerpt: "Mips ve assembly kodları giriş."
tags: [sample post, readability, test]
---
**GCD and LCM Euclid’s Algorithm**
===
When somebody ask what is gcd(36, 60) OR lcm(4, 6)  and you want to answer but you don’t know keep reading to this article.
**WHAT IS GCD**  
The Greatest Common Divisor is moreover known as the greatest common factor (gcf), highest common factor (hcf), greatest common measure (gcm), or highest common divisor, I chose to say GCD.  GCD is the largest number that divides the given numbers. The easy way to find GCD is to factorize both numbers and multiple common factors.

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

Register'lar Neden Var
---
İşlemci birim zamanda sadece bir işlem yapabilir. Örneğin 3 sayıyı toplamasını istediğimizde önce ilk ikisini toplayacak, sonra ara sonucu tekrar ram'e yazacak. Sonra bu ara sonuç ile 3. sayıyı tekrar çağırıp onlarıda toplayacak. Sonra tekrar Ram'e kadar gidi yazacak. Fakat ara sonucu işlemcinin içerisinde tutabilseydik işlemleri daha hızlı gerçekleştirebilirdik. Her işlemden sonra verileri ram'e götürüp yazmak zorunda kalmazdık. Böyle diyerek işlemcinin içerisine registerları eklemişler.

Hangi Register Ne işe Yarar
---

|  Register |  Sayısı |  Açıklama |
|:---|:---:|---:|
| $zero     | 0     | İçerisinde 0 sayısı vardır.  |
|---
| $at       | 1     | Assembler tarafından kullanılır.  |
|---
| $v0-$v1  | 2-3   | Metodların return değişkenleri için. |
|---
| $a0-$a3  | 4-7   | Metodlara gidecek parametreler için. |
|---
| $t0-$t7  | 8-15  | Geçici değişkenler  |
|---
| $s0-$s7  | 16-23 | Kayıt registerları |
|---
| $t8-$t9  | 24-25 | Biraaz daha geçici değişken  |
|---
| $k0-$k1  | 26-27 | İşletim sistemi tarafından kullanılır. |
|---
| $gp      | 28    | Global Pointer  |
|---
| $sp      | 29    | Stack Pointer |
|---
| $fp      | 30    | Frame Pointer  |
|===
| $ra      | 31    | Return Adress |


Örnek Bir Assembly Kodu
---
C dilinde yazılmış `f = (a+b)+(c+d)` işlemini assembly ile yazalım.
(Değişkenler sırasıyla s0,s1,s2,s3,s4 registerlarına getirilmiştir.)
{% highlight ca65 %}
add $t0, $s1, $s2
add $t1, $s3, $s4
add $s0, $t0, $t1
{% endhighlight %}
