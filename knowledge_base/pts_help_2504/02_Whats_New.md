# 2. What's New

## What's New

What's New describes the new features of the current and the previous two versions of Plant Simulation .

Below you find:

- What's New in Plant Simulation 2504
- What's New in Plant Simulation 2404
- What's New in Plant Simulation 2302

**Also consult**

The Components of the Program Window

Introducing Plant Simulation

Update Arbitrary Old Models

The Step-by-Step Help

The Objects Reference Help

The SimTalk Reference

Outdated SimTalk Names

The 3D Help

SimTalk Access to 3D

The Quick Reference Cards

The Add-Ins Reference Help

The Libraries Reference

**What's New in Plant Simulation 2504**

## What's New in Plant Simulation 2504

Plant Simulation 2504 provides a number of new and improved features.

- Important Announcement for Plant Simulation 2606
- New Features of the Material Flow Objects
- Changed Features of the Material Flow Objects
- New and Changed Features of the Fluid Objects
- New and Changed Features of the Resource Objects
- New and Changed Features of the Information Flow Objects
- New and Changed Features of the User Interface Objects
- New 3D Features
- Changed 3D Features
- New and Changed SimTalk Features
- Miscellaneous

Back to What's New

### Important Announcement for Plant Simulation 2606

We will terminate support for the 2D visualization of the animation in PlantSimulation 2606 to be published in June 2026.

This means that any 2D Only or 2D and 3D model you open in Plant Simulation 2606 will automatically be converted to a 3D model.

Any SimTalk methods and attributes that only apply to 2D will open the Method Debugger . You will then have to adapt your simulation model accordingly.

This applies to the Methods for Animating Objects in 2D , to the Attribute for Animating Objects in 2D , to the settings of the tab 2D in the Preferences and the Model Settings , the Display Panel , etc.

Back to What's New in Plant Simulation 2504

### New Features of the Material Flow Objects

The material flow objects provide a number of new features.

- We added sequential assembly mode to the AssemblyStation .
- We added the command Exit Blocking List [Store] to the Store . It shows the parts waiting to be carried away by a Worker . This also affects the method exitBlockList [SimTalk] - Store .
- We added the read-only attribute IsInterrupted [SimTalk] to all objects that support interruptions (pauses or failures).
- We added the settings Multiple Gap and Multiple Pitch to the setting MU Distance Type of the Conveyor .
- We added the method fi ndFreePlaceInRange [SimTalk] to the Store .
- We added the method removeFromBlocklists [SimTalk] to the MUs .
- We added the check box Stop at Destination and the attribute StopAtDestination [SimTalk] to the Transporter .
- We added the method rotateTowards [SimTalk] - Transporter to the Transporter .
- We added the method changeDrivingDirection [SimTalk] to the Transporter .
- We added the attribute MU [SimTalk] - importer to the Importer types Imp , SetupImp , FailImp , and TransportImp . Use it to query for which MU a resource was ordered.
- We added the argument exporters to the Receive Control [processing importer] of all Importers We still support the previous argument Exporters table of data type table .

Back to What's New in Plant Simulation 2504

- .

### Changed Features of the Material Flow Objects

The material flow objects provide a number changed features.

- We enhanced the behavior of the attribute CurveSpeed [SimTalk] . It now also supports Transporters driving on Tracks , in addition to Transporters driving freely within the area of the model.
- We changed the name of the attribute AssemblyList to AssemblyTable [SimTalk] and the attribute PartTableMode of the AssemblyStation to AssemblyTableMode [SimTalk] as they use a table, not a list. (English version only)
- We changed the behavior of the setting Assembly Table &gt; Predecessors of the AssemblyStation . You can now also add the number of the main part as the Predecessor to the Assembly Table to use parts of the main part number as mounting parts.
- We changed the behavior of the Assembly Table of the AssemblyStation . You can no longer change the Assembly Table if the main part is already located on the AssemblyStation . To change the Assembly Table in the Entrance Control of the Station , you now have to select the check box Before Actions of the Entrance Control .
- We changed the title of the column named Number of the Assembly Table to Amount . (English version only)
- We changed the behavior of the attributes EntranceFree [SimTalk] and ExitFree [SimTalk] . They now only return true if the object is not failed, not paused, not unplanned, and not stopped.
- We changed the behavior of the Exit Control of the ParallelStation . If you activated Exit Control Once and the parts are to be carried away, the Exit Control for the waiting parts will now not be called a second time if the Worker carries a part away.
- We changed the Supermarket Configuration [button] of the Store . The Initial Value can now also be smaller than the Minimum Value . In this case the order is triggered on Init .
- We changed the behavior of the method getExporters [SimTalk] of the Importer . The argument Exporters:table is now optional. If you do not pass the argument, getExporters returns an array containing all Exporters .
- We changed the behavior of objects which can set-up for parts and which have the attribute SetupForType [SimTalk] . Setting the attribute SetupAttrName to a non-empty string will set the attribute SetupForType to true.
- We renamed the attribute End of the EventController to EndTime [SimTalk] - EventController as end is a SimTalk keyword . (English version only)
- We renamed the attribute Date of the EventController to StartDate [SimTalk] - EventController as date is a SimTalk keyword . (English version only)
- We changed the behavior of the attribute IsIdle [SimTalk] - Transporter of the Transporter . Newly created Transporters now always have the state IsIdle=true .
- We changed the behavior of the attribute DestinationWasReached [SimTalk] of the MUs . We now also set it to true, when a MU arrives at a sensor for which the Destination matches the Destination of the MU .

**Back to What's New in Plant Simulation 2504**

### New and Changed Features of the Fluid Objects

The fl uid objects provide a number of new and changed features.

- We added the object ContinuousMixer to the fl uid objects .

Back to What's New in Plant Simulation 2504

### New and Changed Features of the Resource Objects

The resource objects provide a number of new and changed features.

- We added the setting Pick/Drop at Store to the Workplace .
- We changed the behavior of the Workplace . You can no longer close its entrance or exit via SimTalk with the attributes EntranceLocked or ExitLocked .
- We enhanced the behavior of the Worker . He now shows additional states by their respective colors, see Orientation [state graphic] .
- We added the attribute IsIdle [SimTalk] - Worker to the Worker .
- We added the attribute HasOrder [SimTalk] - Worker to the Worker .
- We added the methods cancelTransportPart [SimTalk] and transportPart [SimTalk] to the Worker .
- We changed the behavior of the methods goTo , goToHome , and goToPool of the Worker . If the Worker is interrupted, but must teleport to reach the intended destination, the Worker does not

accept the order and the method returns false.

- We added the method getRouteLength [SimTalk] - Marker to the Marker .
- We added the read-only attribute NumIdleWorkers [SimTalk] and the method getIdleWorker [SimTalk] to the WorkerPool .
- We changed the behavior of Drag-and-Drop for the WorkerPool . You can now drag any object onto the WorkerPool to use it as the Parts Buffer [text box] .
- We added a column each for the State , the Capacity , and the Free Capacity to the Exporters [Broker] table of the Broker if the Exporter is a Worker .

We added a column for the Capacity and the Free Capacity to the Offered Services [Broker] table of the Broker .

Back to What's New in Plant Simulation 2504

### New and Changed Features of the Information Flow Objects

The information flow objects provide a number of new and changed features.

- We added the command Show Object [context menu, DataTable] to the context menu of the DataTable . It shows the object in the Frame if the column has the data type object .
- We changed the behavior of the methods appendRow [SimTalk] and insertRow [SimTalk] of the DataTable . They no longer allow you to add a row if the maximum number of rows has already been reached.
- We changed the behavior of the method appendRow [SimTalk] . It now returns the index of the added row.
- We changed the format of the DataTable which the method putAttributeNamesIntoTable [SimTalk] objects returns.

The column named Signature of the parameter Table now contains the complete signature of a built-in Method , instead of only the parameters.

The new column named Side Effect contains a boolean value, which designates if read access has a side effect or only returns a value.

- We added the check box Default to the settings Background Color [cells] and Font Color [cells] . The setting is activated by default, meaning that these colors are the default colors according to the setting &gt; Theming you selected.
- We added the setting Client ID to the tab Security of the MQTT Interface.
- We added the attribute QoS [SimTalk] to the MQTT Interface.
- We added the attribute ReadInterval [SimTalk] to the MQTT Interface.
- We added the method dropTable [SimTalk] to the SQLite Interface.
- We added the read-only attribute hasSyntaxError [SimTalk] to the Method and to the user-defined attributes of type method .
- We added the read-only attribute NumInExecution [SimTalk] to the Method .
- We added the methods callMethod [SimTalk] and callMethodKw [SimTalk] to the PythonModule .
- We added the methods get [SimTalk] and set [SimTalk] to the PythonModule . They replace the methods getValue and setValue .
- We added the read-only attribute ModuleName [SimTalk] to the PythonModule .
- We added the method importPythonModule [SimTalk] to the Plant Simulation Module of the Python Interface .
- We changed the behavior, when you set an object of type OPCUA , SIMIT , or PLCSIM\_Advanced to Active and thus establish a connection to an OPC-UA-Server , to SIMIT or to PLCSIM Advanced .

In previous versions Plant Simulation automatically set the Real-time factor of the EventController to 1 and cleared the setting Skip Long Event Intervals . This is no longer the case. When you select the check box Active for these objects, Plant Simulation now asks if it should set the Real-time factor of the EventController to 1 and clear the setting Skip Long Event Intervals . To prevent this question in the future, select Never ask again in the message dialog. Then Plant Simulation will only inquire again, when you delete the registry key HKEY\_CURRENT\_USER\Software\Siemens\Tecnomatix Plant Simulation 2504\Preferences\VCRealTime1 .

- We removed support for Active Workspace of the Teamcenter Interface .

Back to What's New in Plant Simulation 2504

### New and Changed Features of the User Interface Objects

The user interface objects provide a number of new and changed features.

- We added the setting Worker Pools to the setting Data Source [Chart] of the Chart . In previous versions you only could drag the WorkerPools over the icon of the Chart and drop it there to
- show a WorkerChart . The setting Worker Pools provides more configuration options.
- We improved the behavior of the Comment . If you only entered Text on the Tab Display and nothing on the Tab Comment , Plant Simulation shows the Tab Display when you open the dialog of the Comment the next time.
- We enhanced the behavior of the HtmlReport . We added more objects for which you can specify named arguments, compare Add a Reference to an Object on the HTML Page .
- We changed the behavior of the object Dialog . When you save a simulation model, in which a userdefined Dialog is open and close this model, Plant Simulation automatically opens this Dialog when you open the model the next time.
- We changed the behavior of user-defined annotations of the Chart , see Annotations [button] . Plant Simulation now always shows them in the foreground.

Back to What's New in Plant Simulation 2504

### New 3D Features

Plant Simulation 3D provides a number of new features.

- We added additional interactive 3D user commands you can undo and redo with the commands Undo [3D] and Redo [3D] : Changing 3D view options, creating and deleting of graphics, graphic groups, animatable objects and sensors, grouping and ungrouping of graphics, changing of graphic inheritance, and removing textures.
- We added additional actions/commands you can undo with the command Undo [3D] .

You can now undo and redo all undoable 3D interactions while the simulation was pause. Only when you start a new simulation or continue an existing simulation, Plant Simulation discards all remembered undoable 3D commands and prevents remembering new undoable 3D commands until you stop the simulation again.

You can now also undo and redo undoable 3D commands after editing a simulation setting if an object in the simulation settings dialog. Exceptions are simulation settings, which affect the size or capacity of an object ( Length , Width , Height , X/Y/Z-Dimension , Booking Point ) and Use Rotation of Marker . Changing these simulation settings in addition discards all remembered undoable 3D commands.

- We added the method \_3D.Poses.moveToMU [SimTalk] to poses objects to start a movement toward a MU instance.
- We added the method moveToMU [SimTalk] to animatable objects to start a movement toward a MU instance.
- We added the method \_3D.Poses.moveToMUAnimationPosition [SimTalk] to poses. The method starts a movement toward a position at which a MU instance can be placed onto another place.
- We added the method moveToMUAnimationPosition [SimTalk] to joints. The method moves the joint to the place where the specified MU instance would be located when being moved to the specified place.
- We added the method createPolyLine [SimTalk] to create a polyline in your simulation model.
- We added the setting Smooth Rotation and the method \_3D.AniSmoothRotation [SimTalk] to the length-oriented objects, ensuring a smooth rotation of the MUs located on them.
- We added the method \_3D.JointUseShortestRotationDirection [SimTalk] to animatable objects allowing you to make joints of type Revolute Joint always take the shortest distance in space instead of the numerically shortest distance via the angle difference if they are moved with one of the moveTo methods.
- We added the command Stop at Next Event to the Context Menu of the Selected Simulation Object .
- We added the optional parameter Factor to the methods \_3D.CameraAnimations.&lt;AnimationPathName&gt;.play [SimTalk] and \_3D.CameraAnimations.&lt;AnimationPathName&gt;.schedule [SimTalk] .
- We enhanced the behavior when setting anchor points for animation paths, including robot animation paths. You can force horizontal or vertical segments in the object coordinate system by pressing Shift .

Back to What's New in Plant Simulation 2504

### Changed 3D Features

Plant Simulation 3D provides a number of changed features.

- We changed the behavior when assigning a material property to a 3D object. When assigning a value to one of the material properties, we now automatically set the material to active ( MaterialActive := true ).

This applies, for example, to the following and additional attributes:

- MaterialAmbientColor [SimTalk] , MaterialDiffuseColor [SimTalk] , MaterialEmissiveColor [SimTalk] , MaterialShininess [SimTalk] , MaterialSpecularColor [SimTalk] , and MaterialTransparency [SimTalk] .
- \_3D.MaterialAmbientColor [SimTalk] , \_3D.MaterialDiffuseColor [SimTalk] , \_3D.MaterialEmissiveColor [SimTalk] , \_3D.MaterialShininess [SimTalk] , \_3D.MaterialSpecularColor [SimTalk] , and \_3D.MaterialTransparency [SimTalk] .

Thus the method \_3D.activateMaterialWithColor is no longer required and no longer supported.

- \_3D.StorageAreaMaterialAmbientColor [SimTalk] , \_3D.StorageAreaMaterialDiffuseColor [SimTalk] , \_3D.StorageAreaMaterialEmissiveColor [SimTalk] , \_3D.StorageAreaMaterialShininess [SimTalk] , \_3D.StorageAreaMaterialSpecularColor [SimTalk] , and \_3D.StorageAreaMaterialTransparency [SimTalk] .
- We changed the layout of the dialogs Start Simple Recording and Start Simulation Recording . We added the setting UHD 4K to resize the window to be recorded to 3840x2160 pixels, see Resize For .
- We changed the behavior when you hold down Shift while defining the segments of a length-oriented object or an animation polycurve. Plant Simulation no longer fixes the absolute tangential angle to a multiple of 90°, but the relative tangential angle.
- We changed the behavior of the commands that show something, for example, the command Show in the dialog Show Structure [class library] , Show in the dialog Show Inheritance [Home ribbon] , Show Sender , Show Receiver in the EventDebugger , etc.:

When you hold down Shift and select one of these commands, Plant Simulation now zooms so close as if you selected the object or the graphic and selected the command Zoom to Objects [context menu] .

- We changed the behavior of the command Find Outdated Functions . In 3D Only models the command Find Outdated Functions now also shows attributes and methods referring to the 2D representation of the model, such as XPos , YPos , CurrIconNo , turnIcon , etc. This makes it easier to prepare you simulation models for Plant Simulation 2606 , which will not support 2D
- at all.
- We removed the command Video Settings . We now only provide a single built-in video codec.

Back to What's New in Plant Simulation 2504

### New and Changed SimTalk Features

SimTalk provides a number of new and changed features.

- We changed the random number seed values for user-defined attributes of data type Method and RandTime .

Until now each user-defined attribute had its own random number seed value. Now Plant Simulation keeps a common seed value in the object. As of now Plant Simulation automatically assigns the random number value when inserting an object, but only if the object can create random numbers. This is then the case when the object itself can create random numbers, for example a station for its processing time, or when the object has a user-defined attribute of data type Method or RandTime . If both is not the case, Plant Simulation assigns the value 0 to the attribute RandomSeed when inserting the object. If the value of the attribute RandomSeed is 0, the attribute will not be shown in the window Show Attributes and Methods and will not be written to the folder model. When you create a user-defined attribute of data type Method and RandTime for such an object, Plant Simulation sets a random number value automatically as well.

- We added the methods readFile [SimTalk] - JSON and writeFile [SimTalk] - JSON to the data type JSON.
- We enhanced the behavior of SimTalk 2.0 . You can now also assign JSON Literals .
- We added functionality to reference an object of type Python with the SimTalk data type Any [SimTalk] - data type . In previous versions, the method PythonModule.getValue converted Python data types to SimTalk data types where possible. If this was not possible, the Python value was converted to a string . Now Plant Simulation returns the Python object as a value of data type any .

The Python data type list was converted to a SimTalk array in previous versions. Now Plant Simulation returns the Python list object as a value of data type any . This prevents Plant Simulation from unnecessarily allocating memory when using large lists.

- We added the exponentiation operator ** to the Basic Mathematical Functions in SimTalk 2.0 . Instead of pow(x, y) you can now also use x ** y .
- We added the parameter TotalSize to the method setXYWH [SimTalk] .
- We changed the behavior of the method hasAttribute [SimTalk] - 2D . It now returns false for the parameter Imp , SetupImp , and FailImp if this attribute does not exist for the specified object.
- We changed the behavior of the global function isArray [SimTalk] . It now returns true for JSON arrays.
- We changed the behavior of print [SimTalk] - output function and the function to\_str [SimTalk] . Strings within arrays are now enclosed in quotation marks.
- We added Microsoft Edge WebView2 support for displaying HTML content.

```simtalk
var a : string["Kent, Clark", ""]
var s : string := to_str(a)  -- now assigns ["Kent, Clark", ""] -- assigned [Kent, Clark, ] in previous versions
```

**New and Changed SimTalk Features**

Microsoft Edge WebView2 can display documents in pdf (Portable Document Format) format. You can show pdf documents directly in Plant Simulation with the function openHTMLWindow [SimTalk] .

This only works if Microsoft Edge WebView2 Runtime is installed on your computer.

Back to What's New in Plant Simulation 2504

### Miscellaneous

Plant Simulation 2504 provides a number of new and changed features covering various topics.

- We adapted the Look and Feel of Plant Simulation 2504 to the Siemens Digital Industries Software standards. We adjusted the color scheme and show static text boxes with title case capitalization instead of sentence-style capitalization.
- We added the command Show Copilot . The Copilot is an intelligent assistant designed to help you to quickly find the information you need within the Plant Simulation Help .
- We added the Omniverse Connector . The Omniverse Connector is a powerful add-on application that helps you transfer your geometries and simulation studies from Plant Simulation X into NVIDIA Omniverse to realize an industrial metaverse visualization, simulation, and collaboration experience.
- We added a link from a help topic to a video on YouTube, if we demonstrate that feature in the video.

<!-- image -->

<!-- image -->

Note that we use the YouTube URL shortener in our links to the videos, for example https://youtu.be/ PgT4wkT2Xj8?si=Udlvoq8KcAI9GxQw&amp;t=18 .

- We added the setting Background Color [3D] to Preferences &gt; 3D .
- We added the setting Theming to Preferences &gt; User Interface .
- We added the setting Use Tab Page Icons in Object Dialogs to Preferences &gt; User Interface .
- We enhanced the behavior when saving a folder model . When you click Save Model File to save the loaded folder model, Plant Simulation checks if a method named OnSaveFolderModel exists at the Basis of the Class Library . If this is the case, Plant Simulation calls this method and does not save the folder model automatically. You can save the folder model by calling SaveFolderModel within the method OnSaveFolderModel .

You can, for example, use OnSaveFolderModel to bring the folder model to a state in which it is to be saved to a Source Code Control System.

- We enhanced the use of the dialog Show Attributes and Methods [described] . You can now select several objects at the same time and press F8 to open a single dialog, which shows the attributes which the selected objects share. You can change any of the shared attributes for all of the selected objects.

- We enhanced the behavior of the command Incremental Search . It now also finds Workers , which are located on Workplaces , FootPaths , and are on their way to the WorkerPool . It does not find Workers located in the WorkerPool though.

In general, Incremental Search finds objects by their name. For Workers Incremental Search also includes the name of the class and the counter of the instance . For Worker:1 Incremental Search finds the first instance of the class named Worker for example.

- We changed how objects are shown in the Toolbox . We no longer use the first icon of the object, but internal graphics. To show an icon of your own, create an icon and name it ToolboxIcon .
- We renamed the command Find a Command to Search Commands and moved it to the right at the top of the Plant Simulation window.

Back to What's New in Plant Simulation 2504

### What's New in Plant Simulation 2404

### What's New in Plant Simulation 2404

Plant Simulation 2404 provides a number of new and improved features.

- Simulation-Relevant Changes
- New Features of the Material Flow Objects
- Changed Features of the Material Flow Objects
- New and Changed Features of the Fluid Objects
- New and Changed Features of the Resource Objects
- New and Changed Features of the Information Flow Objects
- New and Changed Features of the User Interface Objects
- New 3D Features
- Changed 3D Features
- New and Changed SimTalk Features
- Miscellany
- New and Changed Features of the Value Stream Mapping Library

Back to What's New

### Simulation-Relevant Changes

We made simulation-relevant changes in Plant Simulation 2404. For this reason, you have to adapt simulation models, which you created in previous versions of Plant Simulation , when you open them in Plant Simulation 2404.

- We changed how Plant Simulation resolves relative paths of a user-defined attribute of data type table with columns of data type object of a MU . In previous versions, Plant Simulation resolved the path according to the location of the MU . From this version on, it resolves it according to the Frame in which the MU is located.
- We changed the behavior of the Cycle time .
- The Cycle time now starts anew at the start of a shift.
- If you defined the Cycle time with a distribution, Plant Simulation now rolls the dice each time after the Cycle time elapsed. In previous versions, the dice was only rolled once at the start of the simulation.
- We changed the behavior of an AGV which uses a default curve radius of 0 .

If you enter 0 , the AGV decelerates to 0, rotates on the spot with the specified rotation speed , and then accelerates again.

**Note**

In previous versions, the AGV did not use the rotation speed when rotating on the spot with a default curve radius of 0.

To use the behavior of previous versions, enter -1 as the rotation speed for the respective AGVs .

Back to What's New in Plant Simulation 2404

### New Features of the Material Flow Objects

The material flow objects in Plant Simulation provide a number of new features.

- We enhanced the behavior of the TwoLaneTrack . You can now specify the route weighting attribute for lane A and lane B separately. To do so, create two user-defined attributes of data type real in the TwoLaneTrack . Then give them the name of the route weighting attribute followed by \_A or \_B respectively.

Plant Simulation only considers the route weighting attributes if no common route weighting attribute exists that applies for both lanes.

- We added the statistics value Entrance blocked to the tab Statistics of the material flow objects. We also added the read-only attributes StatEntranceBlockedPortion and StatEntranceBlockedTime .
- We added the option Wait for free target and the attribute WaitForFreeTarget to the PickAndPlace robot .

- We added the option Workers sequentially deliver MUs to assemble and the attribute SequentialDelivery to the AssemblyStation .
- We added a feature to the AssemblyStation allowing you to add mounting parts to the main part until the capacity of the main part is reached.
- We added the option Fill-up Main MU to the Assembly table of the AssemblyStation . For this setting, the AssemblyStation accepts parts from any of its predecessors until the capacity of the main MU is reached.
- We enhanced the behavior of the Assembly table . Enter -1 as the Number to make the AssemblyStation accept parts from this predecessor/MU Name until the capacity of the main MU is reached.
- We added the attribute EnforceProcessing to the objects Station , ParallelStation , AssemblyStation , and DismantleStation .

You might use EnforceProcessing to make a station work for statistics purposes, although no part is being processed. You might, for example, use it to make a rotation or opening or closing of a door count as Working .

- We added the method calculateAngles to the PickAndPlace robot and calculateAngles to the Turntable .
- We added the method setRouteFromCoordinates to the Transporter . You can either specify several coordinates or you can specify a single coordinate to which the Transporter drives.
- We added the method restartCycle to the objects which provide the Cycle time .

Back to What's New in Plant Simulation 2404

### Changed Features of the Material Flow Objects

The material flow objects in Plant Simulation provide a number of changed features.

- We enhanced the behavior of the failure profiles . When you activate the check box Availability of a failure profile , you can now also select another distribution than the standard Erlang -distribution. For any other of the available distributions, you have to enter the parameters that this distribution requires. Plant Simulation will then enter the resulting value for the MTTR .
- We enhanced the behavior when you select Absolute path in the dialog Select Object for a userdefined attribute of data type Method . Plant Simulation no longer inserts a leading asterisk in front of the user-defined attribute of data type Method .
- We changed what the attribute ReservedFor of the AssemblyStation returns.
- If you select the check box Workers sequentially deliver MUs to assemble , ReservedFor returns the object for which the place is currently reserved.
- If you clear the check box, ReservedFor returns an array of objects for which places are reserved.
- We changed when the Receive Control of the Importer is being scheduled. It now is called after the Entrance Control of the Workplace and after the Order Control of the Worker / Exporter .

- We changed the behavior of the PickAndPlace robot . When it calls its Target Control after placing the part, the active element ( @ ) now is void instead of containing the part that was just placed.
- We changed the behavior of the Cycle Time .
- The Cycle Time now starts anew at the start of a shift.
- If you defined the Cycle Time with a distribution, Plant Simulation now rolls the dice each time after the Cycle time elapsed. In previous versions, the dice was only rolled once at the start of the simulation.
- We enhanced the functionality of the methods mu of the Store and mu of the MUs . You can now specify a negative number for the parameter Number . The method then references the n-th MU from the bottom of the stack instead of from the top.
- We enhanced the behavior of the Transporter . To make the AGV rotate on the spot with the Rotation Speed you set, enter 0 as the Default Curve Radius . Thus, time passes for the rotation on the spot as the AGV has to reduce its speed to 0 before rotating and, if applicable, decelerate, and then accelerate again.

**Note**

The behavior of AGVs that use the Default Curve Radius of 0 changes because of this change of behavior.

To use the behavior of previous versions, enter -1 as the Rotation Speed for the respective AGVs .

- We changed the behavior of the Converter when you select the Strategy &gt; Method and when a MU with activated automatic routing enters the Converter . In previous versions, the Strategy Method was called. This is no longer the case. From this version on, the MU automatically follows the computed route.
- We changed the behavior of the method DefaultCurveRadius [SimTalk] of the Transporter . We now prohibit changing the DefaultCurveRadius if the Transporter is already driving on a route.

Back to What's New in Plant Simulation 2404

### New and Changed Features of the Fluid Objects

The fl uid objects in Plant Simulation provide a number of new and changed features.

- We added settings for the Exit strategy of the Pipe . We added the attribute ExitStrategy for setting the exit strategy as such. We added the attribute ExitStrategyPercentageValues for setting the percentages for the exit strategy

Percentage .

Back to What's New in Plant Simulation 2404

### New and Changed Features of the Resource Objects

The resource objects in Plant Simulation provide a number of new and changed features.

- We added a feature for queueing Workers in front of a Workplace which is occupied. We only show the queue in 3D . You can set the Distance in queue , Walk to the end of the animation path of the queue , and Walk along the animation path of the queue in the Workplace . These features set How Workers Queue Up in Front of the Workplace .
- We added the method getRouteCoordinates to the Workplace .
- We added features for defining the Home location and the Scope of the Worker . We added the attributes HomeLocation and Scope to the Worker .
- We added features for defining the Home location and the Scope of the Worker to the Workers to Create table of the WorkerPool .

As the format of the table changed, we also renamed the Creation Table to Workers to Create table.

- We added the methods goTo , goToHome , and goToPool to the Worker . They send the Worker to the specified destination.
- We added the methods teleportTo , teleportToHome , and teleportToPool to the Worker . They teleport the Worker to the specified destination.
- We replaced the method creationTable of the WorkerPool with the method getWorkersToCreateTableRow .

We replaced the method setCreationTable of the WorkerPool with the method setWorkersToCreateTable .

We replaced the method getCreationTable of the WorkerPool with the method getWorkersToCreateTable .

We renamed the method GetJobOrdersInPoolOnly to GetJobOrdersAtHomeOnly .

We renamed the check box Get job orders in the pool only to Get job orders at home only .

- We added the Load control and the Unload control to the Workplace .
- We enhanced the behavior of the Workplace . You can define a Recovery time for a Workplace that has a Capacity of 1 . It starts once a Worker leaves the Workplace .
- We changed the return value of the method getRouteLength of the Worker and of the method getRouteLength of the Workplace .

If Plant Simulation did not find a route, it returns -1 .

- We changed the behavior of the Broker . An Importer , who is interrupted because another station with a higher priority requires the resource, is now sorted at the first place in the list of the Open Importers of the respective Broker .
- We renamed the Tab Controls of the Broker to Tab Attributes . We added the option Choose the nearest worker and the attribute ChooseNearestWorker .

**Back to What's New in Plant Simulation 2404**

### New and Changed Features of the Information Flow Objects

The information flow objects in Plant Simulation provide a number of new and changed features.

- We added the PythonModule for executing Python code in Plant Simulation .
- We added the Tab Security to the OPCUA Interface , moved dialog items from the Tab Attributes to it, and added the settings Security mode and Security policy .
- We also added the commands Edit Ignored Items and Clear Ignored Items to the View Menu .
- We enhanced the display and usability of the Variable . It now provides a type graphic allowing you to directly open the window of a Variable of data type list , queue , stack , or table . We added the settings Background color , Alignment , and Integer places .
- We added the control structure for-downto-next to the drop-down list on the Edit ribbon tab &gt; Insert Control Structure of the Method .
- We added the command Insert Control Structure to the context menu of the Method Editor .
- We added the command Ignore Error Handlers to the Debug Menu of the Method . We added the command Ignore Error Handlers to the Debugger Ribbon Tab .
- We added the function getProfileCallCycles to the Profiler .
- We added the methods copyFilteredTableTo , fi ndFirst , getColumnUniqueValues , and mergeTable to the DataTable .
- We added the methods getAttribute , inheritAttribute , and setAttribute to the user-defined attributes . They replace the attributes InheritValue , InheritInitValue , and InheritHasInitValue , which we no longer
- support.
- We added the method createTable to the SQL Interface .
- We added tooltips to the icons of the breakpoints in the Method Editor .
- We changed the behavior when copying and pasting a Method object. Plant Simulation now also copies class breakpoints .
- We changed the behavior when deleting suspended Methods with the command Terminate Suspended Methods . Plant Simulation now deletes all kinds of suspended Methods , meaning Methods that were suspended via a waituntil-statement , a stopuntil-statement , a sleep-instruction , or a wait-instruction .

A Method that is suspended by a waituntil-statement or by a stopuntil-statement , by a wait -instruction, or by a sleep -instruction, shows a tooltip in the Frame window .

<!-- image -->

- We enhanced the behavior of the wait instruction . You can now suspend a Method class , meaning a Method that is located in a folder in the Class Library , with a wait instruction if the Method class was called by a Method that is located in a model containing an EventController .
- We changed the functionality of the method openDialogBox of the DataTable . It no longer shows the font size and font color , which you selected in the dialog Format , but a uniform standard font.
- We removed the Import Items button from the Tab Attributes of the OPCClassic Interface as it did not work reliably.
- We recommend using the OPCUA Interface instead of the outdated OPCClassic Interface .
- We renamed the attribute Active of the AttributeExplorer to IsShown .
- We changed the name of the standard Callback method of the MQTT Interface from CallbackMethod to Callback .
- We changed the behavior when you activate the MQTT Interface . We no longer change the simulation speed of the EventController to 1:1 real time .

Back to What's New in Plant Simulation 2404

### New and Changed Features of the User Interface Objects

The user interface objects in Plant Simulation provide a number of new and changed features.

- We added the attribute IsShown to the HtmlReport .
- We enhanced the behavior of the HtmlReport . In previous versions, you could only specify arguments in an anonymous way. The meaning of the

argument resulted from the context, for example [current.\_3D, %planningview, *, *] , with the arguments separated by commas.

For the objects Checkbox , Display , Frame , Picture of a 3D Scene , PythonModule , Sankey Diagram , and Variable you can now specify arguments via names. You can pass the arguments in any order. Separate the arguments with white spaces, for example [current.\_3D PlanningView=true] .

You can now also Display a PythonModule in the HtmlReport .

- We added the methods getInheritanceBox and setInheritanceBox to the Dialog .
- We enhanced the functionality of the WorkerPool . You can now drag it to the Chart and drop it there to emulate most of the functions that the WorkerChart library provided in previous versions. Be aware that the functionalities are not 100% identical; the WorkerChart had features that the new built-in features do not have and vice versa.
- We renamed the attribute Active of the objects Chart , GanttChart , and SankeyDiagram to IsShown .

Back to What's New in Plant Simulation 2404

### New 3D Features

Plant Simulation 3D provides a number of new features.

- We added the commands Undo and Redo to 3D to undo or redo transformations and a number of other settings which you manually changed in the 3D window.
- We added settings for showing user-defined attributes in a 3D Only model in the outside representation of the object to which they belong. We added the Tab Transformation and the Tab Display to the Tab User-defined in a 3D Only model . We added type graphics to user-defined attributes of data type list , queue , stack , and table allowing

you to directly open the window of the respective list object.

- We enhanced the display and the usability of the Variable in a 3D Only model . It now provides a type graphic allowing you to directly open the window of a Variable of data type list ,

queue , stack , or table .

- We added the Tab Appearance to a number of objects.
- We added the command Show User-defined Attributes to the View ribbon tab.
- We added the command Create User-defined Attribute to the context menu of the background of the 3D window of a simulation object.
- We added the option Synchronized joints to the Tab Poses . It synchronizes the joints so that all joints, that are part of the pose movement , reach the target state at the same time while moving toward a pose.
- We added the option Movement interruptible to the Tab Poses . It sets if failures and pauses will interrupt pose runs of the object or not.
- We added the read-only attribute \_3D.Poses.EndPoseWasReached and the attribute \_3D.MovementInterruptible to poses.

We added the method \_3D.Poses.stopMovement which stops the movement toward the designated pose of the object and, if you entered a deceleration for the joints, decelerates the pose movement toward a halt.

- We enhanced the behavior of Plant Simulation . Once all pose runs of an object reached their destination, Plant Simulation enters an EndOfTime event into the list of scheduled events .
- We added settings for showing the fi ll level of the Buffer in 3D. This matches the respective feature in 2D.
- We added the option Show safety zones to the Tab Appearance of the Transporter .
- We added the option Show material flow direction to the Tab Graphics . It shows or hides the direction arrow on the length-oriented objects which provide a directional material flow.
- We added the setting One-sided delimitation to the Barred area .
- We added the button Set Dimensions and the attribute \_3D.Dimensions to the Tab Transformation of the simulation objects and the non-length-oriented animatable objects.
- We added the buttons Show Graphic Node Count and Show Polygon Count to the dialogs Show Structure and Show Inheritance in a 3D model. The number of graphic nodes and polygons of your imported graphics might blow up the size of your simulation model. They indicate where optimizing and reducing the respective number of graphic nodes and polygons might significantly increase the performance of your model.
- We enhanced the behavior of the Camera Marks . You can now also set Camera Marks in the Planning View .

We added the method F3DconfigurePlanningView .

- We added the method MUAnimations.copyFromSimulationObject to the objects which can animate MUs .
- We added the function F3DattachCamera to attach a camera to an object.
- We added the method moveToCoordinate to the animatable objects.
- We added the option Swap X and Z axis to the dialog Make Animatable Object . We added the optional parameter SwapXAndZAxis to the method \_3D.getGraphic(…).makeAnimatableObject .
- We added the memory usage of the imported graphic to the dialog Import Graphics .
- We added the attributes Generated , Internal , Locked , and Visible to the attributes for accessing graphic groups.

They replace the methods \_3D.isGraphicGroupGenerated , \_3D.setGraphicGroupInternal , \_3D.isGraphicGroupInternal , \_3D.setGraphicGroupExternal , \_3D.lockGraphicGroup , \_3D.isGraphicGroupLocked , \_3D.unlockGraphicGroup , \_3D.showGraphicGroup , \_3D.hideGraphicGroup , and \_3D.isGraphicGroupVisible , which we no longer support.

- We added the methods \_3D.exportModelingViewBitmap and \_3D.exportPlanningViewBitmap .
- We enhanced the behavior of the method \_3D.getGraphic(GraphicGroupName:string[, Path:any[]]) . You can use the abbreviated notation \_3D.GraphicGroupName if GraphicGroupName is a valid identifier.

- We enhanced the behavior of the method \_3D.getObject(ObjectName:string) . You can use the abbreviated notation \_3D.ObjectName if ObjectName is a valid identifier.
- We enhanced the behavior of 3D when selecting objects by dragging a marquee around them in the 3D window . 3D now shows the marquee while you drag it around the objects.
- We enhanced the behavior of 3D . When you use an underscore in the Name of an object and show this object in 3D with activated Captions , Plant Simulation shows the underscore as a blank space.
- We enhanced the behavior of Plant Simulation . When you duplicate a graphic by holding down Ctrl+Shift and clicking the left mouse button, Plant Simulation does not create a copy of the graphic, but the new graphic references the duplicated graphic. This reduces memory consumption. Plant Simulation shows that the graphic is referenced with a diamond in the dialog Show Graphic Structure .
- We enhanced the behavior of Plant Simulation . You can now click a Button , a Checkbox , or a DropDownList in a sub-Frame and switch the value or trigger the respective action.

Back to What's New in Plant Simulation 2404

### Changed 3D Features

Plant Simulation 3D provides a number of changed features.

- We enhanced the layout of the Tab MU Animation . It now provides the respective settings on the Sub-tab Animation Area and on the Sub-tab Animation Path instead of on the main tab itself.
- We changed the definition of the bay width of Store graphics. For dynamic Store types we now add the post diameter to the bay width . In previous versions, the post diameter was part of the slot width.
- We changed the behavior of 3D . Connectors , Interfaces , and Markers do no longer provide poses .
- We changed the behavior of automatically scaled MUs . Plant Simulation now automatically applies size changes of automatically scaled MUs after each modification to all visible inheriting classes and instances of the MU . For this reason, Apply Changes on the Edit ribbon tab is unavailable if the MU that is displayed in the active window is scaled automatically.
- We changed the return value of the method \_3D.getGraphic from any to void. This way you can query if a graphic exists or not.
- We removed support of the method \_3D.exportAsBitmap . We replaced it with the methods \_3D.exportModelingViewBitmap and \_3D.exportPlanningViewBitmap .

Back to What's New in Plant Simulation 2404

### New and Changed SimTalk Features

SimTalk provides a number of new and changed features in Plant Simulation .

- We added the function createPermutations to create all permutations of the specified length of an array element.
- We added the functions deg2rad and rad2deg . They convert an angle in degrees into an angle in radians and vice versa.
- We added the function getStandardColor to return a color value from a standard color palette.
- We added the function CalendarYear .
- We added the function strToHtml . It replaces all occurrences of characters, which have a syntactic meaning in HTML, within the specified text with the respective HTML entities to create valid HTML code.
- We added the methods copyToTableColumn and copyToTableRow to json arrays .
- We added the functions httpGetTimeouts and httpSetTimeouts for communicating with an HTTP server.
- We added the optional parameter Unit to these functions for converting values without units into physical data types with units:

| num_to_acceleration   | num_to_speed   |
|-----------------------|----------------|
| num_to_length         | num_to_weight  |

We added the optional parameter Unit to these functions for converting physical data types with units into data types without units:

| acceleration_to_num   | speed_to_num   |
|-----------------------|----------------|
| length_to_num         | weight_to_num  |

- We added the optional parameter KeepEmptyItems to the function splitString [SimTalk] . It sets if empty strings are to be incorporated into the array ( true ) or not ( false ).

You now can use any character as the Delimiter . In previous versions you could only use characters from the ASCII character set.

- We enhanced the functionality of the data type Json . JSON variables can now also contain elements of data type Object .
- We enhanced the functionality of the function deleteSuspendedMethods . The optional parameter WaitingToo of data type boolean sets if methods, which are suspended via a wait instruction , will be deleted as well.
- We enhanced the functionality of Declare Default Arguments . Parameters of data type array can have an empty array [] or an empty JSON object {} as default argument in SimTalk 2.0 .

Back to What's New in Plant Simulation 2404

### Miscellaneous

Plant Simulation provides a number of new and improved features covering various topics.

- We added enabled the feature Use Cloud Licensing . You can now use Plant Simulation X .
- We added a PlantSimulationConsole version without a user interface, see Starting PlantSimulationConsole.exe
- We added topics about using online help .
- We changed the look and feel of the Online Help to approximate the look and feel of the Siemens Digital Industries Software applications.
- We tightened the description of the SimTalk functions and added more structural elements to them.
- We enhanced the functionality of the window Show Attributes and Methods . You can now copy the name or the value of the selected attribute , read-only attribute , or method with Ctrl+C or with Ctrl+Shift+C .
- We changed how Plant Simulation shows attributes that inherit their value in the window Show Attributes and Methods . In previous versions, they showed an asterisk * . From this version on, they show a check mark ✓ .
- We changed the Date and time format . In previous versions, we used yyyy/mm/dd 24 hour . We now use yyyy-mm-dd 24 hour according to ISO 8601. For the 12 hour format, we now use the abbreviated variant AM and PM instead of a.m. and p.m.
- We added the mobile objects PartA , PartB , and Box to the folder UserObjects in the Class Library .
- We added the menu command Edit Controls to the Context Menu of the Selected Object in the Class Library . It shows the controls which you defined in the class of an object under Edit Controls or on the Tab Controls . Click the respective control to open it in the Method Editor .
- We added the menu command Edit User-defined Attributes to the Context Menu of the Selected Object in the Class Library .
- We added a tooltip that shows the name of the object, its origin , the part it produces, the predecessor and the successor , and its current state .

<!-- image -->

<!-- image -->

- We added the path to the simulation model in the message box that is shown when you select Close Model , Exit or click the Close button in the Plant Simulation title bar.
- We enhanced renaming an object or a user-defined attribute .

If you rename an object or a user-defined attribute and the current name is used in the source code of a Method , Plant Simulation asks if you want to replace the current name with the new name in local methods .

- We enhanced searching in the window Show Structure . You can now search for the entire path of an object.
- We enhanced the functionality of the Event Debugger . We added the text box Run to time .
- We changed the behavior of the command Encrypt Methods . It now encrypts all unencrypted methods and user-defined attributes of data type method . In previous versions, it did not encrypt the built-in Method class in the folder InformationFlow and the user-defined attributes of data type method of the built-in object classes.
- We deprecated the WorkerChart library. Instead, you can now drag the WorkerPool onto the Chart to emulate most of the functions of the WorkerChart . Be aware that the functionalities are not 100% identical, the WorkerChart had features that the new built-in features do not have and vice versa.

Back to What's New in Plant Simulation 2404

### New and Changed Features of the Value Stream Mapping Library

The Value Stream Mapping library version 2201.1.0 provides these new and changed features:

- We extended the check routines. We now check whether a Process has two supplying withdrawal Inventories , as this is not supported by the PPS MRP logic. We also check the uniqueness of products for warehouses and for loop modeling with product transitions, including assembly stations.
- We fixed an error that caused a missing trigger for a FIFO element.
- We fixed an error in the process statistics for the object ProcessLead which caused the waiting percentage being too high in certain constellations.

- We adapted the MRP parts requirements calculation for Supplier deliveries to dynamic requirements per interval instead of static average calculations.
- We limited the maximum total order quantity from Supplier to Customer to 100,000. In conjunction with very high customer requirements, very high product WIPs in the millions generally decrease the performance of such models significantly.
- We implemented additional internal performance optimizations.
- We fixed a number of internal errors, such as dialog adjustments with rework times.

The Value Stream Mapping library provides its own help, which is part of the library.

Back to What's New in Plant Simulation 2404

## What's New in Plant Simulation 2302

## What's New in Plant Simulation 2302

Plant Simulation 2302 provides a number of new and improved features.

- Important New and Changed Features
- Simulation-Relevant Changes
- New Features of the Material Flow Objects
- Changed Features of the Material Flow Objects
- New and Changed Features of the Fluid Objects
- New and Changed Features of the Resource Objects
- New and Changed Features of the Information Flow Objects
- New and Changed Features of the User Interface Objects
- New 3D Features
- Changed 3D Features
- New and Changed SimTalk Features
- Miscellany
- New and Changed Features of the Value Stream Mapping Library

**Back to What's New**

### Important New and Changed Features

We made important changes in Plant Simulation 2302. For this reason, you have to adapt simulation models, which you created in previous versions of Plant Simulation , when you open them in Plant Simulation 2302.

- Plant Simulation 2302 requires the Siemens License Server 2.0.0 or higher. You can download it here: https://support.sw.siemens.com/product/1586485382 . Also consult the accompanying Release Documentation .

In old license files, you have to replace the line:

VENDOR ugslmd

with this line:

VENDOR saltd

**Note**

We automatically change this when installing the new license server when you specify an old license file. If you want to use another license file later on, you have to change this manually though.

**Note**

The Siemens License Server 2.0.0 uses the default Port number 29000 to avoid a conflict with the existing port number 28000.

- We terminated support of the chm format for the Plant Simulation Help . We provide the Plant Simulation Help on our Support Center on the web instead. Using Online Help describes what you can do with it.

If you want to use the Plant Simulation Help locally, consult the document Accessing the help from Plant Simulation on the download page. It contains download information and installation instructions for the Siemens Documentation Server and the Plant Simulation 2302 Help .

**Note**

To install help content in a language other than English , you must first install the English help content.

Back to What's New in Plant Simulation 2302

### Simulation-Relevant Changes

We made simulation-relevant changes in Plant Simulation 2302. For this reason, you have to adapt simulation models, which you created in previous versions of Plant Simulation , when you open them in Plant Simulation 2302.

- We changed the behavior of automatic routing for Part and Container if the destination can only be reached via processing/assembly/dismantle stations.

In previous versions, Plant Simulation ignored the lengths of the Conveyors if all possible routes included stations. This caused two alternative routes, which contained Conveyors with different lengths , to be considered equivalent and the parts were then distributed according to the exit strategy to both alternative routes. From this version on, an alternative route containing shorter/faster Conveyors will be preferred.

- We changed the behavior of the Worker :
- Plant Simulation no longer books parts, which are loaded onto a Worker using a loading time, on the Worker , but on the station. Only after the loading time is over, Plant Simulation moves the MU to the Worker . When the Worker pauses, Plant Simulation cancels the loading process, the part remains on the station, and loading starts anew after the pause, possibly with a different Worker .
- Plant Simulation prematurely terminates unloading of parts onto a Worker if the Worker pauses, and unloads the part onto the station.
- A Worker , who is paused during a failure, now walks to the WorkerPool after the failure ended.
- A Worker now walks to the closest Workplace if several Workplaces are assigned to the station.
- We changed how Plant Simulation handles user-defined attributes of data type method when you extend the path, for example for MyStation.MyMethAttr.executeIn(60) . In the example, MyMethAttr is the name of the user-defined attribute .

In previous versions, these user-defined attributes were not executed if the path was extended. This way, user-defined attributes and Methods behaved differently, as their source code was always executed, no matter if the Method was placed in the middle or at the end of the path.

We changed this behavior. In our example above, the method executeIn(60) is no longer called for the user-defined attribute MyMethAttr itself, but for the return value of MyMethAttr . If you want to prevent the user-defined attribute from being executed, you now have to use the reference operator &amp; , Station.&amp;MyMethAttr.executeIn(60) for our example above.

Back to What's New in Plant Simulation 2302

### New Features of the Material Flow Objects

The material flow objects in Plant Simulation 2302 provide a number of new features.

- We added functions to and removed functions from the EventController :

<!-- image -->

<!-- image -->

<!-- image -->

- We added the button Start Full Speed Simulation to the EventController controls on the Home ribbon tab. We removed the buttons Real Time and Debug Next Simulation Step .
- We added the button Start Full Speed Simulation to the Tab Controls of the EventController . We removed the check box Real Time .
- We added the check box Skip long event intervals to the Tab Settings of the EventController .

<!-- image -->

The open windows of the simulation show the Fast Forward Simulation icon when skipping a long interval.

- We added the button Start Full Speed Simulation and the check box Step halts additionally before event to the EventDebugger .
- We renamed the button MU and Icon Animation on the Home ribbon tab to MUs and States .
- We added the command Incremental Find Object to the Frame ribbon tab of the Frame .
- We added the Tab Importer &gt; Transport Importer to the Conveyor . Here you can define how the Worker picks up conveyed parts and carries them to another station. This also enables the Worker to carry parts to the Conveyor .
- We added the Tab Importer to the Drain . You can specify importers for processing , setting-up , and the removal of failures . This also enables the Worker to carry parts to the Drain .
- We added the check box Wait for free target and the attribute WaitForFreeTarget to the Transport Importer .

- We added the menu command Contents and Reserved Places to the View menu of the material flow objects. We also added the method contentsAndReservedList .

We added the attribute ReservedFor to the material flow objects which can accept parts.

- We added the read-only attributes IsLaneA and IsLaneB to the TwoLaneTrack .
- We added the read-only attribute ReservedPlace to the MUs .
- We added these commands to the View menu of the material flow objects providing a transport importer : Exporters , Services , Unavailable Services , and Associated Workplaces .
- We added the check box Enforce MU distance and the attribute EnforceMUDistance to the Conveyor .
- We enhanced the behavior of the Transporter . Transporters that are driving freely within the area now support automatic routing and the Route weighting attribute . This only applies if the Markers are connected with Connectors .
- We added the text box Curve speed and the attribute CurveSpeed to the Transporter . It applies to the Transporter that drives freely within the area.
- We added the attribute StoppingCounter to the Transporter . It applies to the Transporter that drives freely within the area.
- We added the attribute calcBrakingDistance to the Transporter .
- We enhanced the behavior of the method getRouteIntermediateDestination . It now also applies to the Transporter .
- We added the read-only attributes StatExitBlockedPortion and StatExitBlockedTime . They are, in part, intended to show if a Buffer or PlaceBuffer is starved for parts .
- We added the read-only attribute StatAverageWorkingTime .
- We added the read-only attribute BwBlockListEntry1 .

Back to What's New in Plant Simulation 2302

### Changed Features of the Material Flow Objects

The material flow objects in Plant Simulation 2302 provide a number of changed features.

- We removed the check box Real-time from the EventController . Real-time is now active all the time.
- We changed the functionality of the simulation speed slider of the EventController . It now only sets the real-time factor for a real-time simulation. A non-real-time simulation always runs with maximum speed.

We terminated support for the method startWithoutAnimation . Use the method start(false,false) instead. To facilitate this, we added two optional parameters to the method start .

We terminated support for the attribute Speed .

- We enhanced how to create a User-defined Ribbon Tab and a User-defined Context Menu for the Frame . You can now add considerably more commands to them than in previous versions. We redesigned the dialog and we added a context menu and keyboard shortcuts .
- We improved automatic routing for parts. If the fastest route led across a Converter and if several equally fast routes to the destination across different exits of the Converters existed, then all routes were considered equivalent. The route was thus at first only calculated up to the Converter . We changed this for equally fast routes so that now the route, which leads straight through the Converter will be preferred, as the parts do not have to be singularized for this. If several Converters are located within the fastest route, Plant Simulation will now select the route of the equally fast routes where the part must be converted the least. A useful side effect is that Plant Simulation now finds the clearly shortest route more often, meaning that the entire route to the destination is known immediately.
- We changed the behavior of the attribute Backwards of the Transporter . You cannot change it any longer when the attribute TargetDistance is active.
- We changed the behavior of the AssemblyStation . By entering 0 into the text box Main MU from predecessor you can now set that a Worker has to deliver the main part via a Workplace .
- We enhanced the behavior of the AssemblyStation . You can now move the main part located on the AssemblyStation onto the AssemblyStation again with the method move . Plant Simulation attaches the mounting parts again and then starts processing anew.
- We changed the behavior of the DismantleStation . You can no longer enter 0 for the setting Main MU to successor with number . If you do enter 0 and click Apply or OK , Plant Simulation changes 0 to the default value 1. When you assign 0 to the attribute MainMU , Plant Simulation shows an error message.
- We changed the behavior when you used a non-blocking exit strategy for an object when the Worker was carrying parts away, when there was only a single successor and when that successor could not accept the part. In previous versions, the Worker remained at the starting point until the destination was available. From now on, the Worker walks to the one destination that is possible.
- We changed the behavior of a station which you fail via SimTalk , either with Failed := true or with the method startFailure . The station now requests a Worker if the Failure Importer is active.
- We made the parameter of the method pe of the PlaceBuffer optional. Plant Simulation now uses the default value, meaning 1.
- We made the read-only attributes CurrentSpeed and CurrentAcceleration of the Conveyor watchable.
- We terminated support of the function setParam of the random number distributions. Use setTypeAndAttr instead.

We also enhanced the behavior of setTypeAndAttr . In previous versions, it expected the name of the distribution and the parameter set as a string each.

MyStation.ProcTime.setTypeAndAttr("Uniform", "0:15, 0:20")

Now you can also pass the parameter set as individual parameters.

MyStation.ProcTime.setTypeAndAttr("Uniform", 0:15, 0:20)

- We renamed the attribute AttrType of the user-defined attributes to DataType . This way the name of the attribute matches to the name of the attribute of the object Variable .
- We added the parameter SaveCallChains to the function saveModel .

Back to What's New in Plant Simulation 2302

### New and Changed Features of the Fluid Objects

The fl uid objects in Plant Simulation 2302 provide a number of new and changed features.

- We added the setting Material selection to the Tab Attributes of the FluidSource .
- We changed how we internally save the name of the Product of the Mixer to avoid problems with upperand lower-casing.

Back to What's New in Plant Simulation 2302

### New and Changed Features of the Resource Objects

The resource objects in Plant Simulation 2302 provide a number of new and changed features.

- We enhanced the behavior of the Workplace . We added the check boxes At entrance and At exit , enabling you to attach a Workplace to the entrance or the exit of a Conveyor . This way a Worker can pick a part up at the entrance or the exit of the Conveyor and carry it to another station.

For the point-oriented material flow objects, we attach the Workplace to the entrance and the exit of the object by default.

When you place a Workplace close to the material flow object and click the left mouse button, Plant Simulation opens a window asking you Do you want to activate an importer .

<!-- image -->

- We enhanced the behavior of the Worker . You can now specify a Priority and an Efficiency for each service in its Services list . If you do not enter a Priority and an Efficiency for an individual service, Plant Simulation uses the values for the Priority and the Efficiency of the Worker .

We also added the methods setServices and getServices to facilitate this.

- We added the optional local variable FoundWorkplace to the method getRouteLength of the Worker .
- We enhanced the behavior of the Exporter and the Worker . They no longer require you to enter exp plus the name of the sub-attribute in SimTalk as all sub-attributes are directly available.
- We changed the behavior of the methods getImporters and getExportedServices of the Exporter and the Worker . The parameter table is now optional. If you do not specify the parameter, the methods return an array instead of a table .
- We changed the behavior of the Worker . A Worker who is not automatically brokered stays at the Workplace to which he was sent, no matter if you activated Worker stays here after completing the job in the Workplace or not.
- We changed the behavior of the Worker . A Worker now walks to the closest Workplace if several Workplaces are assigned to the station.
- We added the Arrival control and the attribute ArrivalCtrl to the Marker . In the arrival control you can, for example, program actions that you want to take once an AGV arrives
- at the Marker or is closest to the Marker . You might, for example, provide your fleet management software with feedback about the position of the AGV .

Back to What's New in Plant Simulation 2302

### New and Changed Features of the Information Flow Objects

The information flow objects in Plant Simulation 2302 provide a number of new and changed features.

- We changed the behavior of the command Stop on Wakeup on the Debugger ribbon tab. This change also applies to the command Debug &gt; Stop On &gt; Stop on Wakeup .
- Plant Simulation now stops when waking up all suspended Methods . In previous versions, Plant Simulation only stopped if the Method was suspended with waituntil or stopuntil . Now Plant Simulation also stops Methods which were suspended beforehand with wait or sleep(true, false) .
- We changed the behavior of the command Edit &gt; Reformat Selection in the Method Editor . If you did not select any source code, the command now affects the entire source code, not only the current line of code as in previous versions.
- We changed the behavior when you delete an event that has a breakpoint. Plant Simulation still opens a message window asking you if you want to stop the simulation. If you click No , Plant Simulation now sets a breakpoint at a simultaneous event or at the preceding event if no simultaneous event exists.
- We changed the color of the state LED of the Method , which shows if the Method inherited its source code. It now matches the green color of the Inheritance check box.

- We changed the behavior of syntax-controlled indentation in the Method Editor . The Method Editor no longer enforces the indentation of the source code to a tabulator position. If you inserted a line in the source code and if the source code before this line of code is not indented by a multiple of the tab size , the source code is now aligned to the previous line of code instead of to the tabulator position to the left of it.
- We changed the behavior of the read-only attributes of the MQTT Interface which receive the results of interactions with an MQTT broker. The respective read-only attribute will call the watching method twice. The first time when emptying the read-only attribute before an interaction with an MQTT broker. The second time after the response of the MQTT broker was written to the read-only attribute.
- We enhanced the behavior of the methods setSendBufferSize and setReceiveBufferSize of the Socket interface . You can now define the default buffer size for new connections by specifying -1 as the parameter Channel .
- We added a section for MQTT Communication Statistics to the data which the Profiler shows.
- We added the key combination Ctrl+H for replacing text in the Method Debugger .
- We added the method deleteCellFormat to lists and tables.
- We added dialog items to the Tab Attributes of the MQTT Interface . These allow you to enter settings into text boxes that were only available via SimTalk in previous versions.
- We changed the behavior of the watchable attributes of the MQTT Interface , which record the results of interactions with MQTT brokers. The respective watchable attributes are:
- ConnackReason , ConnackProperties
- DisconnectReason , DisconnectProperties
- SubackReason
- UnsubackReason
- PublishReason , PublishProperties

From version 2302 on, we automatically reset the attribute values to an empty string before an interaction with an MQTT broker. The attribute value thus changes twice for each interaction, so that observer methods to these attributes are called twice as well: The first time before the interactions when the attribute is set to an empty string. The second time after the interaction when the feedback of the MQTT broker arrives and is stored in the attribute.

- We added the Login settings Username and Password to the OPCUA Interface . If you fill in the text boxes Username and Password , Plant Simulation logs you into the OPC server with this data. If you leave the text boxes empty, Plant Simulation logs in as an anonymous user.
- We added the attributes SecurityMode and SecurityPolicy to the OPCUA Interface .
- We added a number of features to the Teamcenter Interface . The new features also affect the functionality of existing features:
- We added these settings to the Tab Connection : Import mode , Group , and Role .
- We added settings to the Tab Import enabling you to import data from a Study of a Collaboration context from Teamcenter .

The setting Study in addition requires that the Teamcenter Manufacturing Access extension is installed for the specified Active Workspace-Server .

We added the check box Retrieve kinematics files .

- We added the command Revise to File &gt; Teamcenter . This command enables you to independently check the model in and revise it.
- We terminated support of the attribute UseActiveWorkspace , you can use the attribute ImportMode instead.
- We changed the functionality of the methods retrieveData and login to reflect new features.
- The Teamcenter Interface now supports authentication to Teamcenter 13.3 and higher with SingleSign-On ( SSO ) in the default mode of the Teamcenter Security Services .

If you are using the Teamcenter Interface with Teamcenter 13.2 or lower, and want to authenticate to Teamcenter with SSO , you have to install the Teamcenter Security Services 13.3 in compatibility mode. For more information consult this knowledge base article https://support.sw.siemens.com

- We enhanced the behavior of the PLCSIM\_Advanced Interface . It can now also handle elements of data type String and WString . For this reason, the PLCSIM\_Advanced Interface requires at least version 5.0 of PLCSIM Advanced .

Back to What's New in Plant Simulation 2302

### New and Changed Features of the User Interface Objects

The user interface objects in Plant Simulation 2302 provide a number of new and changed features.

- We added the Categories &gt; 3D Chart and 3D Histogram to the Chart .
- We added the attributes WindowHeight and WindowWidth to the HtmlReport . We added the method getHTMLCode to the HtmlReport .
- We added the optional parameter Anchor to the method show of the HtmlReport .
- We added the buttons Investment Costs and Piece Costs to the CostAnalyzer .
- We added the attribute TimeScale to the GanttChart .
- We increased the zoom factor for zooming out in a GanttChart to show longer time intervals. Up until now, you could only zoom out to the range of single days; now you can also zoom out to show several months.

Back to What's New in Plant Simulation 2302

### New 3D Features

Plant Simulation 3D provides a number of new features in Plant Simulation 2302.

- We added a way to correct the unexpected viewing height after placing the avatar in the model in Plant Simulation VR .

In general, Plant Simulation views the virtual scene from the height at which the HMD is located above ground. If you are sitting down, this is considerably lower than the eye height of the standing avatar, which is 165 cm. To experience a walk-through of the virtual model from a realistic height, we recommend standing up when wearing the HMD.

If you want to experience Plant Simulation VR while sitting down, create a registry key of type DWORD with the value 1 under Siemens/Tecnomatix Plant Simulation 2302/Preferences/3D/ VRPlayerIsSitting . This raises the viewing height by 50 cm.

- We added the setting Use transparency to the dialog Textured Plate .

We also added the optional parameter UseTransparency to the methods createPicture and createTiledPlate .

- We added the settings Element width and Place remainder to the graphic shapes Factory Walls and Fence .

We added the parameter Element width to the methods createFactoryWalls and createFence .

We added the attribute WallElementWidth to the factory walls.

We added the attribute FenceElementWidth to the fence.

We added the attribute PlaceRemainder to the factory walls and to the fence.

- We added additional parameters to the method createText to match the settings of the dialog Text .
- We added settings to analyze the Graphic complexity to a number of dialogs. When importing graphics, it shows the number of nodes and polygons of the imported graphic. These are the numbers of the raw graphic, which might be reduced by automatic optimization.
- We added buttons for importing and exporting user-defined profiles for the length-oriented objects .
- We added the check box Show MUs as cuboids and the attribute \_3D.MUAnimationAreaShowMUsAsCuboids to animate the MUs as cuboids instead of the graphics of the MU itself.
- We added the command Apply Changes to the Edit ribbon tab of the MUs .
- We added the method \_3D.calculateMUDimensions to compute the dimensions of the MUs from their 3D graphic.
- We added the method \_3D.getMUAnimationRotation .
- We added the method \_3D.openDialog . It opens the dialog Edit 3D Properties of the object.
- We added support for importing 3D graphics files of data type STL (*.stl).
- We added the attribute \_3D.Selected .

Back to What's New in Plant Simulation 2302

### Changed 3D Features

Plant Simulation 3D provides a number of changed features in Plant Simulation 2302.

- We enhanced the virtual reality features of Plant Simulation .
- We changed the behavior when you export a graphic as a Jt file and when you activate Optimize for CAD . Now captions and logical objects are no longer exported.
- We changed the functionality of the method \_3D.exportAsBitmap . We added optional parameters for the camera position and the camera rotation .
- We changed the behavior of Fences and Factory Walls : When you change the settings for placing the remainder , we reset the cutouts .
- We changed the behavior when loading a Jt-file. Plant Simulation no longer executes measurements as the scaling on the topmost node, but so deep in the graphics structure as possible and, if possible, so that the measurements are no longer visible as the scaling in the dialog Edit 3D Settings .
- We removed support for importing NX files or SolidEdge files into Plant Simulation . If you want to use graphics from NX or SolidEdge in Plant Simulation , we recommend exporting them as JT files in their originating program and then import these into Plant Simulation .
- We removed the check box Show states as colors if no state graphics are present from the tab 3D in the Model Settings and the Preferences . Instead, you can select Tab States &gt; Orientation &gt; Color in the dialog Edit 3D Properties for each object. This colors the entire object graphics.

We also added the value Color to the attribute \_3D.StatesOrientation .

- Part and Container no longer show any states visualization.

The Transporter no longer shows the state Blocked . This state was called Waiting in 2D.

- We changed the behavior when you rotate the view with the mouse : When you start rotating a view with the mouse and remain at the position for at least 400ms and if an object or a graphic is located under the mouse pointer, Plant Simulation rotates around the position under the mouse pointer on the object or the graphic.

This also applies when nothing is located under the mouse pointer. In this case, Plant Simulation rotates around the position on the grid even if the grid was invisible.

<!-- image -->

| Mouse pointer, rotate around center of the scene   | Mouse pointer, rotate around object   |
|----------------------------------------------------|---------------------------------------|

- We enhanced the look and feel and behavior of the grid in the 3D window. This also reduces Moire effects when showing the base plate and keeps snap to grid active.
- When you insert or move objects or graphics in a 3D window, Plant Simulation adjusts the size of the grid accordingly.

- We enhanced the behavior when you create a Rotation path (Lines) for a camera animation. We now provide a default configuration that can serve as a template for your own camera flights.
- We enhanced the functionality of the method \_3D.Poses.moveToCoordinate .

In previous versions, Plant Simulation only recognized a robot type if the axes configuration matched a supported robot type from the simulation object level to the gripper object. Now Plant Simulation also checks if a part of this chain matches a supported robot type. A robot type with more axes takes precedence over a robot type with fewer axes.

**Note**

For this reason, the Method Debugger now opens in fewer cases than in previous versions when calling \_3D.moveToCoordinate . Not reaching the destination coordinate/rotation is still not considered an error and still does not open the Debugger . An unsuitable, but recognizable axes configuration will still not be recognized, if 8 axes exist, for example, but only the last three axes are recognized as part of a simpler robot type.

- We enhanced the behavior of camera marks . The number of camera marks is no longer limited. Plant Simulation only shows 9 menu commands when you click the button View &gt; Camera Marks though. You can access additional camera marks in the dialog Camera Marks .
- We enhanced the behavior when you rotate objects in a 3D Only model . All objects now provide the button Add Rotation .

Back to What's New in Plant Simulation 2302

### New and Changed SimTalk Features

SimTalk provides a number of new and changed features in Plant Simulation 2302.

- We added the function openDateSelectBox .
- We added the function getApplicationProcessID which returns the current process ID (PID) of Plant Simulation .
- We terminated support of the function resetInitBox as Plant Simulation no longer shows an InfoBox . Instead, Plant Simulation now shows text pertaining to Reset and Init in the status bar.
- We introduced = as an additional assignment operator.
- We introduced != as another notation for the not-equal operator in SimTalk 2.0 . This makes it easier to write SimTalk source code, as this is the notation also used in Java and C++.
- We enhanced the behavior of the init methods . You can now define two phases when they will be called with the parameter of data type integer .
- In phase 1, the init method is called before the objects have initialized themselves.
- In phase 2, the init method is called when the objects have initialized themselves.

If you want to change the failure parameters, for example, you will do this in phase 1 when the object has not yet calculated the time for the next failure.

**Miscellaneous**

- We enhanced the function num\_to\_str . You can also specify a negative value for the parameter Precision . Plant Simulation then uses the absolute number of the negative value as the number of desired decimal places.

We also added the optional parameter Width .

- We enhanced the function strAscii . You can also specify a negative value for the parameter PositionOfCharacter . The function then returns the n-th character starting at the end of the string.
- We enhanced the usage of the reference operator &amp; . You can now also use it for user-defined attributes of data type object and json to access the user-defined attribute itself and not its value.
- We added the read-only attribute Empty to the one-dimensional arrays .
- We added the function deleteFile . You can use deleteFile to delete any file you do not need any longer.
- We added the optional parameter MultiLine to the method asString for json values.
- We added the method unshareAndDelete to the variables and user-defined attributes of data type json .
- We added the optional parameter RetainInheritedValues to the method replace .

Back to What's New in Plant Simulation 2302

### Miscellaneous

Plant Simulation 2302 provides a number of new and improved features covering various elements.

- We added terms to the topics to improve searching the help .
- We added the tabs Digital Product Experience and Product Excellence Program to the Preferences .
- We removed the command File &gt; Save Folder Model As . Instead, you can select Folder Model (*.psfm) in the dialog Save As to save your simulation model as a folder model.
- We added the check box Create backup files with time stamp to File &gt; Preferences &gt; General .
- We added the function getApplicationProcessID which returns the current process identifier (PID) of the current Plant Simulation session.

Back to What's New in Plant Simulation 2302

### New and Changed Features of the Value Stream Mapping Library

The Value Stream Mapping library version 2201.0000 provides a number of new and changed features.

- We added more 3D visualizations for objects in the library and tools for full 3D support ( DisplayPanels , Timeline , Gozintograph , Downstream , Remark ).
- We added 3D MU visualizations for processes and transport objects.

- We added aggregated 3D MU visualizations for the Inventory and the Supermarket .
- We fixed bugs related to 3D graphics groups.
- We implemented the version change to Plant Simulation 2201 .
- We fixed other bugs.

Back to What's New in Plant Simulation 2302

