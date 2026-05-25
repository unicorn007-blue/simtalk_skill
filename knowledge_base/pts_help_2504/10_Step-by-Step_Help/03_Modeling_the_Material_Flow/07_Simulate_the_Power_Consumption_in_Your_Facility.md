### Simulate the Power Consumption in Your Facility

To accommodate the growing environmental awareness, Plant Simulation provides features to keep track of energy consumption in the face of rising energy costs and the depletion of energy resources. The features on the Tab Energy provide these evaluations regarding energy consumption during the production process in the plant:

- Power consumption per machine
- Total power consumption for all objects contained within a Frame

In our example we will demonstrate how to:

- Configure the Processing Stations and the Conveyor
- Configure the ShiftCalendar
- Check the Power Consumption in the Dialogs of the Objects
- Check the Power Consumption in the Statistics Report
- Check the Power Consumption in the Chart

We use most of the material flow objects with their default settings. We just entered energy-related settings and defined failures for some of the objects.

The finished simulation model looks like this:

Back to Modeling the Material Flow

<!-- image -->

#### Configure the Processing Stations and the Conveyor

Insert the following stations to simulate our parts moving through the factory.

- The Source feeds the parts into the plant. We did not change any of its default settings.
- The first machine, the Station , processes the parts for 1 minute each. We entered the kilowatts it uses up in the states it can be in. We also entered the times that the machine requires for switching from one energy state to another.

<!-- image -->

- The second machine, Station1 , processes the parts for 2 minutes each. We entered the kilowatts it uses up in the states it can be in. We also entered the times that the machine requires for switching from one energy state to another.

<!-- image -->

To simulate a real situation, we also defined a failure profile with these settings:

<!-- image -->

- The conveyor, the object of type Conveyor , transports the parts from the processing station Station1 to the ParallelStation . We entered the kilowatts it uses up in the states it can be in. We also entered the times that the conveyor requires for switching from one energy state to another. You will notice that the length-oriented object Conveyor provides fewer energy settings than the point-oriented objects Station and ParallelStation .

<!-- image -->

To simulate a real situation, we also defined a failure profile with these settings:

<!-- image -->

- The third machine, the ParallelStation , processes the parts for 1 minute each. We entered the kilowatts it uses up in the states it can be in. We also entered the times that the machine requires for switching from one energy state to another.

<!-- image -->

- The Drain removes the parts from the factory. We did not change any of its built-in settings.
- The Charts display a resource statistics chart , and an energy statistics chart for the selected objects.

Back to Simulate the Power Consumption in Your Facility

#### Configure the ShiftCalendar

To model a realistic situation in the factory, we insert a ShiftCalendar that controls the hours during which people and machines work in the factory. We did not change the default shift times, we just entered the material flow objects.

To do so, we held down Shift and dragged a marquee over the objects. We then dragged the selected objects onto the ShiftCalendar and dropped them there.

<!-- image -->

Back to Simulate the Power Consumption in Your Facility

#### Check the Power Consumption in the Dialogs of the Objects

You can view the energy consumption values, which the objects collected, in their dialogs:

- Double-click the icon of the respective object and click the Tab Statistics .
- Click Energy Statistics to view more detailed values about the different portions of energy consumption.

<!-- image -->

Back to Simulate the Power Consumption in Your Facility

<!-- image -->

#### Check the Power Consumption in the Statistics Report

You can view the energy consumption values, which the objects collected, in the Statistics Report .

To view the total energy consumption and the portions of the different energy states , select Energy Statistics in the drop-down list. The values are described under Energy Statistics - Energy Statistics .

<!-- image -->

**Note**

The energy states of the material flow objects differ from the resource states with the same name. The values for the resource states refer to the statistics collection period, while the values for the energy states refer to the total energy consumption.

The material flow objects also show these values on the Tab Statistics and in the dialog that clicking Energy Statistics opens.

Back to Simulate the Power Consumption in Your Facility

#### Check the Power Consumption in the Chart

You can view the energy consumption values, which the objects collected, in a Chart .

- To view the energy consumption of the different energy states , select the objects which you want to display in the Chart . Drag them onto the Chart . Select the Statistics Type &gt; Energy Statistics in the dialog that opens and click OK .

<!-- image -->

**Note**

The energy states of the material flow objects differ from the resource states with the same name. The values for the resource states refer to the statistics collection period, while the values for the energy states refer to the total energy consumption.

Back to Simulate the Power Consumption in Your Facility

**Modeling Workers and the Jobs They Do**

