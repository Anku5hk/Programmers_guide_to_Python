# Programmer's guide to Python
#### Note: This book is not finalized yet and is currently under works.

Hello Learner, welcome to this Programmer's guide to Python handbook, this book was originally designed as notes when I was learning Python, but then I thought okay why not make it public for other learners, so I added some missing components and completed it as a book. I hope this helps you in learning Python programming. Happy Learning!!

**What's not this:** Not a traditional programming course/book, this is by no means a complete Python walkthrough and might be structured somewhat differently. I have tried to cover & mostly emphasis on important features and tricks inside Python. This book is not recommended for 'programming freshers', you should try more beginner friendly books like [Byte of Python](https://python.swaroopch.com/)/[Think Python](https://greenteapress.com/wp/think-python-2e/) and comeback to this one to further fine tune your learning.</br>  

**What is this:** This book is meant for a programmer who's already familiar with other languages such as C/C++/Java and wants to learn Python but fast. The one who needs a Python refresher can also benefit by this book. The goal is to take you through enough Python (and much more), while saving you tons of time. I have tried to keep the explanations concise most of the times, so things can be gone through fast. To grow as a programmer its always better to practice. I would suggest copying & running your own programs and creating your own notes.

## Index
1. [Basics](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#1-basics)
2. [Data Types](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#2-data-types)
3. [Data structures](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#3-data-structures)
4. [Flow Control](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#4-flow-control)
5. [Exception Handling](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#5-exception-handling)
6. [Functions](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#6-functions)
7. [Classes and Objects](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#7-classes-and-objects)
8. [Modules and Packages](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#8-modules-and-packages)
9. [Files and I/O](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#9-files-and-io)
10. [OOP Concepts](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#10-oop-concepts)

## <strong>1. Basics</strong>
### <strong>1.1 Introduction</strong>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; According to Wikipedia "Python is an interpreted high-level general-purpose programming language." It was created by Guido van Rossum and released in 1991. It supports multiple programming paradigms like object-oriented, procedural and functional. Python is also dynamically-typed and garbage-collected. Python's best implementation is in C language called [Cython](https://github.com/python/cpython), it is the default/standard but there are other implementations in Java, .Net, etc. Its philosophy revolves around code readability and code simplicity, you can also check [zen of python](https://www.python.org/dev/peps/pep-0020/) for more on that. Python is widely used in Web-Development([flask](https://flask.palletsprojects.com/en/2.0.x/), [django](https://www.djangoproject.com/), [fastapi](https://fastapi.tiangolo.com/)), Android/Windows/IOS/OSX application development([kivy](https://kivy.org/#home)), Big-Data Processing/Databases([Pyspark](https://spark.apache.org/docs/latest/api/python/), [Pandas](https://pandas.pydata.org/)), Machine learning([pytorch](pytorch.org/), [tensorflow](tensorflow.org/), [sklearn](scikit-learn.org/stable/)), Mathematical/Scientific libraries([numpy](numpy.org/), [scipy](scipy.org/)), DevOps, Security, etc. The current/latest version is Python3 which was released in 2008 and is still relevant (as of 2021), as Python2 was discontinued on 1 Jan 2020, Python3 is the way to go.
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; There is a fair amount of debate around "Python is a slow language", this [article](https://hackernoon.com/why-is-python-so-slow-e5074b6fe55b) has some answers, but for most part that does not affect its usability/credibility, it is the most preferred programming language and is still growing popular (as of 2021). There are other languages which are good enough to be Python's successor such as Rust, GO and Julia. These languages do have potential to eventually replace Python, at least in some domains in the coming time, but it is yet to be seen.
### <strong>1.2 Literal constant</strong>
* Are raw data, literals are constant fixed values. A raw value by itself is a literal constant.
```Python
# some literals
4, 6, 2.5, 7.4, 'string', 'something'
# here 4 has no other value replacement, so its a integer literal
# similarly 'something' is also a string literal
```
### <strong>1.3 Keywords</strong>
* Are reserved words which are defined by Python, so they can't be used as operands.
```Python
# some keywords
if, else, for, while, is, as, or, not, and, None, def, class, return, yield, pass, raise
```
### <strong>1.4 Operands</strong>
* Are also called variables. They have a user-defined name, which should not begin with a number and names are case sensitive just like in other programming languages.
* Unlike C/C++/Java, Python is Dynamically-Typed. It is when the type checking happens at run-time (and not at compile-time). Type checking is to ensure type-safe, say an *int* doesn't get assigned to a *str*.
* In Python there is no "variable declaration", you do not need to declare a variable, they come to existence when they are assigned something. Also there is no need for "type declaration", variables are just name pointers.
* Whenever an object is created in Python, the object/value along with its type is assigned some memory in a storage. When that object is assigned a variable, that variable is just a name/reference to this memory. The value on the left is the name assigned to this object and on the right is the representation of this object. As variables are just names they do not have types, they can be assigned to any type of object.
```python
## some common used variable names style
# camel casing names
myVar, myString42, rawData
# capital camel casing names
MyVar, MyString30, FileData
# snake casing names
my_var, my_string12, some_data3

## Dynamically type feature
# the type is checked only at run-time
if False:
  30 + "some string"
# Above statement should return a TypeError but it will not,
# because that condition is never executed, if it did it will raise the exception, try with "if True"

## Dynamically typed: Assigning a name (variable) to the object
my_var = 34
my_var = "I am string"
my_var = [1,2,3,4]
my_var = 4.0
# Assigning name 'my_var' to 34, then changing it to point to a string, then a list.
# All of them are valid, as variables don't have types
# Note: Python is garbage collected (auto memory management), 
# so any object that doesn't have a reference is removed automatically from the memory. 
# For example, 34 is collected as after 'my_var' is assigned to "I am string"

## Variables are just reference
a = 34
b = a
a = 20
print(a, b) # 20, 34
# Here, 'a' was pointing to 34, we assigned 'a' to 'b', which means now 'b' also refers to 34 (and not 'a')
# so changing 'a' to 20 doesn't affect the 'b', it still points to 34
```
### <strong>1.5 Operators</strong>
* Are used to perform operations on operands. The Arithmetic, Assignment, Comparison, Bitwise operators work the same as in C/C++/Java/Javascript, so I will not explain them here. The Logical, Identity, Membership operators are Python specific, we'll take a look at them.
* Seven Types of Operators (comma separated) in Python.
```Python
"""
## Arithmetic operators (follows PEMDAS rule)
+,-,\*,/,%,\*\*,//
## Assignment operators
=,+=,-=,/*=,/=,%=,//=,\*\*=,&=,|=,^=,>>=,<<=
## Comparison operators
==,!=,>,<,>=,<=
## Bitwise Operators
&,|,^,~,<<,>>
## Logical Operators
not,and,or
## Identity Operators
is,is not
## Membership Operators
in,not in
"""
```
* <b>Logical operators</b>: not,and,or.
```Python
## not: to negate the underlying condition (it reverses the condition)
a = 30
# here the underlying condition is the isinstance() function, which return True/False
# normally 'if' executes when a underlying condition is 'True' right?, by applying 'not' to it
# the 'if' condition is satisfied only when the output is 'False'
if not isinstance(a, int):
  print('not printed')
if not isinstance(a, str):
  print('printed')

## 'and' is similar to '&&' in C/C++/Java: both conditions should be satisfied
a=20
b=30
if a > 10 and b < 50:
  print('printed')
if a > 42 and b < 50:
  print('not printed')

## 'or' is similar to '||' in C/C++/Java: either of conditions should be satisfied
if a > 10 or b < 10:
  print('printed')
if a > 20 or b < 30:
  print('not printed')
```
* <b>Identity operator</b>: is,is not.
```Python
## is: checks if 2 objects have same identity
my_var1 = 42
my_var2 = 42
# checking values with '=='
if my_var1 == my_var2:
  print('printed')
# now checking if they are referring to same object
if my_var1 is my_var2:
  print('printed')

# another example
x = 500
y = 500
# let's check with 'is' operator
if x is y:
  print('not printed')
# oops?
# Every object in Python when it is created is assigned a unique number, known as its identity
# which is what the 'is' operator checks, we can print id using the 'id()' function   
print(id(x)) # 140544545318224 
print(id(y)) # 140544545318416
# This is because Python interpreter creates values is range [-5, 256] at the beginning of the program 
# to gain some performance boost. Because values in this range are very frequently used as per Python.

## is not: negate the 'is' condition, working is similar as we saw above
# Notice: 'not' should be applied after 'if' and not after 'is'
if not a is b:
  print("printed")
```
* <b>Membership operators</b>: in,not in.
```Python
## in: used to check if a value is inside a sequence or not, returns a boolean value
# consider a list containing some values, we'll learn about lists in details later, for now think of it as an array
my_list = [23,5,32,65,20]
# check with 'in' operator if 'my_list' contains the value 20, yes so True
print(20 in my_list) # True
# similarly check if it contains 30, nope so False
print(30 in my_list) # False

## not in: negate the 'in' condition, same as above but returns opposite values
# consider the same list, we'll check values again
# checking if 10 'not in' 'my_list' 
print(10 not in my_list) # True
# this spells as 10 is not in my_list, which is True
# checking if 24 'not in' 'my_list', which is, so False
print(32 not in my_list) # False
```
### <strong>1.6 Expressions</strong>
* An expression is something that is evaluated by the interpreter, say on a value/sequence by doing some operation (arithmetic/conditional/lambda function). They are a part of statements (as in expression statements).
```Python
# Some examples
"Yes"+"this"
x+6
if a==3 else 2
a or b
2 and 3
lambda x:x**2
```
### <strong>1.7 Python Syntactic Sugar</strong>
* Are optionally available to write some expressions/statements in a short way.
```Python
## Some examples
## Multiple Target assignment
a = b = c = 10
# let's check the outputs
print(a,b,c) # 10,10,10
a = 20
b = 30
# let's check again
print(a,b,c) # 20,30,10
# This "a = b = c = 10" is similar to
some_var = 10
a = some_var
b = some_var
c = some_var
# as we saw earlier variables are just names, when we change a/b/c
# we are only changing their reference, others are not affected
# but there is some catch and we'll catch it later

## Chaining operators
# is similar to "if x<=y and y<z:"
if 10 <= 20 < 30:
  print("okay got it")

## continuations
# Example 1: Using backslash
# use '\' at the end of the line to continue on another line
text = "This is text 1." \
"This is text 2" \
"And I can also continue here in the next line."
# Example 2: Using parens (...)
output = something
         .some_fun()
         .calling_other_fun()
         
# Apart from these there are more syntactic sugars in Python such as ternary operator, comprehensions, incrementing & derementing etc
```
### <strong>1.8 Statements</strong>
* Are basically every line/block of code that Python interpreter executes. There are two types, simple and compound statements.
```Python
## simple statements
# expressions we saw earlier
# assignments like
a = 40
t = "Time"
# and also keywords like
yield, del, return, pass, raise, break, continue

## compound statements
# like function and class definitions which we will covered later on
# and also keywords like
if, else, elif, while, for, try, with
```
### <strong>1.9 Comments</strong>
* Hiding information/description from the interpreter to exclude.
```Python
# this is a single line comment
# TODO: this is a todo comment, useful in IDEs like Visual Studio Code/Pycharm

"""this is a
multiline comment
"""
```
### <strong>1.10 Indentations</strong>
* Unlike using brackets in C/C++/Java, indentations are used for a code block in Python. Indentations can be of any range, usually four indentations are preferred, only constraint is that they should be consistent throughout that block of code. Any next un-indented line is used to show the end of that block of code.
* They are used in Flow Control, Exception Handling, Functions/Classes definitions in Python, else *IndentationError* is raised. Every statement should follow the indentation rule.
```Python
## Example 1
# Notice: the colon at the end of 'if' condition
if 10 > 5:
print('printed') # IndentationError

## Example 2
if 10 > 5:
    # preferred indentation
    print('printed')
print('block code ends')
# also valid indentation
if 10 > 5:
  print('printed')
  print('also printed')
# continue other code

## Example 3
class MyClass:
some_var = 10 # IndentationError
  def my_function():
  some_var1 = 20 # IndentationError
```
### <strong>1.11 Namespaces</strong>
* As seen in C++ namespaces are a collection of names of variables/functions, but unlike C++, Python does not have the *namespace* keyword and so no user defined namespaces. Python maintains all of the namespaces in a dictionary automatically. They are maintained/recorded according to the scope of a variable/function, just as in any programming language. 
  
  **Three types of namespaces.**
  1. **built-in**: Are readily available functions without any import.
  2. **global**: Are which user defines outside of any function/class.
  3. **local**: Are which user defines inside a function/class.
```Python
## built-in namespace
"""
# For example some functions which do not require any import
print(), len(), map(), range(), list(), set(), str(), etc. 
"""

## global namespace
# importing any modules adds them global namespace
import time
# variables and functions
my_var = 10
def my_fun():
    pass

## local namespace
def some_fun():
    # variables and functions defined here
    my_var = 10
    def my_fun():
        pass
```
### <strong>1.12 Time Complexity</strong>
* It is used to measure how the runtime of a function increases with the size of input. Note that time complexity is not equal to execution time. It is used to calculate how a function will scale, given the number of inputs. Time Complexity for a smaller data/problem can be negligible or not necessary to be optimized, usually one should invest time in tuning time complexity for larger, time intensive problems or problems that require faster response time. A good time complexity [chart](https://www.bigocheatsheet.com/). 
  
  **Common Time Complexities in ascending order of their growing time.**
  1. **O(1)**: Constant time. Time does not increase at all.
  2. **O(logN)**: Logarithmic time. When time is increasing logarithmically (grows at inversely proportional rate of N).
  3. **O(N)**: Linear time. Time increases linearly with the input size.
  4. **O(NLogN)**: Linearithmic time. Logarithmic and Linear time together.
  5. **O(N\*\*K)**: Polynomial time. When time increases at N (input) to the power K (constant) times.
  6. **O(K\*\*N)**: Exponential time. When time increases at K (constant) to the power N (input) times.
  **Note**: Explaining all time complexities would consume lots of space for this book, you can get more information about it [here](https://www.hackerearth.com/practice/basic-programming/complexity-analysis/time-and-space-complexity/tutorial/).
* Similar to time complexity there is also space complexity, it is used to measure how the memory of a function increases with the size of input.

## <strong>2. Data Types </strong>
Defines a particular kind/domain of data item, they define the type of data a variable holds. They also define the operations allowed on that data type. Python doesn't require declaration of data types like in C/C++/Java (as we saw before variables are just pointers). Any variable can be assigned any data type/object, a string variable can be assigned *int* or *float* or any other object it doesn't matter. There is no *final* (used for declaring a constant variable) keyword for variables in Python like in Java. The constant variables in Python are defined inside another *.py* file in capital letters and then they are imported inside the current module to be used.
#### Three types of Data Types in programming.
  1. **Primitive**: Are built-in or predefined data types in a programming language, Eg. *int*, *float*, double (n/a in Python), char (n/a in Python), bool etc.
  2. **Composite/Derived**: Are data types which are constructed using two/more data types, Eg. Array (*list* in Python), Record (*tuple* in Python), Union (*dict* in Python), Strings (*str* in Python), Functions, Pointers (n/a in Python), Structures (n/a in Python) etc.
  3. **Abstract**: They define operations on objects using functions but without specifying the exact implementations of those functions (the underlying implementation can differ from languages but the working has to stay the same), Eg. Stack, Queue, Map, Tree, Graphs etc.
#### Mutable and Immutable types in Python.
  1. **Immutable**: Values cannot be altered/added/removed once created or are read-only types once created, Eg. *int*, *float*, *complex*, *bool*, *None*, *str*, *tuple*, *frozenset*.
  2. **Mutable**: Values can be altered/added/removed after creation, Eg. *list*, *dict*, *set*.

Data types explained below are [int](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#21-three-numeric-types), [float](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#21-three-numeric-types), [complex](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#21-three-numeric-types), [str](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#22-text-type-str), [bool](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#23-boolean-type-bool), [byte](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#24-binary-types-byte) and [User-defined Data Type](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#25-user-defined-data-type). Later we'll take a look at the [None](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#26-none-object) object and some built-in functions. For simplicity I've arranged the rest of them in the [Data Structure](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#3-data-structures) section. Alright, let's begin.
### <strong>2.1 Three Numeric Types</strong>
1. **Integer** (int): Numbers that do not have decimal values. In Python, *int* is also a *long* type and it can be of any size. 
2. **Float** (float): Numbers that do have decimal values. In Python, *float* is also a *double* type as it is a double precision floating point number. 
3. **Complex** (complex): Numbers that have two parts, real and imaginary. First part is a normal number, the second part is an imaginary number which should be followed by j.
* Creating numeric types. 
```Python
# here my_int is an operand, 42 is a literal and its data type is int
my_int = 42 # int
print(type(my_int)) # <class 'int'>

my_float = 3.0 # float
print(type(my_float)) # <class 'float'>
my_complex = 4.22 + 20j # complex
my_complex = complex(4.22, 20) # alternative way
print(my_complex) # (4.22+20j)
```
* Some functions on numeric types.
```Python
# returns maximum from n numbers(n > 2)
print(max(30, 20)) # 30
# returns minimum from n numbers(n > 2)
print(min(30, 20)) # 20
# returns absolute value of a number
print(abs(-50)) # 50
# returns a rounded to decimal value of a number
print(round(my_float)) # 3
# returns the power of a number, similar to using '**' operator, eg "10**2" 
print(pow(10, 2)) # 100
# returns quotient and remainder of integer division
print(divmod(6, 4)) # (1, 2)
# convert a number to a hexadecimal number
print(hex(42)) # 0x2a
```
* Type conversion examples.
```Python
my_int = 42
my_float = 3.0
# int to str
print(str(my_int)) # 42
# int to float
print(float(my_int)) # 42.0
# float to int
print(int(my_float)) # 3
# float to str
print(str(my_float)) # 3.0
```
### <strong>2.2 Text Type (str)</strong>
* Unlike Java, Python does not have *char* type for storing character/character array, it has *str* object (similar to *string* in C++) which is a collection of character data. *str* (String types) hold sequences of characters and are also called string literals. 
* They are immutable i.e items/values (here characters) cannot be altered/deleted once created. But you can use *replace()* method of string to alter and *strip()* to remove specific substring. 
* Creating text types.
```Python
# Single Quote: insert string value inside single inverted commas  
text = 'strings can be single quoted'
# Double Quote: can be useful for escaping single inverted comma(') rest there is no difference
text = "strings can be double quoted" 
# Triple Quote: used for multi-line text, can be used with single/double inverted commas
text = """This is a long text.
        And want to use multiple lines."""
```
* Types of strings.
```Python
print("normal str,\t escaping characters") # normal str,    escaping characters
print(r"\n raw string \t no escaping characters") # \n raw string \t no escaping characters
# unicode type, it represents english and non-english characters
print(u"This is unicode") # This is unicode
# formatting type, used to pass python expression/variable inside a string
n = 1
text = f"This is a String number {n}" # f-string to pass variable
text = f"This is a String number {20-19}" # or even to pass expression
text = "This is a String number %s" %n  # or C like formatting 
text = "This is a String number {0}".format(n) # or format method of string
print(text) # This is a String number 1
```
* Multiplying and joining operations on strings.
```Python
## Multiplying: use the '*' operator on string to replicate to the count.
string1 = "this" * 5
print(string1) # thisthisthisthisthis

## Joining: use the '+' operator to join two or more strings, they should be str. 
# str is immutable, so a new string is created when joining. 
string1 = "This is 1."
string2 = "This is 2."
new_string = string1 + string2
print(new_string) # This is 1.This is 2.
```
* Indexing, iterating and slicing operations on strings.
```Python
sample_str = "This contain some characters"

## Indexing: accessing item/character from string
print(sample_str[0]) # T
print(sample_str[2]) # i

# negative indexing: starts from 1 and not 0
print(sample_str[-1]) # s
print(sample_str[-5]) # c

## Iterating: going over item by item from a string
for x in sample_str:
  print(x)

## Slicing: for creating substrings, syntax is [start_index:end_index:step] 
# start_index is starting index of substring, default is 0
# end_index is ending index, (end_index - 1) is considered, default is last index
# step is the gap between characters, default is 1 
my_string = "This is some string."
print(my_string[5:7]) # is
print(my_string[5:]) # is some string.
print(my_string[:4]) # This 
print(my_string[:5:2]) # Ti 
print(my_string[:-4]) # This is some str
# reverse a string
print(my_string[::-1]) # .gnirts emos si sihT
```
* Some methods of string.
```Python
my_string = "this IS it."
# Returns Lowercases all characters of given string
print(my_string.lower()) # this is it.
# Returns Uppercases all characters of given string
print(my_string.upper()) # THIS IS IT.
# Returns Capitalizing first character string
print(my_string.capitalize()) # This is it.
# Splits at a given string key(which is whitespace here) and returns list of strings
print(my_string.split(" ")) # ['this', 'IS', 'it.']
# Removes whitespace from beginning, also can strip given another key string 
print(my_string.strip()) # this IS it.
# Searches given key/string(which is 'it' here) and returns starting index if found
print(my_string.index("it")) # 8
# Searches given key string(which is 'it' here), replaces with 
# second key(which is 'not it' here) string and then returns the final string
print(my_string.replace("it","not it")) # this IS not it.
# joins a list of strings to a single string with a given string key(which is '.' here)
print(".".join(['hey','is','this','it?'])) # hey.is.this.it?
```
* Some functions on string.
```Python
my_string = "this IS it."
# Returns the length of a string
print(len(my_string)) # 11
# Returns the string representation of any object, for str object returns a string with no escaping characters
print(repr("This \t should have escaped.")) # 'This \t should have escaped.'
# Returns a Unicode of a character
print(ord("c")) # 99 
# Returns Converted the Unicode to a character
print(chr(ord("c"))) # c
```
* Type conversion examples.
```Python
my_string = "bar"
my_string1 = "20"
# str to int
print(int(my_string)) # ValueError
print(int(my_string1)) # 20
# str to float
print(float(my_string)) # ValueError
print(float(my_string1)) # 20.0
# str to bytes
print(bytes(my_string, encoding='utf-8')) # b'bar'
```
### <strong>2.3 Boolean Type (bool)</strong>
* Has only 2 values *True* and *False*. *True* is also 1, so 4 + *True* is 5. *False* is also 0, so 4 + *False* stays 4. Boolean values *True* & *False* are also referred as Truthy & Falsy values when evaluating.
* Creating boolean types. 
```Python
my_bool = True
print(type(my_bool)) # <class 'bool'>
my_bool = my_bool + 4 # becomes 5
my_bool = False
my_bool = my_bool + 4 # stays 4
```
* Type conversion or truth value testing with boolean values.
```Python
# number to bool, anything not 0 is True
print(bool(-40), bool(0), bool(40)) # True False True
# str to bool, empty string is False, rest is True
print(bool(""), bool("This is string")) # False True
```
### <strong>2.4 Binary Types (byte)</strong>
#### 2.4.1 Little bit about Computer Memory
A computer stores data in its memory in binary (0's and 1's) format only. A bit (binary digit) is the smallest possible unit of data in a computer. Typically a group of eight bits is known as a byte. Eg 10100101 this is a byte. A single byte represents numbers between 0 (00000000) to 255 (11111111), so 256 (2^8) bits in total, similarly a KiloByte (KB) is 1024 bytes, a MegaBytes (MB) is 1024 KB and so on. A file is a sequence of these bytes, the size of a file is determined by the number of bytes in them. A programming language usually deals with two types of file, a Text file and Binary file. Text file contains character data and Binary files contain well.. binary data. For example images, documents, executables & compressed files, compiled programs etc are called binary files. Now to store characters (Text files) in a computer, encoding schemes are used. It is simply a way to represent Character (human readable data) in Binary format (computer readable), various schemes such as UTF-8 or UTF-16 are used. A Encoding scheme has to follow a Character Set (such as ASCII/ISO/UTF/Unicode), which is basically a table of unique numbers assigned to the letters, numbers and symbols used in languages or on keyboards.

#### 2.4.2 Two functions to convert a string to bytes
#### 1. bytes(source, encoding, errors) => bytes
**Parameters**:</br>
  * *source* *object*: Any object.
  * *encoding* *str*: Provide encoding scheme for the source string.
  * *errors* *str*: Way to handle errors for source data.

**Explanation**: This function creates an immutable object consisting of Unicode (character set containing all major languages characters) 0-256 characters.
* Creating byte types. 
```Python
## create a bytes object
data = bytes("This is bytes data", 'UTF-8')
print(data) # b'This is bytes data'
# or can use b prefix on string like syntax
print((b'42')) # b'42'
print(type(b'42')) # <class 'bytes'>

## initialize bytes object with 0's by providing size in int
my_bytes = bytes(4)
print(my_bytes) # b'\x00\x00\x00\x00'

## indexing a bytes object returns a Unicode of a character
print(data[0], chr(data[0])) # 84 T
``` 
* Type conversion. 
```Python
## create bytes object using a iterable objects
print(bytes([1,2,3])) # b'\x01\x02\x03'
print(bytes((80,50,60))) # b'P2<'
```
#### 2. bytearray(source, encoding, errors) => bytearray
**Parameters**:</br>
  * *source* object: Any object.
  * *encoding* *str*: Provide encoding scheme, if source is string.
  * *errors* *str*: Way to handle errors, if the source is a string.

**Explanation**: This function returns a mutable version of bytes object.
* Creating bytearray types. 
```Python
# create bytearray with 0's by providing size in int
output = bytearray(4)
print(output) # bytearray(b'\x00\x00\x00\x00')
print(bytes("Something", 'UTF-8')) # b'Something'
print(type(output)) # <class 'bytearray'>

## bytearray is mutable so
output[0] = 30
print(output) # bytearray(b'\x1e\x00\x00\x00')
```
### <strong>2.5 User-defined Data Type</strong>
* User defined data types are used to create a new data type by combining the built-in data types. Unlike in C/C++ Python doesn't have *struct*, but what it does have is classes, which can be utilized to do the same.
* Create a user defined data type.
```Python
class MyDataType:
  def __init__(self, x, y):
    # initialize here
    self.x = x 
    self.y = y
    
  # this function is totally optional  
  def __str__(self):
    """Define this 'magic method' to enable print functionality for this object, it should return a string."""
    return f"{self.x} {self.y}"

my_dt = MyDataType(10, "Hello")
# check type
print(type(my_dt)) # <class '__main__.MyDataType'> 
# access/change values using '.' operator
print(my_dt.x, my_dt.y) # 10, Hello
# or print if __str__ is defined
print(my_dt) # 10, Hello
# change values
my_dt.x = 42 
my_dt.x = "THis can also become a string" 
# The problem is you can't define type of data or length of an array(list) in Python
# For such situations you can create your own methods for inserting
# where you can check the type of data that is fed in
# But will it not be a Data structure? Nope?
```
* Create a slightly better data type that can check the inputs.  
```Python
class MyDataType:
  def __init__(self, x, y):
    """__init__ is another 'magic method', which enables usage of constructor in python, more on this later."""
    # initialize here
    if not isinstance(x, int) or not isinstance(y, str):
      raise TypeError() # raise error if type does not match
    self.x = x 
    self.y = y
    
  def insert(self, x=None, y=None):
    """To check values while inserting in our custom data type"""
    if x:
      if isinstance(x, int):
        self.x = x
      else:
        raise TypeError("Should be a integer")  
    if y:
      if isinstance(y, str):
        self.y = y  
      else:
        raise TypeError("Should be a String")
        
  def __str__(self):
    """Define this 'magic method' to enable print functionality for this object, it should return a string."""
    return f"{self.x} {self.y}"

# create our data type
my_dt = MyDataType(10, "Hello")  
# insert values
my_dt.insert(15, "Foo") 

print(my_dt) # 15 Foo
my_dt.insert(20) 
my_dt.insert(y="Bar")
print(my_dt) # 20 Bar
# raising type error if data type is not what we expected
my_dt.insert(y=20) # TypeError: Should be a String
```
### <strong>2.6 *None* Object</strong>
* *None* is similar to *null* in C/C++/Java, it indicates that something has no value, but there are some differences. In those languages *null* refers to a pointer that doesn't point to anything and it is also *0*, not in Python. In Python, *None* is not "0", it's an object itself. It is an object of *NoneType* class and is a singleton i.e only one instance is created of *None* in a program. 
* *None* is often used in absence of value in a variable, as a default value in a function parameter and is returned by default by a function if no return statement is provided or any condition is met.
* Creating a *None* type.
```Python
n = None
print(type(None)) # <class 'NoneType'>

## to check whether an object is not None simply use 'if <object_name>'
if n: # same as "if n != None:"
  print('will not enter this condition')

## not to negate that condition
if not n: # same as "if n == None:"
  print('will enter this condition, as n is None')
```
### <strong>2.7 Some related built-in functions</strong>
 Let's check some functions which we'll be using later on such as [type()](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#1-typeobject--str), [isinstance()](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#2-isinstanceobject-class--bool), [id()](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#3-idobject--int), [dir()](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#4-dirobject--list).
#### 1. type(object) => *str*
**Parameters**:</br>
  * *object* object: Any object.

**Explanation**: This function is used for type checking, it returns the class name of an object.
```Python
a = "What?"
print(type(a)) # str
b = 5.0
print(type(b)) # float
```
#### 2. isinstance(object, class) => bool
**Parameters**:</br>
  * *object* object: Any object.
  * *class* class: Any class.

**Explanation**: This function checks if an object is an instance of a particular class. Returns True/False.
```Python
a = 23
print(isinstance(a, int)) # True
print(isinstance(a, float)) # False
print(isinstance(a, str)) # False
```
#### 3. id(object) => int
**Parameters**:</br>
  * *object* object: Any object.

**Explanation**: This function returns the object identity which is the object’s address in memory. The returned object id varies across programs/systems, so will not be the same anytime. 
```Python
my_float = 50.0
# object id will differ each time with program
print(id(my_float)) # 1875526208176
```
#### 4. dir(object) => list
**Parameters**:</br>
  * *object* object: Any object.

**Explanation**: Returns a *list* containing names of variables/functions/class in an object. This function also works on modules, as modules are also objects.
```Python
## names under current local scope
print(dir())

## list of object's attributes
print(dir(int))
print(dir(my_obj))
```

## <strong>3. Data Structures</strong>
#### Wikipedia suggests
  > In computer science, a data structure is a data organization, management and storage format that enables efficient access and modification.

Simply put data structures are used to organize data in a way that it can be stored/retrieved efficiently. Data can be any data types or even other data structures. Different data structures have their advantages/disadvantages in terms of accessing/storing/removing data speed, so they should be used as per the task/ease. They can also be called literal collections. In Python, you can't/don't need to declare the size of the built-in data structures beforehand, they are dynamically scaled/released automatically in the background. 
#### Composite Data Type, Abstract Data Type and Data Structures differences.
  1. Composite Data Types are data structures but not all data structures are composite types.
  2. Abstract Data Type defines only the mathematical model of the implementation of a data type i.e they only exist in pseudo code.
  3. Data structures are the actual coded/coding implementation of the pseudo code i.e they are implemented in a programming language's code.
 
The built-in Data Structures explained below are [list](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#31-list), [tuple](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#32-tuple), [dict](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#33-dict) and [set](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#34-set). Additionally we'll also take a look at some of their alternatives. Later we'll check out some more built-in functions which provide additional useful operations. Let's get to it.
### <strong>3.1 List</strong>
* By the name it may seem a *LinkedList* data structure but its not, *list* is an array (Dynamic Array) like implementation in Python. *list* is an ordered collection of sequence of items, which can be of any data type or objects.
* *List* is Mutable (values can be changed) and an *iterable* object (can be iterated using loops, more on this later). It supports Indexing, Slicing, and also Comprehensions, which is a short way of creating a sequence.  
* They are preferred in most use cases. They are regularly used for storing, indexing & iterating elements. 
* Creating a *list*.
```Python
# insert items inside '[]' brackets
my_list = [1,1,3,'a','cab boy',4.0]
# or create empty list
some_list = [] 
# or using the list() function
some_list = list()
```
* Basic operations on a *list*. 
```Python
my_list = [23,65,12,76,10]

## Adding/Appending: adding values to list
my_var = 1
my_list.append(my_var)
print(my_list) # [23, 65, 12, 76, 10, 1]

## Altering: change values of list items
my_list[0] = 100
my_list[4] = 200
print(my_list) # [100, 65, 12, 76, 200]

## Removing: remove values from list
my_list.remove(my_var)
# remove using 'del' statement is mostly preferred, eg 'del my_list[index]'
del my_list[0] # or even with slicing, eg del my_list[2:4]
# or using 'pop' method of list, 'my_list.pop(index)'
# Note: del statement can be used to delete any other object too.
print(my_list) # [65, 12, 76, 200]

## Checking if some value is present in list
if 20 in my_list: # similar to "if some_var in my_list:" where "some_var = 20"
  print('not printed')
if 200 in my_list:
  print('printed')
```  
* Joining and multiplying operations on a *list*.
```Python
## Joining: join two or more lists
# using '+' operator
my_list1 = [2,4,5,6] + [34,7,4,2]
print(my_list1) # [2, 4, 5, 6, 34, 7, 4, 2]
# using 'extend()' method
my_list1.extend([3,6,2])
print(my_list1) # [2, 4, 5, 6, 34, 7, 4, 2, 3, 6, 2]

## Multiplying: using '*' operator on a list
eg_list = ['This',30]
print(eg_list*3) # ['This', 30, 'This', 30, 'This', 30]
```
* Indexing, iterating, slicing operations on a *list*.
```Python
my_list = [1,1,3,'a','cab boy',4.0]
my_list1 = [45,23,5,6,34,6,22]

## Indexing: for accessing/altering elements
var_1 = my_list1[0] # as usual 0 is the first element

var_2 = my_list1[1]
print(var_1, var_2) # 45, 23
# altering values in list
my_list1[0] = 100
my_list1[1] = 200
print(my_list1) # [100, 200, 5, 6, 34, 6, 200] 
# checking if some value is present in list
if 20 in my_list1: # similar to "if some_var in my_list1:" where "some_var = 20"
  print('not printed')
if 200 in my_list1:
  print('printed')

## Iterating: going over item by item from a list
for var in my_list1:
  print(var) # [2, 4, 5, 6, 34, 7, 4, 2, 3, 6, 2]

## Slicing: for creating sub-list, syntax is [start_index:end_index:step]
print(my_list[3:5]) # ['cab', 1.0]
print(my_list[5:]) # [2.0, 1]
print(my_list[:3]) # [3, 'a', 'this way']
print(my_list[:5:2]) # [3, 'this way', 1.0]
# negative indexing similar to string
print(my_list[:-4]) # [3, 'a', 'this way']
# reverse a list
print(my_list[::-1]) # [1, 2.0, 1.0, 'cab', 'this way', 'a', 3]
```
* *list* comprehension.
```Python
## List comprehension: create a new list in a single line 
# Note: range function returns sequence of integers, we'll learn more on range later 
my_list1 = [x for x in range(10)]
# this is similar to 
my_list1 = []
for x in range(10):
    my_list1.append(x)

# comprehensions are syntactic sugar, they save lines of code
my_list2 = [[y for y in range(x)] for x in range(5)] # it can be nested
my_list3 = [abc for abc in range(10) if abc > 5] # if condition
my_list4 = [True if z > 5 else False for z in range(10)] # if with else condition
# Notice: the syntax difference between if and if..else clauses
# also try printing each of the list
```
* Copy a *list* example. 
```Python
my_list = [1,2,3,4,5,6]
new_copy = my_list
del new_copy[0] # deleting first item

print(my_list, new_copy) # [2, 3, 4, 5, 6] [2, 3, 4, 5, 6]
# the deletion is reflected to of the lists because they refer to same object
# this behaviour is exclusive to mutable objects, the catch from 'Multiple Target assignment'
# modified mutable objects reflect changes to its references

## Creating a copy 
new_copy = my_list[:] # or "my_list.copy()"
del new_copy[0]
# now they do not refer to the same object 
print(my_list, new_copy) # [2, 3, 4, 5, 6] [3, 4, 5, 6]
```
* Some methods of *list*.
```Python
my_list1 = [10,50,40,50,60,80,15]
# reverses a list, its inplace so does not return anything
my_list1.reverse() 
print(my_list1) # [15, 80, 60, 50, 40, 50, 10]
# sorts a list, inplace
my_list1.sort()
print(my_list1) # [10, 15, 40, 50, 50, 60, 80]
# returns index of first arrival of given value 
print(my_list1.index(50)) # 3
# removes value from a list given value
my_list1.remove(15) 
# removes value from a list given index, also returns the value
print(my_list1.pop(5)) # 80
my_list1.clear() # list becomes empty
print(my_list1) # []
```
* Some functions on the *list*.
```Python
my_list1 = [10,50,40,50,60,80,15]

# returns sorted list of items in ascending order by default, 
# sorting is O(nLogn), for reversing pass 'reverse=True'
print(sorted(my_list1)) # [10, 15, 40, 50, 50, 60, 80]
# return length of list
print(len(my_list1)) # 7
# sum of variables
print(sum(my_list1)) # 305
print(sum([10, 20])) # 30
```
* Type conversion examples.
```Python
my_list = list((1,2,3,4,5)) # tuple to list
my_list = list({1,2,3,4,5}) # set to list
```
* **Time Complexity** </br>
indexing, appending (to the end) and get_length are O(1).</br>
deleting, poping, inserting (at position), iteration are O(n).
#### 3.1.1 Array
* *list* allows to hold data of any data-type/object which is great, but this means the data is usually less tightly coupled, so they end up taking more storage. To hold a large amount of data efficiently one can utilize the *array* types.
* Similar to *list*s they are mutable, iterables, they support indexing, slicing, they even share almost all *list* operations. The difference is they allow storing data of limited types only such as characters, integers or floating point numbers and one data type per array. It has to be one of in C language's Data-Types (eg. *signed int*/*unsigned float*).
* They are not part of the core Python, so they need to be imported from the *array* module and are required to be declared first. When declaring we need to define the type of data the *array* can contain, it can be one of types mentioned in the table shown [here](https://docs.python.org/3/library/array.html#module-array). 
* Creating an array.
```Python
import sys
import array

# create a normal list
my_list = [54,32,65,32,65,32]
# while declaring the first parameter is c data type (only the mentioned in the table)
# and another is data from a sequence type such as list/tuple
my_array = array.array('i', my_list)
print(my_array) # array('i', [54, 32, 65, 32, 65, 32])
# so here i shows signed integer data type
# create a character data array
char_array = array.array('u', 'somestr')
print(char_array) # array('u', 'somestr')

# check their memory usage 
print(sys.getsizeof(my_list)) # 152
print(sys.getsizeof(my_array)) # 88
# we can see a difference in bytes, array consumes less space compared to list
```
* Indexing, iterating and slicing operations on an *array*.
```Python
import array
my_array = array.array('i', [5,7,11,6,2,8,1])

## Indexing
print(my_array[0]) # 5

## Iterating
for a in my_array:
    print(a) # [5,7,11,6,2,8,1]

## Slicing
print(my_array[1:3]) # array('i', [7, 11])
```
* Some methods of *array*.
```Python
import array
my_array = array.array('i', [5,3,5,5,2,7,8])

my_array.append(30)
print(my_array.index(30)) # 7
my_array.remove(30)
print(my_array.pop(3)) # 5
# length of item in byte
print(my_array.itemsize) # 4
# appending from array
my_array.fromlist([67,87])
print(my_array) # array('i', [5, 3, 5, 2, 7, 8, 67, 87])
```
### <strong>3.2 Tuple</strong>
* Are ordered collections of sequence of items similar to *list*s. But unlike *list*s they are Immutable (items cannot be altered/deleted), so they are preferred when data should not be changed. They are data efficient than *list* and are slightly faster than *list*. Indexing, Slicing is supported and they are iterable objects just like lists, but there is no *tuple* comprehension (it becomes a generator). 
* They are mostly used to store different data type items, unlike *list*s which are mostly used for storing similar items, but either way is also valid. 
* Creating a *tuple*.
```Python
# insert items inside '()' brackets
my_tuple = (1,2,3,'we','are','one',5.0)
# create empty tuple
some_tuple = () # or using tuple() function
```
* Basic operations on a *tuple*.
```Python
## tuple is immutable, there is no append()/remove(), can't use 'del' like in list
# so to add a element join two tuples, and assign it to the previous/new variable
my_tuple = (1,2,3,4)
my_tuple += (5,) # adding another element as tuple, its basically joining two tuples
print(my_tuple) # (1, 2, 3, 4, 5)
# Notice: The target tuple should have ',' if single element is being added
some_tuple = (5) # this will give the type of variable inside parenthesis and not tuple, here 'int'
print(type(some_tuple)) # <class 'int'>
```
* Joining and multiplying operations on a *tuple*.
```Python
## Joining: join two or more tuples
my_tuple1 = (34,65,23) + (34,34)
print(my_tuple1) # (34, 65, 23, 34, 34)

## Multiplying: using '*' operator on a tuple
my_tuple1 = (34,65,23) * 2
print(my_tuple1) # (34, 65, 23, 34, 65, 23)
```
* Indexing, iterating and slicing operations on a *tuple*.
```Python
my_tuple = (1,2,3,'we','are','one',5.0)

## Indexing: accessing item/character from tuple
my_var = my_tuple[0] # okay
my_tuple[0] = 23 # not okay because Immutable, raises TypeError

## Iterating: going over item by item from a tuple
 for var in my_tuple:
   print(var) # (1,2,3,'we','are','one',5.0)
# checking if some value is present using the 'in' operator
if 5.0 in my_tuple:
  print('printed')

## Slicing: for creating sub-tuple, syntax is [start_index:end_index:step] 
print(my_tuple[3:5]) # ('we','are')
print(my_tuple[5:]) # ('one',5.0)
print(my_tuple[:3]) # (1,2,3)
print(my_tuple[:5:2]) # (1,3,'are')
# negative indexing
print(my_tuple[:-4]) # (1,2,3) 
print(my_tuple[:-2:2]) # (1, 3, 'are')
# reverse a tuple
print(my_tuple[::-1]) # (5.0, 'one', 'are', 'we', 3, 2, 1)
```
* Unpacking a *tuple*.
```Python
## unpacking tuple (more on unpacking later on)
a,b,c = (1,2,3) # unpacking values into a,b,c
# even below line does the same, 1,2,3 becomes a tuple and then unpacks into a,b,c 
# same is true when returning comma separated values from a function 
a,b,c = 1,2,3 # same as (1,2,3)
# this behaviour further aids in swapping without using extra variable,
# you can also do the same with more variables
a,b = b,a 
```
* Some methods of *tuple*.
```Python
my_tuple1 = (3,2,6,2,5,3,1,1)
# Returns number of occurrences of value.
print(my_tuple1.count(3)) # 2
# Returns the first index of value.
print(my_tuple1.index(2)) # 1
```
* Some functions on *tuple*s.
```Python
my_tuple = (3,6,1,8,2,3)

# returns sorted list of items in ascending order by default
# can be reversed using the reverse parameter
print(sorted(my_tuple, reverse=True)) # [8, 6, 3, 3, 2, 1]
# returns length of tuple
print(len(my_tuple)) # 6
```
* Type conversion examples.
```Python
my_tuple = tuple([1,2,3,4,5]) # list to tuple
my_tuple = tuple({1,2,3,4,5}) # set to tuple
```
* **Time Complexity** </br>
indexing, appending (to the end) and get_length are O(1). </br>
deleting, poping, inserting (at position), iteration are O(n).
#### 3.2.1 NamedTuple
* As the name suggests, they are "named" *tuple* i.e regular tuples that support field/item names (and also indexes). So along with indexing they support accessing fields/elements using their names with the '.' operator (just as accessing the class variables). 
* They are a subclasses of a *tuple*. When instantiated they return a new *tuple* subclass named \<typename\>. This new subclass can be used to create tuple-like objects which are also immutables, indexable, iterables and are as data efficient as a regular *tuple*.  
* They are not part of core Python and need to be imported from the *collections* module. They provide more readable, self-documenting code over the regular *tuple* where they are intended. 
* So why not use custom class anyway? If you're okay with immutable types, *namedtuple* saves you most of the hassle of writing the code for operations (like iterable, indexing) with the convenience of naming access. 
* Creating a *namedtuple*.
```Python
from collections import namedtuple
import sys

# first parameter of namedtuple is typename: string which is name of tuple subclass
# second parameter is field_names: iterable/string  which has names of fields/variables/data tuple will contain 
Name_tup = namedtuple("mynamedtuple", ['a', 'b'])
# or provide names from a single string (separated by space)
Name_tup = namedtuple("mynamedtuple", "a b")
# print the class name 
print(Name_tup) # <class '__main__.mynamedtuple'>

# create the namedtuple object
name_tup1 = Name_tup(42,65)
# can also create another object with different data type
name_tup2 = Name_tup("oh","this")
print(name_tup1) # mynamedtuple(a=42, b=65)
print(name_tup2) # mynamedtuple(a='oh', b='this')

# accessing elements with names
print(name_tup2.a) # oh
print(name_tup2.b) # this

# comparing with regular tuple
print(name_tup1 == (42, 65)) # True
# comparing their sizes
print(sys.getsizeof(name_tup1), sys.getsizeof((42, 65))) # 56, 56

# like regular tuple immutable
name_tup1[0] = 32 # TypeError
```
* Indexing, iterating and slicing operations on a *namedtuple*.
```Python
from collections import namedtuple

Name_tup = namedtuple("mynamedtuple", ['aa', 'bbk', 'cab'])
name_tup1 = Name_tup(42,60,52)

## Indexing like tuples
print(name_tup1[0]) # 42
print(name_tup1[1]) # 60

## Iterating
for a in name_tup1:
    print(a) # 42,60,52

## Slicing
print(name_tup1[1:]) # (60, 52)
```
* Some methods of *namedtuple*.
```Python
from collections import namedtuple

Name_tup = namedtuple("mynamedtuple", ['aa', 'bbk', 'cab'])
name_tup1 = Name_tup(42,60,52)
# convert to dictionary
print(name_tup1._asdict()) # {'aa': 42, 'bbk': 60, 'cab': 52}
# replace the value, creates and returns a new mynamedtuple instance
print(name_tup1._replace(aa=32)) # mynamedtuple(aa=32, bbk=60, cab=52)
```
### <strong>3.3 Dictionary</strong>
* Dictionary short form *dict* in Python, is an unordered collection of key & value pairs of items. Dictionaries are mutable, iterable, but Indexing/Slicing doesn't work as their order doesn't matter. 
* A dictionary uses Hashtable to store data with a key & value.A hashtable uses a hash function which, given a key, generates an index to an array like Data Structure, which stores the actual values. So instead of indexing, these keys are used to access values. This behaviour helps hashmap to do almost all operations in O(1) making them very efficient for storing and retrieval operations.
* Keys in a dictionary should be hashable i.e have a hash value that does not change throughout its lifetime, all immutable objects are hashables. Values have no restriction, they can be any object. 
* They are used in Dynamic Programming and generally where values are supposed to have some key associated with them.
* Creating a dictionary.
```Python
# insert keys & values inside '{}' brackets
# Note: key & value are separated with ':' colon. i.e key:value

my_dict = {'e':23, 'w':65, 'q':52}
# create empty dictionary
my_dict = {} # or using dict() function
```
* Basic operations on a dictionary.
```Python
my_dict = {'raf': 23, 'soe': 65, 'qr': 52, 10: 20}
## add operation
my_var = 20
key = 10
tuple_key = (20,)
# add item at key
my_dict[key] = my_var # adding 10: 20
my_dict[tuple_key] = 45 # adding (20,): 45
my_dict['az'] = 42 # adding 'az': 42
print(my_dict) # {'raf': 23, 'soe': 65, 'qr': 52, 10: 20, (20,): 45, 'az': 42}

## remove
del my_dict[tuple_key] # remove the item

## accessing element
key = 'qr'
my_var = my_dict[key] # can raise KeyError if not present
# use get() method to avoid KeyError, None is default, can be set to anything else
print(my_dict.get("ar", None)) # None

## check if key is inside my_dict   
if 'az' in my_dict:
  print('printed')
```
* Joining and iterating operations on a dictionary.
```Python
my_dict = {'a':34, 'b': 42}
my_dict1 = {'z':5, 'y':3, 'x':4}

## Joining: join two dictionary, '+' operator is not supported
# using the update method of dictionary
my_dict.update(my_dict1)
print(my_dict) # {'a': 34, 'b': 42, 'z': 5, 'y': 3, 'x': 4}
# or use "my_dict | my_dict1" 
print(my_dict | my_dict1) # {'a': 34, 'b': 42, 'z': 5, 'y': 3, 'x': 4}
# or unpack them in a new dict 
print({**my_dict, **my_dict1}) # {'a': 34, 'b': 42, 'z': 5, 'y': 3, 'x': 4}

## Iterating: going over item by item from a dictionary
# use the items method for both keys, values unpacking
for k,v in my_dict1.items(): 
   print(k, v) # {'z':5, 'y':3, 'x':4}
```
* Dictionary comprehension. 
```Python 
my_dict = {x:x*x for x in range(5)} # generating keys and values on the go
print(my_dict) # {0: 0, 1: 1, 2: 4, 3: 9, 4: 16}
# another way is using the zip function
my_keys = ['a', 'b', 'c']
my_values = [1,2,3]
my_dict = {k:v for k,v in zip(my_keys, my_values)}
print(my_dict) # {'a': 1, 'b': 2, 'c': 3}
# similar to list's comprehension, dictionaries also support if..else clause inside comprehension
# create a dictionary without a key 'a' 
my_dict = {k:v for k,v in zip(my_keys, my_values) if k is not 'a' }
```
* Some methods of dictionaries.
```Python
my_dict1 = {'a':1, 'b':2, 'c':3}
my_dict2 = {'z':50, 'y':40, 'x':30}

# returns a dict_keys object, it contains dictionary's keys, it is iterable, you can also convert it to list
print(my_dict1.keys()) # dict_keys(['a', 'b', 'c'])
# returns a dict_values object, it contains dictionary's values, it is iterable, you can also convert it to list
print(my_dict1.values()) # dict_values([1, 2, 3])
# returns a dict_items object, has keys & values, you know the rest
print(my_dict1.items()) # dict_items([('a', 1), ('b', 2), ('c', 3)])
# removes item(key,value) given key, which is 'a' here and returns value
print(my_dict1.pop("a")) # 1 
my_dict1.clear() # removes all items of dictionary
```
* Type conversion examples.
```Python
keys = [1,2]
values = [2,3]
my_dict = dict([keys, values]) # list to dictionary
my_dict = dict(((1,2), (2,3))) # tuple to dictionary
```
* **Time Complexity** </br>
Dictionaries are implemented using HashMaps, so most operations are O(1) and depending on implementation worst case O(n). </br>
insert, add, delete is O(1). </br>
iteration is O(n).
### <strong>3.4 Set</strong>
* Are unordered collections of non repeating sequences of immutable items. Similar to dictionary, *set* is mutable, iterable, but Indexing/Slicing doesn't work. 
* Items/Members inside a *set* should be hashable (must have a *\_\_hash\_\_()* method), its hash value must never change during its lifetime. *int*, *float*, *str* & *tuple* (with hashable items in them) are hashable. This behaviour allows sets to check if a particular object is unique from other members and also to perform operations like intersection, union. 
* Sets are used to maintain unique values and in membership testing i.e check if the variable is already present in the *set*. Like in BFS/DFS algorithms for checking visited nodes.
* Creating a *set*.
```Python
# insert values inside '{}' brackets
my_set = {9,1,5,2,20} # Notice: dictionary like parenthesis but without keys
# items order don't matter, so while printing order might differ
print(my_set) # {1, 2, 20, 5, 9}
# create a empty set
my_set = set() 
```
* Basic operations on a *set*.
```Python
my_var = 4
my_set = {9,1,5,2,20}

## add
my_set.add(my_var) # if repeated value, it will not be added again 

## remove
my_set.remove(my_var) # removes a member, raises KeyError if not found

## accessing element: indexing is not supported
my_set[0] # not allowed, TypeError: 'set' object is not subscriptable.
# so use in operator to check if my_var is inside my_set   
if my_var in my_set: 
  print('not printed')
```
* Joining and iterating operations on a *set*.
```Python  
a = {54,23,67}
b = {34,65,55.6}

## Joining: join two sets, '+' operator is not supported, use the update method
a.update(b) 
print(a) # {65, 34, 67, 55.6, 54, 23}

## Iterating: going over item by item from a set
for x in a: 
   print(x) # {65, 34, 67, 55.6, 54, 23}
```
* *set* comprehension.
```Python
# creating a set using comprehensions
my_set = {a for a in (10,10,20,30,60,20,40)}

# similar to previous comprehensions, there is also multiple comprehension
my_set = {(a,b) for a in range(2) for b in range(3)}
# Notice: (a,b) is a tuple inside a set
# above expression is similar to
my_set = set()
for a in range(2):
    for b in range(3):
        my_set.add((a, b))
print(my_set) # {(0, 1), (1, 2), (0, 0), (1, 1), (0, 2), (1, 0)}
# you can try practicing different combinations of comprehensions  
```
* Some methods of *set*.
```Python   
my_set1 = {3,5,7,1,8}
my_set2 = {1,2,3,4,5}

# find intersection, or use 'my_set1 & my_set2'     
print(my_set1.intersection(my_set2)) # {1, 3, 5}
# to find union, or use 'my_set1 | my_set2'   
print(my_set1.union(my_set2)) # {1, 2, 3, 4, 5, 7, 8}
# find difference in my_set1 and my_set2
print(my_set1.difference(my_set2)) # {8,7}
# checks if my_set2 is a subset of my_set1
print(my_set1.issubset(my_set2)) # False
# checks if my_set2 is a superset of my_set1
print(my_set1.issuperset(my_set2)) # False
# removes all members of set
my_set2.clear() 
# create a copy of a set, a shallow copy
my_copy = my_set1.copy() 
# it means copying only references of original items into a new sequence, 
# so if a item isn't a literal constant like a list, 
# any modification made inside that list will be reflected to that item of a new copy 
```
* Type conversion examples.
```Python
my_list = [1,2,3,4,5]
# here my_list is mutable, but set() function unpacks the items from my_list
my_set = {my_list} # this raises TypeError
my_set = set(my_list) # this unpacks items from list to set
# also if my_list contained a list inside it, TypeError: unhashable type: 'list' is raised
my_set = set((1,2,3,4,5)) # tuple to set
```
* **Time Complexity** </br>
Sets are implemented using hash tables, so pretty much all operations should be O(1) and worst case when Hash collision occurs O(n). </br>
adding, checking (with the *in* operator) and removing are O(1). </br>
iterating is O(n). </br>
union is O(m+n). </br>
intersection is O(min(m,n)), worst is O(m\*n).
#### <strong>3.4.1 FrozenSet</strong>
* They are *set* but the only difference is that they are immutable. So once a *frozenset* is created the elements/members cannot be removed/added. Rest is pretty much similar to *set*, they are a non repeating sequence of items, unordered, iterable and no indexing/slicing is supported. They can be created using any iterable object.
* Creating a *frozenset*.
```Python
# using a list
my_fset = frozenset([10,65,65,2,7,94,34,42,21])
# or any other iterable
my_fset = frozenset((10,65,65,2,7,94,34,42,21))
print(type(my_fset)) # <class 'frozenset'>
print(my_fset) # frozenset({65, 2, 34, 7, 10, 42, 21, 94})

## immutable 
my_fset.add(20) # AttributeError: 'frozenset' object has no attribute 'add'
my_fset.remove(20) # AttributeError: 'frozenset' object has no attribute 'remove'
```
* Some methods of *frozenset*.
```Python  
my_fset1 = frozenset({3,5,7,1,8})
my_fset2 = frozenset({1,2,3,4,5})

# intersection 
print(my_fset1.intersection(my_fset2)) # frozenset({1, 3, 5})
# union
print(my_fset1.union(my_fset2)) # frozenset({1, 2, 3, 4, 5, 7, 8})
# difference
print(my_fset1.difference(my_fset2)) # frozenset({8, 7})
# creates a copy of a set
my_copy = my_fset1.copy() 
# checks if my_fset2 is a subset of my_fset1
print(my_fset1.issubset(my_fset2)) # False
# checks if my_fset2 is a superset of my_fset1
print(my_fset1.issuperset(my_fset2)) # False
```
### <strong>3.5 Extras</strong>
#### 3.5.1 Stack
* Stacks are LIFO, Last In First Out Data Structures. Elements go in and out from a single direction only. Main operations/methods of Stack are adding an element which is called a *push* operation and removing an element which is called a *pop* operation. Other operations are *isEmpty*, *isFull* and *peek* etc.
* The main operations of Stack can be easily performed using *list*'s available methods. And as *append* is ~O(1) and *pop* is O(1), *list* should be good enough for Stacks.
```Python
# create a stack
my_stack = []
## add/remove operation
my_stack.append(20) # push: append at top
my_stack.pop() # pop: remove at top
```
#### 3.5.2 Queue
* Queues are FIFO, First In First Out Data Structures. Elements go in one direction and go out from another direction. Main operations/methods of Queue are adding an element which is called an *enqueue* operation and removing an element which is called a *dequeue* operation. Other operations are *isEmpty*, *isFull* and *peek* etc. Variants of Queue are circular queue, priority queue and dequeue. 
```Python
# create a queue
my_queue = []
## add/remove operation
my_queue.append(20) # enqueue: append at rear
my_queue.pop(0) # dequeue: remove at front
```
* Python also has a *dequeue* (double ended queue) Data Structure which can also be used as a normal Queue. They are implemented as doubly linked-list and support adding & removing from both sides (front & end), they are efficient at add/remove from left (front) operation. Other operations have similar performance as *list*. 
* For Queues we only need to append at the end and pop/remove at the front, both of which are O(1) for *dequeue* which is good enough. They are not part of core Python and need to be imported from the *collections* module.
```Python
from collections import deque
import sys
my_list = [23,45,12,67,132,67]
# create a deque using any iterable
dq = deque(my_list)

## Queue operations
dq.append(20) # # push: append at top
dq.popleft() # pop: remove at top

# Only drawback is that they are data inefficient than list
print(sys.getsizeof(dq)) # 624
print(sys.getsizeof(my_list)) # 152
```
#### 3.5.3 Priority Queue
* Priority Queues are used when the elements are supposed to have some priority associated with them. So instead of using FIFO like normal queues, Priority Queue uses priority, elements with highest priority are taken out first. In order to work the data has to be comparable (same type).
* Python provides *heapq* which are Priority Queues implementation, they support only min-heap (smallest element has highest priority). The *heapq* module implements the Heap Data Structure (Binary heap) which is the most efficient way of implementing a Priority Queue. A Heap DS is a complete binary tree (all levels are filled except the leaf positions) that satisfies a heap property, which is nothing but the max/min criteria for getting elements out. 
* A Heap DS has a *heapify* function, it is responsible for constructing a Heap DS i.e constructing/adding elements in a binary tree for sorting. Three main operations *add*, *delete* and *peek* are explained below:
  1. *add*: First traverse to the last (leaf) empty position, add the element there and heapify the tree.
  2. *delete*: Select the index to be deleted, replace with the last element (rightest leaf), remove the last element and heapify the tree.
  3. *peek*: Traverse to the rightest leaf position, return the element.
* A Priority Queues is useful in tasks such as prioritizing, scheduling, load balancing etc. Another implementation of Priority Queue is in the *queue* module, named *PriorityQueue*, you can also use a normal *list* for doing the same utilizing the *sorted()* function, but *heapq* operations are efficient. 
```Python
import heapq

# create a priority queue, initialize with a empty list
my_pq = []

## add: use the heappush function to add elements, syntax (container, item)
# here container is our list 'my_pq'
heapq.heappush(my_pq, 3)
heapq.heappush(my_pq, 2)
heapq.heappush(my_pq, 0)

## remove: use the heappop function to get elements from the list
print(heapq.heappop(my_pq)) # 0
# smallest element is taken out
print(my_pq) # [2, 3]
# when a element is inserted it is put in right sorted position
# so [0] is always the smallest and the pop position

# elements should be comparable, so once int is inserted other elements should be int only
# or TypeError will be raised
# heapq.heappush(my_pq, (2, "task1")) # TypeError

my_pq = []
# the items can also be tuple, so we can provide some name  
heapq.heappush(my_pq, (1, "task2"))
heapq.heappush(my_pq, (5, "task3"))
print(heapq.heappop(my_pq)) # (1, 'task4')

# use heapify function to construct a Heap DS or sort elements
my_pq = [34,6,23,67,23,78]
heapq.heapify(my_pq)
print(my_pq) # [6, 23, 23, 67, 34, 78]
```
* Apart from the above Data Structures there are some more that I haven't mentioned, you can find them in the [collections](https://docs.python.org/3/library/collections.html) module. 
### <strong>3.6 Some related built-in functions</strong>
Now let's check out some more important built-in functions such as [range()](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#1-rangestart_index0-end_index-step1--range), [enumerate()](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#2-enumerateiterable--tuple), [zip()](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#3-zipiterable--zip), [sorted()](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#4-sortediterable-keynone-reversefalse--list), [filter()](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#5-filterfunction-iterable--filter) and [map()](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#6-mapfunction-iterable--map).
#### 1. range(start_index=0, end_index, step=1) => range
**Parameters**:</br>
  * *start_index* *int*: The start index for iteration.
  * *end_index* *int*: The stopping index for iteration.
  * *step* *int*: A skipping index in iteration.

**Explanation**: This function returns a sequence of length *start_index(0 by default)* to *end_index(is a required argument)*. *range()* function returns a range object, which is iterable, supports indexing and is immutable. It is mainly used in loops, where a certain number of times a loop should work, like for iterating to the length of an array in C/C++/Java.
```Python
# create a range object of length 20
my_range = range(20)) 
print(my_range) # range(0,20)
print(type(my_range)) # <class 'range'>

# create a range object values ranging 5 to 20
print(range(5,20)) # range(5,20)
# create a range object values ranging 6 to 20 with 2 steps
print(range(6,20,2)) # [6, 8, 10, 12, 14, 16, 18] 

## indexing a range
print(range(20)[0]) # 0
# supports slicing but its not preferred/recommended
print(range(20)[0:10]) 
# convert a range sequence to a list
print(list(range(5,10))) # [5,6,7,8,9] 

## looping a range object
for var in range(5): 
  print(var) # [1,2,3,4,5]
# reversing the order with step=-1 and end_index=-1
for var in range(5, -1, -1): 
  print(var) # [5,4,3,2,1]
```
#### 2. enumerate(iterable) => enumerate
**Parameters**:</br>
  * *iterable* iterable: Iterable object containing items.

**Explanation**: This function returns a *enumerate* object given an iterable, each item is a *tuple* which contains index & value. Index is in range from 0-length of the *list* and value is an item from the *list*. The *enumerate* object is iterable and indexing/slicing is not supported. Similar to *range*, *enumerate* is mostly used in iteration of loops. 
```Python
# create a enumerate object from a list
my_list = [100,200,500,100]
print(type(enumerate(my_list))) # <class 'enumerate'>

# checking the item of enumerate, it is a tuple (index, value)
print(list(enumerate(my_list))[0]) # (0,100) 

# looping over the enumerate object
for i, val in enumerate(my_list):
  print(i) # 0,1,2,3
  print(val) # 100,200,500,100
```
#### 3. zip(\*iterable) => zip
**Parameters**:</br>
  * *iterable* iterable: Iterable object containing items, '\*' denotes a function that can take multiple input objects.

**Explanation**: This function returns a *zip* object given single/multiple iterables, each item is a *tuple* which contains n (number of input iterables) length elements. When provided with multiple iterables, the length of the returned *zip* object is equal to the length of the smallest iterable. *zip()* is commonly used to unpack values from multiple iterables simultaneously in a loop.  
```Python
a = ['This','is','something']
b = (14, 3, 6)
c = {34,7} 
# create a zip object given a iterable
my_zip = zip(a)
print(type(zip(a))) # <class 'zip'>

# the length of zip is 2 because smallest is c and its length is 2
# so remaining values in a,c are ignored
print(len(list(zip(a, b, c)))) # 2
# convert to list in order to print
print(list(zip(a, b, c))) # [('This', 14, 7), ('is', 3, 34)]

# loop over the values
for v in zip(a, b, c):
  # v is a tuple with 3 values, so we can index them
  print(v[0], v[1], v[2]) # [('This', 14, 7), ('is', 3, 34)]
# or unpack them into named variables
for var1, var2 in zip(a,b):
  print(var1, var2) # [('This','is','something'), (14, 3, 6)]
```
#### 4. sorted(iterable, key=None, reverse=False) => list
**Parameters**:</br>
  * *iterable* iterable: Iterable object containing items.
  * *key* iterable: Optional function to fetch values from your iterable object.
  * *reverse* bool: Whether to reverse the sorting.

**Explanation**: This function returns a sorted *list* given an iterable object. Sorting is O(nLogn). *key* parameter takes a function which is then used to extract the elements, helpful when an object has some inner structure. Also has a *reverse* parameter, which is used to do reverse sorting if it is set to *True*.
```Python
my_tuple = (14, 3, 6)
my_set = {34,7,1}
my_string = "ererer"

my_list = [[10,20,56,23,12],[200], [2,7,23]]

def my_fun(a):
  # return element you want iterable to be sorted by
  # here we are returning length of each element(sub-list)
  return len(a)

# sort a string
print(sorted(my_string)) # ['e', 'e', 'e', 'r', 'r', 'r']
# sort a tuple in reverse order
print(sorted(my_tuple, reverse=True)) # [14, 6, 3]
# sort a list by the length of sub-list
print(sorted(my_list, key=my_fun)) # [[200], [2, 7, 23], [10, 20, 56, 23, 12]]
# Notice: "my_fun" is passed and not called, we'll learn about this in the function's section.
```
#### 5. filter(function, iterable) => filter
**Parameters**:</br>
  * *function* function: Your function for filtering.
  * *iterable* iterable: Iterable object containing items.

**Explanation**: This function takes an input function & an iterable and applies that function on every item of that iterable. The return value of the filter's input function has to be boolean. *filter()* returns only if *True* condition is met, if *False* is met nothing is returned, also if no condition is met nothing is returned. *filter()* as the name suggests, is used to filter out non-required values from an iterable object. *filter()* returns a filter object which is iterable and indexing/slicing is not supported.
```Python
## Example: create simple filter object that filter elements which are divisible by 10
def my_func(var):
  # returns True if number is divisible by 10
  if var % 10 == 0:
    # value is returned
    return True 
  # value is not returned   
  return False

my_list = [101,100,501,200]
# create a filter object
my_filter = filter(my_func, my_list)  
print(type(my_filter)) # <class 'filter'>
output = list(my_filter)
# or looping through filter object 
for val in filter(my_func, my_list):
  print(val) # [100, 200]
```
#### 6. map(function, iterable) => map
**Parameters**:</br>
  * *function* function: Your function to apply on items.
  * *iterable* iterable: Iterable object containing items.

**Explanation**: This function takes an input *function* & an iterable object and applies that *function* on every item of that *iterable*. As the name suggests, a function is mapped to each element of an *iterable*. So unlike *filter()*, *map()* returns the direct value returned by our input *function*.
```Python
## Example 1: Return square of each element in a list
my_tuple = (1,2,3,4,5)
def my_func(var):
  # returns square of a number
  return var**2
  
my_mapper = map(my_func, my_tuple)   
print(type(my_mapper)) # <class 'map'>
# call list construtor to executes the map function
output = list(my_mapper) # [1, 4, 9, 16, 25]

# or looping through map object
for val in map(my_func, my_tuple):
  print(val) # [1, 4, 9, 16, 25]
```

## <strong>4. Flow Control</strong>
Flow Control is used for making decisions in programs. This decision making helps turn the output of the program based on the executed conditions. Python supports all the general statements for conditions and loops except *switch*. Let’s check them out.
### <strong>4.1 *if...else* statement</strong>
* *if...else* is the simplest and most general conditional statement that helps turn the program execution based on the conditions provided. An *if...else* can be extended to any length using *elif* and also can be nested as required. Like in other programming languages, the *elif* & *else* part is totally optional.
* Creating a conditional *if...else* statement.
```Python
my_var = 10

# check if my_var is 20, else print something else, notice the indentations
if my_var == 20:
  print('Yes its 20')
else:
  print('Its something else')
```
* *if...else* can be extended with single/multiple *elif*.
```Python
my_var = 30

# same example with different value
if my_var == 20:
  print('Yes its 20')
elif my_var == 30:
  print('Yes its 30')
else:
  print('Its something else')
```
* Nesting *if...else*.
```Python
my_value = 18

# notice the indentation here
if my_value > 10:
  if my_value < 20:
    print("my_value is between 10 and 20")
  else:
    print("my_value is greater than 20")
else:
  print("my_value is smaller than 10")
```
* Ternary Operator to use *if...else* in a single line.
```Python
## Ternary Operator: SYNTAX => [on_true] if [expression] else [on_false] 
my_var = "Yes" if 20%2 == 0 else "No"
# here is 'Yes' is the output when 'if' condition is satisfied, else 'No' is the output
print(my_var) # "Yes"
```
* Truth value testing, check whether an object is Truthy and Falsy. Their values are given below(comma separated).
```Python
# Truthy(True values): non-zero numbers(including negative numbers),True,Non-empty Data-structures/sequences
# Falsy(False values): 0,0.0,0j,None,False,[],{},(),"",range(0)

my_var = 10
my_var1 = None

## Some Examples
# my_var is a non-zero number, which is Truthy, so 'if' will execute
if my_var: 
  print("printed") # printed
# my_var1 is 'None', which is Falsy, so 'if' will not execute  
if my_var1: 
  print("not printed")
# check a empty tuple
if ():
  print("not printed")
# check a non-empty list
if [23,45,34]:
  print("printed")

# By default user-defined object is also Truthy, you can manipulate using '__bool__()' special method
# can also use 'bool()' built-in function to check the Truth value  
print(bool(42)) # True
print(bool("This?")) # True
print(bool("")) # False
print(bool(None)) # False
# Explore the rest!
```
### <strong>4.2 *for* statement</strong>
* Is used for looping purposes, to iterate a certain number of times. Python supports regular to the length looping using the *range* object or there is a more pythonic way of looping. 
```Python
my_list = [10,20,30,40,50]

## regular looping using range object
for i in range(len(my_list)): # [0:4]
  print(my_list[i])

## pythonic loops
for v in my_list:
  print(v)
# or 
for a in [10,20,30,40,50]:
  print(a)   
  
## there's also a 'else' condition, when a "for" loop is not executed
# if no statement has executed inside a "for" loop, this 'else' condition will execute
for v in []:
  print("List has no elements")
else:
  print("So this will execute")
```
### <strong>4.3 *while* statement</strong>
* A *while* loop executes till its given condition is valid and stops execution when it's invalid. *while* loops are more flexible than *for* loops and they can be executed infinitely by setting the condition to *True*, something that is not possible with *for* loops.
```Python
i=0
my_list = [10,20,30,40,50]

# define a while loop, till i is smaller than length of my_list
while i < len(my_list):
  print(my_list[i])
  i+=1 # similar to 'i=i+1', since 'i++' is not supported
  
# infinite looping
while True:
  # do something
  # but remember to stop at some point!
```
### <strong>4.4 *break* and *continue* statements</strong>
* **break**: Use to break from iteration/loop. 
* **continue**: Use to continue to the next iteration in loops.
```Python
i=-1
my_list = [10,20,30,40,50]

while i<len(my_list):
  i+=1
  if i == 0:
    continue
  if i == 4:
    break
  print(my_list[i]) # [20,30,40]
```

## <strong>5. Exception Handling</strong>
As humans while writing code we are prone to make mistakes/errors, causing programs to crash or behave incorrectly. The process of finding and fixing the errors/bugs is called debugging. A programmer usually spends most of their time debugging and it becomes very essential to spot their types and fix them accordingly. As programs get larger in size errors might not be that straightforward to fix/spot and it might take a huge amount of time in debugging. In Python errors are called Exceptions, it is a Pythonic way of saying something exceptional has occurred and it needs to be handled. All exceptions are instances of classes derived from *BaseException* class. User code can *raise* (throw in Java/C++) any built-in exceptions. Users can also subclass built-in exception classes to define their own Exceptions. Although, Python docs recommend subclassing from *Exception* class or its subclass only. Let’s begin this chapter.
### <strong>5.1 Three Types of Errors/Exceptions</strong>
#### 1. Compile Time Errors
* These exceptions are raised due to the syntactical mistake in code and are usually easier to spot and fix. They are raised when the Python Interpreter is compiling a program. A user at this point has to fix the error to be able to execute the program. 
* The interpreter raises a *SyntaxError*/*IndentationError* and also indicates the line causing the error when found. *SyntaxError* is raised due missing colon in compound statements, invalid condition checking in *if..else* statements, missing string quote or bracket operator's termination, empty *import* statement, missing/misspelling keywords, empty function/class definition etc. *IndentationError* is raised when using a invalid indentation in compound statements.    
```Python
## Example 1: wrong indentation in condition
a = 30
if a == 30:
    print("Execute this")
     print("This will raise a Indentation error") # IndentationError

## Example 2: missing closing brackets in list and string  
data = [232,54,65 # SyntaxError
data = "this string is not complete # SyntaxError

## Example 3: missing colon in function 
def myfun() # SyntaxError
    print("my function")
```
#### 2. Runtime Error
* Are raised at runtime due to some illegal invocation/operation on objects. If a program is syntactically correct, the interpreter starts to execute and if an exception is raised it is a runtime error. The program to the part of the runtime error line is executed, the rest of the execution is stopped. Along with the Exception type interpreter also prints appropriate messages on the screen. A user at this point can fix the error or can bypass and continue the rest of the execution by using Exception Handling. </br>
**Some common runtime errors in Python.**
  1. **AttributeError**: Raised when an attribute reference or assignment fails.
  2. **TypeError**: Raised when an operation or function is applied to an object of inappropriate type.
  3. **ValueError**: Raised when an operation or function receives an argument that has the right type but an inappropriate value.
  4. **RecursionError**: Raised when the maximum recursion depth is exceeded.
  5. **IndexError**: Raised when a sequence subscript is out of range.
  6. **KeyError**: Raised when a mapping (dictionary) key is not found in the set of existing keys.
* For more exceptions check the exception hierarchy on [python doc](https://docs.python.org/3/library/exceptions.html#exception-hierarchy). 
* Python also has a [*warnings*](https://docs.python.org/3/library/warnings.html#warnings.warn) module which is a subclass of *Exception* class and unlike all other exceptions they don't terminate the program. They are only meant to warn the user by showing some message.
```Python
## Example 1: indexing error
a = [34,56,32,87]
print(a[6]) # IndexError

## Example 2: dividing by zero
print(34/0) # ZeroDivisionError

## Example 3: accessing unknown attribute 
import math
math.square # AttributeError

## Example 4: raise a warning
import warnings
warnings.warn("Something is not right.")
print("This can execute")
```
#### 3. Logical Error
* Are not raised, but the program output is not an expected behaviour. They usually get difficult to fix as the program grows. They occur when the program logic is incorrect. Common examples such as using the wrong variable/operator, calling the wrong function/method instead, subclassing a wrong class etc.  
* To avoid these errors it is recommended to debug a program normally or use unit testing framework [unittest](https://docs.python.org/3/library/unittest.html#module-unittest) to test the program before integrating it into an application.
```Python
## Example 1: accessing wrong index
my_list = [82,92,38,42,54,23,64,87]
# printing last 3 values
print(my_list[-2:]) # [64, 87]
# here program has no error, but instead of printing 3
# its only printing 2 numbers, because we provided wrong index
# this example is not hard to fix, but in larger programs it consumes a lot of 
# time to find which object/variable/function must have caused the wrong output 
```
### <strong>5.2 Handling the Exceptions</strong>
* Exception handling is a way to handle the Runtime errors. Exception/Error handling helps to continue the program execution while handling the Errors/Exceptions on the way. If you know a particular block of code is likely to cause an error, you can integrate that code inside a *try..except* block and provide a behaviour for the Exception.
* Python has the *try* block to try the suspicious code, *except* (catch in C/C++/Java) block to add behaviour when such error occurs. Optionally Python has an *else* block which executes only if no exception has occurred. Then there is a *finally* block which executes if/not an error occurs.
* Basic exception handling.
```Python
## use traceback built-in module for printing Tracebacks
import traceback

## Example 1: catching specific errors
try:
  a=10
  a = "this"+a
except (TypeError, ZeroDivisionError):    
  print("ZeroDivisionError/TypeError occurred")
  # printing traceback
  traceback.print_exc()
  
## Example 2: catch any exception with 'Exception' class, it is base class of all exceptions
# let's cause stackoverflow/RecursionError in python
# below is a user defined function, we'll get into details in next chapter
def my_fun():
  try:
    my_fun() 
  except Exception as e:
    # printing exception class
    print(e.__class__)  # <class 'RecursionError'>
    # printing the exception
    print(e) # maximum recursion depth exceeded
my_fun()
```
* *finally* and *else* statements.    
```Python
try:
 a = 20/0
 a=20
except Exception as e:
  print(e.__class__) # <class 'ZeroDivisionError'>
  print(e) # division by zero
else:
    print("This optional block executes if no exception was raised.")  
finally:
    print("Finally, its finally, which always executes.")    
```
* Create a user defined *Exception*.
```Python
## Example 1: a simple exception
class MyException(Exception):
  pass

try:
  raise MyException
except MyException:
  print("My Exception was raised") # My Exception was raised

## Example 2: Raise a large value exception in pow()
class NumberTooLargeException(Exception):
  def __init__(self, message):
    self.message = message
  def __str__(self):
      return f"NumberTooLargeException: {self.message}"    

def calculate_pow(num1, num2):
  try:
    if num1 > 100 and num2 > 10:
      raise NumberTooLargeException("base & exp are too large, should be below 100 & 10")
    elif num1 > 100:
        raise NumberTooLargeException("base is too large, should be below 100")  
    elif num2 > 10:
      raise NumberTooLargeException("exp is too large, should be below 10")  
    print(pow(num1, num2))  
  except Exception as e:
    print(e)    

calculate_pow(10, 2) # 100
calculate_pow(100, 2) # 1000
calculate_pow(100, 200) # NumberTooLargeException: exp is too large, should be below 10
calculate_pow(1000, 20) # NumberTooLargeException: base & exp are too large, should be below 100 & 10
```
### <strong>5.3 Raising the exceptions</strong>
* Raising (throw in C++/Java) built-in/User-defined exceptions is done using the *raise* statement. Most commonly raised are *ValueError* and *AttributeError*.
```Python
## Example 1: manually raising a exception
def my_fun(a):
  try:
    if a == 20:
      raise ValueError("I don't want number 20") 
      # or not specifying a specific exception like, "raise Exception('my message')"
    return "Okay"
  except ValueError as v:
    print(v)
my_fun(20) # I don't want number 20
```
### <strong>5.4 **assert** statement</strong>
* *assert* helps in debugging, it is used to check if a certain condition is true, else *raise* an *AssertionError*.
```Python
a = 10

# Example 1: check if a is 10
assert a == 10 # No error raised

# Example 2: check if a is 30
assert a == 30, "Your error message here" # AssertionError
```

## <strong>6. Functions</strong>
In this chapter we'll explore what are functions, the most important part of functional programming. Just as in any other programming languages, functions play an essential part of a program. They contain a block of code under a single name, which can be called out indefinitely without having to re-write the code. In Python, functions are also objects which further opens the gate for more capabilities such as closures and decorators. But before moving onto them, let's start from the basics. 
### <strong>6.1 Function Basics</strong>
* A function is a block of code (group of statements) used to perform some operation/task on some data/variables/sequences. A function may or may not have parameters, it may or may not return something (in Python, *None* is returned by default if the *return* statement is not defined). Functions do not require return type declaration in Python. Functions are the callable objects in Python i.e they can be called with rounded brackets parenthesis.
* **Parameters vs Arguments**: Parameters are the ones which are defined in function definition, arguments are the ones which are passed when a function is called. 
* Functions in Python are first class, which means they are objects too, they can be stored in a variable, they can be passed as an argument to other functions and they can also be returned like a variable.
* Defining and calling functions.  
```Python
# Example 1: Non-parameterized function which returns nothing 
# use the 'def' keyword to define a function followed by its name with rounded brackets 
# function names are recommended to be in snake_casing 

def my_function1():
  # this is function's body
  pass # to ensure the program runs this empty function   
  # Note: if the function is not empty 'pass' is not required at all
  
# Example 2: function with parameter which returns nothing
def my_function2(var1, var2):
  pass
# alternative way is to describe the input/return type hints
# As they are just hints, it does not matter what is send/returned
def my_function2(var1: int, var2: int) -> None: 
  pass
  
# Example 3: function with a default parameter and return statement
def my_function3(var1, var2, var3, return_op=False): 
    # Note: return_op is a default parameter, they should always follow later
    if return_op:
        # did something, now returning something
        return var1 + var2 + var3

# calling a function without a return statement, returns None by default
print(my_function1()) # None

# calling a function and passing the arguments
print(my_function3(30, 20, 10, return_op=True)) # 60
# check if it is a function using the built-in callable() function
print(callable(my_function1)) # True
```
* Functions are objects too.
```Python
## Example: define a function that also takes a function as parameter
def square_or_some_fun(number, some_fun=None):
  if some_fun:
    # if some_fun is a function it can be callable, can check it with callable() 
    output = some_fun(number)
  else:
    output=number**2  
  return output

def cube_num(n):
  return n**3

# assigning a function to a variable/data structure, it is not same as calling a function
# Notice: no rounded brackets on the function
my_var = cube_num 
print(my_var) # <function cube_num at 0x000001C1FDFAF0D0>
# Note: 'my_var' is only referring to 'cube_num()', so both are the same
print(my_var(2)) # 8

# passing a argument to another function
print(square_or_some_fun(2)) # 4 
# passing a function as argument
print(square_or_some_fun(2, my_var)) # 8
# passing a list at some_fun will raise TypeError
print(square_or_some_fun(2, [4,4])) # TypeError: 'list' object is not callable
```
### <strong>6.2 Packing and Unpacking in functions</strong>
1. **Packing**: It is when we pass more than the number of defined variables to a function. Packing allows us to pass an arbitrary amount of arguments, which is useful when we are not sure about the exact number. They should always be the last parameters in a function, else they'll contain all the values and the rest of them will stay empty. Variables can be packed in either a *tuple* (which is generally named as *\*args*) or in a dictionary (generally named as *\*\*kwargs*), these names are not a compulsion but are recommended as common practice.
```Python
## Example 1: packing args into a tuple
# Notice: the * operator before args variable
def sum_nums(a,b, *args):
  total = a+b
  if args:
    print(type(args)) # <class 'tuple'>
    # rest of the values are inside args
    print(args) # (4, 4, 2, 1, 1, 4)
    for n in args:
      total+=n

  return total

# passing only two arguments, so args stays empty
sum_nums(2,3) # 5   
# passing more than two arguments, now all values after 3 go into args 
sum_nums(2,3,4,4,2,1,1,4) # 28

## Example 2: packing kwargs into a dictionary
# Notice: the ** operator before kwargs variable
def sum_nums2(x,y,**kwargs):
  total = x+y
  if kwargs:  
    print(type(kwargs)) # <class 'dict'>
    # rest of the values are inside kwargs
    print(kwargs) # {'a': 2, 'b': 4, 'd': 4, 'any_name': 5, 'my_var': 8}
    # total the values
    for v in kwargs.values():
      total+=v

  return total
  
# passing only 2 arguments, so kwargs stays empty
print(sum_nums2(2,3)) # 5   
# passing more than 2 arguments, now all values after 3 go into kwargs
# Notice: arguments should have some unique name, they will be the keys in kwargs dictionary
print(sum_nums2(2, 3, a=2, b=4, d=4, any_name=5, my_var=8)) # 28
# try using both args & kwargs in a function, print and check their values
```
2. **Unpacking**: It is when a *list/tuple/dict* is passed, which then unpacks or gets extracted as function arguments. Now passing a *tuple/list* can be done with '\*' operator followed by sequence's name and passing a dictionary requires '\*\*' operator followed by sequence's name.
```Python
def my_fun1(a,b,c,d):
  return a+b+c+d

my_list = [1,2,3,4]
my_dict = {'a':1,'d':4,'b':2,'c':3}

## Example 1: unpacking from a list/tuple, list here, notice the * operator
print(my_fun1(*my_list)) # 10

## Example 2: unpacking from a dictionary, notice the ** operator
print(my_fun1(**my_dict)) # 10 

# same goes for built-in functions too, "print()" function unpacks the list values
print(*my_list) # 1,2,3,4
```
### <strong>6.3 Recursion</strong>
* Recursion is when a function calls itself. It is a powerful tool that works on a particular set of problems where a problem can be divided into simple repetitive chunks. 
* Recursion uses system stack to maintain the memory required for the recursive calls, this usually leads to higher memory usage compared to iteration.    
* Recursion requires to handle the *StackOverFlow*, the complexion in debugging and also it can sometimes be hard to formulate a recursive solution.
* There are certain advantages such as reduction in size of code when an iterative solution is lengthy/complex, there are situations where recursion is an easier/better solution. Also if implemented correctly using Dynamic Programming or dependent on a problem it reduces the time complexity and also some memory usage.
* To identify a recursion problem, one has to identify the smaller repetitive parts of a solution. A recursive solution usually forms a decision tree-like structure where the branches are sub-problems. After identifying the sub-problems one has to identify the base case, which is the condition where a recursion program stops itself. This is very important or else the program will run indefinitely causing a *StackOverFlow* error. Finally the sub-problem solution with the base case is sequenced correctly to form a recursive solution.  
```Python
## Example 1: Sum of n given number
# using iteration
def iter_sum(n):
    total = 0
    for i in range(n+1):
        total += i
    return total
    
# using recursion    
def recur_sum(n):
    # 'n == 0' is the base case here
    if n == 0:
        return 0
    else:
        return n + recur_sum(n-1)   
        
print(iter_sum(5)) # 15
print(recur_sum(5)) # 15
# here iterative solution seems easy/understandable, but the recursive solution is much more concise

## stack calls over recursion
'''
# In our recursion function recursive calls are made till n is 0, in this example recursion is bottom-up, 
# so we'll begin from the last line. Note: '->' is the output from that call
5 + recur_sum(4) -> 10 = 15 # finally 15 is the result, which is returned to the original caller
4 + recur_sum(3) -> 6 = 10 # same thing here
3 + recur_sum(2) -> 3 = 6 # similarly the result 3 is returned here from previous call and added with 3
2 + recur_sum(1) -> 1 = 3 # the result 1 is returned here from previous call and added with 2
1 + recur_sum(0) -> 0 = 1 # this is the last call, as the base case is hit, now the return calls are made
'''
```
* In recursion, there are some problems that require re-computation of repetitive calculations. We can save some computation by storing the previous results in the memory and looking up from it when it is required to compute again. This process is known as Memoization (or caching).
* Now it would be memory inefficient to store all the previous results of a function with longer runtimes. So we can use techniques such as using FIFO (remove the oldest first), LFU (remove the least frequently used first) or LRU (remove the least recently used first) etc, to manage the number of results to store in the memory. 
* Python provides support for LRU using the *functools* module (which is included in the standard library). Using the *lru_cache* function, a desired function can be optimized to use LRU cache for storing its repetitive calculations. So whenever a function is run *lru_cache* will check for cached results for the inputs, if it exists the output will be returned instantly else the function will be run and the output will be cached for next time. It maintains a dictionary with keys as inputs & values as outputs.
* As *lru_cache* is a *decorator* function, we'll see an example of it in the *decorator*'s section, for now let's use Memoization without memory management. 
```Python
## Example: find factorial of n numbers using recursion and memoization
# for storing previous calculation/result we can use a dictionary (memo here)
def factorial(input_value, cur_num=2, memo = {1:1}):
    # base case, we return 'memo' to the caller
    if cur_num > input_value:
      return memo

    # calculate factorial 
    memo[cur_num] = cur_num * memo[cur_num - 1]
    # recursively call the next number, finally return 'memo' from the base case
    return factorial(input_value, cur_num+1, memo)

print(factorial(5)) # {1: 1, 2: 2, 3: 6, 4: 24, 5: 120}

## stack calls over recursion
'''
# In this recursion function recursive calls are made till 'cur_num' > 'input_value',
# as soon as it is we return to the caller and return output 'memo'. Below is the calculated factorial line. 
# This is a top-down recursive call so we'll begin from top. Note: '->' is the value from the memo.
# 1. we multiply 2 with 1 which came from memo[1], later store it at memo[2]
memo[2] = 2 * memo[2 - 1] -> 1 
# 2. we multiply 3 with 2 which came from memo[2] and store result at memo[3]
memo[3] = 3 * memo[3 - 1] -> 2 
# 3. similarly we multiply with memo[3] and store at memo[4]
memo[4] = 4 * memo[4 - 1] -> 6  
# 4. lastly we store the final calculation
memo[5] = 5 * memo[5 - 1] -> 24 
# 5. Our base case hits at this call, from there we return 'memo' which returns to the last line of the function
# and then return 'memo' from there to the caller from outside of the function. 
'''
```
* Recursion can be overwhelming even for intermediate programmers, recursion requires practice on well... recursion. [Here](https://web.stanford.edu/class/cs9/lectures/06/Recursion%20Problems.pdf) is a list of some recursive problems. If you are not that familiar with recursion [here](https://www.youtube.com/watch?v=ngCos392W4w) is a nice video explanation.
### <strong>6.4 Anonymous functions</strong>
* Is a function that is defined without a name (without using *def* keyword in python). Anonymous function can be created using the *lambda* keyword, it is a single line function. This function helps in reducing the line of code required for defining a short function. 
```Python
## Example 1: return sum of 2 numbers 
# syntax => lambda arguments : expression
my_function = lambda a,b: a+b  
# Notice: 'a+b' is also the return statement without using 'return' keyword 

## calling the function
print(my_function(1,1)) # 2 
```
### <strong>6.4 *pass* statement</strong>
* It is to declare a function/method/class with an empty body without raising an error, so that we can come back later to implement the function.  
```Python
# Example 1: empty function body
def my_fun():
  pass
```
### <strong>6.5 global and nonlocal statements</strong>
1. **global**: Is used to modify a variable with global scope from inside a function.
```Python
# defining 3 variables in global scope
my_var1, my_var2, my_var3 = 10, 20, 30

def some_fun():
  # declaring my_var1 as global inside a local scope, so now my_var1 can be modified for global scope
  global my_var1
  
  # accessing a global scope variable, works fine
  print(my_var3) # 30
  # accessing a global scope variable defined as global, works fine
  print(my_var1) # 10
  # same thing with my_var2 doesn't work (comment below line to execute the program further) 
  print(my_var2) # UnboundLocalError
  # Its because Python tries to figure out the scope of a variable by watching if it has some assignment in this scope
  # if it does Python thinks it is a local variable, which we cannot access before assignment right?
  # in below lines my_var2 has assignment, so it is considered as local variable,
  # even if same named global variable exists
  # if the assignment is removed, my_var2 it will be considered global and it can be access normally

  my_var1 = 30 # modifying for global scope
  my_var2 = 40 # modifying only for local scope

some_fun()
print(my_var1, my_var2) # 30, 20
# Notice: my_var1 is now changed but my_var2 is not
```
2. **nonlocal**: Is used to modify a variable of local scope from inside a nested function.
```Python
def some_fun():
  # defining my_var1 and my_var2 in local scope 
  my_var1 = 10
  my_var2 = 20
  
  def some_nested_fun():
    # declaring my_var2 as nonlocal, so now it can be modified for some_fun() scope too
    nonlocal my_var2 
    my_var1 = 30 # modifying for some_nested_fun() scope
    my_var2 = 40 # modifying for some_fun() scope
    print(my_var1, my_var2) # 30, 40

  some_nested_fun()  
  # here my_var1 is not modified but my_var2 is
  print(my_var1, my_var2) # 10, 40    

some_fun()
```
### <strong>6.6 Closures</strong>
* They are the nested function objects that remember the data from the local scope. It is a nested function (a function inside a function) that has access to variables called "free variables" from the local scope even if the function is removed from the current namespace.   
* These "free variables" are attached to the closure function object once it is returned by the enclosing function, so even if the enclosing function is out of the scope or is removed the variables still exist. 
* Closures are an easy alternative to classes with few methods in them and they also provide some level of data hiding in functions.  
* Creating a simple closure function.
```Python
# this is the enclosing/outer function
def my_enclosing(para1, para2):
    # this is the closure function
    def inner():
        print(para1, para2)
 
    # Note: the inner function is returned not called
    return inner

# initializing the closure function 
my_closure = my_enclosing(10, 20)
# calling my_closure, which is just referring to "inner()" as "my_enclosing()" has returned it
my_closure() # 10, 20

# here para1 & para2 are free variables attached to "inner()" function
# so even if "my_enclosing()" is removed, "inner()" can still access them
del my_enclosing
# now calling "my_enclosing()" should raise NameError, 
# Note: comment the following line to execute the program further
my_enclosing() # NameError

# but "my_closure()" should still have access to para1 & para2
my_closure() # 10 20
```
* Another example of closure.
```Python
## Example: create a callable that prints maximum from all previous values
## Creating a callable using a class, 
# Note: we'll learn more about classes in next chapter, you can comeback to this one later

class Make_maxer:
    def __init__(self):
        self.my_values = {10, 50, 80}
        self.all_time_max = self.max(my_values)

    def __call__(self, new_value):
        self.my_values.add(new_value)
        current_max = max(self.my_values)
        if current_max > self.all_time_max:
            print(f"Found new max: {current_max}")
            self.all_time_max = current_max

# creating a instance of Make_maxer
my_maxer = Make_maxer()
my_maxer(20)
my_maxer(95) # Found new max: 95


## Now creating the same with closures
def make_maxer():
    # a closure can access this variables
    my_values = {10, 50, 80}
    all_time_max = max(my_values)

    def maxer(new_value):
        # Note: all_time_max is nonlocal because we have its assignment below
        nonlocal all_time_max
        my_values.add(new_value)
        current_max = max(my_values)
        if current_max > all_time_max:
            print(f"Found new max: {current_max}")
            all_time_max = current_max

    return maxer

# creating closure object
my_maxer = make_maxer()
# Note: "my_maxer" is just referring to "maxer()", checking its name
print(my_maxer.__name__) # maxer

# adding some values to maxer
my_maxer(42)
my_maxer(105) # Found new max: 105

## the free variable names can be found in "__code__" variable of a function
print(my_maxer.__code__.co_freevars) # ('all_time_max', 'my_values')
# their values are attached to the __closure__ variable
closure_values = my_maxer.__closure__
print(closure_values[0].cell_contents, closure_values[1].cell_contents) # 105 {105, 10, 42, 80, 50, 20}
```
### <strong>6.7 Decorators</strong>
* They are used to wrap another function around to extend/replace its functionality. It is simply running a function inside another function, like a nested function. This allows extending the wrapped function's behaviour without actually modifying the function itself. This functionality is utilized using functions being first class in Python. A function can be decorated using '@' prefix, which is just a "Syntactic sugar".
* In Python, functions and classes (we'll see an example in next Chapter) can be decorated. The wrapper/decorator function has an inner function that can choose to call or not call the wrapped/decorated function, which is replacing the decorated function entirely. Finally the decorators can also have their own parameters.
* Creating a simple decorator.
```Python
# this is a decorator function
def my_decorator(func):
    # decorator function has a inner function which calls the decorated function
    def inner():  
        print("decorator did something")
        # calling decorated function
        output = func()
        print(output)
    return inner 

# decorated function, decorate with '@' prefix
@my_decorator
def my_decorated():
  print("decorated did something")
  return 42
  
# calling the decorated function
my_decorated()

# the above lines without the '@' prefix are similar to this
my_decorator(my_decorated) 
```
* A decorated function with parameters.
```Python
## Example: create a decorator to extend functionality of other function
# First defined the decorator function with parameter as decorated function 
def my_decorator(deco_func):
  # Second define the inner function
  # Note: inner function can do something before/after calling our wrapped function
  def my_inner(deco_func_para1, deco_func_para2): 
    # Notice: the parameters of a decorated should be the parameters of inner function
    # because this function is going to be returned and we're going to call it
    # do something of inner function say printing
    print(f"Product of two numbers is {deco_func_para1 * deco_func_para2}")

    # now calling our decorated function, passing the required arguments
    output = deco_func(deco_func_para1, deco_func_para2) 
    return output

  # Finally return the inner function
  return my_inner 

def my_fun(a,b):
  print(f"Sum of two numbers is {a+b}")

# calling my_fun gets sum of two numbers
my_fun(10, 20) # Sum of two numbers is 30
# to extend my_fun's functionality without changing its previous code

# pass the my_fun as deco_func to my_decorator
my_decorated_fun = my_decorator(my_fun) 

# done, my_decorated_fun can now do both product as well as sum
my_decorated_fun(10, 20) # Product of two numbers is 200 # Sum of two numbers is 30

## now doing the same using decorators
@my_decorator
def my_fun(a,b):
  print(f"Sum of two numbers is {a+b}")

# now calling 'my_fun()' will automatically call/invoke my_decorator()
my_fun(10,20) # Product of two numbers is 200 # Sum of two numbers is 30
```
* Replacing the functionality of a decorated function.
```Python
## Example: create a decorator function that replaces the decorated function 
def my_adder(func):
  def adder(para1, para2):
    return para1 + para2
  return adder

# decorating subtr and mutpl
@my_adder
def subtr(p1, p2):
  return p1 - p2

@my_adder
def mutpl(p1, p2):
  return p1 * p2

# now calling subtr and mutpl
print(subtr(20, 10)) # 30
print(mutpl(2, 5)) # 7
# this is because we didn't call the 'func'/decorated function inside 'my_adder'
# so if a function is decorated with 'my_adder' it is going to be replace by 'adder' and 'func' won't be called
```
* A decorator function with parameters.
```Python
## Example: create a function that prints/returns the output
# this function is called decorator factory, because it returns a decorator
def result_fetcher(print_op=True):
    def resulter(func): # this is our decorator function
        def inner(para1, para2):
            output = func(para1, para2)
            if print_op:
                print(f"Output is {output}")
            else:
                return output
        return inner
    return resulter

# passing the parameters in result_fetcher decorator
@result_fetcher(print_op=False)
def addr(p1, p2):
    return p1 + p2

@result_fetcher(print_op=True)
def multpl(p1, p2):
    return p1 * p2

# calling addr and multpl
print(addr(10, 20)) # 30     
multpl(10, 20) # Output is 200     
```
* The *lru_cache* decorator to manage memory.
```Python
## lru_cache basics
from functools import lru_cache
# simply add a decorator to computational function 
@lru_cache
def power_of(num1, num2):
  print('power_of was called')
  return pow(num1, num2)

# call the function and lru_cache will store the result
v = power_of(342, 388)  # power_of was called
# so next time for the same inputs results will be returned directly
v = power_of(342, 388)  

# set the size of lru_cache by passing a parameter
# if the memory gets full, the least recently used ones will be removed
@lru_cache(256)
def power_of(num1, num2):
  print('power_of was called')
  return pow(num1, num2)

# check cache info like times hit/used , missed and current remaining size
print(fib.cache_info()) # CacheInfo(hits=8, misses=11, maxsize=128, currsize=11)
# clear the cache 
fib.cache_clear()
```
* Another example of *lru_cache*.
```Python
## Checking function call counts of fibonacci function with and without lru_cache
# Note: cache is similar to lru_cache, only without the size limit, good for smaller programs
from functools import cache
# checking without caching
call_counter = 0
def fib(num):
    global call_counter
    call_counter += 1
    if num < 2:
        return num
    else:
        return fib(num-1) + fib(num-2)

fib(10)
print(call_counter) # 177

# checking with caching
call_counter = 0
@cache
def fib(num):
    global call_counter
    call_counter += 1
    if num < 2:
        return num
    else:
        return fib(num-1) + fib(num-2)

fib(10)
print(call_counter) # 11
# 177 vs 11, the difference speaks everything
```
### <strong>6.8 Generators and Coroutines</strong>
* Generators are used to generate streams of data. Instead of loading all the data at once (example like *list* object does) they "lazy load" the data, which means they return a value only when the *next()* function is called upon them. The *next()* function is used to fetch the next element from the *generator* object.
* Generators are *iterator*s (we'll learn more about them in next Chapter) objects, so they can be iterated using loops. A generator object is created using a function with one or more *yield* statements in it. *yield* allows generators to be iterated with/without defining loops in their function.
* *yield* helps to save the state (or maintains current index of iteration) of a *generator* object, this allows generators to be interrupted and resumed throughout the program's execution. Once a *generator*'s data is exhausted it stops returning values and raises *StopIteration*, at this point it needs to be created again. 
* For longer iteration (larger/infinite length of data handling) generators are preferred because they are memory efficient, in a sense they can be utilized to generate/load data when required. This helps in avoiding the machine to run out of memory. Lastly, generators can also be created using comprehensions, using the rounded brackets.
* Creating a simple generator.
```Python
## Example 1: create a generator function which returns a square of each values
def square_generator(*args):
  for a in args:
    yield a**2
    # Notice: using 'yield' instead of 'return' makes this function "lazy" and hence a generator

generator = square_generator(2,3,4)
# fetch the value using the next() function
print(next(generator)) # 4
# whenever a value is returned the generator is paused at the 'yield' statement
# now next value is called the 'for' loop will be resumed and so on
print(next(generator)) # 9
print(next(generator)) # 16
# now once exhausted, StopIteration is raised
print(next(generator)) # StopIteration


## Creating the above generator using comprehensions
generator = (a**2 for a in [2,3,4,5])
print(type(generator)) # <class 'generator'>
print(hasattr(generator, '__next__')) # True
# fetch the first value
print(next(generator)) # 4

# now try iterating a generator
for a in generator:
  print(a) # [9, 16, 25]
  # Notice: generator resumed after first value

# creating a new generator
generator = (x**2 for x in [2,3,4,5])
for v in generator:
  print(v) # [4, 9, 16, 25]
  # Notice: we didn't call "next()" first, so all values are iterated properly
# however now it is exhausted, so will raise error 
print(next(generator)) # StopIteration
```
* The pause and play of generators.
```Python
def some_generator():
  print('Hello 1')
  yield 10
  print('Hello 2')
  yield 20
  print('Hello 3')
  yield 30
  
# creating a generator  
my_generator = some_generator()
# calling the next() on generator will execute till first 'yield' statement
print(next(my_generator)) # Hello 1 # 10
# now calling the next() again will resume from the execute 'yield 10' till next 'yield' statement which is 'yield 20'
print(next(my_generator)) # Hello 2 # 20
# so we get the returned value
# this is how the generator saves its state at yield statement, allowing the object to be interrupted and resumed anytime
```
* Iterating generators that don't have loops in them.
```Python
def my_generator():
  yield 1
  yield 2
  yield 3

generator = my_generator()
## now iterating the generator  
for a in generator:
  print(a) # [1,2,3]
# behind the scenes the 'for' loop is actually calling the 'next()' function on each iteration, 
# which is why in our square_generator example the 'for' loop was able to continue from the interruption/breakpoint 

## yield from: to yield from a sequence or even a generator (it'll be called a subgenerator) 
# above function can be coded as following
def my_generator():
  yield from [1,2,3]

for a in my_generator():
  print(a) # [1,2,3]
```
* Coroutines are similar to generators, but instead of generating data they are used for consuming the data. Similar to a *generator*, a coroutine also has *yield* in its function. The difference is that the *yield* is assigned to a variable, it is used to pass some value into the function. So a generator becomes coroutine if its *yield* is assigned to a variable.
* Coroutines can also maintain their state just like a *generator*, allowing to a constant flow of input data. Apart from *send()*, there are more two methods named *close()* and *throw()* associated with the *generator* objects. *close()* is used to terminate the *generator*'s/*coroutine*'s execution and *throw()* is used to raise an *Exception* into a *generator* function. 
* Coroutines are easy to define and can be combined with other generators/coroutines, this helps in building pipelines and in other asynchronous workflows.   
* Creating a coroutine.
```Python
def my_coroutine():
  print('Coroutine is activated..')
  val = yield   
  print(f"{val} received")

# Note: a coroutine is activated only after reaching the first yield statement
# to activate you need to call next() on its object
coroutine = my_coroutine()
next(coroutine)
# now you can start sending values
# Note: if you call next() at this point None will be send
coroutine.send(42) # 42 received
# now coroutine has started looking for next yield, if it doesn't find any the coroutine terminates raising StopIteration

# to stop this from happening, create a infinite loop and call '.close()' method when done 
def my_coroutine():
  print('Coroutine is activated..')
  while True:
    val = yield   
    print(f"{val} received")

coroutine = my_coroutine()
next(coroutine)
coroutine.send(42) # 42 received
coroutine.send(34) # 34 received
coroutine.close()

## Example: percent calculator using coroutine
# Note: when pairing yield with a expression it is recommended to use parentheses like this (yield)
def percent_coroutine(total):
  while True:
    result = (yield) / total * 100  
    # limiting float number to 3 decimal points using :.3
    print(f"Your Percentage are {result:.3}")

percent_calc = percent_coroutine(420)  
next(percent_calc)
percent_calc.send(250) # Your Percentage are 59.5
percent_calc.send(356) # Your Percentage are 84.8
percent_calc.send(155) # Your Percentage are 36.9
percent_calc.close()
```
* Using generators and coroutines together.
```Python
## Example: Create a fibonacci generator and then a coroutine to filter even numbers in a list and finally return it 
def fib_gen(limit=10):
  """
  This is a generator function that generates fibonacci numbers.
  """
  x, y = 0, 1
  for _ in range(limit):
      x, y = y, x+y
      yield x
  # at last send None to coroutine, to signal for stopping
  yield None

def co_fetcher():
  """
  This is a coroutine function that takes numbers and stores the even numbers in a list and finally returns the list.
  """
  even_fibs = []
  while True:
    num = yield
    # stopping condition for coroutine
    if not num:
      break
    if num % 2 == 0:
      even_fibs.append(num)
  return even_fibs

# create a generator
fib = fib_gen()
# create and activate the coroutine 
fetcher = co_fetcher()
next(fetcher)

# Note: As the coroutine is terminated it raises StopIteration, 
# so the returned value should inside the "value" attribute of the exception
while True:
  try:
      # send values generated from generator to coroutine
      fetcher.send(next(fib))
  except StopIteration as e:
    print(f"Your even fibonacci are {e.value}") # Your even fibonacci are [2, 8, 34]
    # make sure to stop this loop too
    break
```
### <strong>6.9 Functional Programming</strong>
* Python like C++ is a multi-paradigm and supports functional programming. In functional programming, input flow through various functions and outputs are generated based on their behaviour. As functions don't have an internal state like objects, they can't produce different outputs given the same inputs (as state/data cannot be saved in a function), they are just meant to perform some operation on some data and return the output. 
* A function is pure (without any side effect) if it does not rely on any mutable types, global variables or some objects' attributes i.e relying solely on its input arguments and generating the output only based on them. This adds advantage in parallel programming, testing, making programs more modular and requiring less debugging overall.
* When designing systems, depending on the scenario specific paradigm approaches are preferred, today's systems are usually built with multi-paradigm in mind with say some computational parts written with functional programming & GUI parts designed with OOP.

## <strong>7. Classes and Objects</strong>
In this chapter we're going to take a look at the most fundamental part of Python, objects. Earlier we learned about function, now it's time for classes, which allows us to create more sophisticated objects. Later we'll check out what are methods in classes and their types. Then we'll check out objects and lastly some helpful built-in Python objects. Let's begin. 
### <strong>7.1 Classes</strong>
* **Class**: Is a blueprint/template of/for an object. It defines what the object holds (which variables/data types), what methods/operations that can be performed on that object. 
* In Python, classes are also objects. Similar to functions, they can be assigned, passed or returned. Every class in Python is created using the *type()* function, this function has 2 signatures, one that we saw in Chapter 2 that returns *bool* output given an *object* as input, another one is used to create classes. The *type()* function is actually a metaclass. Metaclasses are used to create/modify class objects. They are a complicated concept and are very rarely required to be created, so we'll not be covering them here. I found a very clear explanation on [stackoverflow](https://stackoverflow.com/questions/100003/what-are-metaclasses-in-python), which is worth checking out if you're further interested in metaclasses.
* **Instance**: Is an object of a class, it is created using the class. This instance/object is then used to perform operations/tasks that the class is intended to. An instance has its own state and it is also mutable, so modifying some variables will reflect changes for that particular instance.
* **Constructor**: Is a function that is called when the class's object is instantiated/created, a class may or may not have a constructor. A default constructor does not have parameters and a parameterized constructor does have parameters.
* **Methods**: Functions inside the class are called methods.
* **self**: It resembles an instance of class inside the class methods. Similar to Java/Javascript's *this* keyword, it is used to access variables/methods of that instance. But in Python, a class method should have a *self* object as the first parameter inside their definition. Although an argument is not required to be passed when calling such a method. When an instance calls a method, the calling instance gets passed automatically by Python as a *self* object to that method, explained more below. Also note that *self* is not a keyword, you can use any other name instead but it is highly recommended to use *self* as a common practice for code readability.
```Python
## Classes
# defining a class using the 'class' keyword followed by its name, 
# class names are recommended to be in CapitalCamelCasing 
# python defines a empty constructor automatically in background, if it is not provided
class MyClass: 
  # instance methods here
  def myfunction(self):
    # Notice: the self parameter in myfunction
    # function body
    pass

# class with default constructor
class MyClass1:
  # default constructor, a constructor is defined with the special method __init__
  def __init__(self):
    # instance variables are created with 'self.' prefix
    self.my_var = 30
    self.other_var = 10
    
  # defining instance methods
  def my_fun1(self):
    # access instance variables using the 'self' object
    print(self.my_var) 
    # change/define new variables inside any instance method using 'self' object
    self.my_var = 42 
    self.my_var1 = 92

  def return_my_var(self):
    return self.my_var 
 
# defining class with a parameterized constructor
class MyClass2:
  # passing parameters (para1, para2) and saving them as instance variables
  def __init__(self, para1, para2, para3=None): 
    self.para1 = para1
    self.para2 = para2

  # here var1 is a method parameter
  def my_func(self, var1): 
    return var1 + max(self.para1, self.para2)


## Instances
# create a instance of MyClass1
some_instance = MyClass1()
# use '.' dot operator to access methods/variables of an object
print(some_instance.other_var) # 10
# if attribute is not found, AttributeError is returned
print(some_instance.other_var_42) # AttributeError
# call methods with the rounded brackets
print(some_instance.return_my_var()) # 30

# create a new instance, pass arguments for parameterized constructor
my_instance = MyClass2(22,35) 
# calling my_func() of my_instance
print(my_instance.my_func(40)) # 75

# in python the invocation of the instance method is operated via the class calling a method 
# by passing the instance as an argument, so this is same as above instance calling method
print(MyClass2.my_func(my_instance, 40)) # 75
# the 'self' resembles the instance object, which is 'my_instance' here
```
* Classes are objects too.
```Python
def my_fun(some_var, some_class=None):
    print("Values is %d"% some_var)
    # create a instance of some_class        
    instance = some_class()
    print(instance.my_var)
    print(type(instance))

# a single liner class
class MyClass: my_var = 42

# pass a class to variable
new_class = MyClass
# new_class is now pointing to MyClass
print(new_class.my_var) # 42

# passing class a argument
my_fun(24, MyClass) # Values is 24 # 42 # <class '__main__.MyClass'>

# returning a class
def some_fun():
  class MyClass: my_var = 42
  return MyClass

# some_fun() returns a class
SomeClass = some_fun()
print(SomeClass.my_var) # 42
```
* Dynamically creating classes using *type()* function. 
```Python
# Syntax: type(Class_name, bases, attrs)
# "bases" is a tuple that should contain parent classes
# "attrs" is a dictionary that should contain attributes
# creating a class without parameters
MyClass = type("MyClass", (), {})
my_instance = MyClass()
print(type(my_instance)) # <class '__main__.MyClass'>

# add attributes to a class
MyClass = type("MyClass", (), {"my_var":42})
my_instance = MyClass()
print(my_instance.my_var) # 42

# add methods to class, add self as first parameter
# define methods and pass them just like attributes
def my_fun(self):
    return self.a
def __init__(self): 
    self.a = 34
    print('constructor was called')

MyClass = type("MyClass", (), {"my_var":42, "my_fun":my_fun, "__init__":__init__})
my_instance = MyClass() # constructor was called
print(my_instance.my_fun()) # 34

# Every class is created using a class of classes which is ...
print(MyClass.__class__.__class__) # <class 'type'>
print(float().__class__.__class__) # <class 'type'>
print(range(42).__class__.__class__) # <class 'type'>
```
* Class decorator example.
```Python
## Example: create a decorator class that limits the number of function calls and also maintains unique values
import math
# a class decorator should have two methods __init__() with the function to be decorated as parameter 
# and __call__() for decorator being callable, with parameters of a decorated function
class CallLimiter:
    def __init__(self, func):
        self.func = func
        self.call_count = 0

    def __call__(self, *args):
        # to maintain unique values, add items to a set
        args = set(args)
        # checking limit of numbers
        if self.call_count >= 2:
            raise ValueError("Maximum calling limit reached")
        self.call_count += 1
        result = self.func(*args)
        print("Your total is %d"% result)

@CallLimiter
def sum_of_numbers(*args):
    return sum(args)

@CallLimiter
def sum_of_sqrt(*args):
    return sum([math.sqrt(a) for a in args])

sum_of_numbers(34,21,65,32) # Your total is 152
sum_of_numbers(34,34,34,8) # Your total is 42
sum_of_numbers(5,34,21,65) # ValueError: Maximum limit reached

sum_of_sqrt(54,20,45,38) # Your total is 24
sum_of_sqrt(54,89,12,90,12,62) # Your total is 37
sum_of_sqrt(54,20,45,38) # ValueError: Maximum limit reached
```
#### 7.1.1 Three Types of methods in classes
Python comes with three built-in decorators named *classmethod*, *staticmethod* and *property*. We'll check the first two here and the later one in the next chapter.
1. **Class**: Class methods are bound to classes and not to instances. These methods have access to class state, they can read class variables/methods and modify class variables. Unlike instance only one copy is created, so every instance/class refers to this copy. Class methods can be accessed by both instances and classes. Unlike in Java, there is no *static* keyword, they are defined using *classmethod* as decoration (using *@classmethod* prefix). These methods should have class as the first parameter, which can be of any name, *CLS* is preferred. This parameter further can be used to access other class variables/methods inside these methods. 
```Python
class MyClass: 
  # class variables: they are outside of methods 
  my_var1 = 20
  my_var2 = 10
  
  # defining a class method, use the '@classmethod' decorator
  @classmethod
  def fun1(CLS):
    # Notice: the CLS parameter
    print("This is class method")
    # access class variable using CLS parameter
    print(CLS.my_var1)

## access using class
print(MyClass.my_var1) # can access
MyClass.fun1() # can access

# modify the class variable, will reflect to class and its instances
MyClass.my_var1 = 42

## access using instance    
my_instance = MyClass()
print(my_instance.my_var1) # can access
my_instance.fun1() # can access

## optionally creating class variables using the class
MyClass.new_var = 43
print(MyClass.new_var) # 43
```
2. **Instance**: Instance methods are bound to instances. They have access to both instance & class state, they can read class & instance variables/methods and also can modify class & instance variables. These methods can only be accessed by instance and not by class. A normal function inside a class is an instance method, these methods should have *self* as first parameter, which is used to access the instance's/class's variables/methods inside these methods.
```Python
class MyClass: 
  my_var1 = 10
  # instance methods
  def __init__(self):
    # define instance variables inside the constructor method with 'self.' prefix
    self.other_var1 = 30 
    self.other_var2 = 40
    # can also access class variable
    print(self.my_var1)

  # another instance method   
  def fun1(self):
    # Notice: the self parameter
    print("This is a instance method")

## access using class
print(MyClass.my_var1) # can access
print(MyClass.other_var1) # can't access
MyClass.fun1() # can't access

## access using instance    
my_instance = MyClass()
print(my_instance.other_var1) # can access
my_instance.fun1() # can access

## optionally creating instance variables using the instance
my_instance.new_var = 42
print(my_instance.new_var) # 42
```
3. **Static**: Static methods are also bound to classes. But they don't have access to instance/class state. They can't read/modify any variables beside their local scope. These methods exist because that function has to belong to the class like a independent function but inside a class. They are defined using *staticmethod* as decoration (using *@staticmethod* prefix), these methods are not required to pass class as first argument. These methods can also be subclassed.
```Python
class MyClass: 
  # defining a class method, use the '@staticmethod' decorator
  @staticmethod
  def fun3():
    # can't access instance/class variable/methods, but can do its own task
    print("This is static method")
 
## access using class    
MyClass.fun3() # can access
 
## access using instance
my_instance = MyClass()
my_instance.fun3() # can access
```
* Some functions for objects.
```Python
class DummyClass:
  def some_method():
    pass

my_instance = DummyClass()

# check if a object has some attribute
print(hasattr(my_instance, 'x')) # False
# get value of object's attribute, similar to accessing with '.' operator 
# though one benefit is if attribute is not found, the default value is returned
print(getattr(my_instance, 'x', 42)) # 42
# set value of object's attribute, similar to assigning with '=' operator 
# though one benefit is if attribute is not found, it creates one and assigns value to it 
setattr(my_instance, 'my_new_var', 'Hello')
print(my_instance.my_new_var) # Hello
# delete object's attribute returns nothing, raises AttributeError if not found
delattr(my_instance, 'my_new_var')
print(my_instance.my_new_var) # AttributeError
```
#### 7.1.2 Special methods
* These methods begin & end with double underscore '\_\_' and are called magic/special/dunder methods in Python. These methods are used to enrich your object with more features. These are called "magic" methods because these methods are invoked indirectly by the Python Interpreter and we do not need to invoke them.
* These methods are used to enable operator overloading, overriding built-in functions, accessing attributes etc. So using them in your custom class will enable more functionality but be careful to use them when it makes sense and document (add docstrings) their usage where required to avoid break in some functionality. Also it is a good practice to not invent new special methods to avoid name collisions between the built-ins.  
* Check this [list](http://docs.python.org/3/reference/datamodel.html#special-method-names) of all special methods in Python.
```Python
## MyClass defines '__str__', '__len__' and '__getitem__' magic methods 
# to add functionality behaviour to its instance 
class MyClass:
  def __init__(self, a, b, c, d):
    self.some_id = a
    self.some_name = b
    self.some_age = c
    self.some_values = d
  # define '__str__' to enable print functionality
  def __str__(self):
    """Add doc string to describe their behaviour"""
    return f"id: {self.some_id}, name: {self.some_name}, age: {self.some_age}"
  # define '__len__' to enable showing length of MyClass using the len() function  
  def __len__(self):
    """Length of some_values"""
    return len(self.some_values)    
  # define '__getitem__' for enabling iteration/indexing/slicing of items 
  def __getitem__(self, index):
    """Iterate through some_values""" 
    return self.some_values[index]
  # define '__call__' for making the instance callable
  def __call__(self, new_value):
    self.some_values.append(new_value)

## create a instance to check these functionalities
my_instance = MyClass(239034, "Bob", 23, [10,45,32,67,32,65])

# testing the print functionality, '__str__()' is invoked when 'print()' is called 
print(my_instance) # id: 239034, name: Bob, age: 23

# similarly length functionality
print(len(my_instance)) # 6

# indexing and slicing
print(my_instance[0]) # 10
print(my_instance[0:3]) # [10, 45, 32]
# iterate through the instance 
for a in my_instance:
  print(a) # [10,45,32,67,32,65]

# calling a instance
my_instance(20)
my_instance(90)

# get all values using empty slice
print(my_instance[:]) # [10, 45, 32, 67, 32, 65, 20, 90]
```
#### 7.1.3 Docstrings
* Holds the hints/suggestion working of a function/class provided by the developer. It begins just below the start of a function/class definition. This is a way of documenting functions/class behaviours, useful stuff.
```Python 
class MyClass:
    """This is a docstring."""
    def my_fun():
        """This is what this method does..."""
```
### <strong>7.2 Objects</strong>
* An object has its own attributes/variable (it can be any data-type/data-structure/object) and functions (methods).
* **"Everything in Python is an object"**, in Python's definition of object, some objects may or may not have meta-data/functions and are still objects. The Data-Types in Python have attributes/methods, Data Structures have their attributes/methods, Functions (are first class, as we saw earlier)/Classes are created by metaclasses, so they are all objects. And as a property of an object they all can be assigned to a variable or passed to or returned from a function. So in a sense everything can be called an object. 
* We saw earlier how to create an instance of a class (i.e object) and what/how they can access variables and methods. Here we'll see some examples of everything being an object.
```Python
## data types are object, eg. integer is object of class 'int'
a = 30
print(type(a)) # <class 'int'>
# print some attributes/methods of class int
print(dir(a)[:3]) 

## data structures are object, eg list is object of class 'list'
a = [30, 10, 20]
print(type(a)) # <class 'list'>
# print some attributes/methods of class list
print(dir(a)[:3]) 

## functions are objects of class 'function'
def my_fun():
  pass
print(type(my_fun)) # <class 'function'>

## classes are objects of class 'type'
class MyClass: 
  pass    
print(MyClass.__class__) # <class 'type'>
```
#### 7.2.1 Iterables
* Iterables are objects that can be iterated using loops. An object having a special method *\_\_iter\_\_()* is considered to be iterables. They can be iterated as many times as required.
* Examples of iterables include sequence types such as *list*, *tuple*, *str*, *bytes* and *bytearray*. Also non-sequence types such as dictionary, *set* and others such as *file*, *range* objects.
* A custom class can implement *\_\_iter\_\_()* (which should return an iterator object) or *\_\_get\_\_()* (which is the special method for enabling indexing) method to make its object iterable. They can also become subscriptable/indexable if implemented using *\_\_get\_\_()* method. Examples of non-indexable are dictionaries or *set*s.
* Iterables can be used in *for* loops and in built-in functions like *map()*, *zip()*, *filter()* etc.
* Checking built-in iterables.
```Python
## to check if list is a iterable, check if it has a __iter__() method using dir()
print(dir([1,2,3]))
# or using hasattr
print(hasattr([1,2,3], '__iter__')) # True
# check for tuple
print(hasattr((1,2,3), '__iter__')) # True
# check if set have __iter__ method
print(hasattr({1,2,3}, '__iter__')) # True

## iterables can be used in for loops
for a in (34,32,55,34,56):
    print(a) # 34,32,55,34,56
```
* Create a custom class that has iterable functionality.
```Python
## Example: create a simple iterable object that returns multiplier of 10 by index
class TenMultiplier:
    def __init__(self):
        self.max_range = 10

    # implement __getitem__() or __iter__() method to enable iteration     
    # by implementing __getitem__() our object is also indexable
    def __getitem__(self, index):
        if index > self.max_range:
            # StopIteration is raised to break the iteration in loops
            raise StopIteration
        return index * 10    

my_object = TenMultiplier()
# indexing our object
print(my_object[2]) # 20
# looping over a iterable
for a in my_object:
    print(a) # [0,10,20,30,...100]      
```
#### 7.2.2 Iterators
* Iterator objects can also be iterated using loops. They are also an *iterable* object, but the difference is they must have both *\_\_iter\_\_()* and *\_\_next\_\_()* special methods implemented (this is called the iterator protocol). The *\_\_iter\_\_()* method as we saw earlier returns an *iterator* object, the *\_\_next\_\_()* method is to fetch the next element from the iterator object.
* An *iterator* object represents a stream of data, when the *\_\_next\_\_()* method (or using built-in function *next()*) is called it returns the next consecutive value till the *StopIteration* is raised. And when the *StopIteration* is raised, the *iterator* object is exhausted and no longer returns a value when *\_\_next\_\_()* is called. *iterator* is not required to be finite but be careful when looping over they may cause a *RecursionError*.
* One difference between *iterator* and *iterable* is that once a *iterator* is exhausted it stays empty even after passing it to the *iter()* function (as *Iterator* object returns itself when passed to *iter()*), which is not the case with a *iterable* object (a new *iterator* object is created every time *iter()* is called).
* The *iterator* objects are similar to *generators* "lazy load" data into memory. Examples of iterators are *enumerate*, *zip*, *reversed* etc. The [*itertools*](https://docs.python.org/3/library/itertools.html#module-itertools) module included in the standard library contains a number of commonly-used iterators as well as functions for combining several iterators.
* Limitations of *iterator*s is that values can be iterated only once and in one direction only (can't access previous values) and need to be re-created once exhausted.
* Creating a simple iterator.
```Python
## Example: create a simple iterator from a iterable
# iter() function takes a iterable/iterator object and returns a iterator object
my_iterator = iter([12,34,2,65,21,65])
# iterate to next values using next()
print(next(my_iterator)) # 12
# or calling the special method from a instance
print(my_iterator.__next__()) # 34
for a in my_iterator:
    print(a) # [2,65,21,65]
    # Notice: loop started from index 2, because we already called next() twice
# now as my_iterator is exhausted calling next() again will raise StopIteration
print(next(my_iterator)) # StopIteration
# calling loop will print no value
for a in my_iterator:
    print(a)
```
* Create a custom class that has iterator functionality.
```Python
## Example: create a iterator object which returns a square of each values
class SquareIterator:
  """SquareIterator takes items and returns item's square upon called"""
  def __init__(self, *args):
    self.args = args
    self.iter_len = len(args)-1 # iterating limit for StopIteration
    self.idx = -1 # initialize index to keep track of it

  def __iter__(self):
    """This method returns an iterator object, which is itself."""
    return self
    
  def __next__(self):
    """This method is used to fetch next value, so it should return some value."""
    self.idx += 1  
    # stop if limit is reached
    if self.idx > self.iter_len:
      raise StopIteration
    return self.args[self.idx]**2

my_iter = SquareIterator(2,3,4,8,9,12)  
# iterate values using next()
print(next(my_iter)) # 4
# iterating a iterator object
# for loop calls '__iter__()' and later '__next__()' functions on a iterable/iterator automatically
# we'll see more on the working of for loops next
for v in my_iter:
  print(v) # [9,16,64,81,144]
  # Notice: This time loop started from index 1 now, because we called next() only once
# now like earlier next() will raise error
print(next(my_iter)) # StopIteration

# create a new SquareIterator to reset its index
my_iter = SquareIterator(2,3,4,8,9,12)  
for a in my_iter:
    print(a) # [4,9,16,64,81,144]
```
* When iterating with a *for* loop, the iterable input object is first converted to a temporary *iterator* object and then this object is traversed using *\_\_next\_\_()* till *StopIteration* is raised. So every time a *for* is called a new temporary *iterator* object is created and removed when iteration is finished/interrupted. In case of iterating an *iterator* object, the object itself is returned (as we saw in our *SquareIterator's* *\_\_iter\_\_()* method), so once it's exhausted it stays empty. We'll check an example of the working below.
```Python
## Internal working of for loops
def for_loop(my_iterable):
  """A function to simulate a for loop"""
  # create a temporary iterator object each time starting a loop
  temp_object = iter(my_iterable)
  while True:
      try:
          # call the next() function
          value = next(temp_object)
          print(value) 
      except StopIteration:
          break  # stop the iteration

# pass a iterable/iterator object to our for_loop() function 
my_list = [34,32,55,34,56]
for_loop(my_list) # 34,32,55,34,56

# Now doing the same thing with a for loop
for a in my_list:
    print(a) # 34,32,55,34,56
```
#### The difference between **Iterables**, **Iterators** and **Generators.**
 1. **Iterables**: Are objects that can be iterated, they can be iterated as many times as wanted. They need to implement the *\_\_iter\_\_()* method.
 2. **Iterators**: Are also *iterables* but are "lazy" and can be iterated only once, they need to be re-created for iterating again. They need to implement *\_\_iter\_\_()* and *\_\_next\_\_()* methods. They are used when it is required to implement *iterator* functionality inside a complex class (with other functionalities).
 3. **Generators**: Are *iterables* and *iterators* (but not vice versa). Generators are an easy way to create an iterator object. They can be created using a function with a *yield* statement in it or using generator comprehension. They are used when it is required to create a standalone iterator object.
#### **7.2.4 Descriptors**
* A Descriptor is simply an object that defines at least one of *\_\_get\_\_()*, *\_\_set\_\_()* or *\_\_delete\_\_()* methods and optionally *\_\_set_name\_\_()* method. They allow objects to customize the attribute's/variable's lookup, assignment and deletion. 
* Descriptors are used to control what happens when an attribute is looked up/altered/removed, to override their default behaviour. So instead of the class controlling what happens to the attribute, the attribute decides for itself what goes and what comes out when it is called/assigned. This is helpful when we want some custom behaviour with our attributes.
* **There are two types of Descriptors**.
  1. **Data descriptors**: A Descriptors class that at least has one of *\_\_set\_\_()* or *\_\_delete\_\_()* methods defined.
  2. **Non-data descriptor**: A Descriptors class that only has *\_\_get\_\_()* method defined.
* These two types are not that different but this affects the '.' operator's "lookup chain" i.e data descriptors have more precedence over non-data descriptors. Also for more on descriptors check the [Python docs](https://docs.python.org/3/howto/descriptor.html).
```Python
class MyDescriptor:
    # when a 'MyDescriptor' object is created inside a class this function is called first
    # it records the class name for later reference 
    def __set_name__(self, obj, name):
        # here 'obj' is that class ('MyClass' in our case) object
        # 'self' is our 'MyDescriptor' object 
        self.private_name = "_" + name # internal access name, '_' to avoid name collision

    # when a attribute is looked up(using '.' operator), this method is called
    def __get__(self, obj, objtype=None):
        # fetch 'private_name' from 'MyClass' instance
        value = getattr(obj, self.private_name)
        print(f"{self.private_name} was accessed")
        return value

    # when a attribute is altered(using '=' operator), this method is called      
    def __set__(self, obj, value):
        # here we can decide what is valid value for 'my_var1'
        if self.private_name == '_my_var1':
            if value % 2 == 0:
                raise AttributeError("Not a valid value, require odd number")
        # decide what is valid value for 'my_var2'
        elif self.private_name == '_my_var2':
            if value % 2 != 0:
                raise AttributeError("Not a valid value, require even number")
        # alter 'private_name' of 'MyClass' instance
        setattr(obj, self.private_name, value)
        print(f"{self.private_name} was altered")

class MyClass:
    my_var1 = MyDescriptor() # initialize our descriptor object
    my_var2 = MyDescriptor() # create another attribute

    def __init__(self, var1, var2, var3, var4):
        # calls '__set__()' method of our descriptor to assign the value
        # assign var1, var2 to our descriptor objects my_var1, my_var2 when MyClass is initialized
        self.my_var1 = var1 
        self.my_var2 = var2 
        # normal variables
        self.my_var3 = var3 
        self.my_var4 = var4 

## create a instance of MyClass        
my_instance = MyClass(11, 12, 30, 40) # _my_var1 was altered # _my_var2 was altered
# Notice: the print message we set in '__set__()' method is shown

## check its attribute names
print(my_instance.__dict__) # {'_my_var1': 11, '_my_var2': 12, 'my_var3': 30, 'my_var4': 40}

## accessing the variables using the '.' operator
# calls the '__get__()' method of our descriptor to get its value
print(my_instance.my_var1) # _my_var1 was accessed # 11
print(my_instance.my_var2) # _my_var2 was accessed # 12
# Notice: the print message we set in __get__() method is shown

## calling normal variables
print(my_instance.my_var3) # 30
print(my_instance.my_var4) # 40
# Notice: my_var3, my_var4 show normal behaviour without our print message

## now trying to input invalid value according to out descriptors
my_instance.my_var1 = 42 # AttributeError: Not a valid value, require odd number
my_instance.my_var2 = 41 # AttributeError: Not a valid value, require even number
# Notice: AttributeError is raised due the values didn't match, try a valid value
```

## <strong>8. Modules and Packages</strong>
A short introduction to what are modules and packages in Python. 
### <strong>8.1 Modules</strong>
* Is a file with *.py* extension containing Python code, they are also called scripts. Simply write some Python code in a file and save the file as *.py* extension, your module is ready.
* When you import a module Python looks in a sequence given below:
  1. **Local Directory**: It is where the current *.py* file is located.
  2. **PYTHONPATH**: It is an environment variable that can be used to set additional Python directory paths which Python can use to find modules/packages, it is provided through command line. eg "PYTHONPATH=/path-to/some-dir".
  3. **Python Installation Directory**: This is where your Python is currently installed, it can be viewed with "which python" command from the command line.
  **Note**: This does mean any module with repeating name will be given priority according to this sequence.
* As Python is a Interpreted Language, each time a program is run the *.py* files are compiled from source code to bytecode. To speed this up, when a *.py* file is imported the Python interpreter creates the *.pyc* (byte-compiled version of *.py* files) files if Python has permission to write files in that directory (look for the *\_\_pycache\_\_* folder). So next time Python can directly access the *.pyc* instead of re-compiling if no changes are made in that file. These *byte-compiled* files are platform-independent.
* Use the built-in function *dir()* to find variables/functions/classes inside a module, as modules once imported are objects too. Each imported module's object contains a special variable named *\_\_name\_\_* which is set to the module's name. But the current module which is run by the user has a *\_\_name\_\_* variable set to *\_\_main\_\_*. This helps a programmer to not invoke the script while importing it in another module if they don't intend to. This is similar to the *main()* function's behaviour in C/C++ language.
* Check the [List](https://docs.python.org/3/py-modindex.html) of built-in modules available in Python.
* Importing a module.
```Python
## modules can be imported anywhere in python, there is no restriction
# but for readability they are imported at the beginning
# Eg. math is built-in module, import it using the 'import' keyword
# the 'import' statement creates a module object 
# any module is only imported once in a program, re-importing has no effect
import math 

## accessing a function from math object
# any functions/classes/variables of math module now can be accessed using '.' operator
my_var = math.sqrt(8) 

## import any specifics from the module using 'from' keyword, here we import a function from math module
from math import sqrt

# Note: doing stared import(Eg. from math import *) is not recommended as it might add name collisions
my_var = sqrt(16)

## import with a different access name in order to avoid names collisions
def math(num):
  return pow(num, 2)

## import a module with different name using 'as' followed by a new name
import math as maths 
# accessing a function from 'math' module
print(maths.sqrt(4)) # 2.0
# accessing our 'math' function
print(math(2)) # 4

## Check the functions/classes/variables of a module using dir()
print(dir(math))
```
* Save this below module as *sample.py* or anything you prefer (but change the import name if so in the next module).
```Python
a = 42
def my_fun():
  print("This function was called")

## check if this module is the executing module
if __name__ == "__main__":
  # do something here
  print("sample module was ran")
  my_fun()
```
* \_\_main\_\_ in Python, save this module as *my_module.py* and run this module.
```Python
## Notice: Now importing my_module in this module will not call my_fun() 
# as my_fun() is only called if __name__ equals '__main__', as we intended
# which is only when running from that module i.e running my_module.py script
import sample
print(dir(sample)) # ['__builtins__', '__name__',...]
print(sample.__name__) # sample

# check __name__ variable of current module 
print(__name__) # __main__

## now try doing otherwise, run sample.py check the if this print method is called
if __name__ == "__main__":
  # add code here which you don't want to be invoked unless this script is ran
  print("my_module was ran")
```
### <strong>8.2 Packages</strong>
* A folder with a module named *\_\_init\_\_().py* file is a Python package. Any sub-directories containing *\_\_init\_\_().py* file are also packages (we can call them sub-packages). A Package is a collection of modules (.py files) and is a way to structure the modules under a single package's namespace. To import a module from a package use the "<package_name>.<module_name>" signature. To import a package, import it by its name, that'll import the *\_\_init\_\_().py* module from that package.
* One common practice you might spot in open-source packages is *\_\_init\_\_().py* importing all classes/functions from all of its current directory's modules, this helps in getting all classes/functions under a single package's namespace, so you don't have to call them by following the module names like instead of "<package_name>.<module_name>.<function_name>" you can directly call by "<package_name>.<function_name>".
* You can find all popular open-source Python packages on Python Package Index ([PyPI](https://pypi.org/)), it is an official third-party software repository for Python. You can install a package simply by "pip install <package-name>" command in the command prompt.
**Note**: *pip* comes pre-bundled with Python, some installation may require you use *pip3* instead of *pip*, you can check with "*which pip*" or "*which pip3*", if you see some directory it's already installed or you can install *pip* following the [official guide](https://pip.pypa.io/en/stable/installation/).
* You can also create your own packages, create the following given below example directory structure.
```
./mypackage
  __init__.py
  mymodule.py
  ./myfolder
    __init__.py
    somemodule.py
./somepackage
  others.py
    
# Here "mypackage" folder contains __init__.py so it's s a package, similarly "myfolder" is also a package (or sub-package).
# Note: From Python 3.3 and up it is optional to have __init__.py to be called package, 
# so now "somepackage" directory is also a package.
```
* Importing from such a directory/package is very straightforward using the '.' operator. Create a *test.py* outside of the *./mypackage* directory and try the following code. Note you also need to create additional '.py' files as shown in the above example directory and also define *MyClass* and *myfunction* inside *mymodule* with some code (or just define with *pass* statement).
```Python
## importing a module from package
import mypackage.mymodule

# now use the <module_name> to call its classes/functions
mymodule.myfunction() 

## importing the package by name
import mypackage
# this will call './mypackage/__init__.py' module

## but to import specific classes/functions from that module you need to use from...import
# say import a class from mymodule
from mypackage.mymodule import MyClass
# similarly a function
from mypackage.mymodule import myfunction
```

## <strong>9. Files and I/O</strong>
Basic I/O operations are to take the input from the user and send the output to the user's screen. To handle a file is the task of basically opening/creating a file, reading or making changes and then closing the file. Basic I/O and File operations are very general when working with a project. We'll take a look at three built-in functions for handling these operations and the *with* statement which is very useful for file handling purposes. Later we'll check *Context Management* which is a way to add the *with* statement support to custom objects. Alright.
### <strong>9.1 Three built-in functions for I/O handling</strong>
#### 9.1.1 input(prompt) => None
**Parameters**:</br>
  * *prompt* Any: Your message to the screen.

**Explanation**: Reads input from standard input devices (such as keyboard) and takes it input as string.
```Python
## Take input from user
v = input() # or "input('Your message here ')"
print(type(v)) # <class 'str'>
print(v)
```
#### 9.1.2 print(*values, sep=' ', end='\n', file=sys.stdout, flush=False) => None
**Parameters**:</br>
  * *values* object: Takes the object to be printed, '/*' indicates more than one object. 
  * *sep* Optional[Text]: A separator between multiple values.
  * *end* Optional[Text]: The last print value.
  * *file* Optional[_Writer]: A file-like object (stream), default is screen.
  * *flush* bool: Whether to forcibly flush the stream.
 
**Explanation**: Prints the given object to a standard output device, usually screen.
```Python
## Print output to the screen
print("This is output") # This is output
print("multiple", "objects", "to print") # multiple objects to print
print("This", "is", "a", "String" , sep="_") # This_is_a_String
print("This", end="\t") 
print("is not new line") # This    is not new line
```
#### 9.1.3 open(filename, mode='r', buffering=-1, encoding=None, errors=None, newline=None, closefd=True, opener=None) => file
**Parameters**:</br>
  * *filename* Union[*str*, *bytes*, *int*]: path-like object or a string.
  * *mode* *str*: Opening file mode.
  * *buffering* *int*: For specifying buffering policy.
  * *encoding* Optional[*str*]: Specify encoding format. On Windows the default is "cp1252" and "utf-8" on Linux.
  * *errors* Optional[*str*]: To handle Encoding/Decoding errors.
  * *newline* Optional[*str*]: Specify how newline works.
  * *closefd* *bool*: If set to False, the underlying file descriptor will be kept open even when the file is closed.  
  * *opener* Optional[Callable[[*str*, *int*], *int*]]: A custom file opener, should return a file descriptor.

**Explanation**: This function is used to open a file. It returns a file object (also called handle), this object is further used to perform operations such as read/write/append. For different types of operations there are different modes available, default is r (reading). 
* Various file modes are shown below.
  1. **r**: For opening a file in read-only mode.
  2. **w**: In write mode if the file already exists and has some previous content, it is completely overwritten or a new file is created and content can be written to it.
  3. **a**: In append mode if the file already exists and has some previous content, the new input is appended at the end and not overwritten or a new file is created and content can be written to it.
  4. **x**: In exclusive creation mode if the file already exists, the operation fails or a new file is created and content can be written to it.
  5. **t**: Opening a file in text format, reading a file data as strings, this is the default format.
  6. **b**: Opening a file in binary format, reading a file data as bytes, this is used to handle non-text files like images/database/documents.
```Python
## write to a file, PermissionError is raised if you don't have the permission
file = open("sample.txt", mode="w")
file.write("This is some text written to this file.")
file.close()

## append mode
file = open("sample.txt", mode="a")
file.write("Previous content will not be overwritten.")
file.close()

## read from a file, FileNotFoundError is raised if file is not found 
file = open("sample.txt", mode="r") # or  open("sample.txt")
print(file.read())
file.close()
```
* Mixing modes, you can't mix "a","r" and "w" modes together, but can mix other modes.
```Python
## Example 1: text format and write mode
file = open("sample.txt", mode="tw") 
file.write("This is some text written to the file")
file.close()

## Example 2: read and append mode
file = open("sample.txt", mode="r+")
print(file.read())
file.write("This is some text written to the")
file.close()

## Example 3: binary format and read mode
file = open("some.py", mode="br")
print(file.read())
file.close()
```
* Various file object methods.
```Python
# read all text/non-text data at once, returns string/bytes 
file = open("sample.txt", mode="r") 
print(file.read())
# read all text/non-text data line by line, returns string/byte list
print(file.readlines())
# write string to the file 
file.write("This is some text.")
# take a iterable object containing multiple strings and writes to the file 
file.writelines(["This is a text.", "This is also some text"])
# close a file, frees up system resources, should be called at the last step
file.close()
```
### <strong>9.2 *with* statement</strong>
* This statement simplifies some common resource management like in file streams. It makes code more readable and helps in avoiding resource leaks. When using a *with* statement the resources are handled automatically inside a nested block of code. It guarantees to close the file no matter how the code block is exited. 
```Python
## Example 1: without "with" statement
file = open("sample.txt")
print(file.read())
file.close()
# here if any exception arrives the "file.close()" will not be executed

## Example 2: closing the file using try..finally
try:
  file = open("sample.txt")
  print(file.read())  
finally:
  file.close()

## Example 3: Now doing same as above example using "with" statement
with open("sample.txt") as f:
  print(f.read())
# Notice: no need to call close() method, "with" has you covered

## Example 4: But if you want to handle exception use your own try..except..finally
try:
  file = open("sample.txt")
  print(file.read())  
except Exception as e:
  print(e)  
finally:
  file.close()
```
### <strong>9.3 Context Manager</strong>
* It is a simple protocol that an object needs to follow to add support for the *with* statement. A class needs to define *\_\_enter\_\_()* and *\_\_exit\_\_()* special methods to add the functionality of a context manager. Context managers are usually used in Database management and to handle Thread locks. 
* Also there's a built-in module named [contextlib](https://docs.python.org/3/library/contextlib.html) which can be utilized to achieve the same.
```Python
## Example: simple db manager class with context manager
class MyDBManager:
  def __init__(self):
    self.some_db = {"id": [], 'name': []}
    
  # this method is called when entering the 'with' statement  
  def __enter__(self):
    return self
    
  # this method is called when the 'with' block code ends  
  def __exit__(self, exc_type, exc_val, exc_tb):
    # here we are setting to clear the database once 'with' code ends
    self.some_db['id'] = []
    self.some_db['name'] = []

  # simple function to add values to our db
  def add(self, my_id, name):
    self.some_db['id'].append(my_id)
    self.some_db['name'].append(name)

with MyDBManager() as db_handler:
  # add some values to our db
  db_handler.add(3251, "bob")
  db_handler.add(3252, "rob")
  db_handler.add(3253, "job")
  db_handler.add(3251, "bob")
  # print the db data
  print(db_handler.some_db) # {'id': [3251, 3252, 3253, 3251], 'name': ['bob', 'rob', 'job', 'bob']}
  # now to clear the db just get out of the indentation    

# check the data in db
print(db_handler.some_db) # {'id': [], 'name': []}
# as soon as we were out of the indentation "__exit__()" was called automatically
# which cleared the data, try modifying this behaviour to remove duplicate entries  
```

## <strong>10. OOP concepts</strong>
#### What is OOP?
Wikipedia suggests
  > Object-oriented programming is an approach to designing modular reusable software systems. It is a programming paradigm based on the concept of objects.

  Classes and objects are the two important aspects of OOP. As we saw earlier an object is an instance of class and it has its own attributes & methods and class is where all these attributes & methods are defined.
#### Why OOP?
OOP helps in reducing code complexities & redundancy by promoting better software design practices as opposed to structural/procedure-oriented programming using the concept called objects. OOP really shines when designing large software systems which typically require huge amounts of inter-dependencies among the blocks of code. By following the OOP approach, a software system becomes more reusable, maintainable, scalable, secure and overall less complex compared to structural programming.
**There are four main principles of OOP: [Inheritance](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#101-inheritance), [Abstraction](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#102-abstraction), [Encapsulation](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#103-encapsulation) and [Polymorphism](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#104-polymorphism).**
### <strong>10.1 Inheritance</strong>
* Instead of rewriting the code for all identical blocks like in functional programming, we re-use the methods/variables from say a class inside another class in OOP. This concept is called Inheritance. So basically inheritance helps to eliminate the redundant code.
* We inherit a base/super class and use its methods/variables inside a child/subclass, but not the other way.
* **super()**: This is a built-in function used to access any child's/parent's methods/variables inside of a child class, it is very similar to *super* keyword in Java. When this function is called it returns a temporary object of parent class which then can be used to access all of its methods/variables. 
* **Method Resolution Order (MRO)**: Is the order in which Python looks for a method in the hierarchy of classes. The general order is **child -> parent1 -> parent2...**. When a method/variable is searched, it is looked for in this order. Any name collision is avoided by following this order.
* Inheritance is a powerful concept and is used pretty much all the time when a software is designed using a OOP based language.
#### **10.1.1 Four types of Inheritance.**
1. **Single**: A child/subclass only inherits a single parent/super class.
```Python
## Example: inherit the parent class and try calling its attributes/methods  
class MyParent:
  # class variables
  some_var = 50  
  def __init__(self, para1):
      self.para1 = para1
  def some_func(self, num):
      return num**2
  def other_method(self, num):
      return self.some_var - num

# Inherit MyParent class  
class MyChild(MyParent): 
  # Notice: the rounded brackets after the class_name, 
  # this is where the parent class is to be added, we added MyParent
  def __init__(self, arg1):
    self.arg1 = arg1
    # instantiate parent class inside child class by calling 'super().__init__()'
    super().__init__(arg1)
    # or pass self to the class's constructor like this 'MyParent.__init__(self)' 

  def my_func(self, num):
    # call parent's method using 'super()' function
    output1 = super().some_func(num) 
    print(output1) # 4
    # access parent's variables using 'super()'
    print(super().some_var) # 50
    # here self calls parent's method, as this class doesn't have 'other_method()'
    # this happens due to MRO, as we saw after child parent class is the next lookup target
    output2 = self.other_method(num) 
    print(output2) # 48

  def some_func(self, num):    
    return num**3

# create a instance of child class
child_instance = MyChild(38)
# calling my_func() calls child's method
child_instance.my_func(2)
# calling same named method, calls child's method 
print(child_instance.some_func(2)) # 8
# now calling parent class's method, because child doesn't have this method
print(child_instance.other_method(8)) # 42
```
2. **Multiple**: A child/sub class inherits multiple parent/super classes.
```Python
## Example: Inherit MyParent1,MyParent2 and try calling its attributes/methods  
class MyParent1:
  def __init__(self):
      self.para1 = 10
  def doing_something1(self, num):
      return self.para1 - num
  def other_method(self, num):
      return num**2
  
class MyParent2:
  def __init__(self):
      self.para1 = 20
      self.para2 = 42
  def doing_something2(self, num):
      return self.para1 - num
  def other_method(self, num):
      return num**3

## inherit MyParent1 and MyParent2 classes 
class MyChild(MyParent1, MyParent2): 
  def __init__(self, arg1):
      self.arg1 = arg1
      # initialize first parent using 'super()'
      super().__init__()
      print(self.para1) # 10
      # initialize second parent by passing 'self' object to its constructor
      # because super can only keep track of single class, which is MyParent1
      MyParent2.__init__(self) 
      # so now MyParent2's variables/methods can be accessed
      print(self.para1) # 20
      print(self.para2) # 42

  def my_func(self, num):
    # here MyParent1's method will be called, due to MRO
    output1 = self.other_method(num) 
    # similarly can do 'super().other_method(num)'
    # or even by class name by passing self 'MyParent1.other_method(self)'
    return output1

# create a child instance
child = MyChild(30)
# use the mro method on a instance to check the parent classes
print(MyChild.mro()) # [<class '__main__.MyChild'>, <class '__main__.MyParent1'>,
# <class '__main__.MyParent2'>, <class 'object'>]

# same as before, calling MyParent1's method
print(child.other_method(2)) # 4
# now calling child's method
print(child.my_func(2)) # 4

## to call MyParent2's same named method using child instance
# call with the class name and pass child instance
print(MyParent2.other_method(child, 2)) # 8
print(MyParent1.other_method(child, 2)) # 4
# calling by class name is always available, you can use it to avoid naming collisions 
```
* When it comes to Multiple Inheritance there is one more concept called *mixins*. You might spot them in some library code, they are named somewhat like "<class_name>Mixin". They are classes that act as base classes carrying some features (i.e functions) that other classes are supposed to use. They usually don't have instance variables (might have class variables), they are base classes which do not inherit another class (other than *object*) and are not intended to be instantiated, only sub-classed.
* *Mixins* are a cleaner way to define some functions that other classes can use right away without defining them individually. This concept is not recognized by Python, so they act as a normal class.
```Python
## Example: create a class with printing functionality and subclass it
class SomeMixin:
    def printer(self):
        print(f"a = {self.a}")
        print(f"b = {self.b}")
        print(f"total = {self.total}")
    # can also have other methods
    def do_something(self):
        pass 

# now inside below classes we wont write the printer function
# instead just inherit SomeMixin and we'll have that functionality
class Adder(SomeMixin):
    def __init__(self, a, b):
        self.a = a
        self.b = b
    def perform_op(self):
        self.total = self.a + self.b

class Subbtr(SomeMixin):
    def __init__(self, a, b):
        self.a = a
        self.b = b
    def perform_op(self):
        self.total = self.a - self.b

v = Adder(10, 20)
v.perform_op()
# call printer method, but make sure variables share same names
# across the mixins and child classes 
v.printer() # a = 10 # b = 20 # total = 30

v = Subbtr(40, 10)
v.perform_op()
v.printer() # a = 40 # b = 10 # total = 30
```
3. **Multilevel**: In Multi-Level a child class inherits a parent class and is also a parent class to another class.
```Python
## Example: inherit classes in a sequence like MyClass1 -> MyClass2 -> MyClass3
class MyClass1:
  def __init__(self):
      self.para1 = 5
  def doing_something1(self, num):
      return self.para1 - num
  def other_method(self, num):
      return num**2

class MyClass2(MyClass1):
  def __init__(self):
      self.para2 = 20
      # initialize parent class by class name
      MyClass1.__init__(self)

  def doing_something2(self, num):
      return self.para2 - num
  def other_method(self, num):
      return num**3
  
class MyClass3(MyClass2):
  def __init__(self):
      self.my_para1 = 42
      self.my_para2 = 42
      # initialize parent class by class name
      MyClass2.__init__(self)

  def doing_something2(self, num):
      return self.my_para1 - num
  def other_method(self, num):
      return num**3
      
# can access MyClass1 variables/methods
parent1 = MyClass1() 
# check MRO    
print(MyClass1.mro()) # [<class '__main__.MyClass1'>, <class 'object'>]

# can access MyClass2, MyClass1 variables/methods
parent2 = MyClass2() 
print(MyClass2.mro()) # [<class '__main__.MyClass2'>, <class '__main__.MyClass1'>, <class 'object'>]

# can access MyClass3, MyClass2, MyClass1 variables/methods
child = MyClass3()
print(MyClass3.mro()) # [<class '__main__.MyClass3'>, <class '__main__.MyClass2'>, \
# <class '__main__.MyClass1'>, <class 'object'>]
print(child.para1, child.para2, child.my_para1) # 5 20 42
```
4. **Hierarchical**: A parent/super class is inherited by more than one child/subclass. 
```Python
## Example: inherit a base class by 2 sub classes
class MyParent:
    args = [22,59,81,34,73,12,35]
    
# inherit the 'MyParent' class
class MyChild1(MyParent):
  def max_finder(self):
    return max(self.args)
    
# inherit the 'MyParent' class
class MyChild2(MyParent):
  def min_finder(self):
    return min(self.args)

my_instance1 = MyChild1()
my_instance2 = MyChild2()
print(my_instance1.max_finder()) # 81
print(my_instance2.min_finder()) # 12
```
### <strong>10.2 Abstraction</strong>
* It is a process of hiding internal implementation details and showing only some limited necessary functionality. Hiding in a sense focussing on what methods and classes must do and not their exact definition/implementation. Abstract class is not the way to achieve complete abstraction, as they can also contain normal methods with definition. Interfaces are the way to complete abstraction, although Python doesn't support interfaces Abstract classes should be enough.
* Abstract classes are classes that have at least one abstract method, it can also have other normal method types. Abstract methods are methods that do not have a body (they are empty methods). The abstract classes cannot be instantiated (its object cannot be created). The concrete/inheriting class of this abstract class has to implement all the abstract methods compulsorily else an error should be raised. The concept of abstract is not applicable to variables so they behave normally.
* Python does not have *abstract* keywords like in Java and also does not directly support abstract classes. But Python provides a module named *abc*, it can be used to define Abstract Base classes (ABC) which act about the same. 
* The Abstraction concept is not necessarily a compulsion in order to design a system. But when designing larger systems it can be good to have Abstraction checked, the abstract classes can be designed to act as base for other classes to avoid functionality break/bugs and further make it necessary for other programmers to implement/design other classes following some common interface.    
```Python
## Example: create a abstract class and inherit it
# import the 'ABC' class and 'abstractmethod' from abs module
from abc import ABC, abstractmethod

# inherit the 'ABC' class to create a abstract class 
class MyBase(ABC):
    # define abstract methods by using 'abstractmethod' as decorator
    @abstractmethod
    def get_vars():
        pass
    @abstractmethod
    def change_values(self, a, b):
        pass
    # defining combination of method types   
    # Notice: 'abstractmethod' should always follow later 
    @staticmethod
    @abstractmethod
    def some_info():
        print("this method is both static and abstract")

    def mydefault_fun():
        print("This is normal method")

# create concrete classes using 'MyBase' class as parent class
class MyConcrete1(MyBase):
    def __init__(self, a, b):
        self.a = a
        self.b = b
    def change_values(self, a, b):
        self.a = a
        self.b = b
    def get_vars(self):
        return self.a, self.b
    def some_info(self):
        print(f"This is MyConcrete1")

class MyConcrete2(MyBase):
    def __init__(self, a, b, c):
        self.a = a
        self.b = b
        self.c = c
    def get_vars(self):
        return self.a, self.b, self.c

# create a instance to ensure everything is correct
my_concrete1 = MyConcrete1(10, 20)    
print(my_concrete1.get_vars()) # 10, 20
my_concrete1.some_info() # This is MyConcrete1

# remember a concrete class has to implement all abstract methods of the abstract class, 
# also note that mydefault_fun is not a abstract method so it is not required to be defined
# 'MyConcrete2' will raise TypeError due to not implementing all abstract methods 
# TypeError: Can't instantiate abstract class MyConcrete2 with abstract methods change_values, some_info
my_concrete2 = MyConcrete2(10, 20, 30) 
# you cannot instantiate a abstract class 
my_base = MyBase() # TypeError: Can't instantiate abstract class
```
### <strong>10.3 Encapsulation</strong>
* Encapsulation refers to simply wrapping attributes/data and methods under a single class. This data (of any data-type/data-structure/object) can be only accessed/altered by the class methods themselves essentially to restrict access from outside of the class. This is called data hiding. 
* This technique is essential to protect private data to be accessed/misused from another class directly. To implement this we use Access Modifiers. They are used to define the access type of a variable inside a class. 
* **Three Types of Access modifiers.** 
  1. **Public**: Can be accessed anywhere in the program. All variables are public by default.
  2. **Protected**: Only the current class and derived class can access them. Use "\_<variable_name>" to define them.
  3. **Private**: Only the current class can access them, not even their instance can access them. Use "\_\_<variable_name>" to define them.
* To hide some data, first it is set to *private* type to restrict the direct access and if we want to allow these private data to have some kind of access by outside class, create the public *setters()* and *getters()* methods, like in Java/Javascript. But Python also has another way, it is called the *property* object.
* In Python, all variables are public by default and the way private/protected are implemented they don't really work as one would expect, below are some examples.
* Access modifiers basics.
```Python
class MyClass:
  def __init__(self):
      self.my_var1 = 10 # public variable
      # Notice: the _ underscore before my_var2
      self._my_var2 = 20 # protected variable
      # Notice: the __ underscore before my_var3
      self.__my_var3 = 30 # private variable

  def demo_method(self):
    # can access all variables
    print(f"{self.my_var1}, {self._my_var2}, {self.__my_var3}")

class MyClass1(MyClass):
  def __init__(self):
      super().__init__()

# Note: "can't be accessed will" raise AttributeError, 
# to continue program execution comment/remove those lines

## access by parent instance 
my_instance = MyClass()
print(my_instance.my_var1) # can be accessed
print(my_instance._my_var2) # can be accessed
print(my_instance.__my_var3) # can't be accessed, private variable
my_instance.demo_method() # 10, 20, 30

## access by child instance
my_instance = MyClass1()
print(my_instance.my_var1) # can be accessed
print(my_instance._my_var2) # can be accessed
print(my_instance.__my_var3) # can't be accessed, private variable
```
* Allowing access from outside class.
```Python
## Example: define a class with setter() and getter() methods
class MyClass:
  def __init__(self):
      self.my_var1 = 10 # public variable
      self._my_var2 = 20 # protected variable
      self.__my_var3 = 30 # private variable

  # get_my_var() is getter method that returns the private variable 
  def get_my_var(self):
    return self.__my_var3

  # set_my_var() is a setter method that sets the value of private variable
  def set_my_var(self, new_value):
    # if you want '__my_var3' read-only you can raise AttributeError, uncomment the following line 
    # raise AttributeError("Cannot change this value")
    self.__my_var3 = new_value  
    
some_instance = MyClass()
# call the getter method
print(some_instance.get_my_var()) # 30
# call the setter method
some_instance.set_my_var(50)
# check the value with getter again
print(some_instance.get_my_var()) # 50
# but still can't access directly
print(some_instance.__my_var3) # AttributeError
```
* Problem with Python's access modifier implementation.
```Python
class MyClass:
  def __init__(self):
      self.my_var1 = 10 # public variable
      self._my_var2 = 20 # protected variable
      self.__my_var3 = 30 # private variable

some_instance = MyClass()
# '__dict__' a special variable in python that keeps track of attributes of module/class/object
# this process is name mangling, which uses '_CLASSNAME' prefix for private variables
# you can print this to show all the private variables
print(some_instance.__dict__) # {'my_var1': 10, '_my_var2': 20, '_MyClass__my_var3': 30}
# or use 'vars()' function to return the '__dict__' variable
print(vars(some_instance)) # {'my_var1': 10, '_my_var2': 20, '_MyClass__my_var3': 30}
# you can see the variable right away,
# and now by knowing its name you can alter/remove it using the same naming convention
some_instance._MyClass__my_var3 = 42
print(some_instance._MyClass__my_var3) # 42
# can also remove the variable
del some_instance._MyClass__my_var3 
# causing AttributeError
print(some_instance._MyClass__my_var3) # AttributeError
# so in summary it's not really a private variable, Python does not follow the concept 
```
#### **10.3.1 property(fget=None, fset=None, fdel=None, doc=None) => property** </br>
**Parameters**:</br>
  * *fget* Optional[Callable]: The getter function.  
  * *fset* Optional[Callable]: The setter function.  
  * *fdel* Optional[Callable]: The deleter function.  
  * *doc* Optional[*str*]: Provide some information about this property.

**Explanation**: It is a Pythonic way to use getters and setters in encapsulation. *property()* function simply allows assigning/altering private variables using the '.' operator without really exposing the real (private) variable. Using this function accessing/modifying becomes just as convenient as operating on a regular variable. *property()* can also be used as decorator for further convenience. For more implementation details check [Official Python docs](https://docs.python.org/3/howto/descriptor.html#properties).
**Descriptor vs Property**: Descriptors are the low-level mechanism behind allowing class variables to control what happens during attribute lookup. And properties are descriptors, they are an implementation of descriptors. Although one drawback using descriptors is that for creating a single variable a separate class has to be defined, which is not the case with properties. One can have multiple variables of such behaviour inside a single class using properties.
```Python
## Example: implement encapsulation using property 
class MyClass:
  def __init__(self):
      self.my_var1 = 10 # public variable
      self._my_var2 = 20 # protected variable
      self.__my_var3 = 30 # private variable
      self.__my_var4 = 40 # private variable

  # getter method for '__my_var3'
  # Note: the property decorator, 'my_var' can be renamed to any other name
  @property 
  def my_var(self):
    print("Getter method called")
    return self.__my_var3
    
  # setter method for '__my_var3'
  # if you don't want '__my_var3' value to be altered, don't define this method     
  # Notice: the <VAR_NAME>.setter decorator  
  @my_var.setter
  def my_var(self, new_value):
    print("Setter method called")
    self.__my_var3 = new_value    
  
  # deleter method for '__my_var3'
  # if you don't want '__my_var3' value to be deleted, don't define this method     
  @my_var.deleter
  def my_var(self):
    print("Deleter method called")
    del self.__my_var3   
  
  # getter method for '__my_var4', this is the second variable (we talked about in property vs descriptors)
  @property
  def some_var(self):
    return self.__my_var4
  
  # or without using property decorator, just pass the functions to property function, example below  
  # my_var = property(my_getter, my_setter, my_deleter)
  # that's it, my_var will have getter, setter, deleter methods

# '__my_var3' is a private variable and 'my_var' is the variable that can be
# used to modify '__my_var3' from outside the class     

some_instance = MyClass()
print(some_instance.__dict__) # {'my_var1': 10, '_my_var2': 20, '_MyClass__my_var3': 30, '_MyClass__my_var4': 40}

# access using the property variables by <VAR_NAME>, calls the getter method
print(some_instance.my_var) # Getter method called # 30
print(some_instance.some_var) # 40
# alter their values using '=' operator, calls the setter method
some_instance.my_var = 50 # Setter method called
print(some_instance.my_var) # 50
# remove the variables
del some_instance.my_var # Deleter method called

# some_var has no setter, deleter methods so will raise AttributeError
some_instance.some_var = 90 # AttributeError
del some_instance.some_var # AttributeError
```
### <strong>10.4 Polymorphism</strong>
* Polymorphism means many forms. It is the ability to use a common interface/function to perform tasks on different types of objects. It can be also thought of as a way to get rid of *if..else* or *switch* when the same type of function needs to be called on different objects.     
* **Two main types of Polymorphism.**
  1. **Static**: The behaviour is decided at Compile-time, like in method/operator overloading. 
  2. **Dynamic**: The behaviour is decided at Runtime, like in method/function overriding.
#### **10.4.1 The Four types of Polymorphism.**
1. **Method overloading**: A class can have same named methods but should have distinct input parameters, this functionality is not supported in Python. As the methods with the same name are overwritten by the newer ones. Usually other parameters are set to *None* and missing object types are checked throughout using *if..else* statement or *isinstance()* function for achieving the same, but similar thing can be achieved using functool's singledispatchmethod, [multipledispatch](https://github.com/mrocklin/multipledispatch) or [plum](https://github.com/wesselb/plum). *functool* is included in the standard library and the other two are required to be installed separately using "pip".
```Python
## Example 1: simple Method Overloading in Python
class MyClass:
    def printer(self, a, b):
        total = a + b
        print(f"Your total is {total}")
    # Notice: this method name is same as above
    def printer(self, a, b, name):
        total = a + b
        print(f"{name} your total is {total}")
      
my_instance = MyClass() 
# here 'printer(a,b,c)' has overwritten 'printer(a,b)', so it won't work raising TypeError
my_instance.printer(20, 30, "Bob") # Bob your total is 50
my_instance.printer(20, 30) # TypeError: printer() missing 1 required positional argument

## Example 2: use a single function to handle everything 
class MyClass:
    def printer(self, a, b, name=None):
        total = a + b
        if name:
            print(f"{name} your total is {total}")
        else:
            print(f"Your total is {total}")

my_instance = MyClass() 
my_instance.printer(20, 30, "Bob") # Bob your total is 50
my_instance.printer(20, 30) # Your total is 50
# now it works
```
* Example using *multipledispatch*.
```Python
## Example: simple Method Overloading using multipledispatch
## Note: you need to first install multipledispatch using "pip install multipledispatch" command 
from multipledispatch import dispatch
class MyClass:
    # decorate with dispatch and pass the desired data type for method
    # its important because using it dispatch will figure out the signature 
    @dispatch(int, int)
    def printer(self, a, b):
        total = a + b
        print(f"Your total is {total}")

    @dispatch(int, int, str)
    def printer(self, a, b, name):
        total = a + b
        print(f"{name} your total is {total}")
      
my_instance = MyClass() 
# now calling methods with parameters
my_instance.printer(20, 30, "Bob") # Bob your total is 50
my_instance.printer(20, 30) # Your total is 50
```
2. **Operator Overloading**: Make operators work for user-defined classes, when a class implements a particular operator's function (which is a special function in Python) and changes its functionality (does something and returns something), that functionality is applicable to that class/object only. Changing an operator's behaviour for a specific object can be done by overloading an operator's function.
```Python
## Example: overload the addition and subtraction operator in MyClass
class MyClass:
  def __init__(self, *args):
    self.args = args
  
  # this is a special method to overload '+' operator
  def __add__(self, my_obj):
    # Note: my_obj is the other object Python passes when the '+' operator is called
    """Define functionality behaviour for the '+' operator inside this method, 
    the input parameter can be of any type as required. Just the functionality defined below should support it."""
    return sum(self.args) + sum(my_obj.args)
    
  # similarly this is a special method to overload '-' operator
  def __sub__(self, my_obj):
    """Define functionality behaviour for '-' operator."""
    return abs(sum(self.args) - sum(my_obj.args))
    
my_ins1 = MyClass(90, 20, 10, 42)
my_ins2 = MyClass(10, 70, 20, 50)
# invoking the __add__() method of MyClass
print(my_ins1 + my_ins2) # 324
# or call with class by passing a self and my_obj 
print(MyClass.__add__(my_ins1, my_ins1)) # 324
# invoking the __sub__() method of MyClass
print(my_ins1 - my_ins2) # 12
```
3. **Method overriding**: Use same named methods but inside different classes. Two classes can have same named methods, but the functionality might differ with their class. Useful for handling the operation from a common interface/function. This functionality can also be referred to as Duck Typing. It is a feature of dynamic languages, it means directly (by not caring about exceptions) calling methods on objects without checking their types.  
```Python
## Example: create two classes with same named methods and a interface function to call these methods
class ListHandler:
  my_list = [70, 30, 80, 20]
  def return_addition(self):
    """Returns addition of list elements"""
    return sum(self.my_list)

class DictHandler:
  my_dict = {"key1":70, "key2":90, "key3":10, "key4":60}
  def return_addition(self):
    """Returns addition of dict elements"""
    return sum(self.my_dict.values())

# a common interface to handle same operation
def perform_addition(obj):
  output = obj.return_addition()
  print(output)

# create instances for both classes
handler_l = ListHandler()
handler_d = DictHandler()
# we pass our handler_l and handler_d objects to perform_addition() function
# and hope it works
perform_addition(handler_l) # 200
perform_addition(handler_d) # 230
# and it does, this is duck typing
```
4. **Function overriding**: Changing the default functionality of a built-in function for a particular object, essentially to add some behaviour for a custom object. 
```Python
## Example: create a class and override two functions behaviour
class MyClass:
  def __init__(self, *args):
    self.args = args

  # this special method represents the 'len()' built-in function
  def __len__(self):
    """Defining behaviour here enables function overriding."""
    return len(self.args)

  # Notice: this method is commented so will not execute
  # def __str__(self):
    # """Similarly this is for print functionality for this object."""
    # return " ".join((str(a) for a in self.args))

my_ins = MyClass(10, 20, 30, 40, 50)
# now as the __len__() is implemented this will return the output
print(len(my_ins)) # 5
# this will return address of this object by default
print(my_ins)
# uncomment __str__() and re-run to see change in its functionality
```
## References
* [Python Official docs](https://docs.python.org/3/reference/index.html)
* [Fluent Python](https://www.oreilly.com/library/view/fluent-python/9781491946237/)
* [Time complexity python](https://wiki.python.org/moin/TimeComplexity)
* [Python built-in modules](https://docs.python.org/3/py-modindex.html)
* [Python built-in functions](https://docs.python.org/3/library/functions.html)
