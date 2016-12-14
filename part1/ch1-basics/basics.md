# Chap 1. The basics

## Python interpreter

Python has an interactive interpreter (REPL) that allows you to enter
python statements on a prompt, executes them immediately.

You can the **IDLE** graphical interpreter which is installed when you install Python
to write simple Python programs.

### Simple Arithmetic

You can enter arithmetic expressions in the enterpreter and it i'll evaluate them,
so you can use Python as your calculator.

```python
>>> 1 + 1
2
```
### Using the `print` function

We'll use the `print` function a lot to display things.

```python
>>> print("Hello, World!")
Hello World!
>>> print("I am", 23, "years old")
I am 23 years old
```

### Comments

Comments in Python start with the  **`#`** character (octothorpe) and go on
up to the end of the line.

```python
>>> #this is a comment
>>> 2**3 # this computes 2 raised to the power 3
```

## Basic data types

Data items in Python have a data type which constrain the types of value they
store and the operations that can be performed on them.

### Numbers

Numbers in python are either of type **`int`** (integers/whole numbers) 
and **`float`** (fractional numbers).

```python
>>> 1 + 5       # addition
6
>>> 90 - 15     # subtraction
75
>>> 5 * -2      # multiplication
-10
>>> 0.5 + 0.2   # working with float values
0.7
>>> 7 * 0.5
3.5
>>> 1.0 + 1
1.0             # the result is a float if at least one of the operands is a float
>>> 10 / 2      # division
5
>>> 5 / 2
2.5             # result when dividing 2 integers is converted to float if fractional
>>> 5 // 2      # integer division
2               # result is truncated
>>> 5 % 2       # modulus (remainder)
1
>>> 2 ** 5      # power
32

>>> 2 + 3 ** 2 - 6 * 5 / 2      # python follows standard operator precedence rules
-4.0
>>> (2 + 3) ** 2 - 6 * 5 / 2    # Use parantheses achieve the order you want
10.0
```

### Boolean

Boolean values are either **`True`** or **`False`**. Comparison operations
return a boolean result.

```python
>>> 2 > 1
True
>>> 45 <= 98.0
False
>>> 81 == 9 ** 2
True
```

### Strings

A string is a sequence of characters and is used to represent text data.

```python
# Strings can be delimited with double or single quotes
>>> "Hello, World"
>>> 'Hello, World'

# Special characters can be escaped with a backslash
>>> print('This is a a line\nThis is another line')
This is a line
This is another line

# Multiline strings delimited with 3 quotes
"""
This is a
multiline strings
"""
```

**String operations**:
```python
# Concatenation
>>> "Hello, " + "World"
'Hello, World'
# Repeating
>>> "Hello" * 3
'HelloHelloHello'
# Comparisons
>>> "altitiude" > "elevation"
True
>>> "name" == "Name"
False
# Length of a string using the len function
>>> len("This is a test")
14
# Getting elements of a string
>>> "Hello, World"[4]   # Index starts at 0
'o'
# Indexing from the end
>>> "Hello, World"[-1]
'd'
>>> "Hello, World"[-2]
'l' 
# Slicing strings
>>> "Hello, World"[2:]
'llo, World'
>>> "Hello, World"[2:4]
'll'
```

### None

**`None`** is a special value in Python that is used to indicate the absence of
a value.

### The `type` function

The function **`type`** can be used to find out the type of a variable or value.

```python
>>> type(1 + 2)
<class 'int'>       # integer
>>> type(10.0)
<class 'float'>     # float
>>> type("Hello")
<class 'str'>       # string
>>> type("1")
<class 'str'>
>>> type(2 == 1)
<class 'bool'>      # boolean
>>> type(None)
<class 'NoneType'>  # None is of a type called NoneType
```

### Type conversion

Sometimes in order to perform some operation you may need to converted
a value of one type to a value of a different type.

```python

>>> 1 + "1"
# This will throw an error, you cannot add an int and a string

>>> 1 + int("1") # the string "1" is converted to the int 1 and addition is performed
2
>>> str(1) + "1" # the int 1 is converted to the string "1" and concatenation is performed
'11'

# More conversions
>>> bool(0)
False
>>> float(True)
1.0
>>> str(None)
'None'
>>> bool('')       # Converting an empty string to boolean returns False
False
>>> bool('False')  # Converting any non-empty string to boolean return True
True
```

## Variables and assignment

A variable is a name that refers to some value (technically it's a named location in
memory). A variable can be used in place of a literal value.
You assign a value to a variable using the assignment operator **`=`**.

Valid variable names contain letters, numbers and the underscore. They cannot begin
with a number. The cannot be reserved Python keywords. Check [here](http://greenteapress.com/thinkpython2/html/thinkpython2003.html)
for more details on variable naming.

```python
>>> x = 10
>>> print(x)
10

# A variable can be re-assigned, replacing it's original value
>>> name = "Lulu"
>>> name = "Naomi"
>>> print(name)
Naomi

# In Python the same variable can be assigned values of any type
>>> my_var = 20
>>> type(my_var)
<class 'int'>
>>> my_var = "Python"
>>> type(my_var)
<class 'str'>
```

## Reading user input

The **`input`** function is used to prompt the user enter some input and read it
into our program.

```python
>>> name = input('Enter your name: ')
# the program prints the prompt and waits for the user to enter a value and
# hit the return key
>>> print('Hello', name)
Hello, Jack

# the input function returns a string, we have to convert it if we need to work 
# with a different type

>>> num = input('Enter number: ')
# num contains a string
>>> num = int(num) # convert num to an int
>>> result = num ** 2
>>> print(num, 'square is', result)
```

## If-statement

An if statement executes a block of statements only if a specified condition is met.

In Python you start a block with `:` and then indent subsequent lines that are part
of the block.

**Note**: In Python, indentation is part of the syntax. Improper and inconsistent
indentation leads to syntax errors.

```python

# if-else
if age > 21:
    print("Welcome")
else:
    print("You're too young")


# Multiple branches
if language == 'French':
    print('Bonjour')
elif language == 'Spanish':
    print('Buenos dias')
elif language == 'German':
    print('Guten Tag')
else
    print("I don't speak your language.")

# Conditional operators

# and operator
if language == "French" and gender == "male":
    print("Bonjour Monsieur")

# or operators
if age > 18 or is_with_adult:
    print("You can go in")

# negation
if not salary >= 100000:
    print("I can't work here")

# is operator
if country is "KE":
    currency_code = "KES"

```

The condition expression does not necessarily have to evaluate to a boolean, it
can also work with other data types. The if block is executed if the expression
is truthy (values when converted to boolean return True, such as 
non-zero numbers, non-empty strings, True, etc.) and not when the expression is
falsy (expressions when converted to boolean return False, such as 0, the empty
string, None, etc.)

```python
if 1:
    print("This expression is truthy")

if '':
    print("This won't run")

if not None:
    print("This will also run")

```

## While-loop

The while loop repeats execution of a block of statements as long as the specified
condition is met.

```python

# count down from 10 to 1
n = 10
while n > 0:
    print(n)
print("Blastoff!")

# an infinite loop
while True:
    print("This will go on forever");

```

## The `break` statement

The **`break`** statement is used inside a loop's block to terminate the loop
immediately.

```python

while True:
    command = input("Enter command")
    if command is 'exit':
        break   # terminate loop
    else
        # do something
```

## For-loop

A for loop is used to execute a block a given number of times.

```python

# prints squares of numbers from 0 to 9 inclusive
for i in range(10): # i will go from 0 to 9
    print(i ** 2)   # prints 1 to 81

# you can specify a starting point for your range
for i in range(10, 15):
    print(i)

# you can specify an interval
for i in range(1, 16, 2): # prints all the odd numbers from 1 to 15
    print(i)

# print all the characters in a sentence
sentence = "I like Python!"
for i in range(len(sentence)):
    print(sentence[i])

```

## Exercises

1. Write a program that counts and displays the number of spaces
in a sentence of your choice.

2. Transform the program in 1. so that it prompts the user to
enter the sentence

3. Write a program that computes and displays the factorial
of the number 200.

4. Transform the program in 3 so that it prompts the user
for the input number.

5. Write a program that prompts the user for 2 numbers then
displays all the odd numbers between them. The user should be
free to enter the 2 numbers in any order.

6. What is the result of the expression ```"Hello, World"[::2]```?
Do some digging and find out more about the slicing feature in Python.

7. What is multiple assignment in Python and how does it work?

8. Write a program that allows the user to enter items of
a shopping cart and their prices. At each Iteration
the program prompts the user to enter the name of the item 
then the price of the item. The program then displays the
name of the entered item and the current total price of the
shopping cart. If instead of an item name the user enters *end*,
the program should display the final total and end.


## Resources and further reading

- [Python Docs Unofficial Introduction to Python](https://docs.python.org/3/tutorial/introduction.html)
- [Think Python 2e - Chapter 1: The way of the program](http://greenteapress.com/thinkpython2/html/thinkpython2002.html)
- [Think Python 2e - Chapter 2: Variables, expressions and statements](http://greenteapress.com/thinkpython2/html/thinkpython2003.html)
- [Think Python 2e - Chapter 7: Iteration](http://greenteapress.com/thinkpython2/html/thinkpython2008.html)
- [Think Python 2e - Chapter 8: Strings](http://greenteapress.com/thinkpython2/html/thinkpython2009.html)
