# Programmer's guide to Python
#### Note: This book is not finalized yet and is currently under works.

Hello Learner, welcome to this Programmer's guide to Python handbook, this book was originally designed as notes when I was learning Python, but then I thought okay why not make it public for other learners, so I added some missing components and completed it as a book. I hope this helps you in learning Python programming. Happy Learning!!

**What's not this:** Not a traditional programming course/book, this is by no means a complete Python walkthrough and might be structured somewhat differently. I have tried to cover & mostly emphasis on important features and tricks inside Python. This book is not recommended for 'programming freshers', you should try more beginner friendly books like [Byte of Python](https://python.swaroopch.com/)/[Think Python](https://greenteapress.com/wp/think-python-2e/) and comeback to this one to further fine tune your learning.</br>  

**What is this:** This book is meant for a programmer who's already familiar with other languages such as C/C++/Java and wants to learn Python but fast. The one who needs a Python refresher can also benefit by this book. The goal is to take you through enough Python (and much more), while saving you tons of time. I have tried to keep explanations concise most of the times, so things can be gone through fast. To grow as a programmer its always better to practice. I would suggest copying & running your own programs and creating your own notes.

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

## 1. Basics
### 1.1 Introduction
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; According to Wikipedia "Python is an interpreted high-level general-purpose programming language." It was created by Guido van Rossum and released in 1991. It supports multiple programming paradigms like object-oriented, procedural and functional. Python is also dynamically-typed and garbage-collected. Python's best implementation is in C language called [Cython](https://github.com/python/cpython), it is the default/standard but there are other implementations in Java, .Net, etc. Its philosophy revolves around code readability and code simplicity, you can also check [zen of python](https://www.python.org/dev/peps/pep-0020/) for more on that. Python is widely used in Web-Development([flask](https://flask.palletsprojects.com/en/2.0.x/), [django](https://www.djangoproject.com/), [fastapi](https://fastapi.tiangolo.com/)), Android/Windows/IOS/OSX application development([kivy](https://kivy.org/#home)), Big-Data Processing/Databases([Pyspark](https://spark.apache.org/docs/latest/api/python/), [Pandas](https://pandas.pydata.org/)), Machine learning([pytorch](pytorch.org/), [tensorflow](tensorflow.org/), [sklearn](scikit-learn.org/stable/)), Mathematical/Scientific libraries([numpy](numpy.org/), [scipy](scipy.org/)), DevOps, Security, etc. The current/latest version is Python3 which was released in 2008 and is still relevant(as of 2021), as Python2 was discontinued at 1 Jan 2020, Python3 is the way to go.      
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; There is a fair amount debate around "Python is a slow language", this [article](https://hackernoon.com/why-is-python-so-slow-e5074b6fe55b) has some answers, but for most part that does not affect its usability/credibility, it is the most preferred programming language and is still growing popular(as of 2021). There are other languages which are good enough to be Python's successor such as Rust, GO and Julia. These languages do have potential to eventually replace Python, at least in some domains in coming time, but it is yet to be seen.  
### 1.2 Fundamentals
#### 1.2.1 Literal constant
* Are raw data, literals are constant fix values. A raw value by itself is a literal constant. 
```Python
# some literals
4, 6, 2.5, 7.4, 'string', 'something'
# here 4 has no other value replacement, so its a integer literal
# similarly 'something' is also a string literal
```
#### 1.2.2 Keywords
* Are reserved words which are defined by Python, so they can't be used as operands.
```Python
# some keywords
if, else, for, while, is, as, or, not, and, None, def, class, return, yield, pass, raise
```
#### 1.2.3 Operands/Variable
* Are objects that hold values, it has a user-defined name, a name should not begin with a underscore (because it is reserved for something else), other naming rules are similar to other languages. 
* Unlike C/C++/Java, Python is Dynamically-Typed. It is when the type checking happens at run-time (and not at compile-time). Type checking is to ensure "type-safe", say a *int* doesn't get assigned to a *float*.
* In Python there is no "variable declaration", you do not need to declare a variable, they come to existence when they are assigned something. Also there is no need for "type declaration", variables are just name pointers.
* Whenever a object is created in Python, the object/value along with it's type is assigned some memory in a storage. When that object is assigned a variable, that variable is just a name/reference to this memmory. The value on the left is the name assigned to this object and on the right is the representation of this object. As variables are just names they do not have types, they can be assigned to any type of object.
```python
## variable names example
MyInt, some_var, my_string12, SOME_NUMBER

## Dynamically type feature
# the type is checked only at run-time
if False:
  30 + "some string"
# Above statement should return a TypeError but it will not, 
# because that condition is never executed, if it did it will raise the exception, try with "if True"

## Dynamically typed: Assigning a name (variable) to the object
a = 34
a = "I am string"
a = [1,2,3,4]
a = 4.0
# Assigning a name to 34, then changing it to point to a string, then a list. 
# All of them are valid, as variables dont have types

## Variables are just reference
a = 34
b = a
a = 20
print(a, b) # 20, 34
# Here, a was pointing to 34, we assigned a to b which is b also refers to 34 (and not a)
# so changing a to 20 doesn't affect the b, it still points to 34
```
#### 1.2.4 Operators 
* Are used to perform operations on operands. The Arithmetic, Assignment, Comparison, Bitwise operators work same as in C/C++/Java/Javascript, so I will not explain their working. Other Logical, Identity, Membership operators are Python specific, that we'll take a look at.
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
# the 'if' condition is satisfies only when the output is 'False'
if not isinstance(a, int):
  print('not printed')
if not isinstance(a, str):
  print('printed')

## 'and' is similar to '&&' in C/C++/Java: both conditions should be satisfied
a=20
b=30
if a > 10 and b < 50:
  print('printed')
  
## 'or' is similar to '||' in C/C++/Java: either of conditions should be satisfied
if a > 10 or b < 10:
  print('printed')
```
* <b>Identity operator</b>: is,is not.
```Python
## is: checks if 2 objects are referring to the same object. 
some_var1 = 42
some_var2 = 42
if some_var1 is some_var2:
  print('printed')
# check with id  
print(id(some_var1)) # 2587096149584
print(id(some_var2)) # 2587096149584
# this is also true, here values are checked
if some_var1 == some_var2:
  print('printed')

# another example
a = 42
b = 42.0
print(id(a)) # 2753953689168
print(id(b)) # 2753956924080
if a is int(b):
  # true due to dynamic typing i.e as 42 == int(42.0) are the same, check the id
  print(id(int(b))) # 2753953689168
  
# but then where's the difference  
a = [20, 30]
b = [20, 30]
if a is b:
  # even though their values are same, they are different object so not True
  print('not printed')
print(id(a)) # 2055633338880
print(id(b)) # 2055638580288

## is not: negate the 'is' condition, working is similar as we saw above
# Notice: 'not' should be applied after 'if' and not after 'is'
if not a is b:
  print("printed") 
```
#### 1.2.5 Expressions
* A expression is something that is evaluated by the interpreter, say on a value/sequence by doing some operation (arithmetic/conditional/lambda function). They are a part of statements (as in expression statement).
```Python
# some examples
"Yes"+"this"
x+6
if a==3 else 2
a or b
2 and 3
lambda x:x**2
```
#### 1.2.6 Pythonic Sugar expressions
* Are optionally available to write some expressions in a short way.   
```Python
## Some examples
## Multiple Target assignment
a = b = c = 10
# lets check the outputs
print(a,b,c) # 10,10,10
a = 20
b = 30
# lets check again
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
```
#### 1.2.7 Statements
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
#### 1.2.8 Comments
* Hiding information/description from the interpreter to exclude.
```Python
# this is a single line comment
# TODO: this is a todo commment, useful in IDEs like Visual Code/Pycharm

"""this is a 
multiline comment
"""
```
#### 1.2.9 Indentations 
* Unlike using brackets in C/C++/Java, indentations are used for a code block in Python. Indentations can be of any range, usually four indentations are preferred, only constraint is that they should be consistent throughout that block of code. Un-indented line is used to show the end of that block of code. 
* They are used in Flow Control, Exception Handling, Functions/Classes definitions in Python, else *IndentationError* is raised. Any statements or even comments should follow the indentation rule.
```Python
## example 1
# Notice: the colon at the end of 'if' condition
if 10 > 5:
print('printed') # IndentationError

## example 2
if 10 > 5:
    # preferred indentation
    print('printed')
print('block code ends')
# also valid indentation
if 10 > 5:
   print('printed')
   print('also printed')
# continue other code

## example 3
class MyClass:
some_var = 10 # IndentationError
  def my_function():
  some_var1 = 20 # IndentationError
```
#### 1.2.10 Namespaces
* As seen in C++ namespaces are collection of names of variables/functions, but unlike C++, Python does not have the *namespace* keyword and so no user defined namespaces. Python maintains all of the namespaces in a dictionary automatically. They are maintained/recorded according to the scope of a variable/function, just as in any programming language.</br></br> 
  **Three types of namespaces.**
  #####
  1. **built-in**: Are readily available functions without any import.
  2. **global**: Are which user defines outside of any function/class. 
  3. **local**: Are which user defines inside a function/class/nested.
```Python
## built-in namespace 
"""
# For example some functions which do not require any import 
print(), len(), map(), range(), list(), set(), str()
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
#### 1.2.11 Time Complexity 
* It is used to measure how runtime of a function increases with the size input. Note that time complexity is not equal to execution time. It is used to calculate how a function will scale, given the number of inputs. Time Complexity for a smaller data/problem can be negligible or not necessary to be optimized, usually one should invest time in tuning time complexity for larger, time intensive problems or problem that require faster response time. A good time complexity [chart](https://www.bigocheatsheet.com/). </br></br>
  **Common Time Complexities in ascending order of their growing time.** 
  #####
  1. **O(1)**: Constant time. Time does not increase at all.
  2. **O(logN)**: Logarithmic time. When time is increasing logarithmically (grows at inversely proportional rate of N).
  3. **O(N)**: Linear time. Time increases linearly with the input size.
  4. **O(NLogN)**: Linearithmic time. Logarithmic and Linear time together.
  5. **O(N\*\*K)**: Polynomial time. When time increases at N (input) to the power K (constant) times.
  6. **O(K\*\*N)**: Exponential time. When time increases at K (constant) to the power N (input) times.
  #####
  **Note**: Explaining all time complexities would consume lots of space for this book, you can get more information about it [here](https://www.hackerearth.com/practice/basic-programming/complexity-analysis/time-and-space-complexity/tutorial/) and with some examples [here](https://www.kaggle.com/delayedkarma/understanding-time-complexity-via-python-examples).


## 2. Data Types
Defines a particular kind/domain of data item, they define the type of data a variable holds. They also define the operations allowed on that data type. Python doesn't require declaration of data types like in C/C++/Java (as variables are just pointers). Any variable can be assigned any data type/object, a string variable can be assigned int or float or any other object it doesn't matter. There is no *final* (used for declaring a constant variable) keyword for variables in Python like in Java. The constant variables in Python are defined inside another module (we will cover this later), their names should be in capital letters and then later they are imported inside the current module to be used. </br>
#### Three types of Data Types in programming.
  1. **Primitive**: Are built-in or predefined data types in a programming language, Eg. int, float, double (n/a in Python), char (n/a in Python), bool etc.
  2. **Composite/Derived**: Are data types which are constructed using two/more data types, Eg. Array (list in Python), Record (tuple in Python), Union (dict in Python), Strings (str in Python), Functions, Pointers (n/a in Python), Structures (n/a in Python) etc.
  3. **Abstract**: They define operations on object using functions but without specifying the exact implementations of those functions (the underlying implementation can differ from languages but the working has to stay same), Eg. Stack, Queue, Map, Tree, Graphs etc.
#### Mutable and Immutable types inside Python.
  1. **Immutable**: Values cannot be altered/added/removed once created or are read-only types once created, Eg. int, float, complex, bool, None, str, tuple, frozenset.
  2. **Mutable**: Values can be altered/added/removed after creation, Eg. list, dict, set.
####  
Data types explained below are [int](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#21-three-numeric-types), [float](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#21-three-numeric-types), [complex](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#21-three-numeric-types), [str](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#22-text-type-str), [bool](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#23-boolean-type-bool), [byte](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#24-binary-types-byte) and [User-defined Data Type](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#25-user-defined-data-type). For simplicity I've arranged rest of them in [Data Structure's](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#3-data-structures) section. Later we'll take a look at the [None](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#26-none-object) object and some built-in functions.
### 2.1 Three Numeric Types
1. **Interger** (int): Numbers that do not have decimal values. In Python, *int* is also a *long* and it can be of any size. 
2. **Float** (float): Numbers that do have decimal values. In Python, *float* is also a *double* as it is a double precision floating point number. 
3. **Complex** (complex): Numbers that have two parts, real and imaginary. First part is normal number, the second part is imaginary number which should be followed by j. </br>
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
### 2.2 Text Type (str)
* Unlike Java, Python does not have *char* type for storing character/character array, it has *str* object (similar to *string* in C++) which is a collection of character data. *str* (String types) hold sequence of characters and are also called as string literals. 
* They are immutable i.e items/values (here characters) cannot be altered/deleted once created. But you can use *replace()* method of string to alter and *strip()* to remove specific sub-string. 
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

## Indexing: acessing item/character from string
print(sample_str[0]) # T
print(sample_str[2]) # i
# negative indexing: starts from 1 and not 0
print(sample_str[-1]) # s
print(sample_str[-5]) # c

## Iterating: going over item by item from a string
for x in sample_str:
  print(x)

## Slicing: for creating sub-strings, syntax is [start_index:end_index:step] 
# start_index is starting index of sub-string, default is 0
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
# joins a list of strings to a single string with given string key(which is '.' here)
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
### 2.3 Boolean Type (bool)
* Has only 2 values *True* and *False*. *True* is also 1, so 4 + *True* is 5. *False* is also 0, so 4 + *False* stays 4. Boolean values *True* & *False* are also referred as Truthy & Falsey values when evaluating.
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
### 2.4 Binary Types (byte)
#### 2.4.1 Little bit about Computer Memory
A computer stores data in its memory in binary (0's and 1's) format only. A bit (binary digit) is the smallest possible unit of data in a computer. Typically group of eight bits is known as a byte. Eg 10100101 this is a byte. A single byte represents numbers between 0 (00000000) to 255 (11111111), so 256 (2^8) bits in total, similarly a Kilo Byte (KB) is 1024 bytes, a Mega Bytes (MB) is 1024 KB and so on. A file is a sequence of these bytes, the size of a file is determined by the number of bytes in them. A programming language usually deals with two types of file, a Text file and Binary file. Text file contains characters data and Binary files contain well, binary data. For example images, documents, executables & compressed files, compiled programs etc are called binary files. Now to store characters (Text files) in a computer, encoding schemes are used. It is simply a way to represent Character (human readable data) in Binary format (computer readable), various schemes such as UTF-8 or UTF-16 are used. A Encoding scheme has to follow a Character Set (such as ASCII/ISO/UTF/Unicode), which is basically a table of unique numbers assigned to the letters, numbers and symbols used in languages or on keyboards.

#### 2.4.2 Two functions to convert a string to bytes.
#### 1. bytes(source, encoding, errors) => bytes
**Parameters**:</br>
  * *source* object: Any object.
  * *encoding* str: Provide encoding scheme for the source string.
  * *errors* str: Way to handle errors for source data.
#####
**Explanation**: This function creates a immutable object consisting of Unicode (character set containing all major languages characters) 0-256 characters.
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
  * *encoding* str: Provide encoding scheme, if source is string.
  * *errors* str: Way to handle errors, if the source is a string.
#####
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
### 2.5 User-defined Data Type
* User defined data type, are used to create a new data type by combining the built-in data types. Unlike in C/C++ Python doesn't have *struct*, but what it does has is classes, which can be utilized to do the same.
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
# But will not that be a Data structure? Nope?
```
* Create a slightly better data type that can check the inputs.  
```Python
class MyDataType:
  def __init__(self, x, y):
    """__init__ is antoher 'magic method', which enables usage of constructor in python, more on this later."""
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
#### 2.6 *None* Object
* *None* is similar to *null* in C/C++/Java it indicates that something has no value, but there are some differences. In in those languages *null* refers to a pointer that doesn't point to anything and it is also *0*, not in Python. In Python, *None* is not "0", its a object itself. It is a object of *NoneType* class and is a singleton i.e only one instance is created of *None* in a program. 
* *None* is often use in absence of value in a variable, as a default value in a function parameter and is returned by default by a function if no return statement is provided or any condition is met.
* Creating a None type.
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
#### 2.7 Some built-in functions: [type()](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#1-typeobject--str), [isinstance()](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#2-isinstanceobject-class--bool), [id()](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#3-idobject--int), [dir()](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#4-dirobject--list).
#### 1. type(object) => str
**Parameters**:</br>
  * *object* object: Any object.
#####
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
#####
**Explanation**: This function checks if a object is an instance of a particular class. Returns True/False.
```Python
a = 23
print(isinstance(a, int)) # True
print(isinstance(a, float)) # False
print(isinstance(a, str)) # False
```
#### 3. id(object) => int
**Parameters**:</br>
  * *object* object: Any object.
#####
**Explanation**: This function returns the object identity which is the object’s address in memory. The returned object id varies across programs/systems, so will not be the same anytime. 
```Python
my_float = 50.0
# object id will differ each time with program
print(id(my_float)) # 1875526208176
```
#### 4. dir(object) => list
**Parameters**:</br>
  * *object* object: Any object.
#####
**Explanation**: Returns a list containing names of variables/functions/classs in a object. This function also works on modules, as modules are also objects.
```Python
## names under current local scope
print(dir())

## list of object's attributes
print(dir(int))
print(dir(my_obj))
```

## 3. Data Structures
#### Wikipedia suggests </br>
  > In computer science, a data structure is a data organization, management and storage format that enables efficient access and modification.

Simply put data structures are used to organize data in a way that it can be stored/retrieved efficiently. Data can be any data types or even other data structures. Different data structures have their advantages/disadvantages in terms of accessing/storing/removing data speed, so they should be used as per the task/ease. They can also be called literal collections. In Python, you can't/don't need to declare the size of the built-in data structures beforehand, they are dynamically scaled/released automatically in background. 
#### Composite Data Type, Abstract Data Type and Data Structures differences.
  1. Composite Data Types are data structures but not all data structures are composite types.
  2. Abstract Data Type define only the mathematical model of the implementation of a data type i.e they only exist in pseudo code.
  3. Data structure are the actual coded/coding implementation of the pseudo code i.e they are implemented in a programming language's code.
#### 
The built-in Data Structures explained below are [list](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#31-list), [tuple](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#32-tuple), [dict](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#33-dict) and [set](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#34-set). Additionally we'll also take a look at some of their alternatives. Later we'll check out some more built-in functions which provide additional useful operations.
### 3.1 List
* By the name it may seem a LinkedList data structure but its not, *list* is a array (Dynamic Array) like implementation in Python. *list* is a ordered collection of sequence of items, which can be of any data type or objects.
* It is Mutable (values can be changed). Indexing, Slicing is supported and it is a iterable object (more on this later). 
* They are preferred in most use cases. Where indexing, looping over some items is required lists are used. 
* Creating a list.
```Python
# insert items inside '[]' brackets
my_list = [1,1,3,'a','cab boy',4.0]
# or create empty list
some_list = [] # using list() function
```
* Basic operations on list.
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
* Joining and multiplying list.
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
* Indexing, iterating, slicing operations on *list*.
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
* List comprehension.
```Python
## List comprehension: create a new list in a single line 
# Note: range function returns sequence of integers, we'll learn more on range later 
my_list1 = [x for x in range(10)]
# this is similar to 
my_list1 = []
for x in range(10):
    my_list1.append(x)
# list comprehension saves lines of code
my_list2 = [[y for y in range(x)] for x in range(5)] # it can be nested
my_list3 = [abc for abc in range(10) if abc > 5] # if condition
my_list4 = [True if z > 5 else False for z in range(10)] # if with else condition
# try printing each of the list
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
* Some functions on *list*.
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
* **Time Complexity**</br>
indexing, appending (to the end) and get_length are O(1).</br>
deleting, poping, inserting (at position), iteration are O(n).</br>
#### 3.1.1 Array
* *list* allows to hold data of any data-type/object which is great, but this means the data is usually less tightly coupled, so they end up taking more storage. To hold large amount of data efficiently one can utilize the *array* types.
* Similar to list they are mutable, iterables, they support indexing, slicing, they even share almost all *list* operations. The difference is they allow storing data of limited types only such as characters, integers or floating point numbers and one data type per array. It has to be one of in C language's Data-Types (eg. *signed int*/*unsigned float*).
* They are not part of the core Python, so they need to be imported from the *array* module and are required to be declared first. When declaring we need to define the type of data the *array* can contain, it can be one of types mentioned in the table shown [here](https://docs.python.org/3/library/array.html#module-array). 
* Create a array.
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
# we can see difference in bytes, array consumes less space compared to list
```
* Indexing, iterating and slicing operations on *array*.
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
### 3.2 Tuple
* Are ordered collection of sequence of items similar to lists. But unlike list they are Immutable (items cannot be altered/deleted), so they are preferred when data should not be changed. They are data efficient than *list* and are slightly faster than *list*. Indexing, Slicing is supported and they are iterable objects just like lists, but there no tuple comprehension (it becomes a generator). 
* They are mostly used to store different data type items, unlike list which are mostly used for storing similar items, but either way is also valid. 
* Create a *tuple*.
```Python
# insert items inside '()' brackets
my_tuple = (1,2,3,'we','are','one',5.0)
# this is also valid but using the parenthesis is cleaner 
my_tuple = 1,2,3,'we','are','one',5.0
# create empty tuple
some_tuple = () # or using tuple() function
```
* Basic operations.
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
* Joining and multiplying *tuple*.
```Python
## Joining: join two or more tuples
my_tuple1 = (34,65,23) + (34,34)
print(my_tuple1) # (34, 65, 23, 34, 34)

## Multiplying: using '*' operator on a tuple
my_tuple1 = (34,65,23) * 2
print(my_tuple1) # (34, 65, 23, 34, 65, 23)
```
* Indexing, iterating and slicing operations on *tuple*.
```Python
my_tuple = (1,2,3,'we','are','one',5.0)

## Indexing: acessing item/character from tuple
my_var = my_tuple[0] # okay
# my_tuple[0] = 23 # not okay because Immutable, raises TypeError

## Iterating: going over item by item from a tuple
# for var in my_tuple:
#   print(var) # (1,2,3,'we','are','one',5.0)
# checking if some value is present in tuple
if 5.0 in my_tuple:
  print('printed')

## Slicing: for creating sub-tuple, syntax is [start_index:end_index:step] 
print(my_tuple[3:5]) # ('we','are')
print(my_tuple[5:]) # ('one',5.0)
print(my_tuple[:3]) # (1,2,3)
print(my_tuple[:5:2]) # (1,3,'are')
# negative indexing
print(my_tuple[:-4]) # (1,2,3) 
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
# Returns first index of value.
print(my_tuple1.index(2)) # 1
```
* Some functions on *tuple*.
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
* **Time Complexity**</br>
indexing, appending (to the end) and get_length are O(1).</br>
deleting, poping, inserting (at position), iteration are O(n).
#### 3.2.1 NamedTuple
* As the name suggest, they are named *tuple* i.e regular tuples that support field/item names (and also indexes). So along with indexing they support accessing fields/elements using their names with the '.' operator (just as accessing the class variables). 
* They are sub-class of *tuple*. When instantiated they return a new *tuple* sub-class named \<typename\>. This new sub-class can be used to create tuple-like objects which are also immutables, indexable, iterables and are as data efficient as regular *tuple*.  
* They are not part of core Python and need to be imported from the *collections* module. They provide more readable, self-documenting code over the regular *tuple* where they are intended. 
* So why not use custom class anyway? If you're okay with immutable type, *nametuple* save you most of the hustle to write the code for operations (like iterable, indexing) with the convenience of naming access. 
* Create a *namedtuple*.
```Python
from collections import namedtuple
import sys

# create a tuple sub-class 
# first parameter is typename, string which is name of tuple sub-class
# second parameter is field_names, iterable/string which has names of fields/variables/data tuple will contain 
Name_tup = namedtuple("mynamedtuple", ['a', 'b'])
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

# like regular tuple immuatable
name_tup1[0] = 32 # TypeError
```
* Indexing, iterating and slicing operations on *namedtuple*.
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
# convert to dict
print(name_tup1._asdict()) # {'aa': 42, 'bbk': 60, 'cab': 52}
# replace the value, creates and returns a new mynamedtuple instance
print(name_tup1._replace(aa=32)) # mynamedtuple(aa=32, bbk=60, cab=52)
```
### 3.3 Dict
* Longform Dictionary in Python, are unordered collection of key & value pair of items. *dict* are mutable, iterable, but Indexing/Slicing doesn't work as their order don't matter. 
* *dict* use Hashtable to store data with a key & value. A hashtable uses a hash function which given a key generates a index to an array like Data Structure, which store the actual values. So instead of indexing, these keys are used to access values. This behaviour help hashmap to do almost all operations in O(1) making them very efficient for storing and retrieval operations. 
* Keys in *dict* should be hashable i.e have a hash value that does not change thoughout its lifetime, all immutable objects are hasables. Values have no restriction, they can be any object. 
* They are used in Dynamic Programming and generally where values are supposed to have some key associated with them.
* Create a *dict*.
```Python
# insert keys & values inside '{}' brackets
# Note: key & value are seperated with ':' colon. i.e key:value
my_dict = {'e':23, 'w':65, 'q':52}
# create empty dict
my_dict = {} # or using dict() function
```
* Basic operations.
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
* Joining and iterating operations on *dict*.
```Python
my_dict = {'a':34, 'b': 42}
my_dict1 = {'z':5, 'y':3, 'x':4}

## Joining: join two dicts, '+' operator is not supported
# using the update method of dict
my_dict.update(my_dict1)
print(my_dict) # {'a': 34, 'b': 42, 'z': 5, 'y': 3, 'x': 4}
# or use "my_dict | my_dict1" 
print(my_dict | my_dict1) # {'a': 34, 'b': 42, 'z': 5, 'y': 3, 'x': 4}
# or unpack them in a new dict 
print({**my_dict, **my_dict1}) # {'a': 34, 'b': 42, 'z': 5, 'y': 3, 'x': 4}

## Iterating: going over item by item from a dict
# use the items method for both keys,values unpacking
for k,v in my_dict1.items(): 
   print(k, v) # {'z':5, 'y':3, 'x':4}
```
* *dict* comprehension. 
```Python 
my_dict = {x:x*x for x in range(5)} # generating keys and values on the go
print(my_dict) # {0: 0, 1: 1, 2: 4, 3: 9, 4: 16}
# another way is using the zip function
my_keys = ['a', 'b', 'c']
my_values = [1,2,3]
my_dict = {k:v for k,v in zip(my_keys, my_values)}
```
* Some methods of *dict*.
```Python
my_dict1 = {'a':1, 'b':2, 'c':3}
my_dict2 = {'z':50, 'y':40, 'x':30}

# returns a dict_keys object, it contains dict's keys, it is iterable, you can also convert it to list
print(my_dict1.keys()) # dict_keys(['a', 'b', 'c'])
# returns a dict_values object, it contains dict's values, it is iterable, you can also convert it to list
print(my_dict1.values()) # dict_values([1, 2, 3])
# returns a dict_items object, has keys & values, you know the rest
print(my_dict1.items()) # dict_items([('a', 1), ('b', 2), ('c', 3)])
# removes item(key,value) given key, which is 'a' here and returns value
print(my_dict1.pop("a")) # 1 
my_dict1.clear() # removes all items of dict
```
* Type conversion examples.
```Python
keys = [1,2]
values = [2,3]
my_dict = dict([keys, values]) # list to dict
my_dict = dict(((1,2), (2,3))) # tuple to dict
```
* **Time Complexity**</br> Dicts are implemented using HashMaps, so most operations are O(1) and depending on implementation worst case O(n).</br>
insert, add, delete is O(1).</br>
iteration is O(n).
### 3.4 Set
* Are unordered collection of non repeating sequence of immutable items. Similar to *dict*, *set* is mutable, iterable, but Indexing/Slicing doesn't work. 
* Items/Members inside a set should be hashable (must have a *\_\_hash\_\_()* method), its hash value must never changes during its lifetime. Numbers, strings & tuple (with hashable items in them) are hashable. This behaviour allows sets to check if a particular object is unique from other members and also to perform operations like intersection, union. 
* Sets are used to maintain unique values and in membership testing i.e check if the variable is already present in the set. Like in BFS/DFS algorithms for checking visited nodes.
* Create a *set*.
```Python
# insert values inside '{}' brackets
my_set = {9,1,5,2,20} # Notice: dict like parenthesis but without keys
# items order don't matter, so while printing order might differ
print(my_set) # {1, 2, 20, 5, 9}
# create a empty set
my_set = set() 
```
* Basic operations.
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
* Joining and iterating operations on *set*.
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
# create a copy of a set
my_copy = my_set1.copy() 
# removes all members of set
my_copy.clear() 
# checks if my_set2 is a subset of my_set1
print(my_set1.issubset(my_set2)) # False
# checks if my_set2 is a superset of my_set1
print(my_set1.issuperset(my_set2)) # False
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
* **Time Complexity**</br> Sets are implemented using hash tables, so pretty much all operations should be O(1) and worst case when Hash collision occurs O(n).</br>
adding, checking (with *in* operator) and removing are O(1).</br>
iterating is O(n).</br>
union is O(m+n).</br>
intersection is O(min(m,n)), worst is O(m\*n).<br/>
#### 3.4.1 FrozenSet
* They are *set* but only difference is they are immutable. So once a *frozenset* is created the elements/members cannot be removed/added. Rest is pretty much similar to *set*, they are non repeating sequence of items, unordered, iterable and no indexing/slicing is supported. They can be created using any iterable object.
* Create a *frozenset*.
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
### 3.5 Extras
#### 3.5.1 Stack
* Stacks are LIFO, Last In First Out Data Structures. Elements go in and out from a single direction only. Main operations/methods of Stack are adding an element which is called a *push* operation and removing a element which is called a *pop* operation. Other operations are *isEmpty*, *isFull* and *peek* etc.
* The main operations of Stack can be easily performed using *list*'s available methods. And as *append* is ~O(1) and *pop* is O(1), *list* are good enough for Stacks.
```Python
# create a stack
my_stack = []
## add/remove operation
my_stack.append(20) # push: append at top
my_stack.pop() # pop: remove at top
```
#### 3.5.2 Queue
* Queues are FIFO, First In First Out Data Structures. Elements go in one direction and go out from other direction. Main operations/methods of Queue are adding an element which is called a *enqueue* operation and removing a element which is called a *dequeue* operation. Other operations are *isEmpty*, *isFull* and *peek* etc. Variants of Queue are circular queue, priority queue and dequeue. 
```Python
# create a queue
my_queue = []
## add/remove operation
my_queue.append(20) # enqueue: append at rear
my_queue.pop(0) # dequeue: remove at front
```
* Python also has *dequeue* (double ended queue) Data Structure which can also be used as a normal Queue. They are implemented as doubly linked list and support adding & removing from both sides (front & end), they are efficient at add/remove from left (front) operation. Other operations have similar performance as *list*. 
* For Queues we only need append at the end and pop/remove at the front, both of which are O(1) for *dequeue* which is good enough. They are not part of core Python and need to be imported from the *collections* module.
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
* Priority Queues are used when the elements are supposed to have some priority associated with them. So instead of using FIFO like normal queues, Priority Queue use priority, elements with highest priority are taken out first. In order to work the data has to be comparable (same type).
* Python provides *heapq* which are Priority Queues implementation, they support only min-heap (smallest element has highest priority). The *heapq* module implement the Heap Data Structure (Binary heap) which is the most efficient way of implementing a Priority Queue. A Heap DS is a complete binary tree (all levels are filled except the leaf positions) that satisfies a heap property, which is nothing but the max/min criteria for getting elements out. 
* A Heap DS has a *heapify* function, it is responsible for constructing a Heap DS i.e constructing/adding elements in a binary tree for sorting. Three main operations *add*, *delete* and *peek* are explained below:
  1. *add*: First traverse to last (leaf) empty position, add the element there and heapify the tree.
  2. *delete*: Select the index to be deleted, replace with last element (rightest leaf), remove the last element and heapify the tree.
  3. *peek*: Traverse to the rightest leaf position, return the element.
* A Priority Queues is useful in tasks such as prioritizing, scheduling, load balancing etc. Other implementation of Priority Queue is in *queue* module, named *PriorityQueue*, you can also use normal *list* for doing the same utilizing the *sorted()* function, but *heapq* operations are efficient. 
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

# use heapify function to construct a Heap DS or sort elemnts
my_pq = [34,6,23,67,23,78]
heapq.heapify(my_pq)
print(my_pq) # [6, 23, 23, 67, 34, 78]
```
* Apart from the above Data Structures there are some more that I haven't mentioned, you can find them in the [collections](https://docs.python.org/3/library/collections.html) module. 
### 3.6 Some built-in functions: [range()](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#1-rangestart_index0-end_index-step1--range), [enumerate()](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#2-enumerateiterable--tuple), [zip()](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#3-zipiterable--zip), [sorted()](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#4-sortediterable-keynone-reversefalse--list), [filter()](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#5-filterfunction-iterable--filter) and [map()](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#6-mapfunction-iterable--map).
#### 1. range(start_index=0, end_index, step=1) => range
**Parameters**:</br>
  * *start_index* int: The start index for iteration.
  * *end_index* int: The stopping index for iteration.
  * *step* int: A skipping index in iteraton.
#####
**Explanation**: This function returns a sequence of length *start_index(0 by default)* to *end_index(is a required argument)*. *range()* function returns a range object, which is iterable, supports indexing and is immutable. It is mainly used in loops, where a certain number of times a loop should work, like for iterating to the length of an array in C/C++/Java.
```Python
## examples
# create a range object length 20
print(range(20)) # range(0,20)
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

## looping range object
for var in range(5): 
  print(var) # [1,2,3,4,5]
# reversing the order
for var in range(5, -1, -1): 
  print(var) # [5,4,3,2,1]
```
#### 2. enumerate(iterable) => tuple
**Parameters**:</br>
  * *iterable* iterable: Iterable object containing items.
#####
**Explanation**: This function returns a *enumerate* object given a iterable, each item is a tuple which contains index & value. Index is in range from 0-length of the list and value is a item from the list. The *enumerate* object is iterable and indexing/slicing is not supported. Similar to *range*, *enumerate* is motly used in iteration of loops. 
```Python
## examples
my_list = [100,200,500,100]
# create a enumerate object from a list
print(type(enumerate(my_list))) # <class 'enumerate'>
# converts to list and indexing the first value, the output tuple is index & value
print(list(enumerate(my_list))[0]) # (0,100) 

# looping over enumerate object
for i, val in enumerate(my_list):
  print(i) # 0,1,2,3
  print(val) # 100,200,500,100
```
#### 3. zip(\*iterable) => zip
**Parameters**:</br>
  * *iterable* iterable: Iterable object containing items, '\*' denotes a function can take multiple input objects.
#####
**Explanation**: This function returns a zip object given single/multiple iterables, each item is a tuple which contains n (number of input iterables) length elements. When provided multiple number of iterables, the length of returned *zip* object is equal to the length of the smallest iterable. *zip()* is commonly used to unpack values from multiple iterables simultaneously in a loop.  
```Python
## examples
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
  * *key* iterable: Optional function to fetch values from a your iterable object.
  * *reverse* bool: Whether to reverse the sorting.
#####
**Explanation**: This function returns a sorted list given a iterable object. Sorting is O(nLogn). *key* parameter takes a function which is then used to extract the elements, helpful when a object has some inner structure. Also has *reverse* parameter, which is used to do reverse sorting if it is set to *True*.
```Python
## examples
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
# Notice: "my_fun" is passed not called, we'll learn about this in function's section.
```
#### 5. filter(function, iterable) => filter
**Parameters**:</br>
  * *function* function: Your function for filtering.
  * *iterable* iterable: Iterable object containing items.
#####
**Explanation**: This function takes a input function & a iterable and applies that function on every item of that iterable. The return value of filter's input function has to be boolean. *filter()* returns only if *True* condition is met, if *False* is met nothing is returned, also if no condition is met nothing is returned. *filter()* as the name suggests, is used to filter out non-required values from a iterable object. *filter()* returns a filter object which iterable and indexing/slicing is not supported.
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
#####
**Explanation**: This function takes a input *function* & a *iterable* object and applies that *function* on every item of that *iterable*. As name suggests, a function is mapped to each element of an *iterable*. So unlike *filter()*, *map()* returns the direct value returned by our input *function*.
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

## 4. Flow Control
Flow Control is used for making decisions in programs. This decision making helps turn the output of the program based on the executed conditions. Python supports all the general statements for conditions and loops except *switch*. 
#### 4.1 *if...else* statement
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
* Truth value testing, check whether a object is a Truthy and Falsy. Thier values are given below(comma separated).
```Python
# Truthy(True values): non-zero numbers(including negative numbers),True,Non-empty Data-structures/sequences
# Falsy(False values): 0,0.0,0j,None,False,[],{},(),"",range(0)

my_var = 10
my_var1 = None

## Some Examples
# my_var is a non-zero number, which is Truthy, so 'if' will execute
if my_var: 
  print("printed") # printed
# my_var1 is 'None', which is Falsey, so 'if' will not execute  
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
#### 4.2 *for* statement
* Is used for looping purpose, to iterate a certain number of time. Python supports regular to the length looping using the *range* object or there is more pythonic way of looping. 
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
#### 4.3 *while* statement
* A *while* loop executes till its given condition is valid and stops execution when its invalid. *while* loops are more flexible than *for* loops and they can be executed infinitely by setting the condition to *True*, something that is not possible with *for* loops.
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
#### 4.4 *break* and *continue* statements
* **break**: Use to break from iteration/loop. 
* **continue**: Use to continue to next iteration in loops.
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

## 5. Exception Handling
As humans while writing code we are prone to make mistakes/errors, causing programs the program to crash or behave incorrectly. The process of finding and fixing the errors/bugs is called debugging. A programmer usually spend most of their time debugging and it becomes very essential to spot their types and fix them accordingly. As programs get larger in size errors might not be that straightforward to fix/spot and it might take huge amount of time in debugging. In Python errors are called Exceptions, it is a Pythonic way of saying something exceptional has occurred and it need to be handled. All exceptions are instances of classes derived from *BaseException* class. User code can *raise* (throw in Java/C++) any built-in exceptions. User can also sub-class built-in exception classes to define their own Exceptions. Although, Python docs recommends sub-classing from *Exception* class or its sub-class only. 
### 5.1 Three Types of Errors/Exceptions
#### 1. Compile Time Errors
* These exceptions are raised due to the syntactical mistake in code and are usually easier to spot and fix. They are raised when the Python Interpreter is compiling a program. A user at this point has to fix the error to be able to execute the program. 
* The interpreter raises a *SyntaxError*/*IndentationError* and also indicate the line causing the error when found. *SyntaxError* is raised due missing colon in compound statements, invalid condition checking in *if..else* statements, missing string quote or bracket operator's termination, empty *import* statement, missing/misspelling keywords, empty function/class definition etc. *IndentationError* is raised when using a invalid indentation in compound statements.    
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
* Are raised at runtime due to some illegal invocation/operation on objects. If a program is syntactically correct, interpreter starts to execute and if a exception is raised it is a runtime error. The program to the part of runtime error line is executed, rest of the execution is stopped. Along with the Exception type interpreter also prints appropriate message on the screen. A user at this point can fix the error or can bypass and continue rest of the execution by using Exception Handling. 
* **Some common runtime errors in Python.**
  1. **AttributeError**: Raised when an attribute reference or assignment fails.
  2. **TypeError**: Raised when an operation or function is applied to an object of inappropriate type.
  3. **ValueError**: Raised when an operation or function receives an argument that has the right type but an inappropriate value.
  4. **RecursionError**: Raised when the maximum recursion depth is exceeded.
  5. **IndexError**: Raised when a sequence subscript is out of range.
  6. **KeyError**: Raised when a mapping (dictionary) key is not found in the set of existing keys.
* For more exceptions check the exception hierarchy on [python doc](https://docs.python.org/3/library/exceptions.html#exception-hierarchy). 
* Python also has a [*warnings*](https://docs.python.org/3/library/warnings.html#warnings.warn) module which is a sub-class of *Exception* class and unlike all other exceptions they don't terminate the program. They are only meant to warn the user by showing some message.
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
```
#### 3. Logical Error
* Are not raised, but the program output is not an expected behaviour. They usually get difficult to fix as the program grows. They occur when the program logic is incorrect. Common examples such as using wrong variable/operator, calling wrong function/method instead, sub-classing a wrong class etc.  
* To avoid these errors it is recommended to debug a program normally or use unit testing framework [unittest](https://docs.python.org/3/library/unittest.html#module-unittest) to test the program before integrating it into a application.
```Python
## Example 1: accessing wrong index
my_list = [82,92,38,42,54,23,64,87]
# printing last 3 values
print(my_list[-2:]) # [64, 87]
# here program has no error, but instead of printing 3
# its only printing 2 numbers, because we provided wrong index
# this example is not hard to fix, but in larger programs it consumes a lot of time to find
# which object/variable/function must have caused the wrong output 
```
### 5.2 Handling the Exceptions
* Exception handling is a way to handle the Runtime errors. Exception/Error handling helps to continue the program execution while handling the Errors/Exceptions on the way. If you know a particular block of code is likely to cause an error, you can integrate that code inside a *try..except* block and provide a behaviour for the Exception.
* Python has the *try* block to try the suspicious code, *except* (catch in C/C++/Java) block to add behaviour when such error occurs. Optionally Python has a *else* block which executes only if no exception was occurred. Then there is a *finally* block which executes if/not an error is occurred.  
```Python
## use traceback built-in module for printing Tracebacks
import traceback

## Example 1: catching specific errors
try:
  a=10
  a = "this"+a
except (TypeError, ZeroDivisionError):    
  print("ZeroDivisionError/TypeError occured")
  # printing traceback
  traceback.print_exc()
  
## Example 2: catch any exception with 'Exception' class, it is base class of all exceptions
# lets cause stackoverflow/RecursionError in python
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
* *finally* and *else* statements/conditions.    
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
### 5.3 Raising the exceptions
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
### 5.4 **assert** statement
* *assert* helps in debugging, it is used to check if certain condition is true, else *raise* a *AssertionError*.
```Python
a = 10

# Example 1: check if a is 10
assert a == 10 # No error raised

# Example 2: check if a is 30
assert a == 30, "Your error mesage here" # AssertionError
```

## 6. Functions
### 6.1 Function Basics
* A function is a block of code (group of statements) used to perform some operation/task on some data/variables/sequences. A function may or may not have parameters, it may or may not return something (in Python, *None* is returned by default if *return* statement is not defined). Functions do not require return type declaration in Python. Functions are the callable objects in Python i.e they can be called with rounded brackets parenthesis.
* **Parameters vs Arguments**: Parameters are the ones which are defined in function definition, arguments are the ones which are passed when a function is called. 
* Functions in Python are first class, which means they behave just like an object, they can be stored in a variable or can be passed as a argument to other functions.
* Defining and calling functions.  
```Python
# Example 1: Non-parameterize function which returns nothing 
# use the 'def' keyword to define a function followed by its name 
def my_function1():
  # do something
  pass # to ensure the program runs this empty function   
  # if the function is not empty 'pass' is not required at all
  
# Example 2: function with parameter which returns nothing
def my_function2(var1, var2):
  pass
# alternative way is to describe the input/return type hints
# As they are just hints, it does not matter what is send/returned
def my_function2(var1: int, var2: int) -> None: 
  pass
  
# Example 3: function with default parameters and return statement
# default parameters should always follow later
def my_function3(var1, var2, var3, do_something=False): 
  if do_something:
    # did something
    return var1 + var2 + var3
    
# calling a function without a return statement, returns None by default
print(my_function1()) # None
# calling a function and passing the arguments
print(my_function3(30, 20, 10, do_something=True)) # 60
# check if it is a function using the built-in callable() function
print(callable(my_function1)) # True
```
* First class functions behaviour.
```Python
def square_or_some_fun(number, some_fun=None):
  if some_fun:
    # if some_fun is a function it can be callable 
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
# 'my_var' points to the 'cube_num()', so calling 'my_var' is same calling 'cube_num'
print(my_var(2)) # 8

# passing a argument to another function
print(square_or_some_fun(2)) # 4 
# pass a function as argument
print(square_or_some_fun(2, my_var)) # 8
# passing a list at some_fun will raise TypeError
print(square_or_some_fun(2, [4,4])) # TypeError: 'list' object is not callable
```
### 6.2 Functional Programming
* Python like C++ is a multi-paradigm and support functional programming. In functional programming, input flow through various functions and outputs are generated based on their behaviour. As functions don't have an internal state like objects, previous output cannot be re-gained given different input (as state/data cannot be saved in a function), they are just meant to perform some operation on some data and return the output. 
* A function is pure (without any side effect) if it does not rely any mutable types, global variables or some objects' attributes i.e relying solely on input arguments and generating the output only based on them. This adds advantage in parallel programming, testing, making programs more modular and requiring less debugging overall.
* When designing systems, depending on the scenario specific paradigm apporaches are preferred, todays systems are usually build with multi-paradigm in mind with say some computational part written with functional programming & GUI parts designed with OOP.
### 6.3 *pass* statement
* It is to declare a function/method with a empty body without raising error and later implement the code for the function.  
```Python
# Example 1: empty function body
def my_fun():
  pass
```
### 6.4 Packing and Unpacking
1. **Packing**: It is when we pass more than the number of defined variables to a function. It is useful when we are not sure about the exact number of arguments required for some operation. They should always be the last parameters in a function (else they'll contain all the values). 
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

## Example 2: packing kwargs into a dict
# Notice: the ** operator before kwargs variable
def my_fun2(x,y,**kwargs):
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
print(my_fun2(2,3)) # 5   
# passing more than 2 arguments, now all values after 3 go into kwargs
# Notice: arguments should have some unique name
print(my_fun2(2, 3, a=2, b=4, d=4, any_name=5, my_var=8)) # 28
```
2. **Unpacking**: It is when a *list/tuple/dict* is passed, which then unpack or gets extracted as function arguments. Now passing a *tuple/list* can be done with '\*' operator followed by sequence's name, generally as *\*args*. Passing a *dict* requires '\*\*' operator followed by sequence's name, generally as *\*\*kwargs*.
```Python
def my_fun1(a,b,c,d):
  return a+b+c+d

my_list = [1,2,3,4]
my_dict = {'a':1,'d':4,'b':2,'c':3}

## Example 1: unpacking from list/tuple, list here, notice the * operator
print(my_fun1(*my_list)) # 10

## Example 2: unpacking from dict, notice the ** operator
print(my_fun1(**my_dict)) # 10 

# same goes for built-in functions too, "print()" function unpacks the list values
print(*my_list) # 1,2,3,4
```
### 6.5 Recursion
* Recursion is when a function calls itself. It is a powerful tool that works on particular set of problems where a problem can be divided in simple repetitive chunks. 
* Recursion uses system stack to maintain the memory required for the recursive calls, this usually leads to higher memory usage compared to iteration.    
* Recursion requires to handle the *StackOverFlow*, the complexion in debugging and also it can sometimes be hard to formulate a recursive solution.
* There are certain advantages such as reduction in size of code when a iterative solution is lengthy/complex, there are situations were recursion is a easier/better solution. Also if implemented correctly using Dynamic Programming or dependent on a problem it reduces the time complexity and also some memory usage.
* To identify a recursion problem, one has to identify the smaller repetitive parts of a solutions. A recursive solution usually form a tree like structure where the branches are sub-problems. After identifying the sub-problems one has to identify the base case, which is the condition where a recursion program stops itself. This is very important or else the program will lead to causing a StackOverFlow error. Finally the sub-problem solution with the base case is sequenced correctly to form a recursive solution.  
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
# In our recursion function recursive calls are made till n is 0, so here we begin from the last line
5 + recur_sum(4) -> 10 = 15 # finally 15 is the result, which is returned to the original caller
4 + recur_sum(3) -> 6 = 10 # same thing here
3 + recur_sum(2) -> 3 = 6 # similarly the result 3 is returned here from previous call and added with 3
2 + recur_sum(1) -> 1 = 3 # the result 1 is returned here from previous call and added with 2
1 + recur_sum(0) -> 0 = 1 # this is the last call, as the base case is hit, now the return calls are made
'''
```
* Recursion can be overwhelming even for intermediate programmers, recursion requires practice on well... recursion. [Here](https://web.stanford.edu/class/cs9/lectures/06/Recursion%20Problems.pdf) is list of some recursive problems. If you are not that familiar with recursion [here](https://www.youtube.com/watch?v=ngCos392W4w) is a nice video explanation and further you can also start practicing on online platforms like [leetcode](https://leetcode.com/tag/recursion/)/[hackerrank](https://www.hackerrank.com/domains/algorithms?filters%5Bsubdomains%5D%5B%5D=recursion).
### 6.6 Anonymous functions
* Is a function that is defined without a name (without using *def* keyword in python). Anonymous function can be created using *lambda* keyword, it is a single line function. This function helps in reducing the line of code required for defining a short function. 
```Python
## Example 1: return sum of 2 numbers 
# syntax => lambda arguments : expression
my_function = lambda a,b: a+b  
# Notice: 'a+b' is also the return statement without using 'return' keyword 

## calling the function
print(my_function(1,1)) # 2 
```
### 6.7 global and nonlocal statements
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
  # Its because in Python you don't declare the variable's scope  
  # Python tries to figure out the scope of a variable by watching if it has some assignment in this scope
  # if it does that variable is considered a local variable (even if same named global variable is present)
  # here my_var2 has assignment in below lines so its a local variable which we can't access before assignment    
  # if you remove the assignment of my_var2 it will be considered global and you can access it like my_var3 

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
    my_var1 = 30 # modifying for local scope
    my_var2 = 40 # modifying for some_fun() scope
    print(my_var1, my_var2) # 30, 40

  some_nested_fun()  
  # similar to global keyword now my_var1 is not modified but my_var2 is
  print(my_var1, my_var2) # 10, 40    

some_fun()
```
### 6.8 Decorators
* They are used to wrap another function around to basically extend its functionality. It is simply running a function inside another function, like a nested function. This allows to extend the wrapped function's behaviour without actually modifying the function itself. These decorators are part of "Python syntactic sugar". Using '@' prefix a function can be decorated.
* This functionality is utilized using functions being first class in Python.
```Python
# defining the my_outer_func() which is a container function
def my_outer_func(some_func):
  # wrapper function goes here inside the container
  # my_wrapper_func() does something before/after calling some_func() 

  def my_wrapper_func(some_func_para1, some_func_para2): 
    # Notice: some_func's parameter should be pass to my_wrapper_func
    # so they can be accessed inside this scope
    # do something of my_wrapper_func()
    print(f"Product of two numbers is {some_func_para1 * some_func_para2}")

    # calling some_func(), do something in it and return something if required
    some_func(some_func_para1, some_func_para2) 
    # do something extra if want, return something if want
    
  # return this my_wrapper_func 
  return my_wrapper_func 

def my_fun(a,b):
  print(f"Sum of two numbers is {a+b}")

# calling my_fun gets sum of two numbers
my_fun(10, 20) # Sum of two numbers is 30
# but then i want to extend my_fun's functionality without changing its previous code

# pass the my_fun as some_func to my_outer_func
my_decorated_fun = my_outer_func(my_fun) 

# done, my_decorated_fun can now do both product as well as sum
my_decorated_fun(10, 20) # Product of two numbers is 200 # Sum of two numbers is 30

## now doing the same using decorators
@my_outer_func
def my_fun(a,b):
  print(f"Sum of two numbers is {a+b}")

# now calling 'my_fun()' normally, will automatically call/invoke my_outer_func()
my_fun(10,20) # Product of two numbers is 200 # Sum of two numbers is 30
```

## 7. Classes and Objects
### 7.1 Class
* **Class**: Is a blueprint/template of/for an object. It defines what the object holds (which variables/data types), what methods/operations that can be performed on that object. 
* **Instance**: Is a object of a class, it is created using the class. This instance/object is then used to perform operations/tasks that the class is intended to. A instance has its own state and it is also mutable, so modifying some variables will reflect changes for that particular instance.  
* **Constructor**: Is a function that is called when the class's object is instantiated/created, a class may or may not have a constructor. A default constructor does not have parameters and parameterized constructor does ahve parameters.
* **Methods**: Functions inside the class are called as methods.
* **self**: *self* resembles a instance of class inside the class methods. Similar to Java/Javscript's *this* keyword, it is used to access variables/methods of that instance. But in Python, a class method should have *self* object as the first parameter inside their definition. Although a argument is not required to be passed when calling such method. When a instance calls a method, the calling instance gets passed automatically by Python as *self* object to that method, explained more below. Also note that *self* is not a keyword, you can use any other name instead but it highly recommended to use *self* as a common practice for code readability. 
```Python
## Classes
# defining a class using the class keyword followed by its name 
# python defines a empty constructor automatically in background, if it is not provided
class MyClass: 
  # instance methods here
  def myfunction(self):
    # Notice: the self parameter in myfunction
    # do something  
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
#### 7.1.1 Three Types of methods in classes
1. **Class**: Class methods are bound to classes and not to instances. These methods have access to class state, they can read class variables/methods and modify class variables. Unlike instance only one copy is created, so every instance/class refers to this copy. Class methods can be accessed by both instances and classes. Unlike in Java, there is no *static* keyword, they are defined using *classmethod* as decoration (using *@classmethod* prefix). These methods should have class as first parameter, which can be of any name, *CLS* is preferred. This parameter further can be used to access other class variables/methods inside these methods. 
```Python
class MyClass: 
  # class variables: they not inside of any method 
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
```
2. **Instance**: Instance methods are bound to instances. They have access to both instance & class state, they can read class & instance variables/methods and also can modify class & instance variables. These methods can only be accessed by instance and not by class. A normal function inside a class is a instance method, these methods should have *self* as first parameter, which is used to access the instance's/class's variables/methods inside these methods.
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
```
3. **Static**: Static methods are also bound to classes. But they don't have access to instance/class state. They can't read/modify any variables beside thier local scope. These methods exist because that function has to belong to the class like a independent function but inside a class. They are defined using *staticmethod* as decoration (using *@staticmethod* prefix), these methods are not required to pass class as first argument.
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
* These methods begin & end with double underscore '\_\_' and are called magic/special/dunder methods in Python. This methods are used to enrich your object with more features. These are called "magic" methods because these methods are invoked indirectly, we do not need to invoke them directly.
* This methods are used to enable operator overloading, overriding built-in functions, accessing attributes etc. So using them in your custom class will enable more functionality but be careful to use them when it makes sense and document (add docstrings) their usage where required to avoid break in some functionality.   
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
  # define '__getitem__' for enabling iteration of items 
  def __getitem__(self, index):
    """Iterate through some_values""" 
    return self.some_values[index]

# create a instance to check these functionalities
my_instance = MyClass(239034, "Bob", 23, [10,45,32,67,32,655])
# testing the print functionality, '__str__()' is invoked when 'print()' is called 
print(my_instance) # id: 239034, name: Bob, age: 23
# similarly length functionality
print(len(my_instance)) # 6
# iterate through the instance 
for a in my_instance:
  print(a) # [10,45,32,67,32,655]
```
#### 7.1.3 Docstrings
* Holds the hints/suggestion working of a function/class provided by the developer. It begins just below start of a function/class definition. This is a way of documenting functions/class behaviours, useful stuff.
```Python 
class MyClass:
    """This is a docstring."""
    def my_fun():
        """This is what this method does..."""
```
### 7.2 Objects
* An object has its own attributes/variable (it can be any data-type/data-structure/object) and functions (methods).
* **"Everything in Python is an object"**, in Python's definition of object, some objects may or may not have meta-data/functions and are still objects. The Data-Types in Python have attributes/methods, Data Structures have their attributes/methods, Functions (are first class, as we saw earlier)/Classes also have their attributes/methods, so they are all objects. And as a property of an object they all can be assigned to a variable or passed to a function. So in a sense everything can be called an object. 
* We saw earlier how to create a instance of a class (i.e object) and what/how they can access variables and methods.
```Python
## data types are object
a = 30
print(type(a)) # <class 'int'>
# print attributes/methods of class int
print(dir(a)) 

## data structures are object
a = [30, 10, 20]
print(type(a)) # <class 'list'>
# print attributes/methods of class list
print(dir(a)) 

## functions are objects
def my_fun():
  pass
print(my_fun) # <class 'function'>
print(dir(my_fun))

## classes are objects
class MyClass: 
  def __init__(self):
    pass    
print(MyClass) # <class '__main__.MyClass'>
print(dir(MyClass))
```
#### 7.2.1 Iterables
* Iterables are objects that can be iterated using loops. A object having a special method *\_\_iter\_\_()* are considered to be iterables. They can be iterated as many times as required.
* Examples of iterables include sequence types such as *list*, *tuple*, *str*, *bytes* and *bytearray*. Also non-sequence types such as *dict*, *set* and others such as *file*, *range* objects.
* A custom class can implement *\_\_iter\_\_()* (which should return a iterator object) or *\_\_get\_\_()* (which is the special method for enabling indexing) method to make its object iterable. They can also become subscriptable/indexable if implemented using *\_\_get\_\_()* method. Example of non-indexable are *dict* or *set*.
* Iterables can be used in *for* loops and in built-in functions like *map()*, *zip()*, *filter()* etc.
* Checking built-in iterables.
```Python
# to check if list is a iterable, check if it has a __iter__() method using dir()
print(dir([1,2,3]))
# or using hasattr
print(hasattr([1,2,3], '__iter__')) # True
# check for tuple
print(hasattr((1,2,3), '__iter__')) # True
# check if set have __iter__ method
print(hasattr({1,2,3}, '__iter__')) # True

# iterables can be used in for loops
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
* Iterator objects can also be iterated using loops. They are also a iterable object, but the difference is they must have both *\_\_iter\_\_()* and *\_\_next\_\_()* special methods implemented (this is called the iterator protocol). The *\_\_iter\_\_()* method as we saw earlier returns a iterator object, the *\_\_next\_\_()* method here is to fetch the next element from the iterator object.
* A *iterator* object represents a stream of data, when called upon the *\_\_next\_\_()* method (or using built-in function *next()*) returns the next consecutive value till the *StopIteration* is raised. And when the *StopIteration* is raised, the *iterator* object is exhausted and no longer returns a value when *\_\_next\_\_()* is called. *iterator* are not required to be finite but be careful when looping over they may cause a *RecursionError*.
* One difference between *iterator* and *iterable* is that once a *iterator* is exhausted it stays empty even after passing it to the *iter()* function (as Iterator object returns itself when passed to *iter()*), which is not the case with a *iterable* object (a new iterator object is created every time *iter()* is called).
* The *iterator* objects are used to "lazy" load data into memory. So instead of loading all data at once like a *iterable* (example like *list* object does), *iterator* loads data when it is called upon. Examples of *iterator* are *enumerate*, *zip*, *reversed* etc. The [*itertools*](https://docs.python.org/3/library/itertools.html#module-itertools) module included in standard library contains a number of commonly-used iterators as well as functions for combining several iterators.
* Limitations of *iterator* are that values can be iterated only once and in one direction only (can't access previous values) and need to be re-created once exhausted.
* Creating a simple iterator.
```Python
## Example 1: create a simple iterator from a iterable
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
## Example 1: create a iterator object which returns a square of each values
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
* When iterating with a *for* loop, the iterable input object is first converted to a temporary *iterator* object and then these object is traversed using *\_\_next\_\_()* till *StopIteration* is raised. So everytime a *for* is called a new temporary *iterator* object is created and removed when iteration is finished/interrupted. In case of iterating a *iterator* object, the object itself is returned (as we saw in our SquareIterator's *\_\_iter\_\_()* method), so once its exhausted it stays empty. We'll check a example of the working below.
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
#### 7.2.3 Generators
* Generators are "lazy", they return value only when *next()* function is called upon. Generators are iterators objects but not vice versa, there are some differences. A generator object is created using a function that has one or more *yield* statements in it. They might have or not have loops in them. A *yield* statement makes a function iterable with/without loops. *yield* can also be used to pass values to a generator.
* Similar to a *iterator* object, *yield* in generators saves the state (or maintain current index like in our SquareIterator class), so generators can be interrupted and resumed throughout the program's execution. And once exhausted they stop returning values, at this point they need to be created again. 
* For longer iteration (larger/infinite length of data handling) generators are preferred because they are memory efficient, in a sense they can be utilized to generate/load data when required. This helps in avoiding the machine to run out of memory. Generators can also be created using similar to list comprehension's syntax, but using rounded brackets.
* Creating a simple generator.
```Python
## Example 1: create a generator function similar to our SquareIterator class
def my_square_generator(*args):
  for a in args:
    yield a**2
    # Notice: using "yield" instead of "return" makes this function "lazy" and hence a generator

generator = my_square_generator(2,3,4,5)

# or same using generator comprehension
generator = (a**2 for a in [2,3,4,5])
print(type(generator)) # <class 'generator'>
print(hasattr(generator, '__next__')) # True

## iterate a generator
for a in generator:
  print(a) # [4,9,16,25]
  # Notice: now that we didn't call "next()" this time all values are iterated
# however now it is exhausted, so will raise error 
print(next(generator)) # StopIteration
```
* Generators without loops.
```Python
def my_generator():
  yield 1
  yield 2
  yield 3
# calling my_generator() returns a generator object, which can be iterated  
for a in my_generator():
  print(a) # [1,2,3]
```  
* Passing a value to generator.
```Python
# it is recommended to use parenthesis around yield like this (yield <variable>) in some operations
# in simple assignments its okay without the parenthesis
def my_function():
    v = 0 # initialization
    # parenthesis required
    r1 = (yield v) + 10
    print(f'{v} was passed')
    while True: 
        # okay to not use parenthesis case
        r2 = yield v
        if r2:
            r1 = r1 - r2
        print(f"r1 is {r1} ad r2 is {r2}")

gen = my_function()
next(gen) # will go till first yield
# calling next() will raise TypeError, as None is passed by default to yield when calling next() 
# and adding 10 with None will raise Exception
next(gen) # TypeError

# to pass a value to generator use send() method 
gen.send(10) 
# now calling next will set r2 to None, the if condition doesn't execute
next(gen) # r1 is 20 ad r2 is None
# try again now passing a value
gen.send(10) # r1 is 10 ad r2 is 10
# now the if condition executes and r1,r2 become 10,10

# to terminate the generator use close() method
# this raises GeneratorExit exception inside the generator to terminate the iteration
gen.close() 
next(gen) # StopIteration
```
#### So just to summarize the difference between **Iterables**, **Iterators** and **Generators.**
 1. **Iterators**: Are objects that can be iterated, they can be iterated as many times as wanted. They need to implement the *\_\_iter\_\_()* method.
 2. **Iterators**: Are also iterables but are "lazy" and can be iterated only once, they need to be re-created for iterating again. They need to implement *\_\_iter\_\_()* and *\_\_next\_\_()* methods. They are used when it is required to implement *iterator* functionality inside a complex class (with other functionalities).
 3. **Generators**: Are iterators and iterables. Generators are a easy way to create a iterator object. They can be created using a function with a *yield* statement in it or using generator comprehension. They are used when it is required to create a standalone iterator object.
#### **7.2.4 Descriptors**
* A Descriptors is simply a object that defines at least one of *\_\_get\_\_()*, *\_\_set\_\_()* or *\_\_delete\_\_()* methods and optionally *\_\_set_name\_\_()* method. They allow objects to customize the attribute/variables lookup, storage/assignment and deletion. 
* Descriptors are mainly used to control what happens when a attribute is looked up/altered/removed, to override their default behaviour. So instead of class controlling what happens to the attribute, the attribute decides for itself what goes and what comes out when called/assigned. This operations as we know are performed using the '.' operator. 
* **There are two types of Descriptors**.
  1. **Data descriptors**: A Descriptors class that at least have one of *\_\_set\_\_()* or *\_\_delete\_\_()* methods defined.
  2. **Non-data descriptor**: A Descriptors class that only has *\_\_get\_\_()* method defined.
* These two types are not that different but this affects the '.' operator's "lookup chain" i.e data descriptors have more precedence over non-data descriptor. I have missed some extra details, you can catch them on [Official Python docs](https://docs.python.org/3/howto/descriptor.html).
```Python
## Descriptor example
class MyDescriptor:
    # when class holding 'MyDescriptor' object is defined this function is called
    # which records its name for later reference 
    def __set_name__(self, obj, name):
        # here obj is the 'MyClass' object and 'self' is our 'MyDescriptor' object 
        self.private_name = "_" + name # A access/internal name, '_' to avoid name collision

    # when attribute is looked up(using '.' operator), this method is called
    def __get__(self, obj, objtype=None):
        # fetch 'private_name' from 'MyClass' instance
        value = getattr(obj, self.private_name)
        print(f"{self.private_name} was accesed")
        return value

    # when attribute is altered(using '=' operator), this method is called      
    def __set__(self, obj, value):
        # decide what is valid value for 'my_var1'
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
        # calls '__set__()' method of descriptor to assign the variable
        self.my_var1 = var1 # alter/assign descriptor object's value
        self.my_var2 = var2 # alter/assign descriptor object's value
        self.my_var3 = var3 # normal attributes/variables
        self.my_var4 = var4 # normal attributes/variables 

my_instance = MyClass(11, 12, 30, 40)
print(my_instance.__dict__) # {'_my_var1': 11, '_my_var2': 12, 'my_var3': 30, 'my_var4': 40}

# calls the '__get__()' method of our descriptor to get value
print(my_instance.my_var1) # access descriptor object's value
print(my_instance.my_var2) # access descriptor object's value
# call normal variables
print(my_instance.my_var3)
print(my_instance.my_var4)

# control what should be the valid input for particular var
my_instance.my_var1 = 42 # AttributeError: Not a valid value, require odd number
my_instance.my_var2 = 41 # AttributeError: Not a valid value, require even number
```

## 8. Modules and Packages
### 8.1 Modules
* Is a file with *.py* extension containing Python code, they are also called scripts. Simply write some Python code in a file and save the file as *.py* extension, your module is ready.
* Python looks for modules in a sequence geiven below:
  1. Local Directory: It is where the current *.py* file is located.
  2. PYTHONPATH: It is a environment variable that can be used to set additional directory path which Python can use to find modules/packages, it is provided through command line. eg "PYTHONPATH=/path-to/some-dir". 
  3. Python Installation Directory: This is where your Python is currently installed, it can be viewed with "which python" command from the command line.
  This does means any module with repeating name will be given priority according to this sequence. 
* As Python is a Interpreted Language, each time a program is ran the *.py* files are compiled from source code to bytecode. To speed this up, when a *.py* file is imported the Python interpreter creates the *.pyc* (byte-compiled version of *.py* files) files if Python has permission to write files in that directory (look for the "\_\_pycache\_\_" folder). So next time Python can directly access the *.pyc* instead of re-compiling if no changes are made in that file. Also, these *byte-compiled* files are platform-independent.
* Use the built-in function *dir()* to find variables/functions/classes inside a module, as modules once import are objects too. Each imported module's object contain a special variable named *\_\_name\_\_* which is set to module name. But the current module which is ran by the user has *\_\_name\_\_* variable set to *\_\_main\_\_*. This helps a programmer to not invoke the script while importing it if they don't intent to. This is similar to *main()* function's behaviour in C/C++ language.
* Check the [List](https://docs.python.org/3/py-modindex.html) of built-in modules in Python.</br>
Example: Save this module as *sample.py* or anything you prefer (but change the name if so the in the next module).
```Python
a = 42
def my_fun():
  print("This function was called")

# check if module is a running module
if __name__ == "__main__":
  # do something here
  print("sample module was ran")
  my_fun()
```
Save this module as *my_module.py* and run this module.
```Python
## Modules
# modules can be imported anywhere in python, there is no restriction
# but for readability they are imported at the beginning
# Eg. math is built-in module, import it using the 'import' keyword
# the 'import' statement creates a module object 
# any module is only imported once a program is ran, re-importing has no effect
import math 

## accessing a function from math object
# any functions/classes/variables of math module now can be accessed using '.' operator
my_var = math.sqrt(8) 

## import specific from the module using 'from' keyword
from math import sqrt
# Note: doing stared import(Eg. from math import *) is not recommended as it might add name collisions.
my_var = sqrt(16)

## import with a different access name in order to avoid names collision
def math(num):
  return pow(num, 2)

import math as maths 
# accessing function from 'math' module
print(maths.sqrt(4)) # 2.0
# this 'math' does something else
print(math(2)) # 4

## Check functions/classes/variables of a module using dir()
print(dir(math))

## __main__ in Python
# Notice: Now importing my_module in this module will not call my_fun() 
# as my_fun() is only called if __name__ equals '__main__'
# which is only when running from that module i.e running my_module.py script
import sample
print(dir(sample)) # ['__builtins__', '__name__',...]
print(sample.__name__) # sample
# check __name__ variable of this module 
print(__name__) # __main__

# now try doing otherwise, run sample.py check the if this print method is called
if __name__ == "__main__":
  # add code here which you don't want to be invoked unless this script is ran
  print("my_module was ran")
```
### 8.2 Packages
* A folder with module named *\_\_init\_\_().py* file is a Python package. Any sub-directories containing *\_\_init\_\_().py* file are also packages (we can call them sub-packages). A Package is a collection of modules (.py files) and is a way to structure the modules under a single package's namespace. To import a module from a package use <package_name>.<module_name> signature. To import a package, import it by its name, that'll import the *\_\_init\_\_().py* module from that package.
* One common practice you might spot in open-source packages is *\_\_init\_\_().py* importing all classes/functions from all of its current directory's modules, this helps in getting all classes/functions under a single package's namespace, so you don't have to call them by following the module names like instead of <package_name>.<module_name>.<function_name> you can directly call by <package_name>.<function_name>.
* You can find all popular open-source Python packages on Python Package Index ([PyPI](https://pypi.org/)), it is a official third-party software repository for Python. You can install a package simply by "*pip install <package-name>*" command in the command prompt.</br> 
Note: *pip* comes pre-bundled with Python, some installation may require you use *pip3* instead of *pip*, you can check with "*which pip*" or "*which pip3*", if you see some directory it's already installed or you can install *pip* following the [official guide](https://pip.pypa.io/en/stable/installation/).
* You can also create your own package, create the following given below example directory structure.
```
./mypackage
  __init__.py
  mymodule.py
  ./myfolder
    __init__.py
    somemodule.py
./somepackage
  others.py
    
## Here "mypackage" folder contains __init__.py so its a package, similarly "myfolder" is also a package (or sub-package).
## Note: From Python 3.3 and up it is optional to have __init__.py to be called package, 
so now "somepackage" directory is also a package.
```
* Importing from such directory/package is very straight forward using '.' operator. Create a test.py outside of "./mypackage" directory and try the following code. Note you also need to create .py files as shown in the above example directory and also define "MyClass" and "myfunction" inside "mymodule" with some code (or just define with *pass* statement).
```Python
## importing a module from package
import mypackage.mymodule
# now can use the <module_name> to call its classes/functions
mymodule.myfunction() 

## importing the package by name
import mypackage
# this will call ./mypackage/__init__.py module

## but to import specific classes/functions from that module you need to use from...import
# say import a class from mymodule
from mypackage.mymodule import MyClass
# similarly a function
from mypackage.mymodule import myfunction
```

## 9. Files and I/O
Basic I/O operations are to take input the from user and send output to the user's screen. To handle a file is task of basically opening/creating a file, read or make changes and then close the file. Basic I/O and File operations are very general when working on any projects. We'll take a look at Three built-in functions for handling these operations and *with* statement which is very useful for file handling purposes. Later we'll check *Context Management* which is a way to add *with* statement's support to your objects.
### 9.1 Three built-in functions for I/O handling.
#### 9.1.1 input(prompt) => None
**Parameters**:</br>
  * *prompt* Any: Your message to the screen.
#####
**Explanation**: Reads input from standard input device (such as keyboard) and take it input as string.
```Python
## Take input from user
v = input() # or "input('Your message here ')"
print(type(v)) # <class 'str'>
```
#### 9.1.2 print(*values, sep=' ', end='\n', file=sys.stdout, flush=False) => None
**Parameters**:</br>
  * *values* object: Takes the object to be printed, '/*' indicates more than one object. 
  * *sep* Optional[Text]: A separator between multiple values.
  * *end* Optional[Text]: The last print value.
  * *file* Optional[_Writer]: A file-like object (stream), default is screen.
  * *flush* bool: Whether to forcibly flush the stream.
##### 
**Explanation**: Prints the given object to a standard output device, usually screen.
```Python
## Print output to the screen
print("This is output") # This is output
print("multiple", "objects", "to print") # multiple objects to print
print("This", "is", "a", "String" , sep="_") # This_is_a_String
print("This", end="\t") 
print("is not new lined") # This    is not new lined
```
#### 9.1.3 open(filename, mode='r', buffering=-1, encoding=None, errors=None, newline=None, closefd=True, opener=None) => file
**Parameters**:</br>
  * *filename* Union[str, bytes, int]: path-like object or a string.
  * *mode* str: Opening file mode.
  * *buffering* int: For specifying buffering policy.
  * *encoding* Optional[str]: Specify encoding format. On Windows default is "cp1252" and "utf-8" in Linux.
  * *errors* Optional[str]: To handle Encoding/Decoding errors.
  * *newline* Optional[str]: Specify how newline work.
  * *closefd* bool: If False, the underlying file descriptor will be kept open even when the file is closed.  
  * *opener* Optional[Callable[[str, int], int]]: A custom file opener, should return a file descriptor.
#####
**Explanation**: This built-in function is used to open a file. This method returns a file object (also called handle), this object is further used to perform operations such as read/write/append. For different operations there are different modes one can utilize according to their needs, default is r (reading). 
* Various file modes are shown below.
  1. **r**: For opening a file in read-only mode.
  2. **w**: In write mode if the file already exist and has some previous content it is completely overwritten. Else new file is created and content is written.
  3. **a**: In append mode if the file already exist and has some previous content, the new input is appended at the end, not overwritten. Else new file is created and content is written.
  4. **x**: In exclusive creation mode if the file already exists, the operation fails. Else new file is created and content can be written to it.
  5. **t**: Opening a file in text format, basically reading a file with strings, this is the default format.
  6. **b**: Opening a file in binary format, when reading in this format bytes are returned, basically to handle non-text files like images/database/documents.
```Python
## read from a file, FileNotFoundError is raised if file is not found 
file = open("sample.txt", mode="r") # or  open("sample.txt")
print(file.read())
file.close()

## write to a file, PermissionError is raised if you don't have the permission
file = open("sample.txt", mode="w")
file.write("This is some text written to the")
file.close()

## append mode
file = open("sample.txt", mode="a")
file.write("This is some text written to the")
file.close()

## mixing modes, you can't mix "a","r" and "w" modes together, but can mix other modes
# example 1: text format and write mode
file = open("sample.txt", mode="tw") 
file.write("This is some text written to the")
file.close()
# example 2: read and append mode
file = open("sample.txt", mode="r+")
print(file.read())
file.write("This is some text written to the")
file.close()
# example 3: binary format and read mode
file = open("some.py", mode="br")
print(file.read())
file.close()

## various file methods
# reads all text/non-text data at once, returns string/bytes 
file = open("sample.txt", mode="r") 
print(file.read())
# reads all text/non-text data line by line, returns string/byte list
print(file.readlines())
# writes string to the file 
file.write("This is a text.")
# takes iterable object containing multiple strings and writes to the file 
file.writelines(["This is a text.", "This is also some text"])
# close a file, frees up system resources, should be called at the last step
file.close()
```
### 9.2 *with* statement
This statement simplifies some common resource management like in file streams. It makes code more readable and helps in avoiding resource leaks. When using *with* statement  the resources are handled automatically nested block of code ends. It guarantees to close the file no matter how the code block is exited. 
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
### 9.3 Context Manager 
* It is a simple protocol that a object needs to follow to add support for *with* statement. A class needs to define *\_\_enter\_\_()* and *\_\_exit\_\_()* special methods and that object will function as a context manager. Context managers are usually used in Database management and to handle Thread locks. 
* Also there's a built-in module [contextlib](https://docs.python.org/3/library/contextlib.html) which can be utilized to achieve the same.
```Python
## Simple db example with context manager
class MyDBManager:
  def __init__(self):
    self.some_db = {"id": [], 'name': []}
  # called after the 'with' statement  
  def __enter__(self):
    return self
  # called after block of code ends  
  def __exit__(self, exc_type, exc_val, exc_tb):
    self.some_db['id'] = []
    self.some_db['name'] = []

  # simple function to add values
  def add(self, my_id, name):
    self.some_db['id'].append(my_id)
    self.some_db['name'].append(name)

with MyDBManager() as db_handler:
  # do something
  db_handler.add(3251, "bob")
  db_handler.add(3252, "rob")
  db_handler.add(3253, "job")
  print(db_handler.some_db) # {'id': [3251, 3252, 3253], 'name': ['bob', 'rob', 'job']}

# now to clear the db just get out of the indentaion    
print(db_handler.some_db) # {'id': [], 'name': []}
# as soon as we were out of the indentation "__exit__()" was called automatically
```

## 10. OOP concepts
#### What is OOP?
Wikipedia suggests
  > Object-oriented programming is an approach to designing modular reusable software systems. It is a programming paradigm based on the concept of objects.

  Classes and Objects are the two important aspects of OOP. And as we saw earlier an Object is a instance of class and it has its own attributes & methods which are defined under its represented class.
#### Why OOP?
It helps in reducing code complexities & redundancy by promoting better software design practices as opposed to structural/procedure-oriented programming using the concept called objects. OOP really shines when designing a large software systems which typically requires huge amount of inter-dependencies among the blocks of code. By following OOP approach, a software system becomes more reusable, maintainable, scalable, secure and overall less complex compared to the structural programming.
**There are four main principles of OOP: [Inheritance](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#101-inheritance), [Abstraction](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#102-abstraction), [Encapsulation](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#103-encapsulation) and [Polymorphism](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#104-polymorphism).**
### 10.1 Inheritance
* Instead of re-writing the code for all similar classes like in functional programming, we re-use the methods/variables of a class inside another class in OOP. This concept is Inheritance. So basically inheritance helps to eliminate the redundant code.
* We inherit a base/super class and use its methods/variables inside a child/sub class, but not the other way.
* **super()**: This is a built-in function used access any child's/parent's methods/variables inside of a child class, it is very similar to *super* keyword in Java. When called it returns a temporary object of parent class which then can be used to access to all of its methods/variables. 
* **Method Resolution Order (MRO)**: Is the order in which Python looks for a method in hierarchy of classes. The general order is **child -> parent1 -> parent2...**. When a method/variable is searched, it is looked for in this order. Any name collision is avoided by following this order.
* Inheritance is a powerful concept and is used pretty much all the time when a software is designed using a OOP based language.
#### **10.1.1 Four types of Inheritance.**
1. **Single**: A Child/sub class only inherits a single Parent/Super Class.
```Python
class MyParent:
  # class variables
  some_var = 50  
  def __init__(self, para1):
      self.para1 = para1
  def some_func(self, num):
      return num**2
  def other_method(self, num):
      return self.para1 - num

# inherit MyParent class  
class MyChild(MyParent): 
  def __init__(self, arg1):
    self.arg1 = arg1
    # instantiate parent class inside child class
    super().__init__(arg1) 
  def my_func(self, num):
    # call parent's method using 'super()' function
    output1 = super().some_func(num) 
    # access base classes variables
    print(super().some_var) 
    # here self calls parent's method, as this class doesn't have 'other_method()'
    output2 = self.other_method(num) 
    return output1 + self.arg1 + output2
  def some_func(self, num):    
    return num**3

child_instance = MyChild(38)
# calling my_func() returns child's method
output = child_instance.my_func(2)
# calling same named method, returns child's method 
output = child_instance.some_func(2)
# now calls parent class's method
output = child_instance.other_method(20)
```
2. **Multiple**: A Child/Sub class inherits multiple Parent/Super Classes.
```Python
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
      MyParent2.__init__(self) 
      # so now MyParent2's variables/methods can be accessed
      print(self.para1) # 20
      print(self.para2) # 42

  def my_func(self, num):
    # here MyParent1's method will be called, due to MRO
    output1 = self.other_method(num) # similar to 'super().other_method(num)'
    return output1

## create child instance
child = MyChild(30)
print(MyChild.mro()) # [<class '__main__.MyChild'>, <class '__main__.MyParent1'>, \
# <class '__main__.MyParent2'>, <class 'object'>]
# same as before, calling MyParent1's method
print(child.other_method(2)) # 4
print(child.my_func(2)) # 4

## to call MyParent2's same named method using child instance
# call with class and pass child instance
print(MyParent2.other_method(child, 2)) # 8
print(MyParent1.other_method(child, 2)) # 4
```
* When it comes to Multiple Inheritance there is also one concept called *mixins*. You might spot them in some libraries code, they are named somewhat like <class_name>Mixin. They are classes that act as base classes carrying some features (i.e functions) that other classes are supposed to used. They do usually don't have instance variables (might have class variables), they are base classes which do not inherit other class (other than *object*) and are not intended to be instantiated, only sub-classed.
* *Mixins* are a cleaner way to define some functions that other classes can use right away without defining them individually. Also this concept is not recognized by Python, so they act as a normal class.
```Python
class SomeMixin:
    def printer(self):
        print(f"a = {self.a}")
        print(f"b = {self.b}")
        print(f"total = {self.total}")
    
    # can also have other functions
    def do_something(self):
        pass 

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
v.printer()

v = Subbtr(40, 10)
v.perform_op()
v.printer()
```
3. **Multilevel**: In Multi-Level a child class inherits a parent class and is also a parent class to other class.
```Python
class MyClass1:
  def __init__(self):
      self.para1 = 5
  def doing_something1(self, num):
      return self.para1 - num
  def other_method(self, num):
      return num**2

class MyClass2(MyClass1):
  def __init__(self):
      self.para1 = 10
      self.para2 = 20
  def doing_something2(self, num):
      return self.para1 - num
  def other_method(self, num):
      return num**3
  
class MyClass3(MyClass2):
  def __init__(self):
      self.para1 = 42
      self.para2 = 42
  def doing_something2(self, num):
      return self.para1 - num
  def other_method(self, num):
      return num**3
      
# can access MyClass1 variables/methods
parent1 = MyClass1() 
# check MRO using 'mro()' method of class      
print(MyClass1.mro()) # [<class '__main__.MyClass1'>, <class 'object'>]
# can access MyClass2, MyClass1 variables/methods
parent2 = MyClass2() 
print(MyClass2.mro()) # [<class '__main__.MyClass2'>, <class '__main__.MyClass1'>, <class 'object'>]
# can access MyClass3, MyClass2, MyClass1 variables/methods
child = MyClass3()
```
4. **Hierarchical**: A parent/super class is inherited by more than one child/sub class. 
```Python
class MyParent:
    args = [22,59,81,34,73,12,35]
# child class 1 inheriting 'MyParent'
class MyChild1(MyParent):
  def max_finder(self):
    return max(self.args)
# child class 2 also inheriting 'MyParent'
class MyChild2(MyParent):
  def min_finder(self):
    return min(self.args)

my_instance1 = MyChild1()
my_instance2 = MyChild2()
print(my_instance1.max_finder()) # 81
print(my_instance2.min_finder()) # 12
```
### 10.2 Abstraction
* It is a process hiding internal implementation details and showing only some limited necessary functionality. Hiding in a sense focussing on what methods an class must contain and not their exact definition/implementation. Abstract class is not the way to achieve complete abstraction, as they can also contain normal methods with definition. Interfaces are the way to complete abstraction, although Python doesn't support interfaces Abstract classes should be enough.
* Abstract classes are classes that have at least one abstract method, it can also have other normal method types. Abstract methods are methods that do not have a body (they are empty methods). The abstract classes cannot be instantiated (its object cannot be created). The concrete/inheriting class of this abstract class has to implement all the abstract methods compulsorily else an error will be raised. The concept of abstract is not applicable to variables so they behave normally.
* Python does not have *abstract* keyword like in Java and also does not directly supports abstract classes. But Python provides a module named *abc*, it can be used to define Abstract Base classes (ABC) which act about the same. 
* The Abstraction concept is not necessarily a compulsion in order to design a system. But when designing larger systems it can good to have Abstraction checked, the abstract classes can be designed to act as base for other classes to avoid functionality break/bugs and further make it necessary for other programmer to implement/design other classes following some common interface.    
```Python
### Abstract class example
from abc import ABC, abstractmethod
## create a abstract class by instantiating 'ABC' class
class MyBase(ABC):
    # define abstract methods
    @abstractmethod
    def get_vars():
        pass
    @abstractmethod
    def change_values(self, a, b):
        pass
    # define combination of method types   
    # Notice: 'abstractmethod' should always follow later 
    @staticmethod
    @abstractmethod
    def some_info():
        print("this method is both static and abstract")
    def mydefault_fun():
        print("This is normal function")

## create concrete classes using 'MyBase' class as parent class
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

# 'MyConcrete2' will raise TypeError due to not implementing abstract methods 
# TypeError: Can't instantiate abstract class MyConcrete2 with abstract methods change_values, some_info
my_concrete2 = MyConcrete2(10, 20, 30) 
print(my_concrete2.get_vars()) # 10, 20, 30

# try to create object of 'MyBase' class
my_base = MyBase() # TypeError: Can't instantiate abstract class
```
### 10.3 Encapsulation
* Encapsulation refers to simply wrapping attributes/data and methods under a single class. This data (of any data-type/data-structure/object) can be only accessed/altered by the class methods themselves essentially to restrict access from outside of the class. This is called data hiding. 
* This technique is essential to protect private data to be accessed/misused form another class directly. To implement this we use **Access Modifiers**. They are used to define the access type of a variable inside a class. 
* **Three Types of Access modifiers.** 
  1. **Public**: Can be accessed anywhere in the program. All variables are public by default.
  2. **Protected**: Only the current class and derived class can access them. Use "\_" underscore define them.
  3. **Private**: Only the current class can access them, not even their instance can access them. Use "\_\_" underscore define them.
* First the private data is set to *private* type to restrict the direct access and if we want to allow these private data to be accessed/modified by outside class, public *setters()* and *getters()* methods can be used like in Java/Javascript. But Python also has another way, the *property* object.
* In Python, all variables are public by default and the way private/protected are implemented they don't really work as one would expect, below are some examples.
```Python
## Access modifier
class MyClass:
  def __init__(self):
      self.my_var1 = 10 # public variable
      self._my_var2 = 20 # protected variable
      self.__my_var3 = 30 # private variable

class MyClass1(MyClass):
  def __init__(self):
      super().__init__()

## example 1
# "can't be accessed will" raise AttributeError, to continue program execution comment/remove the line
# access by parent's instance 
my_instance = MyClass()
print(my_instance.my_var1) # can be accessed
print(my_instance._my_var2) # can be accessed
print(my_instance.__my_var3) # can't be accessed, private variable

## example 2
# access by child's instance
my_instance = MyClass1()
print(my_instance.my_var1) # can be accessed
print(my_instance._my_var2) # can be accessed
print(my_instance.__my_var3) # can't be accessed, private variable

## example 3: allow access from outside class
# Define set() and get() methods
class MyClass:
  def __init__(self):
      self.my_var1 = 10 # public variable
      self._my_var2 = 20 # protected variable
      self.__my_var3 = 30 # private variable
  def get_my_var(self):
    return self.__my_var3
  def set_my_var(self, new_value):
    # if you want '__my_var3' 'read-only' you can raise AttributeError, uncomment the following line 
    # raise AttributeError("Cannot change this value")
    self.__my_var3 = new_value  
    
some_instance = MyClass()
print(some_instance.get_my_var()) # 30
some_instance.set_my_var(50)
print(some_instance.get_my_var()) # 50
# but still can't access directly
print(some_instance.__my_var3) # AttributeError

## Problem with python's access modifier implementation
# '__dict__' a special variable in python keeps track of attributes of module/class/object
# this process is name mangling, which uses '_CLASSNAME' prefix for private variables
# print this to show private variables
print(some_instance.__dict__) # {'my_var1': 10, '_my_var2': 20, '_MyClass__my_var3': 30}
# or use 'vars()' to return the '__dict__' variable
print(vars(some_instance)) # {'my_var1': 10, '_my_var2': 20, '_MyClass__my_var3': 30}
# which then further can be accessed using the naming convention
print(some_instance._MyClass__my_var3) # 30
# also can delete the variable
del some_instance._MyClass__my_var3 
# further crashing the program
print(some_instance._MyClass__my_var3) # AttributeError
```
#### **10.3.1 property(fget=None, fset=None, fdel=None, doc=None) => property** </br>
**Parameters**:</br>
  * *fget* Optional[Callable]: The getter function.  
  * *fset* Optional[Callable]: The setter function.  
  * *fdel* Optional[Callable]: The deleter function.  
  * *doc* Optional[str]: Provide some information about the particular property.
#####
**Explanation**: It is a Pythonic way to use getters and setters in encapsulation. *property()* function simply allows assigning/altering private variable using the '.' operator without really exposing the real (private) variable. Using this function accessing/modifying becomes just as convenient as operating on a regular variable. *property()* can also be used as decorator for further convenience. For more implementation details check [Official Python docs](https://docs.python.org/3/howto/descriptor.html#properties).</br></br>
**Descriptor vs Property**: Descriptors are the low-level mechanism behind allowing class variables to control what happens during attribute lookup. And properties are just descriptors, they are a implementation of descriptors. Although one drawback using descriptor is for hooking a single variable a whole class has to be dedicated, which is not the case with properties. One can have multiple variables of such behaviour inside a single class using properties.
```Python
## Implement Encapsulation using python's property object
class MyClass:
  def __init__(self):
      self.my_var1 = 10 # public variable
      self._my_var2 = 20 # protected variable
      self.__my_var3 = 30 # private variable
      self.__my_var4 = 40 # private variable
  # getter method for '__my_var3'
  # Notice: the property decorator, 'my_var' can be renamed to any other name
  @property 
  def my_var(self):
    print("Getter function called")
    return self.__my_var3
    
  # if you don't want '__my_var3' value to be altered, don't define this 'setter' method     
  # setter method for '__my_var3'
  # Notice: the <VAR_NAME> decorator  
  @my_var.setter
  def my_var(self, new_value):
    print("Setter function called")
    self.__my_var3 = new_value    
  
  # if you don't want '__my_var3' value to be deleted, don't define this 'deleter' method     
  # deleter method for '__my_var3'
  @my_var.deleter
  def my_var(self):
    print("Deleter function called")
    del self.__my_var3   
  
  # getter method for '__my_var4', this is the second variable(we talked about in property vs descriptors)
  @property
  def some_var(self):
    return self.__my_var4
    
   # or without using property decorator, just pass the functions to property, example below  
   # my_var = property(my_getter, my_setter, my_deleter)

# here '__my_var3' is a private variable, 'my_var' is the variable that now can be
# used to modify '__my_var3' from outside the class     
some_instance = MyClass()
print(some_instance.__dict__) # {'my_var1': 10, '_my_var2': 20, '_MyClass__my_var3': 30, '_MyClass__my_var4': 40}
# access using the <VAR_NAME>
print(some_instance.my_var) # 30
print(some_instance.some_var) # 40
some_instance.my_var = 50
print(some_instance.my_var) # 50
del some_instance.my_var
some_instance.some_var = 90 # AttributeError
del some_instance.some_var # AttributeError
```
### 10.4 Polymorphism
* Polymorphism means many forms. It is the ability to use a common interface/function to operate or perform tasks on different types of objects. It can be also thought as a way to get rid of *if..else* or *switch* case when same type of function needs to be called on different objects.     
* **Two Types of Polymorphism.**
  1. **Static**: The behaviour is decided at Compile-time, like in method/operator overloading. 
  2. **Dynamic**: The behaviour is decided in Runtime, like in method/function overriding.
#### **10.4.1 The Four types of Polymorphism.**
1. **Method overloading**: A class can have same named methods but should have distinct input parameters, this functionality is not supported in Python. As the methods with same name are overwritten by the newer ones. Usually other parameters are set to None and missing or object types are checked throughout using *if..else* statement or *isinstance()* function for achieving the same, but similar thing can be achieved using [multipledispatch](https://github.com/mrocklin/multipledispatch) or [plum](https://github.com/wesselb/plum).
```Python
## Simple Method Overloading example in Python
class MyClass:
    def printer(self, a, b):
        total = a + b
        print(f"Your total is {total}")
    # Notice: the method name is same
    def printer(self, a, b, name):
        total = a + b
        print(f"{name} your total is {total}")
      
my_instance = MyClass() 
# here 'printer(a,b,c)' has overwritten 'printer(a,b)'
my_instance.printer(20, 30, "Bob") # Bob your total is 50
my_instance.printer(20, 30) # TypeError: printer() missing 1 required positional argument

## traditional way is to use single function to handle everything 
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
```
2. **Operator Overloading**: Make operators work for user-defined classes, when a class implements a particular operator's function (which is a special function in Python) and changes its functionality (does something and returns something), that functionality is applicable to that class/object. Changing operator's behaviour for a specific object by overloading a operator's function.
```Python
## Operator Overloading, here we overload the addition and subtractor operator
class MyClass:
  def __init__(self, *args):
    self.args = args
  
  # this is a special function to overload '+' operator
  def __add__(self, my_obj):
    """Define functionality behaviour for '+' operator inside this method, the input parameter can be any
    type as required. Just the functionality defined should support it."""
    return sum(self.args) + sum(my_obj.args)
    
  # similarly this is a special function to overload '-' operator
  def __sub__(self, my_obj):
    """Define functionality behaviour for '-' operator."""
    return abs(sum(self.args) - sum(my_obj.args))
    
my_ins1 = MyClass(90, 20, 10, 42)
my_ins2 = MyClass(10, 70, 20, 50) 
print(my_ins1 + my_ins2) # 312
print(my_ins1 - my_ins2) # 12
```
3. **Method overriding**: Use same named functions but inside different classes. Two classes can have same named functions, but the functionality might differ with their class. Useful for handling the operation from a common interface/function. This functionality can also be referred as Duck Typing. It is a feature of dynamic languages, it means directly (by not caring about exceptions) calling methods on objects without checking their types.  
```Python
## Method Overriding
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
  
handler_l = ListHandler()
handler_d = DictHandler()
perform_addition(handler_l) # 200
perform_addition(handler_d) # 230
```
4. **Function overriding**: Changing the default functionality of a built-in function for that particular object, essentially to add some behaviour for a custom object. 
```Python
## Function Overriding
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
# now as the' __len__()' is implemented this will return the output
print(len(my_ins)) # 5
# this will return address of this object by default,
print(my_ins)
# uncomment '__str__()' and re-run to see change in its functionality
```
## References
* [Python Official docs](https://docs.python.org/3/reference/index.html)
* [Time complexity python](https://wiki.python.org/moin/TimeComplexity)
* [Python built-in modules](https://docs.python.org/3/py-modindex.html)
* [Python built-in functions](https://docs.python.org/3/library/functions.html)
