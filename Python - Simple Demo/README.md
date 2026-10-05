# Python: Simple Demo

This room introduces the basics of Python programming by building a simple "Guess the Number" game.

The room focuses on three important concepts in imperative programming:

* Variables
* Conditional statements
* Loops

## Variables

The program starts by creating variables to store the secret number, the user's guess, and the number of attempts.

```python
import random

secret = random.randint(1, 20)
tries = 0
guess = 0
```

The `random.randint()` function generates a random integer between the specified values.

The program then asks the user for input:

```python
text = input("Take a guess: ")
guess = int(text)

tries = tries + 1
```

`input()` receives user input as text, while `int()` converts that text into an integer.

## Conditional Statements

The program uses `if`, `elif`, and `else` to compare the user's guess with the secret number.

```python
if guess < 1 or guess > 20:
    print("That number is out of range. Try again.")
elif guess < secret:
    print("Too low, try again.")
elif guess > secret:
    print("Too high, try again.")
else:
    print("You got it in", tries, "tries!")
```

The conditions allow the program to determine whether the guess is outside the allowed range, too low, too high, or correct.

Python uses `elif` as the equivalent of "else if".

## Loops

The first version of the game only allowed one guess. To allow the player to continue guessing, a `while` loop was introduced.

```python
while guess != secret:
    text = input("Take a guess: ")
    guess = int(text)

    tries = tries + 1
```

The loop continues executing while the user's guess is different from the secret number.

Once the guess matches the secret number, the condition becomes false and the loop stops.

## Complete Program

The final version combines variables, conditionals, and a loop:

```python
import random

secret = random.randint(1, 20)
tries = 0
guess = 0

print("I'm thinking of a number between 1 and 20")

while guess != secret:
    text = input("Take a guess: ")
    guess = int(text)

    tries = tries + 1

    if guess < 1 or guess > 20:
        print("That number is out of range. Try again.")
    elif guess < secret:
        print("Too low, try again.")
    elif guess > secret:
        print("Too high, try again.")
    else:
        print("You got it in", tries, "tries!")
```

## Key Takeaways

* Variables are used to store and update values.
* `input()` receives input from the user.
* `int()` converts a string into an integer.
* `print()` displays information on the screen.
* `if`, `elif`, and `else` are used for conditional logic.
* `while` repeats code while a condition is true.
* `!=` means "not equal to".
* Loops allow the game to continue until the correct number is guessed.

## Conclusion

This room provided a practical introduction to Python by building a simple number guessing game.

It demonstrated how variables, conditional statements, and loops work together to create a functional program. It also provided a foundation for understanding more complex Python programs and automation scripts.
