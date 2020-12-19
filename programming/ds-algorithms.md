Table of contents
- [Algorithms](#algorithms)
  - [Properties of an algorithm](#properties-of-an-algorithm)
  - [Techniques to design algorithms](#techniques-to-design-algorithms)
  - [Determining the efficiency of an algorithm](#determining-the-efficiency-of-an-algorithm)
  - [Sorting Techniques](#sorting-techniques)
  - [Search Techniques](#search-techniques)
- [Data Structures](#data-structures)
  - [Basic Data Structures](#basic-data-structures)
    - [Linear data types](#linear-data-types)
    - [Non-linear data types](#non-linear-data-types)
  - [Advanced data structures](#advanced-data-structures)
  - [Analyzing the algorithm](#analyzing-the-algorithm)
    - [Asymptotic analysis](#asymptotic-analysis)
      - [Worst, average and best cases](#worst-average-and-best-cases)
    - [Big Theta, Big-O and Big Omega](#big-theta-big-o-and-big-omega)

# Algorithms
An algorithm can be defined as a step by step procedure for solving a problem.

## Properties of an algorithm
An algorithm has five important properties:
- Finiteness
- Definiteness
- Input
- Output
- Effectiveness

One of the basic techniques for improving the efficiency of algorithms is to use an appropriate data structure.

## Techniques to design algorithms
- **Divide and conquer approach**: It is a useful for solving conceptually difficult problems.
- **Greedy approach**: It is more useful for solving oprimization problems under a given set of conditions.
- **Recursion**: It is a technique of defining the process using itself. It is used to solve problems that are repetitive in nature.
- **Dynamic Programming**
- **Brute-force algorithms**
- **Randomized algorithms**
- **Backtracking algorithms**

## Determining the efficiency of an algorithm
The rate at which the running time of an algorithm increases as a result of an increase in the volume of input data is called the order of growth of the algorithm.

The order of growth of an algorithm is defined by using the big O notation.

The different orders of growth and their corresponding big O notations are:
- Constant - O(1)
- Logarithmic - O(log n)
- Linear - O(n)
- Loglinear - O(n log n)
- Quadratic - O(n^2)
- Cubic - O(n^3)
- Exponential - O(2^n), O(10^n)

## Sorting Techniques
- Bubble sort
- Selection sort
- Insertion sort
- Heap sort
- Shell sort
- Quick sort
- Merge sort
- Counting sort
- Radix sort

## Search Techniques
- Linear search
- Binary search
- Ternary search
- Interpolation
- Jump search
- Exponential search
- Sublist search
- Hash

# Data Structures
Data structure is defined as a way of organizing the various data elements in memory with respect to each other.

Data structures can be classified under the following two categories:
1. Static: Example - Array
2. Dynamic: Example - Linked list

## Basic Data Structures
### Linear data types
- Array
- Stack
- Queue
- Deque

### Non-linear data types
- Linked list
- Tree
- Graph

## Advanced data structures
- Threaded binary tree
- Height balanced binary tree

## Analyzing the algorithm

### Asymptotic analysis
Determining the time complexity of an algorithm.

#### Worst, average and best cases
These time complexities have to be determined for an algorithm.

### Big Theta, Big-O and Big Omega
The notations used in the asymptotic analysis.

Big Theta: *($\theta$)* a notation that bounds a function from above and below, like we saw previously in analysis, which also omits a const from the notation.

Suppose, we have a function with time complexity 4n + 1. Since it's a linear function, we can notate it as `f(n) = g(n) + 1`

Now suppose we have a function, g(n) where f(n) is the Big-Theta of g(n). If the value, f(n), is always between c1\*g(n) (lower bound) and c2*g(n) (upper bound) then for the above example we can say that the worst case time complexity of f(n) is $\theta$(n) and the best case time complexity of f(n) is $\theta$(1).

Big-O notation: *(O)* a notation that bounds a function from above only using the upper bound of an algorithm. For the above example we can say that the time complexity of f(n) is O(n).

Big Omega notation ($\Omega$) is contrary to the Big-O notation. It uses the lower bound to analyze time complexity. In other words is the best case in Big Theta notation. For the f(n) notation, we can say that the time complexity is $\Omega$(1).

