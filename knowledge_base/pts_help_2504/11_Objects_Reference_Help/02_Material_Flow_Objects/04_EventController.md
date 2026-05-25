### EventController

#### EventController [object]

Use the EventController for coordinating and synchronizing the events taking place during a simulation run.

**Icon**

<!-- image -->

**Description**

You can start , stop , and reset the simulation with the EventController . Plant Simulation is a discrete event-oriented simulation system that shows the state changes of the model components at certain points in time, not continually over time. When a part enters a processing station, for example a Station , Plant Simulation computes the time it takes to cover it and enters that time and that event into the List of scheduled events of the EventController . Imagine a timeline where you insert markers at certain points in time.

<!-- image -->

The EventController moves along the timeline like the play-back head of a video player, and interprets messages relating to the events the objects execute. All the while messages about the events arrive which the objects execute. After a certain simulation time, for example the processing time , has elapsed, the EventController arrives at the marker which has been set when the part entered the station. This marker denotes that the processing time has elapsed and that an Out event is pending. The EventController notifies the Station that has to process the Out event and moves the part on to the succeeding object in the flow of materials. Plant Simulation repeats this process cyclically for all MUs located in the simulation model.

**Note**

If you manually delete the EventController , Plant Simulation resets the model beforehand.

<!-- image -->

To add the EventController to your simulation model, click MaterialFlow &gt; EventController on the Home ribbon tab.

Starting and Stopping the Simulation

You can start the simulation:

- By clicking Start/Stop Simulation in the dialog of the EventController .
- By clicking Start/Stop Simulation on the Home Ribbon Tab of the Frame . If you start the simulation by clicking without having inserted an EventController , Plant Simulation asks if you would like to insert one.
- By clicking Start/Stop Simulation on the mini toolbar

<!-- image -->

<!-- image -->

You can stop the simulation:

- By clicking Single Step Simulation in the dialog of the EventController .
- By clicking Start/Stop Simulation on the Home ribbon tab a second time.
- By clicking Start/Stop Simulation on the mini toolbar

<!-- image -->

<!-- image -->

The simulation stops after the current event has been completely processed.

At the end of the simulation run Plant Simulation executes all methods that are named endSim . The end of the simulation run is reached, when the event list is empty or when the End time, which you entered on the tab Settings has been reached.

Instead of clicking the buttons in the dialog of the EventController , you can also click the corresponding buttons on the Home Ribbon Tab .

<!-- image -->

Or you can click the buttons on the Quick Access Toolbar

<!-- image -->

.

.

.

To show a tooltip with information about the EventController , hover with the mouse over it.

<!-- image -->

To change the length of the graphic and the anchor points of the EventController , click Show

**Manipulators**

on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

In addition to running the simulation with the EventController , you can also run the simulation step-bystep with the EventDebugger .

<!-- image -->

**See also**

Control the Simulation with the EventController

Dialog Box of the EventController

Dialog Box of the Event Debugger

<!-- image -->

#### Dialog Box of the EventController

Dialog Box of the EventController

Double-click the icon of the EventController to open its dialog box.

Edit Simulation Properties

There you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

<!-- image -->

<!-- image -->

Instead of clicking the buttons in the dialog of the EventController , you can also click the respective buttons on the Home Ribbon Tab .

<!-- image -->

When you are running the simulation with the EventController buttons on the Home ribbon tab, Plant Simulation shows the time as it progresses in the status bar . When the simulation is finished, the status bar shows the end time .

Edit Animation Properties

In 3D you can change the dimensions of the graphic of the EventController by clicking Show Manipulators

on the Edit ribbon tab or by clicking M on the keyboard.

<!-- image -->

**Time [EventController]**

##### Time [EventController]

Shows the current simulation time of the simulation run in the box next to Time .

Click Time to change the display of the time between the

- Relative time : Plant Simulation resets the relative time to zero, when it starts the simulation run. This is the default. Here the EventController shows the simulation time next to the button Time .
- Current time plus simulation time : Plant Simulation adds the simulation time to the time and date at which it started the simulation run. Here the EventController shows the current time plus the simulation time next to the button Time .

Let us assume that today is the second of January 2023, six o'clock in the morning and that the simulation is to run for two days.

<!-- image -->

- For the setting relative time the time display shows 2:00:00:0000 , i.e., two days.
- For the setting current time plus simulation time the time display shows Mi, 2023/01/04 06:00:00.0000 , i.e., Wednesday, January 04, 2023, 6 o'clock in the morning.

<!-- image -->

<!-- image -->

When you run the simulation, Plant Simulation shows the time as it progresses in the status bar at the bottom of the Plant Simulation program window . When the simulation is finished, the status bar shows the end time .

<!-- image -->

Tab Controls

Tab Controls

The tab Controls provides settings for controlling the simulation run.

<!-- image -->

When you run the simulation, Plant Simulation shows the time as it progresses in the status bar at the bottom of the Plant Simulation program window . When the simulation is finished, the status bar shows the end time .

###### Reset Simulation [EventController]

To reset your simulation model, click the button. Plant Simulation then calls all Methods named reset in your simulation model.

<!-- image -->

Once all reset methods have been executed, Plant Simulation :

- Deletes all unprocessed events
- Resets the simulation time to 0
- Resets statistics
- Clears all failures of all objects in the simulation model
- Sets all objects to the state planned
- Reactivates inheritance of the settings Entrance Locked and Exit Locked for new models if you leave Tools &gt; Inherit 'Entrance/Exit Locked On Reset active

The Request Control , the Receive Control , and the Release Control of the Importer are not called when you reset the simulation.

When you click Reset Simulation while the simulation is running, Plant Simulation finishes processing the current event and then resets the model.

Resetting the simulation model also deletes MUs on the Clipboard , as MUs on the Clipboard would lead to a different numbering of the MUs for a new simulation run.

**Note**

If the simulation model still contains MUs after resetting the model, meaning that Plant Simulation does not start counting MUs with 1, for example MUs.Part:1 , for a new simulation run, check if the model contains additional Frames with inserted EventControllers . Reset the EventControllers there as well.

Plant Simulation deletes suspensions of methods , which are located in the same Frame as the EventController or in a sub-Frame of this Frame . It also deletes suspensions of methods , whose caller (the anonymous identifier ? ) is located in the same Frame as the EventController or in a sub-Frame of this Frame .

The global method deleteSuspendedMethods deletes all suspensions of all methods.

<!-- image -->

Instead, you can also click on the Home Ribbon Tab .

Or you can right-click the EventController in the Frame and select Reset Simulation on the context menu.

<!-- image -->

SimTalk reset [SimTalk] - EventController reset [SimTalk] - predefined name See also Inherit 'Entrance/Exit Locked' On Reset initStat [SimTalk] - material flow objects IsInitialized [SimTalk] ResetCtrl [SimTalk] Reset Simulation [EventDebugger]

###### Start/Stop Simulation [EventController]

Start/Stop Simulation [EventController]

To start the simulation run, click the button.

<!-- image -->

To stop the simulation after the active simulation event has been processed, click the button again. Plant Simulation calls init methods when you click Start/Stop Simulation if they have not been called yet.

Instead, you can also click on the Home Ribbon Tab or double-click the icon of the EventController while holding down Shift .

Or you can right-click the EventController in the Frame and select Start/Stop Simulation on the context menu.

<!-- image -->

SimTalk

start [SimTalk] - EventController

stop [SimTalk] - EventController

StartStopCtrl [SimTalk]

init [SimTalk] - predefined name

InitCtrl [SimTalk] - EventController

See also

Init Control [EventController]

Init Control [general description]

Init Control [Transporter]

IsInitialized [SimTalk]

###### Start Full Speed Simulation [EventController]

To start the simulation run with the animation of MUs and States and with full speed, click the button.

<!-- image -->

Start Full Speed Simulation updates a number of values, for example of objects of type Variable or Display , etc.

When you click Start Full Speed Simulation , Plant Simulation ignores the Real Time scaling factor .

<!-- image -->

###### Start Fast Forward Simulation [EventController]

To start the simulation run without the animation of MUs and States and with maximum speed, click the button. This makes the simulation run as fast as possible.

<!-- image -->

Start Fast Forward Simulation prevents updating a number of values, for example of objects of type Variable or Display , etc.

When you click Start Fast Forward Simulation Plant Simulation ignores the real time scaling factor .

<!-- image -->

<!-- image -->

Instead, you can also click on the Home Ribbon Tab .

<!-- image -->

<!-- image -->

<!-- image -->

Or you can right-click the EventController in the Frame and click Start Fast Forward Simulation on the context menu.

<!-- image -->

**See also**

<!-- image -->

###### Single Step Simulation [EventController]

To process the next simulation event in line, to stop the simulation afterward, and to thus proceed through your model step-by-step, click the button.

<!-- image -->

When you hold down Shift while clicking Step , Plant Simulation opens the Method Debugger for all methods and formulas, which are executed while the event is being processed. This means that the debugger opens for all executed controls, formulas and for suspended methods , which were woken up.

<!-- image -->

If init methods have not been called yet, the init methods are started instead of processing an event.

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

Instead, you can also click on the Home Ribbon Tab .

SimTalk

**StartStopCtrl [SimTalk]**

List of Scheduled Events

List of Events

To open the Event Debugger that shows the event list , click the button.

<!-- image -->

The Event List in the Event Debugger contains the events, which the objects in your simulation model scheduled and which the EventController has to process. It is sorted ascending by time. It lists the Type of event , the scheduled Time , the Receiver and the Sender of the event, the Insertion Time , and Parameters .

<!-- image -->

<!-- image -->

- The column Breakpoint shows an S , for a breakpoint which you inserted by double-clicking a cell in the row.

Double-click a cell in the row where you would like to insert a single breakpoint. Then the Event Debugger stops the simulation immediately before the EventController processes that event. Doubleclick again to remove the breakpoint.

- The column Type shows the type of the event.
- The column Time shows the point in time at which the event is going to be executed.

**Note**

The time does not designate the time of day here but the time interval from the Start Time of the EventController .

- The column Receiver shows the object that receives the simulation event.
- The column Sender shows the object that sends the simulation event.
- The column Insertion Time shows the point in time at which the event was entered into the event list. This column is hidden by default. Drag the column separator to show it.
- The column Parameters shows additional information for certain event types, for example the sensor ID (SensorStart) , the name of the failure profile (DisruptionBegin) , or the parameters passed to a Method (MethCall) .

Plant Simulation provides these types of simulation events .

**SimTalk**

getEventList [SimTalk]

**See also**

GetDisruptionBeginTime [SimTalk]

GetDisruptionEndTime [SimTalk]

**Event List**

Shows the event types, which the objects in your simulation model schedule during the simulation, and which the EventController then processes.

Plant Simulation provides these types of simulation events:

| Event English   | Event German     | Action taking place/state of the object                                                                                                                                                                      |
|-----------------|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| *               | *                | Designates any type of event.                                                                                                                                                                                |
| Animation       | Animation        | A MU is located on a Track , Conveyor , or on a Buffer .                                                                                                                                                     |
| Battery         | Batterie         | The battery of a Transporter is full, empty or on reserve.                                                                                                                                                   |
| BlockageEnd     | BlockierEnde     | The state of a MU changes to unblocked.                                                                                                                                                                      |
| Bump            | Anstoss          | The Transporter collides with another MU . You can then take appropriate actions in the Collision control .                                                                                                  |
| CheckMUDistance | BEAbstandPrüfen  | The MUdistance at the start of the Conveyor is reached; if Enforce MUdistance is activated, the MU has reached the distance to the part moving in front.                                                     |
| CheckMUPosition | BEPositionPrüfen | Checks if the MU has to be stopped after processing the exit control on length-oriented objects. This is the case if neither the position of the front in the direction of motion nor the direction changed. |
| CreateMU        | ErzeugeBE        | The Source attempts to create MUs .                                                                                                                                                                          |
| DeliverParts    | TeileAbliefern   | The Worker picked up parts at a station and carries them to the destination object.                                                                                                                          |
| DisruptionBegin | StörBeginn       | The failure of the object starts.                                                                                                                                                                            |
| DisruptionEnd   | StörEnde         | The failure of the object ends.                                                                                                                                                                              |
| Distance        | Abstand          | The Distance Control of the Transporter is called                                                                                                                                                            |
| EndOfTime       | ZeitBeendet      | The PickAndPlace-robot is done loading/unloading. The Worker is done loading/unloading.                                                                                                                      |

| Event English   | Event German   | Action taking place/state of the object                                                                                                                                                                                                                      |
|-----------------|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                 |                | The Mixer has finished mixing products Converter / AngularConverter is done changing the conveying direction of the MU . All pose runs of an object arrived at their destination in 3D .                                                                     |
| EndOfTurn       | EndeDrehen     | The PickAndPlace-robot , Turnplate , Turntable or Transporter rotating on the spot reaches the end position of the rotation.                                                                                                                                 |
| EntranceEnd     | EintrittEnde   | The MU completely entered a length-oriented object. The specified amount of an educt of the Mixer has been reached. The MU of the Portioner has been completely filled. The Worker has reached its target station when he is walking freely within the area. |
| FinalSpeed      | EndGeschw      | The point in time at which the Transporter or the Conveyor reach their final speed after accelerating or decelerating.                                                                                                                                       |
| GenDuration     | GenDauer       | The Duration Control of the Generator is activated.                                                                                                                                                                                                          |
| GenInterval     | GenAbstand     | The Interval Control of the Generator is activated.                                                                                                                                                                                                          |
| Init            | Init           | Initializes the simulation model using the method init before executing the next scheduled event.                                                                                                                                                            |
| InitStat        | InitStat       | Resets statistics and starts collecting statistics anew.                                                                                                                                                                                                     |
| MethCall        | MethAufr       | Calls a method that was scheduled with the SimTalk method executeIn of the object Method .                                                                                                                                                                   |
| MethWakeup      | MethAufwecken  | Continues executing the call chain after the time you entered in a wait statement has elapsed.                                                                                                                                                               |
| Out             | Aus            | A MU exits the object.                                                                                                                                                                                                                                       |
| OutEnd          | AusEnde        | A MU completely exits a length-oriented object ( Conveyor , Turntable , Track , TwoLaneTrack ).                                                                                                                                                              |
| Pause           | Pause          | Start of the pause of an object. This event will only be created when you paused the object with the method startPauseIn . Start of the pause of the ShiftCalendar and the objects it controls.                                                              |
| PauseEnd        | PauseEnde      | End of the pause of an object. This event will only be created when you paused the object with the method startPause .                                                                                                                                       |

| Event English       | Event German          | Action taking place/state of the object                                                                                                                                                                                                           |
|---------------------|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                     |                       | End of the pause of the ShiftCalendar and the objects it controls.                                                                                                                                                                                |
| PositionReached     | PositionErreicht      | The MU has reached the center of rotation of Turnplate / Turntable The The AngularConverter / Converter has reached the point at which the conveying direction changesThe The Transporter has reached the target.                                 |
| PoweringUpDown      | HochRunterfahren      | The material flow object powers up or down to reflect a change in its energy status.                                                                                                                                                              |
| Reference           | Referenz              | The booking point of the MU exits the object.                                                                                                                                                                                                     |
| RouteObjectReache d | RoutenObjektErreic ht | The Transporter driving freely within the area has reached a Track and is afterward going to be booked on the Track .                                                                                                                             |
| SensorBookPos       | SensorBuchPos         | The booking point of the MU activates a sensor.                                                                                                                                                                                                   |
| SensorEnd           | SensorEnde            | The rear of the MU activates a sensor.                                                                                                                                                                                                            |
| SensorStart         | SensorBeginn          | The front of the MU activates a sensor.                                                                                                                                                                                                           |
| SetupEnd            | RuestenEnde           | The set-up time of a MU has expired                                                                                                                                                                                                               |
| Shift               | Schicht               | Schedules the start or the end of the next shift.                                                                                                                                                                                                 |
| ShiftCalendarStart  | SchichtkalenderSta rt | Sets the state of the objects controlled by the ShiftCalendar according to the state it controls.                                                                                                                                                 |
| StartActions        | StarteAktionen        | Determines if the Entrance Control of the object is activated before starting the actions that are performed when a MU enters the object. The FluidSource starts producing the fluid. New material begins to flow into the Mixer after it ran dry |
| StartTransporter    | FahrzeugStarten       | The Transporter starts driving again after the Start delay duration has passed.                                                                                                                                                                   |
| TankEmpty           | TankLeer              | The Tank is empty. The MU of the Portioner has been emptied. The mixing container of the Mixer is empty.                                                                                                                                          |
| TankFull            | TankVoll              | The Tank is full.                                                                                                                                                                                                                                 |

| Event English   | Event German   | Action taking place/state of the object                                                                                          |
|-----------------|----------------|----------------------------------------------------------------------------------------------------------------------------------|
|                 |                | The mixing container of the Mixer is full.                                                                                       |
| TimeSequence    | Zeitleiste     | The TimeSequence records data.                                                                                                   |
| TriggerAction   | TriggerAktion  | The values of the Trigger change.                                                                                                |
| TriggerStart    | TriggerStart   | The active time of the Trigger starts.                                                                                           |
| TurnAnimation   | DrehAnimation  | Animates the rotation of PickAndPlace-robot / Turnplate / Turntable .                                                            |
| UpdateDisplay   | UpdateDisplay  | Updates the values of the object Display .                                                                                       |
| ZeroSpeed       | NullGeschw     | Point in time when the Transporter or the Conveyor reach the speed 0 after decelerating and then change the direction of motion. |

SimTalk

getEventList [SimTalk]

See also

GetDisruptionBeginTime [SimTalk]

GetDisruptionEndTime [SimTalk]

Context Menu of the List of Scheduled Events

Context Menu of the List of Scheduled Events

Provides commands pertaining to the list of scheduled events.

The context menu of the Event Debugger provides the commands listed in the table of contents to the left.

<!-- image -->

Show Receiver

Open Receiver

Show Sender

Open Sender Stop at Event [context menu]

Create Breakpoint

from Event

Run to Time [context

menu]

Time [context menu]

**Show Receiver**

To select the icon of the object that receives the event in the Frame window, select Show Receiver .

<!-- image -->

Hold down Shift and select this to zoom so close as if you selected the object or the graphic and selected the command Zoom to Objects [context menu] .

**Open Receiver**

To open the dialog box of the object that receives the event, select Open Receiver .

<!-- image -->

**Show Sender**

To select the icon of the object that sends the event in the Frame window, select Show Sender .

<!-- image -->

Hold down Shift and select this to zoom so close as if you selected the object or the graphic and selected the command Zoom to Objects [context menu] .

**Open Sender**

To open the object that sends the event in the Frame window, select Open Sender .

<!-- image -->

**Stop at Event [context menu]**

**Stop at Event [context menu]**

To add a breakpoint for the selected event to the list of scheduled events, select Stop at Event .

<!-- image -->

**Create Breakpoint from Event**

To create a breakpoint from the selected event, select Create Breakpoint from Event . Type in or select missing settings in the dialog Breakpoint .

<!-- image -->

**Run to Time [context menu]**

**Run to Time [context menu]**

To enter the time of the selected event, rounded down to a tenth of a millisecond into the text box Run to Time of the EventDebugger , select Run to Time .

<!-- image -->

**See also**

Run to Time [text box]

**Time [context menu]**

Shows the point in time at which the selected event is going to be executed.

<!-- image -->

**Slower/Faster**

###### Slower/Faster

To increase the speed of the simulation, drag the slider to the right or press the right arrow key.

To decrease the speed of the simulation, drag it to the left or press the left arrow key.

<!-- image -->

Decreasing the speed enables you to better follow the movements of MUs , as Plant Simulation shows their icons for a longer time on the same station.

This has the same effect as dragging the Slower/Faster slider on the Home ribbon tab.

<!-- image -->

<!-- image -->

You can type in or select a scaling factor for the different settings. The scaling factor sets the time that elapses between two events in real-time. The duration of an event in real-time is the simulation time divided by the scaling factor you entered. The resulting duration is an integer value.

- When you click Start/Stop Simulation , Plant Simulation uses real-time simulation with a scaling factor of 3 by default.
- When you click Start Full Speed Simulation , Plant Simulation ignores the scaling factor. This starts the simulation run with the animation of MUs and States and with full speed.
- When you click Start Fast Forward Simulation , Plant Simulation ignores the scaling factor. This starts the simulation run without the animation of MUs and States and with maximum speed.

<!-- image -->

<!-- image -->

<!-- image -->

##### Tab Settings

<!-- image -->

Tab Settings

Tab Settings

The tab Settings provides various settings for the simulation run.

<!-- image -->

###### Start Date [EventController]

Type in the Date and the Time on which the absolute time during the simulation is based or accept the pre-defined date.

SimTalk

StartDate [SimTalk] - EventController

**End Time [EventController]**

###### End Time [EventController]

Type in the End Time at which the simulation will be finished. Type in a relative time, i.e., the period of time during which the simulation runs.

<!-- image -->

Plant Simulation compares this period with the simulation time and stops the simulation run, when both are identical.

Let us assume that today is July 04, 12 o'clock noon and that the simulation is to run for two days.

To make the simulation run for two days, type in 2:00:00:00 . If you do not want to write this out in full, you can also just type 2::: and click Apply to make the program translate this to the full format 2:00:00:00 .

SimTalk

EndTime [SimTalk] - EventController

See also

Format of Time and Date/Format Conversion

End Simulation-time for video recordings

###### Statistics [EventController]

Type in the point in time at which the EventController starts collecting statistics data.

Plant Simulation resets statistics and deletes all statistics values it collected up to that time and starts collecting new statistical data for all material flow objects from this time on.

This way you can discard data collected during the warm-up phase, which might distort the simulation results.

SimTalk

StartStat [SimTalk]

**Skip Long Event Intervals**

###### Skip Long Event Intervals

To skip long phases during which no relevant event takes place during real-time simulation, select this check box.

Events of type Animation and UpdateDisplay are considered to be not relevant.

<!-- image -->

The simulation fast forwards the gap between events if no relevant event would take place for at least 10 seconds, while the animation remains active. These 10 seconds are 10 seconds in real-time which you would have to wait for. For a real-time scaling factor of 3 this would amount to 30 seconds of simulation time. Fast forwarding starts about half a second after the last event and ends about half a second before the next event.

The open windows of the simulation show the Fast Forward Simulation icon during this time. The icon looks like this:

<!-- image -->

This setting is especially helpful for simulation models in which you experiment with different Shifts .

SimTalk

**SkipLongEventIntervals [SimTalk]**

See also

Event List

###### Show Summary Report [EventController]

To show a summary report of the parts which the Drain deleted from the plant, select this check box.

At the end of the simulation run the report checks all Drain objects within the entire simulation model which removed parts from the plant and shows the pertinent values.

<!-- image -->

| Item English         | Description                                                                                                                              | Read-Only Attribute                           | Item German             |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|-------------------------|
| Object               | Shows the names of all Drain objects within the entire simulation model that removed parts.                                              | -                                             | Objekt                  |
| Name                 | Shows the names of the part types which the Drain in this row removed from the plant.                                                    | -                                             | Name                    |
| Mean Life Time       | Shows the mean life time (throughput time) of all parts of this part type which the Drain in this row removed from the plant.            | StatAvgLifeSpan [SimTalk] - Drain             | Mittlere Durchlauf zeit |
| Total Through put    | Shows the total throughput of all parts of this part type which the Drain in this row removed from the plant.                            | StatDeleted [SimTalk] - Drain                 | Durchsatz               |
| Through put per Hour | Shows the number of parts that the Drain removed from the plant in an hour over all observed times during which the Drain was available. | StatThroughput PerHour [SimTalk] - FluidDrain | Durchsatz pro Stunde    |
| Producti on          | Shows the time portion during which the parts spent on a resource object of type production .                                            | -                                             | Produktion              |
| Transpor t           | the time portion during which the parts spent on a resource object of type transport .                                                   | -                                             | Transport               |

| Item English   | Description                                                                                                                                                                                | Read-Only Attribute                       | Item German    |
|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------|----------------|
| Storage        | Shows the time portion during which the parts spent on a resource object of type storage .                                                                                                 | -                                         | Lagerung       |
| Value Added    | Shows the time portion during which the parts were processed and were located on resource objects of type production . This is the time during which the value of the parts was increased. | StatProdWorkin gPortion [SimTalk] - Drain | Wertschö pfung |
| Portion        | Shows the accumulated values of the columns production (green), transport (orange), and storage (red) as bar segments.                                                                     | -                                         | Anteil         |

**Note**

The summary report is deactivated by default. The Statistics Report also shows the described data.

You can also show the Drain Statistics Table of a Drain in an HtmlReport , compare Display a Drain .

SimTalk

SummaryReport [SimTalk]

See also

Show Summary Report [menu command]

Dialog Box of the Event Debugger

Dialog Box of the Event Debugger

The Event Debugger lets you accurately control the execution of simulation events when running your simulation with the buttons is not accurate enough. You can, for example, enter a condition when the Event Debugger is to Start/Stop the Simulation . You can then follow the execution of the events in the Event Debugger step-by-step.

The Event Debugger is part of the EventController . To open the list of scheduled events, click List

<!-- image -->

<!-- image -->

the tab Controls in the EventController . You can also hold down Shift and double-click the icon the EventController in the Frame .

<!-- image -->

<!-- image -->

- The column Breakpoint shows an S , for a breakpoint you inserted, by double-clicking a cell in the row.

Double-click a cell in the row where you would like to insert a single breakpoint. Then the Event Debugger stops the simulation immediately before the EventController processes that event. Doubleclick again to remove the breakpoint.

- The column Type shows the type of event.
- The column Time shows the point in time the event is going to be executed.

**Note**

The time does not designate the time of day here but the time interval from the start time of the EventController .

- The column Receiver shows the receiving object.
- The column Sender shows the sending object.
- The column Insertion Time shows the point in time at which the event was inserted into the EventController . This column is hidden by default. Drag the column separator to show the column.
- The column Parameters shows additional information for certain event types, for example the sensor ID (SensorStart) , the name of the failure profile ( DisruptionBegin ) or the parameters passed to a Method ( MethCall ).

**See also**

**Work with the Event Debugger**

**List of Events**

**Breakpoints Active**

###### Breakpoints Active

To activate breakpoints, select this check box. Plant Simulation then stops executing the event at a breakpoint, which you inserted. You can then examine the status of the simulation run, check the contents of variables, etc.

<!-- image -->

###### Breakpoints

**Breakpoints [described]**

To open the dialog Breakpoints , click this button.

<!-- image -->

<!-- image -->

<!-- image -->

- To create a new breakpoint, click . In the dialog Breakpoint you can then define the breakpoint that stops the simulation when a certain event takes place.
- To edit an existing breakpoint, select it in the list of breakpoints and click
- To delete the selected breakpoint from the list, click

<!-- image -->

<!-- image -->

.

.

**See also**

**The Dialog Box Breakpoint**

Work with the Event Debugger

The Dialog Breakpoint

The Dialog Box Breakpoint

The dialog box Breakpoint provides settings for defining breakpoints.

<!-- image -->

**Receiver**

**Receiver**

Click the ellipsis button to open the dialog Select Object and select the object that receives the breakpoint in the list.

<!-- image -->

Or type in the absolute Path to the receiver of the breakpoint, for example to the object onto which the MU is moved.

If you do not type in a Receiver , this breakpoint applies to events with any receiver.

**Note**

F2 opens the dialog of the object, whose name you typed into the text box.

See also

Select Object

EventDebugger, Example 1

**Sender**

Click the ellipsis button to open the dialog and select the object that sends the breakpoint in the list in the dialog Select Object .

<!-- image -->

Or type in the absolute path to the sender of the breakpoint, for example to the object which moves the MU .

If you do not type in a Sender , this breakpoint applies to events with any sender.

Note

F2 opens the dialog of the object, whose name you typed into the text box.

See also

Select Object

EventDebugger, Example 2

Path

**Start Time [breakpoint]**

**Start Time [breakpoint]**

Type in the Start Time at which the breakpoint will be activated.

<!-- image -->

Start Time and Stop Time define the interval during which the breakpoint is active.

If you do not type in a value for the Start Time and/or the Stop Time , no limits apply to the interval during which the breakpoint is active.

See also

EventDebugger, Example 3

**Stop Time**

Type in the Stop Time at which the breakpoint will be deactivated.

<!-- image -->

Start Time and Stop Time define the interval during which the breakpoint is active.

If you do not type in a value for the Start Time and/or the Stop Time , no limits apply to the interval during which the breakpoint is active.

See also

EventDebugger, Example 3

**Type [breakpoint]**

**Type [breakpoint]**

Select the type of event for which the breakpoint is active. The asterisk ( * ) stands for any type of event.

<!-- image -->

**See also**

List of Events

EventDebugger Example 4

**Condition [breakpoint]**

Type in any Condition you would like to apply to the definition of the breakpoint. Before an event is released for execution, the Event Debugger checks the expression you entered.

<!-- image -->

This expression may be anything that returns a boolean value. If the condition returns true, the Event Debugger stops the simulation. If you use a formula for the Condition , you can access the Receiver using the anonymous identifier @ . You might, for example, enter @.Name = "Wheel" AND @.getNo = 4 or @.length&lt;100

The anonymous identifier ? accesses the Sender of the event.

Or you can click and select a Method in the dialog Select Object .

Note

The Method Debugger cannot track the method of the condition!

See also

Select Object

EventDebugger Example 4

<!-- image -->

**Trace File [breakpoint]**

To select an existing file, into which the Event Debugger writes the scheduled events of the objects, click the button at the right-hand side.

Type in the name of the file. If you do not type in a name, the Event Debugger does not create a trace file.

Or type in the path and the name of the trace file into which the Event Debugger writes the events.

See also

EventDebugger, Example 5

**Trace File [breakpoint]**

###### Run to Time [text box]

Type in the point in time up to which the simulation runs once you start it.

Once the point in time is reached, the EventController will stop without executing endSim methods .

<!-- image -->

The Context Menu of the List of Scheduled Events also shows the command Run to time .

**Trace File [check box]**

###### Trace File [check box]

To make the Event Debugger write all events it records to the file whose name you type into the text box Trace File , select this check box.

<!-- image -->

The specified trace file will only be written, when you select the check box Trace File .

SimTalk

TraceActive [SimTalk]

See also

Trace File [text box]

###### Trace File [text box]

Type in the name of the file to which the Event Debugger writes all events it records during the simulation run. If the file does not exist, the Event Debugger creates it.

<!-- image -->

The specified trace file will only be written, when you select the check box Trace File .

To open the dialog Save As and select an existing file to which the Event Debugger writes all events, click this . You can also set the name with the attribute TraceFile.

SimTalk

TraceFile [SimTalk]

See also

Trace File [check box]

###### Reset Simulation [EventDebugger]

Reset Simulation [EventDebugger]

To reset your simulation model, click this button.

<!-- image -->

The button does the same as the Reset Simulation button in the EventController .

SimTalk

reset [SimTalk] - EventController

See also

Reset Simulation [EventController]

initStat [SimTalk] - material flow objects

IsInitialized [SimTalk]

ResetCtrl [SimTalk]

###### Start/Stop Simulation [EventDebugger]

To start the simulation run, click this button. To stop the simulation after the active simulation event has been processed, click the button again.

<!-- image -->

The button does the same as the Start/Stop Simulation button in the EventController .

SimTalk

start [SimTalk] - EventController

stop [SimTalk] - EventController

See also

Start/Stop Simulation [EventController]

###### Start Full Speed Simulation [EventDebugger]

Start Full Speed Simulation [EventDebugger]

To start the simulation run with the animation of MUs and States and with full speed, click this button.

<!-- image -->

.

Start Full Speed Simulation updates a number of values, for example of objects of type Variable or Display , etc.

When you click Start Full Speed Simulation , Plant Simulation ignores the Real Time scaling factor .

SimTalk

Realtime [SimTalk]

RealtimeScale [SimTalk]

start [SimTalk] - EventController [SimTalk]

See also

MUs and States [Home ribbon]

<!-- image -->

Real-time x [EventController]

###### Start Fast Forward Simulation [EventDebugger]

To start the simulation run without MUs and States and with maximum speed, click this button. This makes the simulation run as fast as possible.

<!-- image -->

Start Fast Forward Simulation prevents updating a number of values, for example of objects of type Variable or Display

<!-- image -->

Instead, you can also click on the Home Ribbon Tab .

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

The button does the same as the Start Fast Forward Simulation button in the EventController .

SimTalk

start [SimTalk] - EventController

See also

MUs and States [Home ribbon]

<!-- image -->

Start Fast Forward Simulation [EventController]

###### Single Step Simulation [EventDebugger]

To process the next simulation event in line, to stop the simulation afterward, and to thus proceed through your model step-by-step, click this button.

<!-- image -->

.

The button does the same as the Single Step Simulation button in the EventController .

To debug all methods and formulas, which are executed while the event is being processed, hold down Shift while clicking Step . Plant Simulation opens the Method Debugger for all executed controls,

formulas and for suspended methods , which were woken up. Clicking Debug Next Simulation Step does the same.

See also

Single Step Simulation [EventController]

<!-- image -->

###### Debug Next Simulation Step [EventDebugger]

To open the Method Debugger for all methods and formulas, which are executed while the event is processed, click this button.

<!-- image -->

This means that the Method Debugger opens for all executed controls, formulas and for suspended methods , which were woken up. Holding down Shift while clicking Single Step Simulation accomplishes the same, in the EventDebugger and in the EventController .

See also

Single Step Simulation [EventDebugger]

<!-- image -->

**Step Halts Additionally Before Event**

###### Step Halts Additionally Before Event

To stop twice if the next event in the Event List is in the future, select this check box.

<!-- image -->

The first Single Step ( F10 ) jumps the simulation time to the event.

The second Single Step executes the event and stops immediately afterward. If the next event occurs at the same simulation time though, Plant Simulation does not stop in addition.

You can use this setting if you want to investigate the state of the model, for example the exact position of parts on a Conveyor , at the time at which the next event will be executed.

Step Halts Additionally Before Event is cleared by default, meaning that Single Step Animation stops once after each event.

See also

Event List

###### Close [Event Debugger]

To close the window of the Event Debugger , click this button or click the X in the title bar.

<!-- image -->

##### Navigate Menu

Navigate Menu

The commands are described under the Navigate Menu .

View Menu

View Menu

The View Menu provides commands to access its functions.

Refresh [on View menu]

Show Summary Report [menu command]

Show Attributes and Methods [on View menu]

SimTalk

updateDialog [SimTalk]

See also

View Menu [general description]

###### Show Summary Report [menu command]

Shows a summary report of the parts which the Drain deleted. At the end of the simulation run the Report checks all Drain objects within the entire simulation model which removed parts from the plant.

<!-- image -->

**See also**

Show Summary Report [EventController]

##### Tools Menu

###### Tools Menu [EventController]

The Tools Menu provides these menu commands:

| Edit Controls > Init control   | Random Numbers Variant     |
|--------------------------------|----------------------------|
| Edit Observers                 | Increment Variant on Reset |
| User-defined Attributes        | Antithetic Random Numbers  |
| 3D                             | -                          |

###### Init Control [EventController]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Init Control , which is called once at the beginning of the simulation run during the init phase before the objects are initialized and before init methods are executed.

<!-- image -->

You can also initialize attributes which affect event generation, for example the availability. Here the Init Controls are executed before events are generated. The normal init methods are executed after the initial events are computed.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.

- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

SimTalk

InitCtrl [SimTalk] - EventController

See also

Select Object

Set How Many Workers Are Created During Initialization

init [SimTalk] - predefined name

Init Methods and Init Controls

Call Sequence of the Init Controls

Example of the Call Sequence

Call Sequence of Reset and Init Methods

###### Random Numbers Variant

Shows and sets the random numbers variant. Different variants generate different random numbers. Select the command and type in a different random numbers variant.

<!-- image -->

**SimTalk**

RandomNumbersVariant [SimTalk]

See also

RandomSeed [SimTalk] - material flow objects

Simulating Random Processes

Video on YouTube

[https://youtu.be/HKDhTbohV6M?si=aHiNrXBQoamJuMCI&amp;t=292](https://youtu.be/HKDhTbohV6M?si=aHiNrXBQoamJuMCI&t=292)

###### Increment Variant on Reset

Sets if different random numbers will be generated after resetting the model or not.

<!-- image -->

If you activate the command, it shows a check mark to the left of the command.

SimTalk

IncrementRandomNumbersVariantOnReset [SimTalk]

See also

Simulating Random Processes

###### Antithetic Random Numbers

Sets if Plant Simulation uses common random numbers or antithetic random numbers .

<!-- image -->

For creating a random number for a distribution, for example for the exponential distribution , Plant Simulation uses a uniformly distributed random number U located between 0 and 1. For antithetic random numbers it uses 1U .

If you activate the command, it shows a check mark to the left of the command.

**SimTalk**

setAntitheticRandomNumbers [SimTalk]

##### Help Menu

The commands are described under the Help Menu .

**Methods of the EventController**

#### \_Methods of the EventController

The EventController provides:

- The methods listed in the table of contents to the left.
- The Methods of All Objects .

To view all of the methods , read-only attributes and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

An example of the Syntax line of the individual methods might look like this:

```simtalk
< Path >.openDialog([CallOpenControl:boolean:=false]) → boolean
```

- The expression &lt;Path&gt; designates the path of the object to which the method applies.
- The signature of the method, consisting of the identifier and the data type of the parameter, is listed in parentheses. The expression (Parameter:string) , for example, designates a parameter of data type string . Instead of a constant value, you can also use a variable of the required type or a method that returns the required data type.

**Note**

Make sure to enter the parentheses for expressions within parentheses (…). Not entering them may lead to unexpected results and open the Debugger .

Optional parameters are listed within brackets. The expression [,Parameter:boolean] , for example, means that you can, but do not have to enter the boolean parameter.

If a parameter has a default value, the signature shows the default value after the parameter.

If the method has a return value, the signature shows its data type after the arrow -&gt;.

getEventList [SimTalk]

Returns the list of scheduled events of the EventController designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.getEventList(MaximumNumberOfEvents:integer) → table

Parameter

The parameter MaximumNumberOfEvents of data type integer designates the maximum number of events, which the EventController writes to the data table.

Specify getEventList(-1) to write all events to the data table. The event list provides the columns Type , Time , Receiver , Sender , Insertion Time , and Parameters .

Return Value

The return value has the data type table .

Example

TableVariable := EventController.getEventList(-1)

See also

List of Events

Event List

**reset [SimTalk] - EventController**

Makes the EventController designated by &lt;Path&gt; run all methods in your simulation model that are named reset .

Remarks

Once all reset methods have been executed, Plant Simulation :

- Deletes all unprocessed events
- Resets the simulation time to 0
- Resets the statistics
- Clears all failures of all objects in the simulation model
- Sets all objects to the state planned
- Deletes all parts if you activate
- Reactivates inheritance of the settings Entrance Locked and Exit Locked for new models if you leave Tools &gt; Inherit 'Entrance/Exit Locked On Reset active.

**Note**

The Request Control , the Receive Control , and the Release Control of the Importer are not being called when you reset the simulation.

Plant Simulation does not execute the reset the simulation command immediately, but only when all methods being executed at the moment have been completely executed. This includes the method , which has triggered the Reset action. The method start behaves like this as well.

Type

Method

Syntax

```simtalk
< Path >.reset
```

**Example**

```simtalk
EventController.reset
EventController.start
EventController.RandomNumbersVariant := EventController.RandomNumbersVariant + 1 // When this method has been executed all the way, the Eventcontroller will be reset.
```

// When the reset phase has been finished all the way, the simulation will be started again. end

**SimTalk**

reset [SimTalk] - predefined name

ResetCtrl [SimTalk]

start [SimTalk] - EventController

See also

Reset Simulation [EventController]

Reset Simulation [EventDebugger]

Entrance Locked [material flow objects]

Exit Locked [material flow objects]

Inherit 'Entrance/Exit Locked' On Reset

**start [SimTalk] - EventController**

**start [SimTalk] - EventController**

Activates the EventController designated by &lt;Path&gt; and starts the simulation run.

Remarks

If the method is called during the simulation run for another EventController in another Frame , Plant Simulation stops the current EventController and starts the simulation run in the other Frame .

Plant Simulation does not start the EventController immediately, but only when all methods being executed at the moment have been completely executed. The method reset behaves like this as well.

Type

Method

Syntax

```simtalk
< Path >.start([WithAnimation:boolean:=animation, RealTime:boolean:=EventController.Realtime])
```

**Parameters**

- The parameter WithAnimation of data type boolean sets if the simulation will be started with animation ( true ) or without animation ( false ).

**Default Value of the Parameter**

The default value is animation.

If you do not specify this parameter, the EventController considers the global setting for the animation, compare MUs and States and the function animation .

- The parameter RealTime of data type boolean sets if the EventController starts a real-time simulation ( true ) or a full-speed simulation ( false ).

**Note**

Real-time simulation considers the real-time factor and can thus run faster than real-time if the real-time factor is greater than 1. It can run slower if the real-time factor is smaller than 1.

**Default Value of the Parameter**

The default value is EventController.Realtime .

If you do not specify this parameter, the EventController uses the value of the attribute RealTime .

**Example**

.delivery.EventController.start(false,false) // starts the simulation with maximum speed without animation

SimTalk

reset [SimTalk] - EventController

Realtime [SimTalk]

animation [SimTalk]

See also

Start/Stop Simulation [EventController]

MUs and States [Home ribbon]

Real-time x [EventController]

##### stop [SimTalk] - EventController

stop [SimTalk] - EventController

Stops the EventController designated by &lt;Path&gt; and thus terminates the simulation run.

Remarks

The simulation will not stop until the current method execution (including the entire call stack) finished or was suspended. A wait-statement will for example suspend method execution.

Type

Method

Syntax

```simtalk
< Path >.stop([EndSim:boolean:=false])
```

Parameter

The optional parameter EndSim of data type boolean set if the simulation will be stopped and if the endSim methods will be executed ( true ) or if the simulation will only be stopped ( false ).

**Default Value of the Parameter**

The default value is false.

Example

root.EventController.stop

SimTalk

endSim [SimTalk]

See also

Start/Stop Simulation [EventController]

wait [SimTalk]

Suspending Methods

#### Read-Only Attributes of the EventController

\_Read-Only Attributes of the EventController

The EventController provides:

- The read-only attributes listed in the table of contents to the left.
- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print EventController.AbsSimTime

**AbsSimTime [SimTalk]**

AbsSimTime [SimTalk]

Returns the current simulation time of the EventController designated by &lt;Path&gt; as an absolute time statement.

Type

Read-only attribute

Syntax

< Path >.AbsSimTime → dateTime

Return Value

The return value has the data type dateTime .

Example

print EventController.AbsSimTime // might return 2023/01/02 06:00:00.0000

See also

Time [EventController]

##### GetNextEventTime [SimTalk]

Returns the time at which the next event in the event list of the EventController designated by &lt;Path&gt; is scheduled to be executed.

Type

Read-only attribute

Syntax

< Path >.GetNextEventTime → time

Return Value

The return value has the data type time .

Example

```simtalk
print EventController.GetNextEventTime // might
return 10.0000
```

See also

List of Events

##### IsInitialized [SimTalk]

IsInitialized [SimTalk]

Returns if the EventController designated by &lt;Path&gt; has been initialized (true) or not (false).

Type

Read-only attribute

Syntax

&lt; Path &gt;.IsInitialized → boolean

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type boolean .

Example

print root.EventController.IsInitialized

##### IsResetting [SimTalk]

Returns if the EventController designated by &lt;Path&gt; is being reset at the moment (true) or not (false).

Remarks

Plant Simulation sets IsResetting to true when you reset the simulation model with the EventController designated by &lt;Path&gt;.

Plant Simulation sets it to false again as soon as all reset methods have been processed.

Type

Read-only attribute

Syntax

&lt; Path &gt;.IsResetting → boolean

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type boolean .

Example

print EventController.IsResetting

See also

reset [SimTalk] - EventController

##### IsRunning [SimTalk]

IsRunning [SimTalk]

Returns if the EventController designated by &lt;Path&gt; is running at the moment (true) or not (false).

Type

Read-only attribute

Syntax

```simtalk
< Path >.IsRunning → boolean
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type boolean .

Example

print root.EventController.IsRunning

##### SimTime [SimTalk]

Returns the current simulation time of the EventController designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

< Path >.SimTime → time

Watchable

The read-only attribute is watchable .

**Note**

You can, for example, watch the SimTime value with an object of type Display or Chart . You should never use SimTime in a method, which affects the simulation, with a waituntil-instruction or a stopuntil-instruction .

The time does not advance continuously, but jumps from event to event. If you activate the animation, Plant Simulation generates additional events so that the waituntil-instruction or stopuntil-instruction might be woken up at an earlier point in time than intended.

Return Value

The return value has the data type time .

Examples

```simtalk
param sensorID: integer, Front: boolean
if @.ID = 1
	@.Speed := 0
	print EventController.SimTime, " The first Transporter stopped."
end
print "Machine was deactivated at:", root.EventController.SimTime."
```

See also

Time [EventController]

waituntil [SimTalk] and stopuntil [SimTalk]

waituntil [SimTalk]

stopuntil [SimTalk]

#### Attributes of the EventController

\_Attributes of the EventController

The EventController provides:

- The attributes listed in the table of contents to the left.
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:

EventController.AbsTimeFormat := true

- To get the value of an attribute, you might, for example, type:
- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
print EventController.AbsTimeFormat
posit := MyStation.Cont.XPos
```

**AbsTimeFormat [SimTalk]**

**AbsTimeFormat [SimTalk]**

Shows the time of the EventController designated by &lt;Path&gt; as the absolute time ( true ) or as the relative time ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.AbsTimeFormat:boolean

Assignment Value

You can assign a value of data type boolean .

Example

EventController.AbsTimeFormat := false

See also

Time [EventController]

##### BreakpointsActive [SimTalk]

Activates ( true ) or deactivates ( false ) breakpoints of the Event Debugger of the EventController designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.BreakpointsActive:boolean

Assignment Value

You can assign a value of data type boolean .

Example

EventController.BreakpointsActive := true

See also

Breakpoints Active

##### EndTime [SimTalk] - EventController

EndTime [SimTalk] - EventController

Sets the time at which the simulation run controlled by the EventController designated by &lt;Path&gt; will end.

Remarks

Plant Simulation does not change the display in the dialog box after assigning a value to the attribute. You have to click OK or Apply to update the value!

Type

Attribute

Syntax

< Path >.EndTime:time

Assignment Value

You can assign a value of data type time .

Example

```simtalk
if root.EventController.EndTime - root.EventController.SimTime < 600
	print "Less than 10 minutes until the end of the simulation."
end
```

See also

End Time [EventController]

##### ExperimentManager [SimTalk]

Is set by the ExperimentManager when it controls an experiment of the EventController designated by &lt;Path&gt;.

Remarks

If the EventController controls the simulation, the attribute is void .

Type

Attribute

Syntax

&lt; Path &gt;.ExperimentManager:path

Assignment Value

You can assign a value of data type path .

Example

print EventController.ExperimentManager

See also

List of Events

ExperimentManager [object]

IncrementRandomNumbersVariantOnReset [SimTalk]

Makes the EventController designated by &lt;Path&gt; generate different random numbers after resetting the model ( true ) or not ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.IncrementRandomNumbersVariantOnReset:boolean

Assignment Value

You can assign a value of data type boolean .

Example

EventController.IncrementRandomNumbersVariantOnReset := false

See also

Increment Variant on Reset

Simulating Random Processes

##### InitCtrl [SimTalk] - EventController

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation runs the init control when you initialize the simulation model controlled by the EventController designated by &lt;Path&gt; by clicking Start/Stop Simulation or when the method start is called.

Plant Simulation executes the init control once at the beginning of the simulation run during the init phase before the objects are initialized and before init methods are being executed.

Type

Attribute

Syntax

< Path >.InitCtrl:method

Assignment Value

You can assign a value of data type method .

Examples

```simtalk
EventController.InitCtrl := &myInitControl
// The source code of an init control might look like this: MyWorkersTable[2,1] := 2 // enters the desired amount of the worker John MyWorkersTable[2,2] := 1 // enters the desired amount of the worker Nellie
WorkerPool.setCreationTable(MyWorkersTable)
```

SimTalk

init [SimTalk] - predefined name

start [SimTalk] - EventController

See also

Start/Stop Simulation [EventController]

Init Control [EventController]

Set How Many Workers Are Created During Initialization

##### RandomNumbersVariant [SimTalk]

Sets the random numbers variant that the EventController designated by &lt;Path&gt; uses.

Remarks

Different variants generate different random numbers.

Type

Attribute

Syntax

&lt; Path &gt;.RandomNumbersVariant:integer

Assignment Value

You can assign a value of data type integer .

Example

EventController.RandomNumbersVariant := 2

SimTalk

RandomSeed [SimTalk] - material flow objects

See also

Random Numbers Variant

Simulating Random Processes

**Realtime [SimTalk]**

##### Realtime [SimTalk]

Sets if the method start of the EventController designated by &lt;Path&gt; will start a real-time simulation ( true ) or a fast forward simulation ( false ).

Remarks

Realtime only applies if you call the method start without the second parameter named Realtime .

Type

Attribute

Syntax

```simtalk
< Path >.Realtime:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
EventController.Realtime := false
EventController.start
```

SimTalk

start [SimTalk] - EventController

See also

Real-time x [EventController]

Start Full Speed Simulation [Home ribbon]

##### RealtimeScale [SimTalk]

Sets the time factor of the EventController designated by &lt;Path&gt; that elapses between two events in real-time.

Remarks

The value you specify makes sure that the EventController shows the time span with this factor when the simulation proceeds.

The duration of an event in real-time is the simulation time divided by the scaling factor you enter. The resulting duration is an integer .

Type

Attribute

Syntax

&lt; Path &gt;.RealtimeScale:real

Assignment Value

You can assign a value of data type real .

Example

EventController.RealtimeScale := 10

See also

Real-time x [EventController]

**ResetCtrl [SimTalk]**

##### ResetCtrl [SimTalk]

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation runs the reset control whenever you click Reset Simulation in the EventController designated by &lt;Path&gt; or when the method reset is called.

Plant Simulation executes the reset control before calling any reset method you inserted in the Frame and any of its sub-Frames .

Type

Attribute

Syntax

&lt; Path &gt;.ResetCtrl:method

Assignment Value

You can assign a value of data type method .

Example

EventController.ResetCtrl := &amp;myResetMethod

SimTalk

reset [SimTalk] - EventController

See also

Reset Simulation [EventController]

Reset Simulation [EventDebugger]

##### SkipLongEventIntervals [SimTalk]

Makes the EventController designated by &lt;Path&gt; skip long phases during which no relevant event takes place during real-time simulation ( true ) or not ( false ).

Remarks

Events of type Animation and UpdateDisplay as considered to be not relevant.

Type

Attribute

Syntax

&lt; Path &gt;.SkipLongEventIntervals:boolean

Assignment Value

You can assign a value of data type boolean .

Example

EventController.SkipLongEventIntervals := true

See also

Skip Long Event Intervals StartDate [SimTalk] - EventController Sets the date and the time on which the absolute time of the EventController designated by &lt;Path&gt; during the simulation is based.

Type

Attribute

Syntax

&lt; Path &gt;.StartDate:dateTime

Assignment Value

You can assign a value of data type dateTime .

Example

EventController.StartDate := str\_to\_dateTime("2025/01/02 14:00:00")

See also

Start Date [EventController]

##### StartStat [SimTalk]

Sets the point in time at which the EventController designated by &lt;Path&gt; resets statistics collection and starts statistics collection anew.

Type

Attribute

Syntax

&lt; Path &gt;.StartStat:time

Assignment Value

You can assign a value of data type time .

Example

root.EventController.StartStat := str\_to\_time("40:00.00") // 40 minutes after simulation start

See also

Statistics [EventController]

##### StartStopCtrl [SimTalk]

StartStopCtrl [SimTalk]

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation runs the Method whenever you click Start/Stop Simulation in the EventController designated by &lt;Path&gt; or when the method start is called.

Plant Simulation also runs the start stop control , whenever you click Single Step Simulation in the EventController , when the next event is processed, and when the start stop control is executed again. The attribute is also called, when the simulation ends.

You can use the expression ?.IsRunning in the code of the control to tell if the EventController was started ( false ) or stopped ( true ).

Type

Attribute

Syntax

&lt; Path &gt;.StartStopCtrl:method

Assignment Value

You can assign a value of data type method .

Example

EventController.StartStopCtrl := &amp;myStartStopControl

SimTalk

IsRunning [SimTalk]

start [SimTalk] - EventController

See also

Start/Stop Simulation [EventDebugger]

Single Step Simulation [EventDebugger]

##### SummaryReport [SimTalk]

Makes the EventController designated by &lt;Path&gt; show a summary report at the end of the simulation run of those parts which the Drain deleted ( true ) or not ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.SummaryReport:boolean

Assignment Value

You can assign a value of data type boolean .

Example

EventController.SummaryReport := true

See also

Show Summary Report [EventController]

##### TraceActive [SimTalk]

TraceActive [SimTalk]

Sets if the EventController designated by &lt;Path&gt; records events ( true ) or does not record them ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.TraceActive:boolean

Assignment Value

You can assign a value of data type boolean .

Example

EventController.TraceActive := true

See also

Trace File [check box]

##### TraceFile [SimTalk]

Sets the name of the trace file into which the Event Debugger of the EventController designated by &lt;Path&gt; writes the event log.

Type

Attribute

Syntax

&lt; Path &gt;.TraceFile:string

Assignment Value

You can assign a value of data type string .

Example

EventController.TraceFile := "C:\temp\run1"

See also

Trace File [text box]

