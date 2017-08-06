# Birthday Months  
## Exercise 

This exercise is Part 3 of 4 of the birthday data exercise series. The other exercises are: [Part 1](http://www.practicepython.org/exercise/2017/01/24/33-birthday-dictionaries.html), [Part 2](http://www.practicepython.org/exercise/2017/01/24/33-birthday-dictionaries.html), and [Part 4](http://www.practicepython.org/exercise/2017/01/24/33-birthday-dictionaries.html).

In the [previous exercise](http://www.practicepython.org/exercise/2017/02/06/34-birthday-json.html) we saved information about famous scientists’ names and birthdays to disk. In this exercise, load that JSON file from disk, extract the months of all the birthdays, and count how many scientists have a birthday in each month.

Your program should output something like:
```python
{
	"May": 3,
	"November": 2,
	"December": 1
}
```
### Discussion

You already have the skills to achieve this exercise with concepts we’ve already covered: for [loops](http://www.practicepython.org/exercise/2014/02/15/03-list-less-than-ten.html), [dictionaries](http://www.practicepython.org/exercise/2014/02/15/03-list-less-than-ten.html), and basic arithmetic. However, I want to talk about a Python built-in called a Counter.

A [counter](http://www.practicepython.org/exercise/2014/02/15/03-list-less-than-ten.html) takes a list and counts how many of each element were in the list. To use the Counter, first import it from collections:

```python
from collections import Counter
```
This lets you use the Counter data structure built into Python in your program. Then, give it a list:
```python
sandwiches = ["ham", "cheese", "roast beef", "ham", "cheese", "roast beef", "ham"]
c = Counter(sandwiches)
```
If you print(c), you will see this:
```python
Counter({"ham": 3, "roast beef": 2, "cheese": 2})
```
This means there are 3 ham, 2 roast beef, and 2 cheese sandwiches in my list. I can get this information directly from the Counter:
```sh
>>> print("There are {} ham sandwiches".format(c["ham"]))
There are 3 ham sandwiches
```
Hope this is useful!