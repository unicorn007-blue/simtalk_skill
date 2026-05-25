### Constant Values

Constants contain values that do not change.

You can assign constant values of the following data types:

| Boolean [SimTalk] - value   | Real [SimTalk] - value   |
|-----------------------------|--------------------------|
| Integer [SimTalk] - value   | String [SimTalk] - value |
| pi [SimTalk] - value        |                          |

See also

Simple Values

#### Boolean [SimTalk] - value

You can assign true or false to a constant value of data type boolean .

**Example**

```simtalk
order_done := true
```

**See also**

Boolean [SimTalk] - data type

#### Integer [SimTalk] - value

You can assign numbers from 0 to 9 with an optional leading sign, namely plus ( + ) or minus ( -), to a constant value of data type integer .

**Remarks**

This is also called integer constant .

**Note**

The range for constant integer values is -9223372036854775807 to 9223372036854775807.

**Example**

```simtalk
order_number := -112304
```

**See also**

Integer [SimTalk] - data type , data type

#### pi [SimTalk] - value

The constant value pi is the ratio of the circumference of a circle to its diameter. It has the data type real .

**Example**

print pi // 3.141592653589793

#### Real [SimTalk] - value

You can assign one or several digits after the decimal point to a constant value of data type real .

**Remarks**

This is also called a real constant .

In exponential notation the constant value consists of a mantissa followed by the letter E and an exponent. You can, for example, also specify the number 100 as 1.0e2 (1.0 times the second power of 10).

**Note**

The value range of the exponent is limited to the interval [307, -307].

**Note**

You recognize a constant value of data type real by the decimal point . If it is missing, the constant value has the data type integer with a limited value range.

The data types time , date , and dateTime do not support constant values. Instead, use real or integer constant values, or the data type conversion functions str\_to\_time , str\_to\_date , and str\_to\_dateTime .

**Example**

```simtalk
Conveyor.Speed := 2.5
Avogadro := 6.5e23
epsilon := 1.0e-6 // 0.000001
```

**See also**

Real [SimTalk] - data type

#### String [SimTalk] - value

You can assign a string consisting of letters, numbers and special characters within quotation marks "" to a constant value of data type string .

Remarks

When working with constants of data type string , i.e., a sequence of characters, keep this in mind:

- You can assign a string consisting of letters, numbers and special characters within quotation marks ( "" ) to a constant value of data type string . This is also called a string constant .
- To use quotation marks (quotes) within the string, you have to protect the quotation marks by typing in a backslash \ in front of them. Otherwise Plant Simulation considers the quotation mark to be the end of the constant value.
- To specify a line break within the string, terminate the line of text at this position with a backslash \ and continue the string constant in the next line.
- Protect a backslash within a string by typing a second backslash \\ . This is necessary if the string literal ends with a backslash.

priority: = "Urgent"

```simtalk
print "It is \"very\" urgent." -- outputs It is "very" urgent.
var address : string
address := "Frank Jones\ Halford Lane 9\ Cedar Rapids, IA 52409"
print address -- outputs Frank Jones Halford Lane 9 Cedar Rapids, IA 52409
a := "It is \"very\" urgent." -- the backslash protects the quotation
Path := "C:\Temp"             -- no need to protect the backslash here
Path := "C:\\" + FolderName   -- protected backslash at the end of the
marks string
```

- A constant value of data type string can contain 1024 characters at most. You can put together strings of arbitrary length by linking together individual strings with the + operator though.

```simtalk
var s : string
s := "This is a long string," + " formed by linking together several" + " sub-strings."
print s -- outputs This is a long string, formed by linking together several substrings.
```

See also

**String [SimTalk] - data type**

Protect quotation marks in Why Use SimTalk 2.0?

