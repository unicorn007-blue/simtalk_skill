#### \_Miscellaneous Global Functions

SimTalk provides the functions listed in the table of contents to the left covering a wide range of applications.

Query the Data Type of a Variable of Data Type Any describes the methods for doing just that.

See also

\_\_Accessing General 3D Functions

##### animation [SimTalk]

Activates or deactivates the animation of MUs and States during a simulation run.

Remarks

Calling the function without parameter returns the current state of the animation.

Calling the function with parameter sets the state of the animation to activated ( true ) or deactivated ( false ).

Type

Function

Syntax

```simtalk
animation → boolean animation([Activate:boolean]) → boolean
```

**Parameter**

The optional parameter Activate of data type boolean activates ( true ) or deactivates ( false ) the animation of MUs and States .

Return Value

The return value has the data type boolean .

The return value is true if the animation of MUs and States is activated.

**Example**

animation         // returns if animation is on or off animation(true)   // activates animation

See also

<!-- image -->

**applicationHome [SimTalk]**

##### applicationHome [SimTalk]

Returns the folder in which Plant Simulation is installed.

Type

Function

Syntax

```simtalk
applicationHome → string
```

Return Value

The return value has the data type string .

Example

```simtalk
print applicationHome // might
return C:\Program Files\Siemens\Plant Simulation 2504\
```

See also

Installing Plant Simulation

##### applicationVersion [SimTalk]

Returns the coded version number of Plant Simulation .

Type

Function

Syntax

```simtalk
applicationVersion
-> integer
```

**Return Value**

The return value of data type integer is composed as follows: VVMMMPPP

- VV is the major version number.
- MMM is the minor version number.
- PPP is the number of the patch level.

**Example**

```simtalk
print applicationVersion // might
return 15002002, i.e. version
15.2.2
print applicationVersion // might
return 16001003, i.e. version
16.1.3
print applicationVersion // might
return 22001006, i.e. version
2201.0006
print applicationVersion // might
return 23002008, i.e. version
2302.0008
print applicationVersion // might
return 24004000, i.e. version
2404.0000
```

**See also**

About Plant Simulation calcBrakingDistance [SimTalk] - general description Calculates the required braking distance for a given Speed and a given Deceleration .

Remarks

The braking distance is calculated according to the formula s=1/2 v 2 /a.

**Note**

The function is especially helpful for the Transporter .

Type

Function

Syntax

calcBrakingDistance(Speed:speed, Deceleration:acceleration) -&gt; length

**Parameters**

- The parameter Speed of data type speed designates the Speed .
- The parameter Deceleration of data type acceleration designates the Deceleration .

**Example**

print calcBrakingDistance(100kmh, 10) // returns 138.888888888889m

Return Value

The return value has the data type length .

See also

Deceleration [SimTalk] - Transporter

SafetyZones [SimTalk]

calcBrakingDistance [SimTalk] - Transporter

##### calcDroppedPerpendicularFootPoint [SimTalk]

Calculates the foot of the dropped perpendicular of the point P on the line A1-A2 and returns it.

Type

Function

**Syntax**

calcDroppedPerpendicularFootPoint(A1:length[3], A2:length[3], P:length[3]) -> length[3]

**Parameters**

- The parameter A1 is an array of data type length with three values. It sets the first point of the line.
- The parameter A2 is an array of data type length with three values. It sets the second point of the line.
- The parameter P is an array of data type length with three values. It designates the point for which the foot of the dropped perpendicular is calculated.

**Return Value**

The return value is an array with three values of data type length .

**Example**

```simtalk
print calcDroppedPerpendicularFootPoint([1,0.1,0.1],[2,0.2,0.4],[5,0.5,1]) // returns [4.91818181818182, 0.491818181818182, 1.27545454545455]
```

**callEvery [SimTalk]**

##### callEvery [SimTalk]

Calls all Methods with the designated name in the designated Frame and all of its sub-frames.

**Remarks**

Plant Simulation stops executing the Method that contains the callEvery call, until all methods called are executed.

Plant Simulation searches the Frames for Methods using the depth-first strategy. It always immediately executes Methods it encounters.

Type

Function

Syntax

```simtalk
callEvery(Frame:path, Method:string[, Parameters:parameters])
```

**Parameters**

- The parameter Frame of data type path designates the Frame within which you want to call all Methods .
- The parameter Method of data type string designates the name of the Method you want to call.
- The optional parameters are passed as parameters to the calling Methods .

In our example we placed several Frames within Frames in the model. The numbering M x indicates the sequence the Frames were inserted, i.e., Frame M 11 was placed before Frame M 12, M 111 before M 112, etc. The numbers 1 to 9 indicate the sequence Plant Simulation searches for methods with the name specified in callEvery . Plant Simulation always calls the more recent object first. In our example it calls the Frames in this order: 1, 9, 2, 7, 8, 3, 6, 5, 4.

<!-- image -->

The depth-first strategy starts with the Frame entered in Path, and then searches through the hierarchy, using the sequence in which we inserted the Frames as a guideline.

The function searches all hierarchy levels for methods with the name of this Method . As soon as it finds such a method, it will be called with the designated parameters.

**Example**

callEvery(.frame2,"outputMessage",999,"here")

**checkForLicense [SimTalk]**

##### checkForLicense [SimTalk]

Checks if a user-defined license is available or not.

Type

Function

**Syntax**

```simtalk
checkForLicense(Feature:string, Version:string, PasswordHash:string) → integer
```

**Parameters**

- The parameter Feature of data type string designates the name of the license feature.
- The parameter Version of data type string designates the requested version number of the license.
- The parameter PasswordHash of data type string designates the SHA-1-Hash of the password of the license.

**Return Value**

The return value has the data type integer .

The individual values have this meaning:

- 0: The license feature is registered and valid.
- 1: The license feature is not registered.
- 2: The file has an invalid registry data format.
- 3: The SHA-1-Hash is wrong.
- 4: The Host-ID is wrong.
- 5: The registered version of the feature is too old.
- 6: The license has expired.
- 7: The feature does not permit the use with the license type of Plant Simulation (Professional / Standard / Runtime /...).

**Example**

if checkForLicense("MyFeature", "1", "686483805ac47ca14e03514f7481a7973b401762") = 0 // The license is available, you can proceed ...

else closeModel messageBox("The license 'MyFeature' is unavailable. The model was closed.\n", 1, 1) end

**See also**

createLicenseFile [SimTalk]

setRequiredLicense [SimTalk]

**checkID [SimTalk]**

##### checkID [SimTalk]

Checks if you can use an expression as the name of an object (true) or not (false).

Type

Function

Syntax

```simtalk
checkID(Expression:string) → boolean
```

**Parameter**

The parameter Expression of data type string designates the expression. The function considers all keywords and function calls.

Return Value

The return value has the data type boolean .

**Example**

```simtalk
print checkID("sin") -- returns false
```

See also

Keywords

##### clearConsole [SimTalk]

Deletes the contents of the Console window .

Remarks

The screenshot shows which data will be deleted.

<!-- image -->

**Type**

Function

**Syntax**

clearConsole

**Example**

clearConsole

See also

Console

closeConsole [SimTalk]

openConsole [SimTalk]

setConsoleFilter [SimTalk]

print [SimTalk] - output function

**Specifying Start Options**

##### clearLogFile [SimTalk]

Deletes the contents of the log file into which Plant Simulation wrote all messages which were output to the Console window .

Remarks

clearLogFile does not delete the log file itself.

Type

Function

Syntax

```simtalk
clearLogFile → boolean
```

Return Value

The return value has the data type boolean .

Example

clearLogFile

See also

Console

getLogFile [SimTalk]

Specifying Start Options

**closeAllWindows [SimTalk]**

##### closeAllWindows [SimTalk]

Closes all open object windows, even those that are minimized, including 3D windows.

Remarks

The optional boolean parameter has no effect.

Type

Function

Syntax

closeAllWindows([UnusedParameter:boolean])

**Example**

closeAllWindows

See also

List of Open Windows

##### closeConsole [SimTalk]

Closes the open Console window .

**Remarks**

All messages that were output to the Console will be lost.

<!-- image -->

clearConsole [SimTalk] openConsole [SimTalk] setConsoleFilter [SimTalk] Specifying Start Options

##### closeHTMLWindow [SimTalk]

Closes the browser window which you previously opened using the title of the window.

Type

Function

Syntax

```simtalk
closeHTMLWindow(CloseHTMLWindow:string) → boolean
```

Parameter

The parameter CloseHTMLWindow of data type string designates the title of the window you want to close.

Return Value

The return value has the data type boolean .

Example

closeHTMLWindow("Siemens Corporate Site") closeHTMLWindow("Image of the ParallelStation")

See also

openHTMLWindow [SimTalk]

##### closeModel [SimTalk] - global function

Closes the open simulation model without saving it.

Remarks

**Note**

You can also define a Method with the name onCloseModel in any folder in the Class Library , including the Basis folder. This Method is being executed when you close the model or when you exit Plant Simulation . You can, for example, program clean-up tasks, delete temporary files, etc.

The method onCloseModel has to declare the boolean parameter onExitApplication . Plant Simulation sets this parameter to false when onCloseModel is called when you close the model. Plant Simulation sets this parameter to true when onCloseModel is called when you exit Plant Simulation .

You can also program several onCloseModel methods and place them into different folders. Plant Simulation then calls all existing onCloseModel method classes in the Class Library when you close the model or exit the application.

Type

Function

Syntax

closeModel → boolean

**Return Value**

The return value has the data type boolean .

Plant Simulation returns false in these cases and does not close the model:

- When you call the function in sub-routines.
- When you call the function in user-defined attributes of data type method .
- When you call the function in formulas.

**Note**

If you want to save your simulation model before you close it, you have to call the function saveModel before calling the function closeModel .

**Note**

If the model is closed, all existing onCloseModel method classes in the Class Library , including the onCloseModel method located in the Basis folder, are called. Within these methods you can execute clean-up tasks, for example delete temporary files.

**Example**

closeModel

See also

Close Model

close3D [SimTalk]

loadModel [SimTalk] - function

saveModel [SimTalk]

##### computeSHA1Hash [SimTalk]

computeSHA1Hash [SimTalk]

Returns the 40-digit SHA1 hash code of the passed text.

Type

Function

Syntax

```simtalk
computeSHA1Hash(Text:string) → string
```

**Parameter**

The parameter Text of data type string designates the string for which you would like to know the hash code.

Return Value

The return value has the data type string .

Example

```simtalk
print computeSHA1Hash("MyText") // returns 0e9e68d9402c96044f0f93194f7010bc2e056752
```

**See also**

computeSHA3Hash [SimTalk]

strHash [SimTalk]

##### computeSHA3Hash [SimTalk]

Returns the SHA3 hash code of the passed text.

Remarks

computeSHA3Hash uses the SHA3-256-algorithm (NIST: FIPS 202).

Type

Function

Syntax

```simtalk
computeSHA3Hash(Text:string) → string
```

**Parameter**

The parameter Text of data type string designates the string for which you would like to know the hash code.

Return Value

The return value has the data type string .

Example

```simtalk
print computeSHA3Hash("MyText") // returns 27acf01aa72d499265cc50388f80054e644640586fb04c3165cd4f86d20e02a8
```

See also

computeSHA1Hash [SimTalk]

strHash [SimTalk]

##### connectAutomatically [SimTalk]

Automatically connects the object designated by &lt;Path&gt; with objects located in its vicinity whose entrances and exits are close together.

**Remarks**

We added this function because creating an object with SimTalk does not automatically connect it.

Plant Simulation proceeds as follows when automatically connecting objects as described below.

**Note**

In a 3D Only model Plant Simulation connects automatically using 3D-coordinates and 3D-sizes, otherwise it uses 2D pixel coordinates.

- It always uses the first connection possible.
- If a connection exists between the respective object and any other object at a particular side ( Entrance or Exit ), Plant Simulation does not add a new connection at the same side.
- If two objects are located close to each other, the automatic connection will be created between the respective object and the object with which the connections was established first .
- Plant Simulation only establishes an automatic connection in 3D, if the bounding boxes overlap in the Z -direction.

**Note**

When automatically connecting objects, Plant Simulation uses the first Connector class in the Class Library , starting at the top.

To change that order, compare Work with Folders, Frames, Objects in the Class Library .

**Note**

The following applies for automatically connecting the length-oriented objects Turnplate , Turntable , AngularConverter , Conveyor , Converter , Track , and TwoLaneTrack in 3D:

If TransferLengthToObject is off for one of these objects in 3D, but if a suitable MU animation path exists, then Plant Simulation uses the start point and the end point of these animation paths for automatically connecting the objects and for displaying Connectors . Suitable MU animation paths are Default or Cross for the Converter , Lane A or Lane B for the TwoLaneTrack and Default for the remaining objects. This applies for Connect Objects Automatically and for the method connectAutomatically .

Type

Function

Syntax

&lt; Path &gt;.connectAutomatically -&gt; boolean

Return Value

The return value has the data type boolean .

Example

MyStation.connectAutomatically

See also

Connect Objects Automatically [model settings]

TransferLengthToObject [SimTalk]

**createCombinations [SimTalk]**

##### createCombinations [SimTalk]

Creates all combinations of the specified Length of the elements array.

Remarks

If a value is contained multiple times in the elements array, the result also contains multiple combinations.

Type

Function

**Syntax**

createCombinations(Elements:integer[], Length:integer) -&gt; integer[]

**Parameters**

- The parameter Elements is an array of data type integer which designates the elements of the array whose length you would like to create.
- The parameter Length of data type integer designates the length of the element designated by the parameter Elements .

**Return Value**

The return value is an array of data type integer .

The number of generated combinations is limited to 1,000,000.

**Examples**

```simtalk
// Creates all combinations with two elements
print createCombinations([1,2,3], 2) // returns [1, 2][1, 3][2, 3]
// Creates all combinations of two colors
var arrString:string[]
var arrInt:integer[]
arrString.append("red")
arrString.append("green")
arrString.append("blue")
arrInt.append(1)
arrInt.append(2)
arrInt.append(3)
var resArr = createCombinations(arrInt, 2)
var colorCombination:string
for var y := 1 to resArr.ydim
	print arrString[resArr[1, y]], ", ", arrString[resArr[2, y]]
next
```

<!-- image -->

**createLicenseFile [SimTalk]**

##### createLicenseFile [SimTalk]

Generates a user-defined license and writes it to a Windows Registry file.

Remarks

You can then send this file to another person to enter the user-defined license into the Registry on the target computer.

You can use the method setRequiredLicense to make a library folder request this license. A simulation model/an object containing such a folder can only be loaded if the license is entered into the Registry and is valid. If you want to always permit loading the model or the object, but only want to permit certain actions when a license is available, you can also request the user-defined license in a method by calling the global function checkForLicense .

If you deactivate the safety setting File &gt; Model Settings &gt; General &gt; Prohibit Access to the Computer , the function createLicenseFile can copy data from another folder and write it to the model folder or its sub-folders. The function cannot copy files from the model folder or its sub-folders.

Type

Function

Syntax

```simtalk
createLicenseFile(Feature:string, Version:string, HostID:string, ExpirationDate:string/date, Password:string, FileName:string[, Restriction:string]) → string
```

**Parameters**

- The parameter Feature of data type string designates the name of the license feature. The name cannot contain blank spaces.
- The parameter Version of data type string designates the version number of the license. The registered version has to be greater than or equal to the requested license. The version number cannot contain blank spaces.
- If, for example, version 10 of the feature is registered, you can request version 9.5.0 but not vice versa.
- The parameter HostID of data type string designates the Host ID of the computer for which the license is valid. If you type in an empty string "" or "any" , the license if valid on all computers. You can query the valid Host IDs of a computer by starting Plant Simulation on the target computer and click Query Host ID under File &gt; Preferences &gt; License .

**Note**

Always use the adapter of the physical LAN port for the Host ID .

**The Host ID can be:**

- A MAC address , which might look like this 300505c9d27c for example
- A Composite Host ID , which might look like this COMPOSITE=93FC21BB758E for example.
- A Sold-To-ID , which might look like this SOLDTO=1234567 for example.

A Sold-To-ID has the advantage that the license is not bound to a certain computer but to the Plant Simulation license of a customer. This means that the license is valid on each computer that requests a Plant Simulation license whose license file has this Sold-To-ID . To query the Sold-To-ID by starting Plant Simulation on the target computer and selecting File &gt; Help &gt; About Plant Simulation . The Host ID may not contain any blank spaces.

- An Enterprise Cloud Account ID , which might look like this ECA=123456789 for example.
- The parameter ExpirationDate of data type string / date designates the expiration date until which the license is valid. If you type in an empty string "" or "permanent" , the license has no expiration date. The date cannot contain blank spaces.
- The parameter Password of data type string designates the secret password.
- The parameter FileName of data type string designates the file name or the file &lt; Path &gt;. The function writes the Registry data for the generated license to this file. The file should have the file extension .reg so that the license can be entered into the Registry on the target computer by double-clicking it.
- The optional parameter Restriction of data type string designates the restriction you want to apply to the license. You can only type in "Application" , "Runtime" , "Simulation" , or "Viewer" . The license will then only be available if the license type of Plant Simulation matches the specified type or a type of lower value. This means that if you restrict the license to "Application" , the license is also available in a Runtime license and a Simulation license of Plant Simulation . User-defined licenses are always available in a Viewer license.

**Return Value**

The return value has the data type string .

It is the SHA-1-Hash for the password. When you call the function checkForLicense , you have to type in this hash. If the hash does not match the hash of the password, the license is considered invalid. We recommend to call the function checkForLicense within an encrypted method so that the function call cannot be removed.

It is practically impossible to extract the password from the hash. If you inadvertently give the unencrypted Method to somebody else, your password will still be unknown. This is important in case you also used the password somewhere else. As you have to type in the password when generating a license with the function checkForLicense no license can be generated using the hash value either.

**Example**

```simtalk
PasswordHash := createLicenseFile("MyLicenseName", "1.0", "COMPOSITE=0ADF1C780F29", "", "abc", "C:\TEMP\license.reg")
```

See also Prohibit Access to the Computer [model settings] Host IDs About Plant Simulation checkForLicense [SimTalk] setRequiredLicense [SimTalk]

##### createPermutations [SimTalk]

Creates all permutations of the specified Length of the elements array.

Remarks

If a value is contained multiple times in the elements array, the result also contains multiple permutations.

Type

Function

**Syntax**

createPermutations(Elements:integer[], Length:integer) -&gt; integer[]

**Parameters**

- The parameter Elements is an array of data type integer which designates the elements of the array whose length you would like to create.
- The parameter Length of data type integer designates the length of the element designated by the parameter Elements .

**Return Value**

The return value is an array of data type integer .

The number of generated permutations is limited to 1,000,000.

**Example**

```simtalk
print createPermutations([1,2,3], 2) // returns [1, 2][1, 3][2, 1][2, 3][3,
```

// Creates all permutations with two elements 1][3, 2]

##### currentEventCtl [SimTalk]

currentEventCtl [SimTalk]

Returns the EventController that controls the current simulation run.

Type

Function

**Syntax**

```simtalk
currentEventCtl → object
```

Return Value

The return value has the data type object .

**Example**

```simtalk
if currentEventCtl /= VOID
	print "simulation running in frame", currentEventCtl.location
	print "simulation running in frame", root
end
```

**See also**

EventController [object]

##### deg2rad [SimTalk]

Converts the specified angle in degrees into the respective angle in radians.

Type

Function

Syntax

```simtalk
deg2rad(AngleInDegrees:real)
-> real
```

**Parameter**

The parameter AngleInDegrees of data type real designates the angle in degrees which you would like to convert into the angle in radians.

Return Value

The return value has the data type real .

Example

```simtalk
print deg2rad(45) // returns 0.785398163397448
```

See also

rad2deg [SimTalk]

deleteAllDebugExpressions [SimTalk]

Deletes all debug expressions in all methods.

Type

Function

Syntax

deleteAllDebugExpressions

Example

deleteAllDebugExpressions

##### deleteFile [SimTalk]

Deletes the specified file for good.

Remarks

You can use deleteFile to delete any file you do not need any longer.

Type

Function

Syntax

```simtalk
deleteFile(FileName:string)
-> integer
```

Parameter

The parameter FileName of data type string designates the file you want to delete.

Return Value

The return value has the data type integer .

Is the Windows error code.

Is 0 if no error occurred.

**Example**

deleteFile("MyFile")              // deletes the file named MyFile from the installation folder deleteFile("D:\Publisher.gif")    // deletes the graphics file from the D drive

enableFullScreenMode [SimTalk]

Activates ( true ) or deactivates ( false ) full screen mode.

Type

Function

Syntax

enableFullScreenMode(Activate:boolean)

Parameter

The parameter Activate of data type boolean activates ( true ) or deactivates ( false ) full screen mode.

Example

enableFullScreenMode(true)

See also

Full Screen [Window ribbon]

##### execute [SimTalk] - function

Receives a string and interprets it as though it were the source code of a method.

Remarks

The function execute accepts all statements. The anonymous identifier ? refers to the Method object that called the execute function. The anonymous identifier @ is received by the calling method.

The function execute runs the referenced Method . Use execute to run Methods that you referenced via variables. Let us say you save a Method to a variable obj of data type object , you can then call this Method using obj.execute .

**Note**

The syntax, which is used in the argument for the execute function, has to be the same as the Method syntax which calls the execute function.

The semantics of execute is as follows:

- If a runtime error occurs while the string method is being executed, there are two possibilities:
- If the setting Ignore Errors in Formulas is deactivated, Plant Simulation opens the Debugger .
- If the setting Ignore Errors in Formulas is activated, the function execute acts like the function executeSilent .
- If no runtime error occurs:
- If the string method does not have a return value, execute returns VOID.
- In all other cases, execute will return the return value of the string method .
- You can also pass parameters to the execute statement .

```simtalk
var objPath : string := "Track"
var attrName: string := "Length"
var attrVal : length := 3.5 execute(to_str(objPath, ".", attrName, ":=", attrVal))
execute("-> integer; return 42") // returns 42
execute("param x, y: integer; print x+y", 1, 2) // outputs 3
```

**Type**

Function

**Syntax**

```simtalk
execute(SourceCode:string[ ,Parameter:parameter, ...])
```

See also

executeSilent [SimTalk]

Ignore

executePythonFile [SimTalk]

Executes the source code of the specified Python file.

Remarks

You can access the objects in your Plant Simulation model in the same way as you would when executing the Python code using a PythonModule .

Type

Function

Syntax

```simtalk
executePythonFile(File:string)
-> boolean
```

Parameter

The parameter File of data type string designates the Python file that contains the source code that you would like to execute.

Return Value

The return value has the data type boolean .

true if no error occurred while executing the source code in the Python file.

false if an error occurred.

**Example**

```simtalk
print executePythonFile("D:\test.py", "TestArg")
```

**See also**

Execute External Python Code

**executeSilent [SimTalk]**

##### executeSilent [SimTalk]

Receives a string and interprets it as though it were the source code of a method.

**Remarks**

The function executeSilent accepts all statements. The anonymous identifier ? refers to the Method object that called the executeSilent function. The anonymous identifier @ is received by the calling method.

The semantics of executeSilent is as follows:

- If the string method does not have a return value, executeSilent returns VOID.
- If the string method has a return value, these may look as follows:
- If the string method contains a syntax error, executeSilent returns VOID.
- If a runtime error occurs while the string method is executed, executeSilent returns the default value of the corresponding type, i.e., the value of a local variable of this type would have at the beginning of the execution of the method. Plant Simulation does not open the Debugger when a runtime error occurs, but continues to be executed.

```simtalk
var objPath : string := "Track"
var attrName: string := "Length"
var attrVal : length := 3.5 executeSilent(to_str(objPath, ".", attrName, ":=", attrVal))
executeSilent("-> integer; 1+") // returns VOID
```

Use the function execute to make Plant Simulation open the Debugger , when runtime errors occur. For example, the executeSilent -statement below returns false because assigning the keyword "if" to the name of an object causes a runtime error.

```simtalk
executeSilent("->boolean; Station.name := \"if\"; return true") // returns false because of a runtime error
```

- In all other cases, executeSilent will return the return value of the string method.
- You can also pass parameters to the executeSilent instruction.

```simtalk
executeSilent("->integer; return := 42") // returns 42
executeSilent("param x, y: integer; print x+y", 1, 2) // returns 3
```

The function executeSilent executes the referenced Method . You can use it to execute Methods that you referenced via variables. Let us say you save a Method to a variable obj of data type object , you can now call this Method using obj.executeSilent .

```simtalk
param obj: object, new_name: string
if not executeSilent("param o: object -> boolean; o.name := \"" + new_name + "\"; return true" obj)
	print "invalid name"
end
```

Be aware that the variant

```simtalk
executeSilent("->boolean; " + obj + ".name := \"" + new_name + "\"; return true")
```

does not work, when obj points to a method.

The syntax which is used in the argument for the executeSilent function has to be the same as the Method syntax which calls the executeSilent function.

Type

Function

Syntax

```simtalk
executeSilent(SourceCode:string[ ,Parameter, ...])
```

See also

execute [SimTalk] - function

##### existsFile [SimTalk]

existsFile [SimTalk]

Returns if a file or folder exists (true) or does not exist (false).

Type

Function

Syntax

```simtalk
existsFile(NameOfFileOrFolder:string) → boolean
```

**Parameter**

The parameter NameOfFileOrFolder of data type string designates the file or the folder.

Return Value

The return value has the data type boolean .

**Examples**

```simtalk
var fileName: string
fileName := "MyDataTable.tab"
if not existsFile(fileName)
	table.writeFile(fileName)
else
	print "The file ",fileName," already exists."
end
print existsFile("noname.mod")
print existsFile("C:\Program Files\Siemens\Tecnomatix Plant Simulation XX\Help\PlantSimulationENU.chm")
```

##### existsMethod [SimTalk]

Returns if a path points to a Method object or to a user-defined attribute of data type method or not.

Type

Function

Syntax

```simtalk
existsMethod(NameOfMethod:string) → boolean
```

Parameter

The parameter NameOfMethod of data type string designates the path of the Method .

Return Value

The return value has the data type boolean .

true if the Method object or the user-defined attribute of data type method exists.

false if it does not exist.

Example

print existsMethod("Station.MethodAttr")

##### existsObject [SimTalk]

existsObject [SimTalk]

Returns if a path to a simulation object is valid or not.

Remarks

The function existsObject cannot access the anonymous identifiers ? , @ , self , and current , which are variables of the Method .

To check if the object named Station exists in the Frame current use:

current.extendPath("Station")

Type

Function

Syntax

```simtalk
existsObject(NameOfObject:string) → boolean
```

Parameter

The parameter NameOfObject of data type string designates the path of the object.

Return Value

The return value has the data type boolean .

true if the object exists.

false if it does not exist.

Examples

```simtalk
print existsObject(".Mus.Part:123")
```

if existsObject("ProdFrame") ProdFrame.derive(current,100,200) end

**See also**

\_3D.existsObject [SimTalk]

extendPath [SimTalk]

**exitApplication [SimTalk]**

##### exitApplication [SimTalk]

Terminates the simulation run and exits Plant Simulation .

Remarks

**Note**

Plant Simulation does not save model data before exiting. Changes to the model or to the simulation data are lost if you do not save the model before, compare the function saveModel . Plant Simulation does not issue a warning or prompt asking you if you really want to exit.

**Note**

You can also define a Method with the name onCloseModel in any folder in the Class Library , including the Basis folder. This Method is being executed when you close the model or when you exit Plant Simulation . You can, for example, program clean-up tasks, delete temporary files, etc.

The method onCloseModel has to declare the boolean parameter onExitApplication . Plant Simulation sets this parameter to false when onCloseModel is called when you close the model. Plant Simulation sets this parameter to true when onCloseModel is called when you exit Plant Simulation .

You can also program several onCloseModel methods and place them into different folders. Plant Simulation then calls all existing onCloseModel method classes in the Class Library when you close the model or exit the application.

Type

Function

Syntax

exitApplication

**Example**

```simtalk
if EventController.time > 36000 saveModel("Variation_IIV") exitApplication
end
```

See also

Exit Application

**saveModel [SimTalk]**

**getCallStack [SimTalk]**

##### getCallStack [SimTalk]

Returns the active call stack, and writes it to a table.

**Remarks**

The first column is of data type string and contains the absolute path of the method.

The second column is of data type integer and contains the row number of the executed SimTalk instruction.

**Note**

If getCallStack is called in a local ErrorHandler , the function returns the call stack of the faulty method and not the call stack of the ErrorHandler .

<!-- image -->

**Syntax**

getCallStack → list

**Return Value**

The return value has the data type list .

**Example**

```simtalk
var tab: table
tab := getcallStack
```

<!-- image -->

See also Tab Call Stack [Watch window] Error Handling setErrorHandler [SimTalk]

**getCommandLineArg [SimTalk]**

##### getCommandLineArg [SimTalk]

Queries if a command-line argument has been passed to Plant Simulation when starting it.

Type

Function

**Syntax**

```simtalk
getCommandLineArg(CommandLineArgument:string, byref Value:string) → boolean
```

**Parameters**

- The parameter CommandLineArgument designates the command-line argument that has been passed to Plant Simulation when starting it.
- If the parameter CommandLineArgument expects a value, you can query this value with the parameter Value .

The local variable Value is always assigned the value of the next specified command-line argument, compare this example.

/NoMessageBox /TrustModels /TestCode true getCommandLineArg("NoMessageBox", Value) -> Value = '/TrustModels' getCommandLineArg("TrustModels", Value)  -> Value = '/ TestCode' getCommandLineArg("TestCode", Value)     -> Value = 'true'

**Note**

If the parameter CommandLineArgument does not expect a value, do not specify the parameter Value or ignore it.

**Return Value**

The return value has the data type boolean .

true if Plant Simulation was started with the specified command-line argument.

false if it was not started with the specified command-line argument.

**Example**

// Suppose we started Plant Simulation with these command-line arguments: // PlantSimulation2504.exe /L Runtime /abc 42 /xyz /myfile "C:\Program Files\a.txt"

```simtalk
var arg: string
if getCommandLineArg("abc", arg)
	print arg // outputs 42 end if getCommandLineArg("myfile", arg)
	print arg // outputs C:\Program Files\a.txt end if getCommandLineArg("xyz", arg)
	print arg // outputs an empty string
end
```

**See also**

**Specifying Start Options**

##### getEpsilon [SimTalk]

getEpsilon [SimTalk]

Returns the value you set for which Plant Simulation considers numerical values to be about equal.

Type

Function

Syntax

```simtalk
getEpsilon → real
```

Return Value

The return value has the data type real .

Example

```simtalk
print getEpsilon // might output 7e-08
```

See also

Tolerance For About Equal (~=) Comparison [model settings]

setEpsilon [SimTalk]

##### getFileModificationDateTime [SimTalk]

Returns the date and the point in time at which the file was last written.

Type

Function

Syntax

```simtalk
getFileModificationDateTime(FilePath:string) → dateTime
```

**Parameter**

The parameter FilePath of data type string designates the path of a file for which you would like to know when it was written to last.

You have to enter the entire file path, including the name of the file and the file extension .spp.

Return Value

The return value has the data type dateTime .

**Example**

```simtalk
print getFileModificationDateTime("D:\MyControls.spp") // might, for example,
return 26.10.2016 14:53:15.7710
```

**getHighResolutionClock [SimTalk]**

##### getHighResolutionClock [SimTalk]

Returns the number of seconds that passed since opening the model.

Remarks

You can use the function to measure extremely short time spans, for example the time which a SimTalk instruction requires.

Type

Function

Syntax

```simtalk
getHighResolutionClock → real
```

**Return Value**

The return value has the data type real .

**Example**

```simtalk
var t1, t2: real
t1 := getHighResolutionClock
var x := sin(t1)
t2 := getHighResolutionClock
print "elapsed time: ", (t2-t1)*1000, " milliseconds"
```

**See also**

processTime [SimTalk]

sysDate [SimTalk]

##### getLibrariesDirectories [SimTalk]

Returns the Libraries Directories which you set in the Preferences .

Type

Function

Syntax

```simtalk
getLibrariesDirectories → string[]
```

Return Value

The return value is an array of data type string .

Example

```simtalk
print getLibrariesDirectories // might
return [D:\MeineBibliotheken\, D:\MyLibraries\]
```

See also

Libraries Directories

##### getLibraryFiles [SimTalk]

getLibraryFiles [SimTalk]

Returns the file paths to .pslib files and all their versions.

Type

Function

**Syntax**

```simtalk
getLibraryFiles(FolderPath:string) → string[]
```

**Parameter**

The parameter FolderPath of data type string is the path of a library folder. The library does not have to exist in the currently loaded model.

Return Value

The return value is an array of data type string .

The return value contains all file paths to .pslib files and all versions. The array always contains a files path and the associated library version alternating. The array is sorted in descending order according to version number.

The returned array is empty if no .pslib file is found for the library.

**Example**

```simtalk
var arr:
string[] := getLibraryFiles(".Tools.ExperimentManager")
print "Number of library files: ", arr.dim / 2
print "Newest file: ", when arr.dim > 0 then arr[1] else "(not found)"
var i : integer := 1
while i < arr.dim
	print "File: ", arr[i], "  Version: ", arr[i+1]
	i += 2
end
```

getLibraryVersionFromFile [SimTalk]

Returns the version of the library designated by &lt;Path&gt;.

Type

Function

Syntax

&lt; Path &gt;.getLibraryVersionFromFile(FilePath:string) → string

Parameter

The parameter FilePath of data type string has to be the path to a library file (.pslib).

Return Value

The return value has the data type string .

Example

print getLibraryVersionFromFile("C:\Program Files\Siemens\Plant Simulation 2504\Libraries\Tools\MyLibrary.pslib")

See also

getLibraryInfo [SimTalk]

getLogFile [SimTalk]

getLogFile [SimTalk]

Gets the log file into which Plant Simulation wrote all messages which were output to the Console .

Type

Function

Syntax

```simtalk
getLogFile → string
```

Return Value

The return value has the data type string .

Example

getLogFile

See also

clearLogFile [SimTalk]

Specifying Start Options

getProfileCallCycles [SimTalk]

Returns a JSON object containing the call cycles that Profiler collected provided it is activated.

Type

Function

Syntax

```simtalk
getProfileCallCycles([getProfileCallCycles:integer])
-> json
```

**Parameter**

The optional parameter MaxNumCycles of data type integer restricts the amount of call cycles which getProfileCallCycles returns.

To return all call cycles, do not specify the parameter. The amount of returned data can be very large and that the call can take a long time to finish.

Return Value

The return value has the data type json .

**Example**

print getProfileCallCycles(10)

**See also**

Activate Profiler

profiler [SimTalk]

Activate Profiler getSeedTable [SimTalk]

Returns the active Random Number Seed Values table .

Remarks

The first column contains the random number seed values ( integer ).

The second column contains the comments to the random number seed values ( string ). The number of the row matches the number of the random number stream.

**Note**

The seed values only apply to the distribution functions , such as z\_uniform , z\_normal , etc.

Type

Function

Syntax

```simtalk
getSeedTable → table
```

Return Value

The return value has the data type table .

Example

```simtalk
localseedtable := getSeedTable
```

See also

setSeedTable [SimTalk]

resetRandomNumberStream [SimTalk]

Random Number Seed Values

Distribution Functions, z\_ functions

##### getStandardColor [SimTalk]

Returns the specified color value from a standard color palette.

Remarks

You can, for example, use getStandardColor in the Entrance Control of the Source to assign different colors to the produced MUs .

Type

Function

Syntax

getStandardColor(Index:integer) -&gt; integer

**Parameter**

The parameter Index of data type integer specifies one of 30 color values of a standard color palette.

Return Value

The return value has the data type integer .

**Example**

```simtalk
-- Entrance control of a Source object
@._3D.MaterialDiffuseColor = getStandardColor(z_uniform(1,30) -- Assigns a random color to the created part
```

**hideBBL [SimTalk]**

##### hideBBL [SimTalk]

Minimizes Plant Simulation to an icon in the status area of the taskbar.

Type

Function

**Syntax**

```simtalk
hideBBL(MinimizeWindow:boolean[, HideWindow:boolean]) → boolean
```

**Parameters**

- Setting the parameter MinimizeWindow of data type boolean to true minimizes Plant Simulation into the taskbar status area. The application window can be restored by double-clicking the icon in the status area of the taskbar.

Setting the parameter to false restores the application window (if it has been minimized to the status area of the taskbar).

**Note**

The parameter HideWindow of data type boolean is optional and only relevant, when the parameter boolean has the value true .

- Setting the parameter HideWindow of data type boolean to true hides the application window without showing an icon status area of the taskbar, so the user cannot restore the application window.

Setting the parameter to false shows an icon in the status area of the taskbar, when Plant Simulation is minimized in the status area of the taskbar. This is the default.

**Return Value**

The return value has the data type boolean .

**Example**

hideBBL(true) // hides the Plant Simulation window

**See also**

Specifying Start Options , -hideBBL

##### isComputerAccessPermitted [SimTalk]

Returns if access to the computer is permitted for the executed Method (true) or not (false).

Remarks

Access can be denied for these two reasons:

- Access is prohibited under Model Settings &gt; General &gt; Prohibit Access to the Computer .
- The executed Method belongs to a library and access is prohibited for this library. You find this setting under Edit Library Information &gt; Prohibit Access to the Computer .

Type

Function

Syntax

isComputerAccessPermitted → boolean

Return Value

The return value has the data type boolean .

Example

print isComputerAccessPermitted

See also

Model Settings &gt; Prohibit Access to the Computer [model settings]

Edit Library Information &gt; Prohibit Access to the Computer [Make Library]

**isSet [SimTalk]**

##### isSet [SimTalk]

Returns if the value of a built-in attribute in Plant Simulation is set (true ) or not (false).

Remarks

Examples for such attributes are the values of the drop-down lists in the dialogs of the objects. You can also access these settings in the window Show Attributes and Methods by double-clicking the respective attribute and selecting a value in the drop-down list.

<!-- image -->

The attribute ResourceType of the material flow objects can, for example, take the values Production/ Produktion , Transport/Transport , or Storage/Lagerung , depending on the model language and the setting you selected for Display Down-list Boxes in the SimTalk Language of the Model .

Type

Function

Syntax

<!-- image -->

Parameter

The parameter ValueOfTheAttribute of data type string designates the value of the attribute.

Return Value

The return value has the data type boolean .

**Example**

```simtalk
print MyStation.ResourceType // the value is Storage, outputs Storage or Lagerung in the Console
print MyStation.ResourceType.isSet("Storage") // checks, independent of the model language, if the value is Storage or Lagerung
```

**See also**

putValuesIntoTable [SimTalk] - function

Model Language [model settings]

Display Down-list Boxes in the SimTalk Language of the Model

##### keepWindowsAlwaysOnTop [SimTalk]

Sets if Plant Simulation windows will always appear on top of all open windows on the screen or not.

Type

Function

Syntax

keepWindowsAlwaysOnTop(WindowInForeground:boolean)

**Parameter**

The parameter WindowInForeground of data type boolean sets if Plant Simulation windows will always appear on top of all open windows on the screen ( true ) or not ( false ).

**Example**

keepWindowsAlwaysOnTop(true)

##### language [SimTalk]

Returns the model language which you selected under File &gt; Model Settings/Preferences &gt; General &gt; Model Language .

Remarks

Use language to show language-specific messages.

Type

Function

Syntax

```simtalk
language → integer
```

Return Value

The return value has the data type integer .

The return value 0 designates German , 1 designates English , 2 designates Japanese , 3 designates Chinese , and 8 designates Hungarian .

Example

print language

See also

userInterfaceLanguage [SimTalk]

Model Language [preferences]

Model Language [model settings]

**licenseName [SimTalk]**

##### licenseName [SimTalk]

Returns the name of the active Plant Simulation license.

Type

Function

Syntax

```simtalk
licenseName → string
```

**Return Value**

The return value has the data type string .

| This license                  | Returns this value   |
|-------------------------------|----------------------|
| Professional                  | EMPLANT_PRO          |
| Plant Simulation X Advanced   | EMPLANT_PRO          |
| Standard                      | EMPLANT_STD          |
| Plant Simulation X Standard   | EMPLANT_STD          |
| Foundation                    | EMPLANT_FND          |
| Plant Simulation X Essentials | EMPLANT_FND          |
| Application                   | EMPLANT_APP          |
| Runtime                       | EMPLANT_RUN          |
| Plant Simulation X Runtime    | EMPLANT_RUN          |
| Research                      | EMPLANT_RES          |
| Educational                   | EMPLANT_EDU          |
| Student                       | EMPLANT_STUDENT      |
| Simulation                    | EMPLANT_SIM          |
| Viewer                        | EMPLANT_VIEW         |

**Example**

```simtalk
print licenseName -- might
return EMPLANT_PRO
```

**See also Start Plant Simulation with Different Kinds of Licenses Features of the Individual Licenses Plant Simulation License Types**

##### loadModel [SimTalk] - function

loadModel [SimTalk] - function

Loads the specified simulation model.

Remarks

If you cleared the security setting File &gt; Model Settings &gt; General &gt; Prohibit Access to the Computer , the function can copy data from another folder and write it to the model folder or its sub-folders. It cannot copy data from the model folder or its sub-folders.

Type

Function

Syntax

```simtalk
loadModel(ModelName:string[, Password:string]) → boolean
```

**Parameters**

- The parameter ModelName of data type string designates the path of the simulation model.
- The optional parameter Password of data type string designates the password that is used for opening an encrypted model file.

**Note**

The function only works if no model is loaded at the moment. Typically, you will use the function directly after a call of the function closeModel or from external interfaces, such as the COM interface .

Return Value

The return value has the data type boolean .

**Examples**

closeModel loadModel("C:\MySimulationData\myModel.spp", "MyPassword123")

closeModel loadModel("D:\MyModels\MyFolderModel.psfm\$.spp")

**See also**

Prohibit Access to the Computer [model settings]

Open Model File Save As &gt; Folder Model closeModel [SimTalk] - global function saveFolderModel [SimTalk] saveModel [SimTalk]

##### makePathRelative [SimTalk]

makePathRelative [SimTalk]

Converts an absolute path to a relative path.

Type

Function

**Syntax**

```simtalk
makePathRelative(Path:string[, StartObject:object]) → string makePathRelative(Path:object[, StartObject:object]) → string
```

**Parameters**

- The parameter Path of data type string or object designates the path.

Plant Simulation converts this path into a relative path starting with the Frame in which the Method is located.

- The optional parameter StartObject of data type object sets the object from which on Plant Simulation starts evaluating the Path .

Return Value

The return value has the data type string .

Is an empty string "" if the path is not valid.

**Example**

```simtalk
Station.ExitCtrl := makePathRelative(Station.ExitCtrl)
```

**See also**

The Absolute Path

The Relative Path

##### makeRGBValue [SimTalk]

Generates the RGB color values of the specified color.

**Remarks**

You can use the RGB values in the methods drawEllipse , drawLine , drawRectangle and drawText , the attribute BackgroundColor and the attribute Color of the objects Connector , Variable , Comment , and Display designated by &lt;Path&gt; to efficiently define colors.

Type

Function

Syntax

&lt; Path &gt;.makeRGBValue(Red:integer, Green:integer, Blue:integer) → integer

**Parameters**

- The parameter Red of data type integer designates its red component of the color.
- The parameter Green of data type integer designates its green component.
- The parameter Blue of data type integer designates its blue component.

You can specify an integer number between 0 and 255 .

Instead of directly typing the values for the color components into the source code of the Method , you can also press Ctrl and the spacebar to open the dialog Colors . Then, select the color in the dialog, and click OK . Plant Simulation then inserts the color values into the method.

<!-- image -->

If you already defined a color by setting its color values, Plant Simulation recognizes it, selects it in the dialog Colors , and transfers its values for red, green, and blue into the source code of your Method .

Compare this example:

```simtalk
var rgb: integer := makeRGBValue(0,0,255)
```

If you hold down Ctrl and press the spacebar in the Method Editor , Plant Simulation recognizes the color values, and selects the color blue in the dialog Colors .

If you then select the color red in the dialog Colors , for example, and click OK , Plant Simulation automatically enters the color values of the color red into the source code of your Method , namely:

```simtalk
var rgb : integer := makeRGBValue(255,0,0)
```

**Return Value**

The return value has the data type integer .

**Example**

```simtalk
.Models.Model.BackgroundColor.Color := makeRGBValue(110,0,200) .Models.Model.Connector.Color := makeRGBValue(100,0,200) .Models.Model.Comment.Color := makeRGBValue(110,0,200) .Models.Model.Display.Color := makeRGBValue(110,0,200) .Models.Model.&Variable.Color := makeRGBValue(110,0,200)
```

**See also**

drawEllipse [SimTalk]

drawLine [SimTalk]

drawRectangle [SimTalk]

drawText [SimTalk]

BackgroundColor [SimTalk] - Frame

Color [SimTalk] - Connector

##### messageBox [SimTalk]

Shows a message box provided by the operating system.

**Remarks**

Instead of directly typing the text and the numbers into the source code of the method, you can also press Ctrl and the spacebar to open the dialog MessageBox Settings . Then, type in the message text, select the button combinations, and the symbol, and click OK .

<!-- image -->

In the screenshot below Plant Simulation shows the string My message text, my text … , which we entered. The number 50 designates the button combination Yes No Cancel , and the number 3 shows the yellow triangle with the exclamation mark.

**messageBox [SimTalk]**

**Type**

Function

Syntax

<!-- image -->

**Parameters**

- The parameter Text of data type string designates the text, which you are going to show. Type in the text, which you want to show in the title bar of the dialog, between two vertical bars, for example messageBox("|My Company|This is a message.") .

<!-- image -->

To insert a line break into your text, type in strChr(10) , for example messageBox("My message text," + strChr(10) + "my text, ...") .

<!-- image -->

<!-- image -->

- The optional parameter Buttons of data type real designates these buttons:
- 1 the OK button
- 3 the button combination OK, Cancel
- 10 the button combination Repeat, Retry, Cancel
- 48 the button combination Yes, No
- 50 the button combination Yes, No, Cancel
- 76 the button combination Abort, Retry, Ignore

If you do not enter a value for the parameter Buttons , the message box only shows the OK button.

- The optional parameter Icons of data type real designates these icons:
- 0 no icon
- 1 an error
- 2 the question mark
- 3 the exclamation mark
- 4 Info

If you do not enter a value for the parameter Icons , the message box shows the exclamation mark .

Plant Simulation recognizes parameters, which you already defined, and offers this selection in the dialog MessageBox Parameters . When you change any of the parameters here, Plant Simulation transfers your changed settings to the source code of the Method and applies them.

**Return Value**

The return value has the data type integer .

The return value tells you which button/button combinations the user clicked.

|   Return Value | stands for   |
|----------------|--------------|
|              1 | OK           |
|              2 | Cancel       |
|              4 | Ignore       |
|              4 | Continue     |
|              8 | Retry        |
|              8 | Try Again    |

**messageBox [SimTalk]**

|   Return Value | stands for   |
|----------------|--------------|
|             16 | Yes          |
|             32 | No           |

**Examples**

```simtalk
switch messageBox("My message text, my text ... ",50, 3)
case 16
	print "Yes"
case 32
	print "No"
else
	print "Cancel"
end
```

messageBox("|My Company|This is a message.") // shows My Company in the title bar modelFile [SimTalk]

Returns the name of the active model file and the folder within which it is located.

Type

Function

Syntax

```simtalk
modelFile → string
```

Return Value

The return value has the data type string .

Example

```simtalk
print modelFile // outputs for example D:\Public\Plant Models\MyPlantAnytown.spp
```

See also

Open Model File

saveModel [SimTalk]

##### numOfLimitedObjects [SimTalk]

Counts all of the built-in objects which are contained in the entire model.

**Remarks**

numOfLimitedObject does not count Lists and Tables , Methods , Variables , Comments , MUs , Connectors , Interfaces , EventControllers , the Toolbar , Folders , and Class objects .

You might want to know this number if you are working with a Plant Simulation Standard License which is limited to 4000 objects.

For licenses, which limit the number of objects you can use, the root object Basis in the Class Library shows how many objects are used and how many are allowed for the license you are using at the moment.

For the Student license it might look like this. Our simulation model contains our Frame named Model and 10 objects which we inserted into it. 80 is the maximum number of objects which are allowed in the Student license .

<!-- image -->

Type

Function

Syntax

numOfLimitedObjects → integer Return Value The return value has the data type integer .

Example

print numOfLimitedObjects // returns 10 for the above model

See also

Console

Console Filter

Start Plant Simulation with Different Kinds of Licenses

NumberOfLimitedObjects [SimTalk] of the Frame openColorSelectBox [SimTalk]

Opens the dialog Colors provided by Windows.

Remarks

The dialog looks like this:

<!-- image -->

Type

Function

Syntax

<!-- image -->

**Parameter**

The parameter Color of data type integer designates the active color value. Typically this will be a color which you define with the function makeRGBValue .

Return Value

The return value has the data type integer .

The return value is the RGB color value of the color selected by the user.

**Example**

```simtalk
colorVar := openColorSelectBox(colorVar) openColorSelectBox(makeRGBValue(255,150,0)) // current color is orange
```

**See also**

makeRGBValue [SimTalk]

openConsole [SimTalk]

Opens the Console window .

Type

Function

Syntax

openConsole → boolean

Return Value

The return value has the data type boolean .

Example

openConsole

See also

Console

clearConsole [SimTalk]

closeConsole [SimTalk]

setConsoleFilter [SimTalk]

Specifying Start Options

##### openDateSelectBox [SimTalk]

Opens a dialog in which you can select a date.

**Remarks**

To set the date you select, click OK . If you close the dialog with the Close button in the title bar, Plant Simulation returns 1900/01/01, the first of January, 1900.

<!-- image -->

**Type**

Function

**Syntax**

<!-- image -->

**Parameters**

- The parameter TitleText of data type string designates the caption that the dialog shows in its title bar.
- The optional parameter InitialDate of data type date sets the date you select in the dialog.

**openDateSelectBox [SimTalk]**

**Return Value**

The return value has the data type date .

The return value is the date that the user picked.

**Examples**

```simtalk
openDateSelectBox("Select a date")
print openDateSelectBox("Select a date") // returns 2024/05/18
openDateSelectBox("Select a date", str_to_date("2024-05-18"))
print openDateSelectBox("Select a date") // returns 2024/05/18
```

##### openHTMLBrowser [SimTalk]

Starts the HTML Browser and opens the address designated by the parameter of data type string .

Remarks

To make the HTML Browser open a connection to the local calling Plant Simulation process, type an L or a forward slash / as the first character of the address.

URLs that begin with L/ only work when the web server has been started.

The safety setting File &gt; Model Settings &gt; General &gt; Prohibit Access to the Computer affects the function openHTMLBrowser as follows:

- It permits only URLs with the protocols http, https, file, UNC paths and normal paths into the file system.
- It does not permit references to executable files for paths into the file system. For Plant Simulation executable files are files whose file extension is listed in the environment variable

PATH\_EXT.

- For paths to files it only permits those paths that point to the model folder or its sub-folders.

Type

Function

Syntax

```simtalk
openHTMLBrowser(WWWAddress:string) → string
```

**Parameter**

The parameter WWWAddress of data type string designates the address to be opened.

Return Value

The return value has the data type string .

Examples

openHTMLBrowser("https://www.siemens.com/global/en.html")

openHTMLBrowser("https://www.siemens.com/global/de.html")

**See also**

**Prohibit Access to the Computer [model settings]**

##### openHTMLWindow [SimTalk]

Opens a browser window without the properties of a normal HTML browser window.

**Remarks**

The safety setting File &gt; Model Settings &gt; General &gt; Prohibit Access to the Computer affects the function openHTMLWindow as follows:

- It permits only URLs with the protocols http, https, file, UNC paths, and normal paths into the file system.
- It does not permit references to executable files for paths into the file system.
- For Plant Simulation executable files are files whose file extension is listed in the environment variable

PATH\_EXT.

- For paths to files it only permits those paths that point to the model folder or its sub-folders.

Microsoft Edge WebView2 can display documents in pdf (Portable Document Format) format. Provided Microsoft Edge WebView2 Runtime is installed on your computer, openHTMLWindow will show pdf documents directly in Plant Simulation .

Type

Function

Syntax

```simtalk
openHTMLWindow(Address:string, WindowTitle:string, X:integer, Y:integer, Width:integer, Height:integer) → boolean
```

**Parameters**

- The parameter Address of data type string designates the address of the browser window.
- The parameter WindowTitle of data type string designates the title of the window.
- The parameter X of data type integer designates the x-coordinate at which the window opens on screen.
- The parameter Y of data type integer designates the y-coordinate at which the window opens on screen.
- The parameter Width of data type integer designates the width of the window.
- The parameter Height of data type integer designates the height of the window.

**Return Value**

The return value has the data type boolean .

**Examples**

openHTMLWindow("C:\Temp\mysite.htm", "My Page", 200,400,200,300)

openHTMLWindow("C:\Temp\document.pdf", "My pdf document", 200,400,200,300)

**See also**

Prohibit Access to the Computer [model settings]

closeHTMLWindow [SimTalk]

openObjectSelectBox [SimTalk]

Opens the dialog Select Object .

Remarks

The dialog Select Object looks like this:

<!-- image -->

Type

Function

Syntax

<!-- image -->

**Parameters**

- The parameter Filter of data type string designates the filter, i.e., the objects which the list box below Objects shows.
- Specify an empty string "" to show all objects.
- Specify the InternalClassType to only show objects of that type.

<!-- image -->

##### openObjectSelectBox [SimTalk]

- Specify ":Table" to only show lists and tables.
- Specify ":MatCarrier" to only show material flow objects.
- Specify ":Importer" to only show material flow objects that have importers .

You can also enter several of these object types separated by colons.

**Note**

The internal identifiers for the classes are case-sensitive.

- The parameter FrameOrFolder of data type object designates the Frame or the folder for which the dialog Select Object will be initially opened.

**Return Value**

The return value has the data type string .

**Examples**

```simtalk
var path := openObjectSelectBox("Station", current) // only shows the objects of type Station in the 'Select Object' dialog
```

// which are inserted into the simulation model

```simtalk
var path2 := openObjectSelectBox(":Table", .InformationFlow) // shows all lists and tables in the 'Select Object' dialog
```

**See also**

Select Object [for controls]

InternalClassType [SimTalk]

processTime [SimTalk]

Returns the CPU time, which Plant Simulation used, in seconds.

Type

Function

Syntax

processTime -&gt; real

Return Value

The return value has the data type real .

The return value has a resolution of several milliseconds.

Example

print processTime

See also

getHighResolutionClock [SimTalk]

sysDate [SimTalk]

##### profiler [SimTalk]

profiler [SimTalk]

Activates or deactivates the Profiler .

Remarks

While it is active, it continuously collects information pertaining to the frequency of calls and the runtime of methods.

Type

Function

Syntax

```simtalk
profiler(Activate:boolean)
```

**Parameter**

The parameter Activate of data type boolean activates ( true ) or deactivates ( false ) the Profiler .

**Example**

profiler(true) // activate Profiler

**See also**

| Activate Profiler           | getProfileCallCycles [SimTalk]   |
|-----------------------------|----------------------------------|
| Show Profiler Data [button] | resetProfile [SimTalk]           |
| Reset Profiler              | saveProfile [SimTalk]            |

##### putValuesIntoTable [SimTalk] - function

Writes the values of an attribute of data type string , which can only take certain values predefined in Plant Simulation , into a table.

**Remarks**

Examples for such attributes are the values of the drop-down lists in the dialogs of the objects. You can also access these settings in the window Show Attributes and Methods by double-clicking the respective attribute and selecting a value in the drop-down list.

<!-- image -->

The attribute ResourceType of the material flow objects can, for example, take the values Production/ Produktion , Transport/Transport , or Storage/Lagerung , depending on the Model Language and the setting you selected for Display Down-list Boxes in the SimTalk Language of the Model .

The function returns the values according to the Model Language you selected and which you can also query with the function language .

Type

Function

Syntax

putValuesIntoTable(TargetTable:table)

**Parameter**

The parameter TargetTable of data type table designates the target table.

**Example**

```simtalk
var lst: list[string]
lst.create
MyStation.ResourceType.putValuesIntoTable(lst)
MyDialog.setList("My drop-down list box",lst)
```

The result looks like this after the values have been filled into the drop-down list:

<!-- image -->

**Note**

You can query if the value, which you enter, is selected without having to query the selected model language with the function isSet .

See also

Show Attributes and Methods [described]

ResourceType [SimTalk]

Display Down-list Boxes in the SimTalk Language of the Model

Model Language [model settings]

language [SimTalk]

isSet [SimTalk]

##### rad2deg [SimTalk]

Converts the specified angle in radians into the respective angle in degrees.

Title

Function

Syntax

```simtalk
rad2deg(AngleInRadians:real)
-> real
```

**Parameter**

The parameter AngleInRadians of data type real designates the angle in radians which you would like to convert into the angle in degrees.

Return Value

The return value has the data type real .

Example

```simtalk
print rad2deg(0.785398163397448) // returns 45
```

See also

deg2rad [SimTalk]

##### readStringFromFile [SimTalk]

readStringFromFile [SimTalk]

Reads the entire contents of the file and returns it as a value of data type string .

Remarks

If the file starts with a BOM (Byte Order Mark), it will be evaluated and not returned as part of the string.

Type

Function

Syntax

```simtalk
readStringFromFile(FileName:string)
-> string
```

Parameter

The parameter FileName of data type string designates the file whose contents you would like to read.

Return Value

The return value has the data type string .

Example

```simtalk
var s: string := readStringFromFile(ApplicationHome + "Templates\English\Interaction\Interaction_connect.txt")
print s
```

**See also**

writeStringToFile [SimTalk]

bytes\_to\_str [SimTalk]

##### resetProfile [SimTalk]

Deletes all data collected by the Profiler up until the time at which you reset the model.

Remarks

Call this function before activating the Profiler to only record valid data for the active simulation run.

Type

Function

Syntax

resetProfile

**Example**

resetProfile

**See also**

| Activate Profiler           | profiler [SimTalk]    |
|-----------------------------|-----------------------|
| Show Profiler Data [button] | saveProfile [SimTalk] |
| Reset Profiler              |                       |

resetRandomNumberStream [SimTalk]

Resets a random number stream for the distribution function , such as z\_uniform , z\_normal , etc.

Remarks

Each of the material flow objects automatically uses a random number stream of its own. You can set that random number stream with the attribute RandomSeed . You cannot access the random number streams of the objects with resetRandomNumberStream though. The random number stream, that the function passes, refers to the distribution function , such as z\_uniform , z\_normal , etc.

Type

Function

Syntax

resetRandomNumberStream(Stream:integer)

Parameter

The parameter Stream of data type integer designates the random number stream.

Example

resetRandomNumberStream(5)

See also

Distribution Functions, z\_ functions

RandomSeed [SimTalk] - material flow objects

Random Number Seed Values

setRandomSeedCounter [SimTalk]

setSeedTable [SimTalk]

getSeedTable [SimTalk]

##### saveFolderModel [SimTalk]

Saves the simulation model in a folder/file structure which facilitates storing your model in a version control system such as Git .

Type

Function

Syntax

```simtalk
saveFolderModel(FileName:string[, CompactFormat:boolean:=false, UseGit:boolean:=false])
```

**Parameters**

- The parameter FileName of data type string sets the path to and the name of the model.
- The optional parameter CompactFormat of data type boolean sets if Plant Simulation saves the objects inside of Frames , which have an origin, to an individual .yaml file ( true ) or not ( false ).

For the default setting false all the objects are saved into the $.yaml file of the Frame . This reduces the number of files stored in the file system. This can be important for very large models to get a reasonable performance.

**Default Value of the Parameter**

The default value is false.

- The optional parameter UseGit of data type boolean sets if Plant Simulation creates a Git repository when the folder model is saved for the first time ( true ) or not ( false ).

The initial version will be committed automatically. This option is only available if Git is installed on your computer. In addition a .gitignore file is created in the top level folder. The content of this file ignores the .UserSettings.yaml so that it is not put under version control.

**Default Value of the Parameter**

The default value is false.

**Git Commit Support**

When you save a model as a folder model, you can set with the registry key

FolderModelCommitCommand of type String Value which command will be called when saving the model.

Create the registry key either under HKEY\_CURRENT\_USER\Software\Siemens\Tecnomatix Plant Simulation 2504 or under HKEY\_LOCAL\_MACHINE\Software\Siemens\Tecnomatix Plant Simulation 2504 .

If the registry key exists, TortoiseGit will be started. If the registry key does not exist, TortoiseGit will not be started.

To never open the Commit dialog when saving the simulation model, enter an empty String "" .

If you are using another source control system than Git , enter the path to that source control system as the Value data .

**Example**

saveFolderModel("D:\MyModels\MyDeportioner.psfm", true, true)

See also

Save As &gt; Folder Model

loadModel [SimTalk] - function

##### saveModel [SimTalk]

Saves the current model with the file name you specify.

Remarks

If the file name does not specify a directory, Plant Simulation saves the model into the current directory which you can set with the function setCurrentDirectory .

If you did not set the current directory, it will be the directory into which you last saved a Plant Simulation model or a Plant Simulation item (icon, data table, etc.).

The method modelFile returns the current name of the model and the current folder of the model file.

**Note**

If you call the function saveModel within a formula or within an executeSilent command, Plant Simulation does not save any call chains into the model. This means that it does not save the currently called Method or the already scheduled Methods nor suspended Methods .

If you deactivate the safety setting File &gt; Model Settings &gt; General &gt; Prohibit Access to the Computer , the function saveModel can copy data from another folder and write them to the model folder or its sub-folders. The function cannot copy files from the model folder or its sub-folders.

Type

Function

Syntax

```simtalk
saveModel(ModelName:string[, StopMethodExecution:boolean[, UseNewName:boolean[, SaveCallChains:boolean]]]) → boolean
```

**Parameters**

- The parameter ModelName of data type string designates the name of the model file. This can be a fully qualified path.
- The optional parameter StopMethodExecution of data type boolean sets if Plant Simulation stops executing methods ( true ) or if method execution will be continued ( false ) after loading the model. If method execution is stopped, Plant Simulation opens the Method Debugger and highlights the line after the saveModel instruction. The default setting is false .

The simulation is stopped in both cases after loading the model. The parameter StopMethodExecution of data type boolean only affects method execution.

**saveModel [SimTalk]**

- The optional parameter UseNewName of data type boolean sets if the current model is to use the file name designated by the parameter of data type string ( true ), or if the model is to keep its name ( false ).

**Default Value of the Parameter**

The default value is true.

- The optional parameter SaveCallChains of data type boolean sets if all call chains in the model file are going to be saved ( true ) or not ( false ).

When you specify false Plant Simulation does not save the Methods being executed at the moment and suspended Methods .

**Default Value of the Parameter**

The default value is true.

Return Value

The return value has the data type boolean .

**Example**

```simtalk
print saveModel("C:\Temp\MyModel1.spp", false)
if not EventController.isRunning // was the model just loaded? if messageBox("Continue the simulation?",48,2) = 16 // Yes? EventController.start
end
end
```

**See also**

Prohibit Access to the Computer [model settings]

Save Model File

setCurrentDirectory [SimTalk]

closeModel [SimTalk] - global function

loadModel [SimTalk] - function

modelFile [SimTalk]

##### saveProfile [SimTalk]

Saves all data collected by the Profiler to the designated file. Any existing contents of the file will be overwritten.

Remarks

You can print this file or load it into a Method object.

If you deactivate the safety setting File &gt; Model Settings &gt; General &gt; Prohibit Access to the Computer , the function saveProfile can copy data from another folder and write them to the model folder or its sub-folders. The function cannot copy files from the model folder or its sub-folders.

Type

Function

Syntax

```simtalk
saveProfile(FileName:string[, IncludeTop50CallCycles:boolean]) → boolean
```

**Parameters**

- The parameter FileName of data type string designates the path to the file. Any existing content of the file will be overwritten.
- The optional parameter IncludeTop50CallCycles of data type boolean sets if the Top 50 Call Cycles will be written to the file ( true ) or not ( false ).

Return Value

The return value has the data type boolean .

**Example**

saveProfile("C:\Users\Jeff\MyRun1.txt")

**See also**

| Prohibit Access to the Computer [model settings]   | Top 50 Call Cycles   |
|----------------------------------------------------|----------------------|
| Activate Profiler                                  | profiler [SimTalk]   |

| Show Profiler Data [button]   | resetProfile [SimTalk]   |
|-------------------------------|--------------------------|
| Reset Profiler                |                          |

##### sendSMTPMail [SimTalk]

Sends an e-mail via the denoted mail server to the designated address.

**Remarks**

If you deactivate the safety setting File &gt; Model Settings &gt; General &gt; Prohibit Access to the Computer , Plant Simulation does not execute the function sendSMTPMail and shows an error message.

Type

Function

Syntax

```simtalk
sendSMTPMail(Mail-Server:string, Receiver:string, Subject:string, MessageText:string)
```

**Parameters**

- The parameter Mail-Server of data type string designates the mail server.
- The parameter Receiver of data type string designates the receiver of the mail.
- The parameter Subject of data type string designates the subject of the mail.
- The parameter MessageText of data type string designates the message text of the mail.

**Example**

sendSMTPMail("mail.company.com", "John.Smith@abc.org", "Test", "Hello John, the smoke test was successful.")

**See also**

Prohibit Access to the Computer [model settings]

setAnimationRefreshRate [SimTalk]

Sets how often Plant Simulation refreshes the graphics in your simulation model per second.

Remarks

You can specify a number between 1 and 100 .

Depending on your model a lower number may lead to a higher simulation speed. A higher number results in a smooth animation which may decrease the simulation speed.

Type

Function

Syntax

setAnimationRefreshRate(RefreshRate:integer) → integer

Parameter

The parameter RefreshRate of data type integer designates the refresh rate.

Return Value

The return value has the data type integer .

Example

setAnimationRefreshRate(50)

See also

Frame Rate [preferences]

##### setAntitheticRandomNumbers [SimTalk]

Sets if Plant Simulation uses antithetic random numbers ( true ) or normal random numbers ( false ).

Type

Function

Syntax

setAntitheticRandomNumbers(AntitheticRandomNumbers:boolean) → boolean

Parameter

The parameter AntitheticRandomNumbers of data type boolean sets if Plant Simulation uses antithetic random numbers ( true ) or normal random numbers ( false ).

Return Value

The return value has the data type boolean .

The return value shows the previous setting.

Example

setAntitheticRandomNumbers(true)

See also

Antithetic Random Numbers

**setConsoleFilter [SimTalk]**

##### setConsoleFilter [SimTalk]

Sets if the Console activates the designated filters or not.

Type

Function

Syntax

```simtalk
setConsoleFilter(Filter:string, Activate:boolean) → boolean
```

**Parameters**

- The parameter Filter of data type string designates the filter.
- ◦ Info : Information about the model without user input.
- Message : Information with user input from dialog windows and message boxes.
- Print : Information from print commands in Methods .
- Debug : Internal program messages for our software engineers.

You can also enter several filters, separated by the pipe symbol |.

- The parameter Activate of data type boolean sets if the filter will be activated ( true ) tor not ( false ).

**Return Value**

The return value has the data type boolean .

**Example**

setConsoleFilter("Info|Message|Debug", false)

**SimTalk**

clearConsole [SimTalk]

closeConsole [SimTalk]

openConsole [SimTalk]

See also

Console Console Filter Specifying Start Options , -logfile &lt;file name&gt; , for example -logfile MyLogFile.txt Specifying Start Options , -NoWarning

**setEpsilon [SimTalk]**

##### setEpsilon [SimTalk]

Sets the value for which Plant Simulation considers numerical values to be about equal.

Type

Function

**Syntax**

```simtalk
setEpsilon(Value:real) → real
```

**Parameter**

The parameter Value of data type real designates the value.

**Note**

Use the about equal comparison to prevent rounding errors when using real values.

Specify print (1/3+1000-1000)*3 and see which number your computer returns.

**Return Value**

The return value has the data type real .

**Example**

```simtalk
setEpsilon(0.0001)
var a : real := 1.0003
var b : real := 1.00003
if a ~= 1.0  // this condition is false print "a is about equal to 1"
end
if b ~= 1.0  // this condition is true print "b is about equal to 1"
end
```

**See also**

Tolerance For About Equal (~=) Comparison [model settings]

getEpsilon [SimTalk]

##### setInfiniteLoopDetectionTimeout [SimTalk]

Sets the number of seconds which method execution might take before Plant Simulation opens the dialog telling you that you can stop method execution by pressing Shift+Alt+Ctrl .

Type

Function

Syntax

```simtalk
setInfiniteLoopDetectionTimeout(Timeout:integer) → integer
```

**Parameter**

The parameter Timeout of data type integer designates the number of seconds for the timeout. Specifying 0 , or a negative value, will deactivate infinite loop detection entirely. Otherwise the allowed minimum value is 3 seconds.

Return Value

The return value has the data type integer .

The return value is the previous value.

Example

setInfiniteLoopDetectionTimeout(60)

##### setMUTraceRouteMethod [SimTalk]

Designates a Method or an array\_of\_Methods , which is called each and every time, when a MU is moved to another object.

Remarks

Methods which are registered with setMUTraceRouteMethod are removed from the Registry when you reset the EventController . Each model has to register its Methods anew when initializing the model. This prevents that Methods are executed for a model, which does not use setMUTraceRouteMethod , and which were registered by another model.

Type

Function

Syntax

```simtalk
setMUTraceRouteMethod(&Method:object) → object setMUTraceRouteMethod([array_of_Methods:any]) → object setMUTraceRouteMethod → object
```

Parameters for a Single Method Object

The method has four parameters.

- In the example below the parameter fromObject of data type object designates the object on which the MU was located before it was moved.
- The parameter fromLength of data type length designates the position of the MU on a length-oriented object at which the MU was located before it was moved.
- The parameter fromLane of data type integer designates the lane on which the MU was located on a TwoLaneTrack .
- The parameter time of data type time designates the point in time at which the MU is to be moved.

Return Value

The return value has the data type object .

Example

```simtalk
param fromObject: object, fromLength: length, fromLane: integer, t: time
var numSankeys: integer
var sankeylist: object
var toLength: length sankeylist := rootfolder.internal.ActiveSankeyObjects
numSankeys := sankeylist.dim
for var i := 1 to numSankeys
	sankeylist.read(i).printTrace(@,fromObject,fromLength,fromLane,?,t)
next
```

**Parameters for An Array of Methods**

The parameter array\_of\_Methods of data type any designates an array of Method objects.

You can also call the function setMUTraceRouteMethod without a parameter. If you specify an array of Method objects, Plant Simulation enters all Methods as Callback Methods and removes all previously existing Callback Methods from the list of Callback Methods .

If you call the function setMUTraceRouteMethod without parameter, it does not change the previously existing Callback Methods but returns an array of the previously existing Callback Methods .

**Return Value**

Is an array of data type object which contains all previously existing Callback Methods .

**Example**

```simtalk
// add 'MyMethod' to the Callback Methods
var callbacks:
object[] := setMUTraceRouteMethod() // get the already installed Callback Methods
callbacks.append(&MyMethod)      // add MyMethod setMUTraceRouteMethod(callbacks) // set the previously installed methods plus MyMethod as Callback Methods // remove 'MyMethod' from the Callback Methods
callbacks := setMUTraceRouteMethod() // get the installed Callback Methods
callbacks.deleteValue(&MyMethod)     // remove MyMethod from the array setMUTraceRouteMethod(callbacks)     // set the previously installed methods minus MyMethod as Callback Methods // clear all Callback Methods
var empty: object[] setMUTraceRouteMethod(empty) // setting an empty array will uninstall all Callback Methods
```

##### setPythonDLLPath [SimTalk]

Specifies the path to the Python installation to be use if you are have multiple Python environments on your computer.

**Remarks**

Plant Simulation supports Python versions 3.12 and 3.13.

If you installed several Python versions on your computer, use setPythonLLPath to choose which version you want to use.

Type

Function

Syntax

```simtalk
setPythonDLLPath(dllpath:string)
```

**Parameter**

The parameter dllPath of data type string designates the path to the Python dll that you want to use.

**Example**

```simtalk
setPythonDLLPath("C:\Program Files\Python312\python312.dll") -- uses the Python version for all users, located in C:\Program Files\Python312, which is the default setting
setPythonDLLPath("C:\Users\<YourLoginName>\AppData\Local\Programs\Python\Pyt hon312\python312.dll") -- uses the Python version for the current user located in the folder above
```

**See also**

**PythonModule**

##### setRandomSeedCounter [SimTalk]

Is only required if you want to influence the automatic allocation of the random number seed value, which normally is not required.

**Remarks**

When you insert an object into your model, Plant Simulation automatically assigns a random number seed value to this object. You can query the next assigned random seed value with the function setRandomSeedCounter(0) . After the object is created, Plant Simulation increases this counter by 1, so that the next object gets a different random seed value.

This guarantees that the newly inserted object uses different random numbers, for example for Processing Times , for Failures , etc. To facilitate this, each model has a counter that Plant Simulation increases when automatically assigning the random number seed value. Calling the function setRandomSeedCounter with 0 only returns the current counter. If you call the function setRandomSeedCounter with a value other than 0, Plant Simulation sets the counter to this value.

Besides, the function setRandomSeedCounter returns the previous value of the counter. If you only want to get the current value of the counter, call the function with CounterValue=0 .

If you set the counter to a value smaller than the previous value, it is not guaranteed that each newly inserted object has a unique random number seed value.

This function can be useful if you want to automatically create simulation models. You could, for example, use the Teamcenter Interface to detect the objects within your installation to then create these objects using a Method . When you then delete the created objects and get the up-to-date information from Teamcenter and create the model anew, the created object will get different random number seed values, even if the Teamcenter database did not change. To use the same random number seed values, call the function setRandomSeedCounter once before creating the objects to always initialize the counter with the same value.

Type

Function

Syntax

```simtalk
setRandomSeedCounter(CounterValue:integer) → integer
```

**Parameter**

The parameter CounterValue of data type integer designates the value of the counter.

Return Value

The return value has the data type integer .

The return value is the current random seed counter.

Example

```simtalk
setRandomSeedCounter(4)
print setRandomSeedCounter(0)
```

See also

resetRandomNumberStream [SimTalk]

Random Numbers Variant

RandomSeed [SimTalk] - material flow objects

##### setSeedTable [SimTalk]

Sets the random number seed values for creating the random number streams.

Remarks

**Note**

The seed values only apply to the distribution functions , such as z\_uniform , z\_normal , etc.

Each of the material flow objects automatically uses a random number stream of its own. You can set that random number stream with the attribute RandomSeed .

**Note**

Plant Simulation applies the new random numbers immediately and resets all random number streams with the new seed values.

Type

Function

Syntax

```simtalk
setSeedTable(SeedTable:table)
```

Parameter

The parameter SeedTable of data type table designates a table with one or two columns or a list .

- The first column contains the random number seed values ( integer ).
- The optional second column contains the comments to the random number seed values ( string ). The number of the row matches the number of the random number stream.

**Examples**

```simtalk
var t: table[integer]
t.create
t[1,6] := 1 setSeedTable(t)
var t: table[integer]
t.create
t[1,6] := 1
```

**setSeedTable [SimTalk]**

```simtalk
t[2,6] := "Explain usage" setSeedTable(t)
```

See also

Random Number Seed Values

RandomSeed [SimTalk] - material flow objects

getSeedTable [SimTalk]

resetRandomNumberStream [SimTalk]

Distribution Functions, z\_ functions

##### showStatisticsReport [SimTalk]

Shows the Statistics Report of the objects which you type into the list.

Type

Function

**Syntax**

```simtalk
showStatisticsReport(List:list[, FileName:string])
```

**Parameters**

- The parameter List of data type list designates the list into which you entered the names of the objects.
- The optional parameter FileName of data type string designates the name of the file into which Plant Simulation writes the statistics values.

**Example**

showStatisticsReport(myStatisticsObjects) showStatisticsReport(myStatisticsObjects,"My Statistics Report")

**See also**

Statistics Report [described]

**strHash [SimTalk]**

##### strHash [SimTalk]

Calculates the hash value from the passed string.

Remarks

The value is located between 0 and 2147483647 (including both thresholds). The hash function is case-sensitive. If you do not want this, convert the string to lower case with the function strToLower beforehand.

You might, for example, use the hash value to find a string very fast. Comparing integer numbers is faster than comparing strings. The hash value generation is not a bijective function, i.e., it is not unambiguously reversible.

Once you have found the hash value, you should then compare the strings. If you want to map the hash value to a smaller value range, i.e., if you want to program a hash table, you should use the modulo value of the hash value.

Type

Function

Syntax

```simtalk
strHash(string) → integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
var hashTable: any[7]
var emptyStringArray: string[]
for var i := 1 to hashTable.dim
	hashTable[i] := emptyStringArray
next
hashTable[strHash("Source")   mod 7 + 1] := ["Source"]
hashTable[strHash("Drain")    mod 7 + 1] := ["Drain"]
hashTable[strHash("AssemblyStation") mod 7 + 1] := ["AssemblyStation"]
var SourceFound: boolean := hashTable[strHash("Source") mod 7 + 1].find("Source") /= 0
var BufferFound: boolean := hashTable[strHash("Buffer") mod 7 + 1].find("Buffer") /= 0
```

**See also**

strToLower [SimTalk] computeSHA1Hash [SimTalk]

computeSHA3Hash [SimTalk]

**throwRuntimeError [SimTalk]**

##### throwRuntimeError [SimTalk]

Returns an error message to the calling Method in library methods. This is, for example, the case if the library method was called with parameter values that are not allowed.

**Remarks**

You can also use the function outside of libraries. When the function throwRuntimeError is called, Plant Simulation opens the Method Debugger for the calling Method and shows the message that was passed to throwRuntimeError . In case the Method does not run as a subroutine, i.e., if no caller exists, Plant Simulation opens the Method Debugger at the position which contains the function throwRuntimeError . If the method is encrypted, Plant Simulation opens a message box instead that shows the message.

If the Method that executes throwRuntimeError is part of a library, Plant Simulation returns the call chain up to the point at which the first Method was found which does not belong to this library. For this Method Plant Simulation then opens the Method Debugger . If the Method that executes throwRuntimeError does not belong to a library, Plant Simulation opens the Method Debugger for the first direct caller of the Method .

If an error handling method ( ErrorHandler ) exists in the calling Method or in one of its callers, Plant Simulation does not open the Method Debugger , but instead calls the error handling method. That means that the search for an error handling method starts at the Method for which the Method Debugger would open. If this Method does not have an error handling method, Plant Simulation goes back in the call chain until it finds a local error handling method. If none of these Methods in the call chain has a local error handling method, it instead calls the global error handling method. If no global error handling method exists either, then Plant Simulation opens the Method Debugger or the message window as described above.

Type

Function

Syntax

```simtalk
throwRuntimeError(ErrorMessage:string)
```

**Parameter**

The parameter ErrorMessage of data type string sets the error message that Plant Simulation shows.

**Example**

```simtalk
param NewPosition : length // the method drives the hook of the crane to a new position
if NewPosition < 0 or NewPosition > MyCrane.MyCraneArmLength
```

throwRuntimeError("invalid crane position") end // set the new position ...

**See also**

Error Handling

Calculate Values with a Formula

getCallStack [SimTalk]

setErrorHandler [SimTalk]

**updateGUI [SimTalk]**

##### updateGUI [SimTalk]

Updates the graphical user interface of Plant Simulation .

Remarks

If executing a Method takes a long time, it might seem that Plant Simulation stopped responding to your input. To prevent this from happening, you can every now and then call the function updateGUI within this Method .

updateGUI redraws the contents of the Frames , but only if the time has elapsed that is equal to the reciprocal of the frame rate you specified under File &gt; Preferences &gt; Simulation &gt; Frame Rate . This makes sure that Plant Simulation does not use up too much time for redrawing.

Type

Function

Syntax

```simtalk
updateGUI
-> integer updateGUI([forceUpdateNow:boolean:=false])
-> integer
```

**Parameter**

Specify the optional parameter forceUpdateNow and set it to true to enforce an immediate update of the user interface.

Do not specify the parameter or set it to false to only redraw the user interface one time after some time has passed since the last update. This time depends on the frame rate that you specified under File &gt; Preferences &gt; Simulation &gt; Frame Rate .

**Default Value of the Parameter**

The default value is false.

**Example**

```simtalk
for var y := 1 to JTFileTable.yDim
	MyFrame._3D.importGraphics([0,y,0], JTFileTable[1,y], false, true) updateGUI
next
```

**See also**

**Frame Rate [model settings]**

##### userInterfaceLanguage [SimTalk]

userInterfaceLanguage [SimTalk]

Returns the language of the user interface of Plant Simulation .

Type

Function

Syntax

```simtalk
userInterfaceLanguage → integer
```

Return Value

The return value has the data type integer .

0 designates German , 1 English , 2 Japanese , 3 Chinese , and 8 designates Hungarian .

**Example**

```simtalk
if userInterfaceLanguage = 0      // German print "Guten Morgen"
elseif userInterfaceLanguage = 1  // English print "Good morning"
elseif userInterfaceLanguage = 2  // Japanese print "Ohayo gozaimasu"
elseif userInterfaceLanguage = 3  // Chinese print "Zao an"
elseif userInterfaceLanguage = 8  // Hungarian print "Jó reggelt"
end
```

**See also**

**language [SimTalk]**

Model Language [model settings]

Specifying Start Options , /UILanguage:ENU , /UILanguage:DEU , /UILanguage:JPN , / UILanguage:CHS , or /UILanguage:HUN

##### writeStringToFile [SimTalk]

Writes the content of the specified Text to a file.

Type

Function

**Syntax**

```simtalk
writeStringToFile(Text:string, FileName:string[, Append:boolean, Encoding:string:="UTF-8"])
```

**Parameters**

- The parameter Text of data type string designates the text which you would like to write to the file.
- The parameter FileName of data type string designates the file or the directory path and the name of the file into which the file will be written. If the file exists, it will be overwritten.
- The optional parameter append of data type boolean sets if Plant Simulation deletes the existing content before writing ( false ) or if it does not delete it before writing and appends a line break (Carriage Return + Line Feed) to the written text ( true ).
- Do not specify the optional parameter Encoding of data type string or specify "UTF-8" , to save the file in UTF-8-format with a BOM (Byte Order Mark).

Specify "Unicode" or "UTF-16" for Encoding , to save the file in UTF-16-format with a BOM.

Specify an empty string "" to save the file as UTF-8 without BOM.

**Default Value of the Parameter**

The default value is "UTF-8" .

**Examples**

writeStringToFile("hello world", "C:\Users\Public\Public Documents\a.txt")

```simtalk
writeStringToFile(&MyMethod.Program, "C:\Temp\SourceCode.txt") -- exports the source code of MyMethod to a text file
var data:json data["Name"] = "John Doe" data["Profession"] = "Simulation specialist" data["NumProjects"] = 378
```

// JSON must have a BOM, so turn it off with empty last argument writeStringToFile(data.asString, "D:\tnt.json", false, "")

See also

readStringFromFile [SimTalk]

Program [SimTalk]

