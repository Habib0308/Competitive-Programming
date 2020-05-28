# Chapter 1
Competitive programming combines two topics: 
1. The design of algorithms
2. The implementation of algorithms

Getting Familiar with python
## Input & Output
The input for the program usually consists of numbers and strings that are separated with spaces and newlines. 

For example for the following input:
```123 456 9254```
```
# Input -> 10 20 monkey
a, b, c = input().split(' ')
print(a, b, c)

# Input with map -> 10 20
a, b = map(int, input().split(' '))
print(a, b)
```
## Working with numbers
### Integers
Python has dynamic data type so integers, float are same as variables.

Integers are very easily handled for input and output It doesn't matte rif value is either long or short.

### Floating point numbers
The required precision of the answer is usually given in the problem statement.
#### Decimal point placing
For example, the following code prints the value of x with 9 decimal places:
```
print("{:.2f}".format(x))
```
#### Comparing Floating point numbers
the numbers can be compared as follows (e = 10<sup>−9</sup>)
```
if (abs(a-b) < 1e-9):
    // a and b are equal
```
## Shortening code
* List Comprihentions
* Lambda expressions

## Mathematics
### Sum Formulas
![sum formula](https://github.com/Habib0308/Competitive-Programming/blob/master/images/sum%20formula.png)
```
## Sum Formulas -> 1 + 2 + 3 ... n = n(n+1)/2
## Sum Formulas -> 1^k + 2^k + 3^k ... n^k = n(n+1)(2n+1)/6	
```
### arithmetic progression
The difference between any two consecutive numbers is constant. For example:

3,7,11,15
```
## AP -> a + .. + b = n(a+b)/2
```
Where a is the first number, b is the last number and n is the amount of numbers.
### geometric progression
A sequence of numbers where the ratio between any two consecutive numbers is constant. For example:

3,6,12,24
```
## GP -> a + ak + ak^2 + .. + b = (bk -a) / (k - 1)
```
Where a is the first number, b is the last number and the ratio between consecutive numbers is k.

### harmonic sum
![harmonic Sum](https://github.com/Habib0308/Competitive-Programming/blob/master/images/harmonic%20sum.png)


### Sets
```
x = set([2, 4, 7])
a = set([1, 2, 5])
b = set([2, 4])
```
#### intersection
Common terms
```
print(a.intersection(b))
```
#### union
```
print(a.union(b))
```
#### difference
elements that are in A but not in B.
```
print(a.difference(b))
```
### Logic
#### NOT
Opposite of Input
#### OR
Anyone is True then True
#### AND
All Must be True for answer to be True

#### Imply
If A is "True" then B is "True"

So if A is False and B is also False then True

![imply gate](https://upload.wikimedia.org/wikipedia/commons/c/cc/IMPLY_ANSI.svg)
#### XNOR
If and only if one is True and the other is False then True

![XNOR](https://upload.wikimedia.org/wikipedia/commons/thumb/f/f8/XNOR_using_NOR.svg/1280px-XNOR_using_NOR.svg.png)

### Functions
#### Round up
```
import math
math.ceil(5.1111)
>>> 6
```
#### Round down
```
import math
math.floor(5.1111)
>>> 5
```
#### min and max
```
print(min([1, 2, 3]))
print(max([1, 2, 3]))
```
#### Logarithms
A useful property of logarithms is that log<sub>k</sub>(x) equals the number of times we have to divide x by k before we reach the number 1.
```
import math
math.log(a,Base)
```

Some other articles to read

[20-simple-python-performance-tuning-tips](https://stackify.com/20-simple-python-performance-tuning-tips/)
