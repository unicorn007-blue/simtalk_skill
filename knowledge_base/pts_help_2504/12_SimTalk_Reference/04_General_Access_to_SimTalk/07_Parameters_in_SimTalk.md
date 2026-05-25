### Parameters in SimTalk

#### Parameters [SimTalk]

You can pass values to a Method when this Method is called during the simulation run. These values are called arguments .

You then have to declare the same number of parameters within the Method and these parameters have to have the same data types as the passed arguments. Exceptions are integer and real values. Plant Simulation automatically converts these.

In the example below x is the name of the parameter and 123 is the value of the argument .

```simtalk
param x: integer := 123
```

**Note**

When converting real values to integer values, Plant Simulation deletes numbers after the decimal point. This may lead to your Method to not behave as you would expect. In general, it is a good idea to avoid automatic type conversion.

**Parameters [SimTalk]**

See also Declare Parameters Declare Default Arguments param [SimTalk] Declare the Function Result of a Method Programming a Method Video on YouTube

[https://youtu.be/5t-wLNmKpbU?si=Q-8tGoRXDIy3nd2i&amp;t=34](https://youtu.be/5t-wLNmKpbU?si=Q-8tGoRXDIy3nd2i&t=34)

#### Declare Parameters

If the Method has to have parameters , you have to declare these parameters at the start of the source code.

Start the declaration with the keyword param , then enter the identifier , followed by a colon , and the data type . The identifier serves for accessing the parameter later on.

If several parameters in sequence have the same data type, you can list all identifiers of these parameters, separated by commas, followed by a colon and the data type.

If you want to declare several parameters with different data types, separate the declarations (name, colon, and data type) with commas.

```simtalk
param repeats: integer                           // single parameter of data type integer param minimum, maximum: real                     // two parameters of data type real
param rpm: real, tool: string                    // two parameters with different data types
param workpiece: string, Islength, shorten: real // three parameters with different data types
```

In this Method the parameters can be used like local variables . The initial value is set by the caller. This way the Method can react to different values.

Type the keyword byref in front of the parameter to not pass the value, but a reference to this variable. Changes of the parameter also affect the caller of the Method .

For the data types stack , queue , list , and table you just have to enter the data type, additional parameters are not required.

```simtalk
param order: list                                 // DataList of any type param orders, deliveries: queue                   // two DataQueues of any type
param cost: table, VAT: real, complaints: stack   // mixed declaration DataTable and DataStack
```

**Declare Optional Parameters**

Declare optional parameters as follows:

```simtalk
param maxValue:real := 1.0 -> real                // optional parameter
return z_uniform(0,maxValue)
```

**Declare the Function Result**

If a Method does not need any parameters, you just have to declare the data type of the result of the Method .

```simtalk
-> boolean // no parameters // or with parameters param v1,v2: integer, name: string -> boolean
```

See also

Declare Default Arguments

Declare the Function Result of a Method

Video on YouTube

[https://youtu.be/5t-wLNmKpbU?si=Q-8tGoRXDIy3nd2i&amp;t=34](https://youtu.be/5t-wLNmKpbU?si=Q-8tGoRXDIy3nd2i&t=34)

#### Declare Default Arguments

You can assign default arguments , also called optional arguments , or optional parameters in a Method in SimTalk 2.0 .

If the Method is then called without the argument, the associated parameter will be set to the default value, which is defined in the Method .

```simtalk
param x: integer := 123
```

The Method can be called with or without argument. If the Method is called without argument, the parameter x has the value 123 in the example above.

You can also assign default arguments to some of the parameters only. If a parameter has a default argument, all following parameters also have to have a default argument .

```simtalk
param a: string, b, c: string := "",
d: boolean := true
```

The Method in the following example can be called with one to four arguments, but not without any argument at all, as no default argument was defined for the parameter A .

Possible calls are:

Method("A") Method("A", "B") Method("A", "B", "C")

Method("A", "B", "C", false)

Allowed Values for Default Arguments

- Default arguments only accept constant values , i.e., numbers, string constants, the boolean constants true and false , void , and pi .
- Parameters of data type object , table , list , stack , queue , and any can only have void as default argument.
- Parameters of data type date and dateTime cannot have a default argument at all.
- Parameters of data type array can have an empty array [] or an empty JSON object {} as default argument.
- Reference parameters , i.e., parameters declared by the keyword byref , cannot have a default argument.

See also Declare Parameters Colors for Syntax Highlighting Video on YouTube https://youtu.be/5t-wLNmKpbU?si=4oreA6Pt8xKQtFuP&amp;t=126

#### Declare the Function Result of a Method

Mathematical functions return a result . A Method may also return a result.

To make a Method work like a function, specify -&gt; (a minus sign and a greater-than sign) followed by the data type. If the function requires parameters, specify them in front of the declaration of the return value -&gt; .

Note A function only returns one result.

Within the function you have to assign the result to the return value result . After the function has been executed, Plant Simulation returns the contents of this variable to the caller.

Compare these examples:

- A function without a parameter, calculating a real value, looks like this:
- A function with a parameter, returning a string value, looks like this:
- A function with several parameters, returning a table , looks like this:

```simtalk
-> real
param CustomerNo:integer -> string
param orders,deliveries: list, delivery_date: time -> table
```

**Note**

Instead of using result , you can also terminate the Method by using return , compare Exiting Methods Using Return .

The data types stack , queue , list , and table do not behave like described above. At the beginning, the local variable result is empty. Before accessing result you either assign a value to result or you have to use the method create .

**Example**

```simtalk
// returns a list that contains the value added tax amount // added to the prices of the price list that was passed
param pricelist: queue, VAT: real -> list[real]
```

