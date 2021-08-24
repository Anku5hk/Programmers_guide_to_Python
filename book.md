# Programmer's guide to Python
Hello Learner, welcome to this Programmer's guide to Python handbook, this book was originally designed as notes when I was learning python, but then I thought okay why not make it public for other learners, so I added some missing components and completed it as a book. I hope this helps you in learning python programming. Happy Learning!!

**What's not this:** Not a traditional programming course/book, this is by no means a complete python walkthrough and is structured somewhat differently (intentionally) to cover and only emphasis on what is important. This book is not recommended for 'programming freshers', you should try more beginner friendly books like [Byte of Python](https://python.swaroopch.com/)/[Think Python](https://greenteapress.com/wp/think-python-2e/) and comeback to this one to further fine tune your learning.</br>  

**What is this:** This book is meant for a programmer who's already familiar with other languages such as c/c++/Java and wants to learn python but fast. The one who needs a python refresher can also benefit by this book. The goal is to take you through enough python, while saving you tons of time. I have tried to keep explanations concise most of the times, so things can be gone through fast. To grow as a programmer its always better to practice. I would suggest typing & running your own programs and creating your own notes.

#### [Some Topics are under progress..]

## Index
1. [Basics](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#1-basics)
2. [Data Types](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#2-data-types)
3. [Data structures](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#3-data-structures)
4. [Flow Control, File & Exception Handling](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#4-flow-control-and-exception-handling)
5. [Functions, Classes and Objects](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#5-functions-classes-and-objects)
6. [OOP Concepts](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#6-oop-concepts)


## 1. Basics
### Introduction
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;As wikipedia suggests "Python is an interpreted high-level general-purpose programming language." It was created by Guido van Rossum and released in 1991. It supports multiple programming paradigms like object-oriented, procedural and functional. "Python is also dynamically-typed and garbage-collected". Python's best implementation is in C language([Cython](https://github.com/python/cpython)) which is the default/standard, but there are other implementations in Java, .Net, etc. Its philosophy revolves around code readability and code simplicity, you can also check [zen of python](https://www.python.org/dev/peps/pep-0020/). Python is widely used in Web-Development([flask](https://flask.palletsprojects.com/en/2.0.x/), [django](https://www.djangoproject.com/), [fastapi](https://fastapi.tiangolo.com/)), Android/Windows/IOS/OSX application development([kivy](https://kivy.org/#home)), Big-Data Processing/Databases([Pyspark](https://spark.apache.org/docs/latest/api/python/), [Pandas](https://pandas.pydata.org/)), Machine learning([pytorch](pytorch.org/), [tensorflow](tensorflow.org/), [sklearn](scikit-learn.org/stable/)), Mathemetical/Scientific libraries([numpy](numpy.org/), [scipy](scipy.org/)), DevOps, Security, etc. The current/latest version is python3 which was released in 2008 and is still relevant(as of 2021), as python2 was discontinued at 1 Jan 2020.      
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;There is a fair amount debate around "python is a slow language", this [blog](https://hackernoon.com/why-is-python-so-slow-e5074b6fe55b) has some answers, but for most part that does not affect its usability/credibility, it is the most preferred programming language and is still growing popular(as of 2021). There are other languages which are good enough to be python's successor such as GO Lang, Rust and Julia. These languages do have potential to eventually replace python, at least at some tasks in coming time, but it is yet to be seen.  
### Fundamentals
* **Literals**: Are raw data given to a variable, literals are constant fix values eg 4, there is no other value replacement for 4, so its a integer literal. A raw value by itself is a literal. 
```Python
# some literals
4, 6, 2.5, 7.4, 'string', 'something'
```
* **Keywords**: Are reserved words which are defined by python, so they can't be used as operands.
```Python
# some keywords
if, else, for, while, is, as, or, not, and, None, def, class, return, yield, pass, raise
```
* **Operands/Variable**: Are objects that hold values, it has a user-defined name, a name should not begin with a underscore(because it is reserved for something else), other naming rules are similar to other languages. Variables do not need to be declared, just assign values to them. Unlike c/c++/Java "python is dynamically-typed", python's variable does not actually hold the value itself but a pointer to the storage where the value is stored. This means the variables can point to any type of object. This allows for example, a variable assigned string be changed to any int, float, data structure, custom object.
```python
## variable names example
MyInt, some_var, my_string12, SOME_NUMBER

## dynamically typed
a = 34
a = 4.0
a = "I am string"
a = [1,2,3,4]
```
* **Operators**: Are used to perform operations on operands. The Arithmetic, Assignment, Comparison operators work same as in C/C++/Java/Javascript. Other Logical, Identity, Membership operators are also very straight forward, I'll explain going through later on.
```Python
## Operators in python(comma separated)
## Arithmetic operators
+,-,\*,/,%,\*\*,//
## Assignment operators
=,+=,-=,/*=,/=,%=,//=,\*\*=,&=,|=,^=,>>=,<<=
## Comparison operators
==,!=,>,<,>=,<=
## Logical Operators
not,and,or
## Identity Operators
is,is not
## Membership Operators
in,not in

## extra operations
# chaining operators operation Eg.
if x <= y < z: # is similar to "if x<=y and y<z:"
```
* **Expressions**: Are a part of statement (as in expression statement), a expression is something that returns value/sequence by doing some operation (arithmetic/conditional/lambda function).
```Python
# some examples
"Yes"+"this"
x+6
if a==3 else 2
a or b
2 and 3
lambda x:x**2
```
* **Statements**: Are basically every instruction/line of code that python interpreter executes. There are two types, simple and compound statements. 
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
if, while, for, try, with 
```
### Extras
* **Indentations**: Unlike using brackets in c/c++/java, indentations are used for a code block in python. Indentations can be of any range, usually four indentations are preferred, only constraint is that they should be consistent throughout that block of code. Unindented line is used to show the end of that block of code. They are used in Flow Control, Exception Handling, Functions/Classes definitions in python, else IndentationError is raised. Any statements or even comments should follow the indentation rule.
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
* **Comments**
```Python
# this is a single line comment

"""this is a 
multiline comment
"""
```
* **Time Complexity**: It is used to measure how runtime of a function increases with the size input. Note that time complexity is not equal to execution time. It is used to calculate how a function will scale, given the number of inputs. A good time complexity [chart](https://www.bigocheatsheet.com/). </br>
**Common Time Complexities in ascending order of their growing time.** 
  1. O(1): Constant time. time does not increase at all.
  2. O(logN): Logarithmic time. when time is increasing logarithmically (grows at inversely proportional rate of N).
  3. O(N): Linear time. time increases linearly with the input size.
  4. O(NLogN): Log-Linear time, Logarithmic and Linear time together.
  5. O(N\*\*K): Polynomial time. when time increases at N(input) to the power K (constant) times.
  6. O(K\*\*N): Exponential time. when time increases at K(constant) to the power N (input) times.</br>
**Note**: Explaining all time complexities would consume lots of space for this book, so I have linked a explanation from the internet [here](https://www.kaggle.com/delayedkarma/understanding-time-complexity-via-python-examples).
## 2. Data Types
Are used to define the type of data a variable holds. Python doesn't require declaration of data types like in c/c++/java (as variables are just pointers). Any variable can be assigned any data type, a string variable can be assigned int or float or any other object it doesn't matter.
### Three Numeric Types
1. **int** (interger): Numbers that do not have decimal values.
2. **float**: Numbers that do have decimal values.
3. **complex**: Numbers that have two parts, real and imaginary. First part is normal number, the second part is imaginary number which should be followed by j. 
```Python
## assigning values to variables 
# here my_int is an operand, 42 is a literal and its data type is int
my_int = 42 # int
print(type(my_int)) # <class 'int'>
my_float = 3.0 # float
print(type(my_float)) # <class 'float'>
my_complex = 4.22 + 20j # complex
my_complex = complex(4.22, 20) # alternative way
print(my_complex) # (4.22+20j)

## Some supported functions
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
# returns the unicode value given a character
print(ord("c")) # 99
# returns normal value back given the unicode value
print(chr(ord("c"))) # c

## type conversion
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
### String
Are sequence of characters in python. Unlike Java, python does not have 'char' for character/character array, it has 'str' object (similar to 'string' in c++) which is a collection of character data. They are immutable i.e items/values (here characters) cannot be altered/deleted once inserted. But you can use 'replace()' method of string to alter and 'strip()' to remove specific sub-string.
```Python
## assigning strings
text = 'strings can be single quoted'
text = "strings can be double quoted"
text = """This is a long text.
        And want to use multiple lines."""
        
## String types
print("normal str,\t escaping characters") # normal str, escaping characters
print(r"\n raw string \t no escaping characters") # \n raw string \t no escaping characters
# String formatting, used to pass python expression/variable inside a string
n = 1
text = f"This is a String number {n}" # f-string to pass variable
text = f"This is a String number {20-19}" # or even to pass expression
text = "This is a String number %s" %n  # or C like formatting 
text = "This is a String number {0}".format(n) # or format method of string
print(text) # This is a String number 1

## multiplying('*') operator on string
string1 = "this" * 5
print(string1) # thisthisthisthisthis

## join two strings, both should be str 
string1 = "This is 1."
string2 = "This is 2."
print(string1 + string2) # This is 1.This is 2.

## slicing string syntax is [start_index:end_index:step], end_index is not considered
print(string1[5:7]) # is
print(string1[5:]) # is 1.
print(string1[:4]) # This 
print(string1[:5:2]) # Ti 
print(string1[:-4]) # This i
# reverse a string
print(string1[::-1]) # .1 si sihT
# unlike list, string does not create a copy 
print(string1[:]) # This is 1.

## Some methods of string
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

## Some functions on string
# Returns the length of a string
print(len(my_string)) 
# Returns a Unicode of a character
print(ord("c")) # 99 
# Returns Converted the Unicode to a character
print(chr(ord("c"))) # c

## type conversion
my_string = "bar"
my_string1 = "20"
# str to int
print(int(my_string)) # ValueError
print(int(my_string1)) # 20
# str to float
print(float(my_string)) # ValueError
print(float(my_string1)) # 20.0
```
### Boolean
Has only 2 values (True and False), True (is also 1, so 4 + True is 5) and False (is also 0, so 4 + False stays 4).
```Python
## assigning bool
my_bool = True
print(type(my_bool)) # <class 'bool'>
my_bool = my_bool + 4 # becomes 5
my_bool = False
my_bool = my_bool + 4 # stays 4

## type conversion
# int/float to bool, anything not 0 is True, also None is False
print(bool(-40), bool(0), bool(40)) # True False True
# str to bool, empty string is False, rest is True
print(bool(""), bool("This is string")) # False True
```
### Special 
**None**: None is similar to 'null' in java. Python docs "None is frequently used to represent the absence of a value, as when default arguments are not passed to a function." 
```Python
n = None
print(type(None)) # <class 'NoneType'>

## to check whether an object is not None
if n: # same as "if n != None:"
  print('will not enter this condition')

## not is used to negate the condition
if not n: # same as "if n == None:"
  print('will enter this condition, as n is None')
```
### Custom Data Type
User defined data type, which are used to create a new data type by combining the built-in data types. Unlike in C/C++ python doesn't have 'struct', but what it does has is objects, which can be utilized to do the same.
```Python
## Example 1
# create object of a data type
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
# The problem is you can't define type of data or length of an array(list) in python
# For such situation you can create your own methods for inserting
# where you can check the type of data that is fed in
# But will not that be a Data structure? Nope?

## Example 2
class MyDataType:
  def __init__(self, x, y):
    """__init__ is antoher 'magic method', which enables usage of construtor in python, more on this later."""
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
### Extras
#### Some functions explained below: [type()](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#1-type), [isinstance()](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#2-isinstance), [id()](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#3-id).
#### 1. type() 
 **Parameters** => [object] </br>
 **Returns** => str </br>
**Explaination**: This function returns the class_name of an object.
```Python
a = "What?"
print(type(a)) # str
b = 5.0
print(type(b)) # float
```
#### 2. isinstance() 
**Parameters** => [object, class] </br>
**Returns** => bool </br>
**Explaination**: This function checks if a object is an instance of a particular class. Returns True/False.
```Python
a = 23
print(isinstance(a, int)) # True
print(isinstance(a, float)) # False
print(isinstance(a, str)) # False
```
#### 3. id() 
**Parameters** => [object] </br>
**Returns** => int </br>
**Explaination**: This function returns object id of a object.
```Python
my_float = 50.0
# object id wil differ each time with program
print(id(my_float)) # 1875526208176
```
#### Logical and Identity operators.
```Python
### Logical operators: not,and,or
## not: to negate the underlying condition (it reverses the condition)
a = 30
# here the underlying condition is the isinstance() function, which return True/False 
# normally 'if' executes when a underlying condition is 'True' right?, by applying 'not' to it
# the 'if' condition is satisfied when the output is 'False'
if not isinstance(a, int):
  print('not printed')
if not isinstance(a, str):
  print('printed')

## 'and' is similar to '&&' in c/c++/java: both conditions should be satisfied
a=20
b=30
if a > 10 and b < 50:
  print('printed')
  
## 'or' is similar to '||' in c/c++/java: either of conditions should be satisfied
if a > 10 or b < 10:
  print('printed')
  
### Identity operator: is,is not
## is: checks if 2 objects are referring to the same object. 
some_var1 = 42
some_var2 = 42
if some_var1 is some_var2:
  print('printed')
# check with id  
print(id(some_var1)) # 2587096149584
print(id(some_var2)) # 2587096149584
if some_var1 == some_var2:
  # this is also true, here values are checked
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
## 3. Data Structures
Data Structure is a way to store and organize data so that it can be used efficiently. They are used to store/retrieve data from. Data can be data types or even other data structures. Different data structures have their advantages/disadvantages in terms of accessing/storing/removing data speed, so they should be used as per the task/ease. They can also be called literal collections. Python has built-in 4 data structures. In python, you can't/don't need to declare the size of the built-in data structures beforehand, they are dynamically scaled/released automatically in background.
### List
They are array like implementation in python. They are ordered collection of sequence of items, which can be of any data type or object. They are Mutable(values can be changed). Indexing, Slicing is supported and they are iterable objects(more on this later). They are preferred in most use cases. Where indexing, looping over some items is required lists are used.
```Python
## create list
my_list = [1,2,3,'a','this way','cab',1.0,2.0]

## add/remove values
my_var = 1
my_list.append(my_var)
# remove 
my_list.remove(my_var) # or del my_list[index] or my_list.pop(index)
# using 'del' statement
del my_list[0] # or even with slicing like, del my_list[2:4]
# del can also be used to delete any other object

## join two lists
# using '+' operator
my_list1 = [2,4,5,6] + [34,7,4,2]
# using extend() method
my_list1.extend([3,6,2]) # my_list1 becomes [2,4,5,6,34,7,4,2,3,6,2]

## accessing/altering elements
var_1 = my_list1[0]
var_2 = my_list1[1]
print(var_1, var_2) # 2,4
# iterating with loop
for var in my_list1:
  print(var) # [2, 4, 5, 6, 34, 7, 4, 2, 3, 6, 2]
# altering values in list
my_list1[0] = 100
my_list1[1] = 200
print(my_list1) # [100, 200, 5, 6, 34, 7, 4, 2, 3, 6, 2] 
# checking if some value is present in list
if 20 in my_list1: # similar to "if some_var in my_list1:" where "some_var = 20"
  print('not printed')
if 200 in my_list1:
  print('printed')

## slicing list
print(my_list[3:5]) # ['cab', 1.0]
print(my_list[5:]) # [2.0, 1]
print(my_list[:3]) # [3, 'a', 'this way']
print(my_list[:5:2]) # [3, 'this way', 1.0]
# this is negative index which begins from end of list from 1
print(my_list[:-4]) # [3, 'a', 'this way']
# reverse a list
print(my_list[::-1]) # [1, 2.0, 1.0, 'cab', 'this way', 'a', 3]
# or my_list.copy() to create a copy, which does not stays the same reference
print(my_list[:]) # [3, 'a', 'this way', 'cab', 1.0, 2.0, 1]

## list comprehension
my_list2 = [x for x in range(10)] # without condition
my_list2 = [[y for y in range(x)] for x in range(1, 4)] # which also can be nested
my_list2 = [x for x in range(10) if x > 5] # if condition
my_list2 = [True if x > 5 else False for x in range(10)] # if with else condition

## Some functions on list
# returns sorted list of items in ascending order by default, 
# sorting is O(nLogn), for reversing pass 'reverse=True'
print(sorted(my_list1)) # [2, 2, 3, 4, 5, 6, 6, 7, 34, 100, 200]
# return length of list
print(len(my_list1)) # 11
# sum of variables
print(sum(my_list1)) # 369
print(sum([10, 20])) # 30

## Some methods of list
my_list1.append(9) # adds value to the list 
my_list1.reverse() # reverses list inplace
my_list1.sort() # sorts list inplace
my_list.clear() # list becomes empty
print(my_list) # []
# returns index of first arrival of value passed 
print(my_list1.index(3)) # 2 
# removes value from a list given value
my_list1.remove(2) 
# removes value from a list given index, also returns the value
print(my_list1.pop(5)) # 6

## type conversion
my_list = list((1,2,3,4,5)) # tuple to list
my_list = list({1,2,3,4,5}) # set to list
```
* **Time Complexity**</br>
indexing, appending and get_length are O(1).</br>
deleting, poping, inserting, iteration are O(n).
### Tuple
Are ordered collection of sequence of items similar to lists. But unlike list they are Immutable (items cannot be altered/deleted), so they are preferred when data should not be changed and so iterating is slightly faster than list. Indexing, Slicing is supported and they are iterable objects just like lists, but no tuple comprehension (it becomes a generator). They are used to store different data type items, unlike list which are mostly used for storing similar items, but either way is also valid. 
```Python
my_tuple = (1,2,3,'we','are','one',5.0)

## accessing element
my_var = 10
my_var = my_tuple[0] # okay
my_tuple[0] = my_var # not okay because Immutable, raises TypeError
# iterating over a tuple  
for var in my_tuple:
  print(var) # (1,2,3,'we','are','one',5.0)
# checking if some value is present in tuple
if 5.0 in my_tuple:
  print('printed')

## also can't add/remove element in tuple, there is no append()/remove(), can't use 'del' like in list
# so to add a element join two tuples, and assign it to the previous/new variable
my_tuple += (5,) # adding another element as tuple, its basically joining two tuples
# Notice: the target tuple should have ',' if single element is being added

## join two tuples
my_tuple1 = (34,65,23) + (34,34)

## slicing tuple
print(my_tuple[3:5]) # ('we','are')
print(my_tuple[5:]) # ('one',5.0,5)
print(my_tuple[:3]) # (1,2,3)
print(my_tuple[:5:2]) # (1,3,'are')
# this is negative index which begins from end of tuple from 1
print(my_tuple[:-4]) # (1,2,3,'we') 
# reverse a tuple
print(my_tuple[::-1]) # (5, 5.0, 'one', 'are', 'we', 3, 2, 1)

## unpacking tuple(more on unpacking later on)
a,b,c = (1,2,3) # unpacking values into a,b,c
# even this does the same, 1,2,3 becomes a tuple and then unpacks into a,b,c 
# same is true when returning comma separated values from a function 
a,b,c = 1,2,3 # same as (1,2,3)
# this behaviour further aids in swapping without using extra variable
a,b = b,a 

## Some functions on tuple
# returns sorted list of items in ascending order by default
my_tuple = (3,6,1,8,2,3)
print(sorted(my_tuple, reverse=True)) # [8, 6, 3, 3, 2, 1]
# returns length of tuple
print(len(my_tuple)) # 6
 
## Some methods of tuple
# Returns number of occurrences of value.
print(my_tuple1.count(34)) # 3
# Returns first index of value.
print(my_tuple.index(3)) # 0

## type conversion
my_tuple = tuple([1,2,3,4,5]) # list to tuple
my_tuple = tuple({1,2,3,4,5}) # set to tuple
```
* **Time Complexity**</br>
indexing, appending and get_length are O(1).</br>
deleting, poping, inserting, iteration are O(n).
### Set
Are unordered collection of non repeating sequence of items. Sets are mutable. Items/Members inside a set should be hashable (must have a \_\_hash\_\_() method), which means its hash value must never changes during its lifetime. Numbers, strings & tuple(with hashable items in them) are hashable. This behaviour allows sets to check if a particular object is unique from other members and also to perform operations like intersection, union. Sets are iterable, but Indexing/Slicing doesn't work as their order don't matter. Sets are mostly used to maintain unique variables and to quickly check if the variable is already present in the set. Like in BFS/DFS algorithms for checking visited nodes.
```Python
## create set
my_set = set() # create a empty set
# create a non empty set
my_set = {9,1,5,2,20} # Notice: dict like parenthesis but without keys
# items order don't matter, so while printing order might differ
print(my_set) # {1, 2, 20, 5, 9}

## add, remove
my_var = 4
my_set.add(my_var) # if repeated value, it will not be added again 
my_set.remove(my_var) # removes a member, raises KeyError if not found

## join two sets, '+' operator is not supported for set
a = {54,23,67}
b = {34,65,55.6}
a.update(b) 
print(a) # {65, 34, 67, 55.6, 54, 23}

## accessing element
my_set[0] # not allowed, TypeError: 'set' object is not subscriptable.
# iterating over a set
for var in my_set:
   print(var) # {1, 2, 20, 5, 9}
# check if my_var is inside my_set   
if my_var in my_set: 
  print('not printed')
  
## Some methods of sets
my_set1 = {3,5,7,1,8}
my_set2 = {1,2,3,4,5}
# find intersection, or similar to 'my_set1 & my_set2'     
print(my_set1.intersection(my_set2)) # {1, 3, 5}
# to find union, or similar to 'my_set1 | my_set2'   
print(my_set1.union(my_set2)) # {1, 2, 3, 4, 5, 7, 8}
my_copy = my_set1.copy() # returns a copy of a set
my_copy.clear() # removes all members of set
# checks if my_set2 is a subset of my_set1
print(my_set1.issubset(my_set2)) # False
# checks if my_set2 is a superset of my_set1
print(my_set1.issuperset(my_set2)) # False

## type conversion
my_list = [1,2,3,4,5]
# here my_list is mutable, but set() function unpacks the items from my_list
my_set = {my_list} # this raises TypeError
my_set = set(my_list) # this unpacks items from list to set
# also if my_list contained a list inside it, TypeError: unhashable type: 'list' is raised
my_set = set((1,2,3,4,5)) # tuple to set
```
* **Time Complexity**</br> Sets are implemented using hash tables, so pretty much all operations should be O(1) and worst case when 'hash collision' occurs O(n).</br>
adding, checking (with 'in' operator) and removing are O(1).</br>
iterating is O(n).</br>
union is O(m+n).</br>
intersection is O(min(m,n)), worst is O(m\*n).
### Dict
Longform Dictionary in python, use Hashtable to store data with a key & value. A hashtable uses a hash function which given a key generates a index to an array like Data Structure, which store the actual values. So instead of indexing, keys are used to access values. This behaviour help hashmap do almost all operations in O(1) making them very efficient for storing and retrieval operations. Keys in dict should be hashable (similar to sets), values have no restriction(can be any object). They are used in Dynamic Programming and generally where values are supposed to have some key associated with them.
```Python
## create empty dict
my_dict = dict() # or "my_dict = {}"
# create non empty dict
my_dict = {'e':23, 'w':65, 'q':52}

## add, remove
my_var = 20
key = 10
tuple_key = (20,)
my_dict[key] = my_var # add item at key
my_dict[tuple_key] = 45
print(my_dict) # {'e': 23, 'w': 65, 'q': 52, 10: 20, (20,): 45}
del my_dict[tuple_key] # remove the item

## join two dicts
my_dict1 = {'z':5, 'y':3, 'x':4}
my_dict.update(my_dict1)
print(my_dict) # {'e': 23, 'w': 65, 'q': 52, 'z': 5, 'y': 3, 'x': 4}

## accessing element
key = 'a'
my_var = my_dict[key] # can raise KeyError if not present
# use get() method to avoid KeyError, None is default, can be set to anything else
print(my_dict.get(key, None)) # None
# traverse all items
for k,v in my_dict.items(): 
  print(k, v) # {'e': 23, 'w': 65, 'q': 52, 'z': 5, 'y': 3, 'x': 4}
# check if key is inside my_dict   
if 'w' in my_dict:
  print('printed')
   
## dict comprehension 
my_dict = {x:x*x for x in range(6)} # stand alone, generating keys and values
print(my_dict) # {0: 0, 1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
# another way
my_keys = ['a', 'b', 'c']
my_values = [1,2,3]
my_dict = {k:v for k,v in zip(my_keys, my_values)}

## Some methods of dicts
my_dict1 = {'a':1, 'b':2, 'c':3}
my_dict2 = {'z':50, 'y':40, 'x':30}
# returns a dict_keys object, it contains dict's keys, it is iterable, you can also convert it to list
print(my_dict1.keys()) # dict_keys(['a', 'b', 'c'])
# returns a dict_values object, it contains dict's values, it is iterable, you can also convert it to list
print(my_dict1.values()) # dict_values([1, 2, 3])
# returns a dict_items object, has keys & values, is also iterable and you know the rest
print(my_dict1.items()) # dict_items([('a', 1), ('b', 2), ('c', 3)])
# removes item(key,value) given key, which is 'a' here and returns value
print(my_dict1.pop("a")) # 1 
my_dict1.clear() # removes all items of dict

## type conversion
keys = [1,2]
values = [2,3]
my_dict = dict([keys, values]) # list to dict
my_dict = dict(((1,2), (2,3))) # tuple to dict
```
* **Time Complexity**</br> Dicts are implemented using HashMaps, so most operations are O(1) and depending on implementation worst case O(n).</br>
insert, add, delete is O(1).</br>
iteration is O(n).
### Other Data Structures
#### 1. Stack
can be easily implemented using lists.
```Python
my_stack = []
## add/remove operation
my_stack.append(20) # append at top
my_stack.pop() # remove at top
```
#### 2. Queue
similarly can be easily implemented using lists.
```Python
my_queue = []
## add/remove operation
my_queue.append(20) # append at rear
my_queue.pop(0) # remove at front
```
### Extras
#### Some functions explained below: [range()](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#1-range), [enumerate()](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#2-enumerate), [zip()](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#3-zip), [sorted()](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#4-sorted), [filter()](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#5-filter), [map()](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#6-map).
#### 1. range()
**Parameters** => [start_index=0, end_index, step=1] </br>
**Returns** => range </br>
**Explaination**: This function returns a sequence of length start_index(0 by default) to end_index(is a required argument). range() function returns a range object, which is iterable and supports indexing but are immutable. It is used in loops, where a certain number of times a loop should work, like for iterating to the length of an array in c/c++/java.
```Python
## examples
print(range(20)) # [0:20] 
print(range(5,20)) # [5:20] 
print(range(6,20,2)) # [6, 8, 10, 12, 14, 16, 18] 
## indexing a range
print(range(20)[0]) # 0
# also slicing but its not preferred/recommended
print(range(20)[0:10]) 
# makes range sequence a list sequence
print(list(range(5,20))) # [5:20] 

## looping range object
for var in range(20): 
  print(var) # [0:19]
# reversing the order
for var in range(20, -1, -1): 
  print(var) # [19:0]
```
#### 2. enumerate()
**Parameters** => [iterable] </br>
**Returns** => tuple </br>
**Explaination**: This function returns a enumerate object given a list, each item is a tuple and has (index, value) per item. Index is in range from 0-length of the list and value is item from the list. enumerate object is iterable but Indexing/slicing is not supported.
```Python
## examples
my_list = [100,200,500,100]
# returns a iterable object
print(type(enumerate(my_list))) # <class 'enumerate'>
# converts to list and indexing first value gives a tuple
print(list(enumerate(my_list))[0]) # (0,100) 

# looping over enumerate object
for i, val in enumerate(my_list):
  print(i) # 0,1,2,3
  print(val) # 100,200,500,100
```
#### 3. zip() 
**Parameters** => [\*iterable] </br>
**Returns** => zip </br>
**Explaination**: This function returns a zip object given multiple iterables, each item is a tuple which contains n (number of input iterables) length elements. When provided multiple number of iterables, the length of returned 'zip' object is the smallest iterable's length. zip() is commonly used to unpack values from multiple iterables simultaneously.  
```Python
## examples
a = ['This','is','something']
b = (14, 3, 6)
c = {34,7} 
print(type(zip(a))) # <class 'zip'>
# convert to list
# the length of zip is 2 because smallest is c and its length is 2
# so remaining values in a,c are ignored
print(len(list(zip(a, b, c)))) # 2
print(list(zip(a, b, c))) # [('This', 14, 7), ('is', 3, 34)]
# loop over the values
for v in zip(a, b, c):
  # v is a tuple with 3 values, so we can index them
  print(v[0], v[1], v[2]) # [('This', 14, 7), ('is', 3, 34)]
# or unpack them into named variables
for var1, var2 in zip(a,b):
  print(var1, var2) # [('This','is','something'), (14, 3, 6)]
```
#### 4. sorted()
**Parameters** => [iterable, key=None, reverse=False] </br>
**Returns** => list </br>
**Explaination**: This function returns a sorted list given a iterable object. Sorting is O(nLogn). key parameter takes function which is then used to extract the elements, helpful when input iterable is . Also has 'reverse' parameter, which is used to do reverse sorting if it is set to 'True'.
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

print(sorted(my_string)) # ['e', 'e', 'e', 'r', 'r', 'r']
print(sorted(my_tuple, reverse=True)) # [14, 6, 3]
# sort list by the length of sub-list
print(sorted(my_list, key=my_fun)) # [[200], [2, 7, 23], [10, 20, 56, 23, 12]]
```
#### 5. filter()
**Parameters** => [function, iterable] </br>
**Returns** => filter </br>
**Explaination**: This function takes a function & a iterable and applies that function on every item of that iterable. The return value of filter's function has to be boolean. filter() returns only if 'True' condition is met, if 'False' is met nothing is returned, also if no condition is met nothing is returned. filter() as the name suggests, is used to filter out not required values from a iterable object. filter() returns a filter object which iterable but indexing/slicing is not supported.
```Python
## Example 1
my_list = [101,100,501,200]
def my_func(var):
  # returns True if number is divisible by 10
  if var % 10 == 0:
    # value is returned
    return True 
  # value is not returned   
  return False
  
my_filter = filter(my_func, ())  
print(type(my_filter)) # <class 'filter'>

## Example 2
# only filter elements which are divisible by 10
output = list(filter(my_func, my_list)) # [100, 200]
# or looping through filter object
for val in filter(my_func, my_list):
  print(val) # [100, 200]
```
#### 6. map()
**Parameters** => [function, iterable] </br>
**Returns** => map </br>
**Explaination**: This function takes a function & a iterable and applies that function on every item of that iterable. As name suggests, a function is mapped to each element of an iterable. So unlike filter(), map() returns the direct value returned by our function.
```Python
## Example 1
my_tuple = (1,2,3,4,5)
def my_func(var):
  # returns square of a number
  return var**2
print(type(map(my_func, ()))) # <class 'map'>

## Example 2
# return square of each element in a list
output = list(map(my_func, my_tuple)) # [1, 4, 9, 16, 25]
# or looping through map object
for val in map(my_func, my_tuple):
  print(val) # [1, 4, 9, 16, 25]
```

## 4. Flow Control and Exception Handling
### Flow Control
Flow Control is used for making decisions in programs. This decision making helps turn the output of the program based on the executed conditions. Python supports all the general statements for conditions and loops except 'switch'. 
#### if...else
```Python
my_var = 20
my_var1 = None
if my_var == 20:
  print('Yes its 20')
elif my_var == 30:
    print('Its 30')
else:
  print('Its something else')

# single line condition
my_var = True if 20%2 == 0 else False
# here is True is the output when 'if' condition is satisfied, else False is the output

# using only 'if' after some variable/sequence to check if it is not 'None'
if my_var:
  # similar to "if my_var != None"
  print("printed")
if my_var1:
  # will not execute, my_var1 is 'None'
  print("not printed")
  
# negate the condition using 'not'
if not my_var:
  # similar to "if my_var == None"
  print("not printed")
if not my_var1:
  # my_var1 is 'None', so will print 
  print("printed") 
```
#### for loop
```Python
my_list = [10,20,30,40,50]
# regular looping by indexes
for i in range(len(my_list)): # [0:4]
  print(my_list[i])

# pythonic loops
for v in my_list:
  print(v)
# or 
for a in [10,20,30,40,50]:
  print(a)   
  
# there's also a 'else' condition, when a 'for' loop is not executed
# if any iterable has no elements, this 'else' condition will execute
for v in []:
  print("List has no elements")
else:
  print("So this will execute")
```
#### while loop
```Python
i=0
my_list = [10,20,30,40,50]
while i < len(my_list):
  print(my_list[i])
  i+=1 # similar to 'i=i+1', since 'i++' is not supported
```
### Exception Handling
Exception handling helps to continue the program execution while handling the Errors/Exceptions on the way.   
```Python
## use traceback module for printing Tracebacks
import traceback
# 'catch' keyword is replaced with 'except', rest is the same
## catching specific errors
try:
  a=10
  a = "this"+a
except (TypeError, ZeroDivisionError):    
  print("ZeroDivisionError/TypeError occured")
  # print traceback
  traceback.print_exc()
  
## catch any exception with 'Exception' class, it is base class of all exceptions
# lets cause stackoverflow/RecursionError in python
def my_fun():
  try:
    my_fun() 
  except Exception as e:
    # print exception class
    print(e.__class__)  # <class 'RecursionError'>
    # print exception
    print(e) # maximum recursion depth exceeded
my_fun()

## manually throw(raise) exception
def my_fun(a):
  try:
    if a == 20:
      raise ValueError("I don't want number 20") 
      # or not specifying specific exception like, "raise Exception('my message')"
    return a+100
  except ValueError as v:
    print(v)
number = my_fun(20) # I don't want number 20
      
## finally and else condition    
try:
 a = 20/0
 a=20
except Exception as e:
  print(e.__class__) # <class 'ZeroDivisionError'>
  print(e) # division by zero
else:
    print("This executes if no exception was raised.")  
finally:
    print("Finally, its finally, which always executes.")      
```
### File Handling
1. txt file
2. json file
3. xml file
### Extras
* **break**: breaks from loop. 
* **continue**: continue to next iteration in loops.
* **pass**: move down to next statement.
```Python
## break and continue
i=-1
my_list = [10,20,30,40,50]
while i<len(my_list):
  i+=1
  if i == 0:
    continue
  if i == 4:
    break
  print(my_list[i]) # [20,30,40]
  
## pass
# pass can be used inside empty a functions, just to have that function without raising error
# and implement the function later while coding
def my_fun():
  pass
```
* **assert**: Helps in debugging, it is used to check if certain condition is true, else raise a AssertionError.
```Python
a = 10
assert a == 10 # No error raised
assert a == 30 # AssertionError
```
## 5. Functions, Classes and Objects
### Functions
* A function is used to perform some operation/task on some data/variables/sequences, it may or may not have parameters, it may or may not return something (in Python, None is returned by default if 'return' statement is not defined). 
* Functions in python are first class, which means they behave just like an object, they can be stored in a variable or can be passed as a argument to other functions.
* **Parameters vs arguments**: Parameters are the ones which are defined in function definition, arguments are the ones which are passed when a function is called. 
* Functions in python support Packing and Unpacking variables into tuple/dict. Explained below.
1. **Packing**: It is when we pass more than the number of defined variables to a function. It is useful when we are not sure about the exact number of arguments required for some operation. They should always be the last parameters in a function (or they'll contain all the values). 
2. **Unpacking**: It is when a list/tuple/dict is passed, which then unpack as function parameters. Now passing tuple/list can be done with '\*' prefix followed by sequence's name, generally as '\*args'. Passing dict requires '\*\*' prefix followed by sequence's name, generally as '\*\*kwargs'.
```Python
## defining functions
# Example 1. Non-parameterize function which returns nothing 
def my_function1():
  # do something
  pass # to ensure the program runs this empty function   
  # if the function is not empty 'pass' is not required at all
  
# Example 2. function with parameter which returns nothing
def my_function2(var1, var2):
  pass
# alternative way is to describe the input/return type hints
# As they are just hints, it does not matter what is send/returned
def my_function2(var1: int, var2: int) -> None: 
  pass
  
# Example 3. default parameters should always follow later
def my_function3(var1, var2, var3, do_something=False): 
  if do_something:
    # did something
    return var1 + var2 + var3

## calling a function without a return statement, returns None by default
print(my_function1()) # None
print(my_function3(30, 20, 10, do_something=True)) # 60

## first class functions behaviour
def square_num(number, some_fun=None):
  if some_fun:
    output = some_fun(number)
  else:
    output=number**2  
  return output

def cube_num(n):
  return n**3

# assigning a function to a variable, it is not same as calling a function
# Notice: no rounded brackets on the function
my_var = cube_num 
print(my_var) # <function my_funtion at 0x000001C1FDFAF0D0>
# 'my_var' now points to the 'cube_num()', so calling 'my_var' is calling 'cube_num'
print(my_var(2)) # 8

## passing a function as argument to another function
print(square_num(2)) # 4 
# pass function as argument
print(square_num(2, my_var)) # 8

## packing in functions 
# packing variables into tuple and dict
def my_test(*args, **kwargs):
  print(type(args)) # tuple
  print(type(kwargs)) # dict

# packing args example
def sum_nums(a,b, *args):
  total = a+b
  if args:
    for n in args:
      total+=n
  return total

# passing only 2 arguments
sum_nums(2,3) # 5   
# passing more than 2 arguments
sum_nums(2,3,3,4,2,1,1,4) # 20

# packing kwargs example
def my_fun2(x,y,**kwargs):
  total = x+y
  if kwargs:  
    for k,v in kwargs.items():
        # here we're allowing only specific keys
        if k in 'abd': 
            total+=v
  return total
  
# passing only 2 arguments
print(my_fun2(2,3)) # 5   
# passing more than 2 arguments, however arguments should have some unique name
print(my_fun2(2, 3, a=2, b=4, d=4, any_name=5000, my_var=8000)) # 15

## unpacking in functions
# unpacking variables from tuple/dict
def my_fun1(a,b,c,d):
  return a+b+c+d

my_list = [1,2,3,4]
my_dict = {'a':1,'d':4,'b':2,'c':3}
# passing from list/tuple, list here
print(my_fun1(*my_list)) # 10
# passing from dict
print(my_fun1(**my_dict)) # 10 
```
#### Anonymous functions
Is a function that is defined without a name(without using 'def' keyword in python). This can be created using 'lambda' keyword, it is a single line function. 
```Python
## example 1
# function to return sum of 2 numbers 
# syntax => lambda arguments : expression
my_function = lambda a,b: a+b  
# Notice: 'a+b' is also the return statement without using 'return' keyword 

## calling the function
print(my_function(1,1)) # 2 
```    
#### Docstrings
Holds the hints/suggestion working of a function/class provided by the developer. It begins just below start of a function/class definition.
```Python 
class MyClass:
    """This is a docString"""
    def my_fun():
        """This is what this method does..."""
```
### Class
* **Class**: Is a blueprint/template of/for an object. Which defines what the object holds(which variables/data types), what methods/operations can be performed on that object. 
* **Instance**: Is a object of a class, it is created using the class. This instance/object is then used to perform operations/tasks that the class is intended to. A instance has its own state, so modifying some variables will only reflect changes for that particular instance only.  
* **Constructor**: Is a function that is called when the class's object is instantiated/created, a class may or may not have a constructor. A default constructor does not have parameters and parameterized constructor does.
* **Methods**: Functions that are inside class are called as methods. 
* **self**: 'self' is a keyword that resembles a instance of class in class methods. Similar to Java/Javscript's 'this' keyword, it is used to access variables/methods of that instance. But in Python, a class method should have 'self' object as the first parameter inside their definition. Although argument is not required to be passed when calling such method. When a instance calls a method, the calling instance gets passed automatically by python as 'self' object to that method, explained more below.
```Python
## class
# define class
# python defines empty constructor automatically in background, if not provided
class MyClass: 
  # class method
  def myfunction(self):
    # do something  
    pass

# class with default constructor
class MyClass1:
  # default constructor
  def __init__(self):
    # instance's variables are created with 'self.' prefix
    self.my_var = 30
    self.other_var = 10
    
  # instance methods
  def my_fun1(self):
    # access instance variables using 'self' object
    print(self.my_var) 
    # change/define new variables inside any instance method using 'self' object
    self.my_var = 42 

  def return_my_var(self):
    return self.my_var 
    
class MyClass2:
  # parameterized constructor, passing parameters and saving them as instance variables
  def __init__(self, para1, para2, para3=None): 
    self.para1 = para1
    self.para2 = para2
  # here var1 is a method parameter
  def my_func(self, var1): 
    return var1 + max(self.para1, self.para2)

## instance
# use '.' dot operator to access methods/variables of an object
some_instance = MyClass1()
# access variables
print(some_instance.other_var) # 10
# access methods
print(some_instance.return_my_var()) # 30

# create new instance, pass arguments for parameterized constructor
my_instance = MyClass2(22,35) 
# calling my_func() of my_instance
print(my_instance.my_func(40)) # 75

# in python the invocation of the instance method is operated via the class calling a method 
# by passing the instance as an argument, so this is same as above instance calling method
new_var = MyClass2.my_func(my_instance, 40)
# the 'self' keyword ressembles the instance object, which is 'my_instance' here
```
#### Three Types of methods in class:
1. **Class**: Class methods are bound to classes and not to instances. These methods have access to class state, so they can access class variables/methods and modify class variables. Unlike instance only one copy is created, so every instance/class refers to this copy. Class methods can be accessed by both instance and class. They are defined using 'classmethod' as decoration(using '@classmethod' prefix), these methods should have class as first parameter, which unlike 'self' can be of any name, 'CLS' is preferred. This parameter further can be used to access other class variables/methods inside these methods.
2. **Instance**: Instance methods are bound to instances. They have access to both instance and class state, which allows access to class & instance variables/methods and also can modify class & instance variables. These methods can only be accessed by instance and not class. A normal function inside a class is a instance method, these methods should have 'self' as first parameter, which is used to access the instance's/class's variables/methods inside these methods.
3. **Static**: Static methods are also bound to classes. But they don't have access to instance/class state. So they can't access/modify any variables beside its local scope. These methods exist because that function has to belong to the class like a independent function but inside a class. They are defined using 'staticmethod' as decoration(using '@staticmethod' prefix), these methods are not required to pass class as first argument.
```Python
## define class
class MyClass: 
  # class variables
  my_var1 = 20
  my_var2 = 10
  
  # instance methods
  def __init__(self):
    # instance variables
    self.other_var1 = 30 
    self.other_var2 = 40
    # can also access class variable
    print(self.my_var1)
  def fun1(self):
    print("This is a instance method")
  
  # class method
  @classmethod
  def fun2(CLS):
    print("This is class method")
    # access class variable
    print(CLS.my_var1)
 
  # static method
  @staticmethod
  def fun3():
    # can't access instance/class variable/methods, but can do its own task
    print("This is static method")
 
## access using instance    
my_instance = MyClass()
print(my_instance.my_var1) # can access
print(my_instance.other_var1) # can access
print(my_instance.fun1()) # can access
print(my_instance.fun2()) # can access
print(my_instance.fun3()) # can access
 
## access using class
print(MyClass.my_var1) # can access
print(MyClass.other_var1) # can't access
print(MyClass.fun1()) # can't access
print(MyClass.fun2()) # can access
print(my_instance.fun3()) # can access
```
### Objects
* An object has its own attributes/data(can be any data-type/data-structure/object) and functions(methods).
* **"Everything in python is an object"**, in python's definition of object, some objects may or may not have meta-data/functions and are still objects. The Data-types in python have attributes/methods, data structures have their attributes/methods, Functions(are first class, as we saw earlier)/Classes also have their attributes/methods, so they are all objects. And as a property of an object they all can be assigned to a variable or passed to a function. So in a sense everything can be called an object. 
* We saw earlier how to create a instance of a class(i.e object) and what/how they can access variables and methods.
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
### Extras
#### Namespaces
As seen in c++ are collection of names of variables/functions, but unlike in c++, python does not have 'namespace' keyword, so no user defined namespaces. Python maintains its namespaces in a dictionary. They are maintained according to their scopes automatically, just like in any programming language. There are three types of namespaces.
1. **built-in**: Are readily available functions without any import.
2. **global**: Are which user defines outside of any function/class. 
3. **local**: Are which user defines inside a function/class/nested.
```Python
## built-in namespace 
# For example functions which do not require any imports 
print(), len(), map(), range(), list(), set(), str()

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
#### Modules
Is simply a python file (with .py extension), 'dir()' can be used to find variables/functions/class inside a module. Python looks for modules in a sequence local directory(where current .py is located) -> PYTHONPATH(provide python dir path using PYTHONPATH env variable) ->  lastly inside python installation directory. This does means any module with repeating name will be given priority according to this sequence. [List](https://docs.python.org/3/py-modindex.html) of built-in modules in python.
```Python
## Modules
# modules can be imported anywhere in python, there is no restriction
# but for readability they are imported at the beginning
# math is built-in module, now the name 'math' refers to module math
import math 
# any functions/classes/variables of math module can be accessed using '.' operator
# accessing function from math
my_var = math.sqrt(8) 

# import specific functions/classes/variables from the module using 'from' keyword
from math import sqrt
my_var = sqrt(16)

# import with a different access name in order to avoid names collision
def math(num):
  return pow(num, 2)

import math as maths 
# accessing function from 'math' module
print(maths.sqrt(4)) # 2.0
# this 'math' does something else
print(math(2)) # 4
```
#### Packages
Are defined with \_\_init\_\_().py file in that folder.
#### Decorators
Are used to wrap another function to basically extend its functionality. It is simply running a function inside another function, like a nested nested function. This allows to extend the wrapped function's behaviour without actually modifying the function itself. This are called decorators, also called 'syntactic sugar'. Using '@' prefix a function can be decorated. This functionality is utilized using functions being first class in python.
```Python
# my_outer_func() is just a container function
def my_outer_func(some_func):
  # wrapper function here
  # my_wrapper_func() does something before/after calling some_func() 
  def my_wrapper_func(some_func_para1, some_func_para2): 
    # do something of my_wrapper_func()
    print("Wrapper function was called")
    # call some_func(), do something in it and return something if required
    output = some_func(some_func_para1, some_func_para2) 
    # do something extra
    # return nothing if not required
    return output 
    
  # but need to return my_wrapper_func()   
  return my_wrapper_func 

## without using decorators
def my_fun(a,b):
  return a+b

my_decorated_fun = my_outer_func(my_fun) 
print(my_decorated_fun(10, 20)) # 30

## now using decorators
@my_outer_func
def my_fun(a,b):
  return a+b

# now just call my_fun() normally, this will call my_outer_func()
print(my_fun(10,20)) # 30
```
#### Some objects explained below: [Iterators](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#1-iterators), [Generators](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#2-generators) and [Descriptors](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#3-descriptors). 
#### 1. Iterators
Are objects that can be iterated using loops, these aren't necessarily list. A iterator object implements '\_\_iter\_\_()' and '\_\_next\_\_()' special functions. These are implemented inside a class to make it's object iterable.
```Python
## Iterators
# user-defined iterators
class SquareIterator:
  """SquareIterator takes items and returns item's square upon call"""
  def __init__(self, *args):
    self.args = args
    self.iter_len = len(args)-1
  def __iter__(self):
    """This method is used to initialize a iterator, it returns an iterator object."""
    self.idx = -1 # we initialize index
    return self
  def __next__(self):
    """This method is used to fetch next value, it can be called or loops do call it automatically."""
    self.idx += 1  
    if self.idx > self.iter_len:
      raise StopIteration
    return self.args[self.idx]**2

my_iter = SquareIterator(10,20,30,40,50)  
# initialize iterator
my_iter = iter(my_iter) 
# iterate values using next
print(next(my_iter)) # 100
# same as next(my_iter)
print(my_iter.__next__()) # 400

## iterating a iterator object
# for loop calls '__iter__()' and '__next__()' functions on a iterable
for v in my_iter:
  print(v) # [100,400,900,1600,2500]
  
## use hasattr to check if some object has some particular function 
print(hasattr(my_iter, "__iter__")) # True
print(hasattr(list, '__iter__')) # True
print(hasattr(tuple, '__iter__')) # True
```
#### 2. Generators
Generators are lazy iterators, they return value when 'next()' function is called upon. They might have or not have loops in them. 'yield' statement makes a function iterable with/without loops. 'yield' saves the state, which helps in iterating value changes over the generator's lifetime, so unlike regular loops which removes loop state as soon as execution is finished/interrupted, it can be interrupted and resumed whenever inside a program. For longer iteration(larger data) generators are preferred because they are memory efficient, in a sense they can be utilized to generate data required in time and not before time. Generators can also be created using similar to list comprehension's syntax, but using rounded brackets.
```Python
## basic generator
def my_generator(*args):
  for a in args:
    yield a   
generator = my_generator(10,20,30,40,50)

# or using comprehension
generator = (a for a in [10,20,30,40,50])
print(type(generator)) # <class 'generator'>
print(next(generator)) # 10

## iterate a generator
for a in generator:
  print(a) # [10,20,30,40,50]

## create a generator without loop
def my_generator():
  yield 1
  yield 2
  yield 3
for a in my_generator():
  print(a) # [1,2,3]
```
#### 3. Descriptors
A Descriptors is simply a object that defines at least one of '\_\_get\_\_()', '\_\_set\_\_()' or '\_\_delete\_\_()' methods and optionally '\_\_set_name\_\_()' method. They allow objects to customize the attribute/variables lookup, storage/assignment and deletion. Descriptors are mainly used to control what happens when a attribute is looked up/altered/removed, to override their default behaviour. So instead of class controlling what happens to the attribute, the attribute decides for itself what goes and what comes out when called/assigned. This operations as we know are performed using the '.' operator. More details on descriptors working check [this](https://docs.python.org/3/howto/descriptor.html).
```Python
## Descriptor example
class MyDescriptor:
    """ This is a simple descriptor that allows to create custom descriptor object."""
  
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
## 6. OOP concepts
#### What is OOP?
Wikipedia says
> Object-oriented programming is an approach to designing modular reusable software systems. It is a programming paradigm based on the concept of "objects".

Classes and Objects are the two important aspects of OOP. And as we saw earlier an Object is a instance of class and it has its own attributes & methods which are defined under its represented class.
#### Why OOP?
It helps in reducing code complexities & redundancy by promoting better software design practices as opposed to functional/structural programming using the concept called "objects". OOP really shines when designing a large software systems which typically requires huge amount of inter-dependencies among the blocks of code. By following OOP approach, a software system becomes more reusable, maintainable, scalable, secure and overall less complex compared to the structural programming.

**There are four main principles of OOP: [Inheritance](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#1-inheritance), [Encapsulation](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#2-encapsulation), [Abstraction](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#3-abstraction) and [Polymorphism](https://github.com/Anku5hk/Programmers_guide_to_Python/blob/main/book.md#4-polymorphism).**
### 1. Inheritance
* Instead of re-writing the code for all similar classes like in functional programming, we re-use the methods/variables of a class inside another class in OOP. This concept is Inheritance. So basically inheritance helps to eliminate the redundant code.
* We inherit a base/super class and use its methods/variables inside a child/sub class, but not the other way. Python also supports Multilevel and Multiple inheritance.
* **super()**: This is the function to access parent's methods/variables inside of a child class, when called it returns a temporary object of parent class which then can be used to access to all of its methods/variables. 
* **Method Resolution Order (MRO)**: Is the order in which Python looks for a method in hierarchy of classes. The general order is **child -> parent1 -> parent2...**. When a method/variable is searched, it is looked for in this order. Any name collision is avoided by following this order.
```Python
## Single Inheritance
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


## Multilevel Inheritance
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


## Multiple Inheritance
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

# inherit MyParent1 and MyParent2 classes
class MyChild(MyParent1, MyParent2): 
  def __init__(self, arg1):
      self.arg1 = arg1
      # initialize first parent using 'super()'
      super().__init__()
      print(self.para1) # 10
      # initialize second parent by passing 'self' object to its constructor
      MyParent2.__init__(self) 
      # so now MyParent2's variables/methods be acessed
      print(self.para1) # 20
      print(self.para2) # 42

  def my_func(self, num):
    # here MyParent1's method will be called, due to MRO
    output1 = self.other_method(num) # similar to 'super().other_method(num)'
    return output1

# create child instance
child = MyChild(30)
print(MyChild.mro()) # [<class '__main__.MyChild'>, <class '__main__.MyParent1'>, <class '__main__.MyParent2'>, <class 'object'>]
# same as before, calling MyParent1's method
print(child.other_method(2)) # 4

# to call MyParent2's same named method using child instance
# call with class and pass child instance
output1 = MyParent2.other_method(child, 2) # 8
output2 = MyParent1.other_method(child, 2) # 4
```
### 2. Encapsulation
* Encapsulation refers to simply wrapping attributes/data and methods under a single class. This data(of any data-type/data-structure/object) can be only accessed/altered by the class methods themselves essentially to restrict access from outside of the class. This is called data hiding. 
* This technique is essential to protect private data to be accessed/misused form another class directly. To implement this we use **Access Modifiers**. They are used to define the access type of a variable inside a class. 
* Three Types of Access modifiers. 
  1. **Public**: Can be accessed anywhere in the program. All variables are public by default.
  2. **Protected**: Only the current class and derived class can access them. Use "\_" underscore define them.
  3. **Private**: Only the current class can access them, not even their instance can access them. Use "\_\_" underscore define them.
* First the private data is set to 'private' type to restrict the direct access and if we want to allow these private data to be accessed/modified by outside class, public **setters()** and **getters()** methods can be used like in Java/Javascript. But python also has another way, the 'property' object.
* In python, all variables are public by default and the way private/protected are implemented they don't really work as one would expect, below are some examples.
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
  def getMyVar(self):
    return self.__my_var3
  def setMyVar(self, new_value):
    # if you want '__my_var3' 'read-only' you can raise AttributeError, uncomment the following line 
    # raise AttributeError("Cannot change this value")
    self.__my_var3 = new_value  
    
some_instance = MyClass()
print(some_instance.getMyVar()) # 30
some_instance.setMyvar(50)
print(some_instance.getMyVar()) # 50
# but still can't access directly
print(some_instance.__my_var3) # AttributeError

## Problem with python's access modifier implementation
# '__dict__' a special variable in python keeps track of variables/functions of an object/class
# this process is name mangling, which uses '_CLASSNAME' prefix for private variables
# print this to show private variables
print(my_instance.__dict__) # {'my_var1': 10, '_my_var2': 20, '_MyClass__my_var3': 30}
# which then further can be accessed using the naming convention
print(my_instance._MyClass__my_var3) # 30
# also can delete the variable
del my_instance._MyClass__my_var3 
# further crashing the program
print(my_instance._MyClass__my_var3) # AttributeError
```
* **property()** </br>
**Parameters** => [fget=None, fset=None, fdel=None, doc=None] </br>
**Returns** => property </br>
**Explaination**: It is a pythonic way to use getters and setters in encapsulation. 'property()' function simply allows assigning/altering private variable using '.' operator. 'property()' has parameters like fget(which represents getter function), fset(which represents setter function), fdel(which represents delete function) and doc(which is a string, to provide some information). For more implementation details check [Python docs](https://docs.python.org/3/howto/descriptor.html#properties).
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
    
  # if you dont want '__my_var3' value to be altered, don't define this 'setter' method     
  # setter method for '__my_var3'
  # Notice: the <VAR_NAME> decorator  
  @my_var.setter
  def my_var(self, new_value):
    print("Setter function called")
    self.__my_var3 = new_value    
  
  # if you dont want '__my_var3' value to be deleted, don't define this 'deleter' method     
  # deleter method for '__my_var3'
  @my_var.deleter
  def my_var(self):
    print("Deleter function called")
    del self.__my_var3   
  
  # getter method for '__my_var4'
  @property
  def some_var(self):
    return self.__my_var4

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

## References
* [Python Official docs](https://docs.python.org/3/reference/index.html)
* [Time complexity python](https://wiki.python.org/moin/TimeComplexity)
