# Guessing Game One   
## Problem 

Generate a random number between 1 and 9 (including 1 and 9). Ask the user to guess the number, then tell them whether they guessed too low, too high, or exactly right. (_**Hint**: remember to use the user input lessons from the very [first exercise](characterinput.md)_)

Extras:

* Keep the game going until the user types “exit”
* Keep track of how many guesses the user has taken, and when the game ends, print this out.
Discussion

### Concepts :

* Modules
* Random numbers
* User input
### Random Numbers (and Modules)

This is your first exposure to using Python code that somebody else wrote. In Python, these formally-distributed code packages are called _modules._ The thing we want from a module in this exercise is the ability to generate random numbers. This comes from the _random_ module.

To use a module, at the top of your file, type
``` python
	import random
  ```
This means you are allowing your Python program to use a module called _random_ in the rest of your code.

To use it (and generate a random integer), now type:
``` python
	a = random.randint(2, 6)
```
Once you run this program, the variable a will have a random integer that the computer made for you, between 2 and 6 (including 2 and 6). The specific documentation for this method is [here](https://docs.python.org/2.7/library/random.html#random.randint).

There are many ways you can generate random numbers - integers, decimals, and much more. The [Python documentation](https://docs.python.org/2.7/library/random.html) has much more detailed information about what is possible from the _random_ module.

### User input

We covered all you need to know in the [first exercise](characterinput.md) of this blog!