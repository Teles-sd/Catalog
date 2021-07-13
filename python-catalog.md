
# Python <!-- omit in toc -->


This is my summary for **Python**.
<!-- --><br/>

> **Notes:**
> 
> This is not a step by step guide to Python.  
> However, there is a lot of information here.
> 
> You could start at [this section](#python-help) for how to get help within Python.
>

<!-- --><br/>

------------------------------------

### TABLE OF CONTENT

- [TABLE OF CONTENT](#table-of-content)
- [TERMINOLOGY](#terminology)
- [PACKAGES](#packages)
- [REFERENCES](#references)
- [SOME COMMANDS ON CONDA & JUPYTER](#some-commands-on-conda--jupyter)
  - [Misc](#misc)
- [PYTHON HELP](#python-help)
  - [Built-in](#built-in)
  - [On Jupyter or IPython](#on-jupyter-or-ipython)
- [OPERATIONS](#operations)
  - [Operators Precedence](#operators-precedence)
  - [Numbers](#numbers)
  - [Reserved Words](#reserved-words)
- [STRINGS](#strings)
  - [String basics](#string-basics)
  - [String indexing](#string-indexing)
  - [String functions](#string-functions)
  - [String methods](#string-methods)
- [STRING FORMATTING](#string-formatting)
  - [Old Formatting Method](#old-formatting-method)
  - [New Formatting Method](#new-formatting-method)
  - [Other (weird) way of formatting](#other-weird-way-of-formatting)
- [LISTS](#lists)
  - [List basic operations](#list-basic-operations)
  - [List Indexing](#list-indexing)
  - [List methods](#list-methods)
  - [List Comprehension](#list-comprehension)
- [DICTIONARIES](#dictionaries)
  - [Dictionary basics](#dictionary-basics)
  - [Dictionary methods](#dictionary-methods)
- [TUPLES](#tuples)
  - [Tuple basics](#tuple-basics)
  - [Tuple unpacking](#tuple-unpacking)
- [SETS](#sets)
  - [Set basic](#set-basic)
  - [Set methods](#set-methods)
- [FILES](#files)
  - [Open File](#open-file)
  - [File methods](#file-methods)
  - [Create file with StringIO](#create-file-with-stringio)
- [CODE FLOW CONTROL STRUCTURES](#code-flow-control-structures)
  - [if-elif-else](#if-elif-else)
  - [for-else-break](#for-else-break)
  - [while](#while)
  - [Stop repetitions (break, else & continue)](#stop-repetitions-break-else--continue)
  - [Boolean functions](#boolean-functions)
- [FUNCTIONS](#functions)
  - [Function basics](#function-basics)
  - [Args & Kwargs](#args--kwargs)
  - [Lambda](#lambda)
- [UNPACKING (aka STARRED EXPRESSIONS)](#unpacking-aka-starred-expressions)
- [SCOPE & NAMESPACES](#scope--namespaces)
- [OBJECT ORIENTED: CLASSES & OBJECTS](#object-oriented-classes--objects)
  - [Class basics](#class-basics)
  - [Inheritance](#inheritance)
  - [Special methods](#special-methods)
- [ERRORS: TRY & EXCEPT](#errors-try--except)
- [PACKAGES, MODULES & IMPORTING](#packages-modules--importing)
  - [Some info](#some-info)
  - [Modules](#modules)
  - [Packages](#packages-1)
- [BUILT-IN FUNCTIONS FOR ITERABLES](#built-in-functions-for-iterables)
  - [Map](#map)
  - [Zip](#zip)
  - [Filter](#filter)
  - [Reduce](#reduce)
  - [Enumerate](#enumerate)
- [DECORATORS & CLOSURE](#decorators--closure)
  - [Decorator](#decorator)
  - [Closure](#closure)
- [ITERATORS & GENERATORS](#iterators--generators)
  - [Iterator](#iterator)
  - [Generator](#generator)
- [DEBUGGING](#debugging)
  - [Python Debugger](#python-debugger)
- [COLLECTIONS MODULE](#collections-module)
  - [Counter](#counter)
  - [DefaultDict](#defaultdict)
  - [NamedTuple](#namedtuple)
- [DATETIME MODULE](#datetime-module)
  - [Parsing & Formatting](#parsing--formatting)
- [EXECUTION TIME](#execution-time)
  - [TimeIt Module](#timeit-module)
  - [Line Profiler package](#line-profiler-package)
- [REGULAR EXPRESSIONS (RE) MODULE](#regular-expressions-re-module)
  - [RE basics](#re-basics)
  - [Pattern Repetition Syntax](#pattern-repetition-syntax)

<!-- --><br/>



------------------------------------

### TERMINOLOGY


| Term/Expression | Meaning |
| :-------------: | :------ |
| `<description>` | To replace, or that will be replaced, according to description (without the `<` and `>`). |
| `...`           | Possible to repeated pattern. |
| `$`             | Some command to be used on the Terminal (shell). |
<!-- --><br/>
<!-- --><br/>



- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### PACKAGES


| Source | Package | Description |
| :----: | ------- | ----------- |
| pacman | python  | Next generation of the python high-level scripting language. |
| conda  | python  | ??? |
| AUR    | python-line_profiler  | Line-by-line profiler for python. |
| conda  | line_profiler  | ??? |

<!-- --><br/>
<!-- --><br/>



- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



----------------------------------

### REFERENCES

- [Python Home Page][home]

- [Python Documentation][doc]
  
  - [Documentation: Regular Expression][re]

- [Glossary][glossary]

- [The import system][import]

- [Modules][modules]

<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



[home]:https://www.python.org/ "Python.org"
[doc]:https://docs.python.org/3/ "Python Documentation"
[re]:https://docs.python.org/3/library/re.html "Regular expression operations"
[glossary]:https://docs.python.org/3/glossary.html "Glossary"
[import]:https://docs.python.org/3/reference/import.html "The import system"
[modules]:https://docs.python.org/3/tutorial/modules.html "Modules - Python documentation"

------------------------------------

### SOME COMMANDS ON CONDA & JUPYTER


- List environments:

```shell
$ conda env list
```
<!-- --><br/>


- Activate/deactivate environment (conda>=4.6):

```shell
$ conda activate <environment>
```
```shell
$ conda deactivate <environment>
```
<!-- --><br/>


- Open jupyter:

```shell
(<env>)$ jupyter notebook
```
```shell
(<env>)$ jupyter notebook <file>.ipynb
```
```shell
(<env>)$ jupyper lab
```
```shell
(<env>)$ jupyper lab <file>.ipynb
```
<!-- --><br/>


- List running Jupyter servers:

```shell
(<env>)$ jupyter notebook list
```
<!-- --><br/>


- Terminate Jupyter server:

```shell
(<env>)$ jupyter notebook stop
```
```shell
(<env>)$ jupyter notebook stop <port>
```
<!-- --><br/>


- Jupyter shortcuts:

|     Shortcut      |  Action  |
| :---------------: | -------- |
| [Shift] + [Enter] | Run cell & go next.  |
| [Ctrl] + [Enter]  | Run cell & DON´T go next.  |
| [Alt] + [Enter]   | Run cell & add cell bellow.  |
| [D] + [D]         | Delete selected cell.  |

<!-- --><br/>



#### Misc


- Finding anaconda´s install directory:

```shell
$ which conda
```
<!-- --><br/>


- Finding the anaconda´s python interpreter (environmental):

```shell
(<env>)$ which python
```
<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### PYTHON HELP


#### Built-in


- Python documentation about a object:

```Python
help(<object>)
```
```Python
print(<object>.__doc__)
```
<!-- --><br/>


- Display the type of a object:

```Python
type(<object>)
```
<!-- --><br/>


- **Zen of Python**:

```Python
import this
```
<!-- --><br/>
<!-- --><br/>



#### On Jupyter or IPython


- Show possible Methods and Attributes for the Python object.  
  Type then press [Tab]:

```Python
<object>.
```
<!-- --><br/>


- Show Object Documentation.  
  Type then press [Shift] + [Tab]:

```Python
<object>.
```
<!-- --><br/>


- Show Function Parameters.  
  Type then press [Shift] + [Tab]:

```Python
<function>()
```
<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### OPERATIONS


#### Operators Precedence


- Order of operations (Operator Precedence):

|        Operator        |  Description  |
| :--------------------: | ------------- |
|         `**`           | Exponential.  |
|     `~`, `+`, `-`      | Complement (bits reversed), unary plus and minus. |
|  `*`, `/`, `%`, `//`   | Multiply, divide, modulo, floor division.  |
|       `+`, `-`         | Addition and subtraction.  |
|      `>>`, `<<`        | Right and left bitwise shift.  |
|          `&`           | Bitwise 'AND'.  |
|       `^`, `|`         | Bitwise 'XOR' and 'OR'.  |
| `<=`, `<`, `>`, `>=`   | Logical operators.  |
| `=`, `%=`, `/=`, `//=`, <br/> `-=`, `+=`, `*=`, `**=`| Assignment operators.  |
|      `is`, `is not`    | Identity operators.  |
|      `in`, `not in`    | Membership operators.  |
|   `not`, `or`, `and`   | Logical operators.  |

<!-- --><br/>


> **Examples**
>
> ```
> Dividend ->  9 | 4  <- Divisor
>                |---
> Reminder ->  1 | 2  <- Quotient
> ```
> ---
>
> ```Python
> # Division:
> 9/4
> ```
> 
> Output:
> ```
> 2.25
> ```
> ---
>
> ```Python
> # Floor division (quotient):
> 9//4
> ```
> 
> Output:
> ```
> code
> ```
> ---
>
> ```Python
> # Mod (reminder):
> 9 % 4
> ```
> 
> Output:
> ```
> 1
> ```
> ---

<!-- --><br/>
<!-- --><br/>



#### Numbers


- Absolute Value:

```Python
abs(<num>)
```
<!-- --><br/>


- Round with some precision for the number of decimal cases (default=0):

```Python
round(<num>)
```
```Python
round(<num>, <precision>)
```
<!-- --><br/>


- Returns a 2-tuple containing the numerator and denominator:

```Python
<float>.as_integer_ratio()
```
<!-- --><br/>


- Binary:

```Python
bin(<number>)
```
<!-- --><br/>


- Hexadecimal:

```Python
hex(<number>)
```
<!-- --><br/>


- Pow (equivalent to x**y ):

```Python
pow(<num>, <num>)
```
<!-- --><br/>


- Pow (equivalent to (x**y)%z ):

```Python
pow(<num>, <num>, <num>)
```
<!-- --><br/>
<!-- --><br/>



#### Reserved Words

```Python
False
True
None

and
or
is
in
not

if
elif
else
for
continue
finally
while
break

def
pass
return
lambda
yield

class

try
except
raise
assert

from
import
as
with

nonlocal
global

del
```
<!-- --><br/>
<!-- --><br/>



- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### STRINGS


#### String basics


- To define a **String**, simple or double quotation marks can be used:

```Python
' <text> '
```
```Python
" <text> "
```
<!-- --><br/>


- To include quotes on a String define it using the other, or escape it:

```Python
' "<text>" '
```
```Python
" '<text>' "
```
```Python
' \'<text>\' '
```
```Python
" \"<text>\" "
```
<!-- --><br/>


- Define a String with implicit EOL:

```Python
''' <text> 
    ...
    <text> '''
```
```Python
""" <text> 
    ...
    <text> """
```
<!-- --><br/>


- Get a raw string (any escape sequence interpretation will be ignored):

```Python
r <string>
```
<!-- --><br/>


- Some Special Characters:

|    Special Character   |  Description   |
| :--------------------: | -------------- |
|         `\t`           | Tab.           |
|         `\n`           | EOL (New line).|

<!-- --><br/>
<!-- --><br/>



#### String indexing


- Access an element (**index starts at 0**):

```Python
<string>[<index>]
```
<!-- --><br/>


- Access multiple elements (_Slicing_).
  - Both index are optional.
  - The `start` is included.
  - The `stop` is **not** included.

```Python
<string>[<start>:<stop>]
```
<!-- --><br/>


- Access elements at steps (increment, accepts negative value):

```Python
<string>[::<step>]
```
```Python
<string>[<start>:<stop>:<step>]
```
<!-- --><br/>
<!-- --><br/>



#### String functions


- Print string(s):

```Python
print (<string>)
```
```Python
print (<string>, ..., <string>)
```
<!-- --><br/>


- Change the EOL character to be printed (default: '\n'):

```Python
print (<string>, end=<string>)
```
<!-- --><br/>


- Change the separator character to be printed between multiple strings (default: ' '):

```Python
print (<string>, ..., <string>, sep=<string>)
```
<!-- --><br/>


- Print raw string (any escape sequence interpretation will be ignored):

```Python
print (r <string>)
```
<!-- --><br/>


- Print message and return String from console input;

```Python
input(<string>)
```
<!-- --><br/>


- Get the size　of the String:

```Python
len(<string>)
```
<!-- --><br/>


- Concatenate Stings:

```Python
<string> + <string>
```
<!-- --><br/>


- Repeat String:

```Python
<string> * <number>
```
<!-- --><br/>


- Execute code written on a String:

```Python
exec(<string>)
```
<!-- --><br/>


- Execute code written on a String and evaluate its return:

```Python
eval(<string>)
```
<!-- --><br/>
<!-- --><br/>



#### String methods


- Make first letter Upper Case:

```Python
<string>.capitalize()
```
<!-- --><br/>


- Count how many instances of a character there is:

```Python
<string>.count('<char>')
```
<!-- --><br/>


- Find position of first instance of a character:

```Python
<string>.find('<char>')
```
<!-- --><br/>


- Make string centered on a specific size using some character:

```Python
<string>.center(<size>, '<char>') 
```
<!-- --><br/>


> **Examples**
>
> ```Python
> 'hellooo'.center(20,'~')
> ```
> 
> Output:
> ```
> '~~~~~~hellooo~~~~~~~'
> ```
> ---

<!-- --><br/>


- Return `True` if all characters in the string are alphabetic, `False` otherwise:

```Python
<string>.isalpha()
```
<!-- --><br/>


- Return `True` if all characters in the string are decimal characters, `False` otherwise:

```Python
<string>.isdecimal()
```
<!-- --><br/>


- Check if there are only AlphaNumeric characters:

```Python
<string>.isalnum()
```
<!-- --><br/>


- Check if there are only Alphabetical characters:

```Python
<string>.isalpha()
```
<!-- --><br/>


- Make all Lower case:

```Python
<string>.lower()
```
<!-- --><br/>


- Make all Upper case:

```Python
<string>.upper()
```
<!-- --><br/>


- Check if is all Lower case:

```Python
<string>.islower()
```
<!-- --><br/>


- Check if is all Upper case:

```Python
<string>.isupper()
```
<!-- --><br/>


- Check if ends with a character:

```Python
<string>.endswith('<char>')
```
<!-- --><br/>


- Returns a List of Strings splitting on a character as divisor (default=' '):

```Python
<string>.split()
```
```Python
<string>.split(<divisor>)
```
<!-- --><br/>


- Returns a List of Strings, including the divisor:

```Python
<string>.partition(<divisor>)
```
<!-- --><br/>


- Replace any appearance of a pattern by other:

```Python
<string>.replace('<pattern>', '<replacement>')
```
<!-- --><br/>


- Get a String from a List of Strings, with a divisor between each element:

```Python
'<divisor>'.join(<list>)
```
<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### STRING FORMATTING

Allows to modify a string with an object.



#### Old Formatting Method


- To format a Strings with an Object, one format needs to be specified:
  - `s` - String (or any object with string representation, like numbers).
  - `d` - Integers (decimal system).
  - `f` - Floating point numbers.
  - `x` - Integers in hex representation (lowercase).
  - `X` - Integers in hex representation (uppercase).

```Python
' %<format> ' % <obj>
```
```Python
' %<format>  ...  %<format> ' % (<obj>, ..., <obj>)
```
<!-- --><br/>


- The Formatting also allows optional operators:
  - padding:
    - Minimum padding width.
    - Negative number to align to the left, default to right.
    - Type zero on front (as `%0<padding>`) to fill remaining space with zeros.
  - decimal:
    - Number of decimal cases (default=6).
    - Can also be a truncate index for strings.

```Python
' %<padding>.<decimal><format> ' % <obj>
```
<!-- --><br/>


> **Examples**
>
> ```Python
> data = ("John", "Doe", 53.44)
> format_string = "Hello %s %s. Your current balance is $%s."
> print(format_string % data)
> ```
> 
> Output:
> ```
> Hello John Doe. Your current balance is $53.44.
> ```
> ---
>
> ```Python
> numerooo = 69.69
> otro_num = 27
> a = 'Formatting operators:\n'
> n = 'Número como string: %s\n'
> i = 'Inteiro:  %d\n'
> f = 'Float:[%12.3f] \n      [123456789-12]\n'
> h = 'Hexadecimal: %X '
> 
> print( a, n % numerooo, i % numerooo, f % numerooo, h % otro_num)
> ```
> 
> Output:
> ```
> Formatting operators:
> 
> Número como string: 69.69 
> Inteiro:  69 
> Float:[      69.690] 
>       [123456789-12] 
> Hexadecimal: 1B
> ```
> ---

<!-- --><br/>
<!-- --><br/>



#### New Formatting Method


- Format a Strings with Object(s):

```Python
' {} '.format(<obj>)
```
```Python
' {}  ...  {} '.format(<obj>, ..., <obj>)
```
<!-- --><br/>

> **Note :**
> 
> The Format method does not modify the String variable; it returns a String formatted.
> 
> ---
> 
> **Example**
>
> ```Python
> aurelio = 'One: {}\nTwo: {}\nThree: {}\n'
> print(aurelio.format(1, 'two', 12.3))
> print(aurelio)
> ```
> 
> Output:
> ```
> One: 1
> Two: two
> Three: 12.3
> 
> One: {}
> Two: {}
> Three: {}
> ```
> ---

<!-- --><br/>


- The Formatting allows optional operators, Specifiers and Formatting Operators, defined below:

```Python
' {<specifiers>:<formatting>} '.format(<obj>)
```


- Specifiers Operators define what will be inserted on the String:
  - `{}` - Strings will be applied in the order passed on `format()`.
  - `{<position>}` - Positional argument (number) for strings given to `format()`.
  - `{<key>}` - Keyword argument; must be defined on `format()` arguments.


- Formatting Operators define how to format the object.  
  From each of the "groups" below, only one operator may be used.  
  It is possible to use Operators from many groups, but must be this order:
  - Fill:
    - `{:*}` - fills remaining space (from padding) with `*`.
    - `{:0}` - fills remaining space (from padding) with zeros.
  - Align:
    - `{:<}` - aligns left (default for strings).
    - `{:^}` - aligns center.
    - `{:>}` - aligns right (default for numbers).
  - Sign:
    - `{:-}` - only prints sign for negative values (default).
    - `{:+}` - prints '+' for positive values.
    - `{: }` - prints ' ' for positive and '-' for negative values.
  - Padding and Decimal:
    - `{:<padding>.<decimal>}` - both.
    - `{:<padding>}` - minimum padding width.
    - `{:.<decimal>}` - number of decimal cases (default=6). Used as truncate index if a strings is passed.
  - Format:
    - `{:d}` - Integers (decimal system).
    - `{:f}` - Floating point numbers.
    - `{:b}` - Binary.
    - `{:e}` - Exponent representation (aka. scientific notation).
    - `{:E}` - Exponent representation with uppercase `E`.
    - `{:%}` - Faction to percentage.

<!-- --><br/>


- Dynamic Formatting:

```Python
' {:{fill}{align}{width}} '.format(<obj>, fill='<fill>', align='<align>', width=<padding>))
```
<!-- --><br/>


> **Examples**
>
> ```Python
> ' {2} {0} {3} {1} '.format( 'one', 'three', 'zero', 'two' )
> ```
> 
> Output:
> ```
> ' zero one two three '
> ```
> ---
>
> ```Python
> B='bee'
> C='see'
> ' {a} {b} {c} '.format( b=B, c=C, a='eei' )
> ```
> 
> Output:
> ```
> ' eei bee see '
> ```
> ---
>
> ```Python
> "Binary representation of {0} is {0:b}".format(12)
> ```
> 
> Output:
> ```
> 'Binary representation of 12 is 1100'
> ```
> ---

<!-- --><br/>


- Format a Strings [unpacking](#unpacking-aka-starred-expressions) a [Tuple](#tuples):

```Python
' {}  ...  {} '.format( * <tuple> )
```
<!-- --><br/>


- Format a Strings [unpacking](#unpacking-aka-starred-expressions) a [Dictionary](#dictionaries):

```Python
' {<key>}  ...  {<key>} '.format( ** <dict> )
```
<!-- --><br/>


- Format a Strings with a [Object](#object-oriented-classes--objects)'s attributes:

```Python
<obj> = <Class>()

' {<variable>.<attribute>}  ...  {<variable>.<attribute>} '.format(<variable>=<obj>)
```
<!-- --><br/>
<!-- --><br/>



#### Other (weird) way of formatting


- Format with local variables:

```Python
f' {<var>} '
```
```Python
f' {<dict>[<key>]}  ...  {<dict>[<key>]} '
```
<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### LISTS

- In Python, Lists allow multiple types of data and don´t have a fixed size.

<!-- --><br/>

#### List basic operations


- Define a List:

```Python
<list> = [<element>, ..., <element>]
```
<!-- --><br/>


- Append a element to the end of a List:

```Python
<list>.append(<element>)
```
<!-- --><br/>


- Insert a element on a specific index:

```Python
<list>.insert(<index>, <element>)
```
<!-- --><br/>


- Removes an element of index from a list and returns it (default= [-1](#list-indexing)):

```Python
<list>.pop()
```
```Python
<list>.pop(<index>)
```
<!-- --><br/>


- Remove the first occurrence of a element:

```Python
<list>.remove(<element>)
```
<!-- --><br/>


- Add Lists to another:

```Python
<list> + <list>
```
```Python
<list>.extend(<list>)
```
<!-- --><br/>


- Check if an element is in a List (returns a boolean):

```Python
<element> in <list>
```
<!-- --><br/>
<!-- --><br/>


#### List Indexing

- The same ways of accessing and indexing Strings works for Lists.

<!-- --><br/>


- Access an element (**index starts at 0**):

```Python
<list>[<index>]
```
<!-- --><br/>


- Access multiple elements (_Slicing_).
  - Both index are optional.
  - The `start` is included.
  - The `stop` is **not** included.

```Python
<list>[<start>:<stop>]
```
<!-- --><br/>


- Access elements at steps (increment, accepts negative value):

```Python
<string>[::<step>]
```
```Python
<string>[<start>:<stop>:<step>]
```
<!-- --><br/>
<!-- --><br/>


> **Examples**
>
> ```Python
> asdf = [1,2,'minha juda']
> print(asdf[::-1])
> ```
> 
> Output:
> ```
> ['minha juda', 2, 1]
> ```
> ---
>
> ```Python
> print(asdf[-1])
> ```
> 
> Output:
> ```
> minha juda
> ```
> ---
>
> ```Python
> print(asdf[-1][::-1])
> ```
> 
> Output:
> ```
> aduj ahnim
> ```
> ---

<!-- --><br/>
<!-- --><br/>


#### List methods


- Get the index of a specific element:

```Python
<list>.index(<element>)
```
<!-- --><br/>


- Reverse list elements order:

```Python
<list>.reverse()
```
<!-- --><br/>


- Return list elements sorted elements without altering the list(or string)):

```Python
sorted(<list>)
```
```Python
sorted(<string>)
```
<!-- --><br/>


- Sort list elements (the list is modified):

```Python
<list>.sort()
```
<!-- --><br/>


- Count how many times a element appears:

```Python
<list>.count(<element>)
```
<!-- --><br/>
<!-- --><br/>


#### List Comprehension

- Check [code flow control](#code-flow-control-structures) for a better understanding.

<!-- --><br/>


- Define a List iteratively using list comprehension:

```Python
[<element/instruction> for <element> in <iterable>]
```
<!-- --><br/>


- Use list comprehension to filter elements:

```Python
[<element/instruction> for <element> in <iterable> if <boolean>]
```
```Python
[<element/instruction> if <boolean> else <element/instruction> for <element> in <iterable>]
```
<!-- --><br/>


- Use list comprehension with variables from different iterables:

```Python
[<element/instruction> for <element> in <iterable> ... for <element> in <iterable>]
```
<!-- --><br/>
<!-- --><br/>


> **Examples**
>
> ```Python
> celsius = [0, 10, 15, 20, 30, 50, 100]
> fahrenheit = [ int(temp*(9/5)+32)  for temp in  celsius ]
> ```
> 
> Output:
> ```
> [32, 50, 59, 68, 86, 122, 212]
> ```
> ---
>
> ```Python
> l_1 = [1,2,3]
> l_2 = [4,5,6]
> l_3 = [7,8,9]
> mat = [l_1, l_2, l_3]
> 
> first_col = [row[0] for row in mat]
> diag = [mat[ind][ind] for ind in [0,1,2] ]
> diag2 = [mat[ind][2-ind] for ind in [0,1,2] 
> fulllist = [ mat[i][j]  for i in range(len(mat)) for j in range(len(mat[i]))]
> 
> print('first column: ', first_col)
> print('main diagonal: ', first_col)
> print('secondary diagonal: ', first_col)
> print('full list: ', first_col)
> ```
> 
> Output:
> ```
> first column:  [1, 4, 7]
> main diagonal:  [1, 4, 7]
> secondary diagonal:  [1, 4, 7]
> full list:  [1, 4, 7]
> ```
> ---
>
> ```Python
> # Matrix multiplication using list comprehension:
> 
> X = [[12,7,3],
>      [ 4,5,6],
>      [ 7,8,9]]
> 
> Y = [[5,8,1,2],
>      [6,7,3,0],
>      [4,5,9,1]]
> 
> result = [[sum(a*b for a,b in zip(X_row,Y_col)) for Y_col in zip(*Y)] for X_row in X]
> for r in result: print(r)
> ```
> 
> Output:
> ```
> [114, 160,  60, 27]
> [ 74,  97,  73, 14]
> [119, 157, 112, 23]
> ```
> ---

<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### DICTIONARIES


#### Dictionary basics


- Define dictionary:

```Python
<dict> = {'<key>':<object> , ..., '<key>':<object>}
```
```Python
<dict> = dict(<key>=<object> , ..., <key>=<object>)
```
<!-- --><br/>


- Accessing elements:

```Python
<dict>['key']
```
<!-- --><br/>


- Adding new elements:

```Python
<dict>['key'] = <object>
```
<!-- --><br/>


- Create dictionary using _dictionary comprehension_:

```Python
{<key>:<value> for (<key>, <value>) in <iterable>}
```
<!-- --><br/>
<!-- --><br/>


#### Dictionary methods


- Returns the value of key if it exists, returns the given value otherwise:

```Python
<dict>.get(<key>, <value>)
```
<!-- --><br/>


- Get dict keys (returns a object of type `dict_keys`):

```Python
<dict>.keys()
```
```Python
list(<dict>.keys())
```
<!-- --><br/>


- Get dict values (returns a object of type `dict_values`):

```Python
<dict>.values()
```
```Python
list(<dict>.values())
```
<!-- --><br/>


- Get dict items (returns a object of type `dict_items`):

```Python
<dict>.items()
```
```Python
list(<dict>.items())
```
<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### TUPLES


#### Tuple basics

- Tuple are immutable once defined.
- Tuples have only two methods: `count` and `index`.
- The same ways of accessing and indexing Strings and Lists works for Tuples.

<!-- --><br/>


- Defining a tuple;

```Python
<tuple> = (<object> , ..., <object>)
```
<!-- --><br/>


- Return the index of a element:

```Python
<tuple>.index(<object>)
```
<!-- --><br/>


- Count how many times an element is repeated:

```Python
<tuple>.count(<object>)
```
<!-- --><br/>


- Defining a tuple with only one item:

```Python
<tuple> = (<object>, )
```
<!-- --><br/>
<!-- --><br/>


#### Tuple unpacking


- Many variables can be assigned at the same time using a Tuple containing the same number of elements as the number of variables:

```Python
(<variable>, ..., <variable>) = <tuple>
```
```Python
<variable>, ..., <variable> = <tuple>
```
<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### SETS


#### Set basic

- Sets only allow ordered, non repeating, values or elements.

<!-- --><br/>

- Define a set:

```Python
<set> = set(<iterable>)
```
```Python
<set> = {<element>, ... ,<element>}
```
<!-- --><br/>


- Add elements to set:

```Python
<set>.add(<element>)
```
<!-- --><br/>


- Discard element of a set:

```Python
<set>.discard(<element>)
```
<!-- --><br/>


- Create a set using _set comprehension_:

```Python
{<element> for <element> in <iterable>}
```
<!-- --><br/>
<!-- --><br/>



#### Set methods


- Clear set:

```Python
<set>.clear()
```
<!-- --><br/>


- Create a copy of a set:

```Python
<set> = <set>.copy()
```
<!-- --><br/>


- Return a set with the _difference_ between one and another:

```Python
<set>.difference(<set>)
```
<!-- --><br/>


- Update a set to be the _difference_ between it and another set:

```Python
<set>.difference_update(<set>)
```
<!-- --><br/>


- Return a set with the _intersection_ between one and another:

```Python
<set>.intersection(<set>)
```
<!-- --><br/>


- Update a set to be the _intersection_ between it and another set:

```Python
<set>.intersection_update(<set>)
```
<!-- --><br/>


- Return a set as the _union_ between one and another:

```Python
<set>.union(<set>)
```
<!-- --><br/>
<!-- --><br/>


> **Examples**
>
> ```Python
> l = [1,2,2,33,4,4,11,22,3,3,2]
> shit = list(set(l))
> ```
> 
> Output:
> ```
> [1, 2, 33, 4, 3, 11, 22]
> ```
> ---

<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### FILES

> **Note :**
> 
> - To read or write to a file, it needs to be opened. 
> 
> - When the work is done, **it needs to be closed**, so the resources tied with the file are freed.
> 
> ---

<!-- --><br/>
<!-- --><br/>


#### Open File


- On Jupyter or IPython, display current working directory:

```Python
pwd
```
<!-- --><br/>


- Open a file:

```Python
<file> = open('<file-path>')
```
<!-- --><br/>

```Python
<file> = open('<file-path>', '<mode>')
```
<!-- --><br/>

```Python
<file> = open('<file-path>', mode='<mode>')
```

- Operations Mode (more than one may be specified):
  - `t` - Text mode (default).
  - `b` - Binary mode.
  - `r` - Read (default), synonym of `rt`. Gives an error if the file does not exist.
  - `w` - Write. Creates the file if it does not exist, **overwrite if it does**.
  - `+` - Open for updating, synonym of `rw`.
  - `x` - Exclusive creation: creates the file, returns an error if the file already exists.
  - `a` - Append to the end of the file. Creates the file if it does not exist.

<!-- --><br/>

> **Note :**
> 
> When working with files in _text mode_, it is highly recommended to specify the encoding type.
> 
> The default encoding is platform dependent. In Linux it is `utf8`. In windows, it might be `ascii`, `cp1252` (ANSI), `iso8859_2`, ...
> 
> If relying on default the code might behave differently in different platforms.
> 
> ---


- Specify the encoding while opening a file.

```Python
<file> = open('<file-path>', '<encoding>')
```
```Python
<file> = open('<file-path>', encoding='<encoding>')
```
<!-- --><br/>


- If an exception occurs when performing an operation on the file, the code exits without closing it.  
  A safer way to use a file is:

```Python
with open('<file-path>', <encoding>) as <file>:
    <instructions>
```
<!-- --><br/>
<!-- --><br/>


#### File methods


- Return a String with the file content until EOF:

```Python
<file>.read()
```
<!-- --><br/>


- Return a String with at most the given size of characters from the file content:

```Python
<file>.read(<size>)
```
<!-- --><br/>


- Return current cursor position:

```Python
<file>.tell()
```
<!-- --><br/>


- Change stream ("cursor") offset ("position") relative to start of the file:

```Python
<file>.seek(<offset>)
```
```Python
<file>.seek(0)
```
<!-- --><br/>


- Change stream offset relative to the position indicated by `whence`:

```Python
<file>.seek(<offset>, <whence>)
```

- Possible values for `whence`:
  - `0` – start of the stream (the default); offset should be zero or positive
  - `1` – current stream position; offset may be negative
  - `2` – end of the stream; offset is usually negative

<!-- --><br/>


- Read file from current cursor position to EOL:

```Python
<file>.readline()
```
<!-- --><br/>


- Return a list with each line from cursor position to EOF:

```Python
<file>.readlines()
```
<!-- --><br/>


- A file object can als o be used as an iterable.  
  For example, to print each line:

```Python
for line in <file>:
    print(line)
```
<!-- --><br/>


- Write content to a file.
  This method also returns the number of characters written.

```Python
<file>.write('<content>')
```
<!-- --><br/>
<!-- --><br/>


- Close a file after it's used:

```Python
<file>.close()
```
<!-- --><br/>
<!-- --><br/>


#### Create file with StringIO


- Create a File Object from a string:

```Python
import io
<file> = io.StringIO(<string>)
```
<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### CODE FLOW CONTROL STRUCTURES


#### if-elif-else


- IF structure for multiple instructions:

```Python
if <boolean>:
    <instructions>
elif <boolean>:
    <instructions>
else:
    <instructions>
```
<!-- --><br/>


- IF structure possible for single line instructions:

```Python
<instruction> if <boolean> else <instruction>
```
```Python
<value> if <boolean> else <value>
```
<!-- --><br/>


- IF structure possible for multiple single line instructions:

```Python
<instruction> if <boolean> else ( <instruction> if <boolean> else (...) )
```
```Python
<instruction> if <boolean> else <instruction> if <boolean> else (...)
```
<!-- --><br/>
<!-- --><br/>


#### for-else-break

> **Note :**
> 
> Iterables are: lists, range, dictionary keys, dictionary values, dictionary items, tuples, strings, iterators, and other objects that alow to be iterated over.
> 
> ---

<!-- --><br/>


- FOR structures:

```Python
for <element> in <iterable>:
    <instructions>
```
```Python
for _ in <iterable>:
    <instructions>
```
<!-- --><br/>


- Create a range-sequence object of Integers (default: start=0, step=1):
  - Both `start` and `step` arguments are optional.
  - The `start` is included.
  - The `stop` is **not** included.

```Python
range(<start>, <stop>, <step>)
```
<!-- --><br/>


> **Examples**
>
> ```Python
> print(range(10))
> print(type(range(10)))
> print(list(range(10)))
> ```
> 
> Output:
> ```
> range(0, 10)
> <class 'range'>
> [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
> ```
> ---
>
> ```Python
> # Print integers from 1 to 30, but for multiples of 3 print "Fizz" instead, for multiples of 5 print "Buzz" instead, and for multiples of both print "FizzBuzz" instead:
> for n in range(1,31): print('FizzBuzz', end=', ') if (n%3==0 and n%5==0) else (print('Fizz', end=', ') if n%3==0 else (print('Buzz', end=', ') if n%5==0 else print(n, end=', ')))
> ```
> 
> Output:
> ```
> 1, 2, Fizz, 4, Buzz, Fizz, 7, 8, Fizz, Buzz, 11, Fizz, 13, 14, FizzBuzz, 16, 17, Fizz, 19, Buzz, Fizz, 22, 23, Fizz, Buzz, 26, Fizz, 28, 29, FizzBuzz, 
> ```
> ---

<!-- --><br/>


- FOR with [tuple unpacking](#tuple-unpacking):

```Python
for (<variable>, ..., <variable>) in [<tuple>, ..., <tuple>]:
    <instructions>
```
<!-- --><br/>


> **Examples**
>
> ```Python
> for (um, dois) in [ (1, 2), (3, 4), (5, 6) ]:
>     print("%d x %d = %d" %(um,dois,um * dois))
> ```
> 
> Output:
> ```
> 1 x 2 = 2
> 3 x 4 = 12
> 5 x 6 = 30
> ```
> ---
>
> ```Python
> for (key, value) in d.items():
>   print(key, ':', value)
> ```
> 
> Output:
> ```
> key1 : one
> key2 : two
> key3 : three

> ```
> ---

<!-- --><br/>
<!-- --><br/>


#### while


- WHILE structure:

```Python
while <boolean>:
    <instructions>
```
<!-- --><br/>
<!-- --><br/>


#### Stop repetitions (break, else & continue)


- FOR or WHILE with else and/or break.  
  Executes the `else` block after the loop, but only if it didn't find a `break`.

```Python
for <element> in <iterable>:
    <instructions>

    if <boolean>:
        <instructions>
        break
else:
    <instructions>
```
```Python
while <boolean>:
    <instructions>

    if <boolean>:
        <instructions>
        break
else:
    <instructions>
```
<!-- --><br/>


- Stop current iteration but continue repetitions:

```Python
while <boolean>:
    <instruction>

    if <boolean>:
        continue
    
    <instruction>
```
```Python
for <element> in <iterable>:
    <instruction>
    
    if <boolean>:
        continue
    
    <instruction>
```
<!-- --><br/>


> **Examples**
>
> ```Python
> x = 0
> while x <= 10:
>     x += 1
>     if (x % 2) == 1:
>         continue
>     print (x, 'is even')
> ```
> 
> Output:
> ```
> 2 is even
> 4 is even
> 6 is even
> 8 is even
> 10 is even
> ```
> ---

<!-- --><br/>
<!-- --><br/>


#### Boolean functions


- Return `True` if an object is an **instance** of a given type or any of the types within a tuple, `False` otherwise:

```Python
isinstance(<object>, <type>)
```
```Python
isinstance(<object>, type(<object>))
```
```Python
isinstance(<object>, <Class>)
```
```Python
isinstance(<object>, <type-tuple>)
```
<!-- --><br/>


- Returns `True` if **all** items in an iterable object are _True_, `False` otherwise.  
  If the iterable is empty returns `True`.

```Python
all(<iterable>)
```
<!-- --><br/>


- Returns `True` if **any** item in an iterable object is _True_, `False` otherwise.  
  If the iterable is empty returns `False`.

```Python
any(<iterable>)
```
<!-- --><br/>


> **Examples**
>
> ```Python
> # Remove all items in a List containing a number:
> foo = ['This', 'That', 'Those4423', '42', '13b', 'Yes', '2']
> [word for word in foo if not any(character.isdecimal() for character in word)]
> ```
> 
> Output:
> ```
> ['This', 'That', 'Yes']
> ```
> ---

<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### FUNCTIONS


#### Function basics


- Defining a simple function:

```Python
def <function>():
    <instructions>
```
<!-- --><br/>


- Call function:

```Python
<function>()
```
<!-- --><br/>


- Add a Docstring (a type of description the can be displayed by some IDE and on the function's help) to a function:

```Python
def <function>():
    """
    <Docstring>
    """
    <instructions>
```
<!-- --><br/>


- Function with arguments:

```Python
def <function>(<args>, ...):
    <instructions>
```
<!-- --><br/>


> **Examples**
>
> ```Python
> def isprime(num):
>     """
>     Function to check if a number is prime.
>     """
>     for i in range(2, round(num/2)):
>         if num%i == 0 :
>             print("Not prime")
>             break
>     else:
>         print("Prime")
> 
> isprime(104729)
> ```
> 
> Output:
> ```
> Prime
> ```
> ---

<!-- --><br/>


- Return:

```Python
def <function>():
    <instructions>
    return <object>
```
<!-- --><br/>


- Functions can also be defined and used inside functions.  
  Those are called _Nested Functions_.
  Check the [Scope](#nested-statements--scope) topic for a better understanding about variables.

```Python
def <outer_function>():
    <instructions>

    def <inner_function>():
        <instructions>

    <instructions>
    <inner_function>()
    <instructions>
```
<!-- --><br/>


- Recursive function:

```Python
def <some_function>(<args>):
    <instructions>
    <some_function>(<args>)
```
<!-- --><br/>


- In Python, functions are also Objects that can be assigned to variables.  
  Check the [Scope](#nested-statements--scope) topic for a better understanding of the next example.


> **Examples**
>
> ```Python
> def func():
>     a = 1
>     print(locals())
> 
> returnOfFunc = func()
> print("Type of the return: ", type(returnOfFunc))
> 
> sameFunc = func
> 
> def otherFunc(f):
>     f()
> 
> otherFunc(sameFunc)
> ```
> 
> Output:
> ```
> {'a': 1}
> Type of the return:  <class 'NoneType'>
> {'a': 1}
> ```
> ---

<!-- --><br/>


- Get a String with a source code of a function:

```Python
import inspect
inspect.getsource( <function> )
```
<!-- --><br/>
<!-- --><br/>


#### Args & Kwargs

- Tha names 'args' and 'kwargs' stand for arguments and keyword-arguments respectively.
- They are variables that allow a function to handle arguments and keyword-arguments that were not specified in the function's definition.
- When the function is called, any extra arguments go to the `args` **Tuple**.  
  The extra keyword-arguments go to the `kwargs` **Dictionary**.


- Command Explanation:

```Python
def <function>(<args>, *args):
    <instructions>
```
```Python
def <function>(<args>, **kwargs):
    <instructions>
```
```Python
def <function>(<args>, *args, **kwargs):
    <instructions>
```
<!-- --><br/>
<!-- --><br/>


#### Lambda


- Lambda functions are "anonymous" functions (don't need to have a variable name) and that can be defined in a single line.

- Usually useful to be passed a single time as argument to another function.


- Defining a lambda function:

```Python
lambda <args>, ..., <args> : <instruction>
```
<!-- --><br/>


- A lambda can however be attributed to a label.
  In this case it will behave as a normally defined function.

```Python
<lambda> = lambda <args>, ..., <args> : <instruction>
```
<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### UNPACKING (aka STARRED EXPRESSIONS)


- Unpacking can be done with Lists, Tuples and Dictionaries.

- Unpacking is useful to use the items of an iterable as arguments for a function call requiring separated positional arguments.

- For Lists and Tuples it is used the `*` operator **before** the variable.

- For Dictionaries it is used the `**` operator  **before** the variable.


> **Examples**
>
> ```Python
> args = [5, 27, 2]
> print(list(range(*args)))
> ```
> 
> Output:
> ```
> [5, 7, 9, 11, 13, 15, 17, 19, 21, 23, 25]
> ```
> ---
>
> ```Python
> words = dict(word1="the", word2="bird", word3="is")
> print( "{word1} {word2} {word3} {word4} ...".format(**words, word4="the") )
> 
> ```
> 
> Output:
> ```
> the bird is the ...
> ```
> ---

<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### SCOPE & NAMESPACES

- Scope defines where on the code each Namespace can be accessed.

- Namespace is the place where variables are stored.

- Python looks for variables on the Namespace according to its scope, in the following order, from inwards to outwards scope:

    1. Locals - Variables inside a function.

    2. Enclosing Function locals - Variables on the local scope of the Enclosing function of a Nested function.  
       Accessed or declared from within a Nested function with `nonlocal`.

    3. Global - Variables in the top level of a file.  
       Accessed or declared from within a function with `global`.

    4. Built-in - Python pre-assigned variables.

<!-- --><br/>

- Return a Dictionary of global or local variables:

```Python
locals()
```
```Python
globals()
```
<!-- --><br/>
<!-- --><br/>


> **Examples**
>
> ```Python
> # Locals and Globals:
> 
> x = 'global variable'
> 
> def func():
>     x = 'local variable'
>     print("Print within function: ", x)
> 
> print("Print outside function: ", x)
> func()
> ```
> 
> Output:
> ```
> Print outside function:  global variable
> Print within function:  local variable
> ```
> ---
>
> ```Python
> # Locals and Enclosing function locals:
> 
> def outerFunc():
>     x = 'local variable from outer function'
> 
>     def innerFunc1():
>         x = 'nested local variable from inner function 1'
>         print ("Print within inner function 1: ", x)
> 
>     def innerFunc2():
>         nonlocal x
>         print ("Print within inner function 2: ", x)
> 
>     innerFunc1()
>     innerFunc2()
> 
> outerFunc()
> ```
> 
> Output:
> ```
> Print within inner function 1:  nested local variable from inner function 1
> Print within inner function 2:  local variable from outer function
> ```
> ---
>
> ```Python
> # Locals, Enclosing function locals and Globals:
> 
> x = 'global variable'
> 
> def func1():
>     x = 'local variable'
>     def nested1():
>         x = 'enclosed local variable'
>         print("Print within nested function 1: ", x)
>         # Here, the first place 'nested1' looks for variables is within it's locals.
>     nested1()
> 
> def func2():
>     x = 'local variable'
>     def nested2():
>         print("Print within nested function 2: ", x)
>         # Here, 'nested2' won't find local variables so it looks for the enclosing function locals.
>         # The nested function here can access the variable but can't modify it.
>     nested2()
> 
> def func3():
>     def nested3():
>         print("Print within nested function 3: ", x)
>         # Here, 'nested3' will only find the variable in the global scope.
>         # Again, it can access the variable but can't modify it.
>     nested3()
> 
> def func4():
>     x = 'local variable'
>     def nested4():
>         nonlocal x
>         x = 'defined enclosed, but altering the enclosing local variable'
>         # Here, the enclosing function local variable is modified by the nested function.
>     nested4()
>     print("Print within function 4:        ", x)
> 
> def func5():
>     def nested5():
>         global x
>         x = 'defined enclosed, but altering global variable'
>         print("Print within nested function 5: ", x)
>         # Here, the global variable is modified.
>     nested5()
> 
> 
> 
> print("\nPrint outside functions:        ", x)
> func1()
> print("\nPrint outside functions:        ", x)
> func2()
> print("\nPrint outside functions:        ", x)
> func3()
> print("\nPrint outside functions:        ", x)
> func4()
> print("\nPrint outside functions:        ", x)
> func5()
> print("\nPrint outside functions:        ", x)
> ```
> 
> Output:
> ```
> Print outside functions:         global variable
> Print within nested function 1:  enclosed local variable
> 
> Print outside functions:         global variable
> Print within nested function 2:  local variable
> 
> Print outside functions:         global variable
> Print within nested function 3:  global variable
> 
> Print outside functions:         global variable
> Print within function 4:         defined enclosed, but altering the enclosing local variable
> 
> Print outside functions:         global variable
> Print within nested function 5:  defined enclosed, but altering global variable
> 
> Print outside functions:         defined enclosed, but altering global variable
> ```
> ---

<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### OBJECT ORIENTED: CLASSES & OBJECTS


#### Class basics

- Classes have a _Initialization Function_ (`__init__`), aka _Constructors_.  
  It is used to assign values to attributes and do operations necessary when the object is being created.

- The `self` parameter is reference to the current instance of the class.  
  It is used to access attributes of the class.  
  **It has to be the first parameter of any _method_ (function in the class).**

<!-- --><br/>


- Create a Class:

```Python
class <Class>:
    
    <attributes> = <value>
    
    def __init__(self, <parameters>, ...):
        self.<attributes> = <parameter>
        <instructions>
    
    def <methods>(self, <parameters>, ...):
        <instructions>
```
<!-- --><br/>


- Instantiate (create an Object/Instance from) a Class:

```Python
<object> = <Class>()
```
```Python
<object> = <Class>(<parameters>, ...)
```
<!-- --><br/>


- Call a method or parameter from a Object:

```Python
<object>.<method> (<args>, ...)
```
```Python
<object>.<attributes>
```
<!-- --><br/>


- Delete attributes on objects:

```Python
del <object>.<attribute>
```
<!-- --><br/>


- Delete a Instance:

```Python
del <object>
```
<!-- --><br/>
<!-- --><br/>


#### Inheritance

- Classes can inherit attributes and methods from other class.

- A child Class can overwrite the methods inherited from it's parent Class.  
  After that, it is still possible to access the original parent´s methods only from within the Class .

<!-- --><br/>


- Create a Class that inherit the properties from other Class:

```Python
class <Class> (<parent-Class>):
    
    <attributes>

    <__init__>

    <methods>
    
    # Overwriting a parent method:
    
    def <parent-method>(self, <parameters>, ...):
        <new-instructions>
    
    def <method>(self):
        
        # Using the new method:
        <parent-method>()
        
        # Using the overwritten parent method:
        <parent-Class>.<parent-method>()
```
<!-- --><br/>
<!-- --><br/>


#### Special methods


- Constructor:  behavior of `<object> = <Class>()`:

```Python
class <Class>:

    def __init__(self, <parameters>, ...):
        self.<property> = <parameter>
```
<!-- --><br/>


- Behavior when using `<object> + <other-object>`:

```Python
class <Class>:

    def __add__(self, <other-object>):
        <instructions>
        return <object>
```
<!-- --><br/>


- Return of the function `len()` when using `len(<object>)`:

```Python
class <Class>:

    def __len__(self):
        <instructions>
        return <object>
```
<!-- --><br/>


- Behavior of `<object>[<key>]`:

```Python
class <Class>:

    def __getitem__(self, key):
        <instructions>
        return <object>
```
<!-- --><br/>


- Return of `str(<object>)` or `print(<object>)`:

```Python
class <Class>:

    def __str__(self):
        <instructions>
        return <string>
```
<!-- --><br/>


- Behavior when object deleted by `del(<object>)`:

```Python
class <Class>:

    def __del__(self):
        <instructions>
```
<!-- --><br/>


- More info on special methods:

  - [Special Methods](https://www.pythonlikeyoumeanit.com/Module4_OOP/Special_Methods.html)

  - [Special Method Names](https://diveintopython3.net/special-method-names.html)

<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### ERRORS: TRY & EXCEPT


- Try code with possible errors.

- In case a _specific_ Exception is thrown, treats as specified on the `except` block.
  If the Exception is not specified, any error will be treated.

```Python
try:
    <instructions>
    
except <exception>:
    <instructions>
    
except ...
    ...

except:
    <instructions>
```
<!-- --><br/>


- If none of the Exceptions occur, the `except` block is executed:

```Python
try:
    <instructions>

except:
    <instructions>
    
else:
    <instructions>
```
<!-- --><br/>


- The `finally` block runs independent of  what happens.
  Useful in case of:
  - A return on the except block;
  - If an Exception is thrown in the except block,
  - If an Exception is thrown on the try block, but is not treated on any except block, in which case finally is executed before the Exception is propagated.

```Python
try:
    <instructions>

except:
    <instructions>
    
finally:
    <instructions>
```

<!-- --><br/>


- Throw an Exception:

```Python
raise <exception>
```
```Python
raise NameError(<string>)
```
<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### PACKAGES, MODULES & IMPORTING


#### Some info

- When importing a module or package, Python will search for it in this order:
  - built-in modules,
  - files on directories given by the variable `sys.path` (usually the directory containing the input script or the current directory, since Python programs can modify `sys.path`),
  - standard library path.

<!-- --><br/>


- The variable `sys.path` is a list of strings that determines the interpreter’s search path for modules and can be modified using standard list operations:

```Python
import sys
sys.path.append('<path>')
```
<!-- --><br/>


- Some standard and built-in libraries of Python:
  - `sys`
  - `os`
  - `time`
  - `pickle`
  - `numpy`
  - `math`
  - `random`
  - `line_profiler`
  - ...

- More info:
  - [Glossary][glossary]
  - [The import system][import]
  - [Modules][modules]

<!-- --><br/>
<!-- --><br/>


#### Modules


- Modules are Objects that can be loaded from a file into Python using `import`.  
  Modules have a Namespace containing any Objects defined on its file. The file name is the module name with the suffix .py appended.


- Import a Module:

```Python
import <module>
```
```Python
import <module> as <name>
```
<!-- --><br/>


- Unload a imported module:

```Python
del <module>
```
<!-- --><br/>


- Import Objects from a Module directly into the global scope:

```Python
from <module> import <object>
```
```Python
from <module> import <object> as <name>
```
<!-- --><br/>


- Import all names that a Module defines (except those beginning with an underscore `_`):

```Python
from <module> import *
```

> **Note :**
> 
> In general the practice of importing * from a module or package is frowned upon, since it often causes poorly readable code.
> 
> However, it is okay to use it to save typing in interactive sessions.
> 
> ---
> 

<!-- --><br/>


- Whenever the Python interpreter reads a source file, it sets a few built-in variables and executes all of the code found in the file.  
  When a file in run directly its `__name__` variable will have value `"__main__"`.  
  When a file in imported by other file (as a module) its `__name__` variable will receive the name of the file (without extension).  
  To avoid running some parts of a code within a file that is being imported, it can check its `__name__` variable with:

```Python
if __name__ == "__main__":
    <instructions>
```
<!-- --><br/>


- Get a list with the names a module (or object) defines.  
  If an object is not passed returns the list of names in the current local scope.

```Python
dir(<module>)
```
```Python
dir(<object>)
```
```Python
dir()
```
<!-- --><br/>


- List the names of built-in functions and variables:

```Python
import builtins
dir(builtins) 
```
<!-- --><br/>


- Find the path where a module is:

```Python
<module>.__file__
```
```Python
import imp
imp.find_module('<module>')
```
<!-- --><br/>
<!-- --><br/>


#### Packages

- Packages (aka. Libraries) are Modules which can contain submodules or recursively, subpackages.
  - A directory with a file named `__init__.py` is seen as a _Regular Package_ (as they existed in Python =< 3.2), and the files within are seen by Python as Modules.
  - When the package is imported, the `__init__.py` file initializes the package and is implicitly executed. The objects it defines are bound to names in the package’s namespace.
  - In the simplest case, `__init__.py` can just be an empty file, but it can also execute initialization code for the package.
  - If it doesn't has `__init__.py`, it is treated as a _namespace package_.

<!-- --><br/>


> **Examples**
> 
> In a project directory with the following hierarchical structure, a script could import a created module's or package's objects.
> 
> ```
> project/
> |
> |   script.py
> |   module.py
> |   ...
> |   
> |   package/
> |   |
> |   |   __init__.py
> |   |   module.py
> |   |   ...
> |   | 
> |   |   sub_package/
> |   |   |
> |   |   |   __init__.py
> |   |   |   module.py
> |   |   |   ...
> |   |   |
> |   |
> |
> ```
> 
> In this example, any of these syntaxes (from within the script) would be valid for importing modules and/or objects:
> 
> ```Python
> import module
> ```
> ```Python
> import module as <name>
> ```
> ```Python
> from module import *
> ```
> ```Python
> from module import <object>
> ```
> ```Python
> import package
> ```
> ```Python
> from package import module
> # Or equivalently (but must be referenced with its full name):
> import package.module
> ```
> ```Python
> from package import module as <name>
> # Or equivalently:
> import package.module as <name>
> ```
> ```Python
> from package.module import <object>
> ```
> ```Python
> from package.sub_package import module
> # Or equivalently (but must be referenced with its full name):
> import package.sub_package.module
> ```
> ```Python
> from package.sub_package import module as <name>
> # Or equivalently:
> import package.sub_package.module as <name>
> ```
> ```Python
> from package.sub_package.module import <object>
> ```
> ---

<!-- --><br/>


- Command Explanation:

```Python
command
```
<!-- --><br/>


- Command Explanation:

```
project/
|
|   scrip.py
|   module.py
|   ...
|   
|   package/
|   |
|   |   __init__.py
|   |   module.py
|   |   ...
|   | 
|   |   sub_package/
|   |   |
|   |   |   __init__.py
|   |   |   module.py
|   |   |   ...
|   |   |
|   |
|
```
<!-- --><br/>


> **Note :**
> 
> For Intra-package References see [this topic](https://docs.python.org/3/tutorial/modules.html#intra-package-references).
> 
> ---
> 

<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### BUILT-IN FUNCTIONS FOR ITERABLES


#### Map


- Apply a given function to all elements of an iterable.  
  Only function name given as argument (no parenthesis, i.e. function call) or define a lambda directly on the argument.

- Returns a memory instruction (_map type_ object).

```Python
map(<function>, <iterable>)
```
```Python
map(<lambda>, <iterable>)
```
<!-- --><br/>


- Get a list from a map:

```Python
list(<map>)
```
<!-- --><br/>


> **Examples**
>
> ```Python
> celsius = [0, 9, 10, 15, 20, 22, 30, 40, 50, 90, 100, 120]
> fahrenheit = list(map(lambda temp: temp * (9/5) + 32, celsius))
> print(fahrenheit)
> ```
> 
> Output:
> ```
> [32.0, 48.2, 50.0, 59.0, 68.0, 71.6, 86.0, 104.0, 122.0, 194.0, 212.0, 248.0]
> ```
> ---

<!-- --><br/>
<!-- --><br/>


#### Zip


- Takes any number of iterables as argument.  
  Each item with the same index from all given iterables are paired together in a tuple.  
  If the iterables have different lengths, the zip will go until the size of the smaller one.

- Returns a memory instruction (zip type object) made of the formed tuples.

```Python
zip(<iterable>, ..., <iterable>)
```
<!-- --><br/>


> **Examples**
>
> ```Python
> upCase = ['A', 'B', 'C']
> loCase = ['a', 'b', 'c']
> nums = (1, 2, 3, 4, 5)
> list(zip(uCase, lCase, nums))
> ```
> 
> Output:
> ```
> [('A', 'a', 1), ('B', 'b', 2), ('C', 'c', 3)]
> ```
> ---

<!-- --><br/>


- Reverse a Zip:

```Python
zip( * <zip>)
```
<!-- --><br/>
<!-- --><br/>


#### Filter


- Uses a **filter function with boolean return** to exclude or include items in an iterable object.

- Returns a memory instruction (filter type object).

```Python
filter(<function>, <iterable>)
```
<!-- --><br/>


> **Examples**
>
> ```Python
> ages = [5, 12, 17, 18, 24, 32]
> underage = list(filter( (lambda ag: False if x>18 else True) , ages))
> print(underage)
> ```
> 
> Output:
> ```
> [5, 12, 17]
> ```
> ---

<!-- --><br/>
<!-- --><br/>


#### Reduce


- Apply a function sequentially to all elements of an iterable, two by two:  
  Initially with the first two elements, then with this result and the next from the iterable, and so on.

- Goes until the iterable is reduced to a single element which is returned.

```Python
from functools import reduce          # (for Python 3)
reduce(<function>, <iterable>)
```
<!-- --><br/>


> **Examples**
>
> ```Python
> from functools import reduce
> values = [47, 11, 42, 13]
> biggest = reduce( (lambda a,b: a if a>b else b) , values )
> print(biggest)
> ```
> 
> Output:
> ```
> 47
> ```
> ---

<!-- --><br/>


- If the iterable has only one element, it is returned without go through the function.  
  If the iterable has no elements, a initializer needs to be defined:

```Python
reduce(<function>, <iterable>, <initializer>)
```
<!-- --><br/>
<!-- --><br/>


#### Enumerate


- Takes an iterable and adds counters, as keys for each item, in a tuple together with the item.  
  By default stars the counter from 0.

- Returns a memory instruction (enumerate type object).

```Python
enumerate(<iterable>)
```
```Python
enumerate(<iterable>, <start>)
```
<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### DECORATORS & CLOSURE


#### Decorator


- Decorator is a Function that adds other functionalities (_decorate_) to a existing or new function:

<!-- --><br/>


- Define a Decorator for functions with return:

```Python
def <decorator> (<function>):

    def <new-function>( <parameters> ):
        <instructions>
        return <function>( <args> )
    
    return <new-function>
```
<!-- --><br/>


- Define a Decorator for functions without return:

```Python
def <decorator> (<function>):

    def <new-function>( <parameters> ):
        <instructions>
        <function>( <args> )
        <instructions>
    
    return <new-function>
```
<!-- --><br/>


- Decorate existing functions:

```Python
<new-function> = <decorator> (<function>)
```
<!-- --><br/>


- Decorate new functions:

```Python
@<decorator>
def <function> ():
    <instructions>
```
<!-- --><br/>


> **Examples**
>
> ```Python
> def addExplaning(func):
>     
>     def outFunc(x):
>         print("I'm a function that multiplies 5 by the given number %d:" %(x))
>         return func(x)
>     
>     return outFunc
> 
> @addExplaning
> def times5(x):
>     return x*5
> 
> times5(9)
> ```
> 
> Output:
> ```
> I'm a function that multiplies 5 by the given number 9:
> 45
> ```
> ---

<!-- --><br/>


- Multiple decorators can be chained:

```Python
<new-function> = <decorator> ( <decorator> ( ... (<function>) ) )
```
```Python
@<decorator>
...
@<decorator>
def <function> ():
    <instructions>
```
<!-- --><br/>


- Make a general decorators that work with any number of parameters:
  - `args` will be a tuple of positional arguments
  - `kwargs` will be a dictionary of keyword arguments

```Python
def <decorator> (<function>):

    def <new-function>( <parameters> ):
        <instructions>
        return <function>(*args, **kwargs)
    
    return <new-function>
```
```Python
def <decorator> (<function>):

    def <new-function>( <parameters> ):
        <instructions>
        <function>(*args, **kwargs)
        <instructions>
    
    return <new-function>
```
<!-- --><br/>
<!-- --><br/>


#### Closure


- Get some data attached (_closure_) to a function.  
  By using this, once defined, the function will hold a "hidden" data.

- Can be used to create objects storing data without the need to make a Class.

<!-- --><br/>


- Define a Closure:

```Python
def <closure>( <parameters> ):

    def <new-function>():
        <instructions>
        <instruction> ( <data> )
        <instructions>
    
    return <new-function>
```
<!-- --><br/>


- Attach data to the function:

```Python
<function> = <closure>( <data> )
```
<!-- --><br/>


- For accessing Enclosed Values, all function objects have the `__closure__` attribute with a tuple of cell objects.  
  The cell objects have the attribute `cell_contents` which stores the enclosed value.

```Python
<function>.__closure__
```
```Python
<function>.__closure__[<index>].cell_contents
```
<!-- --><br/>


> **Examples**
>
> ```Python
> def make_multiplier(n):
>     
>     def multiplier(x):
>         return x * n
>     
>     return multiplier
> 
> times3 = make_multiplier(3)
> times5 = make_multiplier(5)
> 
> print(times3(9))
> print(times5(9))
> 
> print(times3.__closure__[0].cell_contents)
> print(times5.__closure__[0].cell_contents)
> ```
> 
> Output:
> ```
> 27
> 45
> 3
> 5
> ```
> ---

<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### ITERATORS & GENERATORS


#### Iterator


- A Python Iterator is an Object that implements the special methods `__iter__()` and `__next__()` (iterator protocol).

- The `next()` and `iter()` functions, when applied to the Iterator, call the `__next__()` and `__iter__()` methods, respectively.

- The `next()` function manually iterates through the items stored by the Iterator.  
  When it reaches the end, raises the `StopIteration` Exception.  
  The Iterator Object can be iterated through all items **only once**.

```Python
next (<iterator>)
```
<!-- --><br/>


- The `iter()` function returns an Iterator from an Object:

```Python
<iterator> = iter(<obj>)
```
```Python
<iterator> = iter(<iterable>)
```

<!-- --><br/>
<!-- --><br/>


#### Generator


- A Function that generates and returns an Iterator is known as "Generator".  
  When called, returns an Iterator object, but does not start execution immediately.  
  Methods '__iter__()' and '__next__()' are implemented automatically.

- Local variables are not destroyed when the function yields (i.e. when `next()` is applied).

- Generators can be used to represent an **infinite** stream of data.

<!-- --><br/>


- Define Generator:

```Python
def <gerenator>():
    <instructions>
    yield <value>
```
<!-- --><br/>


- Generate Iterator:

```Python
<iterator> = <gerenator>()
```
<!-- --><br/>


> **Examples**
>
> ```Python
> def PowTwo(max=0):
>     n = 0
>     
>     while n < max:
>         yield 2 ** n
>         n += 1
> 
> for i in PowTwo(11):
>     print(i, end=' ')
> ```
> 
> Output:
> ```
> 1 2 4 8 16 32 64 128 256 512 1024 
> ```
> ---
>
> ```Python
> # Sum of the squares of the numbers in the Fibonacci Sequence
> def fibonacci_numbers(nums):
>     x, y = 0, 1
>    for _ in range(nums):
>         x, y = y, x+y
>         yield x
> 
> def square(nums):
>     for num in nums:
>         yield num**2
> 
> print(sum(square(fibonacci_numbers(100))))
> ```
> 
> Output:
> ```
> 203023208030065646654504166904697594722575
> ```
> ---

<!-- --><br/>


- Generator Expression.
  Much more memory efficient than an equivalent list comprehension.

```Python
(<element/instruction> for <element> in <iterable>)
```
```Python
(<element/instruction> for <element> in <iterable> if <boolean>)
```
```Python
(<element/instruction> if <boolean> else <element/instruction> for <element> in <iterable>)
```
```Python
(<element/instruction> for <element> in <iterable> ... for <element> in <iterable>)
```
<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### DEBUGGING


- Evaluate a boolean and throw an 'AssertionError' (and possible message) if `False`:

```Python
assert <boolean>
```
```Python
assert <boolean>, <str-message>
```
<!-- --><br/>
<!-- --><br/>


#### Python Debugger


- Can create a interactive debugging "breakpoint" at the function `set_trace()`.  
  On it, while running, the code pauses execution. Then, it is possible to interactively modify variables, check their values, etc.


- Import:

```Python
import pdb
```
<!-- --><br/>


- Create a breakpoint:

```Python
pdb.set_trace()
```
<!-- --><br/>


- Once on the interactive debugging mode, some commands are available:

|  Command  | Description |
| :-------: | ----------- |
|  `h`, `help`  | Print the list of available commands. |
|  `h <command>`, `help <command>`  | Print help about that command. |
|  `c`, `cont`, `continue`  | Continue execution, only stop when a breakpoint is encountered. |
|  `q`, `quit`, `exit`  | Quit from the debugger. The program being executed is aborted. |

<!-- --><br/>


- More info on [Python Debugger](https://docs.python.org/dev/library/pdb.html#debugger-commands).

<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### COLLECTIONS MODULE


#### Counter


- Import:

```Python
from collections import Counter
```
<!-- --><br/>


- Count how many times each element appears in an iterable (returns a type Counter object):

```Python
Counter(<iterable>)
```
<!-- --><br/>


- See a number of elements (default: all) ordered by most common appearances:

```Python
Counter(<iterable>).most_common()
```
```Python
Counter(<iterable>).most_common(<number>)
```
<!-- --><br/>


- Get a List of Tuples, with elements and count values, from a Counter:

```Python
<counter>.items()
```
<!-- --><br/>


- Get a Counter from a List of Tuples, with elements and count values:

```Python
Counter(dict(<tuple-list>))
```
<!-- --><br/>


- Get a List, with count values, from a Counter:

```Python
<counter>.values()
```
<!-- --><br/>
<!-- --><br/>


#### DefaultDict


- Does not return a error when trying to access a non existing key.  
  The defaultdict has a default item given, which might be a type object (int, list, object, functions ...) or a function.  
  When it tries to access an item with a key that doesn't exist it creates the item using the default item.

<!-- --><br/>


- Import:

```Python
from collections import defaultdict
```
<!-- --><br/>


- Create a DefaultDict with a default item:

```Python
<defaultdict> = defaultdict(<type-object/function>)
```
<!-- --><br/>


> **Examples**
>
> ```Python
> d = defaultdict(str)
> d['existent'] = 0
> d['non-existent']
> print(d)
> ```
> 
> Output:
> ```
> defaultdict(<class 'str'>, {'existent': 12, 'non-existent': ''})
> ```
> ---
>
> ```Python
> d = defaultdict(int)
> for letter in 'mississippi':
>     d[letter] += 1
> 
> d.items()
> ```
> 
> Output:
> ```
> dict_items([('m', 1), ('i', 4), ('s', 4), ('p', 2)])
> ```
> ---
>
> ```Python
> s = [('yellow', 1), ('blue', 2), ('yellow', 3), ('blue', 4), ('red', 1)]
> d = defaultdict(list)
> for color, value in s:
>     d[color].append(value)
> 
> d.items()
> ```
> 
> Output:
> ```
> dict_items([('yellow', [1, 3]), ('blue', [2, 4]), ('red', [1])])
> ```
> ---

<!-- --><br/>
<!-- --><br/>


#### NamedTuple


- Named Tuples are basically easy-to-create lightweight object types.

<!-- --><br/>


- Import:

```Python
from collections import namedtuple
```
<!-- --><br/>


- Create a Named Tuple "Class" with a name and parameters (separated by spaces on a string):

```Python
<namedtuple> = namedtuple('<name>', '<parameter> ... <parameter>')
```
<!-- --><br/>


- Instantiate a Named Tuple:

```Python
<object> = <namedtuple>(<value>, ... ,<value>)
```
```Python
<object> = <namedtuple>(<parameter> = <value>, ... ,<parameter> = <value>)
```
<!-- --><br/>
<!-- --><br/>


> **Examples**
>
> ```Python
> from collections import namedtuple
> Point = namedtuple('Point', 'x y')
> pt1 = Point(1.0, 5.0)
> pt2 = Point(2.5, 1.5)
> 
> from math import sqrt
> sqrt((pt1.x - pt2.x)**2 + (pt1.y - pt2.y)**2)
> ```
> 
> Output:
> ```
> 3.8078865529319543
> ```
> ---

<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### DATETIME MODULE


- Import:

```Python
import datetime
```
<!-- --><br/>


- Create a Time Stamp with time info:

```Python
<time-stamp> = datetime.time(<hour>)
```
```Python
<time-stamp> = datetime.time(<hour>,<minute>,<second>,<microseconds>)
```
<!-- --><br/>


- Access parameters of Time Stamp with time info:

```Python
<time-stamp>.hour
```
```Python
<time-stamp>.minute
```
```Python
<time-stamp>.second
```
```Python
<time-stamp>.microsecond
```
```Python
<time-stamp>.tzinfo      # timezone
```
<!-- --><br/>


- Create a Time Stamp with date info:

```Python
<time-stamp> = datetime.date(<year>,<month>,<day>)
```
```Python
<time-stamp> = datetime.date.today()
```
<!-- --><br/>


- Access parameters of Time Stamp with date info:

```Python
<time-stamp>.year
```
```Python
<time-stamp>.month
```
```Python
<time-stamp>.day
```
<!-- --><br/>


- Create a Time Stamp with both time and date info:

```Python
<time-stamp> = datetime.datetime(<year>,<month>,<day>,<hour>,<minute>,<second>,<microseconds>)
```
```Python
<time-stamp> = datetime.datetime.today()
```
```Python
<time-stamp> = datetime.datetime.now()
```
<!-- --><br/>


- Parameters info:

```Python
datetime.datetime.min
```
```Python
datetime.datetime.max
```
```Python
datetime.datetime.resolution
```
<!-- --><br/>


- Convert a Time Stamp with both time and date info to Time Stamp with only one or other:

```Python
<time-stamp>.time()
```
```Python
<time-stamp>.date()
```
<!-- --><br/>


- Convert a Time Stamp to a string in readable format:

```Python
<time-stamp>.ctime()
```
```Python
str(<time-stamp>)
```
<!-- --><br/>

> **Examples**
>
> ```Python
> print(datetime.datetime.now())
> print(datetime.datetime.now().ctime())
> ```
> 
> Output:
> ```
> 2021-07-08 21:03:17.986499
> Thu Jul  8 21:03:17 2021
> ```
> ---

<!-- --><br/>
<!-- --><br/>



#### Parsing & Formatting


- Formats are given as Strings including some of the possible elements:
  - `%y`  -   Year without century as a decimal number [01,99].
  - `%Y`  -   Year with century as a decimal number [0001,9999].
  - `%m`  -   Month as a decimal number [01,12].
  - `%d`  -   Day as a decimal number [01,31].
  - `%H`  -   Hour (24-hour clock) as a decimal number [00,23].
  - `%I`  -   Hour (12-hour clock) as a decimal number [01,12].
  - `%M`  -   Minute as a decimal number [00,59].

<!-- --><br/>


- Convert String to DateTime Objects (Parsing):

```Python
<time-stamp> = datetime.strptime(<string>, <format>)
```
<!-- --><br/>


- Convert DateTime Objects to String (Formatting):

```Python
<time-stamp>.strftime(<format>)
```
<!-- --><br/>


- More info on [Formatting](https://docs.python.org/dev/library/time.html#time.strftime).

<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### EXECUTION TIME


#### TimeIt Module


- Import:

```Python
import timeit
```
<!-- --><br/>


- Measure the execution time of a single-line code, for a number of executions (default: number=1000000).  
  Returns a float for the total sum of time with unit in seconds.

```Python
timeit.timeit('<instruction>')
```
```Python
timeit.timeit('<instruction>', number=<number-executions>)
```
<!-- --><br/>


> **Examples**
>
> ```Python
> code_string = "'-'.join([str(n) for n in range (10)])"
> t = timeit.timeit(code_string)
> print("Join using List Comprehension:", eval(code_string), "Time (sec):", t, sep='\n')
> ```
> 
> Output:
> ```
> Join using List Comprehension:
> 0-1-2-3-4-5-6-7-8-9
> Time (sec):
> 3.214837338000052
> ```
> ---
>
> ```Python
> code_string = "'-'.join(str(n) for n in range (10))"
> t = timeit.timeit(code_string)
> print("Join using Generator Expression:", eval(code_string), "Time (sec):", t, sep='\n')
> ```
> 
> Output:
> ```
> Join using Generator Expression:
> 0-1-2-3-4-5-6-7-8-9
> Time (sec):
> 3.868655133000175
> ```
> ---
>
> ```Python
> code_string = "'-'.join(map(str, range (10)))"
> t = timeit.timeit(code_string)
> print("Join using Map function:", eval(code_string), "Time (sec):", t, sep='\n')
> ```
> 
> Output:
> ```
> Join using Map function:
> 0-1-2-3-4-5-6-7-8-9
> Time (sec):
> 2.859254074999626
> ```
> ---

<!-- --><br/>


- On Jupyter notebook (and IPython), it is possible to use TimeIt to get statistics about the execution:

```Python
%timeit <instruction>
```
<!-- --><br/>


> **Examples**
>
> ```Python
> print("Statistics for join using List Comprehension:")
> %timeit '-'.join([str(n) for n in range (10)])
> ```
> 
> Output:
> ```
> Statistics for join using List Comprehension:
> 2.96 µs ± 40.5 ns per loop (mean ± std. dev. of 7 runs, 100000 loops each)
> ```
> ---
>
> ```Python
> print("Statistics for join using Generator Expression:")
> %timeit '-'.join(str(n) for n in range (10))
> ```
> 
> Output:
> ```
> Statistics for join using Generator Expression:
> 3.42 µs ± 106 ns per loop (mean ± std. dev. of 7 runs, 100000 loops each)
> ```
> ---
>
> ```Python
> print("Statistics for join using Map function:")
> %timeit '-'.join(map(str, range (10)))
> ```
> 
> Output:
> ```
> Statistics for join using Map function:
> 2.57 µs ± 51.1 ns per loop (mean ± std. dev. of 7 runs, 100000 loops each)
> ```
> ---

<!-- --><br/>
<!-- --><br/>


#### Line Profiler package


- Analyse a code and show which part or line is wasting more time.

- [Article about Python Profiling](https://zapier.com/engineering/profiling-python-boss/).

<!-- --><br/>

- Set up:

```Python
try:
    from line_profiler import LineProfiler

    def do_profile(follow=[]):
        def inner(func):
            def profiled_func(*args, **kwargs):
                try:
                    profiler = LineProfiler()
                    profiler.add_function(func)
                    for f in follow:
                        profiler.add_function(f)
                    profiler.enable_by_count()
                    return func(*args, **kwargs)
                finally:
                    profiler.print_stats()
            return profiled_func
        return inner

except ImportError:
    def do_profile(follow=[]):
        "Helpful if you accidentally leave in production!"
        def inner(func):
            def nothing(*args, **kwargs):
                return func(*args, **kwargs)
            return nothing
        return inner
```
<!-- --><br/>


- Usage:
  - Create a test function containing the problem function(s) (of interest).
  - Decorate the test function and pass the problem function(s) in a List to the `follow` parameter.
  - Run the test function.

```Python
def <problem_function>():
    <instructions>
...
def <problem_function>():
    <instructions>

@do_profile(follow=[<problem_function>, ..., <problem_function>])
def <test_function>():
    <instructions>
    <problem_function>()
    ...
    <problem_function>()
    <instructions>

<test_function>()
```
<!-- --><br/>


> **Examples**
>
> ```Python
> def get_number():
>     for x in range(5000000):
>         yield x
> 
> @do_profile(follow=[get_number])
> def expensive_function():
>     for x in get_number():
>         i = x ^ x ^ x
>     return 'some result!'
> 
> result = expensive_function()
> ```
> 
> Output:
> ```
> Timer unit: 1e-06 s
> 
> Total time: 3.70629 s
> File: <ipython-input-7-ecb175f9e1b7>
> Function: get_number at line 1
> 
> Line #      Hits         Time  Per Hit   % Time  Line Contents
> ==============================================================
>      1                                           def get_number):
>      2   5000001    1938981.0      0.4     52.3      for x in range(5000000):
>      3   5000000    1767308.0      0.4     47.7          yield x
> 
> Total time: 14.9942 s
> File: <ipython-input-7-ecb175f9e1b7>
> Function: expensive_function at line 5
> 
> Line #      Hits         Time  Per Hit   % Time  Line Contents
> ==============================================================
>      5                                           @do_profile(follow=[get_number])
>      6                                           def expensive_function():
>      7   5000001   11861348.0      2.4     79.1      for x in get_number():
>      8   5000000    3132886.0      0.6     20.9          i = x ^ x ^ x
>      9         1          0.0      0.0      0.0      return 'some result!'
> 
> ```
> ---

<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### REGULAR EXPRESSIONS (RE) MODULE


#### RE basics


- Find text patterns, using Unicode characters.

- [Documentation: Regular Expression][re]

<!-- --><br/>


- Import:

```Python
import re
```
<!-- --><br/>


- Find a pattern (passed as a string) on a string.
  - Returns a Match Object. The 'span' is a tuple with initial and final position for the match found.
  - Returns nothing if pattern not found.

```Python
re.search(<pattern>, <string>)
```
```Python
re.search(r <pattern>, <string>)
```
<!-- --><br/>


- Split strings on patters:

```Python
re.split(<pattern>, <string>)
```
<!-- --><br/>


- Find all matches and Return it:

```Python
re.findall(<pattern>, <string>)
```
<!-- --><br/>


- Match Object methods:

```Python
<match>.start()
```
```Python
<match>.end()
```
<!-- --><br/>
<!-- --><br/>


> **Examples**
>
> ```Python
> import re
> patterns = ['term1', 'term2'] 
> text = 'String with term1 and term1 again.' 
>  
> for patt in patterns: 
>     match = re.search(patt, text) 
>     if match: 
>         print('Found "{}" in "{}":\n {}\n'.format(patt, text, match)) 
>     else: 
>         print('Did not found "{}" in "{}".\n'.format(patt, text))
> ```
> 
> Output:
> ```
> Found "term1" in "String with term1 and term1 again.":
>  <re.Match object; span=(12, 17), match='term1'>
> 
> Did not found "term2" in "String with term1 and term1 again.".
> 
> ```
> ---

<!-- --><br/>
<!-- --><br/>


#### Pattern Repetition Syntax


A pattern might have alphanumeric character or special characters used for repetitions.


- `\`  
  Escapes special characters.

- `*`  
  Match 0 or more repetitions of the preceding RE.

- `+`  
  Match 1 or more repetitions of the preceding RE.

- `?`  
  Match 0 or 1 repetitions of the preceding RE.

- `{m}`  
  Exactly 'm' copies of the previous RE should be matched.

- `{m,n}`  
  Match from 'm' to 'n' repetitions of the preceding RE.
    - Omitting 'm' specifies the lower bound to zero.
    - Omitting 'n' specifies the upper bound as infinite .

- `A|B`  
  Match either 'A' or 'B'.

- `[]`  
  Indicate a set of possible characters (inside the `[]`).
    - `[-]`  
      Range of possible characters.  
      Examples:  
        - `[a-z]` : From a to z.  
        - `[0-9A-Fa-f]` : Any hexadecimal digit.  
        - `[0-5][0-9]` : All two-digits numbers from 00 to 59.  
    - `[^]`  
      "Except". Complementing the set.  
      The hat accent '^' is not seen as a special character if it’s not the first character in the set.  
      Example:
        - `[^5]` : Any character except '5'.
        - `[^^]` : Any character except '^'.

<!-- --><br/>


> **Examples**
>
> ```Python
> # find any sequence of charactes enclosed by `$`:
> 
> line = """aaa$bb$ccc$ddd$eee
> fff$ggg$hh$iii$jj"""
> 
> import re
> m = re.findall(r"\$[^$]+\$", line)
> 
> # Breakdown of the RE "\$[^$]+\$" :
> #
> # `\$`     - Escaped `$`
> # `[^$]`   - Any character except `$`
> # `[^$]+`  - Match 1 or more of `[^$]`
> 
> print(*m, sep='\n')
> ```
> 
> Output:
> ```
> $bb$
> $ddd$
> $ggg$
> $iii$
> 
> ```
> ---

<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------




------------------------------------



------------------------------------




------------------------------------



------------------------------------



------------------------------------



------------------------------------



------------------------------------



------------------------------------



------------------------------------



------------------------------------



