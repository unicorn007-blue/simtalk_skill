#### Tab States

States

Select settings for displaying the states of the objects on the tab States .

You can:

- Turn inheritance of the settings off or on.
- Select if you do not want to display states of the object with a state graphic or otherwise in which Orientation the state graphics should be arranged.
- Select if you want the state graphic to be scaled with the object.
- Set or edit Position , Mirroring , and Scale of the state graphic.
- Temporarily Show All Possible States which the object can take in the 3D windows. This can be especially helpful when changing the horizontal settings as no horizontal placeholder will automatically be generated, which covers the entire spread of all state graphics. Once all states are displayed by graphics, the label of the button changes to Show All Possible States . When you then click the button, the object only displays the active state/states again. The same automatically happens after closing the dialog.

<!-- image -->

Internally Plant Simulation keeps the setting for position, mirroring, and for scaling the state graphic with the object once per orientation. This means that you can pre-configure an object how to show horizontal as well as vertical arranged state graphics.

<!-- image -->

State Graphic

State Graphic

Plant Simulation provided a set of state graphics that visualize the state of the simulation objects. State Graphics correspond to the LEDs in Plant Simulation 2D.

State graphics have the same color as the LEDs in 2D and Plant Simulation shows them whenever it displays the corresponding LED in 2D. Several state graphics may be displayed at the same time. All state graphics of an object are grouped in a state graphic.

The default vertical state graphic looks like the stack light or signal tower light you might know from the machines on the shop floor of your facility.

<!-- image -->

<!-- image -->

| State of the object   | Color   | LED   | State graphic vertical   | State graphic horizontal   |
|-----------------------|---------|-------|--------------------------|----------------------------|
| or Pipe is closed     |         |       |                          |                            |
| Waiting               | orange  |       |                          |                            |

**Note**

The energy states Failed and Stopped , or Powering up or down , Off , and Standby , or Working and Blocked can never occur at the same time. Plant Simulation thus shows the state graphics for these states at the same position.

When you change the setting, Plant Simulation deletes all state graphics and creates new state graphics afterward, which are arranged accordingly.

**You can:**

- Create, replace, or delete a state graphic by selecting the Orientation of the state graphic.
- Move or scale the entire state graphic by adjusting its Position , its Mirroring , and its Scale .

**Inheritance**

The inheritance check box turns inheritance of the State Graphic that corresponds to the LEDs in 2D off or on.

- A green check box means that inheritance is turned on. Then the object inherits, i.e., uses, settings of the parent object from which it was derived. When you change the settings of the parent object, Plant Simulation also changes the respective settings of the child object.
- An orange check box with a minus means that inheritance is turned off. The value you specify only applies to the setting of this object.

The state is shown whenever the corresponding LED in 2D is displayed.

See also

LEDs and States of the Material Flow Objects in 2D

Show Object States

###### Orientation [state graphic]

To select how the state graphics for the selected object are displayed, click the drop-down list.

<!-- image -->

| Setting    | Description                                                                                                                                                                                                                                                                                                                              | Looks like this   |
|------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------|
| Off        | Does not show any state graphics. This is the default setting for objects, which cannot have any states, such as the Frame . You cannot change this setting for objects of this type. 3D does not create any state graphics. When you select Off for objects, which already have state graphics, 3D deletes all existing state graphics. |                   |
| Horizontal | Creates rectangles that are colored like the states they display and arranges them horizontally on top of the standard graphics of the object.                                                                                                                                                                                           |                   |
| Vertical   | Creates colored rings and arranges them vertically as a signal lamp on a pole that is a placeholder for all states. These state graphics are normally positioned at a corner of the standard graphics of the object. This is the default setting for most objects which have predefined states.                                          |                   |
| Color      | Colors the entire object graphics with the color of the respective state.                                                                                                                                                                                                                                                                |                   |

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

If you select the Orientation &gt; Color , you can select the state or states that Plant Simulation uses when coloring the object:

<!-- image -->

<!-- image -->

| State of the object          | Color      |
|------------------------------|------------|
| Unplanned                    | light blue |
| Paused                       | blue       |
| Failed                       | red        |
| Stopped                      | pink       |
| Powering up/down             | purple     |
| Off                          | dark gray  |
| Standby                      | light gray |
| Working                      | green      |
| Blocked                      | yellow     |
| Setting-Up                   | brown      |
| Entrance closed              | cyan       |
| Waiting                      | orange     |
| In execution ( Method )      | green      |
| Suspended ( Method )         | purple     |
| Encrypted ( Method )         | gray       |
| Syntax error ( Method )      | light red  |
| Program inherited ( Method ) | dark green |

**Orientation [state graphic]**

**Note**

Not all objects provide all of the above states.

If an object shows its states in color, this affects the graphics of the object and of its animatable objects. It does not affect the stations that are inserted into a Frame or MUs/Workers on that object.

For a Frame , the state material is somewhat transparent. For all other objects it is opaque.

**States of the Worker**

Select which states the Worker shows in your Model Frame .

<!-- image -->

Plant Simulation then shows the T-shirt of the Worker in the respective color.

**SimTalk**

\_3D.StatesOrientation [SimTalk]

\_3D.StatesForColoring [SimTalk]

\_3D.StatesPosition [SimTalk]

\_3D.StatesScale [SimTalk]

See also

Show Object States

LEDs and States of the Material Flow Objects in 2D

LEDs and States of the Energy Features

LEDs and States of the Frame

LEDs and States of the Mobile Objects

LEDs and States of the Exporter

<!-- image -->

**LEDs and States of the Method**

###### Scale With Object [check box]

To scale the state graphic as well, when you scale the object itself, select this check box.

<!-- image -->

To not scale the state graphic as well, when you scale the object itself, clear the check box. Plant Simulation still scales the position of the state graphic though.

SimTalk

\_3D.StatesScaleWithObject [SimTalk]

**Position [state graphic]**

###### Position [state graphic]

Type a value into the text box or roll the mouse wheel to move the Position of the state graphic along the x-axis, the y-axis, and the z-axis. The settings for the three axes are independent of each other.

To move the object by 0.01 meters, click the mouse in the respective text box, hold down Ctrl and roll the mouse wheel.

The different objects in Plant Simulation show their state graphic with different default orientations, depending on their use in the simulation models.

<!-- image -->

###### Mirror [state graphic]

Select the respective check box to mirror the state graphic on that axis.

<!-- image -->

**Scale [state graphic]**

###### Scale [state graphic]

Type different values into the text boxes for the x-axis, the y-axis, and the z-axis to scale the state graphic on this axis with this factor.

You can only type in positive values.

- Typing in 0.5 for example halves the size of the state graphic for the axis for which you entered this factor.
- Typing in 2.0 doubles the size of the state graphic for the axis for which you entered this factor.

To also type the value, which you typed into one of the text boxes, into the remaining text boxes for scaling, select Uniform . This way you do not have to manually type the value into the other text boxes.

<!-- image -->

###### Show All Possible States

To show all states that an object can take, click this button.

<!-- image -->

The button then changes its label to Show Only Active States .

The different states are listed under State Graphic . This is especially helpful for the horizontal orientation if no state is active. For the best display, you might have to adjust the Position , Mirroring , or Scale of the state graphic.

<!-- image -->

The object returns to only showing the active state graphics when you close the dialog.

**Show Only Active States**

To only show the active states of the object again, click this button. By default, the object only shows the currently active states. The button restores the default setting.

<!-- image -->

See also

Position [state graphic]

Mirror [state graphic]

Scale [state graphic]

