#### Methods of All Objects

Methods of All Objects

All objects share the methods described below. The topics about the individual objects list additional methods that apply to these objects.

**You can use methods to**

- query information from an object and return a value
- make calculations
- starts one or several actions that control the behavior of the object

We grouped the methods in the Plant Simulation Help according to their functions.

To view all of the methods , read-only attributes and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

An example of the Syntax line of the individual methods might look like this:

<!-- image -->

- The expression &lt;Path&gt; designates the path of the object to which the method applies.

##### General Methods

- The signature of the method, consisting of the identifier and the data type of the parameter, is listed in parentheses. The expression (Parameter:string) , for example, designates a parameter of data type string . Instead of a constant value, you can also use a variable of the required type or a method that returns the required data type.

**Note**

Make sure to enter the parentheses for expressions within parentheses (…). Not entering them may lead to unexpected results and open the Debugger .

Optional parameters are listed within brackets. The expression [,Parameter:boolean] , for example, means that you can, but do not have to enter the boolean parameter.

If a parameter has a default value, the signature shows the default value after the parameter.

If the method has a return value, the signature shows its data type after the arrow -&gt;.

**See also**

- \_General Methods
- \_Methods for Animating Objects

Methods of the Display Panel

- \_Methods for the Location, Predecessor, and Successor
- \_Methods for Managing Inheritance Relations
- \_Methods for Managing Attributes
- \_Methods of User-defined Attributes

**General Methods**

###### \_General Methods

Most of the objects provide the methods listed in the table of contents to the left.

To view all of the methods , read-only attributes , and attributes of the material flow object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

**addObserver [SimTalk]**

###### addObserver [SimTalk]

Adds an observer to the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.addObserver(AttributeName:string, Method:object)
```

**Parameters**

- The parameter AttributeName of data type string designates the name of the watchable attribute or read-only attribute .
- The parameter method of data type object designates the Method that is going to be called when the value of this attribute or read-only attribute changes. Plant Simulation then executes the actions, which you programmed in this method .

Within the called Method you can use the anonymous identifiers ? and @ to address the object, whose attribute changed, i.e., the caller of the Method .

Two parameters are passed to the Method , which will be executed:

- The name of the watched attribute or the watched read-only attribute , whose value changed. This way you can use a single Method as the called Method for several attributes.
- The previous value of the watchable attribute or the watchable read-only attribute . This way you can still access the previous value after the Method changed it to the new value.

The source code for our occupiedObserver looks like this:

<!-- image -->

**Example**

MyStation.addObserver("occupied", &amp;myMethod)

**See also**

**Edit Observers [general description]**

removeObserver [SimTalk] removeAllObservers [SimTalk]

attributeWatchable [SimTalk]

###### attributeWatchable [SimTalk]

Returns if an attribute or read-only attribute of the object designated by &lt;Path&gt; is watchable (true) or not (false).

**Remarks**

To check which attributes and read-only attributes of an object are watchable, you can also select the object and press F8 . Watchable attributes and read-only attributes are marked with an asterisk ( * ) in the column Watchable in the window Show Attributes and Methods .

<!-- image -->

Type

Method

Syntax

<!-- image -->

Parameter

The parameter AttributeName of data type string designates the attribute or read-only attribute .

Return Value

The return value has the data type boolean .

Example

```simtalk
print ParallelStation.attributeWatchable("NumMU")
```

**See also Show Attributes and Methods [described]**

**Watchable Values**

###### closeDialog [SimTalk] - all objects

closeDialog [SimTalk] - all objects

Closes the dialog box of the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.closeDialog([ApplyChanges:boolean:=true]) → boolean
```

Parameter

The optional parameter ApplyChanges of data type boolean determines if Plant Simulation ignores all changes you made in the dialog box or if it accepts and applies your changes.

Specify true to make the object evaluate all settings in the dialog box and apply them as the new values.

Specify false to make the object discard your changes.

**Default Value of the Parameter**

The default value is true.

Return Value

The return value has the data type boolean .

Example

MyStore.closeDialog            // apply changes MyTrack.closeDialog(false)     // do not apply changes

See also

**\_3D.closeWindows [SimTalk]**

OK button

Cancel button

###### deleteObject [SimTalk]

Deletes the object designated by &lt;Path&gt;.

Remarks

You cannot delete objects that are currently active, for example Methods that are being executed at the moment. For this reason you cannot, for example, delete a Frame using the Constructor method if the Constructor method itself is located within that Frame .

**Note**

Deleting a class object automatically deletes all of its instances without warning.

**Note**

To delete a MU , we recommend to use the method delete . This prevents that you accidentally delete part of your simulation model when you address the wrong object.

Type

Method

Syntax

```simtalk
< Path >.deleteObject → boolean
```

Return Value

The return value has the data type boolean .

true if the object was deleted successfully.

false if the object was not deleted.

Example

```simtalk
.Materialflow.MyStation.deleteObject // deletes the object from the class library MyStation.deleteObject // deletes the object from the Frame
```

See also

Delete [Home ribbon]

###### delete [SimTalk] - MUs

###### derive [SimTalk]

Derives the object designated by &lt;Path&gt; in the Class Library , i.e., it creates a subclass that inherits its properties from the class of the derived object.

Remarks

Plant Simulation immediately applies all changes in the class to the subclass.

Type

Method

Syntax

```simtalk
< Path >.derive([Destination:object, Name:string, NextRandomSeedValue:integer]) → object
```

**Parameters**

- The optional parameter Destination of data type object designates the destination at which Plant Simulation creates the object.
- The optional parameter Name of data type string designates the name of the object that will be created. If this Name cannot be used because it is not unique, Plant Simulation shows an error message.
- The optional parameter NextRandomSeedValue of data type integer sets which Random Seed Value is going to be used next. Plant Simulation uses this value instead of the value which you can query with the method setRandomSeedCounter .

The parameter NextRandomSeedValue ensures reproducible simulation behavior when you create objects during the simulation.

Return Value

The return value has the data type object .

It is the derived object, if it was able to derive the object.

VOID if deriving failed.

Examples

```simtalk
var Station := .MaterialFlow.Station.derive // Creates a new class in the folder MaterialFlow which is derived from the object named Station.
```

**derive [SimTalk]**

```simtalk
Station.Name := 'TestCenter'
Station.Coordinate3D := [4.0, 5.0, 0.0]
var NewVariable : object := .InformationFlow.&Variable.derive // To derive a Variable, we have to use the &-operator to prevent calling // the command 'derive' for the value of the Variable.
var NewVariable : object := .InformationFlow.&Variable.derive // To derive a Variable, we have to use the &-operator to prevent calling // the command 'derive' for the value of the Variable.
```

**SimTalk**

duplicate [SimTalk]

deleteObject [SimTalk]

RandomSeed [SimTalk] - material flow objects

setRandomSeedCounter [SimTalk]

create [SimTalk] - MUs

See also

Derive

Cut Inheritance

Random Seed Value

###### duplicate [SimTalk]

Copies the object designated by &lt;Path&gt; in the Class Library and creates a new class.

Remarks

Plant Simulation cuts inheritance relations to the original of the duplicated object.

To create the object at a certain position in the Frame , you can use the attribute Coordinate3D .

Type

Method

Syntax

```simtalk
< Path >.duplicate([Destination:object, Name:string]) → object
```

**Parameters**

- The optional parameter Destination of data type object designates the destination at which Plant Simulation creates the object.
- The optional parameter Name of data type string designates the name of the object that will be created.

Return Value

The return value has the data type object .

It is the duplicated object, if it was able to duplicate the object.

VOID if duplicating failed.

**Examples**

.MaterialFlow.Conveyor.duplicate .MaterialFlow.Conveyor.duplicate(.Models.MyPlant,"MyConveyor") .InformationFlow.&Variable.duplicate .InformationFlow.&Method.duplicate

```simtalk
var myConveyor:object := .MaterialFlow.Conveyor.duplicate(.Models.Model."MyConve yor")
MyConveyor.setPosition := [100, 100] // Sets the pixel coordinates.
```

**duplicate [SimTalk]**

SimTalk derive [SimTalk] deleteObject [SimTalk] Coordinate3D [SimTalk] - general description See also Duplicate Cut Inheritance

###### extendPath [SimTalk]

Extends the path of the object designated by &lt;Path&gt;, allowing you to access objects contained within or located on that object.

Type

Method

Syntax

```simtalk
< Path >.extendPath(PathExtension:string) → object
```

Parameter

The parameter PathExtension of data type string designates the path of the object whose path you want to extend.

Return Value

The return value has the data type object .

Examples

```simtalk
var obj := MyFrame.extendPath("Station3")
if obj /= void
	obj.ProcTime := 63.5
end
current.extendPath("Station") -- tells if the object named Station -- exists in the Frame current
```

See also

existsObject [SimTalk]

getHTMLCode [SimTalk] - all objects

Returns the HTML code for the object designated by &lt;Path&gt; with statistics which would generate a statistics table in the HtmlReport .

Remarks

The syntax is the same as in the HtmlReport .

Type

Method

Syntax

```simtalk
< Path >.getHTMLCode([Caption:string, StatisticsType:string,ColumnOrColumnRange:any]) → string
```

**Parameters**

- The optional parameter Caption of data type string designates the caption of the object.
- The optional parameter StatisticsType of data type string designates the statistics type of the object. Start entering the statistics type with a percentage sign, for example %WorkingTime .
- You can specify one of these statistics types:

| Statistics type English                                | Statistics type German                                  |
|--------------------------------------------------------|---------------------------------------------------------|
| %ResStates                                             | %Stati                                                  |
| %MatFlowProperties                                     | %Matflusseigenschaften                                  |
| %RotationTime ( Turnplate , Turntable , PickAndPlace ) | %Drehungszeit ( Drehplatte , Drehtisch , PickAndPlace ) |
| %MovingTime ( Converter )                              | %Umsetzzeit ( Umsetzer )                                |
| %WorkingTime                                           | %Arbeitszeit                                            |
| %SetupTime                                             | %Rüstzeit                                               |
| %WaitingTime                                           | %Wartezeit                                              |
| %BlockedTime                                           | %Blockiertzeit                                          |
| %PowerUpDownTime                                       | %HochHerunterfahrzeit                                   |
| %StoppedTime                                           | %Angehaltenzeit                                         |
| %FailedTime                                            | %Störungszeit                                           |

| Statistics type English            | Statistics type German               |
|------------------------------------|--------------------------------------|
| %PausedTime                        | %Pausenzeit                          |
| %EmptyTime                         | %Leerzeit                            |
| %MUMatFlowProperties               | %BEMatflusseigenschaften             |
| %MUEmptyTime                       | %BELeerzeit                          |
| %DrainCumulated                    | %SenkeKumuliert                      |
| %DrainAllTypes                     | %SenkeAlleTypen                      |
| %DrainTypesPortions (non summable) | %SenkeTypenanteile (nicht addierbar) |
| %DrainTypesTimes (non summable)    | %SenkeTypenzeiten (nicht addierbar)  |
| %Energy                            | %Energie                             |
| %MUClassStatistics                 | %BEKlassenStatistik                  |
| %MUClassTimePortions               | %BEKlassenZeitanteile                |
| %MUTimePortions                    | %BEZeitanteile                       |
| %TransUsageTime                    | %TransVerwendungszeit                |
| %TransReadyTime                    | %TransBereitzeit                     |
| %TransPausedTime                   | %TransPausenzeit                     |
| %TransFailedTime                   | %TransStörungszeit                   |
| %TransTraveledDistance             | %TransWegstrecke                     |
| %TransBatteryTime                  | %TransBatteriezeit                   |
| %Broker                            | %Broker                              |
| %BrokerMediationTime               | %BrokerVermittlungsdauer             |
| %BrokerDwellTime                   | %BrokerVerweildauer                  |
| %Exporter                          | %Exporter                            |
| %ExporterTimePortions              | %ExporterZeitanteile                 |
| %WorkerTraveleledDistance          | %WerkerWegstrecke                    |
| %ImporterWaiting                   | %ImporterWartend                     |
| %ImporterWaitingTime               | %ImporterWartezeit                   |
| %ImporterMUWaitingTime             | %ImporterBEWartezeit                 |
| %ImporterSetpWaitingTime           | %ImporterRüstWartezeit               |

- The optional parameters ColumnIndex|ColumnRange|ColumnName of data type integer designate ColumnIndex|ColumnRange|ColumnName of the column. You have to start entering column names with the number of the respective column.

Compare these examples for column identifiers:

| Column identifier   | Designates                                                         |
|---------------------|--------------------------------------------------------------------|
| #Sum                | The column with the index or name Sum                              |
| 0                   | The row index column, if available, otherwise it leads to an error |
| 3                   | The column with the number 3                                       |
| 2..5                | The columns 2 to 5                                                 |
| ..5                 | All columns from the first available column to column 5            |
| *..5                | All columns from the first available column to column 5            |
| 5..                 | All columns from column 5 onward                                   |
| 5..*                | All columns from column 5 onward                                   |
| *                   | The last column of the table                                       |

This syntax is the same as in the HtmlReport .

**Return Value**

The return value has the data type string .

**Examples**

```simtalk
print Source.getHtmlCode
Comment1.Cont := DataTable.getHtmlCode()            // entire table
Comment2.Cont := DataTable.getHtmlCode("caption")   // table with caption
Comment3.Cont := DataTable.getHtmlCode(1, 3)        // numerical column index
Comment4.Cont := DataTable.getHtmlCode("1", 3)      // mixture of numerical/ string column indexes
Comment5.Cont := DataTable.getHtmlCode("1..2")      // column index range
Comment6.Cont := DataTable.getHtmlCode("#A")        // named column
```

**See also**

Display a HtmlReport

**Display a Frame**

**getObservers [SimTalk]**

###### getObservers [SimTalk]

Returns all observers of the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.getObservers
-> table
```

**Return Value**

The return value has the data type table .

<!-- image -->

This table has three columns.

- Column 1 is of data type string and contains the name of the Observed Value .
- Column 2 is of data type object and contains the name of the Method .

The Method in column 2 can contain a relative path to a Method or an object reference . If it is a relative path, you have to use the method asString of the DataTable to access the path in column 2.

- Column 3 is of data type boolean and contains true if the observer was created in the current object ( Created Here ), i.e., it is not inherited.

**Example**

```simtalk
// deletes all observers of a Station
var observerTable := Station.getObservers
for var row := 1 to observerTable.ydim
	if observerTable[3,row]             // only delete observers which are not inherited if observerTable[2,row] /= void // observer is specified as an object reference
		Station.removeObserver(observerTable[1,row], observerTable[2,row])
	else                            // observer is specified by a
```

relative path Station.removeObserver(observerTable[1,row], observerTable.asString(2,row)) end end next

**See also**

Edit Observers [general description]

New [observer]

asString [SimTalk] - DataTable

**getXYWH [SimTalk]**

###### getXYWH [SimTalk]

Returns the coordinates of the position of the dialog of the object designated by &lt;Path&gt;, and assigns them to the local variables, which you specify.

**Remarks**

For a maximized window getXYWH returns -1 for the X-Coordinate and the Y-Coordinate, and the correct size of the maximized window.

Type

Method

Syntax

&lt; Path &gt;.getXYWH(byRef X:integer, byRef Y:integer, byRef Width:integer, byRef Height:integer)

**Local Variables**

- The local variable X of data type integer designates the x-coordinate of the dialog of the object.
- The local variable Y of data type integer designates the y-coordinate.
- The local variable Width of data type integer designates its width.
- The local variable Height of data type integer designates its height.

For objects, which do not save their position and size, the method assigns -1, when the dialog is closed.

**Example**

```simtalk
Frame1.getXYWH(x,y,w,h)
print x," ",y," ",w," ",h
```

**See also**

setXYWH [SimTalk]

isNameUnique [SimTalk] - identifier

Returns if the identifier within the name space of the object designated by &lt;Path&gt; is unique ( true ), i.e., is not assigned yet, or if it is not unique ( false ), i.e., is already assigned.

Type

Method

Syntax

```simtalk
< Path >.isNameUnique(NameToBeChecked:string) → boolean
```

Parameter

The parameter NameToBeChecked of data type string designates the name that is to be checked .

Return Value

The return value has the data type boolean .

true if the name is unique.

false if the name to be checked is already assigned for the object designated by &lt;Path&gt;.

This object then either has a built-in attribute or a built-in method or a user-defined attribute with this identifier. When the object designated by &lt;Path&gt; is a Frame or a folder , then isNameUnique also considers objects with this identifier, which you inserted into the Frame .

**Note**

Use isNameUnique to find out in advance if the identifier is already assigned to an object within the surrounding Frame to prevent a runtime error if you want to rename an object with SimTalk commands.

**Example**

```simtalk
print .Hall2.isNameUnique("Station1")  // object inserted into Frame print .Hall2.isNameUnique("Name")      // built-in attribute print .Hall2.isNameUnique("~")         // built-in method print .Hall2.isNameUnique("myUserDefinedAttribute")
```

See also

hasAttribute [SimTalk] - 2D

**Namespace**

###### memUsage [SimTalk]

Computes how much memory the object designated by &lt;Path&gt; uses.

**Remarks**

To show how much memory the individual objects in a Frame consume, you can also select the command Show Memory Usage on the context menu of the Structure window in the windows Show Inheritance and Show Structure .

<!-- image -->

Type

Method

Syntax

<!-- image -->

Return Value

The return value has the data type integer .

**memUsage [SimTalk]**

**Example**

```simtalk
print FootPath1.memUsage // might
return 9685, i.e.
96.8 KB
print MyStation.memUsage -- might
return 4975, i.e.
4.9 KB
```

**See also**

**Show Structure [class library]**

\_3D.memUsage [SimTalk]

moveToFolder [SimTalk]

Moves the object designated by &lt;Path&gt; to the folder designated by the parameter Folder .

Type

Function

Syntax

&lt; Path &gt;.moveToFolder(Folder:Path) → object

Parameter

The parameter Folder of data type path designates the folder into which the object is to be moved.

Return Value

The return value has the data type object .

Example

.Resources.Exporter.moveToFolder(.Models)

See also

Move to Folder Control

MoveToFolderCtrl [SimTalk]

```simtalk
openDialog [SimTalk] - all objects Opens the dialog box of the object designated by <Path>. Type Method Syntax openDialog [SimTalk] - all objects
< Path >.openDialog([CallOpenControl:boolean:=false]) → boolean
```

Parameter

The optional parameter CallOpenControl of data type boolean determines if Plant Simulation opens the dialog box the same way as double-clicking the icon does ( true ) or not ( false ).

The method also executes any Open Control you specified.

When you specify false , Plant Simulation just opens the dialog box, without executing any Open Control .

**Default Value of the Parameter**

The default value is false.

Return Value

The return value has the data type boolean .

true if Plant Simulation succeeded in opening the dialog box.

**Example**

```simtalk
Buffer.openDialog .drill.openDialog(false)
basis.Materialflow.Source.openDialog(true) self.~.~.&MyMethod.openDialog  // opens the window of the method // MyMethod instead of executing it
```

**See also**

\_3D.openDialog [SimTalk]

Open Control removeAllObservers [SimTalk]

Deletes all observers of the object designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.removeAllObservers → boolean

Return Value

The return value has the data type boolean .

true if inherited observers exist.

Example

MyStation.removeAllObservers

SimTalk

removeObserver [SimTalk]

addObserver [SimTalk]

See also

Delete [observer]

###### removeObserver [SimTalk]

Deletes the specified observer of the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.removeObserver(AttributeName:string, Method:method/void) → boolean
```

**Parameters**

- The parameter AttributeName of data type string designates the name of the watchable attribute or read-only attribute .
- The parameter Method of data type method designates the name of the method that is going to be executed.

When you specify void , Plant Simulation deletes all observers which point to a non-existing Method .

Return Value

The return value has the data type boolean .

Example

MyStation.removeObserver("occupied", "myMethod") MyStation.removeObserver("occupied", &myMethod)

SimTalk

removeAllObservers [SimTalk]

addObserver [SimTalk]

See also

Edit Observers [general description]

Delete [observer]

**replace [SimTalk]**

###### replace [SimTalk]

Replaces the object designated by ObjectToReplace with the object designated by &lt;Path&gt;.

Remarks

The object designated by &lt;Path&gt; has to be a class in the Class Library .

If the object designated by the parameter ObjectToReplace is a class, Plant Simulation merges both classes. This means that all instances of the class to be replaced will be replaced with instances of the replacing class and that the class to be replaced will be deleted.

If the object designated by the parameter ObjectToReplace is an instance, Plant Simulation replaces this instance with an instance of the replacing class.

Type

Method

Syntax

```simtalk
< Path >.replace(ObjectToReplace:object[, RetainInheritedValues:boolean:=false])
```

**Parameters**

- The parameter ObjectToReplace of data type object designates the object which you want to replace.
- The optional parameter RetainInheritedValues of data type boolean only takes effect if the object to be replaced is an instance. This means that the object to be replaced is located in a Frame . The parameter has no effect when merging classes.

If the parameter RetainInheritedValues has the value true , Plant Simulation cuts inheritance for attributes of the instance to be replaced if the new origin class has another attribute value than the previous origin class.

**Default Value of the Parameter**

The default value is false.

**Example**

.MaterialFlow.Station.replace(.MaterialFlow.MyStation, false)

SimTalk

##### ReplacementMode [SimTalk]

**replace [SimTalk]**

See also Replacing and Merging Objects with Drag-and-Drop Load Object Replacement Mode

###### setName [SimTalk]

setName [SimTalk]

Sets the name of the object designated by &lt;Path&gt; to the specified expression.

Remarks

You can type in a combination of letters, digits, and underscore (\_) characters, for example MyStation , MyStation1 , My\_Station\_1 .

The name of an object cannot start with a digit, i.e., you cannot specify 1Station .

**Note**

You cannot change the name of the EventController and of the Connector !

Type

Method

Syntax

```simtalk
< Path >.setName(NewName:string) → boolean
```

Parameter

The parameter NewName of data type string designates the name.

Return Value

The return value has the data type boolean .

As opposed to assigning the name to the attribute Name , the method setName returns if assigning the new name was successful or not.

Example

```simtalk
print MyStation.setName("MyStation") // returns true
```

See also

Name [general description]

Name [SimTalk] - general description

**Rename [model or object]**

**setPosition [SimTalk]**

###### setPosition [SimTalk]

Sets the position of the icon of the object designated by &lt;Path&gt; in the Frame .

Remarks

A 3D Only model does not provide the method setPosition .

Type

Method

Syntax

```simtalk
< Path >.setPosition(X:integer, Y:integer[, CallMoveInFrameControl:boolean:=true])
```

**Parameters**

- The parameter X of data type integer designates the x-coordinate of the object.
- The parameter Y of data type integer designates the y-coordinate.
- The optional parameter CallMoveInFrameControl of data type boolean determines if Plant Simulation also calls a Move in Frame control ( true ) or not ( false ).

**Default Value of the Parameter**

The default value is true.

Specify false to not call the Move in Frame control .

**Example**

MyStation.setPosition(15,400) ParallelStation.setPosition(80,200,true)

**See also**

**Move-in-frame control**

###### setXYWH [SimTalk]

Sets the position on the screen of the dialog box of the object designated by &lt;Path&gt;.

Remarks

setXYWH also applies for a DataTable , which you opened as a dialog in the foreground. Specifying a negative number for X or for Y centers the dialog on screen.

Type

Method

Syntax

```simtalk
< Path >.setXYWH(X:integer, Y:integer, Width:integer, Height:integer[, TotalSize:boolean:=true])
```

**Parameters**

- The parameter X of data type integer designates the x-coordinate of the dialog on screen.
- The parameter Y of data type integer designates the y-coordinate.
- The parameter Width of data type integer designates the width of the dialog.
- The parameter Height of data type integer designates the height of the dialog.

**Note**

The values Width and Height only apply for windows that you can resize, i. e., for Object windows of the Frame , the Method , the Method Debugger , the DataQueue , the DataStack , the DataList , the DataTable , and the Icon Editor .

- The optional parameter TotalSize of data type boolean sets if the Width designates the total width of the dialog box and the Height designates the total height of the dialog box ( true ) or the Width and the Height within the frame bordering the dialog box ( false ).

**Examples**

MyStation.setxywh(10,100,10,20) Model1.setxywh(500,100,15,25)

MyDataTable.openDialogBox MyDataTable.setxywh(-500,100,15,25)

**See also**

getXYWH [SimTalk]

###### showObject [SimTalk]

Selects the object designated by &lt;Path&gt; and shows it.

Remarks

For instances Plant Simulation selects the object designated by &lt;Path&gt; in the view of the Frame and shows it.

If the Frame , into which the object is inserted, is not open, Plant Simulation opens the Frame first.

For classes Plant Simulation expands the folder in the Class Library and selects the object.

Type

Method

Syntax

&lt; Path &gt;.showObject

**Example**

MyFrame.ParallelStation.showObject

.MaterialFlow.ParallelStation.showObject

###### updateDialog [SimTalk]

updateDialog [SimTalk]

Updates the contents of the open dialog box of the object designated by &lt;Path&gt;.

Remarks

Updating the contents is sometimes necessary because Plant Simulation does not automatically show changed settings of an object, whose dialog box is open, for example by assignments in a method, in the dialog box itself.

Type

Method

Syntax

```simtalk
< Path >.updateDialog → boolean
```

Return Value

The return value has the data type boolean .

true if the dialog was updated succeeded in updating the dialog.

false if updating failed.

Example

```simtalk
EventController.StartDate := sysdate
EventController.updateDialog
```

See also

Refresh [on View menu]

###### writeObject [SimTalk]

Saves the object designated by &lt;Path&gt; to a file into the active folder (compare setCurrentDirectory ) or into the folder whose absolute path you enter.

Remarks

writeObject applies to all classes and folders in the Class Library .

Type

Method

Syntax

```simtalk
< Path >.writeObject(FileName:string[, SaveAsLibrary:boolean:=false, Password:string]) → boolean
```

**Parameters**

- The parameter FileName of data type string designates the name of the object file. You can, but you do not have to enter the file extension.
- The optional parameter SaveAsLibrary of data type boolean determines if Plant Simulation saves the designated folder as a library (true) or as a normal object (false).

**Default Value of the Parameter**

The default value is false.

- The optional parameter Password of data type string sets the password Plant Simulation uses when saving the designated file.

**Example**

.Informationflow.DataList.writeObject("MyDataList.psobj") .Materialflow.ParallelStation.writeObject("mypp.psobj" .ApplicationObjects.Productionsystem.writeObject("MyLibrary.pslib", true)

**SimTalk**

setLibraryInfo [SimTalk]

setCurrentDirectory [SimTalk]

**Methods for Animating Objects**

<!-- image -->

**Methods for Animating Objects**

##### \_Methods for Animating Objects

The objects provide the methods listed in the table of contents to the left to animate them .

To view all of the methods and attributes of the material flow object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

**See also**

**\_Attributes for Animating Objects in 2D**

**closeImg [SimTalk]**

###### closeImg [SimTalk]

Closes the Icon Editor of the object designated by &lt;Path&gt;.

Remarks

A 3D Only model does not provide the method closeImg .

Type

Method

Syntax

```simtalk
< Path >.closeImg(ApplyChanges:boolean) → boolean
```

**Parameter**

The parameter ApplyChanges of data type boolean determines if Plant Simulation accepts your changes ( true ) or discards them ( false ).

Return Value

The return value has the data type boolean .

**Example**

ParallelStation.closeImg(false)   // discards any changes MyGenerator.closeImg(true)        // applies your changes

**See also**

Icon Editor

###### createIcon [SimTalk]

Creates a new icon for the object designated by &lt;Path&gt;.

Remarks

For the newly created icon the setting Activate Transparency is activated and the background is filled with the transparency color.

Note

The method applies to the icon of the addressed instance, not to icon of the object class.

Note

A 3D Only model does not provide the method createIcon .

Type

Method

Syntax

&lt; Path &gt;.createIcon(IconName:string, Width:integer, Height:integer) → integer

**Parameters**

- The parameter IconName of data type string designates the name of the icon.
- The parameter Width of data type integer designates the width of the icon.
- The parameter Height of data type integer designates its height.

Return Value

The return value has the data type integer .

Example

MyStation.createIcon("state",20,30)

SimTalk

deleteIcon [SimTalk]

See also Activate Transparency New Icon Icon Editor

###### delAniPoint [SimTalk]

Deletes an animation point in the active icon of the class of the object designated by &lt;Path&gt;.

Remarks

A 3D Only model does not provide the method delAniPoint .

Type

Method

Syntax

&lt; Path &gt;.delAniPoint(AnipointNumber:integer) → boolean

Parameter

The parameter AnipointNumber of data type integer designates the animation point. It passes the number of the animation point that Plant Simulation returned, for example in the method setAniPoint .

Return Value

The return value has the data type boolean .

**Example**

```simtalk
var previousNumber: integer
previousNumber := .example.CurrIconNo // saves the current icon number
ParallelStation.CurrIconNo := 1 // sets the active icon
ParallelStation.delAniPoint(PointNo // number was saved in PointNo
ParallelStation.CurrIconNo := previousNumber // restores the previous icon
```

SimTalk

**setAniPoint [SimTalk]**

See also

Add/Remove Animation Point

delAniPoints [SimTalk]

Deletes all animation points in the active icon of the class of the object designated by &lt;Path&gt;.

Remarks

You might have to change the current icon of the class beforehand.

Note

A 3D Only model does not provide the method delAniPoints .

Type

Method

Syntax

&lt; Path &gt;.delAniPoints → boolean

Return Value

The return value has the data type boolean .

Example

.example.delAniPoints

SimTalk

getAniPoints [SimTalk]

setAniLine [SimTalk]

See also

Add/Remove Animation Line

Add/Remove Animation Polyline

###### deleteIcon [SimTalk]

Deletes the icon of the object designated by &lt;Path&gt;.

Remarks

A 3D Only model does not provide the method deleteIcon .

Type

Method

Syntax

```simtalk
< Path >.deleteIcon(IconName:string) < Path >.deleteIcon(IconNumber:integer)
```

**Parameter**

The parameter IconName of data type string designates the name of the icon .

Instead, you can also specify the number of the icon as the parameter IconNumber of data type integer .

**Note**

The method applies to the icon of the addressed instance, not to an icon of the object class.

**Example**

MyParallelStation.deleteIcon("MyIcon") MyParallelStation.deleteIcon(1)

SimTalk

createIcon [SimTalk]

###### existsIcon [SimTalk]

existsIcon [SimTalk]

Checks if the icon of the object designated by &lt;Path&gt; exists ( true ) or does not exist ( false ).

Type

Method

Syntax

```simtalk
< Path >.existsIcon(IconName:string) → boolean < Path >.existsIcon(IconNNumber:integer) → boolean
```

**Parameter**

The parameter IconName of data type string designates the name of the icon .

Instead, you can also specify the number of the icon as the parameter IconNumber of data type integer .

Return Value

The return value has the data type boolean .

Example

press.existsIcon("failed") press.existsIcon(2)

###### getAniPoints [SimTalk]

Returns all animation points and animation lines of the object designated by &lt;Path&gt; and writes them into a table.

Remarks

A 3D Only model does not provide the method getAniPoints .

Type

Method

Syntax

&lt; Path &gt;.getAniPoints(AniPointTable:table)

**Parameter**

The parameter AniPointTable of data type table designates the name of the table into which the method writes the values.

|   Column | Description                                                                                            |
|----------|--------------------------------------------------------------------------------------------------------|
|        0 | Contains the number of the animation point or of the animation line respectively.                      |
|        1 | Contains the connected object (*).                                                                     |
|        2 | Contains the number of the linked animation point/line (*).                                            |
|        3 | Contains the x-coordinate of the animation point or starting point of the animation line respectively. |
|        4 | the y-coordinate of the animation point or starting point of the animation line respectively.          |
|        5 | VOID for animation points or the x-coordinate of the next anchor point of the animation line.          |
|        6 | VOID for animation points or the y-coordinate of the next anchor point of the animation line.          |
|        7 | ...                                                                                                    |

**Note**

(*) If you apply this method to any other object than to a Frame , this value is VOID.

**Example**

MyTrack.getAniPoints(MyAnipointsTable) // MyAnipointsTable is a DataTable

SimTalk

setAniLine [SimTalk]

setAniPoint [SimTalk]

See also

Add/Remove Animation Line

Add/Remove Animation Polyline

###### getBoundingBox [SimTalk]

Returns the coordinates of the upper left corner of the bounding box of the object designated by &lt;Path&gt;, and its width and height.

**Remarks**

Plant Simulation then assigns the coordinates to the local variables, whose names you specify.

<!-- image -->

**Note**

A 3D Only model does not provide the method getBoundingBox .

Type

Method

Syntax

&lt; Path &gt;.getBoundingBox(byRef X:integer, byRef Y:integer, byRef Width:integer, byRef Height:integer)

**Local Variables**

- The local variable X of data type integer designates the x-coordinate of the upper left corner of the bounding box.
- The local variable Y of data type integer designates its y-coordinate.
- The local variable Width of data type integer designates the width of the bounding box.

**getBoundingBox [SimTalk]**

- The local variable Height of data type integer designates its height.

The bounding box is the rectangle that surrounds the icon. In the figure below the bounding box is the green area around the rotated icon of the Station .

<!-- image -->

**Note**

The method applies to all objects, except for the Variable , the Comment , the folder and the toolbar .

**Example**

```simtalk
var x,y,width,height: integer
MyStation.getBoundingBox(x,y,width,height)
```

**See also**

**\_\_Accessing the Bounding Box**

###### getIconSize [SimTalk]

Returns the width and the height of the current icon of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation then assigns the width and the height to the local variables, whose names you specify.

Type

Method

Syntax

&lt; Path &gt;.getIconSize(byRef Width:integer, byRef Height:integer)

**Local Variables**

- The local variable Width of data type integer designates the width of the current icon.
- The local variable Height of data type integer designates its height.

**Example**

```simtalk
var w,h: integer
MyStation.getIconSize(w,h)
print w," ",h
```

SimTalk

**setIconSize [SimTalk]**

See also

Set Icon Size

**getPixel [SimTalk]**

###### getPixel [SimTalk]

Returns the RGB value of a pixel denoted by the parameters of the object designated by &lt;Path&gt;.

**Remarks**

**Note**

The method applies to all objects, except for the Variable , the Comment , the folder and the toolbar .

Note

A 3D Only model does not provide the method getPixel .

Type

Method

Syntax

```simtalk
< Path >.getPixel(X:integer, Y:integer) → integer
```

**Parameters**

- The parameter X of data type integer designates the x-coordinate of the pixel.
- The parameter Y of data type integer designates its y-coordinate.

Return Value

The return value has the data type integer .

**Example**

```simtalk
var rgb, red, green, blue: integer
rgb := MyStation.getPixel(1,1)
red := rgb mod 256
green := (rgb div 256) mod 256
blue := rgb div (256*256)
```

**SimTalk**

setPixel [SimTalk]

**See also Pick Color**

**Replace Color**

**getRefPoint [SimTalk]**

###### getRefPoint [SimTalk]

Returns the coordinates of the reference point of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation then assigns the coordinates to the local variables, whose names you specify.

**Note**

The method applies to all objects, except for the Variable , the Comment , the Folder , and the Toolbar .

Note

A 3D Only model does not provide the method getRefPoint .

Type

Method

Syntax

```simtalk
< Path >.getRefPoint(byRef X:integer, byRef Y:integer)
```

**Local Variables**

- The local variable X of data type integer designates the x-coordinate of the reference point.
- The local variable Y of data type integer designates its y-coordinate.

**Example**

```simtalk
var x,y: integer
MyStation.getRefPoint(x,y)
```

SimTalk

setRefPoint [SimTalk]

See also

Set Reference Point [command]

###### linkAniPoint [SimTalk]

Assigns animation points between the Frame designated by &lt;Path&gt; and the designated object located within that Frame .

Remarks

You might have to change the current icon of the objects beforehand.

**Note**

A 3D Only model does not provide the method linkAniPoint .

Type

Method

Syntax

```simtalk
< Path >.linkAniPoint(AnimationpointNumber:integer, LinkTo:object, LinkToAnimationNumber:integer) → boolean
```

**Parameters**

- The parameter AnimationpointNumber of data type integer designates the animation number of the Frame .
- The parameter LinkTo of data type object designates the object located within that Frame .
- The parameter LinkToAnimationNumber of data type integer designates the animation number of the object which you inserted into the Frame .

**Return Value**

The return value has the data type boolean .

true if Plant Simulation established the connection.

false if Plant Simulation did not succeed in creating a connection because, for example, the number of the animation point is not valid or the object is not located in the Frame .

**Example**

```simtalk
var up, down: integer // current icons are correct
down :=.Example.Track.setAniPoint(5,5) // create aniPoint in object
up := .example.setAniPoint(12,14) // create aniPoint in Frame
Example.linkAniPoint(up,.Example.Track,down) // create the connection
```

**SimTalk**

unlinkAniPoint [SimTalk]

See also

unlinkAniPoint [SimTalk]

###### mirrorX [SimTalk] - general description

Mirrors the icon of the object designated by &lt;Path&gt; on the x-axis.

Remarks

Plant Simulation mirrors the icon vertically and thus reverses top and bottom.

Note

You cannot flip icons in the Class Library .

Note

A 3D Only model does not provide the method mirrorX .

Type

Method

Syntax

&lt; Path &gt;.mirrorX

Example

MyStation.mirrorX

SimTalk

mirrorY [SimTalk] - general description

See also

Mirror Vertically

mirrorY [SimTalk] - general description

Mirrors the icon of the object designated by &lt;Path&gt; on the y-axis.

Remarks

Plant Simulation mirrors the curved object horizontally and thus reverses left and right.

Note

You cannot flip icons in the Class Library .

Note

A 3D Only model does not provide the method mirrorY .

Type

Method

Syntax

&lt; Path &gt;.mirrorY

Example

MyStation.mirrorY

SimTalk

mirrorX [SimTalk] - general description

See also

Mirror Horizontally

###### moveAniPoint [SimTalk]

Moves the animation point or the animation line of the object designed by &lt;Path&gt;.

Remarks

**Note**

Plant Simulation does not break the link with the underlying object, but only moves the animation point/line.

**Note**

A 3D Only model does not provide the method moveAniPoint .

Type

Method

Syntax

```simtalk
< Path >.moveAniPoint(AnimationpointNumber:integer, NewX1:integer, NewY1:integer [,NewX2:integer, NewY2:integer, ...]) → boolean
```

**Parameters**

- The parameter AnimationpointNumber of data type integer designates the number of the animation point/line.
- The parameter NewX1 of data type integer designates its new x-coordinate.
- The parameter NewY1 of data type integer designates its y-coordinate.

If you move an animation line , the parameters integer and integer designate the first anchor point of the animation line.

- Additional parameters of data type integer designate any remaining new coordinates.

Return Value

The return value has the data type boolean .

**Example**

.Materialflow.Buffer.moveAniPoint(3,15,25,35,35,15)

**See also**

**Move Animation Point**

###### openImg [SimTalk]

Opens the Icon Editor with the icon of the object designated by &lt;Path&gt;.

Remarks

If the Icon Editor is already open, Plant Simulation prompts you to save your previous work. Only then does it open the other icon. If you do not save the previous changes, the first icon will remain open and the method will have no effect.

**Note**

The objects Comment, Connector , and Variable do not have icons.

Note

A 3D Only model does not provide the method openImg .

Type

Method

Syntax

&lt; Path &gt;.openImg

Example

```simtalk
MyStation.openImg
table.openImg
```

See also

Import

Edit Icons [Home ribbon]

###### putIconToClipboard [SimTalk]

putIconToClipboard [SimTalk]

Opens the Windows clipboard and stores the current icon of the object designated by &lt;Path&gt; in CF\_BITMAP format.

Remarks

putIconToClipboard may fail because:

- The Clipboard is locked by another application.
- The icon designated by the parameter does not exist.

Type

Method

Syntax

```simtalk
< Path >.putIconToClipboard(IconName:string) → boolean < Path >.putIconToClipboard(IconNumber:integer) → boolean
```

**Parameter**

The parameter IconName of data type string designates the name of the icon .

Instead, you can also enter the number of the icon as the parameter IconNumber of data type integer .

Return Value

The return value has the data type boolean .

true if the assignment was successful.

false if the assignment failed.

Example

MyStation.putIconToClipboard(3)

See also

setCurrIconFromClipboard [SimTalk]

###### resetIcon [SimTalk]

Resets the icon of the object designed by &lt;Path&gt; to the state it had before you rotated it.

Remarks

A 3D Only model does not provide the method resetIcon .

Type

Method

Syntax

&lt; Path &gt;.resetIcon

Example

Station1.resetIcon

See also

Reset Icon

###### saveIconToFile [SimTalk]

saveIconToFile [SimTalk]

Saves the icon of the object designed by &lt;Path&gt; as a png file to the Plant Simulation installation folder.

Type

Method

Syntax

```simtalk
< Path >.saveIconToFile(IconName:string, FileName:string) → boolean < Path >.saveIconToFile(IconNumber:string, FileName:string) → boolean
```

**Parameters**

- The parameter IconName of data type string designates the name of the icon . Instead, you can also enter the number of the icon as the parameter IconNumber of data type integer .
- The parameter FileName of data type string designates the filename with which Plant Simulation saves the graphics file.

Return Value

The return value has the data type boolean .

false if saving the icon to a file failed.

**Example**

sp1.saveIconToFile(3,"iconfile")

sp1.saveIconToFile("icon_name","iconfile")

**See also**

Export Icon to File

###### setAniLine [SimTalk]

Adds a new animation line in the active icon of the class of the object designed by &lt;Path&gt;.

Remarks

As only the Frame can have several animation lines, Plant Simulation replaces the existing animation line with the one you insert for all other objects.

**Note**

A 3D Only model does not provide the method setAniLine .

Type

Method

Syntax

&lt; Path &gt;.setAniLine(X1:integer, Y1:integer, X2:integer, Y2:integer, ...) → integer

**Parameters**

- The parameter X1 of data type integer designates the x-coordinate of the starting point of the animation line.
- The parameter Y1 of data type integer designates its y-coordinate.
- The parameter X2 of data type integer designates the x-coordinate of the end point of the animation line.
- The parameter Y2 of data type integer designates its y-coordinate. In between you can insert any number of pairs of coordinates for anchor points. Plant Simulation returns the number of the new animation line.

Return Value

The return value has the data type integer .

**Example**

.Materialflow.Buffer.setAniLine(5,5,20,35,35,5) // V-shaped line SimTalk getAniPoints [SimTalk] See also Add/Remove Animation Line Add/Remove Animation Polyline

###### setAniPoint [SimTalk]

Adds a new animation point in the active icon of the class of the object designed by &lt;Path&gt;.

Remarks

You might have to change the current icon of the class beforehand.

**Note**

A 3D Only model does not provide the method setAniPoint .

Type

Method

Syntax

```simtalk
< Path >.setAniPoint(X:integer, Y:integer) → integer
```

**Parameters**

- The parameter X of data type integer designates the x-coordinate of the animation point.
- The parameter Y of data type integer designates its y-coordinate.

Return Value

The return value has the data type integer .

It is the number of the new animation point.

**Example**

```simtalk
var previousNumber: integer
previousNumber := .Example.CurrIconNo   // saves the current icon number
Station1.CurrIconNo := 1                // sets the active icon
pointNr := .Example.setAniPoint(10,10)  // saves the number
Station1.CurrIconNo := previousNumber   // restores the previous icon
```

**SimTalk**

setAniLine [SimTalk]

getAniPoints [SimTalk]

**See also**

**Add/Remove Animation Point**

###### setCurrIconFromClipboard [SimTalk]

Opens the clipboard, reads the bitmap stored there and converts it to the Plant Simulation format.

**Remarks**

Plant Simulation then assigns the bitmap to the icon defined by the parameter IconName of data type string , or the number defined by the parameter IconNumber of data type integer and sets it as the current icon of the object designed by &lt;Path&gt;.

**Note**

The method applies to the icon of the addressed instance, not to the icon of the object class.

setCurrIconFromClipboard may fail because:

- The Clipboard is locked by another application.
- The Clipboard does not contain an image in CF\_BITMAP format.
- The icon designated by the parameter does not exist.

Type

Method

Syntax

```simtalk
< Path >.setCurrIconFromClipboard(IconName:string) → boolean < Path >.setCurrIconFromClipboard(IconNumber:integer) → boolean
```

**Parameter**

The parameter IconName of data type string designates the name of the icon .

Instead, you can also specify the number of the icon as the parameter IconNumber of data type integer .

Return Value

The return value has the data type boolean .

true if the assignment was successful.

false if the assignment failed.

**Example**

MyFrame.setCurrIconFromClipboard(3) MyFrame.setCurrIconFromClipboard("MyIcon")

**See also**

Paste Contents of the Clipboard [Home ribbon]

###### setIconFromFile [SimTalk]

Sets the icon of the object designed by &lt;Path&gt; to a number and overwrites the icon of the file with a graphics file.

**Remarks**

**Note**

setIconFromFile applies to the icon of the addressed instance, not to icon of the object class.

Type

Method

Syntax

```simtalk
< Path >.setIconFromFile(IconName:string, FileName:string) → boolean < Path >.setIconFromFile(IconNumber:integer, FileName:string) → boolean
```

**Parameters**

- The parameter IconName of data type string designates the name of the icon . Instead, you can also enter the number of the icon as the parameter IconNumber of data type integer .
- The parameter FileName of data type string designates the file name of the graphic, which overwrites the current icon.

The graphics file of the icon may be located in a folder of your choice.

**Return Value**

The return value has the data type boolean .

false if the method fails and does not make changes.

**Example**

MyStation.setIconFromFile(3,"outOfOrder.gif") MyStation.setIconFromFile("failed","C:\graphics\outOfOrder.gif")

**See also**

Import

**setIconSize [SimTalk]**

###### setIconSize [SimTalk]

Sets the size, i.e., the width and the height of the current icon of the object designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.setIconSize(Width:integer, Height:integer)

**Parameters**

- The parameter Width of data type integer designates the width of the current icon.
- The parameter Height of data type integer designates its height.

**Example**

MyStation.setIconSize(44, 44)

SimTalk

getIconSize [SimTalk]

Set Icon Size

###### setPixel [SimTalk]

Sets the pixel of the point of the icon of the object designated by &lt;Path&gt;.

Remarks

Since all objects of the same class share their icons, Plant Simulation changes the pixel in the class and in all derivatives.

Note

The method applies to all objects, except for the Variable , the Comment , the folder , and to the toolbar .

Note

A 3D Only model does not provide the method setPixel .

Type

Method

Syntax

&lt; Path &gt;.setPixel(X:integer, Y:integer, RGB:integer) → integer

**Parameters**

- The parameter X of data type integer designates the x-coordinate of the pixel of the icon designated by &lt;Path&gt;.
- The parameter Y of data type integer designates its y-coordinate.
- The parameter RGB of data type integer designates its color.
- Set the RGB values of the color with the method makeRGBValue .

Return Value

The return value has the data type integer .

Example

// sets the pixel in the upper left corner to pink MyStation.setPixel(1,1,makeRGBValue(255,0,255)) MyStation.redraw

<!-- image -->

###### setRefPoint [SimTalk]

Sets the position of the reference point of the object designated by &lt;Path&gt;.

Remarks

Note

setRefPoint applies to the icon of the addressed instance, not to icon of the object class.

Note

A 3D Only model does not provide the method setRefPoint .

Type

Method

Syntax

&lt; Path &gt;.setRefPoint(X:integer, Y:integer)

**Parameters**

- The parameter X of data type integer designates the x-coordinate of the reference point.
- The parameter Y of data type integer designates its y-coordinate.

Example

MyStation.setRefPoint(15,20)

SimTalk

getRefPoint [SimTalk]

See also

Set Reference Point [command]

**turnIcon [SimTalk]**

###### turnIcon [SimTalk]

Rotates the icon of the object designed by &lt;Path&gt; 90 degrees clockwise.

Remarks

**Note**

You cannot rotate the icons in the Class Library .

**Note**

For the length-oriented objects with activated Curve mode the method turnIcon only affects the icon of the object. If you want to rotate the curved object, you have to use the method rotate and specify an angle.

**Note**

A 3D Only model does not provide the method turnIcon .

Type

Method

Syntax

```simtalk
< Path >.turnIcon < Path >.turnIcon(Angle:real)
```

Parameter

The parameter Angle of data type real designates the angle by which the icon is rotated.

Specify a positive number to rotate the icon clockwise.

Specify a negative number to rotate the icon counter-clockwise.

Example

MyStation.turnIcon              // rotates by 90° clockwise MyStation.turnIcon(35)          // rotates by 35° clockwise MyStation.turnIcon(-45)         // rotates by 45° counterclockwise

**SimTalk rotate [SimTalk] - curved object See also**

**Rotate Icon**

###### unlinkAniPoint [SimTalk]

Breaks the link between two animation points between the Frame designated by &lt;Path&gt; and an object located in the Frame .

Remarks

It may be necessary to change the active icons of the objects.

Note

A 3D Only model does not provide the method unlinkAniPoint .

Type

Method

Syntax

&lt; Path &gt;.unlinkAniPoint(AnimationpointNumber:integer) → boolean

**Parameter**

The parameter AnimationpointNumber of data type integer designates the number of the animation point in the Frame .

Return Value

The return value has the data type boolean .

true if unlinking the link succeeded.

false if no link was unlinked or when the value was located outside of the valid range.

Example

current.unlinkAniPoint(1)

SimTalk

linkAniPoint [SimTalk]

**See also**

**Link Animation Point**

Methods for the Location, Predecessor, and Successor

\_Methods for the Location, Predecessor, and Successor

Most of the objects provide the methods listed in the table of contents to the left for querying their location, their predecessor, and their successor.

To view all of the methods and attributes of the material flow object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

###### pred [SimTalk] - general description

pred [SimTalk] - general description

Returns the direct predecessor of the object designated by &lt;Path&gt;. Or returns the predecessor with the specified number of the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.pred → object < Path >.pred([PredecessorNumber:integer:=1]) → object
```

Parameter

The optional parameter PredecessorNumber of data type integer designates the number of the predecessor.

**Default Value of the Parameter**

The default value is 1, meaning the first predecessor.

Return Value

The return value has the data type object .

**Note**

If the specified predecessor of the object is an Interface , the method does not return the Interface itself, but the predecessor of the Interface . If this successor in turn is another Interface , Plant Simulation follows it until it reaches a material flow object, which can receive MUs .

If the specified predecessor of the object is a Frame , Plant Simulation does not return the Frame itself, but the predecessor of the Interface inserted into this Frame .

**Example**

```simtalk
if model.pred(3).name = "press" ...
end
```

SimTalk

pred [SimTalk] - lane A or B

predConnector [SimTalk] - general description NumPred [SimTalk] - general description See also

Show Predecessors [View ribbon] - 2D

predConnector [SimTalk] - general description

Returns the connection to the immediate predecessor of the object designated by &lt;Path&gt;. Or returns the connection to the predecessor designated by its number of the object designated by &lt;Path&gt;.

Remarks

Adding and deleting connections may change the index number of a connection.

Type

Method

Syntax

```simtalk
< Path >.predConnector → object < Path >.predConnector([PredecessorNumber:integer:=1]) → object
```

**Parameter**

The optional parameter PredecessorNumber of data type integer designates the number of the predecessor.

**Default Value of the Parameter**

The default value is 1, meaning the first predecessor.

Return Value

The return value has the data type object .

VOID if the connection does not exist.

Example

```simtalk
for var i := MyTrack.NumPred downto 1 // deletes connections with predecessors
	MyTrack.predConnector(i).deleteObject
next
```

SimTalk

pred [SimTalk] - general description

predConnector [SimTalk] - lane A or B

**See also**

**Show Predecessors [View ribbon] - 2D**

###### succ [SimTalk] - general description

succ [SimTalk] - general description

Returns the direct successor of the object designated by &lt;Path&gt;. Or returns the successor with the specified number of the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.succ → object < Path >.succ([SuccessorNumber:integer:=1]) → object
```

Parameter

The optional parameter SuccessorNumber of data type integer designates the number of the successor.

**Default Value of the Parameter**

The default value is 1, meaning the first successor.

Return Value

The return value has the data type object .

**Note**

If the specified successor of the object is an Interface , the method does not return the Interface itself, but the successor of the Interface . If this successor in turn is another Interface , Plant Simulation follows it until it reaches a material flow object, which can receive MUs .

If the specified successor of the object is a Frame , Plant Simulation does not return the Frame itself, but the successor of the Interface inserted into this Frame .

If an Interface has a single successor, this successor is uniquely identified and Plant Simulation uses it independently of the Exit strategy of the Interface .

If an Interface has several successors, Plant Simulation determines the successor using its Exit strategy . If you selected a blocking Exit strategy , Plant Simulation determines the successor no matter if this successor can receive a MU at the moment or not. If you selected a non-blocking Exit strategy , Plant Simulation tries to determine the next successor, which can receive MUs , according to the selected Exit strategy . If no successor can receive a MU , the method returns VOID. The successor, which will be able to receive MUs next cannot be determined at this point in time. This does not apply if there is only one successor.

**Example**

@.move(ParallelStation.succ(3))

**SimTalk**

succ [SimTalk] - lane A or B

succConnector [SimTalk] - general description

NumSucc [SimTalk] - general description

See also

Show Successors [View ribbon] - 2D

###### succConnector [SimTalk] - general description

Returns the connection to the immediate successor of the object designated by &lt;Path&gt;. Or returns the connection to the successor with the designated number of the object designated by &lt;Path&gt;.

Remarks

Adding and deleting connections may change the index number of a connection.

Type

Method

Syntax

```simtalk
< Path >.succConnector → object < Path >.succConnector([SuccessorNumber:integer:=1]) → object
```

**Parameter**

The optional parameter SuccessorNumber of data type integer designates the number of the successor.

**Default Value of the Parameter**

The default value is 1, meaning the first successor.

Return Value

The return value has the data type object .

VOID if the Connector does not exist.

Example

```simtalk
MyTrack.succConnector.deleteObject // delete the connector to the succeeding object
```

SimTalk

succ [SimTalk] - general description

succConnector [SimTalk] - lane A or B

**See also**

**Show Successors [View ribbon] - 2D**

**Methods for Managing Inheritance Relations**

##### \_Methods for Managing Inheritance Relations

Most objects provide the methods listed in the table of contents to the left for returning inheritance relations.

To view all of the methods and attributes of the material flow object, open the window Show Attributes and Methods [described] . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

###### childNo [SimTalk]

childNo [SimTalk]

Returns all instances of the class of the object designated by &lt;Path&gt;.

Remarks

This is independent of the name of the instance or the Frame into which the instance is inserted.

Type

Method

Syntax

```simtalk
< Path >.childNo(Number:integer) → object
```

Parameter

The parameter Number of data type integer designates the number in the list of children ( instances ) of the object. You can query the size of the list with the read-only attribute NumChildren .

Return Value

The return value has the data type object .

Example

```simtalk
for var index := 1 to .MUs.Transporter.NumChildren
	print .MUs.Transporter.childNo(index) // outputs all children
next
```

SimTalk

**NumChildren [SimTalk]**

See also

Instance

###### hasAttribute [SimTalk] - 2D

Returns if the object designated by &lt;Path&gt; has the attribute with the designated name (true) or not (false).

Type

Method

Syntax

```simtalk
< Path >.hasAttribute(AttributeName:string) → boolean
```

Parameter

The parameter AttributeName of data type string designates the name of the attribute of which you want to know if the object has it or not.

Return Value

The return value has the data type boolean .

true if the object has the attribute that can be read.

false for the parameter Imp , SetupImp , and FailImp if this attribute does not exist for the specified object.

**Example**

```simtalk
print Station.hasAttribute("Availability")
print Conveyor.hasAttribute("Imp")       -- returns false
print Conveyor.hasAttribute("FailImp")   -- returns false
print Conveyor.hasAttribute("SetupImp")  -- returns false
```

**SimTalk**

\_3D.hasAttribute [SimTalk]

isNameUnique [SimTalk] - identifier

###### inheritAttribute [SimTalk] - object

inheritAttribute [SimTalk] - object

Activates inheritance of the specified attribute of the object designated by &lt;Path&gt; if it was deactivated.

Type

Method

Syntax

&lt; Path &gt;.inheritAttribute(AttributeName:string)

Parameter

The parameter AttributeName of data type string designates the name of the attribute.

Example

Conveyor.inheritAttribute("Length") Conveyor.Sensors.ID1.inheritAttribute("Position") Station.Failures.Failure.inheritAttribute("Availability") Station.Imp.inheritAttribute("Priority") Station._3D.inheritAttribute("VisibleGraphicGroups") &Variable.inheritAttribute("Value")

SimTalk

**\_3D.inheritAttribute [SimTalk]**

See also

Instance

###### typeOf [SimTalk]

Returns if the object designated by &lt;Path&gt; has the same internal class type as the comparison object, i.e., if both have the same internal class type (true) or not (false).

Type

Method

Syntax

```simtalk
< Path >.typeOf(ObjectToBeCompared:object) → boolean
```

Parameter

The parameter ObjectToBeCompared of data type object designates the comparison object.

Return Value

The return value has the data type boolean .

Example

```simtalk
print MyStation.typeOf(station2)
```

// returns true if each station is of type Station

See also

inheritAttribute [SimTalk] - object

\_3D.InternalClassType [SimTalk]

Methods for Managing Attributes

\_Methods for Managing Attributes

Most objects provide the methods listed in the table of contents to the left for managing their attributes.

To view all of the methods and attributes of the material flow object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

getAttribute [SimTalk] - object

Returns the value of an attribute of the object designated by &lt;Path&gt;.

Remarks

If the attribute is a user-defined attribute of data type method , getAttribute returns the method itself.

```simtalk
var bInherited:boolean
Station.getAttribute("MyMethodAttribute", bInherited) // does not call MyMethodAttribute
```

To get the result of the method call instead of the method itself, you have to explicitly call the method:

Station.getAttribute("MyMethodAttribute").execute

Type

Method

Syntax

```simtalk
< Path >.getAttribute(AttributeName:string[, byRef Inherited:boolean, byRef CanInherit:boolean]) → any
```

**Parameters**

- The parameter AttributeName of data type string designates the value of the attribute.
- When a local variable of data type boolean is passed to the optional parameter Inherited , Plant Simulation assigns true to this variable if the attribute designated by string inherits its value, false if it does not inherit the value.

In case an attribute cannot be inherited, the optional parameter Inherited always returns false.

- When a local variable of data type boolean is passed to the optional parameter CanInherit , Plant Simulation assigns true to this variable if the value of the attribute designated by string can be inherited, false if it cannot be inherited.

Return Value

The return value has the data type any .

**Examples**

```simtalk
print MyStation.getAttribute("ProcTime")
```

// checks if inheritance of the attribute 'Accumulating' is active or not

```simtalk
var inherited: boolean
print MyConveyor.getAttribute("Accumulating", inherited)
print inherited
var ResultOfMethod := Station.getAttribute("MethodAttributeWithoutParameters")
var
Result := Station.getAttribute("MethodAttributeWith2Parameters").execute(5, 9)
```

// Check if the source code of the Method is inherited

```simtalk
var bInherit:boolean &Method.getAttribute("Program", bInherit)
print bInherit
SimTalk getSubAttribute [SimTalk] setSubAttribute [SimTalk] setAttribute [SimTalk] - object putAttributeNamesIntoTable [SimTalk] - objects See also Inheritance [general description] Inherit Source Code isNameUnique [SimTalk] - identifier
_3D.getAttribute [SimTalk]
```

**getSubAttribute [SimTalk]**

Returns the value of a sub-attribute of the specified attribute of the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.getSubAttribute(AttributeName:string, SubAttributeName:string) → any < Path >.getSubAttribute(AttributeName:string, SubAttributeName:string[, Inherited:boolean]) → any
```

**Parameters**

- The parameter AttributeName of data type string designates the attribute.
- The parameter SubAttributeName of data type string designates the value of the sub-attribute.
- The optional parameter Inherited of data type boolean determines if the method ignores the value, which you enter as the parameter of data type boolean , and returns, if the attribute is inherited (true) or not (false).

**Return Value**

The return value has the data type any .

**Examples**

```simtalk
var b: boolean
print MyStation.getSubAttribute("ProcTime","Type", b)
print b // the
return value true means that the attribute is inherited, // the
return value false that it is not inherited
print MyStation.getSubAttribute("ProcTime","Type") // "Normal"
print MyStation.getSubAttribute("ProcTime","Mu")   // 1:00.0000
```

**SimTalk**

```simtalk
getAttribute [SimTalk] - object putAttributeNamesIntoTable [SimTalk] - objects setAttribute [SimTalk] - object
```

setTypeAndAttr [SimTalk]

setSubAttribute [SimTalk]

###### putAttributeNamesIntoTable [SimTalk] - objects

Writes the names and the data types of all attributes of the object designated by &lt;Path&gt; into a table.

Remarks

If you do not specify any optional parameters, the method does not return the read-only attributes .

Type

Method

Syntax

```simtalk
IncludeUserDefinedAttribute:boolean:=false, IncludeMethods:boolean:=false,
< Path >.putAttributeNamesIntoTable(Table:table) < Path >.putAttributeNamesIntoTable(Table:table[, Language:integer:=ModelLanguage])
```

**Parameters**

- The parameter Table of data type table designates the table.

The column named Signature of the parameter Table contains the complete signature of a built-in Method , instead of only the parameters of this built-in Method .

The column named Side Effect contains a boolean value, which designates if read access has a side effect or only returns a value.

**Example**

Station.putAttributeNamesIntoTable(DataTable,true,true,UserInterfaceLangua ge)

The instructions above return this DataTable :

<!-- image -->

- The optional parameter IncludeUserDefinedAttribute of data type boolean determines if Plant Simulation also writes user-defined attributes into the table ( true ). If you enter false , Plant Simulation only writes the names of the built-in attributes into the table.

**Default Value of the Parameter**

The default value is false.

- The optional parameter IncludeMethods of data type boolean determines if Plant Simulation not only writes the names of the attributes into the table, but also those of the methods and of the read-only attributes ( true ). If the parameter IncludeUserDefinedAttribute is true as well, Plant Simulation also writes the names of the user-defined methods and read-only attributes into the table.

**Default Value of the Parameter**

The default value is false.

- The optional parameter Language of data type integer sets the language in which Plant Simulation shows the names of the attributes. 0 designates German , 1 designates English . If you do not specify this parameter, Plant Simulation shows the names of the attributes in the language of the model.

**Default Value of the Parameter**

The default value is ModelLanguage .

**Example**

MyStation.putAttributeNamesIntoTable(MyDataTable)

The instructions above return this DataTable :

<!-- image -->

**SimTalk**

| getAttribute [SimTalk] - object   | language [SimTalk]                  |
|-----------------------------------|-------------------------------------|
| getSubAttribute [SimTalk]         | userInterfaceLanguage [SimTalk]     |
| setAttribute [SimTalk] - object   | isNameUnique [SimTalk] - identifier |
| setSubAttribute [SimTalk]         |                                     |

###### setAttribute [SimTalk] - object

setAttribute [SimTalk] - object

Sets the value of the specified attribute of the object designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.setAttribute(AttributeName:string, Value:any)

**Parameters**

- The parameter AttributeName of data type string designates the attribute.
- The parameter Value of data type any designates the value.

**Example**

MyStation.setAttribute("ProcTime",5)

**SimTalk**

getAttribute [SimTalk] - object

getSubAttribute [SimTalk]

putAttributeNamesIntoTable [SimTalk] - objects

setSubAttribute [SimTalk]

See also

isNameUnique [SimTalk] - identifier

###### setSubAttribute [SimTalk]

Sets the value of a sub-attribute of the specified attribute of the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.setSubAttribute(AttributeName:string, SubAttributeName:string, Value:any)
```

**Parameters**

- The parameter AttributeName of data type string designates the attribute.
- The parameter SubAttributeName of data type string designates the sub-attribute.
- The parameter Value of data type any designates the value of the sub-attribute.

**Example**

MyStation.setSubAttribute("ProcTime","Type","uniform")

**SimTalk**

getAttribute [SimTalk] - object

getSubAttribute [SimTalk]

putAttributeNamesIntoTable [SimTalk] - objects

setAttribute [SimTalk] - object

See also

isNameUnique [SimTalk] - identifier

setTypeAndAttr [SimTalk]

Methods for Managing User-defined Attributes

\_Methods of User-defined Attributes

Most objects provide the methods listed in the table of contents to the left for working with the userdefined attributes of the objects, which you define on the Tab User-defined .

The window Show Attributes and Methods shows the user-defined attribute itself and its value.

<!-- image -->

**See also**

User-defined Attributes [general description]

Create a User-defined Attribute Manually

Create a User-defined Attribute During the Simulation

\_Attributes of User-defined Attributes

**createAttr [SimTalk]**

Creates the designated user-defined attribute for the object designated by &lt;Path&gt;.

Remarks

The attribute will be propagated to all of its instances.

Type

Method

Syntax

```simtalk
< Path >.createAttr(AttributeName:string, DataType:string) → boolean
```

**Parameters**

- The parameter AttributeName of data type string designates the name of the user-defined attribute .
- The parameter DataType of data type string designates its data type.

Return Value

The return value has the data type boolean .

false if the new name or the data type is not valid.

Example

```simtalk
MyStation.createAttr("lotsize","integer")
MyStation.createAttr("inventoryNo","string")
@.createAttr("Paint","boolean")
```

SimTalk

deleteAttr [SimTalk]

See also

User-defined Attributes [general description]

Create a User-defined Attribute During the Simulation

New [user-defined attribute]

###### deleteAttr [SimTalk]

Deletes the designated user-defined attribute of the object designated by &lt;Path&gt;.

Remarks

You can only delete user-defined attributes for the object for which you created them and for which they are not inherited. Plant Simulation deletes the user-defined attributes from all instances of the object.

**Note**

Deleting an object will automatically also delete all of its user-defined attributes .

Type

Method

Syntax

```simtalk
< Path >.deleteAttr(AttributeName:string) → boolean
```

Parameter

The parameter AttributeName of data type string designates the user-defined attribute .

Return Value

The return value has the data type boolean .

Examples

```simtalk
.MUs.Part.deleteAttr("lotsize")
```

@.deleteAttr("Paint")

SimTalk

createAttr [SimTalk]

See also

User-defined Attributes [general description]

**deleteAttr [SimTalk]**

**Create a User-defined Attribute During the Simulation Delete [user-defined attribute]**

###### getAttribute [SimTalk] - user-defined attribute

Returns the inheritance status of the designated user-defined attribute of the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.<UserDefinedAttribute>.getAttribute(AttributeName:string, byref Inherited:boolean, byref CanInherit:boolean)
-> any
```

**Parameters**

- The parameter AttributeName of data type string designates the name of the attribute of the userdefined attribute .
- If a local variable of data type boolean is passed to the parameter Inherited , Plant Simulation assigns true to this variable if the attribute designated by string inherits its value, false if it does not inherit the value.

In case an attribute cannot be inherited, the optional parameter Inherited always returns false.

- If a local variable of data type boolean is passed to the parameter CanInherit , Plant Simulation assigns true to this variable if the value of the attribute designated by string can be inherited, false if it cannot be inherited.

**Return Value**

The return value has the data type any .

**Example**

```simtalk
var bInherited:boolean
var bCanInherit:boolean
MyStation.On.getAttribute("Value", bInherited, bCanInherit)
MyStation.On.getAttribute("InitValue", bInherited, bCanInherit)
MyStation.On.getAttribute("HasInitValue", bInherited, bCanInherit)
```

<!-- image -->

SimTalk setAttribute [SimTalk] - user-defined attribute See also User-defined Attributes [general description] Create a User-defined Attribute During the Simulation

###### getAttrName [SimTalk]

Returns the name of the designated user-defined attribute of the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.getAttrName(AttributeNumber:integer) → string
```

Parameter

The parameter AttributeNumber of data type integer designates the name of the user-defined attribute . Plant Simulation shows an error message if the allowed index range is exceeded.

Return Value

The return value has the data type string .

Example

```simtalk
// lists all user-defined attributes of the object
for var index := 1 to MyStation.NumAttr
	print MyStation.getAttrName(index)
next
```

See also

User-defined Attributes [general description]

New [user-defined attribute]

###### getAttrNo [SimTalk]

getAttrNo [SimTalk]

Returns the index number of the designated user-defined attribute of the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.getAttrNo(AttributeName:string) → integer
```

Parameter

The parameter AttributeName of data type string designates the name of the user-defined attribute .

Return Value

The return value has the data type integer .

0 if no user-defined attribute with the specified AttributeName exists.

Examples

```simtalk
param lookFor: string -> any // checks if a user-defined object exists or not and // returns its value if it exists
var index: integer := MyStation.getAttrNo(lookFor)
if index > 0
	return MyStation.getAttrValue(index)
end
param lookFor: string -> boolean // checks if a user-defined object exists or not
var index: integer index := MyStation.getAttrNo(lookFor)
if index = 0
	result := false // does not exist
else
	result := true // exists
end
```

See also

User-defined Attributes [general description]

**New [user-defined attribute]**

###### getAttrType [SimTalk]

getAttrType [SimTalk]

Returns the data type of the designated user-defined attribute of the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.getAttrType(AttributeNumber:integer) → string
```

Parameter

The parameter AttributeNumber of data type integer designates the user-defined attribute .

Return Value

The return value has the data type string .

Example

```simtalk
// lists the data types of all user-defined attributes
for var index := 1 to MyStation.NumAttr
	print MyStation.getAttrType(index)
next
```

See also

User-defined Attributes [general description]

New [user-defined attribute]

###### getAttrValue [SimTalk]

Returns the value of the designated user-defined attribute of the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.getAttrValue(AttributeNumber:integer) → any
```

Parameter

The parameter AttributeNumber of data type integer designates the user-defined attribute . The data type of the value depends on the type of the attribute.

Return Value

The return value has the data type any .

Example

```simtalk
print MyStation.getAttrValue(1)
```

See also

User-defined Attributes [general description]

New [user-defined attribute]

inheritAttribute [SimTalk] - user-defined attribute

Turns inheritance of the attribute designated by AttributeName of the user-defined attribute of the object designated by &lt;Path&gt; on if it was turned off.

Remarks

If several attributes are inherited together, all attributes will be inherited, when you turn inheritance of a single attribute on.

Type

Method

Syntax

&lt; Path &gt;.&lt;UserDefinedAttribute&gt;.inheritAttribute(AttributeName:string)

Parameter

The parameter AttributeName of data type string designates the name of the attribute of the user-defined attribute .

Examples

Station.MyInheritedAttribute.inheritAttribute("Transparent")

MyStation.MyAttribute.inheritAttribute("InitValue")

MyStation.MyAttribute.inheritAttribute("HasInitValue")

See also

User-defined Attributes [general description]

Create a User-defined Attribute During the Simulation

###### setAttribute [SimTalk] - user-defined attribute

Sets the value of the specified attribute of the user-defined attribute of the object designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.&lt;UserDefinedAttribute&gt;.setAttribute(AttributeName:string, Value:any)

**Parameters**

- The parameter AttributeName of data type string designates the name of the attribute of the userdefined attribute .
- The parameter Value of data type any designates the value of the user-defined attribute .

**Example**

MyStation.Color.setAttribute("BackgroundColor", makeRGBValue(255, 87, 192))

The source code sets the Background Color of the user-defined attribute named Color .

**SimTalk**

getAttribute [SimTalk] - user-defined attribute

See also

User-defined Attributes [general description]

Create a User-defined Attribute During the Simulation

<!-- image -->

###### setAttrType [SimTalk]

Sets the data type of the designated user-defined attribute of the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.setAttrType(AttributeNumber:integer, DataType:string) → boolean
```

**Parameters**

- The parameter AttributeNumber of data type integer designates the index number of the user-defined attribute .
- The parameter DataType of data type string designates its data type: boolean , integer , real , string , object , table , list , stack , queue , time , money , length , weight , speed , acceleration , date , dateTime , or randtime .

Return Value

The return value has the data type boolean .

Example

```simtalk
var index: integer
index := MyStore.getAttrNo("Sale")
MyStore.setAttrType(index,"boolean")
```

See also

User-defined Attributes [general description]

New [user-defined attribute]

###### setAttrValue [SimTalk]

###### setAttrValue [SimTalk]

Sets the value of the designated user-defined attribute of the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.setAttrValue(AttributeNumber:integer, Value:any) → boolean
```

**Parameters**

- The parameter AttributeNumber of data type integer designates the index number of the user-defined attribute .
- The parameter Value of data type any designates its value.

Return Value

The return value has the data type boolean .

Example

```simtalk
var index: integer
index := MyStore.getAttrNo("Sale")
MyStore.setAttrValue(index,true)
```

See also

User-defined Attributes [general description]

New [user-defined attribute]

###### unshare [SimTalk]

Makes the user-defined attribute or Variable of the object designated by &lt;Path&gt; unshare a shared list and receive its own copy of the list.

**Remarks**

This might be required after assigning a user-defined attribute or a Variable , that has the data type table/list/stack/queue , to another user-defined attribute of the same data type. Then both attributes are independent of each other instead of using the same list.

It might also be required when user-defined attributes of data type table/list/stack/queue , are created when producing MUs with a Delivery table with a Source .

When assigning a user-defined attribute of data type table/list/stack/queue to another user-defined attribute , Plant Simulation does not copy the list, but creates a reference to that list. Both user-defined attributes then share the same list, i.e., if one of the two user-defined attributes is changed, this also changes the contents of the other one.

If you do not want this behavior, use the method unshare for one of the two user-defined attributes . This results in the respective user-defined attribute having its own copy of the list. This way both user-defined attributes are independent of each other.

**Note**

This also applies to objects of type Variable of data type table/list/stack/queue .

Type

Method

Syntax

&lt; Path &gt;.unshare

**Example**

```simtalk
Station.TabAttr := ParallelStation.TabAttr
Station.TabAttr[1,1] := "Alice" // share the user-defined table attributes ParallelStation.TabAttr[1,1] := "Bob" // change the value in the common table
print Station.TabAttr[1,1] // prints Bob ParallelStation.TabAttr.unshare // now both attributes have their own table
ParallelStation.TabAttr[1,1] := "Charlie"
print Station.TabAttr[1,1] // prints Bob
```

See also

Sequence Cyclical [MU selection]

Sequence [MU selection]

Random [MU selection]

Percentage [MU selection]

Value [Variable] &gt; Unshare

Variable [object]

Unshare a List or Data Table

Miscellaneous Methods of User-defined Attributes

Miscellaneous Methods of User-defined Attributes

Most objects provide the methods listed in the table of contents to the left for the user-defined attributes themselves:

getStatisticsTable

increment [SimTalk]

The window Show Attributes and Methods shows the user-defined attribute itself and its value.

<!-- image -->

**See also**

User-defined Attributes [general description]

Create a User-defined Attribute Manually

Create a User-defined Attribute During the Simulation

\_Methods of User-defined Attributes

\_Attributes of User-defined Attributes getStatisticsTable [SimTalk] - user-defined attribute Returns the statistics table of the user-defined attribute of the object designated by &lt;Path&gt; and writes it into a table.

Remarks

If the user-defined attribute is of data type string , Plant Simulation always lower-cases the string values in the first column.

Type

Method

Syntax

&lt; Path &gt;.&lt;UserDefinedAttribute&gt;.getStatisticsTable(TargetTable:table)

Parameter

The parameter TargetTable of data type table designates the name of the table.

Example

MyStation.MyAttribute.getStatisticsTable(MyStatisticstable)

See also

User-defined Attributes [general description]

Statistics Table [user-defined attribute]

###### increment [SimTalk] - user-defined attribute

Adds 1 (the number 1) to the user-defined attribute of the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.<UserDefinedAttribute>.increment < Path >.<UserDefinedAttribute>.increment(Number:integer) < Path >.<UserDefinedAttribute>.increment(Number:real)
```

**Parameter**

The parameter Number of data type integer or real designates the value that is added to the user-defined attribute .

**Note**

The method only applies to numerical data types. It applies to user-defined attributes and to the object Variable .

**Example**

```simtalk
MyStation.MyAttribute.increment // accomplishes the same as
MyStation.attrib := MyStation.MyAttribute + 1 MyStation.MyAttribute.increment(-1) // accomplishes the same as
MyStation.MyAttribute := MyStation.MyAttribute - 1
```

See also

User-defined Attributes [general description]

**Read-Only Attributes of All Objects**

\_Read-Only Attributes of All Objects

The simulation objects and the 3D objects provide the read-only attributes listed in the table of contents to the left.

The objects in the Class Library share the read-only attributes described below.

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print Source.Empty

##### ~ [SimTalk] (tilde) - material flow objects

Returns the object located directly above the object designated by &lt;Path&gt; in the hierarchy of the objects.

Remarks

The location of the MU is the object on which it is currently located. All other objects return the Frame in which they are located as the location.

Type

Read-only attribute

Syntax

```simtalk
< Path >.~
-> object < Path >.Location
-> object
```

Watchable

The attribute is watchable .

Return Value

The return value has the data type object .

VOID if the Worker or the AGV are on their way to their destination.

**Examples**

```simtalk
print "shaft is located on:", @.~
print "shaft is located on:", @.Location
print Preparing.~ -- Preparing is the name of a Conveyor -- returns .Models.MyCarAssembly.PaintShop.PaintLine1 -- PaintLine1 is the name of the Frame
print .MUs.Part:9.~ -- location of Part 9 -- returns .Models.MyCarAssembly.PaintShop.PaintLine1.Preparing -- Preparing is the name of a Conveyor
```

SimTalk

LocationInFrame [SimTalk]

**~ [SimTalk] (tilde) - material flow objects**

See also

Open Location [described]

<!-- image -->

on the Home Ribbon Tab

##### Class [SimTalk] - read-only attribute

Returns the class in the Class Library from which the object designated by &lt;Path&gt; was derived or instantiated, possibly over several levels.

Remarks

Compare this example: We copied the object Frame three times and named it Frame1 , Frame2 , and Frame3 . Then, we insert Frame1 into Frame2 , and Frame2 into Frame3 . When we call .Frame3.Frame2.Frame1.Class the result will be .Frame1 because .Frame1 is the object in the Class Library from which .Frame3.Frame2.Frame1 was derived.

If you use Class for an instance of an object, Plant Simulation moves up in the inheritance structure until it reaches an object in the Class Library . It then opens this object.

Type

Read-only attribute

Syntax

```simtalk
< Path >.Class → object
```

Return Value

The return value has the data type object .

Example

if class_change current.Class.openDialog end

See also

Class

Open Class [described]

Go to Class [described]

**InternalClassType [SimTalk]**

##### InternalClassType [SimTalk]

Returns the unique built-in English object name that describes the type of the object designated by &lt;Path&gt;.

**Remarks**

**Note**

This is not the localized object name that some of the localized versions of Plant Simulation show, but the English object name which we assigned.

| Return Value English Object Name   | (Information Only Respective German Object Name)   |
|------------------------------------|----------------------------------------------------|
| ActiveX                            | ActiveX                                            |
| AngularConverter                   | Eckumsetzer                                        |
| AssemblyStation                    | Montagestation                                     |
| AttributeExplorer                  | AttributExplorer                                   |
| Basis                              | Basis                                              |
| Broker                             | Broker                                             |
| Buffer                             | Puffer                                             |
| Button                             | Schaltfläche                                       |
| Chart                              | Diagramm                                           |
| Checkbox                           | Kontrollkästchen                                   |
| Comment                            | Kommentar                                          |
| Connector                          | Kante                                              |
| Container                          | Förderhilfsmittel                                  |
| Converter                          | Umsetzer                                           |
| Conveyor                           | Förderstrecke                                      |
| Cycle                              | Takt                                               |
| DataList                           | Kartei                                             |
| DataStack                          | Stapel                                             |
| DataTable                          | Tabelle                                            |
| DatatQueue                         | Warteschlange                                      |

| Return Value        | (Information Only              |
|---------------------|--------------------------------|
| English Object Name | Respective German Object Name) |
| DePortioner         | Entportionierer                |
| Dialog              | Dialog                         |
| DismantleStation    | Demontagestation               |
| Display             | Display                        |
| Drain               | Senke                          |
| DropDownList        | Dropdownliste                  |
| EventController     | Ereignisverwalter              |
| Exporter            | Exporter                       |
| FileInterface       | Dateischnittstelle             |
| FileLink            | Dateiverknüpfung               |
| FlowControl         | Flusssteuerung                 |
| FluidDrain          | Flüssigkeitssenke              |
| FluidSource         | Flüssigkeitsquelle             |
| Folder              | Ordner                         |
| FootPath            | Fußweg                         |
| Frame               | Netzwerk                       |
| GanttChart          | GanttDiagramm                  |
| GAOptimization      | GAOptimierung                  |
| GARangeAllocation   | GABereichszuordnung            |
| GASelection         | GASelektion                    |
| GASequence          | GAReihenfolge                  |
| GASetAllocation     | GAMengenzuordnung              |
| Generator           | Generator                      |
| Interface           | Übergang                       |
| LockoutZone         | Schutzkreis                    |
| Method              | Methode                        |
| Mixer               | Mixer                          |

| Return Value             | (Information Only Object   |
|--------------------------|----------------------------|
| English Object Name MQTT | Respective German MQTT     |
| ODBC                     | ODBC                       |
| OPCClassicInterface      | OPCClassicSchnittstelle    |
| Oracle                   | Oracle                     |
| ParallelStation          | Parallelstation            |
| Part                     | Fördergut                  |
| PatchMatrix              | PatchMatrix                |
| PickAndPlace             | PickAndPlace               |
| Pipe                     | Rohr                       |
| PlaceBuffer              | PlatzPuffer                |
| Portioner                | Portionierer               |
| Report                   | Bericht                    |
| ShiftCalendar            | Schichtkalender            |
| SIMIT                    | SIMIT-Schnittstelle        |
| Sorter                   | Sortierer                  |
| SQLite                   | SQLite                     |
| Station                  | Einzelstation              |
| Store                    | Lager                      |
| Tank                     | Tank                       |
| Teamcenter               | Teamcenter                 |
| TimeSequence             | Zeitleiste                 |
| Toolbar                  | Symbolleiste               |
| Track                    | Weg                        |
| Transporter              | Fahrzeug                   |

| Return Value English Object Name   | (Information Only Respective German Object Name)   |
|------------------------------------|----------------------------------------------------|
| Trigger                            | Trigger                                            |
| Turnplate                          | Drehplatte                                         |
| Turntable                          | Drehtisch                                          |
| TwoLaneTrack                       | ZweispurigerWeg                                    |
| Variable                           | Variable                                           |
| Worker                             | Werker                                             |
| WorkerPool                         | WerkerPool                                         |
| Workplace                          | Arbeitsplatz                                       |
| XMLInterface                       | XMLSchnittstelle                                   |

Type

Read-only attribute

Syntax

```simtalk
< Path >.InternalClassType → string
```

Return Value

The return value has the data type string .

Examples

```simtalk
print MyStation.InternalClassType // returns "Station", works for a Station, which you inserted into a Frame
print .Materialflow.MyStation.InternalClassType // returns "Station"
```

SimTalk

\_3D.InternalClassType [SimTalk]

typeOf [SimTalk]

**See also**

**Show Attributes and Methods [described]**

Location [SimTalk] - material flow objects

Returns the object located directly above the object designated by &lt;Path&gt; in the hierarchy of the objects.

Remarks

Instead of Location you can also type the tilde ~ .

The location of the MU is the object on which it is currently located. All other objects return the Frame in which they are located as the location.

Type

Read-only attribute

Syntax

```simtalk
< Path >.Location
-> object < Path >.~
-> object
```

Watchable

The attribute is watchable .

Return Value

The return value has the data type object .

VOID if the Worker or the AGV are on their way to their destination.

**Examples**

```simtalk
print "shaft is located on:", @.Location
print "shaft is located on:", @.~
print Preparing.Location -- Preparing is the name of a Conveyor -- returns .Models.MyCarAssembly.PaintShop.PaintLine1 -- PaintLine1 is the name of the Frame
print Preparing.Location -- Preparing is the name of a Conveyor -- returns .Models.MyCarAssembly.PaintShop.PaintLine1 -- PaintLine1 is the name of the Frame print .MUs.Part:9.Location -- location of Part 9 -- returns .Models.MyCarAssembly.PaintShop.PaintLine1.Preparing -- Preparing is the name of a Conveyor
```

**See also**

**Open Location [described]**

<!-- image -->

on the Home Ribbon Tab

LocationInFrame [SimTalk]

###### NumAttr [SimTalk]

Returns the number of user-defined attributes of the object designated by &lt;Path&gt;.

Remarks

The first user-defined attribute has the number 1. If no user-defined attributes exist, Plant Simulation returns 0.

Type

Read-only attribute

Syntax

< Path >.NumAttr

Return Value

The return value has the data type integer .

Example

```simtalk
var index: integer
for index := 1 to MyStation.NumAttr
print MyStation.getAttrName(index)
next
```

**See also**

User-defined Attributes [general description]

New [user-defined attribute]

##### NumChildren [SimTalk]

NumChildren [SimTalk]

Returns the number of children of the object designated by &lt;Path&gt; and which inherit their settings from it.

Type

Read-only attribute

Syntax

```simtalk
< Path >.NumChildren → integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
print MyStation.NumChildren
print Transporter.NumChildren
```

SimTalk

childNo [SimTalk]

See also

Instance

**Origin [SimTalk] - general description**

Returns the object from which the object designated by &lt;Path&gt; was derived most recently.

Remarks

Compare this example: We copied the object Frame three times and named it Frame1 , Frame2 , and Frame3 . Then, we insert Frame1 into Frame2 , and Frame2 into Frame3 . When we call .Frame3.Frame2.Frame1.Origin the result will be .Frame2.Frame1 , as .Frame2.Frame1 is the object from which .Frame3.Frame2.Frame1 was derived most recently.

Type

Read-only attribute

Syntax

```simtalk
< Path >.Origin → object
```

Return Value

The return value has the data type object .

Example

current.Origin.openDialog

if local_change current.openDialog else end

SimTalk

OriginRoot [SimTalk]

See also

Show Origin [class library]

Open Origin [described]

Go to Origin [described]

<!-- image -->

on the Home Ribbon Tab

##### OriginRoot [SimTalk]

Returns the root object of the inheritance chain if the object designated by &lt;Path&gt; was inherited across several levels.

Type

Read-only attribute

Syntax

```simtalk
< Path >.OriginRoot → object
```

Return Value

The return value has the data type object .

Example

print Station2111111.OriginRoot // might return .MaterialFlow.Station2

SimTalk

Origin [SimTalk] - general description

**RootFrame [SimTalk]**

##### RootFrame [SimTalk]

Returns the root frame of the object designated by &lt;Path&gt;.

Remarks

The root frame is the Frame that is located highest up in the hierarchy of Frames . The root frame is always located in a folder.

Type

Read-only attribute

Syntax

```simtalk
< Path >.RootFrame → object
```

Return Value

The return value has the data type object .

VOID if no root frame for the object exists. This applies to all classes that are not of type Frame .

Example

```simtalk
print MyDialog.RootFrame // might
return .Models.Model
```

##### UUID [SimTalk]

Returns the unique ID of the object designated by &lt;Path&gt; which it keeps during its entire lifetime.

Type

Read-only attribute

Syntax

```simtalk
< Path >.UUID → string
```

Return Value

The return value has the data type string .

Example

```simtalk
print Station.UUID
```

// returns 3daf7c80-9411-4671-966f-f3ecd2c0f478 for example

See also

What is a Folder Model?

