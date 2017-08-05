# Read From File 
## Problem

Given a _.txt_ file that has a list of a bunch of names, count how many of each name there are in the file, and print out the results to the screen. I have a .txt file for you, if you want to use it!

##### Extra:

* Instead of using the _.txt_ file from above (or instead of, if you want the challenge), take this .txt file, and count how many of each “category” of each image there are. This text file is actually a list of files corresponding to the SUN database scene recognition database, and lists the file directory hierarchy for the images. Once you take a look at the first line or two of the file, it will be clear which part represents the scene category. To do this, you’re going to have to remember a bit about string parsing in Python 3. I talked a little bit about it [in this post.](Stringlists.md)
### Discussion

#####  Topics:

1. Reading a file
2. Dictionaries
### Reading a File

Reading a file is very analogous to writing a file, as [I discussed before in Exercise 21.](writeafile.md) But, the best source is always the official [Python 2.7 documentation.](https://docs.python.org/2.7/tutorial/inputoutput.html#reading-and-writing-files)

Simply, reading to a file takes two steps:

1. Opening the file for reading
2. Read!
Opening a file for reading is the same as opening for writing, just using a different flag:
``` python

  with open('file_to_read.txt', 'r') as open_file:
    all_text = open_file.read()
  ```  
Note how the _'r'_ flag stands for “read”. The code sample from above reads the entire _open_file_ all at once into the _all_text variable_. But, this means that we now have a long string in _all_text_ that can then be manipulated in Python using any string methods you want.

Another way of reading data from the file is line by line:
``` python
  with open('file_to_read.txt', 'r') as open_file:
  	line = open_file.readline()
  	while line:
    	print(line)
    	line = open_file.readline()
```
Instead of _print(line)_, you can imagine doing anything you want to the line of text… If you save it to a variable, you have a string that you can then use something like _.strip()_ or _.split()_ with.


### Dictionaries

Dictionaries are Python’s way of associating two pieces of data together. The [official documentation](https://docs.python.org/2.7/tutorial/datastructures.html#dictionaries) says it all.
``` python
  student_scores = {'Adama': 100, 'Starbuck': 75, 'Apollo': 80, 'Athena': 85, 'Agathon': 90}
  ```
The strings (or whatever happens to the left of the : sign), are called keys. When I want to access the values (the things to the right of the : sign), I need to ask the dictionary for the value associated with the key:
``` python
  adama_score = student_scores['Adama']
  ```
You can then modify the score and save it back to the dictionary:

``` python
  adama_score = student_scores['Adama']
  adama_score += 100	% adama_score is now 200. This doesn't change the dictionary value
  student_scores['Adama'] = adama_score		% the score in the dictionary is now updated
  ```
I can’t ask the dictionary for the key associated with a value, but I can get a list of all the keys, and the same for all the values:
``` python
  all_scores = student_scores.keys()
  all_names = student_scores.values()
  ```
I can use the _in_ keyword (just like in lists), do _dictionary comprehensions_ like list comprehensions (these are cool, take a look at the [official bit about these](https://docs.python.org/2.7/tutorial/datastructures.html#dictionaries)), and iterate over the elements in the dictionary (the syntax is just a little bit different).
``` python
  for pair in student_scores.items():
  	print(pair)
  ```
And this prints out pairs of keys and values that look like: _(Adama, 100)_, etc.

Because dictionaries are not ordered, looping through them does not guarantee the key / value pairs coming out in a particular order. So be careful.