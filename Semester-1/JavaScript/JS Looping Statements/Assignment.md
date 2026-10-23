
# 📝 JavaScript Assignment: `for` Loop

## Instructions
- Solve all questions using a `for` loop.
- Use `console.log()` to display the output.
- Do not use arrays or advanced concepts.

---
## Part A] For Loop
---

## Q1. Counting Numbers 🔢

A teacher wants students to practice counting. Write a program to print all numbers from 1 to 15.

**Sample Output:**
```
1
2
3
4
5
...
15
```

---

Q2. Even Numbers 🎯

A school has lockers numbered with even numbers for a special activity. Write a program to print all even numbers from 2 to 40.

Sample Output:
```
2
4
6
8
10
...
40
```

---

Q3. Odd Numbers 🏃

A fitness coach assigns odd numbers to participants for a special activity. Write a program to print all odd numbers from 1 to 35.

Sample Output:
```
1
3
5
7
9
...
35

```
---`

Q4. Saving Money 💰

You save ₹10 on Day 1, ₹20 on Day 2, ₹30 on Day 3, and continue increasing your daily savings by ₹10. Write a program to calculate your total savings after 10 days.

Sample Output:
```
Total savings after 10 days: ₹550
```

---

Q5. Multiplication Table 📚

You want to practice multiplication. Write a program to print the multiplication table of 12, from 12 × 1 to 12 × 10.

Sample Output:
```
12 x 1 = 12
12 x 2 = 24
12 x 3 = 36
12 x 4 = 48
12 x 5 = 60
12 x 6 = 72
12 x 7 = 84
12 x 8 = 96
12 x 9 = 108
12 x 10 = 120
```

---

Q6. Daily Water Intake 💧

You drink 3 glasses of water every day. Write a program to calculate the total number of glasses you drink over 7 days. Print the cumulative total after each day.

Sample Output:
```
Day 1: 3 glasses
Day 2: 6 glasses
Day 3: 9 glasses
Day 4: 12 glasses
Day 5: 15 glasses
Day 6: 18 glasses
Day 7: 21 glasses

```
---

Q7. Shopping Calculation 🛍️

One chocolate costs ₹15. Write a program to print the total cost of buying 1 to 10 chocolates.

Sample Output:
```
1 chocolate = ₹15
2 chocolates = ₹30
3 chocolates = ₹45
4 chocolates = ₹60
5 chocolates = ₹75
...
10 chocolates = ₹150

```
---

Q8. Sum of Even Numbers ➕

You want to calculate the sum of all even numbers between 2 and 30, including both 2 and 30. Write a program to calculate and print the total.

Sample Output:
```
Sum of even numbers: 240

```
---

Q9. Weekly Exercise 💪

You do 5 push-ups on Day 1, 10 on Day 2, 15 on Day 3, and continue increasing the number by 5 each day. Write a program to print the number of push-ups for each day over 7 days.

Sample Output:
```
Day 1: 5 push-ups
Day 2: 10 push-ups
Day 3: 15 push-ups
Day 4: 20 push-ups
Day 5: 25 push-ups
Day 6: 30 push-ups
Day 7: 35 push-ups
```

---

Q10. Movie Tickets 🎬

One movie ticket costs ₹150. Write a program to print the total ticket cost for 1 to 8 people.

Sample Output:
```
1 person: ₹150
2 people: ₹300
3 people: ₹450
4 people: ₹600
5 people: ₹750
6 people: ₹900
7 people: ₹1050
8 people: ₹1200
```

---

🎯 Challenge

Try solving all 10 questions without looking at anyone else's code. Focus on understanding the three parts of a for loop:

1. Initialization: Where does the loop start?

2. Condition: When should the loop stop?

3. Update: How does the loop variable change?

---
## Part B] For Loop (Additional advanced questions)
---
1. Given an array of temperatures `[28, 32, 25, 40, 18, 35]`, use a `for` loop to count how many days were hotter than 30°C.  
2. Write a `for` loop that calculates the sum of all digits of a given number (example: 4729 → 4+7+2+9 = 22).  
3. Create a `for` loop that prints only the numbers between 1 and 100 that are divisible by both 3 and 5, but not by 7.  
4. Given the string `"JavaScript"`, use a `for` loop to create a new string that contains only the consonants (remove vowels).  
5. Write a `for` loop that finds the largest number in an array of positive integers without using any sorting method.  
6. Use a `for` loop to check whether a given number is a perfect number (a number equal to the sum of its proper divisors). Example: 28.  
7. Print the following series using a single `for` loop:  
   `1 2 4 8 16 32 64 128` 
8. Write a `for` loop that prints the first 20 Fibonacci numbers (starting with 0 and 1).
9. Given an array of student scores `[45, 78, 90, 32, 56, 88]`, use a `for` loop to calculate the average and also count how many students scored above the average.  
10. Write a `for` loop that converts a decimal number to its binary representation (without using built-in methods like `toString(2)`).

### Note: Question No. 8 & 10 are optional from above.

---

### Part C-a] `break` inside a  `for` Loop

1. Write a `for` loop that searches for the first occurrence of the number 7 in an array. As soon as it finds 7, print its index and stop the loop using `break`.  
2. Simulate a simple password checker: keep asking the user for a password (using a `for` loop that runs maximum 5 times). If the correct password is entered, print “Access granted” and `break`. If all 5 attempts fail, print “Account locked”.  
3. Write a `for` loop that adds numbers from 1 onwards until the sum exceeds 100. Print the last number that was added before the sum crossed 100 and stop using `break`.  
4. Given an array of names, use a `for` loop to find the first name that starts with the letter “S”. Print that name and immediately stop the loop with `break`.  
5. Create a `for` loop that prints numbers from 1 to 50. Stop completely (`break`) as soon as you encounter a number that is both a perfect square and greater than 20.

---

### Part C-b] `continue` inside a `for` Loop

1. Print all numbers from 1 to 30, but skip every number that is divisible by 4 using `continue`.  
2. Given an array of mixed positive and negative numbers, use a `for` loop with `continue` to calculate the sum of only the positive numbers.  
3. Write a `for` loop that prints every character of the string `"Hello World"`, but skips all spaces using `continue`.  
4. Print the multiplication table of 6 from 1 to 12, but skip the rows where the product is divisible by 5 (use `continue`).  
5. Given an array of ages `[12, 18, 25, 15, 30, 17, 22]`, use a `for` loop with `continue` to print only the ages of people who are eligible to vote (age ≥ 18).


### Part D] `Reverse` For Loop

1. Write a reverse `for` loop that prints all numbers from 50 down to 1 that are divisible by 3 but **not** divisible by 9.  

2. Write a reverse `for` loop that calculates the product of all odd digits of a given number (example: 4729 → 7 × 9 = 63).   

3. Given the string `"Programming"`, use a reverse `for` loop to create a new string that contains only the consonants in reverse order. 

4. Write a reverse `for` loop that prints the first 15 Fibonacci numbers in **reverse order** (starting from the 15th number down to 0).

5. Use a reverse `for` loop to check whether a given number is a palindrome by comparing digits from both ends (without converting the number to a string).  

6. Given an array `[12, 45, 7, 23, 56, 89, 34]`, use a reverse `for` loop to find the largest number that is less than 50 (do **not** use any built-in methods).   

7. Given an array of temperatures `[32, 28, 41, 19, 35, 27, 38]`, use a reverse `for` loop to count how many days were colder than 30°C, starting from the last day.  

8. Write a reverse `for` loop that converts a decimal number to its binary representation but prints the binary digits in reverse order (example: 13 → 1011 becomes 1101).  

9. **(Reverse For Loop + `break`)**  
Given an array `[90, 85, 70, 95, 60, 88, 75]`, use a reverse `for` loop to find the first score (starting from the end) that is greater than 80. Print that score and its index, then stop the loop using `break`.  

10. **(Reverse For Loop + `continue`)**  
Write a reverse `for` loop that prints numbers from 40 down to 1, but skips every number that is a perfect square using `continue`.

---
### Part E] `Nested For Loop` Questions

1. Print the following right-triangle number pattern using nested `for` loops (without hard-coding any row):
```
1
2 3
4 5 6
7 8 9 10
```

2. Print the following right-triangle number pattern using nested `for` loops (without hard-coding any row):
```
1
2 2
3 3 3
4 4 4 4
```

3. Print the following right-triangle number pattern using nested `for` loops (without hard-coding any row):
```
1
2 3
4 5 6
7 8 9 10
```

4. Print the following pattern using nested `for` loops (without hard-coding any row):
```
* * * *
*     *
*     *
* * * *
```

5. Print the following right-triangle number pattern using nested `for` loops (without hard-coding any row):
```
#
$ $
# # #
$ $ $ $
# # # # #
$ $ $ $ $ $
```

6. Print the following right-triangle alphabet pattern using nested `for` loops (without hard-coding any row):
```
A
A B
A B C
A B C D
A B C D E
```

7. Print this hollow right-triangle star pattern using nested loops:
```
*
* *
*   *
*     *
* * * * *
```

8. Print the following reverse right-angle star pattern using nested `for` loops:
```
*****
****
***
**
*
```

9. Print the following reverse right-angle pattern where each row contains the row number repeated, using nested loops:
```
5 5 5 5 5
4 4 4 4
3 3 3
2 2
1
```


10. Print this reverse right-angle number pattern using nested `for` loops:
```
1 2 3 4 5
1 2 3 4
1 2 3
1 2
1
```

11. Print the following reverse right-angle pattern of consecutive numbers using nested loops:
```
15 14 13 12 11
10  9  8  7
 6  5  4
 3  2
 1
```

12. Print this reverse right-angle hollow star pattern (only the borders should have stars) using nested `for` loops:
```
* * * * *
*     *
*   *
* *
*
```

13. Using nested `for` loops, print a 5×5 square of stars (`*`) but skip printing a star whenever the row number equals the column number (i.e., leave the main diagonal empty).

14. Write nested `for` loops that print the multiplication table of numbers from 1 to 5, but only show the products that are even. (Each table should start on a new line.)

15. Write a program to print a symmetric number palindrome pyramid on each row.

```
    1
  1 2 1
1 2 3 2 1
```
