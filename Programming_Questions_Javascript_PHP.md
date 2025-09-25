
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

#### a) If-Else Statements for Grade Calculation (A, B, C, D, F)
Prompt the user for a numeric grade (0–100), validate input, and display the corresponding letter grade:
- A: 90–100
- B: 80–89
- C: 70–79
- D: 60–69
- F: below 60

#### b) For Loop for Displaying Number Sequences
Use a for loop to display numbers from 1 to 10 (or any specified range) in sequence, separated by spaces or in a list format.

#### c) While Loop for User Input Validation
Continuously prompt the user to enter a positive integer. If the input is invalid (not a number or not positive), repeat the prompt until valid input is received, then display the accepted value.

#### d) Switch Statement for Menu Selection (Calculator Operations)
Show a menu with prompt: "Choose operation: 1-Add, 2-Subtract, 3-Multiply, 4-Divide". Accept user choice, prompt for two numbers, and perform the selected operation using a switch statement. Display the result or an error message for invalid choices.

### Question 6: Square Display Program
Write a JavaScript program that:
- Uses prompt to read an integer value
- Displays the square of the number
- Handles negative numbers appropriately

## Core PHP Programming Assignment Questions

### Question 1: Number Validation Programs
Write separate PHP programs for:

#### a) Prime Number Checker
- Hardcode a test number (e.g., $number = 17;) in your PHP script
- Create a function to check if the number is prime
- Display the number being tested and the result with appropriate message
- Test with at least 3 different hardcoded values (prime and non-prime)

#### b) Armstrong Number Validation
- Hardcode a test number (e.g., $number = 153;) in your PHP script
- Create a function to check if the number is Armstrong number
- Display detailed calculation steps showing the sum of cubes
- Test with both Armstrong and non-Armstrong numbers

#### c) Palindrome Number Verification
- Create a function to check if a number is palindrome
- Hardcode an array of test values (e.g., $testNumbers = [121, 1331, 123, 7];)
- Test each number and display results in a formatted table

**Expected Output Structure:**
```php
<?php
$number = 17; // Hardcoded test value
echo "<h3>Testing number: $number</h3>";
// Your validation logic here
?>
```

### Question 2: Function Implementation
Create PHP functions for:

#### a) Factorial Table Display
```php
function factorial($n) {
    // Calculate factorial recursively or iteratively
}
// Hardcode range: Display factorial of numbers 1-10 in HTML table
// Use a for loop to generate the table rows
```

#### b) Sum Calculation with do-while
```php
function calculateSum($limit) {
    // Sum of positive integers from 1 to $limit using do-while loop
    // Hardcode $limit = 100 for testing
}
// Display the calculation process and final result
```

#### c) User-defined Functions Demonstration
- Create a function `calculateArea($length, $width)` that returns area of rectangle
- Create a function `greetUser($name, $age)` that displays personalized greeting
- Hardcode test values: $length = 10, $width = 5, $name = "John", $age = 25
- Demonstrate function calling and parameter passing
- Show variable scope by using both local and global variables

**Expected Function Calls:**
```php
<?php
$length = 10; $width = 5; // Global variables
echo "Area: " . calculateArea($length, $width);

$userName = "John"; $userAge = 25;
greetUser($userName, $userAge);
?>
```

### Question 3: Advanced PHP Concepts
Write PHP programs demonstrating:

#### a) Array Comparison with C
- Create a PHP program that demonstrates PHP array flexibility vs C arrays
- Hardcode examples showing:
  - Dynamic array sizing: `$arr = []; $arr[] = 1; $arr[] = "text";`
  - Mixed data types in single array: `$mixed = [1, "hello", 3.14, true];`
  - Associative arrays: `$student = ["name" => "John", "grade" => 85];`
- Display each array with explanatory comments about how this differs from C

#### b) Type Casting Demonstration
```php
<?php
// Hardcode test values and demonstrate all conversions
$originalString = "123.45abc";
$originalInt = 42;
$originalFloat = 3.14159;
$originalBool = true;

// Show conversion between different data types
$stringToInt = (int)$originalString;
$stringToFloat = (float)$originalString;
$intToString = (string)$originalInt;
$floatToInt = (int)$originalFloat;
// Display original values, converted values, and their types using gettype()
?>
```

#### c) Array Creation Methods
Show different ways to create and populate arrays with hardcoded data:
```php
<?php
// Indexed arrays - demonstrate 3 methods
$fruits1 = array("apple", "banana", "orange");
$fruits2 = ["apple", "banana", "orange"];
$fruits3 = array();
$fruits3[0] = "apple"; $fruits3[1] = "banana"; $fruits3[2] = "orange";

// Associative arrays - demonstrate 2 methods
$student1 = array("name" => "John", "age" => 25, "grade" => "A");
$student2 = ["name" => "John", "age" => 25, "grade" => "A"];

// Display all arrays using print_r() and var_dump() to show differences
?>
```

