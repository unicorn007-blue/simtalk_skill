### Working with Animation Paths

#### Work with Animation Paths

Animation paths consist of a set of points in space describing the path on which an animated moving object moves on the material flow objects or through the scene. The cameras, through which you view the scene when you fly through it, also use animation paths.

The animatable objects have the animation paths described below. The procedure for creating and editing the different path types are only slightly different. For this reason we describe the common properties here.

**· MU animation paths**

You can create and edit animation paths and the animation area , on which the parts are animated under Edit 3D Properties &gt; Tab MU Animation on the Home ribbon tab.

<!-- image -->

**· Self animation paths**

You can create and edit paths on which the object itself is animated by clicking Edit 3D Properties &gt; Tab Self Animation on the Home ribbon tab.

The anchor points of the self animation paths are the vertices of the line , polycurve , or spline on which the selected object itself moves. You can, for example, use it a self animation path to simulate the movement of a robot.

The polycurve animation anchor points are the vertices of a curved path, i.e., a sequence of curved and straight lines , on which the material flow object itself moves.

The spline animation anchor points are the vertices of a spline curve.

**· Camera animation paths**

You can create and edit paths on which the camera moves through the 3D scene in the Frame by clicking Edit 3D Properties &gt; Tab Camera Animation on the Home ribbon tab.

The anchor points of the camera animation paths are the vertices of the line , polycurve , or spline on which the camera moves through the scene in the Frame .

The polycurve animation anchor points are the vertices of a curved path, i.e., a sequence of curved and straight lines , on which the camera moves.

The spline animation anchor points are the vertices of a spline curve.

Compare Model Joints and Poses

Back to Visualizing the Material Flow in 3D

##### Videos on YouTube

[https://youtu.be/YleFq6afRs4?si=QsQRL-NA5J-OMGpK&amp;t=145](https://youtu.be/YleFq6afRs4?si=QsQRL-NA5J-OMGpK&t=145)

[https://youtu.be/jHOZhlwGhkQ?si=0AsRC64JxvckO1sM&amp;t=623](https://youtu.be/jHOZhlwGhkQ?si=0AsRC64JxvckO1sM&t=623)

#### Create an Animation Path

When you create a new, initial animation path, you will proceed as follows.

- Open the dialog Edit 3D Properties . Click the Tab MU Animation , or the Tab Self Animation , or the Tab Camera Animation depending on the path you want to create.
- Click Add .
- Enter a unique name for the path, if you are creating an animation path. As a rule you will use the Default path for the animation.
- Select the Path type you would like to create.

<!-- image -->

If objects, such as the Store or the ParallelStation , have several defined locations for placing incoming mobile objects, you can distribute them on the animation area on the tab MU Animation .

- Click OK to create the path you just defined. Initially this path consists of a single anchor point located at the origin of the selected object.
- Extend and/or edit the new initial path by clicking Edit 3D Properties &gt; MU Animation/Self Animation/Camera Animation &gt; Edit &gt; Path Anchor Points on the Home ribbon tab.

Compare Insert Curved and Straight Segments

Compare Draw Straight and Curved Segments with a 90° Angle

Compare Draw Straight and Curved Segments without Fixed Values

Back to Edit an Animation Path

##### Videos on YouTube

[https://youtu.be/YleFq6afRs4?si=QsQRL-NA5J-OMGpK&amp;t=145](https://youtu.be/YleFq6afRs4?si=QsQRL-NA5J-OMGpK&t=145)

[https://youtu.be/h2cFAH46ESQ?si=39K86uqevyTU2N3Y&amp;t=870](https://youtu.be/h2cFAH46ESQ?si=39K86uqevyTU2N3Y&t=870)

#### Create an Animation Path that Rotates Objects

To create an animation path, which causes a circular rotation of an object, for example the movement of the arm of a crane, by setting parameters for the rotation instead of by editing anchor points:

- Select the material flow object or the scene object and click Edit 3D Properties on the Home ribbon tab.
- To rotate the MUs that the selected object processes, click the Tab MU Animation To rotate the object itself , click the Tab Self Animation .
- .
- Click Add . Enter a name for the rotation path into the dialog Create Rotation Path that opens. Select the Path type &gt; Rotation Path [MU animation] - Lines .

<!-- image -->

- Edit the settings in the dialog Create Rotation Path :

Enter the Start Angle where the rotation starts. Enter the End Angle where the rotation ends. 3D only rotates the MU if these values are not identical. The values can be greater than 360 degrees and smaller than -360 degrees to execute more than an entire rotation.

Start Angle and End Angle set the direction of the rotation, depending on which value is the greater one:

- An End Angle greater than the Start Angle results in a clockwise rotation.
- An End Angle smaller than the Start Angle results in a counter-clockwise rotation.
- Enter the values for the Axis around which you want to rotate the MUs .
- Normally, you will use the Z-Axis (0,0,1) to rotate the object on the XY plane.
- You also can define the Y-Axis (0,1,0) to rotate the object on the XZ plane or the
- X-Axis (1,0,0) to rotate the object on the YZ plane.

Naturally you can also define any other axis to rotate the object diagonally in 3D space.

To tilt the rotation axis, and thus the way the MU rotates, you would enter a value into at least two text boxes.

You can change one, two or three settings to tilt the axis the MU rotates around on the surface of the object.

- Enter the Center point of the rotation in the coordinate system of the selected object. If the center is not the same as the start position, the rotated object moves on a circular arc and stops at a different position than its starting point, except after a 360 degree rotation.
- Click Apply to compute the animation path. This path is the trace on which the animated object moves. The movement on this path is the rotation.

**Note**

You can use the method \_3D.SelfAnimations.scheduleRotation to run self-rotations or camerarotations without having to create a path.

- To test the rotation path you defined, select an object and start the test animation.

<!-- image -->

- If the rotation movement does not meet your expectations, open the dialog Create Rotation Path again, and edit the parameters there. Then, click Apply and test the settings again until the rotation meets your needs.
- To change the duration of one or more individual rotation steps:
- Select the path in the list, and click Edit .
- Select the anchor point in the dialog Path Anchor Points and click Edit Values to open the dialog Edit Anchor Point .

Under Time you can edit the time of every anchor point, which matches the rotation steps.

<!-- image -->

Compare Rotation path [camera animation] - Lines

Back to Edit an Animation Path

#### Edit an Animation Path

To work with animation paths of parts (MUs) on an object , do one of the following:

<!-- image -->

- Select the object and click Edit 3D Properties on the Home ribbon tab.

- Click the Tab MU Animation in the dialog Edit 3D Properties and create a new animation path or edit an existing animation path.

<!-- image -->

To work with animation paths on which the object itself is animated in the scene , do one of the following:

<!-- image -->

- Select the object and click Edit 3D Properties on the Home ribbon tab.
- Click the Tab Self Animation in the dialog Edit 3D Properties and create a new animation path or edit an existing animation path.

<!-- image -->

To work with camera animation paths of the Frame , do one of the following:

<!-- image -->

- Select the Frame , and click Edit 3D Properties on the Home ribbon tab.
- Click the Tab Camera Animation in the dialog Edit 3D Properties and create a new camera animation path or edit an existing camera animation path.

Note Only the Frame provides the tab Camera Animation .

<!-- image -->

In or from the dialog you can:

- Create an Animation Path .
- Test an Animation Path .
- Edit an Animation Path with the Mouse .
- Edit an Animation Path via Anchor Points .
- Create an Animation Path that Rotates Objects .
- Rename an animation path.
- Delete an animation path.

Back to Work with Animation Paths

#### Edit an Animation Path with the Mouse

When you edit a path in the scene window with the mouse, you will follow these basic procedures.

- Open the dialog Edit 3D Properties . Click the tab MU Animation [3D] , the tab Self Animation , or the tab Camera Animation [Frame] depending on the path you want to edit.
- Select the name of the path you would like to edit and click Edit .

<!-- image -->

- To show the selected path in the scene window, click the button in the cell Show under animation paths . 3D then shows one or several graphics for the anchor points ( node graphics ), connected by a line that symbolizes the path positions, in the scene. You can display several paths at once, but that only one path is active at any one time. Select any one of the anchor points of the path to activate it.
- To add new anchor points to the path, click Extend and click the left mouse button at the position where you would like to insert a new anchor point. Repeat this as often as you need, until the path has the shape you want.
- To change the shape of the path, select an anchor point and manipulate it with the mouse and/or use the settings by clicking Edit 3D Properties &gt; Tab Transformation on the Home ribbon tab.

<!-- image -->

When you drag an anchor point in the X-direction/Y-direction, Plant Simulation also drags the connected curved segments in both directions (until the next straight segment follows).

- To rotate an anchor point, click it, hold down the left mouse button, and drag the mouse, and/or click Edit 3D Properties &gt; Transformation .

**Note**

When you rotate a anchor point describing an animation path, this also rotates any MU moving along that path.

- To delete a part of the path, select an anchor point and press Delete . This removes the selected anchor point from the path, thus modifying its shape.

Back to Work with Animation Paths

#### Edit a Curved Path with the Mouse

In addition to editing any of the path types with the mouse, you can edit polycurve paths as follows:

- Add new anchor points to the animation path by clicking Extend .
- To add a straight segment , click the left mouse button at the position where you would like to insert a new anchor point.
- To add a curved segment , hold down Ctrl , and click the left mouse button at the position where you would like to insert a new anchor point.
- Repeat this as often as you need, until the path has the shape you want.
- Change the shape of a straight segment by selecting an anchor point and by dragging the mouse.

When you drag an anchor point in the X/Y-direction, 3D also drags attached curved segments (until the next straight segment follows) in both directions.

**Note**

When you insert a Track , a TwoLaneTrack , a Conveyor , or a FootPath with active Curve mode in Plant Simulation 2D, you have to select the corresponding 3D object in 3D and create a Polycurve/Spline path for it. Then, edit the path as described above.

Compare Tab Curve [general description] in Plant Simulation 2D

Compare Model Differences in Height Between Conveying Elements

Compare Insert Curved and Straight Segments

Compare Draw Straight and Curved Segments with a 90° Angle

Compare Draw Straight and Curved Segments without Fixed Values

**Back to Work with Animation Paths**

#### Edit an Animation Path via Anchor Points

At times it may not be precise enough to Edit an Animation Path with the Mouse . Then, you can enter exact values into the dialog Path Anchor Points :

- Open the dialog Edit 3D Properties . Select the animation path you would like to edit on the Tab MU Animation , on the Tab Self Animation , or on the Tab Camera Animation .
- Click Edit .
- Select the anchor point you would like to edit and in the dialog Path Anchor Points and then click the button Edit Values or double-click the row in the table.

<!-- image -->

<!-- image -->

- Enter or select the new settings for the Position and for the Rotation of this anchor point into the dialog Edit Anchor Point .
- To add a new anchor point to the end of the selected path, click Add . The list adds the settings of the new anchor point you added to its bottom. Once you have added an anchor point, you can edit its settings in the dialog Edit Anchor Point .
- To insert a new anchor point before the selected anchor point, click Insert Before .
- To delete an anchor point, select it in the list, and click Delete .
- To delete contiguous anchor points, hold down Shift and click the first anchor point in the range and then the last anchor point.
- To delete non-contiguous anchor points, hold down Ctrl and click the anchor points you want to delete one after the other.
- To move the selected anchor point up one position in the list, click Move Up .
- To move the selected anchor point down one position in the list, click Move Down .

<!-- image -->

- To duplicate the settings of the selected anchor point and to insert the duplicated anchor point below the original, click Duplicate .

**Note**

You can edit paths of type Polycurve in the dialog Edit .

**Back to Edit an Animation Path**

#### Test an Animation Path

After defining the animation path, you can test the settings you chose on the Animation tabs in the group box Test path , and modify them, if the results do not meet your expectations. This way, you do not have to run a simulation to test your settings.

- Select the test object , i.e., a MU whose graphic 3D copies and uses as the test object.
- Enter the Velocity with which the test object moves on the path.
- Select if the test object moves in the forward direction or if it moves Backwards 3D automatically enters a negative Velocity , when you select Backwards .
- .
- Click to play the animation with the settings you selected.
- Click to pause the test animation.
- Click to stop the test animation.

<!-- image -->

<!-- image -->

Back to Work with Animation Paths

