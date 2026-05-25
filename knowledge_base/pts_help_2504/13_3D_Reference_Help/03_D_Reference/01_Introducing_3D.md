### Introducing 3D

The simulation in Plant Simulation controls the animation and visualization of the three-dimensional objects which you create in 3D .

This way you can realistically depict an existing installation. 3D provides a number of tools for editing and viewing the three-dimensional scene, different kinds of navigation and different editors and manipulators among others.

Plant Simulation 3D differentiates between these object types:

- Simulation Object
- Animatable Object
- Graphic Group [described]
- State Graphic
- 3D Graphic
- The 3D Window Shows Which Object When details under which circumstances 3D shows the different objects.

The dialog box Show Graphic Structure shows these object types in a structure.

<!-- image -->

You can edit the 3D Properties of the objects in the dialog box Edit 3D Properties .

<!-- image -->

Click Open Simulation Settings in the bottom left corner of the dialog to change the simulation properties of the object.

<!-- image -->

Also compare 3D Properties Visualizing the Simulation and Change 3D Settings Controlling the Visualization .

See also Viewing the 3D Sample Models Creating a Model in 3D Work with the Scene Edit 3D Properties [dialog] 3D Reference Visualizing the Material Flow in 3D SimTalk Access to 3D Undo [3D] , Redo [3D]

#### Simulation Object

A simulation object is an object that is available in 2D and in 3D.

A simulation object is available in 2D and in 3D if you activated the check box in the dialog that clicking 3D Properties &gt; Create In 3D on the Home ribbon tab opens.

<!-- image -->

If this is not the case, the simulation object is only available in 2D.

The built-in material flow objects , the fl uid objects , the resource objects , and the mobile objects are simulation objects by default.

In 3D only models and in 2D and 3D models simulation objects have the same position in the Frame . The dialog box Show Graphic Structure shows all elements which can contribute to the three-dimensional visualization of a simulation object but not the simulation objects contained in a Frame . To show simulation objects that a simulation object of type Frame contains, you have to open the dialog Show Structure for the Frame .

Plant Simulation shows a selected simulation object in green in the 3D window.

<!-- image -->

When you open a simulation object , the 3D window shows a green border on the inside.

<!-- image -->

You can create a new simulation object from any graphic:

- Click the graphic with the right mouse button and select Make Simulation Object .
- Type in the name of the simulation object and select the class whose properties you can to use.
- Select the 2D object class from whose 3D counterpart the simulation object will be derived.

<!-- image -->

<!-- image -->

- Select the components of the object position in three-dimensional space.

See also

Make Simulation Object

Create a Simulation Object with Animation

The 3D Window Shows Which Object When

Undo [3D]

Redo [3D]

#### Animatable Object

To animate simulation objects or to logically split them up into several components, each having its own inheritance, you can create animatable objects in 3D.

Plant Simulation shows a selected animatable object in purple in the 3D window. Just as a Frame consists of simulation objects and additional Frames with simulation objects, each simulation object can be subdivided into animatable objects. You might compare the hierarchy of a Frame , which the dialog Show Structure displays, with the hierarchy which the dialog box Show Graphic Structure displays for a PickAndPlace robot in a new model.

You can create an animatable object from any graphic of your choice.

In the following example we create an animatable object for the robot base of the built-in PickAndPlace robot . The individual components of the robot arm on the other hand are animated by default.

- We click the robot base with the right mouse button and select Make Animatable Object .
- We type in the name of the animatable object, RobotBase in our case.

<!-- image -->

<!-- image -->

- We define the joint settings on the tab Joint .
- We open the robot base in a new 3D window.

<!-- image -->

<!-- image -->

Plant Simulation shows a selected animatable object in the 3D window a purple .

<!-- image -->

When you open an animatable object , the 3D window shows a purple border .

<!-- image -->

See also

Make Animatable Object

Joint

Add Animatable Object

Use as Animation Object

The 3D Window Shows Which Object When

3D Properties Visualizing the Simulation

3D Properties

Create the Animation Objects

Undo [3D]

Redo [3D]

<!-- image -->

#### Graphic Group [described]

Graphic groups define, through the graphics they contain, a possible three-dimensional representation of a simulation object or an animatable object and must have a name that is unique for this object.

Simulation objects and animatable objects consist of graphic groups which contain the graphics which are not located in animatable objects on lower hierarchy levels.

Graphic groups are similar to the 2D icons of the simulation objects. Besides the name you can set if a graphic group is locked, i.e. cannot be selected in the 3D window and if it is visible, i.e. whether it represents the object. Additionally graphic groups of Frames can be external or internal.

External graphic groups represent the object toward the outside.

Internal graphic groups only serve for the interior decoration of Frames .

<!-- image -->

<!-- image -->

Each object has at least one graphic group named default and optionally any number of additional graphic groups which you can show or hide independent of each other. The properties name, locked and internal are, together with the graphic structure, an object property that can be inherited. A graphic group can be totally hidden, i.e. be invisible everywhere, to allow switching between different graphic groups. The visibility of the graphic groups also is a 3D object property which can be inherited. You can create, delete and configure graphic groups on the Tab Graphics in the dialog box Edit 3D Properties and in the dialog box Show 3D Graphic Structure .

A new created graphic group is empty, i.e. does not contain any graphics. To add graphics to a graphic group you must either open the object in a 3D window and import a graphic or insert a shape into the graphic group which you have to select on the Edit ribbon tab. Or you copy and paste a graphic in the dialog box Show Graphic Structure , or from one 3D window into another.

<!-- image -->

**See also**

Add Graphic Group

Graphics [tab, 3D]

Use Alternative Graphic Groups

Create Alternative Graphic Groups for the Components

Set How 3D Shows an Object

The 3D Window Shows Which Object When

Inherit Graphic Groups

Inherit Graphic Group Visibilities

Context Menu of a Graphic Group

Undo [3D]

Redo [3D]

#### State Graphic

State graphics are groups of automatically generated graphics that represent all the states in 3D that are predefined for a simulation object.

You can select these display modes on the Tab States in the dialog box Edit 3D Properties , which you can move and scale as you need them to be:

<!-- image -->

- Vertically stacked light rings look like this:
- Horizontally placed rectangles look like this:

<!-- image -->

<!-- image -->

- Color colors the entire graphic with the respective state color. It looks like this:

<!-- image -->

See also

Add Graphic Group

The 3D Window Shows Which Object When

States

Show 3D Graphic Structure [context menu]

Undo [3D]

**Redo [3D]**

#### 3D Graphic

A 3D graphic describes the entire shape of a visual element in your 3D model.

3D Graphics are all geometric elements and groups of geometric elements which describe the entire shape of a visual element.

You can insert graphics as follows into your model:

- You can select a new 3D graphic from the list Insert Shape and insert it into the 3D window.
- You can Import Graphics .

<!-- image -->

<!-- image -->

You can create an animatable object, in the example below for the robot base, or a simulation object from a graphic.

Plant Simulation shows a selected graphic in yellow green in the 3D window.

<!-- image -->

**See also**

The 3D Window Shows Which Object When

Insert Shape

Context Menu of the Selected Graphic

Graphics [tab, 3D]

Graphic Settings for defining Worker obstacles

Undo [3D]

Redo [3D]

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

**See also**

Set How 3D Shows an Object

#### Viewing the 3D Sample Models

After you have successfully installed Plant Simulation , you can view one of the example models that are part of your program package, to get a first impression about what 3D can do.

- Start the version of Plant Simulation ( Development , Application ) you purchased.
- Click Example Models on the Start Page . Then click Factory 51 under Example Models . This opens the model file.
- To start the simulation, click Reset Simulation and then Start/Stop Simulation on the Home ribbon tab. Watch how the simulation in Plant Simulation controls the animation of the mobile objects in the 3D window with only a slight delay in time.
- To stop the simulation, click Start/Stop Simulation on the Home ribbon tab.

<!-- image -->

**Note**

Also check out the other example models located in the folder Examples in the folder where you installed Plant Simulation .

In addition, some of the videos, which you can open from the Start Page , provide an introduction to 3D or solve certain modeling tasks.

