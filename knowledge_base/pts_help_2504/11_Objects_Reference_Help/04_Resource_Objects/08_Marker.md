### Marker

Use the Marker for setting waypoints in your simulation model along which the Automated Guided Vehicle drives from the AGVPool to its destination .

Icon

<!-- image -->

**Remarks**

The freely driving AGV only works in 3D, not in 2D.

<!-- image -->

With the setting Default Curve Radius / DefaultCurveRadius you can set the size of the roundings at the Markers .

A Default Curve Radius of 0 makes the AGV rotate on the spot instead of driving a curve.

**Note**

When you insert Markers into your model, make sure that the Markers are aligned . This prevents Plant Simulation from computing unnecessary roundings between the Markers . Misaligned Markers might occur if you inserted Markers into your model while Show Grid was off.

**Note**

If a standing Transporter cannot drive to the first Marker using the specified Default Curve Radius , the Transporter rotates on the spot, if possible, and then drives in a straight line toward the Marker .

The Marker can be directional or omnidirectional . You can switch between these two states with the check box Use Rotation of Marker .

<!-- image -->

Add the Object to the Simulation Model

To add the Marker to your simulation model, click Manage Class Library &gt; Basic Objects &gt; Resources &gt; Marker on the Home ribbon tab.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

**See also**

Directional and Omidirectional Markers

Dialog Box of the Marker

Model an Automated Guided Vehicle System (AGVS)

#### Directional and Omidirectional Markers

The Markers in your simulation model can be directional or omnidirectional .

You can switch between these two states with the check box Use Rotation of Marker .

- The AGV does not drive through an inserted omnidirectional Marker but turns in front of the inserted Markers toward the next Marker . The icon of an omnidirectional marker looks like this .
- The AGV can drive through directional Markers in both directions. For selecting the direction, Plant Simulation uses position of the previous Marker in the sequence of Markers .

<!-- image -->

Plant Simulation computes the route by means of a Marker with the 90-degree angle as follows:

- If, for example, the previous Marker is located above the Marker with the 90-degree angle, the AGV drives through the Marker with the 90-degree angle from top to bottom.
- If the previous Marker is located below the Marker with the 90-degree angle, the AGV drives through the Marker with the 90-degree angle from bottom to top.
- If the previous Marker is located exactly at the height of the Marker with the 90-degree angle, Plant Simulation evaluates the current direction of the AGV .

If the front of the AGV points up, the AGV drives through the Marker with the 90-degree angle from top to bottom.

If the front of the AGV points down, the AGV drives through the Marker with the 90-degree angle from bottom to top.

If the front of the AGV points exactly to the center of the Marker with the 90-degree angle, the AGV drives through the Marker with the 90-degree angle from top to bottom.

For Markers with other angles Plant Simulation proceeds accordingly.

For a directional Marker with the default angle of 0° the AGV drives through the markers and then turns on the marker around the angle you set in the direction of the next marker. The icon of a directional marker looks like this .

See also

Marker

#### Dialog Box of the Marker

Dialog Box of the Marker

Double-click the icon of the Marker to open its dialog box.

Edit Simulation Properties

There you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties :

<!-- image -->

For a directional Marker with another than the default angle the AGV drives toward the Marker at the angle you entered, crosses it, and leaves it at the designated angle. In the example below we used an angle of 90°. The icon of a directional marker with an angle of 90° looks like this .

<!-- image -->

##### Tab Attributes

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.

- Select the object in the 3D model and press the spacebar .

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

<!-- image -->

###### Use Rotation of Marker [check box]

To make the AGV use the rotation of the Marker on its way to its destination, select this check box.

<!-- image -->

If you select the check box, the AGV drives across the Marker , and rotates on the Marker with the defined angle in the direction of the next Marker . The icon of a directional marker , which you inserted into the Frame , looks like this .

<!-- image -->

For the default angle of 0° it looks like this:

<!-- image -->

If you type in a rotation angle, for example 90°, it looks like this:

<!-- image -->

You can set the rotation angle in the dialog Edit 3D Properties of the Marker on the tab Transformation under Settings for the Rotation .

<!-- image -->

If you clear the check box , the AGV does not drive across the inserted Markers but rotates in front of the Marker toward the next Marker . The icon of an omnidirectional marker , which you inserted into the Frame , looks like this .

<!-- image -->

**SimTalk**

**UseRotationOfMarker [SimTalk]**

See also

Model an Automated Guided Vehicle System (AGVS) &gt; Cover a Route Along Omnidirectional Markers Model an Automated Guided Vehicle System (AGVS) &gt; Cover a Route Along Directional Markers

**Video on YouTube**

[https://youtu.be/PYXYutlaGOs?si=6CKYE1f\_nLtIVThg&amp;t=924](https://youtu.be/PYXYutlaGOs?si=6CKYE1f_nLtIVThg&t=924)

**Arrival Control [Marker]**

###### Arrival Control [Marker]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Arrival Control , which is called as soon as the Transporter driving freely within the area arrives at the Marker .

<!-- image -->

In the Arrival Control you can, for example, program actions that you want to take once an AGV arrives at the Marker or is closest to the Marker . You might, for example, provide your fleet management software with feedback about the position of the AGV .

For an omnidirectional Marker Plant Simulation executes the control once the Transporter driving freely within the area arrives at the half-way point of the curvature/fillet at the Marker .

If you did not enter a Method , the value of the control is VOID.

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

SimTalk

**ArrivalCtrl [SimTalk]**

See also

Select Object [for controls]

Video on YouTube

[https://youtu.be/PYXYutlaGOs?si=FNgErAj2FbcGgyhv&amp;t=409](https://youtu.be/PYXYutlaGOs?si=FNgErAj2FbcGgyhv&t=409)

**Tab User-defined**

**Tab User-defined**

Define your own attributes as described under the Tab User-defined .

**Navigate Menu**

The commands are described under the Navigate Menu .

**View Menu**

View Menu

The View Menu provides commands to access its functions.

Refresh [on View menu]

Show Attributes and Methods [on View menu]

SimTalk

updateDialog [SimTalk]

See also

View Menu [general description]

Tools Menu

The Tools Menu provides these menu commands: Edit Controls Edit Observers 3D

**Help Menu**

The commands are described under the Help Menu .

##### Methods of the Marker

#### Methods of the Marker

The Marker provides the Methods of All Objects .

To view all of the methods , read-only attributes and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

An example of the Syntax line of the individual methods might look like this:

<!-- image -->

- The expression &lt;Path&gt; designates the path of the object to which the method applies.
- The signature of the method, consisting of the identifier and the data type of the parameter, is listed in parentheses. The expression (Parameter:string) , for example, designates a parameter of data type string . Instead of a constant value, you can also use a variable of the required type or a method that returns the required data type.

**Note**

Make sure to enter the parentheses for expressions within parentheses (…). Not entering them may lead to unexpected results and open the Debugger .

Optional parameters are listed within brackets. The expression [,Parameter:boolean] , for example, means that you can, but do not have to enter the boolean parameter.

If a parameter has a default value, the signature shows the default value after the parameter.

If the method has a return value, the signature shows its data type after the arrow -&gt;.

##### getRouteLength [SimTalk] - Marker

getRouteLength [SimTalk] - Marker

Returns the route length of the Marker designated by &lt;Path&gt; to the specified destination.

Type

Method

Syntax

```simtalk
< >.getRouteLength(ToMarker:path[, byref ObjectsAlongRoute:object[],
Path RouteWeightingAttribute:string]) → length
```

**Parameters**

You can specify the following parameters:

- The parameter ToMarker of data type path designates the destination object.
- The optional parameter ObjectsAlongRoute designates an array of data type object into which the Marker enters the objects along the route to the destination.
- The optional parameter RouteWeightingAttribute of data type string designates the name of the Route Weighting Attribute for automatic routing. If the parameter is not passed, Plant Simulation does not weight the lengths of the routes.

Return Value

The return value has the data type length .

If the destination is not reachable, Plant Simulation returns the value -1.

Example

print Marker1.getRouteLength(Marker2)

##### Read-Only Attributes of the Marker

Read-Only Attributes of the Marker

The Marker provides the \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyMarker.UUID

**Attributes of the Marker**

\_Attributes of the Marker

The Marker provides:

- The attributes listed in the table of contents to the left.
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyMarker.UseRotationOfMarker := true
print MyMarker.UseRotationOfMarker
```

##### ArrivalCtrl [SimTalk]

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation runs the Arrival Control as soon as the Transporter driving freely within the area arrives at the Marker designated by &lt;Path&gt;.

For an omnidirectional Marker Plant Simulation runs the control once the Transporter driving freely within the area arrives at the half-way point of the curvature/fillet at the Marker .

If you did not specify a Method , the value of the attribute is VOID.

Type

Attribute

Syntax

&lt; Path &gt;.ArrivalCtrl:method

Assignment Value

You can assign a value of data type method .

Example

MyMarker.ArrivalCtrl := &amp;myMethod

See also

Arrival Control [Marker]

##### UseRotationOfMarker [SimTalk]

Sets if the AGV uses the rotation of the Marker designated by &lt;Path&gt; when driving to its destination ( true ) or not ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.UseRotationOfMarker:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyMarker.UseRotationOfMarker := true

See also

Amount [text box] - AGVPool

