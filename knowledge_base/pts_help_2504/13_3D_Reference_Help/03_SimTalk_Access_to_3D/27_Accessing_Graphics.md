### Accessing Graphics

#### \_\_Accessing Graphics

SimTalk provides the attributes and methods listed in the table of contents to the left for accessing graphics in 3D .

You can view and access the attributes and methods for accessing graphics by clicking Auto Complete on the Edit ribbon tab of the Method Editor .

<!-- image -->

See also

Auto Complete

#### \_3D.calculateMUDimensions [SimTalk]

Calculates the dimensions of the MU designated by &lt;Path&gt; from its graphic.

Type

Method

Syntax

&lt; Path &gt;.\_3D.calculateMUDimensions([OnlyVisibleGroups:boolean:=false])

Parameter

The optional parameter OnlyVisibleGroups of data type boolean sets if the dimensions of all graphic groups are to be computed ( false ) or only of the visible graphic groups ( true ).

After Plant Simulation has executed the method, the Length , Width , and Height of the MU match the dimensions of the graphic. Plant Simulation uses the zero point of the graphic to calculate the booking point.

**Default Value of the Parameter**

The default value is false.

Example

```simtalk
.MUs.Part._3D.calculateMUDimensions(true)
```

See also

**Calculate Dimensions from 3D**

#### \_3D.exchangeGraphic [SimTalk]

Exchanges the entire graphic of the selected object designated by &lt;Path&gt; with the graphic you imported from a file.

Type

Method

Syntax

```simtalk
< Path >._3D.exchangeGraphic(FilePath:string[, UseNewGraphicMeasurement:boolean:=false]) → boolean
```

**Parameters**

- The parameter FilePath of data type string sets the path and the name of the file you want to import.
- The optional parameter UseNewGraphicMeasurement of data type boolean sets if the new graphic measurements are also to be used for the simulation measurements of the MU .

If you specify true and the object is a MU and if the attribute \_3D.ScaleAutomatically of the loaded .s3d file is set to false, this attribute is set to true again and the graphic measurements are applied to the simulation. In all other cases the method does not execute anything in addition.

**Default Value of the Parameter**

The default value is false.

Return Value

The return value has the data type boolean .

Example

MyFrame._3D.exchangeGraphic("C:\Program Files\Siemens\Plant Simulation 2504\3D\s3D-graphics\Lathe.s3d")

See also

**Exchange Graphics**

\_3D.ScaleAutomatically [SimTalk]

#### \_3D.ExcludeFromShowContentOfLocation [SimTalk]

Hides (true) or shows (false) the object designated by &lt;Path&gt; from view in the representation of the location of the object. Also hides Connectors that are connected with hidden objects.

Remarks

Then the representing graphics of the selected object are only visible within its parent object. This makes, for example, sense for the EventController , for Methods , for DataTables , etc., which are needed to define and control the simulation but not to illustrate the simulated scene.

Type

Attribute

Syntax

&lt; Path &gt;.\_3D.ExcludeFromShowContentOfLocation:boolean

Assignment Value

You can assign a value of data type boolean .

Example

Station.\_3D.ExcludeFromShowContentOfLocation := true

See also

Edit 3D Properties [dialog] &gt; Graphics [tab, 3D] &gt; Exclude from "Show content" of the Location

#### \_3D.exportAsJt [SimTalk]

Exports the designated graphic or the designated 3D object of the object designated by &lt;Path&gt; as a .JT file.

**Remarks**

\_3D.exportAsJt exports only graphics which are part of the object.

Type

Method

Syntax

```simtalk
< Path >._3D.exportAsJt(FilePath:string[, OptimizeForCAD:boolean := false, ExcludeInvisibleParts:boolean := false]) → boolean
```

**Parameters**

- The parameter FilePath of data type string sets the path to the target file.
- The optional parameter OptimizeForCAD of data type boolean sets if the structure of the graphic will be optimized for CAD applications such as NX ( true ) or for other applications such as Plant Simulation or Teamcenter Visualization ( false ).

**Default Value of the Parameter**

The default value is false.

- The optional parameter ExcludeInvisibleParts of data type boolean sets if all graphics of the object ( false or not set) are going to be exported or if only those graphics that would be visible if you would open the object in a 3D window ( true )

**Default Value of the Parameter**

The default value is false.

When you export a graphic as a Jt file and when you activate Optimize for CAD , captions and logical object are excluded.

**Logical objects are:**

- EventController
- FlowControl
- Cycle
- Exporter
- Broker

**\_3D.exportAsJt [SimTalk]**

- ShiftCalendar
- LockoutZone
- All InformationFlow objects
- All UserInterface objects
- All GA objects

Return Value

The return value has the data type boolean .

true if the file could be exported with graphics.

false if nothing was left to be exported.

**Example**

.MaterialFlow.Frame.exportAsJt("D:\MyS3D\MyFrame.jt")

**See also**

- \_3D.exportModelingViewBitmap [SimTalk]
- \_3D.exportPlanningViewBitmap [SimTalk]
- \_3D.exportAsS3D [SimTalk]

Import Graphics [command]

Export Graphics

Export Object

importGraphics [SimTalk]

#### \_3D.exportAsS3D [SimTalk]

Exports the graphic data and the designated animation object of the object designated by &lt;Path&gt; as an .s3D (3D File) file.

Remarks

It exports graphics which are part of the object, attributes that are relevant for the appearance and the animation, as well as the 3D part of embedded objects.

Type

Method

Syntax

```simtalk
< Path >._3D.exportAsS3D(FilePath:string) → boolean
```

Parameter

The parameter FilePath of data type string designates the path to the target file.

Return Value

The return value has the data type boolean .

Example

.MaterialFlow.Frame._3D.exportAsS3D("D:\MyS3D\MyFrame.s3d")

See also

- \_3D.exportModelingViewBitmap [SimTalk]

\_3D.exportPlanningViewBitmap [SimTalk]

\_3D.exportAsJt [SimTalk]

Import Graphics [command]

Export Graphics

Export Object

importGraphics [SimTalk] _3D.exchangeGraphic [SimTalk]

#### \_3D.exportModelingViewBitmap [SimTalk]

Exports the 3D modeling view scene of the object designated by &lt;Path&gt; as a .PNG file.

Remarks

The parameters CameraPosition and CameraRotation correspond to the parameters CameraPosition and CameraPosition of the function F3DconfigureView . If you create SimTalk code with F3DconfigureView , you can also use it with slight modifications here.

Type

Method

Syntax

```simtalk
< Path >._3D.exportModelingViewBitmap(FilePath:string, Width:integer, Height:integer[, CameraPosition:length[3], CameraRotationX:real, CameraRotationZ:real]) → boolean
```

**Parameters**

- The parameter FilePath of data type string sets the path to the target file.
- The parameter Width of data type integer sets the width in pixels in the target file.
- The parameter Height of data type integer sets the height in pixels in the target file.
- The optional parameter CameraPosition is an array of data type length with three values. It sets the camera position in the scene.
- The optional parameter CameraRotationX of data type real sets the rotation angle of the camera around the x-axis.
- The optional parameter CameraRotationZ of data type real sets the rotation angle of the camera around the z-axis.

**Note**

You can either specify all three camera parameters or none of them. If you do not specify them, Plant Simulation creates a bitmap of the entire scene.

**Return Value**

The return value has the data type boolean .

true if Plant Simulation was able to create the bitmap.

**Example**

.Models.Model._3D.exportModelingViewBitmap("D:\FactoryLibraries\MyFrame", 100, 100, [2,3,2], 2,2)

**See also**

\_3D.exportAsJt [SimTalk]

\_3D.exportAsS3D [SimTalk]

F3DconfigureView [SimTalk]

- \_3D.exportPlanningViewBitmap [SimTalk]

Generate SimTalk Code and Copy to Clipboard [camera mark]

Export Bitmap

#### \_3D.exportPlanningViewBitmap [SimTalk]

Exports the 3D planning view scene of the object designated by &lt;Path&gt; as a .PNG file.

Remarks

The parameters ViewPosition and Zoom correspond to the parameters ViewPosition and Zoom of the function F3DconfigurePlanningView . If you create SimTalk code with F3DconfigurePlanningView , you can also use it with slight modifications here.

Type

Method

Syntax

```simtalk
< Path >._3D.exportPlanningViewBitmap(FilePath:string, Width:integer, Height:integer[, ViewPosition:length[2], Zoom:real]) → boolean
```

**Parameters**

- The parameter FilePath of data type string sets the path to the target file.
- The parameter Width of data type integer sets the width in pixels in the target file.
- The parameter Height of data type integer sets the height in pixels in the target file.
- The optional parameter ViewPosition is an array of data type length with two values. It sets the view position in the scene.
- The optional parameter Zoom of data type real sets the zoom factor in the view.

**Note**

You can only specify both the view position and the zoom factor together. If you do not specify them, Plant Simulation creates a bitmap of the entire scene.

**Return Value**

The return value has the data type boolean .

true if Plant Simulation was able to create the bitmap.

**Example**

.Models.Model._3D.exportPlanningViewBitmap("D:\FactoryLibraries\MyFrame", 100, 100, [2,3], 3)

**See also**

Generate SimTalk Code and Copy to Clipboard [camera mark]

\_3D.exportAsJt [SimTalk]

\_3D.exportAsS3D [SimTalk]

F3DconfigurePlanningView [SimTalk]

\_3D.exportModelingViewBitmap [SimTalk]

Use Planning View

Export Bitmap

#### \_3D.getGraphic [SimTalk]

Returns the designated graphic of the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >._3D.getGraphic(GraphicGroupName:string[, Path:any[]]) → void
```

**Parameters**

- The parameter GraphicGroupName of data type string designates the name of the graphic group.
- The optional parameter Path of data type any either lists numerical indexes or names. You cannot mix these two types of addressing.

The numerical indexes are one-based.

The names are just that, namely names, for example MyName .

Compare these examples:

- The expression [] designates the entire graphic group. If you do not specify the parameter, you also access the entire graphic group. If you enter \_3D.getGraphic("default", []) , you address the graphic group named "default" as a whole.
- The expression [1] designates the first direct child graphic.
- The expression ["abc"] designates the direct child graphic with the name abc .
- The expression [1,4] designates the fourth child graphic of the first direct child graphic.
- The expression ["abc","def"] designates the child graphic with the name def of the direct child graphic with the name abc .

The figure below illustrates the values of the parameters GraphicGroupName and Path for the displayed nodes of the Frame .

<!-- image -->

You can view and access the attributes and methods of the graphics and the graphic groups by selecting Edit &gt; Auto Complete in the Method Editor .

**Return Value**

void if the specified graphic does not exist. This way you can query if a graphic exists or not.

**Examples**

```simtalk
/var g := Machine._3D.getGraphic("default", [1]) // returns the first graphic in the graphic group named default
g.Position := [1,2,3]
var g := Machine._3D.getGraphic("default", ["head"]) // returns the graphic named head in the graphic group named default
g.Position := [1,2,3]
```

Abbreviated Notation if GraphicGroupName is a Valid Identifier

If the parameter GraphicGroupName is a valid identifier, you can also type:

```simtalk
var g := Machine._3D.default([1]) // returns the first graphic in the graphic group named default
g.Position := [1,2,3]
var g := Machine._3D.default(["head"]) // returns the graphic named head in the graphic group named default
g.Position := [1,2,3]
```

**See also**

**Auto Complete**

\_3D.InheritGraphics [SimTalk]

\_3D.getObject [SimTalk]

graphic [SimTalk]

- \_Detailed Access To Graphics

Copy 3D Object Settings to a Method

#### \_3D.InheritGraphics [SimTalk]

Activates ( true ) or deactivates ( false ) graphic inheritance of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >._3D.InheritGraphics:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.Models.Model.Station1._3D.InheritGraphics := false
var a: boolean := .Models.Model.Station1._3D.InheritGraphics // returns whether the graphic is inherited or not
```

See also

Edit 3D Properties [dialog] &gt; Graphics [tab, 3D]

\_3D.getGraphic [SimTalk]

#### \_3D.optimizeObject [SimTalk]

Optimizes the 3D object designated by &lt;Path&gt;.

Remarks

The object can either be a simulation object or an animatable object.

**Note**

As you cannot restore discarded data, we advise to optimize the structure of the object after you are done modeling the object. Optimizing the 3D graphic improves performance.

We also recommend to save the model under a different name before optimizing it. This way you can return to the state the model had before optimizing it in case the optimized model reports errors or does not meet your expectations.

Type

Method

Syntax

&lt; Path &gt;\_3D.optimizeObject(WithContainedObjects:boolean, OptimizeInheritance:boolean, OptimizeGraphicStructure:boolean)

**Parameters**

- The parameter WithContainedObjects of data type boolean sets if, starting from the object designated by &lt;Path&gt;, the entire partial structure will be optimized, for example the entire model for basis.\_3D.optimizeObject or the entire folder named MaterialFlow for the instruction .MaterialFlow.\_3D.optimizeObject ( true ). Specify false to only optimize the object itself.
- The parameter OptimizeInheritance of data type boolean sets if setting Optimize 3D Attribute Inheritance will be activated and if Plant Simulation attempts to ( true ):
- Activate inheritance of 3D attributes whose values uniquely match the corresponding value of its origin. Graphics inheritance is never activated.
- Replace MU Animation Paths for individual matrix places, with names such as #0#0 , etc., with an Animation Area if this change is possible without a position change of the animation.
- The parameter OptimizeGraphicStructure of data type boolean sets if the setting Optimize 3D Graphic Structure will be activated and if Plant Simulation applies the optimization setting Flatten structure , without the setting Keep Grouping to all editable graphics ( true ).

If this parameter is true , Plant Simulation optimizes the model with activated setting Preserve References . This is intended to prevent that the model size increases after optimizing the model. In some cases it might prevent an optimal optimization result for the graphic structure.

<!-- image -->

**Example**

<!-- image -->

#### \_3D.ShowContent [SimTalk]

Shows the representing graphics of the objects that are contained within the object designated by &lt;Path&gt; in the view from the outside ( true ) or hides them ( false ).

**Remarks**

Contained objects, for which 3D.ExcludeFromShowContentOfLocation is set to true , never are visible, independent of the setting in the outside representation of this object.

\_3D.ShowContent only applies for objects, which can contain MUs and for the Frame . Objects, which can contain MUs , are most of the material flow objects, plus Container and Transporter and their animatable objects.

<!-- image -->

Type

Attribute

Syntax

&lt; Path &gt;.\_3D.ShowContent:boolean

**Detailed Access To Graphics**

**Assignment Value**

You can assign a value of data type boolean .

**Example**

```simtalk
Station._3D.ShowContent := true
```

**See also**

Edit 3D Properties [dialog] &gt; Graphics [tab, 3D] &gt; Show Content

\_3D.ExcludeFromShowContentOfLocation [SimTalk]

**Detailed Access To Graphics**

