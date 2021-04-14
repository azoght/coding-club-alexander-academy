# Week 1
 
Runestone: [1](https://runestone.academy/runestone/books/published/fopp/GeneralIntro/toctree.html), [2.1-2.6](https://runestone.academy/runestone/books/published/fopp/SimplePythonData/toctree.html)

## Your First Program: Hello World
All it takes is one line of code [(1.7: A Typical First Program)](https://runestone.academy/runestone/books/published/fopp/GeneralIntro/ATypicalFirstProgram.html)

```python
print("Hello World!")

As you can see in the code above, to generate Hello World! as our output, we use a function called print(), which displays the value inside when ran.

Feel free to use whatever message you like in place of Hello World!

## Values and Data Types

Here are some basic data types that you’ll see in pretty much all Python programs. [(2.2: Values and Data Types)](https://runestone.academy/runestone/books/published/fopp/SimplePythonData/Values.html)

**Integer-** a non-decimal number (ex. -3, 100, 2456708)

**Float-** a number expressed as a decimal (ex. 5.0, -18.7, 3.14159)

**String-** a sequence of characters wrapped in quotes (ex. “A”, “Ready 2 code?”)

**Boolean-** a conditional data type, which can either be expressed as True or False

## Operators

Operators are symbols used to alter multiple values (or operands) into a single value. [(2.3: Operators and Operands)](https://runestone.academy/runestone/books/published/fopp/SimplePythonData/Operators.html)

Here are the basic operators used in Python.

**Addition-** used to add or combine two values (+)
```python
print(11 + 98)
```
```
109
```
```python
print("Welcome to " + "Coding Club!")
```
```
Welcome to Coding Club
```
**Subtraction-** used to subtract two values (-)
```python
print(89 - 45)
```
```
44
```
**Multiplication-** used to multiply two values (*)
```python
print(5 * 3)
```
```
15
```
```python
print(Happy * 7)
```
```
HappyHappyHappyHappyHappyHappyHappy
```
**Division-** used to divide two values (\)
```python
print(30 / 6)
```
```
5
```
```python
print(8 / 6)
```
```
1.33333333333333333333333
```
**Truncated Division-** rounds the quotient of two values (\\)
```python
print(11 // 5)
2
```
**Modulus-** remainder of division between two values (%)
```python
print(60 % 3)
```
```
0
```
```python
print(19 % 7)
```
```
5
```
**Exponent-** raises the preceding operand to the power of the succeeding operand
```python
print(2 ** 3)
```
```
8
```
**Note**: When dealing with operators, Python uses the Order of Operations or BEDMAS (Brackets, Exponents, Division & Multiplication, Addition & Subtraction)

So...
```python
print(10 - 8 // 2)
```
```
6
```
is not the same as...
```python
print((10 - 8) // 2)
```
```
1
```

## Functions
Functions are expressions, which take input (arguments) and generate output (return value). [(2.4: Function Calls)](https://runestone.academy/runestone/books/published/fopp/SimplePythonData/FunctionCalls.html)

**Example**: calculate area of rectangle, given length and width
```python
def areaofRectangle(length, width):
	return length * width

print(areaofRectangle(4,6))
```
```
24
```
In the above function, the arguments are length and width, while the return value is equal to the length multiplied by the width, since the area of a rectangle is equal to its length times its width.

**Your Turn!** Think of a formula you learned about in school and create your own function in Python based on this formula. (Bonus if you can figure out how to code the quadratic formula given a, b, and c)

However, a function can also have *no input* whatsoever.

Regardless, a function *should* have output.

## The Type() Function
The function type() gives us the data type of the argument [(2.5: Data Types)](https://runestone.academy/runestone/books/published/fopp/SimplePythonData/DataTypes.html)
```python
print(type("Welcome to Coding Club!"))
```
```
<class 'str'>
```
```python
print(type(16))
```
```
<class 'int'>
```
It should be used if you are unsure what data type a value is.

## Type Conversion Functions
There are other built-in functions that can be used to convert a value from one type to another. [(2.6: Type conversion functions)](https://runestone.academy/runestone/books/published/fopp/SimplePythonData/ConvertTypeFunctions.html)

**Int()-** used to convert a value to an integer
```python
print(int("8732"))
```
```
8732
```
```python
print(type(int("8732")))
```
```
<class 'float'>
```
```python
print(int(764.12))
```
```
764
```
If the argument of this function contains non-number characters (ex. int(“1, 2, tie my shoe”)), a ValueError will be returned.

**Float()-** used to convert a value to a float
```python
print(float("54.321"))
```
```
54.321
```
```python
print(type(float("54.321")))
```
```
<class ‘float’>  
```
```python
print(float(83))
```
```
83.0
```
**Str()-** used to convert a value to a string
```python
print(str(64))
```
```
64
```
```python
print(type(str(64)))
```
```
<class ‘str’>
```
```python
print(str(7.53))
```
```
7.53
```
These type conversion functions can be used for concatenation, for example…
```python
print("The product of 6 and 3 is " + str(6 * 3))
```
```
The product of 6 and 3 is 18
```
**Your turn!** Think of a way you can use type conversion functions when you code.

Recommended Exercises:

[2.17](https://runestone.academy/runestone/books/published/fopp/SimplePythonData/Exercises.html): 1, 2
