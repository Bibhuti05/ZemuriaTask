# Snackbar / Toast Documentation

This document provides an overview of a simple Snackbar (or Toast) implementation using HTML, CSS, and JavaScript. Snackbars are brief messages that appear at the bottom of the screen to provide feedback to users.

## Overview

Snackbars are often used as tooltips or popups to show messages at the bottom of the screen. They are typically used to inform users about the status of an action they have taken, such as saving data, errors, or warnings.

## HTML Structure

The HTML structure consists of a heading, some explanatory text, buttons to trigger the snackbar, and the snackbar element itself.

```html
<h2>Snackbar / Toast</h2>
<p>Snackbars are often used as a tooltips/popups to show a message at the bottom of the screen.</p>
<p>Click on the button to show the snackbar. It will disappear after 3 seconds.</p>

<button onclick="myFunction('sucess')">sucess</button>
<button onclick="myFunction('fail')">fail</button>
<button onclick="myFunction('warn')">warning</button>

<div id="snackbar">Some text some message..</div>
```

## JavaScript Functionality

The JavaScript function `myFunction(out)` is responsible for displaying the snackbar with different background colors based on the button clicked. Below is a detailed description of the function:

### Function Definition

```javascript
function myFunction(out) {
  var x = document.getElementById("snackbar");
  if(out == 'sucess') x.style.backgroundColor = 'green';
  if(out == 'fail') x.style.backgroundColor = 'red';
  if(out == 'warn') x.style.backgroundColor = 'yellow';

  x.className = "show";
  setTimeout(function(){ x.className = x.className.replace("show", ""); }, 3000);
}
