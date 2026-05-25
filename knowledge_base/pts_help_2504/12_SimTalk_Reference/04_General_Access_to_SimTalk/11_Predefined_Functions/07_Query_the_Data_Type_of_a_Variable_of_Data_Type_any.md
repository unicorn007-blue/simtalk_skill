#### Query the Data Type of a Variable of Data Type any

Query the Data Type of a Variable of Data Type Any

SimTalk provides the functions listed in the table of contents to the left for querying the data type of a variable of data type Any .

The function expects a parameter whose data type Plant Simulation compares.

See also

Any [SimTalk] - data type

Return Value

The return value has the data type boolean .

##### getSimTalkTypename [SimTalk]

Returns the name of the data type of an arbitrary value.

Type

Function

Syntax

```simtalk
getSimTalkTypename(Value:any) → string
```

Return Value

The return value for the data types table/stack/queue returns these strings:

| Data Type [SimTalk]   | Return Value [SimTalk]   |
|-----------------------|--------------------------|
| table [SimTalk]       | table [SimTalk]          |
| stack [SimTalk]       | stack [SimTalk]          |
| queue [SimTalk]       | queue [SimTalk]          |

For local variables of data type any , which were assigned a special object, for example a sensor, getSimTalkTypename returns sensor , lane , storage place , 3D object , or 3D animation depending on the type of the special object.

If the passed value has an Array data type, getSimTalkTypename returns an array .

Examples

print getSimTalkTypename(Conveyor.sensorID(1))  // sensor

print getSimTalkTypename(Conveyor.\_3D)          // 3D object

print getSimTalkTypename(TwoLaneTrack.A)        // lane

print getSimTalkTypename(Store[1,1])            // storage place

```simtalk
// compute the character count
param value: any -> integer
switch getSimTalkTypename(value)
case "integer"
	if value > 0
		return log10(value) + 1
	elseif value < 0
		return log10(-value) + 2
	else
```

**getSimTalkTypename [SimTalk]**

```simtalk
return 1;
end
case "string"
	return strlen(value)
case "object"
	return strlen(obj_to_str(value))
case "boolean"
	return when value then /*true*/4 else /*false*/5 else
	return -1  // error end
```

**See also**

Any [SimTalk] - data type Array [SimTalk] - data type

##### isAcceleration [SimTalk]

Returns if the designated argument is of data type Acceleration (true) or not (false).

Type

Function

Syntax

```simtalk
isAcceleration(Argument:any) → boolean
```

Parameter

The parameter Argument of data type any designates the argument to be checked.

Return Value

The return value has the data type boolean .

Example

```simtalk
param arg: any
if isAcceleration(arg)
	print "acceleration = , arg
end
```

See also

Any [SimTalk] - data type

Acceleration [SimTalk] - data type

**isArray [SimTalk]**

##### isArray [SimTalk]

Returns if the designated argument has an Array data type (true) or not (false).

Type

Function

Syntax

```simtalk
isArray(Argument:Value) → boolean
```

Parameter

The parameter Argument of data type any designates the argument to be checked.

Return Value

The return value has the data type boolean .

Example

```simtalk
var a:any[] := [[1,2,3], 42]
print "a = ", a
print "a[1] = ", a[1]
print "a[2] = ", a[2]
print isArray(a)    // true
print isArray(a[1]) // true
print isArray(a[2]) // false
var j:json
j["a"] := [1,2,3]
print isArray(j["a"])  -- returns true
```

See also

Array [SimTalk] - data type

##### isBoolean [SimTalk]

Returns if the designated argument is of data type Boolean (true) or not (false).

Type

Function

Syntax

```simtalk
isBoolean(Argument:any) → boolean
```

Parameter

The parameter Argument of data type any designates the argument to be checked.

Return Value

The return value has the data type boolean .

Example

```simtalk
param arg: any
if isBoolean(arg)
	print "Boolean = ", arg
end
```

See also

Any [SimTalk] - data type

Boolean [SimTalk] - data type

##### isDate [SimTalk]

isDate [SimTalk]

Returns if the designated argument is of data type Date (true) or not (false).

Type

Function

Syntax

```simtalk
isDate(Argument:any) → boolean
```

Parameter

The parameter Argument of data type any designates the argument to be checked.

Return Value

The return value has the data type boolean .

Example

```simtalk
param arg: any
if isDate(arg)
	print "Date = ", arg
end
```

See also

Any [SimTalk] - data type

Date [SimTalk] - data type

##### isDatetime [SimTalk]

Returns if the argument designated is of data type DateTime (true) or not (false).

Type

Function

Syntax

```simtalk
isDatetime(Argument:any) → boolean
```

Parameter

The parameter Argument of data type any designates the argument to be checked.

Return Value

The return value has the data type boolean .

Example

```simtalk
param arg: any
if isDatetime(arg)
	print "Datetime = ", arg
end
```

See also

Any [SimTalk] - data type

DateTime [SimTalk] - data type

##### isInteger [SimTalk]

isInteger [SimTalk]

Returns if the designated argument is of data type Integer (true) or not (false).

Type

Function

Syntax

```simtalk
isInteger(Argument:any) → boolean
```

Parameter

The parameter Argument of data type any designates the argument to be checked.

Return Value

The return value has the data type boolean .

Example

```simtalk
param arg: any
if isInteger(arg)
	print "Integer = ", arg
end
```

See also

Any [SimTalk] - data type

Integer [SimTalk] - data type

##### isJson [SimTalk]

Returns if the designated argument is of data type JSON (true) or not (false).

Type

Function

Syntax

```simtalk
isJson(Argument:any) → boolean
```

Parameter

The parameter Argument of data type any designates the argument to be checked.

Return Value

The return value has the data type boolean .

Example

```simtalk
param arg: any
if isJson(arg)
	print "json = ", arg
end
```

See also

Any [SimTalk] - data type

JSON [SimTalk] - data type

##### isLength [SimTalk]

isLength [SimTalk]

Returns if the designated argument is of data type Length (true) or not (false).

Type

Function

Syntax

```simtalk
isLength(Argument:any) → boolean
```

Parameter

The parameter Argument of data type any designates the argument to be checked.

Return Value

The return value has the data type boolean .

Example

```simtalk
param arg: any
if isLength(arg)
	print "Length = ", arg
end
```

See also

Any [SimTalk] - data type

Length [SimTalk] - data type

##### isList [SimTalk]

Returns if the designated argument is of data type List (true) or not (false).

**Syntax**

```simtalk
isList(Argument:any) → boolean
```

**Parameter**

The parameter Argument of data type any designates the argument to be checked.

Return Value

The return value has the data type boolean .

**Note**

The value VOID does not have a data type as local variables of data types object , table , and list can all take the value void. For this reason a local variable of data type any does not take a data type when you assign void to it.

**Example**

```simtalk
var a: any := void
print isObject(a)  // prints false
print a = void     // prints true
var b : any := 123
print b = void     // prints false
```

**See also**

Any [SimTalk] - data type

List [SimTalk] - data type

##### isListRange [SimTalk]

isListRange [SimTalk]

Returns if the designated argument is a list range (true) or not (false).

Type

Function

Syntax

```simtalk
isListRange(Argument:any) → boolean
```

Parameter

The parameter Argument of data type any designates the argument to be checked.

Return Value

The return value has the data type boolean .

Example

```simtalk
param arg: any
if isListRange(arg)           // something like {1,1}..{2,*} print "listRange = ", arg  // prints listRange = {1,1}..{2,*}
end
```

See also

Any [SimTalk] - data type

##### isObject [SimTalk]

Returns if the designated argument is of data type Object (true) or not (false).

Type

Function

Syntax

```simtalk
isObject(Argument:any) → boolean
```

Parameter

The parameter Argument of data type any designates the argument to be checked.

Return Value

The return value has the data type boolean .

**Note**

For isObject , isTable , and isList this applies: The value VOID does not have a data type as local variables of data types object , table , and list can all take the value void. For this reason a local variable of data type any does not take a data type when you assign void to it. If the function isObject is called with such a variable, the function returns the result false.

**Example**

```simtalk
var a: any := void
print isObject(a)  // prints false
print a = void     // prints true
var b : any := 123
print b = void     // prints false
```

See also

Any [SimTalk] - data type

Object [SimTalk] - data type

##### isQueue [SimTalk]

isQueue [SimTalk]

Returns if the designated argument is of data type Queue (true) or not (false).

Type

Function

Syntax

```simtalk
isQueue(Argument:any) → boolean
```

Parameter

The parameter Argument of data type any designates the argument to be checked.

Return Value

The return value has the data type boolean .

Example

```simtalk
param arg: any
if isQueue(arg)
	print "Queue = ", arg
end
```

See also

Any [SimTalk] - data type

Queue [SimTalk] - data type

##### isReal [SimTalk]

Returns if the designated argument is of data type Real (true) or not (false).

Type

Function

Syntax

```simtalk
isReal(Argument:any) → boolean
```

Parameter

The parameter Argument of data type any designates the argument to be checked.

Return Value

The return value has the data type boolean .

Example

```simtalk
param arg: any
if isReal(arg)
	print "Real = ", arg
end
```

See also

Any [SimTalk] - data type

Real [SimTalk] - data type

**isSpeed [SimTalk]**

##### isSpeed [SimTalk]

Returns if the designated argument is of data type Speed (true) or not (false).

Type

Function

Syntax

```simtalk
isSpeed(Argument:any) → boolean
```

Parameter

The parameter Argument of data type any designates the argument to be checked.

Return Value

The return value has the data type boolean .

Example

```simtalk
param arg: any
if isSpeed(arg)
	print "Speed = ", arg
end
```

See also

Any [SimTalk] - data type

Speed [SimTalk] - data type

##### isStack [SimTalk]

Returns if the designated argument is of data type Stack (true) or not (false).

Type

Function

Syntax

```simtalk
isStack(Argument:any) → boolean
```

Parameter

The parameter Argument of data type any designates the argument to be checked.

Return Value

The return value has the data type boolean .

Example

```simtalk
param arg: any
if isStack(arg)
	print "Stack = ", arg
end
```

See also

Any [SimTalk] - data type

Stack [SimTalk] - data type

##### isString [SimTalk]

isString [SimTalk]

Returns if the designated argument is of data type String (true) or not (false).

Type

Function

Syntax

```simtalk
isString(Argument:any) → boolean
```

Parameter

The parameter Argument of data type any designates the argument to be checked.

Return Value

The return value has the data type boolean .

Example

```simtalk
param arg: any
if isString(arg)
	print "String = ", arg
end
```

See also

Any [SimTalk] - data type

String [SimTalk] - data type

##### isTable [SimTalk]

Returns if the designated argument is of data type Table (true) or not (false).

Type

Function

Syntax

```simtalk
isTable(Argument:any) → boolean
```

Parameter

The parameter Argument of data type any designates the argument to be checked.

Return Value

The return value has the data type boolean .

**Note**

The value VOID does not have a data type as local variables of data types object , table , and list can all take the value void. For this reason a local variable of data type any does not take a data type when you assign void to it.

**Example**

```simtalk
param arg: any
print "Table = ", arg
```

if isTable(arg) end

See also

Any [SimTalk] - data type

Table [SimTalk] - data type

##### isTime [SimTalk]

isTime [SimTalk]

Returns if the designated argument is of data type Time (true) or not (false).

Type

Function

Syntax

```simtalk
isTime(Argument:any) → boolean
```

Parameter

The parameter Argument of data type any designates the argument to be checked.

Return Value

The return value has the data type boolean .

Example

```simtalk
param arg: any
if isTime(arg)
	print "Time = ", arg
end
```

See also

Any [SimTalk] - data type

Time [SimTalk] - data type

##### isWeight [SimTalk]

Returns if the designated argument is of data type Weight (true) or not (false).

Type

Function

Syntax

```simtalk
isWeight(Argument:any) → boolean
```

Parameter

The parameter Argument of data type any designates the argument to be checked.

Return Value

The return value has the data type boolean .

Example

```simtalk
param arg: any
if isWeight(arg)
	print "Weight = ", arg
end
```

See also

Any [SimTalk] - data type

Weight [SimTalk] - data type

