# HTML Element Disappears - Script Timing Issue

This repository demonstrates a common yet subtle bug in HTML where a script that hides or modifies a DOM element is executed before the element is fully loaded into the DOM. This leads to the element never being rendered on the page.

## Bug Description
The provided HTML code attempts to hide a div element with the id "myDiv" using JavaScript.  However, the script runs before the browser has finished parsing and rendering the HTML, resulting in the div never being visible. 

## Solution
The solution involves ensuring that the JavaScript code runs only *after* the entire HTML document has been parsed and the DOM is ready.  This can be achieved in two ways:

1. **Moving the script to the end of the body:** This simple approach guarantees that the script executes after the HTML is parsed.

2. **Using `DOMContentLoaded` event listener:**  This is a more robust approach, ensuring that the script runs after the DOM is fully loaded, regardless of other factors that might delay rendering.

## How to reproduce the bug and test the solution

Clone this repository and open the `bug.html` file in a web browser. You'll see that the text within the div is missing. Then open `bugSolution.html` to see the solution. 

This example highlights the importance of understanding the order of execution in web pages and using proper DOM manipulation techniques.