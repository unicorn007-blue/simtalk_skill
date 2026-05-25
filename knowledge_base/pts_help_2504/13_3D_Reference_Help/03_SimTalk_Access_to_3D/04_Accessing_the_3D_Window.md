### Accessing the 3D Window

#### \_\_Accessing the 3D Window

SimTalk provides the methods and functions listed in the table of contents to the left for accessing the 3D window .

#### \_3D.closeWindows [SimTalk]

Closes all windows which are opened for the object designated by &lt;Path&gt;.

Type

Method

Syntax

< Path >._3D.closeWindows

Example

MyStation.\_3D.closeWindows

See also

closeDialog [SimTalk] - all objects

#### F3DactivateCameraMark [SimTalk]

Activates the specified camera mark in the currently active 3D window.

Remarks

The camera mark changes the viewpoint and object of interest in the active 3D window.

Type

Function

Syntax

F3DActivateCameraMark(CameraMark:string)

Parameter

The parameter CameraMark of data type string designates the name of the camera mark.

Example

F3DactivateCameraMark("MyCameraMark")

See also

Camera Marks

#### F3DattachCamera [SimTalk]

Attaches the camera of the active 3D window to the specified object or detaches a previously attached camera in the active 3D window.

Remarks

F3DattachCamera will not do anything if there either is no 3D window open or if the active 3D window is shown in Planning View .

Type

Function

Syntax

F3DattachCamera(ObjectToAttach:any)

**Parameter**

The parameter ObjectToAttach of data type any specifies the object to which you want to attach the camera:

- Specify void to detach an attached camera in the active 3D window.
- Specify an object or a 3D object, for example an animatable object, to attach the camera of the active 3D window to that object.

Example

```simtalk
F3DattachCamera(.MUs.Part:1)
```

See also

Attach Camera

#### F3DconfigurePlanningView [SimTalk]

Sets the view to a Planning View designated by the specified parameters.

Type

Function

**Syntax**

```simtalk
F3DconfigurePlanningView(ViewPosition:real[2], Zoom:real[, ObjectOfInterest:object/3Dobject])
```

**Parameters**

- The parameter ViewPosition is an array of data type real with two values. They designate the position of the view's projection in the XY Plane .
- The parameter Zoom of data type real designates the zoom factor of the view.
- The optional parameter ObjectOfInterest of data type object opens the object in the active 3D window. The object of interest can be an object, a 3D object (for example an animatable object), or a simulation object.

If you do not specify this parameter, the open 3D window remains unchanged.

**Example**

F3DconfigurePlanningView([-14, -15], 16, .Models.MyWarehouse)

**See also**

\_3D.getObject [SimTalk]

Camera Marks

Use Planning View

F3DconfigureView [SimTalk]

Generate SimTalk Code and Copy to Clipboard [camera mark]

#### F3DconfigureView [SimTalk]

Sets the view to a Modeling View designated by the specified parameters.

Type

Function

Syntax

```simtalk
F3DconfigureView(CameraPosition:real[3], CameraRotationX:real,
CameraRotationZ:real[, ObjectOfInterest:object])
```

**Parameters**

- The parameter CameraPosition is an array of data type real with three values. They designate the position of the camera in three-dimensional space.
- The parameter CameraRotationX of data type real designates the rotation of the camera on the x-axis.
- The parameter CameraRotationZ of data type real designates the rotation of the camera on the z-axis.
- The optional parameter ObjectOfInterest of data type object opens the object in the active 3D window. The object of interest can be an object, a 3D object (for example an animatable object), or a simulation object.

If you do not specify this parameter, the open 3D window remains unchanged.

**Example**

F3DconfigureView([-8.129, -3.707, 7.832], 45.000, -15.000, .Models.MyWarehouse)

**See also**

\_3D.getObject [SimTalk]

Camera Marks

F3DconfigurePlanningView [SimTalk]

Generate SimTalk Code and Copy to Clipboard [camera mark]

