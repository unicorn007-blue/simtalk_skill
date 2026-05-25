#### \_Methods of the Transporter

The Transporter provides:

- The methods listed in the table of contents to the left.
- The Methods of All Mobile Objects .
- The Methods of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

**Note**

The window Show Attributes and Methods only shows the attributes and methods pertaining to the selected type of loading space of the Transporter . If you select Track for example, the window only shows the attributes and methods pertaining to the loading space Track , not those pertaining to the loading space Store or Line .

<!-- image -->

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

An example of the Syntax line of the individual methods might look like this:

&lt;MUPath &gt;.create(Destination:any[, Position:length, CopyStatistics:boolean, PredecessorNumber:integer]) → object

- &lt;MU-Path&gt; designates a valid path to the MU (for example: MyTrack.Cont , ParallelStation.MU(1) , .MUs.Part:203 ). If you use the Method as an entrance or exit control, you can access the MU that triggered the control using the anonymous identifier @ (see Anonymous Identifiers ).
- &lt;MU-location&gt; designates a location- or length-oriented material flow object, a single processing place of an object with several places, or a length-oriented object including a position. You can enter the position as the additional parameter of data type length . If you do not enter a position, Plant Simulation uses 0.
- The signature of the method, consisting of the identifier and the data type of the parameter, is listed in parentheses. The expression (Parameter:string) , for example, designates a parameter of data type string . Instead of a constant value, you can also use a variable of the required type or a method that returns the required data type.

**Note**

Make sure to enter the parentheses for expressions within parentheses (…). Not entering them may lead to unexpected results and open the Debugger .

Optional parameters are listed within brackets. The expression [,Parameter:boolean] , for example, means that you can, but do not have to enter the boolean parameter.

If a parameter has a default value, the signature shows the default value after the parameter.

If the method has a return value, the signature shows its data type after the arrow -&gt;.

calcBrakingDistance [SimTalk] - Transporter

Computes the required distance to slow the Transporter designated by &lt;MU-Path&gt; down to a speed of 0 m/s, based on its Current Speed and its Deceleration .

Remarks

The braking distance is computed according to the formula s=1/2 v 2 /a.

Type

Method

Syntax

<MUPath >.calcBrakingDistance -> length

Return Value

The return value has the data type length .

Is 0m (zero meters) when Acceleration of the Transporter is deactivated.

Example

```simtalk
print .MUs.Transporter:1.calcBrakingDistance // might
return 0.5m
```

SimTalk

calcBrakingDistance [SimTalk] - general description

See also

Deceleration [SimTalk] - Transporter

Acceleration [SimTalk] - Transporter

Acceleration [check box] - Transporter

Current Speed [text box] - Transporter

##### changeDrivingDirection [SimTalk]

Changes the driving direction of the freely driving Transporter designated by &lt;MU-Path&gt; by the specified angle around the Z-Axis . It thus determines the side of the Transporter , which moves in the direction of its route.

Remarks

changeDrivingDirection only applies to freely driving Transporters , which are not moving and are not currently located on a route.

Type

Method

Syntax

```simtalk
<MUPath >.changeDrivingDirection(NumberOf90DegreesSteps:integer)
```

**Parameter**

The parameter NumberOf90DegreesSteps of data type integer sets the number of 90 degree steps by which the driving direction of the Transporter changes.

Compare this example: The value -1 or 3 changes the driving direction of the Transporter driving forward sideways to the left and the value 2 then changes the driving direction sideways to the right.

**Example**

```simtalk
@.changeDrivingDirection(-1)  -- now drive sideways to the left
@.Destination := NextMarker   -- toward NextMarker
```

**SimTalk**

**ConveyingDirection [SimTalk]**

##### drive [SimTalk]

drive [SimTalk]

Makes the AGV designated by &lt;MU-Path&gt; cover the designated distance.

Remarks

If you do not set an angle, the AGV drives on in the current driving direction.

If you set an angle, the AGV retains its orientation and rotates the travel route around the defined angle. In this case the orientation of the AGV does not match the driving direction.

After processing the method drive Plant Simulation calls the Destination Control and sets the attribute DestinationWasReached .

Type

Method

Syntax

```simtalk
<MUPath >.drive(Distance:length[, Angle:real])
```

**Parameters**

- The parameter Distance of data type length sets the distance which the AGV is to cover.
- The optional parameter Angle of data type real sets the angle around which the travel route is to be rotated.

**Examples**

```simtalk
print .MUs.Transporter:1.drive(5) // the Transporter covers the distance of 5 m
```

<!-- image -->

```simtalk
print .MUs.Transporter:1.drive(5, 45) // the Transporter covers the distance of 5 m and rotates the travel route around 45 °
```

SimTalk

DestinationWasReached [SimTalk]

getSafetyZoneContent [SimTalk]

See also

Marker

Destination Control

Fine-position an AGV

Video on YouTube

[https://youtu.be/PYXYutlaGOs?si=Rr5dw1\_bp6d2LFld&amp;t=1001](https://youtu.be/PYXYutlaGOs?si=Rr5dw1_bp6d2LFld&t=1001)

<!-- image -->

endFailure [SimTalk] - Transporter

Terminates the failure of the Transporter designated by &lt;MU-Path&gt;. It also sets the attribute Failed to false.

Type

Method

Syntax

<MUPath >.endFailure

Example

```simtalk
@.MUs.Transporter:4.endFailure
```

SimTalk

endFailureIn [SimTalk] - Transporter

startFailure [SimTalk] - Transporter

startFailureIn [SimTalk] - Transporter

See also

Failed [MUs] - state

##### endFailureIn [SimTalk] - Transporter

Terminates the failure of the Transporter designated by &lt;MU-Path&gt; after the time you specify.

Remarks

endFailureIn schedules a DisruptionEnd event. Once the event is processed, the failure ends and the attribute Failues is set to false. If no failure is active when the event is processed, the method has no effect.

**Note**

If the object does not have a failure profile yet, Plant Simulation creates a failure profile with an availability of 100 %.

Type

Method

Syntax

<MUPath >.endFailureIn(EndFailureIn:time)

**Parameter**

The parameter EndFailureIn of data type time designates the time span after which the failure ends. The time you enter has to be equal to or greater than 0.

**Example**

@.endFailureIn(str_to_time("10:00.00"))

SimTalk

endFailure [SimTalk] - Transporter

startFailure [SimTalk] - Transporter

startFailureIn [SimTalk] - Transporter

See also

Failed [MUs] - state endPause [SimTalk] - Transporter Immediately terminates the pause of the Transporter designated by &lt;MU-Path&gt; and sets the attribute Pause to false.

Type

Method

Syntax

&lt;MUPath &gt;.endPause

**Example**

```simtalk
.MUs.Transporter:11.endPause
```

**SimTalk**

endPauseIn [SimTalk] - Transporter

startPause [SimTalk] - Transporter

startPauseIn [SimTalk] - Transporter

See also

Pause [SimTalk] - Transporter

##### endPauseIn [SimTalk] - Transporter

Terminates the pause of the Transporter designated by &lt;MU-Path&gt; after the time you specify and sets the attribute Pause to false.

Type

Method

Syntax

<MUPath >.endPauseIn(EndPauseIn:time)

**Parameter**

The parameter EndPauseIn of data type time designates the time span after which the pause of the Transporter ends. The time you enter has to be equal to or greater than 0.

**Example**

```simtalk
MyTrack.MU(1).endPauseIn(str_to_time("10:0.0"))
```

**SimTalk**

endPause [SimTalk] - Transporter

startPause [SimTalk] - Transporter

startPauseIn [SimTalk] - Transporter

See also

Pause [SimTalk] - Transporter eraseFailureEvents [SimTalk] - Transporter Deletes the failure events of the Transporter designated by &lt;MU-Path&gt; from the list of scheduled events in the EventController .

Remarks

The events were entered by the methods startFailure , startFailureIn , endFailure , and endFailureIn .

Use eraseFailureEvents to terminate an existing failure and, at the same time, delete remove failure events, as these would end new failures too early.

Type

Method

Syntax

&lt;MUPath &gt;.eraseFailureEvents

**Example**

@.MUs.Cont.eraseFailureEvents

SimTalk

startFailure [SimTalk] - Transporter

startFailureIn [SimTalk] - Transporter

endFailureIn [SimTalk] - Transporter

endFailure [SimTalk] - Transporter

See also

List of Events

##### erasePauseEvents [SimTalk] - Transporter

Deletes the pause events of the Transporter designated by &lt;MU-Path&gt; from the list of scheduled events in the EventController .

Remarks

The events were entered by the methods startPause , startPauseIn , endPause , and endPauseIn .

Use erasePauseEvents to terminate an existing pause and, at the same time, delete unpause events, as these would end new pause events too early.

Type

Method

Syntax

&lt;MUPath &gt;.erasePauseEvents

**Example**

@.erasePauseEvents

SimTalk

startPause [SimTalk] - Transporter

startPauseIn [SimTalk] - Transporter

endPause [SimTalk] - Transporter

endPauseIn [SimTalk] - Transporter

See also

List of Events

##### getLane [SimTalk]

getLane [SimTalk]

Returns the path of the lane on which the Transporter designated by &lt;MU-Path&gt; is located on a TwoLaneTrack .

Type

Method

Syntax

```simtalk
<MUPath >.getLane([Position:length]) → string
```

**Parameter**

The optional parameter Position of data type length designates the position starting from the front of the Transporter .

Do not specify the parameter to use the position of the front end of the MU . This parameter is important if the Transporter stretches across several TwoLaneTracks .

Return Value

The return value has the data type string .

Example

```simtalk
print.MUs.Transporter:1.getLane
```

SimTalk

getLaneNo [SimTalk]

##### getLaneNo [SimTalk]

Returns the number of the lane on which the Transporter designated by &lt;MU-Path is located on a TwoLaneTrack .

Type

Method

Syntax

```simtalk
<MUPath >.getLaneNo([Position:length]) → integer
```

**Parameter**

The optional parameter Position of data type length designates the position, starting at the front of the Transporter .

Do not specify the parameter to use the position of the front. This parameter is important if the Transporter is located on several TwoLaneTracks at the same time.

Return Value

The return value has the data type integer .

1 stands for lane A, 2 for lane B.

Is always 1 if the Transporter is driving on a single-lane Track .

Example

```simtalk
print.MUs.Transporter:1.getLaneNo
```

SimTalk

getLane [SimTalk]

##### getRoute [SimTalk] - Transporter

getRoute [SimTalk] - Transporter

Returns the route of the Transporter designated by &lt;MU-path&gt; to its destination.

Remarks

For Transporters , which drive freely within the area, the method returns the route to the last Marker of this route.

Type

Method

Syntax

```simtalk
<MUPath >.getRoute → object[]
```

**Return Value**

The return value is an array of the data type object that contains the objects along the route.

**Example**

```simtalk
var route := .MUs.Transporter:1.getRoute
if isObject(route[1])
	print "First object: ", route[1].name
else
	print "First object is a two-lane track: ", route.asAny(1).~.Name
end
print "The length is: ", route[1].length
```

**SimTalk**

setRoute [SimTalk] - Transporter HasRouteToDestination [SimTalk] - Transporter asAny [SimTalk] getRouteRemaining [SimTalk] See also Route to Destination [Transporter]

**Destination [text box] - Transporter**

getRouteIntermediateDestination [SimTalk] - Transporter

Returns the next lane in the route to be covered by the Transporter designated by &lt;MU-Path&gt;. If the Transporter is located directly in front of the destination, the method returns the destination.

Remarks

**Note**

For the TwoLaneTrack the intermediate destination can be lane A or lane B . For the Track this is the only lane it provides, named pe . If you want to access the TwoLaneTrack/Track , you need to use Location or ~ .

getRouteIntermediateDestination applies if automatic routing is activated for the Transporter if you set its destination and if a route to the destination was found.

Type

Method

Syntax

&lt;MUPath &gt;.getRouteIntermediateDestination -&gt; any

**Return Value**

The return value has the data type any because the intermediate destinations are lanes, and the destination can be an object, a lane, or a storage place.

void if the Transporter did not find a route.

Example

print .UserObjects.MyTransporter:3.getRouteIntermediateDestination

SimTalk

getRoute [SimTalk] - Part, Container

HasRouteToDestination [SimTalk] - MUs

Automatic Routing [Part, Container]

**See also**

Destination [Part, Container]

Route to Destination [Part, Container]

**getRouteLength [SimTalk] - Transporter**

##### getRouteLength [SimTalk] - Transporter

Returns the length of the shortest route of the Transporter designated by &lt;MU-Path&gt; to its destination in the direction of motion.

**Remarks**

The destination can either be a material flow object, which can be reached directly via Connectors , or a destination, which you typed into a sensor.

**Note**

If you entered the Destination into a sensor, then it does not matter if the sensor is front or reartriggered. Plant Simulation always computes the length of the route from the side of the Transporter which is located in the front in the direction of motion, in relation to the sensor.

Type

Method

Syntax

```simtalk
<MUPath >.getRouteLength(DestinationObject:object[, ObjectsToDestination:table[], IgnoreRouteWeightingAttr:boolean:=false]) → length <MUPath >.getRouteLength(DestinationObject:object[, ObjectsToDestination:object[], IgnoreRouteWeightingAttr:boolean:=false]) → length
```

**Parameters**

**Note**

For a Transporter which is driving freely within the area you do not have to specify any parameters. In this case the return value determines the length of the entire route from the start of the route to the destination object.

- The parameter DestinationObject of data type object designates the destination object.
- The optional parameter ObjectsToDestination of data type table designates the name of a DataTable into which the Transporter enters the objects it would pass en-route to the destination.

The optional parameter ObjectsToDestination can also be an array of data type table into which the Transporter enters the objects it would pass en-route to the destination.

- The optional parameter IgnoreRouteWeightingAttr sets if the Route Weighting Attribute will be ignored ( true ) or if it will be considered ( false ).

The parameter IgnoreRouteWeightingAttr will also affect the return value.

If you set IgnoreRouteWeightingAttr to false, the computed route length is the sum of the weighted distances between the route objects.

If you set IgnoreRouteWeightingAttr to true, Plant Simulation returns the real, unweighted length of the route.

For freely driving Transporters the parameter also determines if Plant Simulation considers the curved segments of the computed route. If IgnoreRouteWeightingAttr is false, Plant Simulation returns the length of the straight segments between the Markers . If IgnoreRouteWeightingAttr is true, Plant Simulation returns the real length of the route including the curved segments.

**Default Value of the Parameter**

The default value is false.

Return Value

The return value has the data type length .

Is -1 if Plant Simulation did not find a route.

**Examples**

```simtalk
print .MUs.Transporter:1.getRouteLength(track6)
print .MUs.Transporter:1.getRouteLength(track6,objectsOnRoute)
```

**SimTalk**

setRoute [SimTalk] - Transporter

setRouteSegments [SimTalk]

See also

Route to Destination [Transporter]

Destination [text box] - Transporter

Route Weighting Attribute [Part, Container]

##### getSafetyZoneContent [SimTalk]

Returns the AGVs which are located in the specified safety zone of the AGV designated by &lt;MU-Path&gt;. Remarks

<!-- image -->

**Note**

Calling the method drive with a negative value for the parameter Distance denotes that the AGV drives backward .

The zones are attached in the direction of motion and only look forward from the Front or backward from the Rear of the AGV , not sideways! This even applies when you specify a non-zero value for the parameter Angle of the method drive .

Type

Method

Syntax

```simtalk
<MUPath >.getSafetyZoneContent(ZoneNumber:integer)
-> object[]
```

**Parameter**

The parameter ZoneNumber of data type integer designates the safety zone, 1 or 2 , whose content you would like to query.

Return Value

The return value is an array of data type object .

**Example**

```simtalk
var agv: object := AGVPool.getAssignedAGV(1)
if agv.getSafetyZoneContent(1).dim > 0
	agv.Speed := 0  -- emergency stop end
```

**SimTalk**

drive [SimTalk]

Distance [SimTalk]

SafetyZones [SimTalk]

SafetyZonesEmpty [SimTalk]

See also

Distance Control

Distance [text box] - distance control

**hitchFront [SimTalk]**

##### hitchFront [SimTalk]

Hitches the front of the active Transporter designated by &lt;MU-Path&gt; to the back of the Transporter driving directly in front of it if you do not specify the optional parameter.

Type

Method

Syntax

&lt;MUPath -Transporter-rear&gt;.hitchFront([Transporter:object])

**Parameter**

The optional parameter Transporter of data type object designates the Transporter to which it is to be hitched. You will use the parameter if the active Transporter is located at the end of a Track , which has several succeeding Tracks on which Transporters are located, which could be hitched up.

Do not specify the optional parameter to search for the Transporter to which it is to be hitched. If the Transporter is not located at the end of the Track , it takes the Transporter that drives directly in front of it. If it is located at the end of the Track , Plant Simulation searches among the successors for a Transporter that is to be hitched and uses the first match.

**Note**

Plant Simulation copies the values of the attributes Speed and Backwards of the tractor to the trailers hitched up to it.

**Note**

The active Transporter can either be one of the trailers, or the tractor, or a Transporter which is not part of a train yet.

<!-- image -->

**Note**

If you hitch up two tugger trains both of which have a tractor, Plant Simulation deactivates the attribute IsTractor of the train that is hitching up.

**Example**

// @ is the transporter which Collided // @.FrontMu references the transporter in front // hitch the current transporter to the transporter driving in front of it @.hitchFront

**See also**

unhitchFront [SimTalk]

hitchRear [SimTalk]

unhitchRear [SimTalk]

**hitchRear [SimTalk]**

##### hitchRear [SimTalk]

Hitches the rear of the active Transporter designated by &lt;MU-Path&gt; to the front of the Transporter that drives directly behind it if you do specify the optional parameter.

Type

Method

Syntax

&lt;MUPath -Transporter-front&gt;.hitchRear([Transporter:object])

**Parameter**

The optional parameter Transporter of data type object designates the Transporter to which it is to be hitched. You will use the parameter if the active Transporter is located at the start of a Track , which has several preceding Tracks on which Transporters are located, which could be hitched up.

Do not specify the optional parameter to search for the Transporter to which it is to be hitched. If the Transporter is not located at the start of the Track , it takes the Transporter that follows directly behind. If it is located at the start of the Track , Plant Simulation searches among the predecessors for a Transporter that is to be hitched and uses the first match.

**Note**

Plant Simulation copies the values of the attributes Speed and Backwards of the tractor to the trailers hitched up to it.

**Note**

The active Transporter can either be one of the trailers, or the tractor, or a Transporter which is not part of a train yet.

<!-- image -->

**Note**

If you hitch up two tugger trains both of which have a tractor, Plant Simulation deactivates the attribute IsTractor of the train that is hitching up.

**Example**

**@.hitchRear**

**SimTalk**

hitchFront [SimTalk]

unhitchRear [SimTalk]

unhitchFront [SimTalk]

**onLaneA [SimTalk]**

##### onLaneA [SimTalk]

Returns if the Transporter designated by &lt;MU-Path&gt; is located on lane A of a TwoLaneTrack (true) or not (false).

Type

Method

Syntax

```simtalk
<MUPath >.onLaneA([Position:length]) → boolean
```

**Parameter**

The optional parameter Position of data type length designates the position starting from the front of the Transporter .

Do not specify the parameter to use the reference point. This parameter is important when the Transporter stretches across several Tracks .

Return Value

The return value has the data type boolean .

Example

```simtalk
print.MUs.Transporter:1.onLaneA
```

SimTalk

onLaneB [SimTalk]

##### onLaneB [SimTalk]

Returns if the Transporter designated by &lt;MU-Path&gt; is located on lane B of a TwoLaneTrack (true) or not (false).

Type

Method

Syntax

```simtalk
<MUPath >.onLaneB([Position:length]) → boolean
```

**Parameter**

The optional parameter Position of data type length designates the position starting from the front of the Transporter .

Do not specify the parameter to use the reference point. This parameter is important when the Transporter stretches across several Tracks .

Return Value

The return value has the data type boolean .

Example

```simtalk
print .MUs.Transporter:1.onLaneB
```

SimTalk

onLaneA [SimTalk]

rotate [SimTalk] - Transporter

rotate [SimTalk] - Transporter

Rotates the AGV designated by &lt;MU-path&gt; with the defined Rotation Speed .

Remarks

After processing the method rotate Plant Simulation calls the Destination Control and sets the attribute DestinationWasReached .

Type

Method

Syntax

&lt;MUPath &gt;.rotate(RotationAngle:real)

Parameter

The parameter RotationAngle of data type real sets the rotation angle in degrees around which the AGV rotates.

Example

```simtalk
print .MUs.Transporter:1.rotate(25)
```

SimTalk

DestinationWasReached [SimTalk]

See also

Rotation Speed [text box]

Marker

Destination Control

Fine-position an AGV

Video on YouTube

[https://youtu.be/PYXYutlaGOs?si=Rr5dw1\_bp6d2LFld&amp;t=1001](https://youtu.be/PYXYutlaGOs?si=Rr5dw1_bp6d2LFld&t=1001)

rotateTowards [SimTalk] - Transporter

Rotates the Transporter designated by &lt;MU-Path&gt; in the direction of the specified coordinate.

Type

Method

Syntax

&lt;MUPath &gt;.rotateTowards(Coordinate:length[3]) -&gt; void

Parameter

The parameter Coordinate is an array of data type length with three values.

They designate the X-Position , the Y-Position , and the Z-Position of the coordinate.

Return Value

The return value is void.

Example

.MUs.Transporter:1.rotateTowards[15,15,45]

##### setRoute [SimTalk] - Transporter

Sends the Transporter designated by &lt;MU-Path&gt; on the specified objects along the route to its destination.

**Remarks**

- For Transporters driving on Tracks/TwoLaneTracks connected with Connectors to other simulation objects, this applies:

If the last object to be reached is not the destination object of the Transporter , Plant Simulation automatically adds the destination object to the route.

If the Transporter leaves the route specified in the table because an Exit Control moves the Transporter on to another successor, Automatic Routing takes effect again immediately afterward.

The method setRoute also accepts material flow objects other than objects of type Track . When assigning a route, which contains such objects with setRoute , then the Transporter passes these objects on its way to the destination. While automatically computing a route, Plant Simulation only takes Tracks/ TwoLaneTracks into consideration.

- For Transporters driving freely within the area, this applies:

The Transporter covers the Markers , Tracks , and its own AGVPool , which all are parts of the route.

**Note**

When you insert Markers into your model, make sure that the Markers are aligned . This prevents Plant Simulation from computing unnecessary roundings between the Markers . Misaligned Markers might occur if you inserted Markers into your model while Show Grid was off.

As opposed to the normal transfer behavior of the Transporter on Tracks , the Transporter remains booked on the Track until it has exited them all the way. For this reason Tracks , which succeed each other in the method setRoute , have to have a minimum distance of one Transporter Length . A minimum distance also applies between Tracks and Markers . Here it is determined by the Length and the Booking Point of the Transporter . If the Booking Point is located in the center of the Transporter , the minimum distance has to be half of the Transporter Length.

In addition, the normal Exit Behavior of the Track does not apply, i.e. no automatic routing to a destination and no exit strategies. The Transporter can only drive along Tracks that are explicitly given by setRoute .

The Destination Control is going to be called and the attribute DestinationWasReached is going to be set to true when the Transporter has reached the last Marker .

If a standing Transporter cannot drive to the first Marker using the specified DefaultCurveRadius , the Transporter rotates on the spot, if possible, and then drives in a straight line toward the Marker .

**Note**

This does not apply to tugger trains .

**Note**

A Transporter that is created in an AGVPool will always be controlled by this AGVPool during its entire lifetime.

A Transporter that is created by a Source or via SimTalk will never be controlled by an AGVPool .

Type

Method

Syntax

```simtalk
<MUPath >.setRoute(ObjectsToDestination:table) <MUPath >.setRoute(ObjectsToDestination:list) <MUPath >.setRoute(ObjectsToDestination:object[])
```

**Parameter**

The parameter ObjectsToDestination of data type table contains the objects along the route in the first column of data type object .

The parameter ObjectsToDestination of data type list contains the objects along the route in the column of data type object .

The parameter ObjectsToDestination as an array of data type object contains all objects along the route.

**Examples**

```simtalk
.MUs.Transporter:1.setRoute(objectsToRoute) // Transporter drives on Track
var AGV : object := AGVPool.Cont // Transporter drives from Marker to Marker
AGV.setRoute([M1,M2,M3,M4])
waituntil AGV.DestinationWasReached
AGV.setRoute([M1,M2,M3,M4]
```

**SimTalk**

DefaultCurveRadius [SimTalk]

DestinationWasReached [SimTalk]

getRoute [SimTalk] - Transporter setRouteFromCoordinates [SimTalk]

setRouteSegments [SimTalk]

HasRouteToDestination [SimTalk] - Transporter

DestinationWasReached [SimTalk]

DefaultCurveRadius [SimTalk]

See also

Automatic Routing [Transporter]

Destination Control

Route to Destination [Transporter]

Destination [text box] - Transporter

Curve Speed [text box]

AGVPool

Marker

Video on YouTube

[https://youtu.be/PYXYutlaGOs?si=G\_5eRYYGFXUoUrSv&amp;t=36](https://youtu.be/PYXYutlaGOs?si=G_5eRYYGFXUoUrSv&t=36)

setRouteFromCoordinates [SimTalk]

Sends the Transporter designated by &lt;MU-Path&gt; along the specified coordinates from its current location to the last specified coordinate.

Remarks

**Note**

When a Transporter drives between route coordinates, you cannot immediately use Automatic Routing by setting a new Destination . The reason for this behavior is that the Transporter is not driving toward a Marker , and therefore cannot determine a starting Marker for Automatic Routing . You first need to make the Transporter drive toward a specific Marker with the method setRoute . Afterward Automatic Routing will work again.

Type

Method

**Syntax**

```simtalk
<MUPath >.setRouteFromCoordinates(RouteCoordinates:table, DestinationFrame:object[, DestinationAngle:Real]) <MUPath >.setRouteFromCoordinates(RouteCoordinates:real[][3], DestinationFrame:object[, DestinationAngle:Real]) <MUPath >.setRouteFromCoordinates(RouteCoordinates:real[3], DestinationFrame:object[, DestinationAngle:Real])
```

**Parameters**

- The parameter RouteCoordinates can be of data type table . It has to have three columns of data type real . The columns contain the values for the x-coordinate, the y-coordinate, and the z-coordinate of the respective points on the route. Plant Simulation reads these values row by row. The AGV drives to each and every coordinate listed in the table one after the other.

<!-- image -->

The parameter RouteCoordinates can be a two-dimensional array of data type real . The array contains a sub-array with three floating-point numbers for each coordinate. The AGV drives to each and every passed coordinate one after the other.

The parameter RouteCoordinates can be an array of data type real with three values which specifies a single coordinate. The AGV only drives to the specified coordinate.

- The parameter DestinationFrame of data type object maps the route coordinate to the destination Frame and ensures the animation in the destination Frame .
- The optional parameter DestinationAngle of data type real sets the angle at which the Transporter approaches the destination coordinate in a directional manner.

If you do not specify the DestinationAngle , the Transporter arrives at the destination coordinate at the angle that results from the coordinates of the route.

**Note**

If you specify the destination angle, the behavior is the same as for the method setRoute in which the last Marker to be approached is a directional Marker in the list of Markers .

If you do not specify the destination angle, the behavior is the same as for the method setRoute in which the last Marker to be approached is an omnidirectional Marker in the list of Markers .

**Examples**

```simtalk
// computes the route of a worker from one workplace to the specified workplace // taking obstacles into account, returning coordinates along the way
var coords:any := workplace.getRouteCoordinates(frame1.workplace) agv:1.setRouteFromCoordinates(coords) // makes the AGV drive along the specified coordinates visually remaining in the current network, // arriving with an angle resulting from the calculated route
var coords:any := workplace.getRouteCoordinates(frame1.workplace) // computes the route of a worker taking obstacles into account and returning coordinates along the route agv:1.setRouteFromCoordinates(coords, frame1) // makes the AGV drive along the specified coordinates into the destination frame named "frame1"
var coords:any := workplace.getRouteCoordinates(frame1.workplace) // computes the route of a worker taking obstacles into account and returning coordinates along the route
coords.copyToTable(RouteTable) // writes the array of coordinates to the specified table agv:1.setRouteFromCoordinates(RouteTable, frame1) // makes the AGV drive along the coordinates of the specified table to the destination frame named "frame1"
var coord:real[3] := workplace.getWorldCoordinate() agv:1.setRouteFromCoordinates(coord, frame1) // makes the AGV drive to the specified single coordinate into the destination frame named "frame1"
```

**SimTalk**

getRoute [SimTalk] - Transporter

setRoute [SimTalk] - Transporter

setRouteSegments [SimTalk]

HasRouteToDestination [SimTalk] - Transporter

DestinationWasReached [SimTalk]

DefaultCurveRadius [SimTalk] See also Route to Destination [Transporter] Destination [text box] - Transporter AGVPool Marker

##### setRouteSegments [SimTalk]

Makes the Transporter designated by &lt;MU-Path&gt;, which is starting at its current location, cover the segments, defined in the table, one after the other.

Remarks

Once the Transporter has reached the end of the last route segment, Plant Simulation calls the Destination Control and sets the attribute DestinationWasReached to true.

**Note**

When a Transporter drives on route segments, you cannot immediately use Automatic Routing by setting a new Destination . The reason for this behavior is that the Transporter is not driving toward a Marker , and therefore cannot determine a starting Marker for Automatic Routing . You first need to make the Transporter drive toward a specific Marker with the method setRoute . Afterward Automatic Routing will work again.

Type

Method

Syntax

&lt;MU- Path &gt;.setRouteSegments(Route:table)

Parameter

The parameter Route of data type table contains the route segments.

The DataTable has four columns. Format it like this:

- Select the data type length and enter the Length of a straight segment into column 1.
- Select the data type real and enter an Angle into column 2.
- Select the data type length and enter the Radius of a curved segment into column 3.
- Select the data type speed and enter the Speed with which the Transporter drives on this segment into column 4.

If the Transporter is to rotate on the spot and if you want to use another Rotation Speed than the one that is set, then set the data type real for this column. Then enter the desired Rotation Speed into the cell of this column.

<!-- image -->

With the settings above you can define the following four segment types:

1. A straight segment. Here you have to enter the Length of the straight segment into column 1.
2. A straight segment deviating from the direction of motion. Here you have to enter the Length into column 1 and the Angle into column 2. This segment behaves like the method drive when you specify an Angle .
3. A curved segment. Here you have to enter the Curve Angle into column 2 and the Radius into column 3. A positive Curve Angle results in a clockwise curve, a negative Curve Angle results in a counter-clockwise curve.
4. A segment on which the Transporter rotates on the spot. Here you have to enter Rotation Angle into column 2. Leave the cell for the Radius empty or enter 0 . Enter the desired Rotation Speed into the cell of column 4 if it differs from the Rotation Speed that is set in the Transporter .

If you do not enter a Speed for the segment types 1 to 3, Plant Simulation uses the Speed of the Transporter .

For the segment type 4, on which the Transporter rotates on the spot, Plant Simulation uses the Rotation Speed of the Transporter .

**Note**

You can only set a Speed for a segment if you do not use a Distance Control for the Transporter .

**Examples**

```simtalk
var AGV : object := AGVPool.Cont
AGV.setRouteSegments(MyRouteSegmentsTable1)
waituntil AGV.DestinationWasReached
AGV.setRouteSegments(MyRouteSegmentsTable2)
var AGV : object := AGVPool.Cont
var route: table[length, real, length, speed]
```

route.create route.appendRow(2) route.appendRow(void, -90, 1, 0.2) route.appendRow(void,  90, 1, 0.2) route.appendRow(2) route.appendRow(void, -90) route.appendRow(2) route.appendRow(0.5, -90) agv.setRouteSegments(route) stopuntil agv.DestinationWasReached

**SimTalk**

drive [SimTalk]

DestinationWasReached [SimTalk]

setRoute [SimTalk] - Transporter

setRouteFromCoordinates [SimTalk]

See also

AGVPool

Destination Control

Distance Control

Route to Destination [Transporter]

Destination [text box] - Transporter

Speed [Transporter]

Cover a Route According to a Segments Table

Rotation Speed [text box]

**Video on YouTube**

[https://youtu.be/PYXYutlaGOs?si=L3QOwJNV1hLqHgII&amp;t=1225](https://youtu.be/PYXYutlaGOs?si=L3QOwJNV1hLqHgII&t=1225)

**setWorldPosition [SimTalk]**

##### setWorldPosition [SimTalk]

Sets the position in world coordinates for the AGV designated by &lt;MU-Path&gt;. This applies for an AGV that is located in the AGVPool or at the end of the route.

**Remarks**

Plant Simulation teleports the AGV to the new position without using up any time.

Type

Method

Syntax

```simtalk
<MUPath >.setWorldPosition(Coordinate:length[3], Angle:real[, Frame:object])
```

**Parameter**

- The parameter Coordinate is an array of data type length with three values. It designates the x-, y-, and z-components of the coordinate of the AGV in three-dimensional space.
- The parameter Angle of data type real sets the angle with which the AGV will be inserted.
- The optional parameter Frame of data type object sets the Frame in which the AGV will be inserted.
- If you do not specify this parameter, Plant Simulation inserts the AGV into the root Frame .

**Examples**

AGVPool.Cont.setWorldPosition([10,-10,0], 45)

```simtalk
// Position AGV on marker
var agv = AGVPool.Cont
agv.setWorldPosition(Marker.Coordinate3D, Marker._3D.Rotation[1])
agv.setRoute([Marker])
```

**SimTalk**

\_3D.getWorldCoordinate [SimTalk]

\_3D.getWorldRotation [SimTalk]

##### startFailure [SimTalk] - Transporter

Fails the Transporter designated by &lt;MU-Path&gt; immediately and sets the attribute Failed to true.

Type

Method

Syntax

<MUPath >.startFailure <MUPath >.startFailure([DurationOfFailure:time])

Parameter

The optional parameter DurationOfFailure of data type time designates the duration of the failure. The time you enter has to be equal to or greater than 0.

**Note**

If you call the method startFailure with the parameter and the Transporter does not have a failure profile yet, Plant Simulation creates a failure profile with an availability of 100 %. The method then schedules a StartFailure event.

**Example**

MyTrack.Transporter:1.startFailure MyTrack.Transporter:1.startFailure (str_to_time("1:30.12"))

**SimTalk**

endFailure [SimTalk] - Transporter endFailureIn [SimTalk] - Transporter startFailure [SimTalk] - Transporter startFailureIn [SimTalk] - Transporter See also Failed [SimTalk] - Transporter

startFailureIn [SimTalk] - Transporter

Fails the Transporter designated by &lt;MU-Path&gt; after the time span you enter. startFailureIn also sets the attribute Failed to false .

Remarks

If a failure is already active when the failure event is processed, startFailureIn does not have any effect.

Type

Method

Syntax

&lt;MUPath &gt;.startFailureIn(StartFailureIn:time)

**Parameter**

The parameter StartFailureIn of data type time designates the time span after which the failure starts. The time you specify has to be equal to or greater than 0.

**Note**

If the object does not have a failure profile yet, Plant Simulation creates a failure profile with an availability of 100%.

**Example**

MUs.Transporter:4.startFailureIn(10)

SimTalk

endFailure [SimTalk] - Transporter

endFailureIn [SimTalk] - Transporter

startFailure [SimTalk] - Transporter

See also

Failed [SimTalk] - Transporter

##### startPause [SimTalk] - Transporter

Pauses the Transporter designated by &lt;MU-Path&gt; immediately and sets the attribute Pause to true.

Type

Method

Syntax

```simtalk
<MUPath >.startPause[(TimeSpan:time)]
```

Parameter

The parameter TimeSpan of data type time sets the length of the pause in relation to the simulation time. The time you specify has to be equal to or greater than 0.

**Example**

```simtalk
@.startPause
@.startPause(60)
```

**SimTalk**

startPauseIn [SimTalk] - Transporter

endPause [SimTalk] - Transporter

startPauseIn [SimTalk] - Transporter

See also

Pause [SimTalk] - Transporter startPauseIn [SimTalk] - Transporter Pauses the Transporter designated by &lt;MU-Path&gt; after the time span you enter and sets the attribute Pause to true.

Type

Method

Syntax

```simtalk
<MUPath >.startPauseIn(StartPauseIn:time)
```

**Parameter**

The parameter StartPauseIn of data type time designates the time after which the Transporter will be paused. The time you specify has to be equal to or greater than 0.

**Example**

MyTrack.Transporter:1.startPauseIn(10) // in 10 seconds

SimTalk

startPause [SimTalk] - Transporter

endPause [SimTalk] - Transporter

startPauseIn [SimTalk] - Transporter

See also

Pause [SimTalk] - Transporter

##### unhitchFront [SimTalk]

Unhitches the front of the active Transporter designated by &lt;MU-Path&gt; from the rear of the Transporter that is currently hitched to it in the front.

**Remarks**

The active Transporter can either be one of the trailers or the tractor.

<!-- image -->

Type

Method

Syntax

<!-- formula-not-decoded -->

Return Value

The return value has the data type boolean .

true if unhitching was successful.

false if no Transporter is hitched in front of the active Transporter .

**Example**

.MUs.Transporter:4.unhitchFront

SimTalk

hitchFront [SimTalk]

hitchRear [SimTalk]

unhitchRear [SimTalk]

##### unhitchRear [SimTalk]

Unhitches the rear of the active Transporter designated by &lt;MU-Path&gt; from the front of Transporter that is currently hitched to it at the back.

**Remarks**

The active Transporter can either be one of the trailers or the tractor.

<!-- image -->

Type

Method

Syntax

&lt;MUPath -Transporter-rear&gt;.unhitchRear → boolean

Return Value

The return value has the data type boolean .

true if unhitching was successful.

false if no Transporter is hitched behind the active Transporter .

**Example**

.MUs.Transporter:4.unhitchRear

SimTalk

hitchFront [SimTalk]

hitchRear [SimTalk]

unhitchFront [SimTalk]

