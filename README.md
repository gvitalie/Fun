# Fun

# 🇺🇦😇🇷🇺

<img width="1681" height="670" alt="image" src="https://github.com/user-attachments/assets/71147ae1-50c7-473b-988b-a90cd4d57a06" />
<img width="1495" height="330" alt="image" src="https://github.com/user-attachments/assets/6085c704-b45a-4679-ad87-3fd336c8bf8f" />
<img width="1763" height="580" alt="image" src="https://github.com/user-attachments/assets/903ad609-e8da-480b-9372-79d7bf34cb78" />

# 🫖☕🍰🐣

```Python
me@amadeus:~$ python3 -q
>>> import math
>>> 
>>> φ = 0
>>> for i in range(3):
...     φ += math.sin(3 + φ)
... 
>>> φ
0.141592653589793🌻🐝🍯
>>> 
me@amadeus:~$
```

[Part 1: Zero is odd or even number? | by Aa | Medium:](https://medium.com/@gvitalie/part-1-zero-is-odd-or-even-number-6e316b04bcbd)

# Fun with π^π and π^(1/π)

```Python
me@amadeus:~$ python3 -q
>>> import math
>>> 
>>> def exp(x):
...     a = 1
...     for i in range(1, 100):
...             a += (x ** i) / math.factorial(i)
...     return a
... 
>>> def ln(x):
...     a = 0
...     for i in range(100):
...             a += 2 * (x - exp(a)) / (x + exp(a))
...     return a
... 
>>> x = 3
>>> for i in range(3):
...     x += math.sin(x)
... 
>>> x
3.141592653589793
>>> x/math.pi
1.0
>>> 
>>> exp(x * ln(x))
36.46215960720795
>>> math.exp(math.pi * math.log(math.pi))
36.4621596072079
>>> 
>>> exp(1/x * ln(x))
1.4396194958475905
>>> math.exp(1/math.pi * math.log(math.pi))
1.4396194958475907
>>> 
>>> # &•
>>> 
me@amadeus:~$ 
```

# π using e^x

```Python
me@amadeus:~$ python3 -q
>>> import math
>>> 
>>> def exp(x):
...     a = 1
...     for i in range(1, 30):
...             a += (x ** i) / math.factorial(i)
...     return a
... 
>>> x = 3
>>> for i in range(3):
...     x += exp(x * 1j).imag
... 
>>> x
3.141592653589793
>>> 
me@amadeus:~$
```
# Extra Light

```Python
me@amadeus:~$ python3 -q
>>> # define experience
>>> def exp(x):
...     prod = a = 1
...     for i in range(1, 30):
...             prod *= x / i
...             a += prod
...     return a
... 
>>> # define reality
>>> x = 1.5
>>> for i in range(3):
...     x += exp(x * 1j).real
... 
>>> 2 * x
3.1415926535897936
>>> 
>>> # define imagination
>>> x = 3
>>> for i in range(3):
...     x += exp(x * 1j).imag
... 
>>> x
3.141592653589793
>>> 
me@amadeus:~$ 
```
# Using custom sin(x)

```Python
me@amadeus:~$ python3 -q
>>> def sin(x):
...     prod = 1; a = 0
...     for i in range(1, 30):
...             prod *= x/i
...             if i % 2 == 0: continue
...             a += prod
...             prod *= -1
...     return a
... 
>>> x = 3
>>> for i in range(3):
...     x += sin(x)
... 
>>> x
3.141592653589793
>>> 
me@amadeus:~$
```
# Using custom cos(x)

```Python
me@amadeus:~$ python3 -q
>>> def cos(x):
...     prod = a = 1
...     for i in range(1, 30):
...             prod *= x/i
...             if i % 2 != 0: continue
...             prod *= -1
...             a += prod
...     return a
... 
>>> x = 1.5
>>> for i in range(3):
...     x += cos(x)
... 
>>> 2 * x
3.1415926535897936
>>> 
me@amadeus:~$
```
# Ad-hoc 1000 digits of π value using e^x

```Python
me@amadeus:~$ cd Tutor/test && source bin/activate
(test) me@amadeus:~/Tutor/test$ python3 -q
>>> from mpmath import mp
>>> 
>>> mp.dps = 1000
>>> 
>>> x = mp.mpf(3)
>>> for i in range(7):
...     x += mp.exp(mp.mpc(0, x)).imag
... 
>>> print(x/mp.pi)
1.0
>>> print(x)
3.141592653589793238462643383279502884197169399375105820974944592307816406286208998628034825342117067982148086513282306647093844609550582231725359408128481117450284102701938521105559644622948954930381964428810975665933446128475648233786783165271201909145648566923460348610454326648213393607260249141273724587006606315588174881520920962829254091715364367892590360011330530548820466521384146951941511609433057270365759591953092186117381932611793105118548074462379962749567351885752724891227938183011949129833673362440656643086021394946395224737190702179860943702770539217176293176752384674818467669405132000568127145263560827785771342757789609173637178721468440901224953430146549585371050792279689258923542019956112129021960864034418159813629774771309960518707211349999998372978049951059731732816096318595024459455346908302642522308253344685035261931188171010003137838752886587533208381420617177669147303598253490428755468731159562863882353787593751957781857780532171226806613001927876611195909216420199
>>> 
(test) me@amadeus:~/Tutor/test$
```

[mpmath - Python library for arbitrary-precision floating-point arithmetic: https://mpmath.org/](https://mpmath.org/)

# Calculating only tail of 🍌🐒

```Python
me@amadeus:~$ python3 -q
>>> def exp(x):
...     prod = a = 1
...     for i in range(1, 30):
...             prod *= x/i
...             a += prod
...     return a
... 
>>> x = 0
>>> for i in range(10):
...     x += exp((x + 3) * 1j).imag
...     print(x)
... 
0.14112000805986716
0.1415926535721955
0.14159265358979284
0.1415926535897932
0.14159265358979353
0.14159265358979342
0.1415926535897933
0.14159265358979364
0.14159265358979353
0.14159265358979342
>>> 
me@amadeus:~$
```
# Just for fun easy 50 digits of π tail only.

```Python
(test) me@amadeus:~/Tutor/test$ python3 -q
>>> from mpmath import mp
>>> 
>>> mp.dps = 50
>>> 
>>> x = mp.mpf(0)
>>> for i in range(10):
...     x += mp.exp(mp.mpc(0, (x + 3))).imag
...     print(x)
... 
0.14112000805986722210074480280811027984693326425227
0.141592653572195558734888568140879746742992817215
0.14159265358979323846264338327950197592715245722096
0.14159265358979323846264338327950288419716939937511
0.14159265358979323846264338327950288419716939937511
0.1415926535897932384626433832795028841971693993751
0.1415926535897932384626433832795028841971693993751
0.14159265358979323846264338327950288419716939937511
0.14159265358979323846264338327950288419716939937511
0.14159265358979323846264338327950288419716939937511
>>> print(mp.pi - 3)
0.14159265358979323846264338327950288419716939937511
>>> 
(test) me@amadeus:~/Tutor/test$
```
