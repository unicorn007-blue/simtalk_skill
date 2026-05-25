### Accessing Global Functions in 3D

#### \_\_Accessing General 3D Functions

SimTalk provides the general 3D functions listed in the table of contents to the left.

**See also**

\_Miscellaneous Global Functions

#### close3D [SimTalk]

Exits 3D .

Type

Function

Syntax

```simtalk
close3D([SaveModel:boolean]) → boolean
```

**Parameter**

The optional parameter SaveModel of data type boolean sets if the 3D model will be saved or not.

- Specify true to save the model.
- Specify false to not save the model.

If you do not specify the optional parameter SaveModel , Plant Simulation will ask if you want to save the model.

**Return Value**

The return value has the data type boolean .

true if Plant Simulation successfully saved the model.

false if it failed to save it.

The function may fail because:

- It was called without the parameter, and you clicked Cancel when asked if you want to save the model. Then, the model was not closed.
- It was called with the parameter true , but Plant Simulation could not save the model. In this case 3D will be closed without saving the model.

**Example**

close3D(true)

**close3D [SimTalk]**

See also is3DOpen [SimTalk] open3D [SimTalk]

#### is2DOpen [SimTalk]

Returns if 2D has been started (true) or not (false).

Type

Function

Syntax

is2DOpen → boolean

Return Value

The return value has the data type boolean .

false for a 3D Only model .

Otherwise true.

Example

print is2DOpen

See also

is3DOpen [SimTalk]

#### is3DOpen [SimTalk]

Returns if 3D has been started (true) or not started(false).

Type

Function

Syntax

is3DOpen → boolean

Return Value

The return value has the data type boolean .

Example

print is3DOpen

See also

close3D [SimTalk]

open3D [SimTalk]

is2DOpen [SimTalk]

#### open3D [SimTalk]

Starts 3D for the model in which you run this method.

Type

Function

Syntax

open3D

Example

open3D

See also

Activate 3D

close3D [SimTalk]

is3DOpen [SimTalk]

**Accessing PLMXML Kinematics Files**

