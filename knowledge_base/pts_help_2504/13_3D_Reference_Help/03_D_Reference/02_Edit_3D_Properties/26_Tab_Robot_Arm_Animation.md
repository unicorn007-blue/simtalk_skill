#### Tab Robot Arm Animation

Robot Arm Animation

Create the path on which the arm of the PickAndPlace robot will be animated on the tab Robot Arm Animation .

**Note**

The settings are only active when the PickAndPlace Robot is connected with a predecessor and a successor. The connected objects are then shown in the list below Animation paths .

<!-- image -->

The visualization of this path connects the anchor points with straight lines while the actual movement of the robot arm is put together with curves. This is different from all other path visualizations which accurately show how, for example, a MU will be moved.

When you type in a path for the combination of start and destination of the robot arm, the robot follows this path when moving from the start to the destination of the movement. This way you can set accurate movements, for example to animate raising and lowering motions, or to circumvent obstacles. If you do not type in a user-defined animation path, the robot runs the default animation, namely a simple raising or lowering motion to make the animation appear more realistic.

<!-- image -->

The animation of the robots in 3D is independent of specially set animation rotation axes. In most cases the angles from the Angles Table do not affect the animation in 3D. The only exception to this is that the moving times of the robot are mostly computed based on the angles from the Angles Table . In some cases the robot might then jump from the default angle to an object or from an object to the default angle when both angles are identical according to the Angles Table .

You can add , extend , edit , and delete animation paths .

Configure the Movement of the Robot Arm shows how to set robot arm animations.

See also

Animate the Robot Arm in 3D

Configuring the Robot with Drag-and-Drop

Configuring the Robot in 3D

- \_\_Accessing Robot Arm Animations
- \_3D.RobotArmAnimations.setTable [SimTalk]
- \_3D.RobotArmAnimations.getTable [SimTalk]

Video on YouTube

[https://youtu.be/K-NEPvShU10?si=4xa\_eEM-5p39BgvU&amp;t=223](https://youtu.be/K-NEPvShU10?si=4xa_eEM-5p39BgvU&t=223)

##### Animation paths

###### Animation Paths [robot arm]

You can:

- Add a new animation path of the robot arm.
- Extend an existing animation path of the robot arm.
- Edit an existing animation path of the robot arm.
- Delete an existing animation path of the robot arm.

**Note**

If you do not define a path, the robot runs a standard animation, namely a simple raising or lowering motion which makes the animation look more realistic.

See also

Work with Animation Paths

Animate the Robot Arm in 3D

Add

Add [button] - robot arm animation

To Add a new robot arm animation path, click this button.

<!-- image -->

You can only add animation paths when the Robot is connected with a predecessor and a successor with Connectors .

Select a Path in the dialog Create Animation Path .

**Path [robot arm animation]**

**Path [robot arm animation]**

Select one of the provided animation paths.

They show the connections via Connectors from the predecessor of the Robot and from the Robot to its successor in the model.

<!-- image -->

###### Extend [robot arm animation]

To add a new anchor point to the animation path, thus making it longer, click this button.

<!-- image -->

Then click the left mouse button at the position, where you would like to insert the anchor point. Repeat this as often as needed.

To terminate Extend animation path mode, click the right mouse button.

You can only navigate in Extend animation path mode with the middle and the right mouse button if you hold down the Ctrl+Alt keys.

**Note**

The visualization of this path connects the anchor points with straight lines, although the actually covered movement of the robot arm consists of curves. This differs from all other path visualizations, which exactly show how, for example, a MU will be moved.

###### Edit

**Edit [button] - robot arm animation**

To edit the anchor points of the selected animation path of the robot arm, click this button.

<!-- image -->

<!-- image -->

You can:

- Add a new anchor point.
- Insert a new anchor point before the selected anchor point.
- Delete the selected anchor point.
- Move the selected anchor point up one position in the list up or down one position in the list.
- Duplicate the selected anchor point.
- Edit the values of the selected anchor point or double-click the row of the anchor point, whose values you want to change, in the list.
- Add a Common Offset to the selected anchor point.

**Add [button] - anchor point, robot arm**

To add a new anchor point to the path, click this button.

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

Duplicate

<!-- image -->

To duplicate the settings of the selected anchor point and to insert the duplicate below the original in the list, click this button.

**Edit Values [button] - anchor point, robot arm**

To edit the values of the anchor point which you selected in the list, click this button.

<!-- image -->

Instead, you can also double-click the row of the anchor point, whose values you want to change, in the list.

Add Common Offset [button] - anchor point, robot arm

To add a common offset to the selected anchor point of the path, click this button.

<!-- image -->

Type a value for the position into the text box, or roll the mouse wheel to add a common offset to the position of the selected anchor point on the x-axis, the y-axis, and the z-axis. The settings for the three axes are independent of each other.

###### Delete [button] - anchor point, robot arm

To delete the selected anchor point of the path, click this button.

<!-- image -->

