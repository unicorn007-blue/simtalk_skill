#### Tab Appearance of the Store

##### Appearance of the Store

Set the configuration of the Store in 3D on the tab Appearance of the Store .

The Store has simulation dimensions of 3 times 3 times 1 by default.

<!-- image -->

<!-- image -->

**Note**

Graphic inheritance and appearance do not influence each other. This means that the graphic can also be inherited for objects with automatically generated graphics, for example to inherit graphic groups which you can show in addition to the default graphic group .

When 3D automatically generates the graphic, this always refers to the default alternative graphic named default , which is thus excluded from graphic inheritance. This applies to length-oriented objects , to the objects Comment and Variable , and to folders.

**You can:**

- Automatically create graphics by selecting or clearing Auto Graphics Active .
- Select the Type of the Store .
- Type in the X -dimension of the Store/individual slots .
- Type in the Y -dimension of the Store/individual slots .
- Type in the Z -dimension of the Store/individual slots .
- Select the Origin for the graphic and the MU animation in the X-direction or the Y-direction. This way you can set if the insertion point of the object represents the center or the left/lower or the right/upper border of the graphic and the MU animation .

- Type in the Gap between the individual slots of the Store .
- Type in the Floor Thickness of the floor of the Store .
- Type in the Board Thickness of the storage boards of the Store .
- Type in the Board Thickness of the Store .
- Type in the Storage Area Material of the Store .
- Type in the Post and Spacing Material of the Store .

**See also**

Simulation properties of the Store [object]

\_\_Accessing the Appearance of the Store

##### Auto Graphics Active

To make Auto Graphics Active , select this check box, and click OK or Apply .

<!-- image -->

The check box also activates or deactivates automatically generated animation graphics.

Select the check box to automatically distribute the MUs across the Store and to ignore existing MU animation paths for the MU animation .

SimTalk

**\_3D.ScaleAutomatically [SimTalk]**

Type [drop-down list] - Store

Select the Type of the Store .

By default, the Store has the simulation dimensions of 3 times 3 times 1.

<!-- image -->

For the non-dynamic types you type in the total dimensions of the Store in the three dimensions X , Y , and Z .

- Floorspace : 3D places the parts on a single flat surface, either on the floor ( Height close to 0) or elevated in space ( Height greater than 0).
- Rack with round posts : 3D puts the parts onto shelves that are placed on round posts.

<!-- image -->

<!-- image -->

- Rack with square posts : 3D puts the parts onto shelves that are placed on square posts.

<!-- image -->

For the dynamic types you type in the slot dimensions of each rack by of the Store in the three dimensions X , Y , and Z . You can also type in the Gap between them, the Floor Thickness , the Board Thickness , and the Ground Clearance .

- Floorspace (dynamic) : 3D puts the parts on a single flat plane, either on the floor (Z-dimension close to 0) or elevated in space (Z-dimension greater than 0). The Store dynamically adjusts its size when you change its capacity in 2D.
- Here you can enter the Gap and the Floor Thickness .

<!-- image -->

- Rack with round posts (dynamic) : 3D puts the parts in rack bays which are placed on round posts. The Store dynamically adjusts its size when you change its capacity in 2D.
- Here you can type in the Gap , the Board Thickness , and the Ground Clearance .

3D adds the post diameter to the bay width ( Y slot dimension ).

<!-- image -->

- Rack with square posts (dynamic) : 3D puts the parts in rack bays which are placed on square posts. The Store dynamically adjusts its size when you change its capacity in 2D.
- Here you can type in the Gap , the Board Thickness , and the Ground Clearance .
- 3D adds the post diameter to the bay width ( Y slot dimension ).

##### Type [drop-down list] - Store

**SimTalk**

\_3D.StoreType [SimTalk]

createRack [SimTalk]

Video on YouTube

[https://youtu.be/ISYfZMdQp3w?si=SObd6u83rdQwbz8n&amp;t=58](https://youtu.be/ISYfZMdQp3w?si=SObd6u83rdQwbz8n&t=58)

<!-- image -->

X [text box] - Store, 3D

Type in the X-Dimension of the Store .

For a non-dynamic Store type the value designates the width of the entire Store .

<!-- image -->

For a dynamic Store type the value designates the width of an individual rack bay/slot of the Store .

<!-- image -->

**SimTalk**

\_3D.Dimensions [SimTalk] - Store

Video on YouTube

[https://youtu.be/ISYfZMdQp3w?si=MvZCKcDB-EywGDXc&amp;t=120](https://youtu.be/ISYfZMdQp3w?si=MvZCKcDB-EywGDXc&t=120)

Y [text box] - Store, 3D Y [text box] - Store, 3D

Type in the Y-Dimension of the Store .

For a non-dynamic Store type the value designates the width of the entire Store .

<!-- image -->

For a dynamic Store type the value designates the width of an individual rack bay/slot of the Store .

<!-- image -->

**SimTalk**

\_3D.Dimensions [SimTalk] - Store

Video on YouTube

[https://youtu.be/ISYfZMdQp3w?si=MvZCKcDB-EywGDXc&amp;t=120](https://youtu.be/ISYfZMdQp3w?si=MvZCKcDB-EywGDXc&t=120)

Z [text box] - Store, 3D

Type in the Z-Dimension of the Store .

For a non-dynamic Store type the value designates the width of the entire Store .

<!-- image -->

For a dynamic Store type the value designates the width of an individual rack bay/slot of the Store .

<!-- image -->

**SimTalk**

\_3D.Dimensions [SimTalk] - Store

Video on YouTube

[https://youtu.be/ISYfZMdQp3w?si=MvZCKcDB-EywGDXc&amp;t=120](https://youtu.be/ISYfZMdQp3w?si=MvZCKcDB-EywGDXc&t=120)

**Origin [graphic]**

##### Origin [graphic]

Select the Origin of the graphic in the X-Direction or the Y-Direction . The origin determines where Plant Simulation inserts the graphic of the Store .

The Origin X sets the point in the X-Direction from which on the Store increases or decreases its size when you change its X-Dimension .

The Origin Y sets the point in the Y-Direction from which on the Store increases or decreases its size when you change its Y-Dimension .

<!-- image -->

<!-- image -->

<!-- image -->

| Origin X               | Origin Y               | Capacity 3 times 3   | Capacity 4 times 3   |
|------------------------|------------------------|----------------------|----------------------|
| Center default setting | Center default setting |                      |                      |
| Left                   | Bottom                 |                      |                      |
| Left                   | Top                    |                      |                      |
| Left                   | Center                 |                      |                      |
| Right                  | Bottom                 |                      |                      |

**Origin [graphic]**

<!-- image -->

| Origin X   | Origin Y   | Capacity 3 times 3   | Capacity 4 times 3   |
|------------|------------|----------------------|----------------------|
| Right      | Top        |                      |                      |
| Right      | Center     |                      |                      |

**SimTalk**

\_3D.OriginX [SimTalk]

\_3D.OriginY [SimTalk]

Video on YouTube

[https://youtu.be/ISYfZMdQp3w?si=DqtD1HO635e\_KZQY&amp;t=155](https://youtu.be/ISYfZMdQp3w?si=DqtD1HO635e_KZQY&t=155)

##### Gap [rack]

Type in the Gap , i.e., the distance between the individual rack bays for the dynamic store types .

Leave the text box empty to not insert any areas between the individual rack bays.

<!-- image -->

Leave the text box empty to insert a borderline but no gaps between the rack bays of a Store with the setting Floorspace (dynamic) . The borderline is part of the area on which the goods can be placed.

Type in a value for the Gap , i.e., for the width of the gaps between the rack bays and the width of the outer border of the Store . Here the borderline is not part of the area on which goods can be placed.

The value for the gaGapp also sets the post diameter . Leave the text box empty to use a default post diameter of 4 cm. Here the post area is part of the areas on which parts can be placed. Type in a value so that the posts are not part of the area on which goods can be placed. For dynamic rack types we add the post diameter to the bay width .

<!-- image -->

**SimTalk**

\_3D.Gap [SimTalk]

**Gap [rack]**

**Video on YouTube**

[https://youtu.be/ISYfZMdQp3w?si=ULV9xW27BwwfqMHw&amp;t=141](https://youtu.be/ISYfZMdQp3w?si=ULV9xW27BwwfqMHw&t=141)

##### Floor Thickness

Type in the Thickness of the floor plate under the floor space of the Store .

**Note**

This setting only applies for the Store Type &gt; Floorspace (dynamic) .

<!-- image -->

**SimTalk**

\_3D.FloorThickness [SimTalk]

##### Board Thickness

Type in the Thickness of the individual shelves of the Store .

**Note**

This setting only applies for the Store Types &gt; Rack with round/square posts (dynamic) .

<!-- image -->

**SimTalk**

\_3D.FloorThickness [SimTalk]

##### Ground Clearance

Type in the Ground Clearance of the Store .

This is the distance between the lower edge of the lowest shelf and the floor on which the rack stands.

Type in 0 so that the lowest shelf rests flat on the floor.

**Note**

This setting only applies for the Store Types &gt; Rack with round/square posts (dynamic) .

<!-- image -->

<!-- image -->

SimTalk

**\_3D.GroundClearance [SimTalk]**

Storage Area Material

Storage Area Material

Click into the color palette next to Storage Area Material to assign a color to the storage area of the Store in the Dialog Box Material .

Dialog Material

Dialog Box Material [storage area]

The dialog box shows the same settings as the tab Material .

<!-- image -->

<!-- image -->

| Command                                       | Attribute                                      |
|-----------------------------------------------|------------------------------------------------|
| Material Active [check box] - graphic         | _3D.StorageAreaMaterialActive [SimTalk]        |
| Diffuse Color [material]                      | _3D.StorageAreaMaterialDiffuseColor [SimTalk]  |
| Ambient Color [material]                      | _3D.StorageAreaMaterialAmbientColor [SimTalk]  |
| Specular Color [material]                     | _3D.StorageAreaMaterialSpecularColor [SimTalk] |
| Emissive Color [material]                     | _3D.StorageAreaMaterialEmissiveColor [SimTalk] |
| Transparency [material]                       | _3D.StorageAreaMaterialTransparency [SimTalk]  |
| Shininess [material]                          | _3D.StorageAreaMaterialShininess [SimTalk]     |
| Copy the Current Material Settings [material] | -                                              |
| Paste a Previously Copied Material            | -                                              |

**See also**

##### Material [tab]

Set the Material of a Graphic

##### Post and Spacing Material

Post and Spacing Material

Click into the color palette next to Post and Spacing Material to assign a color to the posts of the Store in the Dialog Box Material .

###### Dialog Material

Dialog Box Material [post]

The dialog shows the same settings as the tab Material .

<!-- image -->

<!-- image -->

| Command                                       | Attribute                               |
|-----------------------------------------------|-----------------------------------------|
| Material Active [check box] - graphic         | _3D.PostMaterialActive [SimTalk]        |
| Diffuse Color [material]                      | _3D.PostMaterialDiffuseColor [SimTalk]  |
| Ambient Color [material]                      | _3D.PostMaterialAmbientColor [SimTalk]  |
| Specular Color [material]                     | _3D.PostMaterialSpecularColor [SimTalk] |
| Emissive Color [material]                     | _3D.PostMaterialEmissiveColor [SimTalk] |
| Transparency [material]                       | _3D.PostMaterialTransparency [SimTalk]  |
| Shininess [material]                          | _3D.PostMaterialShininess [SimTalk]     |
| Copy the Current Material Settings [material] | -                                       |
| Paste a Previously Copied Material            | -                                       |

<!-- image -->

