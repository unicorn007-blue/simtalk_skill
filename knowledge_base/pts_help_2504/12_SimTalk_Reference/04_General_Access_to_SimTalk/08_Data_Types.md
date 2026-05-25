### Data Types

```simtalk
var i: integer                 // loop index result.create                  // instantiates the results list
i := 1
while not pricelist.empty
loop // stop condition result[i] := pricelist.pop * (1 + VAT)
i := i + 1                  // increases the index end                            // end of function
```

**See also**

Declare Parameters

**Data Types**

#### Data Types [SimTalk]

Each local variable has a data type that defines its range and the permitted operations. Boolean values, for example, do not support mathematical operations.

SimTalk provides these data types:

| Acceleration [SimTalk] - data type   | Method [SimTalk] - data type   |
|--------------------------------------|--------------------------------|
| Any [SimTalk] - data type            | Object [SimTalk] - data type   |
| Array [SimTalk] - data type          | Queue [SimTalk] - data type    |
| Boolean [SimTalk] - data type        | Real [SimTalk] - data type     |
| Date [SimTalk] - data type           | Speed [SimTalk] - data type    |
| DateTime [SimTalk] - data type       | Stack [SimTalk] - data type    |
| Integer [SimTalk] - data type        | String [SimTalk] - data type   |
| JSON [SimTalk] - data type           | Table [SimTalk] - data type    |
| Length [SimTalk] - data type         | Time [SimTalk] - data type     |
| List [SimTalk] - data type           | Weight [SimTalk] - data type   |

All of the above data types are also keywords in SimTalk .

Money [SimTalk]

Plant Simulation only supports the data type money for global variables , user-defined attributes , and for lists and tables .

Money is not a SimTalk data type. For local variables use the data type real instead.

**RandTime [SimTalk]**

The global Variable and the user-defined attributes provide the data type randtime . You can use it to generate random numbers of data type time using a random number stream of its own.

Let's say you want to make the random numbers for the setup time independent of the random numbers for the processing time . To achieve this, create a user-defined attribute of data type randtime , and set the distribution type of the Set-up time to Formula , and type self.&lt;UserDefinedAttribute&gt;.rollDice into the edit box.

RandTime is not a SimTalk data type. When getting a randtime value, Plant Simulation returns a time value.

Path [signature]

The window Show Attributes and Methods shows the signature path for some objects in the column Signature .

Path is not a data type that you can assign. If a built-in attribute is listed with the data type path , you can assign a value of data type object or string to it.

<!-- image -->

**See also**

Data Types in Local Variables

Keywords

#### Acceleration [SimTalk] - data type

A local variable of data type acceleration has a maximum range of values between -8.9*10307 ≤ acceleration ≤ 8.9*10 307, which is displayed like this -8.9e307 ≤ real ≤ 8.9e307.

Remarks

The data type acceleration applies to the objects Conveyor and Transporter .

When assigning it to a variable or an attribute, Plant Simulation interprets the value as meters per second squared (m/s 2 ).

When outputting it, Plant Simulation converts the value to the unit you selected under File &gt; Model Settings/Preferences &gt; Units &gt; Acceleration .

**Note**

In SimTalk 2.0 you can specify the acceleration units mps² , cm² , fps² , and LU/s² .

Type in the unit directly after the values, without a separating blank space, for example 10mps2 or 10.2mps2 .

To create the ² symbol, activate the Num Lock key on the numeric keypad, hold down Alt and type in 0178 on the numeric keypad.

To create the ² symbol on the German keyboard layout , hold down Alt Gr and press the key with the number 2 . If your keyboard does not have the Alt Gr key, hold down Ctrl-right+Alt-right instead.

**Example**

```simtalk
var a : acceleration := 10mps²  // 10 meters per second squared
var b : acceleration := 2.5fps² // 2.5 feet per second squared
```

The data types time , length , weight , speed , and acceleration are not compatible! You can, for example, only assign a value of data type length , real or integer to a variable of data type length .

See also

**isAcceleration [SimTalk]**

#### Any [SimTalk] - data type

A local variable of data type any can take any value.

**Remarks**

The data type of the variable assumes the data type of the first assigned value. If you then assign a value that is incompatible with this data type, Plant Simulation shows an error.

To reset the assumed data type, use the forget [SimTalk] statement.

Referencing an Object of Type Python

In previous versions, the method PythonModule.getValue converted Python data types to SimTalk data types where possible. If this was not possible, the Python value was converted to a string .

Now Plant Simulation returns the Python object as a value of data type any .

The Python data type list was converted to a SimTalk array in previous versions. Now Plant Simulation returns the Python list object as a value of data type any . This prevents Plant Simulation from unnecessarily allocating memory when using large lists.

**Return Value**

The return value has the data type boolean .

Query the data type of a variable of data type any with the following functions. The function expects a parameter whose data type Plant Simulation compares.

| getSimTalkTypename [SimTalk]   | isLength [SimTalk]    | typeStatisticsCumulated [SimTalk]   |
|--------------------------------|-----------------------|-------------------------------------|
| isAcceleration [SimTalk]       | isList [SimTalk]      | isString [SimTalk]                  |
| isBoolean [SimTalk]            | isListRange [SimTalk] | isTable [SimTalk]                   |
| isDate [SimTalk]               | isObject [SimTalk]    | isTime [SimTalk]                    |
| isDatetime [SimTalk]           | isQueue [SimTalk]     | isWeight [SimTalk]                  |
| isInteger [SimTalk]            | isReal [SimTalk]      |                                     |
| isJson [SimTalk]               | isSpeed [SimTalk]     |                                     |

**Examples**

```simtalk
a := 3.14   -- data type real is assumed forget a    -- now we can assign a new data type
a := "Test" -- data type string is assumed
param arg: any // declaring the method named myPrint if isLength(arg) print "length = ", arg end // calling the method myPrint myPrint(1) myPrint("any text") myPrint(MyConveyor.length)
var a : any
a := MyConveyor.acceleration
print a," ",getUnit(a)
print isAcceleration(a)
```

**Note**

The following applies to isObject , isTable , and isList : The value VOID does not have a data type as local variables of data types object , table , and list can all take the value void. For this reason a local variable of data type any does not take a data type when you assign void to it. If the function isObject is called with such a variable, the function returns the result false.

**Example**

```simtalk
var a: any := void
print isObject(a)   // prints false
print a = void      // prints true
var b : any := 123
print b = void      // prints false
```

You can also use the function getSimTalkTypename to get the data type of a variable of data type any .

**Return Value**

The return value has the data type string .

**Example**

```simtalk
param a : any
switch getSimTalkTypename(a)
case "integer"
	print "integer argument"
case "string"
	print "string argument"
end
```

**See also**

Query the Data Type of a Variable of Data Type Any

Video on YouTube

[https://youtu.be/5t-wLNmKpbU?si=dR0rGUZ1qLqr3zj7&amp;t=226](https://youtu.be/5t-wLNmKpbU?si=dR0rGUZ1qLqr3zj7&t=226)

#### Array [SimTalk] - data type

Array [SimTalk] - data type

A local variable of data type array designates a one-dimensional or a two-dimensional value field of one of the base data types listed under Data Types .

Remarks

Base data types for the array data types are:

<!-- image -->

Base data types can be all data types except for table , list , stack , and queue . If you type in any as the base data type, each item of the value field can have a different data type. Then, even lists and tables can be placed in the array .

Array indexes are one-based, i.e., they start with 1, not with 0.

You can declare array variables as follows:

```simtalk
a : integer[10] b : boolean[10,20] a : string[]
```

- Type in a single number within the brackets to specify a one-dimensional array of fixed size, for example a : integer[10] .
- Type in two numbers within the brackets to specify a two-dimensional array of fixed size, for example b : boolean[10,20] .
- Do not type any number at all within the brackets to specify a one-dimensional array , whose size is not fixed, and which is empty initially, for example a : string[] .

Compare this example:

```simtalk
var vector3  : real[3]               // one-dimensional array with 3 real values
var matrix3x3 : real[3,3]            // two-dimensional array with 9 real values
var objList : object[]               // one-dimensional array with n objects (the size can change)
var a        : any[]                 // one dimensional array with n values
of any data type
print vector3[2]                     // prints 0 to the console
vector3 := [1.0, 2.0, 3.0]           // fills a one-dimensional array
print vector3[2]                     // prints 2 to the console // For filling a two-dimensional array you might type:
for var x := 1 to matrix3x3.xDim
	for var y := 1 to matrix3x3.yDim
		matrix3x3[x,y] := x + y
	next
next
print matrix3x3         // prints [2, 3, 4][3, 4, 5][4, 5, 6]
print objList.dim       // prints 0 to the console
objList.append(Station) // adds Station to the array
print objList.dim       // prints 1 to the console
print objList[1]        // prints the path to the Station on the console
a := vector3
a.append("Hello World")
print a.dim             // prints 4 in the console
print a                 // prints [1, 2, 3, Hello World] to the console
```

Plant Simulation displays empty arrays with a space between the brackets like this "[ ]" , compare the following example:

```simtalk
var a : real[]
var s : string := to_str(a)  // s := "[ ]"
```

This example creates a nested array :

```simtalk
-- array of two arrays -- detect the datatype by the method isArray
var a:any[] := [[current, pi, exp(1)], [Eventcontroller, 42]]
print "a = ",a
print  "a[1] = ",a[1]
print  "a[2] = ",a[2] -- datatype array
print isArray(a[1])
print isArray(a)
```

The Functions for Accessing 3D Objects make extended use of the array data types.

The window Show Attributes and Methods shows the value of an array in brackets, compare Show Methods .

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

**See also**

Data Types [SimTalk]

Methods and Attributes of Arrays

isArray [SimTalk]

Print the Contents List to the Console as an Array

Use a Drag-and-Drop Control for Several Objects

Video on YouTube

[https://youtu.be/9g6Uou-8eMc?si=wxwJfDmUOR\_lHVQ5&amp;t=988](https://youtu.be/9g6Uou-8eMc?si=wxwJfDmUOR_lHVQ5&t=988)

##### Add and Subtract Arrays of Numerical Data Types

You can add and subtract arrays of numerical data types ( integer, real, length, weight, speed, acceleration, time ) whose dimensions match.

In addition, you can multiply arrays of a floating point data type ( real, length, weight, speed, acceleration, time ) with a numerical value ( integer, real ) or divide them by a numerical value. We also support matrix multiplication for arrays of a floating point data type.

See also

Relational Operators

##### Compare Arrays of Different Data Types

When comparing arrays of different data types, Plant Simulation throws a runtime error and opens the Method Debugger in the following cases:

- Arrays of data type real , length , time , speed, and weight based on their content.
- Arrays of data type any are compared to other arrays based on their content as well.

**Note**

Arrays of data type integer cannot be compared with arrays of data type real , length , time , speed , or weight .

**Examples**

```simtalk
-- arrays with different data types
var a:any[4] -- array with different data types
a := [current, pi, -42, [1, 2, 3]]
print "a = ",a
print "a[1]: ", getSimTalkTypename(a[1])
a[1] := "Hello" -- change the data type print "a[1]: ", getSimTalkTypename(a[1])
-- create, assign, compare arrays
var a:integer[3]
a[1] := 5
a[2] := 2
a[3] := 7
print "a = ",a
var b:integer[3]
print "b = ",b
b := a
print "b = ",b
print"a = b ", a=b
b.sort
print "b = ",b
print "a = b ", a=b
```

**See also**

**Relational Operators**

##### Methods and Attributes of Arrays

Methods and Attributes of Arrays

The array data types provide a number of attributes and methods for accessing them.

Array data types provide these methods and attributes:

| append [SimTalk] - array            | deleteValue [SimTalk]    | normalize [SimTalk]    |
|-------------------------------------|--------------------------|------------------------|
| appendArray [SimTalk]               | Dim [SimTalk] - array    | pop [SimTalk] - array  |
| appendValueOfType [SimTalk]         | Empty [SimTalk] - array  | sort [SimTalk] - array |
| asAny [SimTalk]                     | find [SimTalk] - array   | sum [SimTalk] - array  |
| contains [SimTalk] - array          | getValueOfType [SimTalk] | X [SimTalk] - array    |
| copyFromTable [SimTalk]             | insert [SimTalk] - array | xDim [SimTalk] - array |
| copyFromTableColumn [SimTalk]       | join [SimTalk]           | Y [SimTalk] - array    |
| copyToTable [SimTalk]               | Magnitude [SimTalk]      | yDim [SimTalk] - array |
| copyToTableColumn [SimTalk] - array | max [SimTalk] - array    | makeRGBValue [SimTalk] |
| delete [SimTalk] - array            | min [SimTalk] - array    |                        |

See also

isArray [SimTalk]

append [SimTalk] - array append [SimTalk] - array

Appends the value designated by the parameter to the end of a one-dimensional array designated by &lt;array&gt; that does not have a fixed size.

Type

Method

Syntax

< array >.append(Value:any)

Parameter

The parameter Value of data type any designates the value that you want to append.

Example

```simtalk
var a: string[]
a.append("string")
a.append("string")
print a[2]
```

See also

appendArray [SimTalk]

join [SimTalk]

###### appendArray [SimTalk]

Appends all elements of the array passed as the parameter to the array designated by &lt;array&gt;.

Remarks

The data types of the passed array and the existing array have to match.

The method appendArray only applies to one-dimensional arrays which do not have a fixed size.

Type

Method

Syntax

&lt; array &gt;.appendArray(ArrayToBeAppended:array)

**Parameter**

The parameter ArrayToBeAppended of data type array designates the array that is to be appended to the existing array.

Example

```simtalk
var a :
integer[]  := [1, 2, 3]
var b :
integer[2] := [4, 5]
a.appendArray(b)
print a  // outputs [1, 2, 3, 4, 5]
```

**See also**

append [SimTalk] - array

**appendValueOfType [SimTalk]**

###### appendValueOfType [SimTalk]

Converts the passed value to a byte sequence and appends these bytes at the end of an array of data type integer designated by &lt;array&gt; whose size is not defined.

**Remarks**

appendValueOfType is useful if you want to send binary data with the object Socket .

Type

Method

Syntax

```simtalk
< array >.appendValueOfType(Value:any, Type:string)
```

**Parameters**

- The parameter Value of data type any designates the value that you want to append.
- The parameter Type of data type string designates the data type of the value that you want to append.

The passed value can be of data type integer , boolean , real , length , time , speed , weight , or acceleration . The value is converted to a byte sequence of a defined length where each byte has a value between 0 and 255.

The length depends on the value of the parameter Type . Allowed values for Type are:

```simtalk
"int8", "int16", "int32", "int64", "uint8", "uint16", "uint32", "uint64", "real32", "real64",
```

"Int8", "Int16", "Int32", "Int64", "Uint8", "Uint16", "Uint32", "Uint64", "Real32", and "Real64".

The number in the Type designates the number of bits, where 8 bits result in 1 byte. "int16" for example converts the value to 2 bytes and appends these as 2 integer values to the array .

The byte order of the byte sequence is determined by the first letter of the parameter Type .

- If Type starts with a lower case letter, the byte sequence is created in little-endian format.
- If Type starts with an upper case letter, the byte sequence is created in big-endian format.

**Example**

```simtalk
var a : integer[]
a.appendValueOfType(123456, "int32")  // append 4 bytes
a.appendValueOfType(-3000, "int16")   // append 2 bytes
var x := a.getValueOfType(1, "int32") // read 4 bytes
var y := a.getValueOfType(5, "int16") // read 2 bytes
```

**See also getValueOfType [SimTalk] Socket**

**asAny [SimTalk]**

###### asAny [SimTalk]

Can be called for arrays of data type string and object designated by &lt;array&gt; and returns a reference to the addressed array-element .

**Remarks**

asAny returns a reference to the addressed array-element if its value is a relative or an absolute path to an existing object or to an existing lane , storage place or to a user-defined attribute of data type table , list , stack or queue .

Type

Method

Syntax

```simtalk
< array >.asAny(Index:integer[, YIndex:integer]) → any
```

**Parameters**

- The parameter Index of data type integer designates the index position of the element in a onedimensional array .

If the array is two-dimensional , the parameter Index designates the X-index-position (i.e., the column number) of the element.

**Return Value**

- The parameter YIndex of data type integer designates the Y-index-position (i.e., the row number) of the element in a two-dimensional array .
- The return value has the data type object if the array element contains a reference or a path to an existing object of type Frame .
- The return value has the data type any if the array element contains the path to a lane on a TwoLaneTrack or to a storage place .
- The return value has the data type table , list , stack or queue respectively if the array element contains the path to a user-defined attribute of data type table , list , stack or queue .
- The return value is VOID if the value of the array element does not contain a path to a valid object, or something similar.

**Example**

```simtalk
var a : object[2];
a[1] := "TwoLaneTrack.A"
a[2] := "Station.MyTableAttr"
var obj0 := a[1]        // obj0 is VOID, as not of type 'object'
var obj1 := a.asAny(1)  // obj1 is .Models.Model.TwoLaneTrack.A of type 'any'
var obj2 := a.asAny(2)  // obj2 is .Models.Model.Station.MeinTabellenAttr of type 'table'
```

See also

Lane A

Lane B

getRoute [SimTalk] - Transporter

###### contains [SimTalk] - array

contains [SimTalk] - array

Returns if the specified value is contained in the array designated by &lt;array&gt; (true) or not (false).

Remarks

The method contains only applies to one-dimensional arrays .

Type

Method

Syntax

```simtalk
< array >.contains(Value:any) → boolean
```

**Parameters**

The parameter Value of data type any designates the value which you would like to know if it is contained in the array .

Return Value

The return value has the data type boolean .

**Examples**

```simtalk
var a :
string[] := ["hello", "world"]
print "this code is always reached"
if a.contains("world")
end
if a.contains("hell")
	print "this code is never reached"
end
param color : string := "yellow" if ["red","green","blue"].contains(color)
print "color is red or green or blue"
end
```

###### copyFromTable [SimTalk]

Copies the table designated by the parameter of data type table into the array designated by &lt;array&gt;.

Remarks

If the array has a fixed size, the dimension of the table, or of the range of the table, have to match the size of the array .

If you copy the table into a one-dimensional array , the values have to be contained in a row of the table.

Type

Method

Syntax

&lt; array &gt;.copyFromTable([SourceRange:listrange,] SourceTable:table)

**Parameters**

- The parameter SourceTable of data type table designates the table from which you would like to copy the data.
- The optional parameter SourceRange of data type listrange designates the range which you want to copy from the table.

**Example**

targetArray.copyFromTable(MyDataTable)

**copyFromTableColumn [SimTalk]**

###### copyFromTableColumn [SimTalk]

Copies the contents of the column of the table into the one-dimensional array designated by &lt;array&gt;.

Type

Method

Syntax

```simtalk
< array >.copyFromTableColumn(SourceTable:table, Column:integer)
```

**Parameters**

- The parameter SourceTable of data type table designates the table from which you would like to copy data.
- The parameter Column of data type integer designates the column whose data you want to copy.

**Example**

```simtalk
var array: string[]
array.copyFromTableColumn(DataTable, 3)
```

###### copyToTable [SimTalk]

Copies the array designated by &lt;array&gt; into a table.

Type

Method

Syntax

&lt; array &gt;.copyToTable(TargetTable:table[, Column:integer, Row:integer])

**Parameters**

- The parameter TargetTable of data type table designates the target table.
- The optional parameter Column of data type integer designates the column of the table.
- The optional parameter Row of data type integer designates the row of the table.

**Example**

arrayVar.copyToTable(MyDataTable,2,9)

**See also**

Write the Content List into a Table for Further Processing

###### copyToTableColumn [SimTalk] - array

copyToTableColumn [SimTalk] - array

Copies the contents of the one-dimensional array designated by &lt;array&gt; to the specified column of a table.

Type

Method

Syntax

```simtalk
< array >.copyToTableColumn(TargetTable:table, Column:integer)
```

**Parameters**

- The parameter TargetTable of data type table designates the table to which you would like to copy data.
- The parameter Column of data type integer designates the column into which you would like to paste data.

**Example**

```simtalk
var array:
string[2] := ["hello", "world"]
array.copyToTableColumn(DataTable, 3)
```

delete [SimTalk] - array

Deletes the contents of the array designated by &lt;array&gt;.

Type

Method

Syntax

```simtalk
< array >.delete([Index:integer])
```

Parameter

The optional parameter Index of data type integer deletes the item located at this index position. The size of the array is smaller by 1 after this.

Example

```simtalk
a := [current,pi,e]
a.delete(2)
print a.dim
```

###### deleteValue [SimTalk]

deleteValue [SimTalk]

Deletes the first occurrence of specified value from the one-dimensional array designated by &lt;array&gt;.

Type

Method

Syntax

```simtalk
< array >.deleteValue(Value:any) → boolean
```

Parameter

The parameter Value of data type any designates the value that is going to be deleted.

Return Value

The return value has the data type boolean .

The return value is true if the value is part of the array .

The return value is false if the value is not part of the array .

Example

```simtalk
a:
string[] := ["Alice", "Bob", "Charlie"]
a.deleteValue("Bob")
print a // prints ["Alice", "Charlie"]
```

Dim [SimTalk] - array

Returns the dimension of the one-dimensional array designated by &lt;array&gt;.

Type

Read-only attribute

Syntax

< array >.Dim

Return Value

The return value has the data type integer .

Example

```simtalk
var a:real[3]
print a.Dim // prints 3
```

###### Empty [SimTalk] - array

Empty [SimTalk] - array

Returns if the array designated by &lt;array&gt; is empty (true) or if it contains items (false).

Remarks

Empty only applies to one-dimensional arrays .

Type

Read-only attribute

Syntax

```simtalk
< array >.Empty → boolean
```

Return Value

The return value has the data type boolean .

Example

```simtalk
var a : integer[]
if a.empty
	a.append(42)
end
if not a.empty
	print a[1]
end
```

###### find [SimTalk] - array

Searches for a value in the one-dimensional array designated by &lt;array&gt;.

Type

Method

Syntax

```simtalk
< array >.find(Value:any[, StartIndex:integer])
```

**Parameters**

- The parameter Value of data type any designates the value that you want to find.
- The optional parameter StartIndex of data type integer sets the start index, i.e., the position, from which on Plant Simulation starts a search toward the end of the array .

Return Value

The return value is the position of the item which was found.

Is 0 if the value is not contained in the array .

**Example**

```simtalk
var a:real[5] := [1.1, 2.2, 3.3, 4.4, 5.5]
print a.find(3.3)     // prints 3
print a.find(3.3, 4)  // prints 0, that is, not found
```

**getValueOfType [SimTalk]**

###### getValueOfType [SimTalk]

Reads a byte sequence from the array of data type integer designated by &lt;array&gt; and converts it to a value and returns it.

Remarks

getValueOfType is useful if you want to receive binary data with the object Socket .

Type

Method

Syntax

```simtalk
< array >.getValueOfType(Index:integer, Type:string)
-> any
```

**Parameters**

- The parameter Index of data type integer designates the value that you want to append.

The parameter Index sets at which position in the array the byte sequence starts. The length of the byte sequence depends on the value of the parameter Type . Allowed values for Type are:

```simtalk
"int8", "int16", "int32", "int64", "uint8", "uint16", "uint32", "uint64", "real32", "real64", "bool",
```

"Int8", "Int16", "Int32", "Int64", "Uint8", "Uint16", "Uint32", "Uint64", "Real32", "Real64", and "Bool".

- The parameter Type of data type string designates the data type of the value that you want to append.

The number in the Type designates the number of bits, where 8 bits result in 1 byte. "int16" for example reads 2 bytes from the array and creates an integer value between -32768 and 32767.

The byte order of the byte sequence is determined by the first letter of the parameter Type .

- If Type starts with a lower case letter, the byte sequence is interpreted in little-endian format.
- If Type starts with an upper case letter, the byte sequence is interpreted in big-endian format.

**Return Value**

The return value has the data type any .

**Example**

```simtalk
var a : integer[]
a.appendValueOfType(123456, "int32")  // append 4 bytes
a.appendValueOfType(-3000, "int16")   // append 2 bytes
var x := a.getValueOfType(1, "int32") // read 4 bytes
var y := a.getValueOfType(5, "int16") // read 2 bytes
```

**See also**

**appendValueOfType [SimTalk]**

**Socket**

###### insert [SimTalk] - array

insert [SimTalk] - array

Inserts a value into the one-dimensional array designated by &lt;array&gt; which does not have a fixed size.

Type

Method

Syntax

```simtalk
< array >.insert(Index:integer, Value:any)
```

**Parameters**

- The parameter Index of data type integer designates the index position at which Plant Simulation inserts the value.
- The parameter Value of data type any designates the value which you want to insert.

**Example**

```simtalk
var a:
real[] := [1.1, 2.2, 3.3, 4.4, 5.5]
a.insert(3,-11)
print a // returns [1.1, 2.2, -11, 3.3, 4.4, 5.5]
```

###### join [SimTalk]

Converts the elements within the array designated by &lt;array&gt; into a string and unites all elements to a single string. Within the resulting string the elements are separated by the separator string.

Type

Method

Syntax

```simtalk
< array >.join(separator:string) → string
```

Parameter

The parameter separator of data type string sets the separator string. The separator string can contain any character.

Return Value

The return value has the data type string .

Example

```simtalk
var a:integer[]
a.append(1)
a.append(2)
a.append(3)
print a.join(" * ") // 1 * 2 * 3
```

See also

append [SimTalk] - array

**Magnitude [SimTalk]**

###### Magnitude [SimTalk]

Returns the magnitude/the length of the designated vector of the numerical one-dimensional array designated by &lt;array&gt;.

Type

Read-only attribute

Syntax

```simtalk
< array >.Magnitude → real
```

Return Value

The return value has the data type real .

Example

```simtalk
var direction:
real[3] := [2.0, 3.5, 2.8]
print direction.Magnitude
```

max [SimTalk] - array

Returns the greatest value contained in the array designated by &lt;array&gt;. If the array is empty, the method returns 0 for an array of numbers and an empty string "" for an array of strings .

Remarks

max only applies to one-dimensional arrays with a numerical data type or with the data type string .

Type

Method

Syntax

< array >.max

**Return Value**

If the method is called with two values having the same physical unit, the returned value also has this unit. Compare these examples:

```simtalk
max(time, time)
-> time max(length, length)
-> length max(length, speed)
-> real max(length, real)
-> real max(integer, integer)
-> integer max(integer, real)
-> integer max(real, integer)
-> integer max(integer, weight)
-> real
```

**Example**

```simtalk
var a:real[5] := [1.1, 2.2, 3.3, 4.4, 5.5]
print a.max // prints 5.5
var arrPartPos: length[]
var maxPartPos: length := arrPartPos.max
arrPartPos := [6300mm, 5600mm]
print arrPartPos.max
```

**See also**

min [SimTalk] - array

**min [SimTalk] - array**

min [SimTalk] - array

Returns the smallest value contained in the array designated by &lt;array&gt;.

Remarks

min only applies to one-dimensional arrays with a numerical data type or with the data type string .

Type

Method

Syntax

< array >.min

**Return Value**

If the method is called with two values having the same physical unit, the returned value also has this unit. Compare these examples:

```simtalk
min(time, time)
-> time min(length, length)
-> length min(length, speed)
-> real min(length, real)
-> real
min(integer, integer)
-> integer min(integer, real)
-> integer min(real, integer)
-> integer min(integer, weight)
-> real
```

**Example**

```simtalk
var a:real[5] := [1.1, 2.2, 3.3, 4.4, 5.5]
print a.min // prints 1.1
var arrPartPos:length[]
arrPartPos := [6300mm, 5600mm]
print arrPartPos.min
```

**See also**

max [SimTalk] - array normalize [SimTalk]

Normalizes the array designated by &lt;array&gt; of a numerical data type.

Remarks

The method normalize only applies to numerical one-dimensional arrays .

A normalized vector retains its direction, its length (its Magnitude ) becomes 1 though. The resulting vector is often called unit vector. A vector is normalized by dividing it by its own length.

Type

Method

Syntax

```simtalk
< array >.normalize → real
```

Return Value

The return value has the data type real .

The return value is the magnitude of the designated old vector.

Example

```simtalk
var v:real[3]
v := [2,3,4]
print v.normalize
print v // prints 5.3851648071345 [0.371390676354104, 0.557086014531156, 0.742781352708207]
```

See also

Magnitude [SimTalk]

###### pop [SimTalk] - array

pop [SimTalk] - array

Removes the last element from the array designated by &lt;array&gt; and returns this value.

Type

Method

Syntax

< array >.pop → any

Return Value

The return value has the data type any .

**Example**

```simtalk
var a:integer[]
a.append(1)
a.append(2)
a.append(3)
print a.pop // 3
```

###### sort [SimTalk] - array

Sorts the array designated by &lt;array&gt;.

Remarks

When sorting a two-dimensional array , Plant Simulation sorts the rows according to the first column.

**Note**

Sorting is case-sensitive.

Type

Method

Syntax

```simtalk
< array >.sort(Descending:boolean:=false)
```

Parameter

The optional parameter Descending of data type boolean sets how the array is going to be sorted:

- Specify true to sort the array in descending order.
- Specify false or do not specify the parameter to sort the array in ascending order.

**Default Value of the Parameter**

The default value is false.

**Examples**

```simtalk
var a:integer[] := [4, 2, 1, 3]
a.sort(false) // ascending
print a       // returns [1, 2, 3, 4]
var a:integer[] := [4, 2, 1, 3]
a.sort(true) // descending
print a      // returns [4, 3, 2, 1]
sum [SimTalk] - array Returns the sum of all values contained in the array designated by <array>. Remarks The method sum only applies to one-dimensional arrays . Type Method Syntax < array >.sum Example
var a:real[5] := [1.1, 2.2, 3.3, 4.4, 5.5]
print a.sum // returns 16.5 sum [SimTalk] - array
```

###### X [SimTalk] - array

Returns the element of the array designated by &lt;array&gt; with the index 1.

Remarks

The attribute X applies to one-dimensional arrays , which are of data type integer , real , or length , and have a fixed dimension of three elements . The attribute X points to the element of the array with the index 1.

The attribute X applies to one-dimensional arrays , which are of data type integer , real , or length , and have a fixed dimension of two elements .

Type

Attribute

Syntax

```simtalk
< array >.X
-> integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
var c:
real[3] := Station.Coordinate3D
print c.X  // prints c[1]
c.X := 42  // c[1] := 42
```

See also

Y [SimTalk] - array Z [SimTalk] - array

xDim [SimTalk] - array

xDim [SimTalk] - array

Returns the x-dimension of the two-dimensional array designated by &lt;array&gt;.

Type

Method

Syntax

```simtalk
< array >.xDim
-> integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
var matrix:real[2,3]
print matrix.xDim // prints 2
```

Y [SimTalk] - array

Returns the element of the array designated by &lt;array&gt; with the index 2.

Remarks

The attribute Y applies to one-dimensional arrays , which are of data type integer , real , or length , and have a fixed dimension of three elements . The attribute Y points to the element of the array with the index 2.

The attribute Y applies to one-dimensional arrays , which are of data type integer , real , or length , and have a fixed dimension of two elements .

Type

Attribute

Syntax

```simtalk
< array >.Y
-> integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
var c:
real[3] := Station.Coordinate3D
print c.Y  // prints c[2]
c.Y := 42  // c[2] := 42
```

See also

X [SimTalk] - array Z [SimTalk] - array

yDim [SimTalk] - array yDim [SimTalk] - array

Returns the y-dimension of a two-dimensional array designated by &lt;array&gt;.

Remarks

The method yDim returns 0 for a one-dimensional array . This way you can find out if a local variable of data type any contains a one-dimensional array or a two-dimensional array and if it was assigned to this station, not if it actually was there yet.

Type

Method

Syntax

```simtalk
< array >.yDim
-> integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
var matrix:real[2, 3]
print matrix.yDim // prints 3
```

###### Z [SimTalk] - array

Returns the element of the array designated by &lt;array&gt; with the index 3.

Remarks

The attribute Z applies to one-dimensional arrays , which are of data type integer , real , or length and have a fixed dimension of three elements .

Type

Method

Syntax

```simtalk
< array >.Z
-> integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
var c:
real[3] := Station.Coordinate3D
print c.Z  // prints c[3]
c.Z := 42  // c[3] := 42
```

**See also**

X [SimTalk] - array Y [SimTalk] - array

#### Boolean [SimTalk] - data type

A local variable of data type boolean can be true or false . See also Boolean [SimTalk] - value isBoolean [SimTalk]

#### Date [SimTalk] - data type

A local variable of data type date designates a date between 01.01.1900 and 31.12.9999.

Remarks

When assigning a value to a variable or an attribute of the data type time , you have to convert the date with the function str\_to\_date .

Before you assign a value to the local variable, it has an initial value . It is 0 for all numerical data types, false for the data type boolean , an empty string ( "" ) for the data type string , and void for the data types object and list or table .

The initial value for the data types date and DateTime depends on the Plant Simulation version in which you initially created your simulation model. For models, which you created in Plant Simulation 14.0 or higher, the start value is 01.01.1900.

See also

isDate [SimTalk]

#### DateTime [SimTalk] - data type

A local variable of data type dateTime designates a date and a time between 01.01.1900 00:00:00 and 31.12.9999 23:59:59.

Remarks

When assigning a value to a variable or an attribute, you have to convert the date with the function str\_to\_dateTime .

Before you assign a value to the local variable, it has an initial value . It is 0 for all numerical data types, false for the data type boolean , an empty string ( "" ) for the data type string , and void for the data types object and list or table .

The initial value for the data types Date and dateTime depends on the Plant Simulation version in which you initially created your simulation model. For models, which you created in Plant Simulation 14.0 or higher, the start value is 01.01.1900.

See also

isDatetime [SimTalk]

#### Integer [SimTalk] - data type

A local variable of data type integer can only contain integer numbers.

Remarks

The range of values is between -9.223.372.036.854.775.808 ≤ integer ≤ 9.223.372.036.854.775.807. Plant Simulation does not check for values outside of this range.

See also

Integer [SimTalk] - value

isInteger [SimTalk]

#### JSON [SimTalk] - data type

JSON [SimTalk] - data type

A local variable of data type JSON can hold values in the JSON data format.

Remarks

JSON, standing for J ava S cript O bject N otation, is a standardized data format that can be used for exchanging data between applications. Many web applications and web services expect their input data and return their results in JSON format.

JSON data is structured data that can be nested arbitrarily. The data consists of one, none, or several elements. Each element is a name-value-pair. The name can contain spaces and special characters.

**Note**

Names in JSON are case-sensitive.

The values of a name-value-pair can have the following data types:

- Integer : A signed integer number
- Real : A floating point number
- Boolean : true or false
- String : A string within quotation marks, for example "my string"
- Array : An ordered list of values within brackets [] and separated by commas
- JSON : An unordered list of elements (name-value-pairs) within braces {} and separated by commas

##### JSON [SimTalk] - data type

- Void : An empty value that JSON displays as null

```simtalk
var person: json
person["Name"] := "Robert"
person["Age"] := 42
person["Personnel No"] := "007-1234-55"
var person
person["age"] := 30
person["age"] += 1  // Congratulations :-)
```

You can also address a name-value-pair via an integer index . This way you can iterate across all name-value-pairs. You always have to either select the name or the value from such a name-value-pair by appending .Name or .Value respectively.

```simtalk
var j: json
j["color"] := "red"
j["shape"] := "triangle"
for var i := 1 to j.dim
	print j[i].Name, " ", j[i].Value
next
```

For more information about JSON, consult Wikipedia https://en.wikipedia.org/wiki/JSON .

See also

Elements of Data Type Object in JSON Variables

Methods and Attributes of JSON

isJson [SimTalk]

##### JSON Literals

JSON literals are enclosed in curly braces { } and contain JSON elements separated by commas. The JSON elements consist of a string literal, a colon, and a JSON value.

**Remarks**

JSON values can be any of the following:

- A number (an integer literal or a real literal)
- A string literal
- The boolean literals true and false
- void
- A local variable of data type integer , real , boolean , string , object , array , or json

**Example**

```simtalk
var j: json
var jobTitle: string := "Engineer"
var addressArray:
string[] := ["Main street 42", "10001 New York"]
j := { "name": "Alice", "age": 42, "female": true, "job": jobTitle, "address": addressArray }
```

**See also**

**Why Use SimTalk 2.0?**

##### Elements of Data Type Object in JSON Variables

JSON variables can, among others, accept elements of data type object .

```simtalk
var j: json
j["o"] := MyStation    -- element "o" is of data type object j["o"].Label := "ABC"  -- assigns a label to the object MyStation
```

**Note**

JSON, standing for J ava S cript O bject N otation, is a standardized data format that can be used for exchanging data between applications.

The element type object is an extension that is not defined within the JSON standard and which only Plant Simulation provides. When JSON data is converted into a string , for example to send it via an interface, all object elements will be written as a string with their absolute path to the object . This is necessary so that the created string is a standard-conform representation which other applications can process.

```simtalk
var json1, json2: json
json1["o"] := MyStation          -- element "o" is of data type object
var s : string := to_str(json1)  -- convert data into a string
json2.parse(s)                   -- element "o" is of data type string
```

Methods and Attributes of JSON

Methods and Attributes of JSON

The data type json provides the methods and attributes listed in the table of contents for accessing it.

JSON provides these methods and attributes:

| asString [SimTalk] - JSON          | Dim [SimTalk] - JSON       |
|------------------------------------|----------------------------|
| contains [SimTalk] - JSON          | getOrCreateJSON [SimTalk]  |
| copy [SimTalk] - JSON              | parse [SimTalk]            |
| copyToTableColumn [SimTalk] - JSON | readFile [SimTalk] - JSON  |
| copyToTableRow [SimTalk] - JSON    | unshareAndDelete [SimTalk] |
| delete [SimTalk] - JSON            | writeFile [SimTalk] - JSON |

**Note**

You can also address a name-value-pair via an integer index . This way you can iterate across all name-value-pairs.

You always have to either select the name or the value from such a name-value-pair by appending .Name or .Value respectively.

```simtalk
var j: json
j["color"] := "red"
j["shape"] := "triangle"
for var i := 1 to j.dim
	print j[i].Name, " ", j[i].Value
next
```

###### asString [SimTalk] - JSON

asString [SimTalk] - JSON

Returns the string representation of the JSON object designated by &lt;json&gt;.

Remarks

You can, for example, send the returned string to a Web-server. The method parse can re-transform such a string into the JSON format.

Type

Method

Syntax

```simtalk
< json >.asString([MultiLine:boolean:=true])
-> string
```

Parameter

The optional parameter MultiLine of data type boolean sets if the method returns the result with line breaks and indenting spaces ( true ) or without them ( false ).

**Default Value of the Parameter**

The default value is true.

Return Value

The return value has the data type string .

Example

```simtalk
var j: json
j["Name"] := "Tom"
j["Age"] := 32
var s: string := j.asString(false)
```

**See also**

parse [SimTalk]

###### contains [SimTalk] - JSON

Returns if the JSON object designated by &lt;json&gt; contains a name-value-pair with the passed name (true) or not (false).

Type

Method

Syntax

```simtalk
< json >.contains(Name:string)
-> boolean
```

**Parameter**

The parameter Name of data type string designates the name which you would like to know if it is contained in the JSON object.

Return Value

The return value has the data type boolean .

Example

```simtalk
var j: json
j["Body color"] := "blue"
if a.contains("Body color")
	print "This code will always be reached."
end
```

###### copy [SimTalk] - JSON

copy [SimTalk] - JSON

Returns a copy of the JSON object designated by &lt;json&gt;.

Type

Method

Syntax

< json >.copy -> json

Return Value

The return value has the data type json .

Examples

```simtalk
var Person1, Person2: json
Person2 := Person1          -- Person1 and Person2 reference the same JSON object Person2["Name"] := "Alice"  -- also changes Person1["Name"]
print Person1["Name"]       -- returns Alice
Person2 := Person1.copy     -- Person1 and Person2 now are different JSON objects Person2["Name"] := "Bob"    -- does not change Person1["Name"]
print Person1["Name"]       -- returns Alice
var Person, Job: json
Job["Description"] := "engineer"
Person["Job"] := Job.copy    -- inserts a copy of Job in Person Job["Company"] := "Siemens"  -- does not change Person["Job"]
```

###### copyToTableColumn [SimTalk] - JSON

Copies the contents of the json array designated by &lt;json array&gt; to the specified column of a table.

Type

Method

Syntax

```simtalk
< json array >.copyToTableColumn(TargetTable:table, Column:integer)
```

**Parameters**

- The parameter TargetTable of data type table designates the table to which you would like to copy data.
- The parameter Column of data type integer designates the column into which you would like to paste data.

**Example**

```simtalk
var j:json
j["a"] := ["hello", "world", 42] j["a"].copyToTableColumn(DataTable, 2) -- copies the three array elements into the first -- three cells of the second column of the table
```

**copyToTableRow [SimTalk] - JSON**

###### copyToTableRow [SimTalk] - JSON

Copies the contents of the json array designated by &lt;json array&gt; to the specified row of a table.

Type

Method

Syntax

```simtalk
< json array >.copyToTableRow(TargetTable:table, Row:integer)
```

**Parameters**

- The parameter TargetTable of data type table designates the table to which you would like to copy data.
- The parameter Row of data type integer designates the row into which you would like to paste data.

**Example**

```simtalk
var j:json
j["a"] := ["hello", "world", 42] j["a"].copyToTableRow(DataTable, 2) -- copies the three array elements into the first -- three cells of the second row of the table
```

###### delete [SimTalk] - JSON

The method delete without parameter deletes the entire contents of the JSON object designated by &lt;json&gt;. The method delete with parameter deletes the specified name-value pair.

Type

Method

Syntax

```simtalk
< json >.delete([Name:string])
-> boolean
```

**Parameter**

Specify the optional parameter Name of data type string to delete the name-value-pair with the specified name.

Return Value

The return value has the data type boolean .

The return value is true if the JSON object did contain the name before.

The return value is false if it did not contain the name before.

**Example**

```simtalk
var person: json
person["Name"] := "Jason"
if person.delete("name")
	print "This code will never be reached."
elseif person.delete("Name")
	print "This code will always be reached."
end
```

###### Dim [SimTalk] - JSON

Dim [SimTalk] - JSON

Returns the number of name-value-pairs which the JSON object designated by &lt;json&gt; contains.

Type

Read-only attribute

Syntax

```simtalk
< json >.Dim
-> integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
param s: string
var j: json
j.parse(s)
if j.Dim = 0
print "No data available."
end
```

###### getOrCreateJSON [SimTalk]

Returns a reference to the empty JSON object designated by &lt;json&gt;.

Remarks

If the JSON object does not contain a name-value-pair with the specified name yet in the variable, Plant Simulation creates a new name-value-pair and sets an empty JSON object as value. The method getOrCreateJSON returns a reference to this empty JSON object.

If the JSON object designated already contains a name-value-pair with the specified name yet in the variable and the value has the data type json , the method getOrCreateJSON returns a reference to the contained value. If the value has another data type than json , Plant Simulation shows an error.

Type

Method

Syntax

```simtalk
< json _Variable>.getOrCreateJSON(Name:string)
-> json
```

Parameter

The parameter Name of data type string designates the name of the name-value-pair.

Return Value

The return value has the data type json .

The return value is a reference to the empty JSON object.

The return value is a reference to the value contained in the JSON object.

Example

```simtalk
-- source code of Method1:
var JsonObj: json
var ColorInfo := JsonObj.getOrCreateJSON("ColorInfo") -- JSON-subobject named "ColorInfo" will be created and returned ColorInfo["color"] := "red" ColorInfo["NumberChangesColor"] += 1 Method2(JsonObj) -- source code of Method2:
param JsonObj: json
var ColorInfo := JsonObj.getOrCreateJSON("ColorInfo") -- existing JSON-subobject will be returned ColorInfo["color"] := "green" ColorInfo["NumberChangesColor"] += 1 -- the value will be increased to 2
```

parse [SimTalk]

Parses the text passed by the parameter Data and returns the parsed value.

Remarks

The text usually starts with an opening curly brace { and specifies a complex JSON object, although the value can also be a single value of data type integer , real , boolean , or an array .

Type

Method

Syntax

```simtalk
< json >.parse(Data:string)
-> any
```

If the value is a JSON object, this value will also be assigned to the variable &lt;json&gt;, otherwise the variable &lt;json&gt; will be set to an empty JSON object.

Parameter

The parameter Data of data type string designates the text to be parsed.

Return Value

The return value has the data type any .

Examples

```simtalk
var j: json
var value1 := j.parse("{ \"count\": 123 }") // value1: json = { "count": 123 } // j     : json = { "count": 123 }
var value2 := j.parse("123")
// value2: integer = 123 // j     : json = {}
var arr := j.parse("[3.141, 100, true]")
```

// arr   : any[] = [3.141, 100, true] // j     : json = {}

###### parse [SimTalk]

**See also**

asString [SimTalk] - JSON

readFile [SimTalk] - JSON

Imports the JSON source code from the specified text file into the specified variable of data type JSON.

Type

Method

Syntax

```simtalk
< json _Variable>.readFile(FileName:string) → void
```

Parameters

The parameter FileName of data type string designates the path to and the name of the text file containing the source code you want to use.

Return Value

The return value is void .

Example

js.readFile("D:\json.txt")

```simtalk
var js:json
print js
```

SimTalk

writeFile [SimTalk] - JSON

**unshareAndDelete [SimTalk]**

###### unshareAndDelete [SimTalk]

Unshares the reference to the JSON object designated by &lt;json&gt; and assigns an empty JSON object to the local variable or to the user-defined attribute .

Type

Method

Syntax

< json >.unshareAndDelete

**Example**

```simtalk
var person1, person2 : json
person2 := person1          -- person1 and person2 reference the same JSON object person2["Name"] := "Alice"  -- also changes person1["Name"] person2.unshareAndDelete    -- person2 is an empty JSON object person2["Name"] := "Bob"    -- only changes person2["Bob"]
```

writeFile [SimTalk] - JSON

Writes the JSON source code from the specified JSON variable to the specified text file.

Type

Method

Syntax

```simtalk
< json _Variable>.writeFile(FileName:string) → void
```

Parameters

The parameter FileName of data type string designates the path to and the name of the text file to which the source code is going to be written.

Return Value

The return value is void .

**Example**

```simtalk
-- our text file JSON.txt contains this JSON source code: { "first_name": "John", "last_name": "Doe", "age": 46, "address": { "street_address": "42 42nd Street", "city": "New York", "state": "NY", "postal_code": "10021-3100" } }
```

**SimTalk**

readFile [SimTalk] - JSON

**Length [SimTalk] - data type**

#### Length [SimTalk] - data type

A local variable of data type length has a maximum range of values between -8.9*10 307  ≤ length ≤ 8.9*10 307 , which is displayed like this -8.9e307 ≤ real ≤ 8.9e307.

**Remarks**

When assigning it to a variable or an attribute, Plant Simulation interprets the value as meters (m).

When outputting the value to the Debugger or the Console , Plant Simulation converts the value to the unit you selected under File &gt; Model Settings/Preferences &gt; Units &gt; Length .

**Note**

In SimTalk 2.0 you can specify the length units m , mm , km , cm , yd , ft , and in .

Type in the unit directly after the values, without a separating blank space, for example 10m or 10.2yd .

You can type in the unit for fl oating point values and for integer values .

The data types time , length , weight , speed and acceleration are not compatible! You can, for example, only assign a value of data type length , real or integer to a variable of data type length .

**Example**

```simtalk
var len := 1.0ft
var s : speed := 10.5m / 1:30
var x : length := 3m
```

**See also**

**isLength [SimTalk]**

#### List [SimTalk] - data type

A local variable of data type list shares its built-in properties with the object DataList .

Remarks

Note the difference between the object DataList , which you insert into your model, and the data type list . You can create user-defined attributes and local/global variables of data type list that are part of another object and thus are not an object of their own and do not have their own icon.

For this reason variables and attributes of data type list do not recognize all of the attributes, read-only attributes, and methods of the object DataList , such as Location or existsIcon . All other methods, especially for read and write access, apply to both the DataList and to variables and attributes of data type list .

**Note**

Before accessing the data type list for the first time, you have to create the local variable with the method create or you have to assign a value to the variable.

**Example**

```simtalk
var l: list[string]
l.create
l.insert(1,"Hello")
```

**See also**

Instantiating Local Lists and Tables

isListRange [SimTalk]

isList [SimTalk]

#### Method [SimTalk] - data type

A local variable of data type method is a user-defined attribute of data type method , also called an attribute method in most cases.

**Remarks**

This user-defined attribute is a part of the object, i.e., it moves with the object, when you insert it into another Frame or model or when you move it. Compare the topics Entrance control and self for details about using it.

The object Method and user-defined attributes of data type method have their own random number stream which you can assign with the attribute RandomSeed .

As you are used to from the material flow objects, Plant Simulation automatically assigns the random number stream when you insert an object, so that each object has its own random number stream.

Method execution for user-defined attributes of data type method , which are deleted while they are being executed, is terminated immediately, it will not be continued. Compare the following examples:

- Suppose that a MU has a user-defined attribute of data type method which was suspended via a waituntil-instruction . Then, the MU is deleted in the Drain , which naturally also deletes its user-defined attributes . Thereupon the Method is deleted from the list of suspended methods and method execution is terminated, i.e., the instructions after the waituntil-instruction will not be executed.

If the attribute method was called from another Method , execution of this Method will be continued.

If the attribute method had a return value, the value, which the implicitly existing local variable result had at this point in time, will be returned to the calling Method .

- Suppose that a MU has a user-defined attribute of data type method which is called by the Entrance Control of a Station . The attribute method in turn calls a Method that is inserted in the Frame . This Method deletes the MU with the statement Station.Cont.delete .

The execution of the attribute method and of the Method called by it are terminated immediately. The return value of the attribute method (or VOID if no return value was declared) will be returned to the Entrance Control whose execution will be continued.

User-defined attributes of data type method and objects of type Method behave the same when you extend the path. For the instruction Station.MyMethAttr.executeIn(60) Plant Simulation calls the user-defined attribute named MyMethAttr and not the method executeIn(60) .

If you want to prevent the user-defined attribute from being executed, you have to use the reference operator &amp; , Station.&amp;MyMethAttr.executeIn(60) for our example above.

See also

RandomSeed [SimTalk] - Method/User-defined Attribute

**User-defined Attributes [general description]**

#### Object [SimTalk] - data type

A local variable of data type object points to an object in your simulation model or is void .

Remarks

You can save any graphically represented object with the data type object . This variable can be a local variable, a formal parameter, a global variable and values in tables.

You can assign both objects and strings to the variables of data type object mentioned above.

If you assign an object, Plant Simulation creates an Object Reference , regardless if you specify the object with a relative or an absolute path .

Specify the object with a relative path to immediately resolve the relative path within the context of the current Method and create an object reference to the computed object.

Let's suppose that the method .Models.Model.Method contains the following method call:

SubFrame.methodU(Station)

Plant Simulation resolves the relative path Station to an object reference to .Models.Model.Station and passes this object reference to the method within the SubFrame . If the path cannot be resolved to an object, Plant Simulation opens the Debugger .

If a string is passed to a variable, the string is assigned as a path to the variable. Regardless if this path is relative or absolute, Plant Simulation does not resolve it at this point in time. Instead, the path is resolved each and every time when the variable is read.

Let's suppose that the method .Models.Model.Method contains the following method call:

SubFrame.methodU("Station")

Plant Simulation passes the relative path Station to the method within the SubFrame . At this point in time such an object neither has to exist within the context of the calling method, nor within the context of the called method as the path is not resolved yet.

Let's suppose that we inserted an object of type Station into the SubFrame and that this object has the name Station1 .

Let's also suppose that the source code of methodU in the SubFrame looks like this:

```simtalk
param o: object
Station1.Name := "Station"
o.name := "Station1"
o.name := "Test"  // ERROR!
```

Each time the local variable named o is accessed, the relative path will be resolved, in fact it will be resolved within the context of this method, meaning that path resolution starts in the SubFrame . This way it points to .Models.Model.SubFrame.Station , which now exists. This Station is then renamed to Station1 so that the path Station cannot be resolved in the next line of code and Plant Simulation thus opens the Debugger .

You can assign values of data type object to variables of data type string or to attributes of data type string . If the value contains an object reference , the absolute path will be assigned with a leading asterisk ( * ). If the value contains a relative or an absolute path, this path is assigned.

```simtalk
var o1: object := "Station"
var o2: object := ".Models.Model.Station"
var o3: object := .Models.Model.Station
var s1: string := o1  -- "Station"
var s2: string := o2  -- ".Models.Model.Station"
var s3: string := o3  -- "*.Models.Model.Station"
```

See also

isObject [SimTalk]

The Absolute Path

The Relative Path

Object Reference

#### Queue [SimTalk] - data type

A local variable of data type queue shares some of the built-in properties of the object DataQueue .

**Remarks**

Note the difference between the object DataQueue , which you insert into your model, and the data type queue . You can create user-defined attributes and local/global variables of data type queue that are part of another object and thus are not an object of their own and do not have their own icon.

For this reason variables and attributes of data type queue do not recognize all of the attributes, read-only attributes, and methods of the object DataQueue , such as Location or existsIcon . All other methods, especially for read and write access, apply to both the DataQueue and to variables and attributes of data type queue .

**Note**

Before accessing the data type queue for the first time, you have to create the local variable with the method create or you have to assign a value to the variable.

**Example**

```simtalk
var q: queue[string]
```

q.create q.push("Hello")

**See also**

Instantiating Local Lists and Tables

isQueue [SimTalk]

#### Real [SimTalk] - data type

A local variable of data type real contains floating point numbers. The value range is between -1.7976931348623158e+308 and 1.7976931348623158e+308.

**Remarks**

Real numbers have a precision of 16 places (meaning digits, i.e., digits before and after the decimal point). When displaying the numbers, the computer rounds to 15 places.

As floating point numbers can only save a fixed number of places, rounding errors can, in principle, always occur when computing with floating point numbers. For this reason you should, as a rule, not use the equal operator = when comparing floating point numbers as it checks for exact equivalence. Use the about-equal-operator ~= instead.

You can also type in floating point numbers with mantissa and exponent in this notation: 1.0e-3 this corresponds to 0.001 .

Internally Plant Simulation always saves the numbers with mantissa and exponent. The accuracy of the mantissa is limited to 16 decimal digits. This is determined by the representation of floating point numbers in the CPU, which is defined by the IEEE Standard for Floating-Point Arithmetic (IEEE 754).

The CPU can only process binary data, i.e., zeros and ones. For this reason floating point numbers are represented according to the IEEE-754 standard in the binary numeral system. Consequently, the mantissa actually does not contain 16 decimal digits but 53 binary numbers. Many numbers, which can be represented within the decimal system with a finite number of digits, cannot be represented with a finite number of digits in the binary numeral system.

**Examples**

- The decimal number 1.125 can be represented precise as 1 + 0/2 + 0/4 + 1/8. This corresponds to the binary number 1. 00 1.
- The decimal number 1.1 cannot be represented precise with a finite number of places. Within the binary numeral system this would be 1 + 0/2 + 0/4 + 0/8 + 1/16 + 1/32 + 0/64 + 0/128 + 1/256 + 1/512 + 0/1024 + 0/2048 + 1/4096 + 1/8192 + …

This corresponds to the binary number 1. 000 11 00 11 00 11…

If you type a number with decimal point and digits after the decimal point into the Method Editor , the computer converts this number to a floating point number according to the IEEE-754 standard when interpreting the source code so that the CPU can process it. The number is thus converted into a binary number with a fixed number of places. If binary places are cut off during this process, this number minimally differs from the decimal number that you specified.

You can view this effect when you run the following SimTalk instruction:

```simtalk
var x: real := 1.1 - 1
```

You can then see in the Method-Debugger that x has the value 0.1000000000000001 .

<!-- image -->

<!-- image -->

#### Speed [SimTalk] - data type

A local variable of data type speed has a maximum range of values between -8.9*10307 ≤ speed ≤ 8.9*10 307  which is displayed like this -8.9e307 ≤ real ≤ 8.9e 307 .

**Remarks**

When assigning it to a variable or an attribute, Plant Simulation interprets the value as meters per second (m/s). When outputting it, Plant Simulation converts the value to the unit you selected under File &gt; Model Settings/Preferences &gt; Units &gt; Speed .

Note In SimTalk 2.0 you can specify the speed units mps , fps , kmh , and mph . Type in the unit directly after the number, without a separating blank space, for example 100kmh or 100.5kmh . var len := 1.0ft var s : speed := 10.5m / 1:30 var x : length := 3m

**Note**

In SimTalk 2.0 you can type in the unit s for seconds . Type in the unit s directly after the number, without a separating blank space. Specifying the unit sometimes is necessary to make sure that the computed expression has the correct data type.

```simtalk
var x : length := 10m
var s : speed := x / 2s   // Beware: x/2 would have the wrong unit, m instead of m/s
```

The data types time , length , weight , speed and acceleration are not compatible! You can, for example, only assign a value of data type length , real , or integer to a variable of data type length .

**See also**

**isSpeed [SimTalk]**

**Stack [SimTalk] - data type**

#### Stack [SimTalk] - data type

A local variable of data type stack shares some of the built-in properties of the object DataStack .

**Remarks**

Note the difference between the object DataStack , which you insert into your model, and the data type stack . You can create user-defined attributes and local/global variables of data type stack that are part of another object and thus are not an object of their own and do not have their own icon.

For this reason variables and attributes of data type stack do not recognize all of the attributes, read-only attributes, and methods of the object DataStack , such as Location or existsIcon . All other methods, especially for read and write access, apply to both the DataStack and to variables and attributes of data type stack .

**Note**

Before accessing the data type list for the first time, you have to create the local variable with the method create or you have to assign a value to the variable.

**Example**

```simtalk
var s: stack[string]
s.create
s.push("bottles") -- adds the cell containing the string bottles as the -- first cell of the variable of data type stack
```

**See also**

**Instantiating Local Lists and Tables**

isStack [SimTalk]

#### String [SimTalk] - data type

A local variable of data type string can consist of any number of characters, meaning upper or lower case letters, numbers, special characters, etc. enclosed in quotation marks "" .

**Remarks**

Plant Simulation shows a value of data type string in the source code in this color .

<!-- image -->

**See also**

Functions for Editing Variables of Data Type String

Compare strings with relational operators

Colors for Syntax Highlighting

isString [SimTalk]

String [SimTalk] - value

**Table [SimTalk] - data type**

#### Table [SimTalk] - data type

A local variable of data type table shares some of the built-in properties of the object DataTable .

**Remarks**

Note the difference between the object DataTable that you can insert into models and the data type table . You can create user-defined attributes and local/global variables of data type table that are part of another object and thus are not an object of their own and do not have their own icon.

For this reason variables and attributes of data type table do not recognize all of the attributes, read-only attributes, and methods of the object DataTable , for example Location or existsIcon . All other methods, especially for read and write access apply to both the object DataTable and to variables and attributes of data type table .

**Note**

Before accessing the data type table for the first time, you have to create the local variable with the method create or you have to assign a value to the variable.

**Examples**

```simtalk
var OrderList: table[string,real]
OrderList.create
OrderList[1,1] := "Cans"
OrderList[2,1] := 3000.0
var myWaitingTimesTable: table
MyAssembly.statWaitingTimeTable(myWaitingTimesTable)
```

**See also**

##### Instantiating Local Lists and Tables

**isTable [SimTalk]**

#### Time [SimTalk] - data type

A local variable of data type time has a maximum range of values between -8.9*10 307  ≤ time ≤ 8.9*10 307 which is displayed like this -8.9e307 ≤ real ≤ 8.9e307.

**Remarks**

When assigning it to a variable or an attribute, the value is always interpreted in seconds (sec). Plant Simulation converts the output to a compound format with hours (hh) minutes (mm) and seconds (ss.ss) separated by colons: hh:mm:ss.ss

The data types time , length , weight , speed , and acceleration are not compatible! You can, for example, only assign a value of data type length , real , or integer to a variable of data type length .

See also

isTime [SimTalk]

#### Weight [SimTalk] - data type

A local variable of data type weight has a maximum range of values between -8.9*10 307  ≤ weight ≤ 8.9*10 307  which is displayed like this -8.9e307 ≤ real ≤ 8.9e307.

Remarks

When assigning it to a variable or an attribute, Plant Simulation interprets the value as kilograms (kg). When outputting it, Plant Simulation converts the value to the unit you selected under File &gt; Model Settings/Preferences &gt; Units &gt; Mass .

The data types time , length , weight , speed , and acceleration are not compatible! You can, for example, only assign a value of data type length , real , or integer to a variable of data type length .

See also

isWeight [SimTalk]

#### Instantiating Local Lists and Tables

Instantiating Local Lists and Tables

A local variable of data type list , queue , stack , or table and lists within lists and tables within tables does not contain the data itself, but a reference to the respective data structure.

When the variables are entered into a Method , they are void , i.e., they do not contain a reference to a data structure yet. You have to create the variable, before you can access the data.

Lists and tables provide the methods create and createNestedList for instantiating them.

##### create [SimTalk] - local list

Creates an empty data structure without contents in the local variable designated by &lt;Local-variable&gt;.

Remarks

The method create applies to local variables of data type list , queue , stack , and table .

Type

Method

Syntax

&lt;Local-variable&gt;.create([NumberOfRows:integer])

**Parameter**

The optional parameter NumberOfRows of data type integer designates the number of rows in the list or table.

**Example**

```simtalk
var orderlist: table[string,real]
orderlist.create
orderlist[1,1] := "cans"
orderlist[2,1] := 3000.0 orderlist.forget    // destroys the table
orderlist.create(4) // recreates the table with 4 rows
```

**See also**

**Data Types in Local Variables**

##### createNestedList [SimTalk] - local variable

createNestedList [SimTalk] - local variable

Creates a new sublist or subtable in the local variable designated by &lt;local-list&gt; or by &lt;local-table&gt;.

Remarks

The local variable has to be of data type list , queue , stack , or table . The data type of the column of this list or table has to be of data type list, stack, queue , or table as well.

Type

Method

Syntax

```simtalk
<Local-list>.createNestedList(Column:integer, Row:integer[, Name:string]) → list <Local-table>.createNestedList(Column:integer, Row:integer[, Name:string]) → list
```

**Parameters**

- The parameter Column of data type integer designates the column of the cell.
- The parameter Row of data type integer designates the row of the cell.
- The optional parameter Name of data type string designates the name of the sublist or subtable to be created.

**Note**

This method also applies to sublists and subtables!

Return Value

The return value has the data type list .

Is the nested list ( DataList , DataQueue , DataStack , or DataTable ) that was created.

**Examples**

```simtalk
var t: table[table] t.create                // creates a table
t.createNestedList(1,1) // creates a subtable t[1,1][2,3] := "Hello world" // writes Hello world into the nested table
```

The code inserts a subtable into cell 1 of the our table. It then inserts Hello world into the cell at the position 2,3.

<!-- image -->

```simtalk
var subtable: table
MyDataTable.createNestedList(2,3) // creates a subtable
subtable := MyDataTable[2,3]
subtable.createNestedList(1,1)    // creates a subtable within a subtable subtable[1,1][4,4] := "Hello world"
```

**See also**

setCommonFormat [SimTalk]

Activating and Deactivating Common Format

createNestedList [SimTalk] - DataQueue

createNestedList [SimTalk] - DataList

createNestedList [SimTalk] - DataTable

#### Converting Data Types

You cannot always combine variables and constants of different data types. They may have to be converted before an operation can be executed on them.

Automatically Converting Data Types

Plant Simulation automatically converts numeric values. You have to explicitly start all other type conversions.

Plant Simulation automatically converts the data type integer to real and vice versa. When you assign a real value to an integer variable, the digits after the decimal point will be lost. When parameters are passed, Plant Simulation automatically converts the data type real to integer and vice versa. The same is true for the data types dateTime and date . Here, Plant Simulation deletes the time part.

During calculations Plant Simulation treats the units of the physical data types length , weight , speed , acceleration and time as real numbers. If a calculation results in another physical data type, Plant Simulation assigns the result the corresponding data type. The quotient of length and time is assigned the data type speed . If the result cannot be assigned a physical data type, Plant Simulation uses real instead.

You can only assign a value with the correct unit or a value without a unit ( real or integer ) to a local variable of physical data types ( length , weight , speed , acceleration , time ). In all other cases the assignment throws an error to point out a potential problem.

```simtalk
Note Automatic conversion from real to integer will truncate decimal places, similar to the TRUNC function in Excel. Currently, we provide two workaround for this: Use the round function:
var realVal := pi
var intVal : integer := round(realVal) Add the value 0.5:
var realVal := pi
var intVal : integer := realVal + 0.5
```

Manually Converting Data Types

The remaining data types you have to convert explicitly by calling the conversion function listed below:

| Conversion method                  | Data type of the return value   |
|------------------------------------|---------------------------------|
| bool_to_num [SimTalk] (boolean)    | real [SimTalk]                  |
| num_to_bool [SimTalk] (integer)    | boolean [SimTalk]               |
| str_to_bool [SimTalk] (string)     | boolean [SimTalk]               |
| str_to_date [SimTalk] (string)     | time [SimTalk]                  |
| str_to_dateTime [SimTalk] (string) | dateTime [SimTalk]              |
| str_to_length [SimTalk] (string)   | length [SimTalk]                |
| str_to_num [SimTalk] (string)      | real [SimTalk]                  |
| str_to_obj [SimTalk] (string)      | object [SimTalk]                |
| str_to_speed [SimTalk] (string)    | speed [SimTalk]                 |
| str_to_time [SimTalk] (string)     | time [SimTalk]                  |
| str_to_weight [SimTalk] (string)   | weight [SimTalk]                |
| to_str [SimTalk] (any, …)          | string [SimTalk]                |

#### Operators and Expressions

