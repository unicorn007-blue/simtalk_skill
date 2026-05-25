#### Capacity [general description]

The Capacity is the number of mobile objects ( MUs, parts ) which the material flow objects can hold or process at any one time. Once the capacity is reached, the material flow object does not accept any further MUs .

For the point-oriented objects Station , ParallelStation , Store , Exporter , PlaceBuffer , Buffer , and Sorter Plant Simulation does not take the actual dimension/length of the objects or MUs for the capacity into consideration to determine how many parts they can accommodate.

<!-- image -->

For the length-oriented objects Conveyor , Track , TwoLaneTrack , FootPath , and Transporter Plant Simulation uses the actual length of the object itself and of the length/dimension of the MUs to determine how many parts it can accommodate.

**Note**

The objects AngularConverter , Station , Turnplate , and Turntable have a fixed capacity of 1 .

**See also**

| Capacity [text box] - Buffer      | Length [text box] - lane A   |
|-----------------------------------|------------------------------|
| X-Dimension [ParallelStation]     | Length [text box] - lane B   |
| Y-Dimension [ParallelStation]     | MULength [Part]              |
| Capacity [text box] - PlaceBuffer | MUWidth [Part]               |
| Capacity [text box] - Sorter      | X-Dimension [Container]      |
| X-Dimension [Store]               | Y-Dimension [Container]      |
| Y-Dimension [Store]               | MULength [Container]         |
| Capacity [text box] - Conveyor    | MUWidth [Container]          |

| Length [text box] - Conveyor       | MULength [Transporter]    |
|------------------------------------|---------------------------|
| Capacity [text box] - Track        | MUWidth [Transporter]     |
| Length [text box] - Track          | X-Dimension [Transporter] |
| Capacity [text box] - TwoLaneTrack | Y-Dimension [Transporter] |

