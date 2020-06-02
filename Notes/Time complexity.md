# Chapter 2: Time Complexity


## Calculation rules
We use Big-Oh(O) notation. Where the variable **n** denotes the input size of a variable. For different variable inputs we use different names.
### Loops
#### One loop O(n)
**Adding elements of list by condition**
```python
# List of numbers
numbers = [6, 5, 3, 8, 4, 2, 5, 4, 11] 			#n elements
sum = 0						# O(1)

for val in numbers:				# O(n)
	if val%2==0				# O(1)
        sum = sum+val				# O(1)

print("The sum is", sum)			# O(1)
```
In this code the loop is iterating over the list linearly of size n. so the running time complexity will be:
```
O(1)+O(n)+O(1)+O(1)+O(1)
= O(1+n+1+1+1)
= O(4+n)
= O(n)
```
### Complexity classes
Some common time complexities of algorithms:
#### O(1)
A typical constant-time algorithm is a direct formula that calculates the answer.
#### O(logn)
A logarithmic algorithm often halves the input size at each step.
#### O(\sqrt{k})
A square root algorithm is slower than O(logn) but faster than O(n).
#### O(n)
A linear algorithm goes through the input a constant number of times.
#### O(nlogn)
This time complexity often indicates that the algorithm sorts the input.
#### O(nlogn)
This time complexity often indicates that the algorithm sorts the input, because the time complexity of efficient sorting algorithms is O(nlogn).

Another possibility is that the algorithm uses a data structure where each operation takes O(logn) time.
#### O(n<sup>2</sup>)
A quadratic algorithm often contains two nested loops.
#### O(n<sup>3</sup>)
A cubic algorithm often contains three nested loops.
#### O(2<sup>n</sup>)
This time complexity often indicates that the algorithm iterates through all subsets of the input elements. For example, the subsets of {1,2,3} are ;,
```
{1}, {2}, {3}, {1,2}, {1,3}, {2,3} and {1,2,3}.
```
#### O(n!)
This time complexity often indicates that the algorithm iterates through all permutations of the input elements. 

For example, the permutations of
```
{1,2,3} are (1,2,3), (1,3,2), (2,1,3), (2,3,1), (3,1,2) and (3,2,1).
```
















#### Two Nested Loops ```O(n<sup>2</sup>)```
```python
for a in range(n):			# O(n)
    for b in range(n):			# O(n)
        print("Doing anything")		# O(1)
```
```
O(n)*O(n)
O(n*n)
O(n<sup>2</sup>)
```

#### Three Nested Loops ```O(n<sup>3</sup>)```
```python
for a in range(n):			# O(n)
    for b in range(n):			# O(n)
        for c in range(n):		# O(n)
	    print("Doing anything")     # O(1)
```
```
O(n)*O(n)*O(n)
O(n*n*n)
O(n<sup>3</sup>)
```

#### **K** Nested Loops ```O(n<sup>k</sup>)```
```python
for a in range(n):			# O(n)
    for b in range(n):			# O(n)
        for c in range(n):		# O(n)
            for c in range(n):		# O(n)
                for c in range(n):		# O(n)
                    for c in range(n):		# O(n)
                        .....................
	                      print("Doing anything")     # O(1)
```
```
O(n)*O(n)*O(n)*......O(n)     k numbers of nested loops
O(n*n*n.....n)
O(n<sup>k</sup>)
```

### Order of magnitude
* Don't count steps
* Ignore constants
### Phases
Ignore lower order terms

For example:
```
code consists of three phases with time complexities
O(n), O(n<sup>2</sup>) and O(n). Thus, the total time complexity is O(n<sup>2</sup>).
```
### Several variables
Different Inputs are represented differently.
```
def func(arrA, arrB):
    coun=0
    for a in arrA:
        for b in arrB:
            if a==b:
                count+=1
     return count
```
This algorithm has O(a\*b) complexity

### Recursion
The time complexity of a recursive function depends on the number of times the function is called multiplied by the time complexity of a single call.
#### Example 1:
```
def f(n):
    if (n == 1):
        return 0
    f(n-1)
```
The call f(n) causes n function calls, and the time complexity of each call is O(1). Thus, the total time complexity is O(n).
#### Example 2:
```
def f(n):
    if (n == 1):
        return 0
    f(n-1)
    f(n-1)
```
For each call two function calls are envoked. It's similar to the image below, consider each node to be a function call..

![binary tree](https://i.stack.imgur.com/x8d4D.png)

|function call|number of calls|
|-------------|-------------|
|g(n)|1|
|g(n−1)|2|
|g(n−2)|4|
|···|···|
|g(1)|2<sup>n−1</sup>|

Based on this, the time complexity is
1+2+4+··· +2n−1 = 2<sup>n−1</sup> = O(2<sup>n</sup>).

### Estimating efficiency
we can try to guess the required time complexity of the algorithm that solves the problem. The following table contains some useful estimates assuming a time limit of one second.

|input size|required time complexity|
|--------|--------|
|n ≤ 10|O(n!)|
|n ≤ 20|O(2<sup>n</sup>)|
|n ≤ 500|O(n<sup>3</sup>)|
|n ≤ 5000|O(n<sup>2</sup>)|
|n ≤ 10<sup>6</sup>|O(nlogn) or O(n)|
|n is large|O(1) or O(logn)|

### Maximum subarray sum
This section discusses a classic problem that has a straightforward O(n<sup>3</sup>) solution. However, by designing a better algorithm, it is possible to solve the problem in O(n<sup>2</sup>) time and even in O(n) time.
#### Problem:
Find a sub array with maximum sum.
#### Brute force sollution.
Find all available sollutions and pick the one.
```
best = 0
for i in arr:
    for j in arr:
        sum = 0
        for k in arr:
            sum += k
        best = max(best, sum)
```
**O(n<sup>3</sup>)** complexity

```
best = 0
for i in arr:
    sum = 0
    for j in arr:
        sum += j
        best = max(best, sum)
```
**O(n<sup>2</sup>)** complexity

```
best, sum = 0, 0
for i in arr:
    sum = max(i, sum + i)
    best = max(best, sum)
print(best)
```
**O(n)** complexity






























[For more details](https://github.com/Habib0308/Design-Analysis-Of-Algorithms/blob/master/Notes/Asymptotic%20Analysis.md)
