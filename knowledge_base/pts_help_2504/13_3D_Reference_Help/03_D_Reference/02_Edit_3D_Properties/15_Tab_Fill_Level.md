#### Tab Fill Level

Fill Level

The tab Fill Level provides settings for showing the fill level of a Buffer in 3D .

<!-- image -->

Show Contents As

Settings for the Position [Buffer]

Settings for the Rotation [Buffer]

Settings for the Dimensions

Inheritance

The inheritance check box turns inheritance of the Fill Level Settings off or on.

- A green check box means that inheritance is turned on. Then the object inherits, i.e., uses, settings of the parent object from which it was derived. When you change the settings of the parent object, Plant Simulation also changes the respective settings of the child object.
- An orange check box with a minus means that inheritance is turned off. The value you specify only applies to the setting of this object.

##### Fill Level

**See also**

Show Fill Level [check box] - Buffer

Check the Fill Level of the Buffers in the Plant

##### Show Contents As

Select how the Buffer Shows Its Contents .

<!-- image -->

**Note**

The fill level bar just shows a quantitative portion of the MUs located in the Buffer , not exact numbers.

<!-- image -->

| Item       | Description                                                                                                                                                                                                                                       | Looks like this   |
|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------|
| MUs        | Shows the MUs stacked in the Buffer . This was the setting in previous versions of Plant Simulation .                                                                                                                                             |                   |
| Fill level | Shows the relative fill level of the Buffer on its picture as a colored bar from left to right. Gray denotes the background of the fill level indicator. Red denotes a fill level of more than 90%. Orange denotes a fill level of less than 10%. |                   |

| Item   | Description                                               | Looks like this   |
|--------|-----------------------------------------------------------|-------------------|
| Both   | Shows the MUs stacked on top of the fill level indicator. |                   |

**SimTalk**

\_3D.ShowContentsAs [SimTalk]

- \_3D.FillLevelPosition [SimTalk]
- \_3D.FillLevelPosition [SimTalk]
- \_3D.FillLevelRotation [SimTalk]

See also

Check the Fill Level of the Buffers in the Plant

Video on YouTube

[https://youtu.be/t7hBJgNZpHE?si=Amm464yWN4w9RZcm&amp;t=1980](https://youtu.be/t7hBJgNZpHE?si=Amm464yWN4w9RZcm&t=1980)

##### Settings for the Position [Buffer]

To set the Position of the fill level display of the Buffer on the x-axis, the y-axis, and the z-axis within the coordinate system of the 3D window specify the respective settings.

<!-- image -->

- Type in a value into the respective text box.
- Hover over the respective text box and roll the mouse wheel to increase or decrease the position by 0.1 meters.
- Hover over the respective text box, hold down Ctrl , and roll the mouse wheel to increase or decrease the position by 0.01 meters.

**Note**

The settings for the three axes are independent of each other.

SimTalk

\_3D.FillLevelPosition [SimTalk]

Settings for the Rotation [Buffer]

Settings for the Rotation [Buffer]

To set the Axis around which to rotate the Buffer , specify a value for each of the three components (x-y-z) that define the rotation axis.

##### Settings for the Rotation [Buffer]

<!-- image -->

Instead, you can also click this button to the right of the axis to set the respective rotation axis. Plant Simulation then enters the respective values into the text boxes.

**Note**

The settings for the three axes are independent of each other.

Type in the Angle of rotation in degrees into the text box.

To add a rotation angle to the axis that you select, click Add Rotation .

SimTalk

\_3D.FillLevelRotation [SimTalk]

See also

Rotate an Object with Keyboard Keys

###### Add Rotation

To add a rotation angle to the axis that you select, click this button.

<!-- image -->

<!-- image -->

Type in the Angle which you would like to add to the Axis that you select.

Select the Axis to which you would like to add the Angle .

Click OK to accept the values and to add the angle to the existing Angle .

Click Cancel to cancel your changes and to close the dialog.

**Settings for the Dimensions**

##### Settings for the Dimensions

To set the Dimensions of the display area of the fill level specify the respective settings.

<!-- image -->

- Type in a value for the X-Dimension of the fill level display into the text box X .
- Type in a value for the Y-Dimension of the fill level display into the text box Y .

**You can also:**

- Hover over the respective text box and roll the mouse wheel to increase the size by 0.1 meters.
- Hover over the respective text box, hold down Ctrl , and roll the mouse wheel to increase the size by 0.01 meters.

**SimTalk**

\_3D.FillLevelPosition [SimTalk]

