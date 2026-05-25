#### Tab Poses

Poses

Create poses for animatable objects on the tab Poses .

**Note**

Connectors , Interfaces , and Markers do not provide poses.

In general a pose designates a combination of position and orientation of an object. In our context a pose designates a number of translation or rotation positions for animatable objects which belong to a simulation object. This also takes the degrees of freedom into account which you set in the joint definitions of these animatable objects.

A pose run designates all movements that were started by any version of the methods \_3D.Poses.moveTo and \_3D.Poses.moveToCoordinate , both for the object itself and for any of its animatable objects.

Joints and poses work together. On the Tab Joint you can define a joint for the selected object and on the tab Poses you can then configure several poses for this joint. The joint of an animatable object is defined by the two settings Rotation or Translation :

<!-- image -->

You can use poses to animate the object itself. As opposed to self animations, you only have to set the position to which the animation is to move when using the animation with poses. As Plant Simulation knows the previous position, it then internally creates self animations which ensure a smooth transition from the previous to the new state.

<!-- image -->

**Note**

Whenever you change Limits , Velocity , Acceleration , or the Joint Type of the animatable object, the initial position for the next pose run that affects this object returns to 0.

A pose run designates all movements that were started by any version of the methods \_3D.Poses.moveTo and \_3D.Poses.moveToCoordinate , both for the object itself and for any of its animatable objects.

<!-- image -->

As soon as you created a pose, you can show and hide it again with the toggle button . Plant Simulation only shows a single pose at a time. If you show a different pose, Plant Simulation first hides the pose that is already shown.

Plant Simulation colors the respective animatable objects and moves the object to the state that corresponds to the pose. While the pose is shown and the dialog is open, you can change the state of the pose stepwise by pressing the left or right arrow key:

Press one of the arrow keys to

- rotate the pose by 1 ° of the range from the joint settings if both limits are defined.
- move the pose by 0.1 m if at least one limit is missing when a Prismatic Joint is selected, or
- rotate the pose by 1 ° if at least one limit is missing when Revolute Joint is selected.

The left arrow key moves the pose toward the Lower Limit , the right arrow key moves the pose toward the Upper Limit , independent of rotation axis or translation direction.

In the example below we showed Pose1 . It moves the Prismatic Joint of the Toolholder up when you press the right arrow key.

Plant Simulation shows selected poses in violet .

<!-- image -->

**You can:**

- Add a pose by clicking Add .
- Edit a pose by clicking Edit .
- Delete a pose by clicking Delete .
- Select if you want to Synchronize Joints or not.
- Select if you want to make a pose Movement Interruptible or not.

You can also Move Poses and Joints with Mouse and Keyboard Keys

**Note**

The PickAndPlace Robot does not provide poses, neither do instances of Connectors , Toolbars , and Folders .

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

SimTalk

**\_\_Accessing Poses**

See also

Model Joints and Poses

<!-- image -->

**Create a Passageway and a Gate**

Move Poses and Joints with Mouse and Keyboard Keys

**Joint**

Self Animation

Configuring the Robot in 3D

Video on YouTube

[https://youtu.be/rQi5oRyZckQ?si=pGkDwvoDw3LOD4Wo&amp;t=1130](https://youtu.be/rQi5oRyZckQ?si=pGkDwvoDw3LOD4Wo&t=1130)

[https://youtu.be/Rj5eYZu8pl4?si=j8ngdeR3Ykgp2JjR&amp;t=625](https://youtu.be/Rj5eYZu8pl4?si=j8ngdeR3Ykgp2JjR&t=625)

##### Add Pose

To Add a new pose to the joint of the animatable object, click this button.

<!-- image -->

**Then proceed as follows:**

- In case you do not have a matching animatable object for your new pose, create an animatable object for the selected object and create a joint for it.

Open the object in a new 3D window. Click the part of the object with the right mouse button and select Make Animatable Object on the context menu.

<!-- image -->

Click OK to open the dialog Edit 3D Properties . Change to the Tab Joint . Define the settings for the joint. Click OK .

<!-- image -->

- Press the spacebar in the window of the object to open the dialog Edit 3D Properties of the object.
- Change to the tab Poses and click Add . Type in a name for the pose and click OK .

<!-- image -->

**Add Pose**

- Click Apply in the dialog Edit 3D Properties . This adds the pose to the list of poses and activates the buttons Edit and Delete .

See also

**\_\_Accessing Poses**

**Joint**

Model Joints and Poses

Video on YouTube

[https://youtu.be/wfVN-mcWNsc?si=aRKnzalxpShWWRBL&amp;t=100](https://youtu.be/wfVN-mcWNsc?si=aRKnzalxpShWWRBL&t=100)

##### Edit Pose

To edit an existing pose , click the pose in the column Name and click this button.

<!-- image -->

Plant Simulation then deselects the object to which the pose belongs.

<!-- image -->

In the dialog Edit Pose you can change the settings of the pose that are highlighted in white.

The grayed-out settings are for your information only, you cannot edit them here. These are the settings you defined on the Tab Joint . Each row in the table contains the definition of a pose.

<!-- image -->

The dialog shows these values:

- A check box to set if you want to use or not use this axis for the animation. The icon to the right shows if the joint is a Prismatic Joint or a Revolute Joint .
- The Path Name which you typed in for the animatable object.

**Edit Pose**

- The Range within which the joint, depending of its type, can move. The range is defined by the Lower Limit and the Upper Limit .

The Range defines the degree of freedom within which the pose of the joint can move.

- For a Revolute Joint you typed in the range between the lower limit and the upper limit on the tab Joint in degrees.
- For a Prismatic Joint you typed in the range between the lower limit and the upper limit on the tab Joint in meters.
- Position/Rotation : Depending on the Type of joint, Prismatic Joint or Revolute Joint , the following values apply to the position or the rotation of the joint.
- Select to use the value which you type into the text box below Value to which the arrow points.
- Select Lower Limit to use the value which you typed in for the lower limit on the tab Joint .
- Select Upper Limit to use the value which you typed in for the upper limit on the tab Joint .
- If you selected , type in the Value , that will be used for the animation.
- If you selected Lower Limit or Upper Limit , the cell shows the value which you typed in on the tab Joint .

Plant Simulation immediately shows changes to the displayed pose in the dialog.

Click OK to apply the values and to close the dialog.

See also

**\_\_Accessing Poses**

Joint

Model Joints and Poses

Move Poses and Joints with Mouse and Keyboard Keys

Video on YouTube

[https://youtu.be/Rj5eYZu8pl4?si=j8ngdeR3Ykgp2JjR&amp;t=625](https://youtu.be/Rj5eYZu8pl4?si=j8ngdeR3Ykgp2JjR&t=625)

##### Delete Pose

To delete an existing pose , click the pose in the column name and click this button.

<!-- image -->

##### Synchronized Joints

To synchronize the joints so that all joints, that are part of the movement, reach the target state at the same time while moving toward a pose, select this check box.

To not synchronize the movement of the joints, clear the check box.

SimTalk

\_3D.SynchronizedJoints [SimTalk]

See also

\_\_Accessing Poses

##### Movement Interruptible

To make failures and pauses interrupt pose runs , select this check box.

To not interrupt the movement of the joints, clear the check box.

If you start a pose run while a failure or pause is active at the moment, the pose run will start regardless of the setting Movement Interruptible . A pose run designates all movements that were started by any version of the methods \_3D.Poses.moveTo and \_3D.Poses.moveToCoordinate , both for the object itself and for any of its animatable objects.

Movement Interruptible applies to the objects FluidSource , FluidDrain , Tank , Mixer , Transporter , Frame , Exporter , and Worker . It also applies to all objects which can transport MUs or Workers , except for the Workplace .

SimTalk

\_3D.MovementInterruptible [SimTalk]

\_3D.Poses.EndPoseWasReached [SimTalk]

See also

- \_\_Accessing Poses

##### Move Poses and Joints with Mouse and Keyboard Keys

You can move poses and joints with the mouse and keyboard keys.

**Note**

By default, the PickAndPlace Robot does not provide poses. In the example below we exchanged the graphic of a Station with the graphic of a PickAndPlace Robot .

To move and rotate a robot in 3D with the mouse:

- If a pose for a simulation object, which can carry parts, is shown on the tab Poses . The pose has to match one of the robot types as described in Configuring the Robot in 3D , except for a robot without joints and for the four axis robot with ball joint gripper .
- If a MU Animation Path or a active MU Animation Area exists for the animatable object that is relevant in the context of this pose.

Here the relevant animatable object is the tip of the pose or an animatable object attached at the tip of the pose. Type it in as the Animation Object on the tab MU Animation of the simulation object.

<!-- image -->

Plant Simulation then shows a tool with which you can move and rotate the pose. Plant Simulation adjusts the pose so that the tip of the pose corresponds to the position and the orientation of the mounted tool.

In doing so, Plant Simulation sets the position [1,1] of the pose to the tool, if an Animation Area is active for the relevant animatable object.

If the object does not have an Animation Area , Plant Simulation sets the tool to the start of the first animation path it found.

<!-- image -->

You can click the tool with the mouse . The tool then changes its color to green, and you can move the robot by dragging the mouse and moving it in different directions Instead you can also press the arrow keys on the keyboard.

To move the pose and thus the entire robot arm , press the Left , Right , Up , or Down arrow keys on the keyboard.

<!-- image -->

To move the pose of the selected joint , which is shown violet, up or down, press Page Up or Page Down on the keyboard.

<!-- image -->

<!-- image -->

You can move an animatable object with Page Up and with Page Down .

- Select an animatable object , which shows a pose state while editing a pose, and press Page Up to move the joint according to its degree of freedom toward its lower limit. The left arrow does the same.
- For an animatable object , the offset is described under Move and Rotate Poses in the 3D Quick Reference . If you hold down Shift , it is ten times the value, i.e., the grid distance itself, etc. If you hold down Ctrl , it is a tenth of the value, i.e., 1 % etc.
- For a non-animatable object the offset is 10 % of the grid line distance that is used for snapping. By default this is 10 % of 1 m, i.e., 10 cm.

<!-- image -->

<!-- image -->

- Select an animatable object , which shows a pose state while editing a pose, and press Page Down to move the joint according to its degree of freedom toward its upper limit. The right arrow does the same.
- For an animatable object , the offset is described under Move and Rotate Poses on the 3D Quick Reference Card . If you hold down Shift , it is ten times the value, i.e., the grid distance itself, etc. If you hold down Ctrl , it is a tenth of the value, i.e., 1 % etc.
- For a non-animatable object the offset is 10 % of the grid line distance that is used for snapping. By default this is 10 % of 1 m, i.e., 10 cm.

