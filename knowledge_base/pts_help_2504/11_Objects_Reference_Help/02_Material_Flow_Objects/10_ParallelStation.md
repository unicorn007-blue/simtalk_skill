### ParallelStation

Use the ParallelStation for modeling stations for processing several parts in parallel at the same time.

Icon

<!-- image -->

**Description**

The built-in properties of the ParallelStation are the same as those of the Station . The ParallelStation has several processing places as opposed to the single processing place of the Station . A set-up time always applies if a MU has a different name than the part it processed before, i.e., its predecessor. Plant Simulation always moves the MU as a whole not continually, i.e., as soon as its front is located on the ParallelStation , the entire MU is located on it.

On the tab MU Animation you can set how the parts are distributed on the Animation Area of the ParallelStation in 3D.

To show a tooltip with information about the ParallelStation , hover with the mouse over it.

<!-- image -->

To change the length of the graphic and the anchor points of the ParallelStation , click Show Manipulators

<!-- image -->

on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the ParallelStation to your simulation model, click Manage Class Library &gt; Basic Objects &gt; MaterialFlow &gt; ParallelStation on the Home ribbon tab.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

**Note**

The TransferStation is based on a ParallelStation whose properties we modified and enhanced. For this reason opening help of the TransferStation with F1 opens help for the ParallelStation .

See also

Station [object]

Define Processing Times of a ParallelStation

Configure the Processing Stations

Configure the Stations ProcessingA and ProcessingB

Configure the Stations Which Handle the Pallet

Video on YouTube

[https://youtu.be/PQhEriOzVzU?si=XuPINjSUuC0pHfur&amp;t=646](https://youtu.be/PQhEriOzVzU?si=XuPINjSUuC0pHfur&t=646)

#### Dialog Box of the ParallelStation

Dialog Box of the ParallelStation

Double-click the icon of the ParallelStation to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

##### Tab Attributes

###### Tab Attributes [ParallelStation]

The tab Attributes provides the settings listed in the table of contents to the left.

Define the number of processing places of the ParallelStation in a net of coordinates. The ParallelStation accesses the individual places using their x-coordinate and their y-coordinate.

- Type the number of processing places on the x-axis into the text box X-Dimension .
- Type the number of processing places on the y-axis into the text box Y-Dimension .
- Activate Start Processing When Full if you want the ParallelStation to only start processing parts when each of the places contains a part.

**X-Dimension [ParallelStation]**

###### X-Dimension [ParallelStation]

Type in the number of processing places of the ParallelStation along its X-axis .

<!-- image -->

The capacity is represented by a two-dimensional net of coordinates. It is the product of Y-Dimension [ParallelStation] times X-Dimension . The greatest allowed value is ten million.

**Note**

If you decrease the dimension of the ParallelStation , make sure that no MUs are located on the places that will be deleted by this action! If MUs are located on the object, the dimension is limited, as Plant Simulation neither deletes MUs outside of the new dimension automatically nor moves them to another processing place!

SimTalk

XDim [SimTalk] - ParallelStation

See also

YDim [SimTalk] - ParallelStation

Capacity [SimTalk] - ParallelStation

pe, [X,Y] [SimTalk] - ParallelStation

setDim [SimTalk]

###### Y-Dimension [ParallelStation]

Type in the number of processing places of the ParallelStation along its Y-axis .

<!-- image -->

The capacity is represented by a two-dimensional net of coordinates. It is the product of Y-Dimension times X-Dimension [ParallelStation] . The greatest allowed value is ten million.

**Note**

If you decrease the dimension of the ParallelStation , make sure that no MUs are located on the places that will be deleted by this action! If MUs are located on the object, the dimension is limited, as Plant Simulation neither deletes MUs outside of the new dimension automatically nor moves them to another processing place!

SimTalk

##### YDim [SimTalk] - ParallelStation

See also

XDim [SimTalk] - ParallelStation

Capacity [SimTalk] - ParallelStation

pe, [X,Y] [SimTalk] - ParallelStation

setDim [SimTalk]

###### Start Processing When Full [check box]

To make the ParallelStation only start processing parts when a part each is located on all of its processing places, select this check box. This is the default setting.

Then new parts can only enter the ParallelStation when it finished processing the current set of parts and when all parts have left the ParallelStation again.

If a part of another type wants to enter the ParallelStation , it starts processing the parts that are already located on it even when it is not full. Only when the ParallelStation finished processing these parts and when it is empty again, the parts of another type can enter.

If the ParallelStation does not have to be set up, parts of different types can also move onto the ParallelStation . Processing might then start with different Processing Times when the ParallelStation is full. This applies to type-dependent and to place-dependent processing times and when you entered a formula as the processing time.

Use the method startProcessing to start processing parts even if the ParallelStation is not full yet.

You can also select the setting Recovery Time Starts &gt; When processing is done for the start of the Recovery Time . For the setting When part exits the Recovery Time starts when the last part exits the station.

<!-- image -->

If you clear Start Processing When Full , the ParallelStation processes the parts immediately after they entered. New parts can enter at any time.

**Note**

For the ParallelStation you can only deactivate Automatic Processing if the Start Processing When Full is selected.

**Note**

For processing time based failures of a ParallelStation the simulated MTBF is reduced, when the number of parallel processing operations of parts on the ParallelStation increases. This means that the more parts are processed simultaneously, the sooner the failure occurs, and the smaller the availability becomes. This then prevents the Availability you entered into the dialog from being reached.

This does not apply when you activated the setting Start Processing When Full .

SimTalk StartProcessingWhenFull [SimTalk] See also startProcessing [SimTalk] - material flow objects Automatic Processing

##### Tab Failures

Define failures as described under the Tab Failures .

**Note**

For processing time based failures of a ParallelStation the simulated MTBF is reduced, when the number of parallel processing operations of parts on the ParallelStation increases. This means that the more parts are processed simultaneously, the sooner the failure occurs, and the smaller the availability becomes. This then prevents the Availability you entered into the dialog from being reached.

This does not apply when you activated the setting Start Processing When Full .

##### Tab Times

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

Cycle Time [general description]

##### Tab Set-Up

Define properties for setting the object up as described under the Tab Set-Up .

**Note**

The ParallelStation does not provide the setting After n parts .

##### Tab Controls

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the respective control.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

You can create an Entrance Control , an Exit Control , a Set-up Control , and a Pull Control .

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

**Pull Control [general description]**

##### Tab Exit

Tab Exit

Select to which of its successors the object moves the MU on the Tab Exit .

All blocking Exit Strategies of the ParallelStation , except for MU Attribute , do not determine a successor as soon as a MU cannot move. Plant Simulation enters all additional MUs into the Exit Blocking List . As soon as the first blocked MU is moved, Plant Simulation enters an Out event for all MUs contained in the Exit Blocking List allowing them to move on.

See also

Blocking [exit strategy]

Strategy [material flow objects]

##### Tab Statistics

Statistics is described under the Tab Statistics .

To view Resource Statistics of Stationary Resources in the Statistics Report , select View &gt; Show Statistics Report in the dialog of the object. You can also click the right mouse button in the Frame and select Show Statistics Report or you can press F6 .

<!-- image -->

**See also**

Statistics Report [described]

Resource Statistics [check box]

Resource Type

##### Tab Importer

On the Tab Importer you can define services for processing the parts, for setting the station up for a certain type of part, and for repairing the station.

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

While the ParallelStation processes parts costs accrue which result from the sum of the investment costs and the operating costs.

**Note**

The investment costs only accrue during the Depreciation Period .

The ParallelStation distributes the costs evenly across its processing places.

The costs are allocated to the part as accrued costs .

When a processing place of the ParallelStation is empty, the costs remain with the ParallelStation as general costs .

See also

Simulate the Accrued Costs of the Machines

CostAnalyzer &gt; How the CostAnalyzer Assigns Costs to Part Types

CostAnalyzer &gt; Costs Shown in the Costs Report

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

| Create a User-defined Attribute Manually              | getAttrName [SimTalk]                  |
|-------------------------------------------------------|----------------------------------------|
| Create a User-defined Attribute During the Simulation | getAttrNo [SimTalk]                    |
| Show in 3D [user-defined attribute]                   | getAttrType [SimTalk]                  |
| New [user-defined attribute]                          | getAttrValue [SimTalk]                 |
| Edit [user-defined attribute]                         | NumAttr [SimTalk]                      |
| Delete [user-defined attribute]                       | setAttrType [SimTalk]                  |
| createAttr [SimTalk]                                  | setAttrValue [SimTalk]                 |
| deleteAttr [SimTalk]                                  | _Attributes of User-defined Attributes |

**Navigate Menu**

##### Navigate Menu

The commands are described under the Navigate Menu .

View Menu The commands are described under the View Menu . SimTalk updateDialog [SimTalk]

**Tools Menu**

##### Tools Menu

The commands are described under the Tools Menu .

##### Tabs Menu

Use the commands of the Tabs menu to show or hide individual tabs of the material flow objects. If you hide tabs that you do not need, Plant Simulation opens the dialog faster, and you can change to those tabs faster that you need in your daily work.

To apply the changed settings, click OK , close the dialog, and reopen it

The menu shows a check mark to the left of the displayed tabs.

The command Inherit turns inheritance of the displayed or hidden tabs in the dialog off or on.

<!-- image -->

##### Help Menu

The commands are described under the Help Menu .

**Methods of the ParallelStation**

#### \_Methods of the ParallelStation

The ParallelStation provides:

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

findPart [SimTalk] - ParallelStation

Finds the part with the specified name on the ParallelStation designated by &lt;Path&gt; and returns it.

Type

Method

Syntax

```simtalk
< Path >.findPart(PartType:string) → object
```

Parameter

The parameter PartType of data type string designates the part type.

Return Value

The return value has the data type object .

Example

```simtalk
var o: object := MyParallelStation.findPart("Container") // assigns for example .MUs.Container:1
```

pe, [X,Y] [SimTalk] - ParallelStation

Sets the designated processing place of the ParallelStation designated by &lt;Path&gt;.

Remarks

Instead of pe(X,Y) you can also use [X,Y] .

To access the MU that is located on that place, append .Cont .

Type

Method

Syntax

```simtalk
< Path >.pe(X:integer,Y:integer) → any < Path >[X:integer,Y:integer] → any
```

**Parameters**

- The parameter X of data type integer designates the X-Dimension of the processing place.
- The parameter Y of data type integer designates the Y-Dimension .

Return Value

The return value has the data type any .

**Example**

```simtalk
@.move(ParallelStation[2,3])
@.move(ParallelStation.pe(2,3))
print ParallelStation[2,3].Cont.name
```

**See also**

X-Dimension [ParallelStation]

Y-Dimension [ParallelStation]

#### Read-Only Attributes of the ParallelStation

Read-Only Attributes of the ParallelStation

The ParallelStation provides:

- The read-only attribute Capacity [SimTalk] - ParallelStation .
- The \_Read-Only Attributes of All Objects .
- The Read-Only Attributes of the Material Flow Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print ParallelStation.Capacity Capacity [SimTalk] - ParallelStation Returns the capacity of the ParallelStation designated by &lt;Path&gt;.

Remarks

The Capacity is the product of XDim times YDim .

Type

Read-only attribute

Syntax

```simtalk
< Path >.Capacity → integer
```

Watchable

The attribute is watchable .

Return Value

The return value has the data type integer .

Example

```simtalk
if ParallelStation.Capacity >= lotsize
	@.move(ParallelStation)
end
```

SimTalk

XDim [SimTalk] - ParallelStation

YDim [SimTalk] - ParallelStation

See also

Y-Dimension [ParallelStation]

X-Dimension [ParallelStation]

#### Attributes of the ParallelStation

##### \_Attributes of the ParallelStation

The ParallelStation provides:

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
ParallelStation.XDim := 3
ParallelStation.YDim := 4
print ParallelStation.XDim
posit := MyStation.Cont.XPos
```

##### StartProcessingWhenFull [SimTalk]

Sets if the ParallelStation designated by &lt;Path&gt; only starts processing parts if a part each is located on all of its processing stations ( true ).

Remarks

StartProcessingWhenFull is the default setting. Here new parts can only enter the ParallelStation when it finished processing the current set of parts and when all parts have left the ParallelStation again.

When a part of another type wants to enter the ParallelStation , it starts processing the parts that are already located on it even when it is not full. Only when the ParallelStation finished processing these parts and when it is empty again, the parts of another type can enter.

Use the method startProcessing to start processing parts even if the ParallelStation is not full yet.

Specify false to make the ParallelStation process the parts immediately after they entered. New parts can enter at any time.

If the ParallelStation does not have to be set up, parts of different types can also move onto the ParallelStation . Processing then might start with different Processing Times when the ParallelStation is full. This applies to type-dependent and to place-dependent processing times and when you entered a formula as the processing time.

**Note**

For processing time based failures of a ParallelStation the simulated MTBF is reduced, when the number of parallel processing operations of parts on the ParallelStation increases. This means that the more parts are processed simultaneously, the sooner the failure occurs, and the smaller the availability becomes. This then prevents the Availability you entered into the dialog from being reached.

This does not apply when you activated the setting Start Processing When Full .

Type

Attribute

Syntax

&lt; Path &gt;.StartProcessingWhenFull:boolean

Assignment Value

You can assign a value of data type boolean .

**Example**

ParallelStation.StartProcessingWhenFull := false

SimTalk

startProcessing [SimTalk] - material flow objects

See also

Start Processing When Full [check box]

##### XDim [SimTalk] - ParallelStation

Sets or gets the number of processing places of the ParallelStation designated by &lt;Path&gt; in the XDimension .

Remarks

The Capacity is the product of X-Dimension times Y-Dimension . The greatest allowed value is ten million.

**Note**

If you decrease the dimension of the ParallelStation , make sure that no MUs are located on the places that will be deleted by this action! If MUs are located on the object, the dimension is limited, as Plant Simulation neither deletes MUs outside of the new dimension automatically nor moves them to another processing place!

Type

Attribute

Syntax

```simtalk
< Path >.XDim:integer
```

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
ParallelStation.XDim := 3
ParallelStation.YDim := 4 // 12 stations
```

See also

X-Dimension [ParallelStation]

YDim [SimTalk] - ParallelStation YDim [SimTalk] - ParallelStation YDim [SimTalk] - ParallelStation Sets or gets the number of processing places of the ParallelStation designated by &lt;Path&gt; in the YDimension .

Remarks

The Capacity is the product of X-Dimension times Y-Dimension . The greatest allowed value is ten million.

**Note**

If you decrease the dimension of the ParallelStation , make sure that no MUs are located on the places that will be deleted by this action! If MUs are located on the object, the dimension is limited, as Plant Simulation neither deletes MUs outside of the new dimension automatically nor moves them to another processing place!

Type

Attribute

Syntax

```simtalk
< Path >.YDim:integer
```

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
ParallelStation.XDim := 3
ParallelStation.YDim := 4 // 12 stations
```

See also

Y-Dimension [ParallelStation]

XDim [SimTalk] - ParallelStation

**AssemblyStation**

