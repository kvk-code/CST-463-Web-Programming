
# Programming Assignment Questions - CST463 Web Programming 



## IMPORTANT IMPLEMENTATION GUIDELINES

**Special Note for All Programming Solutions:**

### JavaScript Programs:
- All JavaScript code must be embedded within a complete HTML document structure
- Include proper `<!DOCTYPE html>`, `<html>`, `<head>`, and `<body>` tags
- JavaScript should be placed within `<script>` tags in the `<head>` or `<body>` section
- The HTML file should be directly viewable and executable in a web browser
- Ensure all HTML elements referenced by JavaScript are properly defined

### PHP Programs:
- All PHP programs must include a complete HTML skeleton structure
- Use proper `<!DOCTYPE html>`, `<html>`, `<head>`, and `<body>` tags around PHP code
- When the .php file is served by a web server, the output should be properly formatted and viewable
- Mix PHP code with HTML appropriately to generate well-formed web pages
- Include proper HTML structure even for simple output displays

**Example Structure for JavaScript:**
```html
<!DOCTYPE html>
<html>
<head>
    <title>Your Program Title</title>
</head>
<body>
    <h1>Program Output</h1>
    <script>
        // Your JavaScript code here
    </script>
</body>
</html>
```

**Example Structure for PHP:**
```php
<!DOCTYPE html>
<html>
<head>
    <title>Your PHP Program</title>
</head>
<body>
    <h1>Program Output</h1>
    <?php
        // Your PHP code here
    ?>
</body>
</html>
```

---

## JavaScript Programming Assignment Questions

### Question 1: Factorial Program
Write a JavaScript program to calculate and display factorial of numbers from 1 to 10 in an HTML table. The program should:
- Use a function to calculate factorial
- Display results in a table with headers "Number" and "Factorial"
- Style the table with a blue dotted border
- Use prompt() to get additional input from user

**Sample Expected Output:**
```html
<table style="border: 2px dotted blue;">
  <tr><th>Number</th><th>Factorial</th></tr>
  <tr><td>1</td><td>1</td></tr>
  <tr><td>2</td><td>2</td></tr>
  <!-- ... more rows ... -->
</table>
```

### Question 2: Array Operations
Create a JavaScript program that demonstrates:
- Three different methods of array creation (literal, constructor, Array.of())
- Implementation of join(), slice(), push(), pop(), and sort() methods
- Display array contents before and after each operation
- Use console.log() and document.write() for output

**Requirements:**
```javascript
// Example array operations to implement
let arr = [5, 2, 8, 1, 9];
// Show join(), slice(), push(), pop(), sort() functionality
```

### Question 3: Largest of Three Numbers
Write a JavaScript function that:
- Uses prompt dialog boxes to input three numbers
- Determines and displays the largest number
- Handles invalid inputs gracefully
- Use appropriate control statements (if-else)

**Function Signature:**
```javascript
function findLargest(a, b, c) {
    // Implementation here
}
```

### Question 4: DOM Event Handling
Create an HTML page with JavaScript that:
- Initially displays "Welcome" in a paragraph
- Has a button labeled "Click Me"
- When clicked, changes paragraph text to "Hello from JavaScript" in bold
- Demonstrates at least three DOM methods (getElementById, innerHTML, onclick)

**HTML Structure:**
```html
<p id="message">Welcome</p>
<button id="clickButton">Click Me</button>
```

### Question 5: Control Statements Demo
Write JavaScript code demonstrating:
- if-else statements for grade calculation (A, B, C, D, F)
- for loop for displaying number sequences
- while loop for user input validation
- switch statement for menu selection (calculator operations)

### Question 6: Square Display Program
Write a JavaScript program that:
- Uses prompt to read an integer value
- Displays the square of the number
- Handles negative numbers appropriately

## Core PHP Programming Assignment Questions

### Question 1: Number Validation Programs
Write separate PHP programs for:

#### a) Prime Number Checker
- Create HTML form to input a number
- PHP script to check if number is prime
- Display result with appropriate message

#### b) Armstrong Number Validation
- Program to check if given number is Armstrong number
- Display detailed calculation steps

#### c) Palindrome Number Verification
- Function to check if a number is palindrome
- Test with multiple input values

**Expected Form Structure:**
```html
<form method="POST" action="">
    <input type="number" name="number" required>
    <input type="submit" value="Check">
</form>
```

### Question 2: Function Implementation
Create PHP functions for:

#### a) Factorial Table Display
```php
function factorial($n) {
    // Calculate factorial
}
// Display factorial of numbers 1-10 in HTML table
```

#### b) Sum Calculation with do-while
```php
function calculateSum() {
    // Sum of positive integers up to 100 using do-while
}
```

#### c) User-defined Functions
- Function with parameters and return values
- Demonstrate function calling and parameter passing
- Show variable scope (local vs global)

### Question 3: Advanced PHP Concepts
Write PHP programs demonstrating:

#### a) Array Comparison with C
- Explain differences between PHP arrays and C arrays
- Show dynamic sizing capabilities
- Demonstrate mixed data types in PHP arrays

#### b) Type Casting
```php
// Demonstrate conversion between different data types
$string = "123";
$integer = (int)$string;
$float = (float)$string;
```

#### c) Array Creation Methods
Show different ways to create arrays:
```php
// Indexed arrays
$arr1 = array(1, 2, 3);
$arr2 = [1, 2, 3];

// Associative arrays
$arr3 = array("name" => "John", "age" => 25);
$arr4 = ["name" => "John", "age" => 25);
```

