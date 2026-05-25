### Store

#### Store [object]

Use the Store for storing parts.

Icon

<!-- image -->

Description

The MUs remain in the Store until you remove them, for example by using a Method . Type the number of storage places into a net of coordinates, i.e., into the text boxes X-Dimension , Y-Dimension , and Z-Dimension . The Store receives MUs as long as storage places are available within the storage area. The part triggers a sensor, when it enters the Store . The sensor then calls an Entrance Control , i.e., a Method object, that determines the storage place onto which the Store places the part . The Entrance Control can update the inventory list or execute any other action you define. If you do not define an Entrance Control , the Store places the part onto the first unoccupied storage place in the net of coordinates.

The Store does neither have a Set-up Time nor a Processing Time . If you decrease the size of the Store , you will have to delete or move MUs that are located outside of these new coordinates. If, for example, a part is located at the position (3,4), the new x-coordinate may not be less than 3, and the new y-coordinate less than 4. During a failure the Store does not place any parts into storage but can still remove them from storage.

You can also configure the Store as a Supermarket in pulling material flow strategies. The Supermarket stores and manages the different part types and controls the fill level for each part type in the Store . Once the minimum stock for a part type is reached, the Supermarket automatically sends an order to the parts supplier so that it fills the Store up again.

You will typically use the Store to model warehouses and other storage facilities in your plant.

In 3D, you can select different configurations for the Store on the tab Appearance .

<!-- image -->

On the tab MU Animation you can set how the parts are distributed across the Animation Area of the Store in 3D.

<!-- image -->

To show a tooltip with information about the Store , hover with the mouse over it.

<!-- image -->

Show Manipulators

To change the length of the graphic and the anchor points of the object, click Show Manipulators on the Edit ribbon tab or press M on the keyboard.

You can use the manipulators to change the dimensions of the Store .

<!-- image -->

<!-- image -->

Add the Object to the Simulation Model

<!-- image -->

To add the Store to your simulation model, click MaterialFlow &gt; Store on the Home ribbon tab.

<!-- image -->

Manage Class Library &gt; Basic Objects &gt;

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

See also Place Parts into Stock and Remove Parts from It Use the Store as Supermarket Stack Parts in the Store

**Appearance of the Store**

Animation Area [described]

Video on YouTube

[https://youtu.be/ISYfZMdQp3w?si=csV--W1TIIRHgh6J](https://youtu.be/ISYfZMdQp3w?si=csV--W1TIIRHgh6J)

#### Dialog Box of the Store

Dialog Box of the Store

Double-click the icon of the Store to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Video on YouTube

[https://youtu.be/ISYfZMdQp3w?si=n9D4XzDdv5CN5Nwg&amp;t=35](https://youtu.be/ISYfZMdQp3w?si=n9D4XzDdv5CN5Nwg&t=35)

Tab Attributes

Tab Attributes [Store]

The tab Attributes provides the setting listed in the table of contents to the left.

The storage places of the Store are organized in a net of coordinates whose dimension you can set in the X-Dimension , the Y-Dimension , and the Z-Dimension . You can access the various storage places using their coordinates.

In 3D, you can edit the dimensions of the graphic of the Store by clicking Show Manipulators on the Edit ribbon tab and selecting and dragging a manipulator.

In 3D, you can select different configurations for the Store on the tab Appearance .

<!-- image -->

Select the check box to use the Store as Supermarket for pulling material flow strategies. Plant Simulation then shows the Configuration button and dims the settings for the dimension.

<!-- image -->

**X-Dimension [Store]**

###### X-Dimension [Store]

Type the number of MUs which the Store can store along the x-axis into the text box X-Dimension .

<!-- image -->

The Capacity of the Store is X-Dimension times Y-Dimension times Z-Dimension . The greatest allowed value is ten million.

If you decrease the dimension of the Store , make sure that no MUs are located on the storage places that will be deleted by this action! Either delete these MUs or move them to another storage place on the smaller loading space.

SimTalk

XDim [SimTalk] - Store

Capacity [SimTalk] - Store

pe(X,Y) / [X,Y] [SimTalk] - Store

setDim [SimTalk]

See also

Y-Dimension [Store]

Z-Dimension [Store]

###### Y-Dimension [Store]

Type the number of MUs which the Store can store along the y-axis into the text box Y-Dimension .

<!-- image -->

The Capacity of the Store is X-Dimension times Y-Dimension times Z-Dimension . The greatest allowed value is ten million.

If you decrease the dimension of the Store , make sure that no MUs are located on the storage places that will be deleted by this action! Either delete these MUs or move them to another storage place on the smaller loading space.

SimTalk

YDim [SimTalk] - Store

Capacity [SimTalk] - Store

pe(X,Y) / [X,Y] [SimTalk] - Store

setDim [SimTalk]

See also

X-Dimension [Store]

Z-Dimension [Store]

**Z-Dimension [Store]**

###### Z-Dimension [Store]

Type the number of MUs which the Store can store along the z-axis into the text box Z-Dimension .

<!-- image -->

The Z-Dimension enables to stack parts in the Store , for example upward in a high bay warehouse. The Capacity of the Store is X-Dimension times Y-Dimension times Z-Dimension

If you decrease the dimension of the Store , make sure that no MUs are located on the storage places that will be deleted by this action! Either delete these MUs or move them to another storage place on the smaller loading space.

SimTalk

ZDim [SimTalk] - Store

getStackHeight [SimTalk]

See also

Stack Parts in the Store

Unload Stacked Parts

X-Dimension [Store]

Y-Dimension [Store]

###### Supermarket [check box]

To use the Store as a Supermarket , select the check box. You can use the Supermarket to model pulling material flow strategies.

<!-- image -->

The Supermarket stores and manages the different part types and controls the fill level for each part type in the Store . When the minimum stock for a part type is reached, the Supermarket automatically sends an order to the parts supplier so that it fills up the Store again with the respective part type.

**Configuration Table**

Click Configuration to open the Configuration Table in which you can set the Part Type , the Minimum Stock , the Maximum Stock , the Initial Stock , and the Supplier .

<!-- image -->

Plant Simulation automatically sets the dimensions of the Store for the animation.

- The X-Dimension is always 1.
- The Y-Dimension shows the amount of the different part types.
- The Z-Dimension shows -1.
- The Store always places parts or the same type on a stack.

<!-- image -->

After inserting the Store into your model, Plant Simulation shows it with the default dimensions. Clicking OK then shows it with the settings that you typed into the Configuration Table and propagates the values to the child objects.

Show the Occupancy of the Supermarket in a Chart

If you drag the Store configured as a Supermarket onto a Chart , it shows the occupancy for all parts that are defined in the Configuration Table by default.

<!-- image -->

**SimTalk**

Supermarket [SimTalk]

<!-- image -->

orderParts [SimTalk] - Store See also Use the Store as Supermarket MU selection [drop-down list] &gt; Order Controlled [MU selection] Configuration [button] View &gt; Show Orders [Source] Video on YouTube

[https://youtu.be/ISYfZMdQp3w?si=oRZapujKzN7zp5-\_&amp;t=381](https://youtu.be/ISYfZMdQp3w?si=oRZapujKzN7zp5-_&t=381)

**Configuration [button]**

###### Configuration [button]

To open the configuration table, click the button. Specify the Part Type , the Name of the part, the Minimum Stock , the Maximum Stock , the Initial Stock , and the Supplier

<!-- image -->

When you activate the check box Supermarket , Plant Simulation activates the Configuration button.

**Note**

Before you can type in data, click the Inheritance check box so that it looks like this .

<!-- image -->

- Type in the absolute path of the Part Type or drag the MU class into the cell and drop it there.
- Type in the Name of the Part Type . If you do not specify anything, Plant Simulation uses the name of the object from the column Part Type . The names that you enter have to be unique.
- Type in the Minimum stock of the part type. This is the smallest amount of parts of the designated part type in the Supermarket .
- Type in the Maximum stock of the part type. This is the greatest amount of parts of the designated part type in the Supermarket .
- Type in the Initial stock of the part type. This is the amount of parts of the designated part type which are created while initializing the Store .

The Initial Value can also be smaller than the Minimum Value . In this case the order is triggered on Init .

- Type in the Supplier of the part type. The supplier can be another Store , a Source , or a Method . When re-ordering parts, Plant Simulation fills the Store to the Maximum stock.

If parts leave the Store while an order is open, Plant Simulation only creates an additional order if the amount of the already ordered parts plus the current parts do not secure the Minimum Stock .

Specify a Method to set from which supplier the parts are ordered if several suppliers can provide this part.

The Method has to have the following signature:

param partName:string, minStock:integer, maxStock:integer, currentStock:integer, orderedParts:integer

- The parameters contain the data from the configuration of the part which is running out of stock.
- The caller ( ? ) of the method is the Store , and the active element ( @ ) is the part which is running out of stock.
- The column Current shows how many parts of this part type are located in the Store at the moment. You cannot edit this column.
- The column Waiting shows the amount of remaining ordered parts. You cannot edit this column. The method orderParts of Source and Store increase this counter.

Click the right mouse button and select Append Row or Insert Row to add additional products and their data. Click Delete Row to delete the selected row.

SimTalk

orderParts [SimTalk] - Store

getSupermarketConfiguration [SimTalk]

setSupermarketConfiguration [SimTalk]

Stock.MyPartName [SimTalk]

See also

Supermarket [check box]

MU selection [drop-down list] &gt; Order Controlled [MU selection]

orderParts [SimTalk] - Source

View &gt; Show Orders [Source]

Use the Store as Supermarket

Video on YouTube

[https://youtu.be/ISYfZMdQp3w?si=oRZapujKzN7zp5-\_&amp;t=381](https://youtu.be/ISYfZMdQp3w?si=oRZapujKzN7zp5-_&t=381)

##### Tab Times

Tab Times

Define Times as described under the Tab Times .

Select a distribution from the drop-down list and type the values that this distribution requires into the text box. Plant Simulation shows the parameters along the upper border of the tab. You can also select a constant time ( Const ).

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr .

See also

Recovery Time [general description]

Recovery Time Starts

Cycle Time [general description]

##### Tab Failures

Define failures as described under the Tab Failures .

##### Tab Controls

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the respective control.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

You can create an Entrance Control , an Exit Control , and a Pull Control .

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

**See also**

Entrance Control [general description]

Exit Control [general description]

Pull Control [general description]

##### Tab Exit

Tab Exit

Select to which of its successors the object moves the MU on the Tab Exit .

See also

Blocking [exit strategy]

Strategy [material flow objects]

##### Tab Statistics

Statistics is described under the Tab Statistics .

To view Resource Statistics of Stationary Resources in the Statistics Report , select View &gt; Show Statistics Report in the dialog of the object. You can also click the right mouse button in the Frame and select Show Statistics Report or you can press F6 .

<!-- image -->

**See also**

Resource Statistics [check box]

Resource Type

**Tab Energy**

##### Tab Energy

Select energy settings for the object on the Tab Energy .

##### Tab Costs

Select costs settings for the object on the Tab Costs .

While the Store places parts into storage costs accrue which result from the sum of the investment costs and the operating costs.

**Note**

The investment costs only accrue during the Depreciation Period .

The costs are allocated to the part, proportional to the capacity, as accrued costs .

If the Store is empty, the costs remain with the Store as general costs .

See also

Simulate the Accrued Costs of the Machines

CostAnalyzer &gt; How the CostAnalyzer Assigns Costs to Part Types

CostAnalyzer &gt; Costs Shown in the Costs Report

**Tab User-defined**

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

##### Navigate Menu

The commands are described under the Navigate Menu .

View Menu

View Menu

The View Menu provides commands to access its functions.

| Refresh [on View menu]                     | Show Orders [Source]             |
|--------------------------------------------|----------------------------------|
| Show Statistics Report [on View menu]      | Contents [material flow objects] |
| Show Attributes and Methods [on View menu] | Forward Blocking List            |

**See also**

View Menu [general description]

**Show Orders [Store]**

###### Show Orders [Store]

Opens a table that shows the orders which are pending with the Store .

The table contains the Part Type of the ordered MU , its Amount , and the Target of the part. The Target is the object that orders the parts.

<!-- image -->

###### Exit Blocking List [Store]

Opens a list, which contains all MUs , which are waiting to be carried away by a Worker .

The table Waiting for Importers shows the path of the MU , its folder, its name, and its number, which waits for a Worker to pick it up and carry it away.

<!-- image -->

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

**Methods of the Store**

#### \_Methods of the Store

The Store provides:

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

**findFreePlace [SimTalk]**

##### findFreePlace [SimTalk]

Finds a free storage place in the Store designated by &lt;Path&gt; and returns it.

Remarks

**Note**

The method applies to the Store , the ParallelStation , the Container , and to the Transporter with a loading space of type Store .

Type

Method

Syntax

```simtalk
< Path >.findFreePlace([StartingAtEnd:boolean:=false, XStart:integer:=1, YStart:integer:=1]) → any
```

**Parameters**

- The optional parameter StartingAtEnd of data type boolean specifies if the search is to proceed starting at the end backward toward the front ( true ) or not ( false ).

**Default Value of the Parameter**

The default value is false.

- The optional parameter XStart of data type integer designates the X-coordinate of the storage place from which on the search is to be started.

**Default Value of the Parameter**

The default value is 1.

- The optional parameter YStart of data type integer designates the Y-coordinate of the storage place from which on the search is to be started.

**Default Value of the Parameter**

The default value is 1.

Return Value

The return value has the data type any .

**Example**

```simtalk
var freePlace := .MUs.Container:1.findFreePlace
if freePlace /= void
	var x,y:integer
	freeplace.getStoragePlace(x, y)
	print "Found free place at (", x, ", ", y, ")"
end
```

**See also**

**findFreePlaceInRange [SimTalk]**

**findFreePlaceInRange [SimTalk]**

##### findFreePlaceInRange [SimTalk]

Finds a free storage place within the designated range of the Store designated by &lt;Path&gt; and returns the position of the free place.

Type

Method

Syntax

```simtalk
< Path >.findFreePlaceInRange(SearchRange:listrange[, LeftToRight:boolean:=true, TopToBottom:boolean:=true])
-> any
```

**Parameters**

You can specify the following parameters:

- The parameter SearchRange of data type listrange designates the range of the list to be searched.
- The optional parameter LeftToRight of data type boolean sets if the list is searched from left to right ( true ) or from right to left ( false ).

**Default Value of the Parameter**

The default value is true.

- The optional parameter TopToBottom of data type boolean sets if the list is searched from top to bottom ( true ) or from bottom to top ( false ).

**Default Value of the Parameter**

The default value is true.

Return Value

The return value has the data type any .

Example

MyStore.findFreePlaceInRange({2,2}..{*.*}, false)

**See also**

**findFreePlace [SimTalk]**

##### findPart [SimTalk] - Store

Finds the part with the specified name in the Store designated by &lt;Path&gt; and returns it.

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
var o: object := MyStore.findPart("Container") // returns for example .MUs.Container:1
```

getSupermarketConfiguration [SimTalk]

Returns the configuration table of the Store designated by &lt;Path&gt;.

Remarks

The configuration table might look like this:

<!-- image -->

Type

Method

Syntax

&lt; Path &gt;.getSupermarketConfiguration(Target:table)

Parameter

The parameter Target of data type table designates the DataTable into which the configuration settings will be written.

Example

MyStore.getSupermarketConfiguration(MyDataTable)

SimTalk

setSupermarketConfiguration [SimTalk]

See also

Configuration [button]

orderParts [SimTalk] - Store

Orders parts from the Store designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.orderParts(PartType:string, Amount:integer, Target:object)
```

**Parameters**

- The parameter PartType of data type string designates the name of the part type that is going to be ordered.
- The parameter Amount of data type integer designates the amount of parts that is going to be ordered.
- The parameter Target of data type object designates the object that orders the parts. The target, i.e., the destination object, can be any material flow object.

If the Target is a Supermarket , Plant Simulation increases the counter of the amount of remaining ordered parts. Compare the column Waiting in the Configuration table of the Store .

**Examples**

MyStore.orderParts("MyPart", 12, MyStation)

```simtalk
param partsName:string, minStock:integer, maxStock:integer, currentStock:integer, orderedParts:integer
var amount:integer := maxStock-currentStock-orderedParts
if amount > 0 then
	MyStore.orderParts(partsName, amount, ?)
end
```

**SimTalk**

orderParts [SimTalk] - Source

See also

Configuration [button]

Supermarket [check box]

pe(X,Y) / [X,Y] [SimTalk] - Store

Sets the designated storage place in the Store designated by &lt;Path&gt;.

Remarks

Instead of pe(X,Y) you can also use [X,Y] .

To access the MU that is located on the designated storage place, append .Cont .

**Note**

The read-only attribute Cont returns the MU at the called position.

Type

Method

Syntax

```simtalk
< Path >.pe(X:integer, Y:integer)
-> any < Path >[X:integer, Y:integer]
-> any
```

**Parameters**

- The parameter X of data type integer designates the X-Dimension of the storage place.
- The parameter Y of data type integer designates the X-Dimension .

Return Value

The return value has the data type any .

Example

```simtalk
@.move(MyStore.pe(2,3)) MyStore[2,3].Cont.move(Station)
```

SimTalk

Cont [SimTalk] - material flow objects

See also

\_Methods and Read-Only Attributes of the Place in the Store [pe]

X-Dimension [Store] Y-Dimension [Store]

##### setSupermarketConfiguration [SimTalk]

Sets the configuration table of the Store designated by &lt;Path&gt;.

Remarks

The configuration table might look like this:

<!-- image -->

Type

Method

Syntax

&lt; Path &gt;.setSupermarketConfiguration(Source:table/void)

**Parameter**

The parameter Source of data type table designates the DataTable which contains the configuration. When setting the configuration Plant Simulation ignores the columns Current and Waiting .

Specify void for the parameter Source to activate inheritance of the Configuration table of the Store .

**Examples**

MyStore.setSupermarketConfiguration(MyDataTable)

MyStore.setSupermarketConfiguration(void) -- activates inheritance of the configuration table

SimTalk

getSupermarketConfiguration [SimTalk]

See also

Configuration [button]

#### Methods and Read-Only Attributes of the pe

\_Methods and Read-Only Attributes of the Place in the Store [pe]

The pe , i.e., the place in the Store , provides the methods and read-only attributes listed in the table of contents to the left.

##### Cont [SimTalk] - pe, Store

Returns the MU , which is located at the top-most position on the designated storage place of the Store designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

```simtalk
< Path >.pe(X:integer, Y:integer).Cont → object < Path >[X:integer, Y:integer].Cont → object
```

**Parameters**

- The parameter X of data type integer designates the position of the storage place in the X-Dimension .
- The parameter Y of data type integer designates the position of the storage place in the Y-Dimension .

Return Value

The return value has the data type object .

Example

```simtalk
MyStore.pe(1,1).Cont.move(Station) MyStore[1,1].Cont.move(Station)
```

See also

X-Dimension [Store]

Y-Dimension [Store]

exitBlockList [SimTalk] - Store

exitBlockList [SimTalk] - Store

Returns an array containing the MUs , which are going to exit the Store designated by &lt;Path&gt; and wait for a Worker to pick them up.

Remarks

Specify the optional parameter ExitBlockingList of data type table to write the objects contained in the Exit Blocking List into this list.

For the Store the Exit Blocking List also contains the position of the place for which the part is entered. If you need this information, you have to specify a table instead of writing the data to an array .

Do not specify the optional parameter ExitBlockingList to return an array containing the objects contained in the Exit Blocking List . The array is one-dimensional and only contains the objects in the blocking list. If you need the start times of the blockages, which are contained in the blocking table, you can query them from the object with the attribute BlockingStarttime .

Type

Method

Syntax

```simtalk
< Path >.exitBlockList([ExitBlockingList:table])
-> void/object[]
```

**Parameter**

The optional parameter ExitBlockingList of data type table designates the name of the table. This can be a DataTable or a local variable, into which the method writes the values.

Plant Simulation automatically generates the format of this table with two columns. Column 1 has the data type object and contains the MUs that unsuccessfully tried to exit the object. Column 2 contains the simulation time at which the MUs attempted to enter the object.

Return Value

The return value is an array of data type object .

Example

```simtalk
var musToExit := Store.exitBlockList   // returns an array of MUs, which are going to exit
var t:table
```

Store.exitBlockList(t)                 // fills the table with MUs, which are going to exit

**SimTalk**

BlockingStarttime [SimTalk]

exitBlockList [SimTalk] - material flow objects

exitBlockList [SimTalk] - lane A or B

See also

Exit Blocking List

Check the Contents List of the Stations

##### getStackHeight [SimTalk]

getStackHeight [SimTalk]

Returns the height of the stack in meters on the designated storage place in the Store designated by &lt;Path&gt;.

Remarks

getStackHeight also applies to places on pallets/Containers and to Transporters with a loading space of type Store .

**Note**

Here the height of the stack designates its physical height, not the number of parts on the stack.

If you output the value with the method print , the unit is the unit you selected under Preferences/ Model Settings &gt; Unit &gt; Length .

Type

Read-only attribute

Syntax

```simtalk
< >.pe(X:integer, Y:integer).getStackHeight → length
Path < Path >[X:integer, Y:integer].getStackHeight → length
```

**Parameters**

- The parameter X of data type integer designates the position of the storage place in the X-Dimension .
- The parameter Y of data type integer designates the position of the storage place in the Y-Dimension .

Return Value

The return value has the data type length .

**Example**

```simtalk
print MyStore.pe(2,1).getStackHeight
print MyStore[2,1].getStackHeight
```

SimTalk

ZDim [SimTalk] - Store See also Stack Parts in the Store Length [preferences] X-Dimension [Store] Y-Dimension [Store]

##### mu [SimTalk] - pe, Store

mu [SimTalk] - pe, Store

Returns all stacked MUs on the designated storage place in the Store designated by &lt;Path&gt;.

**Remarks**

The method mu accesses the MUs on the stack if the Z-Dimension is greater than 1.

The index does not signify the order of entry.

You can query the greatest index with the read-only attribute NumMU .

Type

Method

Syntax

```simtalk
< >.pe(X:integer, Y:integer).mu(MU:integer) → object
Path < Path >[X:integer, Y:integer].mu(MU:integer) → object
```

**Parameter**

- The parameter X of data type integer designates the position of the storage place in the X-Dimension .
- The parameter Y of data type integer designates the position of the storage place in the Y-Dimension .
- The parameter mu of data type integer designates the position of the storage place in the Z-Dimension . Specify -1 to return the MU at the bottom of the stack. It returns VOID if the object is empty.

**Default Value of the Parameter**

The default value for the parameter Number is 1.

**Note**

The last MU is always the MU that is located on the bottom storage place, as a rule this is the MU that was moved onto the object first.

**Return Value**

The return value has the data type object .

**Examples**

```simtalk
print MyStore.pe(5,5).mu(1) // returns the topmost MU on the stack // corresponds to print
MyStore.pe(5,5).cont
print MyStore[5,5].mu(2)    // returns the second MU from the top on the stack
print MyStore[5,5].mu(3)    // returns the MU at the bottom of a stack with 3 parts
print MyStore[1,1].MU(1)   // returns the topmost MU on the stack
print MyStore[1,1].MU(-1)  // returns the MU at the bottom of the stack
```

**SimTalk**

NumMU [SimTalk] - pe, Store

See also

X-Dimension [Store]

Y-Dimension [Store]

Z-Dimension [Store]

##### NumMU [SimTalk] - pe, Store

NumMU [SimTalk] - pe, Store

Returns the number of MUs , which are located on the pe in the Store designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

```simtalk
< Path >.pe(X:integer, Y:integer).NumMU → integer < Path >[X:integer, Y:integer].NumMU → integer
```

**Parameters**

- The parameter X of data type integer designates the position of the storage place in the X-dimension .
- The parameter Y of data type integer designates the position of the storage place in the Y-dimension .

Return Value

The return value has the data type integer .

Example

```simtalk
print MyStore.pe(1,1).NumMU
print MyStore[1,1].NumMU
```

See also

X-Dimension [Store]

Y-Dimension [Store]

#### Read-Only Attributes of the Store

\_Read-Only Attributes of the Store

The Store provides:

- The read-only attributes listed in the table of contents to the left.
- The \_Read-Only Attributes of All Objects .
- The Read-Only Attributes of the Material Flow Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print Store.Capacity Capacity [SimTalk] - Store Capacity [SimTalk] - Store Returns the capacity of the Store designated by &lt;Path&gt;.

Remarks

The Capacity is the product of XDim times YDim times ZDim .

Type

Read-only attribute

Syntax

```simtalk
< Path >.Capacity → integer
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type integer .

Example

```simtalk
if MyStore.Capacity <= lotsize
	@.move(MyStore)
end
```

SimTalk

XDim [SimTalk] - Store

YDim [SimTalk] - Store

ZDim [SimTalk] - Store

See also

X-Dimension [Store]

Y-Dimension [Store]

**Z-Dimension [Store]**

##### Stock.MyPartName [SimTalk]

Stock.MyPartName [SimTalk]

Returns the current stock of the parts designated by MyPartName in the Store designated by &lt;Path&gt;.

Remarks

MyPartName is the name of the respective part, which you set in the Configuration table of the Store .

Type

Read-only attribute

Syntax

```simtalk
< Path >.Stock.MyPartName → integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
print MyStore.Stock.PartRed // might, for example,
return 1
```

See also

Configuration [button]

#### Attributes of the Store

Attributes of the Store

The Store provides:

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
MyStore.YDim := 10
print MyStore.YDim
posit := MyStation.Cont.XPos
```

##### Supermarket [SimTalk]

Supermarket [SimTalk]

Sets if the Store designated by &lt;Path&gt; works as a supermarket ( true ) or not ( false ).

Type

Attribute

Syntax

```simtalk
< Path >.Supermarket:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyStore.Supermarket := true
```

See also

Supermarket [check box]

Configuration [button]

Source &gt; MU selection [drop-down list] &gt; Order Controlled [MU selection]

XDim [SimTalk] - Store

Sets the number of storage places on the x-axis of the Store designated by &lt;Path&gt;.

Remarks

The Capacity is the product of XDim times YDim times ZDim . The greatest allowed value is ten million.

If you decrease the dimension of the Store , make sure that no MUs are located on the storage places that will be deleted by this action! Either delete these MUs or move them to another storage place on the smaller storage area.

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
MyStore.XDim := 10
```

SimTalk

YDim [SimTalk] - Store

ZDim [SimTalk] - Store

See also

X-Dimension [Store]

YDim [SimTalk] - Store

YDim [SimTalk] - Store

Sets the number of storage places on the y-axis of the Store designated by &lt;Path&gt;.

Remarks

The Capacity is the product of XDim times YDim times ZDim . The greatest allowed value is ten million.

If you decrease the dimension of the Store , make sure that no MUs are located on the storage places that will be deleted by this action! Either delete these MUs or move them to another storage place on the smaller storage area.

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
MyStore.YDim := 10
```

SimTalk

XDim [SimTalk] - Store

ZDim [SimTalk] - Store

See also

Y-Dimension [Store]

ZDim [SimTalk] - Store

Sets the number of storage places on the z-axis of the Store designated by &lt;Path&gt;.

Remarks

The ZDim permits to stack parts onto other parts.

The Capacity is the product of XDim times YDim times ZDim . The greatest allowed value is ten million.

If you decrease the dimension of the Store , make sure that no MUs are located on the storage places that will be deleted by this action! Either delete these MUs or move them to another storage place on the smaller storage area.

Type

Attribute

Syntax

```simtalk
< Path >.ZDim:integer
```

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type integer .

Examples

```simtalk
MyStore.ZDim := 4
// Enumerates all the MUs on place (1,1):
var place := Store[1,1]
for var i := 1 to place.NumMU
```

