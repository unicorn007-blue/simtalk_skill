### AssemblyStation

Use the AssemblyStation for adding mounting parts to a main part, for example doors to a car body.

Icon

<!-- image -->

Description

The AssemblyStation moves the mounting parts either to the main MU -according to the value you enter into the Assembly Table -or it deletes them. Mounting parts might also be called assembly parts, add-on parts, attachment part, attached part, etc.

Use the AssemblyStation to model assembly processes. If the assembly process requires services, you can assign the order in which the AssemblyStation requests mounting parts and services. To dismantle parts from the main part, you can use the DismantleStation .

If the AssemblyStation uses an Assembly Table and you specify an Assembly Time and a Sequence Number for each mounting part, the AssemblyStation assembles the mounting parts sequentially. The assembly of each individual mounting part consumes the specified Assembly Time . After all mounting parts are assembled, the Processing Time of the AssemblyStation passes and the main part then leaves the station.

In sequential assembly mode , the AssemblyStation starts assembling the mounting parts with the lowest Sequence Number , then continues with the next higher Sequence Number , and so on. Only the mounting parts that are needed in the current assembly sequence can enter the AssemblyStation . Within a sequence, the mounting parts are assembled in the order in which they entered the AssemblyStation .

**Note**

You cannot move a part via information flow, i.e., by using methods, to the AssemblyStation !

To show a tooltip with information about the AssemblyStation , hover with the mouse over it.

<!-- image -->

<!-- image -->

To change the length of the graphic and the anchor points of the AssemblyStation , click Show Manipulators on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the AssemblyStation to your simulation model, click Manage Class Library &gt; Basic Objects &gt; MaterialFlow &gt; AssemblyStation on the Home ribbon tab.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

See also

Assemble Parts with the AssemblyStation

Assembly Table

Video on YouTube

[https://youtu.be/yEAqrVDBsns?si=KNH0FYXO9k1MRa3W](https://youtu.be/yEAqrVDBsns?si=KNH0FYXO9k1MRa3W)

#### Dialog Box of the AssemblyStation

Dialog Box of the AssemblyStation

Double-click the icon of the AssemblyStation to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Video on YouTube

[https://youtu.be/yEAqrVDBsns?si=TlDLGk6Kj7RtNfar&amp;t=210](https://youtu.be/yEAqrVDBsns?si=TlDLGk6Kj7RtNfar&t=210)

Tab Attributes

Tab Attributes

Define how the AssemblyStation attaches mounting parts to the main part on the tab Attributes .

The tab Attributes provides the settings listed in the table of contents to the left.

###### Assembly Table

Select if the AssemblyStation uses an Assembly Table and if so which kind.

**Note**

You cannot change the Assembly Table if the Main MU is already located on the AssemblyStation . To change the Assembly Table in the Entrance Control of the Station , select the check box Before Actions of the Entrance Control .

Then click Open and type the required information into the assembly table.

- None : The AssemblyStation does not use an Assembly Table . Instead, it expects a part from each of its predecessors.
- Predecessors
- Type the number of the Predecessor , which moves the part, into column 1 of the table and the Amount into column 2 of the Assembly Table . To use the default value 1, do not type in an Amount .
- To make the AssemblyStation accept parts from this predecessor until the capacity of the main MU is reached, type in -1 as the Amount . To use parts of the main part number as mounting parts, add the number of the main MU to the Assembly Table .
- Type the time, in seconds, that each individual part consumes when it's assembled into the column Assembly Time and the number of the sequence in which the part is assembled into the column Sequence Number . The Assembly Time must be a positive number or 0. If you do not specify a time, the default Assembly Time is 0.
- The Sequence Number must be a positive integer number. The default Sequence Number is 1. To assemble the parts non-sequentially, leave the columns Assembly Time and Sequence Number empty.
- MU Types

<!-- image -->

<!-- image -->

- Type the MU Name of the part , such as Part , Container , Transporter , Shaft , etc., into column 1 and the Amount into column 2 of the Assembly Table .

Type the name of the part into the column MU Name , not its path, for example MyMountingPart and not *.UserObjects.MyMountingPart .

- To use the default value 1, do not type in an Amount . To make the AssemblyStation accept parts with this MU Name until the capacity of the main MU is reached, type in -1 as the Amount .
- Type the time, in seconds, that each individual part consumes when it's assembled into the column Assembly Time and the number of the sequence in which the part is assembled into the column Sequence Number . The Assembly Time must be a positive number or 0. If you do not specify a time, the default Assembly Time is 0.

The Sequence Number must be a positive integer number. The default Sequence Number is 1.

To assemble the parts non-sequentially, leave the columns Assembly Time and Sequence Number empty.

**· Depends on Main MU**

<!-- image -->

- Type in the Main MU Name of the main MU , such as Part , Container , Transporter , Shaft , etc.

Type in an asterisk * to handle all main parts which you did not explicitly enter with names of their own into the assembly table . Type in the MU Name and the Amount of the parts.

- To use the default value 1 , do not type in an Amount .

To make the AssemblyStation accept parts with this MU Name until the capacity of the main MU is reached, type in -1 as the Amount .

- Type the time, in seconds, that each individual part consumes when it's assembled into the column Assembly Time and the number of the sequence in which the part is assembled into the column

Sequence Number . The Assembly Time must be a positive number or 0. If you do not specify a time, the default Assembly Time is 0.

The Sequence Number must be a positive integer number. The default Sequence Number is 1.

To assemble the parts non-sequentially, leave the columns Assembly Time and Sequence Number empty.

**Note**

For the settings MU Types and Depends on Main MU this applies:

If the AssemblyStation has objects of type Store as predecessors, it requests the required mounting parts from the Store . If the required parts are not available in the Store at the moment, the Store records the request and delivers the parts to the AssemblyStation once they are available again.

The parts can also be carried from the Store to the AssemblyStation by a Worker . The Store can only provide mounting parts, but no main parts, and it has to be connected with a Connector , even if the Worker carries the part away.

- Fill up Main MU : The AssemblyStation does not use an Assembly Table . Instead, it accepts parts from any of its predecessors until the capacity of the main MU is reached.

<!-- image -->

SimTalk

AssemblyTable [SimTalk]

AssemblyTableMode [SimTalk]

See also

Assemble Parts Sequentially

Assemble Parts Sequentially with the Worker

Always Fill-up the Main MU with Parts

Change the Assembly Table in the Entrance Control

Video on YouTube

[https://youtu.be/yEAqrVDBsns?si=wK5KXXDJ-SG4BAXu&amp;t=275](https://youtu.be/yEAqrVDBsns?si=wK5KXXDJ-SG4BAXu&t=275)

###### Workers Sequentially Deliver MUs to Assemble

To make the Worker deliver the required mounting parts , which the AssemblyStation requested, sequentially one after the other to the AssemblyStation , select this check box.

<!-- image -->

Workers Sequentially Deliver MUs to Assemble prevents that several Workers walk to the AssemblyStation and cannot deliver and deposit the parts because the AssemblyStation cannot accept them. To accomplish this Plant Simulation reserves a processing place for the mounting part on the AssemblyStation .

**Note**

If you select Workers Sequentially Deliver MUs to Assemble , the attribute ReservedFor returns the part for which the place is currently reserved.

If you clear the check box, ReservedFor returns an array of parts for which places are reserved.

To make a single Worker deliver as many mounting parts as he can carry to the AssemblyStation , clear the check box.

To make several Workers deliver the mounting parts to the AssemblyStation in parallel at the same time, clear the check box.

SimTalk

SequentialDelivery [SimTalk]

ReservedFor [SimTalk]

See also

Set How Workers Deliver Mounting Parts

###### Main MU from Predecessor

Type in the number of the Predecessor object which moves the main MU to the AssemblyStation .

<!-- image -->

Type in 0 to make a Worker deliver the main part via a connected Workplace . This only applies to the settings Assembly Table &gt; MU Types and Depends on Main MU . It does not apply to the settings Assembly Table &gt; None/Predecessors .

The predecessor is the object that is connected to the selected object with a Connector and that precedes it in the sequence of stations in the simulation model.

As the AssemblyStation is connected to at least two stations, the order in which you connect it with the predecessors is important. If the assembly process does not work as expected, check the numbering of

the predecessors by activating More View Options &gt; Show Predecessors on the View ribbon tab of the Frame in a 2D model.

<!-- image -->

3D shows the predecessors and the successors of an object in a Tooltip when you drag the mouse over the respective Connector .

**SimTalk**

MainMU [SimTalk] - AssemblyStation

Video on YouTube

[https://youtu.be/yEAqrVDBsns?si=TlDLGk6Kj7RtNfar&amp;t=210](https://youtu.be/yEAqrVDBsns?si=TlDLGk6Kj7RtNfar&t=210)

<!-- image -->

###### Assembly Mode [drop-down list]

Select the Assembly Mode , i.e., how the AssemblyStation handles MUs :

<!-- image -->

- Attach MUs : The AssemblyStation attaches the mounting part to the main MU .
- Delete MUs : The AssemblyStation deletes the mounting part after the assembly operation is finished.

**SimTalk**

**AssemblyMode [SimTalk]**

Video on YouTube

[https://youtu.be/yEAqrVDBsns?si=dQRy7eHXMmdWpUMh&amp;t=236](https://youtu.be/yEAqrVDBsns?si=dQRy7eHXMmdWpUMh&t=236)

Exiting MU [drop-down list] - AssemblyStation

Select how the AssemblyStation handles the Exiting MU , i.e., the MU , which is leaving the station.

- Main MU : The AssemblyStation moves the main MU to the succeeding object.
- New MU : The AssemblyStation moves the assembled/new MU to the succeeding object.

<!-- image -->

<!-- image -->

If you select New MU , the AssemblyStation shows the button and the text box MU . Click this to open the dialog Select Object and select the new MU in the dialog.

**SimTalk**

**ExitingMU [SimTalk]**

NewMU [SimTalk] - AssemblyStation

Videos

[https://youtu.be/yEAqrVDBsns?si=0YHAzasIExF-qyEU&amp;t=246](https://youtu.be/yEAqrVDBsns?si=0YHAzasIExF-qyEU&t=246)

[https://youtu.be/yEAqrVDBsns?si=XKslSQHqWrqklVsf&amp;t=596](https://youtu.be/yEAqrVDBsns?si=XKslSQHqWrqklVsf&t=596)

###### Sequence [drop-down list] - AssemblyStation

Select the Sequence in which the AssemblyStation requests parts and/or services from the drop-down list.

<!-- image -->

- MUs then services : The AssemblyStation requests the MUs before it requests the required services.
- Select this, if the services are not required until all mounting parts are available. The services are

requested, when all mounting parts have been moved to the AssemblyStation or have been deleted, compare Assembly Mode . When all mounting parts are available, set-up and processing operations can start, when the AssemblyStation has received the associated services.

- Services then MUs : The AssemblyStation requests the services before it requests the required MUs .

Select this, if the services are already required for providing the mounting parts. The services are requested before the main part arrives, when the main part is ready to exit the preceding station. When the mounting parts arrive at the AssemblyStation , the Exporters are already located at the AssemblyStation . Set-up and processing procedures only start, when all mounting parts are available.

The mounting parts are moved to the main part or are deleted before the processing time starts, compare Assembly Mode .

If the services are not available for the AssemblyStation , the mounting parts will not be moved to the main part or will not be deleted. The AssemblyStation then records a special Blocking Time .

- MUs and Services : The AssemblyStation requests the MUs and the services at the same time.

Select this, if the services are already required for providing the mounting parts, but not for the assembly proper.

For the setting Services then MUs the services are requested before the main part arrives. When the AssemblyStation can receive the services immediately, it behaves identically for the settings Services then MUs and MUs and Services .

If the AssemblyStation cannot receive the services, the mounting parts will be moved to the main part anyway and will then be deleted.

<!-- image -->

**Video on YouTube**

[https://youtu.be/yEAqrVDBsns?si=sAD9JYQJJzex0Hfw&amp;t=267](https://youtu.be/yEAqrVDBsns?si=sAD9JYQJJzex0Hfw&t=267)

Tab Times

Define Times as described under the Tab Times .

Select a distribution from the drop-down list and type the values that this distribution requires into the text box. Plant Simulation shows the parameters along the upper border of the tab. You can also select a constant time ( Const ).

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr .

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

You can create an Entrance Control , an Exit Control , and a Set-up Control .

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

In addition, you can select the Shift Calendar .

See also

Entrance Control [general description]

Exit Control [general description]

Set-up Control

##### Tab Exit

##### Tab Exit

Select to which of its successors the object moves the MU on the Tab Exit .

See also

Blocking [exit strategy]

Strategy [material flow objects]

Tab Statistics

Tab Statistics [AssemblyStation]

Statistics is described under the Tab Statistics . In addition, the AssemblyStation collects these statistical values:

| Item English       | Description                                                                                                                                            | Read-only attribute                                | Item German           |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------|-----------------------|
| Waiting Parts      | Shows the portion of the statistics collection period during which the AssemblyStation was Waiting [state, material flow objects] for mounting parts . | StatWaitingPartsPor tion [SimTalk]                 | Warten auf Teile      |
| Waiting Resource s | Shows the portion of the statistics collection period during which the AssemblyStation was waiting for Exporters and/or mounting parts .               | StatWaitingResPorti on [SimTalk] - AssemblyStation | Warten auf Ressourcen |

To open the table Waiting Times , which shows the sum of the waiting times for mounting parts for each predecessor, click the button.

<!-- image -->

To view Waiting Times for Parts in the Statistics Report , select View &gt; Show Statistics Report in the dialog of the object. You can also click the right mouse button in the Frame and select Show Statistics Report or you can press F6 .

<!-- image -->

**See also**

| Resource Statistics [check box]   | StatWaitingResPortion [SimTalk] - AssemblyStation   |
|-----------------------------------|-----------------------------------------------------|
| Resource Type                     | StatWaitingResCount [SimTalk] - AssemblyStation     |
| StatWaitingPartsPortion [SimTalk] | StatWaitingResDelta [SimTalk] - AssemblyStation     |
| StatWaitingPartsCount [SimTalk]   | StatWaitingResMu [SimTalk] - AssemblyStation        |
| StatWaitingPartsDelta [SimTalk]   | StatWaitingResTime [SimTalk] - AssemblyStation      |
| StatWaitingPartsMu [SimTalk]      | statWaitingTimePerPredecessor [SimTalk]             |
| StatWaitingPartsTime [SimTalk]    | statWaitingTimeTable [SimTalk]                      |

**Waiting Times**

###### Waiting Times

To open the Waiting Times table, which shows the sum of the waiting times for mounting parts for each predecessor, click this button.

**Note**

Plant Simulation only shows Waiting Times for mounting parts. The Waiting Time for the main part always is 0.

**Note**

Plant Simulation only shows Waiting Times if you selected None or Predecessors as the Assembly Table .

For the settings MU Types and Depends on Main MU the button Waiting Times is unavailable as the AssemblyStation does not collect waiting times for them.

**Note**

In our example below the main part arrives along the connector from the SourceMainParts . As only waiting times for mounting parts are shown, the first row shows 0.

**SimTalk**

statWaitingTimeTable [SimTalk]

<!-- image -->

##### Tab Importer

On the Tab Importer you can define services for processing the parts, for setting the station up for a certain type of part, and for repairing the station.

To view Importer Statistics in the Statistics Report , click the object in the Frame , and press F6 ( Show Statistics Report ), or click Show Statistics Report on the Home ribbon tab.

You can also click the object in the Frame with the right mouse button and select Show Statistics Report on the context menu.

To view Importer Statistics in the Statistics Report , do one of the following:

- Select View &gt; Show Statistics Report in the dialog of the object.
- Click the object with the right mouse button in the Frame and select Show Statistics Report or press F6 .
- Click Show Statistics Report on the Home ribbon tab.

<!-- image -->

See also

Processing Importer

Set-up Importer

Failure Importer

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

View Menu

The commands are described under the View Menu .

It also provides the menu command MUs To Be Deleted .

SimTalk

updateDialog [SimTalk]

###### MUs To Be Deleted

Opens a list with the MUs currently located on the AssemblyStation that it deletes when the main part exits.

<!-- image -->

**SimTalk**

muToBeDeleted [SimTalk]

musToBeDeleted [SimTalk]

NumMUsToBeDeleted [SimTalk]

**Tools Menu**

##### Tools Menu

The commands are described under the Tools Menu .

##### Tabs Menu

Use the commands of the Tabs menu to show or hide individual tabs of the material flow objects. If you hide tabs that you do not need, Plant Simulation opens the dialog faster, and you can change to those tabs faster that you need in your daily work.

To apply the changed settings, click OK , close the dialog, and reopen it

The menu shows a check mark to the left of the displayed tabs.

The command Inherit turns inheritance of the displayed or hidden tabs in the dialog off or on.

<!-- image -->

**Help Menu**

##### Help Menu

The Help Menu provides these menu commands:

**Contents**

Help on Object

**Methods of the AssemblyStation**

#### \_Methods of the AssemblyStation

The AssemblyStation provides:

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

##### musToBeDeleted [SimTalk]

musToBeDeleted [SimTalk]

Returns the contents of the table MUs to Be Deleted of the AssemblyStation designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.musToBeDeleted([Table:table]) → any
```

Parameter

The optional parameter Table of data type table designates the name of the table.

Return Value

The return value has the data type any .

If you specify the optional parameter, the return value has the data type boolean .

Do not specify the optional parameter to return an array containing the MUs that are to be deleted.

Example

MyAssembly.musToBeDeleted MyAssembly.musToBeDeleted(myEvalTable)

SimTalk

muToBeDeleted [SimTalk]

NumMUsToBeDeleted [SimTalk]

See also

MUs To Be Deleted muToBeDeleted [SimTalk]

Returns the specified MU from the table MUs to Be Deleted of the AssemblyStation designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.muToBeDeleted(NumberOfTheMU:integer) → object
```

Parameter

The parameter NumberOfTheMU of data type integer designates the number of the MU in the table.

Return Value

The return value has the data type object .

Example

```simtalk
for var i := 1 to MyAssembly.NumMUsToBeDeleted
	print MyAssembly.muToBeDeleted(i)
next
```

SimTalk

musToBeDeleted [SimTalk]

NumMUsToBeDeleted [SimTalk]

See also

MUs To Be Deleted statWaitingTimePerPredecessor [SimTalk]

Returns the summed-up waiting times for the mounting parts of the designated predecessor of the AssemblyStation designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.statWaitingTimePerPredecessor(Predecessor:integer) → time
```

Parameter

The parameter Predecessor of data type integer designates the number of the predecessor.

**Note**

The return value for the predecessor number, along which the main part arrives at the AssemblyStation , always is 0.

Return Value

The return value has the data type time .

Example

```simtalk
var i : integer
for var i := 1 to MyAssembly.NumPred
	print MyAssembly.statWaitingTimePerPredecessor(i)
next
```

See also

Waiting [state, material flow objects]

Tab Statistics [AssemblyStation] &gt; Waiting Times

##### statWaitingTimeTable [SimTalk]

Returns the table that contains the summed-up waiting times for the mounting parts of all predecessors of the AssemblyStation designated by &lt;Path&gt;.

**Remarks**

**Note**

Plant Simulation only shows Waiting Times for mounting parts. The Waiting Time for the main part always is 0.

**Note**

Plant Simulation only shows Waiting Times when you selected None or Predecessors as the Assembly Table .

**Note**

In our example below the main part arrives along the connector from the SourceMainParts . As only waiting times for mounting parts are shown, the first row shows 0.

<!-- image -->

Type

Method

Syntax

```simtalk
< Path >.statWaitingTimeTable(WaitingTimes:table) → boolean
```

Parameter

The parameter WaitingTimes of data type table designates the name of the table.

Return Value

The return value has the data type boolean .

false for the settings MU Types and Depends on Main MU .

Examples

```simtalk
var myWaitingTimesTable: table
MyAssembly.statWaitingTimeTable(myWaitingTimesTable)
print MyAssembly.statWaitingTimeTable(myWaitingTimesTable)
```

See also

Waiting [state, material flow objects]

Tab Statistics [AssemblyStation] &gt; Waiting Times

#### Read-Only Attributes of the AssemblyStation

\_Read-Only Attributes of the AssemblyStation

The AssemblyStation provides:

- The read-only attributes listed in the table of contents to the left.
- The \_Read-Only Attributes of All Objects .
- The Read-Only Attributes of the Material Flow Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print AssemblyStation.StatWaitingPartsCount NumMUsToBeDeleted [SimTalk]

Returns the number of MUs from the table MUs To Be Deleted of the AssemblyStation designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

```simtalk
< Path >.NumMUsToBeDeleted → integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
for var i := 1 to MyAssembly.NumMUsToBeDeleted
	print MyAssembly.MUToBeDeleted(i)
next
```

SimTalk

muToBeDeleted [SimTalk]

musToBeDeleted [SimTalk]

See also

MUs To Be Deleted

##### StatWaitingPartsCount [SimTalk]

Returns how often the AssemblyStation designated by &lt;Path&gt; was waiting for mounting parts .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatWaitingPartsCount → integer

Return Value

The return value has the data type integer .

Example

print MyAssembly.StatWaitingPartsCount

See also

Waiting [state, material flow objects]

Statistics report , Waiting Times for Parts StatWaitingPartsDelta [SimTalk]

Returns the deviation from the mean value of the time spans during which the AssemblyStation designated by &lt;Path&gt; was waiting for MUs .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatWaitingPartsDelta → real

Return Value

The return value has the data type real .

Example

print MyAssembly.StatWaitingPartsDelta

See also

Waiting [state, material flow objects]

Statistics report , Waiting Times for Parts StatWaitingPartsMu [SimTalk]

Returns the mean duration of the time spans during which the AssemblyStation designated by &lt;Path&gt; was waiting for MUs .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatWaitingPartsMu → real

Return Value

The return value has the data type real .

Example

print MyAssembly.StatWaitingPartsMu

See also

Waiting [state, material flow objects]

Statistics report , Waiting Times for Parts StatWaitingPartsPortion [SimTalk]

Returns the portion of the statistics collection period during which the AssemblyStation designated by &lt;Path&gt; was waiting for mounting parts .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatWaitingPartsPortion → real

Return Value

The return value has the data type real .

Example

print MyAssembly.StatWaitingPartsPortion

See also

Waiting [state, material flow objects]

Tab Statistics [AssemblyStation]

Statistics report , Waiting Times for Parts

##### StatWaitingPartsTime [SimTalk]

Returns the entire time during which the AssemblyStation designated by &lt;Path&gt; was waiting for MUs .

Type

Read-only attribute

Syntax

< Path >.StatWaitingPartsTime → time

Return Value

The return value has the data type time .

Example

print MyAssembly.StatWaitingPartsTime

See also

Waiting [state, material flow objects]

Statistics report , Waiting Times for Parts StatWaitingResCount [SimTalk] - AssemblyStation Returns how often the AssemblyStation designated by &lt;Path&gt; was waiting for mounting parts and/or for processing-Exporters/processing-services .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatWaitingResCount → integer

Return Value

The return value has the data type integer .

Example

print MyAssembly.StatWaitingResCount

See also

Waiting [state, material flow objects]

Statistics report , Waiting Times for Services and Parts

##### StatWaitingResDelta [SimTalk] - AssemblyStation

Returns the standard deviation of the times during the AssemblyStation designated by &lt;Path&gt; was waiting for mounting parts and/or for processing-Exporters/processing-services .

Syntax

&lt; Path &gt;.StatWaitingResDelta → real

Return Value

The return value has the data type real .

Example

print MyAssembly.StatWaitingResDelta

See also

Waiting [state, material flow objects]

Statistics report , Waiting Times for Services and Parts StatWaitingResMu [SimTalk] - AssemblyStation Returns the average duration of a period of time during which the AssemblyStation designated by &lt;Path&gt; was waiting for mounting parts and/or for processing-Exporters/processing-services .

Type

Read-only attribute

Syntax

```simtalk
< Path >.StatWaitingResMu → real
```

Return Value

The return value has the data type real .

Example

print MyAssembly.StatWaitingResMu

See also

Waiting [state, material flow objects]

Statistics report , Waiting Times for Services and Parts

##### StatWaitingResPortion [SimTalk] - AssemblyStation

Returns the ratio of the time during which the AssemblyStation designated by &lt;Path&gt; was waiting for mounting parts and/or for processing-Exporters/processing-services to the statistics collection period.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatWaitingResPortion → real

Return Value

The return value has the data type real .

Example

print MyAssembly.StatWaitingResPortion

See also

Waiting [state, material flow objects]

Tab Statistics [AssemblyStation]

Statistics report , Importers Waiting for Services and Parts

Statistics report , Waiting Times for Services and Parts

##### StatWaitingResTime [SimTalk] - AssemblyStation

Returns the entire time during which the AssemblyStation designated by &lt;Path&gt; was waiting for mounting parts and/or for processing-Exporters/processing-services .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatWaitingResTime → time

Return Value

The return value has the data type time .

Example

print MyAssembly.StatWaitingResTime

See also

Waiting [state, material flow objects]

Statistics report , Waiting Times for Services and Parts

##### Attributes of the AssemblyStation

\_Attributes of the AssemblyStation

The AssemblyStation provides:

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
MyAssembly.AssemblyMode := "attach MUs"
print MyAssembly.Pause
posit := MyStation.Cont.XPos
```

**AssemblyMode [SimTalk]**

##### AssemblyMode [SimTalk]

Sets how the AssemblyStation designated by &lt;Path&gt; moves the MUs on.

Type

Attribute

Syntax

&lt; Path &gt;.AssemblyMode:string

Assignment Value

You can assign a value of data type string .

Specify "Attach MUs" to move the MUs to the main part.

Specify "Delete MUs" to delete the MUs .

Example

MyAssembly.AssemblyMode := "Attach MUs"

See also

Assembly Mode [drop-down list]

##### AssemblyTable [SimTalk]

Sets the table containing the mounting parts of the AssemblyStation designated by &lt;Path&gt;.

Remarks

Depending on the setting you selected under Assembly Table (or AssemblyTableMode ) you specify:

- None : The AssemblyStation does not use an Assembly Table . Instead, it expects a part from each of its predecessors.

**· Predecessors**

- Type the number of the Predecessor , which moves the part, into column 1 of the table and the Amount into column 2 of the Assembly Table . To use the default value 1, do not specify an Amount .
- To make the AssemblyStation accept parts from this predecessor until the capacity of the main MU is reached, speciify -1 as the Amount . To use parts of the main part number as mounting parts, add the number of the main MU to the Assembly Table .
- Specify the time, in seconds, that each individual part consumes when it's assembled into the column Assembly Time and the number of the sequence in which the part is assembled into the column Sequence Number . The Assembly Time must be a positive number or 0. If you do not specify a time, the default Assembly Time is 0.
- The Sequence Number must be a positive integer number. The default Sequence Number is 1. To assemble the parts non-sequentially, leave the columns Assembly Time and Sequence Number empty.

**· MU Types**

- Specify the MU Name of the part , such as Part , Container , Transporter , Shaft , etc., in column 1 and the Amount in column 2 of the Assembly Table .
- Specify the name of the part into the column MU Name , not its path, for example MyMountingPart and not *.UserObjects.MyMountingPart .
- To use the default value 1, do not specify an Amount . To make the AssemblyStation accept parts with this MU Name until the capacity of the main MU is reached, specify -1 as the Amount .
- Specify the time, in seconds, that each individual part consumes when it's assembled into the column Assembly Time and the number of the sequence in which the part is assembled into the column Sequence Number . The Assembly Time must be a positive number or 0. If you do not specify a time, the default Assembly Time is 0.

The Sequence Number must be a positive integer number. The default Sequence Number is 1.

To assemble the parts non-sequentially, leave the columns Assembly Time and Sequence Number empty.

**· Depends on Main MU**

- Specify the Main MU Name of the main MU , such as Part , Container , Transporter , Shaft , etc.

Specify an asterisk * to handle all main parts which you did not explicitly enter with names of their own into the Assembly Time . Specify the MU Name and the Amount of the parts.

- To use the default value 1 , do not specify an Amount .

To make the AssemblyStation accept parts with this MU Name until the capacity of the main MU is reached, specify -1 as the Amount .

- Specify the time, in seconds, that each individual part consumes when it's assembled into the column Assembly Time and the number of the sequence in which the part is assembled into the column Sequence Number . The Assembly Time must be a positive number or 0. If you do not specify a time, the default Assembly Time is 0.

The Sequence Number must be a positive integer number. The default Sequence Number is 1.

To assemble the parts non-sequentially, leave the columns Assembly Time and Sequence Number empty.

**Note**

For the settings MU Types and Depends on Main MU this applies:

If the AssemblyStation has objects of type Store as predecessors, it requests the required mounting parts from the Store . If the required parts are not available in the Store at the moment, the Store records the request and delivers the parts to the AssemblyStation once they are available again.

The parts can also be carried from the Store to the AssemblyStation by a Worker . The Store can only provide mounting parts, but no main parts, and it has to be connected with a Connector , even if the Worker carries the part away.

- Fill up Main MU : The AssemblyStation does not use an Assembly Time . Instead, it accepts parts from any of its predecessors until the capacity of the main MU is reached.

**Note**

The columns Predecessor and MU Name cannot contain duplicate entries.

**Note**

If the assembly table is inherited, inheritance is not automatically deactivated when you write to cells of the assembly table. For this reason you will change the inherited table during an assignment. To deactivate inheritance, assign the assembly table to itself.

**Example**

AssemblyStation.AssemblyTable := AssemblyStation.AssemblyTable  // deactivates inheritance

Type

Attribute

**Syntax**

```simtalk
< Path >.AssemblyTable:table
```

Assignment Value

You can assign a value of data type table .

**Example**

```simtalk
var AssemblyTable: table[string,integer]
AssemblyTable.create
AssemblyTable.writeRow(1,1, "MyPartA",1)
AssemblyTable.writeRow(1,2, "MyPartB",2)
MyAssembly.AssemblyTable := AssyList
```

SimTalk

##### AssemblyTableMode [SimTalk]

See also

Assembly Table AssemblyTableMode [SimTalk]

Sets the type of the Assembly Table of the AssemblyStation designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.AssemblyTableMode:string

Assignment Value

You can assign a value of data type string .

You can specify "None" , "Predecessors" , "MUTypes" , "Depends on Main MU" , or "Fill up Main MU" .

Example

MyAssembly.AssemblyTableMode := "Fill up Main MU"

SimTalk

AssemblyTable [SimTalk]

See also

Assembly Table

##### ExitingMU [SimTalk]

Sets what type of MU exits the AssemblyStation designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >.ExitingMU:string
```

Assignment Value

You can assign a value of data type string .

Specify "Main MU" to make the main MU exit the AssemblyStation .

Specify "New MU" to make a newly created MU exit it.

Example

```simtalk
MyAssembly.ExitingMU := "Main MU"
```

See also

Exiting MU [drop-down list] - AssemblyStation

##### MainMU [SimTalk] - AssemblyStation

Sets the number of the predecessor from which the AssemblyStation designated by &lt;Path&gt; pulls the main MU .

Remarks

Specify 0 to make a Worker deliver the main part via a connected Workplace . This only applies for the settings Assembly table &gt; MU Types Depends on Main MU . It does not apply to the settings Assembly Table &gt; None/Predecessors .

As your AssemblyStation is connected to at least two stations, the order in which you connect the predecessors with it is important. If the assembly process does not work as expected, check the numbering of the predecessors by activating More View Options &gt; Show Predecessors on the View ribbon tab of the Frame in a 2D model.

<!-- image -->

Type

Attribute

Syntax

&lt; Path &gt;.MainMU:integer

Assignment Value

You can assign a value of data type integer .

**Example**

```simtalk
MyAssembly.MainMU := 1
MyAssembly.MainMU := 0 // Worker delivers main part via Workplace
```

**See also**

Main MU from Predecessor

Show Predecessors [View ribbon] - 2D

##### NewMU [SimTalk] - AssemblyStation

Sets the path of the MU that the AssemblyStation designated by &lt;Path&gt; creates when it deletes the main MU and creates a new MU instead.

Type

Attribute

Syntax

```simtalk
< Path >.NewMU:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
MyAssembly.NewMU := ".MUs.basicMU"
```

See also

Exiting MU [drop-down list] - AssemblyStation

##### OrderSequence [SimTalk]

Sets the order in which the AssemblyStation designated by &lt;Path&gt; requests MUs and/or services.

Type

Attribute

Syntax

&lt; Path &gt;.OrderSequence:string

Assignment Value

You can assign a value of data type string .

You can specify "MUs then Services" , "Services then MUs" , or "MUs and Services" .

Example

MyAssembly.OrderSequence := "Services then MUs"

See also

Sequence [drop-down list] - AssemblyStation

##### SequentialDelivery [SimTalk]

Makes the Workers deliver the required mounting parts , which the AssemblyStation designated by &lt;Path&gt; requested, sequentially one after the other to the AssemblyStation ( true ).

Remarks

Specify false to make a single Worker deliver as many mounting parts as he can carry to the AssemblyStation .

Specify false to make several Worker deliver the mounting parts to the AssemblyStation in parallel at the same time.

**Note**

If you set SequentialDelivery to true , the attribute ReservedFor returns the object for which the place is currently reserved.

If you set it to false , ReservedFor returns an array of objects for which places are reserved.

Type

Attribute

Syntax

&lt; Path &gt;.SequentialDelivery:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyAssemblyStation.SequentialDelivery := true

SimTalk

ReservedFor [SimTalk]

See also

Set How Workers Deliver Mounting Parts

**Workers Sequentially Deliver MUs to Assemble**

#### DismantleStation

