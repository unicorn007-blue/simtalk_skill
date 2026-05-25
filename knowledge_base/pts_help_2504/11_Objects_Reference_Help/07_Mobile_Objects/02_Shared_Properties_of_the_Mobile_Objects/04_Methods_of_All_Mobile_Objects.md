#### Methods of All Mobile Objects

Methods of All Mobile Objects

All mobile objects provide:

- \_Methods for Creating and Locating MUs
- Methods for the State of the MU
- \_Methods for Accessing the Load of Container and Transporter
- \_Methods for the Route to the Destination
- Methods for Accessing Statistics of the MUs
- The Methods of the Material Flow Objects

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

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

**Methods for Creating and Locating MUs**

##### \_Methods for Creating and Locating MUs

The MUs provide the methods listed in the table of contents to the left for creating and locating them.

To view all of the methods , read-only attributes , and attributes of the mobile object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

###### create [SimTalk] - MUs

create [SimTalk] - MUs

Creates an instance of the MU class designated by &lt;MU-Path&gt;.

Remarks

**Note**

You cannot create a MU on the individual places of the Sorter .

You cannot create a MU on these objects with the method create : AngularConverter , AssemblyStation , Converter , DePortioner , PickAndPlace , Portioner , Turntable , and Turnplate .

create applies to MU classes and to MU instances. In the latter case, Plant Simulation creates a copy of the MU , including all of its attributes. No inheritance exists between the original MU and the copy.

A MU created on the point-oriented objects can exit the object immediately , without being processed.

A MU will be created on the first place available on the PlaceBuffer , provided you did not designate a specific processing place. No processing time is required for this processing place. If you want the material flow object to process the part, you can achieve this with the method outIn .

On length-oriented objects, Plant Simulation creates MUs with their front as close to the exit of the object as possible. If the available length does not suffice to receive the MU in its entirety, Plant Simulation attempts to place the remainder of the length onto the object with the designated predecessor number. If no predecessor exists, or if the predecessor is a point-oriented object, Plant Simulation inserts the MU so that the rest of the MU hangs in thin air, meaning that it is not located on the length-oriented object in its entirety. If not enough room is available, create fails. Creating a MU always fails if the capacity of the MU-location is exhausted.

You can also create or insert a MU at the beginning of a length-oriented object. Then a part of the MU hangs in thin air afterwards, i.e., is not located all the way on the length-oriented object.

Type

Method

Syntax

```simtalk
<MUPath >.create(Destination:any[, Position:length, CopyStatistics:boolean, PredecessorNumber:integer]) → object
```

**Parameters**

- The parameter Destination of data type any designates any material flow object or a processing place on any material flow object which can accommodate a MU-instance.

The Destination can be any material flow object or a processing place on a material flow object.

- The optional parameter Position of data type length designates the position where the MU will be created on a length-oriented object.
- The optional parameter CopyStatistics of data type boolean sets if statistics of the part is to be copied ( true ) or not ( false ). If statistics is copied, the created MU has the same life time as the original object after being created. If statistics is not copied, a new MU will be created which starts its life time from this point in time on.

If you do not specify the parameter, statistics is not copied (false).

Copying statistics is only possible if the method create is called for a MU instance.

- The optional parameter PredecessorNumber of data type integer sets the predecessor number if the MU does not completely fit on the length-oriented object. If you did not enter a predecessor number, Plant Simulation always uses the predecessor with the number 1 to place the remainder of the part. If the specified predecessor still does not provide enough room for completely placing the part, Plant Simulation again uses predecessor 1 of the designated predecessor.

**Return Value**

The return value has the data type object .

It is the produced MU .

VOID if it could not be produced.

**Note**

Any ConstructorCtrl methods you enter will also be executed.

**Examples**

```simtalk
// A Method to be called periodically by a Generator will create MUs of type // Part on the Station named Start. The variable named unsuccAttempts // counts how often MUs could not be created.
var item: object item := .MUs.Part.create(Start)
if item = VOID then // unsuccessful?
	unsuccAttempts := unsuccAttempts + 1
end
.Part.create(ParallelStation) .Part.create(Store[2,5]) .Part.create(Track,9.3)
Station1.Cont.create(Station2, 0, true)  // duplicates the MU that is located on Station1
```

SimTalk delete [SimTalk] - MUs outIn [SimTalk] - MUs Destination [SimTalk] - MUs ConstructorCtrl [SimTalk] See also Duplicate create [SimTalk] - MUs delete [SimTalk] - MUs Deletes the MU designated by &lt;MU-Path&gt;.

Remarks

You cannot access deleted MUs any longer and you cannot delete MUs in the Class Library with this method .

Note

Any DestructorCtrl methods you enter will also be executed.

Compare this example: Plant Simulation counts and deletes MUs at the end of the assembly line, as they are not needed any more. We entered the method as an Exit Control into the last object of the assembly line.

Type

Method

Syntax

&lt;MUPath &gt;.delete

Example

```simtalk
// the exit control is called when MUs leave the station
counter:= counter + 1 // counts
@.delete // and deletes the MUs afterwards, no further access on @
```

SimTalk

create [SimTalk] - MUs

DestructorCtrl [SimTalk]

getStoragePlace [SimTalk] - MUs

Returns the x-position and the y-position of the storage place on which the MU designated by &lt;MU-Path&gt; is booked.

Remarks

With the returned position of the MU , you can find out on which storage place within a Store a MU is located.

Type

Method

Syntax

```simtalk
<MUPath >.getStoragePlace(byRef x:integer, byRef y:integer)
```

**Parameters**

- The local variable x of data type integer , to which the value will be assigned, designates the x-position of the storage place within the Store .
- The local variable y of data type integer , to which the value will be assigned, designates the y-position of the storage place within the Store .

**Example**

```simtalk
var x,y: integer .MUs.Part:7.getStoragePlace(x,y)
print x," ",y
```

###### insert [SimTalk] - MUs

Places the MU designated by &lt;MU-Path&gt; all the way onto the designated destination object.

Remarks

For point-oriented objects the behavior is the same as for the methods move and transfer .

For length-oriented objects the MU also moves onto the designated destination object, provided it provides enough room. If the designated destination object does not provide enough room, Plant Simulation attempts to place the remainder of the MU onto the first predecessor. If there still is not enough room, Plant Simulation again uses the first predecessor, and so on. If no predecessor exists, or if the predecessor is a point-oriented object, Plant Simulation inserts the MU so that the rest of the MU hangs in thin air, meaning that it is not located on the length-oriented object in its entirety.

**Note**

When inserting the MU with the commands &lt;MU-Path&gt;.insert(DestinationObject:object) or &lt;MU-Path&gt;.insert(Successor:integer) failed, then Plant Simulation enters the MU into the Forward Blocking List of the destination object onto which it intended to move. Once the destination object is ready to accept the next MU , the destination object enters an Out event for all entries, i.e., for all MUs in the Forward Blocking List . Then the destination object deletes all entries from its Forward Blocking List .

If you enter a certain Position on the destination object specified with the parameter of data type length , it does not enter the MU into the Forward Blocking List , as Plant Simulation cannot watch at which point in time this position is available again.

**Note**

If you moved a MU before an Out -event was processed for this MU , for example in a sensor control, and if the MU could not be moved and was thus entered into the Blocking List of the destination object, the MU will not be removed from the blocking list of the destination object, when the object, on which the blocked MU is located, is failed/paused/stopped.

**Note**

If you would like the MU to be processed a second time, use the method outIn and set the parameter WorkOnFinishedPartAgain to true , instead of moving the MU onto itself.

**Note**

If you insert a part into the gap range at the entrance of a gap conveyor, this gap conveyor will no longer consider the gap condition until the part moved out of the gap range. This may cause parts to get stuck when they try to enter the gap conveyor during this time.

If you want to move a part via SimTalk onto a gap conveyor, use the method move .

**insert [SimTalk] - MUs**

Type

Method

Syntax

```simtalk
<MUPath >.insert([Destination:any, Position:length, ConveyingDirection:integer]) → boolean
```

**Parameters**

- The optional parameter Destination of data type any designates the destination object.

Instead, you can also enter the number of the Connector which is located in the direction of motion. If the MU moves backward, the instruction insert(1) moves the MU to the predecessor with the number 1.

**Note**

For the Converter you cannot specify an index. Use the method insert without a parameter instead. Then Plant Simulation moves the MU onto the destination object that is specified in the Target Control .

- The optional parameter Position of data type length designates the position on a length-oriented object.

You can also specify -1 as the position. Then the MU is inserted so that the booking point is located at the position 0 when moving forward and at the end of the object when moving backward.

You can also insert a MU at the position 0 provided there is enough room on the predecessor, or if no predecessor exists, or if the predecessor is a point-oriented object.

- The optional parameter ConveyingDirection of data type integer designates the Conveying Direction in which the MU is going to be inserted on the object. You can specify a number between 0 and 3 .

<!-- image -->

**Return Value**

The return value has the data type boolean .

**Note**

If the destination object has a Pull Control , the return value is false and Plant Simulation enters the MU into the Forward Blocking List of the Destination Object .

**Example**

@.insert(Track,3.3, 1)

SimTalk

move [SimTalk] - MUs

transfer [SimTalk] - MUs

ConveyingDirection [SimTalk]

outIn [SimTalk] - MUs

See also

Forward Blocking List

Pull Control [general description]

Conveying Direction [described]

Video on YouTube

[https://youtu.be/HiPziA8kxc0?si=QuDu7iePtML5x7De&amp;t=908](https://youtu.be/HiPziA8kxc0?si=QuDu7iePtML5x7De&t=908)

move [SimTalk] - MUs

Moves the front of the MU designated by &lt;MU-Path&gt; to the next material flow object.

Remarks

If you specify a Destination Object for the MU , the method move moves the MU to this successor, regardless if the object on which the MU is located and the successor are connected with a Connector .

Plant Simulation moves the entire MU onto a point-oriented object, such as a Station or a ParallelStation . The MU exits the first object entirely and enters the second in its entirety, independent of its length.

The method move only moves the front of the MU immediately to a length-oriented object, such as a Conveyor or a Track , and the remainder of the MU follows continually, according to the speed you set. As long as the MU has not been completely moved, a part of the MUs is located outside of the receiving object. If the MU is moved from a length-oriented object, it covers this part to a certain degree. For this reason a MU may be located on more than one object at the same time. It is only going to be shown on the object on which its booking point is located!

If the MU is moved from a point-oriented object on the other hand, it is moved in its entirety and the parts that has not been moved yet hangs in thin air so to speak.

Within an Entrance Control or an Exit Control , you can access the triggering MU with the anonymous identifier @ . You can also write it abbreviated, for example @.move .

**Note**

If a MU is located on the Pick-and-Place-robot or on the Worker , the instruction @.move moves the part and takes its Unloading Time into consideration. This only applies if you use the method move without a parameter.

**Note**

You cannot move MUs to an object of type Source .

**Note**

You can use the methods transfer or insert to make the MU completely exit a length-oriented object.

**Note**

If you would like the MU to be processed a second time on the same object , use the method outIn and set the parameter WorkOnFinishedPartAgain to true .

**Type**

**Method**

**Syntax**

```simtalk
<MUPath >.move → boolean <MUPath >.move([Destination:object, Position:length]) → boolean <MUPath >.move([Destination:array, Position:length]) → boolean <MUPath >.move([Index:integer, Position:length]) → boolean
```

**Parameters**

- Do not specify a parameter to move the MU to the different successors of the object on which the MU is located using the Exit Strategy you selected.
- Specify the name of the successor as the parameter Destination of data type object to move the MU to this object.
- Specify the names of the successors as the parameter Destination of data type array to try to move the MU to these objects. If none of the objects you specified as members of the array can accept the MU , it will be entered into the Blocking List of each of the objects that are members of the array .
- Specify the index of the successor as the parameter of data type integer to move the MU to this object. The expression integer is short for &lt;MU-path&gt;.location.succ(integer) . You cannot use it if the MU is located on another MU .

The parameter Index of data type integer designates the number of the Connector which is located in the direction of motion. If the MU moves backward, the instruction move(1) moves the MU to the predecessor with the number 1.

**Note**

For the Converter you cannot specify an index. Use the method move without a parameter instead. Then Plant Simulation moves the MU onto the destination object designated in the Target Control

- The optional parameter Position of data type length designates the position on a length-oriented object. If you specify the parameter Position , you can also move MUs between Conveyors with different Conveying Directions . In doing so Plant Simulation switches the conveying direction of the MU . The position -1 means that the MU is moved to the end of the Conveyor .

To prevent a Pull Control for a point-oriented object from being called, specify 0 or any number for the optional parameter Position .

**Note**

If you move a MU driving backward onto a length-oriented object, Plant Simulation automatically places this MU at the end of the length-oriented object.

Return Value

The return value has the data type boolean .

true if moving the MU was successful.

If moving was not successful, the following applies:

**Note**

If moving an object with the commands &lt;MU-Path&gt;.move , &lt;MUPath&gt;.move(DestinationObject:object) , or &lt;MU-Path&gt;.move(Successor:integer) failed, then Plant Simulation enters the MU into the Forward Blocking List / backward Blocking List

of the destination object onto which it intended to move. When the destination object is ready to accept the next MU , the destination object enters an Out event for all entries, i.e., for all MUs in the Forward Blocking List . Then the destination object deletes all entries from its Forward Blocking List .

**Note**

If you specify a certain position on the destination object by specifying the parameter of data type length , the MU does not enter itself into the Forward/Backward Blocking List as Plant Simulation cannot watch at which point in time this position is available again.

In addition, Plant Simulation does not enter a MU into the Forward/Backward Blocking List if it is located on a moving Transporter .

Plant Simulation removes a MU , which is located on the loading space of a Container/Transporter , from the Forward/Backward Blocking List if the Container/Transporter itself is moved.

**Note**

If you moved a MU before an Out -event was processed for this MU , for example in a sensor control, and if the MU could not be moved and was thus entered into the Blocking List of the destination object, the MU will not be removed from the blocking list of the destination object if the object, on which the blocked MU is located, is failed/paused/stopped.

**Note**

If the Destination Object has a Pull Control , the return value is false and Plant Simulation enters the MU into the Forward Blocking List of the Destination Object .

To prevent that Plant Simulation calls the Pull Control of a point-oriented object, specify any value for the optional parameter Position .

**Examples**

```simtalk
var ar: object[]
ar := [Station, Station1, ParallelStation, DismantleStation]
ar.append("TwoLaneTrack.A")
if ?.ExitCtrlFront
	@.move(ar)
end .MUs.Part:1.move(Conveyor) .MUs.Part:2.move(ParallelStation[2,5]) .MUs.Transporter:3.move(track,3.3)
MyConveyor.Cont.move
station.Cont.move(station.succ(2))
var i: integer // checks all successors
for var i := 1 to @.location.NumSucc
	if @.move(i)  // if the moving action was successful
		return
	end
next
print "None of the successors is ready."
@.move(Conveyor, 0) // moves the MU from the beginning of a backward-conveying Conveyor // to the beginning of a forward-conveying Conveyor
@.move(Conveyor, -1) // moves the MU from the end of a forward-conveying Conveyor // to the end of a backward-conveying Conveyor
@.move(Station2, 0) // enter any value for the parameter Position to move the MU to Station2 and // to prevent an existing pull control from being called SimTalk insert [SimTalk] - MUs transfer [SimTalk] - MUs
```

outIn [SimTalk] - MUs See also Unloading Time [PickAndPlace] Unloading Time [Workplace] Anonymous Identifiers [described] Pull Control [general description] Forward Blocking List Backward Blocking List Strategy [material flow objects] Video on YouTube move [SimTalk] - MUs

[https://youtu.be/MY59lMy3UPM?si=CTYnggPjayNmdzlb&amp;t=113](https://youtu.be/MY59lMy3UPM?si=CTYnggPjayNmdzlb&t=113)

num [SimTalk] - MUs

Returns the instance of the designated number of the MU designated by &lt;MU-Path&gt; independent of the actual location of the MU .

Remarks

The method only applies to MUs in the Class Library .

Type

Method

Syntax

```simtalk
<MUPath >.num(Instance:integer) → object
```

Parameter

The parameter Instance of data type integer designates the number of the MU . The number is displayed in the name of the MU , separated by a colon (for example: .MUs.Transporter:13 ).

Return Value

The return value has the data type object .

Example

```simtalk
print .MUs.Transporter.num(1)
```

SimTalk

GetNo [SimTalk]

See also

Number [of the MU]

###### positionList [SimTalk] - MUs

positionList [SimTalk] - MUs

Returns the position list of the MU designated by &lt;MU-Path&gt; and writes it into a table.

**Remarks**

Depending on its length, the MU may be located on several length-oriented material flow objectsConveyors or Tracks -at the same time. The command Position then lists all of the objects.

<!-- image -->

In the following example the Part stretches across three Conveyors . The front of the Part is located on Conveyor5 at the position 3.25 meters. The rear of the Part is located on the Conveyor3 at the position 2.75 meters.

<!-- image -->

At times the Part may not be entirely located on a length-oriented object, but its front or rear are literally up in the air. Compare the examples below:

The Source moves the Part along a Connector to the Conveyor . According to the default transfer behavior the front of the Part is located at the position 0 on the Conveyor . The rest of the Part with the length of 0.5 hangs in the air. The minus sign in the second row in the example below indicates that this length hangs in the air.

<!-- image -->

In this example the Part is moved according to the Exit Control with the method move to the position 4 meters starting at the entrance of the Conveyor . The front of the Part is located at the position 4 on the Conveyor . The rest of the Part with the length of 0.5 hangs in the air. As the Conveyor moves forward, the rear of the Part , which hangs in the air, is located to the left of the insertion position of 4 meters.

<!-- image -->

In this example the Part is moved according to the Exit Control with the method move onto a Conveyor that moves backward to the position 0 meters starting from the entrance of the Conveyor . The rear of the Part is located at the position 0 the Conveyor . The front and the rest of the Part with the length of 0.5 hangs in the air. As the Conveyor moves backward, the front of the Part , which hangs in the air, is located to the right of the insertion position of 0 meters.

<!-- image -->

In this example the Part is moved according to the Exit Control with the method move onto a Conveyor that moves backward to the position 4 meters starting from the entrance of the Conveyor . The rear of the Part is located at the position 4 of the Conveyor . The front and the rest of the Part with the length of 0.5 hang in the air. As the Conveyor moves backward, the front of the Part , which hangs in the air, is located to the right of the insertion position of 4 meters.

<!-- image -->

Type

Method

**Syntax**

<!-- image -->

**Parameter**

The parameter Positions of data type table designates the name of the table.

Plant Simulation automatically generates the format of the table.

**positionList [SimTalk] - MUs**

- Column 1 of the table contains the object on which the MUPart is located ( object ).
- Column 2 and column 3 contain the position of the front and the rear of the MUPart ( length ).

**Example**

```simtalk
@.positionList(MyDataTable)
num := MyDataTable.ydim
print num
```

**SimTalk**

move [SimTalk] - MUs

See also

Position [MUs]

###### removeFromBlocklists [SimTalk]

Removes the MU specified by &lt;MU-Path&gt; from all blocking lists and sets the BlockingStarttime to -1.

Type

Method

Syntax

<MUPath >.removeFromBlocklists -> void

**Example**

```simtalk
.MUs.Part:13.removeFromBlocklists
```

**See also**

BlockingStarttime [SimTalk]

Forward Blocking List

Exit Blocking List

Backward Blocking List setLength [SimTalk] - MUs Sets the length of the MU designated by &lt;MU-Path&gt;.

Remarks

You can extend the length of the part so that it exceeds the borders of the material flow object. In this case the first predecessor or the first successor is used. The booking position of the part has to remain on the current object though.

You can also shorten the length of the part as long as the booking position of the part remains on the current object.

You cannot use the method setLength if the MU is either located on an AngularConverter , a Converter , a Turnplate , or a Turntable at the moment or would be extended on such an object after the length change.

**Note**

Plant Simulation adjusts the read-only attribute BookPos on the length-oriented object when the length changes.

**Note**

When you change the length of a MU , Plant Simulation triggers the Light Barrier Sensors which are affected by the length change.

Type

Method

Syntax

&lt;MUPath &gt;.setLength(Length:length, Direction:integer)

**Parameters**

- The parameter Length of data type length designates the new length of the MU .
- The parameter Direction of data type integer designates the direction into which the MU is elongated.
- 0 : Length change only at the rear.
- 1 : Length change only at the front.
- 2 : Half of the length changes toward the rear of the MU , half of the length changes toward the front of the MU .

Plant Simulation changes the length at the front in the direction of motion when you specify 1 for the parameter Direction .

The length changes at the rear, when you specify 0 for the parameter.

If the MU is transported crosswise , Plant Simulation changes the width of the MU .

**Example**

.MUs.Container.setLength(5,1)

**SimTalk**

BookPntHRelative [SimTalk]

BookPntLRelative [SimTalk]

BookPntWRelative [SimTalk]

BookPos [SimTalk]

transfer [SimTalk] - MUs

Transfers the MU designated by &lt;MU-Path&gt; to the next material flow object.

Remarks

As opposed to the method move , the method transfer completely removes the MU from the active object. On point-oriented objects both methods behave the same.

On length-oriented objects , the method transfer removes the entire MU from the active object. The rear is not transferred to the length-oriented object!

**Note**

When transferring the MUs with the commands &lt;MU-

Path&gt;.transfer , &lt;MU-Path&gt;.transfer(DestinationObject:object) , or &lt;MU-

Path&gt;.transfer(Successor:integer) failed, then Plant Simulation enters the MU into the Forward Blocking List of the destination object onto which it intended to move. When the destination object is ready to accept the next MU , the destination object enters a Out event for all entries, i.e., for all MUs in the Forward Blocking List . Then the destination object deletes all entries from its Forward Blocking List .

**Note**

If you move a MU driving backward onto a length-oriented object, Plant Simulation automatically places this MU at the end of the length-oriented object.

**Note**

If you specified a certain Position with the parameter length , the MU does not enter itself into the Forward Blocking List , as Plant Simulation cannot watch when this specific position becomes free.

**Note**

If you moved a MU before an Out -event was processed for this MU , for example in a sensor control, and if the MU could not be moved and was thus entered into the Blocking List of the destination object, the MU will not be removed from the Blocking List of the destination object if the object, on which the blocked MU is located, is failed/paused/stopped.

**Note**

If you would like the MU to be processed a second time, use the method outIn and set the parameter WorkOnFinishedPartAgain to true , instead of moving the MU onto itself.

**Syntax**

```simtalk
<MUPath >.transfer(Destination:any[, Position:length]) → boolean <MUPath >.transfer(Index:integer[, Position:length]) → boolean
```

**Parameters**

- The parameter Destination of data type object designates the destination object to which the part is going to be transferred.

The parameter Index of data type integer designates the number of the Connector which is located in the direction of motion. If the MU moves backward, the instruction transfer(1) moves the MU to the predecessor with the number 1.

**Note**

For the Converter you cannot specify an index. Use the method transfer without a parameter instead. Then Plant Simulation moves the MU onto the destination object designated in the Target Control .

When moving to length-oriented objects, Plant Simulation not only moves the front of the MU , but the entire MU . The rear end of the MU does not enter the length-oriented object though, but hangs in thin air so to speak.

- The optional parameter Position of data type length is the position on a length-oriented object.

**Return Value**

The return value has the data type boolean .

true if the MU was transferred successfully.

**Note**

If the destination object has a Pull Control , the return value is false and Plant Simulation enters the MU into the Forward Blocking List of the destination object.

**Example**

@.transfer(Conveyor) @.transfer(Conveyor, 3.3)

**SimTalk**

insert [SimTalk] - MUs move [SimTalk] - MUs

outIn [SimTalk] - MUs

See also

Pull Control [general description]

Forward Blocking List

Methods for the State of the Mobile Object

Methods for the State of the MU

The MUs provide the method outIn [SimTalk] - MUs for returning the state they are in.

To view all of the methods , read-only attributes , and attributes of the mobile object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

###### outIn [SimTalk] - MUs

Makes the MU designated by &lt;MU-Path&gt; exit the object on which it is located after the time you specify.

Remarks

A typical use case for the method outIn is to manually change processing of the part, that was created on a station, or to make the part leave the station belated after it was processed on a station, depending on the situation.

**Note**

The method does not have any effect when processing of the part has not started yet.

Type

Method

Syntax

```simtalk
<MUPath >.outIn(SecondsTillOut:time[, WorkOnFinishedPartAgain:boolean:=false])
```

**Parameter**

- The parameter SecondsTillOut of data type time designates the number of seconds after which the part exits the object, based on the current point in time of the simulation. The time you enter has to be equal to or greater than 0. The value -1 signifies that Plant Simulation determines the processing time according to the attribute ProcTime of the material flow object, meaning that it either determines a random number or that it sets a constant processing time.

**Note**

On length-oriented material flow objects or on a PlaceBuffer you can only use the method for MUs which are ready to exit.

- The optional parameter WorkOnFinishedPartAgain of data type boolean sets if an already processed part will be processed again on point-oriented objects.

If you specify true or the part has not been processed all the way yet, the time counts as Processing Time for statistical purposes.

If you specify false and the part has already been processed all the way, the time counts as Waiting Time for statistical purposes.

**Note**

For a material flow object, which does not process the part, such as a Buffer or a PlaceBuffer , for which you specified a Processing Time of 0 , the time always counts as Waiting Time for statistical purposes.

This setting is particularly useful when a MU is created on a station. Then it is completely processed and ready to exit. If it is to be processed still, you can specify outIn(-1, true) directly after create to start processing.

**Default Value of the Parameter**

The default value is false.

**Examples**

Station.Cont.outIn(10)

ParallelStation.Cont.outIn(-1,true) // starts processing the parts on the ParallelStation after the specified // time provided Start processing when full is active

```simtalk
var p : object
p := .MUs.part.create(Station)
```

p.outin(-1, true)

**SimTalk**

create [SimTalk] - MUs

ProcTime [SimTalk] - material flow objects

Methods for Accessing the Load of Container and Transporter

\_Methods for Accessing the Load of Container and Transporter

The Container and the Transporter provide a number of methods for accessing their load.

The Container and the Transporter provide the methods listed in the table of contents to the left for accessing the load they transport.

**Note**

These methods do not apply to the object Part as it does not have loading capacity.

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

deleteMovables [SimTalk] - MUs

deleteMovables [SimTalk] - MUs

Deletes all MUs on the loading space of the MU designated by &lt;MU-Path&gt;.

Type

Method

Syntax

&lt;MUPath &gt;.deleteMovables

**Example**

.Models.container:1.deleteMovables pe(Y,Y) / [X,Y] [SimTalk] - MUs Sets the storage place of the matrix-based loading space of the MU designated by &lt;MU-Path&gt;.

Remarks

Instead of pe(X,Y) you can also specify [X,Y] .

Type

Method

Syntax

```simtalk
<MU>.pe(X:integer, Y:integer) → any
Path <MUPath >[X:integer, Y:integer] → any
```

**Parameters**

- The parameter X of data type integer designates the X-Position of the MU .
- The parameter Y of data type integer designates the Y-Position of the MU .

Return Value

The return value has the data type any .

Example

```simtalk
@.pe(2,3).Cont.move(machine)
print .MUs.Transporter:1[2,3].Cont
```

See also

\_Methods and Read-Only Attributes of the pe

Methods and Read-Only Attributes of the pe

\_Methods and Read-Only Attributes of the pe

The pe , standing for production element, i.e., the place on a Container or Transporter with loading capacity, provides the methods and read-only attributes listed in the table of contents to the left.

###### Cont [SimTalk] - pe, MUs

Cont [SimTalk] - pe, MUs

Returns the MU which is located at the specified position of the loading space of the MU designated by &lt;MU-Path&gt;.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.pe(X:integer, Y:integer).Cont <MUPath >[X:integer, Y:integer].Cont
```

**Parameters**

- The parameter X of data type integer designates the X-Position of the MU .
- The parameter Y of data type integer designates the Y-Position of the MU .

Return Value

The return value has the data type object .

Example

```simtalk
@.pe(1,1).Cont.move(Station) @[1,1].Cont.move(Station)
```

###### getStackHeight [SimTalk] - MUs

Returns the height of the stack in meters on the designated storage place on the storage area of the MU designated by &lt;MU-Path&gt;.

Remarks

Here the height of the stack designates its physical height, not the number of parts on the stack.

If you output the value with the method print , the unit is the unit you selected under Preferences/Model Settings &gt; Unit &gt; Length .

Type

Method

Syntax

```simtalk
< Path >.pe(X:integer, Y:integer)getStackHeight → length < Path >[X:integer, Y:integer]getStackHeight → length
```

**Parameters**

- The parameter X of data type integer designates the position of the storage place in the X-Dimension of the storage area.
- The parameter Y of data type integer designates the position of the storage place in the Y-Dimension of the storage area.

Return Value

The return value has the data type length .

**Examples**

```simtalk
print .MUs.Transporter:1.pe(1,1).getStackHeight
print .MUs.Transporter:1[1,1].getStackHeight
// Accesses the topmost MU of the stack .MUs.Transporter:1[1,1].Cont
```

**SimTalk**

ZDim [SimTalk] - Transporter See also Length [preferences] X-Dimension [Transporter] Y-Dimension [Transporter] Z-Dimension [Transporter] Stack Parts in the Store Unload Stacked Parts mu [SimTalk] - pe, MUs Returns all stacked MUs on the loading space of the MU designated by &lt;MU-Path&gt;. Their position within the net of coordinates does not have to be known.

**Remarks**

The method mu returns the MUs on the stack if the Z-Dimension is greater than 1.

The index does not declare the order of entry. You can query the greatest index with the read-only attribute NumMU .

Type

Method

Syntax

```simtalk
<MU>.pe(X:integer, Y:integer).mu(Number:integer) → object
Path <MUPath >[X:integer, Y:integer].mu(Number:integer) → object
```

**Parameters**

- The parameter X of data type integer designates the X-Dimension of the MU on the loading space.
- The parameter Y of data type integer designates the Y-Dimension of the MU on the loading space.
- The parameter Number of data type integer designates the Z-Dimension of the MU on the loading space.

Specify -1 to return the MU at the bottom of the stack. It returns VOID if the object is empty.

**Default Value of the Parameter**

The default value for the parameter Number is 1.

**Note**

The MU with the highest number is always the MU that is located on the bottom storage place of the stack, as a rule this is the MU that was moved onto the object first.

**Return Value**

The return value has the data type object .

###### mu [SimTalk] - pe, MUs

**Examples**

```simtalk
print @.pe(5,5).mu(1) // returns the topmost MU on the stack // corresponds to print
@.pe(5,5).cont
print @[5,5].mu(2)    // returns the second MU from the top on the stack
print @[5,5].mu(3)    // returns the bottom MU on a stack with 3 parts
print @[1,1].mu(1)    // returns the topmost MU on the stack
print @[1,1].mu(-1)   // returns the MU at the bottom of the stack
```

SimTalk

NumMU [SimTalk] - MUs

See also

X-Dimension [Transporter]

Y-Dimension [Transporter]

Z-Dimension [Transporter]

###### NumMU [SimTalk] - MUs

Returns the number of MUs which are located on the specified storage place of the MU designated by &lt;MU-Path&gt;.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.pe(X:integer, Y:integer).NumMU <MUPath >[X:integer, Y:integer].NumMU
```

**Parameters**

- The parameter X of data type integer designates the X-Position of the MU .
- The parameter Y of data type integer designates the Y-Position of the MU .

Return Value

The return value has the data type integer .

Example

```simtalk
print @.pe(1,1).NumMU
print @[1,1].NumMU
```

Methods for the Route to the Destination

\_Methods for the Route to the Destination

The Container and the Part provide the methods listed in the table of contents to the left for setting their route to their destination object.

**Note**

The Transporter also provides these methods. As they work slightly different, we describe them under getRouteLength [SimTalk] - Transporter , getRoute [SimTalk] - Transporter , and setRoute [SimTalk] Transporter .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

###### getRoute [SimTalk] - Part, Container

Returns the route of the Part/Container designated by &lt;MU-Path&gt; to its destination.

**Remarks**

For two alternative routes of the same length the method getRoute only returns the unique start of the route and ends before the alternative objects, compare the example for the part.

```simtalk
var route :
object[] := .MUs.PartA:1.getRoute
print route // returns [*.Models.Model.Source, *.Models.Model.Conveyor1, *.Models.Model.Conveyor2b, *.Models.Model.Conveyor3]
```

For two alternative routes of the same length the Tooltip of PartA:1 shows the current location of the part and its destination. Then it lists the material flow objects along the route up to the alternative objects. The

<!-- image -->

Rightwards Heavy Arrow shows the current location of the part within the route.

The South East Arrow and South West Arrow shows that the route splits up from here on, followed by additional objects denoted by dots arranged below each other. The destination terminates the route.

<!-- image -->

Type

Method

Syntax

```simtalk
<MUPath >.getRoute → object[]
```

Return Value

The return value is an array of data type object that contains the objects along the route.

Example

```simtalk
var route : any := .MUs.part:1.getRoute
print "First intermediate destination: ", route[1].Name
```

SimTalk setRoute [SimTalk] - Part, Container getRouteIntermediateDestination [SimTalk] - Part, Container HasRouteToDestination [SimTalk] - MUs getRouteRemaining [SimTalk] See also Route to Destination [Part, Container] Destination [Part, Container]

getRouteIntermediateDestination [SimTalk] - Part, Container

Returns the next object in the route to be covered by the Part/Container designated by &lt;MU-Path&gt;.

Remarks

If the Part/Container is located directly in front of the destination, getRouteIntermediateDestination returns the destination.

getRouteIntermediateDestination applies when automatic routing is activated for the Part/Container , when you set its destination, and when a route to the destination was found.

Type

Method

Syntax

&lt;MUPath &gt;.getRouteIntermediateDestination -&gt; any

Return Value

The return value has the data type any because the destination can also be a storage place.

void if the Part/Container did not find a route.

Example

print .UserObjects.MyContainer:3.getRouteIntermediateDestination

SimTalk

getRoute [SimTalk] - Part, Container

HasRouteToDestination [SimTalk] - MUs

See also

Automatic Routing [Part, Container]

Destination [Part, Container]

Route to Destination [Part, Container]

###### getRouteLength [SimTalk] - Part, Container

Returns the time it takes the Part/Container designated by &lt;MU-Path&gt; to get to its destination object on the shortest route in the direction of motion.

**Remarks**

The destination can either be a material flow object, which can be reached directly via Connectors , or a destination object, which you typed into a sensor.

Type

Method

Syntax

```simtalk
<MUPath >.getRouteLength(DestinationObject:object[, ObjectsToDestination:table, IgnoreRouteWeightingAttr:boolean:=false]) → time <MUPath >.getRouteLength(DestinationObject:object[, ObjectsToDestination:object[], IgnoreRouteWeightingAttr:boolean:=false]) → time
```

**Parameters**

- The parameter DestinationObject of data type object designates the destination object.
- The optional parameter ObjectsToDestination of data type table designates the name of a DataTable into which the Part/Container enters the objects it would pass en-route to the destination.

The optional parameter ObjectsToDestination can also be an array of data type table into which the Part/Container enters the objects it would pass en-route to the destination.

- The optional parameter IgnoreRouteWeightingAttr sets if the Route Weighting Attribute will be ignored ( true ) or if it will be considered ( false ).

**Default Value of the Parameter**

The default value is false.

**Note**

If you entered the destination into a sensor, it does not matter if the sensor is front- or rear-triggered. Plant Simulation always computes the length of the route from the side of the Part/Container which is located in the front in the direction of motion, in relation to the sensor.

**Return Value**

The return value has the data type time .

Is -1 if Plant Simulation did not find a route.

**Examples**

```simtalk
print .MUs.Container:1.getRouteLength(MyConveyor) // returns how long it takes the Container to reach its destination
print .MUs.Part:1.getRouteLength(MyConveyor,objectsOnRoute)
```

SimTalk

RouteWeightingAttr [SimTalk] - Part, Container

See also

Route to Destination [Part, Container]

Route Weighting Attribute - Transporter

###### getRouteRemaining [SimTalk]

Returns the remaining route of the MUs as an array .

Remarks

The method getRoute returns the entire route of the MU .

The method getRouteRemaining returns the part of route that the MU still has to cover.

Type

Method

Syntax

```simtalk
<MUPath >.getRouteRemaining
-> object
```

Return Value

The return value is an array of data object .

Example

```simtalk
print .MUs.Part:13.getRouteRemaining
```

See also

getRoute [SimTalk] - Part, Container

getRoute [SimTalk] - Transporter

###### setRoute [SimTalk] - Part, Container

setRoute [SimTalk] - Part, Container

Sends the Part/Container designated by &lt;MU-Path&gt; to its destination on the objects which you type into the first column of a table.

Remarks

If the last object to be reached is not the destination object of the Part/Container , Plant Simulation automatically adds the destination object to the route.

If the Part/Container leaves the route specified in the table because an Exit Control moves the Part/ Container onto another successor, automatic routing becomes effective again immediately afterwards.

The method setRoute also accepts material flow objects other than objects of type Conveyor . When assigning a route, which contains such objects with setRoute , then the Part/Container passes these objects on its way to the destination. While automatically computing a route, Plant Simulation only takes Conveyors into consideration.

Type

Method

Syntax

```simtalk
<MUPath >.setRoute(ObjectsToDestination:table) <MUPath >.setRoute(ObjectsToDestination:object[])
```

Parameter

The parameter ObjectsToDestination of data type table designates the name of the table. The objects along the route are contained in the first column of data type object .

Instead the parameter ObjectsToDestination can also be an array of data type object that contains all objects along the route.

**Example**

```simtalk
.MUs.Part:1.setRoute(objectsToRoute)
```

SimTalk

getRoute [SimTalk] - Part, Container HasRouteToDestination [SimTalk] - MUs ResetDestinationWhenAtDestination [SimTalk] - MUs See also Route to Destination [Part, Container]

Reset Destination When at Destination [Part, Container]

Destination [Part, Container]

Methods for Accessing Statistics of the MUs

Methods for Accessing Statistics of the MUs

The MUs provide the methods listed in the table of contents to the left for working with statistics values.

You can also use the method showStatisticsReport [SimTalk] to open the Statistics Report of one or several objects.

The mobile objects show most of these values on the Tab Product Statistics and on the Tab Statistics .

**Note**

A number of statistical data is limited to certain types of objects. In this case, Plant Simulation enters no data into the statistics table or the method call returns an error message.

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

###### initStat [SimTalk] - MUs

Resets the statistics of the MU designated by &lt;MU-Path&gt;, i.e., resets all entries to 0 and statistics collection starts anew.

Type

Method

Syntax

```simtalk
<MUPath >.initStat <MUPath >.initStat([Reset:boolean:=false])
```

**Parameter**

The optional parameter Reset of data type boolean sets if Plant Simulation resets the Average Lifespan to 0 ( true ).

Specify false or do not specify the parameter to reset all statistics values, except for Average Lifespan .

If you do not want to include the statistics of the beginning of the simulation run, you can reset statistics at a later point in time. Then Plant Simulation will collect the statistics from that point in time on.

Calling the method initStat of a MU class always resets the Average Lifespan to 0. The parameter named Reset only affects the MU instances which exist at the point in time at which the method initStat was called. For these instances the Average Lifespan will not be reset. This means that the parameter Reset only takes effect for the class at a later point in time, after these instances were deleted.

**Default Value of the Parameter**

The default value is false.

Example

```simtalk
.MUs.Part.initStat
```

SimTalk

StatisticsStartRes [SimTalk]

statistics [SimTalk] - MUs Returns statistics of the MU designated by <MU-Path>. Type Method Syntax statistics [SimTalk] - MUs

```simtalk
<MUPath >.statistics <MUPath >.statistics(NameOfTable:table_path) <MUPath >.statistics(FileName:string[, CodePage:string])
```

**Parameters**

- Do not specify the parameter to show the data directly in a table on screen.
- Specify the parameter NameOfTable of data type table\_path to write the data to that table.
- Specify the parameter FileName of data type string to write the table to that file. Plant Simulation will overwrite existing entries.

Specify a file name to specify the encoding with the optional parameter CodePage of data type string .

You can specify "ANSI" , "UTF-8" , or "Unicode" .

Do not specify this parameter to use the encoding UTF-8 .

The product statistics table of the MUs shows these values:

| Item English                                                                      | Description                                                                                                                                                                                                                                                                                                                                                                        | Read-only attribute                     | Item German   |
|-----------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------|---------------|
| Shows the name of the MU the statistical data is interpreted (data type string ). | -                                                                                                                                                                                                                                                                                                                                                                                  | Name                                    | Name for      |
| Time Shows the current simulation                                                 | time ( time                                                                                                                                                                                                                                                                                                                                                                        | -                                       | ). Zeit       |
| Start (P) Shows the ( time ).                                                     | time the product statistics collection of the object started                                                                                                                                                                                                                                                                                                                       | -                                       | Start (P)     |
| %age_ P_IP                                                                        | Shows the time portion during which the MU was located on a material flow object of type Production and was processed. The sum of the columns %age_P_Wa , %age_P_IP , %age_P_Stp , %age_P_F , and %age_P_P of the Product Statistics Table shows the ratio of the time the MU was located on a material flow object of type Production to the entire statistics collection period. | StatProdWor kingPortion [SimTalk] - MUs | %_P_IBA nt    |

| Item English   | Description                                                                                                                                                                                                                                                                                                                                                                                | Read-only attribute                       | Item German   |
|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------|---------------|
| %age_ P_SU     | Shows the time portion during which a resource of type Production was setting-up for this MU ( real ).                                                                                                                                                                                                                                                                                     | StatProdSetu pPortion [SimTalk] - MUs     | %_P_RA nt     |
| %age_ P_Wa     | Shows the time portion during which the MU was located on a material flow object of type Production and was waiting. The sum of the columns %age_P_Wa , %age_P_IP , %age_P_Stp , %age_P_F , and %age_P_P of the Product Statistics Table shows the ratio of the time the MU was located on a material flow object of type Production to the entire statistics collection period.           | StatProdWait ingPortion [SimTalk] - MUs   | %_P_WA nt     |
| %age_ P_Stp    | Shows the time portion during which the MU was located on a material flow object of type Production and was stopped. The sum of the columns %age_P_Wa , %age_P_IP , %age_P_Stp , %age_P_F , and %age_P_P of the Product Statistics Table shows the ratio of the time the MU was located on a material flow object of type Production to the entire statistics collection period.           | StatProdStop pedPortion [SimTalk] - MUs   | %_Ang_ WAnt   |
| %age_ P_F      | Shows the time portion during which the MU was located on a material flow object of type Production and was in a failed state. The sum of the columns %age_P_Wa , %age_P_IP , %age_P_Stp , %age_P_F , and %age_P_P of the Product Statistics Table shows the ratio of the time the MU was located on a material flow object of type Production to the entire statistics collection period. | StatProdFailP ortion [SimTalk] - MUs      | %_P_SA nt     |
| %age_ P_P      | Shows the time portion during which the MU was located on a material flow object of type Production and was in a paused state. The sum of the columns %age_P_Wa , %age_P_IP , %age_P_Stp , %age_P_F , and %age_P_P of the Product Statistics Table shows the ratio of the time the MU was located on a material flow object of type Production to the entire statistics collection period. | StatProdPaus ingPortion [SimTalk] - MUs   | %_P_PA nt     |
| %age_ T_IP     | Shows the time portion during which the MU was located on a material flow object of type Transport and was processed. The sum of the columns %age_T_Wa , %age_T_IP , %age_T_F , and %age_T_P of the Product Statistics Table shows the ratio of the time the MU was located on a material flow object of type Transport to the entire statistics collection period.                        | StatTranspPa usingPortion [SimTalk] - MUs | %_T_IBA nt    |
| %age_ T_SU     | Shows the time portion during which a resource of type Transport was setting-up for this MU ( real ).                                                                                                                                                                                                                                                                                      | StatTranspSe tupPortion                   | %_T_RA nt     |

| Item English   | Description                                                                                                                                                                                                                                                                                                                                                                          | Read-only attribute                        | Item German   |
|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------|---------------|
|                |                                                                                                                                                                                                                                                                                                                                                                                      | [SimTalk] - MUs                            |               |
| %age_ T_Wa     | Shows the time portion during which the MU was located on a material flow object of type Transport and was waiting. The sum of the columns %age_T_Wa , %age_T_IP , %age_T_F , and %age_T_P of the Product Statistics Table shows the ratio of the time the MU was located on a material flow object of type Transport to the entire statistics collection period.                    | StatTranspW aitingPortion [SimTalk] - MUs  | %_T_WA nt     |
| %age_ T_Stp    | Shows the time portion during which the MU was located on a material flow object of type Transport and was stopped. The sum of the columns %age_T_Wa , %age_T_IP , %age_T_F , and %age_T_P of the Product Statistics Table shows the ratio of the time the MU was located on a material flow object of type Transport to the entire statistics collection period.                    | StatTranspSt oppedPortio n [SimTalk] - MUs | %_Ang_ SAnt   |
| %age_ T_F      | Shows the time portion during which the MU was located on a material flow object of type Transport and was in a failed state. The sum of the columns %age_T_Wa , %age_T_IP , %age_T_F , and %age_T_P of the Product Statistics Table shows the ratio of the time the MU was located on a material flow object of type Transport to the entire statistics collection period ( real ). | StatTranspFa ilPortion [SimTalk] - MUs     | %_T_SA nt     |
| %age_ T_P      | Shows the time portion during which the MU was located on a material flow object of type Transport and was in a paused state. The sum of the columns %age_T_Wa , %age_T_IP , %age_T_F , and %age_T_P of the Product Statistics Table shows the ratio of the time the MU was located on a material flow object of type Transport to the entire statistics collection period ( real ). | StatTranspPa usingPortion [SimTalk] - MUs  | %_T_PA nt     |
| %age_ S_IP     | Shows the time portion during which the MU was located on a material flow object of type Storage and was processed. The sum of the columns %age_S_Wa , %age_S_IP , %age_S_F , and %age_S_P of the Product Statistics Table shows the ratio of the time the MU was located on a material flow object of type Storage to the entire statistics collection period.                      | StatStoreWor kingPortion [SimTalk] - MUs   | %_L_IBA nt    |
| %age_ S_SU     | Shows the time portion during which a resource of type Storage was setting-up for this MU ( real ).                                                                                                                                                                                                                                                                                  | StatStoreSet upPortion [SimTalk] - MUs     | %_L_RA nt     |

| Item English              | Description                                                                                                                                                                                                                                                                                                                                                                      | Read-only attribute                      | Item German                           |
|---------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------|---------------------------------------|
| %age_ S_Wa                | the time portion during which the MU was located on a material flow object of type Storage and was waiting. The sum of the columns %age_S_Wa , %age_S_IP , %age_S_F , and %age_S_P of the Product Statistics Table shows the ratio of the time the MU was located on a material flow object of type Storage to the entire statistics collection period.                          | StatStoreWai tingPortion [SimTalk] - MUs | %_L_WA nt                             |
| %age_ S_Stp               | Shows the time portion during which the MU was located on a material flow object of type Storage and was stopped. The sum of the columns %age_S_Wa , %age_S_IP , %age_S_F , and %age_S_P of the Product Statistics Table shows the ratio of the time the MU was located on a material flow object of type Storage to the entire statistics collection period.                    | StatStoreSto ppedPortion [SimTalk] - MUs | %_L_An gAnt                           |
| %age_ S_F                 | Shows the time portion during which the MU was located on a material flow object of type Storage and was in a failed state. The sum of the columns %age_S_Wa , %age_S_IP , %age_S_F , and %age_S_P of the Product Statistics Table shows the ratio of the time the MU was located on a material flow object of type Storage to the entire statistics collection period.          | StatStoreFail Portion [SimTalk] - MUs    | %_L_SA nt                             |
| %age_ S_P                 | Shows the time portion during which the MU was located on a material flow object of type Storage and was in a paused state. The sum of the columns %age_S_Wa , %age_S_IP , %age_S_F , and %age_S_P of the Product Statistics Table shows the ratio of the time the MU was located on a material flow object of type Storage to the entire statistics collection period ( real ). | StatStorePau singPortion [SimTalk] - MUs | %_L_PAn t                             |
| Count                     | Shows the number of existing MU instances of this class with product statistics on. The MUs may be located in different Frame hierarchies ( integer ).                                                                                                                                                                                                                           | StatCount [SimTalk]                      | Anzahl                                |
| Delete d                  | Shows the number of MUs which were removed from the plant during statistics collection of the class. Plant Simulation only counts MUs for which you selected the check box Product statistics .                                                                                                                                                                                  | StatDeleted [SimTalk] - MUs              | Vernicht et                           |
| avgLT/ Averag e Lifespa n | Shows the average life-span of MUs which were created and removed from the plant during the statistics collection period. Plant Simulation only counts MUs for which you selected the check box Product statistics .                                                                                                                                                             | StatAvgLifeS pan [SimTalk] - MUs         | mittLZ / DurchlZ eit (Durchla ufzeit) |

For MUs these restrictions of resource statistics apply:

| Item English   | Note                                                                                                                                                                                                                   | Item German   |
|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------|
| Working        | The entries in the columns %_AAnt, Working, WorkingTime, A_Mu und A_Delta are always 0, as you cannot set a processing time for MUs with loading capacity and thus they never are working.                             | Arbeiten      |
| Failures       | The entries in the columns %_SAnt, Stoerungen, Stoerungszeit, S_Mu und S_Delta are always 0, as you cannot fail the accommodation capacity of the MUs. Failures of the Transporter only refer to its driving behavior. | Störungen     |
| Pauses         | The entries in the columns %_PAnt, Pausen, Pausenzeit, P_Mu und P_Delta are always 0, as you cannot pause the accommodation capacity of the MUs. Pauses of the Transporter only refer to its driving behavior.         | Pausen        |
| Setup          | The entries in the columns %_RAnt, Ruesten, Ruestszeit, R_Mu, R_Delta, Ruestzeit(W), Ruestzeit(A) and Ruestzeit(B) are always 0, as theMU themselves cannot be set-up.                                                 | Rüsten        |

As material flow resources the MUs can only take on the states Blocked and Waiting .

The drive statistics table of the Transporter shows these values:

| Item German   | Description                                                                                                         | Read-only attribute                                             | Item German   |
|---------------|---------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------|---------------|
| Name          | Shows the name of the object for which the statistical data of the row are evaluated ( string ).                    | -                                                               | Name          |
| Time          | Shows the current simulation time ( time ).                                                                         | -                                                               | Zeit          |
| OrderOcc      | Shows the ratio of the time during which the Transporter had an order and was loaded to the life-span ( real ).     | StatOrderOccTime [SimTalk] StatOrderOccPortion [SimTalk]        | AuftragBelegt |
| OrderEmpty    | Shows the ratio of the time during which the Transporter had an order and was not loaded to the life-span ( real ). | StatOrderEmptyTime [SimTalk] StatOrderEmptyPortion              | AuftragLeer   |
| Home          | Shows the ratio of the time during which the Transporter was                                                        | StatHomeDrivingTime [SimTalk] StatHomeDrivingPortio n [SimTalk] | Heim          |

| Item German   | Description                                                                                                | Read-only attribute                   | Item German      |
|---------------|------------------------------------------------------------------------------------------------------------|---------------------------------------|------------------|
|               | returning to its base to the life-span ( real ).                                                           |                                       |                  |
| Charges       | Shows how often the battery was charged ( integer ).                                                       | StatBatChargeCount [SimTalk]          | Ladungen         |
| %age_C        | Shows the ratio of the time during which the battery of the Transporter was charging to the life- span.    | StatBatChargePortion [SimTalk]        | %_LAnt           |
| Tsp%age_F     | Shows the ratio of the time during which the Transporter was in a failed state to the life- span ( real ). | ShiftCalendarObject [SimTalk] - Frame | Fzg%_SAnt        |
| TspFailures   | Shows the number of failures during the total life-span ( integer ).                                       | StatTspFailCount [SimTalk]            | FzgStoerungen    |
| TspFailTime   | Shows the sum of all failure times during the total life-span of the Transporter ( time ).                 | StatTspFailTime [SimTalk]             | FzgStoerungszeit |
| TspF_Mu       | Shows the mean duration of a failure ( time ).                                                             | StatTspFailMu [SimTalk]               | FzgS_Mu          |
| TspF_Delta    | Shows the standard deviation from the mean value ( time ).                                                 | StatTspFailDelta [SimTalk]            | FzgS_Delta       |
| Tsp%ageP      | Shows the ratio of the time during which the Transporter was paused to the total life-span ( real ).       | StatTspPausingPortion [SimTalk]       | Fzg%_PAnt        |
| TspPauses     | Shows the number of pauses during the total life-span ( integer ).                                         | StatTspPausingCount [SimTalk]         | FzgPausen        |
| TspPauseTime  | Shows the sum of all pause-times of the Transporter ( time ).                                              | StatTspPausingTime [SimTalk]          | FzgPausenzeit    |

| Item German   | Description                                                | Read-only attribute           | Item German   |
|---------------|------------------------------------------------------------|-------------------------------|---------------|
| TspP_Mu       | Shows the mean duration of a pause ( time ).               | StatTspPausingMu [SimTalk]    | FzgP_Mu       |
| TspP_Delta    | Shows the standard deviation from the mean value ( time ). | StatTspPausingDelta [SimTalk] | FzgP_Delta    |

**Example**

```simtalk
Station.Cont.statistics                  // outputs to screen .MUs.Transporter:1.statistics(stat_tab)  // outputs to a table
@.statistics("D:\temp\statistics")       // outputs to a file
```

