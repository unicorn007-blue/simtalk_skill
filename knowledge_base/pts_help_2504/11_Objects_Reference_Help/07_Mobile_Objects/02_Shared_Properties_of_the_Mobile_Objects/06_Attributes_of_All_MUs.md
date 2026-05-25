#### Attributes of All MUs

\_Attributes of All MUs

You can change the settings of the moving objects in their dialogs or with SimTalk commands. The objects provide attributes for each setting, compare Attributes of All Objects and Attributes of the Material Flow Objects .

All mobile object provide:

- The attributes listed in the table of contents to the left.
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
.MUs.Transporter.Length := 4.5
print .MUs.Transporter.Length
posit := Station.Cont.XPos
```

##### AutomaticRouting [SimTalk] - Part, Container

Activates ( true ) or deactivates ( false ) automatic routing of the Part/Container designated by &lt;MUPath&gt;.

Remarks

To make the Part/Container independently find the fastest route to its Destination Object along the direction of motion, set the attribute to true .

The Part/Container looks for the fastest route to the destination via all types of Conveyors and Buffers which are connected with Connectors . If no such route exists, Stations (including ParallelStations, AssemblyStations, DismantleStations, and PickAndPlaceRobots ) and Sorters are also included in the search. The route can also include sub-Frames and surrounding Frames , as long as the routes are connected with Connectors .

If different routes exist, which all take the same time to reach the Destination , the Part/Container does not commit itself to a certain route. Instead, the Exit Strategy of the material flow object is used to determine the route to be taken when the alternative routes branch. All routes containing Stations are considered to be equal. You can change this by using a Route Weighting Attribute .

An Exit Control along the predicted route take precedence over Automatic Routing . Thus the Part/ Container can deviate from the predicted route. (Naturally you can always transfer the MU onto any position on a Conveyor with a Method which would also lead to a detour.) In this case Plant Simulation automatically computes a new route from the current location of the Part/Container to the Destination . While Automatic Routing is deactivated the default exit behavior, i.e., the Exit Strategy , which you selected, applies.

**Note**

As long as the Part/Container follows the predicted route, the Exit Strategy of the covered Conveyors is irrelevant.

This also applies for the Strategy Method at the converting point of the Converter .

**Note**

When you click OK or Apply in the dialog of the Part/Container , Plant Simulation predicts the route anew. If you inserted or deleted Connectors before that, the Part/Container might now take a different route. In addition, Plant Simulation also reevaluates the Destination when you click OK or Apply . If you entered a relative path to the Destination and the Part/Container is located in a Sub-Frame , for example, the Part/Container will not find the Destination or the Destination might even reference a point to a different object.

**Note**

If Automatic Routing conveys Part/Container via Converters with connected Conveyors , Automatic Routing assumes that the Conveyors always convey parts in the forward direction.

**Note**

Plant Simulation considers the lengths of the Conveyors . An alternative route containing shorter/faster Conveyors will always be preferred.

Type

Attribute

Syntax

&lt;MUPath &gt;.AutomaticRouting:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.MUs.MyPart.AutomaticRouting := true
```

SimTalk

DestinationWasReached [SimTalk]

See also

Automatic Routing [Part, Container]

Automatic Routing [Transporter]

AutomaticRouting [SimTalk] - Transporter

Route Weighting Attribute [Part, Container]

Destination [Part, Container]

Strategy Method [Converter]

**BookPntHRelative [SimTalk]**

##### BookPntHRelative [SimTalk]

Sets the relative position of the booking point of the MU designated by &lt;MU-Path&gt; in the Z-Dimension.

Remarks

You can specify a value between 0 and 1 .

**Note**

A long MU may be located on several length-oriented objects at the same time!

Type

Attribute

Syntax

```simtalk
<MUPath >.BookPntHRelative:real
```

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type real .

Example

```simtalk
.MUs.Transporter.MULength := 4.5          // meters .MUs.Transporter.BookPntHRelative := 0.1  // meters
```

SimTalk

BookPntLRelative [SimTalk]

BookPntWRelative [SimTalk]

See also

Booking Point Height [general description]

##### BookPntLRelative [SimTalk]

Sets the relative position of the booking point of the MU designated by &lt;MU-Path&gt; in the X-Dimension.

**Remarks**

**Note**

A long MU may be located on several length-oriented objects at the same time!

Plant Simulation uses BookPntLRelative , when the Conveying Direction is forward or backward . You can specify a value between 0 and 1 .

<!-- image -->

If the part is not animated on the expected position on the object, check the position of the booking point . Compare this example:

- Here Booking Point Length and Booking Point Width of the square part are located in its center at the position 0.5 . The part is animated at the center of the conveyor belt.

<!-- image -->

- Here the Booking Point Width of the square part is located at the position 0.2 . The part is animated with an offset to the left in the direction of motion on the conveyor belt.

<!-- image -->

**Note**

If you assign a value to the booking point in a Method , Plant Simulation interprets this number as meters. Only when outputting it with the method print , it converts the value according to the settings you selected under File &gt; Model Settings/Preferences &gt; Units &gt; Length .

Type

Attribute

**Syntax**

```simtalk
<MUPath >.BookPntLRelative:real
```

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type real .

Example

```simtalk
.MUs.Container.MULength := 4.5            // meters .MUs.Transporter.BookPntLRelative := 0.5  // percent
```

**SimTalk**

Booking Point Length [general description]

BookPntHRelative [SimTalk]

BookPntWRelative [SimTalk]

See also

Conveying Direction [described]

**BookPntWRelative [SimTalk]**

##### BookPntWRelative [SimTalk]

Sets the relative position of the booking point of the MU designated by &lt;MU-Path&gt; in the Y-Dimension.

**Remarks**

Plant Simulation uses BookPntWRelative , when the Conveying Direction is lateral right or lateral left . You can specify a value between 0 and 1 .

**Note**

A long MU may be located on several length-oriented objects at the same time!

<!-- image -->

If the part is not animated on the expected position on the object, check the position of the booking point . Compare this example:

- Here Booking Point Length and Booking Point Width of the square part are located in its center at the position 0.5 . The part is animated at the center of the conveyor belt.

<!-- image -->

- Here the Booking Point Width of the square part is located at the position 0.2 . The part is animated with an offset to the left in the direction of motion on the conveyor belt.

<!-- image -->

**Note**

If you assign a value to the booking point in a Method , Plant Simulation interprets this number as meters. Only when outputting it with the method print , it converts the value according to the settings you selected under File &gt; Model Settings/Preferences &gt; Units &gt; Length .

Type

Attribute

**Syntax**

```simtalk
<MUPath >.BookPntWRelative:real
```

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type length .

Example

```simtalk
.MUs.Part.MUWidth := 5             // meters .MUs.Part.BookPntWRelative := 0.5  // percent
```

SimTalk

BookPntHRelative [SimTalk]

BookPntLRelative [SimTalk]

See also

Booking Point Width [general description]

Conveying Direction [described]

##### ConveyingDirection [SimTalk]

Sets the conveying direction of the MU designated by &lt;MU-Path&gt;.

**Remarks**

When changing the Conveying Direction the front position in insertion direction, i.e., the attribute FrontPos is retained. For this reason the length-oriented object has to provide enough room before and after the part for the new simulation-relevant length . This means that no overlapping with other parts is allowed and that the part still has to be located in its entirety on the length-oriented object when changing the conveying direction. Before changing the conveying direction, the part also has to be located on the length-oriented object in its entirety.

<!-- image -->

| Conveying direction                                                                      | Looks like this   |
|------------------------------------------------------------------------------------------|-------------------|
| Forward . The part moves with its front in the insertion direction of the material flow. |                   |
| Lateral right . The part moves with its right-hand side in the insertion direction.      |                   |
| Backward . The part is turned 180° and moves backward against the insertion direction.   |                   |
| Lateral left . The part moves with its left-hand side in the insertion direction.        |                   |

**Note**

We advise against manually changing the Conveying Direction , but to let the Converter , AngularConverter or the Turntable do that.

**Note**

Changing the Conveying Direction also permanently affects the attribute ObjectAngle . Changing the ObjectAngle does not change the Conveying Direction .

**Note**

3D also considers the conveying direction of the part for the side at which the MU is attached to an object. This means that, for example, the setting MU Side to Attach &gt; Left does not in each case attach the left side of the MU , from the view of the MU , to an animation line, but for the setting Conveying Direction &gt; 1 (lateral right) to the back.

Type

Attribute

Syntax

```simtalk
<MUPath >.ConveyingDirection:integer
```

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type integer .

You can specify 0 for forward , 1 for lateral right , 2 for backward and 3 for lateral left .

Example

```simtalk
.MUs.Container.ConveyingDirection := 1
```

SimTalk

ObjectAngle [SimTalk] - object icons

FrontPos [SimTalk]

**changeDrivingDirection [SimTalk]**

See also

Conveying Direction [described]

MU Side to Attach

##### CostingActive [SimTalk] - MUs

CostingActive [SimTalk] - MUs

Sets if the costs settings for the Part/Container designated by &lt;MU-Path&gt; are active ( true ) or not ( false ).

Type

Attribute

Syntax

```simtalk
<MUPath >.CostingActive:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.MUs.MyPart.CostingActive := true
```

See also

Tab Costs [MUs] &gt; Active [check box] - costs, MUs Destination [SimTalk] - MUs Sets the name of the material flow object to which the MU designated by &lt;MU-Path&gt; will be transported.

Remarks

This object can be the material flow object itself or a Workplace attached to it.

The MU can be transported using Automatic Routing via all types of conveyors to the destination, if you did not define an Exit Control .

If a Worker carries the MU and if the transport importer of the object on which the MU is currently located, is active, the Worker carries the MU to the Destination . If the MU has a route to the destination, the Worker carries the MU to the next object on this route.

Attribute

Type

Attribute

Syntax

<MUPath >.Destination:path

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type path .

Examples

```simtalk
@.Destination:=.myfactory.station1
param SensorID: integer, Front: boolean, BookPos: boolean
var MU : object
@.Stopped  := true -- stopped
var Destination:object := Robot
MU := @.Cont
```

##### Destination [SimTalk] - MUs

```simtalk
MU.Destination := Drain
if not MU.move(Destination)
	stopuntil MU.Standort /= @ and not Destination.IsLoading
end
@.Stopped := false
```

SimTalk

DestinationWasReached [SimTalk]

Automatic Routing [Part, Container]

See also

Destination [Part, Container]

Destination [text box] - Transporter

##### DestinationListRow [SimTalk]

Sets the Destination to which the MU designated by &lt;MU-Path&gt; drives next when you assigned true to AutomaticRouting and when the attribute Destination points to a DataTable/DataList .

**Remarks**

This means that the MU drives to the object next,which is located in column 1 of the row with the number DestinationListRow . Once the MU has reached the destination, Plant Simulation automatically increments the value of DestinationListRow by 1. When the end of the column is reached, DestinationListRow is reset to the value 1.

**Note**

The value is incremented when the MU has reached the destination and the moving process is finished all the way. When you query the value of DestinationListRow while the MU is still moving to the destination, the value might not be incremented yet. This might, for example be the case, if the Processing Time will be determined in a formula which uses DestinationListRow .

If you query the DestinationListRow at a later point in time, the value has already been incremented. This might, for example, be the case if the Processing Time will be determined after the object is set up or in an Entrance Control with the activated setting Before Actions .

**Note**

For tugger trains this applies: If the first Transporter of the tugger train in the direction of motion has reached the Destination , Plant Simulation increments the value of DestinationListRow by 1. If the tugger train drives backward, the first Transporter in the direction of motion is the last Transporter .

Type

Attribute

Syntax

&lt;MUPath &gt;.DestinationListRow:integer

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type integer .

**Example**

```simtalk
@.DestinationListRow := 1
```

print@.Destination[1, @.DestinationListRow]

SimTalk

AutomaticRouting [SimTalk] - Transporter

Destination [SimTalk] - Transporter

See also

Destination [text box] - Transporter

Video on YouTube

[https://youtu.be/KH\_zcasaNp0?si=2srM4EDZ9ivD6zSa&amp;t=920](https://youtu.be/KH_zcasaNp0?si=2srM4EDZ9ivD6zSa&t=920)

##### DestinationWasReached [SimTalk]

Sets if the MU designated by &lt;MU-Path&gt; has reached its Destination Object ( true ) or not ( false ).

Remarks

DestinationWasReached retains the value true until you assign it a new destination or until you assign the value false to DestinationWasReached and thus reset it manually.

DestinationWasReached is set to true once the front of the MU has reached the entrance of its Destination .

DestinationWasReached is set to true, when a MU arrives at a sensor for which the Destination matches the Destination of the MU .

**Note**

Plant Simulation calls the Destination Control of Transporters only when the Transporter wants to exit the Destination .

For automated guided transport systems the attribute DestinationWasReached will be set to true when the end of the route has been reached. Plant Simulation sets DestinationWasReached to false when a new route is assigned.

You can use an Observer Method for all MU Types to start an action at this point in time.

Type

Attribute

Syntax

&lt;MUPath &gt;.DestinationWasReached:boolean

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

**Examples**

```simtalk
// Observer watching DestinationWasReached of a Container
param newValue: boolean
if newValue
	@.DestinationWasReached := false
	@.Cont.move(MyStore)  // unload the content of the Container
end
var AGV : object := AGVPool.Cont  // Transporter drives from Marker to Marker
AGV.setRoute([M1,M2,M3,M4])
waituntil AGV.DestinationWasReached
AGV.setRoute([M1,M2,M3,M4])
```

**SimTalk**

Destination [SimTalk] - MUs

Destination [SimTalk] - sensors

AutomaticRouting [SimTalk] - Part, Container

setRoute [SimTalk] - Transporter

See also

Destination [Part, Container]

Destination [text box] - Transporter

Destination [sensor]

Automatic Routing [Part, Container]

Destination Control

Video on YouTube

[https://youtu.be/PYXYutlaGOs?si=G\_5eRYYGFXUoUrSv&amp;t=36](https://youtu.be/PYXYutlaGOs?si=G_5eRYYGFXUoUrSv&t=36)

##### Length [SimTalk] - MUs

Sets the length of the MU designated by &lt;MU-Path&gt; according to the current ConveyingDirection .

Remarks

For the Conveying Direction forward or backward the length matches the MULength .

For the Conveying Direction lateral right or lateral left the length matches the MUWidth .

<!-- image -->

Only the length-oriented objects use the length. Plant Simulation interprets the length in meters. Only at output time, for example using the method print , does Plant Simulation convert the value to the unit you selected under File &gt; Model Settings/Preferences &gt; Units &gt; Length .

Type

Attribute

Syntax

<MUPath >.Length:length

Watchable

The attribute is watchable .

**Length [SimTalk] - MUs**

Assignment Value

You can assign a value of data type length .

**Note**

In SimTalk 2.0 you can specify the length units m , mm , km , cm , yd , ft , and in .

Type in the unit directly after the values, without a separating blank space, for example 10mps2 or 10.2mps2 .

You can enter the unit for fl oating point values and for integer values .

**Example**

```simtalk
.MUs.Transporter.Length := 2.5m
```

SimTalk

MULength [SimTalk]

MUWidth [SimTalk]

ConveyingDirection [SimTalk]

See also

MU Length [general description]

MU Width [general description]

##### MaterialCostsPerPiece [SimTalk]

Sets if the material costs per piece of the Part/Container designated by &lt;MU-Path&gt;.

Remarks

Material costs accrue during the simulation when a new part enters the production process. Material costs encompass the purchasing price, raw material cost, etc.

Type

Attribute

Syntax

```simtalk
<MUPath >.MaterialCostsPerPiece:real
```

**Assignment Value**

You can assign a value of data type real .

Example

```simtalk
.MUs.MyPart.MaterialCostsPerPiece := 10000
```

See also

Tab Costs [MUs] &gt; Material Costs per Piece [text box]

##### MUHeight [SimTalk]

MUHeight [SimTalk]

Sets the height of the MU designated by &lt;MU-Path&gt;.

Type

Attribute

Syntax

```simtalk
<MUPath >.MUHeight:length
```

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type length .

Example

```simtalk
.MUs.Part.MUHeight := 1 -- 1 meter
```

SimTalk

MUWidth [SimTalk]

See also

MU Height [general description]

##### MUHeightWithContent [SimTalk]

Overwrites the height of the MU designated by &lt;MU-Path&gt; when parts are stacked.

Remarks

If, for example, you are using a pallet/container with a height of 0.144 with a stacking number/zdimension of 3, whereas each element in the stack has a height of 0.3, you can set the attribute to 1.044 to stack the loaded pallets.

Type

Attribute

Syntax

```simtalk
<MUPath >.MUHeightWithContent:real
```

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type real .

Default Value

The default value is -1.0. This way the MUHeight is used for stacking.

**Examples**

```simtalk
.MUs.Container.MUHeightWithContent := 1.044 // stack loaded pallets
@.MUHeightWithContent = 0.84
Warehouse.WMS.placeIntoStock(@, @.Cont.Cont.Name, 12)
// This method calculates the total height of the container // including the parts loaded onto the container and // assigns the value to the attribute MUHeightWithContent
var pallet = Station.Cont
var stackHeight:real = 0.0 // Compute stacking height
for var x := 1 to pallet.XDim
```

**MUHeightWithContent [SimTalk]**

```simtalk
for var y := 1 to pallet.YDim stackHeight = max(stackHeight, pallet[x,y].getStackHeight)
next
next // Set total height of container MUHeightWithContent = pallet.MUHeight + stackHeight
```

**SimTalk**

MUHeight [SimTalk]

See also

MU Height [general description]

getStackHeight [SimTalk]

##### MULength [SimTalk]

Sets the length of the MU designated by &lt;MU-Path&gt;.

**Remarks**

Only the length-oriented objects use the MULength to determine how many MUs they can hold if the Conveying Direction is forward or backward .

<!-- image -->

Plant Simulation interprets the length in meters. Only at output time, for example with the method print , does Plant Simulation convert the value to the unit you selected under File &gt; Model Settings/Preferences &gt; Units &gt; Length .

Type

Attribute

Syntax

&lt;MUPath &gt;.MULength:length

Watchable

The attribute is watchable .

**MULength [SimTalk]**

Assignment Value

You can assign a value of data type length .

**Example**

```simtalk
.MUs.Part.MULength := 2.5 // 2.5 meters
```

SimTalk

MUWidth [SimTalk]

ConveyingDirection [SimTalk]

See also

MU Length [general description]

Booking Point Length [general description]

Length [SimTalk] - MUs

Conveying Direction [described]

##### MUWidth [SimTalk]

Sets the width of the MU designated by &lt;MU-Path&gt;.

**Remarks**

Only the length-oriented objects use the MUWidth to determine how many MUs they can hold if the ConveyingDirection is lateral right or lateral left .

<!-- image -->

Plant Simulation interprets the width in meters. Only at output time, for example with the method print , does Plant Simulation convert the value to the unit you selected under File &gt; Model Settings/Preferences &gt; Units &gt; Length .

Type

Attribute

Syntax

&lt;MUPath &gt;.MUWidth:length

**Watchable**

The attribute is watchable .

**MUWidth [SimTalk]**

Assignment Value

You can assign a value of data type length .

Example

.MUs.Container.MUWidth := 2.5 -- 2.5 meters

SimTalk

MULength [SimTalk]

ConveyingDirection [SimTalk]

See also

MU Width [general description]

Booking Point Width [general description]

Length [SimTalk] - MUs Name [SimTalk] - MUs Sets the name of the MU designated by &lt;MU-Path&gt;.

Remarks

You can type in a combination of letters, digits, and underscore (\_) characters, for example MyPart , MyPart1 , My\_Part\_1 . The name of an object cannot start with a digit, i.e., you cannot enter 1Part .

Type

Attribute

Syntax

```simtalk
<MUPath >.Name:string
```

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type string .

Example

```simtalk
.UserObjects.Part.Name := "MyPart"
```

See also

Name [text box] - 3D

**ProdStatOn [SimTalk]**

##### ProdStatOn [SimTalk]

Activates ( true ) or deactivates ( false ) the collection of Product Statistics for the MU class designated by &lt;MU-Path&gt;.

Type

Attribute

Syntax

```simtalk
<MUPath >.ProdStatOn:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MUs.Part.ProdStatOn := true
```

See also

Product Statistics [all MUs]

ResetDestinationWhenAtDestination [SimTalk] - MUs

Sets if the MU class designated by &lt;MU-Path&gt; resets the Destination Object and the route to the destination when a Part or a Container arrived at the destination ( true ) or not ( false ).

Remarks

The Destination is reset at the same point in time as the attribute DestinationWasReached , namely when entering the Destination .

If the Part or the Container arrived at the destination and if no new destination is set or if the destination is not reset, the Part / Container again tries to find a route to the same destination. This can be useful in certain exceptional cases, but will probably be not useful in most cases.

If the destination is a DataTable or a list object , the destination will only be reset if the last object contained in the DataTable or list object has been reached.

If the attribute is true , the DataTable will be processed once only.

If the attribute is false , the DataTable will be processed cyclically.

Type

Attribute

Syntax

&lt;MUPath &gt;.ResetDestinationWhenAtDestination:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.MUs.Part.ResetDestinationWhenAtDestination := true
```

SimTalk

setRoute [SimTalk] - Part, Container

DestinationWasReached [SimTalk]

See also Destination [SimTalk] - MUs Reset Destination When at Destination [Part, Container] Reset Destination When at Destination [Transporter]

##### ResStatOn [SimTalk] - MUs

Activates ( true ) or deactivates ( false ) the collection of Resource Statistics for the MU class designated by &lt;MU-Path&gt;.

Type

Attribute

Syntax

```simtalk
<MUPath >.ResStatOn:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.MUs.Transporter.ResStatOn := true
```

See also

Resource Statistics [MUs]

##### RouteWeightingAttr [SimTalk] - Part, Container

Is used for controlling the Route Weighting Attribute , when you activate Automatic Routing for the MU designated by &lt;MU-Path&gt;.

Remarks

The value of the Route Weighting Attribute determines the name of a user-defined attribute of the objects along the route. The Time of the Conveyor or the AngularConverter or the Dwell Time of the Buffer are then multiplied with the value which you assigned to the user-defined attribute of the respective object. The user-defined attribute has to have the data type real .

If you assign a negative value to the user-defined attribute , this object is not used for automatic routing. For Conveyors which do not have a user-defined attribute with the name, that is defined by Route Weighting Attribute , Plant Simulation uses the factor 1.0.

If the user-defined attribute is of data type time , then the Time or the Dwell Time of the object are irrelevant, as then only the time that is set in the user-defined attribute will be used. You can also create such an attribute for stations so that the station is used when searching for the fastest route. If you assign the time value -1 , the object is excluded from automatic routing.

If the user-defined attribute is of data type method , then the user-defined method is executed to compute a value of data type real or time when searching for the route. This is useful if you want to evaluate time usage of the object depending on the model state. Using methods might have detrimental effects on the runtime of the model.

**Note**

If you assign a value to the attribute RouteWeightingAttr , Plant Simulation automatically re-computes the Destination .

Type

Attribute

Syntax

&lt;MUPath &gt;.RouteWeightingAttr:string

Assignment Value

You can assign a value of data type string .

**Example**

```simtalk
.MUs.Par.RouteWeightingAttr :="MyWeightFactor"
MyConveyor.MyWeightFactor := 0.7 // preferably use this main route
```

SimTalk

RouteWeightingAttr [SimTalk] - Transporter

See also

Route Weighting Attribute [Part, Container]

Automatic Routing [Part, Container]

Route Weighting Attribute - Transporter

**Stopped [SimTalk] - MUs**

##### Stopped [SimTalk] - MUs

Stops ( true ) the MU designated by &lt;MU-Path&gt; or makes it continue on its way ( false ) on the Conveyor , the Track , or the TwoLaneTrack .

Remarks

Most often you will use the attribute Stopped with a Driving Control of the Transporter .

You can, for example, use the check box Stopped to make a MU , which you want to load onto a pallet, stop and wait until the pallet arrives. Once the pallet has arrived, you can then stop the MU so that the MU can be loaded onto the pallet.

When you change the state of the attribute Stopped for a trailer, this stops the entire tugger train or makes it continue on its way.

**Note**

If you select the check box Stopped , Plant Simulation stops a possible driving toward the target position. Plant Simulation does not call the Destination Control and sets the value of the attribute TargetPosition to the default value -1.

**Note**

You can only clear the check box Stopped of a MU on a Converter if the converting point has not been reached yet or if the exit for the MU was set and if the Converting Time expired.

Type

Attribute

Syntax

```simtalk
<MUPath >.Stopped:boolean
```

Assignment Value

You can assign a value of data type boolean .

Examples

```simtalk
param SensorID: integer, Front: boolean
@.Stopped := true
```

wait z_uniform(1,25,35)

```simtalk
@.Stopped := false
.MUs.Part:2.Stopped := true  // MU stops .MUs.Part:2.Stopped := false // MU continues
```

SimTalk

TargetPosition [SimTalk]

See also

Stopped [MUs]

Driving Control

Destination Control

Video on YouTube

[https://youtu.be/9g6Uou-8eMc?si=xHk\_vSci-dv8fxtf&amp;t=120](https://youtu.be/9g6Uou-8eMc?si=xHk_vSci-dv8fxtf&t=120)

**XPos [SimTalk] - MUs**

##### XPos [SimTalk] - MUs

Returns the x-coordinate of the MU designated by &lt;MU-Path&gt; in the Frame into which you inserted it.

Remarks

You cannot set the x-position of the MU , you can only get it!

We advise against using XPos as it only returns a meaningful value when the MUs actually is shown, i.e., when MU Animation is active and when the Frame window is open.

Type

Attribute

Syntax

```simtalk
<MUPath >.XPos:integer
```

Return Value

The return value has the data type integer .

Examples

```simtalk
var posit: integer
posit := Station.Cont.XPos
x
-> integer
x := .MUs.Part:1.XPos
```

SimTalk

Coordinate3D [SimTalk] - MUs

##### YPos [SimTalk] - MUs

Returns the y-coordinate of the MU designated by &lt;MU-Path&gt; in the Frame into which you inserted it.

Remarks

You cannot set the y-position of the MU , you can only get it!

We advise against using this attribute as it only returns a meaningful value when the MUs actually is shown, i.e., when MU Animation is active and when the Frame window is open.

Type

Attribute

Syntax

```simtalk
<MUPath >.YPos:integer
```

Return Value

The return value has the data type integer .

Examples

```simtalk
var posit: integer
posit := Station.Cont.YPos y
-> integer
y := .MUs.Part:1.YPos
```

SimTalk

Coordinate3D [SimTalk] - MUs

