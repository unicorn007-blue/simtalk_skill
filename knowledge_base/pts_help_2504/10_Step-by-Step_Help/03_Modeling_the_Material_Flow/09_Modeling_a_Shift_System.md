### Modeling a Shift System

#### Model a Shift System

When creating your simulation model, you will, more than likely, also have to integrate the shift system that applies to your plant. You can quickly and easily define these shifts with the object ShiftCalendar .

The ShiftCalendar can control the working hours as well as the paused times, the planned times, and the unplanned times of these material flow objects : Frame , Station , ParallelStation , AssemblyStation , DismantleStation , Buffer , PlaceBuffer , Store , Sorter , Conveyor , AngularConverter , Turntable , Turnplate , Track , TwoLaneTrack , Source , Drain , WorkerPool , and Exporter .

Naturally, you can also control Frames in which you modeled components of your overall plant, with the ShiftCalendar . Here you use Methods as unplanned time and paused time controls of that Frame to propagate the shift settings to the objects, which you inserted into this Frame .

The ShiftCalendar can control the working hours as well as the paused times, the planned times, and the unplanned times of these fl uid objects : FluidSource , Mixer , Portioner , and DePortioner .

You can use the method schedule to make the ShiftCalendar set the date and time to start or to finish the production process.

**Starting and Ending a Shift**

When a ShiftCalendar starts a shift, it sets the attribute Unplanned of the material flow objects and of any of the Frames at controls to false, i.e., it deactivates unplanned times. If need be, you can program an Unplanned Control that executes other actions, which your modeling situation requires.

The statistics of the material flow objects then starts to collect the unplanned time. This is the time when a resource is not planned to work.

When you define shifts that are active from 6 o'clock in the morning until 10 o'clock at night, for example, the planned time lasts from 6 o'clock to 22 o'clock. The unplanned time lasts from 22 o'clock to 6 o'clock the following morning.

When a ShiftCalendar finishes a shift, it sets the attribute Unplanned of the material flow object and Frames it controls to true, i.e., it activates unplanned times. Then, the objects stop processing the current part and release all services.

**Starting and Ending a Break**

When a ShiftCalendar starts a break, it sets the attribute Pause of the material flow objects and of the Frames it controls to true, i.e., it activates pauses. For the material objects activating a pause also affects statistics. For Frames Plant Simulation only changes the state of the attribute. If need be, you can program a Pause Control for your Frames that executes the actions your modeling situation requires.

When a ShiftCalendar ends a break, it sets the attribute Pause of the material flow object and Frames it controls to false, i.e., it deactivates pauses. For the Frames you can react to the end of a pause in a pause control that executes the actions your modeling situation requires.

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

Go to Define Shifts with the ShiftCalendar

Go to Pause Material Flow Objects and Frames

Back to Modeling the Material Flow

#### Defining Shifts with the ShiftCalendar

Define Shifts with the ShiftCalendar

You can insert the ShiftCalendar into your simulation model from the folder Resources in the Class Library or from the toolbar Resources in the Toolbox .

<!-- image -->

<!-- image -->

You can define the settings for the entire shift system in the ShiftCalendar . You can:

- Specify the Names of the Shifts, the Respective Times and Days

- Specify Times During Which the Plant Works Part of the Time
- Specify the Stations Which the ShiftCalendar Controls
- Schedule Date and Time to Start or Finish the Production Process

Once you have entered all the settings for the shifts, you have to select the check box Active , so that Plant Simulation uses the shifts in your simulation model.

Compare Pause Material Flow Objects and Frames

**Back to Model a Shift System**

Specify the Names of the Shifts, the Respective Times and Days

Before you can type in data, click the Inheritance check box so that it looks like this .

Type the data pertaining to one shift into the cells of one row.

<!-- image -->

- Type the names of the different shifts into the cells below Shift . You might, for example, enter Morning shift , Day shift , Evening shift , Graveyard shift , etc.

In 2D the ShiftCalendar displays different icons for the shifts and the states it is in:

<!-- image -->

<!-- image -->

| Icon   | Description                  |
|--------|------------------------------|
|        | The ShiftCalendar is waiting |
|        | The ShiftCalendar is paused  |

- Type the times at which the shifts start into the cells below From . Enter a time between 0:00 o'clock and 24:00 o'clock. You can only enter hours and minutes, not hours, minutes and seconds.
- To create a shift located within one day, type in a greater number for the time it ends than for the time it starts. You might, for example, define a Morning shift that starts at 6:00 o'clock in the morning and ends at 14:00 o'clock on the same day.
- To create a shift that spans two days, type in a smaller number for the time it ends than for the time it starts. You might, for example, define a Graveyard shift that starts at 22:00 o'clock at night on one day, and ends at 6:00 o'clock in the morning on the next day.
- Type the times at which the shifts end into the cells below To . Enter a time between 0:00 o'clock and 24:00 o'clock. You can only specify hours and minutes, not hours, minutes and seconds.
- To select the individual days on which the shift in the row is active, click in the cells below the days of the week.

**You might, for example:**

- Define a Morning shift that works from Monday up to and including Saturday .
- Define an Evening shift that works from Monday up to and including Friday .
- Type the times of the breaks for each shift into the cells below Pauses . Enter the hour and the minute when the break starts, a hyphen and the hour and minute the break ends. When you define several breaks during one work day, separate them with a semicolon.

To define a coffee break from 9 o'clock to a quarter past 9 o'clock, and a lunch break from 12 o'clock to a quarter till 1 o'clock, enter 9:00-9:15;12:00-12:45 .

To make the ShiftCalendar check if the values you entered for the breaks are plausible or not and if you used the correct format to enter the break times, click Apply .

You can also import the settings for the individual shifts, which you saved as a tab-delimited text file or which you received from factory management. Type in the data, so that it matches the screenshot below. Or you can export a shift, which you defined, and then import it into another simulation model. To do so, right-click in the list field and select Export or Import on the context menu.

<!-- image -->

Compare Context Menu of Embedded Lists

Back to Define Shifts with the ShiftCalendar

Specify Times During Which the Plant Works Part of the Time

Before you can type in data pertaining to public holidays, retooling periods and times during which the plant only works part of the time, click the check box Inheritance , so that it looks like this .

<!-- image -->

- To type the date when your plant starts not working into the cells below Date From :
- Double-click into the cell and click the down arrow .
- Select a date in the calendar. Click the right or left buttons to move to another month.

<!-- image -->

To designate an entire day as a day-off, only type in a start date and no end date ( Date To ), and no Reduce Time To .

- To type the date when your plant stops not working into the cells below Date To :

- Double-click into the cell and click the down arrow .
- Select a date in the calendar. Click the right or left buttons to move to another month.
- To designate a single day on which your plant only works part of the time, type its date in the cell in the column Date From . Type the hour and the minute when the reduced working time starts, a hyphen and the hour and minute the reduced time ends into the cells below Reduce Time To .

If your plant only works half a day on Christmas Eve, for example the shifts from midnight to noon, you would type 0:00 - 12:00 into the cell Reduce Time To .

**Note**

The ShiftCalendar combines the reduced time and the definition of the shifts for a day. If, for example, the start time of a day with a reduced working time falls on a break, then this work day starts with a break.

- Type a description of the event of why your plant does not work into the cells below Comment .

You can also import a calendar, which you saved as a tab-delimited text file or which you received from factory management. Type in the data, so that it matches the screenshot below. Or you can export a calendar you defined and then import it into another simulation model. To do so, right-click in the list field and select Export or Import on the context menu.

<!-- image -->

**Back to Define Shifts with the ShiftCalendar**

Specify the Stations Which the ShiftCalendar Controls

Enter the name of any of the built-in material flow objects, or enter the name of a Frame you used to model a machine, whose working hours you would like to control with the ShiftCalendar into the cells of the list.

<!-- image -->

This automatically enters the ShiftCalendar :

- Into the dialog Select Shift Calendar that the command Select Shift Calendar on the Frame ribbon tab of the Frame opens.
- Into the text box Shift calendar on the tab Controls of the material flow object.

<!-- image -->

Back to Define Shifts with the ShiftCalendar

Schedule Date and Time to Start or Finish the Production Process You can use the method schedule to set the date and the time to start or to finish the production process. We distinguish between:

- Forward scheduling , beginning from the start date forward into the future, and
- Backward scheduling , which computes the start date going backward in time from the demand date.

Normally you start with the demand date, and compute the start date through backward scheduling. If this start date is located in the past though, you have to recompute the dates beginning with the present time and forward-schedule the end date.

<!-- image -->

In our example below we programmed the method schedule to compute the end date of two jobs taking into account the shifts we defined in the ShiftCalendar .

The source code looks like this:

```simtalk
var startTime := str_to_dateTime( "4.1.2013 0:00" )
var durationTime := str_to_time( "10:00:00.0" )
var EndTime := ShiftCalendar.schedule( startTime, durationTime, "forward" )
print "StartDate: ", startTime, "   Duration: ", durationTime, "   EndDate: ", EndTime
startTime := str_to_dateTime( "20.12.2013 0:00" )
durationTime := str_to_time( "19:00:00.0" )
EndTime := ShiftCalendar.schedule( startTime, durationTime, "forward" )
print "StartDate: ", startTime, "   Duration: ", durationTime, "   EndDate: ", EndTime
```

The first job starts on January 4, 2013 at midnight and takes 10 hours to finish. The second job starts on December 12, 2013 and takes 19 hours. We want to know on what days and at which times the parts will be all processed, considering the morning and day shifts we defined in the ShiftCalendar .

We also programmed the Method to print the results of its computations to the Console .

<!-- image -->

Back to Define Shifts with the ShiftCalendar

#### Pausing Material Flow Objects and Frames

Pause Material Flow Objects and Frames

The ShiftCalendar interacts with the material flow objects and the Frames it controls by changing their Paused/Planned/Unplanned state.

One of these objects is:

- Paused if it is not processing parts due to a pause. It resumes processing once you terminate the pause, either by selecting Planned from the drop-down list or by setting its attribute Pause to false .

**Note**

When a station fails, and a pause occurs during the failure, the failure time of the station will still be consumed, although the station is paused. Statistics counts the times during which these two states overlap as paused time. Resetting your model removes both failures and pauses of the object.

- Unplanned if it is not scheduled to work during the shifts which you defined in the ShiftCalendar .
- Planned if it is scheduled to work during the shifts which you defined in the ShiftCalendar . The scheduled/planned time is the processing time minus the times of the breaks.

We distinguish between:

- Paused Material Flow Objects and
- Paused Frames

Back to Model a Shift System

Paused Material Flow Objects

The ShiftCalendar interacts with the material flow objects by changing their paused state according to the shifts you defined. During a simulation run the dialog of these objects also reflects this by selecting the present state in the drop-down list.

<!-- image -->

When it is paused, the material flow object does not receive any mobile parts. MUs can exit the object, when you program a Method to make them do so. Plant Simulation stops set-up and processing until the end of the pause or of the unplanned time.

The unplanned state is identical to the paused state. The only difference is how Plant Simulation counts the internal statistics of the objects. When you define shifts that are active from 6 o'clock in the morning until 10 o'clock at night, for example, the planned time lasts from 6 o'clock to 22 o'clock. The unplanned time lasts from 22 o'clock to 6 o'clock the following morning.

<!-- image -->

When it is planned/scheduled to work, the object receives and processes MUs and moves them on to the succeeding object in the material flow.

Back to Pause Material Flow Objects and Frames

Paused Frames As opposed to the material flow objects, which you can also pause manually, you can only change the paused and the unplanned states of the Frame with its attributes Pause and Unplanned .

In addition, you can program a pause and/or an unplanned time control, both of which activate a Method in changing the value of the attribute .

<!-- image -->

**Example of a Pause Control**

You can change the paused state of the Frame by assigning the value true or false to the attribute Pause . Use the anonymous identifier ? to access the object from within a control.

Plant Simulation executes the Pause Control , whenever the paused state of the Frame changes. When you get the paused state within the Method , it shows the state after the change.

The source code looks like this:

```simtalk
print "Current pause ", current.pause
MyStation.pause := current.pause
var shift := root.ShiftCalendar.getCurrShift
print "Current shift: ", shift
if not current.unplanned
if current.pause
	current.currIcon := "pause"
else
	current.currIcon := "working"
end
end
```

**Example of an Unplanned Control**

Plant Simulation executes the Unplanned Control , whenever the unplanned state of the Frame changes, i.e., whether the Frame is not scheduled to work during the time you entered or whether it is scheduled to work.

You can change the unplanned state by assigning the value true or false to the attribute Unplanned . Use the anonymous identifier ? to access the object from within a control.

The source code looks like this:

```simtalk
print "Frame unplanned: ", current.unplanned
MyStation.unplanned := current.unplanned
if current.unplanned
	current.currIcon := "unplanned"
else
	if current.pause
		current.currIcon := "pause"
	else
		current.currIcon := "working"
	end
end
```

Back to Pause Material Flow Objects and Frames

