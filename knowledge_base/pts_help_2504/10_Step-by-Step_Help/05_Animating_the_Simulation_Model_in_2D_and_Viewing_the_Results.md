## Animating the Simulation Model in 2D and Viewing the Results

### Animate the Simulation Model in 2D and View the Results

Animating the simulation model in 2D and viewing the results provides information about the respective features.

- Animate the Simulation Model in 2D
- View and Visualize Statistics

- Switch States and Execute Actions

Compare Modeling the Material Flow

Compare Visualizing the Material Flow in 3D

Compare Getting to Know Plant Simulation

### Animating the Simulation Model in 2D

#### Animate the Simulation Model in 2D

One of your tasks when creating your simulation model will be to visually show the flow of materials through the plant you are modeling. For this you can either animate the built-in icons of the material flow objects and the mobile objects ( MUs ) in a 2D Only model , or you can create a 3D Only model .

- By default, Plant Simulation shows the state of the material flow objects, and of the Frame itself, during your simulation runs in 2D as one or more colored dots in the LED display along the upper border of the icons of the objects you inserted into the Frame .
- You can also create an icon each for the different states the objects may take to display the state of operation of an object, such as failed , paused , etc. during a simulation run.

To use state icons instead of the LEDs, right-click the material flow object and select Edit Icons . Click State Icons/LEDs &gt; Use State Icons on the General ribbon tab of the Icon Editor , so that the latter shows that it is selected.

<!-- image -->

For this, you can modify any of the built-in icons or design new icons in the Icon Editor . Here you can also create and modify the animation structures, i.e., the animation points and animation lines, to define the route and the paths which the MUs take.

Plant Simulation shows the settings for the animation in 2D on the Animation ribbon tab of the Icon Editor .

<!-- image -->

Plant Simulation shows the settings for the animation in 3D on the Tab MU Animation in the dialog Edit 3D Properties .

#### Activating and Deactivating the Animation

**Note**

As the animation of the parts and of the icons of the object slows down the simulation, only activate it, when you actually want to show the simulation model to somebody or if you want to check if the model behaves correctly. For your overnight batch runs we recommend to deactivate it.

In Plant Simulation we differentiate between the:

- State Animation , i.e., the animation of the icons of the material flow objects themselves. The LEDs of the objects show the state in which they are at the moment. This way you can easily detect which objects obstruct the flow of materials.
- MU Animation , i.e., the animation of the moving objects in your simulation model. During the simulation run the animation shows the state of the objects and the position and the movements of the MUs .

You can activate or deactivate MU and State Animation only together, not individually.

<!-- image -->

- When you activate MUs and States , you immediately see the flow of the parts and the blocked stations, where the MUs pile up.

#### Working with Object Icons

- When you deactivate MUs and States while an object intends to change its state, Plant Simulation delays its display on screen until you activate the animation again or until the object is selected.

To deactivate

MUs and States

, click on the Home ribbon tab.

<!-- image -->

To run the simulation with the setting you selected, click Start/Stop Simulation in the EventController .

<!-- image -->

Back to Animate the Simulation Model in 2D

##### Working with Object Icons

Work with Object Icons

Plant Simulation uses the icons of an object to display it in the Class Library , in the Toolbox , and in the Frame . The icons can also serve to display the state of operation of the object, such as failed , paused , unplanned , etc. You can modify the built-in icons, including any of the animation paths, or design new ones in the Icon Editor .

**Note**

2D and 3D use object icons.

At times you have to edit one of the existing icons of an object or you will want to add new icons to it.

Back to Animate the Simulation Model in 2D

Edit an Icon

To edit the icons of an object, do one of the following:

- Right-click the object in the Frame and select Edit Icons .
- Select the object in the Frame and click Edit Icons on the Home ribbon tab.
- Right-click the object in the Class Library and select Edit Icons .
- Click on the Home ribbon tab to edit the icons of the selected Frame

<!-- image -->

.

<!-- image -->

- Click on the Home ribbon tab to edit the icons of the selected object .
- Then, use the functions on the Edit Ribbon Tab , the Animation Ribbon Tab , and the General Ribbon Tab of the Icon Editor to actually edit the icon.
- Click to apply the changes you made.

<!-- image -->

<!-- image -->

**Note**

2D Only and 3D Only simulation models in Plant Simulation use icons.

Back to Work with Object Icons

Create an Icon

To create a new icon and to then open an existing drawing that you would like to use, do one of the following:

- Click New Icon on the Edit ribbon tab. If the drawing you open is larger than the default icon size of 41 by 41 pixels, enter another width and/or height.
- Click Import &gt; Import Bitmap File/Import Icon Resource , navigate to the folder that contains the drawing you would like to use as an icon, select the file and click Open .
- Drag a graphics file (.gif, .bmp, .ppm, .ppm raw, .dxf or .dwg) from the Windows Explorer, etc. over the drawing window and drop it there.
- Enter a meaningful Name for the icon.
- To draw a line or a shape, select a drawing color and one of the drawing tools

<!-- image -->

window.

- To move the reference point, click and then click the position to which you would like to move the reference point.
- To change the color
- of one or several pixels, select a color in the color palette and click the pixel(s) whose color you would like to change with one of the drawing tools.
- of a contiguous color area, select a color in the color palette and click the area whose color you would

<!-- image -->

like to change with

- To draw with two colors, you can assign a color each to the left mouse button and the right mouse button:
- Click a color in the color palette with the left mouse button to add this color to the top drawing color field. Or
- Double-click the color field and define a color of your choice in the dialog Colors .
- Then, click the respective mouse button to draw with that color.
- You can:
- make one or several pixels transparent, by clicking the transparency field and click the pixel(s), which you would like to make transparent with one of the drawing tools.
- make a contiguous color area transparent, by clicking the transparency field and click the area, which

<!-- image -->

you would like to make transparent with

.

**Note**

The background of the Frame shines through any area you marked as transparent.

<!-- image -->

- Click

to apply the changes you made and close the Icon Editor .

Back to Work with Object Icons on the Edit ribbon tab, and draw the shape in the drawing

<!-- image -->

##### Make Areas of an Icon Transparent

To make a contiguous area of a graphics file, which you opened, transparent, so that the background color of the Frame shines through, proceed as follows:

- Open the Icon Editor by clicking Edit Icons on the Home ribbon tab.
- Click or to navigate to the icon you want to make transparent.
- Click the color picker and click in the background of the icon. This makes that color the active drawing color, which we want to replace.
- Select the transparency color that replaces the active drawing color in the Color Palette proper, not in the transparency color field!

<!-- image -->

<!-- image -->

<!-- image -->

If the transparency color is not part of the color palette proper, double-click any field in the Color Palette that contains a color you do not need, and enter 0 , 128 , 128 into the dialog Colors &gt; Custom and click OK .

- Make sure that Icon &gt; Activate Transparency is active.
- Click Apply Changes to make the area transparent.
- To use the changed icon as the current icon of the object, make sure that is selected.

<!-- image -->

<!-- image -->

Back to Work with Object Icons

#### Set and Link Animation Points and Lines

During the simulation run the MU moves along the connecting lines, which you established with the Connector , from material flow object to material flow object and/or material flow object to components you modeled in a Frame . In your animated simulation model, Plant Simulation places the reference point

<!-- image -->

of the icon of the MU onto the animation point of the icon of a point-oriented material flow object or on the animation line of the icon of a length-oriented object, or on the icon of the Frame .

<!-- image -->

For a material flow object the correlation looks like this:

<!-- image -->

For a Frame the correlation looks like this:

<!-- image -->

To insert an animation point or an animation line into the icon of the class of a material flow object or of a Frame :

- To open the Icon Editor , right-click the Frame into which you would like to insert an animation structure and select Edit Icons .
- To activate Animation Mode , which enables you to insert animation points and animation lines, click the Animation Ribbon Tab .

To insert an animation point or an animation line into the icon of the class of an object, click Open Class on the Home ribbon tab. You will notice that Plant Simulation opens the class object of the selected object. If you want to insert an animation point into the icon of the active instance of the icon, do not click Open Class .

<!-- image -->

- To insert an animation point into the icon of a point-oriented object, click . Then, click into the drawing area with the left mouse button at the location of your new animation point.
- To insert a straight animation line into the icon of a length-oriented object, click . Then, click into the drawing area with the left mouse button, hold the mouse button down to insert the beginning of the line, drag the mouse until the line is as long as you want it to be and release the mouse button. This inserts the end of the line.

<!-- image -->

<!-- image -->

- To insert a non-straight animation line into the icon of a length-oriented object, click .Then, click once into the drawing area with the left mouse button to set the starting point of the line, click again to set the next anchor point. Plant Simulation connects the anchor points to create the line. Continue this until the polygonal chain meets your needs.
- To move an animation point or an animation line to a different position, click on the Animation ribbon tab.

<!-- image -->

These colors represent the different states of an animation point:

- Blue : Is the standard color for all objects, except for the Frame . For a Frame Plant Simulation shows that the animation point is linked to an object located within that Frame .
- Light blue : Is the same as blue . In addition, it shows that an animation point of a Frame is linked to this animation point.
- Red : The animation point in a Frame is not linked to an object located within that Frame . For this reason Plant Simulation does not show an animation for this point.
- When you are done inserting, close the class object, and click Yes to save the changes to the icon of the class.

To link an animation point , which you inserted into the class of an object, with the animation point/line of a Frame :

- Select the Frame in which you would like to link the animation structure with the right mouse button and select Edit Icons .
- To activate Animation Mode , which enables you to link animation points and animation lines, click the Animation ribbon tab.
- To show the name of the model or of the object next to the animation point/animation line in the drawing window, select Tools &gt; Show Animation Numbers . This makes assigning animation points easier.
- Click Link/unlink animation point and select the animation point/line in the icon of the Frame. Plant Simulation shows the selected animation point or the animation line

<!-- image -->

<!-- image -->

This opens the window of the Frame you selected above. Click the material flow object to which you want to assign the animation point/line. You will notice that the color of the assigned animation point or the animation line changes to blue. When a MU moves to this animation point/line during the simulation run, Plant Simulation shows it on this animation point/line.

**Note**

You can delete an animation point and insert a new one immediately afterwards without the correlation getting lost.

<!-- image -->

<!-- image -->

- To apply the settings, click .
- To delete all animation points/lines of an object, click or click the animation line with the right mouse button.

Compare Representation [2D only]

Back to Animate the Simulation Model in 2D

### Viewing and Visualizing Statistics

#### View and Visualize Statistics

By default, all material flow objects collect statistics values from the beginning to the end of the simulation runs. If you don't want them to do so, deactivate statistics collection by clearing the check box Resource Statistics on the tab Statistics or Product Statistics on the tab Product Statistics .

In addition, the material flow objects provide Energy Statistics values.

The EventController controls when statistics collection starts and when it will be reset, i.e., started anew.

- Click the tab Settings . Click in the text box Statistics and enter the time at which the EventController resets statistics and deletes all statistics values it collected up so that time, compare Statistics

<!-- image -->

Collection Period . Plant Simulation starts collecting statistical data for all material flow objects anew from this time on. This way you can discard data collected during warm-up phases, which might distort the validity of the simulation results.

<!-- image -->

<!-- image -->

<!-- image -->

- When you reset your simulation model, by clicking Reset Simulation , Plant Simulation deletes statistics data of all objects and resets the statistics values to 0. During a simulation run you can achieve the same effect with the method initStat . This way you can restart the collection of statistical information after a warm-up period of a machine, for example.

Covering Plant Simulation statistics in detail would go beyond the scope of the Plant Simulation Step-byStep Help . It is described under the topic Statistics of the Material Flow Objects in the Plant Simulation Reference Help .

Compare Statistics of the Mobile Objects

Back to Animate the Simulation Model in 2D

#### Viewing Statistics in the Dialogs of the Objects

View Statistics in the Dialogs of the Objects

In its most basic form you can view the statistics, which the objects collected during a simulation run, in their dialogs, either on the tab Statistics or by opening the statistics report of the objects:

- The material flow objects proper show the most important statistical data they collect on the tab Statistics .

By default, the resource type used most often is pre-selected:

- Production : For the Station , ParallelStation , the AssemblyStation , and for the DismantleStation .
- Transport : For the PlaceBuffer , Buffer , Sorter , Track , TwoLaneTrack , Conveyor , Transporter , and for the Container .
- Storage : For the Store .

The resource type you select here affects statistics of mobile objects.

**Note**

The percentages for Working , Setting-Up , Waiting , Blocked , Powering up/down , Failed , Stopped , Paused , and Unplanned should add up to 100 percent.

<!-- image -->

**Note**

Plant Simulation does not dynamically update the values during a simulation run when the dialog box is open. To accomplish this, select Refresh in the View menu of the object or press F5 .

| Item       | Description                                                                                    |
|------------|------------------------------------------------------------------------------------------------|
| Working    | Shows the portion of the statistics collection period during which the object was Working .    |
| Setting-up | Shows the portion of the statistics collection period during which the object was Setting-Up . |

| Item                | Description                                                                                                                                                                                                                                                                                         |
|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Waiting             | Shows the portion of the statistics collection period during which the object was Waiting .                                                                                                                                                                                                         |
| Blocked             | Shows the portion of the statistics collection period during which the object was Blocked .                                                                                                                                                                                                         |
| Powering up/down    | Shows the portion of the statistics collection period during which the object was Powering up/down .                                                                                                                                                                                                |
| Failed              | Shows the portion of the statistics collection period during which the object was Failed .                                                                                                                                                                                                          |
| Stopped             | Shows the portion of the statistics collection period during which the object was Stopped by a LockoutZone .                                                                                                                                                                                        |
| Paused              | Shows the portion of the statistics collection period during which the object was Paused .                                                                                                                                                                                                          |
| Unplanned           | Shows the portion of the statistics collection period during which the object was Unplanned , i.e., is not scheduled to work.                                                                                                                                                                       |
| Relative occupation | Shows the capacity-based portion of the time during which the object was occupied, not paused and not failed to the time the object was not paused and not failed as a real number.                                                                                                                 |
| Relatively empty    | Shows the portion of the statistics collection period during which the object was Empty in relation to the time during which the object was available.                                                                                                                                              |
| Contents            | Shows the number of MUs , which are located on the object, as an integer number. The rules described under Entries below apply.                                                                                                                                                                     |
| Minimum contents    | Shows the minimum number of MUs that was located on the object, as an integer number. The rules described under Entries below apply.                                                                                                                                                                |
| Maximum contents    | Shows the maximum number of MUs that was located on the object, as an integer number. The rules described under Entries below apply.                                                                                                                                                                |
| Entries             | Shows the number of MUs that entered the object as an integer number. When a MU enters the object, it only counts the MU itself, not its contents: When a Container holding several MUs enters the object, the number of entries increases by 1, not by the number of MUs the Container transports! |
| Exits               | Shows the number of MUs that exited the object as an integer number. When a MU exits the object, it only counts the MU itself, not its contents: When a Container holding several MUs leaves the object, the number of exits increases by 1, not by the number of MUs the Container transports!     |
| Average dwell time  | Shows the average time of all parts which stayed on the station. Plant Simulation only counts times during which the object was not paused and not unplanned.                                                                                                                                       |

To view the statistics values, which the object collected, click Show Statistics Report on the Home ribbon tab. You can query most of these values with the Methods that are listed next to the name of the value in the description of the statistics table.

<!-- image -->

To view Energy Statistics values, click . Plant Simulation show these values in a dialog of its own:

<!-- image -->

| Item              | Description                                                                                 |
|-------------------|---------------------------------------------------------------------------------------------|
| Total consumption | Shows the sum of the total energy consumption.                                              |
| Working           | Shows the portion of the total energy consumption during which the object was working .     |
| Setting-up        | Shows the portion of the total energy consumption during which the object was setting-up .  |
| Operational       | Shows the portion of the total energy consumption during which the object was operational . |
| Failed            | Shows the portion of the total energy consumption during which the object was failed .      |
| Standby           | Shows the portion of the total energy consumption during which the object was on standby .  |
| Off               | Shows the portion of the total energy consumption during which the object was off .         |

**Note**

The energy states of the material flow objects differ from the resource states with the same name. The values for the resource states refer to the statistics collection period, while the values for the energy states refer to the total energy consumption.

To view Energy Statistics - Energy Statistics in the Statistics Report , click the object in the Frame , and press F6 .

- The mobile objects ( MUs ) show the most important statistical data they collect on the tab Product Statistics .

<!-- image -->

**You can:**

- Check How Many Parts Were Introduced into the Plant
- Check How Many Parts Left the Plant
- Check Statistics of the Individual Stations
- Check the Contents List of the Stations
- Check Product Statistics of Parts
- Check Statistics of Exporter and Worker
- Viewing the Statistics Report

Compare Show Statistics with Display Panels in the 2D Model

Compare Show Statistics in a Chart

Compare Show Statistics and Other Values in a Report

Compare Show Values During the Simulation with the Display

Back to Accessing Statistics with SimTalk

Check How Many Parts Were Introduced into the Plant

Next to the values described under View Statistics in the Dialogs of the Objects , you can make the Source record which MUs it actually created at which point in time.

- To write all events for which the Source produced MUs during a simulation run to a table, select Creation table on the tab Statistics .

**Note**

The Source records these events in addition to the resource statistics it collects in any case.

<!-- image -->

- To open the creation table, click Open .

Each row on the table shows an event for which the Source produced a MU :

- The column Name shows the name of the produced MU class.
- The column Path shows the path of the MU class, the name of the MU and its number.
- The column Time of Generation shows the time at which the Source produced the individual MU .

<!-- image -->

Compare Produce Parts with the Source

Back to View Statistics in the Dialogs of the Objects

Check How Many Parts Left the Plant

Next to the values described under View Statistics in the Dialogs of the Objects , you can make the Drain record statistics for MUs with the same name, i.e., product statistics, which move through the simulation model.

The numbers for the average exit interval and for the throughput are of special interest for production planning and production control specialists.

<!-- image -->

To collect statistics data depending on the type of MU , select Type Dependent Statistics . Plant Simulation will show this statistical data after the simulation run on the tab:

| Item       | Description                                                                                                                                                                                                       |
|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Working    | Shows the percentage of the sum of the times during which the MUs were located on a working object, in relation to the statistics collection periods of all MUs . In general, this is the life time of the MUs .  |
| Setting-up | Shows the percentage of the times that the objects were setting-Up for the MUs , in relation to the statistics collection periods of all MUs . In general, this is the life time of the MUs .                     |
| Waiting    | Shows the percentage of the times during which the objects were waiting for the MUs , in relation to the statistics collection periods of all MUs . In general, this is the life time of the MUs .                |
| Stopped    | Shows the percentage of the sum of the times during which the MUs were located on an stopped object, in relation to the statistics collection periods of all MUs . In general, this is the life time of the MUs . |
| Failed     | Shows the percentage of the sum of the times that the MUs were located on a failed object, in relation to the statistics collection periods of all MUs . In general, this is the life time of the MUs .           |
| Paused     | Shows the percentage of the sum of the times that the MUs were located on a paused object, in relation to the statistics collection periods of all MUs . In general, this is the life time of the MUs .           |

| Item                  | Description                                                                                                                                                                                                                                                                     |
|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Average lifespan      | Shows the average life-span of MUs , which were created and removed from the plant during the statistics collection period. Only those MUs are counted whose product statistics was active.                                                                                     |
| Average exit interval | Shows the average time interval between exits of the MUs , which the Drain removed from the plant. It results from adding up the times of all intervals, and then dividing them by the number of intervals. Statistics only starts counting from the time the first MU arrived! |
| Total throughput      | Shows the number of MUs , which the Drain removed from the plant, starting at the time, at which you activated Type dependent statistics .                                                                                                                                      |
| Throughput per hour   | Shows the number of MUs , which the Drain removed from the plant in an hour on average, covering all observed times during which MUs arrived.                                                                                                                                   |
| Throughput per day    | Shows the number of MUs , which the Drain removed from the plant in a day on average, covering all observed times during which MUs arrived.                                                                                                                                     |

To view the statistics, which the Drain collected, click Show Statistics Report on the Home ribbon tab. You can query most of these values with the Methods that are listed next to the name of the value in the description of the statistics table.

**Back to View Statistics in the Dialogs of the Objects**

##### Check Statistics of the Individual Stations

All material flow object show the values described under View Statistics in the Dialogs of the Objects on the tab Statistics .

The AssemblyStation and the DismantleStation show additional statistical values.

The AssemblyStation records the percentage of the time it was:

- Waiting for parts , i.e., for mounting parts in relation of the statistics collection period.
- Waiting for resources . This is the portion of the time during which the AssemblyStation was waiting before the main MU entered into it, or from the time set-up is finished, until assembly starts in relation of the statistics collection period.

Click the button to open the table Waiting Times , which shows the sum of the waiting times of the MUs for each predecessor.

<!-- image -->

##### Back to View Statistics in the Dialogs of the Objects

Check the Contents List of the Stations

Check the Contents List of the Stations

You can check and work with the Contents List of the individual material flow objects in a number of ways.

**You can:**

- Open the Contents List in the Dialog of the Material Flow Objects
- Write the Content List into a Table for Further Processing
- Print the Contents List to the Console as an Array

We demonstrate how to work with the contents list with the objects from the sample model below.

<!-- image -->

You can also use these techniques for working with the Forward Blocking List , the Exit Blocking List , and the Backward Blocking List of the individual material flow objects.

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

**Back to View Statistics in the Dialogs of the Objects**

Open the Contents List in the Dialog of the Material Flow Objects

To open the Contents List of the individual material flow objects in your simulation model during or after the simulation run, open the dialog of the respective object and select View &gt; Contents .

<!-- image -->

- The point-oriented objects with a capacity of 1 part show the path in the list, i.e., the name and the identifying number of the current part.
- The point-oriented objects with a capacity of more than 1 part show the path in the list, i.e., the names and the identifying numbers of the parts that are located on it. The capacity or the number of parts located on the object determines how many parts it shows.
- The ParallelStation shows the path, i.e., the name and the identifying number of the current parts in the list. The position of the part in the table matches the position of the part in its x-y coordinate system. The data type of the columns is object .

<!-- image -->

<!-- image -->

<!-- image -->

- The length-oriented objects ( Conveyor , Track , TwoLaneTrack , and Transporter ) show the path in the contents table, i.e., the name and the identifying number of the parts, that are located on the object. In addition it shows the position of the MUs in the object.

The column Object show the path to the part , the column From show the start position of the MU , and the column To show the end position in the length unit you selected under File &gt; Model Settings/ Preferences &gt; Units &gt; Length . The number of rows matches the number of MU parts located on the object.

In our example, the Conveyor is 15 meters long, while each part is 2.5 meters long.

<!-- image -->

The Conveyor can thus accommodate 5 parts in their entirety, which the contents list shows.

<!-- image -->

Back to Check the Contents List of the Stations

Write the Content List into a Table for Further Processing As the internal Contents List of the objects, which the menu command View &gt; Contents opens, will be deleted when you reset your simulation model, you have to save it, if you need this data later on for further processing.

<!-- image -->

As the default return value of the contents list, among others of the method contentsList , is an array , we are going write this array into a table with the method copyToTable .

<!-- image -->

To accomplish this, we entered the following source code into an endSim method:

```simtalk
// Copies the contents lists into the table MyContentsList // as an array with the method copyToTable var x,y : real;
var row : integer
MyContentsList.delete
var a : any := Buffer.contentsList
MyContentsList[1,1] := "Buffer"
a.copyToTable(MyContentsList,2,1)
row := MyContentsList.yDim + 2 // inserts an empty line MyContentsList[1,row] := "Conveyor"
print a // prints the contents list as an array to the console print "Number of items: ",a.yDim
var b := Conveyor.contentsList // local variable is of data type any print b print "Number of items: ",b.yDim
b.copyToTable(MyContentsList, 2,row) MyContentsList.openDialog // Writes the contentsList into a table
```

// as previous versions of Plant Simulation did Buffer.contentsList(ContentsListBuffer) Conveyor.contentsList(ContentsListConveyor)

Then, we manually formatted the table MyContentsList by selecting the correct data types for the columns and by entering the column index items as shown below.

<!-- image -->

After running the simulation, the endSim method writes the contents lists to the table:

<!-- image -->

To delete the contents of the contents list, you can enter the following source code into a reset method .

<!-- image -->

In addition, it writes the contents lists as an array each for the objects Buffer and Conveyor to the Console .

<!-- image -->

Finally, the endSim method writes the contents lists of the Buffer and the Conveyor into the tables ContentsListBuffer and ContentsListConveyor , which we inserted into the Frame .

<!-- image -->

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

Back to Check the Contents List of the Stations

###### Print the Contents List to the Console as an Array

To print the Contents List of the objects Buffer and Conveyor from our example to the Console as an array each, type the following source code into a Method and run the method.

```simtalk
print Buffer.contentsList
print Conveyor.contentsList
```

<!-- image -->

The result looks like this:

<!-- image -->

##### Back to Check the Contents List of the Stations

Check Product Statistics of Parts

All MUs , represented by the Part , Container and Transporter , show the percentages of the times the part spent waiting or working on a resource of type Production , Transport or Storage on the tab Product Statistics .

<!-- image -->

To view all product-related statistics data, which the MU collected, click Home &gt; Show Statistics Report . You can query most of these values with the read-only attributes that are listed next to the name of the value in the description of the statistics report.

<!-- image -->

As the Container and the Transporter can load and transport other parts, they also provide resource statistics, compare View Statistics in the Dialogs of the Objects .

Back to View Statistics in the Dialogs of the Objects

<!-- image -->

Check Statistics of Exporter and Worker

For the Exporter and the Worker the Tab Statistics shows the values for the Services and the Exporter . For each of these blocks, adding up the individual values yields 100 percent. You can query most of these values with the read-only attributes that are listed next to the name of the value in the description of the Statistics Report .

<!-- image -->

When you select the check box Fail Services on the tab Attributes , the Exporter collects the failure times of the Services and of the Exporter . When you deactivate it, the Exporter only collects the failure times of the Exporter .

<!-- image -->

The Exporter only collects failed times that take place during the processing and the set-up time, i.e., times that are located outside of the paused time and of the unplanned time.

Waiting times only accumulate during the times, when the Exporter is available, i.e., when these times are located outside of the paused , the unplanned , and of the failed times.

| Item                 | Description                                                                                                                                                                                             |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Services setting-up  | Shows the portion of the set-up time for services of the statistics collection period of the Exporter , weighted with the capacity.                                                                     |
| Services processing  | Shows the portion of the working time of the services of the statistics collection period of the Exporter , weighted with the capacity.                                                                 |
| Services repairing   | Shows the portion of the statistics collection period, which the services spent for repairs, weighted with the capacity.                                                                                |
| Services waiting     | Shows the portion of the statistics collection period, which the services spent waiting for an importer plus the time the services spent waiting for a MU at the importer , weighted with the capacity. |
| Services failed      | Shows the portion of the statistics collection period during which the services were failed.                                                                                                            |
| Exporter operational | Shows the portion of the statistics collection period during which the Exporter was working, weighted with the capacity.                                                                                |
| Exporter paused      | Shows the portion of the statistics collection period during which the Exporter was paused.                                                                                                             |
| Exporter unplanned   | Shows the portion of the statistics collection period during which the Exporter was unplanned.                                                                                                          |

| Item                      | Description                                                                                                            |
|---------------------------|------------------------------------------------------------------------------------------------------------------------|
| Exporter failed           | Shows the portion of the statistics collection period during which the Exporter was failed.                            |
| Free capacity             | Shows the capacity that is available at the moment.                                                                    |
| Mediated capacity         | Shows the capacity that is brokered at the moment.                                                                     |
| Free capacity (sum)       | Shows the sum of the released capacity that the Exporter placed with any importer .                                    |
| Mediated capacity (sum)   | Shows the sum of the brokered capacity.                                                                                |
| Minimum free capacity     | Shows the minimum capacity that is available. When the Exporter did not collect any valid value yet, the tab shows -1. |
| Maximum free capacity     | Shows the maximum capacity that is available. When the Exporter did not collect any valid value yet, the tab shows -1. |
| Minimum mediated capacity | Shows the minimum brokered capacity. When the Exporter did not collect any valid value yet, the tab shows -1.          |
| Maximum mediated capacity | Shows the maximum brokered capacity. When the Exporter did not collect any valid value yet, the tab shows -1.          |

Back to View Statistics in the Dialogs of the Objects

#### Viewing the Statistics Report

The most comfortable way of viewing statistics values of one or of several objects is to open the Statistics Report .

Below we demonstrate how to use it.

- Let us assume that we want to show the statistics of several objects in a single report. To do so, we select them ( Shift +click, or drag a marquee over them) and press F6 . Compare this example:

<!-- image -->

- This opens the Statistics Report , which looks like this:
- The report adds the statistics of the objects, which you selected, to the drop-down list in the top left corner of the display window. In our example these are the statistics values of the Stationary resources Source , Station , Station1 , Conveyor , ParallelStation , and Drain as well as the Importer Statistics . To jump to any of the topics, which interest you, select that topic from the drop-down list:

<!-- image -->

<!-- image -->

- One of the main topic shows the resource statistics of the material flow objects split up by the states these objects were in, i.e., the working , the waiting , the set-up , the blocked , the powering up/down , the failed , the stopped , the paused , and the unplanned time . These times add up to 100 percent. The set-up time and the empty time, which follow, may be part of the working , the waiting , or of the blocked time .

The subtopics further down in the report show details about the working , the waiting , the blocked , the failed , the stopped , the paused , the unplanned , the set-up , and the empty time in the order in which they appear here.

The bar on the right hand side shows the respective portions of the times.

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

- This is followed by material flow values of general interest.

<!-- image -->

- The subtopics show details of the working , the waiting , the blocked , the failed , the paused , the unplanned , the set-up , and the empty time in the order in which they appear in the first table. For details compare the Statistics Report .
- To add one or several objects in your model, which collect statistics to an open report, select it/them in the Frame and press F6 . In our example we added the Drain .

<!-- image -->

<!-- image -->

You will notice that the report added the object Drain to the list of stationary resources as well as to the drop-down list of available topics.

<!-- image -->

- To jump to the statistics of this Drain , select Drain Statistics from the drop-down list. For details compare the Statistics Report .

<!-- image -->

<!-- image -->

- You can add any of the objects, which collect statistics, to the report. It then adds these objects to the drop-down list.
- To show a Tooltip with the name of the respective read-only attribute for this statistics value, drag the mouse over the column header.
- To save the report as an HTML file (*.htm or *.html) or as a text file (*.txt) click Save . Enter a name for the file and select the folder into which you want to save it.
- To update the report with the current values, click Refresh .
- To print the report, click Print .

<!-- image -->

Compare View Statistics in the Dialogs of the Objects

Compare Show Statistics with Display Panels in the 2D Model

Compare Show Statistics in a Chart

Compare Show Statistics and Other Values in a Report

Compare Show Values During the Simulation with the Display

Compare Accessing Statistics with SimTalk

Back to View and Visualize Statistics

#### Showing Statistics with Display Panels in the 2D Model

Show Statistics with Display Panels in the 2D Model

To quickly and easily show values of interest during a simulation run in your simulation model, you can define a Display Panel each for the individual objects in the Frame . The display panel is kind of a dashboard that watches statistics values or states of the objects and shows them in different ways: As text , as a bar , or as an LED .

**Note**

A 3D Only model does not provide the Display Panel .

<!-- image -->

<!-- image -->

When you deactivate MUs and States , Plant Simulation shows the display panel , but does not update its values and continues showing the previous values. It does not update the values either, if no simulation is running. To still show current values, it updates them:

- When the simulation stops, either because you stopped it or because the End Time has been reached.
- When you click OK or Apply in the dialog of an object.
- When you select View &gt; Update in the dialog of an object.
- When you press F5 in the Frame window.
- When you call the method redraw of an object.

You can:

- Show Values as Text
- Show Values as Bars
- Show States with LEDs
- Show and Hide Display Panels with a Check Box

Compare View Statistics in the Dialogs of the Objects

Compare Show Statistics in a Chart

Compare Show Statistics and Other Values in a Report

Compare Show Values During the Simulation with the Display

Compare Accessing Statistics with SimTalk

Back to View and Visualize Statistics

Show Values as Text

Suppose you want to display the working portion of a station. To do so, you'll first add the label Working and then the value proper, i.e., the value that a Method records, to the right of it.

- Click the station for which you want to show the value with the right mouse button and select Edit Display Panel or click Edit Display Panel on the Home ribbon tab.

<!-- image -->

- To activate and to show the Display Panel in the Frame , select the check box Active . To deactivate it, clear it.
- Enter the Width and the Height of the display panel in the Frame . If need be, adjust the X-Position and the Y-Position .
- Click New to add a new item to the display panel .

<!-- image -->

<!-- image -->

- To add the label, select Static Text as the Type and enter Working: into the text box above it.
- To make the background color of the display panel shine through the text, select Transparent .
- Enter the X-Position of the label on the display panel and click OK .
- Then, define the Border Color around the display panel and its Background Color to make the display panel stand out in the Frame . Click the drop-down arrow in the color box and select a color in the dialog Colors . We selected black as the border color and light gray as the background color.
- Click Apply to show the display panel with the item you defined so far in the Frame . As you'll want to show the value to the right of the label, increase the Width of the display panel .
- Next, select the value you want to display next to the label. Click New .
- In the dialog Display Panel Element click and select the Value you want to show. As we want to show the working portion of our station, we select the read-only attribute StatWorkingPortion
- Select the display Type &gt; Text and select Display as percentage . Finally, adjust where Plant Simulation shows the value on the display panel by moving the X-position to the right of the label Working: .

<!-- image -->

<!-- image -->

As we want to show several values aligned correctly one below the other, we right -align them.

<!-- image -->

- Click OK to close the dialog Display Panel Element .
- Click OK again to finish defining the display panel .

Back to Show Statistics with Display Panels in the 2D Model

##### Show Values as Bars

Suppose you want to display the number of parts in a Buffer as a bar above the icon of the object.

<!-- image -->

- Click the station for which you want to show the value with the right mouse button and select Edit Display Panel .
- Select the check box Active to show the Display Panel in the Frame .
- To display the bar above the icon, move the X-Position and the Y-Position to the top left corner of the icon.
- Enter the Width and the Height of the display panel in the Frame . In this case it matches the width and the height of the bar itself.

<!-- image -->

- Click New to add the new item.
- In the dialog Display Panel Element click and select the Value you want to show. As we want to show the number of parts in the buffer, we select the read-only attribute NumMU .
- Select the display Type &gt; Bar .
- Select the Color of the bar and enter its Length and its Width .
- Finally, select the Direction into which the bar deflects starting at the X-position of the item. We selected Right .
- Click OK to add the item.
- Click OK again to finish defining the display panel .

<!-- image -->

<!-- image -->

Suppose you want to display the working , waiting , blocking , failed and paused portions of a station on a display panel below the object.

<!-- image -->

- Click the station for which you want to show the values with the right mouse button and select Edit Display Panel .
- Select the check box Active to show the display panel in the Frame .
- Enter the position , the width , and the height of the display panel in the Frame .
- Click New to add the new item.
- In the dialog Display Panel Element click and select the Value you want to show. We selected the read-only attribute StatWorkingPortion .
- Select the display Type &gt; Bar .
- Select the Color of the bar and enter its Length and its Width .
- Select the Direction into which the bar deflects starting at the X-position of the item. We selected Up .
- Click OK to add the item.

<!-- image -->

<!-- image -->

- Click OK again to finish defining the display panel . It then looks like this.
- Repeat the steps described above to add the values StatWaitingPortion , StatBlockingPortion , etc. to the display panel . Select a different color for each value and shift the X-position of each value to the right so that they do not overlap.

<!-- image -->

It then looks like this

<!-- image -->

<!-- image -->

Back to Show Statistics with Display Panels in the 2D Model

Show States with LEDs

Suppose you want to add a light-emitting diode to display more states on the icon of the object than the built-in LEDs show. You can, for example, show an LED if the Conveyor is occupied.

<!-- image -->

- Click the station for which you want to show the LED with the right mouse button and select Edit Display Panel .

- Select the check box Active to show the Display Panel in the Frame . Enter the Position , the Width , and the Height of the display panel in the Frame .
- Click New to add the new item.
- In the dialog Display Panel Element click and select the Value you want to show. We selected the attribute Occupied .
- Select the display Type &gt; LED .
- Select the Color of the LED and enter its Width .

<!-- image -->

Back to Show Statistics with Display Panels in the 2D Model

<!-- image -->

Show and Hide Display Panels with a Check Box

You can quickly and easily show or hide all or some display panels with the object Checkbox and a control method.

Insert the object Checkbox into your simulation model from the folder UserInterface in the Class Library or from the toolbar User Interface in the Toolbox . Then insert a Method , which you are going to use as the control of the Checkbox . We called our Checkbox ShowDisplayPanel and our Method showResults .

Configure the Checkbox as shown in the screenshot below:

<!-- image -->

Program the Control of the Checkbox .

The source code looks like this:

```simtalk
//Shows or hides the display panels.
var OnOff: boolean OnOff := ShowDisplayPanel.Value
MyStation1.DisplayPanel.Active   := OnOff
Conveyor.DisplayPanel.Active     := OnOff
Buffer.DisplayPanel.Active       := OnOff
MyStation2.DisplayPanel.Active   := OnOff
```

When you then click the Checkbox , Plant Simulation hides the displayed display panels. When you click it again, Plant Simulation displays the hidden display panels again.

<!-- image -->

Back to Show Statistics with Display Panels in the 2D Model

#### Showing Statistics in a Chart

Show Statistics in a Chart

To present the results of your simulation runs to colleagues and management, you will use the Chart . You can insert the Chart into your simulation model from the folder UserInterface in the Class Library or from the toolbar User Interface in the Toolbox .

<!-- image -->

The Chart graphically displays the data sets that Plant Simulation recorded during a simulation run.

You can select to show:

- Data from a table, into which you saved the simulation results, for example.
- Data from input channels you define, that dynamically record the values of attributes of objects that your are interested in.

To show statistics values of an object in the Chart , which you inserted into a Frame , you can use drag-and-drop:

<!-- image -->

| To                                                       | Drag a                                        | To a   |
|----------------------------------------------------------|-----------------------------------------------|--------|
| Show the statistics of a material flow object            | material flow object, Portioner , DePortioner | Chart  |
| Show the frequency distribution of the number of MUs     | PlaceBuffer , Buffer , Store                  | Chart  |
| Show the contents of a table                             | DataTable , TimeSequence , MaterialsTable     | Chart  |
| Show the value of the Variable you inserted into a Frame | Variable                                      | Chart  |

- To apply the settings you selected in the dialog and to show the records, click Apply . When you resize the display window, Plant Simulation also resizes the shown graph.
- To show the data the Chart collected in the display window, click Show Chart .
- To open the dialog of the Chart , double-click anywhere in the display window.
- To make a Chart of type Histogram or Plotter collect data during the simulation run, select Collect data in the dialog. To deactivate data collection, clear the check box.

- To delete all values that the Chart collected, select Tools &gt; Reset Values .

The Chart lets you select settings in a number of ways. You can:

- Select Settings in the Statistics Wizard
- Select Where the Data Comes From
- Select How the Chart Shows the Data
- Add Labels and a Legend
- Add Annotations

When you select another Category , the Chart in 2D automatically shows the icon of this category in the Frame window.

<!-- image -->

Compare Viewing the Statistics Report

Compare View Statistics in the Dialogs of the Objects

Compare Show Statistics with Display Panels in the 2D Model

Compare Show Statistics and Other Values in a Report

Compare Show Values During the Simulation with the Display

Compare Accessing Statistics with SimTalk

Back to View and Visualize Statistics

Select Settings in the Statistics Wizard

A Chart , which you insert into a Frame , provides the Statistics Wizard . Right-click the Chart and select Statistics Wizard on the context menu.

<!-- image -->

<!-- image -->

- Select the class(es) of object(s) for which you would like to show statistical data in the Chart under the group box Class . The Chart only adds material flow objects to the display for which you selected the check box Resource Statistics on the Tab Statistics .
- Select the type(s) of resource(s) for which you would like to show statistics of the selected object(s) in the Chart from the drop-down list box Resource type : Production , Transport or Storage . Select the Resource Type on the tab Statistics of an object collecting statistical data. Use the check boxes in the Statistics Wizard to restrict which objects Plant Simulation shows.

<!-- image -->

- If you would like Plant Simulation to also show statistical data of objects within Frames that you inserted into the Frame in which the Chart is located, select the check box Include Subframes .
- Select the criterion which Plant Simulation uses when sorting statistical data from the drop-down list Sort Criterion : Either the Name of the object, or one of the states it is in: Working , Setting-Up , Waiting , Blocked , Powering up/down , Failed , Stopped , or Paused .

To sort the stations by their Name in alphabetical order from A to Z, select Sort Criterion &gt; Name . To sort the stations in the order that meets your needs, drag the stations onto the Chart in the order it is to show them. To change the order at a later point in time, edit the table of the Input Channels by cutting the respective columns of the objects and pasting them in the desired order.

- Finally, click OK to open the display window of the Chart with the settings you selected in the dialog.

**Back to Show Statistics in a Chart**

##### Select Where the Data Comes From

Before you start your simulation run, you can tell the Chart what to use as the source of the data it displays and in which mode it collects data.

- Select the Data Source , i.e., whether the Chart takes the data you want to display from a set of input channels or from a table.
- To show values of channels you define in a data table, select Input Channels from the drop-down list.

<!-- image -->

To open a table into which you can type the input channels, click Data Table . These channels are, as a rule, the paths to attributes , read-only attributes , or methods of objects, whose values you want to display. You can also type in complex expressions, such as the sum of two attributes, etc.

Type in any text you want to add as the legend to the Chart into the row index.

For the Statistics type &gt; Resource we pre-configured the following entries in the Statistics Wizard :

<!-- image -->

- To show the contents of a table as a diagram, select Data Table . This might, for example, be a table into which you saved the results of a simulation run.

Type in the name and the path of the data table containing the data, or click the button and select the table in the dialog Select Object .

Type in the Range of the table cells you want to show.

- ◊ To show all cells in all columns and rows, type in {*,*}..{*,*} .
- ◊ To show the first four cells of column one, type in {1,1}..{1,4} .
- ◊ To show all cells in column one, type in {1,1}..{1,*} .

<!-- image -->

You can also type in negative numbers:

- ◊ To show the one but last column of the table, type in {-2,*}..{-2,*} .
- ◊ To show the one but last and the last column, type in {-2,*}..{*,*} .
- Select which mode the Chart uses to update the data it shows.
- Sample mode updates the Chart periodically and takes the next sample after the time span which you type into the text box Interval .
- Watch mode updates the Chart , whenever the value of a watchable read-only attribute , for example NumMU , NumMUParts , StatMaxNumMU , StatNumIn , StatNumOut , etc. or of a watchable attribute changes, for example Pause , Speed , Unplanned , etc.
- The column Watchable in the window Show Attributes and Methods of the individual objects shows all attributes , read-only attribute , and methods that Plant Simulation can watch.
- Plot mode updates the Chart , whenever a simulation event takes place.

**Back to Show Statistics in a Chart**

Selecting How the Chart Shows the Data

Select How the Chart Shows the Data After you have selected where the Chart takes the data from that it displays, you will select the settings for displaying this data.

You can:

- Show a number of values or several sets of a number of values, see Show Values in a Chart .
- Show a number of values or several sets of a number of values in a three dimensional Chart , see Show Values in a 3D Chart .
- Show the frequency distribution for one or several input channels, see Show Values in a Histogram .
- Show the frequency distribution for one or several input channels in a three dimensional Chart , see Show Values in a 3D Histogram .
- Show the progression of one or more values over time, see Show Values as the Chart Plots Them .

**Note**

When you select another Category , the Chart automatically shows the icon of this category in the Frame into which you inserted it.

- Show a number of x-y pairs of values or several sets of x-y pairs of values, see Show Values as an XY Graph .

**Back to Show Statistics in a Chart**

Show Values in a Chart

<!-- image -->

To show a number of values or several sets of a number of values as a chart, click the tab Display and select Chart from the drop-down list Category .

To make the Chart collect data during the simulation run, select Collect data in the dialog. To deactivate data collection, clear the check box.

Back to Select How the Chart Shows the Data

<!-- image -->

Show Values in a 3D Chart

To show a number of values or several sets of a number of values as a 3D chart, click the tab Display and select 3D Chart from the drop-down list Category .

To make the Chart collect data during the simulation run, select Collect Data in the dialog. To deactivate data collection, clear the check box.

<!-- image -->

You can, for example hang the 3D Chart onto the wall of your factory, thus vastly improving visibility and showing the operators the utilization of the machines at a glance.

Back to Select How the Chart Shows the Data

<!-- image -->

Show Values in a Histogram

<!-- image -->

To show the frequency distribution for one or several input channels as a histogram, click the tab Display and select Histogram from the drop-down list Category . A histogram graphically summarizes the distribution of a data set.

To make the Chart collect data during the simulation run, select Collect Data in the dialog. To deactivate data collection, clear the check box.

Back to Select How the Chart Shows the Data

<!-- image -->

Show Values in a 3D Histogram

To show the frequency distribution for one or several input channels as a 3D histogram, click the tab Display and select 3D Histogram from the drop-down list Category . A histogram graphically summarizes the distribution of a data set.

To make the Chart collect data during the simulation run, select Collect data in the dialog. To deactivate data collection, clear the check box.

Back to Select How the Chart Shows the Data

<!-- image -->

###### Show Values as the Chart Plots Them

<!-- image -->

To show the progression of one or more values over time, click the tab Display and select Plotter from the drop-down list Category .

To make the Chart collect data during the simulation run, select Collect Data in the dialog. To deactivate data collection, clear the check box.

Back to Select How the Chart Shows the Data

<!-- image -->

###### Show Values as an XY Graph

To show a number of x-y pairs of values or several sets of x-y pairs of values, click the tab Display and select XY Graph from the drop-down list Category .

**Note**

You can only show values as an XY graph, when you select Data &gt; Data Source &gt; Data Table .

<!-- image -->

Our table containing the data that we want to show, looks like this:

<!-- image -->

- When we select Data in Column , the XY graph looks as shown below. The XY graph shows the content of the row index as the Legend .

<!-- image -->

We selected the Range from 0 to 5.5, which is shown on the y axis, on the tab Axes .

<!-- image -->

On the tab Labels we selected to show the Legend below the chart.

We set the Color , the Line Weight , and the Marker Type of the Line With Markers on the tab Color .

<!-- image -->

- If we select Data in Row , we have to transpose the respective data in the table.

Back to Select How the Chart Shows the Data

###### Select the Chart Type

Select the type of Chart for displaying the recorded data. A record consists of the entries of a row or a column, depending on the setting you selected under Display &gt; Data .

<!-- image -->

Depending on the Category you selected ( Chart , Histogram , or Plotter ), the Chart provides some or all of the following chart types:

| Category             | Description                                                                                                                                                                                                                    |
|----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Columns              | Shows each record as a column. When displaying several records, the Chart places the columns next to each other. Use this to compare values across categories.                                                                 |
| Stacked Columns      | Shows each record as a column. When displaying several records, the Chart places the columns of the individual records on top of each other. It stacks positive values upward, negative values downward.                       |
| 100% Stacked Columns | Shows each record as a column, stacked one on top of the other, showing the respective percentage of the entire set of 100 percent.                                                                                            |
| Bars                 | Shows each record as bars positioned horizontally on top of each other. When displaying several records, the Chart places the bars of the individual records next to each other. Use this to compare values across categories. |
| Stacked Bars         | Shows each record as a set of bars stacked horizontally next to each other. Positive values are stacked to the right, negative values are stacked to the left.                                                                 |

| Category                     | Description                                                                                                                                                                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 100% Stacked Bars            | Shows each record as a set of bars, one stacked horizontally next to each other, showing its respective percentage of the entire set of 100 percent.                                                                                                                                 |
| Area                         | Shows each record as areas. When displaying several records, the Chart stacks the areas from the individual records one behind the other. Use this to show the trend of the contribution of each value over time or categories.                                                      |
| Stacked Area                 | Shows each record as areas. When displaying several records, the Chart stacks the areas from the individual records one on top of the other.                                                                                                                                         |
| 100% Stacked Area            | Shows each record as a set of areas, one stacked on top of the other, showing the respective percentage of the entire set of 100 percent. Displays the trend of the percentage each value contributes over time or categories.                                                       |
| Line                         | Shows each record as a line.                                                                                                                                                                                                                                                         |
| Line with Markers            | Shows each record as a line with markers.                                                                                                                                                                                                                                            |
| Spline                       | Shows each record as a curve.                                                                                                                                                                                                                                                        |
| Spline with Markers          | Shows each record as a curve with markers.                                                                                                                                                                                                                                           |
| Markers                      | Shows each record as a set of different markers.                                                                                                                                                                                                                                     |
| Points and Best Fit Conveyor | Shows each record as a set of data points, and fits the best straight line to them. The line is calculated from least-squares-approximations of the data set.                                                                                                                        |
| Points and Best Fit Curve    | Shows each record as a set of data points, and fits the best curved line to them. The curve is calculated from least-squares-approximations of the data set.                                                                                                                         |
| Pie                          | Shows each record as a slice of a pie, depicting its percentage of the whole. Enter a negative prefix, so that the Chart offsets this slice from the rest of the pie. Use the scrollbar to scroll from record to record. Use this to show the contribution of each value to a total. |
| XY Points                    | Shows x-y pairs as data points. The first record contains the x-coordinates. The Chart interprets all additional records as the associated y-coordinates. Use this to compare pairs of values.                                                                                       |
| Line                         | Shows x-y pairs as data points and connects them with a line. The first record contains the x-coordinates. The Chart interprets all additional records as the associated y-coordinates.                                                                                              |
| Sticks                       | Shows a vertical bar for each x-y pair, starting from the zero line. The first record contains the x-coordinates. The Chart interprets all additional records as the associated y-coordinates.                                                                                       |
| Area                         | Shows the connected points belonging to the x-y pairs and fills the areas thus created. The first record contains the x-coordinates. The Chart interprets all additional records as the associated y-coordinates.                                                                    |
| 3D Columns                   | Shows each record as columns stacked in three-dimensional space. To turn the chart left or right you can enter an angle of Rotation or you can also drag the                                                                                                                         |

| Category      | Description                                                                                                                                                                                                                                                                                               |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 3D Wire Frame | Shows each record as wire-frames stacked in three-dimensional space. To turn the chart left or right you can enter an angle of Rotation or you can also drag the horizontal slider in the display window. To turn the chart up or down, you can enter and the Height or you can drag the vertical slider. |
| 3D Surface    | Shows each record as solid areas stacked in three-dimensional space. To turn the chart left or right you can enter an angle of Rotation or you can also drag the horizontal slider in the display window. To turn the chart up or down, you can enter the Height or you can drag the vertical slider.     |

##### Back to Select How the Chart Shows the Data

Select Additional Display Options

- Select how the Chart show the records i.e., the entries of a row or of a column.
- Graph show the records as a graph only in the display window.
- Table show the records as a table, i.e., as text only in the display window. Select a font and a relative font size on the tab Font .
- Graph and Table show the records as a graph and as a table in the display window.
- Select how the Chart show the data . This way you can present different views of the same record.

<!-- image -->

<!-- image -->

- If you want to, you can also select a 3D Effect for some of the Chart Types :
- None adds no 3D effect to the Chart Type you selected.
- Shadow adds a black shadow to the chart type you selected.
- 3D adds three-dimensional depth to the chart type you selected.
- Gradient Bars adds an effect between a gradient and a 3D look to the chart type you selected.
- Contoured for the chart types 3D Columns and 3D Surface .

You can also type in the Rotation angle and the Height of the columns/surface. To turn the chart left or right, drag the horizontal slider in the display window. To turn it up or down, drag the vertical slider.

<!-- image -->

<!-- image -->

**Note**

Some chart types do not provide 3D effects .

- To change the background color of the Chart proper in the display window, click the tab Color . Doubleclick the cell labeled Background and select another color. Click Apply to change the color.
- To change the color around the Chart proper in display window, click the tab Color . Double-click the color field next to Desk and select another color. Click Apply to change the color.
- To display the Chart in the Frame , instead of the icon of the object, select Display in frame on the tab Display .
- We advise to increase the size of the icon of the Chart in the Frame : Hold down Shift + Ctrl , grab one of the four corners of the icon with the mouse and drag the icon to a convenient size.
- To interrupt the line the Chart draws for values that are not defined, select Gap when null on the tab Display . To continue drawing the line, clear the check box.
- To print the Chart , select Tools &gt; Print .
- To copy the contents of the display window to the Clipboard is a bitmap, select Tools &gt; Copy to Clipboard . You can then paste it into another application with Ctrl+V or Home &gt; Paste .
- To show Grid lines in the x-axis in the display window, select X-axis on the tab Axes . Type in the maximum number of grid lines on the x-axis. This feature is especially handy, when the Chart displays

<!-- image -->

<!-- image -->

numerous points within a limited space, and you want to regulate how many grid lines the display window shows.

To hide them, clear the check box.

<!-- image -->

**Compare these screenshots:**

<!-- image -->

- To show grid lines on the y-axis in the display window, select Y-axis . To hide the grid lines, clear the check box.
- To set the range the Chart is to display scaled on the y-axis, type the first value of into the left text box. The default setting 0 … 0 means that Plant Simulation scales automatically.

Type the last value of the range the Chart is to display scaled on the y-axis into the right text box.

**Note**

When you type in neither Title for Subtitle , the Chart might, under certain circumstances, cut off the upper part of the y Range . To prevent this, you can type a blank space into the text box Subtitle .

<!-- image -->

**Compare these screenshots:**

Back to Select How the Chart Shows the Data

<!-- image -->

##### Add Labels and a Legend

Naturally, you will also want to add a title and a subtitle to your chart, and format them, add text to the x-axis and to the y-axis, and add a legend that tells what the values mean.

<!-- image -->

- Enter any text that Plant Simulation shows as the title of the Chart in the display window into the text box Title . In our example we entered Utilization of the Stations .
- Select a font, if you want to Bold face or Italicize the text and a relative font size on the tab Font .

<!-- image -->

Select a color for all text in the display window on the tab Color . Double-click the color field next to Font and select another color. Click Apply to change the color.

<!-- image -->

- Enter any text that Plant Simulation shows as the subtitle of the Chart in the display window into the text box Subtitle . In our example we entered Engine Plant Anytown .
- Enter any text that Plant Simulation shows in the display window on the x-axis. In our example we entered Station .

Select a font, if you want to Bold face or Italicize the text and a relative font size on the tab Font .

**Note**

This font applies to all labels, except for the Title , the Subtitle and data displayed in Table format in the display window

- Enter any text that Plant Simulation shows in the display window on the y-axis. In our example we entered Percent of 100 .
- Select if and on which side of the display window Plant Simulation shows the legend for the values the Chart displays.

As you remember, you enter the text you want to show as the legend into the row index of the table when you select Data Source &gt; Input Channels &gt; Table File .

Back to Show Statistics in a Chart

<!-- image -->

##### Add Annotations

If need be, you can also add additional lines and/or text to the display window. Click Annotations and fill in the table that opens.

<!-- image -->

- Enter any text that Plant Simulation shows as the title of the Chart in the display window into the text box Title . In our example we entered Utilization of the Stations .
- Select a font, if you want to Bold face or Italicize the text and a relative font size on the tab Font .

<!-- image -->

Select a color for all text in the display window on the tab Color . Double-click the color field next to Font and select another color. Click Apply to change the color.

<!-- image -->

- Enter any text that Plant Simulation shows as the subtitle of the Chart in the display window into the text box Subtitle . In our example we entered Engine Plant Anytown .
- Enter any text that Plant Simulation shows in the display window on the x-axis. In our example we entered Station .

Select a font, if you want to Bold face or Italicize the text and a relative font size on the tab Font .

**Note**

This font applies to all labels, except for the Title , the Subtitle and data displayed in Table format in the display window

- Enter any text that Plant Simulation shows in the display window on the y-axis. In our example we entered Percent of 100 .
- Select if and on which side of the display window Plant Simulation shows the legend for the values the Chart displays.

As you remember, you enter the text you want to show as the legend into the row index of the table when you select Data Source &gt; Input Channels &gt; Table File .

<!-- image -->

- Select the Type of the annotation:

Select

0: Vertical Line for displaying a vertical line.

Select

1: Horizonal Line for a displaying a horizontal line.

**Add Annotations**

Select

2: X-axis Label for labeling the x-axis.

Select

3: Y-axis Label for labeling the y-axis.

Select

4: Text for any text.

- Value : Enter the value where the Chart displays the line in the display window. For a horizontal line or for an annotation of the Y axis or for this is the Y value. For a vertical line or for an annotation of the X axis this is X value.

Y values are specified in the Y scale of the Chart .

X values are specified in the X scale of the Chart . For a bar chart the value 3.5 means that the X value is placed between the third and the fourth bar.

- From : Enter the starting point of the line here. If you do not enter a value, the Chart extends an existing line. This way you can not only create horizontal and vertical lines but also diagonal lines.

For a horizontal line or for text this is an X value. For a vertical line this is a Y value.

- To : Enter the end point of the line here. If you do not enter a value in the cells From and To , the Chart draws the line from the left to right, or from the top to the bottom of the display window.

For a horizontal line this is a X value. For a vertical line this is a Y value.

- Color : Enter the number of the color of the line here. This is the number of one of the lines you defined on the tab Color .
- Style : Enter the style of the line here, such as dotted, dashed, etc.

For lines of Type 0 or 1 , you can enter the line style. For text of Type 4 , you can enter the marker style.

|   Value | Line style                | Marker style               |
|---------|---------------------------|----------------------------|
|       0 | a thin solid line         | text only without a marker |
|       1 | a dashed line             | a plus sign                |
|       2 | a dotted line             | a cross                    |
|       3 | a dash-dot line           | a circle                   |
|       4 | a dash-dot-dot line       | a filled circle            |
|       5 | a medium thin solid line  | a square                   |
|       6 | a thick solid line        | a filled square            |
|       7 | a grid tick               | a diamond                  |
|       8 | a grid line               | a filled diamond           |
|       9 | none                      | upward triangle            |
|      10 | a medium thick solid line | solid upward triangle      |
|      11 | an extra thick solid line | downward triangle          |
|      12 | none                      | solid downward triangle    |

|   Value | Line style   | Marker style                  |
|---------|--------------|-------------------------------|
|      13 | none         | small plus                    |
|      14 | none         | small cross                   |
|      15 | none         | small circle                  |
|      16 | none         | small solid circle            |
|      17 | none         | small square                  |
|      18 | none         | small solid square            |
|      19 | none         | small diamond                 |
|      20 | none         | small solid diamond           |
|      21 | none         | small upward triangle         |
|      22 | none         | small solid upward triangle   |
|      23 | none         | small downward triangle       |
|      24 | none         | small solid downward triangle |
|      25 | none         | large plus                    |
|      26 | none         | large cross                   |
|      27 | none         | large circle                  |
|      28 | none         | large solid circle            |
|      29 | none         | large square                  |
|      30 | none         | large solid square            |
|      31 | none         | large diamond                 |
|      32 | none         | large solid diamond           |
|      33 | none         | large upward triangle         |
|      34 | none         | large solid upward triangle   |
|      35 | none         | large downward triangle       |
|      36 | none         | large solid downward triangle |
|      92 | none         | arrow north                   |
|      93 | none         | arrow north east              |
|      94 | none         | arrow east                    |
|      95 | none         | arrow south east              |
|      96 | none         | arrow south                   |

<!-- image -->

|   Value | Line style   | Marker style     |
|---------|--------------|------------------|
|      97 | none         | arrow south west |
|      98 | none         | arrow west       |
|      99 | none         | arrow north west |

- Text : Enter any text that describes the line.

<!-- image -->

| Prefix   | Position                        |
|----------|---------------------------------|
| &#124;l  | left inside edge of the graph   |
| &#124;L  | left outside edge of the graph  |
| &#124;r  | right inside edge of the graph  |
| &#124;R  | right outside edge of the graph |
| &#124;c  | centered inside of the graph    |

**Back to Show Statistics in a Chart**

#### Show Statistics and Other Values in a Report

If you want to present all of the results of a simulation run, which Plant Simulation outputs to tables and diagrams, on an HTML page on screen, you will use the object HtmlReport . You can also print, and save, this HTML page for sharing it with your colleagues or for displaying it on a website.

You can insert the HtmlReport into your simulation model from the folder UserInterface in the Class Library or from the toolbar User Interface in the Toolbox .

<!-- image -->

<!-- image -->

Creating a report is really quick and comfortable:

- Type in the name of the object in brackets on the tab Content and highlight the name. Click on the toolbar and enter the required settings into the dialog Object Parameters . The dialog offers different settings for the different objects.

<!-- image -->

To open the dialog Object Parameters for an object, which you added to the tab Content with

<!-- image -->

drag-and-drop , click the mouse between the name of the object and the closing bracket, and click .

<!-- image -->

Then, select the settings you need in the dialog Select Object .

- Enter the content, which the HtmlReport shows, as text on the Tab Content of the object. As you will see, the syntax is easy to understand allowing you to quickly type in the required instructions.

<!-- image -->

To open the dialog Object Parameters for an object, which you added to the tab Content with drag-and-drop , click the mouse between the name of the object and the closing bracket, and click Then, select the settings you need in the dialog Select Object .

In our example below, we'll introduce the most important items which you can add to your report.

.

- To address an object, we entered its name within brackets, [ MyStation] in our example.
- To show the icon named logo of the object HtmlReport and to zoom the icon when zooming the report window, we entered an exclamation mark followed by the name of the icon enclosed in brackets followed by an asterisk. The asterisk denotes the icon will be zoomed in/out as well.

[!self, logo, *]

To show the picture of your company, for example its logo, add it as an icon to the object HtmlReport and name it logo . In our example below, we used the Siemens logo.

<!-- image -->

- To show a heading of level 1 , we entered a number sign # followed by the title of the heading:
- To show body text , we entered:
- To show a numbered list , we entered 1. followed by the text we want to display.

**General Information**

Below we provide:

```simtalk
1. An **overview** of the model 1. Various **statistics tables** 1. A **resource chart**
```

To bold text, we enclosed it with two asterisks ** .

- To show a heading of level 2 , we entered two number signs ## followed by the title of the heading:
- To show body text , followed by a bulleted list , we entered the body text, followed by a * denoting the bullet, and the text we want to display.

**Model Overview**

Below we provide this information about the simulation model: * Model file: [=modelFile] * Simulation root: [EventController.Location] * Simulation time: [EventController.SimTime] * End time: [EventController.EndTime]

- To show a formula , we entered the equal sign = followed by the name of the function enclosed in brackets :
- To show the value of the attribute SimTime of the EventController , we entered the name of the object followed by the name of the attribute enclosed in brackets :
- To show a heading of level 2 , followed by a screenshot of the Frame containing our model, we entered:

* Model file: [=modelFile]

```simtalk
* Simulation time: [EventController.SimTime]
```

**Simulation Model The simulation model looks like this: ><**[current, "Test Simulation"]****

The expression Test Simulation is the caption that is shown below the screenshot.

The greater than sign followed by a less-than sign &gt;&lt; centers the screenshot.

- To show the values of objects of type DataTable from our model:
- We selected the DataTable/List whose values you would like to show. We then clicked OK .
- We entered the caption which the HtmlReport shows below the DataTable .
- We entered the identifiers of the columns of the DataTable which the HtmlReport shows on the HTML page.
- Instead, we can also directly type in the respective instructions, compare the example below:

<!-- image -->

<!-- image -->

**Statistics Tables These **statistics values** are of general interest. Feel free to add more. ## Drain Statistics Drain statistics shows the contents of the *summary report* table. [.MaterialFlow.Drain*]**

**Deliveries**

```simtalk
Delivieries shows the contents of the table object *DeliveryList.*
```

[DeliveryList]

- To show the contents of objects of type Chart from our model as screenshots:
- We selected the Chart which you would like to show. We then clicked OK .
- We entered the Caption which the HtmlReport shows below the Chart .
- We entered the Image Width with which the HtmlReport shows the picture of the object. You can also enter an asterisk ( * ) for either the Width or the Height to ensure that the image will not be distorted.
- We entered the Image Height with which the HtmlReport shows the picture of the object. You can also enter an asterisk ( * ) for either the Width or the Height to ensure that the image will not be distorted.

<!-- image -->

<!-- image -->

We clicked OK to apply our settings.

Instead, we can also directly type in the respective instructions, compare the example below:

**Resource Chart The *resource chart* for the *Stations* look like this. Feel free to add more. ## Stations The utilization of the processing  *Stations* is as follows: ><[StationChart, 150, 100]**

The numbers 150 and 100 designate the Width and the Height of the screenshot.

The greater than sign followed by a less-than sign &gt;&lt; centers the screenshot.

- To show a solid horizontal line between the contents of the Report proper and the footer, we entered:

---

- To show a footer containing indented text , designated by the greater sign &gt; , the current date and a signature , we entered the following HTML tag :

> Cedar Rapids, [=day(sysdate)].[=month(sysdate)].[=year(sysdate)+1900] Best regards,

&lt;span style="font-family: Segoe Script; font-size:16pt"&gt;H. Thompson&lt;/ span&gt;

Our finished report with the settings above looks like this:

<!-- image -->

<!-- image -->

Compare Viewing the Statistics Report

Compare Show Reports in a Hierarchically Structured Model

Compare View Statistics in the Dialogs of the Objects

Compare Show Statistics with Display Panels in the 2D Model

Compare Show Statistics in a Chart

Compare Show Values During the Simulation with the Display

Go to Accessing Statistics with SimTalk

Back to View and Visualize Statistics

#### Showing Reports in a Hierarchically Structured Model

Show Reports in a Hierarchically Structured Model

In this example we show how to clearly arrange and model a complex production facility and generate reports with objects of type HtmlReport . We also demonstrate inheritance of our user objects which we created in the folder UserObjects .

We insert an HtmlReport into each of our sub-Frames and rename it to ReportObject . The expression ReportObject is a special name that the programmers built in so that Plant Simulation then uses this object when we reference the Frame in the HtmlReport in brackets.

To do so, we entered these instructions into the overall HtmlReport of the car assembly model, i.e., into .Models.MyCarAssembly.HtmlReport :

**Production Areas The car assembly encompasses three production areas: * CarBody * PaintShop * FinalAssembly [CarBody, #]        // Show the HtmlReport of the Frame 'CarBody' instead of the Frame itself [PaintShop, #]      // Show the HtmlReport of the Frame 'PaintShop' instead of the Frame itself [FinalAssembly, #]  // Show the HtmlReport of the Frame 'FinalAssembly' instead of the Frame itself**

The overall report of our car assembly gathers all objects named ReportObject during the simulation and then shows them.

To add the HtmlReport to your simulation model, click Manage Class Library &gt; Basic Objects &gt; UserInterface &gt; HtmlReport on the Home ribbon tab.

<!-- image -->

As we want to present a visually pleasing simulation model, we create a 3D only model .

We will demonstrate how to:

- Create the Classes of the Cells and the Lines
- Model the Installation and Configure the Components
- Run the Simulation and Show the Report
- Study the HtmlReport

If you do not want to re-create the model yourself, you can also open and study the sample model UserInterface &gt; HtmlReport &gt; Hierarchical Reports . Click Start Page on the Window ribbon tab. Then, click Getting Started &gt; Example Models &gt; Small Examples .

<!-- image -->

Compare Show Statistics and Other Values in a Report

Back to View and Visualize Statistics

Compare HtmlReport &gt; Tab Content

**Creating the Classes of the Cells and the Lines**

##### Create the Classes of the Cells and the Lines

As we do not want to change the default settings of the built-in objects, we duplicate the built-in Frames and objects in the Class Library and then work with these duplicated classes in the folder UserObjects :

- First, we create the classes of our cells and lines. To do so, click the folder UserObjects with the right mouse button and select New &gt; Glass Box Frame . This creates a Frame that shows its content toward the outside.

<!-- image -->

Repeat this twice and rename our Frames that represent our cells and lines. We renamed our Frames to CarBodyCell , PaintShop , and AssemblyLine .

- Then, we duplicate the object Comment in the folder UserInterface . Plant Simulation automatically places the duplicated object into the folder UserObjects . We renamed our Comment to ToDo .
- We need this independent class of the Comment so that Plant Simulation gathers the instances with the name ToDo during the simulation run and displays them. The report in our plant as a whole shows a HTML page/a topic with the tasks that are still to be done. When you click an individual task, Plant

Simulation opens the respective object of type Comment . Then, click in the dialog on Navigate &gt; Open Location to open the location/ Frame , in which this Comment is inserted.

- In addition we add the objects to the toolbar UserObjects in the Toolbox . Class Library and Toolbox then look like this:

<!-- image -->

Then we will:

- Model the Car Body Cell
- Model the Paint Line
- Model the Assembly Line

To display the data of the instances of the UserObjects consistently and in a structured way, we inserted an object of type HtmlReport each into the classes of our Frames and then renamed it to ReportObject . Then Plant Simulation shows this object instead of the Frame on the HTML page in our overall report of the car assembly.

To do so, we entered these instructions into the overall HtmlReport of the car assembly model, i.e., in .Models.MyCarAssembly.HtmlReport :

**Production Areas The car assembly encompasses three production areas: * CarBody * PaintShop * FinalAssembly [CarBody, #]        // Show the HtmlReport of the Frame 'CarBody' instead of the Frame itself [PaintShop, #]      // Show the HtmlReport of the Frame 'PaintShop' instead of the Frame itself [FinalAssembly, #]  // Show the HtmlReport of the Frame 'FinalAssembly' instead of the Frame itself**

**Back to Show Reports in a Hierarchically Structured Model**

Modeling the Car Body Cell

Model the Car Body Cell

Our CarBodyCell consists of the material flow objects Interface/Entrance , two AssemblyStations between which a Buffer each is located, and an Interface /Exit . The three Sources named CarBody , Trunk , and Roof provide the AssemblyStations with parts.

We also inserted an HtmlReport which we renamed to ReportObject and a Chart as a Histogram which we renamed to BufferOccupancy .

<!-- image -->

As we want to show the object names in our 3D window , we select the respective object, press the spacebar, and change to the tab Captions in the dialog. There we activate the check box Name/Label Activated . We repeated this for all objects.

<!-- image -->

In our CarBodyCell we will:

- Configure the Assembly Stations That Assemble the Parts
- Configure the Sources That Provide the Assembly Stations With Parts
- Configure the Buffers between the Assembly Stations
- Configure the Chart as Histogram
- Configure the ReportObject of the Car Body Cell

Back to Show Reports in a Hierarchically Structured Model

Configure the Assembly Stations That Assemble the Parts

To configure our AssemblyStations which assemble the delivered parts

- Select a normally distributed processing time . We typed in these parameters: 10:00, 2:00, 0, 20:00 .

<!-- image -->

- Create a failure with these default values:
- Activate the energy settings on the tab Energy .

<!-- image -->

We did not change any other settings.

<!-- image -->

To configure AssemblyStation1 :

- Select a normally distributed processing time . We typed in these parameters: 15:00, 3:00, 0, 20:00 .

<!-- image -->

- Create a failure with these values:
- Activate the energy settings on the tab Energy .

<!-- image -->

<!-- image -->

We did not change any other settings.

To configure AssemblyStation2 :

- Select a normally distributed processing time . We typed in these parameters: 4:00, 2:00, 0, 6:00 .

<!-- image -->

- Create a failure with these values:
- Activate the energy settings on the tab Energy .
- We did not change any other settings.

<!-- image -->

<!-- image -->

Back to Model the Car Body Cell

Configure the Sources That Provide the Assembly Stations With Parts

To configure the three Sources that provide the three AssemblyStations with parts:

- For the Source named CarBody we entered a constant Interval of 10:00 minutes between the creation events.
- We use the Sources named Trunk and Roof with the default settings.

<!-- image -->

**Back to Model the Car Body Cell**

Configure the Buffers between the Assembly Stations

To configure the two Buffers , named Buffer and Buffer1 , which we inserted between the AssemblyStations :

- Enter their Capacity . We typed in 4 each.

<!-- image -->

- We did not change any other settings.

Back to Model the Car Body Cell

Configure the Chart as Histogram

To configure our Chart named BufferOccupancy as a histogram , double-click the icon of the Chart :

- Change to the tab Display and select the Category &gt; Histogram .
- Drag the two Buffers , named Buffer and Buffer1 , one after the other to the icon of the Chart and drop them there. This sets the Data source &gt; Input Channels and enters the Buffers into the table of the input channels.

<!-- image -->

<!-- image -->

We did not change any other settings.

**Back to Model the Car Body Cell**

Configure the ReportObject of the Car Body Cell

To configure the ReportObject of the CarBodyCell we have to decide which data we want to show. We entered these instructions. The comments after the instructions explain what the code executes.

```simtalk
**[current.name]               // name of the Frame as heading on the first level The above car body cell looks like this: // descriptive text ## Layout                      // second level heading ><[current, *]                 // centered screenshot, adjusted to maximum window width ## Buffer Occupancy            // second level heading The occupancy of the individual Buffers looks like this: // descriptive text ><[BufferOccupancy, 150, 100]  // centered screenshot of the buffer occupancy, // size of the screenshots is 150 mm times 100 mm [Buffer]                       // show statistics values of the object 'Buffer' as a table [Buffer1]                      // show statistics values of the object 'Buffer1' as a table ## Statistics                  // second level heading Statistics of the AssemblyStations and the Buffers looks like this: // descriptive text [AssemblyStation, "Assembly statistics"]    // show statistics values of the object 'AssemblyStation' as // a table, "Assembly**
statistics" is the caption of the table [AssemblyStation1]             // show statistics values of the object 'AssemblyStation1' as a table [AssemblyStation2]             // show statistics values of the object 'AssemblyStation2' as a table [Buffer, "Buffer statistics ", %MatFlowProperties]    // show statistics values of the object // 'Buffer' as a table // "Buffer statistics" is the caption of the table // % MatFlowProperties shows the material flow properties [Buffer1]                      // show statistics values of the object 'Buffer1' as a table
```

When we run the simulation after we finished modeling, Plant Simulation gathers the individual HtmlReports named ReportObject from all sub-Frames and shows them in the overall report of the car assembly model.

**Back to Model the Car Body Cell**

Modeling the Paint Line

Model the Paint Line

Our PaintLine consists of an Interface/Entrance , three Conveyors named Preparing , Painting , and Drying , and of an Interface/Exit . We also inserted an HtmlReport and renamed it to ReportObject .

<!-- image -->

To configure the Conveyor named Preparing :

- Insert it with a Length of 6 meters.

- Create a failure with these default values:

<!-- image -->

We did not change any other settings.

To configure the Conveyor named Painting :

- Insert it with a Length of 8 meters.
- Create a failure with these values:

<!-- image -->

We did not change any other settings.

To configure the Conveyor named Drying :

- Insert it with a Length of 6 meters.
- Create a failure with these default values:

<!-- image -->

We did not change any other settings.

To define the HtmlReport named ReportObject of the PaintLine , we typed in these instructions:

**[current.name] The above paint line of the car assembly looks like this: ## Layout ><[current, *] ## Statistics Statistics of our paint lines look like this: ><[Painting, "Flow statistics", %MatFlowProperties] [Preparing] [Drying]**

When we run the simulation after we finished modeling, Plant Simulation gathers the individual HtmlReports named ReportObject from all subframes and shows them in the overall report of the car assembly model.

**Back to Show Reports in a Hierarchically Structured Model**

Modeling the Assembly Line

Model the Assembly Line

Our AssemblyLine consists of an Interface/Entrance , four Conveyors , three Stations named Step1 , Step2 , and Step3 , and of an Interface/Exit . We attached a Workplace each to each of the Stations . We also inserted an HtmlReport which we renamed to ReportObject and our Comment named ToDo .

<!-- image -->

**We will demonstrate how to:**

- Configure the Conveyors of the Assembly Line
- Configure the Processing Stations and the Workplaces
- Configure the ReportObject of the Assembly Line
- Configure the ToDos of the Assembly Line

Back to Show Reports in a Hierarchically Structured Model

Configure the Conveyors of the Assembly Line

To configure the four Conveyors between the processing stations :

- Insert the first three Conveyors with a length of 5 meters each.
- For the fourth Conveyor , named Conveyor3 , we typed in a length of 4 meters.
- Create a failure each for the Conveyors with these default settings:

<!-- image -->

We did not change any other settings.

**Back to Model the Assembly Line**

Configure the Processing Stations and the Workplaces

To configure the three processing Stations named Step1 , Step2 , and Step3 :

- Create a failure each with these default values:
- Change to the tab Importer and activate the processing importer .

<!-- image -->

Type ~.Broker into the text box Broker . This points to the location of the Broker which controls the Importers . In our case this is the Frame , in which we are going to model the FinalAssembly in our overall model.

<!-- image -->

We did not change any other settings.

- Insert three Workplaces and attach one each to one of the Stations . We use them with their default settings.

Compare Model the Assembly Line

Back to Configure the Final Assembly

Configure the ReportObject of the Assembly Line

To configure the HtmlReport named ReportObject of the AssemblyLine , we typed in these instructions. The comments describe what the source code does.

```simtalk
**[current.name]               // name of the Frame as first level heading The above assembly line of the car assembly looks like this:    // descriptive text ## Layout                      // second level heading ><[current, *]    // centered screenshot, adjusted to maximum width of the window ## Statistics     // second level heading Statistics of the stations Step1, Step2, and Step3              // descriptive text [Step1, "Station statistics"]  // show statistics values of the object 'Step1' as a table // "Station statistics" is the caption of the table [Step2]                        // show statistics values of the object 'Step2' as a table [Step3]                        // show statistics values of the object 'Step3' as a table**
```

**Back to Model the Assembly Line**

Configure the ToDos of the Assembly Line

To configure the Comment of the AssemblyLine named ToDo we typed in these instructions in the tab Comment :

Get the target speed of this AssemblyLine.

<!-- image -->

When we run the simulation after we finished modeling, Plant Simulation gathers the individual Comments named ToDo from all sub-Frames and shows them in the overall report of the car assembly model.

To do so, we entered these instructions into the overall HtmlReport of the car assembly model, i.e., in .Models.MyCarAssembly.HtmlReport :

**ToDo These tasks still have to be completed:**

[.UserObjects.ToDo*]

Back to Model the Assembly Line

Modeling and Configuring the Installation

Model the Installation and Configure the Components

Now that we created the classes of our CarBodyCell , of the PaintShop , and of the AssemblyLine , we can build our simulation model.

We create our car body assembly model in the Frame named Model intended for that in the folder Models in the Class Library . If you want to, you can also rename the Frame Model . We entered MyCarAssembly .

Our car assembly consist of these objects:

- A Source , representing the receiving department, and the PartsTable , defining the parts to be produced.
- An HtmlReport showing the collected data of the individual components of the car assembly.
- Three Frames representing the CarBody , the PaintShop , and the FinalAssembly departments of the assembly plant.

Insert a Frame from the tab MaterialFlow into the Frame MyCarAssembly .

<!-- image -->

By default Plant Simulation inserts a Glass-Box-Frame that shows its content toward the outside in the Frame MyCarAssembly . We want to show our Frames as a Black-Box-Frames though, which do not show their content in the Frame MyCarAssembly . For this reason we have to convert the Glass-Box-Frame to a Black-Box-Frame :

- Click the Frame with the left mouse button and press the spacebar . Change to the tab Graphics .
- Clear the check box Show Content .
- Select the check box Visible for the graphic group named default .
- Do this for each of the three Frames .
- Rename our three Frames . We changed the names to CarBody , PaintShop , and FinalAssembly .

<!-- image -->

The inserted Black-Box-Frame now looks like this.

<!-- image -->

**In the next step we will:**

- Configure the Receiving Department
- Configure the Body Assembly
- Configure the Paint Shop
- Configure the Final Assembly
- Configure the HtmlReport

Back to Show Reports in a Hierarchically Structured Model

Configure the Receiving Department

We model the receiving department with a Source . Proceed as follows:

- Insert a Source from the tab MaterialFlow . Rename it to Receiving .
- Select the Mu Selection &gt; Sequence Cyclical .
- As the setting Sequence Cyclical requires a table, insert an object of type DataTable . We renamed it to PartsTable and entered the PartsTable into the text box Table .

Plant Simulation automatically formats the PartsTable . We entered the data shown below.

<!-- image -->

<!-- image -->

We did not change any other settings.

**Back to Model the Installation and Configure the Components**

###### Configure the Body Assembly

We model the CarBody section of our car assembly plant in a Frame , which we insert from the tab MaterialFlow into the Frame MyCarAssembly .

- Convert the Glass-Box-Frame to a Black-Box-Frame as described under Model the Installation and Configure the Components .
- Click the Frame CarBody with the right mouse button and select Open in New 3D Window .
- Delete the default graphic.
- Insert an Interface .
- Insert our CarBodyCell twice, one above the other.
- Insert a second Interface .
- Connect the Interfaces along the material flow with Connectors with the CarBodyCells . Plant Simulation then renames the Interfaces to Entrance and Exit .
- Insert an HtmlReport .
- Rename it to ReportObject .
- To configure the ReportObject , type in these instructions:

```simtalk
**[current.name] The car body section of our car assembly looks like this: ## Layout**
```

><[current, *] ## CarBodyCells The car body section encompasses several CarBodyCells: [CarBodyCell.Origin*, ##]  // shows the heading two levels lower [EnergyAnalyzer, #]        // shows the heading one level lower

When we run the simulation after we finished modeling, Plant Simulation gathers the individual HtmlReports named ReportObject from all sub-Frames and shows them in the overall report of the car assembly model.

- Insert our Comment named ToDo from the tab UserObjects .

Type in this comment on the tab Comment :

Question: Would adding a third CarBodyCell increase the throughput?

When we run the simulation after we finished modeling, Plant Simulation gathers the individual Comments named ToDo from all sub-Frames and shows them in the overall report of the car assembly model.

- Insert the object EnergyAnalyzer from the tab Tools .

Configure the EnergyAnalyzer for the CarBodyCell :

- ◊ Click the Frame CarBodyCell with the right mouse button and select Open in New 3D Window .
- ◊ This opens the 3D window with the path .Models.MyCarAssembly.CarBody.CarBodyCell . Hold down Ctrl and select the objects AssemblyStation , AssemblyStation1 , and AssemblyStation2 . Drag these objects to the object EnergyAnalyzer in the path .Models.MyCarAssembly.CarBody and drop them there.
- ◊ Repeat this for CarBodyCell1 .

The dialog of the EnergyAnalyzer then looks like this:

<!-- image -->

###### Configure the Paint Shop

We did not change any other settings.

Our ReportObject then shows the energy consumption values of the AssemblyStations after the simulation.

Our finished car body section with the two CarBodyCells looks like this:

<!-- image -->

Go to Study the HtmlReport &gt; Display the Energy Analysis

Back to Model the Installation and Configure the Components

Configure the Paint Shop

We model the PaintShop section of our car assembly plant in a Frame , which we insert from the tab MaterialFlow into the Frame MyCarAssembly .

- Convert the Glass-Box-Frame to a Black-Box-Frame as described under Model the Installation and Configure the Components .
- Click the Frame PaintShop with the right mouse button and select Open in New 3D Window .
- Delete the default graphic.
- Insert an Interface .
- Insert our PaintShop twice, one above the other.
- Insert a second Interface .
- Connect the Interfaces along the material flow with Connectors with the paint lines . Plant Simulation then renames the Interfaces to Entrance and Exit .
- Insert an HtmlReport .
- Rename it to ReportObject .
- To configure the ReportObject , type in these instructions:

**[current.name] The PaintShop section of the car assembly looks like this: ## Layout ><[current, *] ## PaintLines The PaintShop encompasses several PaintLines. [PaintLine.Origin*, ##]**

When we run the simulation after we finished modeling, Plant Simulation gathers the individual HtmlReports named ReportObject from all sub-Frames and shows them in the overall report of the car assembly model.

Our finished PaintShop section with the two PaintLines looks like this:

Back to Model the Installation and Configure the Components

<!-- image -->

###### Configure the Final Assembly

We model the FinalAssembly section of our car assembly plant in a Frame , which we insert from the tab MaterialFlow into the Frame MyCarAssembly .

- Convert the Glass-Box-Frame to a Black-Box-Frame as described under Model the Installation and Configure the Components .
- Click the Frame FinalAssembly with the right mouse button and select Open in New 3D Window .
- Delete the default graphic.
- Insert an Interface .
- Insert our AssemblyLine three times, one above the other.
- Insert a second Interface .
- Connect the Interfaces along the material flow with Connectors with the assembly lines . Plant Simulation then renames the Interfaces to Entrance and Exit .
- Insert the object WorkerPool from the tab Resources . Configure the WorkerPool :
- Click the Inheritance check box for the Creation Table so that it looks like this . Then type 4 into the cell below Amount to create four Workers .

<!-- image -->

- Select the Travel Mode &gt; Beam to Workplace .

<!-- image -->

We did not change any other settings.

- Insert the Broker from the tab Resources . We use the Broker with its default settings.
- Insert the object WorkerChart from the tab Tools .

Type WorkerPool into the text box below Create charts of this WorkerPool .

- Insert an HtmlReport .
- Rename it to ReportObject .
- To configure the ReportObject , type in these instructions:

**[current.name] The final assembly section of the car assembly looks like this: ## Layout ><[current, *] ## Broker Statistics The Broker collected these statistics values: [Broker] ## Worker Chart**

The worker chart shows statistics of all Workers that are staying in the WorkerPool. [WorkerChart] ## Assembly Lines The final assembly section encompasses several assembly lines. [AssemblyLine.Origin*, ##]

When we run the simulation after we finished modeling, Plant Simulation gathers the individual HtmlReports named ReportObject from all sub-Frames and shows them in the overall report of the car assembly model.

**Note**

We created the model in a previous version of Plant Simulation which provided the now deprecated WorkerChart . We can still use it in the model of the current version though as it is part of that model.

- Insert our Comment named ToDo .

Type in this comment on the tab Comment :

Check the availability of AssemblyLine2.

Our finished FinalAssembly with the three assembly lines and the other objects looks like this:

<!-- image -->

Connect the individual sections in the Frame MyCarAssembly with Connectors . Our finished car assembly looks like this:

Back to Model the Installation and Configure the Components

<!-- image -->

###### Configure the HtmlReport

To configure the HtmlReport of the car assembly plant as a whole, we typed in these instructions. We took the General Information topic for the most part from the built-in HtmlReport .

```simtalk
><[!self, Header, *] # General Information ## Overview * Model file: [=modelFile] * Simulation root: [self.location] * Simulation time: [EventController.simtime] *
End time: [EventController.EndTime] * Generated on: [=sysdate] * Contact: <a href="mailto:John.Doe@siemens.com?subject=Simulation report">John.Doe@siemens.com</a> ## Model The car assembly model looks like this: ><[current, *] ## Receiving The receiving section delivers these parts: ><[PartsTable, 1..3] --# Statistics Drain statistics data suffices for our purposes. ## Drain Statistics Drain statistics shows detailed information about the parts that the shipping section removed from the plant. [.MaterialFlow.Drain*] --# Production Areas The car assembly encompasses three production areas: * CarBody * PaintShop * FinalAssembly [CarBody, #] [PaintShop, #] [FinalAssembly, #] --# ToDo These tasks still have to be completed: [.UserObjects.ToDo*] Cedar Rapids, [=day(sysdate)].[=month(sysdate)].[=year(sysdate)+1900] <span style="font-family: Segoe Script; font-size:32pt">>H. Thompson</a>
```

When we run the simulation after we finished modeling, Plant Simulation collects the individual HtmlReports named ReportObject from all sub-Frames and shows them in the overall report of the car assembly model.

Back to Model the Installation and Configure the Components

##### Running the Simulation and Showing the Report

Run the Simulation and Show the Report

After we finished modeling, we can run the simulation and show its results in the report.

In this step we will:

- Run the Simulation
- Show the HtmlReport

Compare Study the HtmlReport

Compare Configure the HtmlReport

Back to Show Reports in a Hierarchically Structured Model

###### Run the Simulation

**To run the simulation:**

- Double-click the EventController in the model MyCarAssembly , change to the tab Settings and type in the time after which the simulation will be terminated.
- We entered one day, i.e., 1:00:00:00 .
- Change to the tab Controls and click to run the simulation.

<!-- image -->

<!-- image -->

**Back to Run the Simulation and Show the Report**

Show the HtmlReport

After the simulation has been terminated, we can click the HtmlReport with the right mouse button and click Show to display it.

During the simulation Plant Simulation collects the individual HtmlReports named ReportObject from all sub-Frames and adds these to the overall report of the car assembly model.

The same applies to the individual Comments named ToDo .

If we want to immediately show the HtmlReport after the simulation is over, we can set this in an endSim method :

- Open the HtmlReport in the model MyCarAssembly and change to the tab User-defined .
- Click New and create a user-defined attribute of Data Type &gt; Method .
- Type in endSim as name.
- Click Open and type in this source code:

<!-- image -->

<!-- image -->

**Note**

When the 3D model contains a large number of objects that the HtmlReport displays, it can take some time before Plant Simulation shows it as it has to render the scene first before taking the screenshots for the HtmlReport .

Back to Run the Simulation and Show the Report

Studying the HtmlReport

Study the HtmlReport When you open the HtmlReport , you will notice that the table of contents shows four heading levels by default. If you want to show fewer heading levels, you can set that with the attribute TOCLevels .

<!-- image -->

We took the topics General Information and Statistics for the most part from the built-in HtmlReport .

###### Display the Production Areas

In addition we want to:

- Display the Production Areas
- Display the Energy Analysis
- Display the ToDos and Change to the Respective Frame

Compare Model the Car Body Cell &gt; Configure the ReportObject

Compare Configure the Body Assembly &gt; Configure the ReportObject

Compare Model the Paint Line &gt; Configure the ReportObject

Compare Configure the Paint Shop &gt; Configure the ReportObject

Compare Model the Assembly Line &gt; Configure the ReportObject

Compare Configure the Final Assembly &gt; Configure the ReportObject

Compare Configure the HtmlReport

Back to Show Reports in a Hierarchically Structured Model

Display the Production Areas

To show the three production areasCarBody , PaintShop , and FinalAssembly -as second level headings below the first level heading Production Areas in our HtmlReport in the Frame MyCarAssembly , we typed in the instructions below.

The instructions in the HtmlReport in the Frame MyCarAssembly define how the overall report of the three production areas will be displayed.

**Production Areas The car assembly encompasses three production areas: * CarBody * PaintShop * FinalAssembly [CarBody, #]        // Show the HtmlReport of the Frame 'CarBody' instead of the Frame itself [PaintShop, #]      // Show the HtmlReport of the Frame 'PaintShop' instead of the Frame itself [FinalAssembly, #]  // Show the HtmlReport of the Frame 'FinalAssembly' instead of the Frame itself**

In our ReportObject in the Frame CarBody , for example, we show the headings one level higher, compare these instructions:

```simtalk
**[current.name] The car body section of our car assembly looks like this: ## Layout ><[current, *] ## CarBodyCells The car body section encompasses several CarBodyCells: [CarBodyCell.Origin*, ##] [EnergyAnalyzer, #]**
```

The instructions in the ReportObject in the Frame CarBody set which information the overall report displays for the CarBody section. The same applies to the Frames PaintShop and FinalAssembly .

<!-- image -->

Compare Configure the HtmlReport

Back to Study the HtmlReport

Display the Energy Analysis The instruction [CarBody, #] in the following code section of the HtmlReport shows the content of the Frame .Models.MyCarAssembly.CarBody .

**Production Areas The car assembly encompasses three production areas: * CarBody * PaintShop * FinalAssembly [CarBody, #]      // Show the HtmlReport of the Frame 'CarBody' instead of the Frame itself**

We set in the ReportObject in the Frame .Models.MyCarAssembly.CarBody what exactly the HtmlReport for the CarBody section shows:

**[current.name] The car body section of our car assembly looks like this: ## Layout ><[current, *] ## CarBodyCells The car body section encompasses several CarBodyCells: [CarBodyCell.Origin*, ##]    // Show the heading two levels lower [EnergyAnalyzer, #]          // Show the heading one level lower**

<!-- image -->

Our HtmlReport in the Frame MyCarAssembly shows the energy consumption of all AssemblyStations , which the tool EnergyAnalyzer recorded:

- The Chart Usage profiles .
- The Chart Consumption over time .
- The Table Detailed consumption .

Compare Configure the Body Assembly

Compare Configure the HtmlReport

Back to Study the HtmlReport

###### Display the ToDos and Change to the Respective Frame

We use the object Comment to quickly change to the Frame in which it is inserted, i.e., its location by selecting Navigate &gt; Open Location in its dialog. The following instructions in the HtmlReport collect all objects of type Comment named ToDo in all sub-Frames .

**ToDo These tasks still have to be completed. [.UserObjects.ToDo*]**

They then show them in the overall report under ToDo .

<!-- image -->

The text that we entered into the individual Comments named ToDo is a link each to the respective Comment in the Frame in which it is inserted. The link shows the path in a Tooltip when you drag the mouse over it and let it hover.

Click the link to open this Comment object.

Then select Navigate &gt; Open Location in its dialog to open the Frame in which the Comment is located.

<!-- image -->

Compare Configure the HtmlReport

Back to Study the HtmlReport

#### Showing Values During the Simulation Run with the Display

Show Values During the Simulation with the Display

If you want to show a value of an attribute , of a method , or of a Variable at all times throughout the entire simulation run, we will use the Display . The Display is, for example, ideally suited to dynamically show the fill level of a Buffer .

You can insert it into your simulation model from the folder UserInterface in the Class Library or from the toolbar User Interface in the Toolbox .

<!-- image -->

- If you deactivate the Display , it shows its icon in the Frame , into which you insert it.
- If you activate it by selecting , the Display shows a value in the Frame window, such as .

You can:

- Select Which Data the Display Shows

##### Select Which Data the Display Shows

- Select How the Display Shows the Data

Compare Viewing the Statistics Report

Compare View Statistics in the Dialogs of the Objects

Compare Show Statistics with Display Panels in the 2D Model

Compare Show Statistics in a Chart

Compare Show Statistics and Other Values in a Report

Back to View and Visualize Statistics

Select Which Data the Display Shows

Before you start your simulation run, you have to tell the Display which value it displays and in which mode it collects the data.

<!-- image -->

- Click to type in the path to and the name of the object whose data you want to view. Then, type the value of a global variable ( Variable ), of an attribute or of a method of an object into the text box after the path. You might, for example, type in buffer.numMU, .Models.Model.ParallelStation.statNumOut, store.XDim , etc.

The Display supports the data types boolean, integer, real, string, object, time, money, length, weight, speed, date , and datetime . If the path you type in is invalid, the background of the text box changes to red.

- If you want to, you can also type in a brief description ( Comment ) of the displayed value. You might, for example, type in a description of the attribute that the Display displays, such as Fill Level Buffer . The Display show this text below the value in the Frame window.

**Note**

When you select to display the value as Text , we recommend to type in one or two spaces after the last word, so that the value does not appear too close to the comment.

- Select which mode the Display uses to update the displayed data.
- Sample mode updates the Display periodically and takes the next sample after the time span you type into the text box Interval .
- Watch mode updates the Display , whenever the value of a watchable read-only attribute changes, for example NumMU , NumMUParts , StatMaxNumMU , StatNumIn , StatNumOut , etc. or of a watchable attribute , for example Pause , Speed , Unplanned , etc.

The column Watchable in the window Show Attributes and Methods of the individual objects shows all methods , read-only attribute , and attributes which Plant Simulation can watch.

**Back to Show Values During the Simulation with the Display**

##### Select How the Display Shows the Data

Before you start your simulation run, you have to tell the Display how to show the value it collects. In Sample mode it updates the value periodically, in Watch mode , whenever the displayed value changes.

<!-- image -->

- Select how you want the Display to show the value: As Text , as a Bar , or as a slice of a Pie . The Display can only show numerical values as a bar and as a slice of a pie. These are easy to comprehend, but not very well suited if accuracy is important.

<!-- image -->

- When you select Bar or Pie , the Display shows the value in relation to the Minimum and the Maximum value of the range you enter. An empty bar/pie indicates values less than or equal to the lower bound of the range. A full bar/pie represents values greater than or equal to the upper bound of the range. You can also change the height and the width of the bar/pie graphic by dragging its outline with the left mouse button while holding both the Shift and the Ctrl keys down.

The Display show the actual minimal and maximal values as dashed lines in the Frame window, which is not as accurate as you might need it to be. To view the current values, click the tab Data and look at the boxes Minimum and Maximum .

To reset the values on the tab to 0, click Reset Values .

- When you select Text , the Display shows the value as a number or as text in the Frame window. Then, you can select a Font size for displaying the value itself and for displaying the Comment you entered. Enter a blank after the text you enter so that the Comment value is not shown attached to the text.
- To make the background of the Display you inserted into a Frame transparent, select Transparent .

<!-- image -->

Then, the Display shows the space around the text in the color of the background image or it shows the grid points of the Frame . If you clear Transparent , Plant Simulation shows the space around the text white.

| Not transparent   | Transparent   |
|-------------------|---------------|

- To select a color for the text the Display displays and for the outline of its display graphic, click in the field next to Color and select a color in the dialog Colors .

Compare Check the Fill Level of the Buffer

Back to Show Values During the Simulation Run with the Display

#### Accessing Statistics with SimTalk

Naturally you can access most of the statistics values with methods , read-only attributes , and attributes :

- For the material flow objects the names of the read-only attributes are listed next to the name of the value in the description of the Statistics Report .
- For the Drain the names of the read-only attributes are listed next to the name of the value in the description of the Statistics Report .
- For the Exporter and the Worker the names of the read-only attributes are listed next to the name of the value in the description of the Statistics Report .
- In addition, you might want to check the topics Read-Only Attributes for Accessing Statistics and Attributes for Statistics .
- For the MUs the names of the read-only attributes are listed next to the name of the value in the description of the Product Statistics of the MUs in the Statistics Report .
- For the object Transporter the names of the read-only attributes are listed next to the name of the value in the description of the Driving Statistics of the Transporter .
- In addition, you might want to check the topics Methods for Accessing Statistics of the MUs and \_Attributes of All MUs .

Compare View Statistics in the Dialogs of the Objects

Compare Show Statistics with Display Panels in the 2D Model

Compare Show Statistics in a Chart

Compare Show Statistics and Other Values in a Report

Compare Show Values During the Simulation with the Display

Back to View and Visualize Statistics

#### Showing Part Flows in a SankeyDiagram

Show Part Flows in a SankeyDiagram

The SankeyDiagram visualizes how parts or Workers move from object to object.

You can insert the SankeyDiagram into your simulation model from the folder User Interface in the Class Library or from the tab User Interface in the Toolbox .

In our model the Source produces parts. The station Roughing processes these parts for the defined time. Then the Worker carries the processed parts to the station FineMachining which adds additional processing steps. The Drain removes the parts from the factory.

The SankeyDiagram visualizes the flow of the parts and the Workers after the end of the simulation.

Our finished simulation model looks like this in 2D and in 3D:

<!-- image -->

**Note**

If you also want to show the names and the labels of the material flow objects in 3D, click the class of the object with the right mouse button and select Edit 3D Properties . Then select Name/Label Activated on the tab Captions .

<!-- image -->

**We will demonstrate how to:**

- Show Part Flows in a SankeyDiagram
- Configure the Objects that Produce and Process Parts
- Configure the SankeyDiagrams

**Back to View and Visualize Statistics**

Configure the Objects that Produce and Process Parts

To model the material flow, we inserted these material flow objects into our simulation model:

- A Source which produces the parts. We use the Source with its default settings.
- A station which roughly machines the parts. For this we used the Station with its default settings.

As we want a Worker to carry the processed parts from the Station labeled Roughing to the Station labeled FineMachining , we defined these settings for the transport importer :

<!-- image -->

- A second station labeled FineMachining , which does the fine machining of the parts. For this we used the Station with its default settings as well.
- A Drain which removes the parts from the factory.

**Back to Show Part Flows in a SankeyDiagram**

Configure the Carrying Operation with Broker, WorkerPool, and Worker

To allow the Worker to carry parts from the station Roughing to the station Fine Machining , we inserted these resource objects into our model:

- A Broker which assigns the required services to the Worker . We use the Broker with its default settings.
- A WorkerPool which sends the Workers off to their jobs. Here we selected the Travel mode &gt; Walk along footpaths and we activated Get Job Orders at Home Only .

<!-- image -->

- A Workplace each which we attached to the stations Roughing and Fine Machining . We cleared the check box Worker Stays Here After Completing the Job .
- A FootPath each between the Workplaces and the WorkerPool and between the Workplaces . Make sure that the Workplaces are connected with Connectors with the FootPaths and the WorkerPool

<!-- image -->

Back to Show Part Flows in a SankeyDiagram

.

##### Configure the SankeyDiagrams

To visualize the Sankey flows of the Worker and the parts , we use a SankeyDiagram each. We selected these configurations for that:

- For the Worker SankeyDiagram we used the default display attributes.

<!-- image -->

As we want to show the Sankey flows of the Worker , we turn the check box for inheritance on the tab Objects off and drag the Worker from the folder Resources in the Class Library to this tab.

We then clicked OK in the dialog to apply the new settings.

- For the Parts SankeyDiagram we only changed the color of the Sankey flows We then clicked OK in the dialog to apply the new settings.
- Run the simulation over a considerable period of time.
- Click the SankeyDiagram labeled Worker with the right mouse button and select Show . The result looks like this:
- .

<!-- image -->

- Click the SankeyDiagram labeled Parts with the right mouse button and select Show to also show the Sankey flows of the parts. The result looks like this:
- To hide the Sankey flows of a SankeyDiagram again, click it with the right mouse button, and select Hide . Instead you can also click the button in the dialog of the respective SankeyDiagram .

<!-- image -->

To demonstrate how the SankeyDiagram shows the Sankey flows of the Worker , who walks freely within the area, we duplicated our model. Then we changed these settings in the WorkerPool :

- We cleared Get Job Orders at Home Only .
- We selected the Travel Mode &gt; Move freely within area .

<!-- image -->

- The SankeyDiagram shows the Sankey flows of the Worker , who walks freely within the area, like this:

<!-- image -->

If we insert a barred area, around which the Worker has to walk, the SankeyDiagram looks like this:

Back to Show Part Flows in a SankeyDiagram

<!-- image -->

#### Showing Parts on Resources in a GanttChart

Show Parts on Resources in a GanttChart

The GanttChart shows how parts move from resource to resource during the simulation. In this context resources are the material flow objects , not the resource objects .

You can insert the GanttChart into your simulation model from the folder UserInterface in the Class Library or from the toolbar User Interface in the Toolbox .

In our model the Source produces different parts with different processing times according to a delivery table. The ParallelStation processes these parts then for the specified times and moves them on to the Station and the Drain . The GanttChart shows the progression of the parts during the simulation.

The finished simulation model looks like this:

<!-- image -->

**We will demonstrate how to:**

- Configure the Source that Produces the Parts
- Configure the ParallelStation that Processes the Parts
- Configure the GanttChart
- Show the GanttChart

Back to View and Visualize Statistics

Configure the Source that Produces the Parts

Our Source produces different parts according to a delivery table . To accomplish this, we entered the settings below on the tab Attributes .

<!-- image -->

Our Delivery Table looks like this:

<!-- image -->

**Back to Show Parts on Resources in a GanttChart**

Configure the ParallelStation that Processes the Parts

Our ParallelStation processes the different parts for the specified times. We selected these settings:

- We entered an X-Dimension of 2 and a Y-Dimension of 1 .

Make sure that the check box Start Processing When Full is cleared or your model might not run.

<!-- image -->

- We set the Processing Times of the individual parts in the list MyProcessingTimes on the tab Times .
- To create a realistic simulation model, we also use failures . We selected these settings on the tab Failures .

<!-- image -->

<!-- image -->

**Back to Show Parts on Resources in a GanttChart**

##### Configure the GanttChart

To show how the parts move from material flow object to material flow object in the simulation model, we configured the GanttChart as follows:

- As we want the GanttChart to collect data during the simulation, we activated Collect data .
- We would like to watch the part named Part . This is already pre-configured, so we do not have to do anything.

To add another part to the tab Parts , select it in the Class Library , drag it to the first cell on the tab, and drop it there.

Instead, you can also select the part in the Class Library , drag it on the icon of the GanttChart , and drop it there. This automatically deactivates inheritance and adds the part to an empty row on the tab Parts .

<!-- image -->

- We would like to watch all Resources . To add them to the tab Resources , we selected them in the Frame , dragged it to the first cell on the tab, and dropped them there.

Instead, you can also select one or several resources in the Frame , drag it/them on the icon of the GanttChart , and drop it/them there. This automatically deactivates inheritance and adds the resources to an empty row each on the tab Resources .

As we want to watch all resources in the simulation model, we could also have left the tab Resources empty.

<!-- image -->

##### Back to Show Parts on Resources in a GanttChart

Show the GanttChart

Click Start/Stop Simulation to run the simulation and let it run for a little while. Then, click Show Chart in the open dialog of the GanttChart . Instead, you can also right-click the GanttChart in the Frame and select Show on the context menu.

You can select the display settings on the tab Attributes .

<!-- image -->

The GanttChart provides two views:

- Resource view shows the resources which are occupied by the parts. The GanttChart shows the resources along the vertical axis and the elapsing time along the horizontal axis.

**Note**

The GanttChart shows the resources in the order in which they processed parts for the first time. The resource, which processed a part first, is shown in the first line in the chart. The resource, which processed a part after that, is shown in the line below, etc.

You cannot change the order of the resources.

<!-- image -->

With the default settings the GanttChart shows a part on all resources with the same color.

- Part view shows the parts which occupy the resources. The GanttChart shows the parts along the vertical axis and the elapsing time along the horizontal axis.

**Note**

The GanttChart shows the parts in the order in which they were processed by a resource for the first time. The part, which was processed by a resource first, is shown in the first line in the chart. The part, which was processed by a resource after that, is shown in the line below, etc.

You cannot change the order of the parts.

<!-- image -->

With the default settings the GanttChart shows a resource for all parts with the same color.

You can select the respective view mode on the drop-down list or on the context menu.

The displayed resource states refer to the resource which is currently occupied by the displayed part.

<!-- image -->

**Show Longer or Shorter Time Intervals**

To show longer time intervals, hold down Ctrl and press the -key or roll the mouse wheel backward. This zooms the view in.

To show shorter time intervals, hold down Ctrl and press the + key or roll the mouse wheel forward. This zooms the view out.

To change the displayed time intervals in greater steps , hold down Shift in addition to Ctrl .

To return to the default zoom factor , hold down Ctrl and press the 0 key.

Back to Show Parts on Resources in a GanttChart

### Toggling States and Executing Actions

#### Switch States and Execute Actions

At times, you may want to toggle between the states on and off , or between different operating modes, etc. in your simulation model. Or you may want to execute an action by clicking a button in the model, for example open a certain table or method with one click instead of navigating to the object in the Frame and double-clicking it.

**You can:**

- Switch States with the Checkbox
- Execute the Action
- Select an Option from a Drop-down List

Back to Animate the Simulation Model in 2D and View the Results

#### Toggling States with the Checkbox

Switch States with the Checkbox

You can insert the Checkbox into your simulation model from the folder UserInterface in the Class Library or from the toolbar User Interface in the Toolbox .

<!-- image -->

To open the dialog of the object Checkbox , double-click the name Checkbox to the right of the icon in the

<!-- image -->

.

The Checkbox looks like this in 2D and in 3D by default:

<!-- image -->

You can use the check box to:

- Toggle the State by Clicking the Checkbox
- Switch Modes Using a Control

Back to Switch States and Execute Actions

Toggle the State by Clicking the Checkbox

To switch between the on and the off state of the Checkbox , click its icon in the Frame . To show an expression of your choice next to the check box, enter it into the text box Label . We entered Motor on/off in our example.

<!-- image -->

<!-- image -->

The Checkbox looks like this in 2D and in 3D by default:

<!-- image -->

<!-- image -->

When you click the check box in the Frame , it changes its icon from green , meaning on , to red , meaning off .

Back to Switch States with the Checkbox

Switch Modes Using a Control

If you want the check box to switch modes when a certain action takes place in your simulation model, you have to program this in a control .

Double-click the name of the check box and select the control in which you programmed when the Checkbox switches modes.

In our example the Checkbox named MyCheckbox changes the Value of the Variable named MyState from true to false and vice versa in the model.

<!-- image -->

The source code looks like this:

<!-- image -->

Back to Switch States with the Checkbox

#### Executing Actions by Clicking a Button

##### Execute the Action

You can insert the Button into your simulation model from the folder UserInterface in the Class Library or from the toolbar User Interface in the Toolbox .

<!-- image -->

We will demonstrate how to:

- Define the Appearance of the Button in 2D
- Program the Control for the Action to be Executed

**Back to Switch States and Execute Actions**

##### Define the Appearance of the Button in 2D

Plant Simulation can show the button in the Frame in a 2D Only model number of ways:

<!-- image -->

- With the built-in icon and the label you type in, for example . You might have to adjust the Width and the Height so that the label fits the button without being cut off. You can do this by holding down Ctrl+Shift and dragging a corner of the icon. Or you can enter exact values into the text boxes. Or you can combine both methods by first dragging to roughly resize the button and then by fine-tuning the values in the text boxes.
- With a user-defined icon , which you draw in the icon editor in 2D.

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

Then, you can show the text you enter as the label in this user-defined icon of the button, for example.

To be able to tell that you clicked the button, we recommend to draw two pictures for the button, one for the unclicked state , and one for the clicked state . In our example above the name of the unclicked icon is icon3 , the name of the clicked icon consequently has to be icon3\_down . The button does not stay pressed, but returns to its unclicked, raised state when you release the mouse button.

<!-- image -->

- With a picture you paste into a new icon in the icon editor ,

It looks like this in a 2D Only model :

<!-- image -->

It looks like this in 3D Only model :

<!-- image -->

To open the dialog of the button, click it with the right mouse button and select Open on the context menu.

<!-- image -->

You can also select the button by dragging a marquee around it.

By default Plant Simulation does not show a tooltip for the button in the Frame when you roll the mouse over it. To display a your own tooltip , create a user-defined attribute and name it Tooltip .

<!-- image -->

After you have defined the appearance of the Button , you have to program the action , which the Control executes, when the Button is clicked.

<!-- image -->

To execute this action, click the button in the Frame .

**Back to Execute the Action**

Program the Control for the Action to be Executed

After you defined the appearance of the Button , you have to program the control that clicking the Button executes.

We explain the control using the example of the Start/Stop Simulation button in our Factory51 sample model.

<!-- image -->

We created our control by clicking the ellipsis button in the text box Control and selecting Create Control on the context menu.

<!-- image -->

We wrote this source code which checks if the EventController is running at the moment. If so, it stops the simulation, and then starts it.

```simtalk
if root.EventController.IsRunning ...root.EventController.stop
else ...root.EventController.start
end
```

Back to Execute the Action

#### Selecting an Option from a Drop-down List

Select an Option from a Drop-down List

You can insert the Drop-Down List into your simulation model from the folder UserInterface in the Class Library or from the toolbar User Interface in the Toolbox .

<!-- image -->

In our sample model we show how to combine the objects Button , Check Box , and Drop-down List with user-defined controls to make meaningful use of them and how to access a number of settings in your simulation model quickly and easily.

- The check box activates or deactivates moving the parts on to a dedicated tray in the plant.
- The drop-down list sets the dedicated destination tray of the parts if you turn the check box on.
- The button opens the table according to which the Source produces the parts.
- The button opens the sensor control of the feeder line that sends the parts on to their destination trays according to the settings of the check box and of the drop-down list .

<!-- image -->

To create the sample model, we will:

- Configure the Source that Produces the Parts [Drop-down List]
- Configure the Feeder Line with Sensor and Sensor Control
- Configure the Turnplate to Rotate the Part According to an Attribute
- Configure the Check Box and the Drop-down List
- Configure the Buttons to Open Parts Table and Callback Method

Back to Switch States and Execute Actions

Configure the Source that Produces the Parts [Drop-down List]

Our Source with the label Parts In produces the parts in a cyclical sequence according to the settings, which we entered into the PartsTable .

<!-- image -->

Compare the topic Produce Parts in a Fixed Sequence One Time Only on how to work with the production table.

Enter the attribute, which sets the tray to which the part is going to be moved, into the subtable that double-clicking into the respective cell in the column Attributes of the production table opens.

We entered the attribute Destination and the respective Tray .

<!-- image -->

If is off, the Source produces the part Board in a cyclical sequence and moves the boards across the materials handling equipment to the destination trays.

<!-- image -->

For moving the part, the callback method , which we enter as the sensor control into the feeder line , uses the attribute Destination of the part.

Back to Select an Option from a Drop-down List

Configure the Feeder Line with Sensor and Sensor Control

The feeder line is part of the materials handling equipment that transports the parts to their destination trays. Our line is 11 meters long. We created a sensor at 10 meters and entered the method PartDestination , which has the label Callback , as the sensor control .

<!-- image -->

<!-- image -->

If the check box is on, we access the drop-down list

<!-- image -->

within the callback method PartDestination with the attribute Items . It then moves the board on to the tray according to the value, which you selected in the drop-down list .

The source code looks like this:

```simtalk
// Apply the destination selected in the drop-down list // named/labeled 'SelectDestination/Dedicated Destination'.
if DestinationActive.Value // destination is active // set new destination of the part
	@.Destination := SelectDestination.Items[SelectDestination.Value]
end
```

Back to Select an Option from a Drop-down List

Configure the Turnplate to Rotate the Part According to an Attribute

Following the feeder line in our plant we added a Turnplate to rotate the produced boards.

To do so, we selected the Strategy &gt; MU Attribute and the Attribute type &gt; Object , and entered the required values into the attribute list .

<!-- image -->

We entered the attribute named Destination , the names of the destination trays, Tray1 to Tray4 , and the angle by which the board will be rotated. 90 stands for 90 degrees clockwise, -90 stands for 90 degrees counterclockwise.

<!-- image -->

##### Back to Select an Option from a Drop-down List

Configure the Check Box and the Drop-down List

In our example the check box and the drop-down list work together:

<!-- image -->

<!-- image -->

- The check box activates or deactivates moving the boards on to a dedicated tray.
- The drop-down list sets the dedicated destination of the boards once you click the check box to set it to on.

<!-- image -->

<!-- image -->

To configure the drop-down list , proceed as follows:

- Enter the Width and the Height with which the drop-down list will be shown in the Frame . We entered a Width of 6 meters and the Height of 1 meter.
- Click the button Items and enter the items which the drop-down list shows in the Frame .

<!-- image -->

The drop-down lists look different in 2D and in 3D.

<!-- image -->

- Enter the number of the item in the list which the drop-down list will show in the Frame by default into the text box Value . We entered 1 to make the drop-down list show Tray1 when it is closed.

<!-- image -->

- In 3D you can set the caption of the drop-down list , show it in the Frame , and set its position.

<!-- image -->

On the View ribbon tab in 3D you can select if you want to show the name , or the label , or both in the Frame .

<!-- image -->

To open the dialog of the drop-down list , click it with the right mouse button and select Open on the context menu.

<!-- image -->

**Note**

In 3D Plant Simulation only accepts the click the Checkbox if it occupies at least 10 pixels in each direction in the model window. If you zoom out very far, the Checkbox might become too small, preventing Plant Simulation to recognize it reliably.

<!-- image -->

If the check box is on, we access the drop-down list

<!-- image -->

within the Callback Method of the sensor with the attribute Items . It then moves the board on to the tray according to the value that you selected.

The source code looks like this:

```simtalk
// Apply the destination selected in the drop-down list // named/labeled 'SelectDestination/Dedicated Destination'
var l: list
l.create
SelectDestination.getItems(l)
if DestinationActive.Value then  // destination is active // set new destination of the part
	@.Destination := l[SelectDestination.Value]
end
```

Back to Select an Option from a Drop-down List

<!-- image -->

Configure the Buttons to Open Parts Table and Callback Method

We finally thought it to be helpful if we could open the parts table and the callback method with one click instead of having to navigate to them in the Frame and double-clicking their icon.

To do so, we configured two buttons:

- The button opens the table according to which the Source named PartsIn produces the parts.
- Enter the Width and the Height with which the button will be shown in the Frame . We entered a Width of 6 meters and a Height of 1 meter.
- Enter the control , which will be called, when you click the button . We decided to use a control that is part of the object. So we right-clicked into the text box Control and select Create Control .

<!-- image -->

We then entered the following source code into the control that opened. It opens the parts table named PartsTable in the Frame .

<!-- image -->

<!-- image -->

<!-- image -->

- The button opens the sensor control of the feeder line that sends the parts on to their destinations according to the settings of the check box and of the drop-down list .
- Enter the Width and the Height with which the button will be shown in the Frame . We entered a Width of 6 meters and a Height of 1 meter.
- Enter the control, which will be called, when you click the button . We decided to use a control that is part of the object. So we right-clicked into the text box Control and select Create Control .

<!-- image -->

We then entered the following source code into the control that opened. It opens the callback method of the sensor control in the Frame with the name PartDestination and the label Callback .

As we want to open the window of the Method , not to execute its source code, we have to enter the reference operator &amp; in front of the name of the sensor control .

<!-- image -->

Compare Program the Control for the Action to be Executed

Back to Select an Option from a Drop-down List

**Importing Data for the Simulation**

