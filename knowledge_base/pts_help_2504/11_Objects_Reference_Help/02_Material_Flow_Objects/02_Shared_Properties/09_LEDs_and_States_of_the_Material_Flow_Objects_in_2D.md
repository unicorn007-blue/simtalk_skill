#### LEDs and States of the Material Flow Objects in 2D

During the simulation runs Plant Simulation shows the state of the material flow objects and of the Frame in 2D as one or more colored dots in the LED display along the upper border of the built-in icons of the objects in the Frame .

Each object has an icon named Default . Plant Simulation shows the object with that icon in the Toolbox .

You can also create additional icons, and have Plant Simulation use these icons to display the state of the object:

- Open the Icon Editor .
- Click State Icons/LEDs on the General ribbon tab of the Icon Editor .

<!-- image -->

The LED display can display several active states at the same time, while the state icon can only display the single state it represents.

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

| Description                                              | Looks like this   | LED        | State icon    |
|----------------------------------------------------------|-------------------|------------|---------------|
| The object is Failed                                     |                   | red        | Failed        |
| The object is Stopped                                    |                   | pink       | -             |
| The object is Paused                                     |                   | blue       | Pause         |
| The object is Unplanned                                  |                   | light blue | -             |
| The object is Powering up/ down                          |                   | purple     | -             |
| The object is Working                                    |                   | green      | Working       |
| The object is Blocked                                    |                   | yellow     | -             |
| The object is Setting-Up                                 |                   | brown      | Setup         |
| The Entrance of the object is closed                     |                   | cyan       | No_entry      |
| The object is Waiting for services and/or mounting parts |                   | orange     | Res_not_avail |
| The object is Operational                                | -                 | -          | Operational   |

| Description                             | Looks like this   | LED         | State icon   |
|-----------------------------------------|-------------------|-------------|--------------|
| Inflow into one of the Fluid Objects    |                   | light green | -            |
| Outflow out of one of the Fluid Objects |                   | dark green  | -            |

3D shows the states, that correspond to the LEDs in 2D, in the State Graphic .

<!-- image -->

**Note**

To correctly display state changes with state icons, make sure that the object provides one icon each for the different states. Otherwise, Plant Simulation cannot find the corresponding icon to display, when the object's state changes and keeps displaying the icon for the previous state.

SimTalk

createIcon [SimTalk]

CurrIcon [SimTalk]

CurrIconNo [SimTalk]

ObjectMirrored [SimTalk] - object icons

ZoomX [SimTalk]

ZoomY [SimTalk]

See also

States &gt; State Graphic in 3D

States &gt; Orientation [state graphic] &gt; Color in the dialog Edit 3D Properties of the object

LEDs and States of the Frame

LEDs and States of the Mobile Objects

LEDs and States of the Energy Features

LEDs and States of the Exporter

LEDs and States of the Method

LEDs and States of the MQTT Interface

