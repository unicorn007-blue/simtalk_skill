### Working with Graphics

#### Work with Graphics

Plant Simulation displays objects in 3D with graphics, which are structured in one or several graphic groups.

Graphic groups of objects and Frames consist of one or more graphics and have a name that is unique for this object. This is similar to the 2D icons of the simulation objects. You can define a graphic group to either be external or internal.

External graphic groups represent the object toward the outside, while internal graphic groups are used to decorate the inside of the object. The properties which graphic groups are internal or locked are, together with the graphic structure, an object property that can be inherited. A graphic group can be permanently shown or hidden to allow switching between alternative visual representations. Each simulation object or animatable object contains at least one external graphic group named default and optionally any number of alternative or additional graphic groups, which you can show or hide independent of each other.

In addition, a Frame initially contains one internal graphic group named deco . The visibility of the graphic groups is an object property which can be inherited independent from the graphic structure and the properties internal and locked . You can create, delete, or configure graphic groups on the Tab Graphics in the dialog Edit 3D Properties and in the dialog Show 3D Graphic Structure .

<!-- image -->

<!-- image -->

| Icon looks like this   | means that the graphic group is   |
|------------------------|-----------------------------------|
|                        | visible                           |
|                        | visible                           |
|                        | not visible, as selected          |
|                        | not visible, as selected          |

You can delete and edit each graphic of a graphic group individually. To modify a graphic you can either change it with the mouse in a 3D window or you can specify the new position , the rotation , the scaling , or the material in the dialog Edit 3D Properties of the selected graphic.

**Note**

If you change any graphic or the graphic structure of a class object, this also changes all inherited objects. If you change the graphics of a derived object, this only changes the object in which you make the changes because 3D deactivates graphic inheritance if it has not been deactivated already. As deactivating graphic inheritance causes graphics to be duplicated, we strongly advise you to make changes in the class object as far as possible.

The state graphic in 3D corresponds to the LEDs in 2D . You can create, replace or delete the state graphic on the Tab States in the dialog Edit 3D Properties by selecting the orientation of the states for the state graphic: Horizontal , Vertical , or Off . When you change this setting, 3D always deletes all state graphics and creates new state graphics afterward, which are arranged according to your selection.

<!-- image -->

Back to Visualizing the Material Flow in 3D

#### Inherit Graphics

Object graphics are, as other object properties, data of the object that can be inherited. This means that objects, which inherit their graphics, share the graphics with their parent object and thus preserve memory. Hence graphic changes in the class objects are automatically also visible in derived objects whose graphic inheritance is activated.

Graphic changes in derived objects deactivate graphic inheritance. Then the derived object contains its own, now changed, copy of the object graphic of the parent object and requires additional memory.

The following graphic changes deactivate graphic inheritance:

- Adding or deleting graphic groups or graphics.
- Transforming graphics, i. e., moving, rotating, zooming in or out of graphics.
- Changing the material of graphics.
- Grouping or ungrouping of a graphic group.
- Renaming of a graphic group.
- Changing the graphic group settings internal or locked .

**Note**

As turning graphic inheritance off makes your model file larger and slower from a certain point on, we strongly advise you to make graphic changes in the class object as far as possible.

You can activate or deactivate graphic inheritance as follows:

- By clicking the inheritance check box under Home &gt; Edit 3D Properties &gt; Graphics &gt; Graphic Groups so that it looks like this .
- By clicking Inherit Graphic Groups in the dialog Show Graphic Structure .

<!-- image -->

<!-- image -->

When you turn graphic inheritance on, the object will use the graphics of its parent again and cancel your changes.

When you leave graphic inheritance off, the object keeps its changed graphics of the instance and thus uses more memory.

**See also**

\_3D.InheritGraphics [SimTalk]

Using Inheritance

Back to Work with Graphics

#### Duplicate Graphics

To duplicate the selected graphic, hold down Ctrl+Shift and click the left mouse button in the 3D window at a different position.

Plant Simulation does not create a copy of the graphic, but the new graphic references the duplicated graphic. This considerably reduces memory consumption.

Plant Simulation shows that the graphic is referenced with a diamond in the dialog Show Graphic Structure .

<!-- image -->

#### Edit Grouped Graphics

To move, rotate, or scale several graphics at the same time while retaining their positions to each other, you can group them and manipulate the group as a whole.

**Note**

If you change any graphic or the graphic structure of a class object, this also changes all inherited objects. If you change the graphics of a derived object, this only changes the object in which you make the changes because Plant Simulation turns off graphic inheritance if it has not been deactivated already. As deactivating graphic inheritance causes graphics to be duplicated, we strongly advise you to make changes in the class object as far as possible.

To group several graphics:

- Hold down Shift and click the objects to select them or drag a marquee over them.
- Click Group Graphics on the Edit ribbon tab of 3D or press Ctrl+G . 3D creates a single new group.
- Then, move, rotate, scale, or zoom the group as you do a single graphic.
- Naturally you can also move, rotate, scale, or zoom the group on the Tab Transformation in the dialog Edit 3D Properties .

<!-- image -->

To restore the previous structure of the graphics:

- Select the newly created group.
- Click Ungroup Group of Graphics on the Edit ribbon tab of 3D or press Ctrl+U to replace this group with the contained graphics again.

<!-- image -->

Compare Move an Object Precisely

Compare Move an Object With Keyboard Keys

Compare Move an Object With the Mouse

Back to Work with Graphics

#### Set the Material of a Graphic

You can define the surface qualities, the appearance, i. e., the material of the graphic: How well it reflects light, what color it reflects, and what color it emits.

**Note**

If you change any graphic or the graphic structure of a class object, this also changes all inherited objects. If you change the graphics of a derived object, this only changes the object in which you make the changes because Plant Simulation deactivates off graphic inheritance if it has not been deactivated already. As deactivating graphic inheritance causes graphics to be duplicated, we strongly advise you to make changes in the class object as far as possible.

To define properties of the material of a graphic:

<!-- image -->

- Select the graphic and click 3D Properties on the Home ribbon tab.
- Click the Tab Material and edit the material of the graphic.
- To assign a material to the graphic, select Material Active .
- To apply a Diffuse Color , click the down arrow and select a color in the color selector.

<!-- image -->

The diffuse color is the reflection of light from an uneven surface so that an incident ray is seemingly reflected at a number of angles. It is the complement to specular reflection. If a surface is completely nonspecular, the reflected light will be evenly spread over the hemisphere surrounding the surface.

- To apply an Ambient Color , click the down arrow and select a color in the color selector.

The ambient color is the color of the light reflected from the object when it is lit by another ambient object in the scene.

- To apply a Specular Color , click the down arrow and select a color in the color selector.

The specular color is the reflected color of the object's highlights.

- To apply an Emissive Color , click the down arrow and select a color in the color selector.

The emissive color is the color emitted by the object. A lamp shade might have a base color of yellow. When you turn the lamp on, though, the emissive color might be white.

- To apply a Transparency , enter a value between 0.0 , for opaque, and 1.0 , for completely transparent, into the text box.

The transparency sets how opaque or clear the graphic is. Water, for example, might be more clear than opaque.

**Note**

If your model contains several partially or fully transparent graphics one directly behind the other from your current view point, some or all of these graphics might look wrong or might seem to be missing.

This is due to heuristics without which the rendering performance would drastically decrease.

- To apply a Shininess , enter a value between 0.0 , for a very dull surface, and 1.0 , for a highly polished surface, into the text box.

The shininess sets how sharp light is reflected by the object. A billiard ball, for example, has a large shininess, making for small and sharp highlights.

- To apply the material you selected to the graphic, click Apply .

You also can:

- Copy the Current Material Settings by clicking

.

<!-- image -->

<!-- image -->

- Paste a Previously Copied Material by clicking

.

<!-- image -->

- Remove the Materials in Nested Graphics by clicking

**Note**

When you define materials for a graphic in the graphic structure at different levels in the structure, 3D always uses the material that is located furthest down in the structure for the actual rendering.

Back to Work with Graphics

#### Use a Different Graphic for an Object

In some cases it will suffice to model the machines of your plant with the default graphics we provide for the material flow objects and for the mobile objects. In other cases you will want to replace these default graphics with pictures that resemble the actual machines used in your plant. In some cases you might even have the actual graphics files of these machines from the builder of the machine, which you can then use.

.

**Note**

If you change any graphic or the graphic structure of a class object, this also changes all inherited objects. If you change the graphics of a derived object, this only changes the object in which you make the changes because Plant Simulation deactivates off graphic inheritance if it has not been deactivated already. As deactivating graphic inheritance causes graphics to be duplicated, we strongly advise you to make changes in the class object as far as possible.

We saved the graphics that are part of your program package in s3d format, we already defined animation paths for most of them, and we scaled the objects correctly, so that they match the size of the other objects.

Instead, you can also select a graphic which you created in 3D with the command Export Scene &gt; Export Object .

To show an object with a different graphic, you can do one of the following:

- Exchange the object graphic with another pre-defined object graphic

<!-- image -->

Select the object, and click Exchange Graphics on the Edit ribbon tab of the 3D window or select the command on the context menu.

Plant Simulation opens the dialog Exchange Graphics . By default it opens to the folder where you installed Plant Simulation , namely C:\Program Files\Siemens\Tecnomatix Plant Simulation XX\3D\s3D-graphics . Change to the folder Plant Simulation\3D\s3d-graphics and select one of the s3d files. You might have to open one of the folders within that folder.

Click Open to replace all graphic and animation data of the selected object with data from the selected .s3d-file. This means that all graphic groups, the state graphic, and the animation attributes will be removed from the selected object and graphics and animation attributes of the saved object will be added instead.

Select the .s3D graphic that you want to use.

<!-- image -->

<!-- image -->

To exchange graphics, you can also drag an .s3d -file from a File Explorer window and drop it onto a 3D window .

- Insert the graphic of an existing graphics file

<!-- image -->

Select the graphic, and click Graphics on the Edit ribbon tab of 3D .

Plant Simulation opens the dialog Open . By default it opens to the folder where you installed Plant Simulation , namely C:\Program Files\Siemens\Tecnomatix Plant Simulation XX\3D\jt-graphics .

Select the .jt graphic that you want to use.

Instead, you can also import a graphic which you created in 3D with the command Export Scene &gt; Export Graphics . Or you can import a graphics file that you exported from another 3D modeling program in a format that Plant Simulation can import.

<!-- image -->

After Plant Simulation inserted the imported graphics, it will add them to the selected graphic group while keeping any already existing graphics. Delete any graphics that you do not need any longer.

To import graphics you can also drag a file of a supported graphic format from a File Explorer window and drop it onto a 3D window .

- Create your own object graphic

<!-- image -->

Open the object, click

Insert Shape on the Edit ribbon tab of 3D

and select the shape that you want to create.

After Plant Simulation inserted the shape you define, it will add it to the selected graphic group while keeping any already existing graphics. Delete any graphics that you do not need any longer.

You can also use graphics from other graphic groups by opening the dialog Show 3D Graphic Structure of the source object, copying the desired graphic with the respective context menu command, and then inserting it into the destination object with Ctrl+V .

- You can also create a complex graphic by inserting multiple shapes or imported graphics and position, rotate, scale, or color them.

Or you can use the icons of the 2D objects and map them to a Textured Plate in 3D .

**Note**

After modifying the object graphics by importing, creating, or transforming them, you might have to adjust the animation paths or the animation points of the 3D object to the new overall graphic. You do not have to do this if you used the command Exchange Graphics .

Compare Import JT Graphics Representing an Object

Back to Work with Graphics

Video on YouTube

[https://youtu.be/K-NEPvShU10?si=ChF\_2xnoMuE1Fq7q&amp;t=730](https://youtu.be/K-NEPvShU10?si=ChF_2xnoMuE1Fq7q&t=730)

#### Creating Your Own Objects

Create Your Own Objects

To create your own object, proceed as follows.

- Duplicate or derive any of the class objects that we provide in Class Library and that have similar properties as the one you would like to create.
- You can then edit the 3D properties of this new class object, so that it fits your needs, for example by using another graphic ( installation folder &gt; 3D &gt; s3d graphics ), work with animation paths , etc.
- Import a three-dimensional graphic from the Plant Simulation graphics library that is part of your program package ( installation folder &gt; 3D &gt; jt graphics ), from your own graphics library, or from a

graphics program that can save files in a format that Plant Simulation can import , into your simulation model. After you imported a graphic that you downloaded from the internet or created in a 3D modeling program, you might have to scale, rotate and move it to the origin of the scene.

You can then transform the graphic into a simulation object. To do so, click the graphic with the right mouse button and select Make Simulation Object . If the thus created simulation object can contain additional simulation objects, you might also want to adjust its animation paths to the changed object graphic, compare Work with Animation Paths .

- Model your own 3D graphic by inserting a shape as often as required, position, rotate, scale or color it. You can also use any graphics from other graphic groups and edit them. If you want to use several graphics for your object graphic, you have to group these individual graphics to be able to transform the group into a simulation object later on. Click the graphic with the right mouse button and select Make Simulation Object . In case the thus created simulation object can include additional simulation objects, you should also adjust its simulation paths to the changed object graphic, compare Working with Animation Paths .
- Create a simulation object with animation to make your simulation model look as close as possible as it its in reality.

**Note**

If you change any graphic or the graphic structure of a class object, this also changes all inherited objects. If you change the graphics of a derived object, this only changes the object in which you make the changes because Plant Simulation deactivates off graphic inheritance if it has not been deactivated already. As deactivating graphic inheritance causes graphics to be duplicated, we strongly advise you to make changes in the class object as far as possible.

Compare Inherit Graphics

Back to Work with Objects in 3D

Import a 3D Graphic

To create your own 3D objects, you can import graphics into your 3D simulation model.

3D can import these file formats:

- All 3D Graphic Files

- JT Files (*.jt)

**Note**

We recommend to use the JT format whenever possible.

- Parasolid Files (*.x\_b; *.x\_t, *.xmt\_bin, *.xmt\_txt)
- IGES Files (*.igs ; *.iges)
- STEP Files (*.stp; *.step)
- VRML Files (*.wrl)
- STL Files (*.stl)
- Catia V4 Files (*.exp; *.model)
- CAD Layout Files (*.dgn, *.dwg, *.dxf)

To import a graphic that contains animation structures which you, or a colleague, defined, you can, for example, import JT Files :

- Click Import Graphics on the Edit ribbon tab. Select the respective file type, navigate to the folder that contains the graphic, select it and click Open .

These graphic files can either be files that are part of your program package or files you yourself created with the command Export Graphics .

<!-- image -->

- To replace the graphic of an object with another graphic that contains animation structures:

Click the object with the right mouse button and select Exchange Graphic . Select 3D Files , navigate to the folder that contains the graphic, select it and click Open .

To import a VRML File .

Click Import Graphics on the Edit ribbon tab. Select , navigate to the folder that contains the graphic, select it, and click Open .

<!-- image -->

Compare Add a Graphic and a Color to the Background of the 2D Frame

Back to Create Your Own Objects

Video on YouTube

[https://youtu.be/h2cFAH46ESQ?si=eKZLbWqgeP17LH\_F&amp;t=125](https://youtu.be/h2cFAH46ESQ?si=eKZLbWqgeP17LH_F&t=125)

Model Your Own 3D Graphic

To create your own graphics for a simulation object, insert one or several of these three-dimensional shapes.

Barred Area , Box , Cone , Cuboid , Cylinder , Dimensioning , Factory Walls , Fence , Mezzanine , Rack , Sphere , Stairs , Text , or Textured Plate .

<!-- image -->

- Click the shape you want to create. In our example we create a cuboid .
- Select the Graphic Group to which you want to add the cuboid.
- Type in the Dimension X/Width , the Dimension Y/Depth , and the Dimension Z/Height of the cuboid.

<!-- image -->

- To create the cuboid, click Create . 3D attaches the cuboid to the mouse pointer. Drag the mouse to the position at which you would like to insert it and click the left mouse button. To cancel inserting, click the right mouse button or press Esc .
- To change the position , the rotation , or the scale of the shape after you inserted it, select it and click 3D Properties &gt; Tab Transformation on the Home ribbon tab. Then change the settings according to your needs.
- To set if the cuboid is an obstacle for the worker , select it. Then, click Edit 3D Properties on the Home ribbon tab and click the Tab Graphic Settings .

<!-- image -->

<!-- image -->

- To assign a color and a material, select the cuboid and click 3D Properties on the Home ribbon tab. Then, click the Tab Material .
- To create a more complex graphic, insert several shapes and position, rotate, scale or color them. In addition to the pre-defined shapes you can copy graphics from other graphic groups or import graphics from graphic files.
- To delete the shape from the scene window, click it with the right mouse button and click on the mini toolbar or select Show Graphic Structure .

<!-- image -->

<!-- image -->

If the graphic group to which you added the shape, deco in our case, is not expanded already, expand it. Click the node of the shape you want to delete with the right mouse button. Select Delete .

<!-- image -->

**Note**

When you start to insert a newly created shape into an external graphic group, Plant Simulation automatically activates Show External Graphic Groups until you click the destination position so that you can align the new graphic, which is attached to the mouse pointer, with all other graphics of the destination graphic group.

Compare Create a Textured Plate

Compare Create a Non-textured Plate [example]

Compare Model a Bottle

Back to Create Your Own Objects

##### Create a Textured Plate

**Create a Textured Plate**

**To create a textured plate:**

- Click Textured Plate on the Edit ribbon tab of the 3D window .

For our example we use the rectangular image with the logo. We selected these settings:

<!-- image -->

- Click Create . 3D attaches the textured plate to the mouse pointer. Drag the mouse to the position at which you would like to insert it and click the left mouse button. To cancel inserting, click the right mouse button or press Esc .

The inserted plate looks like this with the settings Orientation &gt; Floor and Fit Texture to Plate .

<!-- image -->

- You can also show the plate with a different Orientation :

<!-- image -->

- When you select Show on Both Sides , 3D shows the image on the top/front and on the bottom/back of the inserted plate.

<!-- image -->

<!-- image -->

- When you select Fit Image Size , and enter 2 tiles for the x-dimension and the y-dimension, 3D inserts two tiles of the image in each dimension.
- To move the textured plate to another position of your choice, click it with the left mouse button and drag the mouse.
- To move the textured plate up on the base plate, hold down Ctrl and press the Up arrow.
- To change the size of the textured plate after you inserted it, select it and click Edit 3D Properties &gt; Tab Transformation on the Home ribbon tab. Then change the scale according to you needs.
- To set if the textured plate is an obstacle for the worker , select it. Then, click Edit 3D Properties on the Home ribbon tab and click the Tab Graphic Settings .
- To assign a material to the textured plate, select it and then click Edit 3D Properties &gt; Tab Material on the Home ribbon tab.

<!-- image -->

**Note**

When you start to insert a newly created shape into an external graphic group, 3D automatically activates Show External Graphic Groups until you click the destination position so that you can align the new graphic at the mouse pointer with all other graphics of the destination graphic group.

**Back to Create Your Own Objects**

##### Create a Non-textured Plate [example]

To create a flat, non-textured plate:

- Click Cuboid on the Edit ribbon tab.
- Enter 0 into the respective text box, to create the plate on this plane.

<!-- image -->

<!-- image -->

- Click Create and proceed as described under Create a Textured Plate to place or move the plate.

**Back to Create Your Own Objects**

Model a Bottle With the 3D shapes Cylinder and Cone Frustum we can put together a bottle or a similar-looking item. To better distinguish the different components of the bottle when putting them together, use easily distinguishable colors.

First, we model the bottom of the bottle with a cylinder:

- Click Cylinder .
- We want to create a flat bottom of the bottle. To do so, we typed in and selected these settings:
- After inserting it, our flat cylinder is gray by default. As this is hard to recognize on the gray grid plate and the gray background of the Frame , we assigned it another color.

<!-- image -->

<!-- image -->

In the second step we model the body of the bottle. For this use a Cylinder as well.

##### Model a Bottle

- Click Cylinder . Our body of the bottle is a cylinder that is open at the bottom and at the top with these settings:
- After we assigned the inserted cylinder another color, it looks like this:

<!-- image -->

<!-- image -->

In the third step we model the part of the bottle that gets narrower toward the top, the bottleneck:

<!-- image -->

- Click Cone Frustum . We used these settings:

<!-- image -->

- After we assigned the inserted cone frustum another color, it looks like this:

<!-- image -->

In the fourth step we model the cap of the bottle. For this we use a Cylinder :

- Click Cylinder . To make the cap fit the neck of the bottle, it has to have the same radius of the neck, which we designed above. We used these settings:

<!-- image -->

- After we assigned the inserted cylinder another color, it looks like this:

<!-- image -->

The individual parts of our bottle look like depicted below. Now we just have to put the bottle together.

<!-- image -->

- ·
- First, we put the body of the bottle onto the bottom of the bottle . To do so, select the body of the bottle and drag it fairly precisely over the bottom of the bottle . Then click Align to Grid on the Edit ribbon tab. Group these two parts by clicking Group on the Edit ribbon tab.
- Next, we place the bottleneck . To do so, select the bottleneck. Drag it fairly precisely over the bottom part of the bottle. Then click Align to Grid .

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

Now these two parts are located directly above each other, the upper part does not sit flush on the lower part though. To fix this, we have to move the bottleneck downward in the Z-Dimension . Click the bottleneck with the right mouse button and select Edit 3D Properties . Adjust the Z-Dimension until everything fits. We used the settings below.

<!-- image -->

**Group the parts of the bottle.**

- In our last step we place the cap onto the bottleneck . To do so, select the cap. Hold down Ctrl and press the Up arrow on the keyboard to move it upward over the neck of the bottle. Press the Left arrow to place the cap fairly precisely over the neck of the bottle.

<!-- image -->

Then, click Align to Grid . Now the cap is located directly above the bottleneck, and we just have to move it down.

<!-- image -->

<!-- image -->

- Adjust the Z-dimension until everything fits. We used these settings:

<!-- image -->

Back to Create Your Own Objects

#### Set How 3D Shows an Object

Depending on which level of the object hierarchy you open a 3D window, a 3D object can look different. For this reason we differentiate between the outside representation of the object and the inside representation of the object:

- The outside representation of a 3D object designates the entirety of all graphics, which will be selected when you click the object in a 3D window that opened the location of this object.

This includes:

- Its state graphics which are not marked as Internal .
- Its state graphics which you set according to the States Orientation .

When you selected Show Content for the object, this also includes in addition:

- Its state graphics which are marked as Internal .
- The outside representation of those of its contained 3D objects, which are not explicitly excluded from the parent outside representation, i. e., for which you selected Exclude from "Show content" of the Location .
- The inside representation designates the entirety of all Frame graphics, which are visible, when the Frame itself is opened in a 3D window.

**This includes:**

- Its state graphics which are marked as Internal .
- Its state graphics which you set according to the States Orientation .
- The outside representation of its contained 3D objects.

Independent of the representation, a graphic group is generally only visible when you select the check box Visible . It makes sense to initially clear Visible for graphic groups, which you only want to use temporarily for the representation of the object.

<!-- image -->

When editing the object, it might helpful to show the outside representation and the inside representation at the same time. To do so, activate Show External Graphic Groups in a 3D window, which contains the object you are editing.

In addition, you can show or hide all Connectors and Interfaces in the active 3D window by clicking the button Show Connections .

| Graphic Group   | Setting                     | Part of the Inside Representation                                         | Part of the Outside Representation                |
|-----------------|-----------------------------|---------------------------------------------------------------------------|---------------------------------------------------|
| Graphic group   |                             | No                                                                        | No                                                |
| Graphic group   |                             | Yes                                                                       | : yes : no                                        |
| Graphic group   |                             | Show External Graphic Groups on: yes Show External Graphic Groups off: no | Yes                                               |
| Graphic group   |                             | Show External Graphic Groups on: yes Show External Graphic Groups off: no | Only in the location                              |
| Graphic group   | from Connector or Interface | No inside representation available                                        | Show Connections on: yes Show Connections off: no |
| States group    | No settings available       | Yes                                                                       | Show Connections on: yes Show Connections off: no |

The following sample model demonstrates the different ways of representing objects in 3D:

In addition to a number of material flow objects, our model MyPlant contains the Frame named WashingMachine and two instances of the Frame named WorkerCell .

<!-- image -->

The 3D window of the Frame named MyPlant shows the WashingMachine as a green box. The green box is the outside representation of the WashingMachine .

When you open the WashingMachine in a 3D window of its own, it shows its content , namely a Station displaying its states , a Part , two Interfaces , and Connectors . This is the inside representation of the WashingMachine . You can right-click into the background of the 3D window and select Show Structure to show its structure.

<!-- image -->

<!-- image -->

Click Show Connections to hide the Interfaces and Connectors .

<!-- image -->

Click Show External Graphic Groups to also show external graphic groups in the internal representation , allowing you to edit them. In our WashingMachine the graphic group named default is the only graphic group that is not internal but external . You can right-click into the background of the 3D window and select Show Graphic Structure to show its graphic structure.

<!-- image -->

In the outside representation external graphics are always visible, provided you selected the check box Visible .

The content of an object, on the other hand, is only visible, when you selected Show Content for this object, which is not the case for the WashingMachine .

As we selected Show Content for the WorkerCell , its content is visible in its outside representation.

<!-- image -->

Comparing the outside representation of the WorkerCell in the window MyPlant with the inside representation in its own 3D window, namely with the window WorkerCell , you'll notice that the outside representation shows the safety fence and the floor plate, while the inside representation does not show them. This is because these graphics belong to the external graphic group named default and because Show External Graphic Groups is deactivated by default in the window of the WorkerCell .

<!-- image -->

The work tables and the cabinets of the internal graphic group named deco , on the other hand, are also visible in the outside representation because by definition deco belongs to the content of the WorkerCell .

The objects Broker and WorkerPool in the WorkerCell however are visible in the inside representation , but not in the outside representation . This is because the check box is selected by default for these objects.

<!-- image -->

In a sub-Frame , which you inserted into another Frame , and for which you selected Show content , you can press the backspace key to return to the previous scene.

The context menu of a sub-Frame shows commands for the object under the mouse.

<!-- image -->

Compare Work with Graphics

Back to Work with Objects in 3D

#### The 3D Window Shows Which Object When

The table shows when a 3D window shows graphic groups, graphics, sensors, and object states:

| Object is visible                             | when                                        | and                                                      | or/and                                                                           |
|-----------------------------------------------|---------------------------------------------|----------------------------------------------------------|----------------------------------------------------------------------------------|
| External graphic group                        | it is defined as visible                    | the object either is internal and its location is open   | or the object is open in the window or is visible.                               |
| Internal graphic group                        | it is defined as visible                    | the object either is open in the window                  | or the object is visible and displayed with its content.                         |
| Object, no sensor or connection               | it has visible graphic groups               | the object either is open in the window                  | or all its locations contained in the window are visible and show their content. |
| Connection ( Connector , Interface , Marker ) | the window shows connection                 | the connection either is external                        | or their location is open.                                                       |
| Sensor                                        | its location shows sensors                  | a location either is open in the window or it is visible | -                                                                                |
| Object name/object label                      | the window shows object names/object labels | the object shows names and labels                        | and the object is open in a window or is visible.                                |
| Object state (LED)                            | the object is visible                       | the object shows state graphics                          | and the object is in the state which the LED shows.                              |

See also

Set How 3D Shows an Object

#### Using Alternative Graphic Groups

Use Alternative Graphic Groups

In this sample model we show how to model a simplified airplane and how to show the progress of the airplane assembly. To do so, we show the selected graphic groups which graphically display the finished components.

We will solve the following modeling tasks:

- Create a New MU Class for the Object
- Create Alternative Graphic Groups for the Components
- Show the Progress of the Airplane Assembly

**Back to Work with Graphics**

##### Create a New MU Class for the Object

First, we will create a new MU class that represents the airplane we are going to build:

- Open the folder MUs in the Class Library .
- Click the object Container with the right mouse button and select Duplicate .
- Press F2 and rename the newly created Container to Airplane .

<!-- image -->

While you're at it, you can also rename the Frame named Models in the folder Models to MyAirplaneAssembly .

Back to Work with Graphics

##### Create Alternative Graphic Groups for the Components

After creating the MU class Airplane for our model, we will create the graphics of the different components of the airplane. For demonstration purposes we will content ourselves with the shapes that 3D provides. In a real situation, we would naturally use the CAD drawings we received from the engineering department.

- Open the Frame containing our simulation model in 3D , My3DAirplaneAssembly in our case.
- Edit the MU class Airplane . Click it in the Class Library with the right mouse button and select Open in 3D . Click into the background of the Frame .UserObjects.Airplane with the right mouse button and select Edit 3D Properties .

<!-- image -->

**Note**

As we do not need the default graphic of our airplane, the pallet with the name default , we delete this graphic by selecting it and pressing Del .

- Click Add to add a new graphic group . We first want to add the graphic group for the fuselage of the airplane. Type Fuselage into the text box Name .

<!-- image -->

Once you clicked OK in the dialog above and Apply in the dialog Edit 3D Properties , the dialog Show Graphic Structure shows our new graphic group as well.

<!-- image -->

- Now we create the actual graphic that represents the fuselage . Change to the Edit ribbon tab and select Cylinder .
- Select the graphic group to which you want to add the newly created graphic, Fuselage in our case. Enter the dimension of the cylinder and click Create .

<!-- image -->

<!-- image -->

Plant Simulation attaches the cylinder to the cursor in the 3D window .UserObjects.Airplane . Drag it to the position of your choice and click the left mouse button to insert it into the scene window.

**Note**

Make sure that Scale automatically on the tab Transformation is cleared, otherwise Plant Simulation will not show the cylinder with the settings you entered.

- 3D inserts the cylinder in the upright position. This is not what we want though. We need our fuselage to be in the horizontal position. To rotate it by 90 degrees, click it with the right mouse button and select Edit 3D Properties .
- Enter the settings from the screenshot below and click Apply to rotate the fuselage by an angle of 90 degrees on the y-axis.
- In the next step, we are going to add the graphic group for the cockpit of our airplane. Click with the right mouse button in the Frame .UserObjects.Airplane and select Edit 3D Properties . Change to the

<!-- image -->

<!-- image -->

tab Graphics and click Add . Type Cockpit into the text box Name and click OK in the dialog. Then click Apply in the dialog Edit 3D Properties .

<!-- image -->

- Then, create the actual graphic that represents the cockpit . Change to the Edit ribbon tab and select Cone Frustum .

<!-- image -->

Select the graphic group to which you want to add the newly created graphic, Cockpit in our case. Enter the dimension of the cone and click Create . Plant Simulation attaches the cone to the cursor in the 3D window .UserObjects.Airplane . Drag it to the position of your choice and click the left mouse button to insert it into the scene window.

<!-- image -->

- Rotate the Cockpit by 90 degrees and place it at the right-hand side of the fuselage. We used the settings shown the screenshot below.

<!-- image -->

While you're at it, you might also assign the cockpit a color on the tab Material .

- As our airplane also needs a right wing and a left wing , we create these next. Repeat the steps described above.
- Add the graphic group for the right wing .
- Select the graphic group RightWing to which the graphic will be added. Create the actual graphic for the right wing .

<!-- image -->

<!-- image -->

- Place the right wing at the appropriate position on the fuselage. We used the settings below.
- Repeat these steps for the left wing . We used the settings below to place the left wing at the appropriate position on the fuselage.

<!-- image -->

<!-- image -->

- In our last step we are going to create the tail assembly (empennage) consisting of the vertical stabilizer and the horizontal stabilizer (tailplane). Repeat the steps described above.
- ◊ Add the graphic group for the tail assembly .
- ◊ Select the graphic group TailAssembly to which the graphic will be added. Create the actual graphics representing the tail assembly . We used a Cone for the vertical stabilizer and a Sphere for the horizontal stabilizer .

<!-- image -->

<!-- image -->

- ◊ Place the horizontal stabilizer at the appropriate position on the fuselage. We used the settings below. We also scaled the sphere in all three dimensions to stretch and to flatten it.
- ◊ Select the graphic group TailAssembly to which the graphic will be added. Create the graphic representing the vertical stabilizer .

<!-- image -->

<!-- image -->

- ◊ Place the vertical stabilizer at the appropriate position on the fuselage. We used the settings below. We also scaled the cone in the y-dimension.

The dialog Graphic Structure also shows that our tail assembly consists of two graphics.

<!-- image -->

<!-- image -->

Instead of using shapes which we create in 3D itself, we can also Import JT Graphics Representing an Object .

**Back to Work with Graphics**

Displaying the Progress of the Airplane Assembly

Show the Progress of the Airplane Assembly

In our last step we are going to show the progress of the airplane assembly in our plant by successively hiding and showing graphic groups as the airplane moves from processing station to processing station.

We will demonstrate how to:

- Insert and Configure the Source and the Processing Stations
- Program the Visibility Controls
- Change Orientation and Position of the Object on the Stations

**Back to Work with Graphics**

Insert and Configure the Source and the Processing Stations

First, we are going to insert the Source that produces the airplane and the stations that process and assemble it. Connect the stations with Connectors . While you are at it, you might also insert a Method below each of the stations and name them as shown in the screenshot. We will then program the individual methods in the next step.

Our finished model looks like this:

<!-- image -->

- Insert and configure the Source so that it matches the screenshots below. Make sure that it produces a MU of type Airplane . Select the method hidePlane as the Exit Control on the tab Controls .

<!-- image -->

- Insert and configure the Station . Enter a Processing Time of 10 seconds ( 0:10 ). Select the method showFuselage as the Entrance Control on the tab Controls .
- Insert and configure next station, called Station1 . Enter a Processing Time of 10 seconds . Select the method showTailAssembly as the Entrance Control on the tab Controls .
- Insert and configure final station, called Station2 . Enter a Processing Time of 10 seconds . Select the method showWings as the Entrance Control on the tab Controls .

Back to Show the Progress of the Airplane Assembly

Program the Visibility Controls

Next, we are going to program the methods that we use as Exit Control and as Entrance Control of the stations for hiding and showing graphic groups as the airplane moves from station to station. To do so, we will use the attribute Visible .

- Program the method hidePlane , which we use as the Exit Control of the Source . It hides all components of the airplane. Once all components are hidden, it moves the airplane on to the next station.

We entered the following source code:

```simtalk
@._3D.getGraphic("Fuselage").Visible := false
@._3D.getGraphic("Cockpit").Visible := false
@._3D.getGraphic("LeftWing").Visible := false
@._3D.getGraphic("RightWing").Visible := false
@._3D.getGraphic("TailAssembly").Visible := false
@.move -- move the airplane on to the next station
```

- Program the method showFuselage , which we use as the Entrance Control of the station named Station . It shows the fuselage and the cockpit of the airplane.

We entered the following source code:

```simtalk
@._3D.getGraphic("Fuselage").Visible := true
@._3D.getGraphic("Cockpit").Visible := true
```

- Program the method showTailAssembly , which we use as the Entrance Control of the station named Station1 . It shows the tail assembly of the airplane.

We entered the following source code:

```simtalk
@._3D.getGraphic("TailAssembly").Visible := true
```

- Program the method showWings , which we use as the Entrance Control of the station named Station2 . It shows the wings of the airplane.

We entered the following source code:

```simtalk
@._3D.getGraphic("LeftWing").Visible := true
@._3D.getGraphic("RightWing").Visible := true
```

- As we are running the simulation in 3D , we want to see a smooth animation. A Real-time factor of 16 in the dialog of the EventController in our simulation model ensures this.
- Let's run the simulation to check if everything works as intended, which indeed it does.

<!-- image -->

<!-- image -->

**Back to Show the Progress of the Airplane Assembly**

Change Orientation and Position of the Object on the Stations

If you want to, you can also adjust the orientation and the position the airplane on the stations. The default orientation of the airplane looks realistic on a conveyor, modeled for example with a Conveyor . It does not look good on the Stations that we used though.

- First, let's rotate the airplane by 90 degrees to the right. To do so, click the class of the airplane with the right mouse button, and select Open in 3D . Click the right mouse button in the background of the window and select Edit 3D Properties . Enter 90 into the text box Angle on the tab Transformation &gt; Rotation .

<!-- image -->

<!-- image -->

Run the simulation again to show the result of the rotation.

<!-- image -->

- Now let's change the position of the airplane on the stations. This is necessary, because by default 3D places the MUs at the origin of its scene, i.e., the point where the two red lines intersect. This is why the tail of our airplane is placed on the reference point of the stations.

To change the position of the airplane on the stations, open the class of the airplane in a new 3D window. Press Ctrl+A to select all graphic groups of the airplane. Move them to the left with the left arrow key until the center of the wings is located on the y-axis. We also move the plane up on the z-axis by holding down Ctrl and Shift and pressing the up arrow key .

<!-- image -->

Run the simulation again to show the result of centering the airplane on the processing stations.

<!-- image -->

Back to Show the Progress of the Airplane Assembly

#### Displaying Object States

Show Object States

State graphics in 3D correspond to the LEDs in 2D , compare LEDs and States of the Material Flow Objects in 2D . State graphics in 3D have the same color as the respective LEDs in 2D . 3D shows a state graphic whenever it displays the respective LED in 2D . A state graphic can show several states at the same time.

You can select the settings for the state graphic on the Tab States in the dialog Edit 3D Properties .

<!-- image -->

We will demonstrate how to:

- Show States on a Signal Post Above the Machine
- Show States at the Front of the Machine

**Back to Work with Graphics**

Show States on a Signal Post Above the Machine

When you select to show vertically arranged LEDs for a machine for which you imported or created a graphic, you will have to adjust the position settings of the state graphics so that Plant Simulation show them correctly without overlapping a part of the machine. By default, vertical states are shown with a signal lamp on a gray signal post positioned at the left top rear corner of the standard graphics. This way you don't have to visualize the states to be able to move them around without the dialog Edit 3D Properties .

To activate vertically arranged LEDs , open the object in 3D , click the right mouse button into the background of the 3D window, and select Edit 3D Properties .

<!-- image -->

Our default graphic of the Station with vertically arranged state graphics on a signal post looks like this:

Back to Show Object States

<!-- image -->

Show States at the Front of the Machine

Plant Simulation show the states as horizontally arranged cubes at the back of the graphic of the machine by default. Depending on the look of the graphic of the machine this may not be practical as the graphic of the machine might hide the state graphics as such. To fix this, we'll demonstrate how to show the state graphics at the front of the machine.

Our sample graphic without state graphics looks like this:

<!-- image -->

To activate horizontally arranged cubes , open the object in 3D , click the right mouse button into the background of the 3D window, and select Edit 3D Properties .

<!-- image -->

- To show the state graphics, click Show All Possible States . Rotate the machine to show the state graphics. You'll notice that the default setting is not helpful as all state graphics are hidden by the machine when we look at it from the front and as some of them disappear inside of the machine.

- To fix that, let's move the horizontal states to the front of the machine. You can either
- Move the state graphics with the arrow keys . Select the state graphics bar. Press the Up or Down arrow to move it in the Y direction. Press the Left or Right arrow to move it in the X direction. Hold down Ctrl and press the Up or Down arrow to move it in the Z direction. Or you can
- Move the state graphics with the mouse . Select the state graphics bar. Drag the mouse left and right to move it in the Y direction. Drag the mouse back and forth to move it in the X direction. Hold down the Ctrl key and drag the mouse up and down to move it in the Z direction.

You'll notice that moving objects with the arrow keys and/or the mouse might not be accurate enough. Instead, you can also enter precise values into the dialog Edit 3D Properties . If you want to, you can also combine the three methods by first moving the object with the arrow keys, or the mouse, to roughly position the object where you want it to be and by then entering precise values into the dialog.

- Click the machine with the right mouse button and select Show Graphic Structure . Then select Edit 3D Properties in the window Show Graphic Structure .
- Change the position on the tab Transformation so that X reads -1.07 , so that Y reads -0.2 , and that Z reads 0.25 .
- Click Apply to check if the result looks like we expected it to be. The state graphics bar moved to the front of the machine, but it is too high. To fix that, we scale it in the Z direction. Clear the check box Uniform and enter 0.9 into the text box Z . Now it looks good.

Compare LEDs and States of the Material Flow Objects in 2D

Back to Show Object States

**Creating a Simulation Object with Animation**

