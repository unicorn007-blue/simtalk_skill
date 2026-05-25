### Modeling Transport Systems

#### Model Transport Systems

You will use transport systems in a variety of ways in your simulation models. You might have to model a simple conveyor that transports parts between two stations, as well as complex electric overhead monorail systems or forklifts that transport parts from one location to another, as well as cranes and automated guided vehicle systems.

For this task you can use the Conveyor , the Track and the TwoLaneTrack , which you find in the folder MaterialFlow in the Class Library .

- The Conveyor is an active material flow object that has a propulsion system of its own. It transports passive parts that do not have a propulsion system of their own.
- The Track and the TwoLaneTrack are passive material flow objects without a propulsion system of their own. They mainly serve as the route on which the active material flow object Transporter drives, either forward or in reverse.

When modeling your transport system keep these characteristics of Conveyor , Track and TwoLaneTrack in mind:

- All three are length-oriented objects, i.e., Plant Simulation uses their own Length , and the MU length of the MUs , which you type into their dialog boxes to determine how many MUs they can hold. The

- point-oriented material flow objects on the other hand, such as the Station , the ParallelStation , etc. do not use a length.
- You can create controls and sensors for them.
- Parts transfer from a point-oriented object to a length-oriented object in their entirety, i.e., they are located on Conveyor and Track/TwoLaneTrack in their full length as soon as their front has moved onto these objects.
- Parts transfer from one length-oriented object to another length-oriented object with the Speed which you type into the dialog box of the length-oriented object. This is of importance, when you use Entrance Controls .
- To model simple transport systems, you will use the active object Conveyor .
- To model cross-transfer systems, AGV systems, cranes, etc. you will use the passive objects Track or TwoLaneTrack .

By activating Automatic Routing of the moving objects Transporter , Part , and Container you can make sure that they always find their Destination Object on the shortest possible route .

Back to Modeling the Material Flow

#### Work with Length-oriented Objects

Work with Length-oriented Objects in 2D and 3D

By inserting Track , TwoLaneTrack , Conveyor , and FootPath as a sequence of curved segments and/or straight segments, you can realistically model the conveyor systems and tracks of your plant. The mobile objects Part , Container , Transporter and Worker move to their destination on them, either to the Workplace attached to or directly to the designated material flow object.

Plant Simulation uses the length of the polygonal and curved objects during the simulation. The Scaling Factor you select in the Frame in 2D controls how Plant Simulation computes the length. Plant Simulation automatically animates and aligns mobile objects along the polygon or the curve.

The illustration shows the most important items of the curve which you can define in 2D :

<!-- image -->

- To turn the MU in the direction of motion of the flow of materials, when it turns a curve, select Rotate movables .
- In 3D the MUs are automatically rotated in the direction of motion as the notch on the Y axis of the part shows.
- To use the Length of the curve in the layout within the Frame as the actual length of the Track , the TwoLaneTrack , the Conveyor , or the FootPath , select Transfer Length in 2D. When the dialog is open, Plant Simulation enters this value into the textbox Length .

<!-- image -->

<!-- image -->

<!-- image -->

To be able to edit the Length , clear the check box . Then you can type in a new length or make slight adjustments to the length of the inserted object.

<!-- image -->

To create a class from a Conveyor , Turntable , Track , TwoLaneTrack , or FootPath , model this class in the Frame , and then drag this object from the Frame to the Class Library . You can then insert this class into the active and into any other simulation model.

You can:

- Insert Curved and Straight Segments
- Draw Straight and Curved Segments with a 90° Angle
- Draw Straight and Curved Segments without Fixed Values
- Change the Shape of a Segment
- Reuse the Segments of a Length-oriented Object
- Create a Curved Object with SimTalk Commands

Compare Work with Length-oriented Objects in 3D

Back to Model Transport Systems

Insert Curved and Straight Segments

To insert a Track , a TwoLaneTrack , a Conveyor , a FootPath , or a Pipe as a sequence of curved and straight segments into the Frame that contains your simulation model:

**Note**

If you are modeling in 2D, make sure that Curve mode in the class of the object, either in the Class Library or in the Toolbox , is active . In Curve mode Plant Simulation animates the MUs using the number you typed into the text box Animate on Every Xth Pixel.

- Zoom the Frame to a size that it can accommodate the object you want to insert.
- Click the length-oriented object in the Toolbox , and drag the mouse to the Frame window and click the point where the object is to start. This opens the dialog Edit Parameters of Curve .

**Note**

When you drag a length-oriented object from the Class Library to the Frame , Plant Simulation inserts

<!-- image -->

it as a straight segment . You can then append points to it or insert points between existing anchor points.

To draw a straight segment, click a second time at the position at which you want the end of the segment to be. To draw a curved segment, hold down Ctrl , drag the mouse down to draw the curve downward, and click the left mouse button once to set the curve.

<!-- image -->

To draw the next straight segment of the line, release Ctrl , drag the mouse to the end point of the line and click the left mouse button once.

<!-- image -->

To draw a continuous sequence of straight and curved segments, for example for continuous conveyors, click an existing curved or straight end segment to start a new segment. Plant Simulation then uses the end coordinate of the first sequence as the start coordinate of the second sequence and automatically connects the two. You can prevent this by holding down Alt .

<!-- image -->

Click the right mouse button once or click Finish to exit Insert mode and to insert the curve you drew. This also closes the dialog Edit Parameters of Curve .

Press Esc or click Abort to terminate curve mode without inserting the curve.

Click Delete Last Point to delete the most recently inserted anchor point.

When the grid is active , Plant Simulation places the points that make up the line onto grid points, provided this is possible. For this, fixed values take precedence. When you type in a radius of 2.5 meters, for example, the end point of the arc will not be placed onto a grid point. This results in a non-tangential transition between the end of the arc and the end of the next straight segment, which will be placed onto a grid point again.

When you insert a straight segment after a curved segment, Plant Simulation always enforces a tangential angle of 0°.

<!-- image -->

To insert the length-oriented curved object with fixed values, type them into the text boxes in the dialog and select the check box fi xed of the respective item to tell Plant Simulation that you want to use these fixed values.

- For a line segment, you can type in the Line Length in world coordinates and the Tangential Angle as compared to the previous segment.

<!-- image -->

For both segment types you can type in an Anchor Point Height . It determines the height, i.e., the distance from the floor, to the next anchor point. It is, for example, useful when you model a ramp for material handling equipment.

<!-- image -->

- For a curved segment , you can type in the Arc Length , its Radius , and its Curve Angle in degrees as compared to the previous segment.

The Curve Angle is the angle that is formed by the radius between the start point A and the end point B of the arc segment. A positive number designates a clockwise angle. A negative number a counterclockwise angle.

**Note**

When you define a curve angle of 360°, Plant Simulation automatically connects the end point the curve with its starting point.

- For a following Straight Segment you can type in the Tangential Angle and the Line Length .

<!-- image -->

The tangential angle designates the change in the tangential direction. Type in a positive number for a clockwise angle . Type in a negative number for a counterclockwise angle . Normally the tangential angle is relative to the previous direction of the curved segment. For the first segment the tangential angle is the angle to the positive x direction.

When you insert a straight segment after a curved segment, Plant Simulation always enforces a tangential angle of 0 degrees.

<!-- image -->

<!-- image -->

Plant Simulation creates the start tangential angle as follows:

After clicking an existing object with the mouse, Plant Simulation applies the angle from the previous object as start tangential angle . This also applies to icons.

When setting a straight segment by a mouse click on an existing object, Plant Simulation uses, depending on the mouse position, either the angle of the object or +-90 degrees to this angle as the start tangential angle .

When setting a curved segment without clicking an existing object, Plant Simulation proceeds like this: When you type in an angle for straight segments, it uses this angle as the start tangential angle . When you hold down Ctrl , Plant Simulation uses, depending on the mouse position, 0, +-90 or 180 degrees as the start tangential angle.

Inserting a length-oriented curved object in 3D works similar to inserting it in 2D. When you insert a length-oriented curved object, 3D shows the extrusion path of this object. The path of the polycurve initially just consists of the starting point:

- Either the insertion point, i.e., the position on the grid on which you click or
- The end point of the picked object, which is its exit projected onto the XY layer.

**Just like in 2D :**

- 3D shows a movable line, which connects a manipulator at the starting point with another manipulator attached to the cursor.
- You insert straight path segments by clicking the left mouse button. You insert curved path segments by holding down Shift and by clicking the left mouse button.
- You terminate curve mode by clicking the right mouse button. In 3D , you can also do this by pressing Esc .
- 3D will not insert a length-oriented object, if the curved object does not consist of at least two segments/points after you finished or terminated inserting the curved object.

Compare Add Animations and Interactions to the Simulation Objects

Compare Edit a Curved Path with the Mouse

Back to Work with Length-oriented Objects in 2D and 3D

##### Draw Straight and Curved Segments with a 90° Angle

To insert a length-oriented curved object with a straight segment, and a 90° curve followed by another straight segment:

<!-- image -->

- Click the icon if the Conveyor in the Toolbox

.

- Drag the mouse to the Frame window to the point where you would like to start the straight segment of the line.
- Click the left mouse button once to set the starting point of the line.
- Plant Simulation opens the dialog Edit Parameters of Curve . Here, we defined default settings for inserting a curve with a 90° angle, i.e., a fixed tangential angle of 0°, a fixed curve angle of 90° and a fixed radius of 2 meters.

<!-- image -->

<!-- image -->

You can either apply these values or you can type in a different radius to make the curve wider. To do so, drag the mouse to the dialog and type another value into the text box.

**Note**

Plant Simulation saves the last set of settings in the dialog, so that you can re-use them the next time you insert a curved object.

To draw the curve, drag the mouse back to the Frame window, hold down Ctrl , drag the mouse down to draw the curve downward, and click the left mouse button once to set the curve.

<!-- image -->

To draw a curve pointing to the left: Drag the mouse back to the Frame window and hold down Ctrl . Make sure that Fixed for the Curve angle of the arc segments is activated and type in 90 . Then drag the mouse down to draw the curve downward, and click the left mouse button once to set the curve.

<!-- image -->

- To draw the next straight segment of the line, release Ctrl , drag the mouse to the end point of the line and click the left mouse button once.
- Click the right mouse button once to exit Insert mode. This also closes the dialog Edit Parameters of Curve .

<!-- image -->

When the grid is active , Plant Simulation places the points that make up the line onto grid points, provided this is possible. For this fixed vales take precedence. When you type in a radius of 2.5 meters, for example, the end point of the arc will not be placed onto a grid point. This results in a non-tangential transition between the end of the arc and the end of the next straight segment, which will be placed onto a grid point again.

<!-- image -->

To get a tangential transition, you can:

- Deactivate Snap to Grid by holding down Alt , when you click the left mouse button to set the end point of the second straight segment.
- Type in a Tangential angle of 0 degrees and set it as fi xed for this straight segment. Then deactivate this setting for the following straight segments.

<!-- image -->

To draw a curved segment without using fixed values, you have to click the left mouse button three times. To activate curve mode, hold down Ctrl , when you click the mouse button the first time!

- The first mouse click sets the starting point.
- The second mouse click sets the radius.
- The third mouse click sets the arc length or the curve angle respectively.

Back to Work with Length-oriented Objects in 2D and 3D

Draw Straight and Curved Segments without Fixed Values

To draw a straight segment of a length-oriented curved object without using fixed values:

- To set the starting point of the segment, click the left mouse button once. You will notice that Plant Simulation attaches the icon of the Connector to the front end of the cursor in the Frame window. The text boxes now show the actual values of the line segment.
- Drag the mouse in a direction of your choice and as far as you want the segment to be long. Click the left mouse button again to set the first anchor point. Now, Plant Simulation draws the segment with the settings you selected.
- Continue this until the object has the length and the shape you want.

##### Change the Shape of a Segment

- To set the end point of the segment, and to exit Insert mode, click the right mouse button.

To draw a curved segment of a length-oriented curved object without using fixed values:

- To set the starting point of the curved segment, hold down Ctrl and click the left mouse button once. You will notice that the text boxes now show the actual values of the curve segment.
- To set the Tangential Angle , drag the mouse in a direction of your choice.
- To set the Radius of the curved segment continue dragging the mouse until the curve has the radius you want it to be and click the left mouse button.
- To set the Arc Length , continue dragging the mouse until the curve is as long as you want it to be and click the left mouse button.
- To set the end point of the segment, click the right mouse button.
- To delete the last anchor point from the curve, drag the mouse pointer from the Frame window to the dialog Edit Parameters of Curve and click Delete Last Point .

Naturally you can combine both techniques to insert curved and straight segments in any sequence you like.

**Back to Work with Length-oriented Objects in 2D and 3D**

**Change the Shape of a Segment**

You can modify the shape of a segment in a number of ways:

- In 3D you can change the shape of a straight segment by clicking Show Manipulators and by then dragging the manipulators.

<!-- image -->

In 2D you can change the shape of the straight segment by clicking an anchor point with the left mouse button, and dragging it up and down or left and right until the shape meets your needs. Depending on how far you moved the anchor point, Plant Simulation lengthens the segment or shortens it.

- To delete an anchor point from the curve, right-click it and select Delete Point on the context menu.
- To insert an anchor point between two existing anchor points, right-click at the location between those points and select Insert Point on the context menu.

- To extend an existing curved segment of the length-oriented object without adding a new anchor point, click the drag point with the left mouse button and drag the mouse to the new position.
- To append anchor points to the end of the curve, right-click anywhere on the curve and select Segments &gt; Append on the context menu. Add an additional anchor point with the dialog Edit Parameters of Curve .
- To edit existing segments and to insert new segments, select Segments &gt; Edit . In the Segments Table you can also insert a segment at the beginning of the object which is not possible manually with the mouse.

In the example below we insert a curved segment at the beginning of the Pipe so that it seamlessly attaches to the FluidSource .

- Click the Pipe and press F7 .
- This opens the Segments table. Click in row 2 and select Insert Row . This inserts an empty row above row 2.

<!-- image -->

We typed in these values:

<!-- image -->

- The result looks like this. We then have to adjust the position of the Pipe .

<!-- image -->

- To change the direction of a curved object, for example from right to left, edit the Curve angle in the Segments table. Our Conveyor1 evades an obstacle to the right.

<!-- image -->

The Curve angles in the Segments table look like this.

<!-- image -->

Our Conveyor2 is to evade the obstacle to the left. To accomplish this, we changed the Curve angles in the Segments table as shown below.

<!-- image -->

This then looks like this:

<!-- image -->

- To replace the right angle of a curved object with a curve, we are going to edit the Segments table. We originally inserted this Footpath with a right angle. We now want the Worker to walk along a curve.

<!-- image -->

We press F7 to open the Segments table of the Footpath . It looks like this:

<!-- image -->

To see how we have to change the Segments table of our Footpath , we insert a second Footpath with a curve instead of the right angle above our Footpath . Footpath1 and its Segments table look like this:

<!-- image -->

Then left-click the Footpath and press F7 . Right-click in the last row of the Segments table and select Insert Row to insert an empty row before it. Type in the values that our curved Footpath1 has. Click Apply . Our Footpath now has a curve instead of a right-angle.

<!-- image -->

You can then delete Footpath1 which just provided the template for our curve.

- To change the direction of motion of a curved object, i.e., to make the last point of the object the first point, right-click the object and select Reverse . This is especially handy if you want to mirror the layout of a production line by copying it and then reversing the direction of motion of the mirrored line to ensure a circular flow of materials.

<!-- image -->

- To split the length-oriented curved objects into individual separate segments at the selected point, click the point where you would like to split it up and select Split Up . This looks like this in 2D and in 3D:
- To move the entire length-oriented curved object , click it once with the left mouse button and drag the mouse up or down or left or right. You can also use the arrow keys to move the object one pixel at a time or hold down Shift and press an arrow key to move the object one grid unit at a time.
- To delete the entire length-oriented curved object , click it once with the left mouse button and press Delete .

<!-- image -->

<!-- image -->

- To extend an existing length-oriented curved object , without adding a new anchor point, grab the handle with the left mouse button and drag the mouse to the new location.
- To link two or more existing length-oriented curved object , insert a Connector between them.
- To insert and connect another straight length-oriented object with an existing length-oriented curved object , click with the left mouse button on the end of the first object, move the mouse to the beginning of the second object and click the mouse button.

Compare Work with Length-oriented Objects in 3D

Compare Change the Shape of the Pipes

Back to Work with Length-oriented Objects in 2D and 3D

Create a Curved Object with SimTalk Commands

Naturally, you can also create a curved object with the SimTalk commands derive and duplicate .

```simtalk
var obj := .Materialflow.Conveyor.derive(.Models.Frame)
obj.Coordinate3D := [5, 5, 0]
var obj1 := .Materialflow.Conveyor.derive(.Models.Frame)
obj1.Coordinate3D := [1, 1, 0]
```

Reuse the Segments of a Length-oriented Object shows how to use the methods getCurveSegments and setCurveSegments .

Back to Work with Length-oriented Objects in 2D and 3D

Reuse the Segments of a Length-oriented Object

For smaller segments tables you can open two simulation models at the same time, copy the values in one model and paste them into the segments table of the other model. In the example below we copy the values of a feeder line for a Drain from a German model to an English model.

<!-- image -->

We copied the values of the individual cells in the German table and pasted them into the respective cell in the English table. As the English table originally only has three rows, we clicked the right mouse button in the index of row 2 and selected Append Row . This appended an empty row below row 2. Then we copied and pasted the remaining values and clicked OK .

<!-- image -->

To transfer the segments table of a curved object from one Frame to another Frame in the same simulation model , we write the segments table into a Variable with a Method . Then, we copy this Variable and paste it into the other Frame .

<!-- image -->

To export the segments table:

- Program a Method to export the coordinates of the curved object into a table with the method getCurveSegments . Enter the following source code into the method which we named exportMySegments :

Conveyor.getCurveSegments(MySegmentsVariable)

Executing the method, exportMySegments in our example, writes this data into the Variable named MySegmentsVariable .

<!-- image -->

Clicking Open opens the segments table. Here you can view and check the values of the segments table.

<!-- image -->

To import the segments table into another Frame in the same simulation model:

- Insert a Conveyor of any shape into the other Frame .
- Copy the Variable , MySegmentsVariable in our example, and paste it into that Frame , Model1 in our example. Then, insert a Method into Model1 . We named our method importSegments .
- Program the Method with the method setCurveSegments to overwrite the settings of the Conveyor , which we inserted, with the exported settings. Run the Method .

Conveyor.setCurveSegments(MySegmentsVariable)

<!-- image -->

If you want to use these settings in another simulation model , insert a DataTable into that model. Save the segments table, MySegmentsVariable in our example, as an object file (.psobj). You can then import the exported segments into a DataTable in the other simulation model and reuse it there.

Back to Work with Length-oriented Objects in 2D and 3D

<!-- image -->

Keyboard Shortcuts for Inserting a Curved Object

When Curve mode is active these keyboard shortcuts apply, even before you click a mouse button for the first time.

| To do this                                                                                                                                              | Press/click                                      |
|---------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|
| Set the starting point of a straight segment.                                                                                                           | left mouse button                                |
| Set the starting point of a curved segment.                                                                                                             | Ctrl +left mouse button                          |
| Deactivate the Snap To Grid feature.                                                                                                                    | Alt +left mouse button                           |
| Deactivate the Snap To Grid feature for the last point.                                                                                                 | Alt +right mouse button                          |
| Draw a straight segment horizontally or vertically and to deactivate Snap To Grid .                                                                     | Shift +left mouse button                         |
| Terminate Insert mode.                                                                                                                                  | right mouse button                               |
| Insert a new curved object of the same class without having to select it in the Toolbox again.                                                          | Ctrl +right mouse button, then left mouse button |
| Draw the last straight segment horizontally or vertically and to deactivate Snap To Grid . The right mouse button just refers to the last anchor point. | Shift +right mouse button                        |

| To do this                                                                                                                    | Press/click                                                              |
|-------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------|
| Deactivate default settings                                                                                                   | Shift + Alt                                                              |
| Insert the icon of the length-oriented object or of the length-oriented object as a curved object against the default values. | Shift +first click of the left mouse button                              |
| Open the dialog Sensor .                                                                                                      | Alt +double-click the red Sensor line on Conveyor , Track , TwoLaneTrack |
| 3D : Insert ascending curve                                                                                                   | Press the Up key, then the left mouse button                             |
| 3D : Insert descending curve                                                                                                  | Press the Down key, then the left mouse button                           |

Compare Edit Length-oriented Objects with Keyboard Keys in 3D

Back to Work with Length-oriented Objects in 2D and 3D

#### Model a Transport System with Active Objects of Type Conveyor

Model a Transport System with Active Objects

When you model transport systems with active objects, such as stationary belt conveyors, roller conveyors, etc., you will use the Conveyor . Below we outline how you can use the Conveyor .

**You can:**

- Model a Simple Conveyor Between Two Stations
- Model an Accumulating/a Non-Accumulating Transport System
- Model a Fixed Gap or a No Gap Conveyor
- Model a Multiple Gap or a Multiple Pitch Conveyor
- Model a Transport System with Passive Objects
- Model Transport Systems

##### Model a Simple Conveyor Between Two Stations

In this example we model a simple Conveyor between two Station .

In its most basic way, a transport system consists of a conveyor that moves parts between two processing stations. In our example we inserted a Conveyor between two Stations , SP1 and SP2 . The MUs are transferred from the point-oriented station SP1 onto the length-oriented Conveyor , which then transports them to the point-oriented station SP2 .

**Model an Accumulating/a Non-Accumulating Transport System**

<!-- image -->

The Conveyor moves the MUs from the station SP1 with the Final Speed we enter into the station SP2 . Plant Simulation computes the Transport Time using the Final Speed and the Length of the Conveyor . Speed , Length and Transport Time depend on each other. When you change Speed or Length , Plant Simulation recomputes the Transport Time anew. Changing the Transport Time also changes the speed .

<!-- image -->

**Back to Model a Transport System with Active Objects**

##### Model an Accumulating/a Non-Accumulating Transport System

In this example we model an accumulating/non-accumulating transport system.

You can use the Conveyor to model an accumulating or a non-accumulating transport system between stations.

- To make the MUs accumulate on the Conveyor , select the check box Accumulating . This enables the MUs to move front to end to each other, when the exit of the Conveyor is blocked.
- To make the MUs retain their distance to each other, i.e., make all succeeding MUs stop moving when the preceding MU cannot exit, clear the check box to deactivate Accumulating .

As we want to apply the default behavior of the Conveyor , we do not change its Capacity of -1, which stands for an infinite number of MUs . This way its capacity is defined by its own length and by the length of the parts ( MUs ), which it transports.

In our sample we entered an Availability of 85 percent and a MTTR of 6:00 minutes for the two Stations , SP1 and SP2 .

<!-- image -->

Plant Simulation marks a failed failure profile red.

You can use an accumulating Conveyor to decouple stations. Then, the Conveyor behaves like a roller conveyor that enables the MUs to move up to those in front of them, when the exit of the conveyor is blocked.

<!-- image -->

When you do not decouple the stations, the Conveyor behaves like a belt conveyor, meaning that the belt stops when a MU blocks the exit of the Conveyor and restarts as soon as the MU at the exit has moved on to the successor.

**Back to Model a Transport System with Active Objects**

##### Model a Fixed Gap or a No Gap Conveyor

In this example we model a fixed gap or a no gap Conveyor .

You can use the Conveyor to model conveyors ensuring gaps between the parts moving on it. The gap is the distance between the rear of the preceding part and the front of the succeeding part.

<!-- image -->

- The default setting of the Conveyor for the MU Distance is -1 , meaning that the feature MU Distance is deactivated and that the parts can move onto the conveyor as soon as they arrive from the predecessor.

<!-- image -->

<!-- image -->

- A conveyor with no gap between the parts does not allow a space between them, when you type in a MU Distance of 0 .
- A conveyor with a fi xed gap ensures that the space between the parts moving on it always is the same. The fixed gap causes the conveyor to frequently stop though.
- In the example below we typed in 0.5 as the MU Distance , which ensures a space of 0.5 meters between the transported parts.

<!-- image -->

<!-- image -->

- A conveyor with a Minimum Gap ensures that the space between the parts moving on it will not become less than the minimum gap. This setting prevents the conveyor from stopping and ensures that all parts exit the conveyor if it transports a certain number of parts.

In our example we selected the MU Distance Type &gt; Minimum Gap and typed in 1 as the MU Distance , which ensures a minimum space of 1 meter between the transported parts.

<!-- image -->

- A conveyor with a Minimum Pitch determines the minimum distance between the front of the preceding part and the front of the succeeding part. This setting prevents the Conveyor from stopping and from waiting for new parts and enables it to run dry.

<!-- image -->

<!-- image -->

- A conveyor with a Pitch sets the distance between the between the front of the preceding part and the front of the succeeding part. This setting ensures that the conveyor stops and waits for new parts. It also enables the conveyor to run dry.

<!-- image -->

- To force the Conveyor to keep the specified Distance between the MUs , even if the MUs accumulate on the Conveyor , select Enforce MU distance .

<!-- image -->

When you clear Enforce MU Distance , the MUs accumulate on the Conveyor .

<!-- image -->

When running the simulation in our sample model, you'll notice the continuous flow of parts on the minimum gap conveyor and on the conveyor which does not use a MU Distance . The no gap conveyor and the fi xed gap conveyor on the other hand stop quite often, denoted by the waiting parts.

<!-- image -->

Back to Model a Transport System with Active Objects

##### Model a Multiple Gap or a Multiple Pitch Conveyor

In this example we model a multiple gap and a multiple pitch Conveyor .

Model a Multiple Gap Conveyor

You can use the Conveyor to model conveyors ensuring multiple gaps between the parts moving on it.

Multiple Gap sets the distance between the rear of the preceding MU and the front of the succeeding MU . The distance can be an integer multiple of the defined MU Distance .

For the Source we selected the Uniform distribution with a Lower Bound of 0 and an Upper Bound of 0:04 .

<!-- image -->

For the Conveyor we selected the settings below with the MU Distance Type &gt; Multiple Gap and an MU Distance of 1 meter.

<!-- image -->

When we run the simulation, we see that the Conveyor does not stop to wait for new MUs after the gap has passed, but that the next MU can only enter the Conveyor if an integer multiple of the gap can be preserved.

Open the EventDebugger , step through the simulation event by event, and watch the event types CheckMUDistance , CreateMU , and Out .

<!-- image -->

Model a Multiple Pitch Conveyor

To model a Multiple Pitch Conveyor , we duplicated our Multiple Gap Conveyor model and changed the setting MU Distance Type to Multiple Pitch .

Multiple Pitch sets the distance between the front of the preceding MU and the front of the succeeding MU . The distance can be an integer multiple of the defined MU Distance . We did not change any other settings.

<!-- image -->

When we run the simulation, we see that the Conveyor does not stop to wait for new MUs after the pitch has passed, but that the next MU can only enter the Conveyor if an integer multiple of the pitch can be preserved. For this setting the Conveyor behaves like a chain conveyor.

Open the EventDebugger , step through the simulation event by event, and watch the event types CheckMUDistance , CreateMU , and Out .

Back to Model a Transport System with Active Objects

<!-- image -->

#### Model a Transport System with Passive Objects of Type Track

Model a Transport System with Passive Objects

When you model transport systems with passive objects, you will use the Track or the TwoLaneTrack on which the active MU Transporter drives.

As the Track is a passive object, you cannot just connect it with two stations, but have to make sure that a Transporter is available, plus you have to load and unload this Transporter . To prevent the MUs from automatically transferring from the preceding station, in our example SP1 , onto the Track , do not connect them with a Connector .

<!-- image -->

To create and insert a Transporter you can do one of the following:

- Use the Source : Select Attributes &gt; Time of Creation &gt; Number Adjustable and enter an Amount of 1 . To tell it to create transporters, select MU &gt; .MUs.Transporter .
- Use the SimTalk method create and enter this command into the init method of your simulation model:

<!-- image -->

```simtalk
.MUs.Transporter.create(Track)
```

This inserts a Transporter at the end of the Track . If you want to insert a Transporter anywhere else on the Track , enter a position into the Method . This example creates the Transporter that is positioned 5.5 meters along the length of the Track :

<!-- image -->

.MUs.Transporter.create(Track, 5.5)

As the Transporter is to move parts from station to station, SP1 and SP2 in our example, you first have to produce those parts and then load them onto the Transporter at the station SP1 and unload them at the station SP2 . For this you will program a control in a Method and enter its name into the respective text box on the tab Controls .

<!-- image -->

Without entering a control, the Transporter must moves to the end of the Track and stops there. To make the Transporter move back to the beginning of the Track , once it unloaded the parts, select the check box Front and enter this source code into the exit control , FrontOutCtrl in our example:

```simtalk
if @.empty
	@.Backwards := true
end
```

Once the Transporter backed up to the beginning of the Track , Plant Simulation activates the rear backward exit control, when you select Rear and enter the name of the Method into the text box Backward exit . This control has to accomplish these tasks:

- Wait until a MU is ready to exit the station, SP1 in our example.
- Load the MUs into the Transporter .
- Move the Transporter to the end of the Track .

In our example we entered these instructions:

```simtalk
waituntil Sp1.occupied and SP1.cont.finished
SP1.cont.move( @ ) // load the part
@.Backwards := false
```

Line 1 of the source code tells Plant Simulation to wait until a MU is located on the station SP1 and is processed all the way.

Line 2 loads the MU onto the Transporter . We use the anonymous identifier @ to address the Transporter .

Line 3 tells the Transporter to move forward again to the end of the Track .

When the Transporter reaches the end of the Track it has to accomplish these tasks:

- Wait until the station, SP2 in our example, is Empty .
- Unload the Transporter .
- Move the Transporter back to the beginning of the Track .

As the Transporter initially moves to the end of the Track and then activates the following exit control while being unloaded, we query if it is loaded or empty.

In our example we entered this these instructions:

```simtalk
if @.empty
	@.Backwards := true
else
	waituntil SP2.empty prio 1
	@.cont.move(SP2)
	@.Backwards := true
end
```

**Back to Systems**

Model a Tugger Train

Model a Tugger Train

To model tugger trains , consisting of a tractor and a number of trailers it pulls, you will use a number of extended features of the Transporter . In our sample model a tugger train is loaded with parts, which will be unloaded at a station on the main line and on the side line each.

The model demonstrates how to:

- Define the Tractor of the Tugger Train .
- Model the Source Creating the Tugger Trains .
- Model the Tracks on Which the Tugger Trains Drive .
- Configure the Loading and Unloading Stations .

Back to Model a Transport System with Passive Objects

Define the Tractor of the Tugger Train

To set the tractor of the tugger train :

- Duplicate the object Transporter in the Class Library . Rename it to Tractor .

<!-- image -->

- Double-click the object Tractor . To designate it as the tractor of the tugger train , which pulls the trailers , select the check box Is Tractor .

<!-- image -->

<!-- image -->

- To prevent the tractor from loading parts onto its bed, enter 0 as the X-Dimension and the YDimension . For the loading space types Track and Line , enter 0 as the Capacity .

<!-- image -->

**Back toModel a Tugger Train**

Model the Source Creating the Tugger Trains

Model the Source Creating the Tugger Trains

We modeled the source, which creates the tugger trains , in the Frame named SourceTuggerTrains . We did this to prevent our overall model from becoming too cluttered with objects.

The Frame contains of these objects:

- A Source object, which creates tractors and trailers according to the settings, which we enter into a sequence table .
- A Track , which should be long enough to accommodate the tugger train with its entire length after the Source has created it. This ensures that the tugger train is able to move onto the succeeding object as a whole. The tugger train in our example consists of a tractor and four trailers , each of which is 1.5 meters long. So we entered a length of 10 meters for the Track .

<!-- image -->

- A Method , in which we program how the trailers are hitched to the tractor when they collide with the trailer in front of them.

**Back to Model a Tugger Train**

Configure the Source and Create the Sequence Table

To configure the Source object, which creates the tractors and the trailers , which make up the tugger train , double-click its icon.

To produce the objects as a sequence according to the settings, which we enter into the sequence table:

- Select MU Selection &gt; Sequence .

<!-- image -->

- Click and select the DataTable named MySequenceTable , which we inserted above. To create a tractor object using the MU class Tractor and four trailer objects using the MU class Transporter , we entered the values shown in the screenshot below.
- The characters, which we enter into the column Attributes , only serve as a placeholder for the subtables contained in these cells. Within the sub-tables we set the attributes of the tractor and of the trailers .

<!-- image -->

To designate the tractor we entered the attribute IsTractor and set it to true . To set its speed, we entered the attribute Speed and entered 1.0 m/s.

**Note**

We already defined the attributes of the tractor in the class Tractor . We just entered them again to make sure that the settings in the tractor are the correct ones, in case the settings of the class get changed.

<!-- image -->

To designate the trailers , we set the attribute IsTractor to false . As we want the trailers of drive faster than the tractor and to collide with the object in front of them, we entered 1.1 m/s as their Speed . To designate the collision control ( CollisionCtrl ), we entered the name of the Method , which we inserted above, hitchMethod in our case. The collision control hitches the trailers to each other and the front trailer to the tractor .

Back to Model the Source Creating the Tugger Trains

<!-- image -->

**Video on YouTube**

[https://youtu.be/BvHLQCIjGIA?si=SbE5dRcUJQea823K&amp;t=425](https://youtu.be/BvHLQCIjGIA?si=SbE5dRcUJQea823K&t=425)

Program the Collision Control

To program the Collision Control named hitchMethod , which we inserted above, double-click the Method object. We want this control to hitch the colliding trailer to the one in front of it. To do so, we have to establish the trailer moving in front of the active trailer .

Finally, we are going to hitch the rear Transporter to the one moving in front of it to create the tugger train .

<!-- image -->

These statements above translate into this source code in our Method like this:

if @.isTractor = false then @.hitchFront(@.FrontMU) end

###### Back to Model the Source Creating the Tugger Trains

Model the Tracks on Which the Tugger Trains Drive

To demonstrate how the tugger trains move as a single unit on a track system, let's model a main line, from which a side line splits, which then feeds back into the main line. For this we use four Tracks and connect them with Connectors . To move the side line over the main line, hold down the Shift and/or Ctrl keys and press the arrow keys.

<!-- image -->

After we have finished creating the track system, we have to insert:

- The station producing the tugger trains , which we modeled in the Frame named SourceTuggerTrains . We connect this Frame with the object Track .
- A Source which produces the parts with the default settings and a station, which loads them onto the trailers of the tugger train .
- An unloading station on the main line and the side line each, plus a Drain each, which removes the parts from the lines. For the two Drains , which we named ShippingMain and ShippingSide , we use the default settings.
- An EventController for running the simulation.

The finished simulation model looks like this in 2D and in 3D.

**Configure the Loading and Unloading Stations**

Back to Model a Tugger Train

<!-- image -->

###### Configure the Loading and Unloading Stations

We will model the loading station and the unloading stations with the object TransferStation . You find more information under Load, Unload, and Reload Parts with the TransferStation .

Configure the loading station on the tab Attributes . Select the object which provides the parts ( parts from ) and the object on which the tugger train moves ( target is on ). In our case this is the SourceParts and the Track .

Enter the position of the sensor, which triggers loading the tugger trains with parts. We entered 7 (meters). The TransferStation then enters these settings into the dialog Sensor of the Track .

<!-- image -->

Next, configure the stations UnloadingMain and UnloadingSide as shown in the screenshots below.

<!-- image -->

When you are finished, start the simulation and watch how the tugger trains are loaded with parts, move on the main line, are unloaded, are loaded again, and are unloaded on the side line on their second trip.

Back to Model a Tugger Train

#### Using Automatic Routing

Use Automatic Routing

Here we demonstrate how to use automatic routing to ensure that the parts always reach their destination object on the shortest possible route.

**You can:**

- Work with Automatic Routing of the Transporter

You find the respective settings on the tab Routing of the Transporter .

The Transporter finds its destination along the shortest route.

<!-- image -->

- Work with Automatic Routing of Part and Container
- You find the respective settings on the tab Routing of Part and Container .

The Part and the Container find their Destination along the fastest route.

<!-- image -->

**Back to Model Transport Systems**

Working with Automatic Routing of the Transporter

Work with Automatic Routing of the Transporter

In this sample model we demonstrate how a Transporter automatically finds its destination object. As soon as the destination object is assigned a reachable destination, Plant Simulation computes the route which describes the way on which the Transporter reaches its destination. The Transporter finds its destination along the shortest route.

The Source named SourceTransporters creates Transporters , which wait for parts at the sensor of the LoadingStation .

In the sensor control we set that the Transporter waits until the SourceParts has produced a part of type MyPart . Once a part is located on the LoadingStation , this part is loaded onto the Transporter . Then we determine the destination object of the parts, i.e., one of the unloading stations Unload1 , Unload2 , or Unload3 . When the Transporter has reached the destination object, the part will be unloaded and the Transporter returns to the LoadingStation , where it is loaded anew.

We will demonstrate how to:

- Insert and Configure the Tracks
- Program the Control for Loading the Transporter
- Configure the Sources and the Transporter
- Program the Control for Unloading the Transporter
- Make the 3D Model Visually Pleasing

The finished simulation model looks like this in 2D:

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

**Back to Use Automatic Routing**

**Insert and Configure the Tracks**

Before we start modeling, we create the objects that we need as we do not want to change the built-in object classes.

We duplicated the Source , the Track , the Connector , the Transporter , the Part , the Method , and the DataTable in their respective folders. Plant Simulation places the duplicated objects into the folder UserObjects in the Class Library . We renamed the objects and added them to the toolbar User Objects with drag-and-drop.

<!-- image -->

Now we model our route network on which the Transporter drives. As a part of the route network consists of three route loops, we first create a loop, copy it, and insert it twice. Then we connect the upper Tracks with Connectors .

<!-- image -->

We continue this until our route network is finished. Make sure that the individual route pieces are connected!

<!-- image -->

Then we move the individual loops so that they look like this:

<!-- image -->

Next we configure the LoadingStation and the three unloading stations , Unload1 , Unload2 , and Unload3 . For this we renamed the respective route pieces as shown below. In addition we colored them on the tab Curve &gt; Color to better recognize them.

Then we create a sensor on the LoadingStation at which the parts are going to be loaded onto the Transporters . Click the right mouse button on the route piece LoadingStation and select Create Sensor . We selected these settings:

<!-- image -->

Finally we insert the two Sources that produce the Transporters and the Parts , the SequenceTable , and the method unload . Our model then looks like this:

<!-- image -->

##### Back to Work with Automatic Routing of the Transporter

Program the Control for Loading the Transporter

After we created the route network, the LoadingStation , and the unloading stations , we program the Sensor Control for loading the parts onto the Transporter .

<!-- image -->

In the Sensor Control we define that the Transporter waits until the SourceParts has produced a part of type MyPart . As soon as a part is located on the LoadingStation , it is loaded onto the Transporter . The anonymous identifier ? designates the part that is assigned to the contents of the calling object.

Next we determine the Destination with the instruction @.Destination . To do so, we differentiate the consecutive number of the Transporter , @.ID , using the modulo function (mod 2 or mod 3) for integer remainders. This way each third part receives an identical Destination . This is one of the unloading stations Unload1 , Unload2 or Unload3 . After the Destination is assigned, each Transporter is assigned the method named unload as Destination Control , DestCtrl .

Our source code of the Sensor Control looks like this:

```simtalk
param SensorID: integer, Front: boolean
waituntil SourceParts.Occupied prio 1
SourceParts.Cont.move(@) if (@.ID mod 2) = 0
@.Destination := Unload2
elseif (@.id mod 3) = 0
@.Destination := Unload3
else
	@.Destination := Unload1
end
@.DestCtrl := "unload"
```

**Back to Work with Automatic Routing of the Transporter**

**Configure the Sources and the Transporter**

Now we configure the SourceTransporters , which produces the Transporters and the SourceParts , which produces the parts.

- As we always want to assign a Destination to the Transporter in our model, we selected the MU Selection &gt; Sequence for the SourceTransporters and our SequenceTable as the required table:

We entered our LoadingStation as the Destination into the subtable Settings . Apart from that we use the default settings.

<!-- image -->

<!-- image -->

We connect the SourceTransporters with the object MyTrack5 with a Connector .

- For the SourceParts we only selected our part named MyPart as the MU . Apart from that we use the default settings.

As we want to move the parts with a control to the LoadingStation , we do not need a Connector between the two stations.

<!-- image -->

- For our Transporter named MyTransporter we activate automatic routing on the tab Routing .

<!-- image -->

- We use our part named MyPart with the default settings.

Back to Work with Automatic Routing of the Transporter

Program the Control for Unloading the Transporter

Finally, we program our control for unloading the Transporter . We do this in the method named unload . This control is going to be called when the Transporter has reached its Destination .

The unload control unloads the part from the bed of the Transporter , assigns the now empty Transporter to the LoadingStation as new Destination and removes the Destination Control , DestCtrl . In addition the control writes the name of the Transporter , the previous destination, and the new destination to the Console .

Our source code looks like this:

```simtalk
@.deleteMovables
print @,":"
print "Previous destination: ",@.Destination // write the previous // destination to the Console
@.Destination := LoadingStation
@.DestCtrl := ""
print "New destination: ",@.Destination      // write the new // destination to the Console
@.move
```

<!-- image -->

Back to Work with Automatic Routing of the Transporter

Make the 3D Model Visually Pleasing

Use New Standard Graphics of the 2D Objects shows how we replaced the outdated icon of the Track in our existing simulation model with the icon of the Track of version 15 and higher.

To better be able to tell the LoadingStation and the unloading stations -Unload1 , Unload2 and Unload3 -apart from the other route pieces, we selected different colors for the lanes of these Tracks in 3D.

<!-- image -->

In addition we activated and displayed the Captions of the LoadingStation and of the unloading stations . We selected these and similar settings:

<!-- image -->

<!-- image -->

Click on the tab View of the 3D ribbon tab to show the names of the objects. Start the simulation, reduce the simulation speed and watch how the Transporters move to the same UnloadingStation each third time and unload the parts there.

<!-- image -->

Drag the mouse over the Transporter to show its name, its current location, its destination, and the previous route in a Tooltip .

<!-- image -->

The command View &gt; Route to Destination selects the objects that are part of the route to the destination in the Frame .

Back to Work with Automatic Routing of the Transporter

<!-- image -->

##### Working with Automatic Routing of Part and Container

###### Work with Automatic Routing of Part and Container

In this sample model we demonstrate how a Pallet ( Container ) automatically finds its destination by using its destination object. As soon as the destination object is assigned a reachable destination, Plant Simulation the route which describes the way on which the Pallet reaches its destination traveling on the Conveyors .

The Part and the Container find their Destination along the fastest route.

The Source named SourcePallets creates Pallets , which wait for parts at the sensor of the LoadingStation .

In the sensor control we set that the Pallet waits until the SourcePallets has produced a part of type MyPart . Once a part is located on the LoadingStation , this part is loaded onto the Pallet . Then we determine the destination object of the parts, i.e., one of the stations Unload1 , Unload2 , or Unload3 . We inserted a sensor each into these stations. When the Pallet has reached the destination object, the part will be unloaded and the Pallet returns LoadingStation , where it is loaded anew.

We will demonstrate how to:

- Insert and Configure the Conveyors
- Configure the Unloading Stations
- Program the Control for Loading the Pallet
- Configure the Sources and the Pallet
- Program the Control for Unloading the Pallet
- Make the 3D Model Visually Pleasing

We created our simulation model originally in 2D. After saving it as a 3D Only model , it looks like this:

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

###### Insert and Configure the Conveyors

Before we start modeling, we create the objects that we need as we do not want to change the built-in object classes.

We duplicated the Source , the Conveyor , the Connector , the Container , the Part , the Method , and the DataTable in their respective folders. Plant Simulation places the duplicated objects into the folder UserObjects in the Class Library . We renamed the objects and added them to the toolbar User Objects with drag-and-drop.

Now we model our route network on which the Container travels. To simplify matters, we saved our model for automatic routing of the Transporter under a new name.

Then we held down Alt , dragged the object MyConveyor in the folder User Objects in the Class Library onto the object MyTrack and dropped it there. This replaced all instances of the object MyTrack with instances of the object MyConveyor . This way we do not have to manually create the route network. As we kept the changes to the instances of the Track , we now have to manually rename the individual route pieces, for example from MyTrack1 to MyConveyor1 , etc.

Next we configure the LoadingStation and the three unloading stations , Unload1 , Unload2 , and Unload3 .

<!-- image -->

Then we change the sensor of the LoadingStation at which the parts are going to be loaded onto the Transporters . Click the right mouse button on the sensor of the LoadingStation and select Open Sensor . We selected these settings. As the Destination is the LoadingStation itself, Plant Simulation enters self .

###### Configure the Unloading Stations

<!-- image -->

Finally we configure our Sources that produce the Pallets and the Parts .

**Back to Work with Automatic Routing of the Transporter**

Configure the Unloading Stations

For each of the three unloading stations -Unload1 , Unload2 , and Unload3 -we create a sensor each in their center at which the parts are going to unloaded.

As we only want to activate the sensor when the Pallet has the same Destination as the one we selected in the sensor , we select Only when Destination . The Destination of the action, unloading the parts in our case, is the respective station. Plant Simulation enters self when we select the respective unloading station .

As control we enter our method named unload in each case.

Back to Work with Automatic Routing of the Transporter

<!-- image -->

Program the Control for Loading the Pallet

After we created the route network, the LoadingStation , and the unloading stations , we program the Sensor Control for loading the parts onto the Pallet .

<!-- image -->

In the Sensor Control we define that the Pallet waits until the SourceParts has produced a part of type MyPart . As soon as a part is located on the LoadingStation , it is loaded onto the Pallet . The anonymous identifier ? designates the part that is assigned to the contents of the calling object.

Next we determine the Destination with the instruction @.Destination . To do so, we differentiate the consecutive number of the Pallet , @.ID , using the modulo function (mod 2 or mod 3) for integer remainders. This way each third part receives an identical Destination . This is one of the unloading stations Unload1 , Unload2 or Unload3 . After the Destination is assigned, each Pallet is assigned the method named unload as Destination Control .

Our source code of the Sensor Control looks like this:

```simtalk
param SensorID: integer, Front: boolean
waituntil SourceParts.Occupied prio 1
SourceParts.Cont.move(@) if (@.ID mod 2) = 0
@.Destination := Unload2
elseif (@.id mod 3) = 0
	@.Destination := Unload3
else
	@.Destination := Unload1
end
```

Back to Work with Automatic Routing of the Transporter

###### Configure the Sources and the Pallet

In this step we configure the SourcePallets , which produces the Pallets and the SourceParts , which produces the parts .

- As we always want to assign a Destination to the Pallet in our model, we selected the MU Selection &gt; Sequence for the SourcePallets and for the required table our SequenceTable :

<!-- image -->

We entered our LoadingStation as the Destination into the subtable Settings . Apart from that we use the default settings.

<!-- image -->

- For the SourceParts already contains as MU our part named MyPart . As we want to move the parts with a control to the LoadingStation , we do not need a Connector between the two stations.
- For our Pallet named MyContainer we activated Automatic Routing on the tab Routing .
- We use our part named MyPart with the default settings.

<!-- image -->

**Back to Work with Automatic Routing of the Transporter**

###### Program the Control for Unloading the Pallet

Finally, we program our control for unloading the Pallet . We do this in the method named unload . This control is going to be called when the Pallet has reached its Destination .

The unload control unloads the part from the Pallet , assigns the now empty Pallet to the LoadingStation as new Destination . In addition the control writes the name of the Pallet , the previous destination and the new destination to the Console .

Our source code looks like this:

```simtalk
@.Cont.move(MyDrain)
print @,":"
print "Previous destination: ",@.Destination // write the previous // destination to the Console
@.Destination := LoadingStation
print "New destination: ",@.Destination      // write the new // destination to the Console print                                        // add an empty line
```

Back to Work with Automatic Routing of the Transporter

<!-- image -->

Make the 3D Model Visually Pleasing

To better be able to tell the LoadingStation and the unloading stations -Unload1 , Unload2 , Unload3 -apart from the other route pieces, we selected different colors for the lanes of these Conveyors in 3D.

<!-- image -->

In addition we activated and displayed the Captions of the LoadingStation and of the unloading stations . We selected these and similar settings:

<!-- image -->

<!-- image -->

Click on the tab View of the 3D ribbon tab to show the names of the objects. Start the simulation, reduce the simulation speed and watch how the Pallets move to the same UnloadingStation each third time and unload the parts there.

<!-- image -->

As we created our Conveyors by replacing the Tracks from another model with our Conveyor , we have to adjust the Base Height for each instance of the route piece individually, by entering 1 into the text box Base Height . While the Tracks are placed flush on the floor of the installation, the Conveyors usually are placed on legs elevated from the floor.

We also selected a number of other settings in the class of our Conveyor .

<!-- image -->

Drag the mouse over the Pallet to show its name, its current location, its destination, and the previous route in a Tooltip .

<!-- image -->

The command View &gt; Route to Destination selects the objects that are part of the route to the destination in the Frame .

<!-- image -->

Back to Work with Automatic Routing of the Transporter

#### Modeling an Automated Guided Vehicle System

Model an Automated Guided Vehicle System (AGVS)

You can use the resource objects AGVPool and Marker to model AGV systems in your installation in which the AGV , starting at the AGVPool , covers the designated route along the markers you inserted. The AGV is not bound to a permanently installed route network, but drives freely within the space of the installation.

**Note**

When you insert Markers into your model, make sure that the Markers are aligned . This prevents Plant Simulation from computing unnecessary roundings between the Markers . Misaligned Markers might occur if you inserted Markers into your model while Show Grid was off.

**Note**

The freely driving AGV only works in 3D, not in 2D.

<!-- image -->

<!-- image -->

We show how the AGVs :

- Cover a Route Along Omnidirectional Markers

Here the AGV does not drive across the inserted marker but turns in front of the inserted markers according to the angle that Plant Simulation computed toward the next marker . The icon of an omnidirectional marker inserted into a Frame looks like this .

<!-- image -->

Set the route pattern which the AGV covers in the method setRoute of the Transporter :

```simtalk
var AGV : object := AGVPool.Cont
AGV.setRoute([M1,M2,M3,M4]) // sets the route
waituntil AGV.DestinationWasReached
AGV.DestinationWasReached := false // recognizes when the destination of the route was reached print "The AGV is ready for the next route."
```

**· Cover a Route Along Directional Markers**

Here the AGV drives onto the marker and then rotates toward the marker around the default angle of 0° in the direction of the next marker . The icon of a directional marker inserted into a Frame with the default angle looks like this .

<!-- image -->

**Cover a Route Along Directional Markers with the Defined Angle**

Here the AGV drives toward the marker at an angle of 90°, which we defined, crosses it, and leaves it at an angle of 90°.

<!-- image -->

The icon of a directional marker inserted into a Frame with an angle of 90° looks like this .

<!-- image -->

**· Cover a Route According to a Segments Table**

Here the AGV covers the route according to the route segments which we set in a table. To do so, we use the method setRouteSegments .

In addition, you can:

- Load Parts Onto an AGV and Rotate Them
- Fine-position an AGV
- Prevent AGVs from Colliding

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

**Back to Model Transport Systems**

Cover a Route Along Omnidirectional Markers

In this simple sample model the AGV covers the set route along omnidirectional markers . This means that it does not drive across the markers but turns in front of the marker toward the next marker . Plant Simulation computes the curve, which the AGV drives, according to the angle of the connecting line between the current marker and the next marker .

The finished simulation model looks like this:

<!-- image -->

Proceed as follows to create the model:

- Duplicate the objects Transporter in the folder MUs and Marker in the folder Resources in the Class Library . Plant Simulation places the duplicated objects into the folder UserObjects . We renamed our objects as shown below.

<!-- image -->

- Insert the AGVPool from the tab Resources in the Toolbox . The AGVs of the automated guided vehicle system are created in the AGVPool .

<!-- image -->

We use our duplicated AGV named MyAGV .

<!-- image -->

- Insert the Markers which form the route pattern into the Frame . We inserted four markers and renamed them M1 , M2 , M3 , and M4 .

<!-- image -->

As we want to see these identifiers in the Frame , we selected the respective Marker and pressed the spacebar . Then we selected the settings below for the first Marker on the tab Captions . We repeated this for the remaining Markers .

<!-- image -->

- Set the route pattern which the AGV covers. You have to program this in a Method . We named our Method setRoutePattern and typed in this source code:
- To make AGV use the set route pattern, we typed in this source code into our init-method :
- Run the simulation and watch how the AGV drives along the route and covers the individual Markers one after the other from M1 to M4 . To better follow the route, we entered the real-time factor 3 in the EventController .

```simtalk
var AGV : object := AGVPool.Cont
AGV.setRoute([M1,M2,M3,M4]) // sets the route
waituntil AGV.DestinationWasReached
AGV.DestinationWasReached := false // recognizes when the destination of the route was reached print "The AGV is ready for the next route."
```

// set the route pattern setRoutePattern()

The AGV does not drive across the inserted Markers but turns in front of the inserted Markers according to the angle that Plant Simulation computed toward the next Marker . For our model it looks like this:

Back to Model an Automated Guided Vehicle System (AGVS)

<!-- image -->

Cover a Route Along Directional Markers

In this sample model the AGV covers the route along directional Markers with the default angle.

Proceed as follows to create the model:

- Duplicate the model of the omnidirectional markers .
- Convert the omnidirectional markers to directional markers :

We double-clicked the Marker M1 , selected Use rotation of marker on the tab Attributes and clicked OK . If you do not specify an angle, the Marker uses the default angle of 0°.

<!-- image -->

Plant Simulation now shows the Marker with this icon .

Repeat this for the remaining Markers .

In our example we use the default angle of 0 degrees for our Markers .

<!-- image -->

- Run the simulation and watch how the AGV drives along the route and covers the individual Markers . To better follow the route, we entered the real-time factor 3 in the EventController .

The AGV drives across the Markers from M1 to M4 and turns on the Marker with the specified angle in the direction of the next Marker .

<!-- image -->

We can also use another rotation angle than the default angle of 0°:

- Click the Marker and press the Spacebar to enter the rotation angle in the dialog Edit 3D Properties .
- Type the rotation angle into the text box angle in the group box Rotation . We typed in an angle of 90 degrees. Click Apply to show the changed settings in the Frame window.
- Click OK when the angle meets your expectations and you want to apply it.

<!-- image -->

Plant Simulation now shows the Marker with this icon .

**Cover a Route According to a Segments Table**

<!-- image -->

<!-- image -->

<!-- image -->

- Run the simulation and watch how the AGV drives along the route and covers the individual Markers . To better follow the route, we entered the real-time factor 3 in the EventController .

The AGV covers the Markers from M1 to M4 . It drives toward the Marker M3 at an angle of 90°, which we defined, crosses it, and leaves it at an angle of 90°.

<!-- image -->

**Back to Model an Automated Guided Vehicle System (AGVS)**

Cover a Route According to a Segments Table

In this example the AGV covers the route according to the route segments which we set in a table. To do so, we use the method setRouteSegments .

Proceed as follows to create the model:

- Insert the AGVPool from the tab Resources in the Toolbox . The AGVs of the automated guided vehicle system are created in the AGVPool .
- Insert a Method and program the source code so that it executes the following instructions:
- We want the AGV created in the AGVPool to cover the segments of the route.

- We create a local Variable of data type table with four columns in which we set the segments of the route.
- We append a row for each segment to the table.
- We then tell the AGV to cover the segments of the route which we specified in the table named Route .
- We finally suspend method execution.

The respective source code looks like this:

```simtalk
var AGV : object := AGVPool.Cont
var route:table[length, real, length, speed]
route.create
route.appendRow(2)
route.appendRow(void, -90, 1, 0.2)
route.appendRow(void,  90, 1, 0.2)
route.appendRow(2)
route.appendRow(void, -90)
route.appendRow(2)
route.appendRow(0.5, -90)
agv.setRouteSegments(route)
stopuntil agv.DestinationWasReached
```

- Rename the Method to init so that the simulation will be run immediately after resetting the simulation model.
- Run the simulation and follow the movements of the AGV in the simulation model.
- To show the route segments in the created table, insert a break point in the last row of the source code and run the Method . Then double-click the cell Value in the column Name on the tab Variables in the Method-Debugger .

<!-- image -->

##### Cover a Route According to a Segments Table

- The first column contains the Length of the straight segment.
- The second column contains the Angle with which the curve changes its direction.
- The third column contains the Radius of the curved segment.
- The fourth column contains the Speed with which the AGV drives on this segment.
- To trace how the AGV drives on the individual segments, click .

<!-- image -->

<!-- image -->

in the dialog box of the EventDebugger to cover the segments one after the other.

<!-- image -->

Then click Load Parts Onto an AGV and Rotate Them Load Parts Onto an AGV and Rotate Them In this example we show how the AGV drives underneath a Conveyor , loads a pallet, and rotates it while driving toward its destination. After the AGV has placed the part, it drives back to the point of departure along the Markers and picks up the next pallet.

Back to System

<!-- image -->

In our example we will:

- Insert the Material Flow Objects
- Create the Conveyor on Which to Place the Pallet
- Insert the Transport Components

The finished simulation model looks like this:

<!-- image -->

##### Back to Model an Automated Guided Vehicle System (AGVS)

Insert the Material Flow Objects

Insert the material flow objects which produce and transport the pallets:

- The Source produces parts of type Container , our pallet, every 20 seconds.

<!-- image -->

- Conveyor1 transports the pallets to the pick-up place. We use Conveyor1 with its default settings.
- The pick-up place is Conveyor1 underneath which the AGV drives and loads the pallet.
- For Conveyor1 we selected these simulation settings.

<!-- image -->

- We also created an Exit Control as a user-defined attribute . In it we set the route of the AGV and make it rotate the pallet.

<!-- image -->

We entered this source code:

```simtalk
waituntil AGVPool.NumIdleAGVs > 0
var agv := AGVPool.getIdleAGV
agv.setDim(1,1)
agv.setRoute([MarkerPick])
waituntil agv.DestinationWasReached
@.move(agv)
@.ConveyingDirection := 1
agv.setRoute([MarkerPlace]) wait 1
agv._3D.getObject(1).moveTo(90)
waituntil agv.DestinationWasReached
@.move(Conveyor2)
agv.setRoute([M1,M2,M3,M4,M5,M6,M7])
agv._3D.getObject(1).moveTo(00)
waituntil agv.DestinationWasReached
agv.IsIdle := true
```

**Back to Load Parts Onto an AGV and Rotate Them**

Create the Conveyor on Which to Place the Pallet

To create the conveyor under which the AGV drives to pick the pallet up:

- We selected these 3D settings.
- We typed in a Base Height of 0.4 meters for our Conveyor .

<!-- image -->

As the AGV is to drive underneath Conveyor1 to pick up the pallet, we added a new graphic group to it and named it graphic .

<!-- image -->

We then opened Conveyor1 in a new 3D window and created four posts with a height of 0.4 meters, which matches the Base Height of our Conveyor , and a width and a depth of 0.1 meters each.

<!-- image -->

- Insert another Conveyor onto which the AGV places the pallets. We use Conveyor2 with its default settings.
- Insert a Drain which removes the pallets from the plant. We use the Drain with its default settings.

**Back to Load Parts Onto an AGV and Rotate Them**

###### Insert the Transport Components

Insert the transport components:

- As we want to change the properties of our AGV , we duplicate the Transporter in the folder MUs . This prevents that we change the built-in class of the Transporter .

<!-- image -->

Now we create a plate on the loading space of the AGV , which rotates the loaded pallet:

- Click the Transporter in the folder UserObjects with the right mouse button and select Open in 3D .
- Create a Cylinder . We selected these settings:
- Click the cylinder with the right mouse button and select Make Animatable Object . Type in Plate as the name. Click OK .

<!-- image -->

<!-- image -->

- This automatically opens this dialog with the tab Joint . Select Revolute Joint and type in 20 as the Velocity .
- Our Transporter then looks like this:

<!-- image -->

<!-- image -->

- We then typed in Plate as the Animation Object of the AGV .
- Insert the AGVPool which creates the AGVs of the automated guided transport system. By default this is the Transporter .

<!-- image -->

<!-- image -->

- Insert the Markers along which the AGV drives.

The Markers M1 to M7 are omnidirectional Markers .

The Markers MarkerPick and MarkerPlace are directional Markers .

<!-- image -->

Run the simulation and watch how the AGV drives from the AGVPool underneath Conveyor1 to MarkerPick and picks up the pallet there. On its way to MarkerPlace the pallet rotates on the AGV and is placed rotated on Conveyor2 at the MarkerPlace . Then the AGV drives back to the pick-up place and repeats the process.

Back to Load Parts Onto an AGV and Rotate Them

<!-- image -->

Fine-position an AGV

If the AGV is driving freely within the area of your model, you will sometimes have to fine-position it. You can achieve this with the methods rotate and drive of the Transporter .

In our example the AGV drives from the AGVPool via the Marker named M1 to the Marker named M2 . There it rotates by 90° to the left and drives 2 meters upward. Afterward it moves sideways in a 90° angle 1.6 meters to the left, and loads the part from the Station . Then it moves sideways in a 90° angle 1.6 meters to the right and drives backward to the Marker M2 .

On the Marker M2 the AGV rotates 90° to the right and drives via the Marker named M3 to the Marker named M4 . There it unloads the part onto the Station1 and drives back to the AGVPool via the Markers M2 and M1 .

The finished simulation model looks like this:

<!-- image -->

We use the material flow objects and the resource objects with their default settings. We fine-position the AGV in our init method by using the methods setRoute , rotate , and drive of the Transporter .

The source code of our init method looks like this. The comments describe what the instructions accomplish.

```simtalk
var AGV := AGVPool.Cont
AGV.setRoute([M1, M2])             // AGV drives to the marker M2
stopuntil AGV.DestinationWasReached AGV.rotate(-90)                    // AGV rotates 90° to the left
stopuntil AGV.DestinationWasReached
AGV.drive(2)                       // AGV drives 2m upward
stopuntil AGV.DestinationWasReached
AGV.drive(1.6, -90)                   // AGV moves sideways in a
stopuntil AGV.DestinationWasReached   // 90° angle 1.6 m to the left
var MU := Station.Cont
waituntil MU.Finished                 // MU waits until it's processed wait 2                                // MU waits 2 seconds
MU.move(AGV)                          // MU moves to the AGV wait 2                                // AGV waits 2 seconds
AGV.drive(1.6, 90)                    // AGV moves sideways in a
```

##### Prevent AGVs from Colliding

```simtalk
stopuntil AGV.DestinationWasReached   // 90° angle 1.6 m to the right
AGV.drive(-2)                         // AGV drives 2m downward
stopuntil AGV.DestinationWasReached
AGV.rotate(90)                     // AGV rotates 90° to the right
stopuntil AGV.DestinationWasReached
AGV.setRoute([M3, M4])             // AGV drives across M3 to M4
stopuntil AGV.DestinationWasReached
waituntil Station1.empty           // AGV waits until Station1 is wait 2                             // empty, waits 2 seconds
MU.move(Station1)                  // MU moves to Station1 wait 2                             // AGV waits 2 seconds
AGV.setRoute([M2, M1, AGVPool])    // AGV drives via the markers M2 // and M1 back to the AGVPool
```

**Back to Model Transport Systems**

Prevent AGVs from Colliding

In this model we demonstrate how to use the settings of the Distance Control of the Transporter to prevent two AGVs from colliding.

The finished simulation model looks like this.

<!-- image -->

Proceed as follows to create the model:

- Insert an AGVPool that creates the AGVs .
- Insert four Markers each for each of the two Transporters . Transporter1 covers the markers M11 , M12 , M13 , and M14 . Transporter2 covers the markers M21 , M22 , M23 , and M24 .
- Insert an init control that finds an idle AGV in the AGVPool that can do the job. In addition we set the routes of the AGVs .

Then configure the objects.

- We use the default setting of the AGVPool , meaning that the AGV is the Transporter in the folder MUs .

<!-- image -->

- We use the default settings for the Safety Zones of the Transporter .
- We use the default settings of the Distance Control that we created.

<!-- image -->

<!-- image -->

- We programmed the init control that finds an idle AGV in the AGVPool and sets the routes which the AGVs cover.

```simtalk
var AGV1 := AGVPool.getIdleAGV
AGV1.setRoute([M11, M12, M13, M14])
wait 2
var AGV2 := AGVPool.getIdleAGV
AGV2.setRoute([M21, M22, M23, M24])
```

When you run the simulation, you can watch how Transporter2 slows down once Transporter1 enters its Safety Zone 2 and then stops when it enters Safety Zone 1 . Transporter2 continues on its route once Transporter1 passed by safely.

<!-- image -->

To show the defined Safety Zones of the Transporter , select Edit 3D Properties &gt; Tab Appearance &gt; Show Safety Zones .

<!-- image -->

When you move the markers M11 and M12 to the left in the X-Direction , meaning that Transporter2 now arrives first at the point where the routes cross, Transporter1 slows down and stops to let Transporter2 pass. This shows that the safety zone settings and the Distance Control reliably prevent the AGVs from colliding.

Back to Model Transport Systems

<!-- image -->

#### Modeling a Battery-powered Transporter, Basic

Model a Battery-powered Transporter, Basic

In this sample model we show how easy it is to quickly model a battery-powered Transporter . The Transporters drive on a Track moving parts from one point to another. The Exit Control of the Track detects the charge of the battery; if enough power is left, it continues moving parts, if not, it drives onto the Track to the charging station, which charges the battery.

The finished simulation model looks like this:

<!-- image -->

First we duplicated the Transporter in the Class Library and renamed it to TransporterBattery .

- We selected these settings on the tab Battery :

<!-- image -->

- We typed in these instructions into the Charge Control :

```simtalk
if @.BatCharge >= @.BatCapacity
	@.Stopped := false
end
```

Then we modeled the material flow and configured the material flow objects:

<!-- image -->

- We selected these settings in the Source which feeds the Transporters into the plant.

<!-- image -->

- We created an Exit Control in the object Track , which sends a Transporter with a low battery charge on the Track , ChargeBattery in our case, that leads to the charging station.

We typed in this source code:

```simtalk
if @.BatCharge <= @.BatReserve
	@.move(1)
else
	@.move(2)
end
```

- We created two sensors on the object Track and selected these settings.

<!-- image -->

At the sensor with the ID 3 the TransferStation loads the parts onto the loading space of the Transporter .

At the sensor with the ID 1 the PickAndPlace robot unloads the parts from the loading space of the Transporter and places them on the Conveyor at the sensor. We typed in these instructions into the sensor control OnSensor1 .

```simtalk
param SensorID: integer, Front: boolean, BookPos: boolean // Activating the sensor moves the parts on to the designated // destination, namely the PickAndPlace robot.
@.Stopped := true
var Destination:object := PickAndPlace
while not @.Empty
	var MU: object := @.cont
	if not MU.move(Destination)
		stopuntil MU.Location /= @ and not Destination.IsLoading
	end
end
@.Stopped := false
```

- The SourceParts , which produces the parts that the Transporter transports, we use with the default settings.
- For the TransferStation we selected these settings:
- For the PickAndPlace robot , which unloads the parts from the Transporter and places them on the Conveyor , we use a Loading Time and an Unloading Time of 2 minutes each and these settings on the tab Exit .
- For the Conveyor we created this sensor at which the PickAndPlace robot places the parts.

<!-- image -->

<!-- image -->

<!-- image -->

- We created a sensor in the Track named ChargeBattery and selected these settings:

<!-- image -->

**We typed in these instructions into the Sensor Control :**

```simtalk
param SensorID: integer, Front: boolean, BookPos: boolean
@.Stopped := true
@.BatCharging := true
NumberOfBatteryCharges += 1 // increments the number of battery charges // in the Variable
```

- We finally inserted a graphic representing the charging station and the Variable named NumberOfBatteryCharges , which shows how often the batteries were charged.

<!-- image -->

When we now run the simulation, it looks like this.

<!-- image -->

Compare Model a Battery-powered Transporter, Extended

Back to Model Transport Systems

#### Modeling a Battery-powered Transporter, Extended

Model a Battery-powered Transporter, Extended

With the settings on the tab Battery you can model a battery-powered Transporter . The battery has to be charged when the battery charge is lower than the reserve charge of the battery. During battery operation power consumption consists of the driving consumption and the base consumption . Within the charge control of the Transporter we have to prevent that the battery gets discharged all the way and that the Transporter stops because of that. For charging the battery the Transporter requires charge current . The time recharging takes is the difference between the capacity of the battery and its current charge and the charge current of the charging station .

Once the reserve charge during driving or the battery capacity at the end of charging is reached, the charge control of the Transporter is called. We can differentiate these two events in the charge control with the value of the battery charge using the attribute BatCharge .

We will demonstrate how to:

- Model a Battery-powered Transporter, Extended
- Program the Sensor Control for Loading and Unloading the Parts
- Configure Battery-powered Operation of the Transporter
- Program the Battery Controls

The finished simulation model looks like this:

<!-- image -->

Compare Model a Battery-powered Transporter, Basic

Back to Model Transport Systems

Model the Material Flow

In our first step we model the material flow for the battery-operated Transporter .

- The Source constantly creates parts of type MyPart .

<!-- image -->

- These are then moved on to the Buffer . We use the Buffer with its standard settings.
- For the Track we created two sensors with the settings below. The parts are loaded onto the Transporter at the Buffer and they are unloaded at the Station :

<!-- image -->

Make sure that the starting point and the end point of the Track are connected so that the Transporters can drive around in a circle.

- We use the Station and the Drain with their respective standard settings.
- In addition we inserted a Track as the ChargingStation and another Track for the ParkingPosition of the Transporter .
- In our Init Control we create a Transporter each on the Track and on the ParkingPosition .

```simtalk
// create two Transporters .UserObjects.MyTransporter.create(Track, 8) .UserObjects.MyTransporter.create(ParkingPosition)
```

**Back to Model a Battery-powered Transporter, Extended**

Program the Sensor Control for Loading and Unloading the Parts

We would like to load the produced parts from the Buffer onto the Transporter at the first sensor and unload them from the Transporter onto the Station at the second sensor.

We programmed this in our Sensor Control as follows:

```simtalk
param SensorID: integer, Front: boolean, BookPos: boolean // load parts at sensor 1 from the Buffer onto the Transporter
if sensorID = 1
	@.Stopped := true
	repeat
		waituntil Buffer.Occupied prio 1
		Buffer.cont.move(@) wait 3 // the loading time is 3 seconds
	until @.Full
	@.Stopped := false // unload parts at sensor 2 from the Transporter onto the Station
elseif sensorID = 2
	@.Stopped:=true
	repeat
		waituntil Station.Empty prio 1
		@.cont.move(Station)
		wait 3 // the unloading time is 3 seconds
	until @.Empty
	@.Stopped := false
end
```

##### Back to Model a Battery-powered Transporter, Extended

Configure Battery-powered Operation of the Transporter

We configure battery-powered operation of the Transporter on the tab Battery . We entered the settings below:

<!-- image -->

We did not change other settings.

**Excursus: The relative and the absolute path**

For the Charge Control we just entered its name into the text box. Once we click Apply , Plant Simulation highlights the text box in red as it does not find the charge control within the namespace of the Class Library with the specified relative path . We accept that though as the Transporters are created in our Frame named Model and are thus located within the same namespace as the Charge Control .

<!-- image -->

<!-- image -->

<!-- image -->

We entered 0.5 m/s as the speed of the Transporter .

<!-- image -->

We entered our startCharging control as the Entrance Control into the ChargingStation of the Transporter .

<!-- image -->

For the ParkingPosition to which the Transporter with fully charged battery drives we use the standard settings of the Track .

**Back to Model a Battery-powered Transporter, Extended**

Program the Battery Controls

Then we program the battery charge control myBatteryChargeControl . It charges the battery and then, once it is fully charged, moves the Transporter onto the ParkingPosition .

```simtalk
// battery charge control of the Transporter, recognizes that the battery has to be charge, // once the charge is smaller than or equal to the battery reserve
if @.BatCharge <~= @.BatReserve
	@.BatCharging := true   // start charging the battery
	@.transfer(ChargingStation)
elseif  @.BatCharge >~= @.BatCapacity
	@.move(ParkingPosition)  // move Transporter with charged battery to ParkingPosition
end
```

Lastly we program the entrance control of the ChargingStation . It moves the fully charged Transporter from the ParkingPosition onto the Track .

```simtalk
// entrance control of the ParkingPosition
waituntil ParkingPosition.NumMU > 0 prio 1
ParkingPosition.Cont.move(Track, 9)
```

When we now run the simulation, we can trace how the Transporters circulate and first move onto the ChargingStation when the battery charge is low and then move on to the ParkingPosition .

<!-- image -->

Back to Model a Battery-powered Transporter, Extended

**Preparing Data for the Simulation with DataFit**

