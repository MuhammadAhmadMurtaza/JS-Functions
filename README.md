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
10. [Known Gaps & Improvements](#-known-gaps--improvements)
11. [Try It Yourself](#-try-it-yourself)
12. [How to Run](#-how-to-run)
13. [Cheat Sheet](#-cheat-sheet)
14. [Key Takeaways](#-key-takeaways)
15. [Roadmap](#-roadmap)

---

## 📂 Project Structure

```
js-fundamentals/
│
└── 04-functions/
    └── index.js      # nice(), sum(), and an arrow function
```

> 💡 Rename the folder to match your own layout.

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
</table>

---

## 🗺️ Roadmap

- [x] Variables: `var`, `let`, `const`
- [x] Operators, `if / else`, and the ternary operator
- [x] Loops and ten loop problems
- [x] Functions: declarations, parameters, defaults, `return`, and arrow functions
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
