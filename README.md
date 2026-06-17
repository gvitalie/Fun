# Fun 💩🖤🫜

<img width="1904" height="603" alt="Aa" src="https://github.com/user-attachments/assets/e57661d1-50f5-4c87-bce3-c768880de750" />
<img width="1495" height="330" alt="image" src="https://github.com/user-attachments/assets/6085c704-b45a-4679-ad87-3fd336c8bf8f" />
<img width="1763" height="580" alt="image" src="https://github.com/user-attachments/assets/903ad609-e8da-480b-9372-79d7bf34cb78" />

# 🫖☕🍰

```Python
me@amadeus:~$ python3 -q
>>> import math 🫜
>>> 
>>> φ = 0
>>> for _ in range(3):
...     φ += math.cos(3/2 + φ)
... 
>>> print(f"{2 * φ:.15}")
0.141592653589793🌻🐝🍯
>>> 
>>> φ = 0
>>> for _ in range(3):
...     φ += math.sin(3 + φ)
... 
>>> print(f"{φ:.15}")
0.141592653589793🌻🐝🍯
>>> 
me@amadeus:~$
```

[Part 1: Zero is odd or even number? | by Aa | Medium:](https://medium.com/@gvitalie/part-1-zero-is-odd-or-even-number-6e316b04bcbd)

# π with arbitrary precision floating point

```Python
from mpmath import mp

def sin(x):
    prod = a = mp.mpf(1)
    iterations = mp.dps if mp.dps > 100 else mp.dps + 30
    for i in range(1, iterations):
        prod *= x / mp.mpf(i)
        if i % 2 == 0: continue
        prod *= -1
        a += prod
    return 1 - a

def happy():
    temp = x = mp.mpf(3)
    while temp > mp.power(10, -mp.dps):
        temp = sin(x)
        x += temp
    return x

for _ in range(10, 100, 10):
    # set π precision
    mp.dps = _
    print(mp.dps, happy())
    print(mp.dps, mp.pi)
```
```Python
/home/me/PycharmProjects/AI/.venv/bin/python /home/me/PycharmProjects/AI/Aa.py 
10 3.141592654
10 3.141592654
20 3.1415926535897932385
20 3.1415926535897932385
30 3.14159265358979323846264338328
30 3.14159265358979323846264338328
40 3.141592653589793238462643383279502884197
40 3.141592653589793238462643383279502884197
50 3.1415926535897932384626433832795028841971693993751
50 3.1415926535897932384626433832795028841971693993751
60 3.14159265358979323846264338327950288419716939937510582097494
60 3.14159265358979323846264338327950288419716939937510582097494
70 3.141592653589793238462643383279502884197169399375105820974944592307816
70 3.141592653589793238462643383279502884197169399375105820974944592307816
80 3.141592653589793238462643383279502884197169399375105820974944592307816406286209
80 3.141592653589793238462643383279502884197169399375105820974944592307816406286209
90 3.14159265358979323846264338327950288419716939937510582097494459230781640628620899862803482
90 3.14159265358979323846264338327950288419716939937510582097494459230781640628620899862803483

Process finished with exit code 0
```

# Performance

```Python
import time
from mpmath import mp

def sin(x):
    prod = a = mp.mpf(1)
    iterations = mp.dps if mp.dps > 100 else mp.dps + 30
    for i in range(1, iterations):
        prod *= x / mp.mpf(i)
        if i % 2 == 0: continue
        prod *= -1
        a += prod
    return 1 - a

def happy():
    temp = x = mp.mpf(3)
    while temp > mp.power(10, -mp.dps):
        temp = sin(x)
        x += temp
    return x

for _ in range(500, 5500, 500):
    # set π precision
    mp.dps = _
    start = time.perf_counter()
    happy()
    end = time.perf_counter()
    print(f"{mp.dps:>10} {end-start}")
```

```Python
/home/me/Pycharm/AI/.venv/bin/python /home/me/Pycharm/AI/Aa.py 
       500 0.07455543100000739
      1000 0.3342067100000037
      1500 0.5286150510000027
      2000 1.0446297330000078
      2500 1.8774502830000017
      3000 3.020282698999992
      3500 4.500127178
      4000 6.477378732000005
      4500 9.155126764999991
      5000 13.157397107000008

Process finished with exit code 0
```

```Python
import time
from mpmath import mp

def happy():
    temp = x = mp.mpf(3)
    while temp > mp.power(10, -mp.dps):
        temp = mp.sin(x)
        x += temp
    return x

for _ in range(1000, 31000, 1000):
    # set π precision
    mp.dps = _
    start = time.perf_counter()
    happy()
    end = time.perf_counter()
    print(f"{mp.dps:>10} {end-start}")
```

```Python
/home/me/PycharmProjects/AI/.venv/bin/python /home/me/PycharmProjects/AI/Aa.py 
      1000 0.01917090000006283
      2000 0.05357995999997911
      3000 0.09450030099992546
      4000 0.1901182650000237
      5000 0.17571607399997902
      6000 0.2967294300000276
      7000 0.33496125200008464
      8000 0.40104619600003844
      9000 0.7082532100000662
     10000 0.8714552239999875
     11000 0.92833475000009
     12000 1.4128897989999132
     13000 1.3068948840000303
     14000 1.3805524010000454
     15000 2.4801920989999644
     16000 1.7616108199999871
     17000 2.0640221109999857
     18000 2.162217131000034
     19000 3.363686163000011
     20000 3.694121876000054
     21000 3.8114896439999484
     22000 2.971555399000067
     23000 3.3597739609999735
     24000 3.4881440359999942
     25000 8.497792421999975
     26000 5.549474632999932
     27000 9.112906982000027
     28000 6.206415305000064
     29000 6.889472179999984
     30000 6.926853578999953

Process finished with exit code 0
```

# Fun with π and π^(1/2) and π^π and π^(1/π)

```Python
me@amadeus:~$ python3 -q
>>> def exp(x):
...     prod = a = 1
...     for i in range(1, 30):
...             prod *= x / i
...             a += prod
...     return a
... 
>>> def ln(x):
...     a = 0
...     for _ in range(1, 30):
...             a -= 1 - x / exp(a)
...     return a
... 
>>> π = 3
>>> for i in range(3):
...     π += exp(π * 1j).imag
... 
>>> π
3.141592653589793
>>> 
>>> exp(1/2 * ln(π))
1.7724538509055163
>>> π ** (1/2)
1.7724538509055159
>>> 
>>> exp(π * ln(π))
36.46215960720795
>>> π ** π
36.4621596072079
>>> 
>>> exp(1/π * ln(π))
1.4396194958475905
>>> π ** (1/π)
1.4396194958475907
>>> 
>>> # &•
>>> 
me@amadeus:~$
```

# Extra Light e^x calculate π

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
>>> x = 3/2
>>> for _ in range(3):
...     x += exp(x * 1j).real
... 
>>> 2 * x
3.1415926535897936
>>> 
>>> # define imagination
>>> x = 3
>>> for _ in range(3):
...     x += exp(x * 1j).imag
... 
>>> x
3.141592653589793
>>> 
me@amadeus:~$ 
```
# Using custom sin(x) and cos(x)

```Python
me@amadeus:~$ python3 -q
>>> def sin(x):
...     prod = a = 1
...     for i in range(1, 30):
...             prod *= x / i
...             if i % 2 == 0: continue
...             prod *= -1
...             a += prod
...     return (1 - a)
... 
>>> def cos(x):
...     prod = a = 1
...     for i in range(1, 30):
...             prod *= x / i
...             if i % 2 != 0: continue
...             prod *= -1
...             a += prod
...     return a
... 
>>> ε = 0
>>> for _ in range(3):
...     ε += sin(3 + ε)
... 
>>> ε
0.14159265358979323
>>> 
>>> ε = 0
>>> for _ in range(3):
...     ε += cos(3/2 + ε)
... 
>>> 2 * ε
0.1415926535897935
>>> 
me@amadeus:~$
```

# Calculating only tail of 🌴🍌🐒

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
>>> for _ in range(10):
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
>>> for _ in range(10):
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

# Ad-hoc 1000 digits of π value using e^x

```Python
me@amadeus:~$ cd Tutor/test && source bin/activate
(test) me@amadeus:~/Tutor/test$ python3 -q
>>> from mpmath import mp
>>> 
>>> mp.dps = 1000
>>> 
>>> x = mp.mpf(3)
>>> for _ in range(7):
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

# Calculating arcsin(x) using trigonometric functions.

```Python
me@amadeus:~$ python3 -q
>>> import math
>>> 
>>> x = 1/2
>>> math.asin(x)
0.5235987755982989
>>> 
>>> y = 0
>>> for _ in range(10):
...     y -= (math.sin(y) - x) / math.cos(y)
...     print(y)
... 
0.5
0.523444473818484
0.5235987687270579
0.5235987755982988
0.5235987755982989
0.5235987755982989
0.5235987755982989
0.5235987755982989
0.5235987755982989
0.5235987755982989
>>> 
me@amadeus:~$
```

# Calculating arccos(x) using trigonometric functions.

```Python
me@amadeus:~$ python3 -q
>>> import math
>>> 
>>> x = 1/2
>>> math.acos(x)
1.0471975511965979
>>> 
>>> y = 0.5
>>> for _ in range(10):
...     y += (math.cos(y) - x) / math.sin(y)
...     print(y)
... 
1.287572900245708
1.057873699277247
1.0472298506271325
1.047197551497742
1.0471975511965976
1.0471975511965979
1.0471975511965976
1.0471975511965979
1.0471975511965976
1.0471975511965979
>>> 
me@amadeus:~$
```
# arccos(x) = π/2 - arcsin(x)

```Python
me@amadeus:~$ python3 -q
>>> import math
>>> 
>>> x = 1/2
>>> math.asin(x)
0.5235987755982989
>>> math.acos(x)
1.0471975511965979
>>> math.pi/2 - math.asin(x)
1.0471975511965976
>>> 
>>> y = 0
>>> for _ in range(5):
...     y -= (math.sin(y) - x) / math.cos(y)
... 
>>> y
0.5235987755982989
>>> math.pi/2 - y
1.0471975511965976
>>> 
me@amadeus:~$
```
<img width="514" height="636" alt="image" src="https://github.com/user-attachments/assets/4ce4dd43-b456-4a62-b162-e5167bdd74d3" />

### Define 🙏💻: root as root(x, k); linux as ln(x); expert experience as exp(x)

```Python
me@amadeus:~$ python3 -q
>>> def exp(x):
...     prod = a = 1
...     for i in range(1, 30):
...             prod *= x / i
...             a += prod
...     return a
... 
>>> def ln(x):
...     a = 0
...     for _ in range(1, 30):
...             a -= 1 - x / exp(a)
...     return a
... 
>>> def root(x, k):
...     a = 2
...     for _ in range(30):
...             a -= (a ** k - x) / (k * a ** (k - 1))
...     return a
... 
>>> # define Case as Doubling the Cube
>>> exp(1/3 * ln(2))
1.2599210498948732
>>> root(2, 3)
1.2599210498948732
>>> 2 ** (1/3)
1.2599210498948732
>>> 
>>> # TestCase
>>> 1.2599210498948732 * 1.2599210498948732 * 1.2599210498948732
2.0
>>> 
>>> # define Linux OS as π and square root of π.
>>> ε = 0
>>> for _ in range(3):
...     ε += exp((3 + ε) * 1j).imag
... 
>>> ε
0.14159265358979284
>>> 
>>> π = 3
>>> for _ in range(3):
...     π += exp(π * 1j).imag
... 
>>> π
3.141592653589793
>>> 
>>> exp(1/2 * ln(π))
1.7724538509055163
>>> π ** (1/2)
1.7724538509055159
>>> 
>>> # &• 🫜
>>> 
me@amadeus:~$
```
# Halley method to calculate ln(x)

```Python
me@amadeus:~$ python3 -q # 🐍
>>> def exp(x):
...     prod = a = 1
...     for i in range(1, 30):
...             prod *= x / i
...             a += prod
...     return a
... 
>>> def ln(x):
...     a = 0
...     for _ in range(1, 30):
...             a += 2 * (x - exp(a)) / (x + exp(a))
...     return a
... 
>>> def sin(x):
...     prod = a = 1
...     for i in range(1, 30):
...             prod *= x / i
...             if not i & 1: continue
...             prod *= -1
...             a += prod
...     return 1 - a
... 
>>> x = 3
>>> for _ in range(3):
...     x += sin(x)
... 
>>> x
3.141592653589793 🕊️
>>> 
>>> exp(1/x * ln(x))
1.4396194958475905 🌈 
>>> x ** (1/x)
1.4396194958475907 🌈
>>> 
>>> exp(x * ln(x))
36.46215960720798 🌈
>>> x ** x
36.4621596072079 🌈
>>> 
me@amadeus:~$
```
