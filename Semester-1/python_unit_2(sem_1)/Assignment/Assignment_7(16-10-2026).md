# Assignment-7

**Topic:** Python While Loop

**Instruction:** Predict the exact output of each program before running it. Pay attention to the condition, statement order, indentation, and variable updates. Write **No output** if nothing is printed and **Infinite loop** if the program does not terminate.

------------------------------------------------------------------------

## Type 1: Output Guessing

### Level 1: Understand the Basic Flow

### Q1. Simple Counting

``` python
i = 1

while i <= 4:
    print(i)
    i += 1
```

**Predicted output:**

``` text
```

### Q2. Counting by Two

``` python
n = 2

while n <= 8:
    print(n, end=" ")
    n += 2
```

**Predicted output:**

``` text
```

### Q3. Reverse Counting

``` python
x = 5

while x >= 1:
    print(x, end=" ")
    x -= 1
```

**Predicted output:**

``` text
```

### Q4. The Condition Is Initially False

``` python
count = 7

while count < 5:
    print("Hello")
    count += 1

print("Finished")
```

**Predicted output:**

``` text
```

------------------------------------------------------------------------

### Level 2: Track the Order of Statements

### Q5. Update Before Printing

``` python
i = 1

while i <= 4:
    i += 1
    print(i, end=" ")
```

**Predicted output:**

``` text
```

### Q6. Print After the Loop

``` python
n = 1

while n <= 3:
    print(n, end=" ")
    n += 1

print("Done")
```

**Predicted output:**

``` text
```

### Q7. Two Updates in One Iteration

``` python
x = 1

while x < 10:
    print(x, end=" ")
    x += 2
    x += 1
```

**Predicted output:**

``` text
```

### Q8. Change the Variable Before Checking Again

``` python
value = 10

while value > 0:
    value -= 3
    print(value, end=" ")
```

**Predicted output:**

``` text
```

------------------------------------------------------------------------

### Level 3: Arithmetic and Accumulation

### Q9. Add the Counter Values

``` python
i = 1
total = 0

while i <= 4:
    total += i
    i += 1

print(total)
```

**Predicted output:**

``` text
```

### Q10. Multiply During Each Iteration

``` python
n = 1
result = 1

while n <= 4:
    result *= 2
    n += 1

print(result)
```

**Predicted output:**

``` text
```

### Q11. Use the Remainder Operator

``` python
n = 11

while n > 0:
    print(n % 3, end=" ")
    n -= 4
```

**Predicted output:**

``` text
```

### Q12. Integer Division

``` python
number = 583

while number > 0:
    print(number // 10, end=" ")
    number //= 10
```

**Predicted output:**

``` text
```

------------------------------------------------------------------------

### Level 4: Conditions and Logical Thinking

### Q13. Print Only When a Condition Is True

``` python
i = 1

while i <= 6:
    if i % 2 == 0:
        print(i, end=" ")
    i += 1
```

**Predicted output:**

``` text
```

### Q14. A Conditional Expression Inside a Loop

``` python
n = 1

while n <= 5:
    print("Even" if n % 2 == 0 else "Odd", end=" ")
    n += 1
```

**Predicted output:**

``` text
```

### Q15. The Condition Changes Inside the Loop

``` python
x = 1

while x < 10:
    print(x, end=" ")
    x *= 2
```

**Predicted output:**

``` text
```

### Q16. A Tricky Starting Value

``` python
i = 5

while i > 0:
    print(i, end=" ")
    i -= 2

print("Stop:", i)
```

**Predicted output:**

``` text
```

------------------------------------------------------------------------

### Level 5: Strings and Tricky Cases

### Q17. Build a String Repeatedly

``` python
i = 1
result = ""

while i <= 4:
    result += "A"
    print(result)
    i += 1
```

**Predicted output:**

``` text
```

### Q18. A String Variable Changes Each Time

``` python
word = "PY"

while len(word) < 6:
    print(word)
    word += "T"

print(word)
```

**Predicted output:**

``` text
```

### Q19. Does the Loop Run at All?

``` python
x = 3

while x > 10:
    print("Inside")
    x += 1

print(x)
```

**Predicted output:**

``` text
```

### Q20. Find the Problem

``` python
i = 1

while i <= 4:
    print(i, end=" ")
    i -= 1

print("Finished")
```

**What happens when this program runs?**

Choose one: - A. It prints `1 2 3 4 Finished` - B. It prints
`1 0 -1 -2 ...` and continues indefinitely - C. It prints nothing - D.
It produces a syntax error

**Your answer and reasoning:**

``` text
```
------------------------------------------------------------------------


## Type 2: Basic While Loop Problems — Statement Based

**Instructions:** Solve each problem using **one `while` loop only**. Read the input and output format carefully. Test cases show sample inputs and the expected outputs.

### Level 1: Basic Counting

### Q21. Print Numbers from 1 to N

**Task:** Take a positive integer `N` and print all numbers from `1` to `N`, each on a new line.

**Input:**
```text
5
```

**Expected Output:**
```text
1
2
3
4
5
```

**Test Cases:**

| Input | Expected Output |
|---|---|
| `3` | `1`<br>`2`<br>`3` |
| `1` | `1` |
| `6` | `1`<br>`2`<br>`3`<br>`4`<br>`5`<br>`6` |

### Q22. Print Numbers from N to 1

**Task:** Take a positive integer `N` and print the numbers in descending order, from `N` to `1`.

**Input:**
```text
5
```

**Expected Output:**
```text
5
4
3
2
1
```

**Test Cases:**

| Input | Expected Output |
|---|---|
| `3` | `3`<br>`2`<br>`1` |
| `1` | `1` |
| `4` | `4`<br>`3`<br>`2`<br>`1` |

### Q23. Print Even Numbers up to N

**Task:** Take a positive integer `N` and print all even numbers from `2` up to `N`. If `N` is odd, stop at the last even number below it.

**Input:**
```text
10
```

**Expected Output:**
```text
2
4
6
8
10
```

**Test Cases:**

| Input | Expected Output |
|---|---|
| `7` | `2`<br>`4`<br>`6` |
| `4` | `2`<br>`4` |
| `1` | No output |

### Q24. Print Odd Numbers up to N

**Task:** Take a positive integer `N` and print all odd numbers from `1` up to `N`.

**Input:**
```text
9
```

**Expected Output:**
```text
1
3
5
7
9
```

**Test Cases:**

| Input | Expected Output |
|---|---|
| `6` | `1`<br>`3`<br>`5` |
| `5` | `1`<br>`3`<br>`5` |
| `1` | `1` |

### Q25. Print Multiples of a Number

**Task:** Take two positive integers, `K` and `N`. Print the multiples of `K` that are less than or equal to `N`.

**Input:**
```text
K = 3
N = 15
```

**Expected Output:**
```text
3
6
9
12
15
```

**Test Cases:**

| Input | Expected Output |
|---|---|
| `K = 4, N = 18` | `4`<br>`8`<br>`12`<br>`16` |
| `K = 5, N = 12` | `5`<br>`10` |
| `K = 7, N = 6` | No output |

------------------------------------------------------------------------

### Level 2: Counting with Small Changes

### Q26. Multiplication Table

**Task:** Take an integer `N` and print its multiplication table from `N × 1` to `N × 10`.

**Input:**
```text
4
```

**Expected Output:**
```text
4 x 1 = 4
4 x 2 = 8
4 x 3 = 12
4 x 4 = 16
4 x 5 = 20
4 x 6 = 24
4 x 7 = 28
4 x 8 = 32
4 x 9 = 36
4 x 10 = 40
```

**Test Cases:**

| Input | Expected Output |
|---|---|
| `2` | Print the table of 2 from `2 x 1 = 2` to `2 x 10 = 20` |
| `5` | Print the table of 5 from `5 x 1 = 5` to `5 x 10 = 50` |

### Q27. Count by a Given Step

**Task:** Take two positive integers, `START` and `STEP`. Starting from `START`, print the next five values, adding `STEP` after each value. Print exactly five numbers.

**Input:**
```text
START = 2
STEP = 3
```

**Expected Output:**
```text
2
5
8
11
14
```

**Test Cases:**

| Input | Expected Output |
|---|---|
| `START = 1, STEP = 2` | `1`<br>`3`<br>`5`<br>`7`<br>`9` |
| `START = 10, STEP = 5` | `10`<br>`15`<br>`20`<br>`25`<br>`30` |

### Q28. Sum of Numbers from 1 to N

**Task:** Take a positive integer `N` and calculate the sum of all integers from `1` to `N`. Print only the final sum.

**Input:**
```text
5
```

**Expected Output:**
```text
15
```

**Test Cases:**

| Input | Expected Output |
|---|---|
| `3` | `6` |
| `1` | `1` |
| `10` | `55` |

### Q29. Sum of Even Numbers up to N

**Task:** Take a positive integer `N` and calculate the sum of all even numbers from `2` up to `N`.

**Input:**
```text
10
```

**Expected Output:**
```text
30
```

**Test Cases:**

| Input | Expected Output |
|---|---|
| `6` | `12` |
| `9` | `20` |
| `1` | `0` |

### Q30. Sum of Odd Numbers up to N

**Task:** Take a positive integer `N` and calculate the sum of all odd numbers from `1` up to `N`.

**Input:**
```text
7
```

**Expected Output:**
```text
16
```

**Test Cases:**

| Input | Expected Output |
|---|---|
| `5` | `9` |
| `8` | `16` |
| `1` | `1` |

------------------------------------------------------------------------

### Level 3: Simple Repeated Calculations

### Q31. Calculate the Total Cost

**Task:** A shop sells one notebook for `PRICE` rupees. Take the price of one notebook and the number of notebooks purchased, `QUANTITY`. Calculate the total cost using repeated addition.

**Input:**
```text
PRICE = 20
QUANTITY = 4
```

**Expected Output:**
```text
80
```

**Test Cases:**

| Input | Expected Output |
|---|---|
| `PRICE = 15, QUANTITY = 3` | `45` |
| `PRICE = 7, QUANTITY = 5` | `35` |
| `PRICE = 50, QUANTITY = 1` | `50` |

### Q32. Calculate Total Savings

**Task:** A student saves the same amount of money every day. Take `DAILY_SAVING` and `DAYS`. Calculate the total amount saved after that many days using a loop.

**Input:**
```text
DAILY_SAVING = 25
DAYS = 6
```

**Expected Output:**
```text
150
```

**Test Cases:**

| Input | Expected Output |
|---|---|
| `DAILY_SAVING = 10, DAYS = 7` | `70` |
| `DAILY_SAVING = 50, DAYS = 2` | `100` |
| `DAILY_SAVING = 12, DAYS = 1` | `12` |

### Q33. Calculate a Number Raised to a Power

**Task:** Take two non-negative integers, `BASE` and `POWER`. Calculate `BASE` raised to `POWER` using repeated multiplication. Assume `POWER` is between `0` and `8`.

**Input:**
```text
BASE = 3
POWER = 4
```

**Expected Output:**
```text
81
```

**Test Cases:**

| Input | Expected Output |
|---|---|
| `BASE = 2, POWER = 3` | `8` |
| `BASE = 5, POWER = 1` | `5` |
| `BASE = 7, POWER = 0` | `1` |

### Q34. Calculate Factorial

**Task:** Take a non-negative integer `N` and calculate its factorial. The factorial of `N` is the product of all integers from `1` to `N`. Remember that `0! = 1`.

**Input:**
```text
5
```

**Expected Output:**
```text
120
```

**Test Cases:**

| Input | Expected Output |
|---|---|
| `3` | `6` |
| `4` | `24` |
| `0` | `1` |

### Q35. Find the Sum from START to END

**Task:** Take two integers, `START` and `END`, where `START` is less than or equal to `END`. Calculate the sum of all integers from `START` through `END`, including both endpoints.

**Input:**
```text
START = 3
END = 7
```

**Expected Output:**
```text
25
```

**Test Cases:**

| Input | Expected Output |
|---|---|
| `START = 1, END = 4` | `10` |
| `START = 5, END = 5` | `5` |
| `START = 10, END = 12` | `33` |

------------------------------------------------------------------------

### Level 4: Read the Condition Carefully

### Q36. Count Down by Two

**Task:** Take a positive even integer `N`. Print numbers from `N` down to `2`, decreasing by `2` each time.

**Input:**
```text
10
```

**Expected Output:**
```text
10
8
6
4
2
```

**Test Cases:**

| Input | Expected Output |
|---|---|
| `6` | `6`<br>`4`<br>`2` |
| `2` | `2` |
| `12` | `12`<br>`10`<br>`8`<br>`6`<br>`4`<br>`2` |

### Q37. Repeatedly Divide by Two

**Task:** Take a positive integer `N`. Print the value of `N` after repeatedly applying integer division by `2`. Continue while the value is greater than `0`. Print each new value after dividing.

**Input:**
```text
20
```

**Expected Output:**
```text
10
5
2
1
0
```

**Test Cases:**

| Input | Expected Output |
|---|---|
| `8` | `4`<br>`2`<br>`1`<br>`0` |
| `5` | `2`<br>`1`<br>`0` |
| `2` | `1`<br>`0` |

### Q38. Count How Many Steps Are Needed

**Task:** Start with a positive integer `N`. In each step, subtract `3` from the number. Continue until the value becomes less than or equal to `0`. Print the number of steps taken.

**Input:**
```text
N = 11
```

**Expected Output:**
```text
4
```

**Test Cases:**

| Input | Expected Output |
|---|---|
| `N = 10` | `4` |
| `N = 6` | `2` |
| `N = 2` | `1` |

### Q39. Save Until the Target Is Reached

**Task:** A student already has `SAVED` rupees and adds `DAILY_AMOUNT` rupees each day. Calculate how many days are needed for the savings to become greater than or equal to `TARGET`. Assume `SAVED` is less than `TARGET` and `DAILY_AMOUNT` is positive.

**Input:**
```text
SAVED = 20
DAILY_AMOUNT = 15
TARGET = 70
```

**Expected Output:**
```text
4
```

**Test Cases:**

| Input | Expected Output |
|---|---|
| `SAVED = 0, DAILY_AMOUNT = 10, TARGET = 35` | `4` |
| `SAVED = 25, DAILY_AMOUNT = 25, TARGET = 75` | `2` |
| `SAVED = 5, DAILY_AMOUNT = 7, TARGET = 20` | `3` |

### Q40. Print a Number Sequence in Reverse Steps

**Task:** Take two positive integers, `START` and `STEP`, where `START` is divisible by `STEP`. Print values starting from `START`, subtracting `STEP` each time, and stop after printing `0`.

**Input:**
```text
START = 20
STEP = 5
```

**Expected Output:**
```text
20
15
10
5
0
```

**Test Cases:**

| Input | Expected Output |
|---|---|
| `START = 12, STEP = 3` | `12`<br>`9`<br>`6`<br>`3`<br>`0` |
| `START = 8, STEP = 2` | `8`<br>`6`<br>`4`<br>`2`<br>`0` |
| `START = 9, STEP = 3` | `9`<br>`6`<br>`3`<br>`0` |

------------------------------------------------------------------------

**Reminder:** Use one `while` loop per question. Focus on initializing variables, checking the condition, updating the variable, and deciding when the loop should stop.
