#### Statistics of the Material Flow Objects

Statistics of the Material Flow Objects

A typical task of a simulation run is to find out the distribution of failure times, waiting times or blockages, and the material flow through the processing stations. When interpreting the simulation run, you can use statistical data the material flow objects collect by default.

As a rule, you will always try to arrive at the best configuration of the production process: short throughput time, making the best use possible of the resources available and meeting all deadlines. The standard statistics of objects in Plant Simulation provide data to allow you to make valid statements about the process you are studying.

See also

Statistics Collection Period [material flow objects]

Resource Statistics [material flow objects]

Statistics Report [described]

Methods for Accessing Statistics

Attributes for Statistics

##### Statistics Collection Period [material flow objects]

The statistics collection period is the interval between activating statistics collection or resetting it on the one hand and the time you query statistics on the other hand.

Plant Simulation collects statistical data by default. To deactivate statistics collection for the object, clear the check box Resource Statistics on the tab Statistics of the object, or set the attribute ResStatOn to false . Deactivating Resource Statistics deletes all statistical data for the object.

**Note**

When you reset your simulation model, Plant Simulation deletes the statistical information of all objects. During a simulation run you can achieve the same effect using the method initStat . This way you can restart the collection of statistical information after a warm-up period of a machine.

Access statistical data, for example by calling the method statistics , and save it to a table or file.

The following example illustrates the terms statistics collection period and statistics collection :

<!-- image -->

**Statistics Query One**

The statistics collection period starts when you activate statistics collection of the object, by selecting the check box Resource Statistics on the tab Statistics , or by assigning the value true to the attribute ResStatOn , and ends with the query of the statistical data. The progression of the failure of the object, the start of the statistics query and the time of statistics query 1 add up to a failure portion of 100 % for statistics query 1 . For this query the times the object was not Failed are all located outside the statistics collection period.

**Statistics Query Two**

The course of the failure of the object, the start of the statistics query and the time of statistics query 2 add up to a failure portion of less than 100 % for statistics query 2 because, for a time, the object was not failed during the statistics collection period of the object.

##### Resource Statistics

###### Resource Statistics [material flow objects]

During a simulation run a material flow resource can take on different states.

The resource states are Working , Setting-Up , Waiting , Blocked , Powering up/down , Failed , Stopped , Paused , and Unplanned

**Note**

In this context, resources are any of the material flow objects, for which you can select a Resource Type .

The statistics collection period is the sum of the states Working , Setting-Up , Waiting , Blocked , Powering up/down , Failed , Stopped , Paused , and Unplanned . For some objects, for example for the ParallelStation , some of these states can overlap during the simulation run.

For statistical purposes the times below are organized so that they do not overlap. The values for Working , Setting-Up , Waiting , Blocked , Powering up/down , Failed , Stopped , Paused , and Unplanned should add up to 100 percent.

This diagram shows how the statistics collection period of a resource is divided up.

<!-- image -->

The following colors represent the states of the objects. The LED display can display several active states at the same time, while the state icon can only display the state it represents.

<!-- image -->

| State of the object                        | Looks like this   | LED         | State icon    |
|--------------------------------------------|-------------------|-------------|---------------|
| Failed                                     |                   | red         | Failed        |
| Stopped                                    |                   | pink        | -             |
| Paused                                     |                   | blue        | Pause         |
| Unplanned                                  |                   | light blue  | -             |
| Powering up/down                           |                   | purple      | -             |
| Working                                    |                   | green       | Working       |
| Blocked                                    |                   | yellow      | -             |
| Setting-Up                                 |                   | brown       | Setup         |
| Entrance closed                            |                   | cyan        | No_entry      |
| Waiting for services and/or mounting parts |                   | orange      | Res_not_avail |
| Operational                                | -                 | -           | Operational   |
| Inflow into one of the Fluid Objects       |                   | light green | -             |
| Outflow out of one of the Fluid Objects    |                   | dark green  | -             |

3D shows the State Graphic of the object as a colored ring on a pole by default. The state graphics in 3D correspond to the colored LEDs described above.

<!-- image -->

<!-- image -->

To view Resource Statistics of Stationary Resources in the Statistics Report , click the object in the Frame , and press F6 ( Show Statistics Report ), or select View &gt; Show Statistics Report in the dialog of the object.

<!-- image -->

| A bar with this color   | Means that the object is   | Looks like this English   | Looks like this German   |
|-------------------------|----------------------------|---------------------------|--------------------------|
| green                   | Working                    |                           |                          |
| brown                   | Setting-Up                 |                           |                          |
| gray                    | Waiting                    |                           |                          |
| yellow                  | Blocked                    |                           |                          |
| purple                  | Powering up/down           |                           |                          |
| red                     | Failed                     |                           |                          |
| pink                    | Stopped                    |                           |                          |

<!-- image -->

| A bar with this color   | Means that the object is   | Looks like this English   | Looks like this German   |
|-------------------------|----------------------------|---------------------------|--------------------------|
| blue                    | Paused                     |                           |                          |
| light blue              | Unplanned                  |                           |                          |

**See also**

State Graphic

in 3D

Empty [state, material flow objects]

Relative Occupation

ResCurrentState [SimTalk] - material flow objects

###### Working [state, material flow objects]

The definition of working depends on the material flow or fluid object that processes or conveys the MU .

| The object                                                                           | Is working when                                                                                                                                                                                                                        |
|--------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Station , ParallelStation , AssemblyStation , DismantleStation , PlaceBuffer , Drain | it processes at least one MU                                                                                                                                                                                                           |
| Track , TwoLaneTrack                                                                 | at least one MU is moving on it                                                                                                                                                                                                        |
| Conveyor                                                                             | its current speed is not 0. It can also be working when it is moving and when it does not transport any part                                                                                                                           |
| Turnplate , Turntable                                                                | it has a speed or when it is rotating, no matter if it moves a part or not                                                                                                                                                             |
| Converter , AngularConverter                                                         | has a speed or when the moving time is running                                                                                                                                                                                         |
| PickAndPlace Robot                                                                   | it is rotating, no matter if it moves a part or not or when it picks a part up or deposits a part                                                                                                                                      |
| Source , Store , Buffer , Transporter , Container , Pipe , Tank                      | -                                                                                                                                                                                                                                      |
| Sorter                                                                               | - The processing time is identical with the sorting time, i.e., it is always zero. This means that sorting takes place instantaneously. Even though the processing time is zero, each sorting action counts as a processing procedure. |
| FluidDrain , FluidSource                                                             | material flows                                                                                                                                                                                                                         |
| Mixer                                                                                | materials are mixed                                                                                                                                                                                                                    |
| Portioner                                                                            | material is transformed into a MU                                                                                                                                                                                                      |
| DePortioner                                                                          | MU is transformed into a material                                                                                                                                                                                                      |

**Note**

The read-only attribute ResWorking , returns the state working of the resource.

<!-- image -->

The LED of a station that is processing parts is green .

3D shows the State Graphic of the object as a colored ring on a pole by default.

The Statistics Report shows the Working Time below Resource Statistics of Stationary Resources .

SimTalk ResWorking [SimTalk] - material flow objects ResCurrentState [SimTalk] - material flow objects See also Failure Relates To &gt; The processing time Statistics Report [described] &gt; Working Time Tab Statistics [material flow objects] LEDs and States of the Material Flow Objects in 2D State Graphic Setting-Up [state, material flow objects]

A material flow or fluid resource is setting up when it prepares for processing a different type of MU .

If the object is Paused or Failed , it cannot set-up.

<!-- image -->

The LED of a station that is setting-up is brown .

3D shows the State Graphic of the object as a colored ring on a pole by default.

The Statistics Report shows the Set-up Time below Resource Statistics of Stationary Resources .

SimTalk

ResSetup [SimTalk] - material flow objects

ResCurrentState [SimTalk] - material flow objects

See also

Statistics Report [described] &gt; Set-up Time

Tab Statistics [material flow objects]

Tab Set-Up [general description]

LEDs and States of the Material Flow Objects in 2D

State Graphic

###### Waiting [state, material flow objects]

A material flow or fluid resource is waiting when it is not in the other states.

The object is waiting when

- It is not Paused .
- It is not Failed .
- It is not Stopped .
- All of its processing places are not Working .

This applies for example because the station is waiting for resources ( Exporters/Workers ) or for mounting parts .

- All of its processing places are not Setting-Up .
- It is not fully occupied.

**Note**

The read-only attribute ResWaiting returns the state waiting of the resource.

**Note**

<!-- image -->

Plant Simulation does not show the general state Waiting with an LED. It only shows the orange LED if the station is waiting for an Exporter/Worker and/or for mounting parts .

3D shows the State Graphic of the object as a colored ring on a pole by default.

The Statistics Report shows the Waiting Time below Resource Statistics of Stationary Resources .

SimTalk

ResWaiting [SimTalk] - material flow objects

ResCurrentState [SimTalk] - material flow objects

See also

Tab Statistics [material flow objects]

StatWaitingCount [SimTalk]

StatWaitingDelta [SimTalk]

StatWaitingPortion [SimTalk]

Waiting [state, material flow objects]

StatWaitingMu [SimTalk] StatWaitingTime [SimTalk] LEDs and States of the Material Flow Objects in 2D State Graphic

###### Blocked [state, material flow objects]

A material flow or fluid resource is blocked , when it is not in one of the other states.

The object is blocked when

- It is fully occupied.
- It is not Paused .
- It is not Failed .
- It is not Stopped .

·

All of its processing places are not

Working

.

- All of its processing places are not Setting-Up .

**Note**

The read-only attribute ResBlocked returns the state blocked of the resource.

<!-- image -->

The LED of a blocked station is yellow

.

3D shows the State Graphic of the object as a colored ring on a pole by default.

The Statistics Report shows the Blocked Time below Resource Statistics of Stationary Resources .

**SimTalk**

ResBlocked [SimTalk] - material flow objects

ResCurrentState [SimTalk] - material flow objects

See also

Statistics Report [described] &gt; Blocked Time

Tab Statistics [material flow objects]

StatBlockingPortion [SimTalk]

LEDs and States of the Material Flow Objects in 2D

State Graphic

###### Powering up/down [state, material flow objects]

A material flow resource or a fluid resource is powering up when it is switched on. It is powering down when it is switched off. Powering up/down designates the state when the object changes its energy state.

**Note**

Plant Simulation only records this value if the station is not failed , not paused , not stopped , or not unplanned .

Plant Simulation shows the State Graphic of the object as a colored ring on a pole by default.

The Statistics Report shows the Powering up/down Time below Resource Statistics of Stationary Resources .

SimTalk

ResCurrentState [SimTalk] - material flow objects

See also

Statistics Report [described] &gt; Powering up/down Time

Tab Statistics [material flow objects]

StatPoweringUpDownCount [SimTalk]

StatPoweringUpDownDelta [SimTalk]

StatPoweringUpDownMu [SimTalk]

StatPoweringUpDownPortion [SimTalk]

StatPoweringUpDownTime [SimTalk]

LEDs and States of the Material Flow Objects in 2D

State Graphic

in 3D

###### Failed [state - material flow objects]

A material flow or fluid resource is failed , when it is not working due to a failure of any kind.

The object may resume processing only after you remove the failure, by clearing the check box Failed .

**Note**

When a station fails, and a pause occurs during the failure, the failure time of the station will still be consumed, although the station is paused.

**Note**

When a Worker/Exporter is brokered to the failed station, it remains brokered to the station while it is failed. Statistics of the Worker/Exporter does not count this time as waiting .

Statistics counts the times during which these two states overlap, as pause time.

<!-- image -->

The LED of a failed station is red

3D shows the State Graphic of the object as a colored ring on a pole by default.

The Statistics Report shows the Failed Time below Resource Statistics of Stationary Resources .

SimTalk

ResCurrentState [SimTalk] - material flow objects

See also

Statistics Report [described] &gt; Failed Time

Working [state, material flow objects]

Tab Statistics [material flow objects]

Failed [SimTalk] - material flow objects

endFailure [SimTalk] - material flow objects

endFailureIn [SimTalk] - material flow objects

eraseFailureEvents [SimTalk] - material flow objects

StatFailPortion [SimTalk]

startFailure [SimTalk] - material flow objects startFailureIn [SimTalk] - material flow objects LEDs and States of the Material Flow Objects in 2D State Graphic in 3D

###### Stopped [state, material flow objects]

A material flow or fluid resource is stopped , when the LockoutZone stops all processing operations of the material objects assigned to it.

The stations only start processing parts again after all failures were removed. They then only use up the remaining processing time. When you reset your model, all stations change their state from stopped to operational .

**Note**

When a Worker/Exporter is brokered to the stopped station, it remains brokered to the station while it is stopped. Statistics of the Worker/Exporter does not count this time as waiting .

**Note**

During the reset phase of the simulation Plant Simulation resets the attribute Stopped .

<!-- image -->

The LED of a stopped station is pink

.

3D shows the State Graphic of the object as a colored ring on a pole by default.

The Statistics Report shows the Stopped Time below Resource Statistics of Stationary Resources .

SimTalk

ResCurrentState [SimTalk] - material flow objects

See also

LockoutZone

Stopped [SimTalk] - material flow objects

Stopped [SimTalk] - Frame

Stopped [SimTalk] - LockoutZone

Statistics Report [described] &gt; Stopped Time

Tab Statistics [material flow objects]

LEDs and States of the Material Flow Objects in 2D

State Graphic

in 3D

###### Paused [state, material flow objects]

A material flow or fluid resource is paused , when it is not working on parts due to a pause.

The object may resume processing once you terminate the pause, by selecting Planned from the dropdown list Paused/Planned/Unplanned .

**Note**

When a station fails, and a pause occurs during the failure, the failure time of the station will still be consumed, although the station is paused.

**Note**

When a Worker/Exporter is brokered to the paused station, it remains brokered to the station while it is paused. Statistics of the Worker/Exporter does not count this time as waiting .

Statistics counts the times during which these two states overlap, as pause time.

Plant Simulation only increments the counter for pauses and unplanned times when the duration of the pause or shift pause is not 0.

<!-- image -->

The LED of a paused station is blue

.

3D shows the State Graphic of the object as a colored ring on a pole by default.

The Statistics Report shows the Paused Time below Resource Statistics of Stationary Resources .

If an object changes to the unplanned state, the Unplanned Control is called. To be backwardcompatible, Plant Simulation also set the attribute Pause to true when Unplanned is set to true. Unplanned is the state used for statistics and the read-only attribute ResCurrentState returns Unplanned .

SimTalk

ResCurrentState [SimTalk] - material flow objects

StatEmptyPortion [SimTalk]

StatPausingPortion [SimTalk]

See also

Working [state, material flow objects]

Statistics Report [described] &gt; Paused Time Tab Statistics [material flow objects] Pause [SimTalk] - material flow objects LEDs and States of the Material Flow Objects in 2D

State Graphic in 3D

###### Unplanned [state, material flow objects]

A material flow or fluid resource is unplanned , when the current time is outside of any shift of the ShiftCalendar to which the resource is assigned.

**Note**

Plant Simulation only increments the counter for pauses and unplanned times when the duration of the pause or shift pause is not 0.

**Note**

When a Worker/Exporter is brokered to the paused station, it remains brokered to the station while it is paused. Statistics of the Worker/Exporter does not count this time as waiting .

<!-- image -->

The LED of an unplanned station is light blue .

3D shows the state of the object as a colored ring on a pole by default.

SimTalk

ResCurrentState [SimTalk] - material flow objects

See also

ShiftCalendar [object]

Statistics Report [described] &gt; Paused Time

Tab Statistics [material flow objects]

Unplanned [SimTalk] - material flow objects

StatUnplannedCount [SimTalk]

StatUnplannedDelta [SimTalk]

StatUnplannedMu [SimTalk]

StatUnplannedPortion [SimTalk]

StatUnplannedTime [SimTalk]

LEDs and States of the Material Flow Objects in 2D

State Graphic

in 3D

###### Empty [state, material flow objects]

A material flow resource is empty , when no MU is booked on it and when the resource is not failed , not paused , or not stopped . The empty time always is part of the waiting time.

When the object has several processing places, as for example the ParallelStation , you can query if a MU is located on a certain processing place. When the respective station is empty, the method returns true.

The Statistics Report shows the Empty Time below Resource Statistics of Stationary Resources .

SimTalk

ResCurrentState [SimTalk] - material flow objects

See also

Statistics Report [described] &gt; Empty Time [material flow objects]

Failed [state - material flow objects]

Paused [state, material flow objects]

Stopped [state, material flow objects]

Waiting [state, material flow objects]

Tab Statistics [material flow objects]

Empty [SimTalk] - material flow objects

StatEmptyCount [SimTalk]

StatEmptyDelta [SimTalk]

StatEmptyMu [SimTalk]

StatEmptyPortion [SimTalk]

StatEmptyTime [SimTalk]

LEDs and States of the Material Flow Objects in 2D

###### Relative Occupation

The relative occupancy is the sum of all dwelling times of all MUs during the statistics collection period during which the object was not paused and not failed , divided by the capacity and the entire statistics collection period without counting pauses and failures.

The return value 0 stands for 0 percent, the return value 1 stands for 100 percent.

Take a ParallelStation for example with four processing stations that processes a single MU during the entire statistics collection period. It has a relative occupancy of 25 percent.

A Conveyor , which is fully occupied during the entire statistics collection period, has a relative occupancy of 100 % for example. If the distance of the MUs on the Conveyor is exactly as great as the length of the MU , the relative occupancy is 50%. The Speed of the connected Conveyors affects the relative occupancy or when the MU moves from the Conveyor onto a point-oriented object respectively. Relative occupancy plus relative empty time do not add up to 100% because it does not matter how much of the Conveyor is occupied during the time that it is not empty.

You can use this method to compute the average time a MU spent in the Buffer :

```simtalk
EventController.SimTime * Buffer.StatRelativeOccupation * Buffer.Capacity / Buffer.StatNumIn
```

Relative Occupation with Interruptions

The relative occupancy with interruptions is the sum of all dwelling times of all MUs on the object during the statistics collection period, divided by the capacity and the entire statistics collection period.

SimTalk

StatRelativeOccupation [SimTalk] - material flow objects

StatRelativeOccupation [SimTalk] - MUs

StatRelativeOccupation [SimTalk] - Tank

See also

Paused [state, material flow objects]

Failed [state - material flow objects]

Statistics Report [described] &gt; Material Flow Properties [material flow objects]

Tab Statistics [material flow objects]

##### Statistics Report

###### Statistics Report [described]

The Statistics Report shows a variety of statistics data on screen. You can also save it as a .htm file to the computer's hard disk.

- Resource Statistics of Stationary Resources
- Energy Statistics - Energy Statistics
- Resource Statistics of Moving Resources
- Resource Statistics of the Drain
- Importer Statistics
- Exporter and Worker Statistics
- Broker Statistics [described]
- Product Statistics of the MUs [statistics report]
- Driving Statistics of the Transporter [statistics report]

To open the statistics report, which shows Resource Statistics data of the selected object or class, select View &gt; Show Statistics Report in the dialog of the object.

<!-- image -->

You can also right-click the object in the Frame and select Show Statistics Report or you can select the object in the Frame and press F6 .

To show statistics data of several objects, select them ( Shift +click, or drag a marquee over them) in the Frame and press F6 .

To add one or several objects to an open report, select it/them and press F6 . The report adds the statistics of the objects, which you selected to the drop-down list.

<!-- image -->

To jump to any of the topics in the report, which interest you, select that topic from the drop-down list:

<!-- image -->

The report then shows that topic by itself on the page. To print just this page, click the button Print This Page . To show all topics in the display window, click Show All . To print the entire report, click Print .

To show a Tooltip with the name of the respective read-only attribute for this statistics value, drag the mouse over the column header and hold it there.

To save the report as an HTML file (*.htm or *.html) or as a text file (*.txt) click Save . Enter a name for the file and select the folder into which you want to save it.

To update the report with the current values, click Refresh .

The individual material flow objects also show the most important statistics values on the Tab Statistics .

**See also**

##### Methods for Accessing Statistics

Viewing the Statistics Report in the Step-by-Step Help .

Resource Statistics of Stationary Resources

###### Resource Statistics of Stationary Resources

This section of the resource statistics of stationary resources , i.e., the material flow objects proper, shows a number of values.

- Portions of the States which Accrued During the Statistics Collection Period
- Material Flow Properties [material flow objects]
- Working Time
- Waiting Time
- Blocked Time
- Powering up/down Time
- Stopped Time
- Failed Time
- Paused Time
- Set-up Time [statistics report]
- Empty Time [material flow objects]
- Rotation Time
- Moving Time [statistics report]

**Video on YouTube**

[https://youtu.be/PQhEriOzVzU?si=K4259NAQXWtluT2S&amp;t=347](https://youtu.be/PQhEriOzVzU?si=K4259NAQXWtluT2S&t=347)

**Portions of the States which Accrued During the Statistics Collection Period**

Shows the individual portions of the states Working , Set-up , Waiting , Blocked , Powering Up/down , Failed , Stopped , Paused , Unplanned , Empty , and the Portion of the time of the statistics collection period.

<!-- image -->

The subtopics further down in the report provide details about the states Working , Set-up , Waiting , Blocked , Powering Up/down , Failed , Stopped , Paused , Unplanned , and Empty , in the order in which they appear here.

**Note**

The values for Waiting , Working , Blocked , Setting-Up , Powering up/down , Failed , Stopped , Paused , and Unplanned should add up to 100 %.

The bar chart on the right-hand side displays the respective portions of the times.

<!-- image -->

| A bar with this color   | Means that the object is   | Looks like this English   | Looks like this German   |
|-------------------------|----------------------------|---------------------------|--------------------------|
| green                   | Working                    |                           |                          |
| brown                   | Setting-Up                 |                           |                          |
| gray                    | Waiting                    |                           |                          |
| yellow                  | Blocked                    |                           |                          |
| purple                  | Powering up/down           |                           |                          |
| red                     | Failed                     |                           |                          |
| pink                    | Stopped                    |                           |                          |
| blue                    | Paused                     |                           |                          |
| light blue              | Unplanned                  |                           |                          |

**Material Flow Properties [material flow objects]**

Shows a number of Material Flow Properties of the specified objects, which are of interest.

| Item English      | Description                                                                                                                                                                                                                                                                                                               | Read-only attribute                            | Item German         |
|-------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------|---------------------|
| Number of Entries | Shows the number of MUs that entered the object. When a MU enters the object, the object only counts the MU itself, not its contents: When a Transporter/ Container transporting several parts enters the object, the number of entries increases by 1, not by the number of parts located on the Transporter/Container ! | StatNumIn [SimTalk] - material flow objects    | Anzahl der Eingänge |
| Number of Exits   | Shows the number of MUs that exited the object. The restrictions described under Number of Entries apply.                                                                                                                                                                                                                 | StatNumOut [SimTalk] - material flow objects   | Anzahl der Ausgänge |
| Minimum Contents  | Shows the minimum number of MUs that was located on the object The restrictions described under Number of Entries apply.                                                                                                                                                                                                  | StatMinNumMU [SimTalk] - material flow objects | Minimaler Inhalt    |
| Maximum Contents  | Shows the maximum number of MUs that was located on the object. The restrictions described under Number of Entries apply.                                                                                                                                                                                                 | StatMaxNumMU [SimTalk] - material flow objects | Maximaler Inhalt    |
| Relatively Empty  | Shows the portion of the statistics collection period during which the object was Empty in relation to the time during which the object was available.                                                                                                                                                                    | StatRelativeEmptyP ortion [SimTalk]            | Relativ leer        |
| Relatively Full   | Shows the portion of the statistics collection period during which all temporary storage places of the                                                                                                                                                                                                                    | StatRelativeFullPorti on [SimTalk]             | Relativ voll        |

| Item English                              | Description                                                                                                                                                                                                                                                       | Read-only attribute                                       | Item German                            |
|-------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|----------------------------------------|
|                                           | Buffer were occupied in relation to the time during which the object was available.                                                                                                                                                                               |                                                           |                                        |
| Relative Occupation without Interruptions | Shows the sum of all dwelling times of all MUs during the statistics collection period during which the object was not paused and not failed . This sum is then divided by the capacity and the entire statistics collection period without pauses and failures . | StatRelativeOccupat ion [SimTalk] - material flow objects | Relative Belegung ohne Unterbrechungen |
| Relative Occupation with Interruptions    | Shows the time during which the object was occupied and paused and failed divided by the capacity and the statistics collection period.                                                                                                                           | StatRelativeOccupat ion [SimTalk] - material flow objects | Relative Belegung mit Unterbrechungen  |

**Working Time**

Shows details about the Working Time of the specified material flow objects.

<!-- image -->

| Item English       | Description                                                                                        | Read-only attribute          | Item German         |
|--------------------|----------------------------------------------------------------------------------------------------|------------------------------|---------------------|
| Portion            | Shows the portion of the statistics collection period during which the object worked.              | StatWorkingPortion [SimTalk] | Anteil              |
| Count              | Shows how often the object worked.                                                                 | StatWorkingCount [SimTalk]   | Anzahl              |
| Sum                | Shows the total time during which the object worked.                                               | StatWorkingTime [SimTalk]    | Summe               |
| Mean Value         | Shows the mean duration of the time spans during which the object worked.                          | StatWorkingMu [SimTalk]      | Mittelwert          |
| Standard Deviation | Shows the standard deviation of the time spans during which the object worked from the mean value. | StatWorkingDelta [SimTalk]   | Standardab weichung |

**See also**

Working [state, material flow objects]

Working Time

**Set-up Time [statistics report]**

Shows details about the Set-up Time of the material flow objects.

<!-- image -->

| Item English       | Description                                                                                   | Read-only attribute        | Item German         |
|--------------------|-----------------------------------------------------------------------------------------------|----------------------------|---------------------|
| Portion            | Shows the portion of the statistics collection period during which the object was setting-up. | StatSetUpPortion [SimTalk] | Anteil              |
| Count              | Shows how often the object was setting- up.                                                   | StatSetUpCount [SimTalk]   | Anzahl              |
| Sum                | Shows the total time the object was setting-up.                                               | StatSetupTime [SimTalk]    | Summe               |
| Mean Value         | Shows the mean duration of a set-up process.                                                  | StatSetUpMu [SimTalk]      | Mittelwert          |
| Standard Deviation | Shows the standard deviation of the set-up from the mean value.                               | StatSetUpDelta [SimTalk]   | Standardabweic hung |

See also

Setting-Up [state, material flow objects]

Set-up Time [general description]

**Waiting Time**

Shows details about the Waiting Time of the material flow objects.

<!-- image -->

| Item English       | Description                                                                           | Read-only attribute          | Item German         |
|--------------------|---------------------------------------------------------------------------------------|------------------------------|---------------------|
| Portion            | Shows the portion of the statistics collection period during which the object waited. | StatWaitingPortion [SimTalk] | Anteil              |
| Count              | Shows how often the object waited.                                                    | StatWaitingCount [SimTalk]   | Anzahl              |
| Sum                | Shows the total time during which the object waited.                                  | StatWaitingTime [SimTalk]    | Summe               |
| Mean Value         | Shows the mean duration of the objects waiting period.                                | StatWaitingMu [SimTalk]      | Mittelwert          |
| Standard Deviation | Shows the standard deviation of the waiting periods from the mean value.              | StatWaitingDelta [SimTalk]   | Standardabw eichung |

See also

Waiting [state, material flow objects]

Waiting Time

**Blocked Time**

Shows details about the Blocked Time of the material flow objects.

<!-- image -->

| Item English       | Description                                                                                              | Read-only attribute           | Item German         |
|--------------------|----------------------------------------------------------------------------------------------------------|-------------------------------|---------------------|
| Portion            | Shows the portion of the statistics collection period during which the object was blocked.               | StatBlockingPortion [SimTalk] | Anteil              |
| Count              | Shows how often the object was blocked.                                                                  | StatBlockingCount [SimTalk]   | Anzahl              |
| Sum                | Shows the total time during which the object was blocked.                                                | StatBlockingTime [SimTalk]    | Summe               |
| Mean Value         | Shows the mean duration of the time spans during which the object was blocked.                           | StatBlockingMu [SimTalk]      | Mittelwert          |
| Standard Deviation | Shows the standard deviation of the time spans during which the object was blocked, from the mean value. | StatBlockingDelta [SimTalk]   | Standardabweich ung |

**See also**

Blocked [state, material flow objects]

Blocked Time

**Powering up/down Time**

Shows details about the Powering up/down Time of the material flow objects.

**Note**

Plant Simulation only records this value if the station is not failed , not paused , not stopped , or not unplanned .

<!-- image -->

| Item English       | Description                                                                                                          | Read-only attribute                  | Item German         |
|--------------------|----------------------------------------------------------------------------------------------------------------------|--------------------------------------|---------------------|
| Portion            | Shows the portion of the statistics collection period during which the object was powering up or down.               | StatPoweringUpDownPo rtion [SimTalk] | Anteil              |
| Count              | Shows how often the object was powering up or down.                                                                  | StatPoweringUpDownC ount [SimTalk]   | Anzahl              |
| Sum                | Shows the total time during which the object was powering up or down.                                                | StatPoweringUpDownTi me [SimTalk]    | Summe               |
| Mean Value         | Shows the mean duration of the time spans during which the object was powering up or down.                           | StatPoweringUpDownM u                | Mittelwert          |
| Standard Deviation | Shows the standard deviation of the time spans during which the object was powering up or down, from the mean value. | StatPoweringUpDownD elta [SimTalk]   | Standardab weichung |

**See also**

Powering up/down [state, material flow objects]

Powering up/down Time

**Stopped Time**

**Stopped Time**

Shows details about the Stopped Time of the material flow objects.

<!-- image -->

| Item English       | Description                                                                                              | Read-only attribute                                  | Item German         |
|--------------------|----------------------------------------------------------------------------------------------------------|------------------------------------------------------|---------------------|
| Portion            | Shows the portion of the statistics collection period during which the object was stopped.               | StatStoppedPortion [SimTalk] - material flow objects | Anteil              |
| Count              | Shows how often the object was stopped.                                                                  | StatStoppedCount [SimTalk] - material flow objects   | Anzahl              |
| Sum                | Shows the total time during which the object was stopped.                                                | StatStoppedTime [SimTalk]                            | Summe               |
| Mean Value         | Shows the mean duration of the time spans during which the object was stopped.                           | StatStoppedMu [SimTalk] - material flow objects      | Mittelwert          |
| Standard Deviation | Shows the standard deviation of the time spans during which the object was stopped, from the mean value. | StatStoppedDelta [SimTalk] - material flow objects   | Standardabweich ung |

**See also**

Stopped [state, material flow objects]

Stopped Time

**Failed Time**

Shows details about the Failed Time of the material flow objects.

<!-- image -->

| Item English       | Description                                                                           | Read-only attribute       | Item German         |
|--------------------|---------------------------------------------------------------------------------------|---------------------------|---------------------|
| Portion            | Shows the portion of the statistics collection period during which the object failed. | StatFailPortion [SimTalk] | Anteil              |
| Count              | Shows how often the object failed.                                                    | StatFailCount [SimTalk]   | Anzahl              |
| Sum                | Shows the total time during which the object failed.                                  | StatFailTime [SimTalk]    | Summe               |
| Mean Value         | Shows the mean duration of a failure of the object.                                   | StatFailMu [SimTalk]      | Mittelwert          |
| Standard Deviation | Shows the standard deviation of the failure time from the mean value.                 | StatFailDelta [SimTalk]   | Standardabweic hung |

See also

Failed [state - material flow objects]

Failed Time

**Paused Time**

**Paused Time**

Shows details about the Paused Time of the material flow objects.

<!-- image -->

| Item English       | Description                                                                        | Read-only attribute          | Item German         |
|--------------------|------------------------------------------------------------------------------------|------------------------------|---------------------|
| Portion            | Shows the portion of the statistics collection period which the object was paused. | StatPausingPortion [SimTalk] | Anteil              |
| Count              | Shows how often the object was paused.                                             | StatPausingCount [SimTalk]   | Anzahl              |
| Sum                | Shows the total time the object was paused.                                        | StatPausingTime [SimTalk]    | Summe               |
| Mean Value         | Shows the mean duration of a pause.                                                | StatPausingMu [SimTalk]      | Mittelwert          |
| Standard Deviation | Shows the standard deviation of the length of pauses from the mean value.          | StatPausingDelta [SimTalk]   | Standardabw eichung |

**See also**

Paused [state, material flow objects]

Paused Time

**Empty Time [material flow objects]**

Shows details about the Empty Time of the material flow objects.

<!-- image -->

| Item English                                                                                    | Description                                                                                                          | Read-only attribute      | Item German         |
|-------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------|--------------------------|---------------------|
| Portion Shows the portion of the statistics collection period during which the object was empty | StatEmptyPortion [SimTalk]                                                                                           |                          | Anteil              |
| Count                                                                                           | Shows how often the object was empty.                                                                                | StatEmptyCount [SimTalk] | Anzahl              |
| Sum                                                                                             | Shows the total time during which the object was empty, i. e., was not Failed , was not Paused and was not Stopped . | StatEmptyTime [SimTalk]  | Summe               |
| Mean Value                                                                                      | Shows the mean duration of a time span during which the object was empty.                                            | StatEmptyMu [SimTalk]    | Mittelwert          |
| Standard Deviation                                                                              | Shows the standard deviation of the time spans during which the object was empty from the mean value.                | StatEmptyDelta [SimTalk] | Standarda bweichung |

**See also**

Empty [state, material flow objects]

Empty Time [material flow objects]

**Rotation Time**

Shows details about the Rotation Time of the PickAndPlace Robot, the Turnplate , and the Turntable .

<!-- image -->

| Item English            | Description                                                                                                                                                                                                                                                                                                                                                                                       | Read-only attribute                                                                                                                                   | Item German            |
|-------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|
| Rotation empty portion  | Shows the portion of the statistics collection period during which the Turntable was rotating and no part was located on the table ( Empty ). Shows the portion of the statistics collection period during which the PickAndPlace robot was rotating without moving a part.                                                                                                                       | StatRotationEmptyPo rtion [SimTalk] - Turntable StatRotationEmptyPo rtion [SimTalk] - PickAndPlace                                                    | Drehung leer, Anteil   |
| Rotation empty sum      | Shows the total time during which the Turntable was rotating and no part was located on the table. Shows the total time during which the PickAndPlace robot was rotating without moving a part.                                                                                                                                                                                                   | StatRotationEmptyTi me [SimTalk] - Turntable StatRotationEmptyTi me [SimTalk] - PickAndPlace                                                          | Drehung leer, Summe    |
| Rotation loaded portion | Shows the portion of the statistics collection period during which the Turnplate was rotating and a part was located on the plate. Shows the portion of the statistics collection period during which the Turntable was rotating and a part was located on the table. Shows the portion of the statistics collection period during which the PickAndPlace robot was rotating while moving a part. | StatRotationLoadedP ortion [SimTalk] - Turnplate StatRotationLoadedP ortion [SimTalk] - Turntable StatRotationLoadedP ortion [SimTalk] - PickAndPlace | Drehung belegt, Anteil |
| Rotation loaded sum     | Shows the total time during which the Turnplate was rotating and a part was located on the plate. Shows the total time during which the Turntable was rotating and a part was located on the table, Shows the total time during which the PickAndPlace robot was rotating while moving a part.                                                                                                    | StatRotationLoadedT ime [SimTalk] - Turnplate StatRotationLoadedT ime [SimTalk] - Turntable                                                           | Drehung belegt, Summe  |

| Item English   | Description   | Read-only attribute                              | Item German   |
|----------------|---------------|--------------------------------------------------|---------------|
|                |               | StatRotationLoadedT ime [SimTalk] - PickAndPlace |               |

**See also**

PickAndPlace Robot

Turnplate [object]

Turntable [object]

**Moving Time [statistics report]**

Shows details about the Moving Time of the Converter .

<!-- image -->

| Item English          | Description                                                                                                                                   | Read-only attribute                | Item German            |
|-----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------|------------------------|
| Moving empty portion  | Shows the portion of the statistics collection period during which the Converter was raising or lowering itself and was not conveying a part. | StatMovingEmpt yPortion [SimTalk]  | Umsetzen leer Anteil   |
| Moving empty sum      | Shows the total time during which the Converter was raising or lowering itself and was not conveying a part.                                  | StatMovingEmpt yTime [SimTalk]     | Umsetzen leer Summe    |
| Moving loaded portion | Shows the portion of the statistics collection period during which the Converter was raising or lowering itself and was conveying a part.     | StatMovingLoad edPortion [SimTalk] | Umsetzen belegt Anteil |
| Moving loaded sum     | Shows the total time during which the Converter was raising or lowering itself and was conveying a part.                                      | StatMovingLoad edTime [SimTalk]    | Umsetzen belegt Summe  |

**See also**

**Converter [object]**

###### Energy Statistics - Energy Statistics

Shows details about Energy Statistics of the material flow objects.

<!-- image -->

**Note**

The energy states of the material flow objects differ from the resource states with the same name. The values for the resource states refer to the statistics collection period, while the values for the energy states refer to the total energy consumption.

<!-- image -->

| A bar with this color in Statistics Report and Chart   | Looks like this English   | Looks like this German   | Means that the object is   |
|--------------------------------------------------------|---------------------------|--------------------------|----------------------------|
| green                                                  |                           |                          | working                    |
| brown                                                  |                           |                          | setting-up                 |
| yellow                                                 |                           |                          | operational                |
| red                                                    |                           |                          | failed                     |
| light gray                                             |                           |                          | on standby                 |
| dark gray                                              |                           |                          | off                        |

| Item English       | Description                                                                                 | Read-only attribute                                | Item German      |
|--------------------|---------------------------------------------------------------------------------------------|----------------------------------------------------|------------------|
| Total consumptio n | Shows the sum of the total energy consumption.                                              | StatEnergyTotalConsumption [SimTalk]               | Gesamtverbra uch |
| Working            | Shows the portion of the total energy consumption during which the object was working .     | StatEnergyWorkingConsumptio nPortion [SimTalk]     | Arbeitend        |
| Setting-up         | Shows the portion of the total energy consumption during which the object was setting-up .  | StatEnergySetupConsumptionP ortion [SimTalk]       | Rüstend          |
| Operational        | Shows the portion of the total energy consumption during which the object was operational . | StatEnergyOperationalConsum ptionPortion [SimTalk] | Betriebsbereit   |
| Failed             | Shows the portion of the total energy consumption during which the object was failed .      | StatEnergyFailConsumptionPor tion [SimTalk]        | Gestört          |
| Standby            | Shows the portion of the total energy consumption during which the object was on standby .  | StatEnergyStandbyConsumptio nPortion [SimTalk]     | Standby          |
| Off                | Shows the portion of the total energy consumption during which the object was off .         | StatEnergyOffConsumptionPort ion [SimTalk]         | Aus              |

**See also**

**Energy Statistics [button]**

Resource Statistics of Moving Resources

Resource Statistics of Moving Resources

Transporter and Container can load and transport other MUs , they thus act as resources and provide resource statistics .

This section of the resource statistics of the moving resources Transporter and Container shows the:

- Material Flow Properties [MUs]
- Empty Time [MUs]

**See also**

**Resource Statistics [material flow objects]**

**Material Flow Properties [MUs]**

Shows Material Flow Properties of the MUs , which are of interest:

| Item English                              | Description                                                                                                                                                                                                                                                                                                              | Read-only attribute                                       | Item German                            |
|-------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|----------------------------------------|
| Number of Entries                         | Shows the number of MUs that entered the object. When a MU enters the object, the object only counts the MU itself, not its contents: When a Transporter/Container transporting several parts enters the object, the number of entries increases by 1, not by the number of parts located on the Transporter/Container ! | StatNumIn [SimTalk] - material flow objects               | Anzahl der Eingänge                    |
| Number of Exits                           | Shows the number of MUs that exited the object. The rules described under Number of Entries apply.                                                                                                                                                                                                                       | StatNumOut [SimTalk] - material flow objects              | Anzahl der Ausgänge                    |
| Minimum Contents                          | Shows the minimum number of MUs that was located on the object The rules described under Number of Entries apply.                                                                                                                                                                                                        | StatMinNumMU [SimTalk] - material flow objects            | Minimaler Inhalt                       |
| Maximum Contents                          | Shows the maximum number of MUs that was located on the object. The rules described under Number of Entries apply.                                                                                                                                                                                                       | StatMaxNumMU [SimTalk] - material flow objects            | Maximaler Inhalt                       |
| Empty Time                                | Shows the portion of the statistics collection period during which the object was Empty .                                                                                                                                                                                                                                | StatEmptyPortion [SimTalk]                                | Leerzeit                               |
| Relative Occupation without Interruptions | Shows the sum of all dwelling times of all MUs during the statistics collection period during which the object was not paused and not failed . This sum is then divided by the capacity and the entire statistics collection period without pauses and failures .                                                        | StatRelativeOccupa tion [SimTalk] - material flow objects | Relative Belegung ohne Unterbrechungen |
| Relative Occupation with Interruptions    | Shows the time during which the object was occupied and paused and failed divided by the capacity and the statistics collection period.                                                                                                                                                                                  | StatRelativeOccupa tion [SimTalk] - material flow objects | Relative Belegung mit Unterbrechungen  |

**Empty Time [MUs]**

Shows details about the Empty Time of the Transporters or of the Containers .

| Item English       | Description                                                                                                           | Read-only attribute        | Item German         |
|--------------------|-----------------------------------------------------------------------------------------------------------------------|----------------------------|---------------------|
| Portion            | Shows the portion of the statistics collection period during which the object was empty.                              | StatEmptyPortion [SimTalk] | Anteil              |
| Count              | Shows how often the object was empty.                                                                                 | StatEmptyCount [SimTalk]   | Anzahl              |
| Sum                | Shows the total time during which the object was empty, i.e., was not Failed , was not Paused , and was not Stopped . | StatEmptyTime [SimTalk]    | Summe               |
| Mean Value         | Shows the mean duration of a time span during which the object was empty.                                             | StatEmptyMu [SimTalk]      | Mittelwerk          |
| Standard Deviation | Shows the standard deviation of the time spans during which the object was empty from the mean value.                 | StatEmptyDelta [SimTalk]   | Standardabw eichung |

**See also**

Empty [state, material flow objects]

Resource Statistics of the Drain

Resource Statistics of the Drain

Shows details about the parts which the objects of type Drain removed from your plant.

This section of the resource statistics shows:

- Cumulated Statistics of the Parts which the Drain Removed From the Plant
- Part Types Which the Drain Removed From the Plant
- Detailed Statistics of the Part Types which the Drain Deleted

See also

Drain [object]

**Cumulated Statistics of the Parts which the Drain Removed From the Plant**

Shows the cumulated statistics of the parts which the Drain removed from the plant.

| Item English   | Description                                                                                                                                                                                                                                                                                                                                                        | Read-only attribute   | Item German   |
|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------|---------------|
| Working        | Shows the mean processing time of the investigated parts. This is the sum of the return values of the read- only attributes StatProdWorkingPortion [SimTalk] - Drain , StatStoreWorkingPortion [SimTalk] - Drain , and StatTranspWorkingPortion [SimTalk] - Drain multiplied with the return value of StatAvgLifeSpan .                                            | -                     | Arbeitend     |
| Set-up         | Shows the mean set-up time of the investigated parts. This is the sum of the return values of the read-only attributes StatProdSetupPortion [SimTalk] - Drain , StatStoreSetUpPortion [SimTalk] - Drain , and StatTranspSetupPortion [SimTalk] - Drain multiplied with the return value of StatAvgLifeSpan [SimTalk] - Drain .                                     | -                     | Rüstend       |
| Waiting        | Shows the mean Waiting time of the investigated parts. This is the sum of the return values of the read-only attributes StatProdWaitingPortion [SimTalk] - Drain , StatStoreWaitingPortion [SimTalk] - Drain and StatTranspWaitingPortion [SimTalk] - Drain multiplied with the return value of StatAvgLifeSpan [SimTalk] - Drain .                                | -                     | Wartend       |
| Stopped        | Shows the mean time that the investigated parts were located on a stopped resource. This is the sum of the return values of the read-only attributes StatProdStoppedPortion [SimTalk] - Drain , StatStoreStoppedPortion [SimTalk] - Drain , and StatTranspStoppedPortion [SimTalk] - Drain multiplied with the return value of StatAvgLifeSpan [SimTalk] - Drain . | -                     | Angehalte n   |
| Failed         | Shows the mean time that the investigated parts were located on a failed resource. This is the sum of the return values of the read-only attributes StatProdFailPortion [SimTalk] - Drain , StatStoreFailPortion [SimTalk] - Drain , and StatTranspFailPortion [SimTalk] - Drain multiplied with the return value of StatAvgLifeSpan [SimTalk] - Drain .           | -                     | Gestört       |
| Paused         | Shows the mean time that the investigated parts were located on a paused resource. This is the sum of the return values of the read-only attributes StatProdPausingPortion [SimTalk] - Drain ,                                                                                                                                                                     | -                     | Pausiert      |

| Item English         | Description                                                                                                                                                                                           | Read-only attribute                      | Item German             |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------|-------------------------|
|                      | StatStorePausingPortion [SimTalk] - Drain , and StatTranspPausingPortion [SimTalk] - Drain multiplied with the return value of StatAvgLifeSpan [SimTalk] - Drain .                                    |                                          |                         |
| Mean Life Time       | Shows the mean life time (throughput time) of all investigated parts.                                                                                                                                 | StatAvgLifeSpan [SimTalk] - Drain        | Mittlere Durchlaufz eit |
| Mean Exit Time       | Shows the average time interval between exits of the MUs which the Drain removed from the plant.                                                                                                      | StatAvgExitInterv al [SimTalk]           | Mittlere Austrittszei t |
| Total Throughp ut    | Shows the total throughput of all parts, which passed through the Drain and which it removed from the plant.                                                                                          | StatDeleted [SimTalk] - Drain            | Gesamtdur chsatz        |
| Throughp ut per Hour | Shows the number of MUs that the Drain removed from the plant in an hour over all observed times during which the Drain was available.                                                                | StatThroughputPe rHour [SimTalk] - Drain | Durchsatz pro Stunde    |
| Throughp ut per Day  | Shows the number of MUs that the Drain removed from the plant in a day over all observed times during which the Drain was available. This is the value of the throughput per hour multiplied with 24. | StatThroughputPe rDay [SimTalk] - Drain  | Durchsatz pro Tag       |

Also compare the Detailed Statistics Table [Drain] , which provides additional values of interest.

**Part Types Which the Drain Removed From the Plant**

Shows all part types (mobile objects, MUs ) which the Drains removed from the plant.

| Item English    | Description                                                                                                                                                                                                                                                                                        | Read-only attribute           | Item German   |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------|---------------|
| All Types       | Shows the number of MUs that the Drain removed from the plant. The Drain only counts the MU itself, not its contents. Let's say a Container loaded with several Parts is removed from the plant by the Drain , then StatDeleted is increased by one, not by the number of parts on the Container . | StatDeleted [SimTalk] - Drain | Alle Typen    |
| Name of the MUs | Shows the amount of MUs with this name which the Drain removed from the plant.                                                                                                                                                                                                                     | -                             | Name des BEs  |
| Name of the MUs | Shows the amount of MUs with this name which the Drain removed from the plant.                                                                                                                                                                                                                     | -                             | Name der BEs  |
| …               | Shows the amount of MUs with this name which the Drain removed from the plant.                                                                                                                                                                                                                     | -                             | …             |

Also compare the Detailed Statistics Table [Drain] , which provides additional values of interest.

**Detailed Statistics of the Part Types which the Drain Deleted**

Shows the detailed statistics of the part types which the Drains in your model removed from the plant.

The Detailed Statistics Table [Drain] and the method typeStatistics return all statistics values of MUs with the same name which the Drain removed from the plant. The table below only shows the most important of these values.

| Item English   | Description                                                                                                                                    | Item German   |
|----------------|------------------------------------------------------------------------------------------------------------------------------------------------|---------------|
| Working        | Shows the portions of the Working times of the investigated parts on a resource of the type Production , Storage or Transport .                | Arbeitend     |
| Set-up         | Shows the portions of the Setting-Up times of the investigated parts on a resource of the type Production , Storage or Transport .             | Rüstend       |
| Waiting        | Shows the portions of the Waiting times of the investigated parts on a resource of the type Production , Storage or Transport .                | Wartend       |
| Stopped        | Shows the portions of the Stopped times of the investigated parts on a resource of the type Production , Storage or Transport .                | Angehalten    |
| Failed         | Shows the portions of the times which the investigated parts were located on a Failed resource of the type Production , Storage or Transport . | Gestört       |
| Paused         | Shows the portions of the times which the investigated parts were located on a Paused resource of the type Production , Storage or Transport . | Pausiert      |
| Sum            | Shows the sum of the columns Working , Set-up , Waiting , Failed , Stopped , and Paused .                                                      | Summe         |

This topic shows the detailed statistics of the part types which the Drain removed from the plant.

| Item English                        | Description                                                                                     | Item German                       |
|-------------------------------------|-------------------------------------------------------------------------------------------------|-----------------------------------|
| Mean Value of the Life Time         | Shows the mean life time (throughput time) of all investigated parts.                           | Mittelwert der Lebenszeit         |
| Standard Deviation of the Life Time | Shows the standard deviation of the mean life time (throughput time) of all investigated parts. | Standardabweichung der Lebenszeit |
| Minimum of the Life Time            | Shows the minimum of the life time (throughput time) of all investigated parts.                 | Minimum der Lebenszeit            |

| Item English                        | Description                                                                                                                       | Item German                          |
|-------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|--------------------------------------|
| Maximum of the Life Time            | Shows the maximum of the life time (throughput time) of all investigated parts.                                                   | Maximum der Lebenszeit               |
| Mean Value of the Exit Time         | Shows the mean exit time (throughput time) of all investigated parts.                                                             | Mittelwert der Austrittszeit         |
| Standard Deviation of the Exit Time | Shows the standard deviation of the mean exit time (throughput time) of all investigated parts.                                   | Standardabweichung der Austrittszeit |
| Minimum of the Exit Time            | Shows the minimum of the exit time (throughput time) of all investigated parts.                                                   | Minimum der Austrittszeit            |
| Maximum of the Exit Time            | Shows the maximum of the exit time (throughput time) of all investigated parts.                                                   | Maximum der Austrittszeit            |
| Total Throughput                    | Shows the total throughput of all parts, which passed through the Drain and which it removed from the plant.                      | Gesamtdurchsatz                      |
| Throughput per Hour                 | Shows the mean throughput per hour. Statistics only collects values for full hours and only for hours during which parts arrived. | Durchsatz pro Stunde                 |
| Throughput per Day                  | Shows the mean throughput per day. Statistics only collects values for full days and only for days during which parts arrived.    | Durchsatz pro Stunde                 |

**Importer Statistics**

###### Importer Statistics

This topic shows details about importer statistics .

**It shows:**

- Importers Waiting for Services and Parts
- Waiting Times for Services and Parts
- Waiting Times for Parts
- Waiting Times for Set-up Exporters

See also

Tab Importer

**Importers Waiting for Services and Parts**

Shows details about the statistics of importers which were waiting for services and/or parts .

| Item English                   | Description                                                                                                                        | Read-only attribute                                                                             | Item German                  |
|--------------------------------|------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|------------------------------|
| Total Delay                    | Shows the portion of the statistics collection period during which the object was Waiting for MUs and for Exporters/services .     | StatWaitingSetUpExpPortio n [SimTalk] + StatWaitingResPortion [SimTalk] - material flow objects | Gesamtverzög erung           |
| Waiting for Services and Parts | Shows the portion of the statistics collection period during which the object was waiting for MUs and/or for Exporters/services .  | StatWaitingResPortion [SimTalk] - material flow objects                                         | Warten auf Dienste und Teile |
| Waiting for Parts              | Shows the portion of the statistics collection period during which the object was setting-up and for which parts were missing.     | StatWaitingPartsPortion [SimTalk]                                                               | Warten auf Teile             |
| Waiting for Set- up Exporters  | Shows the portion of the statistics collection period during which the object was setting-up and for which Exporters were missing. | StatWaitingSetUpExpPortio n [SimTalk]                                                           | Warten auf Rüstexporter      |

**Waiting Times for Services and Parts**

Shows details about the waiting times for services and parts .

| Item English                 | Description                                                                                                                          | Read-only attribute                                                                                       | Item German         |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|---------------------|
| Portion waiting for services | Shows the portion of the statistics collection period during which the object was Waiting for Exporters and/or mounting parts .      | StatWaitingResPortion [SimTalk] - material flow objects StatWaitingResPortion [SimTalk] - AssemblyStation | Anteil              |
| Number                       | Shows how often the object was waiting for Exporters and/or mounting parts .                                                         | StatWaitingResCount [SimTalk] - material flow objects StatWaitingResCount [SimTalk] - AssemblyStation     | Anzahl              |
| Sum                          | Shows the total time during which the object was waiting for Exporters and/or mounting parts .                                       | StatWaitingResTime [SimTalk] - material flow objects StatWaitingResTime [SimTalk] - AssemblyStation       | Summe               |
| Mean Value                   | Shows the mean duration of a time span which the object was waiting for Exporters and/or mounting parts .                            | StatWaitingResMu [SimTalk] - material flow objects StatWaitingResMu [SimTalk] - AssemblyStation           | Mittelwert          |
| Standard Deviation           | Shows the standard deviation of the time spans which the object was waiting for Exporters and/or mounting parts from the mean value. | StatWaitingResDelta [SimTalk] - material flow objects StatWaitingResDelta [SimTalk] - AssemblyStation     | Standardab weichung |

**Waiting Times for Parts**

Shows details about the waiting times for parts in the order in which they appear here.

| Item English              | Description                                                                                                                  | Read-only attribute                | Item German         |
|---------------------------|------------------------------------------------------------------------------------------------------------------------------|------------------------------------|---------------------|
| Portion waiting for parts | Shows the portion of the statistics collection period which the AssemblyStation spent Waiting for mounting parts .           | StatWaitingPartsPo rtion [SimTalk] | Anteil              |
| Number                    | Shows how often the AssemblyStation was waiting for mounting parts .                                                         | StatWaitingPartsCo unt [SimTalk]   | Anzahl              |
| Sum                       | Shows the total time which the AssemblyStation was waiting for mounting parts .                                              | StatWaitingPartsTi me [SimTalk]    | Summe               |
| Mean Value                | Shows the mean duration of a time span which the AssemblyStation was waiting for mounting parts .                            | StatWaitingPartsM u [SimTalk]      | Mittelwert          |
| Standard Deviation        | Shows the standard deviation of the time spans which the AssemblyStation was waiting for mounting parts from the mean value. | Animate Every x-th Pixel           | Standardab weichung |

**Waiting Times for Set-up Exporters**

Shows details about the statistics of importers , which were waiting for set-up exporters .

| Item English                                | Description                                                                                                                            | Read-only attribute                           | Item German                                    |
|---------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|------------------------------------------------|
| Portion waiting for Set- up Exporters       | Shows the portion of the statistics collection period during which the object was setting- up and during which Exporters were missing. | StatWaitingSetUpExpP ortion [SimTalk]         | Anteil                                         |
| Number                                      | Shows how often the object was setting-up and for which Exporters were missing.                                                        | StatWaitingSetUpExpC ount [SimTalk]           | Anzahl                                         |
| Sum                                         | Shows the total time the object was setting-up and for which Exporters were missing.                                                   | StatWaitingSetUpExpTi me [SimTalk]            | Summe                                          |
| Mean Value                                  | Shows the mean duration of a setting- up process for which Exporters were missing.                                                     | StatWaitingSetUpExpM u [SimTalk]              | Mittelwert                                     |
| Standard Deviation                          | Shows the standard deviation of a setting- up process for which Exporters were missing.                                                | StatWaitingSetUpExpD elta [SimTalk]           | Standardabweichung                             |
| Waiting Time while the Resource Waited      | Shows the total time the object was set up and waiting and for which Exporters were missing.                                           | StatWaitingSetUpExpW aitingPortion [SimTalk]  | Wartezeit, während die Ressource wartete       |
| Waiting Time while the Resource Worked      | Shows the total time the object was set up and processing and for which Exporters were missing.                                        | StatWaitingSetUpExpW orkingPortion [SimTalk]  | Wartezeit, während die Ressource arbeitete     |
| Waiting Time while the Resource was Blocked | Shows the total time the object was set up and blocked and for which Exporters were missing.                                           | StatWaitingSetUpExpBl ockingPortion [SimTalk] | Wartezeit, während die Ressource blockiert war |

See also

Waiting [state, material flow objects]

Exporter and Worker Statistics

Exporter and Worker Statistics

This topic shows details about the Exporter and Worker statistics .

**It shows:**

- Service Statistics - States - Capacities and States of the Exporters
- Service Statistics - States - Time Portions of the Exporters
- Worker Statistics - Traveled Distance by Workers

See also

Exporter [object]

Worker [object]

**Service Statistics - States - Capacities and States of the Exporters**

Shows details about the capacities and of the states of the Exporters .

| Item English                   | Description                                                                                    | Read-only attribute                       | Item German                    |
|--------------------------------|------------------------------------------------------------------------------------------------|-------------------------------------------|--------------------------------|
| Sum Free Capacity              | Shows the sum of the released capacity which the Exporter placed with any importer .           | StatSumFreeCapacity [SimTalk]             | Summe freier Kapazität         |
| Sum Mediated Capacity          | Shows the sum of the brokered capacity.                                                        | StatSumMediatedCapacit y [SimTalk]        | Summe vermittelter Kapazität   |
| Minimum Free Capacity          | Shows the minimum capacity, which is available.                                                | StatMinFreeCapacity [SimTalk]             | Minimum freier Kapazität       |
| Maximum Free Capacity          | Shows the maximum available capacity, which is available.                                      | StatMaxFreeCapacity [SimTalk]             | Maximum freier Kapazität       |
| Minimum Mediated Capacity      | Shows the minimum brokered capacity.                                                           | StatMinMediatedCapacit y [SimTalk]        | Minimum vermittelter Kapazität |
| Maximum Mediated Capacity      | Shows the maximum brokered capacity.                                                           | StatMaxMediatedCapacit y [SimTalk]        | Maximum vermittelter Kapazität |
| Ready                          | Shows the portion of the statistics collection period during which the Exporter was available. | StatExporterOperational Portion [SimTalk] | Bereit                         |
| Failed                         | Shows the portion of the statistics collection period during which the Exporter was failed.    | StatExporterFailedPortio n [SimTalk]      | Gestört                        |
| Paused                         | Shows the portion of the statistics collection period during which the Exporter was paused.    | StatExporterPausedPorti on [SimTalk]      | Pausiert                       |
| Unplanned                      | Shows the portion of the statistics collection period during which the Exporter was unplanned. | StatExporterUnplannedP ortion [SimTalk]   | Ungeplant                      |
| Start of Statistics Collection | Shows the time at which statistics collection started.                                         | -                                         | Beginn der Statistikerfassu ng |

**Service Statistics - States - Time Portions of the Exporters**

Shows details about the operating times of the different types of Exporters .

| Item English          | Description                                                                                                                                                                                                                                                                                       | Read-only attribute                                                                    | Item German           |
|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------|-----------------------|
| Set-up Portion        | Shows the portion of the overall statistics time during which the object was setting-up for the services ( Exporters ) weighted with the capacity. The overall statistics time is the statistics collection period without the unplanned time and the paused time .                               | StatServicesSetupPort ion [SimTalk] - Exporter                                         | Rüstanteil            |
| Working Portion       | Shows the portion of the overall statistics time during which the Exporter was working, weighted with the capacity. The overall statistics time is the statistics collection period without the unplanned time and the paused time .                                                              | StatServicesWorkingP ortion [SimTalk] - Exporter                                       | Arbeitsan teil        |
| Repairing Portion     | Shows the portion of the overall statistics time during which the Exporter spent for repairs, weighted with the capacity. The overall statistics time is the statistics collection period without the unplanned time and the paused time .                                                        | StatServicesRepairing Portion [SimTalk] - Exporter                                     | Repariera nteil       |
| Transporti ng Portion | Shows the portion of the overall statistics time during which the Worker was transporting parts from Workplace to Workplace . The overall statistics time is the statistics collection period without the unplanned time and the paused time .                                                    | StatServicesTransporti ngPortion [SimTalk]                                             | Trageante il          |
| En-route to Job       | Shows the portion of the overall statistics time during which the services of the Worker spent for getting to the Workplace or back to the WorkerPool to get the next job order. The overall statistics time is the statistics collection period without the unplanned time and the paused time . | StatServicesEnRouteI dlePortion [SimTalk] , StatServicesEnRouteT oJobPortion [SimTalk] | Unterweg s zu Auftrag |
| Waiting for Importers | Shows the portion of the overall statistics time during which the Exporter spent waiting for an importer , weighted with the capacity. The overall statistics time is the statistics collection period without the unplanned time and the paused time .                                           | StatServicesWaitingI mpPortion [SimTalk] - Exporter                                    | Warten auf Importer   |
| Waiting for MUs       | Shows the portion of the overall statistics time during which the Exporter spent waiting for a MU at the importer , weighted with the capacity. The                                                                                                                                               | StatServicesWaitingM UPortion [SimTalk] - Exporter                                     | Warten auf BEs        |

| Item English   | Description                                                                                                                                                                                                                         | Read-only attribute                             | Item German    |
|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------|----------------|
|                | overall statistics time is the statistics collection period without the unplanned time and the paused time .                                                                                                                        |                                                 |                |
| Failed Portion | Shows the portion of the overall statistics time during which the Exporter was failed, weighted with the capacity. The overall statistics time is the statistics collection period without the unplanned time and the paused time . | StatServicesFailedPort ion [SimTalk] - Exporter | Gestörtan teil |

**Worker Statistics - Traveled Distance by Workers**

Shows details about the distances which the Workers in your simulation model walked.

| Item English      | Description                                                                                                                                     | Read-only attribute                      | Item German               |
|-------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------|---------------------------|
| Traveled Distance | Shows the distance which the Worker traveled from the WorkerPool to the Workplaces attached to the stations and between the stations in meters. | StatTraveledDist ance [SimTalk] - Worker | Zurückgelegt e Wegstrecke |

**Broker Statistics [described]**

###### Broker Statistics [described]

Broker Statistics shows details about the Broker statistics .

**Note**

For Broker hierarchies , i.e., for several Brokers connected with Connectors , the brokered services are only considered for the Broker which you typed into the Importer . This also applies when the service is provided by sub-Brokers .

| Item English                      | Description                                                                                                                                                               | Read-only attribute               | Item German                            |
|-----------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------|----------------------------------------|
| Sum Open Requests                 | Shows the total number of open requests.                                                                                                                                  | StatOpenRequests [SimTalk]        | Summe offener Anfragen                 |
| Sum Satisfied Requests            | Shows the total number of satisfied requests.                                                                                                                             | StatSatisfiedReques ts [SimTalk]  | Summe befriedigter Anfragen            |
| Sum Open Capacity                 | Shows the total amount of open capacities.                                                                                                                                | StatOpenCapacity [SimTalk]        | Summe offener Kapazität                |
| Sum Mediated Capacity             | Shows the total amount of brokered capacities.                                                                                                                            | StatMediatedCapaci ty [SimTalk]   | Summe vermittelter Kapazität           |
| Mediation Time Sum                | Shows the sum of the times, which the Broker required to meet all satisfied requests, i. e., the times during which the importer/importers were waiting for the services. | StatMediationTime [SimTalk]       | Summe Vermittlungsdau er               |
| Mediation Time Mean               | Shows the medium duration of the time the Broker required to meet a single request.                                                                                       | StatMediationTime Mu [SimTalk]    | Mittelwert Vermittlungsdau er          |
| Mediation Time Standard Deviation | Shows the standard deviation of the medium mediation time.                                                                                                                | StatMediationTimeD elta [SimTalk] | Standardabweich ung Vermittlungsdau er |
| Dwelling Time Sum                 | Shows the sum of the times during which Exporters stayed at importers , i. e., the times during which the services were procured.                                         | StatStayTime [SimTalk]            | Summe Verweildauer                     |

| Item English                     | Description                                                                   | Read-only attribute         | Item German                      |
|----------------------------------|-------------------------------------------------------------------------------|-----------------------------|----------------------------------|
| Dwelling Time Mean               | Shows the medium duration during which Exporters stayed at a single importer. | StatStayTimeMu [SimTalk]    | Mittelwert Verweildauer          |
| Dwelling Time Standard Deviation | Shows the standard deviation of the dwelling time from the mean value.        | StatStayTimeDelta [SimTalk] | Standardabweich ung Verweildauer |

**Dwelling Time**

This topic shows details about the dwelling time .

**Note**

When a service is fulfilled by several Workers or Exporters , Plant Simulation records this time interval only once. The same applies for the count . For the time during which the Worker was en-route to his job, statistics counts the time of the Worker who was en-route the longest.

| Item English       | Description                                                                                                                      | Read-only attribute   | Item German         |
|--------------------|----------------------------------------------------------------------------------------------------------------------------------|-----------------------|---------------------|
| Services           | Shows the services, which the Broker procures.                                                                                   | serviceStat [SimTalk] | Dienste             |
| Count              | Shows how often the service in this row was procured, i. e., how often the Exporter/ Exporters stayed at the importer/importers. | serviceStat [SimTalk] | Anzahl              |
| Sum                | Shows the sum of the times during which the service in this row was procured.                                                    | serviceStat [SimTalk] | Summe               |
| Mean Value         | Shows the mean duration of the times during which the service in this row was procured.                                          | serviceStat [SimTalk] | Mittelwert          |
| Standard Deviation | Shows the standard deviation from the mean value of the times during which the service in this row was procured.                 | serviceStat [SimTalk] | Standardabw eichung |
| Minimum            | Shows the minimum time during which the service in this row was procured.                                                        | serviceStat [SimTalk] | Minimum             |
| Maximum            | Shows the maximum time during which the service in this row was procured.                                                        | serviceStat [SimTalk] | Maximum             |

**Mediation Time**

This topic shows details about the mediation time .

**Note**

When a service is fulfilled by several Workers or Exporters , Plant Simulation records this time interval only once. The same applies for the count . For the time during which the Worker was en-route to his job, statistics counts the time of the Worker who was en-route the longest.

| Item English        | Description                                                                                                                                                  | Read-only attribute   | Item German         |
|---------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------|---------------------|
| Services            | Shows the services, which the Broker mediates.                                                                                                               | serviceStat [SimTalk] | Dienste             |
| Count               | Shows how often the importer/importers were waiting for the mediation of the service in this row.                                                            | serviceStat [SimTalk] | Anzahl              |
| Sum                 | Shows the sum of the times during which the importer/ importers were waiting for the mediation of the service in this row.                                   | serviceStat [SimTalk] | Summe               |
| Mean Value          | Shows the mean duration of the times during which the importer/importers were waiting for the mediation of the service in this row.                          | serviceStat [SimTalk] | Mittelwert          |
| Standard Deviatio n | Shows the standard deviation from the mean value of the times during which the importer/importers were waiting for the mediation of the service in this row. | serviceStat [SimTalk] | Standardab weichung |
| Minimu m            | Shows the minimum time during which the importer/ importers were waiting for the mediation of the service in this row.                                       | serviceStat [SimTalk] | Minimum             |
| Maximu m            | Shows the maximum time during which the importer/ importers were waiting for the mediation of the service in this row.                                       | serviceStat [SimTalk] | Maximum             |

**See also**

Broker [object]

Product Statistics of the MUs

Product Statistics of the MUs [statistics report]

This topic shows details about the product statistics of the mobile objects Part , Container and Transporter .

It shows the:

- Cumulated Statistics of the Classes

**· Statistics of the Individual MUs**

See also

Part

Container

Transporter

Cumulated Statistics of the Classes

Cumulated Statistics of the Classes

Shows details about the cumulated statistics of the MU classes .

Product-Oriented Statistics of all Existing and Deleted MUs by Classes

This topic shows details about the product-oriented statistics of all existing MUs and of those, which were removed from the plant.

| Item English   | Description                                                                                                                                                                                                                                             | Read-only attribute              | Item German             |
|----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------------------|
| Count          | Shows how many MU instances of this class existed during the statistics collection period. Plant Simulation only counts those MUs whose product statistics was active during the simulation run. The MUs may be located in different Frame hierarchies. | StatCount [SimTalk]              | Anzahl                  |
| Deleted        | Shows how many MU instances of this class were removed from the plant during the statistics collection period. Plant Simulation only counts those MUs whose product statistics was active during the simulation run.                                    | StatDeleted [SimTalk] - MUs      | Gelöscht                |
| Mean Life Time | Shows the average life-span of the MUs , which were created and removed from the plant during the statistics collection period. Plant Simulation only counts those MUs whose product statistics was active during the simulation run.                   | StatAvgLifeSp an [SimTalk] - MUs | Mittlere Durchlau fzeit |

**Mean Time Portions of a MU Class of the Mean Life Time**

Shows details about the mean time portions of a MU class of the mean life time of that MU .

| Item English          | Description                                                                                                                                                                    | Read-only attribute                       | Item German            |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------|------------------------|
| Production Processing | Shows the portion of the statistics collection period during which the MU class was located on a material flow object of type Production that was processing parts.            | StatProdWorkingPorti on [SimTalk] - MUs   | Produkti on Arbeiten d |
| Set-up                | Shows the portion of the statistics collection period during which the MU class was located on a material flow object of type Production that was setting up for the MU class. | StatProdSetupPortion [SimTalk] - MUs      | Rüstend                |
| Waiting               | Shows the portion of the statistics collection period during which the MU class was located on a material flow object of type Production that was waiting.                     | StatProdWaitingPortio n [SimTalk] - MUs   | Wartend                |
| Stopped               | Shows the portion of the statistics collection period during which the MU class was located on a material flow object of type Production that was stopped.                     | StatProdStoppedPorti on [SimTalk] - MUs   | Angehalt en            |
| Failed                | Shows the portion of the statistics collection period during which the MU class was located on a material flow object of type Production that was failed.                      | StatProdFailPortion [SimTalk] - MUs       | Gestört                |
| Paused                | Shows the portion of the statistics collection period during which the MU class was located on a material flow object of type Production that was paused.                      | StatProdPausingPortio n [SimTalk] - MUs   | Pausiert               |
| Transport Processing  | Shows the portion of the statistics collection period during which the MU class was located on a material flow object of type Transport that was transporting parts.           | StatTranspWorkingPor tion [SimTalk] - MUs | Transpor t Arbeiten d  |
| Set-up                | Shows the portion of the statistics collection period during which the MU class was located on a material flow object of type Transport that was setting up for the MU class.  | StatTranspSetupPortio n [SimTalk] - MUs   | Rüstend                |
| Waiting               | Shows the portion of the statistics collection period during which the MU class was located on a material flow object of type Transport that was waiting.                      | StatTranspWaitingPort ion [SimTalk] - MUs | Wartend                |
| Stopped               | Shows the portion of the statistics collection period during which the MU class was located on a material flow object of type Transport that was stopped.                      | StatTranspStoppedPor tion [SimTalk] - MUs | Angehalt en            |

| Item English       | Description                                                                                                                                                            | Read-only attribute                       | Item German          |
|--------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------|----------------------|
| Failed             | Shows the portion of the statistics collection period during which the MU class was located on a material flow object of type Transport that was failed.               | StatTranspFailPortion [SimTalk] - MUs     | Gestört              |
| Paused             | Shows the portion of the statistics collection period during which the MU was located on a material flow object of type Transport that was paused.                     | StatTranspPausingPor tion [SimTalk] - MUs | Pausiert             |
| Storage Processing | Shows the portion of the statistics collection period during which the MU class was located on a material flow object of type Storage that was processing parts.       | StatStoreWorkingPorti on [SimTalk] - MUs  | Lagerun g Arbeiten d |
| Set-up             | Shows the portion of the statistics collection period during which the MU class was located on a material flow object of type Storage that was setting up for the MU . | StatStoreSetupPortion [SimTalk] - MUs     | Rüstend              |
| Waiting            | Shows the portion of the statistics collection period during which the MU class was located on a material flow object of type Storage that was waiting.                | StatStoreWaitingPorti on [SimTalk] - MUs  | Wartend              |
| Stopped            | Shows the portion of the statistics collection period during which the MU class was located on a material flow object of type Storage that was stopped.                | StatStoreStoppedPorti on [SimTalk] - MUs  | Angehalt en          |
| Failed             | Shows the portion of the statistics collection period during which the MU class was located on a material flow object of type Storage that was failed.                 | StatStoreFailPortion [SimTalk] - MUs      | Gestört              |
| Paused             | Shows the portion of the statistics collection period during which the MU class was located on a material flow object of type Storage that was paused.                 | StatStorePausingPorti on [SimTalk] - MUs  | Pausiert             |

**Statistics of the Individual MUs**

Shows details about the statistics of the individual MUs .

| Item English          | Description                                                                                                                                                                  | Read-only attribute                       | Item German            |
|-----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------|------------------------|
| Production Processing | Shows the portion of the statistics collection period during which the selected MU was located on a material flow object of type Production and was being processed.         | StatProdWorkingPort ion [SimTalk] - MUs   | Produkti on Arbeiten d |
| Set-up                | Shows the portion of the statistics collection period during which the selected MU was located on a material flow object of type Production that was setting up for the MU . | StatProdSetupPortio n [SimTalk] - MUs     | Rüstend                |
| Waiting               | Shows the portion of the statistics collection period during which the selected MU was located on a material flow object of type Production that was waiting.                | StatProdWaitingPorti on [SimTalk] - MUs   | Wartend                |
| Stopped               | Shows the portion of the statistics collection period during which the selected MU was located on a material flow object of type Production that was stopped.                | StatProdStoppedPorti on [SimTalk] - MUs   | Angehalt en            |
| Failed                | Shows the portion of the statistics collection period during which the selected MU was located on a material flow object of type Production that was failed.                 | StatProdFailPortion [SimTalk] - MUs       | Gestört                |
| Paused                | Shows the portion of the statistics collection period during which the selected MU was located on a material flow object of type Production that was paused.                 | StatProdPausingPorti on [SimTalk] - MUs   | Pausiert               |
| Transport Processing  | Shows the portion of the statistics collection period during which the selected MU was located on a material flow object of type Transport and was being processed.          | StatTranspWorkingPo rtion [SimTalk] - MUs | Transpor t Arbeiten d  |
| Set-up                | Shows the portion of the statistics collection period during which the selected MU was located on a material flow object of type Transport that was setting up for the MU .  | StatTranspSetupPorti on [SimTalk] - MUs   | Rüstend                |
| Waiting               | Shows the portion of the statistics collection period during which the selected MU was located on a material flow object of type Transport that was waiting.                 | StatTranspWaitingPo rtion [SimTalk] - MUs | Wartend                |

| Item English       | Description                                                                                                                                                               | Read-only attribute                       | Item German          |
|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------|----------------------|
| Stopped            | Shows the portion of the statistics collection period during which the selected MU was located on a material flow object of type Transport that was stopped.              | StatTranspStoppedPo rtion [SimTalk] - MUs | Angehalt en          |
| Failed             | Shows the portion of the statistics collection period during which the selected MU was located on a material flow object of type Transport that was failed.               | StatTranspFailPortion [SimTalk] - MUs     | Gestört              |
| Paused             | Shows the portion of the statistics collection period during which the selected MU was located on a material flow object of type Transport that was paused.               | StatTranspPausingPo rtion [SimTalk] - MUs | Pausiert             |
| Storage Processing | Shows the portion of the statistics collection period during which the selected MU was located on a material flow object of type Storage and was being processed.         | StatStoreWorkingPor tion [SimTalk] - MUs  | Lagerun g Arbeiten d |
| Set-up             | Shows the portion of the statistics collection period during which the selected MU was located on a material flow object of type Storage that was setting up for the MU . | StatStoreSetupPortio n [SimTalk] - MUs    | Rüstend              |
| Waiting            | Shows the portion of the statistics collection period during which the selected MU was located on a material flow object of type Storage that was waiting.                | StatStoreWaitingPort ion [SimTalk] - MUs  | Wartend              |
| Stopped            | Shows the portion of the statistics collection period during which the selected MU was located on a material flow object of type Storage that was stopped.                | StatStoreStoppedPor tion [SimTalk] - MUs  | Angehalt en          |
| Failed             | Shows the portion of the statistics collection period during which the selected MU was located on a material flow object of type Storage that was failed.                 | StatStoreFailPortion [SimTalk] - MUs      | Gestört              |
| Paused             | Shows the portion of the statistics collection period during which the selected MU was located on a material flow object of type Storage that was paused.                 | StatStorePausingPort ion [SimTalk] - MUs  | Pausiert             |

###### Driving Statistics of the Transporter

Driving Statistics of the Transporter

Driving Statistics of the Transporter [statistics report]

In addition to product and resource statistics the Transporter collects drive statistics data about failures, pauses, battery consumption and the number of jobs performed.

Note

Driving statistics is always active.

You can view:

- Usage of the Transporters
- Ready-Times
- Failures [Transporter]
- Pauses [Transporter]
- Battery [statistics]

See also

Transporter

**Usage of the Transporters**

Shows details about the usage of the Transporters .

| Item English        | Description                                                                                      | Read-only attribute                   | Item German        |
|---------------------|--------------------------------------------------------------------------------------------------|---------------------------------------|--------------------|
| Occupied with Order | Shows the portion of its life-span during which the Transporter had an order and was loaded.     | StatOrderOccPortion [SimTalk]         | Belegt mit Auftrag |
| Empty with Order    | Shows the portion of its life-span during which the Transporter had an order and was not loaded. | StatOrderEmptyPortion [SimTalk]       | Leer mit Auftrag   |
| Return to Base      | Shows the portion of its life-span during which the Transporter was returning to its base.       | StatHomeDrivingPortion [SimTalk]      | Heimfahrt          |
| Ready               | Shows the portion of its life-span during which the Transporter was ready.                       | StatTspReadyPortion [SimTalk]         | Bereit             |
| Paused              | Shows the portion of its life-span during which the Transporter was paused.                      | StatTspPausingPortion [SimTalk]       | Pausiert           |
| Failed              | Shows the portion of its life-span during which the Transporter was failed.                      | ShiftCalendarObject [SimTalk] - Frame | Gestört            |
| Unplanned           | Shows the portion of its life-span during which the Transporter was unplanned.                   | StatTspUnplannedPortio n [SimTalk]    | Ungeplant          |

**Ready-Times**

Shows details about the ready-times of the Transporters .

| Item English       | Description                                                                      | Read-only attribute           | Item German         |
|--------------------|----------------------------------------------------------------------------------|-------------------------------|---------------------|
| Portion            | Shows the portion of its life-span during which the Transporter was ready.       | StatTspReadyPortion [SimTalk] | Anteil              |
| Count              | Shows the number of ready-times during the total life-span.                      | StatTspReadyCount [SimTalk]   | Anzahl              |
| Sum                | Shows the sum of all ready-times during the total life-span of the Transporter . | StatTspReadyTime [SimTalk]    | Summe               |
| Mean Value         | Shows the mean duration of a ready- time.                                        | StatTspReadyMu [SimTalk]      | Mittelwert          |
| Standard Deviation | Shows the standard deviation from the mean value.                                | StatTspReadyDelta [SimTalk]   | Standardabweich ung |

**Failures [Transporter]**

Shows details about the failures of the Transporters .

| Item English       | Description                                                                        | Read-only attribute                   | Item German         |
|--------------------|------------------------------------------------------------------------------------|---------------------------------------|---------------------|
| Portion            | Shows the portion of its life-span during which the Transporter was failed.        | ShiftCalendarObject [SimTalk] - Frame | Anteil              |
| Count              | Shows the number of failures during the total life-span.                           | StatTspFailCount [SimTalk]            | Anzahl              |
| Sum                | Shows the sum of all failure times during the total life-span of the Transporter . | StatTspFailTime [SimTalk]             | Summe               |
| Mean Value         | Shows the mean duration of a failure.                                              | StatTspFailMu [SimTalk]               | Mittelwert          |
| Standard Deviation | Shows the standard deviation from the mean value.                                  | StatTspFailDelta [SimTalk]            | Standardab weichung |

**Pauses [Transporter]**

**Pauses [Transporter]**

Shows details about the pauses of the Transporters .

| Item English       | Description                                                                 | Read-only attribute             | Item German         |
|--------------------|-----------------------------------------------------------------------------|---------------------------------|---------------------|
| Portion            | Shows the portion of its life-span during which the Transporter was paused. | StatTspPausingPortion [SimTalk] | Anteil              |
| Count              | Shows the number of pauses during the total life-span of the Transporter .  | StatTspPausingCount [SimTalk]   | Anzahl              |
| Sum                | Shows the sum of all pause-times of the Transporter .                       | StatTspPausingTime [SimTalk]    | Summe               |
| Mean Value         | Shows the mean duration of a pause.                                         | StatTspPausingMu [SimTalk]      | Mittelwert          |
| Standard Deviation | Shows the standard deviation from the mean value.                           | StatTspPausingDelta [SimTalk]   | Standardabw eichung |

**Traveled Distance**

Shows details about the distance which the instance of the designated Transporter covered while driving on a Track .

<!-- image -->

| Item English      | Description                                                                                            | Read-only attribute                           | Item German              |
|-------------------|--------------------------------------------------------------------------------------------------------|-----------------------------------------------|--------------------------|
| Traveled Distance | Shows the distance which the instance of the designated Transporter covered while driving on a Track . | StatTraveledDistanc e [SimTalk] - Transporter | Zurückgelegte Wegstrecke |

**Battery [statistics]**

**Battery [statistics]**

Battery shows details about battery-related values of the Transporters .

<!-- image -->

| Item English         | Description                                                                                                                            | Read-only attribute             | Item German         |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------|---------------------------------|---------------------|
| Battery Capacity     | Shows the maximum charge capacity of the battery. The charge cannot exceed this value.                                                 | BatCapacity [SimTalk]           | Batteriekap azität  |
| Charging Current     | Shows the charge current of the battery.                                                                                               | BatChargeCurrent [SimTalk]      | Ladestrom           |
| Number of Charges    | Shows the number of times the battery was charged.                                                                                     | StatBatChargeCou nt [SimTalk]   | Anzahl der Ladungen |
| Portion              | Shows the portion of its life-span during which the battery of the Transporter was charging.                                           | StatBatChargePorti on [SimTalk] | Ladezeitant eil     |
| Driving Consumptio n | Shows the battery consumption while the Transporter is moving under battery power.                                                     | BatDriveCons [SimTalk]          | Fahrverbrau ch      |
| Basic Consumptio n   | Shows the basic energy consumption that comes off the battery. This applies as long as the Transporter is running under battery power. | BatBasicCons [SimTalk]          | Basisverbra uch     |

