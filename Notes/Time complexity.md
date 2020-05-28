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

















[For more details](https://github.com/Habib0308/Design-Analysis-Of-Algorithms/blob/master/Notes/Asymptotic%20Analysis.md)
