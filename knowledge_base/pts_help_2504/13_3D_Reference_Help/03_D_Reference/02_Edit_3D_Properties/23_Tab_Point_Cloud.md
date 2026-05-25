#### Tab Point Cloud

Point Cloud

Select settings for displaying a point cloud in your simulation model on the tab Point Cloud .

You can:

- Select the File Path of the point cloud file to be displayed.
- Type in settings for the Position of the point cloud in the model.
- Type in settings for the Rotation of the point cloud in the model.

**Note**

Initially, your 3D window might only show small parts of the point cloud. When you start rotating the view, the 3D window shows additional parts of the graphic.

Plant Simulation will load the point cloud significantly faster if the point cloud file is located on an SSD storage device.

**See also**

\_\_Accessing Point Clouds

**Add a Point Cloud**

Show Point Clouds on the View ribbon tab of the 3D window

<!-- image -->

##### File Path

Click the folder button and select the point cloud file that you want to import.

<!-- image -->

To remove the point cloud from the Frame , delete its name from the text box.

**Note**

Provided the path is relative, it refers to the folder in which your simulation model is located.

The abbreviation .pod stands for point database.

SimTalk

\_3D.PointCloudPath [SimTalk]

**Position [point cloud]**

##### Position [point cloud]

Type a value into the text box X , or roll the mouse wheel to move the Position of the point cloud on the x-axis.

Type a value into the text box Y , or roll the mouse wheel to move the Position of the point cloud on the y-axis.

Type a value into the text box Z , or roll the mouse wheel to move the Position of the point cloud on the z-axis.

**Move to Zero**

To move the selected point cloud (with the center of its base area) to the point of origin of the Frame it belongs to, click Move to Zero . This is especially handy when you import graphics, such as .wrl files, which 3D might not place at the position you expected.

<!-- image -->

The button Move to Zero is only active after you click Apply .

**SimTalk**

\_3D.PointCloudPosition [SimTalk]

##### Rotation [point cloud]

Type in the Rotation Angle of the point cloud in the Frame in degrees. 3D interprets the rotation angle as a rotation around the negative z-axis.

This corresponds to the rotation angles in 2D.

Instead, you can also click the button to the right of the respective axis to set the rotation axis. Plant Simulation then enters the respective values into the text boxes.

<!-- image -->

**Add Rotation**

<!-- image -->

**Note**

Only graphics, objects which do not have a counterpart in 2D, and point clouds provide this button.

To add a rotation angle to the axis that you select, click this button.

<!-- image -->

Type in the Angle which you would like to add to the Axis that you select.

Select the Axis to which you would like to add the Angle .

Click OK to accept the values and to add the angle to the existing Angle . Click Apply to show the result in the scene window.

SimTalk

\_3D.PointCloudRotation [SimTalk]

