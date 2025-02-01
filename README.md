# Uncommon HTML Bug: Accessing Removed DOM Element

This repository demonstrates a subtle bug in JavaScript interacting with the DOM.  The code hides an HTML element and then, asynchronously, attempts to access a property of that element after it's been removed from the DOM. This leads to an error.

The `bug.html` file contains the buggy code, and `bugSolution.html` demonstrates a corrected version.

## Bug Description
The primary issue is the asynchronous nature of the code.  The `setTimeout` function causes a delay, and by the time the code inside it tries to access `document.getElementById("myDiv").innerHTML`, the element with id "myDiv" has already been removed from the document object model (DOM), resulting in an error.

## Solution
The solution involves checking if the element still exists before attempting to access its properties.