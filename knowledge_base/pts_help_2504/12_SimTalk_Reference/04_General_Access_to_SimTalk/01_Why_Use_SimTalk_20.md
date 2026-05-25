### Why Use SimTalk 2.0?

SimTalk 2.0 provides a number of significant improvements compared to SimTalk 1.0 making progamming easier and more comfortable. Use SimTalk 2.0 source code whenever possible and be prepared that support for SimTalk 1.0 might be terminated at a future date.

SimTalk 2.0 encompasses:

**· A line-controlled syntax**

You do not have to type a semicolon ; at the end of each statement. Instead, you can type a single statement into a line. As you might want to be able to split a statement and distribute it over several lines, the interpreter automatically determines if the statement is still incomplete and, if this is the case, continues it in the next line. You can type a semicolon after a statement to add another statement to the same line though.

| SimTalk 2.0                    | SimTalk 1.0                     |
|--------------------------------|---------------------------------|
| MyStation.setName("MyStation") | MyStation.setName("MyStation"); |

**· A simplified body syntax**

In SimTalk 1.0 the source code requires the keywords is do end . SimTalk 2.0 does not need these keywords.

In SimTalk 2.0 you declare parameters with the keyword param , local variables with the keyword var , and the return value of a method with the keyword -&gt; (hyphen plus right angle bracket).

| SimTalk 2.0                    | SimTalk 1.0                               |
|--------------------------------|-------------------------------------------|
| MyStation.setName("MyStation") | is do MyStation.setName("MyStation"); end |

**· Improved referencing of methods and global variables**

In SimTalk 1.0 Methods and Variables are referenced with the reference operator ref .

In SimTalk 2.0 you reference Methods and Variables with a leading &amp; operator , for example var o:object := &amp;Method .

- New div/mod operator : In SimTalk 1.0 the // operator represents an integer division and the \\ operator represents an integer modulo operation.

In SimTalk 2.0 the keyword div represents an integer division and the keyword mod represents an integer modulo operation .

**· Improved string literals**

In SimTalk 2.0 a backslash ( \ ) inside a string only protects double quotation marks and line breaks, it does not protect another backslash as it did in SimTalk 1.0.

"A string literal is a sequence of characters from the source character set enclosed in double quotation marks ( "" ). To represent a double quotation mark in a string literal, use the escape sequence \" . The backslash \ must be followed with a second backslash \\ when it appears within a string." Microsoft Learn

```simtalk
a := "It is \"very\" urgent." -- the backslash protects the quotation marks
Path := "C:\Temp"             -- no need to protect the backslash here
Path := "C:\\" + FolderName   -- protected backslash at the end of the string
```

**· Time literals**

A time literal starts with a digit and must contain one or more colons. A time literal can contain a decimal point and decimal places.

wait 1:30                    // wait for 1 minute and 30 seconds &Methode.methCall(1:0:0:0.5) // call the method in 1 day and half a second

**· JSON Literals**

JSON literals are enclosed in curly braces [ } and contain JSON elements separated by commas. The JSON elements consist of a string literal, a colon, and a JSON value.

```simtalk
var j: json
var jobTitle: string := "Engineer"
var addressArray:
string[] := ["Main street 42", "10001 New York"]
j := { "name": "Alice", "age": 42, "female": true, "job": jobTitle, "address": addressArray }
```

**· Default arguments**

Define default arguments for formal parameters by typing an assignment operator and the default value after the parameter declaration, for example: param x := 0 .

**· Simplified control flow statements**

The control structures which you can insert with the command Structure into your source code, reflect the simplified control structures.

<!-- image -->

You can type control flow statements using the simplified syntax:

- if-end instead of if-then-end
- for-next instead of for-loop-next
- switch-case-end instead of inspect-when-then-end
- while-end instead of while-loop-end

The keyword then in if-statements is optionally allowed.

- The keyword loop in loops is optionally allowed.
- We added the keyword continue , which skips the rest of the loop iteration, and continues with the next iteration. If the iteration was the last iteration, continue exits the loop.
- A changed about equal operator

You now have to use:

- ~= instead of == , compare Tolerance for about equal (~=) comparison . ◦ &lt;~= instead of &lt;== ◦ &gt;~= instead of &gt;==
- New operators for adding, subtracting, or multiplying a value
- An improved list and table syntax

```simtalk
◦
x += y is short
for x := x + y ◦
	x -= y is short
	for x := x - y ◦
		x *= y is short
		for x := x * y
```

You now only type list ranges using braces {} . The optional 1.0 syntax using a grave accent `[ ] is no longer available.

- Read an element of a one-dimensional list with the bracket operator [ ] . This works for StackFile and QueueFile as well. You can read and remove an element from a DataList with the built-in method remove .

**Note**

When reading the contents of a cell of a DataList with the bracket operator [] in SimTalk 1.0 , this reads and removes the contents of the designated cell. The remaining cells move up by one position.

When assigning a value to the designated cell with the bracket operator to a DataList in SimTalk 1.0 , this value is inserted into the cell and the existing cells moves down by one position.

**Note**

When reading the contents of a cell with the bracket operator [ ] in SimTalk 2.0 , the contents of the designated cell will be read, but will remain in the DataStack , DataQueue , and the DataList .

When assigning a value to the designated cell with the bracket operator to a DataList in SimTalk 2.0 , this value will just overwrite the contents of the existing cell. This way a DataList will behave the same way as a DataTable with one column.

**See also**

SimTalk Access to 3D

String [SimTalk] - value

