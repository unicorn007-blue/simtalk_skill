### Accessing Methods of Graphic Groups

#### \_\_Accessing Methods of Graphic Groups

SimTalk provides the methods listed in the table of contents to the left for accessing graphic groups in 3D .

You can view and access the methods for accessing graphic groups by clicking Auto Complete on the Edit ribbon tab of the Method Editor .

<!-- image -->

**See also**

**Auto Complete**

Edit 3D Properties [dialog] &gt; Graphics [tab, 3D] &gt; Graphic Groups [described]

#### \_3D.addGraphicGroup [SimTalk]

Adds the specified graphic group to the object designated by &lt;Path&gt;.

Remarks

Assigning the method deactivates graphic inheritance.

Type

Method

Syntax

```simtalk
< Path >._3D.addGraphicGroup(GraphicGroupName:string, Visible:boolean[, Internal:boolean:=false, Locked:boolean:=false])
```

**Parameters**

- The parameter GraphicGroupName of data type string designates the name of the graphic group.
- The parameter Visible of data type boolean sets if the graphic group will be visible ( true ) or not visible ( false ).
- The optional parameter Internal of data type boolean sets if the graphic group will be internal ( true ) or external ( false ).

**Default Value of the Parameter**

The default value is false.

- The optional parameter Locked of data type boolean sets if the graphic group will be locked ( true ) or not ( false ).

**Default Value of the Parameter**

The default value is false.

**Example**

```simtalk
MyStation._3D.addGraphicGroup("MyGraphicGroup", true, true, false) // new source code, is the same as the source code below
var graphicgroup := _3D.addGraphicGroup("MyGraphic", true, false) // previous source code
_3D.addGraphicGroup("MyGraphic", true, false)
var graphicgroup := _3D.getGraphic("MyGraphic")
```

**See also**

\_3D.deleteGraphicGroup [SimTalk]

Edit 3D Properties [dialog] &gt; Graphics [tab, 3D] &gt; Add [graphic group]

#### \_3D.deleteGraphicGroup [SimTalk]

Deletes the specified graphic group from the object designated by &lt;Path&gt;.

Remarks

Assigning the method deactivates graphic inheritance.

Type

Method

Syntax

```simtalk
< Path >._3D.deleteGraphicGroup(GraphicGroupName:string) → string
```

Parameter

The parameter GraphicGroupName of data type string designates the name of the graphic group.

Return Value

The return value has the data type string .

Example

MyStation._3D.deleteGraphicGroup("MyGraphicGroup")

See also

\_3D.addGraphicGroup [SimTalk]

Edit 3D Properties [dialog] &gt; Graphics [tab, 3D] &gt; Delete [button] - graphic group

#### \_3D.deleteGraphicGroupContent [SimTalk]

Deletes the graphics from the specified graphic group from the object designated by &lt;Path&gt;.

Remarks

Assigning the method deactivates graphic inheritance.

Type

Method

Syntax

&lt; Path &gt;.\_3D.deleteGraphicGroupContent([GraphicGroupName:string])

Parameter

The optional parameter GraphicGroupName of data type string designates the name of the graphic group.

Do not specify the name to delete the content of the default graphic group.

If you try to delete the content of an automatically generated default graphic group, this attempt will fail without an error message.

Specify a name to open the Method Debugger .

Example

MyFrame.\_3D.deleteGraphicGroupContent("deco")

**Accessing Attributes and Read-Only Attributes of Graphic Groups**

