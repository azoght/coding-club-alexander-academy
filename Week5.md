# Week 5

Runestone: [8](https://runestone.academy/runestone/books/published/fopp/Conditionals/toctree.html)

## Boolean Expressions

As you might remember from [Week 1](Week1.md#values-and-data-types), a *boolean* can be represented as one of two values:  **True** or **False**.  [(8.2: Boolean Values and Boolean Expressions)](https://runestone.academy/runestone/books/published/fopp/Conditionals/BooleanValuesandBooleanExpressions.html)
```python
t = True
f = False
print("Is it " + str(t) + " or " + str(f) + "?")
print(type(t))
print(type(f))
```
```
Is it True or False?
<class 'bool'>
<class 'bool'>
```
Keep in mind that the values of booleans are always *capitalized*, so if you put them in all *lowercase*, you will get this.
```python
t = true
f = false
print("Is it " + str(t) + " or " + str(f) + "?")
print(type(t))
print(type(f))
```
```
NameError: name 'true' is not defined
```
Another runtime error.

The way we usually write booleans isn't as values, rather as *expressions* that return boolean values. For example...
```python
print(7 == 7) # Does 7 equal 7?
print(6 == 5) # Does 6 equal 5?
```
```
True
False
```
The first line checks if 7 equals 7. Since 7 does indeed equal 7, the value returned is **True**. The second line checks if 6 equals 5. Since 6 *doesn't* equals 5, the value returned is **False**.

The code above uses one of many *comparison* operators, the equals operator (==), which returns True if both operands are equal. **Please, don't confuse this operator for '='; that's the assignment operator for variables, and it's definitely not the same thing!**

Here are the other comparison operators you need to know: 

**doesn't equal (!=)-** returns True if the both operands are not equal
```python
print(3 != 2) # Does 3 not equal 2?
print(3 != 3)
```
```
True
False
```
**less than (<)-** returns True if the preceding operand is less than the succeeding operand
```python
print(1 < 3) # Is 1 less than 3?
print(4 < 3)
```
```
True
False
```
**greater than (>)-** returns True if the preceding operand is greater than the succeeding operand
```python
print(4 > 2) # Is 4 greater than 2?
print(3 > 4)
```
```
True
False
```
**less than or equal to (<=)-** returns True if the preceding operand is less than or equal to the succeeding operand
```python
print(2 <= 2) # Is 2 less than or equal to 2?
print(4 <= 2)
```
```
True
False
```
**greater than or equal to (>=)-** returns True if the preceding operand is greater than or equal to the succeeding operand
```python
print(3 >= 1) # Is 3 greater than or equal to 1?
print(2 >= 3)
```
```
True
False
```
## Logical Operators

Another kind of operator in Python is the *logical operator*, which, unlike [arithmetic operators](Week1.md#operators) and [conditional operators](Week5.md#boolean-expressions), uses boolean expressions as their operands.

Here are the three logical operators: [(8.3: Logical Operators)](https://runestone.academy/runestone/books/published/fopp/Conditionals/Logicaloperators.html)

**and-** returns True if *both* operands return True
```python
t1 = (2 == 2) # this will return True
f1 = (2 != 2) # this will return False
t2 = (2 < 3) # this will return True
f2 = (2 > 3) # this will return False

print(t1 and t2) # Are t1 and t2 True?
print(t1 and f1) 
print(f1 and f2)
```
```
True
False
False
```
**or-** returns True if *either* of the operands returns True
```python
t1 = (2 == 2) # this will return True
f1 = (2 != 2) # this will return False
t2 = (2 < 3) # this will return True
f2 = (2 > 3) # this will return False

print(t1 or t2) # Is t1 or t2 True?
print(t1 or f1) 
print(f1 or f2)
```
```
True
True
False
```
**not-** returns the *opposite* of what its operand returns
```python
t = (2 <= 3) # this will return True
f = (2 >= 3) # this will return False

print(not t) # What is the opposite of t?
print(not f)
```
```
False
True
```
If you're curious, here are the [*truth tables*](https://www.programiz.com/python-programming/keyword-list#and_or_not) for each of these logical operators.

Before we move on, here are two more operators that return boolean values: [(8.4: in and not in operators)](https://runestone.academy/runestone/books/published/fopp/Conditionals/Theinandnotinoperators.html)

**in-** returns True if a certain substring is found in a string
```python
fruit = "apple"
veggie = "lettuce"

print('a' in fruit) # Is the letter a in "apple"?
print('a' in veggie)
print('let' in fruit) # Is the substring 'let' in "apple"?
print('let' in veggie)
```
```
True
False
False
True
```
Weirdly enough, if you check to see if an *empty* string is in a string, you will always get True. That's because an empty string has a length of 0.
```python
language = "Python"
print('' in language)
print("" in "I'm empty.")
```
```
True
True
```
**not in-** returns True if a certain substring is *not* found in a string
```python
west_provinces = ["British Columbia","Alberta","Saskatchewan","Manitoba"]

print('fish' not in west_provinces[0]) # Is 'fish' not in "British Columbia"?
print('bert' not in west_provinces[1])
print('catch' not in west_provinces[2])
print('Mani' not in west_provinces[3])
```
```
True
False
True
False
```
Did I mention that these operators can be used on *lists* too?
```python
van_communities = ["Kittsilano","Coquitlam","Surrey","Burnaby"]
print('a' in van_communities) # Is the item 'a' in van_communities?
print('Surrey' in van_communities)
print('Langley' in van_communities)
```
```
False
True
False
```

## Conditionals

Now that you understand more about booleans, conditional operators, and logical operators, the next step is to combine them with something much more typical and useful. Enter *conditionals*. [(8.6: Binary Selection)](https://runestone.academy/runestone/books/published/fopp/Conditionals/ConditionalExecutionBinarySelection.html)

We execute code conditionally using if and else statements. If statements will run the code inside it if the condition attached to it is met. If not, the code inside the else statement will run instead.

Here's a simple example, which prints out if a string is empty.
```python
s = ""
if len(s) == 0: # if string is blank
    print("This string is empty")
else:
    print("This string isn't empty")
```
```
This string is empty
```
Actually, even better idea: let's combine a conditional statement with a for loop!
```python
nums = [14,3,7,11,5,8]
for num in nums:
    if num % 2 == 1: # remainder of division by 2 is 1
        print("Odd")
    else:
        print("Even")
```
```
Even
Odd
Odd
Odd
Odd
Even
```
What about code with *more than one* if statement? Sure, that's possible!
```python
# This program prints out a warning message based on the magnitude of an earthquake
richter_magnitude = 5.0

if richter_magnitude < 4 and richter_magnitude > 0: # if magnitude is less than 4...
    print("Just a mild shock, that's all.")
if richter_magnitude >= 4 and richter_magnitude < 7: # if magnitude between 4 and 7...
    print("Be extra cautious and hide.")
if richter_magnitude >= 7: # if magnitude greater than or equal to 7...
    print("Run for your life, it's a big one!")
else:
	print("Invalid magnitude")
```
```
Be extra cautious and hide.
```
**Unary Selection** [(8.7: Unary Selection)](https://runestone.academy/runestone/books/published/fopp/Conditionals/OmittingtheelseClauseUnarySelection.html)

We can also have a conditional statement that is just *if* with no *else*.
```python
x = 7
if not x >= 0: # Is it not greater than or equal to 0?
    print("I'm sorry, but",x,"is a negative number!")
print("Have a good day!")
```
```
Have a good day!
```
**Nested Conditionals** [(8.8: Nested Conditionals)](https://runestone.academy/runestone/books/published/fopp/Conditionals/Nestedconditionals.html)

Like for loops, we can put conditional statements *within* conditional statements.
```python
favourite_colour = "purple"
if len(favourite_colour) < 3: # I've never heard of a colour whose English name has less than 3 letters
    print("Looks like you don't have a favourite colour.")
else: # So if it's long enough to be a colour...
    if favourite_colour == "green":
        print("We have the same favourite colour: green!")
    else:
        print("Wow,",favourite_colour,"is a great colour!")
```
```
Wow, purple is a great colour!
```
**Chained Conditionals** [(8.9: Chained Conditionals)](https://runestone.academy/runestone/books/published/fopp/Conditionals/Chainedconditionals.html)

The elif (else if) statement is a nice, but optional alternative to using more than one if statement or nesting conditionals in else statements.
```python
weekday = "Thursday"

if weekday == "Monday":
    print("No need to feel down, it's Monday!")
elif weekday == "Tuesday" or weekday == "Thursday":
    print("Hang in there, it's",weekday+"!")
elif weekday == "Wednesday":
    print("Halfway through the week!")
elif weekday == "Friday":
    print("Hooray, it's Friday!")
elif weekday == "Saturday" or "Sunday":
    print("It's the weekend!")
```
```
Hang in there, it's Thursday!
```
**The Accumulator Pattern Using Conditionals** [(8.10: The Accumulator Pattern with Conditionals)](https://runestone.academy/runestone/books/published/fopp/Conditionals/TheAccumulatorPatternwithConditionals.html)

Perhaps we don't want to update our accumulator variable every time a loop runs. This is where conditionals come in handy.
```python
# program that counts punctuation marks in a string
s = "Oh my gosh, why are we doing this? Right (to learn code)."
puncts = [",",".","'","?","!","/","(",")",":",";","_","-","[","]"] # list of punctuation marks
p = 0 # accumulator variable
for char in s:
	if char in puncts: # checks if the character is in the list of punctuation marks
		p +=1
print(p)
```
```
5
```
There's also *max/min value accumulation*, in which the greatest or smallest value in a sequence is found using a conditional accumulator pattern.
```python
num_values = [3,11,5,4,9,17,23,21,2,13,15]
greatest_num = num_values[0] # accumulator variable

for num_value in num_values:
    if num_value > greatest_num: # checks if the current value is greater than the accumulator variable
        greatest_num = num_value
        
print(greatest_num)
```
```
23
```
**Your Turn!** Create a program that takes user input and produces an output after it runs through some conditional statements (Try to use as much material we covered so far as possible and be creative). Can't wait to see what you're coding next week!

Recommended Exercises:

[8.13](https://runestone.academy/runestone/books/published/fopp/Conditionals/Exercises.html):  1, 2, 3, 5, 6, 7, 8, 9, 10
