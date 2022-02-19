
https://gto76.github.io/python-cheatsheet/

# Data Structure :pinching_hand:, :pinched_fingers:, :crossed_fingers:

## `collections`
### About dictionary
After Python 3.7 standard `dict` preserve the order. But to be specific, please use `collections.OrderedDict`. [Reference](https://gandenberger.org/2018/03/10/ordered-dicts-vs-ordereddict/)

### `collections.NamedTuple`
1. Faster than dictonary while has similar feature (accessing with field name) since it's just `tuple`. 
2. Methods inherited from tuple. You can unpack it like tuple.
3. It is immutable unlike `dict`. But u can change the field by method.
4. Use cases: Read from csv or db, set configs (since it's immutable but value can be accessed by name)

## LRU Cache
leetcode https://leetcode.com/problems/lru-cache/

Implementation with `OrderedDict`
https://www.geeksforgeeks.org/lru-cache-in-python-using-ordereddict/

<!-- # Algorithm
## Sorting
1. QuickSort, MergeSort, BubbleSort, InsertSort
2. Topological Sort
DAG, cycle detection

## DFS,BFS
1. stack vs deque
2. Level detection with BFS

## DP (:pinching_hand:, :pinched_fingers:, :crossed_fingers:)
1. knapsack problem -->

# Concurrency
read this sht https://realpython.com/python-concurrency/ end to end.
## Why Concurrency
You want to make use of more cores/threads on you CPU to speed up you python code.

Types of task:
1. CPU-bound Task
    - Example: for loop sum 1 to 1000, numeric optimization, find root etc.
    - There is not waiting time in this type
2. I/O-Bounded Task
    - Example: Make requests to endpoints and wait for responses.
    - The CPU is **idle** while it's waiting. So u want to overlapping the times
    - 这个就是小学数学那个早上你需要穿衣服，摊煎饼，烧开水这几项任务，如何安排时间最短，烧开水的时候别等着去干别的

We tackle these two with threading and multiprocessing.

## Thread and Process
- Process: Each process has its own memory space
- Thread: threads are components of a process. Threads in the same process share same memory space
Imagine u choose to run things with multiple process, then the computer would need to copy the source data multiple times. Hence, the higher overhead. Thread, ofc have lower overhead

\*overhead refers to resources required to perform certain task. Could be creating threads, copying data etc..

### Python Global Interperter Lock(GIL)
*Why Multithreading in Python is bullsht.*
The GIL allows only **one** thread to hold the control of the python interpreter. It prevents multiple threads executing at the same time. It bottlenecks the performance of CPU-bound job.

## Speeding I/O bound tasks
1. With Threading
    - Create threads. Threads share data.
3. With `asyncio`
    - Using `one` thread, but switching to other tasks while waiting. It is called cooperative multitasking.
    - Using  `asyncio` is generally faster than using multithreading, as u dont need to create threads.
3. With Multiprocessing
    - Spread the job to each core, and each core running the tasks one by one. So the performance is really depends on the number of cores.
Overhead: Multiprocessing > Threading > `asyncio`

## Speeding CPU bound tasks
Thanks to the stupid GIL, we are unable to use threading. Using multiprocessing will have worse performance than the non-speed version. To by pass it, we leverages multiple cores.


## Libraries
|what|Task|Lib|Pros|Cons|
|---|---|---|---|---|
|thread|I/O|concurrent.futures|nice clear wrapper to use|race condition|
|asyncio|I/O|asyncio|fast|more code|
|process|CPU|multiprocessing|nice clean wrapper|overhead|


# Programming paradigm
Python is a multi-paradigm programming language, meaning it supports OOP and functional programming etc...

### OOP Related Concepts
- Inheritance
- Polymorphism
- Data Abstraction
- Encapsulation.

### Decorator:
Use cases, numpy vectorization decorator, pandas decorator. Basically a wrapper over a function.
#### What is a decortor
It is a way to specify management or augmentation code for functions and classes. Decorators themselves take the form of callable objects, functions, that process other callable ojects. It provides a way to insert automatically run code at the end of function and class definition statements. There are 2 types:
    1. Function Decorators: do name binding at function definition time, providing a layer of logic that can manage functions and meothods, or later calls to them.
    2. Class Decorators: do name binding at class definition time,

#### Why decorators?
    1. Decorators have a very explicit syntax,which makes them easier to spot than helper function calls that may be arbitrarily far-removed from the subject functions or classes.
    2. Decorators are applied once, when the subject function or class is defined. 
    3. Because of both of the prior points, decorators make it less likely that a user of an API will forget to augment function or class according to API requirements.
    
### Generator:
#### Iterator in Python
An iterator is essentially a value producer that yields successive values from its associated iterable object. 
#### Generator functions 
Generator functions return a [lazy iterator](https://en.wikipedia.org/wiki/Lazy_evaluation) instead of something like a list. The lazy iterator doesn't take up a lot of memory. 

Use Cases:
1. Reading Large Files. Instead of loading everything into the memeory at once, u read it row by row.
2. Loading Aws resouce with Generator.

## Mutable vs Immutables
- Mutables: list, set, dictionarym, pandas.DataFrame, numpy.array
- Immutables: numerics, strings, tuples, 
## Pass by reference vs Pass by value
Python function call pass by reference. 
- If the object is mutable, it passes the reference of that object. Changes happens inside will affect the object outside.
- If the object is immutable, it copies that object in memory and pass the reference of the copied object. So immutable arguements are effectively passed by value,

# Python Interpreter
## The Dynamic Typing Interlude
* Variables, Objects, and References
Variables are entries in a system table, with spaces for links to objects. Objects are pieces of allocated memory,with enough space to represent the values for which they stand. References are automatically followed pointers from variables to objects.
* What happen when you create a variable 
    1. Create an object (like a chunk a memory) to represent the value 3.
    2. Create the variable a, if it does not yet exist. 
    3. Link the variable a to the new object 3.
* Do bear in mind that types live with Objects, Not Variables
Because small integers and strings are cached and reused, though, is tells us they reference the same single object.
## Garbage collection
In Python, whenever a name is assigned to a new object, the space held by the prior object is reclaimed if it is not referenced by any other name or object. This automatic reclamation of objects’ space is known as garbage collection, 

Similar to cpp, python's gc is mainly based on reference counters.

## Python is dynamically typed
a model that keeps track of types for you automatically instead of requiring declaration code, but it is also strongly typed, a constraint that means you can perform on an object only operations that are valid for its type.

# Other Python Standard Libraries:
## itertools
repeat, chain, product, permutation, combination
## functools
reduce

<!-- # Data Libraries
Numpy, Pandas, Visualization(matplot, plotly)  -->



