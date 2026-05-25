### Variables

#### Variables [SimTalk]

Local variables , global variables , and parameters store values over time and allow to access them at a later point in time.

You can change the value of a variable at any time according to your modeling needs.

See also

Local Variables

Global Variables

Parameters [SimTalk]

#### Local Variables

If you want to reuse the result of a calculation again at a later point in time, you can save that result to a local variable . Use a local variable if you do not need the value again after the method call.

The name of a local variable is only known in the Method in which you declare it. Other Methods cannot access this local variable . For each Method call Plant Simulation creates a new set of local variables . If a Method calls itself, for example, Plant Simulation creates a new set of local variables and the Method can only access this new set. Only when the call is finished, the previous local variables are available again with the previous values.

You have to declare a local variable within the source code before you can use it.

Before you assign a value to the local variable , it has an initial value .

- It is 0 for all numerical data types.
- It is false for the data type boolean .
- It is an empty string "" for the data type string .
- It is void for the data types object and list/table .
- It is 1900/01/01 for the data type date and 1900/01/01 00:00:00.0000 for the data type dateTime For models which you initially created in Plant Simulation version 13 or older, the initial value is a different one and depends on the version.

If you need to access the saved value later on, use the object Variable instead, compare global variables .

- .

#### Data Types in Local Variables

Use any of the data types provided in SimTalk in your local variables.

You can use these data types in a local variable: Integer , Real , Length , Speed , Acceleration , Weight , Time , Date , DateTime , Json , Boolean , String , Object , Table , List , Stack , Queue , and Any .

For the data types stack , queue , list and table you have to type the data type or data types of the columns in between brackets, [data type]. These local variables slightly differ from the objects, which you insert into a Frame . As opposed to the objects, they only provide built-in methods for Instantiation , State , Access , and Order .

| Data type                   | Shares built-in properties of the object   |
|-----------------------------|--------------------------------------------|
| List [SimTalk] - data type  | DataList                                   |
| Queue [SimTalk] - data type | Properties of the DataQueue                |
| Stack [SimTalk] - data type | Properties of the DataStack                |
| Table [SimTalk] - data type | DataTable [object]                         |

**Note**

Before first accessing these data types, you have to create the local variable with the method create or you have to assign a value to the variable.

**Example**

```simtalk
var l: list[string]
l.create
l.insert(1,"Hello")
```

Plant Simulation automatically initializes all local variables. The initial value depends on the data type:

| Data Type                            | Initial Value   |
|--------------------------------------|-----------------|
| integer , real , length , …[SimTalk] | 0               |
| boolean [SimTalk]                    | false           |
| string [SimTalk]                     | ""              |
| object [SimTalk]                     | void            |
| time [SimTalk]                       | 0:00:00         |

**Compare**

**Data Types [SimTalk]**

#### Declare Local Variables in the Source Code

You can declare a local variable anywhere within the source code.

Start to declare your variable with the keyword var , followed by one or several identifiers for the local variables you are defining. After that you can type a colon and define the data type of the local variable.

**Example**

```simtalk
var x, y: integer
```

You can also assign a value to the local variable when you declare it.

A local variable , which you declare like this, is visible from the line, in which you defined it, to the end of the source code.

A local variable is initialized with an initial value when calling the Method . Compare Data Types in Local Variables .

**Example**

```simtalk
var a: length := Track1.Length
var b: Length := Track2.Length
var c: Length := sqrt(a*a + b*b)
print c
```

If you assign a value to the local variable while you declare it, declaring the data type is optional. The data type of the variable is then determined by the assigned value.

In the example the local variables named a and b will take the data type length . The variable c will take the data type real , as the function sqrt returns a value of data type real .

**Example**

```simtalk
var a := Track1.length
var b := Track2.length
var c := sqrt(a*a + b*b)
print c
```

Plant Simulation sets local variables to the initial value when calling the Methods . If you declare a local variable within a loop , the initial value will not be set anew with each loop pass, but the local variable keeps its previous value. If you assign a value to the local variable within the declaration, Plant Simulation executes the assignment anew with each loop pass.

**Example**

```simtalk
// the loop outputs: 0 0 --> 1 0 --> 2 0
for var i := 1 to 3
	var x: integer
	var y: integer := 0
	print x, " ", y
	x += 1
	y += 1
next
```

A local variable , which is declared within an if-statement , is also visible after the if-statement . This also applies if the instructions within the if-statement are not executed. In this case the local variable has the initial value, even if the variable declaration contains an assignment.

**Example**

```simtalk
if 1 = 2
	var x: integer := 1
end
print x  // outputs 0
```

This also applies to loops : If the loop was never executed because the loop condition was not fulfilled the first time already, you can still access the local variable , which you declared within the loop, after the loop. In that case the local variable contains the initial value.

**Example**

```simtalk
for var y := 1 to DataTable.yDim
	var i : integer i := DataTable[1,y]
next
print i    // outputs 0 if the DataTable is empty
```

**Video on YouTube**

[https://youtu.be/MXDcx2yplxc?si=cICVJfstejBUiwXM&amp;t=62](https://youtu.be/MXDcx2yplxc?si=cICVJfstejBUiwXM&t=62)

#### Global Variables

A global variable , which contains a non-fixed value, can be accessed by any Method in the simulation model. Data stored in a global variable by a Method will still exist after the execution of that Method has finished.

Use global variables (or entries in lists) to keep data for extended periods of time during a simulation run.

Plant Simulation provides the object Variable as a global variable . Any Method can access the global variable by its name and an absolute or relative path pointing to it.

If you do not need to access the saved value later on, use a local variable instead.

**Example**

```simtalk
MyVariable := Transporter:1.CurrentSpeed  -- assign a new value to the global variable 'MyVariable'
print MyVariable                          -- read out the value and print it into the Console window print &MyVariable.DataType       -- print the data type of 'MyVariable'
var obj : object := &MyVariable  -- store a reference to 'MyVariable' in a local variable of data type object
```

