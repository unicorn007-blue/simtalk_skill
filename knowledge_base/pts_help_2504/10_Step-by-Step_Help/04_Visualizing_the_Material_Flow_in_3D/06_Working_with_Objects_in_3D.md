### Working with Objects in 3D

#### Work with Objects in 3D

3D provides a number of ways for working with the objects in the scene. You can:

- Insert Objects into the Scene
- Select Objects in the Scene
- Simultaneously Paste Multiple Copies
- Connect Objects in the Scene
- Move an Object With Keyboard Keys
- Move an Object With the Mouse
- Rotate Objects in the Scene
- Scale Objects in the Scene
- Edit Grouped Graphics
- Set the Material of a Graphic
- Use a Different Graphic for an Object
- Add a Layout File to Your Simulation Model
- Work with Length-oriented Objects in 3D
- Set the Capacity of a Material Flow Object
- Set How 3D Shows an Object
- Adapt the 3D Model to the 2D Model
- Use Identical Lengths and Positions in 2D and in 3D
- Create Your Own Objects

Compare Work with the Scene

Compare Control Your View

Compare Work with the Grid

Compare Work with Animation Paths

Compare Modeling Hierarchically [in 3D]

**Back to Visualizing the Material Flow in 3D**

#### Insert Objects into the Scene

You can insert objects into the 3D scene from the Toolbox or the Class Library . They contain the same objects by default.

- To insert an object from the Toolbox , click the object you want to insert with the left mouse button and drag the mouse to the position in the 3D window at which you want to place the object. Click the mouse button to insert the object. Cancel inserting by clicking the right mouse button or by pressing Esc .
- To insert an object from the Class Library , click the object you want to insert with the left mouse button, hold down the mouse button and drag the mouse to the position in the 3D window at which you want to place the object. Then, release the mouse button. As long as you do not release the mouse button, Plant Simulation shows a preview of the object in the 3D window. You can cancel inserting by releasing the mouse outside of the 3D window.
- To insert an object which you copied with Home &gt; Copy or with Ctrl+C to the Clipboard , press Ctrl+V in the 3D window to paste the copy into the object opened in the 3D window. Plant Simulation pastes the copy at the same position which the copied object takes within its location.

To insert an object from the Toolbox :

<!-- image -->

- If you want the object to snap to the closest intersection of two grid lines of where you click the mouse button, click on the Edit ribbon tab.

<!-- image -->

If you want to place the object freely, do not click . Plant Simulation snaps the object according to the settings for aligning to the grid or for aligning the object to the grid and/or to objects.

<!-- image -->

<!-- image -->

**Note**

When you insert Markers into your model, make sure that the Markers are aligned . This prevents Plant Simulation from computing unnecessary roundings between the Markers . Misaligned Markers might occur if you inserted Markers into your model while Show Grid was off.

- Click the object you want to insert with the left mouse button to select it. Then, drag the mouse to the location where you want to place it and release and click the mouse button.
- If need be, you can fine-tune the location of the object in the dialog 3D Properties that clicking on the Home ribbon tab opens.

<!-- image -->

- To open the dialog of the simulation object, click 2D in the dialog 3D Properties or double-click the object in the 3D scene. Modify settings here.

To insert the same object from the Toolbox into a Frame several times, one after the other without interruption, hold down Ctrl and select the object. The object remains selected in the Toolbox after inserting it and you can thus insert several of these objects one after the other. You can exit this mode by clicking the right mouse button or by pressing Esc .

After you inserted objects into your simulation model, you can align them to the grid

**snap to the grid**

,

make them snap to other objects

<!-- image -->

able to do so, make sure that

**See also**

Move an Object With the Mouse

Work with the Grid

Back to Work with Objects in 3D

#### Select Objects in the Scene

When you click the left mouse button in the 3D window, you can:

- Select a simulation object , which is directly located in the object that is opened in the 3D window. Plant Simulation shows selected simulation objects in the 3D window green .
- Select a simulation object , which is located within other simulation objects, when you hold down the Alt / Alt Gr key.

If your keyboard does not have the Alt Gr key, hold down Ctrl-right+Alt-right instead.

- Select any part/MU , which is located in 3D window without having to hold down the Alt / Alt Gr key.
- Select an animatable object , which is directly located in the simulation object that is opened in the 3D window.
- Plant Simulation shows selected animatable objects in the 3D window purple .
- Select a graphic , which visualizes the simulation object that is opened in the 3D window. Plant Simulation shows selected graphics in the 3D window yellow-green .
- Select a displayed manipulator .

Show Grid is on.

<!-- image -->

<!-- image -->

,

make them

<!-- image -->

, or arrange them on the grid . To be

- Select two or more items in the 3D window by holding down the Shift or the Ctrl key and clicking the desired elements with the left mouse button.
- Select several items in the 3D window by dragging a marquee around the desired objects:
- When you do hold down the Shift or the Ctrl key, the selection with a marquee cancels an existing selection.
- When you hold down the Shift or the Ctrl key, the new selection will be added to the existing selection.
- Press Ctrl+A to select all objects in the scene window.

You can modify the selection with the plus-key ( + ) and the minus key ( -), compare the 3D Quick Reference &gt; While Modeling .

To show objects, for example in the statistics report , in the sequence in which you selected them, hold down Shift and click the objects one after the other. In the example below we first clicked Station1 , then Station2 , and then Station3 .

<!-- image -->

Compare Move an Object With the Mouse

Back to Work with Objects in 3D

Simultaneously Paste Multiple Copies At times you may want to paste more than one copy of the object you copied. You might, for example, want to create a Store with a number of shelves.

To paste multiple copies of an object:

- Insert the object you need, for example a Station , into the scene.
- Select the Station and copy it by pressing Ctrl+C .
- Click Paste &gt; Multiple Paste on the Home ribbon tab.
- Enter the number of Stations you would like to paste into the combo box Count . We entered 4 .
- Enter the Offset of the copies from the object you originally placed. Our Station is 2.0 meters wide:

An offset of 2.0 meters on the x-axis pastes 4 copies of the Station with this offset to the original toward the right. Note the initial predefined offset toward the right and downwards. We implemented this to prevent Plant Simulation from pasting the copies one on top of the other in 2D and in 3D.

Click Paste . If need be, move the pasted copies to where you need them.

<!-- image -->

A number of copies of 4 and an offset of 2.0 meters on the x-axis and on the z-axis pastes 4 copies to the right and up of the original Station .

Click Paste . If need be, move the pasted copies to where you need them.

Back to Work with Objects in 3D

<!-- image -->

#### Connect Objects in the Scene

To connect material flow objects, which you inserted into your model, with the object Connector :

<!-- image -->

<!-- image -->

- Click on the View ribbon tab to display the grid. Click on the View ribbon tab to show
- connectors in the window of the 3D scene.
- Click the Connector in the Toolbox on the tab MaterialFlow .
- Click the source object, where the connection will start, once with the left mouse button. Plant Simulation attaches a line symbolizing the Connector to the mouse pointer. The arrow in the middle shows the direction of the connection.

<!-- image -->

<!-- image -->

- Drag the mouse to the destination object at which the connection will end, and click the left mouse button to establish the connection.
- To terminate connect mode before you click the destination object, click the right mouse button or press Esc .

To connect several objects one after the other, without interrupting the connecting process, hold down Ctrl .

- Attach the outgoing connection to the first object.
- Drag the mouse to the succeeding object.
- Click the left mouse button to attach the incoming Connector to the successor.
- You can also connect the objects in the 2D part of your model, which will simultaneously insert the connections into the 3D part, when you opened 3D .

<!-- image -->

To show or hide connections in the scene window, click

**Note**

By default 3D does not show Connectors , when you create a model in 2D and then update it in 3D.

Compare Connect Objects in the Frame

Compare Undo and Redo

Back to Work with Objects in 3D

#### Move Objects in the Scene

Move Objects in the Scene

3D provides several ways to move an object in the scene.

You can:

- Move an Object With the Mouse
- Move an Object With Keyboard Keys
- Move an Object Precisely

Back to Work with Objects in 3D

Move an Object With the Mouse

To manipulate an object, click it with the left mouse button and drag the mouse.

When you show the grid, manipulating the object relates to the grid plane. When you hide the grid, manipulating relates to the view plane.

- To move the object freely on the grid plane , click the left mouse button, and drag the mouse.
- To move the object vertically up or down , hold down the Alt/Alt Gr key and the left mouse button, and drag the mouse.

**Note**

If you are working with a Frame with visible content , the order of pressing the Alt/Alt Gr key and clicking the mouse button determines what 3D does: When you hold down the Alt/Alt Gr key before you click the mouse, you select simulation objects located within the Frame . In any case, holding the Alt/Alt Gr key down moves the selected object vertically up or down.

If your keyboard does not have the Alt Gr key, hold down Ctrl-right+Alt-right instead.

Compare

Move an Object With Keyboard Keys

Compare Move an Object Precisely

Compare Rotate an Object Precisely

Compare

Select Objects in the Scene

Back to Move Objects in the Scene

##### Move an Object With Keyboard Keys

Instead of using the mouse to manipulate the selected object, you can also hold down the Ctrl , or Shift keys and press one of the arrow keys on the keyboard:

To move the selected object on the grid plane , press the designated arrow key:

- Press the left arrow to move the object to the left by 10% of the distance set in the dialog Edit Grid and Base Plate Settings under Grid Lines [3D] &gt; Select for Snapping .
- Press the left arrow and hold down Shift to move the object to the left by the distance set in the dialog Edit Grid and Base Plate Settings under Grid lines &gt; Select for Snapping .
- Press the right arrow to move the object to the right by 10% of the distance set in the dialog Edit Grid and Base Plate Settings under Grid lines &gt; Select for Snapping .
- Press the right arrow and hold down Shift to move the object to the right by the distance set in the dialog Edit Grid and Base Plate Settings under Grid lines &gt; Select for Snapping .
- Press the up arrow to move the object upward by 10% of the distance set in the dialog Edit Grid and Base Plate Settings under Grid lines &gt; Select for Snapping .
- Press the up arrow and hold down Shift to move the object upward by the distance set in the dialog Edit Grid and Base Plate Settings under Grid lines &gt; Select for Snapping .
- Press the down arrow to move the object downward by 10% of the distance set in the dialog Edit Grid and Base Plate Settings under Grid lines &gt; Select for Snapping . Press the down arrow and hold down Shift to move the object downward by the distance set in the
- dialog Edit Grid and Base Plate Settings under Grid lines &gt; Select for Snapping .

To move the selected object vertically up or down , hold down Ctrl and press the designated arrow key:

- Hold down Ctrl and press the up arrow to move the object upward in the z-direction by 10% of the distance set in the dialog Edit Grid and Base Plate Settings
- Hold down Shift and Ctrl and press the up arrow to move the object upward in the z-direction by the distance set in the dialog Edit Grid and Base Plate Settings under Grid lines &gt; Select for Snapping .
- Hold down Ctrl and press the down arrow to move the object downward in the z-direction by 10% of the distance set in the dialog Edit Grid and Base Plate Settings under Grid lines &gt; Select for Snapping .
- Hold down Shift and Ctrl and press the down arrow to move the object downward in the z-direction by the distance set in the dialog Edit Grid and Base Plate Settings under Grid lines &gt; Select for Snapping .

To rotate the selected object, hold down Ctrl and press the designated arrow key:

- Hold down Ctrl and press the left arrow to rotate the object counterclockwise by 1°. Hold down Shift and Ctrl and press the left arrow to rotate the object counterclockwise by 45°.

##### Move an Object Precisely

- Hold down Ctrl and press the right arrow to rotate the object clockwise by 1°. Hold down Shift and Ctrl and press the right arrow to rotate the object clockwise by 45°.

Compare Move an Object With the Mouse

Compare Edit Length-oriented Objects with Keyboard Keys

Back to Move Objects in the Scene

Move an Object Precisely

At times manually moving an object with the mouse or with keyboard keys will not be accurate enough for your purposes. Then, you can enter exact values into the text boxes in the dialog 3D Properties &gt; Tab Transformation to fine-tune the position, the rotation, and the scale of the selected object:

**To precisely move an object:**

- Select the object you would like to move.
- Press the spacebar or click on the Home ribbon tab and click the tab Transformation
- .
- To move the object to the right on the x-axis , click in the text box and roll the mouse wheel forward to increase the position in steps of 0.1 meters. Hold down Shift and roll the mouse wheel forward to increase the position in steps of 1 meter.

<!-- image -->

<!-- image -->

To move the object to the left on the x-axis , click in the text box and roll the mouse wheel backward to decrease the position in steps of 0.1 meters. Hold down Shift and roll the mouse wheel forward to decrease the position in steps of 1 meter.

- Use the same procedure for the y-axis .

- Use the same procedure for the z-axis .
- Click Apply to apply your change and to see if the meet your requirements.
- Click OK once you're satisfied with the results.

Transformations of an object, such as moving, rotating or scaling it, in one 3D window are not immediately updated in all other 3D windows, but only after you deselect the changed object in its 3D window.

Compare Edit Grouped Graphics

Back to Move Objects in the Scene

#### Rotate Objects in the Scene

Rotate Objects in the Scene

3D provides several ways of rotating an object in the scene window.

You can:

- Rotate an Object with Keyboard Keys
- Rotate an Object Precisely

Rotate an Object with Keyboard Keys

When you manually rotate an object around an axis by holding down Shift+Ctrl and pressing the left or the right arrow on the keyboard, 3D uses the settings under Rotation in the dialog 3D Properties &gt; Transformation &gt; Settings for the Rotation . You can either use the default settings or define the settings that meet your modeling needs.

To manually rotate an object in the 3D window with the settings you define:

- Click on the View ribbon tab to show the grid.
- Click the object you want to rotate.
- To rotate the object by 1° to the left, hold down Ctrl and press the left arrow . To rotate the object by 1° to the right, hold down Ctrl and press the right arrow .
- To rotate the object by 45° to the left, hold down Ctrl and the Shift and press the left arrow To rotate the object by 45° to the right, hold down Ctrl and Shift and press the right arrow .
- To rotate the object by 10° on the x-axis to the left, press 7 on the numeric keypad.
- .

To rotate the object by 10° on the x-axis to the right, press 8 on the numeric keypad.

- To rotate the object by 10° on the y-axis to the left, press 4 on the numeric keypad.
- To rotate the object by 10° on the y-axis to the right, press 5 on the numeric keypad.
- To rotate the object by 10° on the z-axis to the left, press 1 on the numeric keypad. To rotate the object by 10° on the z-axis to the right, press 2 on the numeric keypad.

To define settings for manually rotating an object:

- Select 3D Properties &gt; Transformation &gt; Settings for the Rotation on the Home ribbon tab.
- Define the settings how 3D rotates the object in the text boxes next to Axis .

<!-- image -->

You can either click one of the buttons to rotate the object around that axis, or you can set the axis yourself.

- To rotate the object around an arbitrary axis, defined by the x-component, y-component and zcomponent of this axis:

Enter a value for the x-component of the rotation axis.

Enter a value for the y-component of the rotation axis.

Enter a value for the z-component of the rotation axis.

- Then, click Apply to apply these settings, so that they are active when you rotate the object.

**Note**

Transformations of an object, such as moving, rotating or scaling it, in one 3D window are not immediately updated in all other 3D windows, but only after you deselect the changed object in its 3D window.

**Back to Rotate Objects in the Scene**

##### Rotate an Object Precisely

At times manually rotating an object with keyboard keys will not be accurate enough. Then, you can enter exact values into the text boxes in the dialog 3D Properties &gt; Tab Transformation to fine tune the position, the rotation, and the scale of the selected object:

To precisely rotate an object:

- Click it with the left mouse button to select it.
- Press the spacebar or click on the Home ribbon tab or press Ctrl+3 .
- To rotate the object around an arbitrary axis, defined by its x-component, y-component and zcomponent:

<!-- image -->

Enter a value for the x-component of the rotation axis.

Enter a value for the y-component of the rotation axis.

Enter a value for the z-component of the rotation axis.

<!-- image -->

- Type in the offset to the center of the object for the rotation around the x-axis, the y-axis, and the z-axis. Normally you do not type in another value but apply the presets of 0, 0, 0. This rotates the object around its center.
- Enter the angle of rotation in degrees into the text box.
- To apply your changes if you are satisfied with the results of your changes, click Apply .

Transformations of an object, such as moving, rotating or scaling it, in one 3D window are not immediately updated in all other 3D windows, but only after you deselect the changed object in its 3D window.

Back to Rotate Objects in the Scene

#### Scale Objects in the Scene

To scale an object in the 3D window, type exact values into the text boxes in the dialog 3D Properties &gt; Tab Transformation &gt; Scale to fine tune the position, the rotation, and the scale of the selected object:

**To scale an object:**

- Click it with the left mouse button to select it.

<!-- image -->

Press the spacebar or click on the Home ribbon tab or press Ctrl+3 .

<!-- image -->

- Select Uniform to scale the object with the same factor for all three dimensions and to not distort it while scaling it. This automatically enters the value you type into one text box into the remaining two text boxes. This way you do not have to manually type the same value into each text box again and again.

Type in a value into the text boxes for the x-axis, the y-axis and the z-axis to scale the object on the respective axis with that factor. Typing 0.5 , for example, halves the size of the object on the axis for which you typed it, typing in 2 doubles its size on that axis.

**Note**

You can only type in non-zero values.

- Clear Uniform to scale the object with the factors you type in for the different dimensions. When you type in different values, it does distort the object, for example lengthens or shortens it.

Type a value into the text boxes for the x-axis, the y-axis and the z-axis to scale the object with that factor on the respective axis.

- Click Set Dimensions . Then type in the physical size of the scaled object considering the graphics of the object.

<!-- image -->

<!-- image -->

Transformations of an object, such as moving, rotating or scaling it, in one 3D window are not immediately updated in all other 3D windows, but only after you deselect the changed object in its 3D window.

Back to Work with Objects in 3D

#### Working with Length-oriented Objects in 3D

Work with Length-oriented Objects in 3D

The Conveyor , the Track , the TwoLaneTrack , the Footpath , the Container , the Transporter , and the Pipe are length-oriented objects whose length and dimensions are used in the simulation.

Plant Simulation generates the graphics automatically according to their settings for these objects and for the Turnplate , the Turntable , the Converter , the AngularConverter , and the Store .

In the 3D window you can.

- Edit Length-oriented Objects with the Mouse
- Edit Length-oriented Objects with Keyboard Keys
- Edit Length-oriented Objects Precisely
- Model Differences in Height Between Conveying Elements
- Model a Spiral Conveyor

Compare Generated and Non-Generated Graphics

Compare Work with Length-oriented Objects in 2D and 3D

Compare Change the Shape of a Segment

**Back to Work with Objects in 3D**

##### Edit Length-oriented Objects with the Mouse

To edit the shape and the dimensions of the length-oriented objects and of the Store with the mouse, click

<!-- image -->

Show Manipulators on the Edit ribbon tab. This shows all manipulators of the objects. Then, click one of the manipulators with the left mouse button and drag the mouse to the new position and release the mouse button.

The appearance of the manipulator differs from object to object. For the length-oriented objects the manipulator at the start and at the end of the object is cut off. When you attach an object of the same type to the other object, the two combined halves result in a complete manipulator again. When you move the mouse over a manipulator, Plant Simulation shows a tooltip .

<!-- image -->

These examples show what you can accomplish with the manipulators:

- Here we selected Anchor Point 3 of the TwoLaneTrack and dragged the mouse to the left to shorten the first segment.
- Here we selected Anchor Point 3 of the Conveyor , we held down Ctrl and pressed the Up arrow . This moves the anchor point and thus this part of the Conveyor up. This way you can raise individual segments, for example to allow Workers to walk underneath them or to allow forklifts to pass underneath. Hold down Ctrl and the Up arrow repeatedly to move the anchor point step-by-step.

<!-- image -->

<!-- image -->

<!-- image -->

- Here we selected the Top right corner of the Store and dragged the mouse to the top right to enlarge the graphic of the Store . The changed size is reflected in the width and the depth of the Store and in the length and the width of the animation area .

<!-- image -->

<!-- image -->

To rotate the Store around its center, click the rotation manipulator and drag the mouse to the left or to the right.

Back to Work with Length-oriented Objects in 3D

<!-- image -->

###### Video on YouTube

[https://youtu.be/Kznlnw5BJGc?si=jK3z2M42kfyRVhUp&amp;t=165](https://youtu.be/Kznlnw5BJGc?si=jK3z2M42kfyRVhUp&t=165)

<!-- image -->

Editing Length-oriented Objects with Keyboard Keys

Edit Length-oriented Objects with Keyboard Keys

**You can:**

- Edit Manipulators with Keyboard Keys
- Move Sensors with Keyboard Keys

Back to Work with Length-oriented Objects in 3D

Compare Keyboard Shortcuts for Inserting a Curved Object

Compare Move an Object With Keyboard Keys

Edit Manipulators with Keyboard Keys

You can use Page Up to lengthen the selected manipulator and to shorten it with the Page Down .

- Select the fi rst manipulator of a length-oriented object and press Page Up to lengthen the neighboring segment toward this manipulator.

Page Up lengthens a linear segment in a linear way.

It increases the curve angle for a horizontal curved segment.

It has no effect on a vertical curved segment.

<!-- image -->

Select the last manipulator of a length-oriented object and press Page Up to shorten the neighboring segment toward this manipulator.

Page Up shortens a linear segment in a linear way.

It decreases the curve angle for a horizontal curved segment.

It has no effect on a horizontal curved segment.

<!-- image -->

- Select the fi rst manipulator of a length-oriented object and press Page Down to shorten the neighboring segment toward this manipulator.

Page Down shortens a linear segment in a linear way.

It decreases the curve angle for a horizontal curved segment. It has no effect on a vertical curved segment.

Select the last manipulator of a length-oriented object and press Page Down and to lengthen the neighboring segment toward this manipulator.

Page Down lengthens a linear segment. It increases the curve angle for a horizontal curved segment. It has no effect on a vertical curved segment.

##### Back to Edit Length-oriented Objects with Keyboard Keys

Move Sensors with Keyboard Keys

You can use Page Up and Page Down to move sensors .

- Select a sensor and press Page Up to move the sensor to the left. The left arrow does the same.
- Select a sensor and press the Page Down to move the sensor to the right. The right arrow does the same.

Back to Edit Length-oriented Objects with Keyboard Keys

<!-- image -->

##### Edit Length-oriented Objects Precisely

You can change the length-oriented objects in your simulation model manually with the mouse.

For some purposes this is not accurate enough though. If this is the case, you can edit the position , the rotation , and the scaling of the object in the dialog Edit 3D Properties on the Tab Transformation and on the tab Appearance of the Length-oriented Objects , by entering exact values into the text boxes.

- Select the object that you want to edit.
- Press the spacebar or click on the Home ribbon tab and click the tab Transformation .
- Edit the values of the position , the rotation , and the scaling .
- Click Apply to apply your changes once you are satisfied with the results.
- If necessary, you can edit additional settings on the tab Appearance .

<!-- image -->

<!-- image -->

Back to Work with Length-oriented Objects in 3D

Model Differences in Height Between Conveying Elements

With the length-oriented objects you can create straight and curved ascending and descending slopes in your simulation model.

Proceed as follows to model straight ascending and descending slopes :

- Select the length-oriented object that you want to insert into the Frame . In our example we insert a Conveyor that is 4 meters long. Then, click Show Manipulators on the 3D ribbon tab to show the manipulators.

<!-- image -->

- Click the right manipulator with the right mouse button, hold down Ctrl and press the Up arrow until the right side of the Conveyor has the required height.
- To append a segment to the ascending slope, click the Conveyor with the right mouse button and select Segments &gt; Append .
- Type in the radius and the angle of the segment into the dialog Line/Arc Parameters . Click in the scene to append the segment. Click Finish to close the dialog.

<!-- image -->

<!-- image -->

<!-- image -->

Proceed as follows to model curved ascending and descending slopes :

- Select the length-oriented object that you want to insert into the Frame . In our example we insert a Conveyor .
- Press the Up arrow on the keyboard to insert an ascending slope, a curve pointing upward in the z-dimension .

Press the Down arrow on the keyboard to insert a descending slope, a curve pointing downward in the z-dimension .

- Type in the Radius and the Angle of the segment into the dialog Line/Arc Parameters .

**Note**

The greatest allowed curve angle is 90°.

<!-- image -->

- Click with the mouse into the scene to insert the segment. Click Finish to close the dialog.

The result looks like this:

<!-- image -->

<!-- image -->

When you click the Segments button, the selected check box in the dialog shows, that our Conveyor contains a vertical curve .

<!-- image -->

- To append segments to the ascending slope, click the Conveyor with the right mouse button and select Segments &gt; Append .
- Type in the Radius and the Angle of the segment into the dialog Line/Arc Parameters . Click the left mouse button to insert the segment you just defined and click Finish in the dialog.

<!-- image -->

- The result looks like this.
- Repeat this until the Conveyor has the shape that you need.

<!-- image -->

<!-- image -->

<!-- image -->

Compare Keyboard Shortcuts for Inserting a Curved Object

Back to Work with Length-oriented Objects in 3D

Model a Spiral Conveyor

You can use the Conveyor to model spiral conveyors in your simulation model.

A spiral conveyor transports products upward or downward thus leveling differences in height within your production facility. Depending on the height difference you can also use the spiral conveyor as a buffer.

Proceed as follows to model the spiral conveyor:

- Click the Conveyor on the tab MaterialFlow of the Toolbox .

##### Model a Spiral Conveyor

- Drag the mouse in the 3D window to the position at which you would like to insert the conveyor.
- We used the standard settings in the dialog Line/Arc Parameters . If you need to use a wider arc, enter a greater radius .
- Hold down Ctrl to insert the arc segments of the spiral conveyors. Click several times one after the other to insert the arc segments. The segments are initially placed on a single layer directly above each other. We first inserted a straight segment, then added 13 arc segments, and finished with a straight segment.
- Press F7 to open the Segments table.

<!-- image -->

<!-- image -->

<!-- image -->

- Enter the additional offset to the base height of the preceding segment into the cell ΔZ . We typed in 0.5 meters.
- Click OK in the dialog Segments .

<!-- image -->

**The result looks like this:**

<!-- image -->

You can change the settings of the spiral conveyor on the tab Appearance .

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

Back to Work with Length-oriented Objects in 3D

#### Setting the Capacity of a Material Flow Object

Set the Capacity of a Material Flow Object

While you set the capacity of a material flow object in 2D in two dimensions , you set the position of a part on a simulation object in 3D in three dimensions .

**You can:**

- Define the Capacity of a Simulation Object
- Define the Animation Area of a Simulation Object

Back to Work with Objects in 3D

Define the Capacity of a Simulation Object

For the simulation object you enter the capacity, i.e., the number of parts the objects ParallelStation , Sorter , Store , Transporter , and Container can hold, in two dimensions . Type the respective values into the text boxes X-Dimension and Y-Dimension on the tab Attributes .

<!-- image -->

Plant Simulation places the MUs onto the animation points that you defined in the icon of the class of the object.

<!-- image -->

To view and to set animation points in the icon of a built-in object:

- Click Edit Icons on the Home ribbon tab.
- Click the Animation ribbon tab of the Icon Editor , compare Set and Link Animation Points and Lines .

Back to Set the Capacity of a Material Flow Object

##### Define the Animation Area of a Simulation Object

Whereas you define the capacity of the objects in 2D in two dimensions , you set the animation of the simulation object in 3D in three dimensions on the animation area .

<!-- image -->

To set the animation area of an object with matrix loading space of type Store ( ParallelStation , Sorter , Store , Transporter , Container ), of the PlaceBuffer , and the Worker in 3D, proceed as follows:

- Click the object with the right mouse button to select it.
- Select Edit 3D Properties &gt; MU Animation &gt; Area &gt; Animation Area .

In our example we demonstrate how to place cylinder-shaped containers in a storage box . This resembles a bottling plant in which the filled bottles are put into cases.

Our finished model looks like this:

<!-- image -->

A Source each produces the storage boxes and the cylinder-shaped containers . The AssemblyStation places the containers into the storage boxes and then moves them on across a Conveyor and a Station to the Drain .

Proceed as follows to create the simulation model:

- Insert two Sources . We named them SourceStorageBoxes and SourceCylinders .
- Insert an AssemblyStation . We selected the settings below:
- Insert a Conveyor . We used a Conveyor of type Guide-railed belt conveyor .
- Insert a Station and a Drain .
- Make sure that all objects are connected with Connectors .

<!-- image -->

As we need customized MU Types for the storage boxes and the cylinder-shaped containers , we duplicate the Part and the Container in the folder MUs in the Class Library .

- Press F2 and rename the duplicated container from Container to StorageBox .

To configure the storage box :

- Click the storage box with the right mouse button and open it in 3D.
- Click with the right mouse button into the background of the 3D window and select Exchange Graphics . We selected the storage box below.

<!-- image -->

Click Yes in the message dialog that Plant Simulation shows.

<!-- image -->

As you remember the s3D files do not only contain the graphic of the object, but also information about its dimensions and animation data.

If you click No , Plant Simulation does not apply the adjustments of the dimensions of the storage box and scales it to the current size of the MU named Container , as the check box Scale Automatically on the tab Transformation is selected by default.

- Type in the dimensions in the X-Dimension , Y-Dimension , and Z-Dimension , that set its capacity.

<!-- image -->

- Press F2 and rename the duplicated part to Canister .

To configure our Canister :

- Click the Canister with the right mouse button and open it in 3D.
- Click the default graphic of the Part and delete it. We are going to create our own graphic for our Canister .

Click the Edit ribbon tab and click Cylinder . Type in the values below. Click Create . Make sure that our Canister is placed on the origin of the grid.

<!-- image -->

<!-- image -->

- Now we have to define the length , the width , and the height of our Canister . Double-click it in the Class Library . Type in these values:

<!-- image -->

Run the simulation and watch how the AssemblyStation places 12 containers each in a storage box and then moves the full storage box on.

The animation area of the storage box , which is activated by default, makes sure that the canisters are distributed evenly across the bottom of the storage box . In doing so, Plant Simulation automatically uses these settings:

<!-- image -->

- Click Show/Hide , to show the animation area in the 3D window to see what it looks like. Plant Simulation shows the animation area proper in red with a red orientation indicator in the center.
- The orientation &gt; XY plane evenly distributes the containers in the x-y-direction.
- For the length Plant Simulation only uses 94 % of the Length of the graphic of the storage box of 80 cm and for the width only 92 % of the Width of 60 cm. Plant Simulation automatically subtracted the Wall Thickness of the storage box from the dimensions of the Animation Area . Plant Simulation uses the area settings that we defined in the s3D graphic.
- For the Z-Position of the center Plant Simulation automatically entered 0.05 m as the bottom of the storage box has a height of 5 cm.

<!-- image -->

Stack Parts in the Store demonstrates how to distribute parts across the storage area and how to stack them.

<!-- image -->

Compare Model a Bottle

Compare Animate Bricks on the Animation Area of the Brick Carrier

Compare Animate Brick Carriers on the Animation Area of the Truck

Compare Model a Worker Who Carries Several Parts in 3D

#### Use Identical Lengths and Positions in 2D and in 3D

In most cases you want the respective objects in 3D and in 2D to have the same lengths to represent your plant as true-to-life as possible. In addition, a smooth animation of a simulation model in 3D requires animation paths that match the length of the respective objects in 2D .

By default Plant Simulation uses the same values for the length of all objects , or a single object you selected, in 2D and in 3D. To check this, click Edit 3D Properties on the Home ribbon tab. Then, click the tab Transformation and make sure that Connect 2D and 3D Positions and/or Connect 2D and 3D Rotations are active.

**Note**

Plant Simulation only shows the check boxes for a 2D and 3D model .

<!-- image -->

Back to Work with Objects in 3D

#### Adapt the 3D Model to the 2D Model

When you are modeling in 2D in a 2D and 3D model while 3D is active and when your model contains a Frame containing objects, you might be surprised how the model looks with the standard settings.

<!-- image -->

In our sample model the Frame contains two Interfaces and a Station .

<!-- image -->

If Show Content is active, the content of the Frame , i.e., the Interfaces and the Station , are shown on the same layer as the other material flow objects. This might look strange at first sight, compare the first screenshot.

<!-- image -->

To make the 3D model look like the 2D model, we clear the check box Show Content .

<!-- image -->

Our model then looks like this and matches what we expected to see:

<!-- image -->

Compare Set How 3D Shows an Object

Back to Work with Objects in 3D

