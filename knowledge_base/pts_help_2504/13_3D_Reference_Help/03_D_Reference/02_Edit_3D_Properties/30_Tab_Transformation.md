#### Tab Transformation

Transformation [3D object]

Define settings for the position, settings for the rotation, settings for mirroring, and settings for the scale on the tab Transformation .

To do so, you can type a value into the text boxes or click in them and roll the mouse wheel. The settings allow you exact control, as compared to modifying the position, the angle of rotation, and the scale of the object in the scene window with the mouse.

For the MUs you can also select if you want to scale them automatically or not.

Note

Not all objects provide all of the settings described below.

<!-- image -->

- To apply and show your changes of the settings to the selected object in the scene window, click Apply .
- To apply your changes of the settings to the selected object and close the dialog, click OK .
- To close the dialog without applying any of the settings you modified, click Cancel .

SimTalk

TransformationMatrix [SimTalk]

**\_3D.TransformationMatrix [SimTalk]**

See also

Move an Object Precisely

Video on YouTube

[https://youtu.be/jHOZhlwGhkQ?si=w6CVq7d2pTyd5ctO&amp;t=66](https://youtu.be/jHOZhlwGhkQ?si=w6CVq7d2pTyd5ctO&t=66)

Settings for the Position

Settings for the Position [transformation]

To set the Position of the selected object on the x-axis, the y-axis and the z-axis type in the respective values.

<!-- image -->

- Type a value into the respective text box.
- Hover over the respective text box and roll the mouse wheel to increase or decrease the position by 0.1 meters.
- Hover over the respective text box, hold down Ctrl , and roll the mouse wheel to increase or decrease the position by 0.01 meters.

**Note**

The settings for the three axes are independent of each other.

For MU instances the settings for the position show the local positions computed by the animation.

In a 2D and 3D model you can, in addition, set with the check box Connect 2D and 3D Positions if the position of the object in the 2D part of the simulation model matches the position of the respective object in the 3D part.

SimTalk

\_3D.Position [SimTalk]

Position [SimTalk] - graphic

\_3D.StatesPosition [SimTalk]

See also

importGraphics [SimTalk]

Move to Zero

Connect 2D and 3D Positions

###### Move to Zero

To move the selected grouped graphic (with the center of its base area) to the point of origin of the object it belongs to, click this button.

<!-- image -->

This is especially handy when you import graphics, such as .WRL files, which 3D might not place at the position you expected.

The setting also applies to JtTriStripSets . These are graphic nodes which do not have any child nodes and which often originate from imported graphics.

<!-- image -->

<!-- image -->

**See also**

\_3D.Position [SimTalk]

importGraphics [SimTalk]

Position [SimTalk] - graphic

###### Connect 2D and 3D Positions

To match the position of the object in the 2D part of the simulation model with the position of the respective object in the 3D part, select this check box.

<!-- image -->

Note

A 3D Only model does not provide the setting Connect 2D and 3D Positions .

The example illustrates this:

- Insert a Station into the Frame into the 3D part of a simulation model. Plant Simulation automatically inserts the Station into the Frame in its part of the model.

**Note**

Plant Simulation maps the x-y coordinates of the 3D object to the respective position of the Station in the Frame in the Plant Simulation simulation model. Expert users can edit how coordinates are mapped with the function real time scaling in the Plant Simulation Frame .

- Select Connect 2D and 3D Positions . If you move the Station in the 3D part of the model now, the Station in the Plant Simulation part of the model also moves to a position that matches the position of the Station in the 3D window. The position of the object in Plant Simulation will be coupled to the position of the object in the 3D window until you clear the check box again!

See also

\_3D.PositionsConnected [SimTalk]

Use Identical Lengths and Positions in 2D and in 3D

Settings for the Rotation

Settings for the Rotation [transformation]

To set the axis around which to rotate the object, type in a value for each of the three components (x-y-z) that define the rotation axis.

**Note**

The settings for the three axes are independent of each other.

<!-- image -->

Instead, you can also click this button to the right of the respective axis to set the rotation axis. Plant Simulation then enters the respective values into the text boxes.

Type the angle of rotation in degrees into the text box.

Inheritance

<!-- image -->

The inheritance check box turns inheritance of the Rotation settings off or on.

- A green check box means that inheritance is turned on. Then the object inherits, i.e., uses, settings of the parent object from which it was derived. When you change the settings of the parent object, Plant Simulation also changes the respective settings of the child object.
- An orange check box with a minus means that inheritance is turned off.

<!-- image -->

In a 2D and 3D model you can, in addition, set with the check box Connect 2D and 3D Rotations if the rotation of the object in the Plant Simulation part of the simulation model is synchronized with the rotation of the respective object in the 3D part of the model.

When you set the rotation of a MU in 2D, Plant Simulation transmits it immediately to 3D and vice versa.

SimTalk

\_3D.Rotation [SimTalk]

3D.getGraphic(...).Rotation

See also

Connect 2D and 3D Rotations

Add Rotation

Rotate an Object with Keyboard Keys

Use Rotation of Marker [check box]

###### Connect 2D and 3D Rotations

To match the rotation of the object in the Plant Simulation part of the simulation model with the rotation of the respective object in the 3D part, select this check box.

<!-- image -->

Note

A 3D only model does not provide the setting Connect 2D and 3D Positions .

The example illustrates this:

- Insert a Station into the Frame into the 3D part of a simulation model. Plant Simulation automatically inserts the Station into the Frame in its part of the model.

**Note**

Plant Simulation maps the x-y coordinates of the 3D object to the respective position of the Station in the Frame in the Plant Simulation simulation model. Expert users can edit how coordinates are mapped with the function real time scaling in the Plant Simulation Frame .

- Select Connect 2D and 3D Rotations . If you move the Station in the 3D part of the model now, the Station in the Plant Simulation part of the model also moves to a rotation that matches the rotation of the Station in the 3D window. The rotation of the object in Plant Simulation will be coupled to the rotation of the object in the 3D window until you clear the check box again!

See also

\_3D.RotationsConnected [SimTalk]

Use Identical Lengths and Positions in 2D and in 3D

###### Add Rotation

To add a rotation angle to the axis that you select, click this button.

<!-- image -->

<!-- image -->

Type in the Angle which you would like to add to the Axis that you select.

Select the Axis to which you would like to add the Angle .

Click OK to accept the values and to add the angle to the existing Angle .

Click Cancel to cancel your changes and to close the dialog.

**Settings for Mirroring**

##### Settings for Mirroring

Select the respective check box to mirror/flip the selected object on this plane.

<!-- image -->

<!-- image -->

| Setting      | Description                         | Looks like this   |
|--------------|-------------------------------------|-------------------|
| Not mirrored | Does not mirror the object.         |                   |
| YZ plane     | Mirrors the object on the YZ plane. |                   |
| XZ plane     | Mirrors the object on the XZ plane. |                   |
| XY plane     | Mirrors the object on the XY plane. |                   |

If your model also has a 2D part, the object will be mirrored there as well.

When you set mirroring of a MU in 2D, Plant Simulation transmits it immediately to 3D and vice versa.

Inheritance

The inheritance check box turns inheritance of the Mirror settings off or on.

- A green check box means that inheritance is turned on. Then the object inherits, i.e., uses, settings of the parent object from which it was derived. When you change the settings of the parent object, Plant Simulation also changes the respective settings of the child object.
- An orange check box with a minus means that inheritance is turned off.

SimTalk

**\_3D.Mirror [SimTalk]**

Settings for the Scale

Settings for the Scale [transformation]

Select settings for scaling the object.

You can:

- Select Uniform Scaling of the object.
- Set the Dimensions of the scaled object.

<!-- image -->

Inheritance

<!-- image -->

<!-- image -->

###### Settings for the Scale [transformation]

The inheritance check box turns inheritance of the Scale settings off or on.

- A green check box means that inheritance is turned on. Then the object inherits, i.e., uses, settings of the parent object from which it was derived. When you change the settings of the parent object, Plant Simulation also changes the respective settings of the child object.
- An orange check box with a minus means that inheritance is turned off.

SimTalk

- \_3D.Scale [SimTalk]
- \_3D.getGraphic(...).Scale
- \_3D.StatesScale [SimTalk]

###### Uniform Scaling

To apply uniform scaling , accept the default setting.

This setting automatically enters the value you entered into one text box into the remaining two text boxes for scaling the object.

This way you do not have to manually enter the same value into each text box over again.

<!-- image -->

<!-- image -->

To scale the object on each axis separately, clear Uniform . You can set the three components (x,y,z) with which the object is going to be scaled as follows:

<!-- image -->

- To scale the object by 0.1 meters, hover over the respective text box and roll the mouse wheel.

**Uniform Scaling**

- To scale the object by 0.01 meters, hover over the respective text box, hold down Ctrl , and roll the mouse wheel.
- Type in a value into the respective text box.

You can only specify positive values. Typing in 0.5 , for example, halves the size of the object on the respective axis. Typing in 2.0 doubles its size on the respective axis.

See also

**Set Dimensions**

###### Set Dimensions

To open a dialog in which you can set the dimensions of the scaled graphic of the object, click this button.

<!-- image -->

Then type in the physical size of the scaled object considering the graphics of the object.

<!-- image -->

**Note**

Plant Simulation shows this button for all simulation objects and for all non-length-oriented animatable objects.

- Type in the Dimension of the scaled graphic of the object in the X-Direction .
- Type in the Dimension of the scaled graphic of the object in the Y-Direction .
- Type in the Dimension of the scaled graphic of the object in the Z-Direction .

<!-- image -->

**Set Dimensions**

The following objects do not provide the feature Set Dimensions :

- Part , Container , Transporter , and Worker
- Connector , Interface , and Marker
- Length-oriented objects
- Store
- Variable , Comment , Button , DropDownList , Checkbox , and Display

**SimTalk**

\_3D.Dimensions [SimTalk] - simulation object

##### Scale Automatically

To adjust the size and positioning of the graphic of the MU to the measurements and the booking point length and the booking point width of the MU in 2D, select this check box. 3D then hides the settings for scaling the MU .

Plant Simulation automatically applies size changes of automatically scaled MUs after each modification to all visible inheriting classes and instances of the MU . For this reason Apply Changes on the Edit ribbon tab is unavailable.

<!-- image -->

To set the scaling of the MU yourself, clear the check box and select the settings for scaling .

<!-- image -->

Scale Automatically also affects the Booking Point Height . Plant Simulation only applies the changed booking point height after you cleared Scale Automatically .

**Scale Automatically**

Inheritance

<!-- image -->

The inheritance check box turns inheritance of the Scale settings off or on.

- A green check box means that inheritance is turned on. Then the object inherits, i.e., uses, settings of the parent object from which it was derived. When you change the settings of the parent object, Plant Simulation also changes the respective settings of the child object.
- An orange check box with a minus means that inheritance is turned off.

SimTalk

\_3D.ScaleAutomatically [SimTalk]

See also

Booking Point Length [general description]

Booking Point Width [general description]

Settings for the Scale [transformation]

Undo [3D]

Redo [3D]

