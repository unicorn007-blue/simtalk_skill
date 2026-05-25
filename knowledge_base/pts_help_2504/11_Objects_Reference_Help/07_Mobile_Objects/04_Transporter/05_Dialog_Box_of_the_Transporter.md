#### Dialog Box of the Transporter

Dialog Box of the Transporter

Double-click the icon of the Transporter that is located on one of the material flow objects in the Frame to open its dialog box.

Edit Simulation Properties

To change the settings of the class of the object, double-click it in the Class Library or on the tab Moving Units in the Toolbox . Here you can then type in or select the simulation properties to get the results you need. The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties :

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the 3D model and press the spacebar .

See also

Number [of the MU]

Automatic Routing [Transporters driving freely] , no fixed route

Video on YouTube

[https://youtu.be/9g6Uou-8eMc?si=06ZmZOxHWmYpXJQa&amp;t=614](https://youtu.be/9g6Uou-8eMc?si=06ZmZOxHWmYpXJQa&t=614)

**Failed [check box] - Transporter**

##### Failed [check box] - Transporter

To fail the Transporter and thus stop it, select this check box.

<!-- image -->

The failure only applies to the driving behavior of the Transporter , not to the capacity.

If you manually fail the Transporter , it remains failed while any of the failure profiles you defined is active. It will change to not failed once the last failure ( List &gt; DisruptionEnd event) of the last failure profile ends or when you clear the check box .

**Note**

Plant Simulation resets failures during a Reset Simulation phase of the simulation.

**Note**

The Transporter is failed if you activate this check box or if you activate one of its failure profiles on the Tab Failures .

**Note**

If you fail the Transporter , this also fails its loading space.

SimTalk

Failed [SimTalk] - Transporter

##### Paused/Planned/Unplanned [Transporter]

To pause the Transporter , select Paused from the drop-down list.

<!-- image -->

The pause only applies to the driving behavior of the Transporter , not to the capacity.

To set the Transporter to unplanned, select Unplanned . Unplanned times are the times which you typed into the ShiftCalendar during which the Transporter is not scheduled to work.

To set the Transporter to planned, select Planned . Planned times encompass the processing times without the pauses during the shifts in your plant.

**Note**

Plant Simulation does not reset pauses during the Reset Simulation phase of the simulation. If you use pauses in your simulation, make sure that all objects are set to the desired state during the Reset phase.

**Note**

When you pause the Transporter , this also pauses its Loading Space .

SimTalk

Pause [SimTalk] - Transporter

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

The shared properties are described under the Tab Attributes .

**MU Length [Transporter]**

###### MU Length [Transporter]

Type the Length of the Transporter into the text box. The length-oriented objects use the Length to determine how many Transporters they can accommodate.

<!-- image -->

**SimTalk**

Length [SimTalk] - MUs

MULength [SimTalk]

###### MU Width [Transporter]

Type the Width of the Transporter into the text box.

The length-oriented objects use the Width after the AngularConverter has changed the Conveying Direction to determine how many Transporters they can hold.

**Note**

If the Transporter is passively transported by a Conveyor , it also uses the MU Width .

<!-- image -->

SimTalk

MUWidth [SimTalk]

**MU Height [Transporter]**

###### MU Height [Transporter]

Type the Height of the Transporter .

The Height is only important for 3D as only 3D provides the z-dimension.

<!-- image -->

**SimTalk**

**MUHeight [SimTalk]**

###### Booking Point Length [Transporter]

Type in the relative position of the Booking Point of the Transporter . It applies, when it is conveyed lengthwise .

The value you type in is the distance from booking point 0, which is located at the front of the Transporter , in the direction of motion. You can type in a relative value between 0 and 1 . Plant Simulation uses it, when the Conveying Direction is forward or backward . Plant Simulation shows the absolute position of the booking point in parentheses. In our example below the Transporter has a length of 1.6 meters and its booking point is at the position 0.5. The absolute position of the booking point this is at the position 0.80 meters.

When you are modeling conveyor systems, the booking point oftentimes represents the center of gravity of the part. When the booking point, i.e., the center of gravity of the part, has transferred onto a conveyor, the part starts moving with the Speed you set for this conveyor.

<!-- image -->

By default, a Transporter requires a booking point, as a long Transporter may be located on more than one length-oriented object at the same time. Plant Simulation uses the booking point to determine on which material flow object it shows the Transporter when animating a simulation run. Plant Simulation shows, for example, a Transporter moving along from Track/TwoLaneTrack to Track/TwoLaneTrack on the first Track/TwoLaneTrack until its booking point moves on to the next Track/TwoLaneTrack .

If the part is not animated on the expected position on the object, check the position of the Booking Point .

Compare this example:

- Here Booking Point Length and Booking Point Width of the square part are located in its center at the position 0.5 . The part is animated at the center of the conveyor belt.

<!-- image -->

- Here Booking Point Width of the square part are located at the position 0.2 . The part is animated with an offset to the left in the direction of motion on the conveyor belt.

<!-- image -->

**Note**

When you assign a value to the booking point in a Method , Plant Simulation interprets this number as meters. Only when outputting it with the method print , it converts the value according to the settings you selected under File &gt; Model Settings/Preferences &gt; Units &gt; Length .

**SimTalk**

BookPntLRelative [SimTalk]

**See also**

**Set and Link Animation Points and Lines**

**Booking Point Width [Transporter]**

###### Booking Point Width [Transporter]

Type in the relative position of the Booking Point of the Transporter . It applies when it is conveyed crosswise .

The value you type in is the distance from booking point 0, which is located at the right-hand side of the Transporter in the direction of motion. You can type in a relative value between 0 and 1. Plant Simulation uses it, when the Conveying Direction is lateral right or lateral left . Plant Simulation shows the absolute position of the booking point in parentheses.

When you are modeling conveyor systems, the booking point oftentimes represents the center of gravity of the part. Once the booking point, i.e., the center of gravity of the part, has transferred onto a conveyor, the part starts moving with the Speed you set for this conveyor.

<!-- image -->

The Transporters require a booking point, as a long Transporter may be located on more than one length-oriented object at the same time. Plant Simulation uses the booking point to determine on which material flow object it shows the Transporter when animating a simulation run. Plant Simulation shows, for example, a Transporter moving along from Track/TwoLaneTrack to Track/TwoLaneTrack on the first Track until its booking point moves on to the next Track .

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

**See also**

**Set and Link Animation Points and Lines**

###### Booking Point Height [Transporter]

Type in at which Relative Height the Booking Point of the Transporter is located.

The booking point height is only important if you want to use the z-dimension of the Transporter in 3D . You can type in a relative value between 0 and 1 . Plant Simulation shows the absolute position of the booking point in parentheses.

<!-- image -->

For the default Booking Point Height of 0 Plant Simulation places the Transporter flush onto the Track or on the TwoLaneTrack .

**Note**

When you assign a value to the booking point in a Method , Plant Simulation interprets this number as meters. Only when outputting it with the method print , it converts the value according to the settings you selected under File &gt; Model Settings/Preferences &gt; Units &gt; Length .

**SimTalk**

BookPntHRelative [SimTalk]

###### Speed [Transporter]

Speed [Transporter]

Type in the Speed with which the Transporter drives on the Track/TwoLaneTrack .

When you clear Acceleration , the Transporter attempts to reach its Final Speed immediately without accelerating. Once it reaches the Final Speed , it drives on with the constant speed which you type into the text box Speed . You can also type in -1 for an infinite speed.

SimTalk

Speed [SimTalk] - Transporter

###### Backwards [Transporter]

To make the Transporter itself and the MUs on it move in reverse on the Track/TwoLaneTrack , select this check box.

<!-- image -->

<!-- image -->

To make them move forward, clear the check box. If the Transporter drives in reverse from a Track/ TwoLaneTrack onto a Track/TwoLaneTrack , it moves onto the Track/TwoLaneTrack at its exit and leaves it at its entrance.

**Note**

This only applies if the Transporter drives from a Track/TwoLaneTrack to a Track/TwoLaneTrack , but not from a point-oriented object onto a Track/TwoLaneTrack .

Driving forward or backward are properties of the Transporter , not of the Track/TwoLaneTrack !

If you cleared Acceleration of the Transporter , it reverses the direction into which it drives immediately without decelerating and accelerating.

If you selected Acceleration , the Transporter slows down until its speed is 0. Then it reverses the direction into which it drives and accelerates until it reaches its final speed.

If the attribute TargetDistance of the Transporter is true , you cannot change the attribute Backwards .

SimTalk

Backwards [SimTalk] - Transporter

See also

Backwards [check box] - loading space

###### Acceleration [check box] - Transporter

Acceleration [check box] - Transporter

To make the Transporter increase or decrease its speed on the Track/TwoLaneTrack , select this check box.

Click Apply to activate the text box Acceleration and to show the Current Speed .

SimTalk

AccelerationEnabled [SimTalk] - Transporter

Video on YouTube

[https://youtu.be/9g6Uou-8eMc?si=J53pUaXzIoM3A9V\_&amp;t=1263](https://youtu.be/9g6Uou-8eMc?si=J53pUaXzIoM3A9V_&t=1263)

###### Current Speed [text box] - Transporter

Shows the actual speed with which the Transporter drives on the Track/TwoLaneTrack at this point in time forward (positive number) or in reverse (negative number), when Acceleration is active.

**Note**

Although this value can continually change because the Transporter is accelerating, CurrentSpeed is watchable for certain values. By observing this value you might, for example, recognize when the speed of the Transporter changes, because it collided with the Transporter in front of it, because it stops at the end of a Track/TwoLaneTrack , or because of other outside influences.

An observer of the attribute CurrentSpeed does not wake up if a Transporter driving without acceleration collides with a decelerating/accelerating Transporter and the CurrentSpeed does not change immediately during this action, but the collided Transporter is forced to a continuous speed change by the preceding Transporter . The observer only wakes up, when the final speed of the preceding Transporter is reached.

SimTalk

CurrentSpeed [SimTalk] - Transporter

calcBrakingDistance [SimTalk] - Transporter

See also

Acceleration [check box] - Transporter Acceleration [text box] - Transporter Type in the Acceleration with which the Transporter increases its speed on the Track/TwoLaneTrack .

<!-- image -->

You can type in any real number greater than or equal to 0.

SimTalk

Acceleration [SimTalk] - Transporter

CurrentAcceleration [SimTalk] - Transporter

###### Deceleration [text box] - Transporter

Type in the Deceleration with which the Transporter reduces its speed on the Track/TwoLaneTrack .

<!-- image -->

You can type in any real number greater than or equal to 0.

SimTalk

Deceleration [SimTalk] - Transporter

calcBrakingDistance [SimTalk] - Transporter

###### Is Tractor [check box]

Is Tractor [check box]

To designate the active Transporter as the tractor of the tugger train , which pulls or pushes the trailers, select this check box.

<!-- image -->

<!-- image -->

The Transporter then shows the icon tractor in 2D instead of the icon Operational . As a vector graphic the icon of the tractor looks like this .

**Note**

To prevent the tractor from loading parts onto the loading space, type in 0 as the X-Dimension and the Y-Dimension for the Loading Space Type &gt; Store .

Enter 0 as the Capacity for the Loading Space Types &gt; Track/Line .

SimTalk

IsTractor [SimTalk]

See also

GetTractor [SimTalk]

Designating the Tractor

<!-- image -->

###### Start Delay Duration [text box]

Type the Start Delay Duration after which a Transporter , which collided with the one driving in front of it, starts moving after the Transporter driving in front started moving again.

Select a distribution from the drop-down list, and type in the values, which that distribution requires, into the text box.

For the Transporter that drives freely within the space of the model the Start Delay Duration is the time after which a stopped Transporter starts moving again after you entered a Speed that is greater than 0.

SimTalk

StartDelayDuration [SimTalk]

StartDelayDuration.Type

Tab Load Bay

Tab Load Bay

Select the settings for defining the loading space of the Transporter on the tab Load Bay .

###### Type [loading space]

Type [loading space]

Select the type of loading space of the Transporter .

The loading space of type

- Store designates a loading space consisting of loading places along the X-Dimension , the YDimension , and the Z-Dimension onto which the Transporter places the parts it loads.

<!-- image -->

The orientation of the MUs depends on the orientation of the animation line in 2D and in 3D.

- Track designates a passive length-oriented loading space on to which the Transporter loads and unloads parts. This is especially handy for modeling a cross-sliding car and other types of materials handling equipment. You can also type in Controls and define Sensors . In addition, you can select the Direction of the Animation Line . The orientation of the MU depends on the orientation of the animation line in 2D and in 3D.

**Note**

The animation on the length-oriented loading space requires an animation line in 2D. As Plant Simulation does not create the animation line automatically, you have to create it in the icon of the object. For vector graphics we defined the animation line, you cannot change it.

**Note**

The Length of the loading space is independent of the MU Length of the Transporter as such in 2D and in 3D.

<!-- image -->

- Line designates an active length-oriented loading space similar to a Conveyor being part of the loading space, which transports the loaded parts forward or backward. The CrossSlidingCar makes extensive use of this type of loading space. In addition, you can select the Direction of the Animation Line . The orientation of the MU depends on the orientation of the animation line in 2D and in 3D.

**Note**

The animation on the length-oriented loading space requires an animation line in 2D. As Plant Simulation does not create the animation line automatically, you have to create it in the icon of the object. For vector graphics we defined the animation line, you cannot change it.

**Note**

The Length of the loading space is independent of the MU Length of the Transporter as such in 2D and in 3D.

**Note**

The window Show Attributes and Methods ( F8 ) only shows the attributes and methods pertaining to the selected type of loading space. If you select Track for example, the window only shows the attributes and methods pertaining to the loading space of type Track , not those pertaining to the loading space of type Store or Line .

**Note**

If the Transporter has derived objects or transports other parts, you cannot change any of the attributes pertaining to the loading space in its class with SimTalk commands.

**SimTalk**

LoadBayType [SimTalk]

<!-- image -->

###### X-Dimension [Transporter]

When you select the loading space of Type &gt; Store , Plant Simulation activates the text box X-Dimension . Type in the dimension of the loading space of the Transporter along the x-axis.

The loading Capacity is the product of X-Dimension times Y-Dimension times Z-Dimension . The greatest allowed value is one million.

<!-- image -->

If you decrease the dimension of the loading space of the Transporter , make sure that no MUs are located on the storage places that will be deleted by this action! Either delete these MUs or move them to another storage place on the smaller loading space.

For loaded Transporters for which you activated the Loading Space Type &gt; Store and then typed in a dimension, Plant Simulation computes the distance between the animation points, onto which it places the loaded MUs , according to the dimension as follows:

- The distance in the X-Direction (horizontal) is the length of the loaded object in pixels divided by the X-Dimension .
- The distance in the Y-Direction (vertical) is the width of the loaded object in pixels divided by the Y-Dimension .

**Note**

For computing the dimension in pixels, compare the Scaling Factor .

If either the distance in the X-Direction or in the Y-Direction is smaller than 4 pixels, Plant Simulation does not show any MUs at all but draws a pattern in a 2D Only model to signify that the object is not empty.

As long as the loading space is half empty, Plant Simulation shows a hatch pattern. If the loading space is more than half full, Plant Simulation shows a checker pattern.

<!-- image -->

**SimTalk**

XDim [SimTalk] - Transporter

YDim [SimTalk] - Transporter

ZDim [SimTalk] - Transporter

Capacity [SimTalk] - MUs

setDim [SimTalk]

See also

Type [loading space]

###### Y-Dimension [Transporter]

When you select the loading space of Type &gt; Store , Plant Simulation activates the text box Y-Dimension . Type in the dimension of the loading space along the y-axis.

The loading Capacity is the product of X-Dimension times Y-Dimension times Z-Dimension . The greatest allowed value is one million.

<!-- image -->

If you decrease the dimension of the loading space of the Transporter , make sure that no MUs are located on the storage places that will be deleted by this action! Either delete these MUs or move them to another storage place on the smaller loading space.

For loaded Transporters for which you activated the Loading Space Type &gt; Store , Plant Simulation distributes the animation points, onto which it places loaded MUs , according to the dimension that you typed in. Plant Simulation computes the distances between the animation points as follows:

- The distance in the X-Direction (horizontal) is the length of the loaded object in pixels divided by the X-Dimension .
- The distance in the Y-Direction (vertical) is the width of the loaded object in pixels divided by the Y-Dimension .

**Note**

For computing the dimension in pixels, compare the Scaling Factor .

If either the distance in the X-Direction or in the Y-Direction is smaller than 4 pixels, Plant Simulation does not show any MUs at all but draws a pattern in a 2D Only model to signify that the object is not empty.

As long as the loading space is half empty, Plant Simulation shows a hatch pattern. If the loading space is more than half full, Plant Simulation shows a checker pattern.

<!-- image -->

**SimTalk**

YDim [SimTalk] - Transporter

XDim [SimTalk] - Transporter

ZDim [SimTalk] - Transporter

Capacity [SimTalk] - MUs

setDim [SimTalk]

See also

Type [loading space]

###### Z-Dimension [Transporter]

When you select the loading space of Type &gt; Store , Plant Simulation activates the text box Z-Dimension . Type in the dimension of the loading space along the z-axis.

<!-- image -->

The Z-Dimension enables to stack parts on the loading space of type Store of the Transporter . The loading Capacity is the product of X-Dimension times Y-Dimension times Z-Dimension .

If you decrease the dimension of the loading space of the Transporter , make sure that no MUs are located on the storage places that will be deleted by this action! Either delete these MUs or move them to another storage place on the smaller loading space.

SimTalk

ZDim [SimTalk] - Transporter

YDim [SimTalk] - Transporter

XDim [SimTalk] - Transporter

Capacity [SimTalk] - MUs

setDim [SimTalk]

See also

Unload Stacked Parts

MUHeightWithContent [SimTalk]

###### Length [text box] - loading space

When you select the loading space of Type &gt; Track or Line , Plant Simulation activates the text box Length .

<!-- image -->

Type in the Length of the loading space in meters.

**Note**

The animation on the length-oriented loading space requires an animation line in 2D. As Plant Simulation does not create the animation line automatically, you have to create it in the icon of the object. For vector graphics we defined the animation line, you cannot change it.

**Note**

The Length of the loading space is independent of the MU Length of the Transporter as such in 2D and in 3D.

**SimTalk**

LoadBayLength [SimTalk] - Transporter

See also

Type [loading space]

###### Capacity [text box] - Transporter

For the loading space of Type &gt; Track or Line , Plant Simulation activates the text box Capacity . Type in the Capacity , i.e., the maximum number of MUs that may be located on the loading space in their entirety or in part. Type in -1 for an infinite capacity.

<!-- image -->

**SimTalk**

Capacity [SimTalk] - Transporter

See also

Type [loading space]

###### Speed [text box] - Transporter

When you select the loading space of Line , Plant Simulation activates the text box Speed .

<!-- image -->

Type in the Speed with which the loading space of the Transporter moves. When you activate Acceleration , the speed of the loading space is the same as its Current Speed . You can also enter -1 for an infinite speed.

SimTalk

LoadBaySpeed [SimTalk] - Transporter

Type [loading space]

###### Current Speed [text box] - loading space

When you select the loading space of Type &gt; Line and activate Acceleration , Plant Simulation activates the field Current Speed .

<!-- image -->

Here Plant Simulation shows the actual speed with which the loading space of the Transporter moves at this point in time if Acceleration is active.

SimTalk

LoadBayCurrentSpeed [SimTalk]

Type [loading space]

###### Accumulating [check box] - Transporter

To make the MUs accumulate on the loading space of the Transporter , select this check box. This enables the MUs to move front to end to each other if the exit of the loading space is blocked.

<!-- image -->

When you select the loading space of Type &gt; Line , Plant Simulation activates the check box Accumulating .

To make the parts retain their distance to each other , i.e., to make all succeeding parts stop moving if the preceding part cannot exit the loading space, clear the check box. If the loading space is blocked, it stops, i.e., it reduces its Speed to 0.

<!-- image -->

**SimTalk**

Accumulating [SimTalk] - Transporter

See also

Type [loading space]

###### Backwards [check box] - loading space

To make the loading space of Transporter itself and the MUs on it move backward select this check box.

<!-- image -->

When you select the loading space of Type &gt; Line , Plant Simulation activates the check box Backwards .

To make them move forward , clear the check box.

**Note**

Here moving forward or in reverse are not properties of the Transporter , but of the loading space moving on it!

If you cleared Acceleration of the loading space, the loading space reverses the direction into which it moves immediately without decelerating and accelerating.

If you selected Acceleration , the loading space slows down until its speed is 0. The loading space then reverses the direction into which it moves and accelerates until it reaches its final speed.

<!-- image -->

**SimTalk**

LoadBayBackwards [SimTalk]

See also

Type [loading space]

Backwards [Transporter]

###### Acceleration [check box] - loading space

To make the loading space of the Transporter increase its speed, select this. Type the speed, with which the length-oriented loading space accelerates into the text box Acceleration .

<!-- image -->

When you select the loading space of Type &gt; Line , Plant Simulation activates the check box Acceleration .

<!-- image -->

**SimTalk**

LoadBayAccelerationEnabled [SimTalk]

See also

Type [loading space]

###### Acceleration [text box] - loading space

When you select the loading space of Type &gt; Line and activate Acceleration , Plant Simulation enables the text box Acceleration . Type in the Acceleration with which the loading space of the Transporter increases its speed. You can type in any real number greater than or equal to 0.

<!-- image -->

<!-- image -->

**SimTalk**

LoadBayAcceleration [SimTalk]

See also

Type [loading space]

Acceleration [check box] - loading space

###### Deceleration [text box] - loading space

Type in the Deceleration with which the loading space of the Transporter reduces its speed. You can type in any real number greater than or equal to 0.

<!-- image -->

When you select the loading space of Type &gt; Line and activate Acceleration , Plant Simulation activates the text box Deceleration .

<!-- image -->

**SimTalk**

LoadBayDeceleration [SimTalk]

See also

Type [loading space]

**Controls [loading space]**

###### Controls [loading space]

To open the dialog into which you can enter the controls pertaining to the type of loading space you selected, click this button.

<!-- image -->

- The loading space of type Store provides the Entrance Control and the Exit Control .
- The loading space of type Track provides the Entrance Control , the Exit Control , the Backward Entrance Control , and the Backward Exit Control .

<!-- image -->

<!-- image -->

- The loading space of type Line provides the Entrance Control , the Entrance Control , the Backward Entrance Control , the Backward Exit Control , and the Speed Control .

**Note**

The Speed Control of the loading space of the Transporter provides the same functions as the Speed Control of the object Conveyor .

**Note**

Do not confuse the Speed Control of the loading space of type Line of the Transporter with the Speed Control of the Transporter as such.

**SimTalk**

| EntranceCtrl [SimTalk] - Transporter   | EntranceCtrlFront [SimTalk] - Transporter   | EntranceCtrlRear [SimTalk] - Transporter   |
|----------------------------------------|---------------------------------------------|--------------------------------------------|
| ExitCtrl [SimTalk] - Transporter       | ExitCtrlFront [SimTalk] - Transporter       | ExitCtrlRear [SimTalk] - Transporter       |
| BwEntranceCtrl [SimTalk] - Transporter | BwEntranceCtrlFront [SimTalk] - Transporter | BwEntranceCtrlRear [SimTalk] - Transporter |

<!-- image -->

| BwExitCtrl [SimTalk] - Transporter   | BwExitCtrlFront [SimTalk] - Transporter   | BwExitCtrlRear [SimTalk] - Transporter   |
|--------------------------------------|-------------------------------------------|------------------------------------------|
| LoadBaySpeedCtrl [SimTalk]           |                                           |                                          |

See also

Type [loading space]

**Sensors [Transporter]**

###### Sensors [Transporter]

To create sensors, click Sensors . This opens the dialog Sensor List where you define new sensors or modify or delete existing sensors.

<!-- image -->

When you select the loading space of Type &gt; Track or Line , Plant Simulation activates the button Sensors .

<!-- image -->

**Note**

Creating and manipulating sensors via SimTalk only works if you select the loading space Types &gt; Track or Line !

**Note**

The window Show Attributes and Methods ( F8 ) only shows the attributes and methods pertaining to the selected type of loading space. If you select Track for example, the window only shows the attributes and methods pertaining to the loading space of type Track , not those pertaining to the loading space of type Store or Line .

See also

Type [loading space]

Sensors [general description]

Create a Sensor [material flow objects]

\_Methods of Sensors

**\_Read-Only Attributes of Sensors**

**\_Attributes of Sensors**

##### Tab Routing

Tab Routing [Transporter]

Specify the settings for routing the Transporters on the tab Routing .

Part and Container also provide the tab Routing . As opposed to the Transporter , which drives on objects of type Track and TwoLaneTrack to its destination, Part and Container move to their destination on Conveyors .

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

###### Tab Routing [Transporter]

See also Work with Automatic Routing of the Transporter

Automatic Routing [Transporters driving freely]

###### Automatic Routing [Transporter]

To make the Transporter independently find the shortest route to its Destination Object , select this check box.

<!-- image -->

<!-- image -->

When searching for the shortest route, Plant Simulation uses all Connectors between the current location of the Transporter and its destination object.

- For Transporters driving on Tracks/TwoLaneTracks connected with Connectors to other simulation objects this applies:

Except for the destination object, the route consists of objects of type Track/TwoLaneTrack which are connected with Connectors . The route can also cover Sub-Frames or surrounding Frames , as long as the Tracks/TwoLaneTracks are connected with Connectors via objects of type Interface .

You can also type in a Route Weighting Attribute factor.

An Exit Control along the predicted route takes precedence over Automatic Routing , a predicted route on the other hand takes precedence over a Destination List . Thus, the Transporter can deviate from the predicted route. (Naturally you can always transfer the Transporter onto any position on a Track/TwoLaneTrack with a Method , which also would lead to a deviation.) In this case Plant Simulation automatically computes a new route from the current location of the Transporter to the Destination . If no route exists, which exclusively leads to the Destination on Tracks/TwoLaneTracks , Plant Simulation deactivates Automatic Routing until the Transporter is transferred onto a Track/TwoLaneTrack from which on the route exists again. While Automatic Routing is deactivated, the default exit behavior, i.e., the Exit Strategy , which you selected, applies.

**Note**

As long as the Transporter follows the predicted route, the Exit Strategy of the covered Tracks/ TwoLaneTracks is irrelevant.

**Note**

When you click OK or Apply in the dialog of the Transporter Plant Simulation computes the route anew. When you inserted or deleted Connectors before that, the Transporters might now take a different route. In addition, Plant Simulation also reevaluates the Destination when you click OK or Apply . If you entered a relative path to the destination and the Transporter is located in a Sub-Frame , for example, the Transporter will not find the Destination or the Destination might even reference a different object.

**Note**

If you activated Automatic Routing and also entered a Driving Control , Automatic Routing takes precedence. The Driving Control will only be called if the Transporter does not find a route and Automatic Routing is thus deactivated. The Driving Control will be called, when you did not type in an Exit Control and the Transporter could move to several successors.

**Note**

For tugger trains Automatic Routing only works, when you type the Destination into the tractor .

- For Transporters , which drive freely within the area, this applies:

Except for the destination object, the route consists of objects of type Track or Marker , which are connected with Connectors . The route can also cover Sub-Frames or surrounding Frames , as long as the Markers/Tracks are connected with Connectors via objects of type Interface .

You can also type in a Route Weighting Attribute factor.

**Note**

When you click OK or Apply in the dialog of the Transporter Plant Simulation computes the route anew. When you inserted or deleted Connectors before that, the Transporters might now take a different route. In addition, Plant Simulation also reevaluates the Destination , when you click OK or Apply . If you entered a relative path to the destination and the Transporter is located in a Sub-Frame , for example, the Transporter will not find the Destination or the Destination might even reference a different object.

Part and Container also provide Automatic Routing . Their specific behavior is described there.

SimTalk

AutomaticRouting [SimTalk] - Transporter

RouteWeightingAttr [SimTalk] - Transporter

RoutingCtrl [SimTalk]

Destination [SimTalk] - Transporter

See also

Automatic Routing [Transporters driving freely]

Route to Destination [Transporter]

Destination [text box] - Transporter

getRouteLength [SimTalk] - Track

HasRouteToDestination [SimTalk] - Transporter

**setRoute [SimTalk] - Transporter**

###### Automatic Routing [Transporters driving freely]

To make the Transporter independently find the shortest route to its Destination Object , select this check box.

<!-- image -->

<!-- image -->

When searching for the shortest route, Plant Simulation uses all Connectors between the current location of the Transporter and its destination object.

Except for the destination object, the route consists of objects of type Marker or Track , which are connected with Connectors . The route can also cover sub-Frames or surrounding Frames , as long as the Tracks are connected with Connectors .

You can also enter a Route Weighting Attribute factor.

**Note**

When you click OK or Apply in the dialog of the Transporter Plant Simulation predicts the route anew. When you inserted or deleted Connectors before that, the Transporters might now take a different route. In addition, Plant Simulation also reevaluates the Destination , when you click OK or Apply . If you entered a relative path to the Destination and the Transporter is located in a sub-Frame , for example, the Transporter will not find the Destination or the Destination might even reference a different object.

SimTalk

AutomaticRouting [SimTalk] - Transporter

RouteWeightingAttr [SimTalk] - Transporter

RoutingCtrl [SimTalk]

See also

Route to Destination [Transporter]

Destination [text box] - Transporter

getRouteLength [SimTalk] - Track

HasRouteToDestination [SimTalk] - Transporter

setRoute [SimTalk] - Transporter

###### Reset Destination When at Destination [Transporter]

To make the Transporter reset the destination and the route to the destination object, when the Transporter arrived at the destination , select this check box.

<!-- image -->

The Destination is reset at the same point in time as the attribute DestinationWasReached , namely when leaving the Destination .

If the Transporter arrived at the destination and if no new destination is set or if the destination is not reset, the Transporter again tries to find a route to the same destination. This can be useful in certain exceptional cases, but will probably be not useful in most cases.

If the destination is a DataTable or a list object , the destination will only be reset when the last object in the DataTable or list object has been reached.

If the check box is selected, the DataTable will be processed once only.

If the check box is cleared, the DataTable will be processed cyclically.

SimTalk

ResetDestinationWhenAtDestination [SimTalk] - Transporter

See also

Destination [text box] - Transporter

DestinationWasReached [SimTalk]

Video on YouTube

[https://youtu.be/KH\_zcasaNp0?si=C5susO8SqRCzXxlO&amp;t=755](https://youtu.be/KH_zcasaNp0?si=C5susO8SqRCzXxlO&t=755)

**Stop at Destination**

###### Stop at Destination

To make a Transporter driving on Tracks/TwoLaneTracks stop at its Destination , select this.

A Destination can be a Track/TwoLaneTrack or an object that is set as the Destination of a sensor on a Track/TwoLaneTrack .

The Transporter activates the Destination Control as soon as it stopped at its Destination . To make the Transporter continue on its way, set the attribute Stopped to false.

**Note**

The Transporter only stops at the Destination if you also selected the check box Reset Destination when at Destination . This prevents you from directly using this setting to always send a Transporter to the same Destination and make it stop there on a circular course.

**Note**

Stop at Destination does not affect freely driving Transporters and Transporters that are part of a tugger train .

SimTalk

StopAtDestination [SimTalk]

See also

Destination [text box] - Transporter

Destination Control

Reset Destination When at Destination [Transporter]

DestinationWasReached [SimTalk]

Stopped [SimTalk] - MUs

###### Destination [text box] - Transporter

Click the ellipsis button and select the Destination Object in the dialog Select Object to which the Transporter drives.

<!-- image -->

The Transporter automatically finds the destination object, which you typed in, using the destination lists of the objects of type Track/TwoLaneTrack .

If you activate Automatic Routing , you do not need to define Destination Lists at all. The Transporter will automatically find its Destination object. If a sensor, into which you typed this destination object, is the Destination , can be reached on a shorter route than the destination object itself, then automatic routing directs the Transporter to this sensor .

If the Destination is a TwoLaneTrack , you can also select the Destination Lane , A or B .

**Note**

For tugger trains Automatic Routing only works if you type in the Destination into the tractor .

**Note**

The Destination can also be an Interface or a Frame . If it is a Frame , the Transporter drives to the Interface which can be reached on the shortest route.

You can also type in a table or a list as the Destination . This list or table can be a DataList , a DataQueue , a DataStack , or a DataTable which you inserted into a Frame . It can also be a user-defined attribute or a Variable of data type table , list , queue , or stack . The list or table has to have the column type object . The Transporter then covers all Destination Objects in the list or table one after the other.

- DataTable ( table ): Plant Simulation cyclically processes the DataTable . The Transporter always heads for the Destination Object which is located on the table row to which the attribute DestinationListRow of the Transporter points.

**Note**

In most cases the DataTable will only have a single column. You can also type in any data into additional columns though.

- DataList ( list ): Plant Simulation treats the DataList as a DataTable with one column.
- DataQueue or DataStack ( queue or stack ): The Transporter always drives to the first object in the DataQueue or the DataStack . As soon as the Destination is reached, Plant Simulation removes the first object from the list. The Transporter then drives to the new first object in the list.

**Note**

If the Transporter has reached its Destination , it immediately picks the next destination from the list or table. If the Destination was a sensor , Plant Simulation already determines the next Destination before the Sensor Control is called. To set the immediate next destination in the control, it does not suffice to change the list or table respectively, but you also have to reassign the attribute Destination of the Transporter afterward.

Part and Container also provide the Destination . Their specific behavior is described there.

SimTalk

Destination [SimTalk] - Transporter

DestinationListRow [SimTalk]

See also

Stop at Destination

Create a Sensor [material flow objects] in the Step-by-Step Help

Sensors [general description]

Select Object

setRoute [SimTalk] - Transporter

setRouteFromCoordinates [SimTalk]

setRouteSegments [SimTalk]

Video on YouTube

[https://youtu.be/PYXYutlaGOs?si=6ZNwfhIGkAQHK4ll&amp;t=725](https://youtu.be/PYXYutlaGOs?si=6ZNwfhIGkAQHK4ll&t=725)

###### Route Weighting Attribute - Transporter

Type in the name of the attribute, which is used for controlling the weighting of routes on which the Transporter drives.

<!-- image -->

Transporters Driving on Tracks/TwoLaneTracks

<!-- image -->

For Transporters driving on Tracks/TwoLaneTracks connected with Connectors to other simulation objects this applies:

The value of the route weighting attribute determines the name of a user-defined attribute of a Track/ TwoLaneTrack . The user-defined attribute has to have the data type real .

The lengths of the Track/TwoLaneTrack will be multiplied with the value you assigned to the user-defined attribute . If you assign a negative value to the user-defined attribute , this Track/TwoLaneTrack will not be used for automatic routing. Tracks/TwoLaneTracks , which do not have a user-defined attribute with the name designated by the route weighting attribute, use the factor 1.0.

For TwoLaneTracks you can specify the Route Weighting Attribute for Lane A and Lane B separately. To do so, create two user-defined attributes of data type real in the TwoLaneTrack . Then give them the name of the Route Weighting Attribute followed by \_A or \_B respectively.

<!-- image -->

Plant Simulation only considers the Route Weighting Attribute if no common Route Weighting Attribute exists that applies for both lanes.

**Note**

If you assign a value to the attribute RouteWeightingAttr , Plant Simulation automatically re-computes the destination.

Transporters Driving Freely Within the Area

For Transporters driving freely within the area, this applies:

The value of the route weighting attribute determines the name of a user-defined attribute of the objects Marker, Track or Connector . The user-defined attribute has to have the data type real or be a Method that returns a value of data type real .

For Connectors between two Markers/Tracks the distance between these objects will be multiplied with the value you assigned to the user-defined attribute .

For Markers all distances leading to this Marker will be multiplied with the value you assigned to the user-defined attribute . A negative value prevents the Marker from being used for automatically computed routes.

For Tracks the length will be multiplied with the value you assigned to the user-defined attribute . A negative value prevents the Track from being used for automatically computed routes.

Connectors/Markers/Tracks , which do not have a user-defined attribute with the name designated by the route weighting attribute, use the factor 1.0.

Part and Container also provide the Route Weighting Attribute . Their specific behavior is described there.

**SimTalk**

**RouteWeightingAttr [SimTalk] - Transporter**

**Default Curve Radius [text box]**

###### Default Curve Radius [text box]

Type in the Default Curve Radius with which the freely driving Transporter approaches the Markers .

<!-- image -->

**Remarks**

Plant Simulation uses this value for computing the route of the AGV that drives freely within the area. The Default Curve Radius sets the size of the curvature/fillet at the Markers .

The AGV passes the Marker on a curve segment with the specified Default Curve Radius . The AGV calls the Arrival Control of the Marker at the point of the curve segment at which it is closest to the Marker .

The distance of the Marker should be at least twice the Default Curve Radius at coordinates where the AGV needs to change its direction.

If a standing AGV cannot drive to the first Marker using the specified Default Curve Radius , the AGV rotates on the spot with the defined Rotation Speed , if possible, and then drives in a straight line toward the next Marker .

**Note**

You cannot change the Default Curve Radius if the Transporter is already driving on a route.

Make the AGV Rotate on the Spot with the Rotation Speed

To make the AGV rotate on the spot with the Rotation Speed you set, type in 0 as the Default Curve Radius .

<!-- image -->

Once the AGV arrives at the waypoint of the route, it decelerates to 0, rotates on the spot with the specified Rotation Speed , and accelerates again afterwards.

<!-- image -->

<!-- image -->

While the Transporter rotates on the spot with a Default Curve Radius of 0, the location of the Transporter is void until it reaches its Destination . This means, that observers and waituntil-instructions will be called.

**Note**

In previous versions the AGV did not use the Rotation Speed when rotating on the spot with a Default Curve Radius of 0.

To use the behavior of previous versions, type in -1 as the Rotation Speed for the respective AGVs .

**Note**

To rotate on the spot the AGV needs to decelerate to the Speed 0. When you assign a new route to an AGV with activated Acceleration while the AGV is currently driving, this might in some cases cause the AGV to first decelerate to 0, then turn, and finally drive back to the start of the new route.

SimTalk

DefaultCurveRadius [SimTalk]

See also

Speed [Transporter]

Rotation Speed [text box]

Marker

setRoute [SimTalk] - Transporter

**Rotation Speed [text box]**

###### Rotation Speed [text box]

Type in the Rotation Speed with which the AGV rotates on the spot if you called the method rotate .

<!-- image -->

Type in a real number greater than 0 . The Rotation Speed is measured in degrees per second.

Type in -1 to make the AGV rotate on the spot instantaneous, without using any time.

Make the AGV Rotate on the Spot

To make the AGV rotate on the spot with the Rotation Speed you set, type in 0 as the Default Curve Radius .

<!-- image -->

Once the AGV arrives at the waypoint of the route, it decelerates to 0, rotates on the spot with the specified rotation speed , and accelerates again afterward.

**Note**

In previous versions the AGV did not use the Rotation Speed when rotating on the spot with a Default Curve Radius of 0.

To use the behavior of previous versions, type in -1 as the Rotation Speed for the respective AGVs .

SimTalk

RotationSpeed [SimTalk]

See also

Default Curve Radius [text box]

Curve Speed [text box]

Marker , object

rotate [SimTalk] - Transporter

**setRoute [SimTalk] - Transporter**

**Curve Speed [text box]**

###### Curve Speed [text box]

Type in the Curve Speed with which the Transporter drives through curves on the route.

<!-- image -->

Type in a real number greater than 0 .

The default value -1 designates that the curve speed is not active. The Transporter drives through curves on the route with its normal Speed . This also applies if the Curve Speed is higher than the normal Speed .

The Transporter decelerates in time so that it reaches the specified Curve Speed at the start of the curve and then accelerates again after it has passed the curve.

**Note**

This applies to Transporters driving freely within the area of the model as well as to Transporters driving on Tracks .

**Note**

The Transporter does not maintain the Curve Speed on a lane of a TwoLaneTrack .

Only the tractor of a tugger train maintains the Curve Speed , not the trailers.

**Note**

A Transporter driving on Tracks can only slow down in time to meet the Curve Speed if it either has a route to a destination or if each Track only has a single successor.

If the route network contains intersections, the Transporter can only start slowing down to the Curve Speed if it drove onto the succeeding Track at an intersection.

SimTalk

CurveSpeed [SimTalk]

setRoute [SimTalk] - Transporter

See also

Marker

##### Tab Failures

Define failures as described under the Tab Failures .

**Note**

A failure of the Transporter as such does not fail the loading space . This also affects the Resource Statistics of Moving Resources .

Tab Controls

Tab Controls

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

##### Tab Controls

- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

In addition, you can select the Shift Calendar .

See also

Driving Control

Routing Control

Destination Control

Collision Control [Transporter]

Distance Control Overview

Speed control [Transporter]

###### Driving Control

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Driving Control , which sets to which successor the Transporter drives when it has covered the entire Track/TwoLaneTrack .

<!-- image -->

The Driving Control applies, if you did not specify an Exit Control in the Track/TwoLaneTrack .

<!-- image -->

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.

**Driving Control**

- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

SimTalk

DriveCtrl [SimTalk]

Stopped [SimTalk] - MUs

See also

Select Object [for controls]

Stopped [MUs]

###### Routing Control

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Routing Control , which is called when Plant Simulation automatically predicted a route to the Destination .

<!-- image -->

Within this control you might, for example, read out the newly computed route with the method getRoute . You might then manipulate this route and assign the changed route with the method setRoute . You might also check if the Entrance or the Exit of one of the Tracks/TwoLaneTracks along the predicted route is closed and then circumvent this Track/TwoLaneTrack .

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

**Create a Control that is a Method of the Object**

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.

**Routing Control**

- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

SimTalk

RoutingCtrl [SimTalk]

See also

Select Object [for controls]

getRoute [SimTalk] - Transporter

setRoute [SimTalk] - Transporter

###### Destination Control

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Destination Control , which is called after the Transporter has entered and covered the specified Destination and arrives at the exit of the Destination .

<!-- image -->

After setting the destination in the Destination Control , you have to make the Transporter drive on by moving it with the method move .

Plant Simulation also executes the Destination Control if you used the TargetDistance or TargetPosition , and the Transporter has covered the distance.

If you are working with automated guided transport systems , the Destination Control is called when the Transporter has reached the end of the route, which you set with the method setRoute , rotate , drive , or setRouteSegments .

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

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

SimTalk

DestCtrl [SimTalk]

See also

Select Object [for controls]

Destination [SimTalk] - Transporter

DestinationWasReached [SimTalk]

Marker

setRoute [SimTalk] - Transporter

###### Collision Control [Transporter]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Collision Control . The faster Transporter calls the Collision Control when it collides with a slower Transporter .

<!-- image -->

The faster Transporter is the successor that drives with a higher speed than its predecessor and collides with it when the distance between both Transporters reaches 0.

For tugger trains this applies: When a tugger train collides, the Collision Control of the tractor will always be triggered. Within the control method the anonymous identifier @ is the Transporter , which actually collides, while the anonymous identifier ? designates the tractor of the tugger train .

**Note**

The Collision Control only applies to Transporters that drive on Tracks or TwoLaneTracks .

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Create a Control that is a Method of the Object

You can also create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

SimTalk

CollisionCtrl [SimTalk] - Transporter

See also

Select Object [for controls]

Collided [SimTalk]

Program the Collision Control

Distance Control

Distance Control Overview

The Distance Control provides a number of settings.

See also

Work with a Distance Control without AGVPool

Prevent AGVs from Colliding

###### Distance Control

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Distance Control of the Transporter .

- The Distance Control of the Transporter that drives on a Track or TwoLaneTrack provides these settings:

<!-- image -->

<!-- image -->

The Transporter calls the control when it gets closer to any other MU than the Distance which you typed in. Plant Simulation calls the control when the distance becomes either too small or too great.

**Note**

The Distance Control only recognizes objects that can be located on a Track/TwoLaneTrack , it does not recognize Workers or graphics of objects.

- The Distance Control of the Automated Guided Vehicle ( AGV ), which drives freely within the space of the model, provides these settings:

<!-- image -->

The AGV calls the control you typed in when another AGV enters or exits one of its safety zones.

**Note**

The Distance Control only recognizes AGVs which are associated with an AGVPool .

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

**Create a Control that is a Method of the Object**

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

The standard distance control as a user-defined attribute looks like this:

```simtalk
param IsInsideZone : boolean, ZoneNumber : integer -- param DistanceIsBelowLimit: boolean
if ?.AGVPool /= void
	if ZoneNumber = 1
		var numMUInZone1 = ?.getSafetyZoneContent(1).dim
		if IsInsideZone
			if numMUInZone1 = 1 then ?.StoppingCounter += 1
			end
		else
			if numMUInZone1 = 0 then ?.StoppingCounter -= 1
			end
		end
	end
	var numMUInZone2 = ?.getSafetyZoneContent(2).dim
	if numMUInZone2 > 0
		?.Speed := ?.Origin.speed * 0.7
		if ?.curveSpeed /= -1
			?.curveSpeed := ?.Origin.curveSpeed * 0.7
end
else
	?.Speed := ?.Origin.Speed
	if ?.curveSpeed /= -1
		?.curveSpeed := ?.Origin.curveSpeed
	end
end
end
```

**Parameters**

If the Transporter is not an AGV , the parameter DistanceObjectBelowLimit is true if the distance becomes too small. It is false if the distance becomes too great.

If the Transporter is an AGV , the alternative parameter set applies.

- The parameter IsInsideZone of data type boolean is true if another AGV enters one of the Safety Zones . It is false when the AGV exits the Safety Zone again.
- The parameter ZoneNumber of data type integer has the value 1 for Safety Zone 1 and the value 2 for safety zone 2 . It has the value 0 if the Transporter is not an AGV .

The anonymous identifier ? designates the part ( MU ) for which you typed in the Distance Control and the Distance or the Safety Zones . The anonymous identifier @ designates the part ( MU ) for which the distance became too great or too small or which entered or exited a Safety Zones . At the point in time at which the Distance Control is called @ is located in front of ? in the direction of motion of ? , or it is located in one of the Safety Zones of ? in the direction of motion of ? .

Distance Control for Tugger Trains

For tugger trains you have to type the control into the tractor. When a tugger train falls below the Distance you typed in, the Distance Control of the tractor will be triggered. Within the control method the anonymous identifier @ is the MU to which the distance is too small, while the anonymous identifier ? designates the tractor of the train.

**SimTalk**

DistanceCtrl [SimTalk] DistanceObjectBelowLimit [SimTalk] getSafetyZoneContent [SimTalk] SafetyZonesEmpty [SimTalk] _3D.ShowSafetyZones [SimTalk]

See also Select Object [for controls] Distance [SimTalk] Work with a Distance Control without AGVPool Prevent AGVs from Colliding

**Distance [text box] - distance control**

Type in the Distance from which on the Transporter calls the Distance Control . It prevents the Transporters from getting too close to each other or from moving away too far from each other. Type in a value greater than 0 .

- The Distance Control of the Transporter that drives on a Track or TwoLaneTrack provides these settings:
- The Distance Control of Automated Guided Vehicles ( AGV ), which you defined in the AGVPool and which drive freely within the area, provides these settings:

<!-- image -->

<!-- image -->

<!-- image -->

Length Zone 1

Length Zone 2

ΔWidth Zone 1

ΔWidth Zone 2

SimTalk

Distance [SimTalk]

getSafetyZoneContent [SimTalk]

SafetyZones [SimTalk]

SafetyZonesEmpty [SimTalk]

See also Select Object Distance Control Work with a Distance Control without AGVPool Prevent AGVs from Colliding \_3D.ShowSafetyZones [SimTalk] Edit 3D Properties &gt; Tab Appearance &gt; Show Safety Zones DistanceObjectBelowLimit [SimTalk]

**Length Zone 1**

Type in the Length of Safety Zone 1 .

<!-- image -->

Type in a value greater than or equal to 0 . The Length of Zone 1 has to be smaller than or equal to the Length of Zone 2 .

**Note**

If you type in 0 , more accurately a value smaller than 1cm, Plant Simulation deactivates Zone 1 and the surrounding Zone 2 .

The zones are attached in the direction of motion to the AGV , to the Front in the forward direction, to the Rear in the backward direction.

The values relate to the respective side of the AGV . Length applies to forward and backward respectively and ΔWidth toward both sides.

The entire Length of a zone corresponds to its length, the entire Width to the width of AGV plus twice the ΔWidth .

<!-- image -->

To show the defined Safety Zones of the Transporter , select Edit 3D Properties &gt; Tab Appearance &gt; Show Safety Zones .

<!-- image -->

An Automated Guided Vehicle (AGV) calls the Distance Control once another AGV enters or exits one of its safety zones.

You cannot change the safety zones of an AGV if other AGVs are located in one of the safety zones.

SimTalk

SafetyZones [SimTalk]

\_3D.ShowSafetyZones [SimTalk]

See also

Edit 3D Properties &gt; Tab Appearance &gt; Show Safety Zones

Prevent AGVs from Colliding

**ΔWidth Zone 1**

Type in the ΔWidth on both sides of the AGV (in addition to the width of the AGV itself) of Safety Zone 1 .

<!-- image -->

Type in a value greater than or equal to 0 . The ΔWidth of Zone 1 has to be smaller than or equal to the ΔWidth of Zone 2 .

**Note**

If you set the ΔWidth of a zone to a value that causes the entire width of the zone to fall below 1cm for an AGV of width 0, this zone will be deactivated. We advise against setting the Width of an AGV to 0.

The zones are attached in the direction of motion to the AGV , to the Front in the forward direction, to the Rear in the backward direction.

The values relate to the respective side of the AGV , Length applies to forward and backward respectively and ΔWidth toward both sides. The entire Length of a zone corresponds to its length, the entire width to the width of AGV plus twice the ΔWidth .

<!-- image -->

To show the defined Safety Zones of the Transporter , select Edit 3D Properties &gt; Tab Appearance &gt; Show Safety Zones .

<!-- image -->

An Automated Guided Vehicle (AGV) calls the Distance Control once another AGV enters or exits one of its safety zones.

You cannot change the safety zones of an AGV if other AGVs are located in one of the safety zones.

SimTalk

SafetyZones [SimTalk]

\_3D.ShowSafetyZones [SimTalk]

See also

Select Object [for controls]

AGV [text box]

Edit 3D Properties &gt; Tab Appearance &gt; Show Safety Zones

Prevent AGVs from Colliding

**Length Zone 2**

Type in the Length of Safety Zone 2 .

<!-- image -->

Type in a value greater than or equal to 0 . The Length of Zone 1 has to be smaller than or equal to the Length of Zone 2 .

**Note**

If you type in 0, more accurately a value smaller than 1cm, Plant Simulation deactivates Zone 2 .

The zones are attached in the direction of motion to the AGV , to the Front in the forward direction, to the Rear in the backward direction.

The values relate to the respective side of the AGV . Length applies to forward and backward respectively and ΔWidth toward both sides. The entire Length of a zone corresponds to its length, the entire width to the width of AGV plus twice the ΔWidth .

<!-- image -->

To show the defined Safety Zones of the Transporter , select Edit 3D Properties &gt; Tab Appearance &gt; Show Safety Zones .

<!-- image -->

An Automated Guided Vehicle (AGV) calls the Distance Control when another AGV enters or exits one of its safety zones.

You cannot change the safety zones of an AGV if other AGVs are located in one of the safety zones.

SimTalk

SafetyZones [SimTalk]

\_3D.ShowSafetyZones [SimTalk]

See also

Edit 3D Properties &gt; Tab Appearance &gt; Show Safety Zones

Prevent AGVs from Colliding

**ΔWidth Zone 2**

Type in the ΔWidth on both sides of the AGV (in addition to the width of the AGV itself) of Safety Zone 2 .

<!-- image -->

Type in a value greater than or equal to 0 . The ΔWidth of Zone 1 has to be smaller than or equal to the ΔWidth of Zone 2 .

**Note**

If you set the ΔWidth of a zone to a value that causes the entire width of the zone to fall below 1cm for an AGV of width 0, this zone will be deactivated. We advise against setting the Width of an AGV to 0.

The zones are attached in the direction of motion to the AGV , to the Front in the forward direction, to the Rear in the backward direction.

The values relate to the respective side of the AGV , Length applies to forward and backward respectively and ΔWidth toward both sides. The entire Length of a zone corresponds to its length, the entire width to the width of AGV plus twice the ΔWidth .

<!-- image -->

To show the defined Safety Zones of the Transporter , select Edit 3D Properties &gt; Tab Appearance &gt; Show Safety Zones .

<!-- image -->

An Automated Guided Vehicle (AGV) calls the Distance Control once another AGV enters or exits one of its safety zones.

You cannot change the safety zones of an AGV if other AGVs are located in one of the safety zones.

SimTalk

SafetyZones [SimTalk]

\_3D.ShowSafetyZones [SimTalk]

See also

AGV [text box]

Edit 3D Properties &gt; Tab Appearance &gt; Show Safety Zones

Prevent AGVs from Colliding

###### Speed control [Transporter]

Modifies the built-in behavior of the object. The object calls the Method depending on different circumstances.

<!-- image -->

**Remarks**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Speed Control .

Plant Simulation executes the Speed Control :

- When the Transporter reaches its final speed after accelerating or decelerating or when it stops after decelerating.
- When the Speed of the Transporter without a Speed Control changes when a Destination is set or reached
- When a Transporter , which drives freely within the area, and for which you activated Curve speed , reaches the curve speed the start or the end of a curve.

**Note**

Do not confuse the Speed Control of the Transporter as such with the Speed Control of the loading space of type Line of the Transporter ( Load Bay &gt; Controls ).

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

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

**SimTalk**

SpeedCtrl [SimTalk] - Transporter

See also

Select Object [for controls]

###### Shift Calendar [Transporter]

The ShiftCalendar contains the data of the shifts in your installation and controls during which shifts the Transporter works.

<!-- image -->

Click the ellipsis button and select the ShiftCalendar in the dialog Select Object .

Or you can select the ShiftCalendar in a Frame , drag it to the text box and drop it there.

SimTalk

ShiftCalendarObject [SimTalk] - Frame

See also

Select Object [for controls]

ShiftCalendar [object]

Tab Battery

Tab Battery

Select the settings for running the Transporter off of a battery on this tab. The settings are listed in the table of contents to the left.

The battery is either full, on reserve, or empty. If the battery is empty, the Transporter stops, provided it is located on a Track/TwoLaneTrack , and remains there until the battery is recharged again. If you want the Transporter to move on afterward, you can tell it to do so with the attribute Stopped .

<!-- image -->

Regardless of its location and state, the Transporter always consumes energy coming off the basic battery charge, see Basic Consumption . If the Transporter moves along a Track/TwoLaneTrack , it has a Driving Consumption , which does not depend on the Speed you set.

Charge the battery with the Charge Control . Type the Battery Charge into the text box. The Transporter calls the Charge Control , when the battery is:

- Empty ( Charge is 0).
- Full ( Charge equals Capacity ). To let you know that the battery is fully charged now.
- On reserve ( Charge equals Reserve ). While charging a low battery, the Transporter does not activate the charge control if the charge arrives at the Reserve value from the low point.

Charging the battery starts when you assign true to the attribute BatCharging . You can terminate it at any time by assigning false .

Type the charging current into the text box Charge Current As soon as the battery is fully charged, the Transporter terminates charging by automatically assigning false to the attribute BatCharging . Then, the Transporter calls the Battery Charge Control , which may activate it again, for example by calling the attribute Stopped .

**Note**

The battery charge is independent of failures and/or pauses . The Basic Consumption also applies while charging the battery!

To view Battery statistics in the Statistics Report , click the object in the Frame , and press F6 ( Show Statistics Report ), or click Show Statistics Report on the Home ribbon tab.

###### Battery [check box]

To run the Transporter off of a battery, select this check box.

<!-- image -->

To operate it without battery power, clear the check box.

SimTalk

BatteryUsed [SimTalk]

See also

Configure Battery-powered Operation of the Transporter

**Charge**

###### Charge

Type in the active Charge of the battery in ampere hours (Ah).

<!-- image -->

You can type in any value between 0, which means that the battery is empty, and the Capacity of the battery.

**Note**

The Transporter does not automatically update the value of the battery charge during a simulation run when the tab is displayed on screen. To update it, select View &gt; Refresh or press F5 .

SimTalk

BatCharge [SimTalk]

BatCharging [SimTalk]

See also

Capacity [text box] - battery

Configure Battery-powered Operation of the Transporter

###### Basic Consumption

Type in the Basic Consumption of the battery in ampere (A).

<!-- image -->

Remarks

As long as the Transporter is running under battery power, the battery consumes the energy you enter here, no matter if it is moving or not.

The battery charge is independent of failures and/or pauses . The Basic Consumption also applies while charging the battery!

SimTalk

BatBasicCons [SimTalk]

See also

Configure Battery-powered Operation of the Transporter

**Driving Consumption**

###### Driving Consumption

Type in the Driving Consumption , i.e., the value for the energy the Transporter consumes in ampere (A) while it drives under battery power.

<!-- image -->

SimTalk

BatDriveCons [SimTalk]

Capacity [text box] - battery

Type in the Capacity of the battery in ampere hours (Ah).

SimTalk

BatCapacity [SimTalk]

See also

Configure Battery-powered Operation of the Transporter

Reserve

Type in the Reserve Capacity of the battery in ampere hours (Ah).

<!-- image -->

Once the charge falls below the value you type in here, the Transporter calls the Charge Control in which you program how the battery is to be recharged.

SimTalk

BatReserve [SimTalk]

See also

Charge Control

Configure Battery-powered Operation of the Transporter

###### Charge Current

Type in a value for the Charge Current in ampere (A).

Remarks

The battery charge is independent of failures and/or pauses . The Basic Consumption also applies while charging the battery!

SimTalk

BatChargeCurrent [SimTalk]

See also

Configure Battery-powered Operation of the Transporter

**Charge Control**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Battery Charge Control which is called whenever the battery charge falls below the Reserve Value or when the charge is 0 or when it has reached the Capacity Value .

<!-- image -->

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

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

**SimTalk**

BatChargeCtrl [SimTalk]

See also

Select Object [for controls]

###### Reserve

Capacity [text box] - battery

Program the Battery Controls

##### Tab Graphics [Transporter]

Tab Graphics [Transporter]

Select settings for vector graphics of the Transporter on the tab Graphics .

See also

Graphics [tab, MUs, 2D]

##### Tab Product Statistics [MUs]

The tab Product Statistics is described under the Tab Product Statistics .

<!-- image -->

**See also**

Product Statistics [all MUs]

Product Statistics Values

Methods for Accessing Statistics of the MUs

\_Read-Only Attributes for Accessing Statistics of the MUs

##### Tab Statistics

Tab Statistics [Transporter]

The tab Statistics provides the check box Driving Statistics . It also shows the Statistics Values of the Transporter on the tab itself.

<!-- image -->

To view Driving Statistics of the Transporter [statistics report] in the Statistics Report , click the object in the Frame , and press F6 ( Show Statistics Report ), or click Show Statistics Report on the Home ribbon tab.

You can also click the object in the Frame with the right mouse button and select Show Statistics Report on the context menu.

See also

Tab Statistics [Container, Transporter] of MUs

Methods for Accessing Statistics of the MUs

###### Driving Statistics

To collect resource and driving statistics data for the Transporter and to display the most important statistical data on the tab itself, select this check box.

<!-- image -->

To deactivate the collection of driving statistics, clear the check box.

**Note**

Plant Simulation does not continuously update statistical data displayed in an open window during a simulation run!

Select View &gt; Refresh or press F5 .

To view Driving Statistics of the Transporter [statistics report] in the Statistics Report , click the object in the Frame , and press F6 ( Show Statistics Report ), or click Show Statistics Report on the Home ribbon tab.

SimTalk

ResStatOn [SimTalk] - MUs

**Statistics Values [Transporter]**

###### Statistics Values [Transporter]

The tab Statistics shows the driving statistics of the Transporter .

To view all statistics values that the Transporter collected, select View &gt; Statistics Report .

| Item English         | Description                                                                                                                                                                                                               | Read-only attribute                     | Item German       |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------|-------------------|
| Order Occupied       | Shows the time portion of its life-span during which the Transporter had an order and was loaded.                                                                                                                         | StatOrderOccPortion [SimTalk]           | Auftrag belegt    |
| Order Empty          | Shows the time portion of its life-span during which the Transporter had an order and was not loaded ( Empty ).                                                                                                           | StatOrderEmptyPorti on [SimTalk]        | Auftrag leer      |
| Home Driving         | Shows the time portion of its life-span during which the Transporter was returning to its base.                                                                                                                           | StatHomeDrivingPort ion [SimTalk]       | Heimfahrzeit      |
| Ready                | Shows the portion of the statistics collection period during which the Transporter was ready, meaning that it was not in one of the states Order occupied , Order empty , Home driving , Failed , Paused , or Unplanned . | StatTspReadyPortion [SimTalk]           | Bereit            |
| Failed               | Shows the portion of the statistics collection period during which the Transporter was Failed .                                                                                                                           | StatTspFailPortion [SimTalk]            | Gestört           |
| Paused               | Shows the portion of the statistics collection period during which the Transporter was Paused .                                                                                                                           | StatTspPausingPortio n [SimTalk]        | Pausiert          |
| Unplanned            | Shows the portion of the statistics collection period during which the Transporter was Unplanned ,i.e., was not scheduled to work to the statistics collection period.                                                    | StatTspUnplannedPo rtion [SimTalk]      | Ungeplant         |
| Relative Occupatio n | Shows the capacity-based ratio of the time during which the Transporter was occupied, not paused and not failed to the time the object was not paused and not failed.                                                     | StatRelativeOccupati on [SimTalk] - MUs | Relativ leer      |
| Relative Empty       | Shows the portion of the statistics collection period during which the Transporter was Empty .                                                                                                                            | StatEmptyPortion [SimTalk]              | Relative Belegung |
| Contents             | the number of MUs which are located on the Transporter .                                                                                                                                                                  | NumMU[SimTalk] - MUs                    | Inhalt            |
| Minimum Contents     | Shows the minimum number of MUs which were located on the Transporter .                                                                                                                                                   | StatMinNumMU [SimTalk] - MUs            | Minimaler Inhalt  |

| Item English      | Description                                                                                                                                                                                                                                                                                                | Read-only attribute                          | Item German              |
|-------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------|--------------------------|
| Maximum Contents  | Shows the maximum number of MUs which were located on the Transporter .                                                                                                                                                                                                                                    | StatMaxNumMU [SimTalk] - MUs                 | Maximaler Inhalt         |
| Entries           | Shows the number of MUs that entered the Transporter . When a MU enters the object, the object only counts the MU itself, not its contents: When a Transporter transporting several parts enters the object, the number of entries increases by 1, not by the number of parts located on the Transporter ! | StatNumIn [SimTalk] - MUs                    | Eingänge                 |
| Exits             | Shows the number of MUs that exited the Transporter . The rules described under Entries apply.                                                                                                                                                                                                             | StatNumOut [SimTalk] - MUs                   | Ausgänge                 |
| Traveled Distance | Shows the distance which the Transporter traveled on a Track/TwoLaneTrack or freely within the area of the model in meters.                                                                                                                                                                                | StatTraveledDistance [SimTalk] - Transporter | Zurückgelegte Wegstrecke |

To view Driving Statistics of the Transporter [statistics report] in the Statistics Report , click the object in the Frame , and press F6 ( Show Statistics Report ), or click Show Statistics Report on the Home ribbon tab.

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

View Menu

The View Menu provides commands to access its functions.

| Refresh [on View menu]                     | Forward Blocking List              |
|--------------------------------------------|------------------------------------|
| Show Statistics Report [on View menu]      | Targets                            |
| Show Attributes and Methods [on View menu] | Route to Destination [Transporter] |
| Contents [MUs]                             | Associated Shift Calendar          |
| Position [MUs]                             |                                    |

###### Route to Destination [Transporter]

Selects all Tracks along the predicted route in the Frame on which the Transporter drives toward its destination.

For TwoLaneTracks the command selects the respective lanes on which the Transporter drives.

<!-- image -->

If the command is deactivated, the Transporter did not find a route to the destination.

Drag the mouse over the Transporter to show its name, its current location, its destination, and the previous route in a Tooltip .

See also

getRoute [SimTalk] - Transporter

setRoute [SimTalk] - Transporter

setRouteSegments [SimTalk]

HasRouteToDestination [SimTalk] - Transporter

setRouteSegments [SimTalk]

##### setRouteFromCoordinates [SimTalk]

Tools Menu

Tools Menu

The Tools Menu provides these menu commands:

| Edit Controls > Fail Control [Transporter]   | Edit Observers [general description]   |
|----------------------------------------------|----------------------------------------|
| Edit Controls > Init Control [Transporter]   | 3D [create object]                     |
| Edit Controls > Pause Control [Transporter]  |                                        |

**Fail Control [Transporter]**

###### Fail Control [Transporter]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Fail Control , which is called once at the start of the simulation run during the init phase.

<!-- image -->

Plant Simulation executes the Fail Control whenever the Failed state of the Transporter changes. To accomplish this, either select the check box Failed or assign true to the attribute Failed .

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

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

The standard fail control as a user-defined attribute looks like this:

<!-- image -->

Within the control, you can access the object calling the control using the anonymous identifier ? .

**Parameters**

The Fail Control can define two optional parameters:

- The optional parameter FailureIsStarting of data type boolean sets if the failure starts ( true ) or ends ( false ).
- The optional parameter ProfileName of data type string sets the name of the failure profile that caused the failure.

**Note**

Provided the Fail Control declares both parameters, it will not only be called when the object changes to the failed -state or when the failed -state ends, but also each time when a failure profile is Failed or when the failure is removed.

Let's say failure profile 1 is already failed, and then you also fail failure profile2 in addition, then the Fail Control will still be called, although the object remains in the failed -state.

**SimTalk**

**FailCtrl [SimTalk]**

See also

Select Object [for controls]

Failed [MUs] - state

**Init Control [Transporter]**

###### Init Control [Transporter]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Init Control , which is called once at the start of the simulation run during the init phase.

<!-- image -->

The init controls are called before events are computed. The normal init methods on the other hand are called after the initial events have been computed.

Within the control you can access the object that triggered the control with the anonymous identifier ? . The Method can, for example, initialize important data structures.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

**Create a Control that is a Method of the Object**

You can also create a control which is a user-defined attribute of data type Method . To do so, right-click in the text box and select Create Control . This might look like this:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.ExitControlEnginePlant .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute ; deleting the name from the text box just deletes the name, but keeps the user-defined attribute.

SimTalk

**Stop Mode [drop-down list]**

See also

Select Object [for controls]

**Pause Control [Transporter]**

###### Pause Control [Transporter]

<!-- image -->

Click and select a Method in the dialog Select Object . Type in the source code of the Pause Control .

<!-- image -->

Plant Simulation executes the Pause Control whenever the Paused state of the Transporter changes. To accomplish this, either select the check box Paused or assign true to the attribute Pause .

Within the control, you can access the object starting the control using the anonymous identifier ? . You can also reference the control with the attribute PauseCtrl within methods.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_user-defined attribute\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

The standard pause control as a user-defined attribute looks like this:

<!-- image -->

Parameters

The Pause Control has two parameters.

- The parameter Duration of data type real sets the length of the pause . If the length of the pause is unknown, Plant Simulation passes -1. The same happens if the control is called at the end of the pause .
- The parameter NewValue of data type boolean sets that the control will only be called if the ShiftCalendar changes the state of the object.
- In addition, the object will not be put in the desired state. The Pause Control has to do this. The desired value is passed in the parameter NewValue .

The part still can be processed in its entirety before the object changes to the state paused .

**Note**

If the Pause Control has the parameters listed above, then the ShiftCalendar will not automatically change the state paused . This is useful to complete processing of a part and then pause the shift manually by setting the attribute Pause of the object to true .

Compare this example:

```simtalk
param Duration: real, NewValue: boolean
if ?.Cont /= void
	wait ?.Cont.RemainingProcTime
end
?.Pause := NewValue
```

**Note**

If the Pause Control does not have any parameters, Plant Simulation always calls the Pause Control when the state paused changes.

If the Pause Control has the parameters listed above, Plant Simulation only calls the Pause Control when the state paused is changed by the ShiftCalendar . The reason behind this is to prevent that the pause control calls itself when the state paused is set manually.

Pause Control [Transporter]

SimTalk PauseCtrl [SimTalk] See also Select Object [for controls] Paused [MUs] PauseCtrl [SimTalk]

##### Tabs Menu

Use the commands of the Tabs menu to show or hide individual tabs of the material flow objects. If you hide tabs that you do not need, Plant Simulation opens the dialog faster, and you can change to those tabs faster that you need in your daily work.

To apply the changed settings, click OK , close the dialog, and reopen it

The menu shows a check mark to the left of the displayed tabs.

The command Inherit turns inheritance of the displayed or hidden tabs in the dialog off or on.

<!-- image -->

##### Help Menu

The commands are described under the Help Menu .

**Methods of the Transporter**

