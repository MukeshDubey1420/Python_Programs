# Character Input
## Problem

Create a program that asks the user to enter their name and their age. Print out a message addressed to them that tells them the year that they will turn 100 years old.
### Extras:

1. Add on to the previous program by asking the user for another number and printing out that many copies of the previous message. (Hint: [order of operations](http://www.mathsisfun.com/operation-order-pemdas.html) exists in Python)
2. Print out that many copies of the previous message on separate lines. (Hint: the string "\n is the same as pressing the ENTER button)

### Discussion:

Concepts:

* Getting user input
* Manipulating strings (a few ways)

#### User input in Python
To get user input in Python (2.7.x), the command you use is [raw_input()](https://docs.python.org/2/library/functions.html#raw_input). Store the result in a variable, and use it to your heart’s content. Remember that the result you get from the user will be a string, even if they enter a number.

For example,

```python
name = raw_input("Give me your name: ")
print("Your name is " + name)
```

What this will print in the terminal (or the shell, whatever you are running Python in) will be:

```python
>>> Give me your name: Michele
Your name is Michele
```

What happens at the end of raw_input() is that it waits for the user to type something and press ENTER. Only after the user presses ENTER does the program continue.

#### Manipulating strings (a few ways)

What you get from the raw_input() function is a string. What can you do with it?

First: Make the string into a number. Let’s say you are 100% positive that the user entered a number. You can turn the string into an integer with the function [int()](https://docs.python.org/2/library/functions.html#int). Here is what this looks like:

```python
age = raw_input("Enter your age: ")
age = int(age)
```

(or, if you want to be more compact with your code)

```python
age = int(raw_input("Enter your age: "))
```
	
In both cases, age will hold a variable that is an integer, and now you can do math with it.

(Note, you can also turn integers into strings exactly in the opposite way, using the [str()](https://docs.python.org/2/library/functions.html#str) function)

Second: Do math with strings. What do I mean by that? I mean, if I want to combine (**concatenate** is the computer science word for this) strings, all I need to do is add them:

```python
print("Were" + "wolf")
print("Door" + "man")
print("4" + "chan")
print(str(4) + "chan")
```

The same works for multiplication:

```python
print(4 * "test")
```

but division and subtraction do not work like this. In terms of multiplication, the idea of multiplyling two strings together is not well-defined. What does it mean to multiply two strings in the first place? However, it makes sense in a way to specify multiplying a string by a number - just repeat that string that number of times. Try this in your own program with all the arithmetic operations with numbers and strings - the best way to get a feel for what works and what doesn’t is to try it!