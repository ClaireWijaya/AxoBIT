**Chapter 3 — Python Foundations**

**3.1 Introduction to Python**

**3.1.1 What Is Python?**

Python is a general-purpose programming language known for its readable
syntax. It allows programmers to give instructions to computers using
statements written in a structured, human-readable form.

Python is commonly used in:

- **Artificial intelligence (AI):** Developing systems that perform
  tasks associated with intelligence.

- **Data science:** Analyzing and interpreting data.

- **Automation:** Performing repetitive tasks automatically.

- **Web development:** Building websites and web applications.

- **Scientific computing:** Solving mathematical and scientific
  problems.

- **Education:** Learning programming concepts.

Python is useful for beginners because many instructions resemble
ordinary mathematical expressions.

**3.1.2 Your First Python Program**

Consider the following program:

print("Hello, world!")

**Expected output:**

Hello, world!

Explanation:

- print() is a built-in Python function that displays information.

- "Hello, world!" is a string, which is a sequence of characters.

- Parentheses contain the information passed to the function.

- Quotation marks indicate that the enclosed content is text.

A **function** is a reusable block of code that performs a particular
task. Functions are introduced in detail in Section 3.8.

**3.1.3 How Python Executes Instructions**

Python generally executes a script from top to bottom.

print("First")

print("Second")

print("Third")

Expected output:

First

Second

Third

Each statement runs in sequence unless a condition, loop, function call,
or error changes the normal flow.

A Python program is commonly saved in a file ending in .py, such as
hello.py.

<img src="CHAPTER 3-1_media/media/image1.jpeg"
style="width:4.48611in;height:2.98611in"
alt="From Script to Execution: The Inner Workings of Python | by Karan Ji | Medium" />

Figure 3.1. Python Program Execution

**3.1.4 Comments**

Comments explain code to human readers. Python ignores comments when
executing a program.

\# Display a greeting

print("Welcome to Python!")

A comment begins with \# and continues to the end of that line.

Comments should clarify the purpose of code rather than repeat obvious
instructions.

**3.2 Variables and Assignment**

**3.2.1 What Is a Variable?**

A **variable** is a name that refers to a value in a program.

age = 19

name = "Alex"

score = 95.5

Here:

- age refers to the integer 19.

- name refers to the string "Alex".

- score refers to the floating-point number 95.5.

The = symbol is the **assignment operator**. It assigns the value on its
right to the variable named on its left.

**3.2.2 Changing a Variable's Value**

A variable can be assigned a new value.

score = 80

print(score)

score = 95

print(score)

Expected output:

80

95

The second assignment replaces the value previously associated with
score.

**3.2.3 Using Variables in Calculations**

price = 20

quantity = 3

total = price \* quantity

print(total)

Expected output:

60

Python calculates 20 \* 3 and assigns the result to total.

This approach is more flexible than writing print(20 \* 3) because
changing price or quantity automatically changes the calculated result.

**3.2.4 Variable Naming Rules**

Variable names must follow Python's naming rules.

Valid examples:

student_name = "Alex"

age = 19

total_score = 280

number2 = 10

Invalid examples:

\# 2number = 10

\# student-name = "Alex"

\# class = "Python"

These names are invalid because:

- A variable name cannot begin with a digit.

- A hyphen is not allowed in a variable name.

- Reserved Python keywords, such as class, cannot be used as variable
  names.

Python is case-sensitive. Therefore, score, Score, and SCORE are three
different names.

**Best practice:** Use descriptive names and lowercase words separated
by underscores.

student_age = 19

final_score = 92

**3.2.5 Assigning Values to Multiple Variables**

Python allows multiple assignments in one statement.

x, y, z = 10, 20, 30

print(x)

print(y)

print(z)

Expected output:

10

20

30

You can also assign the same value to multiple variables:

a = b = c = 0

All three variables refer to the value 0.

**3.3 Data Types and Type Conversion**

**3.3.1 What Is a Data Type?**

A **data type** describes the kind of value a program works with.
Different types support different operations.

Python automatically determines the type of a value when it is assigned.

The four fundamental types introduced in this section are integers,
floating-point numbers, strings, and Booleans.

<img src="CHAPTER 3-1_media/media/image2.jpeg"
style="width:3.45139in;height:1.99306in"
alt="6.4 The Python Memory Model: Introduction" />

Figure 3.2. Variables and Fundamental Data Types

**3.3.2 Integers (int)**

An integer is a whole number without a fractional part.

age = 19

temperature = -5

number_of_students = 120

Python identifies these values as integers.

print(type(age))

Expected output:

\<class 'int'\>

**3.3.3 Floating-Point Numbers (float)**

A floating-point number represents a number with a fractional component.

price = 12.50

height = 1.65

temperature = -2.5

Example:

print(type(12.50))

Expected output:

\<class 'float'\>

Floating-point arithmetic can produce small rounding differences. For
example, some decimal fractions cannot be represented exactly in binary
floating-point format.

For ordinary beginner exercises, this is usually not a problem.
Applications requiring precise financial calculations may need decimal
arithmetic instead.

**3.3.4 Strings (str)**

A string represents text.

name = "Alex"

message = 'Welcome!'

university = "Beijing Institute of Technology"

Single and double quotation marks can both define strings.

first_name = "Alex"

last_name = "Tan"

print(first_name + " " + last_name)

Expected output:

Alex Tan

The + operator joins strings together. This operation is called
**concatenation**.

You can also repeat a string:

print("Hi! " \* 3)

Expected output:

Hi! Hi! Hi!

**3.3.5 Booleans (bool)**

A Boolean represents one of two logical values:

- True

- False

Example:

is_student = True

has_finished = False

print(is_student)

print(type(is_student))

Expected output:

True

\<class 'bool'\>

Booleans are particularly useful in conditions and decision-making.

**3.3.6 Checking Data Types**

Use type() to identify a value's type.

a = 10

b = 3.5

c = "Python"

d = True

print(type(a))

print(type(b))

print(type(c))

print(type(d))

Expected output:

\<class 'int'\>

\<class 'float'\>

\<class 'str'\>

\<class 'bool'\>

**3.3.7 Type Conversion**

**Type conversion** changes a value from one data type to another when
the conversion is valid.

Common conversion functions include:

| **Function** | **Purpose**                        | **Example**  | **Result** |
|--------------|------------------------------------|--------------|------------|
| int()        | Convert to an integer              | int("25")    | 25         |
| float()      | Convert to a floating-point number | float("3.5") | 3.5        |
| str()        | Convert to a string                | str(25)      | "25"       |
| bool()       | Convert to a Boolean               | bool(1)      | True       |

Examples:

number = int("25")

price = float("12.5")

message = str(100)

print(number + 5)

print(price + 2)

print(message)

Expected output:

30

14.5

100

The last output is text, not an integer.

**Important:** Not every conversion succeeds.

\# int("hello")

This expression raises a ValueError because "hello" is not a valid
integer representation.

Converting a floating-point number to an integer also removes its
fractional part rather than rounding to the nearest integer.

print(int(4.9))

Expected output:

4

**3.4 Operators and Expressions**

An **operator** performs an operation on one or more values. An
**expression** combines values, variables, and operators to produce a
result.

**3.4.1 Arithmetic Operators**

Python supports the following arithmetic operators:

| **Operator** | **Meaning**          | **Example** | **Result** |
|--------------|----------------------|-------------|------------|
| \+           | Addition             | 8 + 3       | 11         |
| \-           | Subtraction          | 8 - 3       | 5          |
| \*           | Multiplication       | 8 \* 3      | 24         |
| /            | Division             | 8 / 2       | 4.0        |
| //           | Floor division       | 8 // 3      | 2          |
| %            | Modulo, or remainder | 8 % 3       | 2          |
| \*\*         | Exponentiation       | 2 \*\* 3    | 8          |

Examples:

a = 17

b = 5

print(a + b)

print(a - b)

print(a \* b)

print(a / b)

print(a // b)

print(a % b)

print(a \*\* 2)

Expected output:

22

12

85

3.4

3

2

289

**Understanding floor division and modulo**

For positive integers, 17 // 5 gives 3, while 17 % 5 gives 2.

This means:

\\\[ 17 = 5 \times 3 + 2 \\\]

Floor division gives the quotient rounded down to an integer value, and
modulo gives the remainder.

These operators are useful for tasks such as determining whether a
number is even.

number = 14

print(number % 2 == 0)

Expected output:

True

**3.4.2 Comparison Operators**

Comparison operators compare two values and return a Boolean.

| **Operator** | **Meaning**              | **Example** |
|--------------|--------------------------|-------------|
| ==           | Equal to                 | 5 == 5      |
| !=           | Not equal to             | 5 != 3      |
| \>           | Greater than             | 8 \> 4      |
| \<           | Less than                | 2 \< 7      |
| \>=          | Greater than or equal to | 5 \>= 5     |
| \<=          | Less than or equal to    | 3 \<= 4     |

Example:

age = 19

print(age \>= 18)

print(age == 20)

print(age != 16)

Expected output:

True

False

True

**Important distinction:**

- = assigns a value.

- == checks whether two values are equal.

Confusing these symbols is a common beginner mistake.

**3.4.3 Logical Operators**

Logical operators combine or reverse Boolean conditions.

| **Operator** | **Meaning**                         | **Example**    |
|--------------|-------------------------------------|----------------|
| and          | Both conditions must be true        | True and False |
| or           | At least one condition must be true | True or False  |
| not          | Reverses a Boolean value            | not True       |

Example:

age = 20

has_ticket = True

print(age \>= 18 and has_ticket)

print(age \< 18 or has_ticket)

print(not has_ticket)

Expected output:

True

True

False

The first expression is true because the person meets the age condition
and has a ticket.

The second expression is true because at least one condition is true.

The third expression reverses True to False.

**3.4.4 Operator Precedence**

Operator precedence determines which operations are performed first.

For example:

result = 2 + 3 \* 4

print(result)

Expected output:

14

Multiplication occurs before addition.

Use parentheses to make calculations easier to understand.

result = (2 + 3) \* 4

print(result)

Expected output:

20

**3.5 Input and Output**

Programs often need to receive information from users and display
results.

**3.5.1 Displaying Output with print()**

The print() function displays values.

name = "Alex"

age = 19

print("Name:", name)

print("Age:", age)

Expected output:

Name: Alex

Age: 19

Multiple values separated by commas are displayed with spaces between
them by default.

**3.5.2 Receiving Input with input()**

The input() function pauses the program and waits for the user to enter
text.

name = input("Enter your name: ")

print("Hello,", name)

If the user enters Alex, the output is:

Enter your name: Alex

Hello, Alex

The input function returns a string, even if the user types digits.

**3.5.3 Converting User Input to Numbers**

Consider this program:

age = input("Enter your age: ")

print(age + 1)

If the user enters 19, the program raises a TypeError because age is a
string and 1 is an integer.

Convert the input before performing arithmetic.

age = int(input("Enter your age: "))

print("Next year:", age + 1)

If the user enters 19, the output is:

Enter your age: 19

Next year: 20

For decimal numbers, use float().

price = float(input("Enter the price: "))

print("Price after adding 5:", price + 5)

If the user enters 12.5, the result is:

Enter the price: 12.5

Price after adding 5: 17.5

**3.5.4 Formatting Output with f-Strings**

An **f-string** allows variables and expressions to be inserted directly
into text.

name = "Alex"

score = 92

print(f"{name} received {score} marks.")

Expected output:

Alex received 92 marks.

An f-string begins with f before the opening quotation mark. Expressions
inside curly braces are evaluated.

You can format floating-point values:

price = 12.5678

print(f"Price: {price:.2f}")

Expected output:

Price: 12.57

The .2f format displays two digits after the decimal point.

**3.6 Conditional Statements**

A **conditional statement** allows a program to choose which
instructions to execute based on whether a condition is true or false.

**3.6.1 The if Statement**

The if statement executes its body only when its condition is true.

age = 20

if age \>= 18:

print("Adult")

Expected output:

Adult

The colon : marks the beginning of the block. The indented line belongs
to the if statement.

Python uses indentation to identify code blocks. Four spaces are the
standard convention.

**3.6.2 The if-else Statement**

Use else to provide an alternative when the condition is false.

age = 16

if age \>= 18:

print("Adult")

else:

print("Not an adult")

Expected output:

Not an adult

Exactly one of these two branches executes.

**3.6.3 The if-elif-else Statement**

Use elif, meaning "else if," when several conditions need to be checked.

score = 82

if score \>= 90:

print("Grade A")

elif score \>= 80:

print("Grade B")

elif score \>= 70:

print("Grade C")

else:

print("Grade D")

Expected output:

Grade B

Python checks the conditions from top to bottom and executes the first
branch whose condition is true.

The order matters. For example, placing score \>= 70 before score \>= 90
would prevent a score of 95 from reaching the grade A branch.

**3.6.4 Combining Conditions**

age = 20

score = 85

if age \>= 18 and score \>= 80:

print("Requirements satisfied")

else:

print("Requirements not satisfied")

Expected output:

Requirements satisfied

Both conditions must be true because the program uses and.

**3.6.5 Common Conditional Errors**

Incorrect:

\# if age \>= 18

\# print("Adult")

The colon is missing.

Correct:

age = 20

if age \>= 18:

print("Adult")

Another common mistake is inconsistent indentation.

Incorrectly aligned statements may produce an IndentationError or change
the program's logic.

**3.7 Loops**

A **loop** repeats instructions. Loops are useful when performing the
same operation multiple times.

Python provides two fundamental loop statements: for and while.

**3.7.1 The for Loop**

A for loop iterates over the items in a sequence or another iterable
object.

for number in range(5):

print(number)

Expected output:

0

1

2

3

4

range(5) generates the integers from 0 through 4. The ending value 5 is
excluded.

<img src="CHAPTER 3-1_media/media/image3.jpeg"
style="width:3.98611in;height:2.90278in"
alt="Chapter 3 - Loops, Automate the Boring Stuff with Python, 3rd Ed" />

Figure 3.3. Loop Execution

**3.7.2 Using range()**

The range() function can accept one, two, or three arguments.

| **Form**                 | **Meaning**                           |
|--------------------------|---------------------------------------|
| range(stop)              | Starts at 0 and stops before stop     |
| range(start, stop)       | Starts at start and stops before stop |
| range(start, stop, step) | Advances by step                      |

Example:

for number in range(2, 11, 2):

print(number)

Expected output:

2

4

6

8

10

The loop starts at 2, increases by 2, and stops before 11.

**3.7.3 Calculating a Total with a Loop**

total = 0

for number in range(1, 6):

total = total + number

print(total)

Expected output:

15

The loop adds the numbers from 1 to 5.

| **Iteration** | **Number** | **Total after addition** |
|---------------|------------|--------------------------|
| 1             | 1          | 1                        |
| 2             | 2          | 3                        |
| 3             | 3          | 6                        |
| 4             | 4          | 10                       |
| 5             | 5          | 15                       |

The variable total accumulates the result.

The statement total += number is a shorter equivalent of total = total +
number.

**3.7.4 The while Loop**

A while loop repeats as long as its condition remains true.

count = 1

while count \<= 3:

print(count)

count += 1

Expected output:

1

2

3

The loop works as follows:

1.  Check whether count \<= 3.

2.  Print the current value.

3.  Increase count by one.

4.  Repeat the condition check.

5.  Stop when the condition becomes false.

**3.7.5 Infinite Loops**

An **infinite loop** continues indefinitely because its stopping
condition never becomes false.

For example:

\# count = 1

\#

\# while count \<= 3:

\# print(count)

The counter never changes, so the condition stays true.

The corrected version is:

count = 1

while count \<= 3:

print(count)

count += 1

When testing a program in a terminal, Ctrl+C commonly interrupts a
running loop.

**3.7.6 break and continue**

The break statement terminates the nearest enclosing loop.

for number in range(1, 6):

if number == 4:

break

print(number)

Expected output:

1

2

3

The loop stops when number reaches 4.

The continue statement skips the rest of the current iteration and moves
to the next one.

for number in range(1, 6):

if number == 3:

continue

print(number)

Expected output:

1

2

4

5

**3.7.7 Choosing Between for and while**

| **Situation**                                 | **Recommended loop** |
|-----------------------------------------------|----------------------|
| Repeat a known number of times                | for                  |
| Process each item in a list                   | for                  |
| Repeat while a condition remains true         | while                |
| Continue until a user enters a valid response | Often while          |

Both loops can solve many of the same problems. Choose the one that
makes the intended behavior easiest to understand.

**3.8 Functions, Parameters, and Return Values**

**3.8.1 What Is a Function?**

A **function** is a named, reusable block of code that performs a task.

Functions help programmers organize programs, reduce repetition, and
make code easier to test.

Python includes built-in functions such as print(), input(), and len().
Programmers can also define their own functions using def.

**3.8.2 Defining and Calling a Function**

def greet():

print("Hello!")

greet()

greet()

Expected output:

Hello!

Hello!

Explanation:

- def begins a function definition.

- greet is the function's name.

- () contains the function's parameters, if any.

- : marks the beginning of the function body.

- The indented statement belongs to the function.

- greet() calls the function and executes its body.

Defining a function does not automatically execute its body. The
function must be called.

**3.8.3 Parameters and Arguments**

A **parameter** is a name listed in a function definition. An
**argument** is a value supplied when calling the function.

def greet(name):

print(f"Hello, {name}!")

greet("Alex")

greet("Jordan")

Expected output:

Hello, Alex!

Hello, Jordan!

Here:

- name is the parameter.

- "Alex" and "Jordan" are arguments.

The same function can process different arguments.

**3.8.4 Multiple Parameters**

def add(a, b):

print(a + b)

add(3, 5)

add(10, 7)

Expected output:

8

17

The function accepts two arguments and displays their sum.

**3.8.5 Return Values**

The return statement sends a result back to the code that called the
function.

def add(a, b):

return a + b

result = add(3, 5)

print(result)

Expected output:

8

The expression a + b is evaluated, and its result is returned. The
caller assigns that result to result.

Compare the following functions:

def show_sum(a, b):

print(a + b)

def calculate_sum(a, b):

return a + b

show_sum() displays the result, while calculate_sum() provides a result
that can be stored, compared, or used in another calculation.

**3.8.6 Functions with Conditions**

def is_even(number):

return number % 2 == 0

print(is_even(8))

print(is_even(7))

Expected output:

True

False

The function returns a Boolean indicating whether the number is even.

**3.8.7 Default Parameters**

A parameter can have a default value.

def greet(name="Student"):

print(f"Hello, {name}!")

greet()

greet("Alex")

Expected output:

Hello, Student!

Hello, Alex!

If the caller does not provide an argument for name, the default value
"Student" is used.

**3.8.8 Local Variables**

A variable created inside a function is normally local to that function.

def calculate():

result = 10 + 5

print(result)

calculate()

Expected output:

15

The variable result belongs to the function's local scope. Code outside
the function cannot normally access this local variable directly.

**Best practice:** Use parameters to provide input and return values to
communicate results.

**3.9 Lists and List Operations**

**3.9.1 What Is a List?**

A **list** is an ordered collection that can store multiple items.

scores = \[85, 92, 78, 96\]

names = \["Alex", "Jordan", "Sam"\]

mixed = \[10, "Python", True\]

Lists use square brackets, with items separated by commas.

A list can contain repeated values and can be modified after creation.

**3.9.2 Accessing List Elements**

List indexing starts at 0.

scores = \[85, 92, 78, 96\]

print(scores\[0\])

print(scores\[2\])

print(scores\[-1\])

Expected output:

85

78

96

For this list:

| **Index** | **Value** |
|-----------|-----------|
| 0         | 85        |
| 1         | 92        |
| 2         | 78        |
| 3         | 96        |
| -1        | 96        |

Negative indexing counts from the end. For example, scores\[-1\]
accesses the last element.

An index outside the valid range raises an IndexError.

**3.9.3 Changing List Elements**

scores = \[85, 92, 78\]

scores\[1\] = 95

print(scores)

Expected output:

\[85, 95, 78\]

The assignment changes the second element because its index is 1.

**3.9.4 Adding Elements**

Use append() to add an item to the end of a list.

scores = \[85, 92\]

scores.append(88)

print(scores)

Expected output:

\[85, 92, 88\]

Use insert() to add an item at a particular index.

scores = \[85, 92, 88\]

scores.insert(1, 90)

print(scores)

Expected output:

\[85, 90, 92, 88\]

**3.9.5 Removing Elements**

The remove() method removes the first occurrence of a specified value.

numbers = \[10, 20, 30, 20\]

numbers.remove(20)

print(numbers)

Expected output:

\[10, 30, 20\]

The pop() method removes an element and returns its value.

numbers = \[10, 20, 30\]

removed = numbers.pop()

print(removed)

print(numbers)

Expected output:

30

\[10, 20\]

Without an index, pop() removes the last element.

**3.9.6 List Length and Membership**

Use len() to determine the number of items.

scores = \[85, 92, 78, 96\]

print(len(scores))

Expected output:

4

Use in to check whether an item exists.

scores = \[85, 92, 78, 96\]

print(92 in scores)

print(100 in scores)

Expected output:

True

False

**3.9.7 Looping Through a List**

scores = \[85, 92, 78\]

for score in scores:

print(score)

Expected output:

85

92

78

The loop assigns each element to score in sequence.

**3.9.8 Calculating Statistics**

Python provides useful built-in functions for numerical lists.

scores = \[85, 92, 78, 96\]

print("Total:", sum(scores))

print("Highest:", max(scores))

print("Lowest:", min(scores))

print("Average:", sum(scores) / len(scores))

Expected output:

Total: 351

Highest: 96

Lowest: 78

Average: 87.75

The average is the sum divided by the number of elements.

**Important:** An empty list has length zero. Dividing by len(scores)
without checking whether the list is empty can cause a
ZeroDivisionError.

**3.10 Errors and Debugging**

**3.10.1 What Is an Error?**

An error occurs when a program cannot execute as intended. Python
reports many errors with a message called a **traceback**, which helps
identify where the problem occurred.

Understanding error messages is an important programming skill.

**3.10.2 Syntax Errors**

A **SyntaxError** occurs when code violates Python's grammatical rules.

Incorrect:

\# print("Hello"

The closing parenthesis is missing.

Correct:

print("Hello")

Other common causes include missing colons, unclosed quotation marks,
and incorrectly structured statements.

**3.10.3 Indentation Errors**

An **IndentationError** occurs when indentation is invalid.

Incorrect:

\# if True:

\# print("Hello")

Correct:

if True:

print("Hello")

Python uses indentation to define blocks, so consistent spacing is
essential.

**3.10.4 Name Errors**

A **NameError** occurs when Python encounters a name that has not been
defined in the current scope.

Incorrect:

\# print(total)

If total has not been defined, Python cannot determine its value.

Correct:

total = 100

print(total)

Expected output:

100

**3.10.5 Type Errors**

A **TypeError** occurs when an operation is not supported for the given
types.

Incorrect:

\# age = "19"

\# print(age + 1)

The program tries to add a string to an integer.

Correct:

age = int("19")

print(age + 1)

Expected output:

20

**3.10.6 Value Errors**

A **ValueError** occurs when an operation receives a value of the
appropriate general type but cannot use that value as required.

For example:

\# int("hello")

The input is a string, but it does not represent a valid integer.

A program can handle this situation with try and except.

try:

age = int(input("Enter your age: "))

print("Your age is:", age)

except ValueError:

print("Please enter a valid whole number.")

If the user enters nineteen, the program displays the error message
instead of terminating with an unhandled ValueError.

This example handles invalid integer input. It does not attempt to
enforce any particular age range.

**3.10.7 Index Errors**

An **IndexError** occurs when a sequence is accessed using an invalid
index.

Incorrect:

\# numbers = \[10, 20, 30\]

\# print(numbers\[5\])

The list has only three elements, with valid nonnegative indices 0, 1,
and 2.

Correct:

numbers = \[10, 20, 30\]

print(numbers\[2\])

Expected output:

30

**3.10.8 Division by Zero**

A **ZeroDivisionError** occurs when an integer or floating-point number
is divided by zero.

Incorrect:

\# result = 10 / 0

Correct:

divisor = 0

if divisor != 0:

print(10 / divisor)

else:

print("Division by zero is not allowed.")

Expected output:

Division by zero is not allowed.

**3.10.9 A Systematic Debugging Process**

**Debugging** is the process of identifying, understanding, and
correcting problems in a program.

Follow these steps:

1.  **Read the error message.** Identify the exception type and message.

2.  **Locate the relevant line.** Use the traceback to find where Python
    reported the problem.

3.  **Inspect nearby code.** Check variable names, indentation, types,
    and values.

4.  **Reproduce the problem.** Run the program again with the same
    input.

5.  **Check assumptions.** Determine what values the program actually
    receives.

6.  **Make one correction.** Avoid changing unrelated code.

7.  **Test again.** Confirm that the correction solves the problem
    without creating another one.

**3.10.10 Using print() for Debugging**

Temporary print statements can reveal unexpected values.

price = 12

quantity = 3

print("DEBUG price:", price)

print("DEBUG quantity:", quantity)

total = price \* quantity

print("Total:", total)

Expected output:

DEBUG price: 12

DEBUG quantity: 3

Total: 36

This technique is particularly useful when a calculation produces an
unexpected result.

Remove unnecessary debugging statements when the program is finished.

**3.11 Putting the Concepts Together**

This section combines variables, input, conversion, lists, loops,
functions, conditions, and formatted output into small programs.

**3.11.1 Example 1: Simple Calculator**

The program asks the user for two numbers and displays their sum,
difference, product, and quotient.

first = float(input("Enter the first number: "))

second = float(input("Enter the second number: "))

print(f"Sum: {first + second}")

print(f"Difference: {first - second}")

print(f"Product: {first \* second}")

if second != 0:

print(f"Quotient: {first / second}")

else:

print("Quotient: undefined because division by zero is not allowed.")

Example interaction:

Enter the first number: 12

Enter the second number: 4

Sum: 16.0

Difference: 8.0

Product: 48.0

Quotient: 3.0

**Explanation**

1.  input() receives the two numbers as text.

2.  float() converts them into floating-point values.

3.  Arithmetic operators calculate the results.

4.  The conditional statement checks that the divisor is not zero.

5.  The f-strings display the results.

This program assumes that the user enters valid numerical input. A more
robust version could use exception handling to manage invalid input.

**3.11.2 Example 2: Student Score Analyzer**

The following program stores scores in a list, calculates statistics,
and classifies the average.

def calculate_average(scores):

return sum(scores) / len(scores)

scores = \[85, 92, 78, 96, 89\]

average = calculate_average(scores)

print("Scores:", scores)

print(f"Total: {sum(scores)}")

print(f"Average: {average:.2f}")

print(f"Highest: {max(scores)}")

print(f"Lowest: {min(scores)}")

if average \>= 90:

print("Performance: Excellent")

elif average \>= 80:

print("Performance: Good")

elif average \>= 70:

print("Performance: Satisfactory")

else:

print("Performance: Needs improvement")

Expected output:

Scores: \[85, 92, 78, 96, 89\]

Total: 440

Average: 88.00

Highest: 96

Lowest: 78

Performance: Good

**Explanation**

- The scores list stores five numerical values.

- calculate_average() calculates the average and returns it.

- sum() calculates the total.

- max() and min() find the highest and lowest values.

- :.2f displays the average to two decimal places.

- The conditional statements classify the average.

The function assumes that the list is not empty. A reusable version
should check for an empty list before dividing.

**3.11.3 Example 3: Interactive Score Analyzer**

The next example asks the user to enter three scores.

def calculate_average(scores):

return sum(scores) / len(scores)

scores = \[\]

for index in range(3):

score = float(input(f"Enter score {index + 1}: "))

scores.append(score)

average = calculate_average(scores)

print("\nResults")

print("Scores:", scores)

print(f"Average: {average:.2f}")

if average \>= 90:

print("Performance: Excellent")

elif average \>= 80:

print("Performance: Good")

elif average \>= 70:

print("Performance: Satisfactory")

else:

print("Performance: Needs improvement")

Example interaction:

Enter score 1: 85

Enter score 2: 90

Enter score 3: 95

Results

Scores: \[85.0, 90.0, 95.0\]

Average: 90.00

Performance: Excellent

The for loop repeats three times. Each score is added to the list using
append().

This example demonstrates how several basic Python concepts can work
together to solve a practical problem.

**Limitation:** This introductory version assumes that each score is
valid numerical input and does not check whether the score falls within
a particular range.

**3.12 Chapter Summary**

This chapter introduced the Python foundations needed to write simple
programs.

| **Concept**         | **Main idea**                              |
|---------------------|--------------------------------------------|
| Python              | A general-purpose programming language     |
| Variable            | A name referring to a value                |
| Assignment          | Using = to assign a value                  |
| Data type           | The category of a value                    |
| Type conversion     | Changing a value's type                    |
| Arithmetic operator | Performing a mathematical operation        |
| Comparison operator | Comparing values                           |
| Logical operator    | Combining or reversing conditions          |
| Input               | Receiving information using input()        |
| Output              | Displaying information using print()       |
| Conditional         | Choosing instructions based on a condition |
| Loop                | Repeating instructions                     |
| Function            | A reusable block of code                   |
| Parameter           | A name in a function definition            |
| Argument            | A value supplied to a function             |
| Return value        | A result sent back by a function           |
| List                | An ordered, modifiable collection          |
| Exception           | An event that interrupts normal execution  |
| Debugging           | Finding and correcting program problems    |

By the end of this chapter, you should be able to write programs that
accept input, perform calculations, make decisions, repeat instructions,
organize code into functions, and process simple collections of data.

------------------------------------------------------------------------

**3.13 Review Questions, Exercises, and Solutions**

**3.13.1 Multiple-Choice Questions**

Choose the best answer for each question.

1.  Which function displays information in Python?

A. input()\
B. print()\
C. type()\
D. range()

2.  What is the data type of 3.14?

A. int\
B. str\
C. float\
D. bool

3.  What is the result of 17 % 5?

A. 2\
B. 3\
C. 3.4\
D. 12

4.  Which statement repeats instructions while a condition is true?

A. if\
B. return\
C. while\
D. def

5.  Which list method adds an element to the end of a list?

A. remove()\
B. append()\
C. pop()\
D. insert() is the only method that can add elements.

6.  What does a function's return statement do?

A. Always displays a message.\
B. Sends a result back to the caller.\
C. Repeats the function indefinitely.\
D. Defines a variable.

**Solutions**

1.  **B.** print() displays information.

2.  **C.** 3.14 is a floating-point number.

3.  **A.** Dividing 17 by 5 leaves a remainder of 2.

4.  **C.** A while loop repeats while its condition is true.

5.  **B.** append() adds an item to the end.

6.  **B.** return sends a result back to the code that called the
    function.

**3.13.2 True-or-False Questions**

1.  Python variable names are case-sensitive.

2.  input() returns an integer whenever the user enters digits.

3.  A list can contain multiple elements.

4.  The final value in range(5) is 5.

5.  A function can accept parameters.

6.  A NameError can occur when a variable has not been defined.

**Solutions**

1.  **True.** score and Score are different names.

2.  **False.** input() returns a string. Convert it using int() or
    float() when necessary.

3.  **True.** Lists can store multiple elements.

4.  **False.** range(5) produces values from 0 through 4.

5.  **True.** Parameters allow a function to receive input.

6.  **True.** Referencing an undefined name can cause a NameError.

**3.13.3 Fill-in-the-Blank Questions**

Complete each statement.

1.  The function used to display information is \_\_\_\_\_\_\_\_\_\_.

2.  The operator used to compare two values for equality is
    \_\_\_\_\_\_\_\_\_\_.

3.  The keyword used to define a function is \_\_\_\_\_\_\_\_\_\_.

4.  The method used to add an item to the end of a list is
    \_\_\_\_\_\_\_\_\_\_.

5.  The function used to calculate the number of items in a list is
    \_\_\_\_\_\_\_\_\_\_.

**Solutions**

1.  print()

2.  ==

3.  def

4.  append()

5.  len()

**3.13.4 Short-Answer Questions**

1.  What is a variable?

2.  Explain the difference between = and ==.

3.  What is the difference between a parameter and an argument?

4.  Explain the difference between a for loop and a while loop.

5.  Why is debugging important?

6.  What is the difference between print() and return?

**Solutions**

1.  A variable is a name associated with a value in a program.

2.  = assigns a value, whereas == compares two values for equality.

3.  A parameter is a name in a function definition. An argument is a
    value supplied when the function is called.

4.  A for loop iterates over an iterable, while a while loop repeats as
    long as its condition is true.

5.  Debugging helps identify and correct problems so that programs
    behave as intended.

6.  print() displays information, while return sends a result back to
    the caller. A returned result can be stored or used in further
    calculations.

**3.13.5 Code-Reading Questions**

**Question 1**

What is the output?

x = 4

y = 3

print(x + y \* 2)

**Solution**

10

Multiplication happens first: \\(3 \times 2 = 6\\). Then \\(4 + 6 =
10\\).

**Question 2**

What is the output?

numbers = \[10, 20, 30\]

numbers.append(40)

print(numbers\[1\])

print(len(numbers))

**Solution**

20

4

The element at index 1 is 20. After appending 40, the list contains four
elements.

**Question 3**

What is the output?

for number in range(1, 5):

if number == 3:

continue

print(number)

**Solution**

1

2

4

When number equals 3, continue skips the print statement for that
iteration.

**3.13.6 Debugging Questions**

**Question 1:** Identify and correct the error.

\# age = input("Enter age: ")

\# print(age + 1)

**Solution**

The input is a string. Convert it to an integer before performing
arithmetic.

age = int(input("Enter age: "))

print(age + 1)

**Question 2:** Identify and correct the error.

\# for number in range(3)

\# print(number)

**Solution**

The colon is missing after the for statement.

for number in range(3):

print(number)

Expected output:

0

1

2

**3.13.7 Programming Exercises**

**Exercise 1: Rectangle Calculator**

Write a program that asks the user for a rectangle's length and width,
then displays its area.

**Solution**

length = float(input("Enter the length: "))

width = float(input("Enter the width: "))

area = length \* width

print(f"Area: {area}")

If the length is 5 and the width is 3, the area is 15.0.

**Exercise 2: Even or Odd**

Write a function that returns "Even" when a number is even and "Odd"
otherwise.

**Solution**

def check_number(number):

if number % 2 == 0:

return "Even"

return "Odd"

print(check_number(8))

print(check_number(7))

Expected output:

Even

Odd

**Exercise 3: Sum of a List**

Write a function that calculates the sum of all numbers in a list.

**Solution**

def calculate_sum(numbers):

return sum(numbers)

values = \[10, 20, 30, 40\]

print(calculate_sum(values))

Expected output:

100

**Exercise 4: Count Passing Scores**

Given a list of scores, count how many are at least 60.

**Solution**

scores = \[45, 70, 82, 55, 90\]

count = 0

for score in scores:

if score \>= 60:

count += 1

print("Passing scores:", count)

Expected output:

Passing scores: 3

The scores 70, 82, and 90 satisfy the condition.

**Exercise 5: Average Calculator**

Write a function that returns the average of a list of numbers. It
should return None when the list is empty.

**Solution**

def calculate_average(numbers):

if len(numbers) == 0:

return None

return sum(numbers) / len(numbers)

print(calculate_average(\[80, 90, 100\]))

print(calculate_average(\[\]))

Expected output:

90.0

None

The empty-list check prevents division by zero.

**3.14 Glossary, Figure Credits, and Further Learning**

**3.14.1 Glossary**

| **Term**     | **Definition**                                      |
|--------------|-----------------------------------------------------|
| Argument     | A value supplied to a function                      |
| Assignment   | Associating a value with a variable                 |
| Boolean      | A logical value: True or False                      |
| Comment      | Text in source code ignored during normal execution |
| Condition    | An expression used to make a decision               |
| Data type    | A category describing a value                       |
| Debugging    | Identifying and correcting program problems         |
| Expression   | Code that produces a value                          |
| Function     | A reusable block of code                            |
| Index        | A position used to access an element                |
| Integer      | A whole number without a fractional part            |
| Iteration    | One repetition of a loop                            |
| List         | An ordered, modifiable collection                   |
| Loop         | A structure that repeats instructions               |
| Parameter    | A name in a function definition                     |
| Return value | A result provided by a function                     |
| String       | A sequence of characters                            |
| Syntax       | The rules governing valid code structure            |
| Variable     | A name associated with a value                      |

**References**

1.  Python Software Foundation. *The Python Tutorial.* [Python
    Documentation](https://docs.python.org/3/tutorial/?utm_source=chatgpt.com)

2.  Python Software Foundation. *Built-in Functions.* [Python Built-in
    Functions](https://docs.python.org/3/library/functions.html?utm_source=chatgpt.com)

3.  Python Software Foundation. *Errors and Exceptions.* [Python Errors
    and
    Exceptions](https://docs.python.org/3/tutorial/errors.html?utm_source=chatgpt.com)

**Figure References**

**Figure References**

Figure 3.1. Python Program Execution: [From Script to Execution: The
Inner Workings of Python \| by Karan Ji \|
Medium](https://medium.com/%40karanji01/from-script-to-execution-the-inner-workings-of-python-f078d7a863ed)

Figure 3.2. Variables and Fundamental Data Types:
[https://www.teach.cs.toronto.edu/~csc110y/fall/notes/06-memory-model/04-python-memory-model-1.html](https://www.teach.cs.toronto.edu/~csc110y/fall/notes/06-memory-model/04-python-memory-model-1.html?utm)

Figure 3.3. Loop Execution:
[https://automatetheboringstuff.com/3e/chapter3.html](https://automatetheboringstuff.com/3e/chapter3.html?utm_source=chatgpt.com)
