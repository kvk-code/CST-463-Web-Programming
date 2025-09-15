# JavaScript Variable Declarations: var, let, and const

## Overview

JavaScript provides three keywords for declaring variables: `var`, `let`, and `const`. Understanding their differences is crucial for writing clean, bug-free JavaScript code.

## 1. var Declaration

### Characteristics
- **Scope**: Function-scoped or globally-scoped
- **Hoisting**: Hoisted and initialized with `undefined`
- **Redeclaration**: Allowed within the same scope
- **Reassignment**: Allowed

### Examples

```javascript
// Basic var declaration
var name = "John";
console.log(name); // Output: John

// Hoisting behavior
console.log(age); // Output: undefined (not an error!)
var age = 25;
console.log(age); // Output: 25

// Function scoping
function example() {
    if (true) {
        var x = 10;
    }
    console.log(x); // Output: 10 (accessible outside the block)
}

// Redeclaration allowed
var score = 100;
var score = 200; // No error
console.log(score); // Output: 200
```

### Problems with var

#### Problem 1: Unexpected hoisting
```javascript
console.log(message); // undefined instead of error
if (false) {
    var message = "Hello";
}
```

#### Problem 2: Loop variable leakage
```javascript
for (var i = 0; i < 3; i++) {
    setTimeout(() => console.log(i), 100); // Outputs: 3, 3, 3
}
```

**Why does this happen?**
1. The loop runs quickly and schedules three `setTimeout` callbacks (one for each iteration: i=0, i=1, i=2)
2. The loop finishes **before** any of the timeouts fire
3. After the loop completes, `i` has the value `3` (the condition that stopped the loop)
4. When the timeouts execute after 100ms, all three callbacks look at the same `i` variable, which is now `3`
5. Result: All three print `3` instead of the expected `0, 1, 2`

**Visual timeline:**
- Loop Iteration 1: i = 0 → schedules a callback (runs later)
- Loop Iteration 2: i = 1 → schedules a callback (runs later)  
- Loop Iteration 3: i = 2 → schedules a callback (runs later)
- After the loop: i = 3
- Now, all callbacks run (after 100ms), and each sees i = 3

## 2. let Declaration

### Characteristics
- **Scope**: Block-scoped
- **Hoisting**: Hoisted but not initialized (Temporal Dead Zone)
- **Redeclaration**: Not allowed in the same scope
- **Reassignment**: Allowed

### Examples

```javascript
// Basic let declaration
let username = "Alice";
console.log(username); // Output: Alice

// Block scoping
function example() {
    if (true) {
        let y = 20;
        console.log(y); // Output: 20
    }
    // console.log(y); // ReferenceError: y is not defined
}

// Temporal Dead Zone
// console.log(city); // ReferenceError: Cannot access 'city' before initialization
let city = "Paris";
console.log(city); // Output: Paris

// Redeclaration not allowed
let points = 50;
// let points = 75; // SyntaxError: Identifier 'points' has already been declared

// Reassignment allowed
let counter = 0;
counter = 1;
console.log(counter); // Output: 1
```

### How let fixes the loop problem

```javascript
for (let i = 0; i < 3; i++) {
    setTimeout(() => console.log(i), 100); // Outputs: 0, 1, 2
}
```

### let in for loops: Unique variable for each iteration

**Key concept**: When using `let` in a `for` loop, JavaScript creates a **new, separate block-scoped variable** for each iteration of the loop.

**How it works:**
- **Iteration 1**: JavaScript creates a new `i` for this cycle and sets it to `0`
- **Iteration 2**: JavaScript creates another new `i` just for this cycle and sets it to `1`  
- **Iteration 3**: Again a new `i` is created for this cycle, with a value of `2`

Each iteration's `i` is **block-scoped** and exists only during its specific iteration. Any asynchronous functions (like `setTimeout`) created during that iteration will "remember" the value of `i` from their specific iteration.

**Important note**: The counter does **NOT** reset to 0 every time. The loop control keeps incrementing as expected, but each iteration gets its own copy of the variable with the correct value.

#### Visual comparison:

| Declaration | What happens | Output after 100ms |
|-------------|--------------|-------------------|
| `var i` | All callbacks share the same `i` variable | 3, 3, 3 |
| `let i` | Each callback gets its own copy of `i` | 0, 1, 2 |

### Other ways to fix the var problem

If you must use `var`, you can use an **IIFE (Immediately Invoked Function Expression)**:

```javascript
for (var i = 0; i < 3; i++) {
    (function(j) {
        setTimeout(() => console.log(j), 100);
    })(i);
}
// Output: 0, 1, 2
```

This creates a new function scope for each iteration and "captures" the current value of `i`.

## 3. const Declaration

### Characteristics
- **Scope**: Block-scoped
- **Hoisting**: Hoisted but not initialized (Temporal Dead Zone)
- **Redeclaration**: Not allowed in the same scope
- **Reassignment**: Not allowed (immutable binding)

### Examples

```javascript
// Basic const declaration
const PI = 3.14159;
console.log(PI); // Output: 3.14159

// Must be initialized
// const value; // SyntaxError: Missing initializer in const declaration

// Cannot be reassigned
const maxItems = 100;
// maxItems = 200; // TypeError: Assignment to constant variable

// Block scoped
if (true) {
    const secret = "top secret";
    console.log(secret); // Output: top secret
}
// console.log(secret); // ReferenceError

// Objects and arrays can be mutated
const person = { name: "Bob", age: 30 };
person.age = 31; // This is allowed
console.log(person); // Output: { name: "Bob", age: 31 }

const colors = ["red", "green"];
colors.push("blue"); // This is allowed
console.log(colors); // Output: ["red", "green", "blue"]

// But you cannot reassign the reference
// person = {}; // TypeError: Assignment to constant variable
// colors = []; // TypeError: Assignment to constant variable
```

## Comparison Table

| Feature | var | let | const |
|---------|-----|-----|-------|
| **Scope** | Function/Global | Block | Block |
| **Hoisting** | Yes, initialized as `undefined` | Yes, but uninitialized (TDZ) | Yes, but uninitialized (TDZ) |
| **Redeclaration** | ✅ Allowed | ❌ Not allowed | ❌ Not allowed |
| **Reassignment** | ✅ Allowed | ✅ Allowed | ❌ Not allowed |
| **Initialization** | Optional | Optional | Required |
| **Temporal Dead Zone** | No | Yes | Yes |
| **Loop behavior** | Shares variable across iterations | Creates new variable per iteration | Creates new variable per iteration |

## When to Use Which?

### Use `const` by default
```javascript
const API_URL = "https://api.example.com";
const users = [];
const config = { theme: "dark", language: "en" };
```

**When to use:**
- For values that won't be reassigned
- For objects and arrays (you can still modify their contents)
- For function declarations
- For imported modules

### Use `let` when you need reassignment
```javascript
let currentUser = null;
let attempts = 0;
let isLoading = false;

for (let i = 0; i < items.length; i++) {
    // loop logic
}
```

**When to use:**
- For variables that will be reassigned
- For loop counters
- For conditional assignments
- When you need block scoping

### Avoid `var` in modern JavaScript
```javascript
// Don't do this in new code
var oldStyle = "avoid this";

// Use this instead
const modernStyle = "prefer this";
```

**Only use var when:**
- Working with legacy codebases
- You specifically need function-scoping behavior
- Maintaining compatibility with very old browsers

## Best Practices

1. **Default to `const`**: Start with `const` and change to `let` only if you need reassignment
2. **Avoid `var`**: Use `let` or `const` instead for better scoping and fewer bugs
3. **Declare at the top**: Declare variables at the top of their scope for clarity
4. **Use descriptive names**: Choose meaningful variable names
5. **Initialize when possible**: Initialize variables when you declare them

```javascript
// Good practices
const MAX_RETRIES = 3;
let currentRetry = 0;
const userData = { name: "", email: "" };

// Avoid
var x = 1;
var data;
```

## Common Mistakes to Avoid

### 1. Using var in loops with asynchronous callbacks
```javascript
// Problem
for (var i = 0; i < 3; i++) {
    setTimeout(() => console.log(i), 100); // Always prints 3, 3, 3
}

// Solution
for (let i = 0; i < 3; i++) {
    setTimeout(() => console.log(i), 100); // Prints 0, 1, 2
}
```

**Why this happens:**
- `var` creates only one variable shared across all iterations
- All callbacks reference the same variable, which has the final value after the loop ends
- `let` creates a new variable for each iteration, so each callback has its own copy

### 2. Assuming const makes objects immutable
```javascript
// This works (modifying object properties)
const user = { name: "John" };
user.name = "Jane"; // ✅ Allowed

// This doesn't work (reassigning the variable)
// user = { name: "Bob" }; // ❌ TypeError
```

### 3. Accessing variables before declaration
```javascript
// With var - returns undefined
console.log(a); // undefined
var a = 5;

// With let/const - throws error
// console.log(b); // ReferenceError
let b = 10;
```

## Key Takeaways

1. **Scope matters**: Block scope (`let`/`const`) is safer than function scope (`var`)
2. **Hoisting behavior**: `var` is hoisted and initialized, `let`/`const` are hoisted but not initialized
3. **Loop behavior**: `let` creates new variables for each iteration, `var` shares one variable
4. **Modern best practice**: Use `const` by default, `let` when reassignment is needed, avoid `var`
5. **Temporal Dead Zone**: With `let`/`const`, variables cannot be accessed before declaration

## Summary

- **`const`**: Use for values that won't be reassigned (default choice)
- **`let`**: Use for variables that need reassignment or when you need block scoping
- **`var`**: Avoid in modern JavaScript due to scoping issues and unexpected behavior

Understanding these differences will help you write more predictable and maintainable JavaScript code!