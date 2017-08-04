# List Remove Duplicates  
## Problem

Write a program (_function!_) that takes a list and returns a new list that contains all the elements of the first list minus all the duplicates.

**Extras:**

*Write two different functions to do this - one using a loop and constructing a list, and another using sets.
*Go back and do [Exercise 5](listoverlap.md) using sets, and write the solution for that in a different function.
## Discussion

Concepts :

* Sets
### Sets

In mathematics, a set is a collection of elements where no element is repeated. This becomes useful because if you know your data is stored in a set, you are guaranteed to have unique elements.

### Features of sets

*  Sets are **not ordered**. This means that there is no “first element” or “last element.” There are just “elements”. You cannot ask a set for it’s “next element”.
* There are no repeat elements in sets.
* You can convert between sets and lists very easily.
### In Python

In Python, you make and use a set with the _set()_ keyword. For example:
``` python
  names = set()
  names.add("Michele")
  names.add("Robin")
  names.add("Michele")
  print(names)
  ```
And the output will be;
``` python

  set(['Michele', 'Robin'])
  ```
You can do to a set almost anything you can do to a list (except ask for things like “the third element”). See the [Python documentation about sets](https://docs.python.org/2.7/library/stdtypes.html?highlight=set#set) to get a full list of things you can do to sets.

You can convert from a list to a set and a set to a list pretty easily:
``` python
  names = ["Michele", "Robin", "Sara", "Michele"]
  names = set(names)
  names = list(names)
  print(names)
  ```
And the result of this will be:
``` python
  ['Michele', 'Robin', 'Sara']
  ```