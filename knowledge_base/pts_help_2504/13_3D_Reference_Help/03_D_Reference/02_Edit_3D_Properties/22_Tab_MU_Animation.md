#### Tab MU Animation

MU Animation [3D]

Define how the mobile objects ( MUs ) are animated on the material flow objects on the tab MU Animation .

The Frame also counts as a material flow object.

The tab looks different for objects without loading space and for objects with loading space .

- On the Sub-tab Animation Paths you can define these MU Animations :
- The MU Animation on Length-Oriented Objects
- The MU Animation on Point-Oriented Objects
- The MU Animation on Point-Oriented Objects Holding Several Parts
- The MU Animation on Animation Paths on the Workplace
- On the Sub-tab Animation Area you can define the MU Animation on Objects with Loading Space by activating the Animation Area .

<!-- image -->

<!-- image -->

You can create storage places on the objects with matrix loading space AGVPool , Container , ParallelStation , PlaceBuffer , Store , Transporter , and Worker .

The MU Animation , i.e., showing the MUs on the material flow objects during the simulation, is entirely controlled by Plant Simulation 2D. This means that you cannot play an animation for a part without this animation being triggered by an event in 2D.

You can only intervene in the animation by defining animation paths and animation points and redirecting an animation onto another one.

The simulation object, i.e., the object on which the part is located in 2D, determines which animation will be played in 3D by default. If 3D does not find the MU animation path, which is to be used, it does not animate the MU .

**Note**

If the MU is not animated at the expected position on the object, show the animation path on which the MU is animated. Then click Edit and check the values of the X-Position , the Y-Position , and the Z-Position in the dialog Path Anchor Points . You might have to edit one or several of the values.

<!-- image -->

You can redirect the MU Animation to another animation with the attribute \_3D.AnimationObject .

<!-- image -->

You can turn the animation of MUs and States off by clicking

You can set the MU Animation in 2D on the Animation ribbon tab in the Icon Editor Video on YouTube https://youtu.be/rQi5oRyZckQ?si=I4jakuo49O1VkhzN

<!-- image -->

| Work with Animation Paths              | __Accessing MUAnimations                                  |
|----------------------------------------|-----------------------------------------------------------|
| Control the MUAnimation                | __Accessing Self Animations                               |
| Load Parts Onto an AGV and Rotate Them | Add Animations and Interactions to the Simulation Objects |

| Self Animation           | Fix Animation Problems in 3D   |
|--------------------------|--------------------------------|
| Camera Animation [Frame] | MUs and States [Home ribbon]   |

[https://youtu.be/jHOZhlwGhkQ?si=xD7njD9iXcORlmHO&amp;t=540](https://youtu.be/jHOZhlwGhkQ?si=xD7njD9iXcORlmHO&t=540)

##### Animation Object

Type in the name of the alternative Animation Object of the object. Each and every 2D-object, which can receive MUs , can be an animation object.

<!-- image -->

The text box is empty by default, meaning that the object itself is the animation object and transports the MU itself.

The exception is the PickAndPlace robot . Its text box contains the animation axes which the respective PickAndPlace robot has.

For a six axis robot the animation object looks like this:

<!-- image -->

##### MU Side to Attach

Select the side on which the loaded MU will be attached to the object.

Due to the type of part the processing stations or the means of transport can pick the part up at different points.

<!-- image -->

- Bottom : Attaches the loaded MU to the object from the bottom, i.e., from the negative z-direction to this object. A typical application is a station on which a MU is carried on its center of gravity, for example most of the length-oriented objects.
- Booking Point : Attaches the loaded MU to the object from the local position ( 0 , 0 , 0 ) to this object. The local position is the position which you set on the tab Attributes in the dialog of the MU .

<!-- image -->

<!-- image -->

- Top : Attaches the loaded MU to this object from the top, i.e., from the positive z-direction. A typical application is a station on which a MU is attached on its center of gravity, for example an overhead rail system.
- Front : Attaches the loaded MU to this object from the front, i.e., from the positive x-direction.

<!-- image -->

<!-- image -->

- Back : Attaches the loaded MU to this object from the back, i.e., from the negative x-direction.

· Left : Attaches the loaded MU to this object from the left-hand side, i.e., from the negative y-direction.

<!-- image -->

<!-- image -->

- Right : Attaches the loaded MU to this object from the right-hand side, i.e., from the positive y-direction.
- Center bottom : Places the loaded MU with the middle of the base plate of its dimensions onto the animation path of the transporting object. A typical application is a station on which a MU is placed planar.

<!-- image -->

<!-- image -->

- Front bottom : Combines the two settings Front and Bottom .

· Back bottom : Combines the two settings Back and Bottom .

<!-- image -->

· Left bottom : Combines the two settings Left and Bottom .

<!-- image -->

· Right bottom : Combines the two settings Right and Bottom .

<!-- image -->

<!-- image -->

For the side on which the part is attached to the object , Plant Simulation takes the following into account:

- The Conveying Direction of the MU . This means, for example, that the setting MU side to attach &gt; Left does not in any case attach the left side of the MU from the standpoint of the MU to an animation line, but onto the back for the Conveying direction &gt; 1 (lateral right) .
- The Booking Point Height of the MU .
- The MU Length , the MU Width , and the MU Height , which you entered on the tab Attributes of the MU .

For the PickAndPlace-Robot and its animatable objects the following applies:

The MU side to attach also changes the orientation of the loaded MUs if necessary:

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

| Setting   | Description                                                                                    | Looks like this   |
|-----------|------------------------------------------------------------------------------------------------|-------------------|
| Front     | Applies a rotation of 90° around the y-axis, followed by a rotation of 180° around the z-axis. |                   |
| Right     | Applies a rotation of -90° around the x-axis.                                                  |                   |
| Left      | Applies a rotation of 90° around the x-axis.                                                   |                   |
| Back      | Applies a rotation of 90° around the y-axis.                                                   |                   |

Thereby these four settings and the setting Top should point to the respective face normals for an unrotated animation path.

The settings for Bottom apply the same orientation as Top , i.e. the orientation that is used by all other objects as well.

SimTalk

\_3D.MUSideToAttach [SimTalk]

See also

Conveying Direction [described]

MU Length [general description]

MU Width [general description]

MU Height [general description]

Booking Point Height [general description]

Fix Animation Problems in 3D

Video on YouTube

[https://youtu.be/jHOZhlwGhkQ?si=xD7njD9iXcORlmHO&amp;t=540](https://youtu.be/jHOZhlwGhkQ?si=xD7njD9iXcORlmHO&t=540)

[https://youtu.be/rQi5oRyZckQ?si=1sJ57v4ybxtnrMID&amp;t=730](https://youtu.be/rQi5oRyZckQ?si=1sJ57v4ybxtnrMID&t=730)

Sub-tab Animation Paths

Animation Paths [MU animation]

Select and type in settings for the animation path on which the parts are animated on the sub-tab Animation Paths .

<!-- image -->

You can:

###### Add

Add [button] - MU animation path

To add a new MU animation path, click this button.

<!-- image -->

- Type in a Path Name [MU animation] . This only applies to animation paths.
- Select a Path Type [MU animation] in the dialog Create Path .
- Add a new animation path.
- Extend an existing animation path.
- Edit an existing animation path.
- Delete an existing animation path.

**See also**

Work with Animation Paths

MU Animation on Point-Oriented Objects

MU Animation on Point-Oriented Objects Holding Several Parts

MU Animation on Animation Paths on the Workplace

MU Animation on Length-Oriented Objects

Add Animations and Interactions to the Simulation Objects

**Path Name [MU animation]**

Type in a meaningful name for the animation path you are creating.

<!-- image -->

If no MU animation paths are created yet for the default cases of the object, the text box Path Name shows the button. First select the path type. When you then click , Plant Simulation opens a dialog with suggestions for path names which are not yet mapped to existing MU animation paths. The list is limited to 100 entries.

<!-- image -->

The individual paths for individual MUs on the PickAndPlace-robot , the PlaceBuffer , the AGVPool , or the WorkerPool are not considered here as they do not have a fixed path name.

For the mounted parts on the AssemblyStation and for the dismantled parts on the DismantleStation you can select predefined MU animation paths. These are used if you selected the Assembly mode &gt; Delete MUs for the AssemblyStation or if the DismantleStation has more than one successor.

Depending on the selected predecessor or the successor station Plant Simulation enters the number of the predecessor/successor into the column Name on the tab MU Animation .

<!-- image -->

When you create an animation path for a length-oriented object or one of its animatable objects, Plant Simulation creates it immediately, depending on the Path Type , with two or more animation points.

<!-- image -->

**Path Type**

Path Type [MU animation]

Select one of the available path types.

<!-- image -->

- A Lines path consists of straight lines or a sequence of straight lines joined by vertices.
- A Polycurve path consists of the vertices of a curved object, i.e., a sequence of curved and straight lines, on which MUs are animated, when they are transferred onto a material flow object.

- A Spline path consists of the vertices, i.e., the anchor points of a spline curve.
- A Rotation path (Lines) consists of straight lines or a sequence of straight line joined by vertices.

These set the area , the axis , and the center of rotation of the MU.

Rotation Path [MU animation] - Lines

Rotation Path [MU animation] - Lines

To create a rotation path for the selected object, select the Path Type &gt; Rotation path (Lines) in the dialog Create Animation Path .

A rotation path consists of straight lines or of a sequence of straight line which are connected through vertices. These set the area , the axis , and the center of rotation of the MU .

<!-- image -->

Plant Simulation opens the dialog Create Rotation Path . Set how Plant Simulation rotates the parts which the selected object processes on the path that you create.

- Select the Start Angle , the End Angle , and the Radius of the rotation.
- Select the Axis X/Y/Z around which the MU rotates.
- Select the Center of the rotation around which the MU rotates.
- Click OK to apply your settings or click Cancel to not apply them.

<!-- image -->

To edit the rotation path, select it in the list of animation paths and click Edit . Edit the values of the path anchor points in the dialogs, which are opened.

<!-- image -->

If a MU animation path consists of more than one point and if you did not type in a Time or a Velocity respectively, the MU animation takes as long as the Processing Time .

Failures , pauses , etc. interrupt MU animations consisting of more than one point, on point-oriented objects.

See also

Create an Animation Path that Rotates Objects

- \_3D.MUAnimations.createAnimationCurve [SimTalk]
- \_3D.MUAnimations.createAnimationLine [SimTalk]
- \_3D.MUAnimations.createAnimationPoint [SimTalk]
- \_3D.MUAnimations.createAnimationSpline [SimTalk]

**Start Angle [MU animation]**

**Start Angle [MU animation]**

Type in the angle in degrees where the rotation starts.

The Start Angle has to differ from the End Angle , otherwise 3D does not rotate the MU .

To rotate the MU counter-clockwise, the start angle has to be greater than the end angle. You can also type in a value greater than +360 degrees and less than -360 degrees.

<!-- image -->

**See also**

**End Angle [MU animation]**

**End Angle [MU animation]**

Type in the End Angle in degrees where the rotation ends.

The End Angle has to differ from the Start Angle , otherwise 3D does not rotate the MU .

To rotate the MU clockwise, the end angle has to be greater than the start angle. You can also type in a value greater than +360 degrees and less than -360 degrees.

<!-- image -->

**See also**

Start Angle [MU animation]

**Radius [MU animation]**

**Radius [MU animation]**

Type in the Radius of the rotation path.

<!-- image -->

**Axis X/Y/Z [MU animation]**

Select the Axis around which you would like to rotate the MU .

- Click X to rotate the MU around the X-direction.
- Click Y to rotate the MU around the Y-direction.
- Click Z to rotate the MU around the Z-direction. We pre-set the Z-axis so that an end angle greater than the start angle rotates the MU clockwise.

<!-- image -->

**Center [MU rotation]**

**Center [MU rotation]**

To set the Center of the rotation , i.e., the point around which 3D rotates the MU .

- Type in a value for the X-position of the center of rotation into the text box X .
- Type in a value for the Y-position of the center of rotation into the text box Y .
- Type in a value for the Z-position of the center of rotation into the text box Z .

<!-- image -->

###### Extend [MU animation]

To add a new anchor point to the animation path, thus making it longer, click this button.

<!-- image -->

Then click the left mouse button at the position, where you would like to insert the anchor point. Repeat this as often as needed.

To terminate Extend animation path mode, click the right mouse button.

You can only navigate in Extend animation path mode with the middle and the right mouse button if you hold down the Ctrl+Alt keys.

###### Edit

**Edit [MU animation]**

To edit the anchor points of the path you selected, click this button.

<!-- image -->

<!-- image -->

In the dialog Path Anchor Points you can:

- Add a new anchor point.

**Edit [MU animation]**

- Insert a new anchor point before the selected anchor point.
- Delete the selected anchor point.
- Move the selected anchor point up one position in the list or move it down one position in the list.
- Duplicate the selected anchor point.
- Edit the Values of the selected anchor point or double-click the row of the anchor point, whose values you want to change, in the list.
- Add a Common Offset to the selected anchor point.
- Hide or Show the selected path by clicking the cell under animation paths .

<!-- image -->

**SimTalk**

- \_3D.MUAnimations.&lt;AnimationPathName&gt;.PathAnchorPoint [SimTalk]
- \_3D.MUAnimations.getTable [SimTalk]
- \_3D.MUAnimations.setTable [SimTalk]

**See also**

Fix Animation Problems in 3D

**Add [button] - anchor point, MU animation**

To add a new anchor point to the path, click this button.

<!-- image -->

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

**Edit Values**

Edit Values [button] - anchor point, MU animation

To edit the values of the anchor point which you selected in the list, click this button.

<!-- image -->

Instead, you can also double-click the row of the anchor point, whose values you want to change, in the list.

- The dialog of a path of type Rotation path (Lines) provides these settings:

<!-- image -->

- The dialog of a path of type Lines provides these settings:
- The dialog of a path of type Spline provides these settings:
- The dialog of a path of type Polycurve provides these settings:

<!-- image -->

<!-- image -->

<!-- image -->

Here we do not provide the value ΔL.

You can edit these settings for the different path types:

- Position for Lines , Polycurves , Splines , Rotation path (Lines)
- Rotation for Lines and Polycurves , Rotation path (Lines)
- Segments for Polycurves
- Velocity for Lines and Splines , Rotation path (Lines)

SimTalk

- \_3D.MUAnimations.&lt;AnimationPathName&gt;.PathAnchorPoint [SimTalk]
- \_3D.MUAnimations.&lt;AnimationPathName&gt;.getTable [SimTalk]
- \_3D.MUAnimations.&lt;AnimationPathName&gt;.setTable [SimTalk]

**Position [MU animation]**

To move the Position of the selected anchor point on the x-axis, the y-axis and the z-axis, type a value into the text box, or roll the mouse wheel.

The settings for the three axes are independent of each other.

<!-- image -->

**Rotation [MU animation]**

**Rotation [MU animation]**

To set the axis around which to rotate the anchor point, type in a value for each of the three components (x-y-z) that define the rotation axis.

<!-- image -->

Type the Angle of rotation in degrees into the text box.

**Segments [MU animation]**

A path of type Polycurve provides these settings for its segments .

<!-- image -->

**See also**

Segments [curve] - 2D, described

Segments [tab Appearance] - 3D

Insert Curved and Straight Segments

**Velocity [MU animation]**

**Velocity [MU animation]**

To activate Velocity settings, select this check box.

<!-- image -->

The text box Length shows the length of the anchor point.

Type in the Time , which is required for point-oriented movements, such as rotating around or remaining on the selected anchor point.

Type in the Velocity with which the MU rotates around the selected anchor point.

**Add Common Offset [MU animation]**

To add a Common offset to the selected anchor point of a path of type Lines or Spline , click this button.

<!-- image -->

<!-- image -->

- Type a value for the Position into the text box, or roll the mouse wheel to add a common offset to the position of the selected anchor point on the x-axis, the y-axis, and the z-axis. The settings for the three axes are independent of each other.
- Type the Angle of Rotation for the common offset into the text box.

**Delete [button] - MU animation path**

###### Delete [button] - MU animation path

To delete the selected animation path, click this button.

<!-- image -->

##### Sub-tab Animation Area

###### Animation Area [described]

Select and type in settings for the animation area on which the parts are animated on the sub-tab Animation Area .

<!-- image -->

The animation area defines the size of the area on the object on which 3D places the MUs . By default, 3D uses the bounding box of the selected 3D object.

**Note**

Only the objects with matrix loading space ( AGVPool , Container , ParallelStation , PlaceBuffer , Store , Transporter , and Worker ) provide the settings for the Animation Area . As a rule you can use our presets, unless they do not meet your needs.

**You can:**

- Activate the animation area by selecting the check box Animation Area .
- Select to Show MUs as cuboids instead of their standard graphic.
- Select the Orientation of the animation area.
- Select if the values for the Length and Width of the animation area are relative or absolute .
- Type in the Length of the animation area.

<!-- image -->

- Type in the Width of the animation area.
- Type in the settings for the Center .
- Type in the settings for the MU rotation .
- Show or hide your settings.

SimTalk

**\_3D.MUAnimationAreaEnabled [SimTalk]**

See also

MU Animation on Objects with Loading Space

Define the Animation Area of a Simulation Object

Animate Bricks on the Animation Area of the Brick Carrier

Animate Brick Carriers on the Animation Area of the Truck

Model a Worker Who Carries Several Parts in 3D

SimTalk Access to 3D &gt; \_\_Accessing MU Animations &gt; \_\_Accessing the Animation Area

###### Animation Area [check box]

Animation Area [check box]

To activate the settings of the Animation Area select this check box.

<!-- image -->

<!-- image -->

This is the default setting for the ParallelStation , Sorter , Store , Transporter , Container , PlaceBuffer , and Worker .

To not use the animation area, clear the check box.

Inheritance

The inheritance check box turns inheritance of the Animation Area Settings off or on.

- A green check box means that inheritance is turned on. Then the object inherits, i.e., uses, settings of the parent object from which it was derived. When you change the settings of the parent object, Plant Simulation also changes the respective settings of the child object.
- An orange check box with a minus means that inheritance is turned off. The value you specify only applies to the setting of this object.

SimTalk

\_3D.MUAnimationAreaEnabled [SimTalk]

###### Show MUs as Cuboids [check box]

To animate the MUs , which are animated on the animation area of the object, as cuboids, select this check box.

<!-- image -->

To animate the MUs with the graphic of the MU , clear the check box.

Animating the cuboids is considerably faster than animating the graphics of the MUs .

<!-- image -->

**SimTalk**

**\_3D.MUAnimationAreaShowMUsAsCuboids [SimTalk]**

Video on YouTube

[https://youtu.be/t7hBJgNZpHE?si=BH6z7mXFqFrlesH\_&amp;t=1847](https://youtu.be/t7hBJgNZpHE?si=BH6z7mXFqFrlesH_&t=1847)

###### Orientation [animation area]

Select the Orientation of the animation area on which 3D places the MUs .

<!-- image -->

| Setting   | Description                                                                                    | Looks like this   |
|-----------|------------------------------------------------------------------------------------------------|-------------------|
| XY plane  | Places the MUon the XY plane, i.e., flat on the machine                                        |                   |
| XZ plane  | Places the MUon the XZ plane, i.e., perpendicular to the front or the back of the machine      |                   |
| YZ plane  | Places the MUon the XZ plane, i.e., perpendicular to the right or the left side of the machine |                   |

**SimTalk**

**\_3D.MUAnimationAreaOrientation [SimTalk]**

<!-- image -->

<!-- image -->

<!-- image -->

###### Relative/Absolute

To define the values for the animation area settings as absolute values, use the default setting Absolute .

Then only the right text boxes are active, while the text boxes for the relative entries are unavailable.

To define the values for the animation area settings as relative values, select the radio button Relative . Then only the left text boxes are active, while the text boxes for the absolute entries are unavailable.

**Note**

Relative/Absolute is not a setting of the object but only serves as an input help.

Then, enter the values.

<!-- image -->

**SimTalk**

- \_3D.MUAnimationAreaAbsoluteCenter [SimTalk]
- \_3D.MUAnimationAreaRelativeCenter [SimTalk]
- \_3D.MUAnimationAreaAbsoluteSize [SimTalk]
- \_3D.MUAnimationAreaRelativeSize [SimTalk]

###### Length [text box] - animation area

Type in the Length of the animation area on which Plant Simulation places the parts.

Depending on what you selected under Relative/Absolute , you can type in the Length as a relative or as an absolute value. Plant Simulation automatically converts the value to the respective other value.

- The right value designates the absolute length of the animation area in meters.
- The left value designates the relative length of the animation area. You can type in a value between 0 and any size [0..1..]. This value is used for assignments in SimTalk .

<!-- image -->

<!-- image -->

**SimTalk**

- \_3D.MUAnimationAreaAbsoluteSize [SimTalk]
- \_3D.MUAnimationAreaRelativeSize [SimTalk]

Width [text box] - animation area

Type in the Width of the animation area on which 3D places the parts.

Depending on what you selected under Relative/Absolute , you can type in the Width as a relative or as an absolute value. Plant Simulation automatically converts the value to the respective other value.

- The right value designates the absolute width of the animation area in meters.
- The left value designates the relative width of the animation area as a value between 0 and 1. This value is used for assignments in SimTalk .

<!-- image -->

<!-- image -->

**SimTalk**

- \_3D.MUAnimationAreaAbsoluteSize [SimTalk]
- \_3D.MUAnimationAreaRelativeSize [SimTalk]

**Center [animation area]**

###### Center [animation area]

Type in the values for the X position, the Y position, and the Z position of the Center point of the animation area onto which 3D places the parts ( MUs ).

The settings for the center point allow you to move the storage places that are spaced evenly across the animation area to adapt it to the 3D graphic. For the ParallelStation the Z position of -0.5 m for example prevent the MUs from hanging in thin air instead of being placed flat onto the processing area.

Depending on what you selected under Relative/Absolute , you can type in the positions for the Center as a relative or as an absolute value. Plant Simulation automatically converts the value to the respective other value.

- The right value designates the absolute X/Y/Z-position of the center of the animation area in meters.
- The left value designates the relative X/Y/Z-position of the center of the animation area. You can type in any negative or a positive value [..0..1..]. This value is used for assignments in SimTalk .

<!-- image -->

<!-- image -->

To move the center point of the animation area

- up , type in a positive value into the text box Z .
- to the back , type in a positive value into the text box Y .
- to the right , type in a positive value into the text box X .
- down , type in a negative value into the text box Z .
- to the front , type in a negative value into the text box Y .
- to the left , type in a negative value into the text box X .
- into several directions at the same time, type in the values into the respective text boxes.

To check if the number you type in has the desired effect, click Show .

SimTalk

\_3D.MUAnimationAreaAbsoluteCenter [SimTalk]

\_3D.MUAnimationAreaRelativeCenter [SimTalk]

###### MU Rotation

Type in the Angle of the MU rotation in degrees which you would like to add to the rotation axis.

Type in a value for each of the three components (X-Y-Z) which define the rotation axis. This way you define the rotation axis around which the parts on the animation area are rotated.

<!-- image -->

Instead, you can also click the button to the right of the axis, to set this component of the rotation axis. Plant Simulation then enters the respective values into the text boxes.

<!-- image -->

**SimTalk**

\_3D.MUAnimationAreaMURotation [SimTalk]

###### Show/Hide [animation area]

To show the animation area, click Show . To hide it again, click Hide .

<!-- image -->

##### Animation Offset

For the length-oriented objects you can type in an Animation Offset .

<!-- image -->

At times, you might not want the parts to be placed flush onto the surface of the length-oriented object but with an offset to this surface. To do so:

- Click the inheritance check box so that it looks like this .
- Type the offset of the animation path to the surface of the object along the X direction into the text box. You can also roll the mouse wheel to set a positive or a negative offset.
- Type in the offset of the animation path to the surface of the object along the Y direction.
- Type in the offset of the animation path to the surface of the object along the Z direction.

Compare this example:

<!-- image -->

**SimTalk**

**\_3D.AnimationOffset [SimTalk]**

Video on YouTube

[https://youtu.be/rQi5oRyZckQ?si=DNlaqEKpBYxJsuSN&amp;t=770](https://youtu.be/rQi5oRyZckQ?si=DNlaqEKpBYxJsuSN&t=770)

##### Gravity Mode

To activate Gravity Mode for length-oriented objects, select this check box.

<!-- image -->

<!-- image -->

To deactivate it, clear the check box.

Remarks

Gravity Mode only affects automatic animations, that is animations for which you did not specify an animation path.

<!-- image -->

**Note**

This setting only applies to the length-oriented objects. It is especially helpful for suspension tracks, etc.

On a suspension track the part is always placed perpendicular to the floor in Gravity Mode , either hanging from a rail on the ceiling or standing up on a rail on the floor.

SimTalk

\_3D.AniGravityMode [SimTalk]

Video on YouTube

[https://youtu.be/rQi5oRyZckQ?si=-tt6LBpdLvdhfgwg&amp;t=668](https://youtu.be/rQi5oRyZckQ?si=-tt6LBpdLvdhfgwg&t=668)

**Smooth Rotation**

##### Smooth Rotation

To activate Smooth Rotation for length-oriented objects, select this check box.

<!-- image -->

To deactivate it, clear the check box.

Remarks

This setting only applies to the length-oriented objects . It is especially helpful for suspension tracks, etc.

Smooth Rotation only affects automatic animations, that is animations for which you did not specify an animation path.

If the object currently animates its MUs using a user-defined Animation Path Type &gt; Lines , Smooth Rotation specifies whether the part slowly changes its rotation around the anchor points (like this is the case on a Station for example) or if it abruptly changes its orientation (like at a corner on a Conveyor with the standard MU animation).

**SimTalk**

<!-- image -->

##### Test path

Test Path [MU animation]

The group box Test Path provides settings and actions for testing the MU animation path which exists in the scene.

When you start testing, 3D creates a temporary test object which moves on the selected animation path.

<!-- image -->

**You can:**

- Select the Object , which represents the test object.
- Type in the Factor with which the test object moves on the animation path.
- Select if the test object moves in the forward direction or if it moves Backward .
- Play the animation with the settings you selected.

- Pause the animation.
- Stop the animation.

**Note**

Plant Simulation does not save these settings to the model file.

**Object [test MU animation]**

###### Object [test MU animation]

Select the graphic of any of the MU classes which Plant Simulation uses as the test object, which moves on the selected animation path.

<!-- image -->

<!-- image -->

###### Factor [test MU animation]

Type in a number for the Playback Factor which 3D uses for the animation of the object on the test path.

When you select Backwards , 3D automatically enters a negative Velocity , and the MU moves toward the starting point of the animation path.

**Backwards [test MU animation]**

###### Backwards [test MU animation]

Select Backwards if you want the MU to move backward toward the starting point of the animation path, instead of forward toward the end point of the animation path.

Plant Simulation automatically enters a negative Factor into the text box when you select the check box.

###### Play/Pause/Stop [test MU animation]

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

