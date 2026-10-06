# How Websites Work

TryHackMe room focused on the fundamentals of how websites work, including front-end technologies, HTML, JavaScript, sensitive data exposure, and HTML injection.

Room: https://tryhackme.com/room/howwebsiteswork

## Task 1: How Websites Work

The front end is the part of a web application that is rendered and displayed by the user's browser.

Answer:

```text
Front End
```

## Task 2: HTML

HTML (HyperText Markup Language) is used to structure the content of a webpage.

HTML uses tags to define elements such as headings, paragraphs, images, links, and forms.

### HTML Image

The first hidden answer was:

```text
HTMLHERO
```

The second hidden answer was:

```text
DOGHTML
```

Example of an image element:

```html
<img src="img/dog-1.png">
```

HTML can also use attributes such as `class`, `id`, `src`, and `href` to provide additional information or identify elements.

## Task 3: JavaScript

JavaScript allows webpages to become interactive and dynamically change their content.

For example, JavaScript can modify an HTML element using:

```javascript
document.getElementById("demo").innerHTML = "Hack the Planet";
```

An HTML button can also execute JavaScript when clicked:

```html
<button onclick='document.getElementById("demo").innerHTML = "Button Clicked";'>
    Click Me!
</button>
```

This demonstrates how JavaScript can interact with HTML elements through the DOM.

## Task 4: Sensitive Data Exposure

Sensitive information can sometimes be accidentally exposed in a website's source code.

By viewing the page source, the following credentials were found inside an HTML comment:

```html
<!--
    TODO: Remove test credentials!
        Username: admin
        Password: testpasswd
-->
```

The password was:

```text
testpasswd
```

The username was:

```text
admin
```

This demonstrates why sensitive information such as passwords should never be stored in publicly accessible source code.

## Task 5: HTML Injection

HTML Injection occurs when a website displays user-controlled input without properly sanitising it.

If the application inserts the user's input directly into the webpage, an attacker may be able to inject HTML elements.

For this task, the following payload was used:

```html
<a href="http://hacker.com">Click here</a>
```

The application rendered the input as an actual HTML link.

This demonstrates how insufficient input sanitisation can allow an attacker to modify the content and functionality displayed on a webpage.

## What I Learned

* The difference between front-end and back-end components.
* How HTML structures webpages.
* How HTML tags and attributes work.
* How JavaScript can modify HTML elements through the DOM.
* How sensitive information can be exposed through page source code.
* What HTML Injection is and why input sanitisation is important.
* How user-controlled input can be interpreted as HTML by the browser.
