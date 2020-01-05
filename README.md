# Python: An Overview
Based on *Automate the Boring Stuff with Python* by Al Sweigart.

## Execution
- A Python program terminates, or exits, when there are no more lines of code to execute, or run.
- The program execution is a term for the current instruction being executed.

## Expressions
- Expressions consist of values (e.g., 2) and operators (e.g., +).
- A function call can be used in an expression because the call evaluates to its return value.
- Expressions can always evaluate (i.e., reduce) down to a single value.

## Blocks
Lines of Python code grouped together are called blocks.
- Blocks begin when indentation increases.
- Blocks can contain other blocks.
- Blocks end when the indentation decreases to zero, or to the indentation of the containing block.

[Lists](#Lists) are exceptional to block indentation rules.
The line continuation character (\) is used to split a single instruction across multiple lines.

## Output & Input
Printing in Python is accomplished with the `print()` function.

The *pprint* module (pretty print) has a `pprint()` function,  which displays dictionary values cleanly, and a `pformat()` function, which returns the "pretty" text as a string value.

The `input()` function waits for the user to type input and press **Enter**. The value is stored as a string.

### Escape characters
"An escape character lets you use characters that are otherwise impossible to put into a string."
Escape character | Notes
--|:--
`\` | Used before single quotes, double quotes, or backslashes
`\t` | Tab
`\n` | Newline (line break)

## Comments
Comments are ignored and begin with a hash mark (#).
Blank lines are ignored.
Multiline comments can be written as multiline strings.

## Operators
Symbol | Meaning
--|:--
 `**` | Exponent
 `%` | Modulus
 `//` | Integer division/floored quotient
`/` | Division
`*` | Multiplication | String and list replication
`-` | Subtraction
`+` | Addition | String and list concatenation

### Assignment & augmented assignment operators
An assignment statement consists of a variable name, the assignment operator, and the value to be stored.

Symbol | Meaning
--|:--
`=` | Assignment operator
`+=` | Can also perform string and list concatenation
`-=` |
`*=` | Can also perform string and list replication
`/=` | 
`%=` |


#### Multiple assignment
Multiple assignment refers to assigning multiple variables with the values in a list. The number of variables and the length ot the list must be equal.
```python
cat = ['fat', 'black', 'loud']
size, color, disposition = cat

#Multiple assignment with a for loop
spam = {'color':'red', 'age':42}
for k, v in spam.items():
	print('Key: ' + k + ' | Value: ' + str(v))
```

### Comparison operators
Symbol | Meaning
--|:--
`==` | Equal to
`!=` | Not equal to
`<` | Less than
`>` | Greater than
`<=` | Less than or equal to
`>=` | Greater than or equal to


## Booleans
Boolean, or binary, operators always take two Boolean values or expressions.

### Boolean operators (and order of operations)

Operator | Meaning
--|:--
`not` | Operates only on one Boolean value; evaluates to the opposite
`and` | Evaluates to True if both Boolean values are True
`or` 	| Evaluates to True if either of the Boolean values is True
`in` and `not in` | Operators in list or list-like expressions (i.e., (some item) in/not in (some list)) which evaluate to a Boolean value. Can be used with strings (as strings are like lists of single characters).

## Data types
- A data type is a category for values.
- Every value belongs to one data type.

Data type | Notes
--|:--
`int` | (Integer) Whole numbers
`float`| Floating-point numbers
`string` | Text. Delimited by 'single' or "double" quotes. Immutable data type. A raw string is marked with an `r` before the opening quotation mark; raw strings ignore any escape characters. A multiline string begins and ends with triple quotation characters (`'''` or `"""`).
`bool` | Boolean. True (any value that is not 0) or False (0).
`NoneType` | Consists only of `None`
`list` | A value that contains multiple values; "list value" refers to the list itself.
`dict_keys` | A list of the keys of a dictionary
`dict_values` | A list of the values of a dictionary
`dict_items` | A list of tuples for the items of a dictionary

### Data type conversion functions
Function | Notes
--|:--
`str()`	| Data type conversion
`int()` 	| Data type conversion
`float()` | Data type conversion
`list()` 	| Data type conversion (from tuple or list-like object (see Dictionary Methods))
`tuple()` | Data type conversion (from list)

## Functions
Functions are "called" (i.e., a "function call"). Values are passed to functions. Passed values are arguments.
Functions are identified by () after the function name.
Functions may take keyword arguments which modify the output.
All function calls need to evaluate to a return value:
- `return statement`
- `return None`
- (or simply) `return`

Function | Notes | Keyword Arguments
--|:--|:--
`print()` | Displays the string value inside the parentheses on the screen | end=; sep=
`len()` | Evaluates to the integer value of the number of characters in a string or number of values in a list
`range(start, stop, step)` | Used with for loops.
`sys.exit()` | A flow control function which causes the program to terminate or exit.
`type()` | Displays the data type 

### Function definition
Functions are defined with the `def` statement
```python
def functionName(parameters):
	code block, which is the function body, executed upon function call
	return statement
```
Code in a function's local scope cannot use variables in any other local scope.

## Methods
A method is "the same thing as a function, except it is 'called on' a value."
The syntax is `value.method`
Methods belong to a single data type.

## Variables
A variable is "like a box in the computer's memory where you can store a single value."
A variable is initialized the first time a value is stored in it.
Overwriting refers to storing new value in a variable.
Variables:
- Can only be one word, case sensitive
- Can only use letters, numbers, and underscore (_) character
- Cannot begin with a number

Different variables can use the same name if they are in different scopes.

Python uses references whenever variables must store values of mutable data types.

### Variable scope
If a variable is being used in the global scope, then it is always a global variable.
If there is a global statement for that variable in a function, it is a global variable.
If the variable is used in an assignment statement in the function, it is a local variable.
If the variable is not used in an assignment statement, it is a global variable.

## Flow Control
- Flow control statements "can decide which Python instructions to execute under which conditions." 
- Flow control statements can begin with a condition. 
- All flow control statements end with a colon. 
- The block of code which follows is called the clause.

Statement | Notes
--|:--
`if` | The clause following an `if` statement will execute if the statement's condition is True.
`else`	| The else clause is executed only when the `if` (and `elif`) statement's condition is False. An else statement does not have a condition.
`elif` | The "else if" statement always follows an if or another elif statement. `elif` provides another condition that is checked only if any of the previous conditions were False. It is not guaranteed that at least one of the clauses will be executed. In a chain of `elif` statements, only one or none of the statements will execute.
`while`	| A while clause will execute as long as the while statement's condition is True. Often called a "while loop" or just "loop." The condition is always checked at the start of each iteration.
`break` | The "break statement" immediately exits the clause of a while loop or a for loop. The break statement consists of only the `break` keyword.
`continue` | The "continue statement" causes the program execution to restart. The flow control condition is reevaluated like a normal loop cycle.
`for`  `in` | Repeats the code block once for each value in a list or list-like (sequence) value. 

```python
for i in range(5):
    print(i)
# Output is 0,1,2,3,4

for i in [0,1,2,3,4]:
    print(i)
#Output is same as above
```

## Modules
- Python comes with a set of modules called the standard library. 
- Each module is a Python program that contains a related group of functions that can be embedded in your programs.
- Modules must be imported with the `import` keyword; multiple modules can be imported via comma separation.
- To use functions from imported module, you must first type the module name followed by a period.
- Alternativley, modules can be imported with the `from` keyword, e.g.:
```python
from random import *
```
- With a `from ... import *` statement, function calls do not require the module name prefix.

## Parameters
A parameter is a variable in which an argument is stored when a function is called. 
Parameter values are forgotten upon function return.
In general, the value that a function call evaluates to is called the return value of the function. 
A return statement consists of the `return` keyword and the value or expression that the function should return.
Keyword arguments, often used for optional parameters, are identified by the keyword put before them in a function call. E.g.,:
	print('Hello', end=' ') (ending with a space instead of the newline)

## Scope
Parameters and variables that are assigned in a called function are said to exist in that function's local scope.
Variables that are assigned outside all functions are said to exist in the global scope.
A variable must be either a local variable or a global variable.
	Code in the global scope cannot use any local variables.
	Local scope can access global variables using the "global" statement.



## Errors
Errors can be handled with try and except statements. I.e.:
		try:
			the try clause contains the code that could potentially have an error
		except <ErrorType>:
			the except clause is executed if an error happens. Execution does not return to the try clause.

Error Type | Description
--|:--
`ValueError` | E.g., passing a string where an integer is expected, or a float for an index
`ZeroDivisionError` | Dividing by 0
`IndexError` | The index exceeds the number of values in a list
`KeyError` | The key does not exist in the dictionary
`NameError` | The variable which such a name does not exist / is not defined
`TypeError` | E.g., expecting 1 argument but receiving 0
`AttributeError` | E.g., when calling a list method on a string

## Lists
- Lists `[]` contain an ordered series of values
- Lists can be stored in variables or passed to a function.
- A list is a mutable data type: it can have values added, removed, or changed.
- Values inside a list are called items. Items are separated by commas (comma-delimited).
- The location of an item within a list is numerically represented by an integer called the index. 
- The first value in a list is at index 0.
- Lists can contain other list values, accessed by using multiple indexes, e.g., \[0\][1]; the second item in the first list.
- Negative integers count backwards from the end of a list (i.e., -1 is the last item, -2 is the penultimate item).

### Slices
- A slice is like an index, but used to get several values.
E.g., a slice list[0:2] goes up to, but does not include, the value at the second index.
- A slice evaluates to a new list value.
- The first or second value of a slice can be omitted to represent, respectively, beginning at the start of a list, or continuing until the end of a list.

`del` can be used to delete variables (seldom used this way) or delete values from a list
```python
shoppingList = ['milk','bread','eggs']
del shoppingList[0]
# shoppingList == ['bread','eggs']
```
The `del` statement is useful if you know the index; else the `remove()` method may be more useful.

### List methods
Method | Notes
-- | :--
`index(value)` | Returns the index of the argument passed (only the first occurrence).
`append(value)` | Adds the argument to the end of the list.
`insert(index, value)` | Inserts the value at the index passed.
`remove(value)` | Removes the argument from the list (only the first occurrence).
`sort()` | Keywords: reverse=True; key=str.lower


### Copying lists
- List references are used during variable assignment: if two variables are assigned to the same list, and the list 'changes' for one variable, the underlying reference is actually changing (so it 'changes' for both variables).
```python
breakfast = ['bacon','eggs','toast']
myBreakfast = breakfast
yourBreakfast = breakfast
yourBreakfast.append('coffee')

# evaluates to True
'coffee' in myBreakfast
```

The *copy* module has the `copy()` and `deepcopy()` functions.

Function | Notes
--|:--
`copy.copy()`	| makes a duplicate copy of a mutable value
`copy.deepcopy()` | used for copying mutable values that contain mutable values (e.g., a list with lists)

## Tuples
- Tuples `()` are like lists, but they are immutable.
- A tuple with only one value is indicated with a trailing comma (to distinguish from regular parentheses operator)
```python
('singletonTuple',)
 ```

## Dictionaries
- A dictionary `{}` is an unordered collection of many values and their associated keys.
- A dictionary index is called a "key." A "key-value pair" is a key and its associated value.
 - Dictionary indices (keys) can be other data types beyond integers.
- Checking for a value `in` a dictionary's keys is the same as checking `in` the dictionary itself.
```python
spam = {'car':'ford', 'boat':'pearson'}

# The below expressions both evaluate to True
'car' in spam.keys()
'car' in spam
```

### Dictionary methods
Values returned are not lists (immutable).
Passing the return value to the `list()` function is acceptable.

Method | Notes
--|:--
`keys()` | List-like
`values()` | List-like
`items()`	 | Tuples of keys and values
`get(key, fallback value)` | If the key passed does not exist, the default (fallback) value is returned
`setdefault(key, default value)` | If the key passed does not exist, a key is created with the passed value. If the key already exists, the existing value is not changed.

(147/ 505)

[https://docs.python.org/3/tutorial/index.html](https://docs.python.org/3/tutorial/index.html)
