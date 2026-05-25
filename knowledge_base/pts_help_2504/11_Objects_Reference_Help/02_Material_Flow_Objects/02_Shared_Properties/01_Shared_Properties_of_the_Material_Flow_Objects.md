#### Shared Properties of the Material Flow Objects

All material flow objects share a number of the properties. We describe the object-specific properties in the sub-chapters of the respective objects.

Moving and stationary material flow objects are the basic items you use, when you create a simulation model.

- The moving material flow objects Part , Container , and Transporter represent the physical or logical parts moving through the model. These mobile objects ( MUs ) require active and passive material flow objects to process and transport them.

- The active material flow object Source creates mobile objects at the beginning of the flow of materials and the Drain removes them from the plant after the material flow objects have processed them.
- The active material flow objects Station , ParallelStation , AssemblyStation , DismantleStation , Sorter , PlaceBuffer , and Buffer receive MUs , process them for a certain time and then move them on to the next object along material flow connections. They represent work stations in a factory, such as a lathe or a drilling station, etc. They only differ in the number of MUs they can process, a single one or several, and in the way they process them, in series one after the other or in parallel at the same time.

The active length-oriented objects AngularConverter , Converter , Conveyor , Turntable , and Turnplate are used for transporting systems moving MUs at a given speed over a given distance. In descriptions, we also call these objects conveyors or count them as part of conveyor systems.

- The passive material flow objects Store , Track , and TwoLaneTrack do not automatically move MUs on to their successor. A MU remains in the Store until it is removed, for example by employing a Method object. You can only use the Track and TwoLaneTrack in a meaningful way together with the Transporter , which drives along the Track/TwoLaneTrack with the speed you set. You can model diverging and converging strategies with the FlowControl .
- Plant Simulation uses the push-block principle when moving goods from station to station, either along the connections you established with the Connector or by employing a method .

Suppose Station1 is the first station in the sequence of stations in your model, Station2 is the second station, MU1 is the first mobile object that entered the flow of materials, MU2 is the second mobile object. Suppose MU1 is located on Station2 , and MU2 is located on Station1 and wants to move to Station2 .

Once MU2 is completely processed by Station1 , MU2 notifies Station2 that it intends to move to it.

- When Station2 can receive MU2 , it notifies MU2 , and MU2 moves from Station1 to Station2 .
- When Station2 cannot receive MU2 because it is busy, its entrance is locked, etc., MU2 enters itself into the Forward Blocking List of Station2 and of all other stations it intends to move to.
- When MU1 exits Station2 , Station2 schedules an Out event for all entries, i.e., MUs , in the Forward Blocking List , including MU2 . Afterward Station2 deletes all entries from its Forward Blocking List .
- Provided Station2 can receive MU2 , MU2 deletes all references to itself from all blocking lists of all stations it entered itself into, and then moves to Station2 .

You can enter the simulation properties into the text boxes or select them from the drop-down lists in the object dialogs.

<!-- image -->

You can also change the simulation properties in the window Show Attributes and Methods ( F8 ).

<!-- image -->

To edit the 3D properties of the object in the dialog Edit 3D Properties , click in the bottom left corner of the dialog in a 3D only model . Or select the object and press the spacebar In the dialog Edit 3D Properties , you can change back to the dialog of the simulation properties by clicking .

<!-- image -->

<!-- image -->

**See also**

| Time Consumption                                   | Statistics of the Material Flow Objects           |
|----------------------------------------------------|---------------------------------------------------|
| Simulating Random Processes                        | Times and Distributions                           |
| Controls [general description]                     | Methods of All Objects                            |
| Capacity [general description]                     | Attributes of All Objects                         |
| Behavior of Blocked Objects                        | Methods of the Material Flow Objects              |
| Standard Transfer Behavior                         | Read-Only Attributes of the Material Flow Objects |
| Dialog Items of the Objects                        | Attributes of the Material Flow Objects           |
| LEDs and States of the Material Flow Objects in 2D | Dialog Items of the Objects                       |

