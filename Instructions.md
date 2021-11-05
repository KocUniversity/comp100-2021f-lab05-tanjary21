## Python Tuples
Tuples are used for grouping data.
​
### Tuple assignment: Packing/Unpacking

Write a function that returns both the area and the circumference of a circle of radius `r`.
​
### Immutability
Tuples are immutable, i.e. their values cannot be changed. However, you may create new tuples with modified values if you want to do so.

Write a function that takes a list of tuples as input and replaces the last element of each tuple with the first element of that tuple. 
​
## Python Lists
### List slicing, append and extend, List Comprehension
#### Q1.a
Suppose you are working on an artificial intelligence project which requires data. You are required to feed your list data into a model but as *mini-batches* of fixed batch size `n`. *mini-batches* are like smaller pieces of the original list. Write a function to convert a list into nested list of n minibatches. 

For example, if you have the following input: 

```
# input data as a list
data = [12, 24, 47, 5, 63, 105, 5, 95, 8, 14, 2, 7]
# Mini-batch size
n = 4 
```
output should be the following: 
```
# list of lists where every inner list has n elements
[[12, 24, 47, 5], [63, 105, 5, 95], [95, 8, 2, 7]]
```

**Note**: You may assume that the mini-batch size is divisible by the total length of the list.

#### Q1.b
Write the same function above using pythonic way of iterating over the lists (if you haven't done it that way already).

**Bonus:** Did you know that you can do that as a one-liner code in Python? It's not very readable and recommended only when you are comfortable with lists.

#### Q1.c
Write a function to return the `i`th minibatch in a list without creating nested lists.

#### Q1.d
Write a function to combine two consecutive batches into a single batch.
​
#### Q2
You friend sends you some audio data over a network. The sent data is made of numerical elements which are always positive. However, due to a fault in our receiver, some of the data gets corrupted and gets set to some random negative value. In order to reduce the data corruption, we come up with a solution to replace the corrupted data with the average of the neighboring positive numbers. This comes from the fact that audio signals are continuous and the corrupted value is likely to fall between neighboring positive values.

For example,
```
Sent data: [5, 7, 9, 13, 8, 5, 4, 7, 10, 12, 9, 8]
Received data: [5, -12, 9, 13, -58, 5, 4, 7, 10, -1, 9, 8]
Fixed data: [5, 7, 9, 13, 9, 5, 4, 7, 10, 9.5, 9, 8]
```
**Note**: You may set the value of first and last element as that of the neighboring positive element.

​
**Additionally**:
* If two consecutive values are corrupted, then look for the closest positive value.
* Instead of positive numbers, specify a range for sent data.
​

**Easier Alternative**: Replace all negative values with the average of positive values.
​
#### Q3
Write a python program to check whether two lists are *circularly identical*.

For example, if we have the following lists:
```
list1 = [10, 10, 0, 0, 10]
list2 = [10, 10, 10, 0, 0]
list3 = [1, 10, 10, 0, 0]
```

Here, `list1` and `list2` are circularly identical becuase if you rotate the elements of `list 1` like a treadmill, you get `list 2` and vice versa. On the other hand `list3` is not circularly identical to `list1` and `list2`.
​
#### Q4
Write a program to to reverse a list by swapping every `i`th element of a list with `(N-i)`th element. You should enforce a stopping condition to effectively reverse the list.
​
### List Aliasing
​Try to figure out the output of the following code before running it. Then check your understanding by running the code or using Python Tutor.

#### Q5
What will `a`, `b`, `c` be after the following operations?

```
a = [1, 2, 3]
b = [4, 5, 6]
c = a
a = b
a.append(20)
```
​
#### Q6
Consider the following functions:
```
def double_first1(a):
  a[0] *= 2
  return a
​
def double_first2(a):
  a[0] *= 2
​
def change_list1(a):
  a = [100, 200, 300]
  return a
​
def change_list2(a):
  a = [1000, 2000, 3000]
```

What will `l1`, `l2`, and `l3` be after the following operations?
```
l1 = [10, 20, 30]
l2 = double_first1(l1)
double_first2(l2)
l3 = change_list1(l1)
change_list2(l2)
```