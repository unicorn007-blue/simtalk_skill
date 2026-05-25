### PythonModule

Use the PythonModule for utilizing Python code in a Plant Simulation model with full access to the Plant Simulation object model from within the Python code.

Icon

<!-- image -->

Requirements

Using Python requires an installation of CPython on your computer.

We recommend using the official Python distribution from https://www.python.org/ . You can also use a Python version that you installed via Anaconda.

If you are using multiple Python environments, specify the path to the Python DLL with the SimTalk function setPythonDLLPath :

```simtalk
setPythonDLLPath(dllpath:string)
```

You might, for example, type:

setPythonDLLPath("C:\Program Files\Python312\python312.dll")

Note

Plant Simulation supports Python versions 3.12 and 3.13.

**Limitations When Using Python Libraries**

When you use certain libraries, like Pandas or NumPy , you should always exit Plant Simulation instead of only closing your simulation model and opening a new model. When you close the model, the Python interpreter is uninitialized. If you then open a new model and try to use Pandas or NumPy again, this might cause a crash because these libraries do not support reinitialization of the Python interpreter.

Python libraries like MatPlotLib can open a window from within the Python code where a new Windows message pump is started. You must close such a window before you can interact with Plant Simulation again, otherwise Plant Simulation might crash.

To show a tooltip with information about the PythonModule , hover with the mouse over it.

<!-- image -->

Adding the PythonModule to Your Model

To add the PythonModule to the Class Library , click Manage Class Library &gt; Basic Objects &gt; Information Flow &gt; PythonModule on the Home ribbon tab.

<!-- image -->

<!-- image -->

<!-- image -->

After you add the PythonModule to the Class Library , you can insert a PythonModule object into your model Frame , open its dialog, type in your Python code, and execute it.

Once you add the PythonModule to your simulation model, it shows the global Python variables on the Tab Content .

<!-- image -->

Context Menu of the PythonModule

To show the context menu of the PythonModule , right-click in the Tab Content . Click Import before selecting a context menu command.

- Show White Space shows blank spaces between the words.
- Show Global Variables opens a dialog which shows the global Variables used in this PythonModule .

<!-- image -->

**See also**

What You Can Do With the PythonModule

setPythonDLLPath [SimTalk]

Video on YouTube

[https://youtu.be/2QJeW5r1AF4?si=S8Ee2D-4zyOevXZG](https://youtu.be/2QJeW5r1AF4?si=S8Ee2D-4zyOevXZG)

#### What You Can Do With the PythonModule

Python is a high-level programming language. It provides a vast amount of libraries and use cases for your use. There is not much that you cannot do with Python .

You might, for example, use the PythonModule to extract simulation results, do extensive data processing using any of the available Python libraries, and display the values in different ways by creating presentations containing various types of charts. You don't even have to know the programming language Python as such, as ChatGPT is really well-trained for Python .

To import the module into the Python interpreter, click Import in the top right corner of the PythonModule dialog.

<!-- image -->

You can also press F5 while the input cursor is located on the Tab Content :

**Note**

Plant Simulation automatically applies the source code, when you click Import or press F5 .

The PythonModule provides the built-in attribute PythonCode of data type string to get and set the Python source code from a SimTalk Method .

To run the Python code from SimTalk , we provide the methods call and callKw . The respective SimTalk syntax looks like this:

```simtalk
< Path >.call([functionName:string, ...])
-> any
< Path >.callKw([functionName:string, ..., KeyValuePairs:any[] ])
-> any
```

To execute a function, which you defined in the PythonModule , specify the name of the function as the first argument and then the arguments which you want to pass to Python .

Let's assume that you have the following Python code in your PythonModule :

```simtalk
def multiply(a, b):
return a*b
```

<!-- image -->

Click Apply in the dialog and then execute the function from SimTalk in a Method with print .

**Note**

Make sure that Prohibit Access to the Computer in the Model Settings is cleared.

As the error messages that Python shows are in English, Plant Simulation shows them in English as well. We do not localize Python error messages to other languages.

<!-- image -->

The result looks like this when we run the Method .

<!-- image -->

To call Python functions in SimTalk with keyword arguments, use the method callKw :

<!-- image -->

You have to pass keyword arguments using an array with pairs consisting of the keyword and the value.

The result looks like this when we run the Method .

<!-- image -->

With the Python code, which you type into the PythonModule , you can:

- Access the Model Frame from the Python Code
- Access Attributes and Methods from the Python Code
- Access DataTables from the Python Code
- Access Variables from the Python Code
- Call Global SimTalk Functions from the Python Code
- Execute External Python Code

You can also Display a PythonModule in the HtmlReport .

**Note**

Python code is not intended to replace SimTalk code . As SimTalk code also accesses compiled built-in functions, it generally is executed quite a bit faster than Python code .

As many university graduates are exposed to Python , writing Python code during their studies, the Python Module makes programming in Plant Simulation easier.

The presentation during the Plant Simulation User Meeting 2024 in München gives a good overview of the Python Module . You can view and download it here Demo .spp model to use Python code in Plant Simulation 2404 (siemens.com)

Video on YouTube

[https://youtu.be/2QJeW5r1AF4?si=S8Ee2D-4zyOevXZG](https://youtu.be/2QJeW5r1AF4?si=S8Ee2D-4zyOevXZG)

##### Dialog Box of the PythonModule

Dialog Box of the PythonModule

Double-click the icon of the PythonModule to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Import [button] - PythonModule

To import the code you wrote in the PythonModule into the Python interpreter and execute it, click this button.

<!-- image -->

To reload the module and delete all global variables , hold down Shift while clicking Import .

To copy an import statement for the module to the clipboard, hold down Shift and Ctrl while clicking the button.

SimTalk

import [SimTalk] - Python Tab Content Tab Content After you added the PythonModule to your simulation model, it shows the global Python variables on the Tab Content .

<!-- image -->

Type in the Python code that you want to execute in Plant Simulation on the Tab Content .

<!-- image -->

With the Python code, which you type into the PythonModule , you can:

- Access the Model Frame from the Python Code
- Access Attributes and Methods from the Python Code
- Access DataTables from the Python Code
- Access Variables from the Python Code
- Call Global SimTalk Functions from the Python Code
- Call a Function Written in a Another PythonModule
- Execute External Python Code

Click Import to import the Python code, which you type in on the Tab Content , into the Python interpreter.

**See also**

Import [button] - PythonModule

###### Access the Model Frame from the Python Code

To access Plant Simulation objects of your simulation model, use the global Python variables named basis , root , current , and self in your Python code.

The PythonModule shows them when you insert it into your simulation model.

<!-- image -->

**basis**

basis references the root of your Class Library .

As opposed to SimTalk , a path to an object in Python cannot start with a period ( . ).

Therefore, you need to start an absolute path in Python code with the Python variable basis , for example:

<!-- image -->

root

root designates the root of your Frame hierarchy , i.e. the Frame in which the EventController is located.

To access an object in the root Frame of your PythonModule , start the path with the Python variable root , for example:

```simtalk
print(root.EventController)
```

**Note**

As opposed to SimTalk , you do have to specify the path to an object in Python .

current

current designates the Frame into which you inserted your PythonModule .

To access an object in the Frame into which you inserted your PythonModule , start the path with the Python variable current , for example:

print(current.Station)

self

The global Python variable named self designates the PythonModule itself.

###### Access Attributes and Methods from the Python Code

To access attributes and methods of Plant Simulation objects from the Python code, you use the same syntax as you do in SimTalk .

Accessing Attributes of a Plant Simulation Object

To access an attribute of a Plant Simulation object, use the same syntax as you do in SimTalk .

The following code accesses the attribute ProcTime of a station:

print(current.Station.ProcTime) current.Station.ProcTime = 50

The result looks like this when we Import the PythonModule .

<!-- image -->

Accessing Methods of a Plant Simulation Object

To call a method of a Plant Simulation object, use the same syntax as you do in SimTalk .

If the Method accepts arguments - even if all arguments are optional - you must always use parentheses to call the method, for example:

current.MyStation.deleteObject print(current.Station.succ()) print(current.Station.succ(1))

The result looks like this when we Import the PythonModule .

<!-- image -->

Executing SimTalk Methods from Python

To execute a SimTalk method from your Python code, you have to use the method execute of the Method object:

current.MyMethod.execute()

If the Method accepts arguments, you pass them to the execute method:

current.MyMethod.execute('Test', 123)

If the Method returns a value, you will receive it in Python as the return value of the execute method call:

print(current.MyMethod.execute('Test', 123))

See also

execute [SimTalk] - Method

Access DataTables from the Python Code

To access cells in a DataTable , use the Python index access.

To access the cell in column 2 and row 3 you can, for example, type the following.

Example

```simtalk
print(root.DataTable[2,3])
```

To get the entire content of the DataTable , you can type:

```simtalk
print(root.DataTable[None]) # gets the entire content of the DataTable
```

<!-- image -->

If the DataTable has a unique column index, you will get a Python dictionary with the column index as the key.

Otherwise, you will get a Python list which contains Python lists which contain the row values.

You can also use Python slices to only get partial data from the DataTable .

<!-- image -->

###### Access Variables from the Python Code

To access the value of a Variable , use the attribute Value of the Variable .

**Example**

```simtalk
print(root.Variable.Value)
root.Variable.Value = 42
```

The result looks like this when we Import the PythonModule .

<!-- image -->

**See also**

Variable [object]

Value [SimTalk] - Variable

Call Global SimTalk Functions from the Python Code

To call a global SimTalk function from the Python code, you first have to import the PlantSimulation module .

For this module you can then call the predefined functions which Plant Simulation provides.

<!-- image -->

**Example**

```simtalk
import PlantSimulation as ps x = ps.existsObject(".Models.Model.EventController")
print(x)
```

The result looks like this when we Import the PythonModule .

<!-- image -->

See also

Predefined Functions

###### Call a Function Written in a Another PythonModule

To call and execute a function written in one PythonModule from a different PythonModule , you need to get the name of the PythonModule you want to import.

In our example we want to import python code we wrote in PythonModule1 into our PythonModule .

<!-- image -->

To do so, call the function print(\_\_name\_\_) in PythonModule1 . This prints the name of the module to the Console .

<!-- image -->

Then copy the string from the Console and paste in after the keyword import into the PythonModule where you want to execute it.

<!-- image -->

Click Import . This prints the result of the multiplication to the Plant Simulation Console .

<!-- image -->

**Video on YouTube**

[https://youtu.be/2QJeW5r1AF4?si=YbB687Kp5Vu2iM7H&amp;t=407](https://youtu.be/2QJeW5r1AF4?si=YbB687Kp5Vu2iM7H&t=407)

###### Execute External Python Code

To execute Python code, which you wrote and stored in an external file, use the SimTalk function executePythonFile .

**Example**

<!-- image -->

You can access the objects in your Plant Simulation model in the same way as you would when executing the Python code using a PythonModule .

**See also**

executePythonFile [SimTalk]

Video on YouTube

[https://youtu.be/Rj5eYZu8pl4?si=j8ngdeR3Ykgp2JjR&amp;t=625](https://youtu.be/Rj5eYZu8pl4?si=j8ngdeR3Ykgp2JjR&t=625)

**Tab User-defined**

Define your own attributes as described under the Tab User-defined .

The Dialog provides the Callback method as a user-defined attribute .

<!-- image -->

**Navigate Menu**

The commands are described under the Navigate Menu .

**View Menu**

The View Menu provides commands to access its functions.

Refresh [on View menu]

Show Attributes and Methods [on View menu]

SimTalk

updateDialog [SimTalk]

See also

View Menu [general description]

**Tools Menu**

The commands are described under the Tools Menu .

**Help Menu**

The commands are described under the Help Menu .

#### Methods of the PythonModule

**\_Methods of the PythonModule**

The PythonModule provides:

- The methods listed in the table of contents to the left.
- The Methods of All Objects .

To view all of the methods , read-only attributes and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

An example of the Syntax line of the individual methods might look like this:

```simtalk
< Path >.openDialog([CallOpenControl:boolean:=false]) → boolean
```

- The expression &lt;Path&gt; designates the path of the object to which the method applies.
- The signature of the method, consisting of the identifier and the data type of the parameter, is listed in parentheses. The expression (Parameter:string) , for example, designates a parameter of data type string . Instead of a constant value, you can also use a variable of the required type or a method that returns the required data type.

**Note**

Make sure to enter the parentheses for expressions within parentheses (…). Not entering them may lead to unexpected results and open the Debugger .

Optional parameters are listed within brackets. The expression [,Parameter:boolean] , for example, means that you can, but do not have to enter the boolean parameter.

If a parameter has a default value, the signature shows the default value after the parameter.

If the method has a return value, the signature shows its data type after the arrow -&gt;.

##### call [SimTalk]

Executes the specified Python code of the PythonModule designated by &lt;Path&gt; from SimTalk .

Type

Method

Syntax

```simtalk
< Path >.call([functionName:string, ...])
-> any
```

Parameter

The parameter functionName of data type string designates the function code that is going to be executed.

Return Value

The return value has the data type any .

**callKw [SimTalk]**

**Example**

Suppose your Python code looks like this.

<!-- image -->

```simtalk
def multiply(a, b):
return a*b
```

Our SimTalk code, which we call in a Method , looks like this:

<!-- image -->

The result looks like this when we run the Method .

<!-- image -->

**See also**

callKw [SimTalk]

callKw [SimTalk]

Executes the specified Python code of the PythonModule designated by &lt;Path&gt; from SimTalk .

Type

Method

**Syntax**

```simtalk
< Path >.callKw([functionName:string, ..., KeyValuePairs:any[] ])
-> any
```

**Parameters**

- The parameter functionName of data type string designates the function code that is going to be executed.
- The parameter KeyValuePairs of data type any designates keyword arguments. Specify them in an array consisting of pairs of the respective keyword and the value.

**Return Value**

The return value has the data type any .

**Example**

Suppose your Python code looks like this.

<!-- image -->

```simtalk
def multiply(a, b):
return a*b
```

Our SimTalk code, which we call in a Method , looks like this:

```simtalk
print MyPythonModule.call("multiply", 3, 4)
print MyPythonModule.callKw("multiply", ["a", 3, "b", 4])
```

The result looks like this when we import the PythonModule .

##### callKw [SimTalk]

See also

call [SimTalk]

<!-- image -->

##### callMethod [SimTalk]

Calls a method of the PythonModule designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.callMethod(VariableName:string, MethodName:string[, Argument:any, ...])
-> any
```

Parameters

You can specify the following parameters:

- The parameter VariableName of data type string designates the name of the Python variable.
- The parameter MethodName of data type string designates the name of the SimTalk method.
- The optional parameters Argument of data type any designate additional arguments that you can specify.

Return Value

The return value has the data type any .

Example

Suppose your Python code in the PythonModule looks like this.

```simtalk
class ValuePair: def __init__(self, Val1, Val2):
self.Val1 = Val1
self.Val2 = Val2 def getSumString(self, prefix, suffix):
return prefix + str(self.Val1 + self.Val2) + suffix vp = ValuePair(12, 23)
```

Our SimTalk code, which we call in a Method , looks like this:

```simtalk
print PyClassMethod.callMethod("vp", "getSumString", "Sum=", "m") -- returns the string "Sum=35m" in the Console
```

**callMethod [SimTalk]**

See also

callMethodKw [SimTalk]

##### callMethodKw [SimTalk]

Calls a method of the PythonModule designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< >.callMethodKw(VariableName:string, MethodName:string[,
```

Path Positionargument:any, ...] [, Keywordargument:any[] ]) -> any

**Parameters**

You can specify the following parameters:

- The parameter VariableName of data type string designates the name of the Python variable.
- The parameter MethodName of data type string designates the name of the SimTalk method.
- The optional parameters Positionargument of data type any designate additional position arguments that you can specify.
- The optional parameters Keywordargument of data type any designate additional keyword arguments that you can specify.

Return Value

The return value has the data type any .

Example

Suppose your Python code in the PythonModule looks like this.

```simtalk
class ValuePair: def __init__(self, Val1, Val2):
self.Val1 = Val1
self.Val2 = Val2 def getSumString(self, prefix, suffix):
return prefix + str(self.Val1 + self.Val2) + suffix vp = ValuePair(12, 23)
```

**callMethodKw [SimTalk]**

Our SimTalk code, which we call in a Method , looks like this:

```simtalk
print PyClassMethod.callMethodKw("vp", "getSumString", ["prefix", "Sum=", "suffix", "m"])
print PyClassMethod.callMethodKw("vp", "getSumString", "Sum=", ["suffix", "m"]) -- returns the string "Sum=35m" in the Console
```

See also

callMethodKw [SimTalk]

##### get [SimTalk]

Returns the value of the Python variable of the PythonModule designated by &lt;Path&gt;.

Remarks

The method get only converts those Python data types, which can be converted to the SimTalk data types string , real , integer , boolean , time , date , and dateTme . The method returns all other Python data types as the SimTalk data type any , allowing you to address the specified PythonModule .

You can access the PythonModule object as follows:

```simtalk
< Path >.get(VariableName:string)
-> any // Returns the value of the variable with the name VariableName. < Path >.set(VariableName:string, Value:<any>) -> any // Sets the value of the variable with the name VariableName to Value. < Path >.callMethod(MethodName:string[, Parameter:any, ...]) -> any // Calls the method MethodName of the Python object with the specified paramters. < Path >.call([Parameter:any, ...]) -> any // Calls the Python object with the specified paramters.
```

Type

Method

Syntax

```simtalk
< Path >.get(VariablenName:string)
-> any
```

Parameter

The parameter VariableName of data type string designates the name of the Python variable.

Return Value

The return value has the data type any .

**Example**

Suppose our Python code in the PythonModule looks like this:

```simtalk
class ValuePair: def __init__(self, Val1, Val2):
self.Val1 = Val1
self.Val2 = Val2 def getSumString(self, prefix, suffix):
return prefix + str(self.Val1 + self.Val2) + suffix vp = ValuePair(12, 23) def calcArea(x, y):
return x*y valList = [1,2,3] valDict = {None: ['Row1', 'Row2'], 'Col1': [None, 12], 'Col2': ['C21', 'C22']}
```

Our SimTalk code, which we call in a Method , looks like this:

```simtalk
var po = PythonModule.get("vp")
print po.get("Val1") // -> 12
print po.get("Val2") // -> 23
print po.callMethod("getSumString", "Sum=", "m") // returns "Sum=35m"
var calcArea = PythonModule.get("calcArea")
print calcArea.call(3, 4)
var valList = PythonModule.get("valList")
print valList.call(__len__) // -> 3 Returns the number of elements in the Python list object
print valList[1]            // -> 2 Returns the second element of the Python list object (Python lists start with index 0)
var valDict = PythonModule.get("valDict")
print valDict["Col1"]       // returns [None, 12] valDict["Col1"] = [11,12]   // Assign a new value to the Python dictionary object
print valDict["Col1"]       // returns [11, 12]
```

SimTalk

##### set [SimTalk]

import [SimTalk] - Python

Imports the module of the PythonModule designated by &lt;Path&gt; into the Python interpreter.

Type

Method

Syntax

< Path >.import → void

Return Value

The return value is void .

Example

import keyword # printing all keywords at once using "kwlist()" print("The list of keywords is : ") print(keyword.kwlist)

See also

Import [button] - PythonModule

##### importPythonModule [SimTalk]

importPythonModule [SimTalk]

Accesses methods and attributes of another Plant Simulation PythonModule in the PythonModule designated by &lt;Path&gt;.

Type

Method

Syntax

<PlantSimulation>.importPythonModule(Plant Simulation PythonModule) ->

```simtalk
Path Python module object
```

**Parameter**

The parameter Plant Simulation PythonModule designates the name of the Plant Simulation PythonModule .

Return Value

The return value is the Python module object .

Example

// Let's assume that we have a PythonModule object in the same frame as the current running PythonModule // with the name 'MathModule' and this module has the function multiply defined. import PlantSimulation as ps // This imports the module and assigns it to the variable 'mm' mm = ps.importPythonModule(current.MathModule) // Now we can call the function 'multiply' like this: print(mm.multiply(3,4))

set [SimTalk]

Sets the value of the Python variable of the PythonModule designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.set(VariableName:string, Value:any)
```

Parameters

You can specify the following parameters:

- The parameter VariableName of data type string designates the name of the Python variable.
- The parameter Value of data type any designates the value of the Python variable.

Example

PythonModule.set("BatchSize", 40)

See also

get [SimTalk]

#### Read-Only Attributes of the PythonModule

Read-Only Attributes of the PythonModule

The PythonModule provides the \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyPythonModule.UUID

##### ModuleName [SimTalk]

Queries the name of the PythonModule designated by &lt;Path&gt;, which is returned in Python with the instruction \_\_name\_\_ .

Type

Read-only attribute

Syntax

&lt; Path &gt;.ModuleName -&gt; string

Return Value

The return value has the data type string .

Example

print PythonModule.ModuleName -- might return pmbc4890ad\_881f\_45b2\_b7a2\_388d30656003

#### Attributes of the PythonModule

\_Attributes of the PythonModule

The PythonModule provides:

- The attribute PythonCode [SimTalk] .
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
PythonModule.Name := "MyPythonModule"
print MyPythonModule.Origin
```

##### PythonCode [SimTalk]

Designates the Python source code of the PythonModule designated by &lt;Path&gt;, which is passed to SimTalk and then executed in Plant Simulation .

Type

Attribute

Syntax

```simtalk
< Path >.PythonCode:string
```

**Assignment Value**

You can assign a value of data type string .

**Example**

```simtalk
PythonModule.PythonCode = "print(42)" -- enter Python code into the PythonModule
```

**Variable**

#### Variable [object]

Use the Variable for storing data over an extended period of time.

**Icon**

<!-- image -->

**Remarks**

The object Variable is a global variable that other objects and methods in Plant Simulation can access during a simulation run. A variable can represent an unknown item which stores a quantity. Variables can change their content. Variables are also known as placeholders or unknowns .

The opposite of a Variable is a constant, whose value is known and does not change. You might, for example, use a Variable to store data over an extended period of time during your simulation run, to increment or decrement values, to assign values, etc.

A Variable of data type list , queue , stack , or table shows a type graphic to the left of its name when you

<!-- image -->

.

- Double-click the Name of the Variable to open its dialog. Instead, you can also right-click the Variable and select Open on the context menu.
- Double-click the type graphic of the Variable to open the window of the list object .

<!-- image -->

<!-- image -->

<!-- image -->

Instead, you can also right-click the Variable and select Open Dialog on the context menu.

In addition, Plant Simulation provides local variables . You have to declare a local variable within the source code before you can use it. A local variable is only known in the Method in which you declare it and will be deleted at the end of the method call.

You can show the contents of a Variable in an HtmlReport , compare Display a Variable .

To show a tooltip with information about the Variable , hover with the mouse over it.

<!-- image -->

To change the length of the graphic and the anchor points of the Variable , click Show Manipulators on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the Variable to your simulation model, click Manage Class Library &gt; Basic Objects &gt; InformationFlow &gt; Variable on the Home ribbon tab.

See also

Display a Value During the Simulation with a Variable

Video on YouTube

[https://youtu.be/MXDcx2yplxc?si=PZPyKkBoAAWm4ns\_&amp;t=865](https://youtu.be/MXDcx2yplxc?si=PZPyKkBoAAWm4ns_&t=865)

<!-- image -->

<!-- image -->

#### Dialog Box of the Variable

Dialog Box of the Variable

Double-click the icon of the Variable to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

<!-- image -->

##### Name [text box] - Variable

Shows the current name of the Variable , either the built-in name or the name that you specify.

You can type in a combination of letters, digits, and underscore (\_) characters, for example MyVariable , MyVariable1 , My\_Variable\_1 .

The name of an object cannot start with a digit, i.e., you cannot specify 1Variable .

SimTalk

Name [SimTalk] - Variable

Tab Value

Tab Value [Variable]

The Tab Value provides the settings listed in the table of contents to the left.

**Name [text box] - Variable**

###### Data Type [Variable]

Select the data type of the Variable you are creating from the drop-down list.

You can use any of the supported Data Types .

<!-- image -->

- For a Variable of data type object , you have to type the path to and the name of the object into the text box Value . The starting point of the relative path is the Frame into which the Variable is inserted. Or you can click and select the object in the dialog Select Object .

Instead of typing in the path of the object or of selecting the object, you can now also drag the object onto the Variable and drop it there. Plant Simulation then inserts a reference to the object.

<!-- image -->

- To use the data type time with a random number distribution, select the data type randtime , and type in the parameters of the distribution function, as the data type Time only accepts constant values. Then initialize the randtime value before accessing it, for example with the method rollDice which determines the next random number that the Variable uses.

**Data Type [Variable]**

Note

For the list data types ( table , list , stack , queue ) you can use the method unshare .

- For the Data Type [user-defined attribute] &gt; real , length , weight , time , speed , and acceleration you can type in the number of Decimal Places and Integer Places .

SimTalk DataType [SimTalk] - Variable AsString [SimTalk] - Variable See also Methods of the Distributions

###### Value [Variable]

The Data type you select determines what you can do.

- You can select the value from a drop-down list.
- You can type in the value of the Variable .

<!-- image -->

<!-- image -->

**Note**

For the data types length , weight , and speed the units you select in the Plant Simulation main window under File &gt; Model Settings/Preferences &gt; Units &gt; Mass / Speed / Length determine how Plant Simulation interprets the value.

A value of 100 with the length set to km is interpreted as 100 km.

- Click Open to open the dialog box of the objects that correspond to the data types table , list , stack or queue .

<!-- image -->

If the Variable points to a list which is referenced from additional places/objects, the dialog shows the button Unshare .

<!-- image -->

**Unshare a Variable**

To unshare a Variable of data types table , list , stack or queue:

- Click Unshare to make Plant Simulation assign its own copy of the list to the Variable instead of the shared contents of the list. This corresponds to the method unshare .
- Click and select the object of data type object in the dialog Select Object .

**Value [Variable]**

<!-- image -->

- Or type the path to and the name of the object into the text box Value .

Note

F2 opens the dialog of the object, whose name you typed into the text box.

The data type object designates an absolute or a relative path to an object.

- The absolute path always starts with a period, starting in the Class Library , such as .building and identifies the object uniquely. Plant Simulation does not change the absolute path if you derive or insert a Frame using a Variable object, i.e., the absolute path will still reference the source object, not to the one you derived or inserted!
- The relative path which starts with Location or ~ , considers the current location of the Variable object each time the object Variable is accessed. Thus, when deriving or inserting an object consisting of several hierarchically structured Frames , you do not have to change the existing object values in the Variable objects.
- To use the data type time with a random number distribution, select the data type randtime , and type in the parameters of the distribution function, as the data type Time only accepts constant values. Note you have to initialize the randtime value before accessing it, for example by employing the method rollDice , which determines the next random number that the Variable uses.

SimTalk

Value [SimTalk] - Variable

Variable. inheritAttribute ("Value")

AsString [SimTalk] - Variable

unshare [SimTalk]

See also

Data Type [Variable]

Value [user-defined attribute] &gt; Unshare, user-defined attribute

Unshare a List or Data Table

###### Inherit Value [Variable]

To inherit the value of the Variable , click the inheritance check box next to the text box Value so that it is green.

<!-- image -->

To not inherit the value, click the check box again so that it looks like this .

SimTalk

**Value [Variable]**

Variable. inheritAttribute ("Value")

**Initial Value [Variable]**

###### Initial Value [Variable]

To reset a value, which the Variable recorded during a simulation run to an initial value, select this check box.

<!-- image -->

Plant Simulation sets the value during the reset phase and resets it in the init phase of the next simulation run.

Initial Value - text box

After you select the check box, the Variable shows a text box.

Type the initial value for the next simulation run into the text box.

**Note**

The Data Types table , list , stack , queue , and randtime do not provide this feature.

SimTalk

InitValue [SimTalk] - Variable

HasInitValue [SimTalk] - Variable

Tab Display

Tab Display [Variable]

Select how Plant Simulation shows the global Variable in the Frame window on the Tab Display .

It provides the settings listed in the table of contents to the left.

###### Font Size [drop-down list] - Variable

Select the Font Size for displaying the Variable in the Frame into which you inserted it.

<!-- image -->

<!-- image -->

**SimTalk**

Font [SimTalk] - Variable

**Font Color [Variable]**

###### Font Color [Variable]

To select the Font Color with which Plant Simulation shows the Variable in the Frame window, click the drop-down arrow.

<!-- image -->

You can select one of the predefined colors, or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation shows this color next to More Colors and uses it as the active color.

SimTalk

Color [SimTalk] - Variable

###### Background Color [drop-down list] - Variable

To select the color of the background of the Variable which you inserted into a Frame , click the dropdown arrow.

<!-- image -->

You can select one of the predefined colors, or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation shows this color next to More Colors and uses it as the active color.

SimTalk

BackgroundColor [SimTalk] - Variable

**Alignment [Variable]**

###### Alignment [Variable]

Select the Alignment of the display of the Variable with its insertion point in 3D .

<!-- image -->

- Left aligns the Variable named VariableWithReal with the left border of the type graphic.
- Name places the left border of the displayed Name or Value on the insertion point of the Variable .
- Value places the right border of the displayed Name or the left border of the displayed Value on the insertion point of the Variable .
- Right places the right border of the displayed Name or Value on the insertion point of the Variable .

**Alignment**

Looks like this

Left

Name

Value

Right

SimTalk

Alignment [SimTalk] - Variable

###### Integer Places [text box] - Variable

Type in the number of Integer Places which the Variable shows in 3D .

<!-- image -->

The Variable can show up to 15 integer places. The default setting -1 means that Plant Simulation applies no minimum to the number of integer places.

Type in a positive value to fill up the space before the decimal point with blank spaces until the specified number of places has been reached when the Variable is shown in 3D.

<!-- image -->

**Note**

This setting only applies to the Data Type [user-defined attribute] &gt; real , length , weight , time , speed , and acceleration .

**SimTalk**

IntegerPlaces [SimTalk] - Variable

###### Decimal Places [text box] - Variable

Type in the number of Decimal Places which the object Variable shows in 3D . It can show up to 15 decimal places.

<!-- image -->

Remarks

The default setting -1 shows all existing places.

Type in a positive value to show the number of decimal places, which you specified.

|   Integer places | Looks like this   |
|------------------|-------------------|
|               -1 |                   |
|                8 |                   |

**Note**

This setting only applies to the Data Type [Variable] &gt; real , length , money , weight , time , speed , and acceleration .

The number of decimal places for the data type time affects values differently than for the data type real .

The value -1 for the data type time means that the default time display format is displayed with four decimal places.

A positive value means that Plant Simulation shows the number of decimal places that you typed in at most.

SimTalk

DecimalPlaces [SimTalk] - Variable

###### Transparent [Variable]

To make the background of a Variable , which you inserted into a Frame , Transparent , select this check box.

<!-- image -->

Then, the Variable shows the space around the text in the color of the background of the Frame .

To show the space around the text in white, clear the check box.

The setting Transparent also applies in 3D.

| Transparent   | Not transparent   |
|---------------|-------------------|

SimTalk

Transparent [SimTalk] - Variable

**Show Data Type [Variable]**

###### Show Data Type [Variable]

To show the data type in addition to the name and the value of the Variable in the Frame , into which you inserted it, select this check box.

<!-- image -->

To hide the data type, clear the check box.

<!-- image -->

**SimTalk**

ShowDataType [SimTalk] - Variable

###### Show Units [Variable]

To show the unit of the physical size of the Variable , select this check box.

<!-- image -->

Select the unit under File &gt; Model Settings/Preferences &gt; Units .

To hide the units, clear the check box.

For the data type randtime the check box Show Units also sets if Plant Simulation shows the distribution parameters in the Frame window or not.

If you clear Show Units , you can type in the number of Decimal Places .

<!-- image -->

<!-- image -->

**SimTalk**

ShowUnit [SimTalk] - Variable

##### Tab Statistics

**Tab Statistics**

###### Tab Statistics [Variable]

The tab Statistics provides the settings listed in the table of contents to the left.

The tab shows the top five frequencies and the top five durations on the tab itself. Only Variables of Data type string or integer records statistics values.

<!-- image -->

###### Active [check box] - statistics, Variable

To collect statistics data during a simulation run and to show the top five frequencies and the top five durations on the tab, select this check box.

<!-- image -->

Only Variables of Data type string or integer records statistics values.

SimTalk

StatisticsActive [SimTalk] - Variable

**Statistics Table [Variable]**

###### Statistics Table [Variable]

To open the statistics table, click this button.

<!-- image -->

| Item English       | Description                                                                                                                   | Item German         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------|---------------------|
| Value              | Shows the name of the value of the Variable .                                                                                 | Wert                |
| Frequency          | Shows the number of occurrences of the value from the column Value . Statistics only counts, when the value actually changes. | Häufigkeit          |
| Duration           | Shows the duration of the occurrences, which is the complete duration the Value had during the statistics collection period.  | Dauer               |
| Frequency [%]      | Shows the portion of the individual frequencies to the sum of all values in the column Frequency .                            | %_Häufigkeit        |
| Duration [%]       | Shows the portion of the individual durations to the sum of all values in the column Duration .                               | %_Dauer             |
| Mean Duration      | Shows the mean duration of the individual durations.                                                                          | Mittlere Dauer      |
| Standard Deviation | Shows the standard deviation of the duration.                                                                                 | Standardabweich ung |

**SimTalk**

getStatisticsTable [SimTalk] - user-defined attribute

###### Charts [Variable]

To open a pie chart each showing the frequency and the duration of the value, click this button.

<!-- image -->

<!-- image -->

**Frequency Histogram [Variable]**

###### Frequency Histogram [Variable]

To open a histogram showing the frequency, i.e., the number of occurrences of the value, click this button.

<!-- image -->

##### Tab Comment [Variable]

Type any comment describing the function of the Variable into the text box on the tab Comment .

First, click the check box to turn Inheritance off. Only then you can enter data.

To show the comment you type in as a tooltip , drag the mouse over the object in the Frame . The tooltip is shown as you format it when you type it in. It does not automatically create line breaks, but shows the text with the line breaks you manually specify by pressing Enter .

<!-- image -->

**SimTalk**

Comment [SimTalk] - Variable

**Navigate Menu**

##### Navigate Menu

The commands are described under the Navigate Menu .

View Menu

The View Menu provides commands to access its functions.

Refresh [on View menu]

Show Attributes and Methods [on View menu]

SimTalk

updateDialog [SimTalk]

See also

View Menu [general description]

##### Tools Menu

Tools Menu provides these menu commands:

The Tools Menu Edit Controls Edit Observers 3D

##### Help Menu

The commands are described under the Help Menu .

#### Assigning a Value to a Variable

When assigning a new value to the Variable , this value has to be compatible with the active data type.

A value is compatible if Plant Simulation can automatically transform it into a correct value for the task.

A change of value may occur because:

- Plant Simulation cannot display digits after the decimal point and cuts them off. It transforms, for example, the real value 3.9 into the integer value 3.
- Loss of significance occurs for great value differences. Floating point operations only save a certain number of digits and the magnitude of a number (mantissa and exponent). Plant Simulation deletes additional digits created during a calculation and the number does not return the expected value. This kind of error cannot be avoided and only occurs if the difference in size is at least 10 7 .

If you assign a Variable to a Method , keep in mind that Plant Simulation calls and executes this Method if you only type in the name of a Method . This way the Method is returned, instead of the reference you would like to receive. Use the reference operator &amp; to get the required reference to a Variable of data type object .

**Syntax**

```simtalk
Path := any
```

**Example**

```simtalk
Variable := Value
Variable := &MyMethod
```

#### Calling the Contents of a Variable

If the contents of the Variable references another Variable of data type object , access the contents of that variable by typing this Variable in parenthesis.

If the contents of the Variable references a Method , typing this Method in parentheses calls the Method itself.

**Syntax**

(Path)

**Example**

```simtalk
value := (Variable) + 1   // accesses the variable (control_gate)            // calls the method (method)(3.4,"drill")     // calls the method with parameters
```

#### Reading the Contents of a Variable

To access the contents of the Variable designated by &lt;Path&gt;, use its name.

**Syntax**

&lt; Path &gt;

**Example**

```simtalk
MyTable[1,1] := MyVariable
```

#### Methods of the Variable

\_Methods of the Variable

The object Variable provides:

- The methods listed in the table of contents to the left.

**Note**

You can only access the methods of the object Variable , which refer to the object itself, via the reference operator &amp; . Without the operator the method will be applied to the contents of the Variable .

**Example**

.MyPlant.&MyVariable.openDialog

Also compare:

Assigning a Value to a Variable

Calling the Contents of a Variable

Reading the Contents of a Variable

- The Methods of All Objects .

To view all of the methods , read-only attributes and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

An example of the Syntax line of the individual methods might look like this:

```simtalk
< Path >.openDialog([CallOpenControl:boolean:=false]) → boolean
```

- The expression &lt;Path&gt; designates the path of the object to which the method applies.
- The signature of the method, consisting of the identifier and the data type of the parameter, is listed in parentheses. The expression (Parameter:string) , for example, designates a parameter of data type string . Instead of a constant value, you can also use a variable of the required type or a method that returns the required data type.

**Note**

Make sure to enter the parentheses for expressions within parentheses (…). Not entering them may lead to unexpected results and open the Debugger .

Optional parameters are listed within brackets. The expression [,Parameter:boolean] , for example, means that you can, but do not have to enter the boolean parameter.

If a parameter has a default value, the signature shows the default value after the parameter.

If the method has a return value, the signature shows its data type after the arrow -&gt;.

##### \_Methods of the Variable

##### &amp; [SimTalk] - Variable

The &amp; operator/reference operator returns the reference of the Variable instead of its contents.

Remarks

The &amp; operator applies to SimTalk 2.0 .

Type

Method/operator

Syntax

```simtalk
&Variable → object <PathToVariable>.&Variable → object
```

**Return Value**

The return value has the data type object .

Example

```simtalk
print &myVariable.location // might
return .Models.Model.Frame
```

**See also**

&amp; [SimTalk] - reference operator

##### create [SimTalk] - Variable

create [SimTalk] - Variable

Creates a data structure without contents for the Variable designated by &lt;Path&gt;.

Remarks

A Variable of data type stack , queue , list and table does not contain the data itself, but references to the respective data structures. Before using a Variable of these types, Plant Simulation has to create the data structure. Only then it can access the actual data. Any existing references will be overwritten.

Type

Method/operator

Syntax

&lt; Path &gt;.create

Example

```simtalk
orderList.create -- creates the Variable with the name orderList
orderList.insert(1,"A-No. 4712")
```

##### getStatisticsTable [SimTalk] - Variable

Returns the statistics table of the Variable designated by the reference operator &lt;&amp;&gt;.

Remarks

If the Variable is of data type string , Plant Simulation always shows the string values in the first column in lower case letters.

Type

Method

Syntax

```simtalk
< & >Variable.getStatisticsTable([TargetTable:table]) → any
```

**Parameter**

The optional parameter TargetTable of data type table designates the table to which the method getStatisticsTable writes the statistics data.

Return Value

The return value has the data type any .

- true if statistics collection is activated.

false if statistics collection is deactivated. Then the table remains unaltered.

- The return value is the table containing the statistics data if statistics collection is activated if you do not specify the optional parameter.

void if statistics collection is deactivated.

**Examples**

```simtalk
&MyVariable.getStatisticsTable(mystatisticstable) // Writes the statistics values to the table named mystatisticstable. // The
return value is true
if statistics collection is activated. // It is false if it is deactivated. Then the table remains unaltered.
&MyVariable.getStatisticsTable // The
return value is the statistics table
if statistics // collection is activated. It is void if statistics collection is deactivated.
```

**See also**

**Statistics Table [Variable]**

##### increment [SimTalk] - Variable

Adds a value to the Variable designated by the reference operator &lt;&amp;&gt;.

Remarks

The method only applies to numerical data types. It applies to the object Variable and to user-defined attributes .

Type

Method

Syntax

```simtalk
< & >Variable.increment < & >Variable.increment(Value:integer)
```

**Parameter**

The method increment without parameter adds the value 1 to the Variable .

The method increment(Value) adds the Value designated by the parameter of data type integer to the Variable .

Example

```simtalk
x := &MyVariable.increment(-3) // accomplishes the same as //
Variable := Variable - 3 x := Variable
```

ref [SimTalk] - Variable

ref [SimTalk] - Variable

The ref(Path) operator returns the reference of the Variable designated by &lt;Path&gt; instead of its contents.

Remarks

The ref operator applies to SimTalk 1.0 .

Type

Method/operator

Syntax

<!-- formula-not-decoded -->

Return Value

The return value has the data type object .

Example

print ref(MyVariable).location rollDice [SimTalk]

Creates a new random number and saves it to the Variable designated by &lt;Path&gt;.

Remarks

rollDice applies to Variables of data type randtime .

Type

Method

Syntax

< Path >.rollDice → time

Return Value

The return value has the data type time .

Example

```simtalk
for var i := 1 to 10 variable.rolldice // new random number
	print variable    // output random numbers
next
```

#### Read-Only Attributes of the Variable

Read-Only Attributes of the Variable

The Variable provides:

- The read-only attribute AsString [SimTalk] - Variable .
- The \_Read-Only Attributes of All Objects .

**Note**

You can only access the read-only attributes of the object Variable , which refer to the object itself, via the reference operator &amp; .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print &amp;MyVariable.AsString

##### AsString [SimTalk] - Variable

Returns the value of the Variable as a string.

Remarks

Having the value as a string is especially useful for Variables of data type object . If the Variable contains a relative path, AsString returns the relative path.

Type

Read-only attribute

Syntax

```simtalk
< & >Variable.AsString → string
```

Return Value

The return value has the data type string .

Example

```simtalk
ObjVariable := "~.ProdMgr.prodplan"
var a1 := ObjVariable             // assigns .Models.Model.ProdMgr.prodplan
var a2 := &ObjVariable.AsString   // assigns "~.ProdMgr.prodplan"
```

See also

Data Type [Variable]

#### Attributes of the Variable

\_Attributes of the Variable

The object Variable provides:

- The attributes listed in the table of contents to the left.
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the Variable , open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

**Note**

You can only access the attributes of the object Variable , which refer to the object itself, via the reference operator &amp; . Without the operator the attribute will be applied to the contents of the Variable .

&amp;Variable.Name := "MyVariable"

##### Alignment [SimTalk] - Variable

Sets the alignment of the Variable designated by the reference operator &lt;&amp;&gt; with its insertion point in 3D .

Type

Attribute

Syntax

```simtalk
< & >Variable.Alignment:string
```

Assignment Value

You can assign a value of data type string .

You can specify "Left" , "Name" , "Value" , or "Right" .

Example

```simtalk
&MyVariable.Alignment := "Right"
```

See also

Alignment [Variable]

##### BackgroundColor [SimTalk] - Variable

BackgroundColor [SimTalk] - Variable

Sets the background color of the Variable designated by the reference operator &lt;&amp;&gt; in the Frame .

Type

Attribute

Syntax

```simtalk
< & >Variable.BackgroundColor:integer
```

Assignment Value

You can assign a value of data type integer .

Set the RGB values of the color with the method makeRGBValue .

Example

```simtalk
&MyVariable.BackgroundColor := makeRGBValue(100,100,100) &MyVariable.BackgroundColor := 6579300 // is the same as the color above
```

SimTalk

makeRGBValue [SimTalk]

See also

Background Color [drop-down list] - Variable

Color [SimTalk] - Variable Color [SimTalk] - Variable Sets the color with which Plant Simulation displays the Variable designated by the reference operator &lt;&amp;&gt; in the Frame .

Type

Attribute

Syntax

```simtalk
< & >Variable.Color:integer
```

Assignment Value

You can assign a value of data type integer .

Set the RGB values of the color with the method makeRGBValue .

Example

```simtalk
&MyVariable.Color := makeRGBValue(110,0,200)
```

SimTalk

makeRGBValue [SimTalk]

See also

Font Color [Variable]

&amp; [SimTalk] - Variable

##### Comment [SimTalk] - Variable

Comment [SimTalk] - Variable

Sets the comment of the Variable designated by the reference operator &lt;&amp;&gt;.

Type

Attribute

Syntax

```simtalk
< & >Variable.Comment:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
&MyVariable.Comment := "My comment, my comment"
```

See also

Tab Comment [Variable]

&amp; [SimTalk] - Variable

##### DataType [SimTalk] - Variable

Sets the data type of the Variable designated by the reference operator &lt;&amp;&gt;.

Type

Attribute

Syntax

```simtalk
< & >Variable.DataType:string
```

Assignment Value

You can assign a value of data type string .

<!-- image -->

**Example**

```simtalk
&MyVariable.DataType := "string"
```

**See also**

Data Type [Variable]

&amp; [SimTalk] - Variable

##### DecimalPlaces [SimTalk] - Variable

Sets the number of decimal places which the Variable designated by the reference operator &lt;&amp;&gt; shows in the Frame .

Remarks

The Variable can show up to 15 decimal places. The default setting -1 shows all existing places. If you enter a positive value, the Variable shows the number of decimal places, which you entered, in the Frame .

**Note**

This setting only applies to the Data Types &gt; real , length , money , weight , time , speed , and acceleration .

The number of decimal places for the data type time affects values differently than for the data type real . The value -1 for the data type time means that the default time display format is displayed with four decimal places. A positive value means that Plant Simulation shows the number of decimal places that you entered at most.

Type

Attribute

Syntax

&lt; &amp; &gt;Variable.DecimalPlaces:integer

Assignment Value

You can assign a value of data type integer .

Example

&amp;MyVariable.DecimalPlaces := 12

See also

Data Type [Variable]

Decimal Places [text box] - Variable

&amp; [SimTalk] - Variable

##### Font [SimTalk] - Variable

Sets the font size with which Plant Simulation displays the Variable designated by the reference operator &lt;&amp;&gt; in the Frame .

Type

Attribute

Syntax

```simtalk
< & >Variable.Font:integer
```

Assignment Value

You can assign a value of data type integer .

Specify 1 for Small , 2 for Medium , 3 for Large , or 4 for Extra Large .

Example

```simtalk
&MyVariable.Font := 2
```

See also

Font Size [drop-down list] - Variable

&amp; [SimTalk] - Variable HasInitValue [SimTalk] - Variable Sets if the Variable designated by the reference operator &lt;&amp;&gt; has an initial value ( true ) or not ( false ).

Type

Attribute

Syntax

```simtalk
< & >Variable.HasInitValue:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
&MyVariable.DataType := "integer" &MyVariable.HasInitValue := true
```

See also

Initial Value [Variable]

&amp; [SimTalk] - Variable

##### InitValue [SimTalk] - Variable

Resets a value, which the Variable designated by the reference operator &lt;&amp;&gt; recorded during a simulation run, to an initial value.

Remarks

Plant Simulation sets the value during the reset phase and resets it in the init phase of the next simulation run.

**Note**

The Data types table , list , stack , queue , and randtime do not provide this feature.

Type

Attribute

Syntax

< & >Variable.InitValue:any

Assignment Value

You can assign a value of data type any .

Example

```simtalk
&MyVariable.DataType := "integer" &MyVariable.InitValue := 0
```

SimTalk

HasInitValue [SimTalk] - Variable

See also

Data Type [Variable]

Initial Value [Variable]

&amp; [SimTalk] - Variable

##### IntegerPlaces [SimTalk] - Variable

IntegerPlaces [SimTalk] - Variable

Sets the number of integer places which the Variable designated by the reference operator &lt;&amp;&gt; shows in the Frame .

Remarks

The Variable can show up to 15 integer places. The default setting -1 means that Plant Simulation applies no minimum to the number of integer places. Enter a positive value to fill up the space before the decimal point with blank spaces until the specified number of places has been reached when the Variable is shown in 3D .

**Note**

This setting only applies to the Data types &gt; real , length , weight , time , speed , and acceleration .

Type

Attribute

Syntax

```simtalk
< & >Variable.IntegerPlaces:integer
```

**Assignment Value**

You can assign a value of data type integer .

Example

```simtalk
&MyVariable.IntegerPlaces := 6 -- The value "123"     will show as "   123" -- The value "123456"  will show as "123456" -- The value "1234567" will show as "1234567"
```

See also

Data Type [user-defined attribute]

Integer Places [text box] - Variable , text box

Name [SimTalk] - Variable

Sets the Name of the Variable designated by the reference operator &lt;&amp;&gt;.

Remarks

You can type in a combination of letters, digits, and underscore (\_) characters, for example MyVariable , MyVariable1 , My\_Variable\_1 .

The name of an object cannot start with a digit, i.e., you cannot enter 1Variable .

Type

Attribute

Syntax

```simtalk
< & >Variable.Name:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
&Variable.Name := "MyVariable"
```

See also

Name [text box] - Variable

&amp; [SimTalk] - Variable ShowDataType [SimTalk] - Variable Shows the data type of the Variable designated by the reference operator &lt;&amp;&gt; ( true ) or hides them ( false ) in the Frame into which you inserted it.

Type

Attribute

Syntax

&lt; &amp; &gt;Variable.ShowDataType:boolean

Assignment Value

You can assign a value of data type boolean .

Example

&amp;myVariable.ShowDataType := false

See also

Show Data Type [Variable]

&amp; [SimTalk] - Variable

##### ShowUnit [SimTalk] - Variable

Shows the units of the values of the Variable designated by the reference operator &lt;&amp;&gt; ( true ) or hides them ( false ) in the Frame into which you inserted it.

Type

Attribute

Syntax

&lt; &amp; &gt;Variable.&lt;UserDefinedAttribute&gt;.ShowUnit:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
&MyVariable.ShowUnit := true
```

See also

Show Units [Variable]

&amp; [SimTalk] - Variable StatisticsActive [SimTalk] - Variable Collects statistics values of the Variable designated by the reference operator &lt;&amp;&gt; ( true ) or not ( false ).

Remarks

The Variable only collects statistics for the data types string and integer .

Type

Attribute

Syntax

<!-- image -->

&lt; &amp; &gt;Variable.StatisticsActive:boolean

Assignment Value

You can assign a value of data type boolean .

Example

&amp;MyVariable.StatisticsActive := true

See also

Active [check box] - statistics, Variable

&amp; [SimTalk] - Variable

DataType [SimTalk] - Variable

##### Transparent [SimTalk] - Variable

Makes the background of the Variable designated by the reference operator &lt;&amp;&gt; transparent in the Frame ( true ) or not transparent ( false ).

Remarks

The setting Transparent also applies in 3D.

| Not transparent   | Transparent   |
|-------------------|---------------|

Type

Attribute

Syntax

&lt; &amp; &gt;Variable.Transparent:boolean

Assignment Value

You can assign a value of data type boolean .

Specify true to show the space around the text in the color of the background image of the Frame .

Specify false to show the space around the text in white.

Example

&amp;MyVariable.Transparent := false

See also

Transparent [Variable]

&amp; [SimTalk] - Variable

##### Value [SimTalk] - Variable

Value [SimTalk] - Variable

Sets the value of the Variable designated by the reference operator &lt;&amp;&gt;.

Type

Attribute

Syntax

< & >Variable.Value:any

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type any .

Example

```simtalk
var obj: object
waituntil obj.Value = 3 prio 1
obj := &MyVariable regStat
```

See also

Value [Variable]

&amp; [SimTalk] - Variable

#### Properties of Lists and Tables

