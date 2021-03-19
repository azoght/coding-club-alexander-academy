# Week 1

## Your First Program: Hello World
All it takes is one line of code

```python
print("Hello World!")
```
Or if you want to get all fancy...

```python
def  printHelloWorld():  
	print("Hello World!")  

printHelloWorld()
```
As you can see in the code above, to generate Hello World! as our output, we use a function called print(), which displays the value inside when ran.

Feel free to use whatever message you like in place of Hello World!

## Values and Data Types

Here are some basic data types that you’ll see in pretty much all Python programs.

**Integer-** a non-decimal number (ex. -3, 100, 2456708)

**Float-** a number expressed as a decimal (ex. 5.0, -18.7, 3.14159)

**String-** a sequence of characters wrapped in quotes (ex. “A”, “Ready 2 code?”)

**Boolean-** a conditional data type, which can either be expressed as True or False

## Operators

Operators are symbols used to alter multiple values (or operands) into a single value.

Here are the basic operators used in Python.

**Addition-** used to add or combine two values (+)
```python
print(11 + 98)
Output: 109

print("Welcome to " + "Coding Club!")
Output: Welcome to Coding Club
```
**Subtraction-** used to subtract two values (-)
```python
print(89 - 45)
Output: 44
```
**Multiplication-** used to multiply two values (*)
```python
print(5 * 3)
Output: 15

print(Happy * 7)
Output: HappyHappyHappyHappyHappyHappyHappy
```
**Division-** used to divide two values (\)
```python
print(30 / 6)
Output: 5

print(8 / 6)
Output: 1.33333333333333333333333
```
**Truncated Division-** rounds the quotient of two values (\\)
```python
print(11 // 5)
Output: 2
```
**Modulus-** remainder of division between two values (%)
```python
print(60 % 3)
Output: 0

print(19 % 7)
Output: 5
```
**Exponent-** raises the preceding operand to the power of the succeeding operand
```python
print(2 ** 3)
Output: 8
```
**Note**: When dealing with operators, Python uses the Order of Operations or BEDMAS (Brackets, Exponents, Division & Multiplication, Addition & Subtraction)

So...
```python
print(10 - 8 // 2)
Output: 6
```
is not the same as...
```python
print((10 - 8) // 2)
Output: 1
```

## Functions
Functions are expressions, which take input (arguments) and generate output (return value).

**Example**: calculate area of rectangle, given length and width
```python
def areaofRectangle(length, width):
	return length * width

print(areaofRectangle(4,6)
Output: 24
```
In the above function, the arguments are length and width, while the return value is equal to the length multiplied by the width, since the area of a rectangle is equal to its length times its width.

**Your Turn!** Think of a formula you learned about in school and create your own function in Python based on this formula. (Bonus if you can figure out how to code the quadratic formula given a, b, and c)

However, a function can also have *no input* whatsoever, as is the case for the printHelloWorld() function.

Regardless, a function *should* have output.

## The Type() Function
The function type() gives us the data type of the argument
```python
print(type("Welcome to Coding Club!"))
Output: <class 'str'>

print(type(16))
Output: <class 'int'>
```
It should be used if you are unsure what data type a value is.

## Type Conversion Functions
There are other built-in functions that can be used to convert a value from one type to another.

**Int()-** used to convert a value to an integer
```python
print(int("8732"))
Output: 8732

print(type(int("8732"))
Output: <class 'float'>

print(int(764.12))
Output: 764
```
If the argument of this function contains non-number characters (ex. int(“1, 2, tie my shoe”)), a ValueError will be returned.

**Float()-** used to convert a value to a float
```python
print(float("54.321"))
Output: 54.321

print(type(float("54.321")))
Output: <class ‘float’>  
  
print(float(83))
Output: 83.0
```
**Str()-** used to convert a value to a string
```python
print(str(64))
Output: 64  
  
print(type(str(64)))
Output: <class ‘str’>

print(str(7.53))
Output: 7.53
```
These type conversion functions can be used for concatenation, for example…
```python
print("The product of 6 and 3 is " + str(6 * 3))
Output: The product of 6 and 3 is 18
```
**Your turn!** Think of a way you can use type conversion functions when you code.
