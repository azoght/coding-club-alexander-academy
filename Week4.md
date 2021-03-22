# Week 4
## Strings, Lists, and Tuples

This week is all about *sequences* and the basic operations that can be performed on them. Sequences are ordered collections of values of a certain length (which can be returned using the *len()* function), and each kind has a certain *mutability*, or ability to be changed in-place. More on that later.

To get started, here are three fundamental sequences: strings, lists, and tuples.

**Strings**

As mentioned in [Week 1](Week1.md#values-and-data-types), strings are sequences of characters. They are created using either single (') or double ('') quotes
```python
a = "This is Week 4" # double-quoted string
b = 'This is Week 4' # single-quoted string
```
Also, like multi-line comments (see [Week 2](Week2.md#comments)), *multi-line strings* can be created using either three single or double quotes.
```python
# multi-line single-quoted string
c = '''
This is Week 4       
,all about sequences,
and their operations!
'''
# multi-line double-quoted string
d = """
This is Week 4
,all about sequences,
and their operations!
"""
```
The *length* of a string is equal to the number of characters (including spaces) that exist between the quotes of that string. So...
```python
str0 = ""
```
has a length of 0, and...
```python
str1 = " "
```
has a length of 1.

**Lists**

While strings are sequences of characters, lists are sequences of any kind of value. They are created using square brackets ([]), and each item is separated by a comma.
```python
numbers = [1, 2, 3, 4, 5] # list of integers
colours = ["red", "orange", "yellow", "green", "blue", "purple"] # list of strings
```
Certain programming languages say you must specify the type that all items in a list must be, but not Python. You can have items of different types in a list.
```python
mix = [1, "more", 4, "this", 2, "work"] # list of integers and strings
```

**Tuples**

Tuples, like lists are sequences of values of any type. However, the only big thing that makes tuples different from lists is that they're **immutable**, meaning that once they're created, they *can't* be changed. Tuples are created using brackets, and each item is separated by a comma.
```python
t = (2, 4, 5)
```
If you've looked at the documentation for the turtle module, you probably found that the colour of the turtle's fill/pen can be expressed as a tuple of three values: r, g, and b. This is a common way to represent a colour in Python, based on its RGB (Red, Green, Blue) values, where each item in the tuple is an integer between 0 and 255.
```python
import turtle

t = turtle.Turtle() 

t.up()
t.goto(-215,0)
t.width(10)
t.down()

t.color((255,0,0)) # red
t.forward(40)

t.color((255,125,0)) # orange
t.forward(40)

t.color((255,255,0)) # yellow
t.forward(40)

t.color((125,255,0)) # light green
t.forward(40)

t.color((0,255,0)) # green
t.forward(40)

t.color((0,255,125)) # spring green
t.forward(40)

t.color((0,255,255)) # cyan
t.forward(40)

t.color((0,125,255)) # azure
t.forward(40)

t.color((0,0,255)) # blue
t.forward(40)

t.color((125,0,255)) # purple
t.forward(40)

t.color((255,0,255)) # magenta
t.forward(40)
```
![](PythonTurtleCanvases/pythonsandbox-canvas15.png)
## Index Operator and Slice Operator
Strings, lists, and tuples are *ordered* sequences, meaning they have an index, so they come with these operators.

**Index Operator**

Returns the element at a certain index/position of sequence. *x[y]* returns the (y-1)th item of sequence x, because, zero-based indexing.

```python
exclamation = "Wow!"
print(exclamation[1]) # the second character
```
```
o
```
```python
digits_of_pi = [3, 1, 4, 1, 5, 9, 2, 6, 5]
print(digits_of_pi[3]) # the fourth item
print(digits_of_pi[7]) # the eighth item
x = digits_of_pi[3] + digits_of_pi[7]
print(x)
```
```
1
6
7
```
Negative numbers can be indexes too!
```python
this_school = "Alexander Academy"
print(this_school[-3]) # the third last character in this string
```
```
e
```
```python
school_houses = ["Atwood","Carr","Fox","Suzuki"]
print(school_houses[-1]) # the last item in this list
```
```
Suzuki
```

**Slice Operator**
Returns part of a sequence, has similar syntax to the index operator, except the argument is a range. 

*x[y:z]-* returns a sequence of all items in sequence x from index y to (but not including) index z
```python
card_suit = ["Ace",2,3,4,5,6,7,8,9,10,"Jack","Queen","King"]
print(card_suit[4:11]) # between the fifth and twelvth items
```
```
[5, 6, 7, 8, 9, 10, 'Jack']
```
*x[y:]-* returns a sequence of all items in sequence x from index y onward
```python
card_suit = ["Ace",2,3,4,5,6,7,8,9,10,"Jack","Queen","King"]
print(card_suit[3:]) # between the fourth and last items
```
```
[4, 5, 6, 7, 8, 9, 10, 'Jack', 'Queen', 'King']
```
*x[:z]-* returns a sequence of all items in sequence x up to (but not including) index z
```python
card_suit = ["Ace",2,3,4,5,6,7,8,9,10,"Jack","Queen","King"]
print(card_suit[:10]) # between the first and eleventh item
```
```
['Ace', 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

## Concatenation and Repetition

Other ways to create sequences include concatenation and repetition.

**Concatenation**

Concatenation involves the *addition* of more than one sequence.
```python
cat1 = "Siamese" + " cat"
print(cat1) # string created through addition of strings
```
```
Siamese cat
```
```python
cat2 = ["shorthair", "longhair"] + ["siamese", "bengal", "persian", "ragdoll"] # list created through addition of lists
print(cat2)
```
```
['shorthair', 'longhair', 'siamese', 'bengal', 'persian', 'ragdoll']
```
We can also use concatenation to add to an existing sequence, using the [increment operator](Week2.md#updating-variables).

```python
schedule = ["Today", "we", "will"]
print(schedule)
schedule += ["code", "in", "Python!"] # another list is added
print(schedule)
```
```
['Today', 'we', 'will']
['Today', 'we', 'will', 'code', 'in', 'Python!']
```

**Repetition**

Repetition involves the *multiplication* of a sequence by an integer
```python
rep1 = "Wow " * 8 # will repeat 8 times
print(rep1)
```
```
Wow Wow Wow Wow Wow Wow Wow Wow 
```
```python
rep2 = [1, 2, 3, 4] * 5 # will repeat 5 times
print(rep2)
```
```
[1, 2, 3, 4, 1, 2, 3, 4, 1, 2, 3, 4, 1, 2, 3, 4, 1, 2, 3, 4]
```

## Count and Index
Here are two useful methods for any sequence:

**.count()**

Returns the number of times a specific item is in a sequence
```python
phrase = "You can count on me!"
print(phrase.count("o")) # How many "o"s?
```
```
3
```
It works on subsequences too!
```python
lesson = "Today I learned that the best way to learn is to learn how to learn!"
print(lesson.count("learn")) # How many times is "learn" in this string?
```
```
4
```

**.index()**

Returns the index of a certain item in a sequence 
```python
seasons = ["spring","summer","fall","winter"]
print(seasons.index("summer")) # What is the index of "summer"?
```
```
1
```
If there's more than one of that item in a sequence, the index returned will be that of the **earliest occurrence** of that item in the sequence.
```python
weekday_letters = ['S','M','T','W','T','F','S']
print(weekday_letters.count('T')) # How many 'T's?
print(weekday_letters.index('T')) # What is the index of the first 'T'?
```
```
2
2
```
**But what about the index of a word in a string?**
```python
find_out = "Well, let's see what happens..."
index_of_what = find_out.index("what")
print(index_of_what)
print(find_out[index_of_what])
```
```
16
w
```
That's right. In the case of string, whenever a substring is entered in the index() function, the value return is the index of where that substring *starts*.

And you thought it was going to be a range, didn't you?

**One more thing!**

What happens if you try getting the index of an item that isn't there?
```python
no_x = ["w", "y", 25, "z"]
print(no_x.index("x"))
```
```
ValueError: 'x' is not in list
```
We get a runtime error, of course!

Meanwhile, the count() function is different.
```python
no_x = ["w", "y", 25, "z"]
print(no_x.count("x"))
```
```
0
```
It doesn't return an error, it just returns 0, since "x" occurs no times in this list.

## Split and Join
Here are two other very useful methods, which **only** apply to strings.

**.split()**

Splits a string into a list of its words
```python
break_up = "Let's break it up!"
print(break_up.split())
```
```
["Let's", 'break', 'it', 'up!']
```
By the way, notice I said "words" instead of "characters", but if you want to do *that* instead...
```python
break_further = "Let's break it even further!"
print([char for char in break_further])
```
```
['L', 'e', 't', "'", 's', ' ', 'b', 'r', 'e', 'a', 'k', ' ', 'i', 't', ' ', 'e', 'v', 'e', 'n', ' ', 'f', 'u', 'r', 't', 'h', 'e', 'r', '!']
```
You can also change the substring which you split at, for example...
```python
tongue_twister = "She sells seashells by the seashore"
print(tongue_twister.split("se")) # string is split along each occurence of "se"
```
```
['She ', 'lls ', 'ashells by the ', 'ashore']
```

**.join()**

Joins the items in a list of strings together as a string
```python
friends = ["Ross","Rachel","Chandler","Monica","Phoebe","Joey"]
print(" and ".join(friends)) # each item in the list will have " and " between them
```
```
Ross and Rachel and Chandler and Monica and Phoebe and Joey
```

## The Accumulator Pattern
The accumulator pattern is a pattern where the items in a sequence are *iterated* through using a for loop.  It involves an *accumulator variable* (initialized before the loop), and an *iterator variable* (keeps track of iterations). Each time the loop is executed, the accumulator variable is updated. When the loop ends, the accumulator variable is looked at or used.

Here's an example, where the mean (average) of a list is calculated
```python
numList = [17, 23, 15, 30, 12, 8, 28, 16]
s = 0 # this will be the sum of the numbers in numList
for n in numList:
    s += n # the item "n" (iterator variable) of numList is added to s (accumulator variable)
print(s)
avg = s / len(numList) # to calculate average, the sum is divided by the number of numbers in numList
print(avg)
```
```
149
18.625
```
**Your Turn!** Create a for loop that uses the accumulator pattern for a sequence *other than* a list of numbers. I will have a look at them next week.

## The Range Function
As you'll remember from [last week](Week3.md#loops), the *range()* function outputs a sequence of numbers (actually, it's an *iterable*, not a list, but you get the idea). Let's dive into its usage a little further.

**range(x)-** sequence is whole numbers from 0 up to (but not including) x
```python
for i in range(3): # 0 to 3
    print(i)
print(list(range(3)))
```
```
0
1
2
[0, 1, 2]
```
**range(x,y)-** sequence is whole numbers from x up to (but not including) y
```python
for i in range(2,7): # 2 to 7
    print(i)
print(list(range(2,7)))
```
```
2
3
4
5
6
[2, 3, 4, 5, 6]
```
**range(x,y,z)-** sequence is whole numbers from x up to (but not including) y, with a difference of z between each (Don't worry too much about this one, for now...)
```python
for i in range(0,10,2): # every second number between 0 and 10
    print(i)
print(list(range(0,10,2)))
```
```
0
2
4
6
8
[0, 2, 4, 6, 8]
```
**Your Turn!** Now that you've learned a lot about sequences and how to iterate through them using for loops, it's time to put your skills to the test! Create a program that removes characters or words from a string. We will dive deeper into deleting elements from sequences later on, but the methods we've covered this week are a good place to start. Can't wait to see what you come up with next week! 
