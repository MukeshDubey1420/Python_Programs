# Birthday Dictionaries 
## Exercise 

_This exercise is Part 1 of 4 of the birthday data exercise series. The other exercises are: [Part 2](http://www.practicepython.org/exercise/2017/02/06/34-birthday-json.html), [Part 3](http://www.practicepython.org/exercise/2017/02/28/35-birthday-months.html), and [Part 4](http://www.practicepython.org/exercise/2017/04/02/36-birthday-plots.html)._

For this exercise, we will keep track of when our friend’s birthdays are, and be able to find that information based on their name. Create a dictionary (in your file) of names and birthdays. When you run your program it should ask the user to enter a name, and return the birthday of that person back to them. The interaction should look something like this:
```sh
>>> Welcome to the birthday dictionary. We know the birthdays of:
Albert Einstein
Benjamin Franklin
Ada Lovelace
>>> Who's birthday do you want to look up?
Benjamin Franklin
>>> Benjamin Franklin's birthday is 01/17/1706.
```
Happy coding!

### Discussion topics

1. Dictionaries
2. String formatting, briefly

#### Dictionaries

We covered dictionaries in [a previous exercise](http://www.practicepython.org/exercise/2014/12/06/22-read-from-file.html), but it’s been long enough that we will review them here and add a few more notes.

##### QUICK REVIEW

The main topic for this week is the concept of a _dictionary_. In Python they are called dictionaries, but in other languages they may be called _maps_ or _hashmaps_. The concept is the same: it is a way to use a _key_ to access some _value_. It is mapping one set of data (the keys) to another set of data (the values). The only way to access the _value_ part of the dictionary is to use the _key_.

As an example, grocery store systems can store the prices for various items by using a dictionary. In Python, it would look something like this:

```python
price_dictionary = {
	"banana": 1.50,
	"avocado": 0.99,
	"heirloom tomato": 0.89,
	"cherry tomato pack": 3.00
}
```

You specify the dictionary between the {}. Key / value pairs are specified as list (separated by commas). The _key_ is on the left side, and the _value_ is on the right side. Notice how I split up the dictionary definition on multiple lines - I did that just for convenience. You can also write the dictionary on the entire line, but it is hard to read (and it probably even goes off your browser window screen):

```python
price_dictionary = {
	"banana": 1.50, "avocado": 0.99, "heirloom tomato": 0.89, "cherry tomato pack": 3.00}
```

Now that we have the dictionary, we can query it (ask it) for the values associated with each key (for the prices associated with each food). We do that using brackets ([]). For example, to get the price of a banana:

```sh
>>> print(price_dictionary["banana"])
1.50
```
To get a list of all the keys, use the .keys() method:
```sh
>>> print(price_dictionary.keys())
["banana", "avocado", "heirloom tomato", "cherry tomato pack"]
```
We have created our dictionary with many items in it, but we can also add items to it one by one. It is almost like accessing an element in the dictionary, except instead of using the element, we assign something to it.
```sh
>>> price_dictionary["granny smith apple"] = 0.49
>>> price_dictionary["red delicious apple"] = 0.35
>>> print(price_dictionary["granny smith apple"])
0.49
```
Not all key / value pairs have to be the same. You can do something like:
```sh
>>> price_dictionary["dog food"] = "only at Petco"
>>> print(price_dictionary["dog food"])
```
only at Petco
Of course, this can get messy quickly, so be careful!

###### MORE ON DICTIONARY KEYS

Dictionary keys must be unique. If you try to add an element to your dictionary with the same key, it will overwrite the value previously at that key:
```sh
>>> print(price_dictionary["dog food"])
only at Petco
>>> price_dictionary["dog food"] = 10.99
>>> print(price_dictionary["dog food"])
10.99
```
If you try to ask the dictionary for a key that doesn’t exist, it will throw a KeyError in your console, or your program will crash:
```sh
>>> price_dictionary["lemon"]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'lemon'
```
We will talk about how to “catch” errors in later exercises, but for now, there is another way to make sure you don’t throw an error. Instead of accessing elements in a dictionary with the [] notation, you can instead use the .get() method. As the second argument to .get(), you write down what the default value is for the dictionary: if there is no key like the one you wanted, what the dictionary should return:
```sh
>>> print(price_dictionary.get("banana", "no food like this"))
1.50
>>> print(price_dictionary.get("lemon", "no food like this"))
no food like this
```
This can be a helpful way of avoiding causing your program to crash.

Not all Python objects can be keys to a dictionary. For something to be a key in a dictionary, it must be immutable. Basically, it means that you can’t change that variable somewhere else. So for example, numbers and strings can be keys in a dictionary, but lists cannot. Because you can .append() to a list, it cannot be a key in your dictionary. Lists can be values, just not keys:
```sh
>>> price_dictionary[[1, 2, 3]] = "new food"
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unhashable type: 'list'
>>> price_dictionary["lettuce"] = [1.50, 3.50]
>>> print(price_dictionary["lettuce"])
[1.50, 3.50]
```
Lastly, if we want to check if a particular key is in our dictonary, it is very easy. Just use the in keyword:
```sh
>>> "lemon" in price_dictionary
False
>>> "banana" in price_dictionary
True
```
These checks can be used together with if statements to make more complex programs.

### String formatting

We’ve talked about strings a lot on this blog:

[Exercise 1 about printing basic strings](http://www.practicepython.org/exercise/2017/01/24/(/exercise/2014/01/29/01-character-input.html)) 

[Exercise 6 about turning strings into lists](http://www.practicepython.org/exercise/2017/01/24/(/exercise/2014/03/12/06-string-lists.html))

[Exercise 15 about where `join` statements are introduced](http://www.practicepython.org/exercise/2017/01/24/(/exercise/2014/03/12/06-string-lists.html))
   
But we want to introduce one more optional concept for this exercise related to string formatting. There are a number of ways to format strings in Python, so I am just going to show you one quick way for a scenario you find yourself in often while programming.

A common scenario is like this: you want to print both a string and a number in the same line using one print() statement. You can solve this problem like so:

```sh
>>> a = 1
>>> b = 10
>>> print("my number is " + str(a) + " and his number is " + str(b))
my number is 1 and his number is 10
```
But it gets tedious to use + and str(). Instead, you can use the .format() method to cast (i.e. transform) your number into a string when it gets printed.
```sh
>>> a = 1
>>> b = 10
>>> print("my number is {} and his number is {}".format(a, b))
my number is 1 and his number is 10
```
What we are doing is substituting the symbol {} in the print statement in the string we want to display in the exact place we want the number to go, and use the .format() to pass variables to the {} that appear in order. What happens is the variables a and b get converted into strings automatically and injected into our print statement cleanly. You can do this with floats, lists, dictionaries, or anything else you want to display.

There are a number of different formatting options if you want to get specific about how many decimal points to display, etc., but that is out of the scope of this exercise. If you want to read more about string formatting in Python, you can read about it [on this helpful website that goes into a great amount of detail](https://pyformat.info/).