#### Tab Camera Animation

Show Manipulators

You can edit the dimensions of the object by clicking Show Manipulators on the Edit ribbon tab or press M on the keyboard. The box settings reflect this change.

<!-- image -->

SimTalk

createBox [SimTalk]

ObstacleForWorker [SimTalk]

See also

Box

Model Your Own 3D Graphic

\_Detailed Access To Graphics

##### Tab Camera Animation

Camera Animation [Frame]

Define how the camera moves through the 3D scene in the Frame on the tab Camera Animation .

Camera flights through the scene are only possible on dedicated camera paths. The camera animation modifies the view point of the 3D window.

Note

Only the Frame provides the tab Camera Animation .

<!-- image -->

You can:

- Learn How 3D Animates the Camera in the Frame .
- Add , extend , edit , and delete animation paths .
- Click Add &gt; &gt; Rotation path (lines) to add a rotation path to the point-oriented and to the lengthoriented objects.
- Select settings for testing the animation path.

You can also Attach a Camera to an Object , for example to a part or to a Worker . The camera then follows part or Worker on their way through the installation on the pre-defined animation paths of the material flow objects. Here you do not have to create your own animation paths.

**See also**

<!-- image -->

| How 3D Animates the Camera in the Frame          | Self Animation                                                             |
|--------------------------------------------------|----------------------------------------------------------------------------|
| Work with Animation Paths                        | __Accessing Camera Animations                                              |
| Fly on a Defined Path Through the Scene          | __Accessing MUAnimations                                                   |
| Attach a Camera to an Object/Frame and Detach it | __Accessing Self Animations                                                |
| MUAnimation [3D]                                 | View Ribbon Tab [3D only] > Attach Camera Detach Camera Add to Camera Path |

|                                    | Animate Camera   |
|------------------------------------|------------------|
| Play camera path , video recording |                  |

##### How 3D Animates the Camera in the Frame

The Camera Animation in a Frame defines a fly-through through the current Frame on a defined path.

You can customize all aspects of the Camera Animation by selecting settings on the tab or by programming Methods .

The animation controls only apply to the designated Frame in the active window, they do not affect parent or child Frames .

Resetting the simulation also resets all Camera Animations .

You can play, pause, and reset the Camera Animations in animation blocks.

You can schedule saved animations as well as temporary animations. A temporary animation can only represent a rotation around the rotation axis of the object.

An animation block implicitly consists of a single animation.

**Note**

If you need a circular camera flight around an object, use the predefined Rotation path (Lines) which resembles the Ballhaus Kreisel .

Let us illustrate the Camera Animation with a simple example.

Our model looks like this:

<!-- image -->

To create the model:

- Press the spacebar to open the dialog Edit 3D Properties and change to the tab Camera Animation .
- Click Add and add a Camera Animation Path . Click Show to display the path in the 3D window.

<!-- image -->

Initially the camera animation path consists of a single anchor point in the origin of the scene.

<!-- image -->

- Change to the tab View in the program window and click Add .

<!-- image -->

Rotate the scene and click Add Current View to add the current view of the scene to the camera path.

<!-- image -->

Repeat this until we have created the entire path. In our example we circle our station. The finished path looks like this:

<!-- image -->

- Then, edit the properties of the path. After some experiments we decided upon these heights (positions in the Z-direction):

<!-- image -->

- We also want the camera to always look at our Station . To do so, click Define View Direction and select the settings below.
- Instead of setting the view direction for each path anchor point individually, you can also do this for all path anchor points together when you are done defining the path.

To do so, select all anchor points and then click Define View Direction .

<!-- image -->

The path tool then points to our Station in the 3D window.

<!-- image -->

- Click Animate to view our tracking shot.

<!-- image -->

Start the tracking shot proper by clicking Play in the dialog Fly on Path .

We see that the camera rounds the Station on our path and the lens of the camera, i.e., our eyes, always look at our Station .

- If necessary you can also change additional properties of the path:
- You can move the entire path in the X, Y, and Z-direction by clicking above the left column. This selects all path anchor points in the dialog.

<!-- image -->

Then click Add Common Offset and type in the offset to the existing path.

<!-- image -->

- You can also change the settings of individual path anchor points, by setting a higher velocity for the movement from the first anchor point on. This speed applies until you reset the speed for a succeeding anchor point to 1 meter per second or to another value.

The camera moves with a preset speed of 1 meter per second. The speed of the camera movement does not depend on the simulation speed of the EventController .

<!-- image -->

**See also**

Rotation path [camera animation] - Lines

Work with Animation Paths

\_\_Accessing Camera Animations

Fly on a Defined Path Through the Scene

##### Animation paths

Animation Paths [camera animation]

A camera animation path is the path on which the camera moves through the 3D scene,

You can:

- Add a new animation path.
- Extend an existing animation path.
- Edit an existing animation path.

Add

Add [button] - camera animation path

To add a new animation path, click this button.

<!-- image -->

- Type in a Path Name [camera animation] . This only applies to animation paths.
- Select a Path Type [camera animation] in the dialog Create Path .
- Delete an existing animation path.

**See also**

**Work with Animation Paths**

Add Animations and Interactions to the Simulation Objects

**Path Name [camera animation]**

Path Name [camera animation]

Type in a meaningful name for the animation path you are creating.

<!-- image -->

Path Type [camera animation]

Path Type [camera animation]

Select one of the available path types.

<!-- image -->

- A Lines path consists of straight lines or a sequence of straight lines joined by vertices.
- A Polycurve path consists of the vertices of a curved object, i.e., a sequence of curved and straight lines, on which MUs are animated, when they are transferred onto a material flow object.
- A Spline path consists of the vertices, i.e., the anchor points of a spline curve.
- A Rotation path (Lines) consists of straight lines or a sequence of straight line joined by vertices.

These set the area , the axis , and the center of rotation of the MU.

Rotation Path [camera animation] - Lines

Rotation path [camera animation] - Lines

To create a rotation path for the selected object, select the Path type &gt; Rotation path (Lines) in the dialog Create Animation Path .

A rotation path consists of straight lines or of a sequence of straight line which are connected through vertices. These set the area , the axis , and the center of rotation of the camera.

<!-- image -->

Plant Simulation opens the dialog Create Rotation Path .

We use the default settings shown below for a circular camera flight around the selected object. This resembles the 360-degree-shot that is known as the " Ballhaus-Kreisel ", named after cinematographer Michael Ballhaus. You can use the settings as a starting point for your own rotation path.

- If you open a window for the Frame and select an object in this window, the settings create a raised camera flight around the selected object.

<!-- image -->

<!-- image -->

If you create a flight around the Z Axis with the default settings, the camera looks toward the center of the selection on the created path.

- If you open a window for the Frame and do not select anything in this window, the settings create a raised camera flight around the entire scene in this window.

<!-- image -->

If you create a flight around the Z Axis with the default settings, the camera looks toward the center of the floor on the created path.

- If you did not open a window for the Frame , the parameters create a raised camera flight around the entire scene as it would look if you opened a window for this Frame .

If you create a flight around the Z Axis with the default settings, the camera looks toward the center of the floor on the created path.

To define your own settings for rotating the parts which the selected object animates on the path that you create:

- Select the Start Angle , the End Angle , and the Radius of the rotation.
- Select the Axis X/Y/Z around which the camera rotates.
- Select the Center of the rotation around which the camera rotates.
- Click OK to apply your settings or click Cancel to not apply them.

To edit the rotation path, select it in the list of animation paths and click Edit . Edit the values of the path anchor points in the dialogs, which are opened.

<!-- image -->

**See also**

How 3D Animates the Camera in the Frame

Create an Animation Path that Rotates Objects

- \_3D.CameraAnimations.createAnimationCurve [SimTalk]
- \_3D.CameraAnimations.createAnimationLine [SimTalk]
- \_3D.CameraAnimations.createAnimationSpline [SimTalk]

**Start Angle [camera animation]**

**Start Angle [camera animation]**

Type in the angle in degrees where the rotation starts.

The Start Angle has to differ from the End Angle , otherwise 3D does not rotate the camera.

To rotate the camera counter-clockwise, the start angle has to be greater than the end angle. You can also type in a value greater than +360 degrees and less than -360 degrees.

<!-- image -->

If a camera animation path consists of more than one point and if you did not type in a time or a speed, this camera animation takes exactly as long as the processing time.

Failures, pauses, etc. interrupt camera animations which consist of more than one point on point-oriented objects.

**See also**

End Angle [camera animation]

**End Angle [camera animation]**

Type in the angle in degrees where the rotation ends.

The End Angle has to differ from the Start Angle , otherwise 3D does not rotate the camera.

To rotate the camera clockwise, the end angle has to be greater than the start angle. You can also type in a value greater than +360 degrees and less than -360 degrees.

<!-- image -->

**See also**

Start Angle [MU animation]

**Radius [camera animation]**

**Radius [camera animation]**

Type in the Radius of the rotation path.

<!-- image -->

**Axis XYZ [camera animation]**

Select the Axis around which you would like to rotate the camera.

- Click X to rotate the camera around the X-direction.
- Click Y to rotate the camera around the Y-direction.
- Click Z to rotate the camera around the Z-direction. We pre-set the Z-axis so that an end angle greater than the start angle rotates the camera clockwise.

<!-- image -->

**Center [camera animation]**

**Center [camera animation]**

To set the Center of the rotation , i.e., the point around which 3D rotates the camera in the three dimensions, type in the respective values.

- Type in a value for the X-position of the center of rotation into the text box X .
- Type in a value for the Y-position of the center of rotation into the text box Y .
- Type in a value for the Z-position of the center of rotation into the text box Z .

<!-- image -->

###### Extend [camera animation]

To add a new anchor point to the animation path, thus making it longer, click this button.

<!-- image -->

Then click the left mouse button at the position, where you would like to insert the anchor point. Repeat this as often as needed.

To terminate Extend animation path mode, click the right mouse button.

You can only navigate in Extend animation path mode with the middle and the right mouse button if you hold down the Ctrl+Alt keys.

###### Edit

**Edit [camera animation]**

To Edit the anchor points of the path you selected in the dialog Path Anchor Points , click this button.

<!-- image -->

Depending on the selected path the dialog with the values looks different:

- For a Line path the dialog looks like this:

<!-- image -->

- For a Polycurve path the dialog looks like this:
- For a Spline path the dialog looks like this:

<!-- image -->

<!-- image -->

- For a Rotation path the dialog looks like this:

<!-- image -->

**You can:**

- Add a new anchor point.
- Insert a new anchor point before the selected anchor point.
- Delete the selected anchor point.
- Move the selected anchor point up one position in the list or move it down one position in the list.
- Duplicate the selected anchor point.
- Edit the Values of the selected anchor point or double-click the row of the anchor point, whose values you want to change, in the list.
- Add a common offset to the selected anchor point.
- Hide or show the selected path by clicking the cell under animation paths .
- Define View Direction in which the lens of the camera looks.

<!-- image -->

<!-- image -->

- Click Show in View to record the settings, which you manually adjusted, of the current view, and to then write these values into the dialog Path Anchor Points .

**Add [button] - anchor point, camera animation**

Add [button] - anchor point, camera animation

To add a new anchor point to the path, click this button.

<!-- image -->

.

The list window shows these settings. You can then edit the individual values.

<!-- image -->

**Insert Before**

<!-- image -->

To insert a new anchor point before the anchor point, which you selected in the list window, click this button. The list window shows these settings. You can then edit the individual values.

**Delete**

<!-- image -->

To delete the selected anchor point from the list, click this button.

<!-- image -->

<!-- image -->

<!-- image -->

**Edit Values**

<!-- image -->

**Move Up**

To move the selected anchor point one position up in the list, click this button.

Move Down

To move the selected anchor point one position down the list, click this button.

Duplicate

To duplicate the settings of the selected anchor point and to insert the duplicate below the original in the list, click this button.

Edit Values - anchor point, camera animation

To edit the values of the anchor point which you selected in the list, click this button.

Instead, you can also double-click the row of the anchor point, whose values you want to change, in the list.

Depending on the selected path the dialog with the values looks different:

- The dialog of a path of type Lines provides these settings:

<!-- image -->

- The dialog of a path of type Polycurve provides these settings:
- The dialog of a path of type Spline provides these settings:
- The dialog of a path of type Polycurve provides these settings:

<!-- image -->

<!-- image -->

<!-- image -->

You can edit these settings for the different path types:

- Position for Lines , Polycurves , Splines , Rotation path (Lines)
- Rotation for Lines and Polycurves , Rotation path (Lines)
- Segments for Polycurves
- Velocity for Lines and Splines , Rotation path (Lines)

**Position [camera animation]**

**Position [camera animation]**

To move the Position of the selected anchor point on the x-axis, the y-axis and the z-axis, type a value into the text box, or roll the mouse wheel.

The settings for the three axes are independent of each other.

<!-- image -->

**Rotation [camera animation]**

To set the Rotation axis around which to rotate the anchor point, type in a value for each of the three components (x-y-z) that define the rotation axis.

Select an offset from the center of the anchor point around the x-axis, the y-axis, and the z-axis. Normally you do not type in another value but keep the pre-defined settings.

<!-- image -->

**Angle**

Type in the Angle of rotation in degrees into the text box.

**Velocity [camera animation]**

**Velocity [camera animation]**

To activate Velocity settings, select this check box.

<!-- image -->

The Velocity applies until you reset it to a following anchor point to 1 meter per second or to another value.

The camera moves with the preset Velocity of 1 meter per second. The Velocity of the camera movement does not depend on the simulation speed of the EventController .

Length

The text box Length shows the length of the anchor point.

Time

Type in the Time , which is required for point-oriented movements, such as rotating around or remaining on the selected anchor point.

Velocity

Type in the Velocity , which is required for point-oriented movements, such as rotating around or remaining on the selected anchor point.

**Segments [camera animation]**

To set the settings of the segments of a Polycurve path , type the values into the respective cells in the table.

<!-- image -->

**Add Common Offset [camera animation]**

To add a Common offset to the selected anchor point of a path of type Lines or Spline , click this button.

<!-- image -->

<!-- image -->

- Type a value for the Position into the text box, or roll the mouse wheel to add a common offset to the position of the selected anchor point on the x-axis, the y-axis, and the z-axis. The settings for the three axes are independent of each other.
- Type the Angle of Rotation for the common offset into the text box.

**Define View Direction**

To define the viewing direction of the anchor point which you selected in the list, click this button.

<!-- image -->

<!-- image -->

Plant Simulation saves the selected setting in the model, but does not show it in the dialog when you open it the next time.

You can select the direction type, i.e., where the x-axis of the animated object points to for the selected anchor point.

- Look along the path on the selected object.
- Look towards an object . Then, select an object in the active scene from the list destination object .
- Look towards a position . Then, select the Target Position on the X-Axis , the Y-Axis , or the Z-Axis .

<!-- image -->

**Backwards**

You can also select if the viewing direction points Backward by selecting .

**See also**

**Look at Object**

<!-- image -->

- Look in a direction . Then, type in the Direction on the X-Axis , the Y-Axis , or the Z-Axis .

<!-- image -->

**Show in View [camera animation]**

To show the selected camera settings in the active 3D window, click this button.

<!-- image -->

<!-- image -->

**Delete [camera animation]**

###### Delete [camera animation]

To delete the selected animation path, click this button.

<!-- image -->

##### Test Path

###### Test Path [camera animation]

The group box Test Path provides settings and actions for testing any animation path which exists in the scene.

When you start testing, 3D creates a temporary object camera which moves on the selected animation path.

<!-- image -->

- Type in the Factor with which the test object moves on the animation path.
- Select if the test object moves in the forward direction or if it moves Backwards .
- Play the animation with the settings you selected.
- Pause the animation.
- Stop the animation.

**Note**

Plant Simulation does not save these settings to the model file.

###### Factor [test camera animation]

<!-- image -->

Type in a number for the Playback Factor which 3D uses for the animation of the object on the test path.

When you select Backwards , 3D automatically enters a negative Velocity , and the MU moves toward the starting point of the animation path.

**Backwards [test camera animation]**

###### Backwards [test camera animation]

Moves the selected graphic backward toward the starting point of the animation path, instead of forward toward the end point of the animation path.

Plant Simulation automatically enters a negative Factor into the text box when you select the check box.

###### Play/Pause/Stop [test camera animation]

You can check if your animation path does what you want it to do by selecting the settings and by clicking the buttons.

<!-- image -->

Factor

Type in a number for the playback factor which 3D uses for the animation test.

When you select Backwards , 3D automatically enters a negative velocity , and the MU moves toward the starting point of the animation path.

Play

<!-- image -->

To start the animation, click this button.

3D creates a test object of the selected graphic and animates it on the path you selected with the speed you entered. The test object pauses at the end of the animation path.

Any time you entered for the animation path itself will be scaled with the Factor you entered.

Pause

<!-- image -->

To pause animation of the test object, independent of the simulation, click this button.

Stop

<!-- image -->

To stop the animation of the test object, independent of the simulation, click this button. This also deletes the test object.

