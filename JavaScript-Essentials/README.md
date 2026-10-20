# TryHackMe - JavaScript Essentials

## Room Information

- Platform: TryHackMe
- Room: JavaScript Essentials
- Category: Web Security
- Difficulty: Beginner
- Status: Completed
- Room Link: https://tryhackme.com/room/javascriptessentials

## Objectives

Learn the fundamentals of JavaScript and understand how it can be used in web development and web application security.

Topics covered:

- JavaScript variables, data types, functions, and loops
- Integrating JavaScript into HTML
- JavaScript dialogue functions
- Bypassing client-side control flow
- Analyzing minified and obfuscated JavaScript
- JavaScript security best practices

## Tasks and Answers

### Task 1: Introduction

Objective: Understand the purpose of JavaScript and prepare the virtual lab environment.

Status: Completed

### Task 2: Essential Concepts

Objective: Learn about variables, data types, functions, loops, and the request-response cycle.

Question: What term allows you to run a code block multiple times as long as a condition is true?

Answer: `Loop`

### Task 3: JavaScript Overview

Objective: Execute JavaScript code in the browser console and understand basic operations.

Question 1: What is the output if x is changed to 10?

Answer: `The result is: 20`

Question 2: Is JavaScript a compiled or interpreted language?

Answer: `Interpreted`

### Task 4: Integrating JavaScript in HTML

Objective: Understand internal and external JavaScript integration.

Question 1: Which type of JavaScript integration places code directly within the HTML document?

Answer: `Internal`

Question 2: Which method is better for reusing JavaScript across multiple web pages?

Answer: `External`

Question 3: What is the name of the external JavaScript file called by external_test.html?

Answer: `thm_external.js`

Question 4: What attribute links an external JavaScript file in the script tag?

Answer: `src`

### Task 5: Abusing Dialogue Functions

Objective: Explore alert(), prompt(), and confirm() and understand how JavaScript can be abused.

Question 1: In invoice.html, how many times does the code show the alert "Hacked"?

Answer: `5`

Question 2: Which JavaScript interactive element asks the user for input?

Answer: `prompt()`

Question 3: If the user enters Tesla, what value is stored in the carName variable?

Answer: `Tesla`

### Task 6: Bypassing Control Flow Statements

Objective: Understand conditional statements and the security risks of client-side authentication.

Question 1: What message is displayed if the entered age is less than 18?

Answer: `You are a minor.`

Question 2: What is the password for the user admin?

Answer: `ComplexPassword`

### Task 7: Exploring Minified Files

Objective: Learn about JavaScript minification, obfuscation, and deobfuscation.

Question 1: What alert message appears after running hello.html?

Answer: `Welcome to THM`

Question 2: What is the value of the age variable?

Code:

```javascript
age = 0x1 * 0x247e + 0x35 * -0x2e + -0x1ae3;
```

Answer: `21`

### Task 8: Best Practices

Objective: Understand secure JavaScript development practices.

Question: Is it good practice to blindly include JavaScript from any source?

Answer: `nay`

### Task 9: Conclusion

Status: Completed

Successfully completed the JavaScript Essentials room.

## Key Security Takeaways

### 1. Client-Side Validation

Client-side validation improves usability but can be manipulated or bypassed. Sensitive validation and authorization must also be enforced on the server.

### 2. Client-Side Authentication Risks

Credentials and authentication logic stored in browser-accessible JavaScript can be inspected by users. Authentication should be implemented and enforced securely on the server.

### 3. JavaScript Dialogue Functions

- `alert()` displays a message.
- `prompt()` requests user input.
- `confirm()` asks the user to confirm an action.

These functions can be abused to disrupt the user experience, especially when executed repeatedly.

### 4. Minification and Obfuscation

- Minification removes unnecessary characters to reduce file size.
- Obfuscation makes code more difficult to understand.
- Deobfuscation helps recover a more readable representation of obfuscated code.

Neither minification nor obfuscation should be treated as a security boundary.

### 5. Secure Coding Practices

- Validate input on the server.
- Avoid hardcoded credentials, API keys, and access tokens in client-side code.
- Use trusted JavaScript libraries and verify their sources.
- Review external scripts and dependencies.
- Apply appropriate access controls and secure authentication practices.

## What I Learned

This room introduced me to JavaScript from a cybersecurity perspective. I learned how browser-side code works, how to inspect scripts, and why client-side validation and authentication logic can create security vulnerabilities.

These concepts provide a foundation for further studies in web application security, penetration testing, and vulnerability analysis.

## Completion

Room completed: JavaScript Essentials

Next step: Continue learning about web application vulnerabilities, including Cross-Site Scripting (XSS), and practice identifying security weaknesses in authorized lab environments.
