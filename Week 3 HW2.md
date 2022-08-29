# Homework 2

This week we learned about one of the most powerful concepts in all of programming. The `for` and `while` loops are used for so many different things in the world of programming and we will give you a sense of this in this homework. We also cover how to format strings, and use that as a tool for some real world application problems! If you have questions go to office hours (fill out the poll if you haven't already) or ask on the class piazza page.

## Comparison Operators (5 points)
For each of the following expressions below, write the boolean answer that the expression will evaluate to. Double click where it says to put your answer, this will allow you to edit the cell.


```python
a = 7
b = 14
```

`a > b` evaluates to: **[False]**

`a > 0 and b > 0` evaluates to: **[True]**

`a > 0 and b < 0` evaluates to: **[False]**

`a == b` evaluates to: **[False]**

`2*a == b and a < b` evaluates to: **[True]**

`a != b` evaluates to: **[True]**

`a == b or a != -b` evaluates to: **[False]**

`"James" > "Yilun" or "Wendy" > "Yilun"` evaluates to: **[False]**

`"racecar" == "racecar[::-1]` evaluates to: **[True]**

`"a" < "b"` evaluates to: **[True]**

## Operations on Lists (5 Points)

Note: The following cells have to be run in order!


```python
''' Here is a list of the names of everyone in this course! '''

students = ["Caytyn", "Paige", "Victoria", "Riley", "Victor", "Oski",
            "Kingsley", "Geo", "Emmanuel","Carol Christ", "Joshua", "Lyla",
            "Nadia","Camden","Mey", "Sebastian", "Esther","Chloe"]
```


```python
''' What is the length of this list? '''
print (students)
print ( "length of list=",len(students))
```

    ['Caytyn', 'Paige', 'Victoria', 'Riley', 'Victor', 'Oski', 'Kingsley', 'Geo', 'Emmanuel', 'Carol Christ', 'Joshua', 'Lyla', 'Nadia', 'Camden', 'Mey', 'Sebastian', 'Esther', 'Chloe']
    length of list= 18



```python
'''Oops, we forgot the facilitators. Can you create a new list for faciliators and append it to the original list?'''
Facilitators = ["James, Yilun, Wendy"]
students.append(Facilitators)
print(students)

```

    ['Caytyn', 'Paige', 'Victoria', 'Riley', 'Victor', 'Oski', 'Kingsley', 'Geo', 'Emmanuel', 'Carol Christ', 'Joshua', 'Lyla', 'Nadia', 'Camden', 'Mey', 'Sebastian', 'Esther', 'Chloe', ['James, Yilun, Wendy']]



```python
''' I think I also put in a couple people that aren't students by accident.
Can you remove Carol Christ and Oski from the list? '''

students.remove(("Oski") and ("Carol Christ"))

print(students)
```

    ['Caytyn', 'Paige', 'Victoria', 'Riley', 'Victor', 'Kingsley', 'Geo', 'Emmanuel', 'Joshua', 'Lyla', 'Nadia', 'Camden', 'Mey', 'Sebastian', 'Esther', 'Chloe', ['James, Yilun, Wendy']]



```python
'''Now can you give me a new list with only people who's names start with a V. 
This might be a little challenging'''
new_students=[]
for i in students :
    if i[0]=="V":
        new_students.append(i)

print(new_students)


```

    ['Victoria', 'Victor']


## Conditional + Iterative Problems (40 Points)

### <span style="color:red">Absolute</span>ly  Magnificent (5 Points)

Write your own version of an absolute value function. Where it takes in a number a and returns the absolute value of a. You are not allowed to use the built in `abs` function discussed in lecture. 


```python
import math
def my_absolute(a):
    y=(a)**2
    sqrt=math.sqrt(y)
    return sqrt
my_absolute(-2)

    ##"""Return abs(a), but without calling abs.
    ##>>> my_absolute(2)
    ##2
    ##>>> my_absolute(-2)
    ##3
    ##"""

```




    2.0



### Huh. That's Odd... (5 Points)


```python
def is_odd(num):
    if (num%2) == 1:
        print (True)
    else: 
        print (False)
is_odd(-7)

```

    True



```python

def select_odd(a,b,c):
    if (a%2)!=0: 
        print(a)
    else:
        print([])
    if (b%2)!=0: 
        print(b)
    else: 
        print([])
    if (c%2)!=0: 
        print(c)
    else: 
        print([])
select_odd(6,4,5)
    ## '''Returns a new list with only the numbers that are odd in the numbers list. >> select_odd([2, 3, 7, 10])
    ## [3, 7]
    ## >>> select_odd([2, 4, 6, 8]) [] '''
```

    []
    []
    5


### Prime Numbers (10 Points)

[Adapted from Ayars, Problem 1-6] Write a function called `is_prime(n)` that determines whether a number `n` is prime or not, and returns either `True` or `False` accordingly. You can assume that the argument `n` passed to any of your functions will be an integer. Remember to include descriptive doc strings for each function your write!

    def is_prime(n):
        """ Determines if n is prime or not. Takes an integer n.
        Returns True if n is prime, and False otherwise. """
        # Your code here!
        
        
Remember to try various test cases: What if the argument passed to `is_prime` is ...
- 20
- 2
- 1
- 0
- negative


```python
n = ()
def is_prime(n):
    if n < 2: 
        print (False)
    elif n==2:
        print (True)
    if (n % 2) != 0:
            print (True) 
    elif (n % 2) == 0: print (False)
is_prime(6)       
```

    False



```python
is_prime(7)
```

    True


### Fibonacci Sequence (10 Points)
The Fibonacci sequence is a sequence of integers defined by the following relation. The $n$-th integer $a_n$ is defined in terms of previous integers of the sequence as

$$a_n = a_{n-1} + a_{n-2}$$

and $a_0 = 0$ and $a_1 = 1$. So the first few numbers are 0, 1, 1, 2, 3, 5, 8, 13, 21, .... Write a program to print the Fibonacci series from 0 to 50. Expected output:
    
    0 1 1 2 3 5 8 13 21 34
Hint 1: Two (or more) variables can be assigned simultaneously. For instance, to swap the values of `a` and `b`, you can write `a, b = b, a`.

Hint 2: Try doing so using a while or a for loop. If you feel ambitious you can try doing this recursively but that is not required. If you do code this recursively you will see how much prettier recursion can be and is often why computer scientists like to use it.


```python
def while_fib (last, curr): 
    last, curr = 0,1
    while last < 50 : 
        print(last)
        first = last + curr
        last = curr
        curr = first
while_fib(0,1)
```

    0
    1
    1
    2
    3
    5
    8
    13
    21
    34


### Pyramid Building (10 Points)

Write a Python program to construct the following pattern, using a nested `for` loop (or maybe two nested `for` loops).

    * 
    * * 
    * * * 
    * * * * 
    * * * * * 
    * * * * 
    * * * 
    * * 
    *
Hints: You can multiply strings by numbers to have them repeat multiple times!

Also, some solutions to exercise this might use a `range()` going backwards. You can make `range()` go backwards using syntax like this: `range(20,10,-1)`.


```python
def pattern (x): 
    mylist = []
    for i in range (1, x+1 ):
        mylist.append("* "*i)
    print("\n".join(mylist))
    for j in range (-1, -x+1,):
        mylist.append("* "*j)
    print("\n".join(mylist))
x=10 
pattern(x) 
    # I was unsure of how to do the downward portion of the pyramid 
```

    * 
    * * 
    * * * 
    * * * * 
    * * * * * 
    * * * * * * 
    * * * * * * * 
    * * * * * * * * 
    * * * * * * * * * 
    * * * * * * * * * * 
    * 
    * * 
    * * * 
    * * * * 
    * * * * * 
    * * * * * * 
    * * * * * * * 
    * * * * * * * * 
    * * * * * * * * * 
    * * * * * * * * * * 


## How to Format Strings

We did not get the chance to cover this in lecture, but in scientific computing it is often extremeley valuable to print your results out in a way that the average reader could understand. We will be looking at the `.format` method which will help you in some of the problems above.

`print("blah blah {0:2.1f} stuff and blah blah {1:2.1f} other stuff more blahs".format(stuff1, stuff2))`

The above line of code is how we can place well formatted values into a long sentence in python when we want to print it out. You will notice right away the curly braces. The first number inside is the index of the `.format` tuple at the very end of the string (How you put multiple variables into the string). The second number refers to how much white space you would like between the words and your value. The third number is the number of sig figs past the decimal you would like. Below are some examples of how this works in practice.


```python
mass = 7.23872193 #kg
height = 1.4 #meters

print("My mass would be {0:2.1f} kg and my height would be {1:2.1f} meters".format(mass, height))
print("My mass would be {0:2.3f} kg and my height would be {1:2.3f} meters".format(mass, height))
print("My mass would be {0:2.6f} kg and my height would be {1:2.6f} meters".format(mass, height))

print('\n') #prints a new line for neatness

print("My mass would be {0:10.2f} kg".format(mass))
print("My mass would be {0:5.2f} kg".format(mass))
print("My mass would be {0:1.2f} kg".format(mass))
```

    My mass would be 7.2 kg and my height would be 1.4 meters
    My mass would be 7.239 kg and my height would be 1.400 meters
    My mass would be 7.238722 kg and my height would be 1.400000 meters
    
    
    My mass would be       7.24 kg
    My mass would be  7.24 kg
    My mass would be 7.24 kg


## Real World Application Problems (30 Points) 

### Satellite Altitudes (15 Points)

[Adapted from Newman, Exercise 2.2 and Physics 77] A satellite is to be launched into a circular orbit around the Earth so that it orbits the planet once every $T$ seconds. The altitude $h$ above the Earth's surface that the satellite must have is $$ h = \left( \frac{G M T^2}{4 \pi^2} \right)^{1/3} - R, $$ where $G = 6.67 \times 10^{-11}~\text{m}^3~\text{kg}^{-1}~\text{s}^{-2}$ is Newton's gravitational constant, $M = 5.97 \times 10^{24}~\text{kg}$ is the mass of the Earth, and $R = 6371~\text{km}$ is its radius.

**1a.** Write a program that, for a given value of $T$ (entered as a variable T in a cell), calculates and prints out the correct altitude in meters, kilometers, and miles, with one decimal place for each result.

*Output for 1a*: When the code cell for this part of the problem is entered, it should specify (in the comments or the Markdown cell above) what units of $T$ are assumed. The program should print out the correct altitude in meters, kilometers, and miles, with one decimal place for each result.


```python
import math
def time (T): # T is in minutes
    G = 6.67*10**-11 # m**3*kg**-1*s**-2
    M = 5.97*10**24 # kg
    R = 6371 #km
    h = ((G*M*T**2)/4*(math.pi)**2) - R
    meters = h / 1000
    kilometers = h 
    miles = h * 0.621371
    print ("The altitude would be {0:1.1f} in meters, {1:1.1f} in kilometers, and {2:1.1f} in miles".format(meters, kilometers, miles) )
    return h
time(4)         
```

    The altitude would be 15720266411631.2 in meters, 15720266411631152.0 in kilometers, and 9768117660461660.0 in miles





    1.5720266411631152e+16



*Output for 1b:* Use code cells to carry out the desired calculations, and Markdown cells to present and discuss your results. To create a new cell go to the top menu and click `Insert` then `Insert Cell` either above or below the cell you currently have selected

**1b.** Use your program to calculate the altitudes of satellites that orbit the Earth once a day (so-called "geosynchronous" orbit), once every 90 minutes, and once every 45 minutes. What do you conclude from the last of these calculations?


```python
time(90)

time(45)
    # From these calculations, I can conclude that as time increases; so does the height of the satellite relative to earth.
```

    The altitude would be 7958384870891489.0 in meters, 7958384870891489280.0 in kilometers, and 4945109565610715136.0 in miles
    The altitude would be 1989596217722867.5 in meters, 1989596217722867456.0 in kilometers, and 1236277391402675968.0 in miles





    1.9895962177228675e+18



### Perfect Hardboiled Eggs (15 points)

[Adapted from Langtangen, Exercise 1.12 and Physics 77. You may derive the formula in Physics 112 or Physics 89] As an egg cooks, the proteins first denature and then coagulate. When the temperature exceeds a critical point, reactions begin and proceed faster as the temperature increases. In the egg white the proteins start to coagulate for temperatures above 63 C, while in the  yolk the proteins start to coagulate for temperatures above 70 C. For a soft boiled egg, the white needs to have been heated long enough to coagulate at a temperature above 63 C, but the yolk should not be heated above 70 C. For a hard boiled egg, the center of the yolk should be allowed to reach 70 C.

The following formula expresses the time $t$ it takes (in seconds) for the center of the yolk to reach the temperature $T_y$ (in Celsius degrees): $$ t = \frac{M^{2/3} c \rho^{1/3}}{K \pi^2 (4\pi/3)^{2/3}} \ln \left[ 0.76 \frac{T_0 - T_w}{T_y - T_w} \right] . $$ Here, $M$, $\rho$, $c$, and $K$ are properties of the egg:
* $M$ is the mass,
* $\rho$ is the density,
* $c$ is the specific heat capacity, and 
* $K$ is the thermal conductivity.

Relevant values are
* $M = 64~\text{g}$ for a large egg (USA size XL: en.wikipedia.org/wiki/Chicken_egg_sizes),
* $\rho = 1.0378~\text{g cm}^{-3}$,
* $c = 3.7~\text{J g}^{-1}\,\text{K}^{-1}$, and
* $K = 5.4 \cdot 10^{-3}~\text{W cm}^{-1}\,\text{K}^{-1}$.

Furthermore,
* $T_w$ is the temperature (in C degrees) of the boiling water, and
* $T_0$ is the original temperature (in C degrees) of the egg before being put in the water.

Suppose we want our eggs hard-boiled. Implement the formula in a program, set $T_w = 100~\text{C}$ and $T_y = 70~\text{C}$, and compute $t$ for a large egg taken from the fridge ($T_0 = 4~\text{C}$) and from room temperature ($T_0 = 20~\text{C}$). Also compute the results for a small egg ($M = 42~\text{g}$).

*Output for 2:*
When you run your code cell, it should produce the following text, with your numbers instead of the `TTT`, `MMM`, and `SSS` placeholders:

    To hard-boil a large egg taken directly from the fridge, cook it for TTT minutes (MMM min, SSS sec).
    To hard-boil a small egg taken directly from the fridge, cook it for TTT minutes (MMM min, SSS sec).
    To hard-boil a large egg starting from room temperature, cook it for TTT minutes (MMM min, SSS sec).
    To hard-boil a small egg starting from room temperature, cook it for TTT minutes (MMM min, SSS sec).

The `TTT` placeholders should be values in minutes to two decimal places. The `MMM` and `SSS` placeholders should be rounded to the nearest minute/second, with no decimal places. For example,

    To hard-boil a large egg taken directly from the fridge, cook it for 56.78 minutes (56 min 47 sec).
    

#### Hints

Writing the entire formula in one line is difficult to type, difficult to read, difficult to debug---and you have to retype the entire calculation just to change one piece of it. Try breaking it down in smaller chunks assigned to variables, and combine those chunks to produce the final result.

Beware of integer division!

Remember to comment your code and use descriptive variable names so others (and future you) can understand what you're doing!


```python
import math
from numpy import log as ln
def time_egg(M): # mass measured in grams 
    p = 1.0378 # density is measured in g*(cm**-3) 
    c = 3.7 # specific heat capacity is measured in J*(g**-1)*(K**-1)
    K = 5.4*10**-3 # thermal conductivity is measured in W*(cm**-1)*(K**-1)
    T_o = 4 # fridge temperature measured in degrees celsius 
    T_w = 100 # temperature of boiling water; in degrees celsius
    T_y = 70 # temperature of yold; in degrees celsius 
    t = ((M**2/3)*c*(p**1/3)/K*((math.pi)**2)*((4*(math.pi))/3)**2/3)*ln(.76*((T_o - T_w)/(T_y - T_w)))
    min = t
    print ("To hardboil a large egg taken from the fridge, cook it for time_egg minutes (MMM min, SSS sec)")
    print ("To hardboil a small egg taken directly from the fridge, cook it for time_egg minutes (MMM min, SSS sec)")
    return t
time_egg(64)

time_egg(42)
```

    To hardboil a large egg taken from the fridge, cook it for time_egg minutes (MMM min, SSS sec)
    To hardboil a small egg taken directly from the fridge, cook it for time_egg minutes (MMM min, SSS sec)
    To hardboil a large egg taken from the fridge, cook it for time_egg minutes (MMM min, SSS sec)
    To hardboil a small egg taken directly from the fridge, cook it for time_egg minutes (MMM min, SSS sec)





    7149825.054522663




```python

```
