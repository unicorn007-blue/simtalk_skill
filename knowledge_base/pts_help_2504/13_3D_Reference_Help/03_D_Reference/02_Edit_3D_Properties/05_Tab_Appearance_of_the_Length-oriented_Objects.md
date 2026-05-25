#### Tab Appearance of the Length-oriented Objects

Appearance of the Length-oriented Objects

Define configuration settings for the length-oriented objects on the tab Appearance .

Here you can specify the Configuration settings of the different conveyor types.

<!-- image -->

**You can:**

- Open and edit the Segments table of the length-oriented object .
- Specify the Base Height of the length-oriented object .
- Specify the Width of the length-oriented object .

- Select the Type of Conveyor which you want to insert into your simulation model.

Depending on the type you select, the dialog shows settings for the legs , the lanes , and the support frame around the object pertaining to the selected type. When you click Apply , 3D inserts the configured length-oriented object into the scene.

The Tab Appearance looks like this for an object of type Conveyor by default.

The Tab Appearance looks like this for an object of type Track by default.

<!-- image -->

<!-- image -->

The Tab Appearance looks like this for an object of type TwoLaneTrack by default.

<!-- image -->

The Tab Appearance looks like this for an object of type Footpath by default.

<!-- image -->

The Tab Appearance looks like this for an object of type Pipe by default.

<!-- image -->

SimTalk \_3D.ExtConfiguration [SimTalk] See also \_\_Accessing Length-oriented Objects Edit Length-oriented Objects Precisely Model Differences in Height Between Conveying Elements Model a Spiral Conveyor Video on YouTube

[https://youtu.be/jHOZhlwGhkQ?si=h\_U43w9dkxU0Oks6&amp;t=308](https://youtu.be/jHOZhlwGhkQ?si=h_U43w9dkxU0Oks6&t=308)

Segments [tab Appearance] - 3D

To show the values of the individual segments of the selected length-oriented object, click Segments .

<!-- image -->

You can edit some of the values while you can only view others.

The settings of the segments table are described in detail under Segments in the 2D part of the Plant Simulation Help .

<!-- image -->

SimTalk

\_3D.getExtSegments [SimTalk]

\_3D.setExtSegments [SimTalk]

See also

Segments [curve] - 2D, described

Edit Length-oriented Objects Precisely

Change the Shape of the Pipes

Model Differences in Height Between Conveying Elements

Model a Spiral Conveyor

**Base Height [tab Appearance]**

##### Base Height [tab Appearance]

Type in the Base Height of the length-oriented object .

<!-- image -->

The Base Height sets the distance between the insertion height (z-coordinate) of the length-oriented object and the height of a segment whose ΔZ equals 0.

Here the Base Height is 1 meter for all segments.

<!-- image -->

Here the Base Height is 1 meter for the first segment, Index number 2.

<!-- image -->

We then specified an Anchor Point Height of 1.5 meters for the second and third segments. The Anchor Point Height in 2D corresponds to the Base Height in 3D.

<!-- image -->

The fourth and fifth segments have a Base Height of 1 again as you can see in the column Z [m] in the Segments table.

<!-- image -->

The Base Height can be inherited, meaning that you can define it once in the class instead of having to define it for each instance individually. The z-coordinate defines the floor of the installation and the base height defines the distance of the legs from the floor. By changing the setting ΔZ in the Segments Table, you can add an additional offset. The setting ΔZ also affects the simulation time in 2D.

**Note**

Normally, the Base Heights in 2D and in 3D are identical. They might differ if you clear Connect 2D and 3D Positions under Edit 3D Properties &gt; Tab Transformation &gt; Position in a 2D and 3D model .

<!-- image -->

SimTalk

\_3D.BaseHeight [SimTalk] - 3D

See also

Segments [tab Appearance] - 3D

Base Height [curve]

Insert Curved and Straight Segments &gt; anchor point height

Model Differences in Height Between Conveying Elements

Model a Spiral Conveyor

<!-- image -->

<!-- image -->

Width [tab Appearance]

Type in the Width of the length-oriented object .

Changing the Width here also changes the Width in the dialog simulation settings .

SimTalk

\_3D.Width [SimTalk]

See also

Width [text box] - AngularConverter in 2D

Configuration

Configuration [inheritance] - Conveyor

The inheritance check box turns inheritance of the Configuration settings of the length-oriented object off or on.

<!-- image -->

- A green check box means that inheritance is turned on. Then the object inherits, i.e., uses, settings of the parent object from which it was derived. When you change the settings of the parent object, Plant Simulation also changes the respective settings of the child object.
- An orange check box with a minus means that inheritance is turned off.

**You can:**

- Select the Type of conveyor you want to create and the settings that pertain to that length-oriented object .
- Select settings for the Legs of the length-oriented object .
- Select settings for the Lanes of the length-oriented object .
- Select settings for the Frame of the length-oriented object .

The different length-oriented objects provide different configuration settings.

SimTalk

createExtrusionGraphic [SimTalk]

**\_3D.ExtConfiguration [SimTalk]**

###### Conveyor type

Type [drop-down list] - conveyor

Select the Type of conveyor you want to use in your simulation model.

<!-- image -->

You can define the following conveyor types for the length-oriented objects :

- User-defined [Conveyor type]
- Track [appearance in 3D] , is the default setting for the Track and the TwoLaneTrack
- Belt conveyor
- Guide-railed belt conveyor
- Roller conveyor
- Rail conveyor
- Tube conveyor
- Chute conveyor
- Suspension track

Depending on the type you select, the dialog shows the settings pertaining to that type. When you click Apply , 3D inserts the configured length-oriented object into the scene.

**Note**

Depending on the material of the lane , the material flow arrow might be hard to see. To fix that, change the material of the lane to show the material flow arrow more prominently.

**Video on YouTube**

[https://youtu.be/jHOZhlwGhkQ?si=h\_U43w9dkxU0Oks6&amp;t=308](https://youtu.be/jHOZhlwGhkQ?si=h_U43w9dkxU0Oks6&t=308)

**User-defined [Conveyor type]**

For a length-oriented object of type user-defined , you can add , edit , or delete , export , and import extrusion profiles on the tab itself.

Extrusion designates the process of stretching a flat 2D shape in the horizontal direction to create a 3D shape in the scene window.

<!-- image -->

- To add a new extrusion profile, click Add . Then type in the name of the profile into the text box Configuration Name in the dialog that opens. 3D adds the new profile with this name to the bottom of the list.
- To delete the extrusion profile that you selected in the list, click Delete .
- To edit the extrusion profile that you selected in the list, click Edit in the cell below Profile .

<!-- image -->

- To export the settings of the entire extrusion profile, click Export . Type the name of the file to be exported in the dialog Save As and click Save . The file has the extension *.pslist.
- To import the settings of an extrusion profile that you exported, click Import . Select the .pslist file to be imported in the dialog Open and click Open .

The list on the tab shows these settings for the selected conveyor:

| Column/Assignment Value in   | Description                                                                                  |
|------------------------------|----------------------------------------------------------------------------------------------|
| Name                         | Is the name of the profile. For new profiles this is the name you entered as the path name . |
| Type                         | Select the profile type of the selected profile.                                             |

<!-- image -->

| Column/Assignment Value in   | Description                                                                                                                                                                                                                                                                                                                                                                                                                               |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Profile                      | Click Edit to edit the selected profile.                                                                                                                                                                                                                                                                                                                                                                                                  |
| Material                     | In the subtable Material , which you can open by double-clicking in the cell Material , you can set the following: The Diffuse Color [MUs] , compare makeRGBValue . The Ambient Color [MUs] . The Specular Color [MUs] . The Emissive Color [MUs] . The Transparency .                                                                                                                                                                    |
| Start Offset                 | Is the offset of the start reference in the extrusion direction.                                                                                                                                                                                                                                                                                                                                                                          |
| End Offset                   | Is the offset of the end reference in the extrusion direction.                                                                                                                                                                                                                                                                                                                                                                            |
| Repetition Interval          | For the configuration types 14, 15, 16, 17, 18, 19, 22, and 23 the value 0 means that the extrusion is being generated once at the start point of the object. A value greater than 0 means that the extrusion is generated every number of meters that you type in. If you type in 0.5 , the extrusion will be generated every 50 cm along the path. For the other values, this value is meaningless and Plant Simulation only accepts 0. |
| Graphic Group ID             | By default this value is 0. A value between 0 and 10 generates additional graphic groups into which the program places these thus marked extrusions. The Fluid object Pipe for example uses this feature.                                                                                                                                                                                                                                 |

You can select one of these profile types:

| Name/Value for Assignment   | Description                                                                                                                                   |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| Path, z max, Move abs / 0   | Extrude once along the path with z as defined in the anchors, the distance from the edge remains fixed when changing the width.               |
| Path, z max, Move rel / 1   | Extrude once along the path with z as defined in the anchors and pin the profile base point to its relative position when changing the width. |
| Path, z max, Scale x / 2    | Extrude once along the path with z as defined in the anchors and scale in the x-direction when changing the width.                            |

| Name/Value for Assignment               | Description                                                                                                                                                              |
|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Path, z max, Scale xy / 3               | Extrude once along the path with z as defined in the anchors and scale in the x-direction and the y-direction when changing the width.                                   |
| Path, Floor, Move abs / 4               | Extrude once along the path with z = 0.0, the distance from the edge remains fixed when changing the width.                                                              |
| Path, Floor, Move rel / 5               | Extrude once along the path with z = 0.0 and pin the profile base point to its relative position when changing the width.                                                |
| Path, Floor, Scale x / 6                | Extrude once along the path with z = 0.0 and scale in the x-direction when changing the width.                                                                           |
| Path, Floor, Scale xy / 7               | Extrude once along the path with z = 0.0 and scale in the x-direction and the y-direction when changing the width.                                                       |
| Horizontal, Anchors, z max, Move / 8    | Extrude horizontally for every anchor point with z as defined in the anchors and pin to the borders when changing the width. The graphic tilts according to the incline. |
| Horizontal, Anchors, z max, Scale / 9   | Extrude horizontally for every anchor point with z as defined in the anchors and pin to the center when changing the width. The graphic tilts according to the incline.  |
| Horizontal, Anchors, z 1/5, Move / 10   | Extrude horizontally for every anchor point with z = 1/5 of the anchor point height and pin to the borders when changing the width.                                      |
| Horizontal, Anchors, z 1/5, Scale / 11  | Extrude horizontally for every anchor point with z = 1/5 of the anchor point height and pin to the center when changing the width.                                       |
| Horizontal, Anchors, Floor, Move / 12   | Extrude horizontally for every anchor point with z = 0.0 and pin to the borders when changing the width.                                                                 |
| Horizontal, Anchors, Floor, Scale / 13  | Extrude horizontally for every anchor point with z = 0.0 and pin to the center when changing the width.                                                                  |
| Horizontal, Interval, z max, Move / 14  | Extrude horizontally with a fixed interval with z as defined in the anchors and pin to the borders when changing the width. The graphic tilts according to the incline.  |
| Horizontal, Interval, z max, Scale / 15 | Extrude horizontally with a fixed interval with z as defined in the anchors and pin to the center when changing the width. The graphic tilts according to the incline.   |
| Horizontal, Interval, z 1/5, Move / 16  | Extrude horizontally with a fixed interval with z = 1/5 of the anchor point height and pin to the borders when changing the width.                                       |
| Horizontal, Interval, z 1/5, Scale / 17 | Extrude horizontally with a fixed interval with z = 1/5 of the anchor point height and pin to the center when changing the width.                                        |
| Horizontal, Interval, Floor, Move / 18  | Extrude horizontally with a fixed interval with z = 0.0 and pin to the borders when changing the width.                                                                  |

| Name/Value for Assignment               | Description                                                                                                                                                             |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Horizontal, Interval, Floor, Scale / 19 | Extrude horizontally with a fixed interval with z = 0.0 and pin to the center when changing the width.                                                                  |
| Vertical, Floor, Anchors, Move / 20     | Extrude vertically for every anchor point from the path anchor to the floor and pin to the borders when changing the width.                                             |
| Vertical, Floor, Anchors, Fix / 21      | Extrude vertically for every anchor point from the path anchor to the floor and pin to the center when changing the width.                                              |
| Vertical, Interval, Move / 22           | Extrude vertically with a fixed interval from the path anchor to the floor and pin to the borders when changing the width.                                              |
| Vertical, Interval, Fix / 23            | Extrude vertically with a fixed interval from the path anchor to the floor and pin to the center when changing the width.                                               |
| Forward, z max, Anchors, Move abs / 24  | Repeatedly extrude a small segment in the path direction for each anchor point, the distance from the borders remains fixed when changing the width.                    |
| Forward, z max, Anchors, Move rel / 25  | Repeatedly extrude a small segment in the path direction for each anchor point, and pin the base point of the profile to its relative position when changing the width. |
| Forward, z max, Anchors, Fix / 26       | Repeatedly extrude a small segment in the path direction for each anchor point, the distance from the center remains fixed when changing the width.                     |
| Forward, z max, Interval, Move abs / 27 | Repeatedly extrude a small segment in the path direction with a fixed interval, the distance from the borders remains fixed when changing the width.                    |
| Forward, z max, Interval, Move rel / 28 | Repeatedly extrude a small segment in the path direction with a fixed interval, and pin the base point of the profile to its relative position when changing the width. |
| Forward, z max, Interval, Fix / 29      | Repeatedly extrude a small segment in the path direction with a fixed interval, the distance from the center remains fixed when changing the width.                     |
| Vertical, z max, Anchors, Move / 30     | Extrude vertically for each anchor point at the height of the path anchor point and pin to the borders when changing the width.                                         |
| Vertical, z max, Anchors, Fix / 31      | Extrude vertically for each anchor point at the height of the path anchor point and pin to the center when changing the width.                                          |
| Vertical, z max, Interval, Move / 32    | Extrude vertically with a fixed interval at the height of the path anchor point and pin to the borders when changing the width.                                         |
| Vertical, z max, Interval, Fix / 33     | Extrude vertically with a fixed interval at the height of the path anchor point and pin to the center when changing the width.                                          |

| Name/Value for Assignment                 | Description                                                                                                                                                                          |
|-------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Forward, Floor, Anchors, Move abs / 34    | Repeatedly extrude a small segment in the path direction for each anchor point with z = 0.0, the distance from the borders remains fixed when changing the width.                    |
| Forward, Floor, Anchors, Move rel / 35    | Repeatedly extrude a small segment in the path direction for each anchor point with z = 0.0, and pin the base point of the profile to its relative position when changing the width. |
| Forward, Floor, Anchors, Fix / 36         | Repeatedly extrude a small segment in the path direction for each anchor point with z = 0.0, the distance from the center remains fixed when changing the width.                     |
| Forward, Floor, Interval, Move abs / 37   | Repeatedly extrude a small segment in the path direction with a fixed interval with z = 0.0, the distance from the borders remains fixed when changing the width.                    |
| Forward, Floor, Interval, Move rel / 38   | Repeatedly extrude a small segment in the path direction with a fixed interval with z = 0.0, and pin the base point of the profile to its relative position when changing the width. |
| Forward, Floor, Interval, Fix / 39        | Repeatedly extrude a small segment in the path direction with a fixed interval with z = 0.0, the distance from the center remains fixed when changing the width.                     |
| Vertical, Ceiling, Anchors, Move / 40     | Extrude vertically for each anchor point from the path anchor point to the ceiling and pin to the borders when changing the width. The end offset denotes the ceiling height.        |
| Vertical, Ceiling, Anchors, Fix / 41      | Extrude vertically for each anchor point from the path anchor point to the ceiling and pin to the center when changing the width. The end offset denotes the ceiling height.         |
| Vertical, Ceiling, Interval, Move / 42    | Extrude vertically with a fixed interval from the path anchor point to the ceiling and pin to the borders when changing the width. The end offset denotes the ceiling height.        |
| Vertical, Ceiling, Interval, Fix / 43     | Extrude vertically with a fixed interval from the path anchor point to the ceiling and pin to the center when changing the width. The end offset denotes the ceiling height.         |
| Horizontal, Anchors, z max Gr, Move / 44  | Extrude horizontally for each anchor point with z as defined in the anchor points and pin to the borders when changing the width.                                                    |
| Horizontal, Anchors, z max Gr, Scale / 45 | Extrude horizontally for each anchor point with z as defined in the anchor points and pin to the center when changing the width.                                                     |

| Name/Value for Assignment                  | Description                                                                                                                        |
|--------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
| Horizontal, Interval, z max Gr, Move / 46  | Extrude horizontally with a fixed interval with z, as defined in the anchor points and pin to the borders when changing the width. |
| Horizontal, Interval, z max Gr, Scale / 47 | Extrude horizontally with a fixed interval with z, as defined in the anchor points and pin to the center when changing the width.  |

**SimTalk**

createExtrusionGraphic [SimTalk]

\_3D.ExtConfiguration [SimTalk]

**Track [appearance in 3D]**

**Track [appearance in 3D]**

For a length-oriented object of type Track , you can type in its Base Height and its Width .

You can also select settings for its Legs and for its Lanes .

<!-- image -->

**Belt conveyor**

For a length-oriented object of type belt conveyor , you can type in its Base Height and its Width .

You can also select settings for its Legs , for its Lanes , and for the Support frame around it.

<!-- image -->

##### Width [tab Appearance]

**Guide-railed belt conveyor**

For a length-oriented object of type guide-railed belt conveyor , you type in its Base Height and its Width .

You can also select settings for its Legs .

The Guide-railed belt conveyor is often used in the Food and Beverage Industry.

<!-- image -->

You can define these settings for the belt of the conveyor:

- Click Material and select settings for the material of the belt proper of the conveyor.

- Type in the Width and the Height of the belt proper.
- Click Material and select settings for the material of the carrier on which the belt proper of the conveyor runs.
- Type in the Height of the carrier .

<!-- image -->

You can define these settings for the guide as such and for the guide rails of the guide of the conveyor:

- Click Material and select settings for the material of the guide rails of the conveyor.
- Type in the Height of the guide rails of the conveyor. The height is measured starting at the upper edge of the carrier.
- Type in the Diameter of the mounts of the guide rails of the conveyor.
- Type in the Distance of the individual mounts from each other.

<!-- image -->

SimTalk

**\_3D.ExtConfiguration [SimTalk]**

See also

Define the Animation Area of a Simulation Object

Base Height [tab Appearance]

Width [tab Appearance]

**Roller conveyor**

For a length-oriented object of type roller conveyor , you can type in its Base Height and its Width .

In addition, you can select settings for its Legs , for its rollers , and for the Support Frame around it.

**You can:**

- Click Material and select the material of the rollers of the conveyor.
- Type in the Diameter of the rollers.
- Type in the Length of the rollers.

<!-- image -->

SimTalk \_3D.ExtConfiguration [SimTalk] See also Base Height [tab Appearance] Width [tab Appearance]

**Rail conveyor**

For a length-oriented object of type rail conveyor , you can type in its Base Height and its Width .

In addition, you can select settings for its Legs , for its Rail Bars and for the Support Frame around it.

**You can:**

- Click Material and select the material of the rail bars of the conveyor.
- Type in the Count , i.e., the number of rail bars you want to insert.
- Type in the Width of the rail bars, i.e. their distance from each other.
- Select if you also want to insert Crossbars for additional stability by activating the check box.
- Click Material and select the material of the crossbars that stabilize the rail bars of the rail conveyor.
- Type in the Distance of the crossbars that stabilize the rail bars against each other.

<!-- image -->

<!-- image -->

- With activated Foundation the conveyor looks like this.

<!-- image -->

<!-- image -->

- You can also create a rail conveyor with railbars but without a foundation. To make the rail conveyor sit flat on the floor, you have to adjust the Base Height .
- With Foundation the rail conveyor looks like this:

<!-- image -->

<!-- image -->

**SimTalk**

\_3D.ExtConfiguration [SimTalk]

See also

Base Height [tab Appearance]

Width [tab Appearance]

**Tube conveyor**

**Tube conveyor**

For a length-oriented object of type tube conveyor , you can type in its Base Height and its Width .

In addition, you can select settings for its Legs and for the tube .

**You can:**

- Click Material and select the material of the tube of the conveyor.
- Type in the Thickness of the material of the tube proper.

<!-- image -->

SimTalk

\_3D.ExtConfiguration [SimTalk]

**See also Base Height [tab Appearance]**

**Width [tab Appearance]**

**Chute conveyor**

**Chute conveyor**

For a length-oriented object of type chute conveyor , you can type in its Base Height and its Width .

In addition, you can select settings for its Legs and for the chute .

**You can:**

- Select the Type of the chute.
- Type in the Thickness of the chute proper.
- For the chute type Rails , you can type in how many rails support the chute, i.e., the count.
- Click Material and select the material of the chute.

<!-- image -->

<!-- image -->

**Suspension track**

**Suspension track**

For a length-oriented object of type suspension track , you can type in its Base Height and its Width .

**In addition, you can:**

- Select the Type of the suspension that suspends the track from the ceiling.
- Select where the suspension is placed along the length of the inserted suspension track, i.e., the Multiplicity :
- On the anchor points of the inserted suspension track.
- With a single pair of legs along the entire length.
- With a repeated fixed distance from each other, i.e., Equidistant . Enter the Distance between the individual pairs of the suspension device.
- Click Material and select the material of the suspension device that suspends the suspension track from the ceiling of the plant.
- Type in the Diameter of the suspension track.
- Type in the Ceiling Height of the suspension track. This is the distance between the suspension track and the ceiling of the plant.
- Click Material and select the material of the rail bars of the conveyor.

<!-- image -->

**Suspension track**

<!-- image -->

**SimTalk**

\_3D.ExtConfiguration [SimTalk]

See also

Base Height [tab Appearance]

Width [tab Appearance]

**Legs**

##### Legs

Select different settings for the legs of the selected conveyor type.

- Select the type of legs which support your conveyor.
- Select where the legs are placed along the length of the inserted conveyor, i.e., the multiplicity :
- On the anchor points of the inserted conveyor.
- With a single pair of legs along the entire length.
- With a repeated fixed distance from each other, i.e., equidistant . Enter the distance between the individual pairs of legs from each other.
- Type in the diameter of the legs.
- Click material and select the material of the legs of the conveyor.

<!-- image -->

<!-- image -->

You can select one of the following leg types for the conveyor:

**· None**

The conveyor has no legs at all, it is suspended in midair.

<!-- image -->

**· Round double-base**

The conveyor has two round legs placed opposite of each other.

<!-- image -->

**· Round H-base**

The conveyor has two round legs placed opposite of each other with crossbars connecting the left and right leg pairs for additional stability.

<!-- image -->

**· Square double-base**

The conveyor has two square legs placed opposite of each other.

<!-- image -->

**· Square H-base**

The conveyor has two square legs placed opposite of each other with crossbars connecting the left and right leg pairs for additional stability.

<!-- image -->

**· Arched T-base**

The conveyor has T-based legs standing on an arched foot.

<!-- image -->

**SimTalk**

\_3D.ExtConfiguration [SimTalk]

<!-- image -->

##### Lanes

Select different settings for the lanes of the selected conveyor type.

- Click material and select the material of the lanes of the conveyor.

**Note**

Depending on the material of the lane , the material flow arrow might be hard to see. To fix that, change the material of the lane to show the material flow arrow more prominently.

- Type in the height of the lanes.

In the screenshot below the lane is shown in red.

<!-- image -->

For the Configuration type &gt; Track Plant Simulation shows the dialog items Count and Markers .

These settings apply to objects of type Conveyor , Track , and TwoLaneTrack .

- Type the number of lanes that the respective object has into the text box Count .
- Click Markers and select the material of the lane markers of the respective object.

In the screenshot below our Conveyor with the Configuration type &gt; Track has three lanes. The yellow dashed lines separate the lanes.

<!-- image -->

**SimTalk**

\_3D.ExtConfiguration [SimTalk]

**Support Frame [Conveyor]**

##### Support Frame [Conveyor]

Select different settings for the Support Frame of the selected conveyor type.

- Click Material and select the material of the support frame around the conveyor.
- Type in the Height of the support frame around the conveyor.
- Type in the Width of the support frame around the conveyor.

In the screenshot below the support frame of the conveyor is shown in blue.

<!-- image -->

**SimTalk**

\_3D.ExtConfiguration [SimTalk]

