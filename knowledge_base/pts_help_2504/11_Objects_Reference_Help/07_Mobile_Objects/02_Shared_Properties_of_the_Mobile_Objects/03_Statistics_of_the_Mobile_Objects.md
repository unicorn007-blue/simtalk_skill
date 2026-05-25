#### Statistics of the Mobile Objects

When interpreting simulation runs, you can call upon the statistical data that the MUs collect automatically. The statistical data may refer to a single MU only or to all MUs of the MU class collecting data.

The material flow objects usually process the mobile objects ( MUs ) according to an operating plan. During their live time they are located on production, transport and storage objects. If the objects, on which they are located, are not failed or paused , MUs are either being processed or are waiting . The Plant Simulation standard statistics for MUs provides data for making valid statements about the distribution of these different states.

##### Statistics Collection Period [MUs]

The statistics collection period is the interval between activating statistics collection or resetting it on one hand and the time you query the statistics on the other hand.

Plant Simulation collects statistical data by default. To deactivate statistics collection for the object, clear the check boxes Resource Statistics or Product Statistics on their respective tabs or set the attributes ResStatOn or ProdStatOn to false. Deactivating statistics deletes all statistical data for the object. The statistical data for a MU class is the mean of the statistical data of all statistics collecting MU instances that either existed at the time you started a statistics query or existed during the statistics collection period of the class.

**Note**

When you reset a simulation model, Plant Simulation deletes all statistical data of all objects. During a simulation run you can also accomplish this using the method initStat . This way, you can, for example, restart the collection of statistical information after a warm-up period of a machine.

To open the Statistics Report , click Show Statistics Report on the Home ribbon tab, or use the method statistics .

**Note**

Plant Simulation does not continuously update statistical data displayed in an open window during a simulation run! Select View &gt; Refresh or press F5 .

The following example illustrates the expressions statistics collection period and statistics collection :

<!-- image -->

**Query One**

The statistics collection period starts when you activate statistic collection, by selecting the check boxes Product Statistics or Resource Statistics or by assigning the value true to the attributes ProdStatOn or ResStatOn , and ends when you query statistical data. The progression of the stations on which the MU stays, the start of the statistics query and the time of statistics query 1 add up to a portion of 100 percent for the time the MU remained on production objects for statistics query 1. The times the MU was located on transport objects are, for this query, all located outside of the statistics collection period.

Query Two

The sequence of the stations on which the MUs stayed, the start of the statistics query and the time of statistics query 2 add up to a portion of less than 100 percent for the time which the mobile object stayed on production objects for statistics query 2 because, for a time, the MU was located on transport objects during the statistics collection time.

##### Product Statistics of the MUs

###### Product Statistics of the MUs [general description]

The complete statistics collection period of products consists of the non-overlapping times for production, transport, and storage.

<!-- image -->

The times themselves are the times during which a MU is located on an object of the corresponding resource type. Set-up times for the MU may occur for production, transport and storage times.

Select the resource type of the object receiving the MU on the tab Statistics from the drop-down list Resource Type :

- Production : Default setting for the objects Station , ParallelStation , AssemblyStation , DismantleStation , Portioner , and DePortioner .
- Transport : Default setting for the objects PlaceBuffer , Buffer , Sorter , Track , TwoLaneTrack , Conveyor , AngularConverter , Turntable , Transporter , and Container .
- Storage : Default setting for the object Store .

Depending on the state of the resource these times are subdivided into the Waiting , Setting-up , Working , Failed , Paused , and Stopped times.

To view Product Statistics of the MUs [statistics report] in the Statistics Report , click the object in the Frame , and press F6 ( Show Statistics Report ), or click Show Statistics Report on the Home ribbon tab.

Also compare Viewing the Statistics Report in the Step-by-Step Help .

SimTalk StatFailTimePortion [SimTalk] StatPauseTimePortion [SimTalk] StatProductionTimePortion [SimTalk] StatSetUpTimePortion [SimTalk] StatStorageTimePortion [SimTalk] StatTransportTimePortion [SimTalk] StatWaitTimePortion [SimTalk] StatWorkTimePortion [SimTalk] See also Methods for Accessing Statistics of the MUs

**Working [MUs]**

###### Working [MUs]

A MU is working if it is located on a point-oriented material flow object that is not paused , not failed and is being processed by it.

The MU is working if it is located on a length-oriented material flow object and is being transported by it.

MUs , which are loaded or unloaded from a material flow object by a PickAndPlace robot , are always counted as working .

**Note**

The read-only attribute ProdInProcess returns the state processing of the MU ( boolean ).

See also

Working [state, material flow objects]

Paused [state, material flow objects]

Failed [state - material flow objects]

###### Setting-up [MUs]

A MU is setting-up if it is located on a material flow object which is setting-up for processing this MU class.

See also

Setting-Up [state, material flow objects]

**Waiting [MUs]**

###### Waiting [MUs]

A MU is waiting if it is located on a point-oriented object that is not stopped , not paused , not failed , and is not working .

The MU is waiting if it is waiting to be transferred to a length-oriented object.

MUs , which are located in a Blocking List, are always counted as waiting , no matter which state the material flow object is in.

**Note**

The read-only attribute ProdWaiting returns the waiting state of the MU ( boolean ).

See also

Waiting [state, material flow objects]

Stopped [state, material flow objects]

Paused [state, material flow objects]

Failed [state - material flow objects]

Working [state, material flow objects]

###### Stopped [MUs] - state

A MU is stopped if it is located on a material flow object that is stopped by a LockoutZone , is not paused , and is not failed .

See also

Stopped [state, material flow objects]

Paused [state, material flow objects]

Failed [state - material flow objects]

###### Failed [MUs] - state

Failed [MUs] - state

A MU is failed if it is located on a resource that is failed and is not paused .

Note

The read-only attribute ProdOnFailed returns the state failed of the MU ( boolean ).

See also

Failed [state - material flow objects]

Paused [state, material flow objects]

###### Paused [MUs]

A MU is paused if it is located on a paused or an unplanned resource.

**Note**

Do not confuse the paused state of the MU with the paused state of the Drive Control of the Transporter . The read-only attribute ProdOnPaused returns the state paused of the MU ( boolean ).

See also

Paused [state, material flow objects]

Unplanned [state, material flow objects]

##### Additional Statistical Data of the MUs

The statistical data listed below only apply to MU classes, as statistics collection includes all instances of the MU .

| Item English   | Description                                                                                                                                                                                                                                             | Read-only attribute             | Item German                     |
|----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------|---------------------------------|
| Number         | Shows how many MU instances of this class existed during the statistics collection period. Plant Simulation only counts those MUs whose product statistics was active during the simulation run. The MUs may be located in different Frame hierarchies. | StatCount [SimTalk]             | Anzahl                          |
| Deleted        | Shows how many MU instances of this class were removed from the plant during the statistics collection period. Plant Simulation only counts those MUs whose product statistics was active during the simulation run.                                    | StatDeleted [SimTalk] - MUs     | Vernichtet                      |
| Mean Life Time | Shows the average life-span of the MUs which were created and removed from the plant during the statistics collection period. Plant Simulation only counts those MUs whose product statistics was active during the simulation run.                     | StatAvgLifeSpan [SimTalk] - MUs | mittlZeit (Mittlere Lebenszeit) |

##### Resource Statistics of the Container

As the Container can load and transport other MUs , it provides Resource Statistics .

**Note**

Resources statistics of the MUs only provides the Material Flow Properties .

To view Resource Statistics of Moving Resources in the Statistics Report , click the object in the Frame , and press F6 ( Show Statistics Report ), or click Show Statistics Report on the Home ribbon tab.

SimTalk

StatMaxNumMU [SimTalk] - MUs

StatMaxNumMU [SimTalk] - material flow objects

StatMinNumMU [SimTalk] - material flow objects

StatNumIn [SimTalk] - material flow objects

StatNumOut [SimTalk] - material flow objects

StatRelativeOccupation [SimTalk] - material flow objects

See also

Viewing the Statistics Report

Methods for Accessing Statistics of the MUs

Driving Statistics of the Transporter

Driving Statistics of the Transporter [in dialog]

In addition to product statistics of the Part and the Container , the Transporter collects driving statistics data about the states Order occupied , Order empty , Home driving , Ready , Failed , Paused , Unplanned , the battery consumption and the number of jobs performed.

To view Driving Statistics of the Transporter in the Statistics Report , click the object in the Frame , and press F6 ( Show Statistics Report ), or click Show Statistics Report on the Home ribbon tab.

See also

Methods for Accessing Statistics of the MUs

**Viewing the Statistics Report**

###### Order Occupied

A Transporter is in the state Order Occupied if it has an order and is transporting parts.

SimTalk

StatOrderOccPortion [SimTalk]

**Order Empty**

###### Order Empty

A Transporter is in the state Order Empty if it has an order and is not transporting parts, i.e., it is empty.

SimTalk

StatOrderEmptyPortion [SimTalk]

See also

Empty [state, material flow objects]

###### Home Driving

A Transporter is in the state Home Driving if it is returning to its base.

SimTalk

StatHomeDrivingPortion [SimTalk]

###### Ready

Ready

A Transporter is in the state Ready if it is not in any of the other states, for example Order Occupied , Order Empty , Home Driving , Failed , Paused , or Unplanned .

SimTalk

StatTspReadyPortion [SimTalk]

###### Failed [driving statistics]

A Transporter is in the state Failed if it is failed for any reason and cannot do its job.

SimTalk

Failed [SimTalk] - Transporter

**Paused [Transporter]**

###### Paused [Transporter]

A Transporter is in the state Paused if it is paused for any reason.

SimTalk

StatTspPausingPortion [SimTalk]

###### Unplanned [Transporter]

A Transporter is Unplanned if the current time is outside of any shift of the ShiftCalendar to which the Transporter is assigned.

<!-- image -->

