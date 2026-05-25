### DismantleStation

Use the DismantleStation for removing mounting parts from a main part.

Icon

<!-- image -->

**Description**

Use the DismantleStation to model dismantle processes in your plant. To model assembly operations, use the AssemblyStation . Normally the Dismantle Table or the setting Main MU to Successor with Number determine the successor number to which the DismantleStation moves the part. If you want the Worker to carry all parts to a certain target, enter this object as the MU Target on the tab Importer &gt; Transport . In this case Plant Simulation overwrites the above settings.

To show a tooltip with information about the DismantleStation , hover with the mouse over it.

<!-- image -->

To change the length of the graphic and the anchor points of the DismantleStation , click Show

**Manipulators**

on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

Add the Object to the Simulation Model

To add the DismantleStation to your simulation model, click Manage Class Library &gt; Basic Objects &gt; MaterialFlow &gt; DismantleStation on the Home ribbon tab.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

**See also**

**See also**

#### AssemblyStation

Remove Parts with the Dismantle Station

Video on YouTube

[https://youtu.be/yEAqrVDBsns?si=rLxurb7Z5n4OVpJX&amp;t=407](https://youtu.be/yEAqrVDBsns?si=rLxurb7Z5n4OVpJX&t=407)

#### Dialog Box of the DismantleStation

Dialog Box of the DismantleStation

Double-click the icon of the DismantleStation to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

<!-- image -->

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Video on YouTube

[https://youtu.be/yEAqrVDBsns?si=8wllKfPDtLeflvPH&amp;t=466](https://youtu.be/yEAqrVDBsns?si=8wllKfPDtLeflvPH&t=466)

Tab Attributes

Tab Attributes [DismantleStation]

Set how the DismantleStation removes parts from the main part or creates new parts on the tab Attributes .

The tab Attributes provides the settings listed in the table of contents to the left.

###### Sequence [drop-down list] - DismantleStation

Select how the DismantleStation distributes the dismantled MUs to its successors.

<!-- image -->

**· MUs to all Successors :**

- Select Create MUs from the drop-down list Dismantle Mode , to make the DismantleStation create a new MU for each successor and moves that MU there.

<!-- image -->

The DismantleStation moves the main MU to the successor, whose number you typed into the text box Main MU to Successor with number .

- Select Detach MUs from the drop-down list Dismantle Mode , to make the DismantleStation move the MUs to each successor in turn, except for the successor that receives the main MU .

The DismantleStation moves the main MU to the successor, whose number you typed into the text box Main MU to Successor with Number .

If the DismantleStation has four successors for example, and if it moves the main MU on to successor number 2, it will pass the new MU on to successors number 1, 3, and 4. It moves the main MU to the successor with the number 2.

For these settings you have to fill out the Dismantle Table :

- MUs exiting independent of other MUs : The DismantleStation attempts to move the main MU , and after that each MU on to the successor you defined, as soon as possible.
- Main MU after other MUs : The DismantleStation first moves the mounting parts on to the successor, and then the main MU .

If you only want to unload those mounting parts from the main part, which you type into the Dismantle Table , select MUs exiting independent of other MUs or Main MU after other MUs and the Dismantle mode &gt; Detach MUs . Always type a valid MU class into the column MU and a positive number into the column Number .

**SimTalk**

Sequence [SimTalk] - DismantleStation See also DismantleMode [SimTalk] Dismantle Table [button] - DismantleStation DismantleTable [SimTalk] Video on YouTube https://youtu.be/yEAqrVDBsns?si=GuoEsWAOrzqYT9l1&amp;t=487

**Dismantle Table [button] - DismantleStation**

###### Dismantle Table [button] - DismantleStation

To open the Dismantle Table , click this button.

<!-- image -->

The DismantleStation opens a table with three columns.

- Type the path to the class of the MUs into the column MU , such as .MUs.Part , .MUs.Container or .MUs.Transporter . Alternatively you can leave the entry empty to designate any MU class.
- Type the number of MUs that are dismantled into the column Number . You can also type in -1 to dismantle all parts. If you do not enter a number, the DismantleStation uses the default value 1.
- Type the number of the successor into the column Successor . If you do not type in a value, the DismantleStation moves the mounting parts to the successor with the number 1 for the setting Dismantle Mode &gt; Detach MUs . For the setting Dismantle Mode &gt; Create MUs it moves the MUs to the successor to which the main MU moves.

<!-- image -->

**Note**

If you type in a MU Target , the Worker carries all MUs to this target. If you do not type in a MU Target , the Dismantle Table or the setting Main MU to Successor with Number determine it.

Depending on what you select from drop-down list Dismantle Mode : Create MUs or Detach MUs , the DismantleStation creates the corresponding MUs or searches the table for the successor to which it moves it. In the latter case the Dismantle Table may contain more information than is required for moving the MUs .

If you only want to unload those mounting parts from the main MU , which you type into the Dismantle Table , select Sequence &gt; MUs exiting independent of other MUs or Main MU after other MUs and the Dismantle Mode &gt; Detach MUs . Always type a valid MU class into the column MU and a positive number into the column Number .

<!-- image -->

To automatically move all MUs according to their MU class to a successor:

- Type in any MU class into the column MU of the Dismantle Table .
- Type in the value -1 into the column Number to designate all remaining parts of this class.
- Type in the number of the desired successor into the column Successor .
- Repeat this for additional MU classes.

To automatically move all MUs to a successor:

- Leave the column MU in the Dismantle Table empty to designate any MU class.
- Type in the value -1 into the column Number to designate all remaining parts of this class.
- Type in the number of the desired successor into the column Successor .

**SimTalk**

DismantleTable [SimTalk]

**See also**

**DismantleMode [SimTalk]**

###### Dismantle Mode [drop-down list] - DismantleStation

Select the Dismantle Mode , i.e., how the DismantleStation handles the mounting parts.

- The setting Detach MUs detaches the mounting parts from the main MU and moves them on to the successor which you typed into the Dismantle Table . If you only want to unload those mounting parts from the main MU , which type into the Dismantle Table , select Sequence &gt; MUs exiting independent of other MUs or Main MU after other MUs and the Dismantle mode &gt; Detach MUs . Always type a valid MU class into the column MU and a positive number into the column Number .
- The setting Create MUs creates mounting parts.

<!-- image -->

<!-- image -->

**SimTalk**

DismantleMode [SimTalk]

See also Dismantle Table [button] - DismantleStation DismantleTable [SimTalk] Video on YouTube https://youtu.be/yEAqrVDBsns?si=IcmgOmhAm8BektlL&amp;t=720

###### Main MU to Successor with Number [text box] - DismantleStation

Type in the number of the successor to which the DismantleStation moves the main MU .

Note

If you type in a MU Target , the Worker carries all MUs to this target.

If you do not type in a MU Target , the Dismantle Table or the setting Main MU to Successor with Number determine it.

You cannot use 0 to send the main MU on. If you do type in 0 and click Apply or OK , Plant Simulation changes 0 to the default value 1. If you assign 0 to the attribute Main MU , Plant Simulation shows an error message.

SimTalk

MainMU [SimTalk] - DismantleStation

**Exiting MU [drop-down list] - DismantleStation**

###### Exiting MU [drop-down list] - DismantleStation

Select the Exiting MU , i.e., how the DismantleStation moves the main MU or a new MU on to its successor.

<!-- image -->

- For the setting Main MU it moves the main MU on to the succeeding object.
- For the setting New MU it deletes the main MU , creates a new MU , and moves it on to the successor. The DismantleStation then shows the text box MU .

<!-- image -->

Type the path to the class of the new MU into the text box, or click the button and select the new MU in the dialog Select Object .

**SimTalk**

MainMU [SimTalk] - DismantleStation

ExitingMUMode [SimTalk]

NewMU [SimTalk] - DismantleStation Tab Times Define Times as described under the Tab Times .

Select a distribution from the drop-down list and type the values that this distribution requires into the text box. Plant Simulation shows the parameters along the upper border of the tab. You can also enter a constant time ( Const ).

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr [SimTalk] .

See also

Define Processing Times

Select the Set-Up Time

Processing Time [general description]

Set-up Time [general description]

Recovery Time [general description]

Recovery Time Starts

Cycle Time [general description]

**Tab Set-Up**

##### Tab Set-Up

Define properties for setting the object up as described under the Tab Set-Up .

##### Tab Failures

Define failures as described under the Tab Failures .

##### Tab Controls

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the respective control.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

You can create an Entrance Control , an Exit Control , a Set-up Control , and a Pull Control .

**Note**

Plant Simulation calls the Exit Control for each leaving part . When you only call the method @.move , Plant Simulation moves the part at the same successor that would receive it without Exit Control .

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

You can also select the Shift Calendar , which controls the shifts during which the object works.

See also

Entrance Control [general description]

Set-up Control

Pull Control [general description]

Shift Calendar [tab Controls]

Tab Statistics

Tab Statistics [DismantleStation]

Statistics is described under the Tab Statistics .

In addition, the DismantleStation shows the button Blocking Times .

<!-- image -->

To view Resource Statistics of Stationary Resources in the Statistics Report , select View &gt; Show Statistics Report in the dialog of the object. You can also click the right mouse button in the Frame and select Show Statistics Report or you can press F6 .

###### Tab Statistics [DismantleStation]

<!-- image -->

###### Blocking Times [table]

To open the table Blocking Times that shows the sum of the blocking times of the MUs per successor, click this button.

<!-- image -->

**SimTalk**

statBlockingTimePerSuccessor [SimTalk]

statBlockingTimeTable [SimTalk]

<!-- image -->

##### Tab Importer

Define services for processing the parts, for setting the station up for a certain type of part, and for repairing the station on the Tab Importer .

**Note**

If you want the Worker to carry all parts to a certain target, enter this object as MU target on the tab Importer &gt; Transport . In this case Plant Simulation overwrites the settings Dismantle Table or Main MU to Successor with Number to determine the successor number to which the DismantleStation moves the part.

To view Importer Statistics in the Statistics Report , click the object in the Frame , and press F6 ( Show Statistics Report ), or click Show Statistics Report on the Home ribbon tab.

You can also click the object in the Frame with the right mouse button and select Show Statistics Report on the context menu.

<!-- image -->

##### Tab Energy

Select energy settings for the object on the Tab Energy .

##### Tab Costs

Tab Costs

Select costs settings for the object on the Tab Costs .

While the AssemblyStation adds mounting parts to a main part costs accrue which result from the sum of the investment costs and the operating costs.

**Note**

The total investment costs only accrue during the Depreciation Period .

The costs are allocated to the main part as accrued costs . Costs which accrued for the mounting parts so far, are transferred to the main part.

If the AssemblyStation is empty, the costs remain with the AssemblyStation as general costs .

See also

Simulate the Accrued Costs of the Machines

CostAnalyzer &gt; How the CostAnalyzer Assigns Costs to Part Types

CostAnalyzer &gt; Costs Shown in the Costs Report

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

**Navigate Menu**

##### Navigate Menu

The commands are described under the Navigate Menu .

View Menu

##### View Menu

The View Menu provides commands to access its functions.

| Refresh [on View menu]                     | Services [on View menu]              |
|--------------------------------------------|--------------------------------------|
| Show Statistics Report [on View menu]      | Unavailable Services [on View menu]  |
| Show Attributes and Methods [on View menu] | Associated Workplaces [on View menu] |
| Contents [DismantleStation]                | Exiting MUs                          |
| Forward Blocking List                      | Associated Lockout Zones             |
| Exit Blocking List                         | Associated Shift Calendar            |
| Exporters [on View menu]                   |                                      |

###### Contents [DismantleStation]

Opens a list containing all MUs that were dismantled on the DismantleStation .

<!-- image -->

**Exiting MUs**

###### Exiting MUs

Opens a table displaying the MUs located at present on the DismantleStation , and which it deletes when it moves the main part onto the Successor contained in column 2 of the table.

<!-- image -->

**See also**

leavingMU [SimTalk]

leavingMUs [SimTalk]

NumLeavingMU [SimTalk]

##### Tools Menu

The commands are described under the Tools Menu .

**Tabs Menu**

##### Tabs Menu

Use the commands of the Tabs menu to show or hide individual tabs of the material flow objects. If you hide tabs that you do not need, Plant Simulation opens the dialog faster, and you can change to those tabs faster that you need in your daily work.

To apply the changed settings, click OK , close the dialog, and reopen it

The menu shows a check mark to the left of the displayed tabs.

The command Inherit turns inheritance of the displayed or hidden tabs in the dialog off or on.

<!-- image -->

##### Help Menu

The commands are described under the Help Menu .

**Methods of the DismantleStation**

#### \_Methods of the DismantleStation

The DismantleStation provides:

- The methods listed in the table of contents to the left.
- The Methods of the Material Flow Objects .
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

leavingMU [SimTalk]

Returns the specified MU from the table Exiting MUs of the DismantleStation designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.leavingMU(MU:integer) → object
```

Parameter

The parameter MU of data type integer designates the MU .

Return Value

The return value has the data type object .

Example

```simtalk
for var i := 1 to MyDismantleStation.NumLeavingMU
	print MyDismantleStation.leavingMU(i)
next
```

SimTalk

leavingMUs [SimTalk]

See also

Exiting MUs

##### leavingMUs [SimTalk]

leavingMUs [SimTalk]

Returns the contents of the table of the Exiting MUs of the DismantleStation designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.leavingMUs([MUsTable:table]) → any
```

Parameter

The optional parameter MUsTable of data type table designates the name of the table.

Return Value

The return value has the data type any .

Is an array containing the MUs that wanted to leave the DismantleStation if you do not specify the optional parameter.

Example

MyDismantleStation.leavingMUs(myEvalTable) MyDismantleStation.leavingMUs

SimTalk

leavingMU [SimTalk]

See also

Exiting MUs statBlockingTimePerSuccessor [SimTalk]

Returns the blocking time in relation to the specified successor from the table Blocking Times of the DismantleStation designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.statBlockingTimePerSuccessor(Successor:integer) → time
```

Parameter

The parameter Successor of data type integer designates the successor.

Return Value

The return value has the data type time .

Example

```simtalk
for var i := 1 to MyDismantleStation.NumSucc
	print MyDismantleStation.statBlockingTimePerSuccessor(i)
next
```

See also

Tab Statistics [DismantleStation]

statBlockingTimeTable [SimTalk]

statBlockingTimeTable [SimTalk]

Returns the contents of the table Blocking Times of the DismantleStation designated by &lt;Path&gt; and writes it into the table.

Type

Method

Syntax

```simtalk
< Path >.statBlockingTimeTable(BlockingTimes:table) → boolean
```

Parameter

The parameter BlockingTimes of data type table designates the name of the table.

Return Value

The return value has the data type boolean .

Example

```simtalk
var myBlockingTimesTable: table
MyDismantleStation.statBlockingTimeTable(myBlockingTimesTable)
```

See also

Tab Statistics [DismantleStation]

#### Read-Only Attributes of the DismantleStation

Read-Only Attributes of the DismantleStation

The DismantleStation provides:

- The read-only attributes listed in the table of contents to the left.
- The \_Read-Only Attributes of All Objects .
- The Read-Only Attributes of the Material Flow Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print DismantleStation.NumLeavingMU

##### NumLeavingMU [SimTalk]

NumLeavingMU [SimTalk]

Returns the number of MUs contained in the table Exiting MUs of the DismantleStation designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

```simtalk
< Path >.NumLeavingMU → integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
for var i := 1 to MyDismantleStation.NumLeavingMU
	print MyDismantleStation.leavingMU(i)
next
```

See also

Exiting MUs

##### StatAverageDwellTime [SimTalk] - DismantleStation

Returns the average time which the main parts stayed on the DismantleStation designated by &lt;Path&gt;.

Remarks

Plant Simulation only counts times during which the DismantleStation was not paused and not unplanned.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatAverageDwellTime → time

Return Value

The return value has the data type time .

Example

print MyDismantleStation.StatAverageDwellTime

See also

Tab Statistics [DismantleStation]

#### Attributes of the DismantleStation

\_Attributes of the DismantleStation

The DismantleStation provides:

- The attributes listed in the table of contents to the left.
- The Attributes of All Objects .
- The Attributes of the Material Flow Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyDismantleStation.NewMU := ".MUs.basicMU"
print MyDismantleStation.Pause
posit := MyStation.Cont.XPos
```

##### DismantleMode [SimTalk]

Sets how the DismantleStation designated by &lt;Path&gt; handles the MUs .

Remarks

The Dismantle Mode provides these settings:

- The setting Detach MUs detaches the mounting parts from the main MU and moves them on to the successor which you typed into the Dismantle Table .

If you only want to unload those mounting parts from the main part which you type into the Dismantle Table , select Sequence &gt; MUs exiting independent of other MUs or Main MU after other MUs and the Dismantle mode &gt; Detach MUs . Always enter a valid MU class into the column MU and a positive number into the column Number .

<!-- image -->

- The setting Create MUs creates mounting parts.

Type

Read-only attribute

**DismantleMode [SimTalk]**

**Syntax**

&lt; Path &gt;.DismantleMode:string

Assignment Value

You can assign a value of data type string .

Specify "Create MUs" to create MUs .

Specify "Detach MUs" to detach them from the main MU .

Example

```simtalk
MyDismantleStation.DismantleMode := "Detach MUs"
```

See also

Dismantle Table [button] - DismantleStation

Sequence [drop-down list] - DismantleStation

Dismantle Mode [drop-down list] - DismantleStation

##### DismantleTable [SimTalk]

Sets the name of the Dismantle Table of the DismantleStation designated by &lt;Path&gt;.

**Remarks**

The Dismantle Table contains the names of the MUs , which leave the DismantleStation and its successors.

- Enter the path to the class of the MUs into the column MU , such as .MUs.Part , .MUs.Container or .MUs.Transporter . Alternatively you can leave the entry empty to designate any MU class.
- Enter the number of MUs that are dismantled into the column Number . If you do not enter a number, the DismantleStation uses the default value 1.
- Enter the number of the successor into the column Successor . If you do not enter a value, the DismantleStation moves the mounting parts to the successor with the number 1 for the setting Dismantle mode &gt; Detach MUs .

For the setting Dismantle Mode &gt; Create MUs it moves the MUs to the successor to which the main MU moves.

<!-- image -->

**Note**

If you enter a MU Target the Worker carries all parts to this target.

If you do not enter a MU Target , the Dismantle Table or the setting Main MU to successor with number determine it.

Depending on what you select from the drop-down list Dismantle Table : Create MUs or Detach MUs , the DismantleStation creates the corresponding MUs or searches the table for the successor to which it moves it. In the latter case the Dismantle Table may contain more information than is required for moving the MUs .

If you only want to unload those mounting parts from the main part which you type into the Dismantle Table , select Sequence &gt; MUs exiting independent of other MUs or Main MU after other MUs and the Dismantle mode &gt; Detach MUs . Always enter a valid MU class into the column MU and a positive number into the column Number .

<!-- image -->

To automatically move all parts according to their MU class to a successor:

- Type in any MU class into the column MU of the Dismantle Table .
- Type in the value -1 into the column Number to designate all remaining parts of this class.
- Type in the number of the desired successor into the column Successor .
- Repeat this for additional MU classes.

To automatically move all parts to a successor:

- Leave the column MU in the Dismantle Table empty to designate any MU class.
- Type in the value -1 into the column Number to designate all remaining parts of this class.
- Type in the number of the desired successor into the column Successor .

**Note**

If the dismantle table is inherited, inheritance is not automatically deactivated when you write to cells of the dismantle table. For this reason you will change the inherited table during an assignment. To deactivate inheritance, assign the dismantle table to itself.

```simtalk
DismantleStation.DismantleTable := DismantleStation.DismantleTable //  deactivates inheritance
```

Type

Read-only attribute

Syntax

```simtalk
< Path >.DismantleTable:table
```

Assignment Value

You can assign a value of data type table .

Examples

```simtalk
var DismList:table[object,integer,integer]
DismList.create
DismList.writeRow(1,1, .MUs.MyPart,1,1)
DismList.writeRow(1,2, .MUs.MyPart,2,1)
MyDismantleStation.DismantleTable := DismList
// You can use the following example in an entrance control // where 'EntranceCtrlBeforeActions' is set to true.
?.DismantleList := ?.DismantleList // Deactivates inheritance. // (For performance reasons, we recommend to do this in the dialog of the object.)
?.DismantleList[2, 1] := @.AmountOfParts
```

SimTalk

**DismantleMode [SimTalk]**

See also

Dismantle Mode [drop-down list] - DismantleStation

Dismantle Table [button] - DismantleStation

**Sequence [SimTalk] - DismantleStation MU Target**

Main MU to Successor with Number [text box] - DismantleStation

##### ExitingMUMode [SimTalk]

Sets if the main MU exits the DismantleStation designated by &lt;Path&gt; or if a new MU will be created which then exits the object.

Type

Read-only attribute

Syntax

&lt; Path &gt;.ExitingMUMode:string

Assignment Value

You can assign a value of data type string .

You can specify "Main MU" or "New MU" .

Example

MyDismantleStation.ExitingMUMode := "New MU"

See also

Exiting MU [drop-down list] - DismantleStation MainMU [SimTalk] - DismantleStation Sets the number of the successor to which the DismantleStation designated by &lt;Path&gt; moves the main MU .

Remarks

**Note**

If you enter a Worker carries all parts to this target. If you do not enter a MU Target , the Dismantle Table or the setting Main MU to successor with number determine it.

Type

Attribute

Syntax

```simtalk
< Path >.MainMU:integer
```

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MyDismantleStation.MainMU := 2
```

See also

Main MU to Successor with Number [text box] - DismantleStation

MU Target

Dismantle Table [button] - DismantleStation

##### NewMU [SimTalk] - DismantleStation

Sets the path of the MU , which the DismantleStation designated by &lt;Path&gt; creates.

Remarks

NewMU applies when the DismantleStation designated by &lt;Path&gt; deletes the main MU and creates a new MU instead.

Type

Attribute

Syntax

&lt; Path &gt;.NewMU:path

Assignment Value

You can assign a path .

Example

MyDismantleStation.NewMU := .MUs.basicMU

See also

Exiting MU [drop-down list] - DismantleStation

##### Sequence [SimTalk] - DismantleStation

Sets how the DismantleStation designated by &lt;Path&gt; distributes the MUs to the successors to which it is connected.

Remarks

You can specify:

- "MUs to all successors" :

If you select Create MUs from the drop-down list Dismantle Mode , the DismantleStation creates a new part for each successor and moves that part there.

The DismantleStation moves the main MU to the successor, whose number you entered into the text box Main MU to Successor with Number .

If you select Detach MUs from the drop-down list Dismantle Mode , the DismantleStation moves the MUs to each successor in turn, except for the successor that receives the main MU .

The DismantleStation moves the main MU to the successor, whose number you entered into the text box Main MU to Successor with Number .

If the DismantleStation has four successors for example, and if moves the main MU on to successor number 2, it will pass the new MU on to successors number 1, 3, and 4. It moves the Main MU to the successor with the number 2.

**For these settings you have to fill out the Dismantle Table :**

- "MUs exiting independent of other MUs" : Here the DismantleStation attempts to move the main MU and after that each MU on to the successor

you defined, as soon as possible.

- "Main MU after other MUs" :

Here the DismantleStation first moves the mounting parts on to the successor, and then the main MU .

If you only want to unload those mounting parts from the main part which you type into the Dismantle Table , select MUs exiting independent of other MUs or Main MU after other MUs and the Dismantle mode &gt; Detach MUs . Always enter a valid MU class into the column MU and a positive number into the column Number .

Type

Attribute

Syntax

&lt; Path &gt;.Sequence:string

**Assignment Value**

You can assign a value of data type string .

You can specify "MUs to all successors" , "MUs exiting independent of other MUs" , or "Main MU after other MUs" .

**Example**

MyDismantleStation.Sequence := "Main MU after other MUs"

See also

Sequence [drop-down list] - DismantleStation

DismantleMode [SimTalk]

DismantleTable [SimTalk]

**PickAndPlace Robot**

