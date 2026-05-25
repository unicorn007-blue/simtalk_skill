### Debugger Ribbon Tab

The Debugger ribbon tab provides commands to access its functions.

<!-- image -->

The Method Debugger enables you to debug your simulation model. You can stop the simulation and check how the simulation run is proceeding. You can set breakpoints to stop the simulation, so that you can monitor the behavior of methods which you programmed.

The Debugger provides access to all data involved in methods, allowing you to inspect the model and the methods involved. By comparing what is and what should be, you easily detect errors, can correct faulty source code and continue the simulation run or start it anew.

**Note**

You cannot terminate an infinite loop in a method by employing the EventController as another event is expected to take place, but never does.

When Plant Simulation executes a Method , you can press Ctrl+Shift+Alt to open the Debugger .

The Debugger ribbon tab provides these commands, which apply to all methods in your simulation model:

<!-- image -->

| Command                                     | Button   | Method                      |
|---------------------------------------------|----------|-----------------------------|
| Switch to Debugger                          |          | debug [SimTalk]             |
| Stop on Controls Stop on Controls in Object |          | -                           |
| Stop on Wakeup                              |          | -                           |
| Stop on Formulas                            |          | -                           |
| Stop on Error Handlers                      |          | -                           |
| Ignore Breakpoints                          |          | ignoreBreakpoints [SimTalk] |
| Ignore Error Handlers                       |          | -                           |
| Ignore Errors                               |          | setErrorStop [SimTalk]      |

#### Debugger Ribbon Tab

<!-- image -->

| Command                                  | Button   | Method                           |
|------------------------------------------|----------|----------------------------------|
| Ignore Errors in Formulas                |          | setErrorStop [SimTalk]           |
| Manage Breakpoints                       |          | -                                |
| Delete All Breakpoints [Debugger ribbon] |          | clearAllBreakpoints [SimTalk]    |
| Delete All Expressions                   |          | -                                |
| Show Incorrect Methods                   |          | -                                |
| Find Outdated Functions                  |          | -                                |
| Show Suspended Methods                   |          | -                                |
| Terminate Suspended Methods              |          | deleteSuspendedMethods [SimTalk] |
| Activate Profiler                        |          | profiler [SimTalk]               |
| Show Profiler Data [button]              |          | -                                |
| Reset Profiler                           |          | resetProfile [SimTalk]           |

You can also select most of these settings on the Debug Menu of an open Method , which only apply to that Method .

<!-- image -->

**Note**

You can click More Commands on the Quick Access Toolbar to add more commands to the Debugger ribbon bar to best meet your needs.

**See also**

Debug Menu of an open Method Tools Ribbon Tab of an open Method Video on YouTube https://youtu.be/FNpiAaUK8iM?si=B13tpTs8uIOxv0wT&amp;t=171

#### Switch to Debugger

Switches to the open window of the Method Debugger . Debug the source code of

<!-- image -->

SimTalk

debug [SimTalk]

See also

Method Debugger

#### Stop on Controls

Stop on Controls

Stops the simulation when a control is called, for example an entrance or an exit control you specified for an object. Plant Simulation shows the called method in the Method Debugger . Plant Simulation only stops when the control itself is called, not when subprograms are called.

<!-- image -->

You can also select Stop On on the Debug Menu of the Method Debugger to the setting Stop on Controls .

<!-- image -->

When you click the Down arrow on the button, Plant Simulation shows the command Stop on Controls in Object .

##### Stop on Controls in Object

Always stops the simulation when a control is started, which is located within the opened or the selected object.

<!-- image -->

When you select an object in the Frame window and then click Stop on Controls in Object , Plant Simulation stops in all Methods , which are located within this object, and opens the Method Debugger . Plant Simulation also stops in user-defined attributes of type method of the object. If the object is a Frame , Plant Simulation also stops in all Methods , which are inserted into the Frame and in sub- Frames as well as in all attribute methods of all objects inserted into the Frame and in sub-Frames .

When you click the Down on the button Debugger &gt; Controls , Plant Simulation shows the path of the currently set object for whose controls Plant Simulation stops.

<!-- image -->

When you click the submenu command again, Plant Simulation unenlists the object, removes the check mark from the submenu command, and the button Debugger &gt; Controls again affects all Methods and attribute methods located within the model.

<!-- image -->

#### Stop on Wakeup

Stops the simulation and opens the Debugger whenever the execution of a suspended method is being continued.

<!-- image -->

Plant Simulation stops the simulation when waking up all suspended Methods that were suspended with waituntil , stopuntil , wait , or sleep(true, false) .

You can also select Stop on Wakeup on the Debug Menu of an open Method , which only applies to that Method .

<!-- image -->

#### Stop on Formulas

Stops the simulation and opens the Debugger whenever a formula is evaluated.

<!-- image -->

You can also select Stop On on the Debug Menu of an open Method , which only applies to that Method .

<!-- image -->

#### Stop on Error Handlers

Stops the simulation and opens the Debugger whenever an error handling method is being executed.

<!-- image -->

You can also select Stop On on the Debug Menu of an open Method , which only applies to that Method .

<!-- image -->

#### Ignore Breakpoints

Ignores a user-defined breakpoint, which you set in the Debugger with the commands Debug &gt; Toggle Class Breakpoint and Toggle Instance Breakpoint .

<!-- image -->

You can also select Ignore Breakpoints on the Debug Menu of an open Method , which only applies to that Method .

<!-- image -->

**SimTalk**

ignoreBreakpoints [SimTalk]

See also

Toggle Class Breakpoint

Toggle Instance Breakpoint

#### Ignore Error Handlers

Does not execute error handling methods if a runtime error in a Method occurs while it is being executed.

<!-- image -->

Instead, Plant Simulation opens the Method Debugger at the position in the source code at which the runtime error occurred.

You can also select Ignore Error Handlers on the Debug Menu of an open Method , which only applies to that Method .

<!-- image -->

#### Ignore Errors

Stops the simulation after an error occurred in the current method. Plant Simulation opens the Debugger with the method containing the error and marks the line containing the error in red.

<!-- image -->

The simulation might continue in case additional events are entered into the events list of the EventController . This way you can continue working, although your model contains methods with faulty code.

The error message contains a description of the problem and the method, the line number of the error and the active call chain.

You can also select Ignore Errors on the Debug Menu of an open Method , which only applies to that Method .

<!-- image -->

SimTalk

setErrorStop [SimTalk]

getErrorStop [SimTalk]

#### Ignore Errors in Formulas

Prevents Plant Simulation from opening the Debugger when a runtime error occurs in a formula.

<!-- image -->

You can also select Ignore Errors in Formulas on the Debug Menu of an open Method , which only applies to that Method .

<!-- image -->

SimTalk

setErrorStop [SimTalk]

getErrorStop [SimTalk]

#### Manage Breakpoints

Opens a dialog in which you can manage all breakpoints of all methods.

<!-- image -->

<!-- image -->

You can deactivate and reactivate the selected breakpoint by selecting or clearing the check box.

You can open the Method Editor and jump to the respective position in the source code by double-clicking the respective line in the dialog.

You can press Del to delete the selected breakpoint.

You can press B or Ctrl+B to open the dialog Breakpoint Settings for the selected breakpoint.

See also

Breakpoint Active [Debug menu]

Breakpoint Settings [Debug menu]

Breakpoint Active [context menu]

Breakpoint Settings [context menu]

#### Delete All Breakpoints [Debugger ribbon]

Deletes all breakpoints in all methods.

<!-- image -->

Hold down Shift while you click Delete All Breakpoints to also delete the breakpoints in the EventDebugger .

You can also select Delete All Breakpoints [Tools ribbon] on an open Method , which only applies to that Method .

SimTalk

clearAllBreakpoints [SimTalk]

#### Delete All Expressions

Deletes all expressions of all methods, which you typed into the Watch Window on the tab Expressions .

<!-- image -->

**Note**

A large number of saved expressions increases the size of the model file and makes loading and saving the model slower. We recommend to only save expressions while you are developing the model and delete them afterward.

See also

Watch Window [described]

Tab Expressions [Watch window]

#### Show Incorrect Methods

Opens a window displaying all methods, including the absolute path, containing errors in their syntax.

<!-- image -->

After loading a model containing syntax errors, this window opens automatically. Double-click an entry to open the dialog of the Method where you can correct the syntax error.

#### Find Outdated Functions

Finds no longer supported methods , attributes , and functions in the source code of all methods. You then have to take the appropriate measures to fix the problem, for example replace the outdated functions with the functions that replaced them.

<!-- image -->

The command Find Outdated Functions only shows those outdated methods, attributes, and functions for which we offer a direct equivalent.

Plant Simulation shows outdated functions in the source code with this color .

**Proceed as follows:**

- Click Find Outdated Functions in your simulation model.
- Plant Simulation shows the outdated functions in the window Outdated Methods, Attributes and Functions . Double-click the name of the outdated function, which you would like to replace, in the window.

<!-- image -->

- Select the function that is going to replace the outdated function in the dialog Find and Replace .

<!-- image -->

If more than one function can replace the outdated function, select the respective radio button.

<!-- image -->

If the outdated function does not have a direct equivalent, the text box Replace With remains empty.

<!-- image -->

Consult Outdated SimTalk Names to see which new function replaced the outdated function.

- Click Replace to only replace this occurrence in the source code of all methods in the model.
- Click Replace All to replace all occurrences in the source code of all methods in the model.
- Plant Simulation replaces the outdated function with the new function.
- Run the simulation and check if the source code still works as intended.

The command also finds observers of outdated attributes , for example observers of the attribute ChannelID . For such observers Plant Simulation opens a window containing a list of all outdated attributes for the observers . When you double-click an entry in the list, Plant Simulation opens the dialog Edit Observers for the observed object, as long as only a single observed object exists. If several observed objects exist, Plant Simulation opens a window with a list of all observed objects. To open the observer window for the respective object, double-click the respective entry in the list.

Remarks

In 3D Only models the command Find Outdated Functions also shows attributes and methods referring to the 2D representation of the model, such as XPos , YPos , CurrIconNo , turnIcon , etc. This makes it easier to prepare you simulation models for Plant Simulation 2606 , which will not support 2D at all.

See also

Replace Outdated Functions in the Source Code

Outdated SimTalk Names

Colors for Syntax Highlighting

#### Show Suspended Methods

Opens the Watch Window that shows all suspended methods on the tab Suspended .

<!-- image -->

<!-- image -->

Double-click the name of the method to open the Debugger with that method.

Suspended Methods are methods that were suspended by a waituntil-statement or a stopuntilstatement , by a wait -instruction or by a sleep -instruction.

See also

Watch Window [described]

Suspending Methods

Maximum Number of Suspended Methods [preferences]

#### Terminate Suspended Methods

Terminates all kinds of suspended Methods , meaning Methods that were suspended by a waituntilstatement or a stopuntil-statement , by a sleep -instruction, or by a wait -instruction.

<!-- image -->

**Note**

The command does not delete the Method object itself, but terminates the suspended state of this Method .

**Note**

The EventController automatically terminates all suspended Methods during the reset phase of the simulation.

SimTalk

waituntil [SimTalk] and stopuntil [SimTalk]

sleep [SimTalk]

wait [SimTalk]

deleteSuspendedMethods [SimTalk]

#### Activate Profiler

Activate Profiler

Activates or deactivates the Profiler , which shows the time the individual methods take to be executed.

<!-- image -->

**Note**

Activating the Profiler makes the simulation run slightly slower.

SimTalk profiler [SimTalk] resetProfile [SimTalk] saveProfile [SimTalk] See also Show Profiler Data [button] Reset Profiler Working with the Profiler

##### Working with the Profiler

To study the structure, dimensioning and control of a simulation model, you execute several simulation runs. Therefore, each simulation run time should take as little time as possible.

The simulation speed of a model depends on the way you design and program your model. Therefore, it is important to program often-called custom control methods as efficiently as possible.

The Profiler helps to detect time-consuming methods and tells how changes in modeling affect run time. During a simulation run, the Profiler records the run-times and the call frequency of methods.

<!-- image -->

- To activate the Profiler , click Activate Profiler on the Debugger ribbon tab. The Profiler then starts to collect data for all methods which are called. Start the simulation or call the method you would like to analyze.
- To analyze the data it collected, click Show Profiler Data [button] after the simulation run is finished.
- To delete all data left from a previous Profiler run, click Reset Profiler .

<!-- image -->

<!-- image -->

See also

Activate Profiler

Show Profiler Data [button]

Reset Profiler

SimTalk

getProfileCallCycles [SimTalk]

profiler [SimTalk]

resetProfile [SimTalk]

saveProfile [SimTalk]

#### Show Profiler Data

Show Profiler Data [button]

Opens the Profiler window, where you can inspect the results of a Profiler run .

<!-- image -->

You can also show the profiler data for the same simulation run several times in separate windows. This way you can compare the data at different times of the simulation run. To do so, click Show Profiler Data again.

<!-- image -->

<!-- image -->

- The line Time of creation displays the weekday, the date, and the time of the simulation run.
- The line Model name displays the path to and the name of the model with which the simulation run was executed.
- The line Total CPU time shows the total CPU time consumed by the process. This is the sum of the 3 values below.
- The line Total CPU time for 3D rendering shows the CPU time for drawing the 3D frames.
- The line Total CPU time for 3D animation shows the time it takes to update the position of the objects before a frame can be rendered.
- The line Total CPU time for simulation shows the CPU time of the core simulation engine which processes the simulation events. As other programs are also executed by your computer simultaneously, the time shown here is less than the time that really elapsed.
- The line Percentage for method execution shows how much of the Total CPU time for simulation is spent in SimTalk methods. Only this time can be reduced by optimizing the source code of your Methods .
- The line Percentage for worker path network computation shows the percentage which accrued for computing the worker path network.
- The table Top 50 Most Relevant Methods shows a global overview over all methods activated during the simulation.
- The table Top 50 Call Cycles lists every instance, including the time consumed for the caller and the methods called.
- The table OPC UA Communication Statistics summarizes all statistics data that Plant Simulation collected for the communication between the OPCUA interface and the OPC server.

##### Show Profiler Data [button]

- The table MQTT Communication Statistics summarizes all statistics data that Plant Simulation collected for the communication between the MQTT broker and Plant Simulation .
- To print the profile , click Print All .
- To save the profile as an HTML file or as a text file, click Save .
- To update the profile with the most up-to-date data from the simulation run, click Refresh .

**SimTalk**

profiler [SimTalk]

resetProfile [SimTalk]

saveProfile [SimTalk]

getProfileCallCycles [SimTalk]

##### Top 50 Most Relevant Methods

The time consumption of the 50 most important methods groups all instances of methods that inherit the same source code. Each row of a group contains information for a single instance. At the end of each group-separated by a blank linePlant Simulation shows the total time consumed by these instances.

| Value    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| % Global | Shows the relation of the time consumed by all instances of the group, to the total time consumed. A large value shows that this method takes up a large part of the simulation time. Check the programming of the method and modify the source code. If you click the % Global value, the % Local value is shown for the instances of the method with the % Global value. Here you can see the percentage spent in the individual instances of a method. |
| % Local  | Shows the relation of the time consumed by a single instance to the relation to the sum of the times of all instances of the group.                                                                                                                                                                                                                                                                                                                       |
| Time [s] | Shows the time consumed by an instance, is displayed in milliseconds.                                                                                                                                                                                                                                                                                                                                                                                     |
| Calls    | Shows the number of calls.                                                                                                                                                                                                                                                                                                                                                                                                                                |
| ms/Call  | Shows the mean execution time for a single run, which is formed by dividing the values in column 3 (seconds) by the values in column 4 (calls), i.e., the absolute time consumption is divided by the number of calls.                                                                                                                                                                                                                                    |
| Method   | Shows the name of the instance or class of the method or the material flow object. To open the window of the respective Method object or of the material flow object, click the link.                                                                                                                                                                                                                                                                     |

**Note**

At first the Profiler only shows the classes. When you click the percentage of the class, it also shows the instances.

##### Top 50 Call Cycles

The top 50 call cycles show which methods call a method as well as which methods are called by the method.

The overview is divided into different sections which are numbered in the first column. Number 1 is the method which consumes the most time.

The first row lists all callers that activated the method ( callers ). The index marks the entry pertaining to the method itself. Then the methods that are called by the method itself ( callees ) are listed.

<!-- image -->

##### OPC UA Communication Statistics

Summarizes all statistics data that Plant Simulation collected for the communication between the OPCUA interface and the OPC server.

| Value                                                | Description                                                                                                                                                                                                                                                                                                                                                                                                                  |
|------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Total number of values retrieved from the OPC server | Shows the added up number of all transmitted values from the OPC server to Plant Simulation . For OPC items, for which you entered a read interval, which is not zero, the OPC server automatically transmits changed values. For OPC items for which you entered zero as Read Interval Plant Simulation queries the value each time when you call getItemValue for the value once, independent if the value changed or not. |
| Total time for retrieving values from the OPC server | Shows the measured CPU time in seconds which Plant Simulation used for retrieving values from the OPC server. The total time is the sum of the time for the automatically transmitted values and the time for retrieving values for which you entered zero as the Read Interval .                                                                                                                                            |
| Total number of called OPC callbacks methods         | Shows the added up number executed OPC callback methods for all OPC items for which you entered a Read Interval which is not zero and which you entered a callback method into the column Simulation Model Attribute .                                                                                                                                                                                                       |
| Average callback latency                             | Shows the average measured delay between Plant Simulation receiving data from the OPC server and actually executing the                                                                                                                                                                                                                                                                                                      |

| Value                                           | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
|-------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                 | respective callback method which you typed into the column Simulation Model Attribute .                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Maximum callback latency                        | Shows the longest measured delay between Plant Simulation receiving data from the OPC server and actually executing the respective callback method which you typed into the column Simulation Model Attribute .                                                                                                                                                                                                                                                                                                                                                                                                        |
| Maximum callback latency timestamp              | Shows the simulation time at which the maximum callback latency occurred.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Total number of values sent to the OPC server   | Shows the added up number of all values that Plant Simulation transmitted to the OPC server. You can reduce this amount by entering a greater Write Interval into the OPC group. Plant Simulation only transmits the value after the Write Interval has expired and only if the value actually did change. If you enter 0 as the Write Interval , the value is going to be transmitted immediately each time. If a value never changes on the Plant-Simulation-side, i.e., if the value only changes on the Server-side and thus only has to be read by Plant Simulation you should enter zero as the Write Interval . |
| Total time for sending values to the OPC server | Shows the measured CPU time in seconds, which Plant Simulation uses for sending values to the OPC server.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Average setItemValue latency                    | If an OPC item group has a Write Interval which is not zero, and when you assign a value to an item of that group using setItemValue , Plant Simulation will not immediately send the value to the OPC server. The average setItemValue latency is the measured average delay between the first assignment to any item of that group and the point in time when Plant Simulation will actually send the changed values of that group to the OPC server.                                                                                                                                                                |
| Maximum setItemValue latency                    | If an OPC item group has a Write Interval which is not zero, and when you assign a value to an item of that group using setItemValue , Plant Simulation will not immediately send the value to the OPC server. The maximum setItemValue latency is the maximum measured delay between the first assignment to any item of that group and the point in time when Plant Simulation will actually send the changed values of that group to the OPC server.                                                                                                                                                                |
| Maximum setItemValue latency timestamp          | Shows the simulation time at which the maximum setItemValue latency occurred.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |

The setItemValue latencies are also shown in tooltips .

**See also**

OPCUA

##### MQTT Communication Statistics

Summarizes all statistics data that Plant Simulation collected for the communication between the MQTT broker and Plant Simulation .

If no data are sent or received, the Profiler does not show these data.

| Value                                                 | Description                                                                                         |
|-------------------------------------------------------|-----------------------------------------------------------------------------------------------------|
| Total number of calls of the MQTT callback methods    | Shows the added up number of all calls of the Callback Method [MQTT] of all MQTT objects.           |
| Average callback latency                              | Shows the average latency from the arrival of received data until the call of the callback method . |
| Maximum callback latency                              | Shows the maximum latency from the arrival of received data until the call of the callback method . |
| Average size of payload received from the MQTT broker | Shows the average size of the payload received from the MQTT broker.                                |
| Maximum size of payload received from the MQTT broker | Shows the maximum size of the payload received from the MQTT broker.                                |
| Total number of calls of the MQTT publish method      | Shows the added up number of all calls of the publish [SimTalk] method of all MQTT objects.         |
| Average publish duration                              | Shows the average number of calls of the publish method for sending data.                           |
| Maximum publish duration                              | Shows the maximum number of calls of the publish method for sending data.                           |

| Value                                           | Description                                                             |
|-------------------------------------------------|-------------------------------------------------------------------------|
| Average size of payload sent to the MQTT broker | Shows the average size of the payload sent to the MQTT broker in bytes. |
| Maximum size of payload sent to the MQTT broker | Shows the maximum size of the payload sent to the MQTT broker in bytes. |

See also

MQTT

#### Reset Profiler

Resets the Profiler and deletes all data which the Profiler collected. Plant Simulation does not automatically delete existing data when you activate or deactivate the Profiler .

<!-- image -->

**Window Ribbon Tab**

