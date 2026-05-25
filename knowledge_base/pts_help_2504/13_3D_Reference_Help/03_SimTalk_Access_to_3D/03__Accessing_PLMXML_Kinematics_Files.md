### \_Accessing PLMXML Kinematics Files

SimTalk provides the functions listed in the table of contents to the left for accessing PLMXML kinematics files.

#### applyPLMXMLKinematicStructure [SimTalk]

Applies a kinematics structure from the specified PLMXML file to the graphic designated by &lt;Path&gt;.

Remarks

During this process animatable objects are created within the simulation object or animatable object which are furnished with kinematics settings from the PLMXML file and which contain parts of the graphic designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.applyPLMXMLKinematicStructure(FilePath:string[, PreferFirstEntryPoint:boolean:=true, PreferredEntryPointName:string:=""])
-> boolean
```

**Parameters**

- The parameter FilePath of data type string designates the path to the PLMXML file containing the desired information.
- The optional parameter PreferFirstEntryPoint of data type boolean specifies if the first ( true ) or the last ( false ) of the potential kinematics structures is to be used.

**Default Value of the Parameter**

The default value is true .

- The optional parameter PreferredEntryPointName of data type string sets the name of the root of the kinematics structure which is to be used if several potential kinematics structures exist. If this name is an empty string "" , the method ignores the parameter.

If you specify both optional parameters, the preferred name is stronger than the preferred first or last entry point.

**Default Value of the Parameter**

The default value is an empty string "" .

Return Value

The return value has the data type boolean .

true if a kinematics structure was found and applied.

false if no kinematics structure was found.

**Examples**

```simtalk
var newGraphic: any := MyStation._3D.getGraphic("default").importGraphics("D:\Graphic.jt")
var kinematicsApplicable:boolean := newGraphic.applyPLMXMLKinematicStructure("D:\kin.plmxml")
if not kinematicsApplicable then -- error handler end
var roots:
string[] := getPotentialPLMXMLKinematicRoots("D:\kin.plmxml")
if roots.Dim = 0 then -- error handler
else
	var newGraphic: any := MyStation._3D.getGraphic("default").importGraphics("D:\Graphic.jt")
	if roots.Dim > 1 then
		var kinematicsApplicable: boolean  := newGraphic.applyPLMXMLKinematicStructure("D:\kin.plmxml", true, roots[2])
		if not kinematicsApplicable then -- error handler
		end
	else
		var kinematicsApplicable: boolean  := newGraphic.applyPLMXMLKinematicStructure("D:\kin.plmxml")
		if not kinematicsApplicable then -- error handler
		end
	end
end
```

**See also**

getPotentialPLMXMLKinematicRoots [SimTalk]

#### getPotentialPLMXMLKinematicRoots [SimTalk]

Reads kinematics information from the designated PLMXML file and lists all roots of all potential kinematics structures from the file.

Type

Method

Syntax

```simtalk
getPotentialPLMXMLKinematicRoots(FilePath:string)
-> string[]
```

**Parameter**

The parameter FilePath of data type string designates the path to the PLMXML file containing the desired information.

Return Value

The return value is an array of data type string .

- If the array is empty, Plant Simulation did not find a kinematics root. This can have different reasons, for example a PLMXML file that does not contain any kinematics information or whose kinematics are incomplete.
- If the array contains a single name, the file contains a unique kinematics root.
- If the array contains several names, several ways exist for interpreting the structure which are indistinguishable without context.

Note The same name can occur several times.

**Example**

```simtalk
var roots :
string[] := getPotentialPLMXMLKinematicRoots("D:\kin.plmxml")
print roots.dim, roots[1]
```

See also

applyPLMXMLKinematicStructure [SimTalk]

