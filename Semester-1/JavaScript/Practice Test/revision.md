## 📌Module 1: Introduction to JavaScript & Web Basics

* **High-Level Language:** Uses simple, human-readable instructions and hides hardware/memory details.
* *Syntax/Example:* `let totalPrice = productPrice + tax;`


* **Dynamically Typed Language:** Variables do not require explicit type declarations; JavaScript determines data types at runtime.
* *Example:* `let value = 10; typeof value; // "number"`


* **Interpreted Language:** Code is executed step-by-step by a JavaScript engine.
* *Example:* `console.log("First line"); console.log("Second line");`


* **History:** Created in **1995** by **Brendan Eich** at Netscape (originally named Mocha, then LiveScript).
* **JS vs. Java:** Completely different languages. JavaScript is dynamically typed and runs in browsers/Node.js, whereas Java is statically typed and runs on the JVM.
* **Three Pillars of Front-End:** HTML provides structure/content, CSS handles style, and JavaScript controls behavior/interactivity.
* *Example:* `<button onclick="alert('Hello JavaScript!')">Click Me</button>`


* **Frontend vs. Backend:** Frontend runs in the user's browser (HTML/CSS/JS), while Backend runs on remote servers using **Node.js** and **Express.js** to handle logic and databases.

---

## 📌Module 2: Variables & Data Types

* **Variable Declaration Keywords (`var`, `let`, `const`):**
* `var`: Legacy, function-scoped, allows re-declaration/re-assignment, hoisted with `undefined`.
* *Example:* `var name = "John";`


* `let`: Modern, block-scoped, allows re-assignment but not re-declaration.
* *Example:* `let age = 25; age = 26;`


* `const`: Modern, block-scoped, **read-only reference** (disallows re-assignment), requires mandatory initialization.
* *Example:* `const PI = 3.14;`




* **Primitive Data Types (7 types):** `Number`, `String`, `Boolean`, `Undefined`, `Null`, `Symbol`, and `BigInt`.
* *Examples:*
* Number: `let num = 42;`
* String: `let text = "Hello";`
* Boolean: `let isStudent = true;`
* Undefined: `let x;`
* Null: `let y = null;`




* **Non-Primitive Data Types:** Complex structures built using primitives (`Object`, `Array`, `Function`).
* *Examples:*
* Object: `let person = { name: "Alice", age: 30 };`
* Array: `let numbers = [1, 2, 3, 4, 5];`
* Function: `function greet() { return "Hello"; }`




* **`undefined` vs. `null`:** `undefined` is automatically assigned to uninitialized variables, whereas `null` is explicitly assigned by the developer to represent an intentional "no value".
* **`typeof` Operator:** Returns the data type of a value as a string.
* *Example:* `typeof 42; // "number"` *(Note: `typeof null` returns `"object"` due to a historical bug)*.



---

## 📌Module 3: Operators & Type Coercion

* **Arithmetic Operators:** `+`, `-`, `*`, `/`, `%` (Modulus), and `**` (Exponentiation).
* *Examples:*
* Modulus: `let rem = 15 % 4; // 3`
* Exponentiation: `let res = 5 ** 2; // 25`




* **Increment & Decrement Operators (`++`, `--`):**
* **Increment (`++`):** Increases a variable's value by 1.
* *Postfix (`x++`):* Uses current value first, then increments. (`let x = 5; let y = x++;` $\rightarrow$ `y = 5, x = 6`)
* *Prefix (`++a`):* Increments value first, then uses it. (`let a = 5; let b = ++a;` $\rightarrow$ `a = 6, b = 6`)


* **Decrement (`--`):** Decreases a variable's value by 1.
* *Postfix (`m--`):* Uses current value first, then decrements. (`let m = 10; let n = m--;` $\rightarrow$ `n = 10, m = 9`)
* *Prefix (`--p`):* Decrements value first, then uses it. (`let p = 10; let q = --p;` $\rightarrow$ `p = 9, q = 9`)




* **Assignment Operators:** `=`, `+=`, `-=`, `*=`, `/=`, `%=`, `**=`.
* *Example:* `let score = 10; score += 5; // 15`


* **Comparison Operators:**
* Loose Equality (`==`): Compares values only, allowing implicit type coercion. (`"5" == 5` $\rightarrow$ `true`)
* Strict Equality (`===`): Compares both value and data type without coercion. (`"5" === 5` $\rightarrow$ `false`)


* **Logical Operators:** Logical AND (`&&`), Logical OR (`||`), and Logical NOT (`!`).
* *Example:* `let canAccess = isLogged && hasPermission;`


* **Type Coercion:** Automatic or manual conversion of data types.
* *Implicit Example:* `"10" - 5; // 5` (string automatically converted to number)
* *Explicit Example:* `let num = Number("25"); // 25`



---

## 📌Module 4: Conditional Control Flow

* **`if` Statement:** Runs code only when the condition is true.
* *Syntax & Example:*
```javascript
if (marks >= 35) {
    console.log("Passed");
}

```




* **`if...else` Statement:** Handles two possible outcomes (true/false).
* *Syntax & Example:*
```javascript
if (number % 2 === 0) {
    console.log("Even");
} else {
    console.log("Odd");
}

```




* **`if...else if...else` Statement:** Evaluates multiple conditions sequentially (e.g., grading systems).
* *Syntax & Example:*
```javascript
if (marks >= 90) {
    console.log("Grade A");
} else if (marks >= 75) {
    console.log("Grade B");
} else {
    console.log("Grade F");
}

```




* **`switch` Statement:** Best for comparing one single expression against multiple exact fixed values using case labels.
* *Syntax & Example:*
```javascript
switch (day) {
    case 1:
        console.log("Monday");
        break;
    default:
        console.log("Invalid day");
}

```




* **Ternary Operator (`?:`):** Concise shorthand for simple `if-else` assignments.
* *Syntax & Example:* `let message = age >= 18 ? "Can Vote" : "Cannot Vote";`



---

## 📌 Module 5: Loops & Jump Statements

* **`for` Loop:** Best when the exact number of iterations is known.
* *Syntax & Example:*
```javascript
for (let i = 1; i <= 5; i++) {
    console.log(i);
}

```




* **`while` Loop:** Condition is checked before execution.
* *Syntax & Example:*
```javascript
let count = 5;
while (count > 0) {
    console.log(count);
    count--;
}

```




* **`do...while` Loop:** Condition is checked after execution; guarantees running **at least once**.
* *Syntax & Example:*
```javascript
let i = 1;
do {
    console.log(i);
    i++;
} while (i <= 5);

```




* **Jump Statements:**
* `break`: Completely stops and exits the loop.
* *Example:* `if (i === 5) break;`


* `continue`: Skips the current iteration and moves to the next one.
* *Example:* `if (i % 2 === 0) continue; // skips even numbers`
