# Week 6

Runestone: [9](https://runestone.academy/runestone/books/published/fopp/TransformingSequences/toctree.html)

## Mutability

As mentioned in [Week 4](Week4.md#strings-lists-and-tuples), each type of sequence has a *mutability*. Let's start with lists.

Lists are *mutable*, meaning they can be changed/modified. Here's one way you can change the items in a list.
```python
ice_cream_flavours = ["vanilla","chocolate","strawberry"]
print(ice_cream_flavours)

ice_cream_flavours[-1] = "cookies and cream"
print(ice_cream_flavours)
```
```
['vanilla', 'chocolate', 'strawberry']
['vanilla', 'chocolate', 'cookies and cream']
```
You can even modify part of a list the same way.
```python
card_deck = [2,3,4,5,6,7,8,9,10,"Jack","Queen","King","Ace"]
print(card_deck)

card_deck[9:] = ['J','Q','K','A']
print(card_deck)
```
```
[2, 3, 4, 5, 6, 7, 8, 9, 10, 'Jack', 'Queen', 'King', 'Ace']
[2, 3, 4, 5, 6, 7, 8, 9, 10, 'J', 'Q', 'K', 'A']
```
Strings are *immutable*, meaning they can't be changed/modified in-place. Let's see what happens when we try to modify one the same way we would for a list.
```python
tweety_bird = "I thought I taw a putty tat!"

tweety_bird[12] = 's' # to replace 'taw' with 'saw'
print(tweety_bird)
```
```
TypeError: 'str' object does not support item assignment
```
Yet another runtime error!

We *can* modify a string through *concatenation*, as mentioned in [Week 4](Week4.md#concatenation-and-repetition).
```python
x = "I need some water, please."
print(x)

x = "L" + x[13:18] + " sk" + x[13:17] + "!" # changed through concatenation
print(x)
```
```
I need some water, please.
Later, skater!
```
Tuples are also *immutable*.
```python
cyan = (0, 255, 255) # RGB tuple for cyan
print("The RGB for cyan is",cyan)

cyan[-2] = 240
print(cyan)
```
```
The RGB for cyan is (0,255,255)
TypeError: 'tuple' object does not support item assignment
```
But you *can* reassign them. 
```python
polygons = ("triangle",3,"rectangle",4,"pentagon",5,"hexagon",6)
print(polygons)

polygons = ("triangle",3,"quadrilateral",4,"pentagon",5,"hexagon",6)
print(polygons)
```
```
('triangle', 3, 'rectangle', 4, 'pentagon', 5, 'hexagon', 6)
('triangle', 3, 'quadrilateral', 4, 'pentagon', 5, 'hexagon', 6)
```

## Deleting Elements

If we want to delete an item from a list, we can use slicing.
```python
phone_brands = ["Apple","Blackberry","Google","Huawei","Motorolla","Samsung"]
print(phone_brands)

phone_brands = phone_brands[0:phone_brands.index("Blackberry")] + phone_brands[phone_brands.index("Blackberry") + 1:] # deleting "Blackberry" from list
print(phone_brands)
```
```
['Apple', 'Blackberry', 'Google', 'Huawei', 'Motorolla', 'Samsung']
['Apple', 'Google', 'Huawei', 'Motorolla', 'Samsung']
```
Or...you can just use the *del* operator, which is used a little differently than other operators we've encountered so far.
```python
classes = ["Foundations","Pre-Calc","Calculus","Comp","Creative Writing","Science","Chem","Physics","Bio","Environmental Sciences","Psych","Socials","Geo","History","Econ Theory","Law","French","German","Business","ICT","Visual Arts","Photography","Film & TV","CLE","CLC"] # classes offered (and not offered) at Alexander Academy
print(classes)

del classes[4] # deletes 'Creative Writing'
print(classes)

del classes[6:10]
print(classes)
```
```
['Foundations', 'Pre-Calc', 'Calculus', 'Comp', 'Creative Writing', 'Science', 'Chem', 'Physics', 'Bio', 'Environmental Sciences', 'Psych', 'Socials', 'Geo', 'History', 'Econ Theory', 'Law', 'French', 'German', 'Business', 'ICT', 'Visual Arts', 'Photography', 'Film & TV', 'CLE', 'CLC']
['Foundations', 'Pre-Calc', 'Calculus', 'Comp', 'Science', 'Chem', 'Physics', 'Bio', 'Environmental Sciences', 'Psych', 'Socials', 'Geo', 'History', 'Econ Theory', 'Law', 'French', 'German', 'Business', 'ICT', 'Visual Arts', 'Photography', 'Film & TV', 'CLE', 'CLC']
['Foundations', 'Pre-Calc', 'Calculus', 'Comp', 'Science', 'Chem', 'Geo', 'History', 'Econ Theory', 'Law', 'French', 'German', 'Business', 'ICT', 'Visual Arts', 'Photography', 'Film & TV', 'CLE', 'CLC']
```

## Objects and References

When values are assigned to variables (or *references*), they are stored in certain addresses or given specific identifications. The *is* operator returns True if the preceding variable has the **same** address/id as the succeeding variable.  [(9.4: Objects and References)](https://runestone.academy/runestone/books/published/fopp/TransformingSequences/ObjectsandReferences.html)

Let's say you made two variables, x and y, with the exact same string as a value. What would *(x is y)* return? 
```python
x = "Python"
y = "Python"

print(x is y) # Does x have the same address as y?
```
```
True
```
Surprise, surprise! Though the *variable names* are different, the *addresses* are the same, since x and y are pointing to the **exact same** value!

But what if the values were *lists* instead? Let's see what happens...
```python
x = ["Python","is","awesome"]
y = ["Python","is","awesome"]

print(x is y) # Do these lists have the same address?
```
```
False
```
You're probably thinking, *How could this be? The lists are the exact same, so shouldn't they have the same address?* Not exactly, because, you see, unlike strings, lists are mutable. In other words, two references to lists with the exact same contents are given different addresses, so that if a change is made to one, that change won't be made to the other.

## Aliasing and Cloning

**Aliasing** [(9.5: Aliasing)](https://runestone.academy/runestone/books/published/fopp/TransformingSequences/Aliasing.html)

This is done when the variable referring to a sequence is assigned to another variable, for example...
```python
sandy = [9,"3",2, 7,"2",1,"Hey"]
print(sandy)
print("The id of Sandy is",id(sandy)) # we get the random id of sandy

nancy = sandy # the list has been aliased to sandy and nancy
print(nancy)
print("The id of Nancy is",id(nancy)) # the ids should be the same
```
```
[9, '3', 2, 7, '2', 1, 'Hey']
The id of Sandy is 140131862662528
[9, '3', 2, 7, '2', 1, 'Hey']
The id of Nancy is 140131862662528
```
Now let's say we wanted to *change* a list after it has been aliased. Here's what we get.
```python
freddie = ["Mercury","Queen",2018,1991,"Bohemian Rhapsody"]
print("Freddie Mercury:",freddie)

rami = freddie # aliasing freddie and rami
print("Rami Malek has been aliased from Freddie Mercury!")
rami[3] = 1976 # changing the fourth element of rami

print("Freddie Mercury:",freddie) # But does it change freddie?

print(freddie == rami) # Are the contents of freddie and rami the same?
print(freddie is rami) # Do they have the same id?
```
```
['Mercury', 'Queen', 2018, 1991, 'Bohemian Rhapsody']
Rami Malek has been aliased from Freddie Mercury!
['Mercury', 'Queen', 2018, 1976, 'Bohemian Rhapsody']
True
True
```
Since *freddy* and *rami* are referring to the same address, then a change to *rami* is the same change to *freddy*.  We are the champions (of aliasing)!

**Cloning** [(9.6: Cloning Lists)](https://runestone.academy/runestone/books/published/fopp/TransformingSequences/CloningLists.html)

This is done when the contents (or part of the contents) of one list are *copied* to another list, for example...
```python
hans = [8,"14",10,11,"Wazzup"]
print(hans)
print("The id of Hans is",id(hans)) # we get the random id of hans

vance = hans[:] # the list has been cloned from hans to vance
print(vance)
print("The id of Vance is",id(vance)) # the ids shoud be different this time
```
```
[8, '14', 10, 11, 'Wazzup']
The id of Hans is 140662277057984
[8, '14', 10, 11, 'Wazzup']
The id of Vance is 140662276430272
```
What happens when we modify the list *this* time?
```python
jennifer = ["Anniston",1969,"Friends",1994,2003]
print("Jennifer",jennifer[0]+", born",str(jennifer[1])+", was on the TV sitcom",jennifer[2],"from",jennifer[3],"to",str(jennifer[4])+".")

rachel = jennifer[:] # all items from jennifer cloned to rachel
print("Rachel Green has been cloned from Jennifer Anniston!")
rachel[0] = "Green"
del rachel[1]

print("Rachel",rachel[0],"is a character from the TV sitcom",rachel[1]+", which aired from",rachel[2],"to",str(rachel[3])+".")

print(jennifer == rachel) # Are the contents of jennifer and rachel the same?
print(jennifer is rachel) # Do they have the same id?
``` 
```
Jennifer Anniston, born 1969, was on the TV sitcom Friends from 1994 to 2003.
Rachel Green has been cloned from Jennifer Anniston!
Rachel Green is a character from the TV sitcom Friends, which aired from 1994 to 2003.
False
False
```
Since *jennifer* and *rachel* are referring to different addresses, this means that a change to *rachel* **doesn't** make the same change to *jennifer*. So, no one told you it was gonna be this way (insert 4 claps here)!

## Methods on Lists and Strings

**Mutating Methods on Lists** [(9.7.1: List Methods)](https://runestone.academy/runestone/books/published/fopp/TransformingSequences/MutatingMethods.html#list-methods)

The following methods change lists in Python.

*.append()*- adds an item to a list
```python
teachers = ["Hildebrand","Spencer","Yee","Garcia","Gastin","Lai","Ramsay","Cook","Sandhu","Guan","Vicedom"] # teachers at Alexander Academy

print("Before:",teachers)

teachers.append("Zoght") # Looks like I'm the new teacher here!

print("After:",teachers)
```
```
Before: ['Hildebrand', 'Spencer', 'Yee', 'Garcia', 'Gastin', 'Lai', 'Ramsay', 'Cook', 'Sandhu', 'Guan', 'Vicedom']
After: ['Hildebrand', 'Spencer', 'Yee', 'Garcia', 'Gastin', 'Lai', 'Ramsay', 'Cook', 'Sandhu', 'Guan', 'Vicedom', 'Zoght']
```
*.insert()*- inserts a certain item to a certain index of a list
```python
teachers = ["Hildebrand","Spencer","Yee","Garcia","Gastin","Lai","Ramsay","Cook","Sandhu","Guan","Vicedom","Zoght"] # teachers at Alexander Academy

print("Before:",teachers)

teachers.insert(5, "Berthelet") # Ms. Berthelet is a new addition to our school! She'll be inserted at index 5.

print("After:",teachers)
```
```
Before: ['Hildebrand', 'Spencer', 'Yee', 'Garcia', 'Gastin', 'Lai', 'Ramsay', 'Cook', 'Sandhu', 'Guan', 'Vicedom', 'Zoght']
After: ['Hildebrand', 'Spencer', 'Yee', 'Garcia', 'Gastin', 'Berthelet', 'Lai', 'Ramsay', 'Cook', 'Sandhu', 'Guan', 'Vicedom', 'Zoght']
```
*.pop()*- removes and returns the last item from a list, unless a certain index is given
```python
teachers = ["Hildebrand","Spencer","Yee","Garcia","Gastin","Berthelet","Lai","Ramsay","Cook","Sandhu","Guan","Vicedom","Zoght"] # teachers at Alexander Academy

print("Before:",teachers)

last = teachers.pop() # Nevermind, I'm just a student...

print("After:",teachers)

print(last+"!")
```
```
Before: ['Hildebrand', 'Spencer', 'Yee', 'Garcia', 'Gastin', 'Berthelet', 'Lai', 'Ramsay', 'Cook', 'Sandhu', 'Guan', 'Vicedom', 'Zoght']
After: ['Hildebrand', 'Spencer', 'Yee', 'Garcia', 'Gastin', 'Berthelet', 'Lai', 'Ramsay', 'Cook', 'Sandhu', 'Guan', 'Vicedom']
Zoght!
```
*.reverse()*- reverses the order of items in a list
```python
teachers = ["Hildebrand","Spencer","Yee","Garcia","Gastin","Berthelet","Lai","Ramsay","Cook","Sandhu","Guan","Vicedom"] # teachers at Alexander Academy

print("Before:",teachers)

teachers.reverse() # list is reversed

print("After:",teachers)
```
```
Before: ['Hildebrand', 'Spencer', 'Yee', 'Garcia', 'Gastin', 'Berthelet', 'Lai', 'Ramsay', 'Cook', 'Sandhu', 'Guan', 'Vicedom']
After: ['Vicedom', 'Guan', 'Sandhu', 'Cook', 'Ramsay', 'Lai', 'Berthelet', 'Gastin', 'Garcia', 'Yee', 'Spencer', 'Hildebrand']
```
*.sort()*- sorts a list, so its items are in alphabetical order
```python
teachers = ["Vicedom","Guan","Sandhu","Cook","Ramsay","Lai","Berthelet","Gastin","Garcia","Yee","Spencer","Hildebrand"] # teachers at Alexander Academy

print("Before:",teachers)

teachers.sort() # list is sorted from Berthelet to Yee

print("After:",teachers)
```
```
Before: ['Vicedom', 'Guan', 'Sandhu', 'Cook', 'Ramsay', 'Lai', 'Berthelet', 'Gastin', 'Garcia', 'Yee', 'Spencer', 'Hildebrand']
After: ['Berthelet', 'Cook', 'Garcia', 'Gastin', 'Guan', 'Hildebrand', 'Lai', 'Ramsay', 'Sandhu', 'Spencer', 'Vicedom', 'Yee']
```
*.remove()*- removes the first occurrence of an item from a list
```python
teachers = ["Berthelet","Cook","Garcia","Gastin","Guan","Hildebrand","Lai","Ramsay","Sandhu","Spencer","Vicedom","Yee"] # teachers at Alexander Academy

print("Before:",teachers)

teachers.remove("Gastin") # Ms. Gastin no longer teaches at this school, so...

print("After:",teachers)
```
```
Before: ['Berthelet', 'Cook', 'Garcia', 'Gastin', 'Guan', 'Hildebrand', 'Lai', 'Ramsay', 'Sandhu', 'Spencer', 'Vicedom', 'Yee']
After: ['Berthelet', 'Cook', 'Garcia', 'Guan', 'Hildebrand', 'Lai', 'Ramsay', 'Sandhu', 'Spencer', 'Vicedom', 'Yee']
```
**Non-Mutating Methods on Strings** [(9.9: Non-mutating Methods on Strings)](https://runestone.academy/runestone/books/published/fopp/TransformingSequences/NonmutatingMethodsonStrings.html)

The following methods *return*, not modify, strings, but they are useful for Python code.

*.upper()*- returns a string in all uppercase 
```python
school = "Alexander Academy is a great school!"
print("Before:",school)

school = school.upper() # all uppercase
print("After:",school)
```
```
Before: Alexander Academy is a great school!
After: ALEXANDER ACADEMY IS A GREAT SCHOOL!
```
*.lower()*- returns a string in all lowercase
```python
school = "Alexander Academy is a great school!"
print("Before:",school)

school = school.lower() # all lowercase
print("After:",school)
```
```
Before: Alexander Academy is a great school!
After: alexander academy is a great school!
```
*.strip()*- returns a string with preceding and succeeding whitespace removed
```python
school = "   Alexander Academy is a great school!   "
print("Before:",school)

school = school.strip() # removes whitespace
print("After:",school)
```
```
Before:    Alexander Academy is a great school!   
After: Alexander Academy is a great school!
```
*.replace()*- replaces an occurrence of a substring with another substring
```python
school = "Alexander Academy is a great school!"
print("Before:",school)

school = school.replace("a great","an awesome") # replaces 'great' with 'awesome'
print("After:",school)
```
```
Before: Alexander Academy is a great school!
After: Alexander Academy is an awesome school!
```
**Your Turn!** Try out these methods with lists and strings of your own, and combine them with what we've learned so far.

But, there's one more thing...

**String Formatting!**

An even cooler way to do this...
```python
name = input("What's your name? ")
print("Hello, " + name + "!")
```
...is to do this!
```python
name = input("What's your name? ")
print("Hello, {}!".format(name))
```
Think of the '{}' as a blank that you fill in with an expression, but don't forget the *format()* function too!

Here's an example that uses an integer instead of a string.
```python
x = 4
print("The number {} is even.".format(x))
```
You can also put what are called *format strings* inside the braces. For example, the format string ':.2f' formats a number to two decimal points. Learn more about format strings [here](https://docs.python.org/3.4/library/string.html#formatspec).
```python
# program to calculate the mean of two numbers (again)

first_num = float(input("First number: "))
second_num = float(input("Second number: "))

avg = (first_num + second_num) / 2 # two numbers are added, then divided by 2, to get the average

print(avg)

print("The mean of {:.2f} and {:.2f} is {:.2f}".format(first_num, second_num, avg))
```
```
First number: 4.25
Second number: 8.92
6.585
The mean of 4.25 and 8.92 is 6.58
```
I challenge you to incorporate *string formatting* in the above **Your Turn!** project, as well as any of the format strings.

## The Accumulator Patterns with Lists and Strings

**Accumulator Pattern with Lists** [(9.10: The Accumulator Pattern with Lists)](https://runestone.academy/runestone/books/published/fopp/TransformingSequences/TheAccumulatorPatternwithLists.html)

Instead of a single value like in the previous accumulator patterns we've covered, the **accumulator variable** is a list of values. Here's a simple example using a list of integers:
```python
nums = [8,21,13,14,17,2,20,10,3,11] 
nums_truncdiv = [] # accumulator list
for num in nums:
	num_truncdiv = num // 2 # rounded division by 2
	nums_truncdiv.append(num_truncdiv) # added to new list
print(nums_truncdiv)
```
```
[4, 10, 6, 7, 8, 1, 10, 5, 1, 5]
```
**Accumulator Pattern with Strings** [(9.11: The Accumulator Pattern with Strings)](https://runestone.academy/runestone/books/published/fopp/TransformingSequences/TheAccumulatorPatternwithStrings.html)

The accumulator variable can also be a string.
```python
message = "Hello world!"
message_extended = "" # accumulator variable
for m in message:
	message_extended += m.upper() * 5 # adds every character, times 5
	
message_extended = message_extended.replace("     "," ")# Let's remove that big space.
print(message_extended)
```
```
HHHHHEEEEELLLLLLLLLLOOOOO WWWWWOOOOORRRRRLLLLLDDDDD!!!!!
```
Well, wasn't that nice? We *started* with "Hello World" and *ended* with "Hello World!" That's all the Python you need for now, folks! Can't wait to try some fun projects with you guys in the coming weeks!

Recommended exercises:

[9.15](https://runestone.academy/runestone/books/published/fopp/TransformingSequences/Exercises.html):  all
