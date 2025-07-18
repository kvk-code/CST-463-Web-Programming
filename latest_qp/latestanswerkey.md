### **PART A**
**Answer all questions, each carries 3 marks.**

**1. List out the difference between HTTP get and post requests.**
*(Marks: 3)*

| Feature | GET | POST |
| :--- | :--- | :--- |
| **Data Submission** | Appends data to the URL in a query string. | Sends data within the body of the HTTP request. |
| **Data Size** | Limited by the maximum URL length (approx. 2048 chars). | No restriction on data size. |
| **Security** | Less secure as data is visible in the URL and browser history. | More secure as data is not exposed in the URL. |
| **Caching/Bookmark** | Can be cached, bookmarked, and remains in browser history. | Cannot be cached or bookmarked. |
| **Idempotency** | Idempotent (multiple identical requests have the same effect as one). | Not idempotent (multiple requests may create multiple resources). |
| **Usage** | Used for retrieving data from the server (e.g., searching). | Used for submitting data that modifies the server state (e.g., creating a user, submitting a form). |

**Marking Scheme:**
*   Award 1 mark for each of any three valid and distinct differences.

---

**2. How are images used as hyperlinks? Give example.**
*(Marks: 3)*

An image is used as a hyperlink by nesting the `<img>` tag inside an `<a>` (anchor) tag. The `<a>` tag defines the link's destination (`href` attribute), and the `<img>` tag provides the clickable image content.

**Marking Scheme:**
*   **(1 Mark)** For explaining that the `<img>` tag is placed inside the `<a>` tag.
*   **(2 Marks)** For providing a correct HTML code example.

**Example Code:**
```html
<a href="https://www.ktu.edu.in">
  <img src="ktu_logo.png" alt="KTU Official Website" width="100" height="50">
</a>
```

---

**3. Discuss the components of the box model in CSS.**
*(Marks: 3)*

The CSS box model is a box that wraps around every HTML element. It consists of four main components, layered from the inside out:

1.  **Content:** The actual content of the box, where text and images appear. Its dimensions are defined by `width` and `height`.
2.  **Padding:** The transparent area around the content, inside the border. It separates the content from the border.
3.  **Border:** A border that goes around the padding and content. It can be styled with properties like `border-width`, `border-style`, and `border-color`.
4.  **Margin:** The transparent area outside the border. It separates the element from other elements.

**Marking Scheme:**
*   **(1 Mark)** For listing the four components (Content, Padding, Border, Margin).
*   **(2 Marks)** For a brief and correct explanation of what each component represents. A simple diagram can also supplement the explanation.

---

**4. What are the various ways of declaring arrays in Java script?**
*(Marks: 3)*

There are three primary ways to declare an array in JavaScript:

1.  **Array Literal (Recommended):** This is the simplest and most common way.
    ```javascript
    let fruits = ["Apple", "Banana", "Cherry"];
    ```
2.  **Using the `new Array()` Constructor:**
    ```javascript
    let fruits = new Array("Apple", "Banana", "Cherry");
    ```
3.  **Using `new Array()` with a single number:** This creates an empty array with a specified length.
    ```javascript
    let emptyArray = new Array(5); // Creates an array with 5 undefined slots
    ```

**Marking Scheme:**
*   Award 1 mark for each correct method with a valid example.

---

**5. How does type casting converts between data types in PHP?**
*(Marks: 3)*

Type casting in PHP is used to force a variable to be evaluated as a certain data type. This is done by prefixing the variable with the desired type in parentheses. The original variable's type is not changed, only its value is treated as the new type for a single operation.

**Casting Operators:**
*   `(int)`, `(integer)` - cast to integer
*   `(bool)`, `(boolean)` - cast to boolean
*   `(float)`, `(double)`, `(real)` - cast to float
*   `(string)` - cast to string
*   `(array)` - cast to array
*   `(object)` - cast to object

**Example:**
```php
$score_str = "125.5";
$score_int = (int) $score_str; // $score_int is now 125 (integer)
$is_set = (bool) $score_str; // $is_set is now true (boolean)
```

**Marking Scheme:**
*   **(1 Mark)** For explaining the concept of type casting (forcing a type).
*   **(2 Marks)** For listing some casting operators and providing a correct example.

---

**6. Differentiate implode and explode functions in PHP with examples.**
*(Marks: 3)*

**explode():**
*   **Purpose:** Splits a string into an array of strings.
*   **How it works:** It uses a specified delimiter string to break the original string apart.
*   **Example:**
    ```php
    $csv_string = "apple,banana,cherry";
    $fruits_array = explode(",", $csv_string);
    // $fruits_array is now ["apple", "banana", "cherry"]
    ```

**implode():**
*   **Purpose:** Joins the elements of an array into a single string.
*   **How it works:** It uses a specified "glue" string to connect the array elements.
*   **Example:**
    ```php
    $fruits_array = ["apple", "banana", "cherry"];
    $csv_string = implode(",", $fruits_array);
    // $csv_string is now "apple,banana,cherry"
    ```

**Marking Scheme:**
*   **(1.5 Marks)** For `explode()`: 0.5 for definition, 1 for example.
*   **(1.5 Marks)** For `implode()`: 0.5 for definition, 1 for example.

---

**7. Describe the major super global arrays in PHP.**
*(Marks: 3)*

Superglobals are built-in PHP variables that are always accessible in all scopes.
The major superglobal arrays are:
*   `$_GET`: An associative array of variables passed to the current script via the URL parameters (query string).
*   `$_POST`: An associative array of variables passed to the current script via the HTTP POST method.
*   `$_REQUEST`: An associative array that contains the contents of `$_GET`, `$_POST`, and `$_COOKIE`.
*   `$_SESSION`: An associative array containing session variables available to the current script.
*   `$_COOKIE`: An associative array of variables passed to the current script via HTTP Cookies.
*   `$_SERVER`: An array containing information such as headers, paths, and script locations.
*   `$_FILES`: An associative array of items uploaded to the current script via the HTTP POST method.

**Marking Scheme:**
*   **(1 Mark)** For the definition of superglobals.
*   **(2 Marks)** For listing and briefly describing at least 4-5 superglobals.

---

**8. How can a record be inserted into a database table using PHP?**
*(Marks: 3)*

The general steps to insert a record into a database using PHP (with MySQLi as an example) are:
1.  **Establish a Database Connection:** Use `mysqli_connect()` to connect to the MySQL server and select the database.
2.  **Prepare the SQL Query:** Write the `INSERT INTO` SQL statement. It's best practice to use prepared statements to prevent SQL injection.
    ```sql
    INSERT INTO students (name, email) VALUES ('John Doe', 'john.doe@example.com');
    ```
3.  **Execute the Query:** Use a function like `mysqli_query()` (for direct queries) or `prepare()`/`bind_param()`/`execute()` (for prepared statements) to run the SQL query against the database.
4.  **Close the Connection:** Close the database connection using `mysqli_close()`.

**Marking Scheme:**
*   Award 1 mark for each of the three main steps (Connect, Prepare Query, Execute Query).

---

**9. What is the significance of JSON schema?**
*(Marks: 3)*

JSON Schema is a vocabulary that allows you to annotate and validate JSON documents. Its significance lies in:
1.  **Data Validation:** It provides a way to define rules (e.g., data types, required properties, string patterns) for a JSON object. This ensures that the data received or sent is in the correct format, preventing errors.
2.  **Documentation:** A JSON Schema serves as clear, machine-readable documentation for your data structure. It describes what data is expected.
3.  **Automated Tooling:** It can be used to automatically generate user interfaces (forms), data models in programming languages, and test cases.

**Marking Scheme:**
*   **(1 Mark)** For defining what JSON Schema is (a vocabulary for validating/annotating JSON).
*   **(2 Marks)** For explaining its significance, mentioning at least two points like validation and documentation.

---

**10. With a diagram explain the MVC architecture of Laravel.**
*(Marks: 3)*

MVC (Model-View-Controller) is an architectural pattern that separates an application into three main logical components.

*   **Model:** Represents the application's data and business logic. It is responsible for interacting with the database (retrieving, inserting, updating data). In Laravel, Eloquent models are a common implementation.
*   **View:** The user interface (UI) of the application. It displays data received from the controller and sends user actions to the controller. In Laravel, these are typically Blade template files.
*   **Controller:** Acts as an intermediary between the Model and the View. It handles user requests, interacts with the Model to fetch or update data, and then loads the appropriate View with that data.

**Diagram:**
A simple flow diagram should be drawn:
`User Request -> Router -> Controller -> (interacts with) Model -> Controller -> (loads) View -> Response to User`

**Marking Scheme:**
*   **(1 Mark)** For the diagram showing the flow.
*   **(2 Marks)** For a correct explanation of the roles of Model, View, and Controller.

---

### **PART B**
**Answer any one full question from each module, each carries 14 marks.**

#### **Module I**

**11 a) Discuss in detail with examples the audio and video tags in HTML for multimedia elements.**
*(Marks: 7)*

**`<audio>` tag:**
The `<audio>` tag is used to embed sound content in an HTML document.
*   **Key Attributes:**
    *   `src`: Specifies the path to the audio file.
    *   `controls`: Displays standard audio controls like play/pause, volume, etc.
    *   `autoplay`: The audio will start playing as soon as it is ready.
    *   `loop`: The audio will start over again, every time it is finished.
    *   `muted`: The audio output should be muted.
*   **Multiple Sources:** You can use the `<source>` tag inside `<audio>` to provide multiple audio formats. The browser will use the first format it supports.

**Example:**
```html
<audio controls>
  <source src="song.mp3" type="audio/mpeg">
  <source src="song.ogg" type="audio/ogg">
  Your browser does not support the audio element.
</audio>
```

**`<video>` tag:**
The `<video>` tag is used to embed video content.
*   **Key Attributes:**
    *   `src`: Specifies the path to the video file.
    *   `controls`: Displays standard video controls.
    *   `autoplay`, `loop`, `muted`: Same as the audio tag.
    *   `width`, `height`: Sets the dimensions of the video player.
    *   `poster`: Specifies an image to be shown while the video is downloading, or until the user hits the play button.

**Example:**
```html
<video width="320" height="240" controls poster="preview.jpg">
  <source src="movie.mp4" type="video/mp4">
  <source src="movie.webm" type="video/webm">
  Your browser does not support the video tag.
</video>
```
**Marking Scheme:**
*   **(3.5 Marks for `<audio>`):** 1.5 for explanation & attributes, 2 for a correct example with `<source>`.
*   **(3.5 Marks for `<video>`):** 1.5 for explanation & attributes, 2 for a correct example with `<source>` and other attributes.

---

**11 b) Write an HTML code to create a nested list:**
*(The list structure is provided in the question paper)*
*(Marks: 7)*

**HTML Code:**
```html
<!DOCTYPE html>
<html>
<head>
    <title>Nested List</title>
</head>
<body>

    <h1>Course Structure</h1>
    <ol>
        <li>CSE
            <ol type="1"> <!-- Nested ordered list for semesters -->
                <li>First Semester
                    <ul> <!-- Unordered list for subjects -->
                        <li>Graphics</li>
                        <li>Chemistry</li>
                        <li>Life Skills</li>
                    </ul>
                </li>
                <li>Second Semester
                    <ul> <!-- Unordered list for subjects -->
                        <li>Mechanics</li>
                        <li>Programming in C</li>
                        <li>Physics</li>
                    </ul>
                </li>
            </ol>
        </li>
        <!-- Other departments could be added here as <li> elements -->
    </ol>

</body>
</html>
```

**Marking Scheme:**
*   **(2 Marks)** For correctly using the outer `<ol>` for "CSE".
*   **(2 Marks)** For correctly nesting another `<ol>` inside the `<li>` for "First Semester" and "Second Semester".
*   **(2 Marks)** For correctly nesting `<ul>` tags for the subjects under each semester.
*   **(1 Mark)** For overall correct structure and content as per the question.

---

**OR**

**12 a) What is MIME? Explain the significance of MIME and the types of MIME used in web pages.**
*(Marks: 7)*

**MIME (Multipurpose Internet Mail Extensions):**
MIME is a standard for identifying the nature and format of files on the internet. It was originally developed for email attachments but is now fundamental to web protocols like HTTP. When a web server sends a file to a browser, it includes a MIME type in the `Content-Type` header of the HTTP response.

**Significance:**
The MIME type tells the browser how to handle the file. For example, a `text/html` file will be rendered as a web page, an `image/png` file will be displayed as an image, and an `application/pdf` file might be handled by a plugin or downloaded. Without MIME types, the browser would have to guess the file's format, leading to incorrect rendering.

**Common MIME Types:**
*   `text/html`: For HTML documents.
*   `text/css`: For CSS stylesheets.
*   `application/javascript`: For JavaScript files.
*   `image/jpeg`, `image/png`, `image/gif`: For different image formats.
*   `video/mp4`, `audio/mpeg`: For multimedia files.
*   `application/json`: For JSON data.
*   `application/pdf`: For PDF documents.
*   `application/octet-stream`: A generic type for binary files, which usually prompts a download.

**Marking Scheme:**
*   **(2 Marks)** For the definition of MIME.
*   **(2 Marks)** For explaining its significance (telling the browser how to handle content).
*   **(3 Marks)** For listing and describing at least 4-5 common MIME types.

---

**12 b) Write an HTML5 element (or elements) to accomplish each of the following tasks:**
*(Marks: 7)*

**HTML Code:**
```html
<!DOCTYPE html>
<html>
<head>
    <title>Student Form</title>
</head>
<body>
    <form action="/submit-form" method="post">
        <!-- a) Autofocus text input for first name -->
        <label for="fname">First Name:</label><br>
        <input type="text" id="fname" name="fname" autofocus><br><br>

        <!-- b) Rating scale for food -->
        <label for="food_rating">Rate the cafeteria food (1-10):</label><br>
        <input type="range" id="food_rating" name="food_rating" min="1" max="10"><br><br>
        <!-- Alternative: <input type="number" min="1" max="10"> -->

        <!-- c) Required email field -->
        <label for="email">Email ID:</label><br>
        <input type="email" id="email" name="email" required><br><br>

        <!-- d) Text area for comments and a submit button -->
        <label for="comments">Comments:</label><br>
        <textarea id="comments" name="comments" rows="4" cols="50"></textarea><br><br>

        <input type="submit" value="Submit">
    </form>
</body>
</html>
```

**Marking Scheme:**
*   **(1.5 Marks)** For part (a): Correct use of `<input type="text">` and the `autofocus` attribute.
*   **(2 Marks)** For part (b): Correct use of `<input type="range">` or `<input type="number">` with `min` and `max` attributes.
*   **(1.5 Marks)** For part (c): Correct use of `<input type="email">` and the `required` attribute.
*   **(2 Marks)** For part (d): Correct use of `<textarea>` and `<input type="submit">`.

---

#### **Module II**

**13 a) Differentiate class selectors and generic selectors in CSS. Apply appropriate selector in CSS to apply two different styles to the paragraph element:**
*(Marks: 7)*

**Differentiation:**
*   **Generic (or Type/Element) Selector:** Selects all elements of a given type. For example, `p` selects all `<p>` elements, `h1` selects all `<h1>` elements. It is used for applying a base style to all instances of an element.
*   **Class Selector:** Selects elements that have a specific `class` attribute. It is denoted by a period (`.`) followed by the class name (e.g., `.special-text`). It is used to style a specific group of elements, regardless of their type, giving more granular control than a generic selector.

**CSS Code for Styling:**
```html
<style>
    /* Style 1 using a class selector */
    .style1 {
        font-family: "Times New Roman", serif;
        color: red;
        font-style: italic;
        text-indent: 1.5em;
    }

    /* Style 2 using another class selector, or could be applied to p directly if desired */
    .style2 {
        line-height: 2em; /* spacing between consecutive lines */
        text-align: center;
        background-color: yellow;
    }
</style>

<p class="style1">This is the first paragraph with Style 1. The text is in Times New Roman, red, italic, and has an indentation. This is the first paragraph with Style 1. The text is in Times New Roman, red, italic, and has an indentation.</p>

<p class="style2">This is the second paragraph with Style 2. The line spacing is increased, the text is center-aligned, and it has a yellow background. This is the second paragraph with Style 2. The line spacing is increased, the text is center-aligned, and it has a yellow background.</p>
```

**Marking Scheme:**
*   **(3 Marks)** For correctly differentiating between generic and class selectors with examples.
*   **(2 Marks)** For correctly writing the CSS for Style 1 (font, color, style, indent).
*   **(2 Marks)** For correctly writing the CSS for Style 2 (line-height, alignment, background).

---

**13 b) Write JavaScript code to find the factorial of numbers from 1 to 5 and display the factorial with the number in a table with a blue, dotted border.**
*(Marks: 7)*

**JavaScript Code (embedded in HTML):**
```html
<!DOCTYPE html>
<html>
<head>
    <title>Factorial Table</title>
    <style>
        table, th, td {
            border: 2px dotted blue;
            border-collapse: collapse;
            padding: 8px;
            text-align: center;
        }
    </style>
</head>
<body>

    <h2>Factorials from 1 to 5</h2>
    <div id="table-container"></div>

    <script>
        function calculateFactorial(n) {
            if (n === 0 || n === 1) {
                return 1;
            }
            let fact = 1;
            for (let i = 2; i <= n; i++) {
                fact *= i;
            }
            return fact;
        }

        let tableContent = "<table><tr><th>Number</th><th>Factorial</th></tr>";

        for (let i = 1; i <= 5; i++) {
            let factorialValue = calculateFactorial(i);
            tableContent += `<tr><td>${i}</td><td>${factorialValue}</td></tr>`;
        }

        tableContent += "</table>";

        document.getElementById("table-container").innerHTML = tableContent;
    </script>

</body>
</html>
```

**Marking Scheme:**
*   **(3 Marks)** For the JavaScript logic to correctly calculate factorial (loop or recursive function).
*   **(3 Marks)** For the JavaScript code that dynamically generates the HTML `<table>`, `<tr>`, `<td>` elements.
*   **(1 Mark)** For applying the specified CSS style (blue, dotted border) to the table.

---

**OR**

**14 a) What are CSS selectors? Explain in detail the CSS selectors with examples.**
*(Marks: 7)*

**CSS Selectors:**
CSS selectors are patterns used to select the HTML element(s) you want to style. They are the part of a CSS rule that defines which elements the style should be applied to.

**Types of Selectors (with examples):**

1.  **Element Selector (Type Selector):** Selects elements based on the element name.
    `p { color: blue; }` /* Styles all <p> elements */

2.  **ID Selector:** Selects a single, unique element with a specific `id` attribute. An ID must be unique within a page.
    `#header { background-color: grey; }` /* Styles the element with id="header" */

3.  **Class Selector:** Selects elements with a specific `class` attribute.
    `.highlight { font-weight: bold; }` /* Styles all elements with class="highlight" */

4.  **Attribute Selector:** Selects elements based on an attribute or attribute value.
    `a[target="_blank"] { color: red; }` /* Styles all <a> tags with target="_blank" */

5.  **Universal Selector:** Selects all HTML elements on the page.
    `* { margin: 0; padding: 0; }` /* Resets margin and padding for all elements */

6.  **Grouping Selector:** Selects all the HTML elements with the same style definitions by grouping selectors with a comma.
    `h1, h2, p { text-align: center; }` /* Centers all h1, h2, and p elements */

7.  **Descendant Selector:** Selects all elements that are descendants of a specified element.
    `div p { color: green; }` /* Styles all <p> elements inside a <div> */

**Marking Scheme:**
*   **(1 Mark)** For the definition of CSS selectors.
*   **(6 Marks)** For explaining at least 4-5 different types of selectors with correct syntax and examples. (Approx 1.5 marks per selector type).

---

**14 b) Write a Javascript function to determine the largest of three numbers. Use prompt dialog box to enter the three numbers.**
*(Marks: 7)*

**JavaScript Code:**
```html
<!DOCTYPE html>
<html>
<head>
    <title>Largest of Three</title>
</head>
<body>
    <button onclick="findLargest()">Find Largest Number</button>
    <script>
        function findLargest() {
            // Prompt user for three numbers
            let num1_str = prompt("Enter the first number:");
            let num2_str = prompt("Enter the second number:");
            let num3_str = prompt("Enter the third number:");

            // Convert string inputs to numbers
            let num1 = parseFloat(num1_str);
            let num2 = parseFloat(num2_str);
            let num3 = parseFloat(num3_str);

            // Check if inputs are valid numbers
            if (isNaN(num1) || isNaN(num2) || isNaN(num3)) {
                alert("Please enter valid numbers only.");
                return;
            }

            // Determine the largest number
            let largest;
            if (num1 >= num2 && num1 >= num3) {
                largest = num1;
            } else if (num2 >= num1 && num2 >= num3) {
                largest = num2;
            } else {
                largest = num3;
            }

            // Alternative using Math.max()
            // let largest = Math.max(num1, num2, num3);

            // Display the result
            alert("The numbers are " + num1 + ", " + num2 + ", and " + num3 + ".\nThe largest number is: " + largest);
        }
    </script>
</body>
</html>
```

**Marking Scheme:**
*   **(2 Marks)** For correctly using `prompt()` to get three inputs from the user.
*   **(1 Mark)** For converting the string inputs from `prompt` to numbers (e.g., using `parseFloat` or `parseInt`).
*   **(3 Marks)** For the core logic to find the largest number (either `if-else if-else` structure or `Math.max()`).
*   **(1 Mark)** For displaying the final result using `alert()`.

---

#### **Module III**

**15 a) What are associative arrays in PHP? Create an associative array in PHP to declare the name and age of three persons and use appropriate functions to print each element of the array. Sort the array in ascending order of names and ascending order of ages.**
*(Marks: 7)*

**Associative Arrays in PHP:**
An associative array is an array that uses named keys (strings) that you assign to them, instead of numeric indices. They are useful for storing key-value pairs.

**PHP Code:**
```php
<?php
// 1. Create the associative array
$people = [
    "John" => 32,
    "Jane" => 28,
    "Peter" => 45
];

// 2. Print each element
echo "<h3>Original Array:</h3>";
foreach ($people as $name => $age) {
    echo "Name: $name, Age: $age <br>";
}
// Using print_r for debugging view
// print_r($people);

// 3. Sort by name (key) in ascending order
$sorted_by_name = $people;
ksort($sorted_by_name); // ksort sorts by key
echo "<h3>Sorted by Name (Ascending):</h3>";
foreach ($sorted_by_name as $name => $age) {
    echo "Name: $name, Age: $age <br>";
}

// 4. Sort by age (value) in ascending order
$sorted_by_age = $people;
asort($sorted_by_age); // asort sorts by value, maintaining key association
echo "<h3>Sorted by Age (Ascending):</h3>";
foreach ($sorted_by_age as $name => $age) {
    echo "Name: $name, Age: $age <br>";
}
?>
```

**Marking Scheme:**
*   **(1 Mark)** For the definition of an associative array.
*   **(2 Marks)** For correctly creating the associative array with the specified data.
*   **(1 Mark)** For correctly printing the original array elements (e.g., using a `foreach` loop).
*   **(1.5 Marks)** For correctly sorting the array by name (using `ksort`).
*   **(1.5 Marks)** For correctly sorting the array by age (using `asort`).

---

**15 b) Write a function in PHP to check if a number read is a palindrome or not?**
*(Marks: 7)*

**PHP Code:**
```php
<?php
// Function to check for palindrome
function isPalindrome($number) {
    // Convert the number to a string to easily reverse it
    $original_string = (string) $number;
    
    // Reverse the string
    $reversed_string = strrev($original_string);
    
    // Compare the original and reversed strings
    if ($original_string == $reversed_string) {
        return true;
    } else {
        return false;
    }
}

// Example Usage
$num1 = 12321;
$num2 = 12345;

if (isPalindrome($num1)) {
    echo "$num1 is a palindrome.<br>";
} else {
    echo "$num1 is not a palindrome.<br>";
}

if (isPalindrome($num2)) {
    echo "$num2 is a palindrome.<br>";
} else {
    echo "$num2 is not a palindrome.<br>";
}
?>
```

**Marking Scheme:**
*   **(2 Marks)** For defining a PHP function that accepts a number as an argument.
*   **(3 Marks)** For the core logic of the palindrome check (e.g., converting to string and using `strrev()`, or mathematical reversal).
*   **(2 Marks)** For correctly returning `true` or `false` and showing example usage to demonstrate the function works.

---

**OR**

**16 a) Write a PHP script to print the sum of the digits of a three digit number.**
*(Marks: 7)*

**PHP Code:**
```php
<?php
$number = 345; // Example three-digit number
$sum = 0;
$temp_num = $number;

if ($temp_num < 100 || $temp_num > 999) {
    echo "Please enter a valid three-digit number.";
} else {
    // Logic to calculate the sum of digits
    while ($temp_num > 0) {
        $digit = $temp_num % 10; // Get the last digit
        $sum += $digit;           // Add it to the sum
        $temp_num = (int)($temp_num / 10); // Remove the last digit
    }

    echo "The number is: $number <br>";
    echo "The sum of its digits is: $sum";
}
?>
```

**Marking Scheme:**
*   **(2 Marks)** For correctly initializing variables.
*   **(4 Marks)** For the core logic using a `while` loop (or another method) with modulo (`%`) and division operators to extract and sum the digits.
*   **(1 Mark)** For correctly printing the final sum.

---

**16 b) How are functions defined in PHP? Write a PHP function which checks whether a string passed to it starts with the character pattern “PHP”. Apply pattern matching concept.**
*(Marks: 7)*

**Function Definition in PHP:**
A user-defined function in PHP is declared using the `function` keyword, followed by the function name, a set of parentheses `()`, and a block of code `{}`. Arguments can be passed inside the parentheses. A value can be returned using the `return` statement.
**Syntax:**
```php
function functionName($arg1, $arg2, ...) {
    // code to be executed
    return $value;
}
```

**PHP Function for Pattern Matching:**
Using `preg_match()` is the standard way for regex pattern matching.
```php
<?php
// Function definition
function startsWithPHP($input_string) {
    // The pattern ^PHP checks for "PHP" at the beginning of the string.
    // The 'i' modifier makes the search case-insensitive.
    $pattern = '/^PHP/i'; 
    
    if (preg_match($pattern, $input_string)) {
        return true;
    } else {
        return false;
    }
}

// Example Usage
$string1 = "PHP is a great language.";
$string2 = "php is fun!";
$string3 = "I love PHP.";

if (startsWithPHP($string1)) {
    echo "'$string1' starts with 'PHP'.<br>";
}
if (startsWithPHP($string2)) {
    echo "'$string2' starts with 'PHP'.<br>";
}
if (!startsWithPHP($string3)) {
    echo "'$string3' does not start with 'PHP'.<br>";
}
?>
```
*An alternative non-regex solution using `strpos()` would also be acceptable:*
`return strpos(strtoupper($input_string), 'PHP') === 0;`

**Marking Scheme:**
*   **(2 Marks)** For explaining how functions are defined in PHP with correct syntax.
*   **(3 Marks)** For writing a function that uses a correct pattern matching concept (`preg_match` is preferred, but `strpos` is also valid).
*   **(2 Marks)** For the correct pattern (`/^PHP/`) and demonstrating the function's usage with examples.

---



### **PART B (Continued)**

#### **Module IV**

**17 a) Why are cookies used in web pages? With an example explain how cookies are written to the client.**
*(Marks: 7)*

**Why Cookies are Used:**
Cookies are small text files stored on the client's computer by the web browser at the request of a web server. They are used to remember stateful information for the stateless HTTP protocol. Their primary uses are:
1.  **Session Management:** To keep a user logged in, track shopping cart contents, or maintain user-specific data across multiple page requests.
2.  **Personalization:** To store user preferences like themes, language settings, or other customizable options.
3.  **Tracking:** To record and analyze user browsing habits, which can be used for targeted advertising or website analytics.

**How Cookies are Written (PHP Example):**
In PHP, cookies are written to the client's browser using the `setcookie()` function. This function must be called *before* any HTML output is sent to the browser.

**`setcookie()` Syntax:**
`setcookie(name, value, expire, path, domain, secure, httponly);`

*   `name`: The name of the cookie.
*   `value`: The value of the cookie.
*   `expire`: The timestamp when the cookie should expire. Usually set using `time() + (number of seconds)`.
*   `path`: The server path on which the cookie will be available. `/` means it's available on the entire domain.

**Example Code:**
```php
<?php
// Set a cookie named "username" with the value "John Doe"
// It will expire in 1 hour (3600 seconds)
$cookie_name = "username";
$cookie_value = "John Doe";
setcookie($cookie_name, $cookie_value, time() + 3600, "/"); 

// The cookie must be set before any HTML
?>
<!DOCTYPE html>
<html>
<body>

<?php
if(!isset($_COOKIE[$cookie_name])) {
    echo "Cookie named '" . $cookie_name . "' is not set!";
} else {
    echo "Cookie '" . $cookie_name . "' is set!<br>";
    echo "Value is: " . $_COOKIE[$cookie_name];
}
?>
<p>This is a page that sets a cookie. Refresh the page to see the cookie value.</p>
</body>
</html>
```

**Marking Scheme:**
*   **(3 Marks)** For explaining the uses of cookies (Session, Personalization, Tracking).
*   **(1 Mark)** For mentioning the `setcookie()` function and its purpose.
*   **(3 Marks)** For providing a correct and complete PHP example demonstrating how to set and read a cookie.

---

**17 b) Design an HTML form for entering a number by the user. Write a PHP code to display a message indicating, whether the number is even or not, when clicking on the submit button.**
*(Marks: 7)*

**HTML Code (`index.html`):**
```html
<!DOCTYPE html>
<html>
<head>
    <title>Even/Odd Checker</title>
</head>
<body>
    <h2>Check if a Number is Even or Odd</h2>
    <form action="check_even_odd.php" method="post">
        <label for="number">Enter a number:</label>
        <input type="number" id="number" name="number" required>
        <br><br>
        <input type="submit" value="Check Number">
    </form>
</body>
</html>
```

**PHP Code (`check_even_odd.php`):**
```php
<!DOCTYPE html>
<html>
<head>
    <title>Result</title>
</head>
<body>
    <h2>Result</h2>
    <?php
    // Check if the form was submitted using POST method
    if ($_SERVER["REQUEST_METHOD"] == "POST") {
        // Check if the 'number' field is set and not empty
        if (isset($_POST["number"]) && $_POST["number"] !== '') {
            $number = $_POST["number"];
            
            // Validate if the input is a numeric value
            if (is_numeric($number)) {
                // Check if the number is even or odd using the modulo operator
                if ($number % 2 == 0) {
                    echo "The number $number is EVEN.";
                } else {
                    echo "The number $number is ODD.";
                }
            } else {
                echo "Invalid input. Please enter a valid number.";
            }
        } else {
            echo "Please enter a number.";
        }
    } else {
        echo "Form was not submitted correctly.";
    }
    ?>
    <br><br>
    <a href="index.html">Go Back</a>
</body>
</html>
```

**Marking Scheme:**
*   **(3 Marks)** For the correct HTML form structure (`<form>`, `<input type="number">`, `<input type="submit">`, correct `action` and `method`).
*   **(1 Mark)** For checking if the form was submitted (`$_SERVER["REQUEST_METHOD"] == "POST"`).
*   **(1 Mark)** For retrieving the number from the `$_POST` array.
*   **(2 Marks)** For the core logic: validating the input (`is_numeric`) and using the modulo operator (`%`) to check for even/odd.

---

**OR**

**18 a) Write a HTML file to create a form for collecting details of a student like name, branch, age and phone number. Create a PHP script that validates the phone number when the form data is submitted using a 'Register ‘Button. If not valid the error message ‘Enter a valid phone number' is to be displayed.**
*(Marks: 7)*

**HTML Code (`register.html`):**
```html
<!DOCTYPE html>
<html>
<head>
    <title>Student Registration</title>
</head>
<body>
    <h2>Student Registration Form</h2>
    <form action="validate.php" method="post">
        <label for="name">Name:</label><br>
        <input type="text" id="name" name="name" required><br><br>
        
        <label for="branch">Branch:</label><br>
        <input type="text" id="branch" name="branch" required><br><br>
        
        <label for="age">Age:</label><br>
        <input type="number" id="age" name="age" required><br><br>
        
        <label for="phone">Phone Number:</label><br>
        <input type="text" id="phone" name="phone" required><br><br>
        
        <input type="submit" name="register" value="Register">
    </form>
</body>
</html>
```

**PHP Code (`validate.php`):**
```php
<?php
// Check if the 'Register' button was clicked
if (isset($_POST['register'])) {
    $name = $_POST['name'];
    $branch = $_POST['branch'];
    $age = $_POST['age'];
    $phone = $_POST['phone'];
    
    // Validate the phone number (e.g., must be exactly 10 digits)
    $pattern = '/^[0-9]{10}$/';
    
    if (preg_match($pattern, $phone)) {
        // Phone number is valid, process the data
        echo "<h2>Registration Successful!</h2>";
        echo "Name: " . htmlspecialchars($name) . "<br>";
        echo "Branch: " . htmlspecialchars($branch) . "<br>";
        echo "Age: " . htmlspecialchars($age) . "<br>";
        echo "Phone Number: " . htmlspecialchars($phone) . "<br>";
    } else {
        // Phone number is not valid, display error message
        echo "<h2>Error!</h2>";
        echo "<p style='color:red;'>Enter a valid phone number</p>";
        echo '<a href="register.html">Go back to registration form</a>';
    }
} else {
    // Redirect back to form if accessed directly
    header('Location: register.html');
    exit();
}
?>
```

**Marking Scheme:**
*   **(3 Marks)** For the correct HTML form with all specified fields and the 'Register' button.
*   **(1 Mark)** For checking if the form was submitted.
*   **(2 Marks)** For using a regular expression (`preg_match`) to validate the phone number.
*   **(1 Mark)** For displaying the correct error message on validation failure.

---

**18 b) Explain the server side sessions in detail.**
*(Marks: 7)*

**Server-Side Sessions:**
A session is a mechanism to store information about a user on the server, making it accessible across multiple page requests. This overcomes the stateless nature of HTTP.

**How Sessions Work:**
1.  **Starting a Session:** The `session_start()` function must be called at the very beginning of any PHP script that needs to use session variables. This function checks if a session already exists for the user; if not, it creates a new one.
2.  **Session ID Creation:** When a new session is created, PHP generates a unique Session ID (a long random string).
3.  **Storing the Session ID:** By default, this Session ID is sent to the user's browser and stored in a cookie (usually named `PHPSESSID`).
4.  **Subsequent Requests:** On every subsequent request to the server, the browser sends the Session ID cookie back.
5.  **Retrieving Session Data:** PHP uses the received Session ID to locate and load the corresponding session data file from its temporary directory on the server. This data is then made available in the `$_SESSION` superglobal array.

**Using Session Variables:**
*   **Storing Data:** Data is stored in the `$_SESSION` associative array.
    `$_SESSION['username'] = 'testuser';`
    `$_SESSION['login_time'] = time();`
*   **Accessing Data:** Data is read from the same array.
    `echo 'Welcome, ' . $_SESSION['username'];`
*   **Modifying/Deleting a Variable:**
    `$_SESSION['username'] = 'newuser';`
    `unset($_SESSION['login_time']); // Deletes a single session variable`

**Destroying a Session:**
To completely end a session and delete all its data:
1.  `session_unset()`: Frees all session variables.
2.  `session_destroy()`: Destroys the session data file on the server.
It's good practice to call both.

**Marking Scheme:**
*   **(2 Marks)** For explaining the purpose of sessions (maintaining state).
*   **(3 Marks)** For detailing the workflow: `session_start()`, Session ID, cookie role, and server-side data file.
*   **(2 Marks)** For explaining how to use the `$_SESSION` array (store, access) and how to destroy a session (`session_destroy`).

---

#### **Module V**

**19 a) How are objects created in JSON? What are the different ways of accessing objects using JSON?**
*(Marks: 7)*

**Creating JSON Objects:**
JSON (JavaScript Object Notation) objects are a fundamental part of the JSON data format. A JSON object is an unordered collection of key/value pairs.
*   **Syntax:**
    *   An object begins with a left curly brace `{` and ends with a right curly brace `}`.
    *   Inside, it contains zero or more key/value pairs.
    *   Keys must be strings enclosed in double quotes (`"`).
    *   A colon (`:`) separates each key from its value.
    *   Comma (`,`) separates key/value pairs.
    *   Values can be a string, number, boolean (`true`/`false`), array `[]`, or another JSON object `{}`.

**Example of a JSON Object:**
```json
{
  "firstName": "John",
  "lastName": "Doe",
  "age": 30,
  "isStudent": false,
  "address": {
    "street": "123 Main St",
    "city": "Anytown"
  },
  "courses": ["Math", "Science"]
}
```

**Accessing JSON Object Data (in JavaScript):**
Before accessing, a JSON string must first be parsed into a JavaScript object using `JSON.parse()`.
```javascript
let jsonString = '{"firstName":"John", "lastName":"Doe", "age":30}';
let userObject = JSON.parse(jsonString);
```
Once you have a JavaScript object, you can access its properties in two ways:

1.  **Dot Notation:** This is the most common and readable method. You use a dot (`.`) between the object and the property name.
    ```javascript
    let name = userObject.firstName; // Accesses the value "John"
    console.log(name); 
    ```
2.  **Bracket Notation:** This method uses square brackets `[]` with the property name as a string inside. This is required when the property name is not a valid JavaScript identifier (e.g., contains spaces) or when the property name is stored in a variable.
    ```javascript
    let age = userObject["age"]; // Accesses the value 30
    console.log(age);
    
    let prop = "lastName";
    let lastName = userObject[prop]; // Accesses using a variable
    console.log(lastName);
    ```

**Marking Scheme:**
*   **(3 Marks)** For correctly explaining how JSON objects are created, including the syntax rules (curly braces, double-quoted keys, colon, comma).
*   **(1 Mark)** For mentioning the need to parse a JSON string with `JSON.parse()` in JavaScript.
*   **(1.5 Marks)** For explaining and showing an example of Dot Notation.
*   **(1.5 Marks)** For explaining and showing an example of Bracket Notation.

---

**19 b) Explain route model binding in Laravel.**
*(Marks: 7)*

**Route Model Binding in Laravel:**
Route Model Binding is a powerful feature in Laravel that provides a convenient way to automatically inject Eloquent model instances directly into your routes or controller methods. It simplifies the common task of fetching a model from the database based on a value in the URL (like an ID). If the model instance is not found, Laravel will automatically generate a 404 HTTP response.

There are two types of model binding:

**1. Implicit Binding (Most Common):**
Laravel automatically resolves Eloquent models type-hinted in a route or controller method whose variable names match a route segment name.
*   **How it works:**
    1.  Define a route with a parameter, e.g., `Route::get('/posts/{post}', ...);`. The segment name is `{post}`.
    2.  In the corresponding controller method, type-hint the model (`App\Models\Post`) and use a variable with the same name (`$post`).
*   **Example:**
    *   **Route (`routes/web.php`):**
        ```php
        use App\Http\Controllers\PostController;
        Route::get('/posts/{post}', [PostController::class, 'show']);
        ```
    *   **Controller (`app/Http/Controllers/PostController.php`):**
        ```php
        namespace App\Http\Controllers;
        use App\Models\Post;
        
        class PostController extends Controller {
            public function show(Post $post) {
                // Laravel has already fetched the Post model with the ID from the URL.
                // No need to write: $post = Post::findOrFail($id);
                return view('posts.show', ['post' => $post]);
            }
        }
        ```
    If a user visits `/posts/5`, Laravel will automatically fetch the `Post` with `id=5` and inject it into the `show` method as the `$post` variable.

**2. Explicit Binding:**
You explicitly tell Laravel which model to use for a given parameter in the `RouteServiceProvider`. This is useful for more complex scenarios, like using a column other than `id` for retrieval.
*   **How it works:** In `app/Providers/RouteServiceProvider.php`, use `Route::model()`.
    ```php
    public function boot() {
        parent::boot();
        // Laravel will use the 'slug' column to retrieve the Post model
        Route::model('post', \App\Models\Post::class, function ($value) {
            return \App\Models\Post::where('slug', $value)->firstOrFail();
        });
    }
    ```

**Marking Scheme:**
*   **(2 Marks)** For a clear definition of what Route Model Binding is and its primary benefit (code simplification, auto 404).
*   **(3 Marks)** For explaining Implicit Binding with a correct code example (both route and controller method).
*   **(2 Marks)** For briefly explaining Explicit Binding or customizing the key for implicit binding.

---

**OR**

**20 a) Write a JSON Schema for validating a student information. Also create a student instance conforming to the schema.**
*(Marks: 7)*

**JSON Schema for Student Information:**
This schema defines a "student" object. It requires a `studentId`, `name`, and `email`. It also specifies the data type for each property and a format for the email.

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "Student",
  "description": "A schema for validating student information",
  "type": "object",
  "properties": {
    "studentId": {
      "description": "The unique identifier for a student",
      "type": "integer"
    },
    "name": {
      "description": "Full name of the student",
      "type": "string",
      "minLength": 2
    },
    "email": {
      "description": "Student's email address",
      "type": "string",
      "format": "email"
    },
    "gpa": {
      "description": "Grade Point Average",
      "type": "number",
      "minimum": 0,
      "maximum": 4.0
    },
    "isEnrolled": {
      "description": "Indicates if the student is currently enrolled",
      "type": "boolean",
      "default": true
    }
  },
  "required": [
    "studentId",
    "name",
    "email"
  ]
}
```

**Student Instance Conforming to the Schema:**
This is an example of a JSON object that would be considered valid according to the schema above.

```json
{
  "studentId": 101,
  "name": "Jane Doe",
  "email": "jane.doe@university.edu",
  "gpa": 3.8,
  "isEnrolled": true
}
```

**Marking Scheme:**
*   **(4 Marks)** For writing a valid JSON Schema. Marks awarded for:
    *   Correct basic structure (`$schema`, `title`, `type: "object"`).
    *   Defining `properties` with correct data types (`string`, `integer`, `number`, `boolean`).
    *   Using at least one validation keyword beyond type (e.g., `format`, `minLength`, `minimum`, `maximum`).
    *   Correctly defining a `required` array.
*   **(3 Marks)** For creating a valid JSON instance that strictly conforms to the schema they defined.

---

**20 b) What are views and redirections in Laravel? With example explain how are they used in Laravel.**
*(Marks: 7)*

**Views in Laravel:**
Views are the "V" in the MVC (Model-View-Controller) architecture. They are responsible for presenting the application's data to the user.
*   **What they are:** Essentially, they are HTML files that contain the structure and presentation logic of a web page. Laravel uses the **Blade templating engine**, which allows embedding PHP-like syntax (`{{ ... }}`) directly into HTML for displaying data, using loops, and conditional statements in a clean way.
*   **How they are used:** Views are typically returned from a controller method using the `view()` helper function. Data can be passed from the controller to the view as an associative array.

**Example of using a View:**
*   **Controller (`app/Http/Controllers/UserController.php`):**
    ```php
    use App\Models\User;
    
    public function show($id) {
        $user = User::findOrFail($id);
        // Pass the $user object to the 'profile' view
        return view('user.profile', ['user' => $user]);
    }
    ```
*   **View (`resources/views/user/profile.blade.php`):**
    ```html
    <h1>User Profile</h1>
    <p>Name: {{ $user->name }}</p>
    <p>Email: {{ $user->email }}</p>
    ```

**Redirections in Laravel:**
Redirections are used to send the user's browser from one URL to another. This is common after a form submission (like creating or updating data) to avoid form re-submission issues.
*   **What they are:** An HTTP response with a `Location` header that tells the browser to make a new GET request to a different URL.
*   **How they are used:** Laravel provides a fluent `redirect()` helper function to generate redirect responses.

**Example of using Redirections:**
*   **Redirecting to a named route:** This is the most robust method.
    *   **Route:** `Route::get('/dashboard', [DashboardController::class, 'index'])->name('dashboard');`
    *   **Controller:**
        ```php
        public function store(Request $request) {
            // ... logic to store data ...
            return redirect()->route('dashboard')->with('status', 'Post created successfully!');
        }
        ```
        The `with()` method flashes a message to the session, which can be displayed on the next page.

*   **Redirecting back to the previous page:** Useful for form validation errors.
    ```php
    return back()->withInput()->withErrors($validator);
    ```

**Marking Scheme:**
*   **(3.5 Marks for Views):** 1 mark for definition, 1 mark for explaining `view()` helper and passing data, 1.5 marks for a correct code example (controller and blade file).
*   **(3.5 Marks for Redirections):** 1 mark for definition, 1 mark for explaining the `redirect()` helper, 1.5 marks for showing at least one correct example (e.g., `redirect()->route()` or `back()`).

