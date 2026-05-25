### Modeling a Lockout Zone

#### Model a Lockout Zone

The LockoutZone combines a group of material flow objects. If one of these stations fails, all other stations that are part of the lockout zone stop processing their parts.

You have to define failure profiles for at least one of the stations assigned to the LockoutZone . As soon as one of the stations fails, the LockoutZone stops all processing operations of all assigned stations. You can select if it stops the processing operations immediately or when the required service arrives.

The stations only start processing parts again after all failures were removed. They then only use up the respective remaining processing time. You can assign any of the built-in Material Flow Objects or a station you modeled in a Frame to the LockoutZone .

You can insert the LockoutZone into your simulation model from the folder Resources in the Class Library or from the toolbar Resources in the Toolbox .

<!-- image -->

**You can:**

- Specify the Stations Which the LockoutZone Stops
- Create a Failure Profile for One of the Stations
- Stop the Associated Stations Immediately After a Failure
- Stop the Associated Stations When the Repair Man Arrives
- Use a Stop Processing Control
- Use a Resume Processing Control

Go to Stopped Material Flow Objects and Frames

Back to Modeling the Material Flow

#### Specify the Stations Which the LockoutZone Stops

In our sample model, which we originally created in 2D, the processing stations Station2 , Station3 , and Station4 are part of the lockout zone. If Station3 fails, the lockout zone stops the processing operations of Station2 and Station4 . The percentages of the stopped time of Station2 and Station4 have to match the percentage of the Failed time of Station3 . The total availability of the stations within the lockout zone matches the availability of Station3 .

<!-- image -->

To add a station as a resource to the lockout zone:

- Drag the icon of that object, in our case Station2 , over the icon of the LockoutZone and drop it there.
- Repeat this with Station3 and Station4 .

<!-- image -->

To clarify which objects are part of the lockout zone, you can draw a filled rectangle over the stations onto the background of the Frame in 2D:

- Click the Vector Graphics ribbon tab.
- Then, click the Filled Rectangle button.
- Drag a rectangle over the lockout zone and the stations that are part of it.
- Double-click the black rectangle and select a color. We selected light blue and added a gradient from bottom to top of our box.

<!-- image -->

<!-- image -->

<!-- image -->

- The result looks like this:

<!-- image -->

To create a similar effect in 3D, you might, for example, insert a Cuboid into the Frame and assign a Material to it. Proceed as follows:

- Click the Cuboid on the ribbon tab Edit . Type in a small value for the Dimension Z , the height of the Cuboid .

<!-- image -->

- Insert the Cuboid above Station2 and press the M key to show the manipulators.
- Click the bottom right corner of the Cuboid and drag it, so that it covers the LockoutZone and the Stations .
- As our Cuboid overlaps the captions of the objects, we move it, so that they become visible. Select Station1 , press the spacebar and change to the tab Captions in the dialog Edit 3D Properties . We selected -1.35 as the Y position for the three affected Stations .

<!-- image -->

<!-- image -->

<!-- image -->

- We finally have to adjust the position of the caption of the LockoutZone and assign a Material/color to the Cuboid .
- The result looks like this:

<!-- image -->

Back to Model a Lockout Zone

<!-- image -->

#### Create a Failure Profile for One of the Stations

To make the LockoutZone stop the processing operations of the stations it controls, we have to create a failure profile for one of the stations.

To make one of the stations, in our example Station3 , fail, proceed as follows:

- Click the tab Failures and click New .
- Enter an availability and a mean time to repair . We entered an availability of 85 percent and a mean time to repair of 15 minutes.
- Click OK to close the dialog.

Back to Model a Lockout Zone

<!-- image -->

#### Stop the Associated Stations Immediately After a Failure

To make the LockoutZone stop the processing operations of the stations it controls immediately, select the Stop mode &gt; Stop immediately .

<!-- image -->

The LockoutZone then immediately stops the processing operations of Station2 and Station4 as soon as Station3 fails. Plant Simulation only stops the stations that are part of the LockoutZone , but none of the other stations in the model!

Then, check the statistics values of the stations, which you assigned to the LockoutZone :

- Open the dialogs of Station2 , Station3 , and Station4 and change to the tab Statistics .
- You'll notice that the stopped percentages of Station2 and Station4 match the failed percentage of Station3 . This means that the overall availability of Station2 , Station3 , and Station4 matches the availability of the failed station, namely Station3 .

<!-- image -->

The statistics report show additional statistics data about the stopped and failed times.

To open it, select the stations in the Frame and press F6 .

<!-- image -->

Back to Model a Lockout Zone

#### Stop the Associated Stations When the Repair Man Arrives

To make the LockoutZone stop the processing operations of the stations it controls once the service technician, who repairs the failed stations, arrives, select the Stop mode &gt; Stop when Service arrives .

<!-- image -->

In our example the LockoutZone stops the processing operations of the assigned stations, namely Station2 , Station3 , and Station4 , when the repair service, which the failed Station3 requested, is assigned.

<!-- image -->

Proceed as follows to create our simple sample model:

- Insert the stations you want to simulate and drag these stations over the icon of the LockoutZone to assign them. In our case these are Station2 , Station3 , and Station4 .
- As a service technician is to repair the failed machines, add a Workplace to them and connect the Workplace with the WorkerPool with a footpath .

- As we want Station3 to fail, define a failure profile for it.
- To make a service technician repair Station3 once it fails, insert a Broker into the model and assign it on the sub-tab Failure . Then activate the failure importer . There is no need to change any other settings.

<!-- image -->

<!-- image -->

- Then, run the simulation by clicking on the Home ribbon tab. Once Station3 fails, the Worker walks from the WorkerPool to the failed station on the footpath . Once our service technician has reached the Workplace attached to the failed station Station2 , the LockoutZone stops the associated stations, namely Station2 and Station4 .

<!-- image -->

Back to Model a Lockout Zone

#### Use a Stop Processing Control

If you want to use your own logic when one of the stations assigned to the LockoutZone fails, you have to program a Stop Control .

In our example we write the following information into the table ReportStopping .

<!-- image -->

<!-- image -->

<!-- image -->

Within the control method the anonymous identifier @ designates the triggering station, while the anonymous identifier ? designates the LockoutZone .

<!-- image -->

The source code looks like this:

```simtalk
var row:integer := ReportStopping.ydim + 1
ReportStopping["First Failed Station",row] := @.name
ReportStopping["Start Stopping",row] := eventcontroller.simTime
```

Back to Model a Lockout Zone

#### Use a Resume Processing Control

If you want to use your own logic when all failures of all assigned stations were repaired and the stations can thus continue processing parts, you have to program a Resume Control .

In our example we write the following information into a table.

<!-- image -->

Within the control method the anonymous identifier @ designates the triggering station, while the anonymous identifier ? designates the LockoutZone .

<!-- image -->

The source code looks like this:

```simtalk
var row: integer := ReportStopping.ydim
ReportStopping["Last Failed Station",row] := @.name
ReportStopping["End Stopping",row] := eventcontroller.simTime
ReportStopping["Duration",row] := ReportStopping["End Stopping",row] ReportStopping["Start Stopping",row]
```

The result of our control looks like this:

<!-- image -->

Back to Model a Lockout Zone

##### Stopped Material Flow Objects and Frames

The LockoutZone stops the assigned material flow objects by setting their attribute Stopped to true .

<!-- image -->

The LockoutZone stops an assigned Frame by setting its attribute Stopped to true .

Back to Model a Lockout Zone

<!-- image -->

