# Reverse Word Order   
   _strings_
## Problem

Write a program (using functions!) that asks the user for a long string containing multiple words. Print back to the user the same string, except with the words in backwards order. For example, say I type the string:

  _My name is Michele_
Then I would see the string:

  _Michele is name My_
shown back to me.

### Discussion

Concepts :

* More string things
### More string things

Python has a lot of interesting things you can do with strings. I will show a few here, but you can see many more methods that may or may not be useful at the [official Python documentation about the string format.](https://docs.python.org/2.7/library/stdtypes.html?highlight=strings#string-methods)

Remember that [strings are lists.](Stringlists.md)

### Splitting strings

You can “split” or tear apart strings based on a given set of characters. For example:
``` python
  teststring = "this is a test"
  result = teststring.split("t")
  ```
And at the end, result will contain the list:
``` python
  ['', 'his is a ', 'es', '']
  ```
Instead of "t", you can write any character you want. If you do not include any character, it means “split on all whitespace”:
``` python
  teststring = "  this      has a lot    of   spaces and    tabs"
  result = testring.split()
  ```
Then result contains:
``` python
  ['this', 'has', 'a', 'lot', 'of', 'spaces', 'and', 'tabs']
  ````
### Joining strings

You can also relatively easily “join” or “smush” strings together:
``` python
  listofstrings = ['a', 'b', 'c']
  result = "**".join(listofstrings)
 ``` 
Then result will contain the string:
``` python
  a**b**c
  ```
Take a look at the official Python documentation for more information.