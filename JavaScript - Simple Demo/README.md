# JavaScript: Simple Demo

This room introduces the basics of JavaScript through a simple number guessing game.

## Topics Covered

* JavaScript variables
* Constants
* User input
* `console.log()`
* `parseInt()`
* Conditional statements
* `if`, `else if`, and `else`
* `while` loops
* Comparison operators
* Running JavaScript with Node.js

## Variables and Constants

JavaScript uses `let` to declare variables and `const` to declare constants.

Example:

```javascript
let tries = 0;
let guess = 0;

const secret = Math.floor(Math.random() * 20) + 1;
```

The `secret` constant stores a random number between 1 and 20.

## User Input

Node.js can use the `readline` module to receive input from the user.

```javascript
const text = await rl.question("Take a guess: ");
guess = parseInt(text, 10);
```

The input is initially received as text and then converted into an integer using `parseInt()`.

## Conditional Statements

The program uses conditional statements to compare the user's guess with the secret number.

```javascript
if (guess < 1 || guess > 20) {
    console.log("That number is out of range. Try again.");
} else if (guess < secret) {
    console.log("Too low, try again.");
} else if (guess > secret) {
    console.log("Too high, try again.");
} else {
    console.log("You got it in", tries, "tries!");
}
```

These conditions allow the program to provide feedback depending on the user's guess.

## While Loop

A `while` loop allows the program to continue asking for guesses until the user finds the correct number.

```javascript
while (guess !== secret) {
    // Ask for another guess
}
```

The `!==` operator means "not equal".

The `tries` variable is incremented each time the user makes a new guess.

## Running the Program

The program can be executed with Node.js:

```bash
node guess_v3.js
```

The game generates a new random number every time the program is started.

## Key Takeaways

This room introduced three important concepts used in imperative programming:

* Variables
* Conditional statements
* Loops

It also provided practical experience with user input and basic JavaScript syntax.

## Conclusion

This room was an introduction to JavaScript using a simple number guessing game. The program demonstrated how variables, conditionals, loops, user input, and basic operators can be combined to create an interactive command-line application.
