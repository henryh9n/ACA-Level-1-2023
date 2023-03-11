# Homework 1
### Instructor: Henry Harutyunyan [`@henryh9n`](https://github.com/henryh9n)
### Teaching Associate: Gegham Zakaryan [`@zakaryan2004`](https://github.com/zakaryan2004)

## Problem 1 ~ Find the Duplicates
Given an unsorted list of numbers (integers) `n`, find and print all the duplicates in the list.

### Test Cases
| Input                    | Output |
| ------------------------ | ------ |
| `n = [5, 1, 2, 1, 4,]`   | `1`    |
| `n = [4, 1, 2]`          | `None` |
| `n = []`                 | `None` |
| `n = [6, 2, 5, 2, 6, 2]` | `2 6` |
| `n = [42, 42, 42, 42]`   | `42`   |

Think of the data structures used and try to implement an optimal solution for the problem.

_Additionally:_ Add comments on the complexity analysis of the implementation (Big-O).

## Problem 2 ~ Two Sum
You are given a list `nums` and an integer `target`. Return the indeces of the elements from `n` that sum to `target`.
### Example 1
`nums = [2, 5, 3, 7, 3, 8]`

`target = 12`

#### Output:
`[1, 3]`

#### Explanation:
If we take the element at index `1`, which is **5** and the element at index `3` which is **7**, it sums to **12**.
`nums[1] + nums[3] == 5 + 7 == 12`

### Test Cases
| Input                                          | Output |
| ---------------------------------------------- | ------ |
| `nums = [2, 5, 3, 7, 3, 8]` <br> `target=12`   | `1, 3` |
| `nums = [2, 5, 3, 7, 3, 8]` <br> `target=10`   | `2, 3` |
| `nums = [1, 5, 3, 1, 5, 1]` <br> `target=12`   | `None` |
| `nums = [0, 0, 0, 0]` <br> `target=0`          | `0, 1` |
| `nums = [1]` <br> `target=1`                   | `None` |
| `nums = [1, 3, 2, 42, 1]` <br> `target=42`     | `None` |
| `nums = []` <br> `target=42`                   | `None` |

## Problem 3 ~ Greatest Common Divisor
Create a function that takes an arbitrary number of integers (2 or more) and uses 
the [Euclidean Algorithm](https://www.khanacademy.org/computing/computer-science/cryptography/modarithmetic/a/the-euclidean-algorithm)
to compute the greatest common divisor (GCD) for those numbers.

The (GCD)[https://www.khanacademy.org/math/cc-sixth-grade-math/cc-6th-expressions-and-variables/cc-6th-gcf/v/greatest-common-divisor] 
of 2 numbers is defined as the highest number that divides both of the numbers exactly.

The GCD of more than 2 numbers can be calculated using factoring as follows: `GCD(a, b, c) = GCD(GCD(a, b), c)`

### Example 1
`gcd(24, 36, 16)`

#### Output:
`4`

#### Explanation:
`GCD(24, 36, 16) = GCD(GCD(24, 36), 16) = GCD(12, 16) = 4)`

### Test Cases
| Input               | Output  |
| ------------------- | ------- |
| `gcd(24, 36, 16)`   | `4`     |
| `gcd(24, 36)`       | `12`    |
| `gcd(24)`           | `Error` |
| `gcd()`             | `Error` |

**Note:** Python has an implementation of GCD in the Standard Library. Please refrain from using it for this exercise.

## Problem 4 ~ Profiling Decorator
[Profiling](https://en.wikipedia.org/wiki/Profiling_(computer_programming)) is a way to measure the performance of the software application
by measuring the resources used (time, memory, etc.) for the particular parts of it.

We want to create a decorator `@profile` that we can use to analyze the functions.

The decorator should write all the logs to a file, separate from the application output.

Each time a function is called in the application, it should write to the file the time, name of the function and how long it took to run it.

### Example 1
```
from time import sleep

@profile
def foo(x):
    sleep(2)
    return x**2
   

foo(2)
sleep(60)
foo(42)
```

#### Output: (In `performance.log` file)
```
2023-03-11 21:07:51.998617 - foo(2) - 0:00:02.000984
2023-03-11 21:08:54.013414 - foo(42) - 0:00:02.001023
```
