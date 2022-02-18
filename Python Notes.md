
https://gto76.github.io/python-cheatsheet/

# Data Structure

## `collections`
### About dictionary
After Python 3.7 standard `dict` preserve the order. But to be specific, please use `collections.OrderedDict`. [Reference](https://gandenberger.org/2018/03/10/ordered-dicts-vs-ordereddict/)

### `collections.NamedTuple`
1. Faster than dictonary while has similar feature (accessing with field name). 
2. Methods inherited from tuple. You can unpack it like tuple.
3. It is immutable meaning u. But u can change the field by method.
4. 

## LRU Cache
leetcode https://leetcode.com/problems/lru-cache/

Implementation with `OrderedDict`
https://www.geeksforgeeks.org/lru-cache-in-python-using-ordereddict/

# Algorithm
## Sorting
1. QuickSort, MergeSort, BubbleSort, InsertSort
2. Topological Sort
DAG, cycle detection

## DFS,BFS
1. stack vs deque
2. Level detection with BFS

## DP
1. knapsack problem

# Concurrency
read this sht https://realpython.com/python-concurrency/ end to end.
## Why Concurrency
## 
## At What Cost
## Libraries
## Python Global Interperter Lock(GIL)
Why Multithreading in Python is bullsht.

# OOP
in Python
## Decorator:
### Generator:
Example
Why use generate. (Save memory)

# Other Python Standard Libraries:
## itertools
repeat, chain, product, permutation, combination
## functools
reduce

# Data tools
## Numpy

## Pandas

## Visualization 

# Memoery Related
## Mutable vs Immutables
## Pass by reference vs Pass by value
