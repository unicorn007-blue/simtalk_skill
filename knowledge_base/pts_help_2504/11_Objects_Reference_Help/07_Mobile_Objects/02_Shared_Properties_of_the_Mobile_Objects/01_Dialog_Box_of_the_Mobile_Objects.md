#### Dialog Box of the Mobile Objects

Dialog Box of the Mobile Objects

Double-click the icon of the mobile object that is located on one of the material flow objects in the Frame to open its dialog box.

Edit Simulation Properties

To change the settings of the class of the object, double-click it in the Class Library or on the tab Moving Units in the Toolbox . Here you can then type in or select the simulation properties to get the results you need. The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties :

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the 3D model and press the spacebar .

See also

Classes, Subclasses, and Instances

Inheritance [general description]

Conveying Direction [described]

**Number [of the MU]**

##### Number [of the MU]

The MU shows the unique identifying number of each instance of the MU class next to Number .

<!-- image -->

The Source assigns this number, when it creates the MU . You cannot change this number! The combination of MU class , Name and Number enables Plant Simulation to uniquely identify and access the instance of a mobile object, for example .UserObjects.Part1:191 .

**Note**

If your simulation model still contains parts after resetting the model, meaning that Plant Simulation does not start counting parts with 1, for example MUs.Part:1 , for a new simulation run, check if the model contains additional Frames with inserted EventControllers . Reset the EventControllers in these Frames as well.

**SimTalk**

GetNo [SimTalk]

See also

Reset Simulation [EventController]

##### Conveying Direction [described]

Sets the conveying direction of the Part and of the Container .

<!-- image -->

The conveying direction of the Part and the Container on the material flow object can either be:

- Forward . The part moves with its front in the insertion direction of the material flow.
- Lateral right . The part moves with its right-hand side in the insertion direction.
- Backward . The part is turned by 180° and moves backward against the insertion direction.
- Lateral left . The part moves with its left-hand side in the insertion direction.

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

For illustration purposes we use an icon, which looks like this in its normal state in 2D and 3D:

<!-- image -->

<!-- image -->

<!-- image -->

When changing the Conveying Direction the front position in insertion direction, i.e., the attribute FrontPos is retained. For this reason the length-oriented object has to provide enough room before and after the part for the new simulation-relevant Length . This means that no overlapping with other parts is allowed and that the part still has to be located in its entirety on the length-oriented object when changing the conveying direction. Before changing the conveying direction, the part also has to be located on the length-oriented object in its entirety.

**Note**

We advise against manually changing the Conveying Direction , but to let the Converter , AngularConverter or the Turntable do that.

**Note**

Changing the Conveying Direction also permanently affects the attribute ObjectAngle . Changing the attribute ObjectAngle does not change the Conveying Direction .

**Note**

3D also considers the conveying direction of the part for the side at which the MU is attached to an object. This means that, for example, the setting MU Side to Attach &gt; Left does not in each case attach the left side of the MU , from the view of the MU , to an animation line, but for the setting Conveying Direction &gt; 1 (lateral right) to the back.

**SimTalk**

ConveyingDirection [SimTalk]

changeDrivingDirection [SimTalk]

See also

insert [SimTalk] - MUs

**Stopped [MUs]**

##### Stopped [MUs]

To stop the MU on its way on the Conveyor , the Track , or the TwoLaneTrack , select this check box.

<!-- image -->

To make the MU continue on its way on the Conveyor , the Track , or the TwoLaneTrack , clear the check box.

You can, for example, use the check box Stopped to make a MU , which you want to load onto a pallet, stop and wait until the pallet arrives. When the pallet has arrived, you can then stop the MU so that the MU can be loaded onto the pallet.

Toggling the check box for a trailer, stops the entire tugger train or makes it continue on its way.

**Note**

If you select the check box Stopped , Plant Simulation stops a possible driving toward the target position. Plant Simulation does not call the Destination Control and sets the value of the attribute TargetPosition to the default value -1.

**Note**

You can only clear the check box Stopped of a MU on a Converter if the converting point has not been reached yet or if the exit for the MU was set and if the Converting Time expired.

Most often you will use the attribute Stopped with a Driving Control of the Transporter .

SimTalk

Stopped [SimTalk] - MUs

Tab Attributes

Tab Attributes

The tab Attributes of all MUs provides the settings listed in the table of contents to the left.

###### MU Length [general description]

Type in the Length of the mobile object.

The length-oriented objects Conveyor , Track , and TwoLaneTrack use the Length to determine how many MUs they can hold.

<!-- image -->

**SimTalk**

MULength [SimTalk]

**MU Width [general description]**

###### MU Width [general description]

Type in the Width of the mobile object.

The length-oriented objects Conveyor , Track , and TwoLaneTrack use the Width after the AngularConverter has changed the Conveying Direction to determine how many MUs they can hold.

<!-- image -->

**SimTalk**

MUWidth [SimTalk]

###### MU Height [general description]

Type in the Height of the moving object.

The height is only important for 3D as only 3D provides the z-dimension.

<!-- image -->

**SimTalk**

MUHeight [SimTalk]

MUHeightWithContent [SimTalk]

**Booking Point Length [general description]**

###### Booking Point Length [general description]

Type in the relative position of the Booking Point of the mobile object, which applies, when it is conveyed lengthwise .

The value that you type in is the distance from booking point 0, which is located at the front of the MU , in the direction of motion. Type in a relative value between 0 and 1 . Plant Simulation uses it, when the Conveying Direction is forward or backward .

Plant Simulation shows the absolute position of the booking point in parentheses. In our example below the Transporter has a length of 1.6 meters and its relative booking point is located at the position 0.5 . The absolute position of the booking point is located at the position 0.80 meters.

<!-- image -->

When you are modeling conveyor systems, the booking point oftentimes represents the center of gravity of the part. When the booking point, i.e., the center of gravity of the part, has transferred onto a conveyor, the part starts moving with the Speed you set for this conveyor.

By default, each mobile object has a booking point, as a long MU may be located on more than one length-oriented object at the same time. Plant Simulation uses the booking point to determine on which material flow object it shows the MU when animating a simulation run. Plant Simulation shows, for example, a Transporter moving along from Track to Track on the preceding Track until its booking point moves on to the succeeding Track .

If the part is not animated on the expected position on the object, check the position of the Booking Point .

**Compare this example:**

- Here Booking Point Length and Booking Point Width of the square part are located in its center at the position 0.5 . The part is animated at the center of the conveyor belt.

<!-- image -->

- Here the Booking Point Width of the square part is located at the position 0.2 . The part is animated with an offset to the left in the direction of motion on the conveyor belt.

<!-- image -->

**Note**

If you assign a value to the booking point in a Method , Plant Simulation interprets this number as meters. Only when outputting it with the method print , it converts the value according to the settings you selected under File &gt; Model Settings/Preferences &gt; Units &gt; Length .

**SimTalk**

BookPntLRelative [SimTalk]

**See also Set and Link Animation Points and Lines**

Fix Animation Problems in 3D

###### Booking Point Width [general description]

Type in the relative position of the Booking Point of the mobile object when it is conveyed crosswise .

The value you type in is the relative distance from booking point 0, which is located at the right-hand side of the MU , in the direction of motion. Type in a relative value between 0 and 1 . Plant Simulation uses it, when the Conveying Direction is lateral right or lateral left . Plant Simulation shows the absolute position of the booking point in parentheses.

<!-- image -->

When you are modeling conveyor systems, the booking point oftentimes represents the center of gravity of the part. When the booking point, i.e., the center of gravity of the part, has transferred onto a conveyor, the part starts moving with the Speed you set for this conveyor.

By default, the mobile objects have a booking point, as a long MU may be located on more than one length-oriented object at the same time. Plant Simulation uses the booking point to determine on which material flow object it shows the MU when animating a simulation run. Plant Simulation shows, for example, a Transporter moving along from Track to Track on the preceding Track until its booking point moves on to the succeeding Track .

If the part is not animated on the expected position on the object, check the position of the Booking Point .

**Compare this example:**

- Here Booking Point Length and Booking Point Width of the square part are located in its center at the position 0.5 . The part is animated at the center of the conveyor belt.

<!-- image -->

- Here the Booking Point Width of the square part is located at the position 0.2 . The part is animated with an offset to the left in the direction of motion on the conveyor belt.

<!-- image -->

**Note**

If you assign a value to the booking point in a Method object, Plant Simulation interprets this number as meters. Only when outputting it with the method print , it converts the value according to the settings you selected under File &gt; Model Settings/Preferences &gt; Units &gt; Length .

**SimTalk**

BookPntWRelative [SimTalk]

**See also**

**Set and Link Animation Points and Lines**

Fix Animation Problems in 3D

###### Booking Point Height [general description]

Type in at which relative Height the Booking Point of the MU is located.

The booking point height is only important if you want to use the z-dimension of the MU in 3D . Type in a relative value between 0 and 1 . Plant Simulation shows the absolute position of the booking point in parentheses.

<!-- image -->

For the default Booking Point Height of 0 Plant Simulation places the part flush onto the object, for example onto the belt of a conveyor or on a station .

**Note**

If you assign a value to the booking point in a Method object, Plant Simulation interprets this number as meters. Only when outputting it with the method print , it converts the value according to the settings you selected under File &gt; Model Settings/Preferences &gt; Units &gt; Length .

**SimTalk**

BookPntHRelative [SimTalk]

See also

Set and Link Animation Points and Lines

MU Side to Attach

Fix Animation Problems in 3D

##### Tab Routing

Tab Routing [Part, Container]

The tab Routing of the Part and the Container provides the settings listed in the table of contents to the left.

The Transporter also offers the tab Routing . As opposed to Part and Container , which move to their destination on Conveyors , the Transporter drives on objects of type Track and TwoLaneTrack to its destination.

**Note**

The Part and the Container find their Destination along the fastest route.

The Transporter finds its Destination along the shortest route.

Show the Route of the Part and the Pallet

Drag the mouse over the Pallet to show its name, its current location, its destination, and the previous route in a Tooltip .

<!-- image -->

The command Route to Destination selects the objects that are part of the route to the destination in the Frame .

<!-- image -->

For two alternative routes of the same length the Tooltip of PartA:1 shows the current location of the part and its destination. Then it lists the material flow objects along the route up to the alternative objects. The

<!-- image -->

Rightwards Heavy Arrow shows the current location of the part within the route.

The South East Arrow and South West Arrow shows that the route splits up from here on, followed by additional objects denoted by dots arranged below each other. The destination terminates the route.

<!-- image -->

For two alternative routes of the same length the method getRoute only returns the unique start of the route and ends before the alternative objects, compare the example for the part.

```simtalk
var route :
object[] := .MUs.PartA:1.getRoute
print route // returns [*.Models.Model.Source, *.Models.Model.Conveyor1, *.Models.Model.Conveyor2b, *.Models.Model.Conveyor3]
```

###### Automatic Routing [Part, Container]

To make the Part/Container independently find the fastest route to its destination object along the direction of motion, select this check box.

<!-- image -->

<!-- image -->

The Part/Container looks for the fastest route to the destination via all types of Conveyors and Buffers which are connected with Connectors . If no such route exists, Stations (including ParallelStations, AssemblyStations, DismantleStations, and PickAndPlaceRobots ) and Sorters are also included in the search. The route can also include sub-Frames and surrounding Frames , as long as the routes are connected with Connectors .

If different routes exist, which all take the same time to reach the Destination , the Part/Container does not commit itself to a certain route. Instead, the Exit Strategy of the material flow object is used to determine the route to be taken when the alternative routes branch. All routes containing Stations are considered to be equal. You can change this by using a Route Weighting Attribute .

An Exit Control along the predicted route take precedence over Automatic Routing . Thus, the Part/ Container can deviate from the predicted route. (Naturally you can always transfer the MU onto any position on a Conveyor with a Method which would also lead to a detour.) In this case Plant Simulation automatically computes a new route from the current location of the Part/Container to the Destination . While Automatic Routing is deactivated the default exit behavior, i.e., the Exit Strategy , which you selected, applies.

**Note**

As long as the Part/Container follows the predicted route, the Exit Strategy of the covered Conveyors is irrelevant.

This also applies for the Strategy Method at the converting point of the Converter .

**Note**

When you click OK or Apply in the dialog of the Part/Container , Plant Simulation predicts the route anew. If you inserted or deleted Connectors before that, the Part/Container might now take a different route. In addition, Plant Simulation also reevaluates the Destination when you click OK or Apply . If you entered a relative path to the Destination and the Part/Container is located in a Sub-Frame , for example, the Part/Container will not find the Destination or the Destination might even reference a point to a different object.

**Note**

If Automatic Routing conveys Part/Container via Converters with connected Conveyors , Automatic Routing assumes that the Conveyors always convey parts in the forward direction.

**Note**

Plant Simulation considers the lengths of the Conveyors . An alternative route containing shorter/faster Conveyors will always be preferred.

The Transporter also provides automatic routing. The transporter-specific behavior is described under Automatic Routing .

SimTalk

AutomaticRouting [SimTalk] - Part, Container

DestinationWasReached [SimTalk]

getRouteLength [SimTalk] - Part, Container

getRoute [SimTalk] - Part, Container

HasRouteToDestination [SimTalk] - MUs

setRoute [SimTalk] - Part, Container

See also

Route to Destination [Part, Container]

Destination [Part, Container]

Video on YouTube

[https://youtu.be/KH\_zcasaNp0?si=YkWHXY0MyppXD0\_z](https://youtu.be/KH_zcasaNp0?si=YkWHXY0MyppXD0_z)

###### Reset Destination When at Destination [Part, Container]

To make the Part or the Container reset the Destination and the route to the destination, when Part or Container arrived at the Destination , select this check box.

The Destination is reset at the same point in time as the attribute DestinationWasReached , namely when entering the Destination .

If the Part or the Container arrived at the destination and if no new destination is set or if the destination is not reset, the Part / Container again tries to find a route to the same destination. This can be useful in certain exceptional cases, but will probably be not useful in most cases.

If the destination is a DataTable or a list object , the destination will only be reset if the last object contained in the DataTable or list object has been reached. In this case the DataTable will be processed once only, not cyclically.

If the check box is selected, the DataTable will be processed once only.

If the check box is cleared, the DataTable will be processed cyclically.

SimTalk

ResetDestinationWhenAtDestination [SimTalk] - MUs

See also

Destination [Part, Container]

DestinationWasReached [SimTalk]

###### Destination [Part, Container]

Click the ellipsis button and select the Destination Object to which the MU is being transported.

<!-- image -->

The MU can be transported using Automatic Routing via Conveyors to the Destination .

If a Worker carries the MU and if the Transport Importer of the object on which the MU is currently located, is active, the Worker carries the MU to the Destination . If the MU has a route to the destination, the Worker carries the MU to the next object on this route.

The MU automatically finds the destination object which you entered, using the destination lists of the objects of type Conveyor . If you activate Automatic Routing

<!-- image -->

, the MU will automatically find its Destination object. If a sensor, into which you entered this Destination object, is the Destination , can be reached on a shorter route than the destination object itself, then Automatic Routing directs the MU to this sensor .

**Note**

The Destination can also be an Interface or a Frame . If it is a Frame , the MU drives to the Interface which can be reached on the shortest route.

You can also enter a table or a list as the Destination . This list or table can be a DataList , a DataQueue , a DataStack , or a DataTable which you inserted into a Frame . It can also be a user-defined attribute or a Variable of data type table , list , queue , or stack . The list or the first column of the table has to be of data type object . The MU then covers all Destination Objects in the list or table one after the other.

- DataTable ( table ): Plant Simulation cyclically processes the DataTable .

The MU always heads for the Destination Object , which is located in the table row to which the attribute DestinationListRow of the MU points.

**Note**

In most cases the DataTable will only have a single column. You can also enter any data into additional columns though.

- DataList ( list ): Plant Simulation treats the DataList as a DataTable with one column.
- DataQueue or DataStack ( queue or stack ): The MU always moves to the first object in the DataQueue or the DataStack . As soon as the Destination is reached, Plant Simulation removes the first object from the list. The MU then moves to the new first object in the list.

**Note**

When the MU has reached a Destination , it immediately picks the next Destination from the list or table.

If the Destination was a sensor , Plant Simulation already determines the next Destination before the Sensor Control is called. To set the immediate next destination in the control, it does not suffice to change the list or table respectively, but you also have to reassign the attribute Destination of the MU afterwards.

The Transporter also provides the Destination . The transporter-specific behavior is described there.

SimTalk

Destination [SimTalk] - MUs

DestinationWasReached [SimTalk]

DestinationListRow [SimTalk]

See also

Create a Sensor [material flow objects] in the Step-by-Step Help

Sensors [general description]

Route to Destination [Part, Container]

Destination [text box] - Transporter

Destination [SimTalk] - Transporter

###### Route Weighting Attribute [Part, Container]

Type in the name of the attribute which is used for controlling the weighting of routes.

<!-- image -->

The value of the Route Weighting Attribute determines the name of a user-defined attribute of the objects along the route. The Time of the Conveyor or the AngularConverter or the Dwell Time of the Buffer are then multiplied with the value which you assigned to the user-defined attribute of the respective object. The user-defined attribute has to have the data type real .

If you assign a negative value to the user-defined attribute , this object is not used for automatic routing. For Conveyors which do not have a user-defined attribute with the name, that is defined by the Route Weighting Attribute , Plant Simulation uses the factor 1.0.

If the user-defined attribute is of data type time , then the Time or the Dwell Time of the object are irrelevant, as then only the time that is set in the user-defined attribute will be used. You can also create such an attribute for stations so that the station is used when searching for the fastest route. If you assign the time value -1 , the object is excluded from automatic routing.

If the user-defined attribute is of data type method , then the user-defined method is executed to compute a value of data type real or time when searching for the route. This is useful if you want to evaluate time usage of the object depending on the model state. Using methods might have detrimental effects on the runtime of the model.

**Note**

If you assign a value to the attribute RouteWeightingAttr , Plant Simulation automatically re-computes the Destination .

Tab Graphics

The Transporter also provides the Route Weighting Attribute . The transporter-specific behavior is described there.

SimTalk

RouteWeightingAttr [SimTalk] - Part, Container

Destination [SimTalk] - MUs

See also

Route Weighting Attribute - Transporter

RouteWeightingAttr [SimTalk] - Transporter

Video on YouTube

https://youtu.be/KH\_zcasaNp0?si=4RyHCax9FmufgugE&amp;t=323

Graphics [tab, MUs, 2D]

The tab Graphics of the Part , the Container , and the Transporter provides settings for displaying them as vector graphics in your simulation model.

With this setting Plant Simulation shows the graphics of the parts with the correct size and with the correct distance to each other while animating your simulation model.

Note

The tab Graphics is only available in a 2D Only model .

The default vector graphic of the Part looks like this , of the Container it looks like this , and of the Transporter it looks like this .

<!-- image -->

In addition, the Transporter provides the setting Direction of the Animation Line for the Loading Space Type [loading space] Track and Line .

<!-- image -->

For loaded Containers , Plant Simulation distributes the animation points, onto which it places loaded MUs , according to the X-Dimension [Container] and Y-Dimension [Container] that you typed in. The same applies for Transporters for which you activated the Type [loading space] &gt; Store and then typed in the X-Dimension [Transporter] and the Y-Dimension [Transporter] of the loading space.

Plant Simulation computes the distance between the animation points as follows:

- Distance in the X-Direction (horizontal) is the length in pixels of the loaded object divided by the X-Dimension .
- Distance in the Y-Direction (vertical) is the width in pixels of the loaded object divided by the YDimension .

**Note**

For determining the size in pixels, compare the Scaling Factor [2D only] .

If either the distance in the X-Direction or in the Y-Direction is smaller than 4 pixels, Plant Simulation does not show any MUs at all but draws a pattern in a 2D Only model to signify that the object is not empty.

As long as the loading space is half empty, Plant Simulation shows a hatch pattern. If the loading space is more than half full, Plant Simulation shows a checker pattern.

<!-- image -->

**Note**

To also show the graphic in 3D that corresponds to the vector graphic in 2D, select Scale Automatically on the tab Appearance of Objects and MUs in the dialog Edit 3D-Properties .

<!-- image -->

**See also**

**Appearance of Objects and MUs in 3D**

\_Attributes of Vector Graphics of the MUs

###### Vector Graphics Active

To activate vector graphics mode, select this check box, and click OK or Apply .

<!-- image -->

Then, Plant Simulation shows the graphics of the parts with the correct size and with the correct distance to each other while animating the simulation model.

The table below illustrates the difference between the vector graphic and the icon of the object.

<!-- image -->

**Note**

To also show the graphic in 3D that corresponds to the vector graphic in 2D, select Scale Automatically on the Tab Transformation in the dialog Edit 3D-Properties .

SimTalk

VectorgraphicsActive [SimTalk]

See also

LEDs and States of the Mobile Objects

States &gt; State Graphic

<!-- image -->

###### Color [MU]

Color [MU]

Select the Fill Color of the vector graphic of the mobile object.

<!-- image -->

The fill color fills the interior of the built-in vector graphic with the color that you select.

SimTalk

VectorgraphicsColor [SimTalk]

###### Border Color [vector graphic]

Select the border color of the vector graphic of the mobile object.

<!-- image -->

<!-- image -->

Plant Simulation surrounds the Fill Color with the Border Color in the Border Width that you select.

The Border Color also sets the color of the Direction Arrow .

SimTalk

VectorgraphicsBorderColor [SimTalk]

**Border Width**

###### Border Width

Type in the Border Width of the vector graphic of the mobile object.

Plant Simulation surrounds the fill color with the border width in the Border Color that you select.

A Border Width of 2 looks like this , a Border Width of 4 looks like this .

SimTalk

VectorgraphicsBorderWidth [SimTalk]

<!-- image -->

###### Show Direction Arrow

To show the Direction Arrow on the vector graphic of the mobile object to illustrate the conveying direction, select this check box.

The Border Color , which you select, also sets the width and the color of the direction arrow.

<!-- image -->

The graphic with the direction arrow looks like this . It looks like this without the direction arrow.

SimTalk

VectorgraphicsShowDirectionArrow [SimTalk]

###### Show State

Show State

To show the State of the mobile object as a colored border around its vector graphic, select this check box.

The states are yellow for blocked , red for failed , and blue for paused . The State Color overwrites the Border Color that you select.

SimTalk

VectorgraphicsShowState [SimTalk]

<!-- image -->

<!-- image -->

<!-- image -->

###### Direction of the Animation Line

Select the Direction of the Animation Line on the vector graphic of the Transporter : Lengthwise or Crosswise in relation to the direction of motion.

<!-- image -->

**Note**

This setting is only available for the load space Types &gt; Track and Line .

<!-- image -->

**SimTalk**

**VectorgraphicsAnilineDirection [SimTalk]**

See also

Transporter

Tab Product Statistics

Tab Product Statistics [MUs]

The tab Product Statistics provides the setting Product Statistics and shows Product Statistics Values on the tab itself.

To view Product Statistics of the MUs [statistics report] in the Statistics Report , click the object in the Frame , and press F6 ( Show Statistics Report ), or click Show Statistics Report on the Home ribbon tab.

###### Product Statistics [all MUs]

To collect statistics data for the MU during a simulation run, select this check box. The tab then shows the most important statistical data.

<!-- image -->

**Product Statistics Values**

###### Product Statistics Values

The tab Product Statistics shows these values.

| Item English                                     | Description                                                                                                                                                             | Read-only attribute                       | Item German                                       |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------|---------------------------------------------------|
| Located on a resource of type Production         | Shows the portion of the statistics collection period during which the MU was located on a material flow object of type Production .                                    | StatProductionT imePortion [SimTalk]      | Platziert auf einer Ressource des Typs Production |
| Being processed on a resource of type Production | Shows the portion of the statistics collection period during which the MU was located on a material flow object of type Production and was processed, compare Working . | StatProdWorkin gPortion [SimTalk] - MUs   | Arbeitend                                         |
| Being set-up on a resource of type Production    | Shows the portion of the statistics collection period during which the MU was located on a material flow object of type Production that was Setting-up for the MU .     | StatProdSetupP ortion [SimTalk] - MUs     | Rüstend                                           |
| Waiting on a resource of type Production         | Shows the portion of the statistics collection period during which the MU was located on a material flow object of type Production that was Waiting .                   | StatProdWaiting Portion [SimTalk] - MUs   | Wartend                                           |
| Stopped on a resource of type Production         | Shows the portion of the statistics collection period during which the MU was located on a material flow object of type Production that was stopped.                    | StatProdStoppe dPortion [SimTalk] - MUs   | Angehalten                                        |
| Failed on a resource of type Production          | Shows the portion of the statistics collection period during which the MU was located on a material flow object of type Production that was Failed .                    | StatProdFailPort ion [SimTalk] - MUs      | Gestört                                           |
| Paused on a resource of type Production          | Shows the portion of the statistics collection period during which the MU was located on a material flow object of type Production that was Paused .                    | StatProdPausing Portion [SimTalk] - MUs   | Pausiert                                          |
| Located on a resource of type Transport          | Shows the portion of the statistics collection period during which the MU was located on a material flow object of type Transport .                                     | StatTransportTi mePortion [SimTalk]       | Platziert auf einer Ressource des Typs Transport  |
| Being processed on a resource of type Transport  | Shows the portion of the statistics collection period during which the MU was located on a material flow object of type Transport and was processed, compare Working .  | StatTranspWorki ngPortion [SimTalk] - MUs | Arbeitend                                         |

| Item English                                  | Description                                                                                                                                                          | Read-only attribute                       | Item German                                     |
|-----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------|-------------------------------------------------|
| Being set-up on a resource of type Transport  | Shows the portion of the statistics collection period during which the MU was located on a material flow object of type Transport that was Setting-up for the MU .   | StatTranspSetup Portion [SimTalk] - MUs   | Rüstend                                         |
| Waiting on a resource of type Transport       | Shows the portion of the statistics collection period during which the part was located on a material flow object of type Transport that was Waiting .               | StatTranspWaiti ngPortion [SimTalk] - MUs | Wartend                                         |
| Stopped on a resource of type Transport       | Shows the portion of the statistics collection period during which the MU was located on a material flow object of type Transport that was stopped.                  | StatTranspStopp edPortion [SimTalk] - MUs | Angehalten                                      |
| Failed on a resource of type Transport        | Shows the portion of the statistics collection period during which the MU was located on a material flow object of type Transport that was Failed .                  | StatTranspWaiti ngPortion [SimTalk] - MUs | Gestört                                         |
| Paused on a resource of type Transport        | Shows the portion of the statistics collection period during which the MU was located on a material flow object of type Transport that was Paused .                  | StatTranspWaiti ngPortion [SimTalk] - MUs | Pausiert                                        |
| Located on a resource of type Storage         | Shows the portion of the statistics collection period during which the MU was located on a material flow object of type Storage .                                    | StatStorageTim ePortion [SimTalk]         | Platziert auf einer Ressource des Typs Lagerung |
| Being processed on a resource of type Storage | Shows the portion of the statistics collection period during which the MU was located on a material flow object of type Storage and was processed, compare Working . | StatStoreWorkin gPortion [SimTalk] - MUs  | Arbeitend                                       |
| Being set-up on a resource of type Storage    | Shows the portion of the statistics collection period during which the MU was located on a material flow object of type Storage that was Setting-up for the MU .     | StatStoreSetupP ortion [SimTalk] - MUs    | Rüstend                                         |
| Waiting on a resource of type Storage         | Shows the portion of the statistics collection period during which the MU was located on a material flow object of type Storage that was Waiting .                   | StatStoreWaitin gPortion [SimTalk] - MUs  | Wartend                                         |
| Stopped on a resource of type Storage         | Shows the portion of the statistics collection period during which the MU was located on a material flow object of type Storage that was stopped.                    | StatStoreStoppe dPortion [SimTalk] - MUs  | Angehalten                                      |

| Item English                         | Description                                                                                                                                                                                                                                             | Read-only attribute                      | Item German          |
|--------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------|----------------------|
| Failed on a resource of type Storage | Shows the portion of the statistics collection period during which the MU was located on a material flow object of type Storage that was Failed .                                                                                                       | StatStoreFailPor tion [SimTalk] - MUs    | Gestört              |
| Paused on a resource of type Storage | Shows the portion of the statistics collection period during which the MU was located on a material flow object of type Storage that was Paused .                                                                                                       | StatStorePausin gPortion [SimTalk] - MUs | Pausiert             |
| Amount                               | Shows how many MU instances of this class existed during the statistics collection period. Plant Simulation only counts those MUs whose product statistics was active during the simulation run. The MUs may be located in different Frame hierarchies. | StatCount [SimTalk]                      | Anzahl               |
| Deleted                              | Shows how many MU instances of this class were removed from the installation during the statistics collection period. Plant Simulation only counts those MUs whose product statistics was active during the simulation run.                             | StatDeleted [SimTalk] - MUs              | Gelöscht             |
| Average lifespan                     | Shows the average life-span of the MUs which were created and removed from the installation during the statistics collection period. Plant Simulation only counts those MUs whose product statistics was active during the simulation run.              | StatAvgLifeSpan [SimTalk] - MUs          | Mittlere Lebensdauer |

To view Product Statistics of the MUs [statistics report] in the Statistics Report , click the object in the Frame , and press F6 ( Show Statistics Report ), or click Show Statistics Report on the Home ribbon tab.

See also

Tab Product Statistics [MUs]

Product Statistics [all MUs]

Methods for Accessing Statistics of the MUs Tab Statistics Tab Statistics [Container, Transporter]

The objects Transporter and Container can load and transport other MUs , and thus collect resource statistics values.

See also

Resource Statistics [MUs]

**Resource Statistics [MUs]**

###### Resource Statistics [MUs]

To collect resource statistics data for the MU and to display the most important statistical data on the tab, select this check box.

The values displayed are described under Resource Statistics of the Container .

<!-- image -->

**Note**

Plant Simulation does not continuously update statistical data displayed in an open window during a simulation run! Select View &gt; Refresh or press F5 .

**SimTalk**

ResStatOn [SimTalk] - MUs

Tab Costs

Tab Costs [MUs]

Type in the settings for costs, which accrue for the Part and for the Container on the tab Costs .

The inheritance check box also affects the other settings on the tab.

**Note**

Only the active material flow objects ( AngularConverter , AssemblyStation , Buffer , Converter , Conveyor , DismantleStation , ParallelStation , PickAndPlace -robot, PlaceBuffer , Sorter , Station , Store , Turnplate , Turntable ), and the moving objects Part and Container provide costs settings.

The CostAnalyzer runs the actual cost analysis.

See also

Tab Costs [material flow objects]

Simulate the Accrued Costs of the Machines

Active [check box] - costs, MUs

To turn costs settings of the Part and the Container on, select this check box. To turn them off, clear the check box.

<!-- image -->

The inheritance check box also affects the other settings on the tab.

SimTalk

CostingActive [SimTalk] - MUs

###### Material Costs per Piece [text box]

Material Costs per Piece [text box]

Type in the Material Costs Per Piece .

Material costs accrue during the simulation when a new part enters the production process. Material costs encompass the purchasing price, raw material cost, etc.

SimTalk

MaterialCostsPerPiece [SimTalk]

<!-- image -->

<!-- image -->

###### Distribute Costs [check box]

To distribute the accrued costs evenly across the storage places of the Container , select this check box.

In this case the Container works as a means of transport, i.e., a pallet.

Clear the check box to assign the costs to the Container instead.

In this case the Container works as the main part.

**Note**

You can only distribute costs for the Container .

**Note**

When distribute costs is active, the setting Material Costs per Piece is not evaluated for the Container

SimTalk

DistributeCosts [SimTalk]

**Tab User-defined [MUs]**

##### Tab User-defined [MUs]

Define your own attributes as described under the Tab User-defined .

This table lists, where the relative path starts for a user-defined attribute you define for a MU :

| Object                                | Path of a user-defined attribute created foraMU                                          |
|---------------------------------------|------------------------------------------------------------------------------------------|
| Object variable                       | Starts in the Frame in which the material flow object on which the MU stays, is located. |
| Method (current)                      | Starts in the Frame in which the material flow object on which the MU is located.        |
| Table with column of data type object | Starts with the material flow object on which the MU stays.                              |

##### Navigate Menu

The commands are described under the Navigate Menu .

View Menu

##### View Menu

The View Menu provides commands to access its functions.

| Refresh [on View menu]                     | Position [MUs]                         |
|--------------------------------------------|----------------------------------------|
| Show Statistics Report [on View menu]      | Forward Blocking List                  |
| Show Attributes and Methods [on View menu] | Targets                                |
| Contents [MUs]                             | Route to Destination [Part, Container] |

**Note**

Not all mobile objects provide all of the listed commands.

**Contents [MUs]**

###### Contents [MUs]

Opens a table showing all MUs located on the object. The position of the MU on the table matches the position in the net of coordinates.

<!-- image -->

###### Position [MUs]

Opens a table with one or three columns. Column 1 shows the object on which the MU is located, column 2 shows the position of the front, column 3 shows the position of the rear of the MU .

<!-- image -->

Depending on its length, the MU may be located on several length-oriented material flow objectsConveyors or Tracks -at the same time. The command Position then lists all of the objects.

In the following example the Part stretches across three Conveyors . The Front of the Part is located on Conveyor5 at the position 3.25 meters. The Rear of the Part is located on the Conveyor3 at the position 2.75 meters.

<!-- image -->

At times the Part may not be entirely located on a length-oriented object, but its Front or Rear are literally up in the air. Compare the examples below:

The Source moves the Part along a Connector to the Conveyor . According to the default transfer behavior the Front of the Part is located at the position 0 on the Conveyor . The rest of the Part with the length of 0.5 hangs in the air. The minus sign in the second row in the example below indicates that this length hangs in the air.

<!-- image -->

In this example the Part is moved according to the Exit Control with the method move to the position 4 meters starting at the entrance of the Conveyor . The Front of the Part is located at the position 4 on the Conveyor . The rest of the Part with the length of 0.5 hangs in the air. As the Conveyor moves forward, the Rear of the Part , which hangs in the air, is located to the left of the insertion position of 4 meters.

**Position [MUs]**

<!-- image -->

In this example the Part is moved according to the Exit Control with the method move onto a Conveyor that moves backward to the position 0 meters starting from the entrance of the Conveyor . The Rear of the Part is located at the position 0 the Conveyor . The Front and the rest of the Part with the length of 0.5 hangs in the air. As the Conveyor moves backward, the Front of the Part , which hangs in the air, is located to the right of the insertion position of 0 meters.

<!-- image -->

In this example the Part is moved according to the Exit Control with the method move onto a Conveyor that moves backward to the position 4 meters starting from the entrance of the Conveyor . The Rear of the Part is located at the position 4 of the Conveyor . The Front and the rest of the Part with the length of 0.5 hang in the air. As the Conveyor moves backward, the Front of the Part , which hangs in the air, is located to the right of the insertion position of 4 meters.

<!-- image -->

**SimTalk**

positionList [SimTalk] - MUs

###### Targets

Opens a table which shows all objects in whose Blocking List the part is entered.

<!-- image -->

###### Route to Destination [Part, Container]

Selects all Conveyors along the predicted route in the Frame on which the Container/Part moves toward its destination in the Frame .

<!-- image -->

If the command is deactivated, the Container/Part did not find a route to the destination.

SimTalk

getRouteLength [SimTalk] - Part, Container

getRoute [SimTalk] - Part, Container

HasRouteToDestination [SimTalk] - MUs

setRoute [SimTalk] - Part, Container

Tools Menu

Tools Menu [MUs]

The Tools Menu provides these menu commands:

Edit Controls

###### Edit Observers

**3D**

**Calculate Dimensions from 3D**

**Edit Controls [MUs]**

###### Edit Controls [MUs]

Opens a dialog in which you can select controls, which Plant Simulation activates for the action you want to execute.

All MUs provide the Controls , described under Edit Controls .

**Note**

To open the dialog of the object, whose name you entered into the text box, press F2 .

**See also**

| Constructor Control   | Plausibility Control   |
|-----------------------|------------------------|
| Destructor Control    | Rename Control         |
| Select Control        | Relabel Control        |
| Open Control          | Change Path Control    |
| Drag-and-Drop Control | Move to Folder Control |

**Compare**

Select Object [for controls]

Edit Controls [class library]

Edit Controls [material flow objects]

Edit Controls [Home ribbon]

###### Calculate Dimensions from 3D

Calculates the dimensions of the 3D graphic of the MU and enters them into the dialog of the MU .

See also

Adjust Graphics to MU Size

\_3D.calculateMUDimensions [SimTalk]

**Help Menu**

##### Help Menu

The commands are described under the Help Menu .

