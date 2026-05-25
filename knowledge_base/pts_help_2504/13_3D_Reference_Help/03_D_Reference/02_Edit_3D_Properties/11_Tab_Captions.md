#### Tab Captions

##### Captions

Captions in 3D encompass the Name and the Label of the objects which you or Plant Simulation assigned in 2D.

<!-- image -->

You can select to activate or deactivate the captions in 3D on the tab Captions . In addition, you can define Settings for the Position , Settings for the Rotation , and Settings for the Scale of the captions.

The check box Name/label activated turns inheritance of the position on or off. The value you specify only applies to the setting of this object.

<!-- image -->

To show or hide the Names of the objects in the Frame , click Show Object Names on the View

ribbon tab.

To show or hide the Labels of the objects in the Frame , click the small triangle and then Label

<!-- image -->

Captions , i.e., Names and Labels , are most useful for objects that are not simulation-relevant, like Methods , DataTables , etc.

<!-- image -->

Video on YouTube

[https://youtu.be/jHOZhlwGhkQ?si=39UHDy0ltkOUgcp6&amp;t=1374](https://youtu.be/jHOZhlwGhkQ?si=39UHDy0ltkOUgcp6&t=1374)

##### Name/Label Activated

To activate captions, which encompass the Name and the Label of the object, which you or Plant Simulation assigned in 2D, select the check box.

<!-- image -->

<!-- image -->

To deactivate captions, clear the check box.

Plant Simulation automatically converts underscores \_ in object names to spaces.

Plant Simulation shows underscores \_ in object labels as underscores.

The inheritance check box turns inheritance of the Captions settings on or off.

<!-- image -->

- A green check box means that inheritance is turned on. Then the object inherits, i.e., uses, settings of the parent object from which it was derived. When you change the settings of the parent object, Plant Simulation also changes the respective settings of the child object.
- An orange check box with a minus means that inheritance is turned off. The value you specify only applies to the setting of this object.

You can show or hide the Names and the Labels of all objects in the 3D model by clicking Show Object

<!-- image -->

**Note**

The settings Name/Label enabled in 3D and Show Object Names and Show Object Labels in the Frame in 2D are independent of each other.

**SimTalk**

**\_3D.NameLabelEnabled [SimTalk]**

See also

Show Object Names [View ribbon] - 3D

##### Settings for the Position [captions]

To set the Position of the captions of the selected object on the x-axis, the y-axis and the z-axis, type in the required settings.

- Type in a value into the respective text box.
- Hover over the respective text box and roll the mouse wheel to increase or decrease the position by 0.1 meters.
- Hover over the respective text box, hold down Ctrl , and roll the mouse wheel to increase or decrease the position by 0.01 meters.

**Note**

The settings for the three axes are independent of each other.

<!-- image -->

**Standard Position**

<!-- image -->

To move the captions, i.e., the Names and the Labels of the objects to their standard position, click this.

The standard position is the bottom left corner of the graphic bounding box of the caption.

SimTalk

\_3D.NameLabelPosition [SimTalk]

**Settings for the Rotation [captions]**

##### Settings for the Rotation [captions]

To set the axis around which to rotate the caption of the selected object, type in a value for each of the three components (x-y-z) that define the rotation axis around which the caption of the object rotates in the Frame .

**Note**

The settings for the three axes are independent of each other.

<!-- image -->

Instead, you can also click this button to the right of the axis to set the respective rotation axis. Plant Simulation then enters the respective values into the text boxes.

<!-- image -->

**Angle**

Type in the angle of rotation in degrees into the text box.

**Add Rotation**

<!-- image -->

To add a rotation angle to the axis that you select, click this button.

<!-- image -->

Type in the Angle which you would like to add to the Axis that you select.

Select the Axis to which you would like to add the Angle .

Click OK to accept the values and to add the angle to the existing Angle .

Click Apply to show the result in the scene window.

SimTalk

\_3D.NameLabelRotation [SimTalk]

**Settings for the Scale [captions]**

##### Settings for the Scale [captions]

To apply uniform scaling to the caption, accept the default setting.

<!-- image -->

This setting automatically enters the value you entered into one text box into the remaining two text boxes for scaling the object.

This way you do not have to manually enter the same value into each text box over again.

To scale the caption of the object on each axis separately, clear Uniform .

<!-- image -->

You can set the three components (x,y,z) with which the caption of the object is going to be scaled as follows:

- To scale the caption by 0.1 meters, hover over the respective text box and roll the mouse wheel.
- To scale the caption by 0.01 meters, hover over the respective text box, hold down Ctrl , and roll the mouse wheel.
- Type in a value into the respective text box.

You can only type in positive values. Typing in 0.5 , for example, halves the size of the caption of the object on the respective axis. Typing in 2.0 doubles its size on the respective axis.

SimTalk

\_3D.NameLabelScale [SimTalk]

