#### Dialog Box of the Part

Dialog Box of the Part

Double-click the icon of the Part that is located on one of the material flow objects in the Frame to open its dialog box.

<!-- image -->

###### Tab Attributes

**Edit Simulation Properties**

To change the settings of the class of the object, double-click it in the Class Library or on the tab Moving Units in the Toolbox . Here you can then type in or select the simulation properties to get the results you need. The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties :

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the 3D model and press the spacebar .

See also

Number [of the MU]

Conveying Direction [described]

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

The shared properties are described under the tab Attributes .

###### MU Length [Part]

Type the Length of the Part into the text box.

The length-oriented objects Conveyor , Track and TwoLaneTrack use the Length to determine how many Parts they can hold.

<!-- image -->

**SimTalk**

MULength [SimTalk]

**MU Width [Part]**

###### MU Width [Part]

Type in the Width of the Part .

The length-oriented objects Conveyor , Track and TwoLaneTrack use the Width after the AngularConverter has changed the Conveying Direction to determine how many Parts they can hold.

<!-- image -->

**SimTalk**

**MUWidth [SimTalk]**

See also

Conveying Direction [described]

###### MU Height [Part]

Type the Height of the Part .

The Height is only important for 3D as only 3D provides the z-dimension.

<!-- image -->

**SimTalk**

MUHeight [SimTalk]

**Booking Point Length [Part]**

###### Booking Point Length [Part]

Type in the relative position of the Booking Point of the Part , which applies, when it is conveyed Lengthwise .

The value you type in is the distance from booking point 0, which is located at the front of the Part , in the direction of motion. Type in a relative value between 0 and 1 . Plant Simulation uses it, when the Conveying Direction is forward or Backward .

Plant Simulation shows the absolute position of the booking point in parentheses.

When you are modeling conveyor systems, the booking point oftentimes represents the center of gravity of the part. When the booking point, i.e., the center of gravity of the part, has transferred onto a conveyor, the part starts moving with the Speed you set for this conveyor.

<!-- image -->

By default, each Part requires a booking point, as a long Part may be located on more than one lengthoriented object at the same time. Plant Simulation uses the booking point to determine on which material flow object it shows the Part when animating a simulation run. Plant Simulation shows, for example, a Part moving along from Conveyor to Conveyor on the preceding Conveyor until its booking point moves on to the succeeding Conveyor .

If the part is not animated on the expected position on the object, check the position of the Booking Point .

**Compare this example:**

- Here Booking Point Length and Booking Point Width of the square part are located in its center at the position 0.5 . The part is animated at the center of the conveyor belt.

<!-- image -->

- Here Booking Point Width of the square part are located at the position 0.2 . The part is animated with an offset to the left in the direction of motion on the conveyor belt.

<!-- image -->

**Note**

When you assign a value to the booking point in a Method , Plant Simulation interprets this number as meters. Only when outputting it with the method print , it converts the value according to the settings you selected under File &gt; Model Settings/Preferences &gt; Units &gt; Length .

**SimTalk**

BookPntLRelative [SimTalk]

**Booking Point Length [Part]**

**BookPntWRelative [SimTalk]**

See also

Set and Link Animation Points and Lines

###### Booking Point Width [Part]

Type in the relative position of the Booking Point of the Part when it is conveyed Crosswise .

The value you type in is the relative distance meters from booking point 0, which is located at the right-hand side of the Part , in the direction of motion. Type in a relative value between 0 and 1 . Plant Simulation uses it, when the Conveying Direction is lateral right or lateral left . Plant Simulation shows the absolute position of the booking point in parentheses.

When you are modeling conveyor systems, the booking point oftentimes represents the center of gravity of the part. Once the booking point, i.e., the center of gravity of the part, has transferred onto a conveyor, the part starts moving with the Speed you set for this conveyor.

<!-- image -->

The parts require a booking point, as a long Part may be located on more than one length-oriented object at the same time. Plant Simulation uses the booking point to determine on which material flow object it shows the Part when animating a simulation run. Plant Simulation shows, for example, a Part moving along from Conveyor to Conveyor on the preceding Conveyor until its booking point moves on to the succeeding Conveyor .

If the part is not animated on the expected position on the object, check the position of the Booking Point .

**Compare this example:**

- Here Booking Point Length and Booking Point Width of the square part are located in its center at the position 0.5 . The part is animated at the center of the conveyor belt.

<!-- image -->

- Here Booking Point Width of the square part are located at the position 0.2 . The part is animated with an offset to the left in the direction of motion on the conveyor belt.

<!-- image -->

**Note**

When you assign a value to the booking point in a Method , Plant Simulation interprets this number as meters. Only when outputting it with the method print , it converts the value according to the settings you selected under File &gt; Model Settings/Preferences &gt; Units &gt; Length .

**SimTalk**

BookPntWRelative [SimTalk]

**BookPntLRelative [SimTalk]**

See also

**Set and Link Animation Points and Lines**

###### Booking Point Height [Part]

Booking Point Height [Part]

Type in at which Relative Height the Booking Point of the Part is located.

<!-- image -->

The booking point height is only important if you want to use the z-dimension of the MU in 3D . Type in a relative value between 0 and 1 . Plant Simulation shows the absolute position of the booking point in parentheses.

<!-- image -->

For the default Booking Point Height of 0 Plant Simulation places the part flush onto the object, for example onto the belt of a conveyor or on a station .

**Note**

When you assign a value to the booking point in a Method , Plant Simulation interprets this number as meters. Only when outputting it with the method print , it converts the value according to the settings you selected under File &gt; Model Settings/Preferences &gt; Units &gt; Length .

**SimTalk**

BookPntHRelative [SimTalk]

Tab Routing [Part]

The settings for routing of the Part are described under the Tab Routing .

See also

Automatic Routing [Part, Container]

Reset Destination When at Destination [Part, Container]

Route Weighting Attribute [Part, Container]

Destination [Part, Container]

**Tab Graphics [Part]**

##### Tab Graphics [Part]

Select settings for vector graphics of the Part on the Tab Graphics .

##### Tab Product Statistics [MUs]

The tab Product Statistics is described under the Tab Product Statistics .

<!-- image -->

**See also**

Product Statistics [all MUs]

Product Statistics Values

Methods for Accessing Statistics of the MUs

\_Read-Only Attributes for Accessing Statistics of the MUs

##### Tab Costs [MUs]

Tab Costs [MUs]

Type in the settings for costs, which accrue for the Part and for the Container on the tab Costs .

The inheritance check box also affects the other settings on the tab.

**Note**

Only the active material flow objects ( AngularConverter , AssemblyStation , Buffer , Converter , Conveyor , DismantleStation , ParallelStation , PickAndPlace -robot, PlaceBuffer , Sorter , Station , Store , Turnplate , Turntable ), and the moving objects Part and Container provide costs settings.

The CostAnalyzer runs the actual cost analysis.

See also

Tab Costs [material flow objects]

Simulate the Accrued Costs of the Machines

##### Tab User-defined [MUs]

Define your own attributes as described under the Tab User-defined .

This table lists, where the relative path starts for a user-defined attribute you define for a MU :

| Object                                | Path of a user-defined attribute created foraMU                                          |
|---------------------------------------|------------------------------------------------------------------------------------------|
| Object variable                       | Starts in the Frame in which the material flow object on which the MU stays, is located. |
| Method (current)                      | Starts in the Frame in which the material flow object on which the MU is located.        |
| Table with column of data type object | Starts with the material flow object on which the MU stays.                              |

**Navigate Menu**

##### Navigate Menu

The commands are described under the Navigate Menu .

##### View Menu

The View Menu provides commands to access its functions.

| Refresh [on View menu]                     | Position [MUs]        |
|--------------------------------------------|-----------------------|
| Show Statistics Report [on View menu]      | Forward Blocking List |
| Show Attributes and Methods [on View menu] | Targets               |

##### Tools Menu

Tools Menu provides these menu commands:

The Tools Menu Edit Controls Edit Observers 3D

##### Help Menu

The commands are described under the Help Menu .

##### Methods of the Part

