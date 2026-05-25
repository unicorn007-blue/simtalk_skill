### \_\_Accessing Attributes and Read-Only Attributes of Graphic Groups

SimTalk provides the attributes and read-only attributes listed in the table of contents to the left for accessing graphic groups in 3D .

You can view and access the attributes for accessing graphic groups by clicking Auto Complete on the Edit ribbon tab of the Method Editor .

See also Auto Complete

Edit 3D Properties [dialog] &gt; Graphics [tab, 3D] &gt; Graphic Groups [described]

#### \_3D.GraphicGroupNames [SimTalk]

Returns a list of all graphic groups that exist for the object designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

```simtalk
< Path >._3D.GraphicGroupNames → string[]
```

Return Value

The return value is an array of data type string .

Example

```simtalk
print .Models.MyEnginePlant.Station._3D.GraphicGroupNames // might, for example,
return [default, mygraphicgroup1, MyGraphicGroup2]
```

See also

Edit 3D Properties [dialog] &gt; Graphics [tab, 3D] &gt; Graphic Groups [described]

#### \_3D.InternalGraphicGroups [SimTalk]

Sets the list of all internal graphic groups of the object designated by &lt;Path&gt;.

Remarks

A visible internal graphic group is visible inside of its object and together with its content (compare \_3D.ShowContent ) from the outside.

**Note**

The attribute only applies to the Frame .

**Note**

Assigning the attribute deactivates graphic inheritance.

Type

Attribute

Syntax

```simtalk
< Path >._3D.InternalGraphicGroups:string[]
```

**Assignment Value**

You can assign an array of data type string .

Example

```simtalk
.Models.Model._3D.InternalGraphicGroups := ["deco1", deco2"]
var a :
string[] := .Models.Model._3D.InternalGraphicGroups
```

SimTalk

\_3D.ShowContent [SimTalk]

**See also**

| Edit 3D Properties [dialog] > Graphics [tab, 3D] > Internal [check box]   | _3D.VisibleGraphicGroups [SimTalk]   |
|---------------------------------------------------------------------------|--------------------------------------|
| _3D.LockedGraphicGroups [SimTalk]                                         | Internal [SimTalk] - graphic group   |
| _3D.LockedGraphicGroups [SimTalk]                                         |                                      |

#### \_3D.LockedGraphicGroups [SimTalk]

Sets the list of all locked graphic groups of the object designated by &lt;Path&gt;.

Remarks

This then prevents you from selecting this graphic group in the 3D windows which are opened for this object. This makes, for example, sense for the graphic of a factory building which might otherwise be selected inadvertently.

**Note**

Assigning the attribute deactivates graphic inheritance.

Type

Attribute

Syntax

```simtalk
< Path >._3D.LockedGraphicGroups:string[]
```

Assignment Value

You can assign an array of data type string .

Example

```simtalk
.Models.Model.Station1._3D.LockedGraphicGroups := ["Group1, Group2"]
var a:
string[] := .Models.Model.Station1._3D.LockedGraphicGroups
```

See also

| Edit 3D Properties [dialog] > Graphics [tab, 3D] > Locked [graphic group]   | _3D.InternalGraphicGroups [SimTalk]   |
|-----------------------------------------------------------------------------|---------------------------------------|
| Locked [SimTalk] - graphic group                                            | _3D.VisibleGraphicGroups [SimTalk]    |

#### \_3D.VisibleGraphicGroups [SimTalk]

Sets the graphic groups of the object designated by &lt;Path&gt; that will be visible.

Type

Attribute

Syntax

```simtalk
< Path >._3D.VisibleGraphicGroups:string[]
```

Assignment Value

You can assign an array of data type string .

Example

```simtalk
MyStation._3D.VisibleGraphicGroups := ["default", "deco"]
```

**See also**

| Edit 3D Properties [dialog] > Graphics [tab, 3D] > Visible [check box]   | _3D.InternalGraphicGroups [SimTalk]   |
|--------------------------------------------------------------------------|---------------------------------------|
| _3D.AnimationObject [SimTalk]                                            | _3D.LockedGraphicGroups [SimTalk]     |
| _3D.InheritGraphics [SimTalk]                                            | Visible [SimTalk] - graphic group     |

#### Generated [SimTalk] - graphic group

Returns if the graphics of the graphic group designated by &lt;Path&gt; are generated automatically or not.

Remarks

If the graphic group is generated, you can neither edit, nor delete nor add to it, nor delete the graphic. You can edit some of its appearance properties though.

Type

Read-only attribute

Syntax

&lt; Path &gt;.Generated:boolean

Return Value

The return value has the data type boolean .

Example

print Station.\_3D.getGraphic("MyGraphicGroup").Generated

See also

Graphic Groups [described]

\_3D.getGraphic [SimTalk]

#### Internal [SimTalk] - graphic group

Sets if the graphic group designated by &lt;Path&gt; is an internal group ( true ) or not ( false ).

Remarks

Plant Simulation always shows internal groups in a view for the respective object. Plant Simulation only shows them in a view containing that object if the object's attribute \_3D.ShowContent is set to true.

Type

Attribute

Syntax

```simtalk
< Path >.Internal:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
print _3D.getGraphic("deco").Internal
_3D.getGraphic("deco").Internal := false
```

**See also**

_3D.ShowContent [SimTalk] Graphic Groups [described] _3D.getGraphic [SimTalk]

#### Locked [SimTalk] - graphic group

Sets if the graphic group designated by &lt;Path&gt; is locked ( true ) or not ( false ).

Remarks

Locking a graphic groups prevents you from selecting this graphic group in the 3D windows which are opened for this object.

This makes, for example, sense for the graphic of a factory building which might otherwise be selected inadvertently.

Type

Attribute

Syntax

```simtalk
< Path >.Locked:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
print Station._3D.getGraphic("MyGraphicGroup").Locked
Station._3D.getGraphic("MyGraphicGroup").Locked := false
```

See also

Graphic Groups [described]

\_3D.getGraphic [SimTalk]

#### Visible [SimTalk] - graphic group

Sets if the graphic group designated by &lt;Path&gt; is visible ( true ) or not ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.Visible:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
print Station._3D.getGraphic("MyGraphicGroup").Visible
Station._3D.getGraphic("MyGraphicGroup").Visible := false
```

See also

Graphic Groups [described]

\_3D.getGraphic [SimTalk]

