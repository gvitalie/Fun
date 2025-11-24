# Fun
Fun with π^π and π^(1/π)

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
>>> def exp(x):
...     prod = a = 1
...     for i in range(1, 30):
...             prod *= x/i
...             a += prod
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
