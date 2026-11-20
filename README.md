<div align="center">

# 🧩 JavaScript Fundamentals: Functions

**A hands-on practice file on writing reusable code: function declarations, parameters, default values, `return`, and arrow functions**

</div>

---

## 📖 About This Project

This is my fourth JavaScript practice project. So far I had learned how to store values (`var`, `let`, `const`), make decisions (`if / else`), and repeat work (loops). All of that code ran once, for one set of values.

**Functions** fix that. A function packages code under a name so I can run it again and again with different inputs.

The project is a single file, `index.js`, with three examples:

- `nice(name)`, a function that prints four lines for any name
- `sum(a, b, c = 3)`, a function with a **default parameter** that **returns** a value
- `func1`, an **arrow function**

I also added **35 practice tasks** in five parts, each with a test block and collapsible solutions, so I can keep writing functions of my own. See [Practice Tasks](#-practice-tasks).

There is no HTML page. Everything runs in **Node.js** (or the browser console) and prints with `console.log()`.

---

## 📑 Table of Contents

1. [Project Structure](#-project-structure)
2. [Why Functions?](#-why-functions)
3. [Anatomy of a Function](#-anatomy-of-a-function)
4. [Example 1: `nice(name)`](#-example-1-nicename)
5. [Example 2: `sum(a, b, c = 3)`](#-example-2-suma-b-c--3)
6. [Example 3: The Arrow Function](#-example-3-the-arrow-function)
7. [Expected Console Output](#-expected-console-output)
8. [Declarations vs Arrow Functions](#-declarations-vs-arrow-functions)
9. [Preview: Turning My Loop Problems into Functions](#-preview-turning-my-loop-problems-into-functions)
10. [Practice Tasks](#-practice-tasks)
11. [Known Gaps & Improvements](#-known-gaps--improvements)
12. [Try It Yourself](#-try-it-yourself)
13. [How to Run](#-how-to-run)
14. [Cheat Sheet](#-cheat-sheet)
15. [Key Takeaways](#-key-takeaways)
16. [Roadmap](#-roadmap)

---

## 📂 Project Structure

```
js-fundamentals/
│
└── 04-functions/
    ├── index.js       # nice(), sum(), and an arrow function
    └── practice.js    # my solutions to the practice tasks (create this file yourself)
```

> 💡 Rename the folder to match your own layout. `practice.js` doesn't exist yet. It is where the solutions to the [Practice Tasks](#-practice-tasks) go.

---

## 🤔 Why Functions?

Look at this code, which greets one person:

```js
console.log("Hey Ali you are nice!");
console.log("Hey Ali you are good!");
console.log("Hey Ali your tshirt is nice!");
console.log("Hey Ali your course is good too!");
```

To greet a second person, I would copy all four lines and change the name. For a hundred people, that is four hundred lines, and fixing a typo means fixing it a hundred times.

With a function, I write the four lines **once**:

```js
function nice(name) {
  console.log("Hey " + name + " you are nice!");
  console.log("Hey " + name + " you are good!");
  console.log("Hey " + name + " your tshirt is nice!");
  console.log("Hey " + name + " your course is good too!");
}
```

Now `nice("Ali")`, `nice("Sara")`, and `nice("Omar")` each do the whole job in one line. This idea is often called **DRY**: *Don't Repeat Yourself*.

---

## 🧬 Anatomy of a Function

```js
function sum(a, b, c = 3) {
  console.log(a, b, c);
  return a + b + c;
}

const result1 = sum(3, 2);
```

<table>
  <tr>
    <th>Part</th>
    <th>In the code</th>
    <th>Meaning</th>
  </tr>
  <tr>
    <td><b>Keyword</b></td>
    <td><code>function</code></td>
    <td>Tells JavaScript "I'm defining a function".</td>
  </tr>
  <tr>
    <td><b>Name</b></td>
    <td><code>sum</code></td>
    <td>How I call it later. Good names are usually verbs (<code>sum</code>, <code>greet</code>, <code>isPrime</code>).</td>
  </tr>
  <tr>
    <td><b>Parameters</b></td>
    <td><code>a, b, c = 3</code></td>
    <td>Placeholder variables <b>in the definition</b>. They receive values when the function is called.</td>
  </tr>
  <tr>
    <td><b>Body</b></td>
    <td><code>{ ... }</code></td>
    <td>The code that runs each time the function is called.</td>
  </tr>
  <tr>
    <td><b>Return</b></td>
    <td><code>return a + b + c</code></td>
    <td>Sends a value back to whoever called the function, and <b>ends</b> the function.</td>
  </tr>
  <tr>
    <td><b>Call</b></td>
    <td><code>sum(3, 2)</code></td>
    <td>Runs the function. Writing the parentheses is what makes it run.</td>
  </tr>
  <tr>
    <td><b>Arguments</b></td>
    <td><code>3, 2</code></td>
    <td>The real values passed <b>in the call</b>.</td>
  </tr>
</table>

### 🗣️ Parameters vs Arguments

<table>
  <tr>
    <th></th>
    <th>Parameters</th>
    <th>Arguments</th>
  </tr>
  <tr>
    <td><b>Where</b></td>
    <td>In the function <b>definition</b></td>
    <td>In the function <b>call</b></td>
  </tr>
  <tr>
    <td><b>What</b></td>
    <td>Names (placeholders)</td>
    <td>Actual values</td>
  </tr>
  <tr>
    <td><b>Example</b></td>
    <td><code>function sum(<b>a, b, c</b>)</code></td>
    <td><code>sum(<b>3, 2, 1</b>)</code></td>
  </tr>
</table>

> 💡 **Defining is not running.** Writing `function nice() { ... }` only teaches JavaScript what `nice` means. Nothing happens until the function is **called**.

---

## 👋 Example 1: `nice(name)`

```js
function nice(name) {
  console.log("Hey " + name + " you are nice!");
  console.log("Hey " + name + " you are good!");
  console.log("Hey " + name + " your tshirt is nice!");
  console.log("Hey " + name + " your course is good too!");
}
```

**Important:** in `index.js`, `nice` is defined but **never called**, so it prints nothing. To see it work, call it:

```js
nice("Ali");
```

Output:

```
Hey Ali you are nice!
Hey Ali you are good!
Hey Ali your tshirt is nice!
Hey Ali your course is good too!
```

<table>
  <tr>
    <th>Call</th>
    <th>First line printed</th>
  </tr>
  <tr>
    <td><code>nice("Ali")</code></td>
    <td>Hey Ali you are nice!</td>
  </tr>
  <tr>
    <td><code>nice("Sara")</code></td>
    <td>Hey Sara you are nice!</td>
  </tr>
  <tr>
    <td><code>nice("Omar")</code></td>
    <td>Hey Omar you are nice!</td>
  </tr>
</table>

This function **prints** four lines but does not `return` anything. If you print its result, you get `undefined`:

```js
console.log(nice("Ali"));
// Hey Ali you are nice!
// ... (the four lines)
// undefined      <- nice() returned nothing
```

---

## ➕ Example 2: `sum(a, b, c = 3)`

```js
function sum(a, b, c = 3) {
  // console.log(a + b)
  console.log(a, b, c);
  return a + b + c;
}

result1 = sum(3, 2);
result2 = sum(7, 5);
result3 = sum(3, 13, 1);

console.log("The sum of these numbers is: ", result1);
console.log("The sum of these numbers is: ", result2);
console.log("The sum of these numbers is: ", result3);
```

### 🔬 Tracing Each Call

<table>
  <tr>
    <th>Call</th>
    <th><code>a</code></th>
    <th><code>b</code></th>
    <th><code>c</code></th>
    <th>Printed by <code>console.log(a, b, c)</code></th>
    <th>Returned</th>
  </tr>
  <tr>
    <td><code>sum(3, 2)</code></td>
    <td align="center">3</td>
    <td align="center">2</td>
    <td align="center">3 <i>(default)</i></td>
    <td><code>3 2 3</code></td>
    <td align="center"><b>8</b></td>
  </tr>
  <tr>
    <td><code>sum(7, 5)</code></td>
    <td align="center">7</td>
    <td align="center">5</td>
    <td align="center">3 <i>(default)</i></td>
    <td><code>7 5 3</code></td>
    <td align="center"><b>15</b></td>
  </tr>
  <tr>
    <td><code>sum(3, 13, 1)</code></td>
    <td align="center">3</td>
    <td align="center">13</td>
    <td align="center">1 <i>(passed in)</i></td>
    <td><code>3 13 1</code></td>
    <td align="center"><b>17</b></td>
  </tr>
</table>

### 🎁 Default Parameters

`c = 3` gives the parameter a **fallback value**. If the caller doesn't supply a third argument, `c` becomes `3`.

<table>
  <tr>
    <th>Call</th>
    <th>What <code>c</code> becomes</th>
    <th>Result</th>
  </tr>
  <tr>
    <td><code>sum(3, 2)</code></td>
    <td>3 (default used)</td>
    <td align="center">8</td>
  </tr>
  <tr>
    <td><code>sum(3, 2, 10)</code></td>
    <td>10 (argument wins)</td>
    <td align="center">15</td>
  </tr>
  <tr>
    <td><code>sum(3, 2, undefined)</code></td>
    <td>3 (<code>undefined</code> triggers the default)</td>
    <td align="center">8</td>
  </tr>
  <tr>
    <td><code>sum(3, 2, null)</code></td>
    <td><code>null</code> (<b>not</b> replaced)</td>
    <td align="center">5 (<code>null</code> acts as <code>0</code> in addition)</td>
  </tr>
</table>

> ⚠️ A default is used **only when the argument is missing or `undefined`**, not for `null`, `0`, or an empty string.

### 🕳️ Missing and Extra Arguments

JavaScript is relaxed about how many arguments you pass:

<table>
  <tr>
    <th>Call</th>
    <th>What happens</th>
    <th>Result</th>
  </tr>
  <tr>
    <td><code>sum(3)</code></td>
    <td><code>b</code> is missing, so it is <code>undefined</code>. Then <code>3 + undefined + 3</code>.</td>
    <td align="center"><code>NaN</code></td>
  </tr>
  <tr>
    <td><code>sum(1, 2, 3, 4)</code></td>
    <td>The extra <code>4</code> is ignored.</td>
    <td align="center">6</td>
  </tr>
</table>

Parameters without a default and without an argument are `undefined`, which usually leads to `NaN`. Give the parameters that are optional a default value.

### 📤 `return` vs `console.log`

This is the most important idea in the file.

<table>
  <tr>
    <th></th>
    <th><code>console.log(x)</code></th>
    <th><code>return x</code></th>
  </tr>
  <tr>
    <td><b>What it does</b></td>
    <td>Shows a value on the screen</td>
    <td>Hands a value <b>back to the caller</b></td>
  </tr>
  <tr>
    <td><b>Can I store the value?</b></td>
    <td align="center">❌ No (the function itself returns <code>undefined</code>)</td>
    <td align="center">✅ Yes: <code>const r = sum(3, 2)</code></td>
  </tr>
  <tr>
    <td><b>Can I use it in a calculation?</b></td>
    <td align="center">❌ No</td>
    <td align="center">✅ <code>sum(3, 2) * 10</code></td>
  </tr>
  <tr>
    <td><b>Ends the function?</b></td>
    <td align="center">No</td>
    <td align="center">✅ Yes. Code after <code>return</code> never runs.</td>
  </tr>
</table>

```js
function sum(a, b, c = 3) {
  return a + b + c;
  console.log("I never run");     // unreachable: return already ended the function
}
```

> 💡 In `sum`, the `console.log(a, b, c)` is only there for learning, so I can see what the parameters were. The `return` is what makes `result1`, `result2`, and `result3` useful.

---

## 🏹 Example 3: The Arrow Function

```js
const func1 = (x) => {
  console.log("I am an arrow function", x);
};

func1(34);
func1(66);
func1(84);
```

An arrow function is a shorter way to write a function. It is stored in a variable (`const func1`) like any other value, and called with `func1(...)`.

### 🔁 From Regular Function to Arrow Function

```js
// 1. Regular function declaration
function double(x) {
  return x * 2;
}

// 2. As an arrow function stored in a const
const double = (x) => {
  return x * 2;
};

// 3. Implicit return: with no { }, the expression is returned automatically
const double = (x) => x * 2;

// 4. One parameter: the parentheses are optional
const double = x => x * 2;
```

### ✍️ Arrow Function Syntax Rules

<table>
  <tr>
    <th>Situation</th>
    <th>Syntax</th>
  </tr>
  <tr>
    <td>One parameter</td>
    <td><code>x =&gt; x * 2</code> (parentheses optional)</td>
  </tr>
  <tr>
    <td>Two or more parameters</td>
    <td><code>(a, b) =&gt; a + b</code> (parentheses required)</td>
  </tr>
  <tr>
    <td>No parameters</td>
    <td><code>() =&gt; "hello"</code> (parentheses required)</td>
  </tr>
  <tr>
    <td>One expression, no <code>{ }</code></td>
    <td>The value is <b>returned automatically</b></td>
  </tr>
  <tr>
    <td>With <code>{ }</code> around the body</td>
    <td>You must write <code>return</code> yourself</td>
  </tr>
  <tr>
    <td>Returning an object literal</td>
    <td>Wrap it in parentheses: <code>() =&gt; ({ name: "Ali" })</code></td>
  </tr>
</table>

In this file, `func1` uses `{ }` and prints but doesn't return anything, so `func1(34)` returns `undefined`, just like `nice()`.

---

## 🖥️ Expected Console Output

Running `index.js` prints **9 lines**:

```
3 2 3
7 5 3
3 13 1
The sum of these numbers is:  8
The sum of these numbers is:  15
The sum of these numbers is:  17
I am an arrow function 34
I am an arrow function 66
I am an arrow function 84
```

<table>
  <tr>
    <th>Lines</th>
    <th>Printed by</th>
  </tr>
  <tr>
    <td align="center">1 to 3</td>
    <td>The <code>console.log(a, b, c)</code> inside each of the three <code>sum()</code> calls</td>
  </tr>
  <tr>
    <td align="center">4 to 6</td>
    <td>The three "The sum of these numbers is:" lines</td>
  </tr>
  <tr>
    <td align="center">7 to 9</td>
    <td>The three <code>func1()</code> calls</td>
  </tr>
</table>

### 🧭 Why the Order Looks That Way

The three `sum()` calls run **first**, and each one prints its own `a, b, c` line. Only after all three have finished do the three "The sum of these numbers is:" lines run. So the output is not "call, result, call, result". It is "three calls, then three results".

> 🔎 **The double space:** the string `"The sum of these numbers is: "` ends with a space, and `console.log` also adds a space between its arguments. That is why there are two spaces before each number.

---

## ⚖️ Declarations vs Arrow Functions

<table>
  <tr>
    <th></th>
    <th>Function declaration</th>
    <th>Arrow function</th>
  </tr>
  <tr>
    <td><b>Syntax</b></td>
    <td><code>function sum(a, b) { ... }</code></td>
    <td><code>const sum = (a, b) =&gt; { ... }</code></td>
  </tr>
  <tr>
    <td><b>Can be called before it's written?</b></td>
    <td align="center">✅ Yes (hoisted)</td>
    <td align="center">❌ No (ReferenceError)</td>
  </tr>
  <tr>
    <td><b>Short one-line form</b></td>
    <td align="center">No</td>
    <td align="center">✅ <code>(a, b) =&gt; a + b</code></td>
  </tr>
  <tr>
    <td><b>Has its own <code>this</code></b></td>
    <td align="center">Yes</td>
    <td align="center">No (it uses the surrounding <code>this</code>). I'll cover this later.</td>
  </tr>
  <tr>
    <td><b>Great for</b></td>
    <td>Main, named functions</td>
    <td>Short helpers and callbacks, such as in <code>map</code> and <code>filter</code></td>
  </tr>
</table>

**Hoisting in action:**

```js
console.log(add(2, 3));        // 5  <- works, even though add() is written below
function add(a, b) {
  return a + b;
}

console.log(mul(2, 3));        // ReferenceError: Cannot access 'mul' before initialization
const mul = (a, b) => a * b;
```

This connects to the variables project: an arrow function stored in a `const` follows the same rules as any `const`, including the temporal dead zone.

---

## 🔄 Preview: Turning My Loop Problems into Functions

The previous project solved ten problems with hard-coded inputs. Functions let me solve each one for **any** input. Here are three examples (not yet in `index.js`):

```js
// Q1 of conditionals: even or odd, as an arrow function with implicit return
const isEven = (n) => n % 2 === 0;

// Largest number in an array
function largest(nums) {
  let max = nums[0];
  for (let i = 1; i < nums.length; i++) {
    if (nums[i] > max) {
      max = nums[i];
    }
  }
  return max;
}

// Prime check: the early `return` replaces both the flag variable and the break
function isPrime(n) {
  if (n < 2) return false;
  for (let d = 2; d * d <= n; d++) {
    if (n % d === 0) return false;
  }
  return true;
}
```

<table>
  <tr>
    <th>Call</th>
    <th>Result</th>
  </tr>
  <tr><td><code>isEven(7)</code></td><td><code>false</code></td></tr>
  <tr><td><code>isEven(10)</code></td><td><code>true</code></td></tr>
  <tr><td><code>largest([4, 9, 2, 15, 7])</code></td><td><code>15</code></td></tr>
  <tr><td><code>largest([3, 1])</code></td><td><code>3</code></td></tr>
  <tr><td><code>isPrime(47)</code></td><td><code>true</code></td></tr>
  <tr><td><code>isPrime(49)</code></td><td><code>false</code></td></tr>
  <tr><td><code>isPrime(1)</code></td><td><code>false</code></td></tr>
</table>

Now I can test many inputs with one loop and finally see **every branch** of a problem:

```js
[1, 2, 15, 47, 49].forEach((n) => console.log(n, isPrime(n)));
```

---

## 🏋️ Practice Tasks

Here are **35 extra practice tasks** I wrote to go beyond `index.js`. Every solution below was run in Node.js and the expected output matches.

**How to use this section**

1. Create a file called `practice.js` inside `04-functions/`.
2. Read the task table and write the function **yourself** first.
3. Paste the test lines under it and compare your output with the `// expected` comments.
4. Only then open the solution to compare.

> 💡 Node may print arrays with more than 6 numbers across several lines. The values are the same, only the layout differs.

<table>
  <tr><th>Part</th><th>Focus</th><th>Tasks</th></tr>
  <tr><td>A</td><td>Warm-ups: parameters, defaults, <code>return</code>, arrows</td><td>8</td></tr>
  <tr><td>B</td><td>Conditions and loops inside functions</td><td>8</td></tr>
  <tr><td>C</td><td>Challenges: functions calling functions, arrays, functions as values</td><td>7</td></tr>
  <tr><td>D</td><td>Find the bug</td><td>5</td></tr>
  <tr><td>E</td><td>Your turn: no solutions shown</td><td>7</td></tr>
</table>

---

### 🅰️ Part A: Warm-ups

<table>
  <tr><th>#</th><th>Function</th><th>Task</th><th>Concept</th></tr>
  <tr><td>1</td><td><code>greet(name, greeting = "Hello")</code></td><td>Return <code>"Hello, Ali!"</code>. The greeting is optional.</td><td>Default parameter</td></tr>
  <tr><td>2</td><td><code>square(n)</code></td><td>Return <code>n * n</code> as an arrow function.</td><td>Implicit return</td></tr>
  <tr><td>3</td><td><code>isEven(n)</code></td><td>Return <code>true</code> or <code>false</code>.</td><td>Returning a boolean</td></tr>
  <tr><td>4</td><td><code>maxOf(a, b)</code></td><td>Return the larger number using the ternary operator.</td><td>Ternary</td></tr>
  <tr><td>5</td><td><code>celsiusToFahrenheit(c)</code></td><td>Convert with <code>c * 9 / 5 + 32</code>.</td><td>Formulas</td></tr>
  <tr><td>6</td><td><code>circleArea(r)</code></td><td>Return the area rounded to 2 decimals.</td><td><code>Math.PI</code>, <code>toFixed</code></td></tr>
  <tr><td>7</td><td><code>average(a, b, c)</code></td><td>Return the average of three numbers.</td><td>Arithmetic</td></tr>
  <tr><td>8</td><td><code>printTable(num, upTo = 10)</code></td><td>Print the multiplication table. It prints, it does not return.</td><td>Loop inside a function</td></tr>
</table>

**Test it**

```js
console.log(greet("Ali"));                        // Hello, Ali!
console.log(greet("Sara", "Welcome"));            // Welcome, Sara!
console.log(square(5));                           // 25
console.log(isEven(10), isEven(7));               // true false
console.log(maxOf(3, 9), maxOf(12, 4));           // 9 12
console.log(celsiusToFahrenheit(100));            // 212
console.log(celsiusToFahrenheit(0));              // 32
console.log(celsiusToFahrenheit(-40));            // -40
console.log(circleArea(5));                       // 78.54
console.log(average(10, 20, 30));                 // 20
printTable(5, 3);                                 // 5 x 1 = 5, 5 x 2 = 10, 5 x 3 = 15 (one per line)
```

<details>
<summary><b>👀 Show solutions for Part A</b></summary>

```js
function greet(name, greeting = "Hello") {
  return greeting + ", " + name + "!";
}

const square = (n) => n * n;

const isEven = (n) => n % 2 === 0;

const maxOf = (a, b) => (a > b ? a : b);

const celsiusToFahrenheit = (c) => (c * 9) / 5 + 32;

const circleArea = (r) => Number((Math.PI * r * r).toFixed(2));

const average = (a, b, c) => (a + b + c) / 3;

function printTable(num, upTo = 10) {
  for (let i = 1; i <= upTo; i++) {
    console.log(num + " x " + i + " = " + num * i);
  }
}
```

**Notes:** `toFixed` returns a string, so `Number(...)` turns it back into a number. In `greet`, the default parameter goes **last**, which matters again in Part D.

</details>

---

### 🅱️ Part B: Conditions and Loops Inside Functions

<table>
  <tr><th>#</th><th>Function</th><th>Task</th><th>Concept</th></tr>
  <tr><td>9</td><td><code>countVowels(text)</code></td><td>Count the vowels, ignoring case.</td><td><code>for...of</code>, <code>includes</code></td></tr>
  <tr><td>10</td><td><code>fizzBuzz(n)</code></td><td>Return <code>"FizzBuzz"</code> for multiples of 15, <code>"Fizz"</code> for 3, <code>"Buzz"</code> for 5, otherwise <code>n</code>.</td><td>Order of conditions</td></tr>
  <tr><td>11</td><td><code>factorial(n)</code></td><td>Return <code>n!</code>. Return <code>null</code> for negative numbers.</td><td>Loop + guard clause</td></tr>
  <tr><td>12</td><td><code>reverseString(text)</code></td><td>Return the text reversed.</td><td>Backwards loop</td></tr>
  <tr><td>13</td><td><code>isPalindrome(text)</code></td><td>Ignore case. Reuse <code>reverseString</code>.</td><td>A function calling a function</td></tr>
  <tr><td>14</td><td><code>sumOfDigits(n)</code></td><td>Add the digits. Negative numbers should work too.</td><td><code>while</code>, <code>%</code>, <code>Math.floor</code></td></tr>
  <tr><td>15</td><td><code>getGrade(marks)</code></td><td>A ≥ 90, B ≥ 80, C ≥ 70, D ≥ 60, else F. Return <code>"Invalid"</code> outside 0 to 100.</td><td>Early returns</td></tr>
  <tr><td>16</td><td><code>calculateBill(units)</code></td><td>First 100 units cost 10 each, the next 200 cost 15 each, anything above 300 costs 20 each.</td><td>Tiered pricing</td></tr>
</table>

**Test it**

```js
console.log(countVowels("Programming"));          // 3
console.log(countVowels("Apple"));                // 2
console.log(countVowels("rhythm"));               // 0
console.log(fizzBuzz(3), fizzBuzz(5), fizzBuzz(15), fizzBuzz(7)); // Fizz Buzz FizzBuzz 7
console.log(factorial(5));                        // 120
console.log(factorial(0));                        // 1
console.log(factorial(-3));                       // null
console.log(reverseString("hello"));              // olleh
console.log(isPalindrome("Level"), isPalindrome("hello")); // true false
console.log(sumOfDigits(1234));                   // 10
console.log(sumOfDigits(-905));                   // 14
console.log(getGrade(95), getGrade(82), getGrade(70), getGrade(59), getGrade(101)); // A B C F Invalid
console.log(calculateBill(80), calculateBill(250), calculateBill(350)); // 800 3250 5000
```

<details>
<summary><b>👀 Show solutions for Part B</b></summary>

```js
function countVowels(text) {
  const vowels = "aeiou";
  let count = 0;
  for (const ch of text.toLowerCase()) {
    if (vowels.includes(ch)) {
      count++;
    }
  }
  return count;
}

function fizzBuzz(n) {
  if (n % 15 === 0) return "FizzBuzz"; // check 15 first!
  if (n % 3 === 0) return "Fizz";
  if (n % 5 === 0) return "Buzz";
  return n;
}

function factorial(n) {
  if (n < 0) return null;
  let result = 1;
  for (let i = 2; i <= n; i++) {
    result *= i;
  }
  return result;
}

function reverseString(text) {
  let reversed = "";
  for (let i = text.length - 1; i >= 0; i--) {
    reversed += text[i];
  }
  return reversed;
}

function isPalindrome(text) {
  const clean = text.toLowerCase();
  return clean === reverseString(clean);
}

function sumOfDigits(n) {
  let remaining = Math.abs(n);
  let sum = 0;
  while (remaining > 0) {
    sum += remaining % 10;
    remaining = Math.floor(remaining / 10);
  }
  return sum;
}

function getGrade(marks) {
  if (marks < 0 || marks > 100) return "Invalid";
  if (marks >= 90) return "A";
  if (marks >= 80) return "B";
  if (marks >= 70) return "C";
  if (marks >= 60) return "D";
  return "F";
}

function calculateBill(units) {
  if (units <= 100) return units * 10;
  if (units <= 300) return 100 * 10 + (units - 100) * 15;
  return 100 * 10 + 200 * 15 + (units - 300) * 20;
}
```

**Notes:** `fizzBuzz` must test `15` first, otherwise `15` would stop at `Fizz`. In `getGrade`, each `return` ends the function, so no `else` is needed.

</details>

---

### 🧩 Part C: Challenges

<table>
  <tr><th>#</th><th>Function</th><th>Task</th><th>Concept</th></tr>
  <tr><td>17</td><td><code>calculate(a, operator, b)</code></td><td>Support <code>+ - * /</code>. Return <code>"Cannot divide by zero"</code> and <code>"Unknown operator"</code> when needed.</td><td>Several returns</td></tr>
  <tr><td>18</td><td><code>isLeapYear(year)</code></td><td>Divisible by 4, except centuries, unless divisible by 400.</td><td>Combined conditions</td></tr>
  <tr><td>19</td><td><code>daysInYear(year)</code></td><td>Return 366 or 365. Reuse <code>isLeapYear</code>.</td><td>Function calling function</td></tr>
  <tr><td>20</td><td><code>primesUpTo(limit)</code></td><td>Return an array of all primes up to <code>limit</code>. Reuse <code>isPrime</code> from the preview section.</td><td>Arrays, <code>push</code></td></tr>
  <tr><td>21</td><td><code>fibonacci(count)</code></td><td>Return the first <code>count</code> Fibonacci numbers.</td><td>Swapping two values</td></tr>
  <tr><td>22</td><td><code>applyTwice(fn, x)</code></td><td>Call <code>fn</code> on <code>x</code>, then call it again on the result.</td><td>Functions as arguments</td></tr>
  <tr><td>23</td><td><code>multiplier(factor)</code></td><td>Return a <b>new function</b> that multiplies by <code>factor</code>.</td><td>Returning a function (a preview of closures)</td></tr>
</table>

**Test it**

```js
console.log(calculate(8, "+", 2));                // 10
console.log(calculate(8, "-", 2));                // 6
console.log(calculate(8, "*", 2));                // 16
console.log(calculate(8, "/", 2));                // 4
console.log(calculate(8, "/", 0));                // Cannot divide by zero
console.log(calculate(8, "%", 2));                // Unknown operator
console.log(isLeapYear(2024), isLeapYear(1900), isLeapYear(2000)); // true false true
console.log(daysInYear(2024), daysInYear(2023));  // 366 365
console.log(primesUpTo(30));                      // 2, 3, 5, 7, 11, 13, 17, 19, 23, 29
console.log(fibonacci(10));                       // 0, 1, 1, 2, 3, 5, 8, 13, 21, 34
console.log(fibonacci(1), fibonacci(0));          // [ 0 ] []
console.log(applyTwice(square, 3));               // 81
console.log(applyTwice((x) => x + 5, 10));        // 20
const double = multiplier(2);
const triple = multiplier(3);
console.log(double(5), triple(5));                // 10 15
```

<details>
<summary><b>👀 Show solutions for Part C</b></summary>

```js
function calculate(a, operator, b) {
  if (operator === "+") return a + b;
  if (operator === "-") return a - b;
  if (operator === "*") return a * b;
  if (operator === "/") {
    if (b === 0) return "Cannot divide by zero";
    return a / b;
  }
  return "Unknown operator";
}

function isLeapYear(year) {
  return (year % 4 === 0 && year % 100 !== 0) || year % 400 === 0;
}

function daysInYear(year) {
  return isLeapYear(year) ? 366 : 365;
}

// from the preview section
function isPrime(n) {
  if (n < 2) return false;
  for (let d = 2; d * d <= n; d++) {
    if (n % d === 0) return false;
  }
  return true;
}

function primesUpTo(limit) {
  const primes = [];
  for (let n = 2; n <= limit; n++) {
    if (isPrime(n)) {
      primes.push(n);
    }
  }
  return primes;
}

function fibonacci(count) {
  const result = [];
  let a = 0, b = 1;
  for (let i = 0; i < count; i++) {
    result.push(a);
    [a, b] = [b, a + b]; // swap without a temp variable
  }
  return result;
}

const applyTwice = (fn, x) => fn(fn(x));

function multiplier(factor) {
  return (x) => x * factor;
}
```

**Notes:** `multiplier(2)` returns a function that **remembers** `factor = 2`. That memory is called a *closure*, and it is on the roadmap. `applyTwice(square, 3)` uses the `square` function from Part A.

</details>

---

### 🐞 Part D: Find the Bug

Each snippet below has one bug. Read the code, predict the output, then open the fix.

<table>
  <tr><th>#</th><th>Buggy code</th><th>What it prints</th></tr>
  <tr>
    <td>24</td>
    <td><pre>function add(a, b) {
  a + b;
}
console.log(add(2, 3));</pre></td>
    <td><code>undefined</code></td>
  </tr>
  <tr>
    <td>25</td>
    <td><pre>function greet(greeting = "Hello", name) {
  return greeting + ", " + name + "!";
}
console.log(greet("Ali"));</pre></td>
    <td><code>Ali, undefined!</code></td>
  </tr>
  <tr>
    <td>26</td>
    <td><pre>function add(a, b) {
  return a + b;
}
const total = add;
console.log(total);</pre></td>
    <td><code>[Function: add]</code> instead of a number</td>
  </tr>
  <tr>
    <td>27</td>
    <td><pre>function sumTo(n) {
  let sum = 0;
  for (let i = 1; i <= n; i++) {
    sum += i;
    return sum;
  }
}
console.log(sumTo(5));</pre></td>
    <td><code>1</code> instead of 15</td>
  </tr>
  <tr>
    <td>28</td>
    <td><pre>const double = (x) => {
  x * 2;
};
console.log(double(4));</pre></td>
    <td><code>undefined</code></td>
  </tr>
</table>

<details>
<summary><b>🔧 Show the fixes</b></summary>

<table>
  <tr><th>#</th><th>Cause</th><th>Fix</th></tr>
  <tr>
    <td>24</td>
    <td>No <code>return</code>. The sum is calculated and thrown away, so the function returns <code>undefined</code>.</td>
    <td><code>return a + b;</code></td>
  </tr>
  <tr>
    <td>25</td>
    <td>A default parameter placed first is only used when you pass <code>undefined</code> explicitly. <code>"Ali"</code> lands in <code>greeting</code>.</td>
    <td>Put defaults last: <code>function greet(name, greeting = "Hello")</code>. Now it prints <code>Hello, Ali!</code></td>
  </tr>
  <tr>
    <td>26</td>
    <td>Missing parentheses. <code>add</code> is the function itself, <code>add(2, 3)</code> is the call.</td>
    <td><code>const total = add(2, 3);</code> prints <code>5</code></td>
  </tr>
  <tr>
    <td>27</td>
    <td><code>return</code> sits <b>inside</b> the loop, so the function exits after the first pass.</td>
    <td>Move <code>return sum;</code> after the closing brace of the loop. <code>sumTo(5)</code> gives <code>15</code></td>
  </tr>
  <tr>
    <td>28</td>
    <td>Curly braces turn the arrow function into a normal body, and a normal body needs <code>return</code>.</td>
    <td><code>const double = (x) => x * 2;</code> or <code>(x) => { return x * 2; }</code>. <code>double(4)</code> gives <code>8</code></td>
  </tr>
</table>

</details>

---

### 🎯 Part E: Your Turn (No Solutions)

These are for you. The expected results are given so you can check yourself.

<table>
  <tr><th>#</th><th>Function</th><th>Task</th><th>Check with</th></tr>
  <tr><td>29</td><td><code>gcd(a, b)</code></td><td>Greatest common divisor. Hint: keep replacing <code>(a, b)</code> with <code>(b, a % b)</code> until <code>b</code> is 0.</td><td><code>gcd(48, 18)</code> → <code>6</code><br><code>gcd(7, 13)</code> → <code>1</code></td></tr>
  <tr><td>30</td><td><code>isArmstrong(n)</code></td><td>True if the sum of each digit raised to the number of digits equals the number.</td><td><code>153</code> → <code>true</code><br><code>154</code> → <code>false</code><br><code>9474</code> → <code>true</code></td></tr>
  <tr><td>31</td><td><code>secondLargest(nums)</code></td><td>Return the second largest value in an array without sorting it.</td><td><code>[4, 9, 2, 15, 7]</code> → <code>9</code></td></tr>
  <tr><td>32</td><td><code>countWords(sentence)</code></td><td>Count the words in a sentence.</td><td><code>"I love JavaScript"</code> → <code>3</code></td></tr>
  <tr><td>33</td><td><code>capitalize(word)</code></td><td>Make the first letter uppercase.</td><td><code>"javascript"</code> → <code>"Javascript"</code></td></tr>
  <tr><td>34</td><td><code>sumArray(arr)</code></td><td>Add up an array. An empty array gives 0.</td><td><code>[1, 2, 3, 4]</code> → <code>10</code><br><code>[]</code> → <code>0</code></td></tr>
  <tr><td>35</td><td><code>isSorted(arr)</code></td><td>True if the numbers are in ascending order.</td><td><code>[1, 2, 3]</code> → <code>true</code><br><code>[3, 1, 2]</code> → <code>false</code></td></tr>
</table>

**Bonus:** `primesUpTo(100).length` should be `25`.

### ✅ Practice Progress

- [ ] Part A: warm-ups (1 to 8)
- [ ] Part B: conditions and loops (9 to 16)
- [ ] Part C: challenges (17 to 23)
- [ ] Part D: find the bug (24 to 28)
- [ ] Part E: your turn (29 to 35)
- [ ] Rewrite **my own** earlier loop problems as functions with parameters and `return`

---

## 🔍 Known Gaps & Improvements

Here is what I found while reviewing the code, with a fix for each.

<details>
<summary><b>1. 🔇 <code>nice()</code> is defined but never called</b></summary>

<br>

Defining a function doesn't run it, so nothing from `nice` appears in the output. Add calls:

```js
nice("Ali");
nice("Sara");
```

</details>

<details>
<summary><b>2. 🌐 <code>result1 = sum(3, 2)</code> has no <code>let</code> or <code>const</code></b></summary>

<br>

Without a declaration keyword, JavaScript creates an **accidental global variable**. In strict mode, it throws a `ReferenceError`. Use `const`:

```js
const result1 = sum(3, 2);
const result2 = sum(7, 5);
const result3 = sum(3, 13, 1);
```

</details>

<details>
<summary><b>3. 🔠 Double space in the output</b></summary>

<br>

Remove the trailing space inside the string, because `console.log` already adds one:

```js
console.log("The sum of these numbers is:", result1);
```

</details>

<details>
<summary><b>4. 🧼 A function should do one job</b></summary>

<br>

`sum` both **prints** (`console.log(a, b, c)`) and **returns**. The print is useful while learning, but a finished function should usually return a value and leave printing to the caller. Remove the debug line once you understand the parameters.

</details>

<details>
<summary><b>5. 🏷️ Naming</b></summary>

<br>

<table>
  <tr>
    <th>Current name</th>
    <th>Suggestion</th>
    <th>Why</th>
  </tr>
  <tr>
    <td><code>nice</code></td>
    <td><code>complimentUser</code> or <code>praise</code></td>
    <td>Function names read best as <b>verbs</b>.</td>
  </tr>
  <tr>
    <td><code>func1</code></td>
    <td><code>logWithLabel</code> or similar</td>
    <td>A name should say what the function <b>does</b>.</td>
  </tr>
  <tr>
    <td><code>result1</code>, <code>result2</code>, <code>result3</code></td>
    <td>Fine for practice</td>
    <td>With real data, use meaningful names such as <code>total</code>.</td>
  </tr>
</table>

</details>

<details>
<summary><b>6. ✍️ Inconsistent semicolons</b></summary>

<br>

The file uses a semicolon after `func1(34);` but not after most other lines. JavaScript allows both (it inserts missing semicolons automatically), but mixing styles is confusing and can occasionally cause bugs. Pick one style, or install the **Prettier** extension in VS Code to format automatically on save.

</details>

<details>
<summary><b>7. 🧱 Name clash if loaded together with the loops project</b></summary>

<br>

In Node, each file is its own module, so there's no problem. If two files were loaded on **one browser page**, a top-level `function sum` here and a top-level `let sum` in the loops project would clash (`Identifier 'sum' has already been declared`). Load one file per page, or use different names.

</details>

---

## 🔬 Try It Yourself

<details>
<summary><b>Click to expand the experiment steps</b></summary>

<br>

1. **Call `nice`.** Add `nice("Ali")`, `nice("Sara")`, and `nice("Omar")`.
2. **Print what `nice` returns.** Run `console.log(nice("Ali"))` and see the `undefined` at the end.
3. **Explore defaults.** Predict, then run: `sum(1, 2)`, `sum(1, 2, 3)`, `sum(1, 2, undefined)`, `sum(1, 2, null)`.
4. **Break it on purpose.** Run `sum(1)` and look at the `NaN`. Then give `b` a default of `0`.
5. **Return too early.** Put a `return` in the middle of a function and see the lines below it never run.
6. **Convert to arrow functions.** Rewrite `sum` as `const sum = (a, b, c = 3) => a + b + c;` and confirm the same results.
7. **Test hoisting.** Call `add(2, 3)` above a regular declaration, then call an arrow function above its `const`, and compare.
8. **Write the loop problems as functions.** Start with `isEven`, then `largest`, then `isPrime`, and test each with several inputs.
9. **Write a function with a function.** Write `average(a, b)` that calls `sum`-style logic and divides by 2.
10. **Use an arrow function as a callback.** Run `[1, 2, 3].map((x) => x * 2)` and see `[2, 4, 6]`.

</details>

---

## 🚀 How to Run

You need [Node.js](https://nodejs.org) installed.

```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/<your-repo-name>.git

# 2. Move into the project
cd <your-repo-name>/04-functions

# 3. Run the file
node index.js

# 4. Run my practice solutions (after you create practice.js)
node practice.js
```

**Or run in the browser:** create an HTML page that loads the script, open it, and check the **Console** tab (`F12`).

```html
<script src="index.js"></script>
```

💡 **Tip:** Use the VS Code **Code Runner** extension (or the built-in terminal) to run a file with one click.

---

## 📚 Cheat Sheet

### Ways to Write a Function

```js
// 1. Declaration
function add(a, b) { return a + b; }

// 2. Arrow function with a block body
const add = (a, b) => { return a + b; };

// 3. Arrow function with an implicit return
const add = (a, b) => a + b;

// 4. With a default parameter
function greet(name = "friend") { return "Hello " + name; }
```

### Quick Rules

| Rule | Example |
|---|---|
| Parentheses **run** a function | `sum(3, 2)` runs it, `sum` alone is just the function |
| `return` sends a value back and ends the function | `return a + b;` |
| No `return` means `undefined` | `console.log(nice("Ali"))` ends with `undefined` |
| Defaults apply only to `undefined` | `sum(3, 2, null)` does **not** use the default |
| Missing arguments are `undefined` | `sum(3)` gives `NaN` |
| Extra arguments are ignored | `sum(1, 2, 3, 4)` gives `6` |

### Choosing a Form

| Situation | Use |
|---|---|
| A main, named function used in many places | Declaration |
| A short helper or a callback | Arrow function |
| A one-line calculation | Arrow function with an implicit return |

---

## 🎓 Key Takeaways

<table>
  <tr>
    <td>✅</td>
    <td>A function packages code under a name so it can be reused with different inputs (<b>Don't Repeat Yourself</b>).</td>
  </tr>
  <tr>
    <td>✅</td>
    <td>Defining a function does not run it. It runs only when it is <b>called</b>.</td>
  </tr>
  <tr>
    <td>✅</td>
    <td><b>Parameters</b> are the placeholders in the definition. <b>Arguments</b> are the real values in the call.</td>
  </tr>
  <tr>
    <td>✅</td>
    <td><code>return</code> hands a value back and ends the function. <code>console.log</code> only displays a value.</td>
  </tr>
  <tr>
    <td>✅</td>
    <td>A function with no <code>return</code> gives back <code>undefined</code>.</td>
  </tr>
  <tr>
    <td>✅</td>
    <td>Default parameters (<code>c = 3</code>) fill in only when the argument is missing or <code>undefined</code>.</td>
  </tr>
  <tr>
    <td>✅</td>
    <td>Arrow functions are a shorter syntax, and with one expression they can return without the word <code>return</code>.</td>
  </tr>
  <tr>
    <td>✅</td>
    <td>Function declarations are hoisted. Arrow functions stored in a <code>const</code> are not.</td>
  </tr>
  <tr>
    <td>✅</td>
    <td>Functions make earlier work testable: one function, many inputs.</td>
  </tr>
  <tr>
    <td>✅</td>
    <td>Functions can call other functions, return arrays, take functions as arguments, and even return new functions.</td>
  </tr>
  <tr>
    <td>✅</td>
    <td>Most function bugs are one of four things: a missing <code>return</code>, <code>return</code> in the wrong place, missing <code>()</code> on a call, or a default parameter in the wrong position.</td>
  </tr>
</table>

---

## 🗺️ Roadmap

- [x] Variables: `var`, `let`, `const`
- [x] Operators, `if / else`, and the ternary operator
- [x] Loops and ten loop problems
- [x] Functions: declarations, parameters, defaults, `return`, and arrow functions
- [x] Practice tasks A to E written (35 functions)
- [ ] Solve all [practice tasks](#-practice-tasks) in my own `practice.js`
- [ ] Fix the [known gaps](#-known-gaps--improvements)
- [ ] Rewrite the loop and conditional problems as reusable functions
- [ ] Function scope and closures
- [ ] Arrays in depth, with `map`, `filter`, and `reduce` (arrow functions as callbacks)
- [ ] Objects and methods, and what `this` means
- [ ] DOM manipulation: connect JavaScript to my CSS projects

---

<div align="center">

### ⭐ If you found this helpful, consider giving the repo a star!

Made with ❤️ while learning JavaScript

</div>
