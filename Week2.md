
# Week 2
## Variables
Variables in Python are used to store values.

A variable consists of a *name* and a *value*, and is assigned using an equal sign (=).

Python, unlike other high-level languages uses **dynamic typing**, so the data type of the variable doesn't need to be stated in the assignment.

```python
greeting = "Hello"
print(greeting + " neighbour!")
```
```
Hello neighbour!
```

In the above example, the name of the variable is *greeting* and the value is *"Hello"*. Since Python uses dynamic typing, the compiler will automatically recognize this variable as a string.

You can give variables similar names, as long as they are not the **exact same** name.

```python
YVR = "Vancouver International Airport"
yvr = 604
print("Vancouver's airport is the " + YVR + " and their area code is " + str(yvr))
```
```
Vancouver's airport is the Vancouver International Airport and their area code is 604
```
**Ground Rules For Variable Names:**

 - should be easy for both the coder and reader to remember
 - must start with a letter
 - can only contain letters, numbers, and underscores

**Your Turn!** Think of some examples of variable names that are valid and variable names that are invalid.

## Statements and Expressions

A *statement* is an instruction which the Python compiler reads and executes (e.g. the variable declaration statement mentioned earlier).
```python
week = 2
```
An *expression* is any section of Python code that generates a value. Functions that return values are expressions, as well as the values of variables.
```python
str(week)
```
**The len() function**
Returns the length of a sequence, such as a list or a string.
```python
print(len("Code"))
```
```
4
```

## Updating Variables
Variables are generally updated the same way they are declared.

```python
favouriteNumber = 3
print("My favourite number was " + str(favouriteNumber))
favouriteNumber = 2
print("My favourite number is now " + str(favouriteNumber))
```
```
My favourite number is 3
My favourite number is now 2
```
Another way to update variables is through incrementing and decrementing.

**Increment-** adds a certain value to a variable (+=)
```python
age = 4
age += 2
print(age)
```
```
6
```
**Decrement-** subtracts a certain value from a variable (-=)
```python
balance = 180
balance -= 50
print(dollars)
```
```
130
```
## Interlude: Hard-Coding

Remember to not **hard-code**!

This means that even if you know the answer to an expression, use the full expression step-by-step instead of cheating and using just the expression.

This is hard-coding! (what you *shouldn't* be doing)
```python
x = 2
y = 6

product = 12
print(product)
```
```
12
```
This is **not** hard-coding! (what you *should* be doing)

```python
x = 2
y = 6

product = x * y
print(product)
```
```
12
```

## Input
Now *this* is where Python gets cool!

The **input()** function will ask the user to enter something. The argument for the input() function is known as the *prompt*, which the user will type their input next to when it shows up on the console. We'll also need to store the user's input as a variable for later use. Note that the function's value will *always* be a string even if the input is a number or decimal. You can fix this using the type conversion functions we covered last week. 

Let's say you wanted to create a simple program that asks for the user's name and prints out a greeting in return. Here's how that can be done.

```python
name = input("What's your name? ")
print("Hello,", name + "!")
```
```
What's your name? Angelina
Hello, Angelina!
```
**Note:** The message printed uses two forms of string concatenation. More on that in a future lesson.

Here's a more complicated example which takes a number in metres and converts it into its approximate feet and inches.
```python
metres = float(input("How many metres? "))
total_inches = metres * 39.37
feet = int(total_inches // 12)
inches = int(total_inches % 12)
print(str(feet) + "' " + str(inches) + "''")
```
```
1.6
5' 2''
```
**Let's break it down!**

*Line 1:* We are asking the user to input any number of metres, which is then converted to a float.

*Line 2:* We convert the user's input of metres to inches. Since 1 metre = 39.37 inches, this is the number we'll multiply the user's input by.

*Line 3:* We calculate how many feet can be made from these inches. Since 1 foot = 12 inches, then we divide the inches by that number, truncate it to a whole number, and cast it to an integer.

*Line 4:* We then calculate the remaining inches using the modulus operator. But since the final calculation will just be an approximation, we'll cast that number to an integer as well.

*Line 5:* We print the results from Lines 3 and 4 as a representation of feet and inches, using the single apostrophe (') for feet and the double apostrophe ('') for inches.

**Your Turn!** Try making a program that takes a user's input and outputs a result based on that input. Make sure to use what we learned so far, not just a print statement and variable declaration.

**But before you get started on that...**

## Comments!

Comments are basically little notes, usually to help yourself and others understand your code. These comments won't be read by the compiler, so they can say whatever you want (but keep them relevant please).

**Single-Line Comment:** the most common comment, marked by a hashtag (#), can be either be placed right next to a line of code or as its own line.
```python
# Program to Calculate Average of Two Numbers

# numbers to be averaged inputted by user
n1 = float(input("First number: "))
n2 = float(input("Second number: "))

avg = n1 + n2 # numbers added...
avg = avg / 2 # ...then divided by 2 to get average

print("Average of " + str(n1) + " and " + str(n2) + " = " + str(avg)) # Average printed out
```
**Multi-Line Comment-** marked by triple quotes ('''), used mostly to provide a description/context of the program
```python
'''
Hello, I'm Angelina, and this is a test program!

Does this work?
'''
print("This is a test.")
```
For this course, I highly encourage adding **single-line comments** to your code that explain what is going on. That way, not only will I be able understand your code, but the facilitators and students will too.

