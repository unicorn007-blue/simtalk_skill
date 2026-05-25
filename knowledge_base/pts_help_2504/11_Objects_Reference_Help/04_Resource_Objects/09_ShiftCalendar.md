### ShiftCalendar

#### ShiftCalendar [object]

Use the ShiftCalendar for modeling the shift system of the shifts worked in your plant.

Icon

<!-- image -->

Description

You can define as many shifts as you need in your simulation model. A shift pauses one or several machines in your model, by setting the boolean attributes Pause and Unplanned of the respective material flow objects to true.

**Note**

If you deactivate the Pause during the unplanned time, either by clearing the check box Pause in the dialog of the object, or by setting the attribute Pause to false , the object starts to work.

Use the method schedule to make the ShiftCalendar set the date and time to start or to finish the production process. We distinguish between:

- Forward scheduling beginning from the start date forward into the future, and
- Backward scheduling which computes the start date going backward in time from the demand date.

Normally, you start with the demand date, computing the start date through backward scheduling. If this start date is located in the past though, you have to recompute the dates beginning with the present time and forward-schedule the end date.

<!-- image -->

To show a tooltip with information about the ShiftCalendar , hover with the mouse over it.

To change the length of the graphic and the anchor points of the ShiftCalendar , click Show Manipulators

<!-- image -->

on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the ShiftCalendar to your simulation model, click Manage Class Library &gt; Basic Objects &gt; Resources &gt; ShiftCalendar on the Home ribbon tab.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

**See also**

Model a Shift System

Shift Calendar [tab Controls]

Select Shift Calendar

##### Dialog Box of the ShiftCalendar

Dialog Box of the ShiftCalendar

Double-click the icon of the ShiftCalendar to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

See also

Active [check box] - ShiftCalendar

##### Active [check box] - ShiftCalendar

Active [check box] - ShiftCalendar

To make your facility work in shifts, select this check box.

To deactivate shift work, clear the check box.

<!-- image -->

Instead, you can also right-click the ShiftCalendar object in the Frame and select Activate on the context menu.

To deactivate shift operation, select Deactivate on the context menu.

<!-- image -->

Tab Shift Times

Tab Shift Times

Type in the name of the Shift , the time it starts, the time it ends, and the duration of Pauses on the tab Shift Times .

<!-- image -->

To select which shift works on which day, select the respective check box in the cells below Mo, Tu, We, Th, Fr, Sa, Su .

<!-- image -->

To manipulate the contents of the list, use the commands on the Context Menu of Embedded Lists .

SimTalk

schedule [SimTalk] - ShiftCalendar

ShiftPlan [SimTalk]

See also

Shift [ShiftCalendar]

From

To

Pauses [ShiftCalendar]

Specify the Names of the Shifts, the Respective Times and Days

**Shift [ShiftCalendar]**

###### Shift [ShiftCalendar]

Type in the names of the different shifts into these cells.

You might, for example, type in Morning , Evening , Graveyard , etc.

<!-- image -->

<!-- image -->

In 3D the ShiftCalendar displays these state graphics:

<!-- image -->

**SimTalk**

GetCurrShift [SimTalk]

ShiftPlan [SimTalk]

###### From

Type the times the shifts start in these cells.

Type in a time between 0:00 o'clock and 24:00 o'clock. You can only type in hours and minutes, not hours, minutes and seconds.

<!-- image -->

- To create a shift located within one day, type in a greater number for the time at which it ends than for the time at which it starts. You might, for example, define a Morning shift that starts at 6:00 in the morning and ends at 14:00 on the same day.
- To create a shift that spans two days, type in a smaller number for the time at which it ends than for the time at which it starts. You might, for example, define a Graveyard shift that starts at 22:00 at night on one day, and ends at 6:00 in the morning on the next day.

**Note**

You cannot enter overlapping shift times.

**SimTalk**

ShiftPlan [SimTalk]

To Type the times at which the shifts end into these cells.

Type in a time between 0:00 o'clock and 24:00 o'clock. You can only specify hours and minutes, not hours, minutes and seconds.

<!-- image -->

- To create a shift located within one day, type in a greater number for the time at which it ends than for the time at which it starts. You might, for example, define a Morning shift that starts at 6:00 in the morning and ends at 14:00 the same day.
- To create a shift that spans two days, type in a smaller number for the time at which it ends than for the time at which it starts. You might, for example, define a Graveyard shift that starts at 22:00 at night on one day, and ends at 6:00 in the morning on the next day.

**Note**

You cannot enter overlapping shift times.

SimTalk

ShiftPlan [SimTalk]

Mo, Tu, We, Th, Fr, Sa, Su

To select the individual days on which the shift in the row is active, click the respective check box in the cells below the days of the week.

<!-- image -->

**You might, for example:**

- Define a Morning shift that works Monday up to and including Friday .
- Define an Evening shift that works Monday up to and including Sunday .

**SimTalk**

ShiftPlan [SimTalk]

**Pauses [ShiftCalendar]**

###### Pauses [ShiftCalendar]

Type in the times of the breaks for each shift into these cells.

Type in the hour and the minute when the break starts, a hyphen and the hour and minute the break ends. When you define several breaks, separate them with a semicolon.

To define a coffee break from 9 o'clock to a quarter past 9 o'clock, and a lunch break from 12 o'clock to a quarter till 1 o'clock, type in 9:00-9:15;12:00-12:45 .

<!-- image -->

To make the ShiftCalendar check if the values you typed in for the breaks are plausible or not and if you used the correct format to enter the break times, click Apply .

**SimTalk**

ShiftPlan [SimTalk]

Tab Calendar

Tab Calendar

Define the days on which your plant does not work at all or only works part of the time, and a Comment describing the event on the tab Calendar .

**Note**

Before you can use the date picker, click the check box Inheritance so that it looks like this You can also import a calendar that you saved. Or you can export a calendar you defined and then import it into another simulation model. Click into the list field with the right mouse button and select Import or Export .

<!-- image -->

To manipulate the contents of the list, use the commands on the Context Menu of Embedded Lists .

SimTalk

Calendar [SimTalk]

schedule [SimTalk] - ShiftCalendar

See also

Date From

Date To

Reduce Time To

Comment [reduce time to]

Specify Times During Which the Plant Works Part of the Time

**Date From**

###### Date From

To specify the date at which your plant starts not working into these cells with the date picker:

- Click the Inheritance check box so that it looks like this .
- Double-click into the text box and click the down arrow .
- Select a date in the calendar. Click the right or left buttons to move to another month.

<!-- image -->

To designate an entire day as a day-off, only select a start date, and no end date ( Date To ), and no Reduce Time To .

SimTalk

Calendar [SimTalk]

###### Date To

To specify the date at which your plant stops not working into these cells with the date picker:

<!-- image -->

- Click the Inheritance check box so that it looks like this .
- Double-click into the text box and click the down arrow . Select a date in the calendar. Click the right or left buttons to move to another month.

<!-- image -->

To designate a consecutive number of days-off, enter a start date ( Date From ), and an end date, and no Reduce Time To .

SimTalk

Calendar [SimTalk]

###### Reduce Time To

Type in the hour and the minute when the reduced Working time starts, a hyphen and the hour and minute the reduced time ends.

<!-- image -->

If your plant only works half a day on Christmas Eve, for example the shift from midnight to noon, you would type 0:00 - 12:00 into the cell Reduce Time To .

To designate several days on which your plant only works part of the time, type the start date in the cell in the column Date From , and the end date in the cell in the column Date To . Then, type the period of time in the cell Reduce Time To .

**Note**

The ShiftCalendar combines the reduced time and the definition of the shifts for a day. If, for example, the start time of a day with a reduced working time falls on a break, then this work day starts with a break.

**SimTalk**

**Calendar [SimTalk]**

See also

Working [state, material flow objects]

<!-- image -->

###### Comment [reduce time to]

Type a description of the event causing the Reduce Time To in this cell.

See also

Reduce Time To

Tab Resources

Tab Resources [ShiftCalendar]

Assign resources, meaning objects, to the ShiftCalendar on the tab Resources .

A resource is any of the built-in Material Flow Objects , or a Frame in which you modeled a machine, whose Working hours you would like to control with the ShiftCalendar .

To add a resource to the tab Resources , drag it from the Frame window over the icon of the ShiftCalendar and drop it there. You can also select and then drag-and-drop multiple objects at the same time!

This automatically enters the ShiftCalendar into the text box Shift Calendar on the tab Controls of the material flow object.

<!-- image -->

To manipulate the contents of the list, use the commands on the Context Menu of Embedded Lists .

See also

Specify the Stations Which the ShiftCalendar Controls

Resources [SimTalk] - ShiftCalendar

Shift Calendar [tab Controls]

###### Objects [ShiftCalendar]

Assign resources to the ShiftCalendar on the tab Resources .

A resource is any of the built-in Material Flow Objects , or a Frame in which you modeled a machine, whose Working hours you would like to control with the ShiftCalendar .

<!-- image -->

- Type the path to and the name of the resource object in a cell. Or
- Drag the resource object to the icon of the ShiftCalendar and drop it there. Or
- Type the name of the ShiftCalendar object on the tab Controls of the material flow object into the text box Shift Calendar .

**Note**

Plant Simulation pauses all resources you assign to a shift.

**SimTalk**

Resources [SimTalk] - ShiftCalendar

##### Tab User-defined

Tab User-defined

Define your own attributes as described under the Tab User-defined .

File Menu

File Menu [ShiftCalendar]

The File menu provides the commands listed in the table of contents to the left.

###### Import Shift Times

Imports the times during which your plant works in shifts from a tab delimited text file.

**Export Shift Times**

###### Export Shift Times

Exports the shift times you defined on the Tab Shift Times to a file.

You can then import this file into another ShiftCalendar or edit in a word processing program.

See also

Tab Shift Times

###### Import Calendar

Imports the calendar, i.e., the days during which your plant works in shifts from a tab delimited text file.

**Export Calendar**

###### Export Calendar

Exports the shift calendar you defined on the Tab Calendar to a file.

You can then import this file into another ShiftCalendar or edit in a word processing program.

See also

Tab Calendar Navigate Menu The commands are described under the Navigate Menu . View Menu View Menu The View Menu provides commands to access its functions. Refresh [on View menu] Show Assigned Objects [ShiftCalendar] Show Attributes and Methods [on View menu] SimTalk updateDialog [SimTalk]

**Show Assigned Objects [ShiftCalendar]**

Selects the objects which are assigned to the ShiftCalendar as resources in the Frame window.

<!-- image -->

Instead, you can also select Show Assigned Objects on the context menu of the ShiftCalendar in the Frame .

Tools Menu

The Tools Menu provides these menu commands: Edit Controls Edit Observers

##### Help Menu

The commands are described under the Help Menu .

#### Methods of the ShiftCalendar

**\_Methods of the ShiftCalendar**

The ShiftCalendar provides:

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

##### calculateWorkingDuration [SimTalk]

calculateWorkingDuration [SimTalk]

Calculates the Working Duration between two points in time for the ShiftCalendar designated by &lt;Path&gt;.

Remarks

While calculating the working duration, calculateWorkingDuration takes pauses and shifts into account.

Type

Read-only attribute

Syntax

&lt; Path &gt;.calculateWorkingDuration(StartTime:dateTime, EndTime:dateTime) → time

**Parameters**

- The parameter StartTime of data type dateTime designates the start time from which on the ShiftCalendar computes the working duration.
- The parameter EndTime of data type dateTime designates the end time until which the ShiftCalendar computes the working duration.

**Return Value**

The return value has the data type time .

**Example**

```simtalk
var startDateTime   : dateTime
var endDateTime     : dateTime
var workingDuration : time startDateTime := str_to_dateTime("02.01.2006 0:00")
endDateTime   := str_to_dateTime("02.01.2006 10:15")
workingDuration := MyShiftCalendar.calculateWorkingDuration(startDateTime, endDateTime)
print workingDuration
```

**See also**

Working [state, material flow objects]

##### schedule [SimTalk] - ShiftCalendar

Schedules the date and time to start or to finish the production process for the ShiftCalendar designated by &lt;Path&gt;.

Remarks

The method schedule can schedule 100 years into the future.

Type

Method

Syntax

```simtalk
< Path >.schedule(StartTime:dateTime, Duration:time, Direction:string) → dateTime
```

**Parameters**

- The parameter StartTime of data type dateTime designates the start or end date and time from which on the ShiftCalendar schedules the production date.
- The parameter Duration of data type time designates the duration of the production process.
- The parameter Direction of data type string designates direction, i.e., if the ShiftCalendar computes forward or backward in time.
- For forward scheduling, the production order requires a defined production time for manufacturing the product. Beginning at the start date, which normally is the active date, the method schedule computes the date on which the product has to be finished. It takes production time, shift times, weekends and holidays into consideration.
- For backward scheduling, where you know the date on which the product has to available, as well as the production time, the method schedule computes the start date on which production has to start. It takes production time, shift times, weekends and holidays into consideration.

**Return Value**

The return value has the data type dateTime .

**Example**

```simtalk
startDateAndTime := str_to_dateTime("4.1.2003 9:00")                             // Friday 9:00
Duration := str_to_time("10:00:00.0")                                            // 10 hours
endDateAndTime := MyShiftCalendar.schedule(startDateAndTime,Duration, "forward") // Monday 12:00
```

See also

Schedule Date and Time to Start or Finish the Production Process

#### Read-Only Attributes of the ShiftCalendar

\_Read-Only Attributes of the ShiftCalendar

The ShiftCalendar provides:

- The read-only attributes listed in the table of contents to the left.

GetCurrShift [SimTalk]

Pause [SimTalk] - ShiftCalendar Unplanned [SimTalk] - ShiftCalendar

- The Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyShiftCalendar.Unplanned

##### GetCurrShift [SimTalk]

GetCurrShift [SimTalk]

Returns the name of the shift of the ShiftCalendar designated by &lt;Path&gt; that is currently active.

Remarks

This is the name you typed into the column Shift on the tab Shift Times .

Type

Read-only attribute

Syntax

&lt; Path &gt;.GetCurrShift → string

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type string .

Example

shift := root.MyShiftCalendar.GetCurrShift

See also

Tab Shift Times

Shift [ShiftCalendar]

##### Pause [SimTalk] - ShiftCalendar

Returns if the ShiftCalendar designated by &lt;Path&gt; is paused (true) or not (false).

Type

Read-only attribute

Syntax

&lt; Path &gt;.Pause → boolean

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type boolean .

Example

print MyShiftCalendar.Pause

See also

Paused [state, material flow objects]

Unplanned [SimTalk] - ShiftCalendar

Returns, if the ShiftCalendar designated by &lt;Path&gt; is unplanned (true) or not (false).

Type

Read-only attribute

Syntax

&lt; Path &gt;.Unplanned → boolean

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type boolean .

Example

print MyShiftCalendar.Unplanned

See also

Unplanned [state, material flow objects]

#### Attributes of the ShiftCalendar

\_Attributes of the ShiftCalendar

The ShiftCalendar provides:

- The attributes listed in the table of contents to the left.
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyShiftCalendar.ShiftPlan := shiftTimesTable
print MyShiftCalendar.ShiftPlan
posit := Station.Cont.XPos
```

##### Active [SimTalk] - ShiftCalendar

Active [SimTalk] - ShiftCalendar

Activates the ShiftCalendar designated by &lt;Path&gt; ( true ), i.e., if your plant works in shifts, or deactivates it ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.Active:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyShiftCalendar.Active := true

See also

Active [check box] - ShiftCalendar

##### Calendar [SimTalk]

Sets the calendar of the ShiftCalendar designated by &lt;Path&gt;.

Remarks

Plant Simulation copies the contents of the DataTable , which you specify, to the internal calendar table on the tab Calendar . For clarity reasons we recommend to use column and row headers.

- Select the data type date for the first column ( Date From ) of the table and enter the date the shift starts.
- Select the data type date for the second column ( Date To ) and enter the date the shift ends.
- Select the data type string for the third column ( Reduce Time To ) and enter the hours during which the shift in your plant is active.
- Select the data type string for the fourth column ( Comment ) and enter why the shift does not apply.

Assigning the table overwrites the contents of any existing calendar.

Type

Attribute

Syntax

&lt; Path &gt;.Calendar:any

Assignment Value

You can assign a value of data type any .

Example

MyShiftCalendar.Calendar := shiftCalendarTable

See also

Tab Calendar Resources [SimTalk] - ShiftCalendar Sets the resource objects that the ShiftCalendar designated by &lt;Path&gt; controls.

Remarks

Plant Simulation copies the contents of the DataTable , which you specify, to the internal Resources (Objects table on the tab Resources ).

Select the data type object for the first column of the data table and enter all objects to be controlled by the shift calendar.

Assigning the table overwrites the contents of any existing resource table. For clarity reasons we recommend to use column and row headers. You can also use the rest of the table for any other purpose.

Type

Attribute

Syntax

&lt; Path &gt;.Resources:any

Assignment Value

You can assign a value of data type any .

Example

shifts.Resources := ResourcesTable

See also

Tab Resources [ShiftCalendar]

##### ShiftPlan [SimTalk]

Sets the shift calendar of the ShiftCalendar designated by &lt;Path&gt;.

**Remarks**

Plant Simulation copies the contents of the DataTable , which you specify, to the internal shift times table on the tab Shift Times . For clarity reasons we recommend to use column and row headers.

- Select the data type string for the first column ( Shift ) of the data table and enter the name of the shift.
- Select the data type time for the second column ( From ) and enter the time the shift starts.
- Select the data type time for the third column ( To ) and enter the time the shift ends.
- Select the data type boolean for the fourth to the tenth column ( Mo through Sun ). Enter true , when the shift applies to this day. Enter false , when the shift does not apply to this day.
- Select the data type string for the eleventh column ( Pauses ) and enter the times of the pauses.

**Note**

You cannot specify overlapping shifts.

Assigning the table overwrites the contents of any existing shift times.

<!-- image -->

When you get the shift plan, column 12 of the returned table contains a subtable with the start and end times of the pauses.

Column 13 contains an error code. If a value is non-zero, the values in the shift plan are not consistent.

**Note**

The attribute ShiftPlan returns a temporary table. The ShiftCalendar cannot detect that the temporary table was modified.

The correct way is to assign the returned table to a variable, modify the temporary table and assign it back to the attribute ShiftPlan .

Type

Attribute

Syntax

```simtalk
< Path >.ShiftPlan:table
```

Assignment Value

You can assign a value of data type table .

Example

```simtalk
MyShiftCalendar.ShiftPlan := shiftTimesTable
// This code modifies the shift table
var t:table := ShiftCalendar.ShiftPlan
t["From", 1] := 3:00:00
ShiftCalendar.ShiftPlan := t
```

See also

Tab Shift Times

#### LockoutZone

