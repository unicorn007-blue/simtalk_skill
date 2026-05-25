#### Tab Joint

Joint Define settings for rotating and translating the animation joints of the animation objects on the tab Joint .

- You can select General Settings for the Animation .
- You can select Joint Settings for the Animation .
- You can specify a Value for the Preview Translation/rotation .

With these functions you can create appealing animations, for example to insert parts into a machine and to remove them once they are processed.

Joints and poses work together. On the tab Joint you can define a single joint for the selected objects and on the Tab Poses you can define several poses for this joint.

The joint of an animatable object can be a revolute joint or a prismatic joint .

- For the rotation of a revolute joint you can set the Rotation Axis , the Rotation Center and optionally the maximum Lower Limit and the maximum Upper Limit of the rotation angle. If you do specify a limit, you can confine the range of the rotation.
- For the translation of a prismatic joint you can, in addition, set the Translation Direction and the minimum Lower Limit /position and maximum Upper Limit /position along the direction vector through the stationary position of the object.
- For the rotation of a revolute joint and for the translation of a prismatic joint you can specify the Velocity and Acceleration or Deceleration of the movement.

<!-- image -->

**Note**

Whenever you change Limits , Velocity , Acceleration , or the Joint Type of the animatable object, the initial position for the next pose run that affects this object returns to 0.

A pose run designates all movements that were started by any version of the methods \_3D.Poses.moveTo and \_3D.Poses.moveToCoordinate , both for the object itself and for any of its animatable objects.

You can Move Poses and Joints with Mouse and Keyboard Keys .

To move the pose of the selected joint , which is shown violet, up or down , you can press Page Up or the Page Down on the keyboard.

<!-- image -->

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

SimTalk

moveTo [SimTalk]

moveToCoordinate [SimTalk]

See also

Model Joints and Poses

Create a Passageway and a Gate

Move Poses and Joints with Mouse and Keyboard Keys

\_\_Accessing Joints

Poses

Self Animation

Make Animatable Object

Configuring the Robot in 3D

Video on YouTube

[https://youtu.be/rQi5oRyZckQ?si=nMR11EjzeM\_xxh1N&amp;t=850](https://youtu.be/rQi5oRyZckQ?si=nMR11EjzeM_xxh1N&t=850)

**[https://youtu.be/h2cFAH46ESQ?si=ZgXj23RzNDMNVdLf&amp;t=270](https://youtu.be/h2cFAH46ESQ?si=ZgXj23RzNDMNVdLf&t=270)**

###### General Settings for the Animation

##### General Settings for the Animation

Select and type in general settings for the animation.

The general settings for the animation apply as follows:

- When you open the dialog for an animatable object, the settings apply to the animation of the joint of the animatable object.
- When you do not open the dialog for an animatable object, the settings apply to the self animations of the object, which work without an animation path.

For the joint of the object itself you can:

- Set the Rotation Axis for revolute joints .
- Set the Rotation Center for revolute joints .
- Set the Translation Direction for prismatic joints of the animation object.

<!-- image -->

**Inheritance**

The inheritance check box turns inheritance of the Joint settings off or on.

- A green check box means that inheritance is turned on. Then the object inherits, i.e., uses, settings of the parent object from which it was derived. When you change the settings of the parent object, Plant Simulation also changes the respective settings of the child object.
- An orange check box with a minus means that inheritance is turned off. The value you specify only applies to the setting of this object.

###### Rotation Axis [revolute joint]

To set the axis around which the Joint Type &gt; Revolute joint of the selected object will be rotated, specify the settings for the individual components.

<!-- image -->

- Type in a value for the x-component of the axis into the text box X .
- Type in a value for the y-component of the axis into the text box Y .
- Type in a value for the z-component of the axis into the text box Z .

<!-- image -->

Instead, you can also click this button to the right of the respective axis to set the translation direction. Plant Simulation then enters the respective values into the text boxes.

SimTalk

\_3D.AniRotationAxis [SimTalk]

See also

\_3D.SelfAnimations.scheduleRotation [SimTalk]

Type of Joint

**Rotation Center [revolute joint]**

###### Rotation Center [revolute joint]

To set the center of the rotation i.e., the point around which the Joint Type &gt; Revolute joint of the selected object will be rotated:

<!-- image -->

- Type in a value for the x-position of the center of the rotation into the text box X .
- Type in a value for the y-position of the center of the rotation into the text box Y .
- Type in a value for the z-position of the center of the rotation into the text box Z .

**SimTalk**

\_3D.AniRotationCenter [SimTalk]

See also

\_3D.SelfAnimations.scheduleRotation [SimTalk]

Rotation Center

###### Translation Direction

To set the direction of the translation, i.e, the point from which on the Joint Type &gt; Prismatic joint of the selected object is moved specify the settings of the individual axes.

<!-- image -->

- Type in a value for the position of the center of the x-axis into the text box X .
- Type in a value for the position of the center of the y-axis into the text box Y .
- Type in a value for the position of the center of the z-axis into the text box Z .

<!-- image -->

Instead, you can also click this button to the right of the respective axis to set the translation direction. Plant Simulation then enters the respective values into the text boxes.

**Inheritance**

The inheritance check box turns inheritance of the Joint Settings off or on.

##### Joint Settings for the Animation

- A green check box means that inheritance is turned on. Then the object inherits, i.e., uses, settings of the parent object from which it was derived. When you change the settings of the parent object, Plant Simulation also changes the respective settings of the child object.
- An orange check box with a minus means that inheritance is turned off. The value you specify only applies to the setting of this object.

SimTalk

JointLowerLimit [SimTalk]

See also

Make Animatable Object

Model Joints and Poses

Joint Settings for the Animation

Joint Settings for the Animation

For the animation object of the object you can select or enter the settings shown on the tab.

To show the settings, click the animation object in the dialog Show Graphic Structure with the right mouse button and select Edit 3D Properties .

<!-- image -->

**You can:**

- Set the Translation Direction .
- Select the Type of Joint .
- Activate the Lower Limit for rotating or for moving the joint and then enter the value.
- Activate the Upper Limit for rotating or for moving the joint and then enter the value.
- Type in the Velocity for rotating or for moving the joint of the object.
- Type in the Acceleration for rotating or for moving the joint of the object.
- Type in the Deceleration for rotating or for moving the joint of the object.
- Type in the Value for the Translation/rotation Preview for rotating or for moving the joint of the object.

**Note**

Whenever you change the Lower Limit / upper Limit , the Velocity , the Acceleration , or the Joint Type of an animatable object, the initial position for the next pose run that affects this object returns to 0.

Once all pose runs of an object reached their destination, Plant Simulation enters an EndOfTime event into the Event List .

**Inheritance**

The inheritance check box turns inheritance of the Joint settings off or on.

- A green check box means that inheritance is turned on. Then the object inherits, i.e., uses, settings of the parent object from which it was derived. When you change the settings of the parent object, Plant Simulation also changes the respective settings of the child object.
- An orange check box with a minus means that inheritance is turned off. The value you specify only applies to the setting of this object.

###### Type of Joint

Select the Type of the joint, Prismatic or Revolute .

- Prismatic Joint : The joint moves linearly along the selected Translation Direction .
- Revolute Joint : The joint rotates around the selected Rotation Axis .

<!-- image -->

<!-- image -->

For a Revolute Joint you can select Use Shortest Rotation Direction .

<!-- image -->

If the joint uses the spatially shortest direction, you cannot specify joint limits.

**SimTalk**

JointType [SimTalk]

\_3D.JointUseShortestRotationDirection [SimTalk]

###### Use Shortest Rotation Direction

To make the rotational joint of the object use the spatially shortest direction toward its target orientations, select this check box.

<!-- image -->

**Remarks**

If the joint uses the spatially shortest direction, you cannot specify joint limits.

**SimTalk**

**JointType [SimTalk]**

\_3D.JointUseShortestRotationDirection [SimTalk]

**Lower Limit**

###### Lower Limit

To activate the Lower Limit for rotating or translating the joint, select this check box.

<!-- image -->

Clear the check box to not use a Lower Limit .

**Remarks**

Plant Simulation exclusively uses limits while defining poses . It does not use them to influence any other behavior, such as \_3D.Poses.moveToCoordinate [SimTalk] , \_3D.Poses.moveToMU [SimTalk] , etc.

**SimTalk**

**JointLowerLimitActive [SimTalk]**

**Lower Limit**

Type in the value for the lower limit for rotating or translating the joint:

- For a Prismatic Joint the value designates the degree of freedom in meters.
- For a Revolute Joint the value designates the degree of freedom in degrees.

<!-- image -->

<!-- image -->

**SimTalk**

**JointLowerLimit [SimTalk]**

\_3D.JointUseShortestRotationDirection [SimTalk]

**Upper Limit**

###### Upper Limit

To activate the Upper Limit for rotating or translating the joint, select this check box.

<!-- image -->

Clear the check box to not use an Upper Limit .

**Remarks**

Plant Simulation exclusively uses limits while defining poses . It does not use them to influence any other behavior, such as \_3D.Poses.moveToCoordinate [SimTalk] , \_3D.Poses.moveToMU [SimTalk] , etc.

**SimTalk**

**JointUpperLimitActive [SimTalk]**

Upper Limit

Type in the value for the upper limit for rotating or translating the joint:

- For a Revolute Joint the value designates the degree of freedom in degrees.
- For a Prismatic Joint the value designates the degree of freedom in meters.

<!-- image -->

**Upper Limit**

<!-- image -->

**SimTalk**

**JointUpperLimit [SimTalk]**

\_3D.JointUseShortestRotationDirection [SimTalk]

###### Velocity [joint]

Type in the value for the Velocity with which the joint rotates or moves.

- For a Revolute Joint the value designates the degree of freedom in degrees per second.
- For a Prismatic Joint the value designates the degree of freedom in meters per second.

<!-- image -->

<!-- image -->

An animatable object with the Velocity of 0 does not rotate with the Turntable when the Turntable rotates. This applies when the insertion position of the animatable object is located on the animation rotation axis of the Turntable . This is the case if the insertion point is exactly located on the animation rotation center or is reachable from there along the animation rotation axis without a sideways deviation.

<!-- image -->

This resembles a real Turntable with a fixed base and a rotary table.

SimTalk

JointVelocity [SimTalk]

See also

Move Parts On with the Turntable

###### Acceleration [text box] - joint

Type in the value for the Acceleration with which the joint of the object increases the speed of the Rotation or the Translation .

You can only type in positive values. The value 0 means that acceleration for this joint is deactivated and that a pose run reaches the defined speed immediately.

A pose run, which you start with the method \_3D.Poses.moveTo by entering an alternative time or time sequence, does neither use acceleration nor deceleration, but reaches the defined speed immediately.

- For a Revolute Joint the value designates the acceleration in degree per second squared.
- For a Prismatic Joint the value designates the acceleration in meter per second squared.

<!-- image -->

**Acceleration [text box] - joint**

<!-- image -->

**SimTalk**

**JointAcceleration [SimTalk]**

###### Deceleration [text box] - joint

Type in the value for the Deceleration with which the joint of the object decreases the speed of the Rotation or the Translation .

You can only type in positive values. The value 0 means that deceleration for this joint is deactivated and that a pose run reaches the defined speed immediately.

A pose run, which you start with the method \_3D.Poses.moveTo by entering an alternative time or time sequence, does neither use acceleration nor deceleration, but reaches the defined speed immediately.

- For a Revolute Joint the value designates the deceleration in degree per second squared.
- For a Prismatic Joint the value designates the deceleration in meter per second squared.

<!-- image -->

<!-- image -->

**SimTalk**

**JointDeceleration [SimTalk]**

Preview Translation or Rotation

Preview Translation/rotation

Type in a value for previewing the translation or rotation of the joint.

<!-- image -->

For a Prismatic Joint , you can type in a Value for previewing the translation.

For a Revolute Joint , you can type a Value for previewing the rotation.

**Value [translation/rotation]**

###### Value [translation/rotation]

Type in a value for the joint which corresponds to a position in the pose or the threshold which you typed in under Joint Settings for the Animation .

- For a Revolute Joint this is a value in °.
- For a Prismatic Joint this is a value in the unit which you selected for the length in the model settings.

<!-- image -->

<!-- image -->

By default, this text box is empty, meaning that the preview is deactivated. If you type in a value, Plant Simulation shows a pose in which the joint has this value. If you delete the value from this text box, the preview will be deactivated again.

If a pose is approached or held, when the simulation object to which the respective animatable object belongs, the preview on the tab Graphics is not active.

If a pose is shown via the dialog Edit 3D Properties of the simulation object, all previews for all animatable objects/joints, which are contained in the pose, are not active.

While joint properties are previewed, you can click a joint that is selected in a 3D window and move or rotate it with the left arrow key or the right arrow key.

Press one of the arrow keys to

- rotate the pose by 1 ° of the range from the joint settings when you specified both limits and selected a Revolute Joint .
- rotate the pose by 1 ° if at least one limit is missing and you selected a Revolute Joint .
- move the pose by 0.1 m if at least one limit is missing and you selected a Prismatic Joint .

The left arrow key moves the pose toward the lower limit, the right arrow key moves it toward the upper limit independent of the rotational axis or the translation direction. The value, which you type in, is not saved. It only serves as visual support for entering the limits in the joint settings.

See also

Configure the Poses

JointCurrentValue [SimTalk]

###### Joint Settings for the Animation

