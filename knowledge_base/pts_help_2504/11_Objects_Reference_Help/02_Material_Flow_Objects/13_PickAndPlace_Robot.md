### PickAndPlace Robot

Use the PickAndPlace robot for picking up a part at one station, rotating it, and placing it onto another station.

Icon

<!-- image -->

**Description**

The PickAndPlace robot can pick up and deliver one or more parts. To deliver several parts, type in the Capacity . The PickAndPlace robot transports the part on to its successors within the flow of materials like this:

- The part arrives at the exit of the predecessor. It notifies the PickAndPlace robot that it wants to be picked up.
- The PickAndPlace robot then determines if it picks the part up or not.
- Without a Pull Control , the robot will be notified that a part wants to be picked up, and it accepts it.
- If you entered a Pull Control , the robot executes it, and when the part is selected, it will be picked up.

#### PickAndPlace Robot

- The PickAndPlace robot rotates to the respective predecessor and picks the part up.
- For determining the target station, the robot either uses its default Exit Strategies or the Target Control . Within this Method you set the target station.

The Target Control is called, when the robot picks up a part or when it places a part. Within the method setDestination the boolean parameter controls if the robot waits at the target station or not.

- Then, the PickAndPlace robot rotates to the target station and places the part.
- It then rotates back to the standard position.

The PickAndPlace robot can emulate most of the functions of the TransferStation .

To show a tooltip with information about the PickAndPlace robot , hover with the mouse over it.

<!-- image -->

Show Manipulators

To change the length of the graphic and the anchor points of the object, click Show Manipulators on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

With the manipulators of the bounding box of the PickAndPlace-Robot you can edit its appearance of the object.

<!-- image -->

<!-- image -->

With the rotation manipulator you can set the rotation of the object with the mouse and with keyboard keys:

**Note**

You cannot select a rotation manipulator together with anything else in a 3D window at the same time.

As soon as you select a rotation manipulator, Plant Simulation deselects the other selection.

As soon as you select anything else, Plant Simulation deselects the rotation manipulator.

This also applies when you hold down Ctrl or Shift when selecting.

- Drag the manipulator with the mouse to the right to rotate the object around the z-axis clockwise. Drag the manipulator to the left to rotate the object counter-clockwise.
- Click the rotation manipulator and press the left arrow key or the right arrow key to rotate the object by 1° at a time.

Hold down Shift and press the left arrow key or the right arrow key to rotate the object by 45° at a time.

Add the Object to the Simulation Model

To add the PickAndPlace robot to your simulation model, click Manage Class Library &gt; Basic Objects &gt; MaterialFlow &gt; PickAndPlace on the Home ribbon tab.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

See also

Capacity [text box] - PickAndPlace Pick and Place Parts with the PickAndPlace Robot Configuring the Robot with Drag-and-Drop Configuring the Robot in 3D Video on YouTube https://youtu.be/K-NEPvShU10?si=UI\_gAeEPqPykZWCM

<!-- image -->

#### Configuring the Robot with Drag-and-Drop

Use drag-and-drop to quickly and easily configure the operations that the PickAndPlace robot can execute.

To do so, drag the PickAndPlace robot over the Conveyor , the Track , or the TwoLaneTrack and select the operation that is to take place:

**Note**

You can only configure the PickAndPlace robot with drag-and- drop for length-oriented objects for which you can define sensors.

The title bar of the dialog shows the path of the PickAndPlace robot that is to move the part and of the length-oriented object.

A complete configuration requires two drag-and-drop operations, one for picking or unloading and one for placing or loading.

<!-- image -->

- Pick part : The PickAndPlace robot picks parts from a length-oriented object at a sensor.
- Plant Simulation creates a front-triggered sensor with light barrier mode at the desired position on the length-oriented object with a sensor control for moving the part to the PickAndPlace robot .
- Unload part : The PickAndPlace robot unloads parts from a Container or a Transporter at a sensor on a length-oriented object.
- Plant Simulation creates a front-triggered sensor with light barrier mode at the desired position on the length-oriented object with a sensor control for unloading the part to the PickAndPlace robot .
- Place part : The PickAndPlace robot places parts onto a length-oriented object at a sensor. Plant Simulation creates a rear-triggered sensor with light barrier mode at the desired position on
- the length-oriented object without a sensor control . It also sets the settings Target Selection , Target Object , and Target Sensor ID of the exit behavior of the PickAndPlace robot .
- Load part : The PickAndPlace robot loads parts onto a Container or a Transporter located at a sensor of a length-oriented object.

Plant Simulation creates a sensor, which is triggered by the booking point, at the desired/clicked position on the length-oriented object without a sensor control . It also sets the settings Target Selection , Target Object , and Target Sensor ID of the exit behavior of the PickAndPlace robot .

Plant Simulation stops the Container or Transporter automatically at the sensor position and starts it again automatically when it is full. If you do not want to use the default behavior, you have to create a sensor control in which you have to make sure to start and stop the Container or Transporter .

For all of the cases described above Plant Simulation creates an entry each in the Angles Table and in the Times Table of the PickAndPlace robot .

See also

Pick and Place Parts with the PickAndPlace Robot

Configuring the Robot in 3D

Video on YouTube

[https://youtu.be/K-NEPvShU10?si=jhaYSU7\_maKTcYBb&amp;t=437](https://youtu.be/K-NEPvShU10?si=jhaYSU7_maKTcYBb&t=437)

#### Configuring the Robot in 3D

Configuring the Robot in 3D

In 3D, you can set how the arm of the robot will be animated on the tab Robot Arm Animation . The robot arm animation paths determine which points the robot touches before it picks a part up or deposits it.

This way you can model more specific gripping actions than the predefined ones as well as prevent collisions manually. Robot arm animation paths are only used for robots which have at least three axes.

You can choose to animate the robot with one axis, with three axes, with four axes including a ball joint, with five axes, or with six axes. You can, for example, see the number of axes by opening the dialog Graphic Structure of the object and counting how often you can expand an entry with an animatable object until no additional nested entry exists. If a robot in the structure has a different number of axes, the next lower level applies, a robot with two axes, is for example, treated as a one axis robot.

For the animation in 3D the PickAndPlace robot expects that the required nesting of axes with animation data is defined in the required depth as well as a suitable axes configuration.

The text box Animation Object on the tab MU Animation contains the defined animation objects for the respective robot.

For a six axis robot the Animation Object looks like this:

<!-- image -->

**Note**

Plant Simulation automatically adjusts a model created in previous versions of Plant Simulation .

The PickAndPlace robot starts with the highest animation level and then checks one after the other from top to bottom. Once it recognized a robot type, it does not proceed to find the next robot type.

The PickAndPlace robot applies the animation procedures in the sequence described below. It checks for a

- Six Axis Robot
- Five Axis Robot
- Four Axis Robot with Ball Joint Gripper
- SCARA Robot with Concluding Revolute Joint
- SCARA Robot with Concluding Prismatic Joint
- Three Axis Robot
- One Axis Robot

If the recognition process does not recognize any of the mentioned robot types, Plant Simulation rotates the robot completely around the rotation axis [0,0,-1] through the Rotation Center [0,0,0].

**Note**

The default PickAndPlace robot in versions before Plant Simulation 13.0 was a one axis robot that rotated as such. When loading a model from previous versions, which contains such a robot, this robot will not be changed.

In 3D, you can edit the dimension of the graphic of the objects by clicking Show Manipulators on the Edit ribbon tab or by pressing M on the keyboard.

<!-- image -->

The CranesAndMore library provides a seven axis robot moving on rails as a demonstrator.

**Note**

You can transform any material flow object or fluid object into a robot by exchanging its graphic with one of the robots in the folder 3D\s3d-graphics in the Plant Simulation installation folder.

See also

Robot Arm Animation

Pick and Place Parts with the PickAndPlace Robot

Configuring the Robot with Drag-and-Drop

Video on YouTube

[https://youtu.be/K-NEPvShU10?si=cy1EdJiu-gSTFGdy&amp;t=795](https://youtu.be/K-NEPvShU10?si=cy1EdJiu-gSTFGdy&t=795)

**Six Axis Robot**

Plant Simulation recognizes a robot as a six axis robot/6-axis robot if exactly the specified criteria are met.

- The first animatable object has a revolute joint around the rotation axis [0,0,1] or [0,0,-1] through the rotation center [0,0,0].
- And the first animatable object in the next lower level has a revolute joint around the rotation axis [0,1,0] or [0,-1,0] through the rotation center [0,0,0].
- And the first animatable object in the next lower level has a revolute joint around the rotation axis [0,1,0] or [0,-1,0] through the rotation center [0,0,0].
- And the first animatable object in the next lower level has a revolute joint around the rotation axis [0,0,1] or [0,0,-1] through the rotation center [0,0,0].
- And the first animatable object in the next lower level has a revolute joint around the rotation axis [0,1,0] or [0,-1,0] through the rotation center [0,0,0].

- And the first animatable object in the next lower level has a revolute joint around the rotation axis [0,0,1] or [0,0,-1] through the rotation center [0,0,0].
- And the attribute \_3D.AnimationObject exactly references the respective lowest animatable object.
- And a suitable animation path exists for the object, which the attribute \_3D.AnimationObject references.

**Note**

If any of the criteria listed above are not met, Plant Simulation will not recognize the object as a six axis robot .

The six axis robot can reach all points in its gripping range. It can position the MU in all positions if it can reach the position.

**Note**

If you change rotations of the three lowest-positioned animatable objects so that a rotation around a slanting axis results, it might happen that the robot cannot position the MU in all positions even if it is located within its gripping range. The same can occur if the toolholder of the robot is positioned perpendicular above the insertion point.

If you change the rotation of any animatable object, except for the fourth object, so that the object is rotated by an angle unequal to 0° around an axis that is not the rotation axis as specified above, it might happen that the robot cannot position or rotate the MU as expected. The same might happen, if the fourth object is rotated differently than either by an angle of -90° around [0,1,0] or by an angle of 90° around [0,-1,0].

This also affects the pose/joint tool

**Note**

The six axis robot uses user-defined robot arm animations . If the robot does not have user-defined robot arm animations, it moves up and down to make the animation look more realistic.

**Note**

The robots PickAndPlaceComau.s3d and PickAndPlaceKuka.s3d in the installation folder &gt; 3D &gt; s3dgraphics are six axis robots . You can replace a robot with these two robots with the command Exchange Graphics .

<!-- image -->

, which might be positioned incorrectly.

<!-- image -->

<!-- image -->

The text box Animation Object on the tab MU Animation contains the defined animation objects for the respective robot.

<!-- image -->

**Back to**

Configuring the Robot in 3D

**Video on YouTube**

**[https://youtu.be/K-NEPvShU10?si=cy1EdJiu-gSTFGdy&amp;t=795](https://youtu.be/K-NEPvShU10?si=cy1EdJiu-gSTFGdy&t=795)**

##### Five Axis Robot

Plant Simulation recognizes a robot as a fi ve axis robot/5-axis robot if exactly the specified criteria are met.

- The first animatable object has a revolute joint around the rotation axis [0,0,1] or [0,0,-1] through the rotation center [0,0,0].
- And the first animatable object in the next lower level has a revolute joint around the rotation axis [0,1,0] or [0,-1,0] through the rotation center [0,0,0].
- And the first animatable object in the next lower level has a revolute joint around the rotation axis [0,1,0] or [0,-1,0] through the rotation center [0,0,0].
- And the first animatable object in the next lower level has a revolute joint around the rotation axis [0,1,0] or [0,-1,0] through the rotation center [0,0,0].
- And the first animatable object in the next lower level has a revolute joint around the rotation axis [0,0,1] or [0,0,-1] through the rotation center [0,0,0].
- And the attribute \_3D.AnimationObject exactly references the respective lowest animatable object.
- And a suitable animation path exists for the object, which the attribute \_3D.AnimationObject references.

**Note**

If any of the criteria listed above are not met, Plant Simulation will not recognize the object as a fi ve axis robot .

The fi ve axis robot can reach all points in its gripping range. It can position the MU in most of the established, but not in all positions.

**Note**

If you change the rotation of any animatable object, except for the fourth object, so that the object is rotated by an angle unequal to 0° around an axis that is not the rotation axis as specified above, it might happen that the robot cannot position or rotate the MU as expected. The same might happen, if the fourth object is rotated differently than either by an angle of -90° around [0,1,0] or by an angle of 90° around [0,-1,0].

This also affects the pose/joint tool

<!-- image -->

, which might be positioned incorrectly.

**Note**

This robot uses user-defined robot arm animations . If the robot does not have user-defined robot arm animations, it moves up and down to make the animation look more realistic.

<!-- image -->

The text box Animation Object on the tab MU Animation contains the defined animation objects for the respective robot.

<!-- image -->

**Back to**

##### Configuring the Robot in 3D

##### Four Axis Robot with Ball Joint Gripper

Plant Simulation recognizes a robot as a four axis robot with ball joint gripper/4-axis robot if exactly the specified criteria are met.

- The first animatable object has a revolute joint around the z-axis through the coordinate [0,0,0].
- And the first animatable object in the next lower level has a revolute joint around the rotation axis [0,1,0] or [0,-1,0] through the rotation center [0,0,0].
- And the first animatable object in the next lower level has a revolute joint around the rotation axis [0,1,0] or [0,-1,0] through the rotation center [0,0,0].
- And the first animatable object in the next lower level has a revolute joint through the rotation center [0,0,0].
- And the attribute \_3D.AnimationObject exactly references the respective lowest animatable object.
- And a suitable animation path exists for the object, which the attribute \_3D.AnimationObject references.

**Note**

If any of the criteria listed above are not met, Plant Simulation will not recognize the object as a four axis robot with ball joint gripper .

The four axis robot can reach all points within its gripping range. It can position the MU in all positions if it can reach the point.

**Note**

If you change the rotation of any animatable object, except for the fourth object, so that the object is rotated by an angle unequal to 0° around an axis that is not the rotation axis as specified above, it might happen that the robot cannot position or rotate the MU as expected.

This also affects the pose/joint tool

**Note**

This robot uses user-defined robot arm animations . If the robot does not have user-defined robot arm animations, it moves up and down to make the animation look more realistic.

<!-- image -->

, which might be positioned incorrectly.

**Note**

The default robot in Plant Simulation is a four axis robot with ball joint gripper . You cannot move its poses and joints with the mouse or with keyboard keys.

<!-- image -->

The text box Animation Object on the tab MU Animation contains the defined animation objects for the respective robot.

<!-- image -->

Back to

Configuring the Robot in 3D

Video on YouTube

[https://youtu.be/K-NEPvShU10?si=RT-DUXOYBHpr4spB&amp;t=700](https://youtu.be/K-NEPvShU10?si=RT-DUXOYBHpr4spB&t=700)

##### SCARA Robot with Concluding Revolute Joint

Plant Simulation recognizes a robot as a SCARA robot with concluding revolute joint if exactly the specified criteria are met.

- The first animatable object has a revolute joint around the rotation axis [0,0,1] or [0,0,-1] through the rotation center [0,0,0].
- And the first animatable object in the next lower hierarchy level has a revolute joint around the rotation axis [0,0,1] or [0,0,-1] through the rotation center [0,0,0].
- And the first animatable object in the next lower hierarchy level has a prismatic joint with the translation direction [0,0,1] or [0,0,-1].
- And the first animatable object in the next lower hierarchy level has a revolute joint around the rotation axis [0,0,1] or [0,0,-1] through the rotation center [0,0,0].
- And the attribute \_3D.AnimationObject exactly references the respective lowest animatable object.
- And a suitable animation path exists for the object, which the attribute \_3D.AnimationObject references.

**Note**

If any of the criteria listed above are not met, Plant Simulation will not recognize the object as a SCARA robot with concluding revolute joint .

The SCARA robot with concluding revolute joint can reach all points within its gripping range. It can only place the MUs in positions which are exclusively described by a rotation around the z-axis.

**Note**

If you change the rotation of any animatable object that is a revolute joint, so that the object is rotated by an angle unequal to 0° around an axis that is not the rotation axis as specified above, it might happen that the robot cannot position or rotate the MU as expected.

<!-- image -->

This also affects the pose/joint tool , which might be positioned incorrectly.

The text box Animation Object on the tab MU Animation contains the defined animation objects for the respective robot.

**Back to**

**Configuring the Robot in 3D**

##### SCARA Robot with Concluding Prismatic Joint

Plant Simulation recognizes a robot as a SCARA robot with concluding prismatic joint if exactly the specified criteria are met.

- The first animatable object has a revolute joint around the rotation axis [0,0,1] or [0,0,-1] through the rotation center [0,0,0].
- And the first animatable object in the next lower hierarchy level has a revolute joint around the rotation axis [0,0,1] or [0,0,-1] through the rotation center [0,0,0].
- And the first animatable object in the next lower hierarchy level has a revolute joint around the rotation axis [0,0,1] or [0,0,-1] through the rotation center [0,0,0].
- And the first animatable object in the next lower hierarchy level has a prismatic joint with the translation direction [0,0,1] or [0,0,-1].
- And the attribute \_3D.AnimationObject exactly references the respective lowest animatable object.
- And a suitable animation path exists for the object, which the attribute \_3D.AnimationObject references.

**Note**

If any of the criteria listed above are not met, Plant Simulation will not recognize the object as a SCARA robot with concluding prismatic joint .

The SCARA robot with concluding prismatic joint can reach all points within its gripping range. It can only place the MUs in positions which are exclusively described by a rotation around the z-axis.

**Note**

If you change the rotation of any animatable object that is a revolute joint, so that the object is rotated by an angle unequal to 0° around an axis that is not the rotation axis as specified above, it might happen that the robot cannot position or rotate the MU as expected.

<!-- image -->

This also affects the pose/joint tool , which might be positioned incorrectly.

**Note**

The robot PickAndPlaceComauSCARA.s3d in the installation folder &gt; 3D &gt; s3d-graphics is a SCARA robot . You can replace a robot with this robot with the command Exchange Graphics .

<!-- image -->

The text box Animation Object on the tab MU Animation contains the defined animation objects for the respective robot.

<!-- image -->

Back to

**Configuring the Robot in 3D**

##### Three Axis Robot

Plant Simulation recognizes a robot as a three axis robot/3-axis robot if exactly the specified criteria are met.

- The first animatable object has a revolute joint around the rotation axis [0,0,1] or [0,0,-1] through the rotation center [0,0,0].
- And the first animatable object in the next lower level has a revolute joint around the rotation axis [0,1,0] or [0,-1,0] through the rotation center [0,0,0].
- And the first animatable object in the next lower level has a revolute joint around the rotation axis [0,1,0] or [0,-1,0] through the rotation center [0,0,0].
- And the attribute \_3D.AnimationObject exactly references the respective lowest animatable object.
- And a suitable animation path exists on the object which the attribute \_3D.AnimationObject references.

**Note**

If any of the criteria listed above are not met, Plant Simulation will not recognize the object as a three axis robot .

A three axis robot can reach all points within it gripping range. The MU is attached rigidly at the gripper and is only rotated by the robot movement, not independently by itself.

**Note**

If you change the rotation of any animatable object, so that the object is rotated by an angle unequal to 0° around an axis that is not the rotation axis as specified above, it might happen that the robot cannot position or rotate the MU as expected.

This also affects the pose/joint tool

**Note**

This robot uses user-defined robot arm animations . If the robot does not have user-defined robot arm animations, it moves up and down to make the animation look more realistic.

**Note**

All robots delivered with Plant Simulation 13.0 are three axis robots . When loading a model created in this version, the robot will not be adjusted.

<!-- image -->

, which might be positioned incorrectly.

##### One Axis Robot

The text box Animation Object on the MU Animation contains the defined animation objects for the respective robot.

**Back to Configuring the Robot in 3D**

##### One Axis Robot

Plant Simulation recognizes a robot as a one axis robot/1-axis robot if exactly the specified criteria are met.

- The first animatable object has a revolute joint around the rotation axis [0,0,1] or [0,0,-1] through the rotation center [0,0,0].
- And the attribute \_3D.AnimationObject exactly references the respective lowest animatable object.
- And a suitable animation path exists for the object, which the attribute \_3D.AnimationObject references.

**Note**

If any of the criteria listed above are not met, Plant Simulation will not recognize the object as a one axis robot .

The one axis robot cannot reach all points within it gripping range. The MU is attached rigidly at the gripper and is only rotated by the robot movement, not independently by itself.

**Note**

The one axis robot does not use any user-defined robot arm animations.

The text box Animation Object on the tab MU Animation contains the defined animation objects for the respective robot.

Back to Configuring the Robot in 3D

#### Dialog Box of the PickAndPlace Robot

Dialog Box of the PickAndPlace Robot

Double-click the icon of the PickAndPlace Robot to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

**Angles Table [PickAndPlace]**

###### Angles Table [PickAndPlace]

To open the table of the angles, at which the PickAndPlace robot picks the part up or at which it places it, click this button.

<!-- image -->

You can view or fine-tune these settings:

- The Name of the predecessor at which the PickAndPlace robot picks the part up or the Name of the successor onto which the PickAndPlace robot deposits the part.

You can also type a sensor on the Conveyor in the column Name , for example Conveyor.Sensors.ID1 . This is useful if you want to set several angles on the Conveyor .

<!-- image -->

- The Angle between the station in the column Name and the PickAndPlace robot .

<!-- image -->

If you insert Connectors or if you drag an object onto the PickAndPlace robot and drop it there, Plant Simulation adds the respective values to the angles table.

If you delete a Connector , Plant Simulation does not delete the entry of the now unconnected object from the table. You have to delete the entry yourself, for example by right-clicking the respective row and selecting Delete Row on the context menu.

You can also manually change values or names in the angles table or add new stations to it. This way you can, for example, request the PickAndPlace robot in a Sensor Control .

**Note**

Plant Simulation automatically applies changed names of stations to the Times Table .

If you want the PickAndPlace robot to compute the angles at which you connected it to its predecessors and to its successors, click it with the right mouse button and select Calculate Angles .

<!-- image -->

**SimTalk**

setAnglesTable [SimTalk]

getAnglesTable [SimTalk]

calculateAngles [SimTalk] - PickAndPlace

See also

Times Table [PickAndPlace]

Calculate Angles

Video on YouTube

[https://youtu.be/K-NEPvShU10?si=rrKhAn5Vtns3Px7p&amp;t=109](https://youtu.be/K-NEPvShU10?si=rrKhAn5Vtns3Px7p&t=109)

**Times Table [PickAndPlace]**

###### Times Table [PickAndPlace]

To open the table of the rotation times, click this button.

<!-- image -->

These are the times, which the PickAndPlace robot needs to rotate from the station in the leftmost column to the respective stations in the columns to the right and vice versa.

You can also type in a Time Factor with which all times in the table are multiplied. This way you can simulate the PickAndPlace robot with different speeds without having to manually change the times in the table.

You can view or fine-tune these settings:

- The Names of all objects, which the PickAndPlace robot is to serve and the Default Angle to which the PickAndPlace robot moves after it has deposited the part.
- The Times above the diagonal are the times during which the PickAndPlace robot rotates Empty .

The times below the diagonal are the times during which the PickAndPlace robot rotates full, i.e., while a part is located on it.

The diagonal in the table runs from the values in the topmost cell in the column default angle to the bottommost cell in the last column.

<!-- image -->

In the example above the cell labeled A contains the rotation time from the Station to the Source with picked-up parts, namely 0.3743 seconds.

The cell labeled B contains the rotation time from the Drain to the Source without parts.

The cell labeled C contains the rotation time from Drain1 to the Default Angle without parts.

If you insert Connectors or if you drag an object onto the PickAndPlace robot and drop it there, Plant Simulation enters the respective values into the Times Table . For the calculation Plant Simulation assumes that a quarter-rotation takes up one second. You can change these times.

If you delete a Connector , Plant Simulation does not delete the entry of the now unconnected object from the Times Table . You have to delete the entry in the Angles Table , for example by right-clicking the respective row and selecting Delete Row on the context menu. When you click Apply in the dialog box of the PickAndPlace robot , Plant Simulation also deletes this entry from the Times Table .

You can also manually change the times.

SimTalk

setTimesTable [SimTalk]

getTimesTable [SimTalk]

See also

Time Factor [PickAndPlace]

Default Angle [PickAndPlace]

Angles Table [PickAndPlace]

Video on YouTube

https://youtu.be/K-NEPvShU10?si=rrKhAn5Vtns3Px7p&amp;t=109

Go to Default Position [check box] - PickAndPlace

To rotate the PickAndPlace robot back to its default position after it has deposited the part, select this check box.

**Note**

When you activate the check box, the PickAndPlace robot uses the Default Angle , when you reset the model.

Then, type in the Default Angle at which the default position is located.

<!-- image -->

When Go to Default Position is active, you can also activate the check box Only for Empty Blocking List .

SimTalk

GoToDefaultPosition [SimTalk] - PickAndPlace

OnlyForEmptyBlockingList [SimTalk]

DefaultAngle [SimTalk] - PickAndPlace

See also

Default Angle [PickAndPlace]

Only for Empty Blocking List [PickAndPlace]

###### Only for Empty Blocking List [PickAndPlace]

To make the PickAndPlace robot only rotate back to its default position if its blocking list is empty, i.e., if no additional requests are registered for it, select this check box.

<!-- image -->

###### Time Factor [PickAndPlace]

Time Factor [PickAndPlace]

Type in the Time Factor with which all times in the Times Table are multiplied. This enables to simulate the PickAndPlace robot with different speeds without having to manually change the times in the table.

SimTalk

TimeFactor [SimTalk]

See also

Times Table [PickAndPlace]

###### Default Angle [PickAndPlace]

Type in the Default Angle in degrees to which the PickAndPlace robot rotates when you selected Go to Default Position .

If you would like the PickAndPlace robot to rotate to the side on which the start position is located, add 180 ° to this angle. You can type in a value between 0 ° and 360 °.

<!-- image -->

Note

The Default Angle is also used as the start position after a Reset , no matter if Go to Default Position is activated or not.

SimTalk

DefaultAngle [SimTalk] - PickAndPlace

See also

Go to Default Position [check box] - PickAndPlace

###### Blocking Angle [text box]

Blocking Angle [text box]

Type in the Blocking Angle in degrees which the PickAndPlace robot cannot cross while rotating. This prevents the robot from taking the shortest way.

<!-- image -->

The default setting -1 means that no blocking angle applies and that the robot thus takes the shortest way. You can type in an angle between 0 and 360 degrees.

The Blocking Angle only affects the animation, the simulation is controlled by the rotation times which you defined in the Times Table .

SimTalk

BlockingAngle [SimTalk]

See also

Times Table [PickAndPlace]

###### Capacity [text box] - PickAndPlace

Type in the Capacity , i.e., the number of MUs that the PickAndPlace robot can transport at any one time. Type in a number greater than 1 .

The Capacity enables the PickAndPlace robot to transport more than one part at the same time. It might, for example, pick up a number of bottles and place them into the appropriate slots of a bottle crate one at a time (FIFO).

If you want to unload the parts according to another rule, for example LIFO, you can program this in an Exit Control .

SimTalk

Capacity [SimTalk] - PickAndPlace

See also

Pick Up Several Parts and Place Them with the Robot

###### MU Conveying Direction [drop-down list]

Select the conveying direction of the MU when the PickAndPlace robot passes the part on to its successor and places it there.

**Note**

For the settings Retain , Rotate by 90° to the right , Rotate by 90° to the left , and Rotate by 180° the PickAndPlace robot executes a relative rotation depending on the direction from which the MU arrives.

For the settings Forwards , Lateral right , Backwards , and Lateral left the rotation is an absolute rotation independent of the direction from which the MU arrives.

<!-- image -->

| Conveying direction     | Description                                                                                                        | Looks like this in 2D   | Looks like this in 3D   |
|-------------------------|--------------------------------------------------------------------------------------------------------------------|-------------------------|-------------------------|
| Retain                  | The robot continues conveying the part in the same direction in which it arrives.                                  |                         |                         |
| Rotate 90° to the right | The robot rotates the part 90° to the right and places it on the successor.                                        |                         |                         |
| Rotate 90° to the left  | The robot rotates the part 90° to the left and places it on the successor.                                         |                         |                         |
| Rotate 180°             | The robot rotates the part 180° and places it on the successor.                                                    |                         |                         |
| Forwards                | The robot rotates the part, so that it comes to rest on the successor forward and then places it on the successor. |                         |                         |

<!-- image -->

| Conveying direction   | Description                                                                                                                       | Looks like this in 2D   | Looks like this in 3D   |
|-----------------------|-----------------------------------------------------------------------------------------------------------------------------------|-------------------------|-------------------------|
| Lateral right         | The robot rotates the part, so that it comes to rest on the successor laterally to the right and then places it on the successor. |                         |                         |
| Backwards             | The robot rotates the part, so that it comes to rest on the successor backward and then places it on the successor.               |                         |                         |
| Lateral left          | The robot rotates the part, so that it comes to rest on the successor laterally to the left and then places it on the successor.  |                         |                         |

**SimTalk**

**MUConveyingDirection [SimTalk]**

See also

Set the Conveying Direction of the Parts

**Loading Time [PickAndPlace]**

###### Loading Time [PickAndPlace]

The Loading Time is the time it takes the PickAndPlace robot for picking up a part at a station. If the PickAndPlace robot is full, it rotates to the target station and places the part there.

<!-- image -->

The Loading Time is the time it takes the PickAndPlace robot for picking up a part at a station.

- If the delivering station is a point-oriented object, the part is booked on the PickAndPlace robot while it picks it up. The delivering station is locked until the loading time has elapsed.
- If the delivering station is a length-oriented object, the part remains on the delivering station during the loading time and is then moved on to the PickAndPlace robot .

Select a distribution, and type the values, which that distribution requires, into the text box. Plant Simulation shows these values along the upper border of the tab.

You can also enter a constant time ( Const ).

If you select the Formula distribution, you can type in a numeric expression or the name of a Method .

You can use the anonymous identifier @ to access the part for which the loading time applies. The anonymous identifier ? points to the PickAndPlace robot .

**Note**

During the Loading Time no part can be placed onto the delivering station.

**Note**

Behavior during interruptions of the PickAndPlace robot

Plant Simulation extends the Loading Time by Interruption times of the PickAndPlace robot . The delivering station remains locked during the interruption.

**Note**

Behavior during interruptions of the delivering station .

Interruptions of the delivering station do not affect loading the part by the PickAndPlace robot . The loading operation will be executed while the interruption lasts.

**Note**

The entrance of the PickAndPlace robot is open while its Loading Time is running. The entrance is closed once the part is actually moved on. The PickAndPlace robot opens the entrance again after the Unloading Time has passed.

SimTalk

LoadingTime [SimTalk] - PickAndPlace

LoadingTime . Type [SimTalk] - distribution parameter

IsLoading [SimTalk]

putAttributeNamesIntoTable [SimTalk] - distributions

**Unloading Time [PickAndPlace]**

###### Unloading Time [PickAndPlace]

The Unloading Time is the time it takes the PickAndPlace robot for placing the part it picked up at another station onto the target station.

<!-- image -->

The Unloading Time is the time it takes the PickAndPlace robot for placing the part, which it picked up at another station, onto the target station.

- If the target station is a point-oriented object, the part is booked on the PickAndPlace robot while it places it. The target station is locked until the unloading time has elapsed.
- If the target station is a length-oriented object, the part is moved on to the length-oriented object before the Unloading Time starts.

Select a distribution, and type the values, which that distribution requires, into the text box. Plant Simulation shows these values along the upper border of the tab.

You can also type in a constant time ( Const ).

If you select the Formula distribution, you can type in a numeric expression or the name of a Method .

You can use the anonymous identifier @ to access the part for which the unloading time applies. The anonymous identifier ? points to the PickAndPlace robot .

**Note**

Behavior during interruptions of the PickAndPlace robot .

Plant Simulation extends the Unloading Time by interruption times of the PickAndPlace robot . The target processing station remains locked during the Interruption .

**Note**

Behavior during interruptions of the target station .

Interruptions of the target station do not affect unloading the part by the PickAndPlace robot . The unloading operation continues while the interruption lasts.

**Note**

The entrance of the PickAndPlace robot is open while its Loading Time is running. The entrance is closed once the part is actually moved on. The PickAndPlace robot opens the entrance again after the Unloading Time has passed.

SimTalk UnloadingTime [SimTalk] - PickAndPlace UnloadingTime . Type [SimTalk] - distribution parameter IsLoading [SimTalk] putAttributeNamesIntoTable [SimTalk] - distributions

###### Number of Animation Events [PickAndPlace]

Click the icon of the PickAndPlace with the left mouse button and click Edit Icons on the Home ribbon tab.

Go to the Animation ribbon tab of the Icon Editor and select Set Animation Events . Type a number into the text box that determines how often Plant Simulation draws the PickAndPlace robot while it rotates.

<!-- image -->

**See also**

Set Animation Events

##### Tab Failures

Define failures as described under the Tab Failures .

##### Tab Controls

##### Tab Controls

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
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

In addition, you can select the Shift Calendar .

###### Tab Controls

See also Entrance Control [general description] Exit Control [general description] Pull Control [PickAndPlace] Target Control [PickAndPlace]

###### Target Control [PickAndPlace]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Target Control , which is called as soon as the PickAndPlace robot has picked up the part. As opposed to the Exit Control , the part is not ready to exit the object yet.

<!-- image -->

If you use a Target Control , you have to use the method setDestination to determine the target object.

Plant Simulation also calls the Target Control when the PickAndPlace robot has deposited the part. In this case you set the object at which the robot is going to pick up the next part by calling the method setDestination .

When the PickAndPlace robot calls the Target Control after depositing the part, the active element ( @ ) is void.

Plant Simulation only calls the Target Control while unloading if you cleared the check box Go to Default Position .

<!-- image -->

**Note**

Do not use an Exit Control for determining the target of the MU , as an Exit Control will be called only when the MU is ready to exit the PickAndPlace robot . This point in time is too late though, as the target has to be determined earlier in time.

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

The standard target control as a user-defined attribute looks like this:

<!-- image -->

###### Pull Control [PickAndPlace]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Pull Control , which is called whenever the PickAndPlace robot is ready to pick up a new part or if it is ready when a new MU is waiting at its entrance.

<!-- image -->

If you select Load Part onto MU at Sensor as the Target Selection , Plant Simulation only considers the PickAndPlace robot to be ready if a Container/Transporter is waiting at the sensor . This also applies if you programmed a pull control . It will only be called when a Container/Transporter is waiting at the sensor .

In the Pull Control you can determine which of the parts, which intend to move onto the object, the PickAndPlace robot will accept. For this you have to get the Forward Blocking List of the object with the method fwBlockList and unblock a MU in the list with the method unblock .

**Note**

If you only need the first entry of the Forward Blocking List , you can use the read-only-attribute FwBlockListEntry1 for those objects which have a Forward Blocking List . Access is much faster than with the method fwBlockList .

Let us assume that red parts are especially important and thus have a priority for being processed. Then you can always pull red parts first from the predecessors and only then pull parts in other colors.

**Note**

The Pull Control does not determine if a MU is to be moved to this or to another successor. Instead, it selects one of the parts which have already been determined to move on to this successor.

**Note**

F2 opens the dialog of the object, whose name you typed into the text box.

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

The standard pull control as a user-defined attribute looks like this:

<!-- image -->

**SimTalk**

PullCtrl [SimTalk] - PickAndPlace

See also

Select Object [for controls]

Waiting [state, material flow objects]

Tab Exit

Tab Exit

Select how the PickAndPlace robot moves the parts on to its target stations on the tab Exit .

As a rule you will configure the robot with drag-and-drop .

- For the setting Target Selection &gt; Exit strategy or target control you can select the desired exit strategy . Here the PickAndPlace robot has to be connected with the target objects with Connectors .

To only rotate the PickAndPlace robot to a part that wants to exit the predecessor and to pick it up if the destination object is also ready to receive it, select Wait for free target .

<!-- image -->

- For the settings Target Selection &gt; Place part at sensor and Load part onto MU at sensor the tab shows the settings Target Object and Target Sensor ID . Here the PickAndPlace robot does not have to be connected with a Connector . Instead, the PickAndPlace robot uses the sensor which you have to create.

<!-- image -->

**See also**

Tab Exit [general description]

Blocking [exit strategy]

Strategy [material flow objects]

Wait for Free Target [PickAndPlace]

###### Tab Exit

**Video on YouTube**

[https://youtu.be/K-NEPvShU10?si=K\_SUgl3BdFCcsjMm&amp;t=606](https://youtu.be/K-NEPvShU10?si=K_SUgl3BdFCcsjMm&t=606)

###### Wait for Free Target [PickAndPlace]

To only rotate the PickAndPlace robot to a part that wants to exit the predecessor and to pick it up if the destination object is also ready to receive it, select this check box.

<!-- image -->

To rotate the PickAndPlace robot immediately to the part, clear the check box.

Activating Wait for Free Target prevents that the PickAndPlace robot transports parts to a Station or a Conveyor that is already occupied or reserved. The PickAndPlace robot thus is available for other jobs that it can do the moment.

Plant Simulation only evaluates Wait for Free Target for the setting Target Selection &gt; Exit strategy or target control .

<!-- image -->

Plant Simulation enters the part that cannot be transported into the Exit Blocking List of the target object.

**Note**

If you select the check box, Plant Simulation already evaluates the entered Exit Strategy or the Target Control for the part before the PickAndPlace robot rotates to the part to pick it up.

Plant Simulation enters the thus determined target into the text box Target Object .

**SimTalk**

WaitForFreeTarget [SimTalk] -PickAndPlace

See also

Target Selection [drop-down list]

TargetSelection [SimTalk]

ReservedFor [SimTalk]

ReservedPlace [SimTalk]

contentsAndReservedList [SimTalk]

###### Target Selection [drop-down list]

Select how the PickAndPlace robot selects the target for the part that is to be moved:

- Exit strategy or target control : This is the default behavior of previous versions of the PickAndPlace robot . You either set the target with the selected Exit Strategy or you define the target in the Target Control .
- Load part onto MU at sensor : For this setting you have to manually create a front-triggered sensor with light-barrier mode on the length-oriented target object. In addition, you have to enter the Target Object and the Target Sensor ID . Stopping the Container/Transporter , loading and sending the Container/ Transporter on only works automatically if you did not enter a control. If you use a control, you have to program stopping and sending the Container/Transporter on in this control.

<!-- image -->

<!-- image -->

**Note**

The PickAndPlace robot only picks the part to be loaded up at the sensor if a Container/Transporter is waiting at the sensor .

This also applies when you programmed a Pull Control . It will only be called if a Container/ Transporter is waiting at the sensor .

- Place part at sensor : For this setting you have to manually create a rear-triggered sensor with light barrier mode on the length-oriented target object. In addition, you have to enter the Target Object and the Target Sensor ID .

<!-- image -->

**Note**

Selecting and setting the target object is actually quite easy. Just drag the PickAndPlace robot over the Conveyor , Track , or TwoLaneTrack and select the operation that is to take place, compare this . Plant Simulation then automatically sets the attributes and creates the respective sensor.

<!-- image -->

**SimTalk**

TargetSelection [SimTalk]

See also

Configuring the Robot with Drag-and-Drop

Place Parts with a Target Control

Load and Unload Parts at the Sensor of a Conveyor

Configure the Robots

Video on YouTube

[https://youtu.be/9g6Uou-8eMc?si=5rrGO9qnGKLoDx4L&amp;t=1298](https://youtu.be/9g6Uou-8eMc?si=5rrGO9qnGKLoDx4L&t=1298)

Target Object

Type the path to the length-oriented object, at which the part is to be placed or loaded, into the text box.

Or click and select the target object in the dialog Select Object .

<!-- image -->

SimTalk

**TargetObject [SimTalk]**

See also

Load and Unload Parts at the Sensor of a Conveyor

Configure the Robots

###### Target Sensor ID [text box]

Target Sensor ID [text box]

Type in the Sensor ID of the target sensor at which the part will be placed or loaded.

<!-- image -->

**Note**

Plant Simulation does not create the sensor automatically. You have to create it manually or use drag-and-drop.

**SimTalk**

##### TargetSensorID [SimTalk]

**See also**

Load and Unload Parts at the Sensor of a Conveyor

Configure the Robots

##### Tab Statistics [PickAndPlace]

Statistics is described under the Tab Statistics .

In addition to these vales, the PickAndPlace robot collects these statistical values:

| Item            | Description                                                                                                                                   | Read-only attribute                                 | Item German    |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------|----------------|
| Rotation Empty  | Shows the portion of the statistics collection period during which the PickAndPlace robot was rotating without moving a part, i.e., was Empty | StatRotationEmptyP ortion [SimTalk] - PickAndPlace  | Drehung leer   |
| Rotation Loaded | Shows the portion of the statistics collection period during which the PickAndPlace robot was rotating while moving a part                    | StatRotationLoaded Portion [SimTalk] - PickAndPlace | Drehung belegt |

<!-- image -->

To view Rotation Time in the Statistics Report , select View &gt; Show Statistics Report in the dialog of the object. You can also click the right mouse button in the Frame and select Show Statistics Report or you can press F6 .

**Tab Statistics [PickAndPlace]**

**See also**

Resource Statistics [check box]

Resource Type

<!-- image -->

##### Tab Importer [PickAndPlace]

The importer is described under the Tab Importer . The PickAndPlace robot only provides the Failure Importer .

To view Importer Statistics in the Statistics Report , click the object in the Frame , and press F6 ( Show Statistics Report ), or click Show Statistics Report on the Home ribbon tab.

You can also click the object in the Frame with the right mouse button and select Show Statistics Report on the context menu.

<!-- image -->

See also

Failure Importer

**Tab Energy**

##### Tab Energy

Select energy settings for the object on the Tab Energy .

Tab Costs

Select costs settings for the object on the Tab Costs .

While the PickAndPlace-robot picks a part up at a station, rotates to the target station, and places it there costs accrue. These result from the sum of the investment costs and the operating costs.

Note

The investment costs only accrue during the Depreciation Period .

The costs are allocated to the part as accrued costs .

If the PickAndPlace-robot is empty, the costs remain with the PickAndPlace-robot as general costs .

See also

Simulate the Accrued Costs of the Machines

CostAnalyzer &gt; How the CostAnalyzer Assigns Costs to Part Types

CostAnalyzer &gt; Costs Shown in the Costs Report

**Tab User-defined**

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

##### Navigate Menu

The commands are described under the Navigate Menu .

**View Menu**

##### View Menu

The View Menu provides commands to access its functions.

| Refresh [on View menu]                     | Forward Blocking List     |
|--------------------------------------------|---------------------------|
| Show Statistics Report [on View menu]      | Exit Blocking List        |
| Show Attributes and Methods [on View menu] | Associated Lockout Zones  |
| Contents [material flow objects]           | Associated Shift Calendar |

##### Tools Menu

The commands are described under the Tools Menu .

**Tabs Menu**

##### Tabs Menu

Use the commands of the Tabs menu to show or hide individual tabs of the material flow objects. If you hide tabs that you do not need, Plant Simulation opens the dialog faster, and you can change to those tabs faster that you need in your daily work.

To apply the changed settings, click OK , close the dialog, and reopen it

The menu shows a check mark to the left of the displayed tabs.

The command Inherit turns inheritance of the displayed or hidden tabs in the dialog off or on.

<!-- image -->

##### Help Menu

The commands are described under the Help Menu .

**Methods of the PickAndPlace Robot**

#### \_Methods of the PickAndPlace Robot

The PickAndPlace robot provides:

- The methods listed in the table of contents to the left.
- The Methods of the Material Flow Objects .
- The Methods of All Objects .

To view all of the methods , read-only attributes and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

An example of the Syntax line of the individual methods might look like this:

```simtalk
< Path >.openDialog([CallOpenControl:boolean:=false]) → boolean
```

- The expression &lt;Path&gt; designates the path of the object to which the method applies.
- The signature of the method, consisting of the identifier and the data type of the parameter, is listed in parentheses. The expression (Parameter:string) , for example, designates a parameter of data type string . Instead of a constant value, you can also use a variable of the required type or a method that returns the required data type.

**Note**

Make sure to enter the parentheses for expressions within parentheses (…). Not entering them may lead to unexpected results and open the Debugger .

Optional parameters are listed within brackets. The expression [,Parameter:boolean] , for example, means that you can, but do not have to enter the boolean parameter.

If a parameter has a default value, the signature shows the default value after the parameter.

If the method has a return value, the signature shows its data type after the arrow -&gt;.

##### calculateAngles [SimTalk] - PickAndPlace

Computes the angles at which you connected the PickAndPlace robot designated by &lt;Path&gt; with its predecessor and with its successor in the Frame .

Remarks

The PickAndPlace robot then enters the angles into the Angles Table .

Type

Method

Syntax

&lt; Path &gt;.calculateAngles

**Example**

MyPickAndPlace.calculateAngles SimTalk getAnglesTable [SimTalk]

setAnglesTable [SimTalk]

See also

Calculate Angles

Angles Table [PickAndPlace]

##### getAnglesTable [SimTalk]

getAnglesTable [SimTalk]

Returns the Angles Table of the PickAndPlace robot designated by &lt;Path&gt; and writes it into a table.

Type

Method

Syntax

<!-- image -->

Parameter

The parameter AnglesTable of data type table designates the name of the table.

**It contains:**

- The Name of the predecessor at which the PickAndPlace robot picks the part up or the Name of the successor onto which the PickAndPlace robot deposits the part.

The column Name can also contain a sensor on the Conveyor , for example Conveyor.sensorID(1) .

<!-- image -->

- The Angle between the station in the column Name and the PickAndPlace robot .

<!-- image -->

If you insert Connectors or if you drag an object onto the PickAndPlace robot and drop it there, Plant Simulation adds the respective values to the angles table. If you delete a Connector , Plant Simulation does not remove the respective entry from the table. You have to do this manually.

You can also manually change values or names in the angles table or add new stations to it. This way you can, for example, request the PickAndPlace robot in a Sensor Control .

**Note**

Plant Simulation automatically applies changed names of stations to the Times Table .

Return Value

The return value has the data type table .

Example

```simtalk
var myAnglesTable: table
MyPickAndPlace.getAnglesTable(myAnglesTable)
```

SimTalk

setAnglesTable [SimTalk]

calculateAngles [SimTalk] - PickAndPlace

See also

Angles Table [PickAndPlace]

Times Table [PickAndPlace]

getDestination [SimTalk] - PickAndPlace

Returns the target object where the PickAndPlace robot designated by &lt;Path&gt; is to pick the part up or to deposit it.

Type

Method

Syntax

< Path >.getDestination → any

Return Value

The return value has the data type any .

Is either the target object, or the target place on the target object, or a sensor on the target object.

Also returns a target object if the PickAndPlace robot rotates to the target without transporting a part.

Examples

```simtalk
// sets and gets the target of the part
PickAndPlace.setDestination(@.target, true)
print PickAndPlace.getDestination
end
MyStation := ?.getDestination
```

SimTalk

setDestination [SimTalk] - PickAndPlace

GetLastDestination [SimTalk]

getTimesTable [SimTalk]

Returns the Times Table of the PickAndPlace robot designated by &lt;Path&gt; and writes it into a table.

Type

Method

Syntax

&lt; Path &gt;.getTimesTable(TimesTable:table) -&gt; table

Parameter

The parameter TimesTable of data type table designates the name of the table. The times table contains:

- The Names of all objects, which the PickAndPlace robot is to serve and the Default Angle to which the PickAndPlace robot moves after it has deposited the part.
- The Times above the diagonal are the times during which the PickAndPlace robot rotates empty .

The times below the diagonal are the times during which the PickAndPlace robot rotates full, i.e., while a part is located on it.

The diagonal in the table runs from the values in the topmost cell in the column default angle to the bottommost cell in the last column.

<!-- image -->

In the example above the cell labeled A contains the rotation time from the Station to the Source with picked-up parts, namely 0.3743 seconds.

The cell labeled B contains the rotation time from the Drain to the Source without parts.

The cell labeled C contains the rotation time from Drain1 to the Default Angle without parts.

When you insert Connectors or when you drag an object onto the PickAndPlace robot and drop it there, Plant Simulation enters the respective values into the Times Table . For the calculation Plant Simulation assumes that a quarter-rotation takes up one second. You can change these times.

If you insert Connectors or if you drag an object onto the PickAndPlace robot and drop it there, Plant Simulation enters the respective values into the Times Table . For the calculation Plant Simulation assumes that a quarter-rotation takes up one second. You can change these times.

If you delete a Connector , Plant Simulation does not delete the entry of the now unconnected object from the Times Table . You have to delete the entry in the Angles Table , for example by right-clicking the respective row and selecting Delete Row on the context menu. When you click Apply in the dialog box of the PickAndPlace robot , Plant Simulation also deletes this entry from the times table .

Return Value

The return value has the data type table .

Examples

MyPickAndPlace.getTimesTable(myTimesTable)

```simtalk
var myTimesTable: table
MyPickAndPlace.getTimesTable(myTimesTable)
```

SimTalk

setTimesTable [SimTalk]

See also

Times Table [PickAndPlace]

Angles Table [PickAndPlace]

Default Angle [PickAndPlace]

Empty [state, material flow objects]

##### setAnglesTable [SimTalk]

Assigns an Angles Table to the PickAndPlace robot designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.setAnglesTable(AnglesTable:table)

Parameter

The parameter AnglesTable of data type table designates the name of the table. It contains the following settings.

You can change these values:

- The Name of the predecessor at which the PickAndPlace robot picks the part up or the Name of the successor onto which the PickAndPlace robot deposits the part. You can also enter a sensor on the Conveyor into the column Name , for example Conveyor.Sensors.id1 . This is useful if you want to set several angles on the Conveyor .
- The Angle between the station in the column Name and the PickAndPlace robot .

<!-- image -->

If you insert Connectors or if you drag an object onto the PickAndPlace robot and drop it there, Plant Simulation adds the respective values to the angles table. If you delete a Connector , Plant Simulation does not remove the respective entry from the table. You have to do this manually.

You can also manually change values or names in the angles table or add new stations to it. This way you can, for example, request the PickAndPlace robot in a Sensor Control .

**Note**

Plant Simulation automatically applies changed names of stations to the Times Table .

**Example**

MyPickAndPlace.setAnglesTable(myAngleTable)

SimTalk

getAnglesTable [SimTalk]

calculateAngles [SimTalk] - PickAndPlace

See also

Angles Table [PickAndPlace]

Times Table [PickAndPlace]

##### setDestination [SimTalk] - PickAndPlace

Sets the target object at which the PickAndPlace robot designated by &lt;Path&gt; deposits the part or wants to pick up a new part.

Remarks

You will typically use setDestination in the Target Control / TargetCtrl .

If you send a PickAndPlace robot to a station with the method setDestination , the MUs on this station are unblocked as follows:

- First a already waiting MU is unblocked for which the PickAndPlace robot was requested.
- If this is not the case, the Pull Control is called, if it exists.
- If both of the above is not the case, the MU in the Blocking List is unblocked that was scheduled first.

Type

Method

Syntax

```simtalk
< Path >.setDestination(DestinationObject:any[, WaitAtTarget:boolean]) < Path >.setDestination(DefaultPosition:void)
```

**Parameters**

- The parameter DestinationObject of data type any either designates the target object, or the target place on the target object, or a sensor on the target object.

This parameter can also be a MU or a storage place on a MU .

- The optional parameter WaitAtTarget of data type boolean sets, if the robot waits at the target station ( true ) or not ( false ).
- Provided the robot is empty , you can send it to its default position by entering setDestination(void) .

**Examples**

// set the target of the part if @.target = SP3 PickAndPlace.setDestination(@.target, false) else PickAndPlace.setDestination(@.target, true) end

print PickAndPlace.getDestination

// a target control with a sensor might, for example, look like this: if not ?.Empty if @.PreviousLocation = Conveyor ?.setDestination(Station, false) else ?.setDestination(Conveyor.Sensors.id2, false) end end

?.setDestination(MyStore[2,7])

MyPickAndPlace.setDestination(Conveyor.sensorID(1))

SimTalk

getDestination [SimTalk] - PickAndPlace

TargetCtrl [SimTalk] - PickAndPlace

See also

Target Control [PickAndPlace]

Empty [state, material flow objects]

setTimesTable [SimTalk]

Assigns a Times Table to the PickAndPlace robot designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.setTimesTable(TimesTable:table)

Parameter

The parameter TimesTable of data type table designates the name of the table.

You can enter these settings:

- The Names of all objects, which the PickAndPlace robot is to serve and the Default Angle to which the PickAndPlace robot moves after it has deposited the part.
- The Times above the diagonal are the times during which the PickAndPlace robot rotates empty . The times below the diagonal are the times during which the PickAndPlace robot rotates full, i.e., while a part is located on it. The diagonal in the table runs from the values in the topmost cell in the column default angle to the bottommost cell in the last column.

<!-- image -->

In the example above the cell labeled A contains the rotation time from the Source to the Station with picked-up parts, namely 0.5 seconds.

The cell labeled B contains the rotation time from the Drain to the Source without parts.

The cell labeled C contains the rotation time from Drain1 to the Default Angle without parts.

If you insert Connectors or if you drag an object onto the PickAndPlace robot and drop it there, Plant Simulation enters the respective values into the Times Table . For the calculation Plant Simulation assumes that a quarter-rotation requires takes up one second. You can change these times.

If you delete a Connector , Plant Simulation does not delete the entry of the now unconnected object from the Times Table . You have to delete the entry in the Angles Table , for example by right-clicking the respective row and selecting Delete Row on the context menu. When you click Apply in the dialog box of the PickAndPlace robot , Plant Simulation also deletes this entry from the Times Table .

**Example**

MyPickAndPlace.setTimesTable(myTimesTable)

SimTalk

getTimesTable [SimTalk]

See also

Times Table [PickAndPlace]

Angles Table [PickAndPlace]

Default Angle [PickAndPlace]

Empty [state, material flow objects]

**Read-Only Attributes of the PickAndPlaceRobot**

\_Read-Only Attributes of the PickAndPlaceRobot

The PickAndPlaceRobot provides:

- The read-only attributes listed in the table of contents to the left.
- The \_Read-Only Attributes of All Objects .
- The Read-Only Attributes of the Material Flow Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print PickAndPlaceRobot.GetCurrentAngle

##### GetCurrentAngle [SimTalk]

##### GetCurrentAngle [SimTalk]

Returns the current angle at which the PickAndPlace robot designated by &lt;Path&gt; is located.

Type

Read-only attribute

Syntax

&lt; Path &gt;.GetCurrentAngle → object

Return Value

The return value has the data type object .

Example

print PickAndPlace.GetCurrentAngle

##### GetLastDestination [SimTalk]

Returns the last target object where the PickAndPlace robot designated by &lt;Path&gt; deposited the part or picked up the part.

Type

Read-only attribute

Syntax

```simtalk
< Path >.GetLastDestination → object
```

Return Value

The return value has the data type object .

Example

```simtalk
print MyRobot.GetLastDestination // might
return .Models.MyRobot.Source
```

SimTalk

setDestination [SimTalk] - PickAndPlace

getDestination [SimTalk] - PickAndPlace

**IsLoading [SimTalk]**

##### IsLoading [SimTalk]

Returns if the PickAndPlace robot designated by &lt;Path&gt; is in the state loading at the moment (true) or not (false).

Remarks

Use IsLoading to observe the beginning and the end of the Loading Time .

IsLoading is required to ensure the correct unloading of a Container/Transporter if you entered a Loading Time .

Type

Read-only attribute

Syntax

```simtalk
< Path >.IsLoading → boolean
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type boolean .

Examples

print PickAndPlace.IsLoading

```simtalk
param SensorID: integer, Front: boolean, BookPos: boolean
var MU : object
@.Stopped  := true // stop
var Destination:object := Robot
MU := @.Cont
MU.Destination := Drain
if not MU.move(Destination)
	stopuntil MU.Location /= @ and not Destination.IsLoading
end
@.Stopped := false
```

**SimTalk**

LoadingTime [SimTalk] - PickAndPlace

**See also**

Loading Time [PickAndPlace]

##### IsRotating [SimTalk]

IsRotating [SimTalk]

Returns if the PickAndPlace robot designated by &lt;Path&gt; is rotating at the moment (true) or not (false).

Type

Read-only attribute

Syntax

```simtalk
< Path >.IsRotating → boolean
```

Return Value

The return value has the data type boolean .

Example

print PickAndPlace.IsRotating StatRotationEmptyPortion [SimTalk] - PickAndPlace Returns the portion of the statistics collection period during which the PickAndPlace robot designated by &lt;Path&gt; was rotating empty , i.e., without transporting a part.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatRotationEmptyPortion → real

Return Value

The return value has the data type real .

Example

print MyPickAndPlace.StatRotationEmptyPortion

See also

Tab Statistics [PickAndPlace]

Statistics report , Rotation Time

Empty [state, material flow objects]

StatRotationEmptyTime [SimTalk] - PickAndPlace

Returns the total time during which the PickAndPlace robot designated by &lt;Path&gt; was rotating empty , i.e., without transporting a part.

Type

Read-only attribute

Syntax

< Path >.StatRotationEmptyTime → time

Return Value

The return value has the data type time .

Example

print MyPickAndPlace.StatRotationEmptyTime

See also

Statistics report , Rotation Time

Empty [state, material flow objects]

##### StatRotationLoadedPortion [SimTalk] - PickAndPlace

Returns the portion of the statistics collection period during which the PickAndPlace robot designated by &lt;Path&gt; was rotating while transporting a part.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatRotationLoadedPortion → real

Return Value

The return value has the data type real .

Example

print MyPickAndPlace.StatRotationLoadedPortion

See also

Tab Statistics [PickAndPlace]

Statistics report , Rotation Time StatRotationLoadedTime [SimTalk] - PickAndPlace Returns the total time during which the PickAndPlace robot designated by &lt;Path&gt; was rotating while transporting a part.

Type

Read-only attribute

Syntax

< Path >.StatRotationLoadedTime → time

Return Value

The return value has the data type time .

Example

```simtalk
print MyPickAndPlace.StatRotationLoadedTime
```

See also

Statistics report , Rotation Time

#### Attributes of the PickAndPlace Robot

\_Attributes of the PickAndPlace Robot

The PickAndPlace robot provides:

- The attributes listed in the table of contents to the left.
- The Attributes of All Objects .
- The Attributes of the Material Flow Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyPickAndPlace.Capacity := 12
print MyPickAndPlace.TimeFactor
posit := MyStation.Cont.XPos
```

##### BlockingAngle [SimTalk]

BlockingAngle [SimTalk]

Sets the Blocking Angle of the PickAndPlace robot designated by &lt;Path&gt;.

Remarks

The Blocking Angle is the angle in degrees which the PickAndPlace robot cannot cross. It prevents the robot from taking the shortest way.

The Blocking Angle only affects the animation, the simulation is controlled by the rotation times which you defined in the Times Table .

Type

Attribute

Syntax

&lt; Path &gt;.BlockingAngle:real

Assignment Value

You can assign a value of data type real .

You can specify an angle between 0 and 360 degrees.

The default setting -1 means that no blocking angle applies and that the robot thus takes the shortest way.

Example

MyPickAndPlace.BlockingAngle := 5

See also

Blocking Angle [text box]

Times Table [PickAndPlace]

Capacity [SimTalk] - PickAndPlace

Sets the Capacity of the PickAndPlace robot designated by &lt;Path&gt;.

Remarks

The Capacity is the number of MUs that the PickAndPlace robot can transport at any one time.

The capacity enables the PickAndPlace robot to transport more than one part at the same time. It might, for example, pick up a number of bottles and place same into the appropriate slots of a bottle crate one at a time (FIFO).

If you want to unload the parts according to another rule, for example LIFO, you can program this in an Exit Control .

Type

Attribute

Syntax

```simtalk
< Path >.Capacity:integer
```

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type integer .

You can specify a value greater than 1 .

Example

```simtalk
MyPickAndPlace.Capacity := 12
```

See also

Capacity [text box] - PickAndPlace DefaultAngle [SimTalk] - PickAndPlace Sets the Default Angle of the PickAndPlace robot designated by &lt;Path&gt;.

Remarks

The Default Angle is the rotation angle in degrees to which the side of the end point of the PickAndPlace robot rotates when you set GoToDefaultPosition to true .

To rotate the PickAndPlace robot to the side on which the start point is located, add 180° to this angle.

**Note**

The Default Angle is also used as the start position after a Reset , no matter if Go to Default Position is activated or not.

Type

Attribute

Syntax

```simtalk
< Path >.DefaultAngle:real
```

Assignment Value

You can assign a value of data type real .

Specify a value between 0 ° and 360 °.

Example

```simtalk
MyPickAndPlace.DefaultAngle := 5
```

SimTalk

GoToDefaultPosition [SimTalk] - PickAndPlace

See also

Default Angle [PickAndPlace]

##### GoToDefaultPosition [SimTalk] - PickAndPlace

Rotates the PickAndPlace robot designated by &lt;Path&gt; back to its default position when it has deposited the part ( true ) or not ( false ).

Remarks

**Note**

When you set the attribute to true , the PickAndPlace robot uses the attribute DefaultAngle , when you reset the model.

The attribute DefaultAngle sets the actual Default Angle .

Type

Attribute

Syntax

&lt; Path &gt;.GoToDefaultPosition:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyPickAndPlace.GoToDefaultPosition := true

SimTalk

DefaultAngle [SimTalk] - PickAndPlace

See also

Go to Default Position [check box] - PickAndPlace

Default Angle [PickAndPlace]

LoadingTime [SimTalk] - PickAndPlace

Sets the Loading Time which the PickAndPlace robot designated by &lt;Path&gt;uses for picking up a part at a station.

Remarks

The Loading Time is the time it takes the PickAndPlace robot for picking up a part at a station.

- If the delivering station is a point-oriented object, the part is booked on the PickAndPlace robot while it picks it up. The delivering station is locked until the loading time has elapsed.
- If the delivering station is a length-oriented object, the part remains on the delivering station during the loading time and is then moved on to the PickAndPlace robot .

**Note**

Behavior during interruptions of the PickAndPlace robot

Plant Simulation extends the loading time by interruption times of the PickAndPlace robot . The delivering station remains locked during the interruption.

**Note**

Behavior during interruptions of the delivering station .

Interruptions of the delivering station do not affect loading the part by the PickAndPlace robot . The loading operation continues while the interruption lasts.

**Note**

The entrance of the PickAndPlace robot is open while its Loading Time is running. The entrance is closed once the part is actually moved on. The PickAndPlace robot opens the entrance again after the Unloading Time has passed.

Type

Attribute

Syntax

&lt; Path &gt;.LoadingTime:time

Assignment Value

You can assign a value of data type time .

**Examples**

MyPickAndPlaceRobot.LoadingTime := 1:00

MyPickAndPlaceRobot.LoadingTime.setTypeAndAttr("Normal",30,10)

**See also**

Loading Time [PickAndPlace]

LoadingTime . Type [SimTalk] - distribution parameter

IsLoading [SimTalk]

putAttributeNamesIntoTable [SimTalk] - distributions

##### MUConveyingDirection [SimTalk]

Sets the conveying direction of the MU on the PickAndPlace robot designated by &lt;Path&gt;.

**Remarks**

For the settings Retain , Rotate by 90° to the right , Rotate by 90° to the left , and Rotate by 180° the PickAndPlace robot executes a relative rotation depending on the direction from which the MU arrives.

For the settings Forwards , Lateral right , Backwards , and Lateral left the rotation is an absolute rotation independent of the direction from which the MU arrives.

<!-- image -->

| Conveying direction     | executes                                                                                                           | looks like this in 2D   | looks like this in 3D   |
|-------------------------|--------------------------------------------------------------------------------------------------------------------|-------------------------|-------------------------|
| Retain                  | The robot continues conveying the part in the same direction in which it arrives.                                  |                         |                         |
| Rotate 90° to the right | The robot rotates the part 90° to the right and places it on the successor.                                        |                         |                         |
| Rotate 90° to the left  | The robot rotates the part 90° to the left and places it on the successor.                                         |                         |                         |
| Rotate 180°             | The robot rotates the part 180° and places it on the successor.                                                    |                         |                         |
| Forwards                | The robot rotates the part, so that it comes to rest on the successor forward and then places it on the successor. |                         |                         |

<!-- image -->

| Conveying direction   | executes                                                                                                                          | looks like this in 2D   | looks like this in 3D   |
|-----------------------|-----------------------------------------------------------------------------------------------------------------------------------|-------------------------|-------------------------|
| Lateral right         | The robot rotates the part, so that it comes to rest on the successor laterally to the right and then places it on the successor. |                         |                         |
| Backwards             | The robot rotates the part, so that it comes to rest on the successor backward and then places it on the successor.               |                         |                         |
| Lateral left          | The robot rotates the part, so that it comes to rest on the successor laterally to the left and then places it on the successor.  |                         |                         |

**Type**

Attribute

Syntax

&lt; Path &gt;.MUConveyingDirection:string

**Assignment Value**

You can assign a value of data type string .

You can specify "Retain" , "Rotate 90° to the right" , "Rotate 90° to the left" , "Rotate 180°" , "Forwards" , "Lateral right" , "Backwards" , or "Lateral left" .

**Example**

```simtalk
MyPickAndPlace.MUConveyingDirection := "Forwards"
```

**See also**

MU Conveying Direction [drop-down list]

##### OnlyForEmptyBlockingList [SimTalk]

Only rotates the PickAndPlace robot designated by &lt;Path&gt; back to its default position, when its blocking list is empty ( true ), i.e., when no additional requests are registered for it, or not ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.OnlyForEmptyBlockingList:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyPickAndPlace.OnlyForEmptyBlockingList := true

See also

Go to Default Position [check box] - PickAndPlace

##### PullCtrl [SimTalk] - PickAndPlace

Designates a Method object of the object designated by &lt;Path&gt;.

**Remarks**

Plant Simulation runs the Pull Control whenever the PickAndPlace robot is ready to pick up a new part or when it is ready when a new MU is Waiting at its entrance.

If you set TargetSelection to "Load part onto MU at sensor" the PickAndPlace robot only counts as ready if a Container/Transporter is waiting at the sensor . This also applies if you programmed a Pull Control . It will only be called when a Container/Transporter is waiting at the sensor .

In the Pull control you can determine which of the parts, which intends to move onto the object, the PickAndPlace robot will accept. For this you have to get the forward blocking list of the object with the method fwBlockList and unblock a MU in the list with the method unblock .

Let us assume that red parts are especially important and thus have priority for being processed. Then you can always pull red parts first from the predecessors and only then pull parts in other colors.

**Note**

The pull control does not determine if a MU is to be moved to this or to another successor. Instead, it selects one of the parts which have already been determined to move on to this successor.

**Note**

For the objects Conveyor , Track , and TwoLaneTrack the Pull Control only applies to MUs moving in the forward direction, i.e., to objects, which move onto them at their entrance and exit them at their exit . It does not apply to MUs moving onto them backward at their exit and not to MUs that have been moved to a certain position.

Type

Attribute

Syntax

&lt; Path &gt;.PullCtrl:method

**Assignment Value**

You can assign a value of data type method .

**Example**

MyPickAndPlace.PullCtrl := &amp;myPullControl

**See also**

Pull Control [PickAndPlace]

##### TargetCtrl [SimTalk] - PickAndPlace

Designates a Method object of the object designated by &lt;Path&gt;.

**Remarks**

Plant Simulation runs the Target Control as soon as the PickAndPlace robot designated by &lt;Path&gt; has completely picked up the part. In this control you determine the successor onto which the PickAndPlace robot deposits the part.

As opposed to the exit control , the part is not ready to exit the object yet. You have to set the target object in the method setDestination .

Plant Simulation also calls the control when the PickAndPlace robot has deposited the part. In this case you have to set the object, at which the robot is going to pick up the next part with the method setDestination .

When the PickAndPlace robot calls the Target Control after depositing the part, the active element ( @ ) is void.

Plant Simulation only calls the Target Control while unloading if you cleared the check box Go to Default Position .

<!-- image -->

Type

Attribute

Syntax

< Path >.TargetCtrl:method

Assignment Value

You can assign a value of data type method .

Examples

```simtalk
if ?.empty
	return
end
if @.LastStation = Source
```

**TargetCtrl [SimTalk] - PickAndPlace**

?.setDestination(Drain) ?.setDestination(Station, true)

```simtalk
elseif @.LastStation = Source1
else
	?.setDestination(Drain1)
end
MyPickAndPlace.TargetCtrl := &myTargetControl
```

**SimTalk**

setDestination [SimTalk] - PickAndPlace

See also

Target Control [PickAndPlace]

##### TargetObject [SimTalk]

Designates the length-oriented Target Object at which the PickAndPlace robot designated by &lt;Path&gt; places or loads the part.

Type

Attribute

Syntax

&lt; Path &gt;.TargetObject:path

Assignment Value

You can assign a value of data type path .

Example

MyPickAndPlace.TargetObject := .Models.MyModel.Conveyor

See also

Target Object TargetSelection [SimTalk]

Sets how the PickAndPlace robot designated by &lt;Path&gt; selects the target for the part that is to be moved:

Type

Attribute

Syntax

&lt; Path &gt;.TargetSelection:string

Assignment Value

You can assign a value of data type string .

You can specify:

- "Exit strategy or target control" : Default behavior of previous versions of the PickAndPlace robot . You either set the target with the selected Exit Strategy or you define the target in the Target Control .
- "Load part onto MU at sensor" : For this setting you have to manually create a front-triggered sensor with light-barrier mode on the length-oriented target object. In addition you have to enter the Target Object and the Target sensor ID . Stopping the Container/Transporter , loading and sending the Container/Transporter on only works automatically if you did not enter a control. If you use a control, you have to program stopping and sending the Container/Transporter on in this control.

**Note**

The PickAndPlace robot only picks the part to be loaded up at the sensor when a Container/ Transporter is waiting at the sensor .

This also applies if you programmed a PullCtrl . It will only be called when a Container/Transporter is waiting at the sensor .

- "Place part at sensor" : For this setting you have to manually create a rear-triggered sensor with light barrier mode on the length-oriented target object. In addition you have to enter the Target Object and the Target Sensor ID .

Example

```simtalk
MyPickAndPlace.TargetSelection := "Load part onto MU at sensor"
```

See also

Target Object Target Control [PickAndPlace] Target Object Target Sensor ID [text box]

TargetSensorID [SimTalk]

Sets the sensor ID of the target object at which the PickAndPlace robot designated by &lt;Path&gt; places or loads the part.

Remarks

Plant Simulation does not create the sensor automatically. You have to create it manually or with the method createSensor .

Type

Attribute

Syntax

&lt; Path &gt;.TargetSensorID:integer

Assignment Value

You can assign a value of data type integer .

Example

MyPickAndPlace.TargetSensorID := 2

See also

createSensor [SimTalk] - material flow objects

Target Sensor ID [text box]

TimeFactor [SimTalk]

Sets the Time Factor with which all times in the Times Table of the PickAndPlace robot designated by &lt;Path&gt; are multiplied.

Remarks

The Time Factor enables to simulate the robot with different speeds without having to manually change the times in the table.

Type

Attribute

Syntax

&lt; Path &gt;.TimeFactor:real

Assignment Value

You can assign a value of data type real .

Example

```simtalk
MyPickAndPlace.TimeFactor := 5
```

See also

Time Factor [PickAndPlace]

Times Table [PickAndPlace]

UnloadingTime [SimTalk] - PickAndPlace

Sets the Unloading Time of the PickAndPlace robot designated by &lt;Path&gt;.

Remarks

The Unloading Time is the time it takes the PickAndPlace robot for placing the part, which it picked up at another station, onto target station.

- If the target station is a point-oriented object , the part is booked on the PickAndPlace robot while it places it. The target station is locked until the unloading time has elapsed.
- If the target station is a point-oriented object , the part is moved on to the length-oriented object before the unloading time starts.

**Note**

Behavior during interruptions of the PickAndPlace robot .

Plant Simulation extends the unloading time by interruption times of the PickAndPlace robot . The target processing station remains locked during the interruption .

**Note**

Behavior during interruptions of the target station .

Interruptions of the target station do not affect unloading the part by the PickAndPlace robot . The unloading operation continues while the interruption lasts.

**Note**

The entrance of the PickAndPlace robot is open while its Loading Time is running. The entrance is closed once the part is actually moved on. The PickAndPlace robot opens the entrance again after the Unloading Time has passed.

Type

Attribute

Syntax

&lt; Path &gt;.UnloadingTime:time

Assignment Value

You can assign a value of data type time .

**Examples**

MyPickAndPlaceRobot.UnloadingTime := 1:00

MyPickAndPlaceRobot.UnloadingTime.setTypeAndAttr("Normal",30,10)

See also

Unloading Time [PickAndPlace]

UnloadingTime . Type [SimTalk] - distribution parameter

IsLoading [SimTalk]

putAttributeNamesIntoTable [SimTalk] - distributions

##### WaitForFreeTarget [SimTalk] -PickAndPlace

Sets if the PickAndPlace robot designated by &lt;Path&gt; only rotates to a part that wants to exit the predecessor, to pick it up if the destination object is ready to accept it ( true ).

Remarks

Specify false to make the PickAndPlace robot rotate to the part immediately.

Plant Simulation only evaluates WaitForFreeTarget for the setting Target Selection &gt; Exit strategy or target control .

<!-- image -->

Plant Simulation enters the part that cannot be transported into the Exit Blocking List of the target object.

**Note**

If you set the attribute to true , Plant Simulation already evaluates the entered Exit Strategy or the Target Control for the part before the PickAndPlace robot rotates to the part to pick it up.

Plant Simulation enters the thus determined target into the attribute TargetObject .

Type

Attribute

Syntax

&lt; Path &gt;.WaitForFreeTarget:boolean

Assignment Value

You can assign a value of data type boolean .

**Example**

MyPickAndPlace.WaitForFreeTarget := true

SimTalk

ReservedFor [SimTalk]

ReservedPlace [SimTalk] of the MUs

contentsAndReservedList [SimTalk]

TargetSelection [SimTalk]

See also

Wait for Free Target [PickAndPlace]

Target Selection [drop-down list]

