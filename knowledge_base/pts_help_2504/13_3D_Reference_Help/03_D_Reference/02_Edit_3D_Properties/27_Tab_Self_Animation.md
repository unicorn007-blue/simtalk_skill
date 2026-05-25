#### Tab Self Animation

##### Self Animation

Define how the object itself is animated in the scene on the tab Self Animation .

<!-- image -->

**You can:**

- Learn How 3D Animates the Objects Themselves .
- Add , Extend , Edit , and Delete Animation Paths .
- Add a Rotation path of type lines to the point-oriented and to the length-oriented objects.
- Select settings for Testing the animation path.
- Set the Rotation Axis for simulation objects.
- Set the Rotation Center for simulation objects.

**Self Animation**

**See also**

| Work with Animation Paths   | Joint                         |
|-----------------------------|-------------------------------|
| MUAnimation [3D]            | __Accessing Self Animations   |
| Camera Animation [Frame]    | __Accessing MUAnimations      |
| Poses                       | __Accessing Camera Animations |

**Video on YouTube**

[https://youtu.be/YleFq6afRs4?si=GU2h4C5HV0ZY2xyJ&amp;t=42](https://youtu.be/YleFq6afRs4?si=GU2h4C5HV0ZY2xyJ&t=42)

##### How 3D Animates the Objects Themselves

The Self Animation of an object controls how this object itself will be animated in the simulation model. You can customize all aspects of the self animation by selecting settings on the tab or by programming Methods .

All animation controls only apply to a single object, they do not affect parent objects or child objects.

Resetting the simulation also resets all self animations .

You can play , pause , and reset the self animations in animation blocks.

You can schedule saved animations as well as temporary animations. A temporary animation can only represent a rotation around the rotation axis of the object.

An animation block can contain any number of animations, which 3D executes simultaneously, and whose effects are based on each other.

Let us illustrate the self animation of a Station with a simple example.

Our model looks like this:

<!-- image -->

- Press the spacebar to open the dialog Edit 3D Properties of the Station and change to the tab Self Animation .

Click Add and add an animation path. Click Show to display the path in the 3D window.

Click Extend and then on the positions in the Frame at which we need anchor points of the path, one after the other. Plant Simulation shows the path as a yellow line.

<!-- image -->

- Run the simulation: We see how parts are produced, processed, and removed from the production process. The Station itself is not moved though. This we have to program in a Method .
- Insert a Method into the model and type in this source code:
- Run the simulation again and execute the Method at any point in time. Now we see that the Station moves along the path we defined.

Station._3D.selfAnimations.MoveStation.play()

**See also**

\_3D.SelfAnimations.&lt;AnimationPathName&gt;.play [SimTalk]

Work with Animation Paths

\_\_Accessing Self Animations

Animation Paths

Animation Paths [self animation]

Select and enter settings for the animation path on which the object itself is animated on the tab Self Animation .

You can:

- Add a new self animation path.

Add

Add [button] - self animation path

To add a new animation path, click this button.

<!-- image -->

- Type in a Path Name [self animation] .
- Select a Path Type [self animation] in the dialog Create Path .

Video on YouTube

[https://youtu.be/YleFq6afRs4?si=QsQRL-NA5J-OMGpK&amp;t=145](https://youtu.be/YleFq6afRs4?si=QsQRL-NA5J-OMGpK&t=145)

- Extend an existing self animation path.
- Edit an existing self animation path.
- Delete an existing self animation path.

**See also**

**Work with Animation Paths**

Add Animations and Interactions to the Simulation Objects

**Path Name [self animation]**

Path Name [self animation]

Type in a meaningful name for the animation path you are creating.

<!-- image -->

Path Type

Path Type [self animation]

Select one of the available path types.

<!-- image -->

- A Lines path consists of straight lines or a sequence of straight lines joined by vertices.
- A Polycurve path consists of the vertices of a curved object, i.e., a sequence of curved and straight lines, on which MUs are animated, when they are transferred onto a material flow object.
- A Spline path consists of the vertices, i.e., the anchor points of a spline curve.
- A Rotation path (Lines) consists of straight lines or a sequence of straight line joined by vertices.

These set the area , the axis , and the center of rotation of the MU.

Rotation Path [self animation] - Lines

Rotation Path [self animation] - Lines

To create a rotation path for the selected object, select the Path Type &gt; Rotation path (Lines) in the dialog Create Animation Path .

A rotation path consists of straight lines or of a sequence of straight line which are connected through vertices. These set the area , the axis , and the center of rotation of the object itself.

<!-- image -->

3D opens the dialog Create Rotation Path . Set how 3D rotates the object on the path that you create.

- Select the Start Angle , the End Angle , and the Radius of the rotation.
- Select the Axis X/Y/Z around which the object rotates.
- Select the Center of the rotation around which the object rotates.
- Click OK to apply your settings or click Cancel to not apply them.

<!-- image -->

To edit the rotation path, select it in the list of animation paths and click Edit . Edit the values of the path anchor points in the dialogs, which are opened.

<!-- image -->

If an animation path consists of more than one point and if you did not type in a Time or a Velocity respectively, the animation takes as long as the Processing Time .

**See also**

Create an Animation Path that Rotates Objects

- \_3D.SelfAnimations.createAnimationCurve [SimTalk]
- \_3D.SelfAnimations.createAnimationLine [SimTalk]
- \_3D.SelfAnimations.createAnimationSpline [SimTalk]

**Start Angle [self animation]**

Type in the angle in degrees where the rotation starts.

The Start Angle has to differ from the End Angle , otherwise 3D does not rotate the object.

To rotate the object counter-clockwise, the start angle has to be greater than the end angle. You can also type in a value greater than +360 degrees and less than -360 degrees.

<!-- image -->

**See also**

**End Angle [self animation]**

**End Angle [self animation]**

**End Angle [self animation]**

Type in the angle in degrees where the rotation ends.

The End Angle has to differ from the Start Angle , otherwise 3D does not rotate the object.

To rotate the object clockwise, the end angle has to be greater than the start angle. You can also type in a value greater than +360 degrees and less than -360 degrees.

<!-- image -->

**See also**

**Start Angle [self animation]**

**Radius [self animation]**

Type in the Radius of the rotation path.

<!-- image -->

**Axis XYZ [self animation]**

Select the axis around which you would like to rotate the object.

- Click X to rotate the object around the X-direction.
- Click Y to rotate the object around the Y-direction.
- Click Z to rotate the object around the Z-direction. We pre-set the Z axis so that an end angle greater than the start angle rotates the object clockwise.

<!-- image -->

**Center [self animation]**

To set the center of the rotation, i.e., the point around which Plant Simulation rotates the object, specify the settings for the different dimensions.

- Type in a value for the X-position of the center of rotation into the text box X .
- Type in a value for the Y-position of the center of rotation into the text box Y .
- Type in a value for the Z-position of the center of rotation into the text box Z .

<!-- image -->

**Extend [self animation]**

##### Extend [self animation]

To add a new anchor point to the animation path, thus making it longer, click this button.

<!-- image -->

Then click the left mouse button at the position, where you would like to insert the anchor point. Repeat this as often as needed.

To terminate Extend animation path mode, click the right mouse button.

You can only navigate in Extend animation path mode with the middle and the right mouse button if you hold down the Ctrl+Alt keys.

##### Edit

###### Edit [self animation]

To edit the anchor points of the path you selected, click this button.

<!-- image -->

**You can:**

- Add a new anchor point before the selected anchor point.
- Delete the selected anchor point.
- Move the selected anchor point up one position in the list or move it down one position in the list.
- Duplicate the selected anchor point.
- Edit the Values of the selected anchor point or double-click the row of the anchor point, whose values you want to change, in the list.
- Add a Common Offset to the selected anchor point.
- Hide or show the selected path by clicking the respective cell under animation paths .

<!-- image -->

###### Add [button] - anchor point, self animation

To add a new anchor point to the path, click this button.

<!-- image -->

.

The list window shows the added settings of the anchor point. You can then edit the individual values.

<!-- image -->

**Insert Before**

<!-- image -->

To insert a new anchor point before the anchor point, which you selected in the list window, click this button. The list window shows the added settings of the anchor point. You can then edit the individual values.

**Delete**

<!-- image -->

To delete the selected anchor point from the list, click this button.

**Move Up**

<!-- image -->

To move the selected anchor point one position up in the list, click this button.

**Move Down**

<!-- image -->

To move the selected anchor point one position down the list, click this button.

**Duplicate**

<!-- image -->

To duplicate the settings of the selected anchor point and to insert the duplicate below the original in the list, click this button.

###### Edit Values

Edit Values [button] - anchor point, self animation

To edit the values of the anchor point which you selected in the list, click this button.

<!-- image -->

Instead, you can also double-click the row of the anchor point, whose values you want to change, in the list.

- The dialog of a path of type Lines and Rotation path (Lines) provides these settings:

<!-- image -->

- The dialog of a path of type Polycurve provides these settings:
- The dialog of a path of type Spline provides these settings:

<!-- image -->

<!-- image -->

You can edit these settings for the different path types:

- Position [self animation] for Lines , Polycurves , Splines , Rotation path (Lines)
- Rotation [self animation] for Lines and Polycurves , Rotation path (Lines)
- Segments [self animation] for Polycurves
- Velocity [self animation] for Lines and Splines , Rotation path (Lines)

**Position [self animation]**

**Position [self animation]**

Type in a value into the text box, or roll the mouse wheel to move the position of the selected anchor point on the x-axis, the y-axis and the z-axis.

The settings for the three axes are independent of each other.

<!-- image -->

**Rotation [self animation]**

To set the axis around which to rotate the anchor point, type in a value for each of the three components (x-y-z) that define the rotation axis.

<!-- image -->

Type the Angle of rotation in degrees into the text box.

**Segments [self animation]**

**Segments [self animation]**

A path of type Polycurve provides these settings for its Segments .

<!-- image -->

**See also**

Segments [tab Appearance] - 3D

Insert Curved and Straight Segments

**Velocity [self animation]**

To activate Velocity settings, select this check box.

<!-- image -->

The Velocity applies until you reset it to a following anchor point to 1 meter per second or to another value.

The object moves with the preset Velocity of 1 meter per second. The Velocity of the object movement does not depend on the simulation speed of the EventController .

Length

The text box length shows the Length of the anchor point.

Time

Type in the Time , which is required for point-oriented movements, such as rotating around or remaining on the selected anchor point.

**Add Common Offset [self animation]**

###### Add Common Offset [self animation]

To add a Common offset to the selected anchor point of a path of type Lines or Spline , click this button.

<!-- image -->

<!-- image -->

- Type a value for the Position into the text box, or roll the mouse wheel to add a common offset to the position of the selected anchor point on the x-axis, the y-axis, and the z-axis.
- The settings for the three axes are independent of each other.
- Type the Angle of Rotation in degrees into the text box.

##### Delete [self animation] - path

To delete the selected animation path, click this button.

**Rotation Axis**

##### Rotation Axis

To set the axis around which the selected object will be rotated type in the values of the respective axis.

- Type a value for the x-component of the axis into the text box X .
- Type a value for the y-component of the axis into the text box Y .
- Type a value for the z-component of the axis into the text box Z .

<!-- image -->

Instead, you can also click this button to the right of the respective axis to set the translation direction. Plant Simulation then enters the respective values into the text boxes.

SimTalk

\_3D.AniRotationAxis [SimTalk]

See also

\_3D.SelfAnimations.scheduleRotation [SimTalk]

\_3D.SelfAnimations.playRotation [SimTalk]

##### Rotation Center

To set the center of the rotation around which the object will be rotated, specify the settings for the different dimensions.

- Type a value for the x-position of the center of the rotation into the text box X .
- Type a value for the y-position of the center of the rotation into the text box Y .
- Type a value for the z-position of the center of the rotation into the text box Z .

<!-- image -->

**SimTalk**

\_3D.AniRotationCenter [SimTalk]

See also

\_3D.SelfAnimations.scheduleRotation [SimTalk]

\_3D.SelfAnimations.playRotation [SimTalk]

Test path

Test Path [self animation]

The group box Test Path provides settings and actions for testing the animation path of the selected object.

When you start testing, 3D creates a temporary test object which moves on the selected animation path.

<!-- image -->

**You can:**

- Type in the Factor with which the test object moves on the animation path.
- Select if the test object moves in the forward direction or if it moves Backwards .
- Play the animation with the settings you selected.

###### Test Path [self animation]

- Pause the animation.
- Stop the animation.

**Note**

Plant Simulation does not save these settings to the model file.

<!-- image -->

###### Factor [test self animation]

Type in a number for the Playback Factor which 3D uses for the animation of the object on the test path.

When you select Backwards , 3D automatically enters a negative Velocity , and the MU moves toward the starting point of the animation path.

**Backwards [test self animation]**

###### Backwards [test self animation]

To move the selected graphic backward toward the starting point of the animation path, instead of forward toward the end point of the animation path, select this check box.

Plant Simulation automatically enters a negative Factor into the text box when you select the check box.

###### Play/Pause/Stop [test self animation]

You can check if your animation path does what you want it to do by clicking the respective buttons.

<!-- image -->

To start the animation, click this button. 3D creates a test object of the selected graphic and animates it on the path you selected with the speed you entered. The test object pauses at the end of the animation path.

Any time you entered for the animation path itself will be scaled with the Factor you entered.

Pause

<!-- image -->

To pause animation of the test object, independent of the simulation, click this button.

Stop

<!-- image -->

To stop the animation of the test object, independent of the simulation, click this button. This also deletes the test object.

