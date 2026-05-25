#### Tab Graphics

Graphics [tab, 3D]

**On the tab Graphics you can:**

- Turn inheritance of the amount, the names, and the graphics of all Graphic Groups on or off.
- Turn inheritance of Visibilities of graphic groups on or off.
- Add new Graphic Groups and delete them.
- Rename existing graphic groups, except for the graphic group named default , by over-typing the name.
- Edit the settings of existing graphic groups by selecting or clearing the respective check box.
- Turn Show Content on or off to show or hide the object not only via its external graphic groups, but also via these object and internal graphic groups, which are contained within, toward the outside.

- Turn Exclude from "Show content" of the Location on or off to exclusively show this object within its parent object and never toward the outside, even if the location shows its content toward the outside.
- Turn Show Sensors [check box] on or off to show or hide the sensors which you created for a length-oriented object.
- Show or hide the material flow direction with a direction arrow on the length-oriented objects which provide a directional material flow.
- Select if the object is an Obstacle for the Worker or not.

You can define any number of graphic groups with a unique name for each 3D object. The graphic groups themselves can consist of any number of graphics. The individual graphic groups must have a unique name.

<!-- image -->

<!-- image -->

If you defined more than one graphic group for an object, 3D opens the dialog Select Graphic when you insert a new geometric shape or import a graphic from a file. You can then select the graphic group to which you want to add this graphic.

**See also**

Set How 3D Shows an Object

Work with Graphics

- \_\_Accessing Graphics
- \_Detailed Access To Graphics
- \_\_Accessing Methods of Graphic Groups
- \_\_Accessing Attributes and Read-Only Attributes of Graphic Groups
- \_\_Accessing State Graphics

Video on YouTube

[https://youtu.be/jHOZhlwGhkQ?si=LIBTEB2GP\_cAs66V&amp;t=700](https://youtu.be/jHOZhlwGhkQ?si=LIBTEB2GP_cAs66V&t=700)

##### Graphic Groups

Graphic Groups [described]

Graphic Groups contain the three-dimensional data which show the object in 3D alternatively or additively. Each 3D object has at least one graphic group, named default, which does not necessarily have to contain graphics.

<!-- image -->

In addition to graphic groups some 3D objects can show a State Graphic . The graphic groups are saved separately in the model file.

The inheritance check box shows if the graphic groups of the object are inherited or not.

- A green check box means that inheritance is turned on. Then the object inherits the amount and the names of the graphic groups of its parent object from which it was derived and shares the graphics contained in each graphic group with this object. When you change the graphics of a parent object origin object, Plant Simulation also changes the graphics of the derived object.
- An orange check box with a minus means that inheritance is turned off. Then the object uses its own object graphic groups that have no connection to the graphic groups of the parent object.

You can also turn inheritance of the graphic groups of a 3D object off or on when you

- Click the button Inherit Graphic Groups in the dialog Show 3D Graphic Structure .
- Or when you set the attribute \_3D.InheritGraphics within a method.

Turning inheritance for Graphic Groups off cuts inheritance of the graphic groups just as

<!-- image -->

- Adding or deleting of graphic groups.
- Editing their properties.
- Changing their graphics or their structure or
- Exchanging of all graphic groups.

Then Plant Simulation creates an own copy of all graphic groups for the instance.

**Note**

As cutting graphic inheritance causes graphics to be duplicated and thus increases memory demand, we recommend to make changes in the class object as far as possible to keep graphic sharing for instances.

Turning inheritance for Graphic Groups on restores inheritance of graphic groups and thus applies the graphic groups of the parent object. This means that the instance will lose all changes you made and that it will instead revert to the same graphic structure as the parent object and thus shares all graphics with it again.

Inheritance of the amount, the names and the graphics of Graphic Groups is independent of inheritance of their Visibilities . Inheritance of the Visibilities of the graphic groups can only be reestablished, when the graphic groups also inherit their graphics.

<!-- image -->

The table Graphic Groups lists the graphic groups of the selected object and their properties. These apply to all 3D windows.

- The column Name shows the name of the graphic group. You cannot edit or delete the graphic group named default . The name has to be unique within the object. If you change it, inheritance of the graphic groups is cut.
- The column Generated shows an X if Plant Simulation automatically generated the graphics of the graphic groups. You can neither edit, nor delete, nor add to nor delete generated graphics. You can edit some of their appearance properties though. Compare Generated and Non-Generated Graphics .

It shows an n-dash -if the graphic group is not automatically generated.

- The check box in the column Internal sets for the Frame if the graphic group is only visible within the Frame and will thus only be used for its internal decoration , or if it will be part of the external representation of the selected Frame and will thus be only visible toward the outside. When you change this setting, inheritance of the graphic groups will be cut.

**Note**

The setting Internal is only available for the Frame .

<!-- image -->

- The check box in the column Locked sets if selecting and transforming the graphic group in any 3D window will be prevented or not. Changing this setting will cut graphic inheritance.
- The check box in the column Visible sets if the graphic group is part of the 3D representation of the selected object or not.

By selecting it you can show the graphic group alternatively or additively to the other graphic groups of the selected object. Additional settings define in which 3D window the graphic group will then be visible.

If you clear the check box, the graphic group is invisible everywhere. The names of graphic groups marked as visible are saved in the model in the attribute \_3D.VisibleGraphics . Its inheritance is shown by the state of the inheritance check box Visibilities .

**In addition, you can:**

- Turn inheritance of the Visibilities off or on, i.e., the setting Visible of all graphic groups independent of inheritance of other graphic groups.

<!-- image -->

Edit individual properties of an existing graphic group. Click in the respective row and select or clear the check box.

Rename an existing graphic group. Click in the respective cell and type in a new name.

**Note**

When you add , delete , rename or when you change one of its settings, Plant Simulation cuts inheritance of all graphic groups of the object.

If you defined more than one graphic group for an object, 3D opens the dialog Select Graphic Group when you insert a newly created or an imported graphic. You can then select the graphic group to which you want to add this graphic.

See also

**Work with Graphics**

\_\_Accessing Methods of Graphic Groups

\_\_Accessing Attributes and Read-Only Attributes of Graphic Groups

Show 3D Graphic Structure [context menu] &gt; Inherit Graphic Groups

Add [graphic group]

Delete [button] - graphic group

**Visibilities**

SimTalk

\_3D.InheritGraphics [SimTalk]

Generated [SimTalk] - graphic group

Internal [SimTalk] - graphic group

Locked [SimTalk] - graphic group

Visible [SimTalk] - graphic group

###### Generated and Non-Generated Graphics

Plant Simulation differentiates between graphic groups with predefined generated graphics and graphic groups with user-defined graphics.

- Graphic groups with generated graphics only contain graphics that are predefined by our software engineers or which Plant Simulation created according to fixed settings and which you can neither exchange, nor add to nor delete. Generated graphics show a check mark in the column Generated .

<!-- image -->

You can change some settings of generated graphics in the dialog Edit 3D Properties :

- The Height , Width , the Type , the Materials and the Extrusion Path of the length-oriented objects ( Conveyor , Track , etc.) on the Tab Appearance of the Length-oriented Objects .

<!-- image -->

You can edit the Segments of the extrusion path directly in the window of the scene.

- The dimension , the orientation of the insertion points, the type , and the materials of the different elements of the Store on the Tab Appearance of the Store .
- The color of the MUs on the Tab Appearance by changing the material.

<!-- image -->

Adapt their size to the size of the simulation object of the MU in 2D on the Tab Appearance .

- You can design non-generated graphics according to your own needs. Each change to a non-generated graphic in an object instance deactivates graphic inheritance of this object instance, meaning that no graphic of this instance can thereafter be shared with its origin. Non-generated graphics show a hyphen in the column Generated .
- You can copy graphics from any graphic group in the 3D window or in the dialog Graphic Structure and paste it into graphic groups with non-generated graphics.
- You can insert graphic shapes with the command Insert Shape or paste graphics from other graphic groups. Graphic shapes are generated graphics whose settings you can change afterward on the tab Settings .

<!-- image -->

<!-- image -->

- You can Import Graphics which you exported from Plant Simulation or from any other program in a format that Plant Simulation can read.
- You can delete each and any graphic or change its transformation or its material.

**See also**

Auto Graphics Active

Generated [SimTalk] - graphic group

Graphic Groups [described] &gt; Generated

Generated [context menu]

Work with Length-oriented Objects in 3D

Add

Add [graphic group]

To add a new graphic group to the selected object, click Add . This cuts inheritance of the graphic groups.

<!-- image -->

<!-- image -->

- Type a unique Name into the dialog that opens.
- Select Visible to make the graphic group a part of the 3D representation of the selected object. By toggling this setting, you can alternatively or additively show this graphic group in other graphic groups.
- Select Locked to prevent the graphic group from being selected or moved in any 3D window. Clear Locked to allow that the graphic group can be selected and moved.
- Select Internal to make the graphic group a part of the internal representation of the selected object. It then is only visible in 3D windows in which the selected object is open. Clear Internal to make the graphic group part of the external representation of the selected object
- Click OK to create the graphic group.

<!-- image -->

The created graphic group is empty by default. To add graphics, open the selected object in a 3D window and add shapes or import your own graphics.

SimTalk

\_3D.addGraphicGroup [SimTalk]

See also

Create Alternative Graphic Groups for the Components

**Name [text box] - graphic group**

Type in the Name of the new graphic group of the object.

<!-- image -->

**SimTalk**

\_3D.addGraphicGroup [SimTalk]

Name [SimTalk] - graphic

**Visible [check box]**

**Visible [check box]**

To use the new graphic group for visually representing the object in the 3D windows immediately, select this check box.

<!-- image -->

Activate the check box to show the graphic group immediately alternatively or additively to the other graphic groups of the same object. If a graphic group marked as Visible is actually shown in a certain 3D window or not depends on additional object settings and on the scene root of this 3D window.

Clear the check box to provide the new graphic group as an alternative or additional visual representation for later use and hide it in all 3D windows for now.

<!-- image -->

You can change the setting Visible any time:

- With the check box in the table above.
- In the Context Menu of a Graphic Group with the command Visible in the dialog Show Graphic Structure .
- With the attributes \_3D.VisibleGraphicGroups [SimTalk] and Visible [SimTalk] - graphic group .

Video on YouTube

[https://youtu.be/jHOZhlwGhkQ?si=LIBTEB2GP\_cAs66V&amp;t=700](https://youtu.be/jHOZhlwGhkQ?si=LIBTEB2GP_cAs66V&t=700)

**Locked [graphic group]**

**Locked [graphic group]**

To lock the graphic group in the 3D windows which are opened for this object, select this check box.

<!-- image -->

Locking a graphic group prevents you from selecting this graphic group in the 3D windows which are opened for this object. This makes, for example, sense for the graphic of a factory building which might otherwise be selected inadvertently.

Instead, you can also select the check box on the table on the tab itself.

<!-- image -->

See also Visibilities \_3D.InheritGraphics [SimTalk] \_3D.VisibleGraphicGroups [SimTalk] Locked [SimTalk] - graphic group

Context Menu of a Graphic Group &gt; Locked [context menu]

**Internal [check box]**

**Internal [check box]**

To make the graphic group only visible within the Frame , select this check box.

<!-- image -->

The internal graphic group will then only be used for the internal decoration of the Frame .

<!-- image -->

Clear the check box to make the graphic group an external graphic group that represents the Frame toward the outside. Internal and external graphic groups are only visible if you select the check box Visible .

After you created a graphic group, you can change the setting Internal in the table on the tab itself.

<!-- image -->

Internal graphic groups belong to the content of the Frame and are thus also visible on the outside if you select the check box Visible . They are also visible toward the outside, if the check box Show Content on the Tab Graphics is selected.

To edit external graphic groups, click Show External Graphic Groups on the View ribbon tab to also make them visible inside of the open Frame .

The dialog Show 3D Graphic Structure shows graphic groups with cubes in different borders and colors.

<!-- image -->

**Internal [check box]**

SimTalk \_3D.InternalGraphicGroups [SimTalk] Internal [SimTalk] - graphic group See also Context Menu of a Graphic Group &gt; Internal [context menu]

###### Delete [button] - graphic group

To delete the selected graphic group from the selected object, click this button.

<!-- image -->

**SimTalk**

\_3D.deleteGraphicGroup [SimTalk]

<!-- image -->

###### Visibilities

To make the graphic groups of the object inherit their visibility from the origin object, select this check box.

<!-- image -->

The inheritance check box Visibilities also shows the state of the attribute \_3D.VisibleGraphicGroups .

As soon as you select or clear the check box Visible of one of the graphic groups, 3D changes the state of the Visibilities to non-inheriting. Or you can set inheritance of the visibility by clicking the check box.

<!-- image -->

Plant Simulation only writes the setting of the check box to the attribute \_3D.VisibleGraphicGroups when you click Apply or OK .

Inheritance settings for Graphic Groups and Visibilities normally are independent of each other. Inheritance of the visibilities is reestablished only when graphic inheritance is reestablished.

**See also**

**Work with Graphics**

Create Alternative Graphic Groups for the Components Show 3D Graphic Structure [context menu] &gt; Inherit Graphic Group Visibilities Visible [check box] \_3D.InheritGraphics [SimTalk] \_3D.VisibleGraphicGroups [SimTalk]

##### Show Content

To make the internal graphic groups of the selected object and the external representations of the objects, that are contained within the selected object, represent this object toward the outside, select this check box.

<!-- image -->

<!-- image -->

A 3D object is represented toward the outside by its external graphic groups marked as visible and, if applicable, by its state graphic.

This means that the external graphic groups and the state graphic of all objects, which are located one level lower in the hierarchy than the selected object, will also be visible one level higher in the hierarchy than the selected object. This setting is activated by default.

<!-- image -->

**Note**

By default, the 3D window does not show the content of the Frame and of the folder . It does show the content of all other simulation objects though.

The following figures show how a Frame looks toward the outside with the setting Show Content selected and cleared. As we also selected Show Content for the Station , Plant Simulation shows the parts on the Station together with the content of the Frame .

<!-- image -->

SimTalk

**\_3D.ShowContent [SimTalk]**

See also

Internal [check box]

Set How 3D Shows an Object

Adapt the 3D Model to the 2D Model

Show the Content of the Frame

Video on YouTube

[https://youtu.be/jHOZhlwGhkQ?si=vIcZAB\_uNUMBNYp\_&amp;t=884](https://youtu.be/jHOZhlwGhkQ?si=vIcZAB_uNUMBNYp_&t=884)

[https://youtu.be/t7hBJgNZpHE?si=0QK-ZmSGLuf7BZ9D&amp;t=2047](https://youtu.be/t7hBJgNZpHE?si=0QK-ZmSGLuf7BZ9D&t=2047)

##### Adjust Graphics to MU Size

To adjust the size of the MUs in 3D to their size in 2D, click this button.

<!-- image -->

<!-- image -->

**See also**

**Calculate Dimensions from 3D**

##### Exclude from "Show content" of the Location

To prevent the external representation of the selected object from being displayed together with the external representation of its location, if Show Content is activated for the location, select this check box.

<!-- image -->

Then the representing graphics of the selected object is only visible within its location. This makes sense for abstract objects, such as the Method , Chart , EventController , etc., which are required to define and to control the simulation, but not to illustrate the simulated scene.

This setting also hides Connectors which are connected to excluded objects.

With this setting a DataTable is, for example, not part of the representation of the Frame into which you inserted the Chart even if Show Content is activated for the Frame . That means that when you insert a Frame , for which Show Content is activated, into another Frame ( Frame1 ), then the contents of the Frame , that displays Frame1 , is visible in a 3D window, but not the DataTable for which the check box Exclude from "Show content" of the Location is activated. The Chart is still visible in a 3D window that displays the Frame though.

To redisplay the Chart again together with the content of the Frame , clear the check box.

<!-- image -->

**SimTalk**

**\_3D.ExcludeFromShowContentOfLocation [SimTalk]**

See also

**Show Content**

Video on YouTube

[https://youtu.be/DwZkGMxXJIA?si=SsMP1XxJ9RYfy0At&amp;t=839](https://youtu.be/DwZkGMxXJIA?si=SsMP1XxJ9RYfy0At&t=839)

##### Show Sensors [check box]

To show the sensors, which you created for the length-oriented objects, select this check box.

<!-- image -->

To hide the sensors, clear the check box.

SimTalk

\_3D.ShowSensors [SimTalk]

See also

Sensors [general description]

##### Show Material Flow Direction

To show the direction of the material flow along the insertion direction on length-oriented simulation objects and on length-oriented animation objects with an arrow on it picture, select this check box.

<!-- image -->

To hide the direction of the material flow along the insertion direction, clear the check box.

<!-- image -->

**Note**

For very short objects, 3D does not show the direction arrow at all.

**Color of the Direction Arrow**

3D shows the material flow arrow of passive material flow objects , where MUs move from station to station, in blue .

<!-- image -->

<!-- image -->

3D shows the material flow arrow of active material flow objects , where Transporters transport materials on a Track or on a TwoLaneTrack , in white .

<!-- image -->

3D shows the material flow arrow of fluids , flowing in a Pipe , in light blue .

<!-- image -->

The different objects show the direction arrow like this:

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

| Object            | Description                                                                                                       | Looks like this   |
|-------------------|-------------------------------------------------------------------------------------------------------------------|-------------------|
| Conveyor          | Shows an arrow at the starting point and at the end point each.                                                   |                   |
| Track             | Shows an arrow at the starting point and at the end point each.                                                   |                   |
| TwoLaneTrack      | Shows the name and the direction of the lane at the position defined by the track pitch .                         |                   |
| Converter         | Shows the position of the flow direction at the converting point.                                                 |                   |
| AngularConvert er | Shows the entry and the exit leg with a specific flow direction each. The entry leg is thinner than the exit leg. |                   |
| Turntable         | Shows the position of the flow direction at the rotation point, plus the rotation area as a circle.               |                   |

| Object    | Description                                                     | Looks like this   |
|-----------|-----------------------------------------------------------------|-------------------|
| Turnplate | Shows the position of the flow direction at the rotation point. |                   |
| Pipe      | Shows an arrow at the starting point and at the end point each. |                   |

**Note**

Show the material flow direction only applies to simulation objects and animatable objects which are length-oriented and which have a meaningful material flow direction.

As the FootPath does not have a meaningful material flow direction, it does not show the direction arrow despite being length-oriented.

Show Connections on the View ribbon tab shows or hides the material flow direction of all objects in a 3D window.

<!-- image -->

SimTalk

\_3D.ShowMaterialFlowDirection [SimTalk]

See also

Show Connections [View ribbon] - 3D

\_3D.ShowConnections [SimTalk]

##### Obstacle for the Worker [drop-down list]

Select if the object is an obstacle for the Worker when he walks freely within the area of the model.

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

| Setting                          | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | Looks like this   |
|----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------|
|                                  | In the example to the right the Worker can walk through the pillars and the Station without having to walk around the overall obstacle. This applies for example for the length-oriented material flow objects , such as the Conveyor . For the object Conveyor Plant Simulation approximates the display of the bounding box only roughly to the curve, i.e., it does not show the curve of the conveyor as a smooth curved line. The setting Graphics can have negative effects on the performance when you switch the display often. |                   |
| Bounding box of visible graphics | The bounding box of the entire object is an obstacle for the Worker around which he has to walk. Graphic groups, which are hidden at the moment, are not considered. Length-oriented objects and Frames do not provide this setting.                                                                                                                                                                                                                                                                                                    |                   |

<!-- image -->

| Setting          | Description                                                                                                                                                                                                                                                                                                                                                             | Looks like this   |
|------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------|
| Visible graphics | The graphics of the object are an obstacle for the Worker around which he has to walk. Graphic groups, which are hidden at the moment, are not considered. This applies for example for the length-oriented material flow objects , such as the Conveyor . The setting Visible graphics can have negative effects on the performance when you switch the display often. |                   |

To show the barred areas/obstacles for the Worker in your model, press the o key on your keyboard or

<!-- image -->

click on the tab View of the 3D window.

**Note**

When you view the obstacles for the Worker , you will notice that there is a gap of 40 cm between the obstacles and the objects/graphics. This is because we supposed the width which a Worker needs to pass through is 80 cm. As our Workers do not have a width as such, you see this distance between the obstacles instead.

SimTalk

\_3D.ObstacleForWorker [SimTalk] of an object

\_3D.getGraphic. ObstacleForWorker [SimTalk] of a graphic

See also

Show Obstacles

Barred Area Edit 3D Properties [dialog] &gt; Graphic Settings &gt; Obstacle for the Worker Model a Worker Who Walks Freely Within the Model Model a Worker Who Climbs Stairs Worker [object] in 2D

WorkerPool &gt; Travel Mode [drop-down list] of the Worker

Video on YouTube

[https://youtu.be/Rj5eYZu8pl4?si=BusStMXbJ\_fd1GZ3&amp;t=98](https://youtu.be/Rj5eYZu8pl4?si=BusStMXbJ_fd1GZ3&t=98)

