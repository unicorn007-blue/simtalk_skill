### Accessing Robot Arm Animations

#### \_\_Accessing Robot Arm Animations

SimTalk provides the methods listed in the table of contents to the left for robot arm animations in 3D .

You can buffer the entirety or all animations of a type in a value of data type any , for example:

var a : any := .PickAndPlace.\_3D.RobotArmAnimations

#### \_3D.RobotArmAnimations.getTable [SimTalk]

Returns the existing Robot Arm Animations data of the object designated by &lt;Path&gt; and writes it into the passed table.

Remarks

Plant Simulation automatically formats the passed table.

Type

Method

Syntax

```simtalk
< Path >._3D.RobotArmAnimations.getTable(Animations:table)
```

**Parameter**

The parameter Animations of data type table designates the table which contains the robot animations. The table has three columns:

- The column From of data type string indicates at which object a robot arm animation starts. It designates the default orientation as starting point if the cell is empty.
- The column To of data type string indicates to which object a robot arm animation moves. It designates the default orientation as the destination if the cell is empty.
- The column Table of data type table indicates the robot arm animation path.

It is a subtable with three columns of data type length for the X, Y, and Z values of all coordinates which the robot is to pass on its route from the From position to the To position within the coordinate system of the robot.

**Example**

```simtalk
var t : table
PickAndPlace1._3D.RobotArmAnimations.getTable(t)
PickAndPlace2._3D.RobotArmAnimations.setTable(t)
```

**See also**

\_3D.RobotArmAnimations.setTable [SimTalk]

Edit 3D Properties [dialog] &gt; Robot Arm Animation

#### \_3D.RobotArmAnimations.setTable [SimTalk]

Sets the table that contains the Robot Arm Animations of the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >._3D.RobotArmAnimations.setTable(Animations:table
```

Parameter

The parameter Animations of data type table designates the table which contains the robot animations. The table has three columns:

- The column From of data type string indicates at which object a robot arm animation starts. It designates the default orientation as the starting point if the cell is empty.
- The column To of data type string indicates to which object a robot arm animation moves. It designates the default orientation as the destination if the cell is empty.
- The column Table of data type table indicates the robot arm animation &lt;Path&gt;.

It is a subtable with three columns of data type length for the X, Y, and Z values of all coordinates which the robot is to pass on its route from the From position to the To position within the coordinate system of the robot.

**Example**

```simtalk
var t : table
PickAndPlace1._3D.RobotArmAnimations.getTable(t)
PickAndPlace2._3D.RobotArmAnimations.setTable(t)
```

See also

**\_3D.RobotArmAnimations.getTable [SimTalk]**

Edit 3D Properties [dialog] &gt; Robot Arm Animation

