### Container

Use the Container for modeling pallets, bins, boxes, etc.

Icon

<!-- image -->

**Description**

The Container is a moving material flow object for transporting other MUs . Define the capacity of the loading space-which refers to the number of MUs only, not to their physical size-along the x-axis and the y-axis. During a simulation run Plant Simulation moves the Container along from material flow object to material flow object along the Connectors you inserted.

**Appearance of the Container In 3D**

- You can set how Plant Simulation distributes the parts on the Animation Area on the tab MU Animation of the Container .
- You can set a material on the tab Appearance .
- You can use alternative graphics of the EUR-pallets of types EUR 2/ISO2, EUR 3, and EUR 6/ISO0. Click Exchange Graphics in the 3D window of the Container and select one of the alternative graphics in the Plant Simulation Installation folder &gt; s3d-graphics &gt; Containers .

<!-- image -->

<!-- image -->

The EUR-pallet of type EUR 1/ISO1 is the standard graphic of the Container .

To show a tooltip with information about the Container , hover with the mouse over it.

<!-- image -->

Add the Object to the Simulation Model

To add the Container to your simulation model, click Manage Class Library &gt; Basic Objects &gt; MUs &gt; Container on the Home ribbon tab.

**See also**

Shared Properties of the Mobile Objects

<!-- image -->

<!-- image -->

#### Dialog Box of the Container

Dialog Box of the Container

Double-click the icon of the Container that is located on one of the material flow objects in the Frame to open its dialog box.

Edit Simulation Properties

There you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

To change the settings of the class of the object, double-click it in the Class Library or on the tab Moving Units in the Toolbox . Here you can then type in or select the simulation properties to get the results you need. The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties :

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the 3D model and press the spacebar .

See also

Number [of the MU]

Conveying Direction [described]

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

The shared properties are described under the Tab Attributes .

**MU Length [Container]**

###### MU Length [Container]

Type the Length of the Container into the text box.

The length-oriented objects Conveyor , Track , and TwoLaneTrack use the Length to determine how many Containers they can hold.

<!-- image -->

**SimTalk**

MULength [SimTalk]

###### MU Width [Container]

Type the Width of the Container into the text box.

The length-oriented objects Conveyor , Track , and TwoLaneTrack use the Width after the AngularConverter has changed the Conveying Direction to determine how many Containers they can hold.

<!-- image -->

SimTalk

MUWidth [SimTalk]

**MU Height [Container]**

###### MU Height [Container]

Type the Height of the Container .

<!-- image -->

The height is only important for 3D as only 3D provides the z-dimension.

SimTalk

MUHeight [SimTalk]

###### Booking Point Length [Container]

Type in the relative position of the Booking Point of the Container , which applies, when it is conveyed lengthwise .

The value you type in is the distance in meters from booking point 0, which is located at the front of the Container , in the direction of motion. Type in a relative value between 0 and 1 . Plant Simulation uses it, when the Conveying Direction is forward or backward . Plant Simulation shows the absolute position of the booking point in parentheses.

When you are modeling conveyor systems, the booking point oftentimes represents the center of gravity of the part. Once the booking point, i.e., the center of gravity of the part, has transferred onto a conveyor, the part starts moving with the Speed you set for this conveyor.

<!-- image -->

By default, each Container has a booking point which Plant Simulation uses when it shows the Container on the material flow objects during the simulation run. The Container requires a booking point, as a long Container can be located on more than one length-oriented object at the same time.

Plant Simulation uses the booking point to determine on which material flow object it shows the Container when animating a simulation run. Plant Simulation shows, for example, a Container moving along from Conveyor to Conveyor on the preceding Conveyor until its booking point moves on to the succeeding Conveyor .

If the part is not animated on the expected position on the object, check the position of the Booking Point .

**Compare this example:**

- Here Booking Point Length and Booking Point Width of the square part are located in its center at the position 0.5 . The part is animated at the center of the conveyor belt.

<!-- image -->

- Here Booking Point Width of the square part are located at the position 0.2 . The part is animated with an offset to the left in the direction of motion on the conveyor belt.

<!-- image -->

**Note**

When you assign a value to the booking point in a Method , Plant Simulation interprets this number as meters. Only when outputting it with the method print , it converts the value according to the settings you selected under File &gt; Model Settings/Preferences &gt; Units &gt; Length .

**SimTalk**

MULength [SimTalk]

**BookPntWRelative [SimTalk]**

See also

**Set and Link Animation Points and Lines**

**Booking Point Width [Container]**

###### Booking Point Width [Container]

Type the relative position of the Booking Point the Container when it is conveyed Crosswise .

The value you type in is the distance in meters from booking point 0, which is located at the right-hand side of the Container in the direction of motion. Type in a relative value between 0 and 1 . Plant Simulation uses it, when the Conveying Direction is lateral right or lateral left . Plant Simulation shows the absolute position of the booking point in parentheses.

When you are modeling conveyor systems, the booking point oftentimes represents the center of gravity of the part. Once the booking point, i.e., the center of gravity of the part, has transferred onto a conveyor, the part starts moving with the Speed you set for this conveyor.

<!-- image -->

By default, each MU has a booking point which Plant Simulation uses when it shows the MU on the material flow objects during the simulation run. The MUs require a booking point, as a long MU can be located on more than one length-oriented object at the same time.

Plant Simulation shows, for example, a Container moving along from Conveyor to Conveyor on the preceding Conveyor until its booking point moves on to the succeeding Conveyor .

If the part is not animated on the expected position on the object, check the position of the Booking Point .

**Compare this example:**

- Here Booking Point Length and Booking Point Width of the square part are located in its center at the position 0.5 . The part is animated at the center of the conveyor belt.

<!-- image -->

- Here Booking Point Width of the square part are located at the position 0.2 . The part is animated with an offset to the left in the direction of motion on the conveyor belt.

<!-- image -->

**Note**

When you assign a value to the booking point in a Method , Plant Simulation interprets this number as meters. Only when outputting it with the method print , it converts the value according to the settings you selected under File &gt; Model Settings/Preferences &gt; Units &gt; Length .

**SimTalk**

BookPntWRelative [SimTalk]

**BookPntLRelative [SimTalk]**

See also

Set and Link Animation Points and Lines

###### Booking Point Height [Container]

Type in at which Relative Height the Booking Point of the Container is located.

The booking point height is only important if you want to use the z-dimension of the Container in 3D . Type in a relative value between 0 and 1 . Plant Simulation shows the absolute position of the booking point in parentheses.

<!-- image -->

For the default Booking Point Height of 0 Plant Simulation places the part flush onto the object, for example onto the belt of a conveyor or on a station .

When you assign a value to the booking point in a Method , Plant Simulation interprets this number as meters. Only when outputting it with the method print , it converts the value according to the settings you selected under File &gt; Model Settings/Preferences &gt; Units &gt; Length .

SimTalk

BookPntHRelative [SimTalk]

**X-Dimension [Container]**

###### X-Dimension [Container]

Type the Dimension of the loading space of the Container along the x-axis into this text box.

The loading Capacity is the product of X-Dimension times Y-Dimension times Z-Dimension . The greatest allowed value is one million.

<!-- image -->

If you decrease the dimension of the loading space of the Container , make sure that no MUs are located on the storage places that will be deleted by this action! Either delete these MUs or move them to another storage place on the smaller loading space.

For loaded Containers , Plant Simulation distributes the animation points, onto which it places loaded MUs , according to the dimension that you typed in. Plant Simulation computes the distances between the Animation points as follows:

- The distance in the X-Direction (horizontal) is the length of the loaded object in pixels divided by the X-Dimension .
- The distance in the Y-Direction (vertical) is the width of the loaded object in pixels divided by the Y-Dimension .

**Note**

For computing the dimension in pixels, compare the Scaling Factor .

If either the distance in the X-Direction or in the Y-Direction is smaller than 4 pixels, Plant Simulation does not show any MUs at all but draws a pattern in a 2D Only model to signify that the object is not empty.

As long as the loading space is half empty, Plant Simulation shows a hatch pattern. If the loading space is more than half full, Plant Simulation shows a checker pattern.

<!-- image -->

**SimTalk**

XDim [SimTalk] - Container

YDim [SimTalk] - Container

ZDim [SimTalk] - Container

Capacity [SimTalk] - MUs

**Y-Dimension [Container]**

###### Y-Dimension [Container]

Type the Dimension of the loading space of the Container along the y-axis into this text box.

The loading Capacity is the product of X-Dimension times Y-Dimension times Z-Dimension . The greatest allowed value is one million.

If you decrease the dimension of the Container , make sure that no MUs are located on the storage places that will be deleted by this action! Either delete these MUs or move them to another storage place on the smaller loading space.

<!-- image -->

For loaded Containers , Plant Simulation distributes the animation points, onto which it places loaded MUs , according to the Dimension that you typed in. Plant Simulation computes the distances between the animation points as follows:

- The distance in the X-Direction (horizontal) is the length of the loaded object in pixels divided by the X-Dimension .
- The distance in the Y-Direction (vertical) is the width of the loaded object in pixels divided by the Y-Dimension .

**Note**

For computing the dimension in pixels, compare the Scaling Factor .

If either the distance in the X-Direction or in the Y-Direction is smaller than 4 pixels, Plant Simulation does not show any MUs at all but draws a pattern in a 2D Only model to signify that the object is not empty.

As long as the loading space is half empty, Plant Simulation shows a hatch pattern. If the loading space is more than half full, Plant Simulation shows a checker pattern.

<!-- image -->

**SimTalk**

YDim [SimTalk] - Container

XDim [SimTalk] - Container

ZDim [SimTalk] - Container

Capacity [SimTalk] - MUs [SimTalk]

**Z-Dimension [Container]**

###### Z-Dimension [Container]

Type the Dimension of the Container along the z-axis into this text box.

The Z-Dimension enables to stack parts on the Container . The loading Capacity is the product of XDimension times Y-Dimension times Z-Dimension . The greatest allowed value is one million.

<!-- image -->

If you decrease the dimension of the Container , make sure that no MUs are located on the storage places that will be deleted by this action! Either delete these MUs or move them to another storage place on the smaller loading space.

SimTalk

XDim [SimTalk] - Container

ZDim [SimTalk] - Container

Capacity [SimTalk] - MUs

See also

Unload Stacked Parts

Fill Whole Layer [check box]

MUHeightWithContent [SimTalk]

###### Workpiece Carrier [check box]

A Workpiece Carrier is a carrier object which transports the loaded part from processing station to processing station in your facility. It works if the Container has the Capacity 1 , i.e., if the X-Dimension , the Y-Dimension , and the Z-Dimension is 1 each.

<!-- image -->

In Plant Simulation a workpiece usually is an MU of type Part .

If the Container functions as a Workpiece Carrier , statistics does not collect the values for the carrier, but for the transported parts.

<!-- image -->

If you activate the check box, the Station , on which the Workpiece Carrier is located, does not consider the Container itself for setting-up and processing, but the loaded workpieces , i.e., the MUs . If the Workpiece Carrier is empty, the type of the Workpiece Carrier itself is evaluated.

<!-- image -->

The setting affects the following:

- All Times that evaluate the MU Type , such as Setup Times and Processing Times .

**Note**

An empty workpiece carrier exits the station immediately, without the station being set up and without the Workpiece Carrier being processed.

- The setting Exit &gt; Strategy &gt; MU Attribute of the material flow objects .
- The exit Strategy of the FlowControl .
- The Strategy of the Converter and of the strategy of the Turnplate .
- The setting Fluid Depends On &gt; MU Name of the DePortioner .
- The AssemblyStation where the main part can be a loaded part.
- Automatic Routing which you selected for the part.

For the following settings of the designated objects Plant Simulation uses the attributes or the name of the empty workpiece carrier .

- For the setting Exit &gt; Strategy &gt; MU Attribute of the material flow objects .
- For the settings Exit Behavior &gt; Strategy &gt; MU Attribute and MU Name of the FlowControl .
- For the settings Attributes &gt; Assembly Table &gt; MU Types and Depends on Main MU of the AssemblyStation .
- For the settings Attributes &gt; Strategy &gt; MU Attribute and MU Name of the Turnplate .

- For the settings Attributes &gt; Strategy &gt; MU Attribute and MU Name of the Converter .
- For the setting Fluid Depends On &gt; MU Name of the DePortioner .

SimTalk

**WorkpieceCarrierActive [SimTalk]**

See also

Work with Workpiece Carriers

X-Dimension [Container]

Y-Dimension [Container]

Z-Dimension [Container]

###### Fill Whole Layer [check box]

If the Z-Dimension of the Container is greater than 1, you can load it layer by layer by selecting Fill Whole Layer .

<!-- image -->

Plant Simulation then always starts a new layer and stacks the parts on the layer below.

<!-- image -->

By default, Fill Whole Layer is deactivated and Plant Simulation stacks the parts on each place up to its maximum Z-Dimension and then starts a new layer.

<!-- image -->

Fill Whole Layer also affects the read-only attribute Cont . It returns the next MU from the stack containing the highest number of MUs .

SimTalk FillWholeLayer [SimTalk] Cont [SimTalk] - material flow objects See also Loading a Container Layer by Layer

Z-Dimension [Container]

##### Tab Routing [Container]

Tab Routing [Container]

The settings for routing of the Container are described under the Tab Routing [Part, Container] .

See also

Automatic Routing [Transporter]

Reset Destination When at Destination [Part, Container]

Route Weighting Attribute - Transporter

Destination [Part, Container]

##### Tab Graphics [Container]

Select settings for vector graphics of the Container on the Tab Graphics .

##### Tab Product Statistics [MUs]

Tab Product Statistics [MUs]

The tab Product Statistics is described under the Tab Product Statistics .

<!-- image -->

**See also**

Product Statistics [all MUs]

Product Statistics Values

Methods for Accessing Statistics of the MUs

\_Read-Only Attributes for Accessing Statistics of the MUs

##### Tab Statistics

Tab Statistics [Container]

The tab Statistics provides the check box Resource Statistics .

It also shows a number of Resource Statistics Values of the Container on the tab itself.

###### Resource Statistics [Container]

To collect resource statistics data for the MU and to display the most important statistical data on the tab, select this check box.

<!-- image -->

**Note**

Plant Simulation does not continuously update statistical data displayed in an open window during a simulation run! Select View &gt; Refresh or press F5 .

**SimTalk**

ResStatOn [SimTalk] - MUs

**See also**

Resource Statistics Values

###### Resource Statistics Values

The tab Statistics shows these values.

| Item English        | Description                                                                                                                                                                                                                                                                                          | Read-only attribute                     | Item German       |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------|-------------------|
| Relative Empty      | Shows the portion of the statistics collection period during which the Container was Empty .                                                                                                                                                                                                         | StatEmptyPortion [SimTalk]              | Relativ leer      |
| Relative Occupation | Shows the capacity-based ratio of the time during which the Container was occupied, not paused and not Failed to the time the object was not Paused and not failed as a real number.                                                                                                                 | StatRelativeOccupat ion [SimTalk] - MUs | Relative Belegung |
| Contents            | Shows the number of MUs that are located on the Container .                                                                                                                                                                                                                                          | NumMU[SimTalk] - MUs                    | Inhalt            |
| Minimum Contents    | Shows the minimum number of MUs that was located on the Container .                                                                                                                                                                                                                                  | StatMinNumMU [SimTalk] - MUs            | Minimaler Inhalt  |
| Maximum Contents    | Shows the maximum number of MUs that was located on the Container .                                                                                                                                                                                                                                  | StatMaxNumMU [SimTalk] - MUs            | Maximaler Inhalt  |
| Entries             | Shows the number of MUs that entered the Container . When a MU enters the object, the object only counts the MU itself, not its contents: When a Container transporting several Parts enters the object, the number of entries increases by 1, not by the number of Parts located on the Container ! | StatNumIn [SimTalk] - MUs               | Eingänge          |
| Exits               | Shows the number of MUs that exited the Container . When a MU exits the object, the object only counts the MU itself, not its contents: When a Container transporting several Parts exits the object, the number of exits increases by 1, not by the number of Parts located on the Container .      | StatNumOut [SimTalk] - MUs              | Ausgänge          |

To view Resource Statistics of Moving Resources in the Statistics Report , click the object in the Frame , and press F6 ( Show Statistics Report ), or click Show Statistics Report on the Home ribbon tab.

You can also click the object in the Frame with the right mouse button and select Show Statistics Report on the context menu.

<!-- image -->

##### Tab Costs [MUs]

Tab Costs [MUs]

Type in the settings for costs, which accrue for the Part and for the Container on the tab Costs .

The inheritance check box also affects the other settings on the tab.

**Note**

Only the active material flow objects ( AngularConverter , AssemblyStation , Buffer , Converter , Conveyor , DismantleStation , ParallelStation , PickAndPlace -robot, PlaceBuffer , Sorter , Station , Store , Turnplate , Turntable ), and the moving objects Part and Container provide costs settings.

The CostAnalyzer runs the actual cost analysis.

See also

Tab Costs [material flow objects]

Simulate the Accrued Costs of the Machines

##### Tab User-defined [MUs]

Define your own attributes as described under the Tab User-defined .

This table lists, where the relative path starts for a user-defined attribute you define for a MU :

| Object                                | Path of a user-defined attribute created foraMU                                          |
|---------------------------------------|------------------------------------------------------------------------------------------|
| Object variable                       | Starts in the Frame in which the material flow object on which the MU stays, is located. |
| Method (current)                      | Starts in the Frame in which the material flow object on which the MU is located.        |
| Table with column of data type object | Starts with the material flow object on which the MU stays.                              |

**Navigate Menu**

##### Navigate Menu

The commands are described under the Navigate Menu .

##### View Menu

The View Menu provides commands to access its functions.

| Refresh [on View menu]                     | Position [MUs]                         |
|--------------------------------------------|----------------------------------------|
| Show Statistics Report [on View menu]      | Forward Blocking List                  |
| Show Attributes and Methods [on View menu] | Targets                                |
| Contents [MUs]                             | Route to Destination [Part, Container] |

##### Tools Menu

Tools Menu provides these menu commands:

The Tools Menu Edit Controls Edit Observers 3D

##### Help Menu

The commands are described under the Help Menu .

##### Methods of the Container

#### Methods of the Container

The Container provides the methods listed in the table of contents for accessing it.

The Container provides:

- The methods: findFreePlace [SimTalk] findPart [SimTalk] - Container getStackHeight [SimTalk] - MUs
- The Methods of All Mobile Objects .
- The Methods of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

An example of the Syntax line of the individual methods might look like this:

```simtalk
<MUPath >.create(Destination:any[, Position:length, CopyStatistics:boolean, PredecessorNumber:integer]) → object
```

- &lt;MU-Path&gt; designates a valid path to the MU (for example: MyTrack.Cont , ParallelStation.MU(1) , .MUs.Part:203 ). If you use the Method as an entrance or exit control, you can access the MU that triggered the control using the anonymous identifier @ (see Anonymous Identifiers ).
- &lt;MU-location&gt; designates a location- or length-oriented material flow object, a single processing place of an object with several places, or a length-oriented object including a position. You can enter the position as the additional parameter of data type length . If you do not enter a position, Plant Simulation uses 0.
- The signature of the method, consisting of the identifier and the data type of the parameter, is listed in parentheses. The expression (Parameter:string) , for example, designates a parameter of data type string . Instead of a constant value, you can also use a variable of the required type or a method that returns the required data type.

**Note**

Make sure to enter the parentheses for expressions within parentheses (…). Not entering them may lead to unexpected results and open the Debugger .

Optional parameters are listed within brackets. The expression [,Parameter:boolean] , for example, means that you can, but do not have to enter the boolean parameter.

If a parameter has a default value, the signature shows the default value after the parameter.

If the method has a return value, the signature shows its data type after the arrow -&gt;.

##### findPart [SimTalk] - Container

Finds the part with the specified name on the Container designated by &lt;MU-Path&gt; and returns it.

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
var o: object := Container.findPart("Part") // assigns for example .MUs.Part:1
```

#### Read-Only Attributes of the Container

Read-Only Attributes of the Container

The Container provides:

- The Read-Only Attributes of All MUs .
- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

<!-- image -->

**Attributes of the Container**

#### \_Attributes of the Container

The Container provides:

- The attributes listed in the table of contents to the left.
- The \_Attributes of All MUs .
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
.MUs.Container.Length := 3.5
print .MUs.Container.Length
posit := Station.Cont.XPos
```

**DistributeCosts [SimTalk]**

##### DistributeCosts [SimTalk]

Sets if the costs for the MU class designated by &lt;MU-Path&gt; are being distributed across the Container ( true ) or not ( false ).

Remarks

Note

You can only distribute costs for the Container .

Note

If Distribute Costs is active, the setting Material Costs per Piece is not evaluated for the Container

Type

Attribute

Syntax

&lt;MUPath &gt;.DistributeCosts:boolean

Assignment Value

You can assign a value of data type boolean .

Specify true to distribute the costs evenly across the storage places. In this case the Container works as a means of transport, for example a pallet.

Specify false to assign the costs to the Container itself. In this case the Container works as the main part.

Example

```simtalk
.MUs.MyPart.DistributeCosts := true
```

See also

Tab Costs [MUs] &gt; Distribute Costs [check box]

##### FillWholeLayer [SimTalk]

Sets if the Container designated by &lt;MU-Path&gt; always fills an entire layer if its Z-Dimension is greater than 1 ( true ) or not ( false ).

Type

Attribute

Syntax

```simtalk
<MUPath >.FillWholeLayer:boolean
```

Assignment Value

You can assign a value of data type boolean .

Specify false to fill each place to its maximum Z-Dimension before starting a new layer.

Example

```simtalk
.MUs.Container.XDim := 2 .MUs.Container.YDim := 2 .MUs.Container.ZDim := 2 .MUs.Container.FillWholeLayer := true
```

**See also**

Fill Whole Layer [check box]

Loading a Container Layer by Layer

##### WorkpieceCarrierActive [SimTalk]

Sets if the Container works as a Workpiece Carrier ( true ) or not ( false ).

Remarks

This only applies if the Container has the Capacity 1, i.e., if the X-Dimension the Y-Dimension , and the Z-Dimension is 1 each.

When you activate the attribute, the Container considers everywhere where the type of the MU is evaluated not the Workpiece Carrier itself but the loaded workpiece , i.e., the MU . If the Workpiece Carrier is empty, the type of the Workpiece Carrier itself is evaluated.

The setting affects the following:

- All times that evaluate the MU Type , such as Set-up Times and Processing Times .

**Note**

An empty workpiece carrier exits the station immediately, without the station being set up and without the Workpiece Carrier being processed.

- The setting Exit &gt; Strategy &gt; MU Attribute of the material flow objects .
- The Exit Strategy of the FlowControl .
- The Strategy of the Converter and of the Strategy of the Turnplate .
- The setting Fluid Depends On &gt; MU Name of the DePortioner .
- The AssemblyStation where the main part can be a loaded part.
- Automatic Routing which you selected for the part.

For the following settings of the designated objects Plant Simulation uses the attributes or the name of the empty workpiece carrier .

- For the setting Exit &gt; Strategy &gt; MU Attribute of the material flow objects .
- For the settings Exit Behavior &gt; Strategy &gt; MU Attribute and MU Name of the FlowControl .
- For the settings Attributes &gt; Assembly Table &gt; MU Types and Depends on Main MU of the AssemblyStation .
- For the settings Attributes &gt; Strategy &gt; MU Attribute and MU Name of the Turnplate .
- For the settings Attributes &gt; Strategy &gt; MU Attribute and MU Name of the Converter .
- For the setting Fluid Depends On &gt; MU Name of the DePortioner .

Type

Attribute

**Syntax**

```simtalk
<MUPath >.WorkpieceCarrierActive:boolean
```

**Assignment Value**

You can assign a value of data type boolean .

**Examples**

```simtalk
.MUs.Container.XDim := 1 .MUs.Container.YDim := 1 .MUs.Container.ZDim := 1 .MUs.Container.WorkpieceCarrierActive := true
.MUs.Container:1.XDim := 1 .MUs.Container:1.YDim := 1 .MUs.Container:1.ZDim := 1 .MUs.Container:1.WorkpieceCarrierActive := true
```

**See also**

Workpiece Carrier [check box]

Strategy [check box] - Converter

Fluid Depends On

X-Dimension [Container]

Y-Dimension [Container]

Z-Dimension [Container]

Automatic Routing [Transporter]

**XDim [SimTalk] - Container**

##### XDim [SimTalk] - Container

Sets the number of storage places on the loading space of the Container designated by &lt;MU-Path&gt; in the X-Dimension .

**Remarks**

The Capacity of the Container is XDim times YDim times ZDim . The greatest allowed value is one million.

If you decrease the dimension of the loading space of the Container , make sure that no MUs are located on the storage places that will be deleted by this action! Either delete these MUs or move them to another storage place on the smaller loading space.

For loaded Containers , Plant Simulation distributes the animation points, onto which it places loaded MUs , according to the Dimension that you entered. Plant Simulation computes the distances between the animation points as follows:

- The distance in the X-Direction (horizontal) is the length of the loaded object in pixels divided by the X-Dimension .
- The distance in the Y-Direction (vertical) is the width of the loaded object in pixels divided by the Y-Dimension .

**Note**

For computing the dimension in pixels, compare the Scaling Factor .

If either the distance in the X-Direction or in the Y-Direction is smaller than 4 pixels, Plant Simulation does not show any MUs at all but draws a pattern in a 2D Only model to signify that the object is not empty.

As long as the loading space is half empty, Plant Simulation shows a hatch pattern. If the loading space is more than half full, Plant Simulation shows a checker pattern.

<!-- image -->

Type

Attribute

**Syntax**

```simtalk
<MUPath >.XDim:integer
```

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type integer .

**Example**

```simtalk
.MUs.Container.XDim := 6 .MUs.Container.YDim := 6 .MUs.Container.ZDim := 3
```

**SimTalk**

Capacity [SimTalk] - MUs

YDim [SimTalk] - Container

ZDim [SimTalk] - Container

See also

X-Dimension [Container]

Scaling Factor [2D only]

**YDim [SimTalk] - Container**

##### YDim [SimTalk] - Container

Sets the number of storage places on the loading space of the Container designated by &lt;MU-Path&gt; in the Y-dimension .

Remarks

The Capacity of the Container is XDim times YDim times ZDim . The greatest allowed value is one million.

If you decrease the dimension of the loading space of the Container , make sure that no MUs are located on the storage places that will be deleted by this action! Either delete these MUs or move them to another storage place on the smaller loading space.

For loaded Containers , Plant Simulation distributes the animation points, onto which it places loaded MUs , according to the Dimension that you entered. Plant Simulation computes the distances between the animation points as follows:

- The distance in the X-Direction (horizontal) is the length of the loaded object in pixels divided by the X-Dimension .
- The distance in the Y-Direction (vertical) is the width of the loaded object in pixels divided by the Y-Dimension .

**Note**

For computing the dimension in pixels, compare the Scaling Factor .

If either the distance in the X-Direction or in the Y-Direction is smaller than 4 pixels, Plant Simulation does not show any MUs at all but draws a pattern in a 2D Only model to signify that the object is not empty.

As long as the loading space is half empty, Plant Simulation shows a hatch pattern. If the loading space is more than half full, Plant Simulation shows a checker pattern.

<!-- image -->

Type

Attribute

**Syntax**

```simtalk
<MUPath >.YDim:integer
```

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type integer .

**Example**

```simtalk
.MUs.Container.XDim := 6 .MUs.Container.YDim := 6 .MUs.Container.ZDim := 3
```

**SimTalk**

Capacity [SimTalk] - MUs

XDim [SimTalk] - Container

ZDim [SimTalk] - Container

See also

Y-Dimension [Container]

##### ZDim [SimTalk] - Container

ZDim [SimTalk] - Container

Sets the number of storage places on the loading space of the Container designated by &lt;MU-Path&gt; in the Z-Dimension .

Remarks

The Z-Dimension enables you to stack parts onto other parts.

The Capacity of the Container is XDim times YDim times ZDim . The greatest allowed value is one million.

If you decrease the dimension of the Container , make sure that no MUs are located on the storage places that will be deleted by this action! Either delete these MUs or move them to another storage place on the smaller loading space.

Type

Attribute

Syntax

```simtalk
<MUPath >.ZDim:integer
```

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type integer .

**Examples**

```simtalk
.MUs.Container.XDim := 6 .MUs.Container.YDim := 6 .MUs.Container.ZDim := 3
// Enumerates all MUs on the place (1,1)
var place := .MUs.Container:1[1,1]
for var i := 1 to place.NumMU
print place.MU(i)
next // Accesses the topmost MU of the stack: .MUs.Container:1[1,1].Cont // Accesses the second MU from the top on the place 1,2: .MUs.Container:1[1,2].MU(2)
```

**SimTalk**

MUHeightWithContent [SimTalk]

Z-Dimension [Container]

XDim [SimTalk] - Container

YDim [SimTalk] - Container

See also

Z-Dimension [Container]

**Transporter**

