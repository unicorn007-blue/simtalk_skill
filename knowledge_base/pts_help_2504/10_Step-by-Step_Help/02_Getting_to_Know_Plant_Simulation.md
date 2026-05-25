## Getting to Know Plant Simulation

Getting to Know Plant Simulation introduces you to the basic concepts on which simulation is based and to the basics of working with Plant Simulation .

Compare Modeling the Material Flow

Compare Visualizing the Material Flow in 3D

#### Simulation and Modeling Concepts

### Simulation and Modeling Concepts

Simulation concepts and modeling concepts introduce you to the theoretical background of simulation as such and show you what to keep in mind before you start modeling.

In general, operations research processes are intended to allow you to make the right decisions, qualitatively as well as quantitatively. They formulate optimization models, containing all relevant factors, such as target function, conditions and target description. These processes require a large amount of processing power the more detailed the model is. Besides, the results and acceptance of operations research processes often are not satisfactory.

In addition to linear optimization models simulation nowadays is increasingly used for making the right decisions. Simulation offers good solutions for complex problems but does not automatically create the actual optimum. This is justified by the comparatively low amount of mathematical expenditure to obtain that result.

As processes to be analyzed become more complicated and complex and as more factors have to included, the more important simulation becomes with its analysis of real processes. These processes cannot be covered by mathematical solution processes or optimization processes or they may be realized only by using a large amount of resources.

The aim of simulation is to arrive at objective decisions by dynamic analysis, to allow managers to safely plan and, in the end, to reduce costs.

Thus, if real systems and plants are too expensive for conducting experiments and the time to conduct trials is too limited and too expensive, modeling, simulation and animation are excellent tools for analyzing and optimizing time dynamic processes.

Go to Working with Classes in the Class Library

Go to Using Inheritance

Go to Model Hierarchically [general]

Back to Getting to Know Plant Simulation

#### What is Simulation?

VDI Technical Rule 3633 defines simulation as the emulation of a system, including its dynamic processes, in a model one can experiment with. It aims at achieving results that can be transferred to a real world plant. In addition, simulation defines the preparation, execution and evaluation of carefully directed experiments within a simulation model.

As a rule, you will execute a simulation study like this:

- You first check out the real-world plant you want to model and collect the data you need for creating your simulation model.
- You then abstract this real-world plant and create your simulation model according to the aims of the simulation studies.
- After this, you run experiments, i.e., execute simulation runs, within the simulation model. This will produce a number of results, such as how often machines fail, how often they are blocked, which set-up times accrue for the individual types of station, which utilization the machines have, etc.
- The next step will be to interpret the data the simulation runs produce.
- Finally, management will use the results as a base for its decisions about optimizing the real plant.

Developing your simulation model is a cyclical and evolutionary process. You will start out with a first draft of your model and then refine and modify it to make use of the intermediary results the simulation runs provide. Eventually, after several cycles, you will arrive at your final model.

As a simulation expert, you must never loose sight of these questions:

- What do you want to accomplish with the simulation study?
- What are you examining?
- Which conclusions do you draw from the results of the simulation study?
- How do you transfer the results of the simulation study to the real-world plant?

Go to Time-Oriented Simulation and Event-Controlled Simulation

Back to Simulation and Modeling Concepts

#### Time-Oriented Simulation and Event-Controlled Simulation

Plant Simulation is a discrete, event-controlled simulation program, i.e., it only inspects those points in time, at which events take place within the simulation model.

In reality, on the other hand, time elapses continually. When watching a part move along a conveyor system, you will detect no jumps in time. The curve for the distance covered, and the time it takes to cover it, is continuous, it is a straight line.

A discrete, event-controlled simulation program on the other hand only takes points in time (events) into consideration that are important to the further course of the simulation. Such events may, for example, be a part entering a station or leaving it or of it moving on to another machine. Any movements in between are of little interest to the simulation as such. It is only important that the entrance and the exit ( Out ) events are displayed correctly. When a part enters a material flow object, Plant Simulation computes the time until it exits that object and enters an exit event into the list of scheduled events of the EventController for this point in time.

Thus, the simulation time that the EventController displays, jumps from event to event. This happens as soon as an event is processed.

<!-- image -->

The List shows all events that trigger an action. Click the button to open it.

<!-- image -->

<!-- image -->

Go to What is Simulation?

Back to Simulation and Modeling Concepts

#### Why Use Simulation?

As a rule, you will employ simulation when you have to:

- Plan a new plant . Here simulation helps you to:
- Detect and eliminate problems that otherwise would require cost- and time-consuming correction measures during production ramp-up.
- Determine and optimize the times, such as processing time, failure time, recovery time, etc., and the throughput of the plant.
- Determine the size of buffers and the number of machines your intended throughput requires. When a single machine costs hundreds of thousands of dollars, it certainly helps to know if you need one or more machines of one type.
- Determine the limits of performance of the machines and of the plant as a whole.
- Investigate how failures affect the throughput and the utilization of the machines.
- Determine how many workers and staff members are required for the intended throughput.
- Gain knowledge about the behavior of the plant.
- Determine suitable control strategies of the machines and of the way the machines interact.
- Evaluate different alternatives by running a number of simulation experiments.
- Minimize the investment cost for production lines without jeopardizing required output.
- Optimize an existing plant . Here simulation helps you to:
- Optimize the performance of existing production systems by implementing measures that have been verified in a simulation environment prior to implementation .
- Optimize the control strategies you devised.
- Optimize the sequence of orders that have to be fulfilled to make as few tool changes necessary as possible.
- Test the daily proceedings to make sure that everything works smoothly.
- Put the plan you formulated into practice . Here simulation helps you to:
- Develop a template for creating the control strategies.
- Test different scenarios during the warm-up phase of the plant.
- Train the operators of the machines in the different states, which machines and the plant can be in.

In general, you will reap these benefits from employing simulation:

- Enhance the productivity of existing production facilities.
- Reduce investment in planning new production facilities.
- Cut inventory and throughput time.

**Why Use Simulation?**

- Optimize system dimensions, including buffer sizes.
- Reduce investment risks by early proof of concept.
- Maximize use of manufacturing resources.
- Improve line design and schedule.

Back to Simulation and Modeling Concepts

#### Implement a Simulation Project

As you remember, developing your simulation model is a cyclical and evolutionary process. You will start out with a first draft of your model and then refine and modify it to make use of the intermediary results the simulation runs provide. Eventually, after several cycles, you will arrive at your final model.

Before you start implementing your simulation project, you will, more or less, proceed like this. You will:

**· Describe the project**

Determine the goals, so that the purpose of the simulation project becomes clear. Why are you examining a problem? Which questions do you want answered? Put the definition of the project in writing and consult it repeatedly during the course of the project, as the purpose of the simulation study determines the efforts to be made.

**· Plan the project**

Create a concept of your model, with its initial values, its model items, variables, logic of proceeding and a preliminary description of the simulation experiments. Which parameters do you have to change, which data do you have to collect and how do you interpret this data? Make a list of all functional units that the installation you are modeling will contain. Think about which functional units have identical or similar functionality. Combine them and derive a list of application objects you and your colleagues have to create. Consider re-using existing objects. Specify and plan the remaining objects on paper. Define and describe the interfaces for material and information flow. Outline reset and init methods .

**· Find out about the data you need and how to acquire it**

Ensure early on that the data you need to run the simulation experiments is going to be available. Frequently a lot of time and effort is involved to acquire the data. Make sure that you have the name of a person who responsible for acquiring the data from your client, which may, for example, be another department of your company.

**· Build the simulation model**

Build a first version of the simulation model in its simplest, most basic form. Build the application objects you need and test them one by one. After you are sure that all objects work the way they are supposed to do, put together the overall model. Document the model in a clearly arranged manner, as six months or a year from the time you modeled you might not remember how you accomplished a certain task or why you solved a specific problem the way you did.

**· Verify the simulation model and check its validity**

After you are finished building the simulation model, you have to verify it, i.e., check if the components you modeled perform the tasks you programmed them to do. Test each and every object you created. Check for the correct functioning and for concurrence with the specifications. Test the objects in combination with other objects and then in the overall model. Make sure that all parameters are set to the correct values. Once you have verified the model, check it for its validity: Make sure the functionality of the model is as expected and conforms to the functionality of the planned or real plant and see if the results are plausible and credible. Make an estimate of the most important results and compare them with the results of the simulation. Introduce your model to a production or planning expert and discuss the results, the proceedings and your modeling approach with him.

**· Execute simulation experiments and collect the results**

Execute simulation experiments according to your final trial plans to arrive at the desired data. Plan a number of simulation runs and prepare for the variation of parameters and models to get reliable results.

**· Analyze the results of the experiments**

Analyze and interpret the results of the simulation experiments. Conduct a sensitivity analysis of the most important parameters, data and results.

**· Author the final documentation of the entire simulation project**

Once you are finished with the simulation project, update the notes you made while modeling to create the final documentation of the entire simulation project. This will help you, when you have to update or extend your simulation model or any of its components. Executing simulation experiments is a cyclical and evolutionary process. You will modify and improve your initial simulation model a number of times as you incorporate new insights from previous simulation runs. Thus you will arrive at your final simulation model after several cycles after continuously changing your initial draft of your simulation model.

Go to Prepare Data for the Simulation with DataFit

Go to Run Simulation Experiments

Go to Modeling the Material Flow

### Getting to Know Plant Simulation

#### Get to Know Plant Simulation

You can familiarize yourself with Plant Simulation in a number of ways. You can:

- View the Videos on YouTube
- View the Sample Models
- Consult the Step-by-Step Help

#### View the Videos on YouTube

The Videos , which you can access on the Start Page provide a quick introduction to some of the most commonly used modeling tasks. We constantly add new videos.

<!-- image -->

Click Videos to open the list of Videos we offer on YouTube . Then, click the respective video to view it.

If we demonstrate a feature in a video, the respective help topic provides a link to the video on YouTube and jumps to the respective time in the video. The link shows the time code after the equal sign, =18 in the example below. Each video opens in a tab of its own.

Note that we use the YouTube URL shortener in our links to the videos, for example https://youtu.be/ PgT4wkT2Xj8?si=Udlvoq8KcAI9GxQw&amp;t=18 .

Back to Get to Know Plant Simulation

#### View the Sample Models

To get acquainted with Plant Simulation , you also can view the sample models.

These models demonstrate how to approach a number of problems and will give you ideas on how to solve your modeling tasks. To do so, click Example Models &gt; Small Examples under Getting Started on the Start Page .

<!-- image -->

- Select the respective Category , the Topic , and the Sample Model .

<!-- image -->

- Click Open Model to open the selected.
- Click More Info to show a short description of the model.
- Type a search term describing the topic you want to find into the text box Search and click Search to find a model with this topic. Plant Simulation then searches the descriptions in the ReadMe files which are part of the models.

<!-- image -->

If you inadvertently pressed the Enter key instead of clicking Search , Plant Simulation closes the dialog Examples Collection . To open the start page again, click the button Start Page on the Window ribbon tab.

**Back to Get to Know Plant Simulation**

#### Consult the Step-by-Step Help

To get acquainted with Plant Simulation , you also can consult the Plant Simulation step-by-step help and the Plant Simulation Help that are part of Plant Simulation . The former will cover most of your modeling tasks and provide you with information on how to solve them. Start Plant Simulation , go to File &gt; Help and select Contents . Expand and select the topic you need information about.

If you prefer to read the documentation as a book in consecutive order, consult the printed materials that are part of your program package. You can also locate the PDF file of the manuals and view it online or print it in its entirety or only sections of it.

Back to Get to Know Plant Simulation

#### Working with Plant Simulation, Basics

### Working with Plant Simulation, Basics

Working with Plant Simulation, Basics provides these topics:

- Work with Window Types
- Select Settings in Plant Simulation
- Select Options in the Frame in 2D
- Change the Settings of the Objects
- Find Objects and Text in Your Simulation Model

#### Working with Window Types

Work with Window Types

Plant Simulation is a multiple-document interface application (MDI) which shows its windows in the common parent window.

<!-- image -->

The Plant Simulation program window has a magenta border in the figure above.

**Note**

The different window types open in a certain order within the program window. At times, it may happen that the window you want to work with opens in the background, instead of the foreground, where you would expect it to be. If this is the case, move the windows in the foreground aside to access the window into which you want to enter data.

Instead of closing and reopening the Class Library , the Favorites , the Toolbox , and the Console , you can hide them: Click Auto Hide in the title bar to auto hide the window. When you then click in another window, Plant Simulation hides the window until you move the mouse over the name of the window again. To deactivate auto hide, click .

For further information compare Components of the Program Window in the Reference section of the Plant Simulation Help .

Back to Working with Plant Simulation, Basics

##### Docking Windows

Plant Simulation docking windows are the Class Library , the Favorites , the Toolbox , and the Console .

Docking windows have a red border in the figure below Work with Window Types . Docking windows always open in the foreground, on top of any other windows, i.e., they will also be placed on top of any open dialog windows.

- To undock a docking window, click into the title bar of the window with the right mouse button and select Floating .
- To redock a floating window again, click in the title bar of the window with the right mouse button and select Docking .

<!-- image -->

Or

Click the title bar of the docking window and hold down the mouse button. Plant Simulation shows a docking indicator pointing to the upper, lower, right, and left border of the program window. Drag the mouse to the docking arrow where you would like to dock the window. Plant Simulation highlights this area of the program window in blue. Release the mouse button once the window is at the desired position. Plant Simulation then docks the window to the respective docking window .

<!-- image -->

Plant Simulation also shows individual docking arrows at the four sides of the parent window,

i.e., the Plant Simulation program window.

<!-- image -->

Drag the mouse to the docking arrow of the border of the program window at which you would like to dock the window. Plant Simulation highlights this area of the program window in blue. Release the mouse button once the window is at the desired position. Plant Simulation then docks the window at the respective border of the parent window , i.e., the Plant Simulation program window.

<!-- image -->

- To dock a floating window to any of the sides of the program window, drag the title bar on a floating window to another location. When you drag the window to the edge of the program window or to a location next to another docked window, it docks there.

**Note**

When you move a docked window, this might affect the location and size of other windows in the same row within the program window.

- To prevent a floating window from docking when you drag it, hold down Ctrl , and move the window to a position of your choice.
- To make a docked window a floating window, double-click the move handle or hold down Ctrl , and drag the window.
- To dock a floating window again, double-click its title bar or drag the window to one of the sides of the program window or to a location next to another docked window, it docks there.
- To close a floating window, click Close in the title bar.

<!-- image -->

<!-- image -->

- To show or hide the Class Library , click

on the Window ribbon tab.

<!-- image -->

<!-- image -->

- To show or hide the Favorites window, click on the Window ribbon tab.
- To show or hide the Console , click on the Window ribbon tab.
- To show or hide the Toolbox , click on the Window ribbon tab.
- To customize the Quick Access Toolbar and the Ribbon , click the down arrow on the Quick Access Toolbar and select More Commands .
- To change between docking windows and object windows , press Ctrl+Tab .

<!-- image -->

<!-- image -->

<!-- image -->

The Active Docking Windows are listed on the left and the Active Object Windows on the right.

- The left arrow and the right arrow change between the columns Active Docking Windows and Active Object Windows .
- The Tab key or the up/down arrows change between the windows within a column. Releasing Ctrl activates the selected window.

Back to Work with Window Types

##### Object Windows

Plant Simulation object windows are the windows of the objects Frame , Method , Method Debugger , DataQueue , DataStack , DataList , DataTable , Icon Editor , and the 3D Window .

Object windows always open in the background. Object windows have a blue border in the figure below Work with Window Types .

<!-- image -->

To bring an open object window to the foreground, click the icon of the window in the window tab bar.

To arrange the windows, i.e., to cascade, to tile them horizontally, or to tile them vertically, you can select the respective command on the Window Ribbon Tab .

To bring an open object window to the front, select the name of the window on the Window ribbon tab. You can also arrange these windows with one of these commands.

<!-- image -->

**Note**

You can open the DataList , the DataQueue , the DataStack , and the DataTable in the foreground as a window with the method openDialogBox , compare Opening a List as a Dialog in the Foreground .

You can close all object windows with the function closeAllWindows .

You can minimize and maximize an object window and move it around within the program window. When you maximize an object window , Plant Simulation adds the button combination Minimize , Maximize ,

<!-- image -->

that is otherwise located in the title bar of the window, above the Ribbon Bar .

You can add links to the following object windows to the Favorites :

- Frame windows .
- Method windows
- DataList windows
- DataQueue windows
- DataStack window
- DataTable window
- Windows of user-defined attributes of data type method , table , list , stack , and queue .

You can then quickly open the respective window by double-clicking its name in the favorites list.

<!-- image -->

- To change between docking windows and object windows , press Ctrl+Tab .
- The left arrow and the right arrow change between the columns Active Docking Windows and Active Object Windows .
- The Tab key or the up/down arrows change between the windows within a column. Releasing Ctrl activates the selected window.

Back to Work with Window Types

##### Changing Between Docking and Object Windows

Press Ctrl+Tab to open the Window Navigator . It shows a preview of the docking windows and of the opened object windows. The windows navigator stays open until you release Ctrl again.

<!-- image -->

The Active Docking Windows are listed on the left and the Active Object Windows on the right.

- The left arrow key and the right arrow key change between the columns Active Docking Windows and Active Object Windows .
- The Tab key or the up/down arrow keys change between the windows within a column. Releasing the Ctrl key activates the selected window.

If the focus is located on a docking window, Ctrl+Tab changes between the docking windows.

If the focus is located on an object window, Ctrl+Tab changes between the object windows.

Back to Work with Window Types

##### Dialog Boxes

Plant Simulation dialog boxes are the dialog boxes of the Plant Simulation material flow objects , the mobile objects , the fl uid objects , the resource objects , the information flow objects , and the user interface objects .

Dialog boxes have a green border in the figure below Work with Window Types .

A dialog box always opens in the front as it expects that you select or enter something. You cannot minimize or maximize it.

You can drag a dialog box outside the program window and move it around on the entire screen.

In the dialog boxes of the objects you can edit their simulation properties on the respective tabs.

<!-- image -->

<!-- image -->

If you are working with a 2D and 3D model, you can open the dialog box Edit 3D Properties by clicking the button on the left bottom corner of the dialog box to edit the 3D properties .

<!-- image -->

To close all open document windows at once, click Close All Windows

Back to Work with Window Types

**Selecting Settings in Plant Simulation**

#### Select Settings in Plant Simulation

Before you start working with Plant Simulation , you might want to change some of the default settings that affect your simulation model.

- To select settings, which apply to the active model , select File &gt; Model Settings . Plant Simulation saves these settings in the model file.

<!-- image -->

<!-- image -->

- To select settings, which apply to new models , select File &gt; Preferences . On the tabs General , 2D , 3D , and Editor you can select general settings, which are independent of the simulation model. On the tabs Simulation , User Interface , and Units you can select model-specific settings, which apply to new models.

**You can:**

- Select General Options
- Select the Visualization
- Select Modeling Options for the Frame

**· Select Options for Units and for Displaying the Time**

<!-- image -->

##### Select General Options

Select the language Plant Simulation uses when it creates a new simulation model. This language determines the names of folders and objects, such as MaterialFlow or Materialfluss , Station or Einzelstation , etc.

**Note**

The language of the operating system of your computer determines the language of the Plant Simulation user interface.

**The language determines:**

- The name of the items of the drop-down lists, such as the names of the distributions ( Uniform or Gleich ).
- The return value of the attributes that correspond to the entries of the drop-down lists, such as Station.ProcTime.Type .
- The contents of the window Show Attributes and Methods .
- The names which the feature Auto Complete within the Method Editor suggests.

Select if you want to use the 24-hour clock , the 12-hour clock ( AM / PM ), or the DMY (day-month-year) notation date and time format on the General ribbon tab.

<!-- image -->

<!-- image -->

| Date and time format   | Looks like this   |
|------------------------|-------------------|
| yyyy/mm/dd 12 hour     |                   |
| yyyy-mm-dd 24 hour     |                   |
| dd.mm.yyyy 24 hour     |                   |

Select which kind of comment Plant Simulation adds to your model file each time you save it:

- Without comment adds no comment to the model (.spp) file.
- With comment opens a comment window each time when you save the model. Enter your comment here.
- When you select Without comment or With comment Plant Simulation adds a row to the dialog Model Saving History each time you save the model.

When the model crashes, Plant Simulation adds a description of the problem to the model history window instead of a comment. This helps our software engineers detect what caused the crash.

- None does not save the history of how you saved your model.

To view the comment you entered:

Select File &gt; Options &gt; Show Model History in the program window.

<!-- image -->

Compare Creating a German Model with English Identifiers

Back to Select Settings in Plant Simulation

##### Select the Visualization

You can set the visualization for new simulation models that you create and for existing models:

- Under Preferences &gt; General &gt; Visualization you can select the visualization that you want to use for your new simulation models when you click New Model :
- Only in 2D creates the model consisting only of the 2D part.

<!-- image -->

To edit the simulation properties of an object, double-click the icon of the object, which you inserted into your model.

<!-- image -->

- Only in 3D creates the model consisting only of the 3D part.

<!-- image -->

**Note**

We recommend to always create your models in 3D only mode . This also applies if you are only interested in the 2D view.

<!-- image -->

You can model in Planning View in 3D, which corresponds to the top view in 2D. In addition, you can continuously zoom in the 3D window and 3D has better performance than 2D.

To edit the simulation properties of an object, double-click the icon of the object, which you inserted into your model.

To edit the 3D Properties of an object, click its icon with the left mouse button and press the spacebar .

<!-- image -->

If the dialog simulation properties is open, you can click to open the dialog Edit 3D Properties .

<!-- image -->

If the dialog Edit 3D Properties is open, you can click to open the dialog of the simulation properties .

- Ask each time . Asks each time you create a new simulation model how you want to create it. For this setting Plant Simulation only provides Only in 2D and Only in 3D .
- Under Model Settings &gt; General &gt; Visualization you can select the visualization for an existing simulation model :
- Only in 2D . Shows the model in 2D only.
- In 2D and in 3D . Shows the 2D part and the 3D part of the model.

The setting 2D and 3D is intended to convert a 2D model into a 3D model. We strongly advise against modeling in 2D and 3D mode.

**Note**

We strongly advise you to not modify object positions/rotations/polycurves in a 2D and 3D model or create/delete objects in 2D while you also work in 3D at the same time. Otherwise undoing changes in 3D might have unexpected side effects.

Check if the 3D model behaves according to your expectations and then save the model as a 3D only model.

- Only in 3D . Shows the model in 3D only.

**Note**

If the existing model has a 3D part and when you then display it in 2D Only mode, Plant Simulation terminates 3D. This way you lose all of your changes in 3D if you do not save your changes to 3D by clicking Yes in the message dialog that opens.

We recommend to create your model in 2D Only or in 3D Only mode. The 2D and 3D mode provides fewer modeling options than the respective 2D Only or 3D Only mode. When you created the model in 2D

<!-- image -->

Only and need to create its 3D part at a later point in time, you can also click on the Home ribbon tab.

Depending on the setting that you chose the new model looks slightly different and provides different ribbon tabs. Likewise SimTalk provides different attributes and methods.

| Function                                             | 3D Only                                                     | 2D Only                                                                                                                    | 2D and 3D                             |
|------------------------------------------------------|-------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------|---------------------------------------|
| Axes origin of the scene                             | objects can be inserted anywhere, the grid adjusts its size | upper left corner of the Frame window objects can only be inserted within the displayed grid, starting at the position 0.0 | upper left corner of the Frame window |
| Standard Graphic of certain Information Flow Objects | small icon next to label                                    | large icon next to label                                                                                                   | large icon next to label              |
| Ribbon                                               | Yes                                                         | Yes                                                                                                                        | Yes                                   |
| File Menu                                            | Yes                                                         | Yes                                                                                                                        | Yes                                   |
| Ribbon > Start                                       | Yes                                                         | Yes                                                                                                                        | Yes                                   |
| Ribbon > Debugger                                    | Yes                                                         | Yes                                                                                                                        | Yes                                   |
| Ribbon > 3D > Edit                                   | Yes                                                         | No                                                                                                                         | Yes                                   |
| Ribbon > 3D > View                                   | Yes                                                         | No                                                                                                                         | Yes                                   |
| Ribbon > 3D > Video                                  | Yes                                                         | No                                                                                                                         | Yes                                   |
| Ribbon > Frame > Frame                               | Yes                                                         | Yes                                                                                                                        | Yes                                   |
| Ribbon > Frame > Frame                               | No                                                          | Yes                                                                                                                        | Yes                                   |
| Ribbon > Frame > Icons                               | No                                                          | Yes                                                                                                                        | Yes                                   |
| Ribbon > Frame > Vector Graphics                     | No                                                          | Yes                                                                                                                        | Yes                                   |
| Ribbon > Method > Edit                               | Yes                                                         | Yes                                                                                                                        | Yes                                   |
| Ribbon > Method > Tools                              | Yes                                                         | Yes                                                                                                                        | Yes                                   |
| Ribbon > DataTable > List                            | Yes                                                         | Yes                                                                                                                        | Yes                                   |

| Function                                       | 3D Only                                                  | 2D Only                                                | 2D and 3D                           |
|------------------------------------------------|----------------------------------------------------------|--------------------------------------------------------|-------------------------------------|
| Context Menu of the Class Library              | 3D-related commands only general and 3D-related commands | no 3D-related commands general and 2D-related commands | 2D-related and 3D- related commands |
| Dialog Box of the Objects > Menus              | 3D-related commands only general and 3D-related commands | no 3D-related commands general and 2D-related commands | 2D-related and 3D- related commands |
| Ribbon > Icon Editor > Edit                    | No                                                       | Yes                                                    | Yes                                 |
| Ribbon > Icon Editor > Animation               | No                                                       | Yes                                                    | Yes                                 |
| Ribbon > Icon Editor > General                 | No                                                       | Yes                                                    | Yes                                 |
| Dialog of Length- oriented Objects > Tab Curve | No                                                       | Yes                                                    | Yes                                 |
| Display Panel                                  | No                                                       | Yes                                                    | Yes                                 |

**3D Only models do not provide the following attributes and methods:**

| Attribute/Method English   | Attribute/Method German       |
|----------------------------|-------------------------------|
| AxesOrigin                 | AchsenUrsprung                |
| BackgroundColor            | Hintergrundfarbe              |
| closeImg                   | schliesseBild                 |
| copyBitmapToClipboard      | kopiereBitmapInZwischenAblage |
| copyBitmapToFile           | kopiereBitmapInDatei          |
| createIcon                 | erzeugeBild                   |
| CurrIcon                   | BildName                      |
| CurrIconNo                 | BildNr                        |
| CurrIconTransparent        | BildTransparent               |
| delAniPoint                | löscheAniPunkt                |
| delAniPoints               | löscheAniPunkte               |

| Attribute/Method English   | Attribute/Method German    |
|----------------------------|----------------------------|
| deleteIcon                 | löscheBild                 |
| DisplayPanel               | Anzeigetafel               |
| drawEllipse                | zeichneEllipse             |
| drawLine                   | zeichneLinie               |
| drawRectangle              | zeichneRechteck            |
| drawText                   | zeichneText                |
| eraseAllLayers             | löscheAlleEbenen           |
| eraseLayer                 | löscheEbene                |
| existsIcon                 | existiertBild              |
| Frame                      | Netzwerk                   |
| getAniPoints               | holeAniPunkte              |
| getBoundingBox             | holeUmgebendesRechteck     |
| getIconSize                | holeBildGröße              |
| getPixel                   | holePixel                  |
| getRefPoint                | holeRefPunkt               |
| getRepresentationArea      | holeDarstellungsBereich    |
| getXYWH                    | holeXYWH                   |
| Icons                      | Symbole                    |
| inheritSizeAndOrientation  | erbeGrößeUndAusrichtung    |
| linkAniPoint               | verbindeAniPunkt           |
| mirrorX                    | spiegelnX                  |
| mirrorY                    | spiegelnY                  |
| moveAniPoint               | verschiebeAniPunkt         |
| NumAnimationEvents         | AnzahlAnimationsereignisse |
| ObjectAngle                | ObjektWinkel               |
| ObjectMirrored             | ObjektGespiegelt           |
| openImg                    | öffneBild                  |
| putIconToClipboard         | legeBildInZwischenablage   |
| rearrange                  | aufräumen                  |

| Attribute/Method English   | Attribute/Method German    |
|----------------------------|----------------------------|
| redraw                     | zeichneNeu                 |
| redraw                     | zeichneNeu                 |
| RepresentationMode         | DarstellungsModus          |
| resetIcon                  | rücksetzen                 |
| RotateAroundRefPoint       | DreheUmRefPunkt            |
| RotateMUs                  | DreheBEs                   |
| saveIconToFile             | sichereBildInDatei         |
| ScalingFactor              | SkalierungsFaktor          |
| selectContents             | selektiereInhalt           |
| selectionToClipboard       | selektionInZwischenablage  |
| setAniLine                 | setzeAniLinie              |
| setAniPoint                | setzeAniPunkt              |
| setBackgroundImage         | setzeHintergrundBild       |
| setCurrIconFromClipboard   | setzeBildAusZwischenablage |
| setIconFromFile            | setzeBildAusDatei          |
| setIconSize                | setzeBildGröße             |
| setPixel                   | setzePixel                 |
| setPosition                | setzePosition              |
| setRefPoint                | setzeRefPunkt              |
| setRepresentationArea      | setzeDarstellungsBereich   |
| setXYOrigin                | setzeXYUrsprung            |
| setXYWH                    | setzeXYWH                  |
| ShowDisplayPanels          | AnzeigetafelnAnzeigen      |
| ShowObjectLabels           | ObjektetikettenAnzeigen    |
| ShowObjectNames            | ObjektnamenAnzeigen        |
| StatusWithIcons            | ZustandsanzeigeMitBild     |
| turnIcon                   | dreheBild                  |
| unlinkAniPoint             | löseAniPunkt               |
| XPos                       | XPos                       |

| Attribute/Method English   | Attribute/Method German   |
|----------------------------|---------------------------|
| YPos                       | YPos                      |
| ZoomFactor                 | ZoomFaktor                |
| ZoomX                      | ZoomX                     |
| ZoomY                      | ZoomY                     |

Go to Select Modeling Options for the Frame

Back to Select Settings in Plant Simulation

##### Select Modeling Options for the Frame

Select on the tab 2D which items the Frame shows on the View Ribbon Tab [2D only] . Which features you want to show or hide largely depend on your modeling situation. The more items you choose to show in the Frame , the more cluttered its display gets. We recommend to experiment with the different settings.

<!-- image -->

**Note**

You can override these settings for each individual Frame on the ribbon tab View &gt; More View Options .

<!-- image -->

If it annoys you that Plant Simulation opens a dialog prompting you to confirm, when you delete objects , clear the check box Confirm .

<!-- image -->

If you want to use another spacing for the grid in the Frame , enter a larger or a smaller number for the Frame grid .

Compare Select Options in the Frame in 2D

Back to Select Settings in Plant Simulation

##### Select Options for Units and for Displaying the Time

As daylight saving time is widely used internationally, you will also use it in your simulation model.

<!-- image -->

**Note**

To select units and time settings, which only apply to the active model, select File &gt; Model Settings &gt; Units .

To select units and time settings, which apply to all new models, select File &gt; Preferences &gt; Units .

- Select the check box Daylight Saving Time .
- If the plant you are modeling is located in the European Union , you do not have to change the default settings. Here daylight saving time starts at 02:00 o'clock in the morning Greenwich Mean Time (GMT) on the last Sunday in March. It ends at 03:00 o'clock in the morning on the last Sunday in October. In the EU, all time zones change at the same moment.
- If the plant you are modeling is located in the United States of America , you have to change the settings. For most of the US daylight saving time starts at 02:00 o'clock in the morning on the second Sunday of March. It ends at 02:00 o'clock in the morning on the first Sunday of November.

<!-- image -->

If your specific modeling needs require it, you can also change the display of the Time Scale . You can enter a number between 0 and 86400 . You can enter an integer greater than 1 into the text boxes next to Transfer If .

You might, for example, divide a minute into 100 units, instead of in 60 seconds, or you might want to read 1:50 as 1.5 hours instead of 1 minute and 50 seconds.

**Note**

You can only change the display of the time scale, not the time scale itself. You can only change these settings if no simulation model is open!

A time statement consists of four numbers, separated by colons, normally in the format days:hours:minutes:seconds . Plant Simulation stores the value itself in seconds and converts it at output time for the display .

Plant Simulation converts times according to the values you enter into the text boxes Time Scale and Transfer If .

The following examples illustrate what to enter to achieve different displays of the time:

- If you want to use the standard time format, 24 hours to the day, 60 minutes to the hour, 60 seconds to the minute, use the default setting Time Scale 1/1.0 Transfer if 24:60:60 .
- If you want to simulate a longer period of time and want to display the time in the format years:months:days:hours , enter Time Scale 1/ 3600 Transfer If 12 : 30 : 24 , as an hour has 3600 seconds, a year has 12 months, a month has 30 days, and a day has 24 hours.
- If you want to divide a minute into 100 subunits instead of 60 seconds, enter Time Scale 1/ 0.6 Transfer If 24 : 60 : 100 .

Compare Select Options in the Frame in 2D

Compare Units [preferences]

Back to Select Settings in Plant Simulation

#### Changing the Settings of the Objects

##### Change the Settings of the Objects

You can change the settings of the objects, i.e., the values of attributes, in a number of ways.

You can:

- Change Values in the Dialog of the Objects
- Change Values by Assigning a Value in SimTalk
- Change Values in the Window Show Attributes and Methods
- Change Values with the AttributeExplorer

Back to Working with Plant Simulation, Basics

##### Change Values in the Dialog of the Objects

As a rule you are going to select the settings of the individual objects in your simulation model in the dialogs of the respective objects.

To do so, you either enter a value into a text box .

<!-- image -->

Or you select a value from a drop-down list .

<!-- image -->

Or you check or clear a check box to activate or to deactivate a setting. Instead of clicking the check box itself, you can also click its label .

<!-- image -->

All of these settings correspond to attributes which you can also access with the programming language SimTalk . The What's This help for the respective dialog item shows the name of the attribute in the bottom row below SimTalk .

Back to Change the Settings of the Objects

<!-- image -->

##### Change Values by Assigning a Value in SimTalk

You can also change the settings, which you can select in or type into the dialogs of the objects, by assigning a value to an attribute in SimTalk . Compare the examples below.

To set a constant Processing Time of three minutes , you can type the setting below into the dialog.

<!-- image -->

Or you can type this instruction into a Method :

<!-- image -->

**Paths in SimTalk Instructions**

In the example we inserted the material flow object MyStation into the Frame called Models . This is why the title bar of the station MyStation shows the absolute path .Models.MyPlantAnytown.MyStation .

As we inserted the Method named MyMethodMyStation into the same Frame as the station MyStation , which the title bar of the Method also shows, we can type in the instruction MyStation.ProcTime := 180 or MyStation.ProcTime := 3:00 and do not have to type the entire path, i.e., .Models.MyPlantAnytown.MyStation.ProcTime := 180 .

Within the instruction MyStation.ProcTime := 180 the term MyStation designates the object for which the instruction applies. This is followed by a separator, namely a period . , followed by the name of the attribute which we want to change, ProcTime in our case. The value after the assignment operator := , without a blank space between the colon and the equal sign, is assigned to the value of the attribute while the is being executed, 180 , i.e., three minutes in our case.

To set the Exit Strategy &gt; Linear sequence , you can select it in the drop-down list and then type the numbers of the successors of the Station into the List that clicking the button Open List opens.

<!-- image -->

Or you can type these instructions into a Method :

<!-- image -->

**Note**

When you type a string into an assignment, Plant Simulation does not differentiate between sentence case and lower case.

When you query the value, it shows it in sentence case as the respective drop-down list shows it. In the example above you could type 'Linear sequence' , 'linear sequence' , 'LINEAR SEQUENCE' , etc.

When you query the value with print , Plant Simulation shows Linear sequence .

To manually set the Station up, clear the check box Automatic .

<!-- image -->

Or you can type this instruction into a Method :

<!-- image -->

Back to Change the Settings of the Objects

##### Change Values in the Window Show Attributes and Methods

You can also access the values of the settings of the objects in the window Show Attributes and Methods of the respective object.

- To open the dialog, click the object and press the F8 key.
- Then, double-click the respective attribute.
- Enter the new value into the dialog that opens or select a value in the drop-down list.

<!-- image -->

To switch the value of an attribute of data type boolean from true to false and vice versa, double-click the row of the attribute in the window Show Attributes and Methods .

<!-- image -->

Compare Simultaneously Show and Change Attributes of Several Objects

Compare Working with the Window Show Attributes and Methods

Back to Change the Settings of the Objects

##### Change Values with the AttributeExplorer

Instead of opening the dialog of each and every material flow object in your model and entering values for a single attribute or for a number of attributes into the text boxes, you can define which attributes of which objects the AttributeExplorer gets.

This way you can manage the attributes defining the settings of the individual stations in your simulation model at a single location. You can then enter different values for the capacities, the times, etc. Plant Simulation writes these values back to the dialogs of the objects and uses them in your simulation model. You can also export this settings table as a tab-delimited text file and import this file into the AttributeExplorer of another simulation model, thus using identical settings in several of your simulation models.

You can also use the AttributeExplorer to find objects of the type you define, to find attributes, for example the position of a number of objects. You can then align them in the Frame , etc.

Compare Set Parameters with the AttributeExplorer

Compare Specify the Attributes You Want to View or Change

Back to Change the Settings of the Objects

#### Finding Objects and Text in Your Simulation Model

Find Objects and Text in Your Simulation Model

Proceed as follows to find the name of an object, a condition , an expression contained in an attribute , part of the source code of a Method , or an expression contained in a table in your simulation model:

1. Click the Frame ribbon tab and click Find Object .

<!-- image -->

Or click the right mouse button anywhere in the Class Library and select Find Object on the context menu.

<!-- image -->

2. Select what you want to find from the left drop-down list.

<!-- image -->

Compare Find Objects and Attributes using the AttributeExplorer Back to Working with Plant Simulation, Basics Video on YouTube https://youtu.be/FNpiAaUK8iM?si=B1tgMoMpdc03wCmj&amp;t=437

##### Find the Name of an Object

To find the name of an object you inserted into your simulation model:

1. Select Name from the left drop-down list.
2. Type in the name of the object you want to find into the right drop-down combo box. We entered Station .
3. If you do not select the check box Match Whole Word Only , Plant Simulation finds all words that contain the word you entered.

In our example it finds all word containing the word Station , such as Station , Station1 , Station11 , MyStation , etc.

<!-- image -->

4. Type the name of the folder or the Frame into the text box Look In , where Plant Simulation is going to start searching for the expression you entered into the text box.

Instead, you can also click and select a folder or a Frame in the dialog Select Object .

To search on the highest level of the structure, accept the default setting that Plant Simulation enters, namely the period ( . ).

5. Select Include Subframes to also search all Frames located in the Frame in which the item you are searching for is located.
6. Click Find , to start searching.

7. Double-click the name of the object in the results field, to open its dialog. You can then change any of the settings.
8. If you select Match Whole Word Only , Plant Simulation only finds entire words that exactly match the word you entered. In our example it only finds the word Station .
9. If you select Match Whole Word Only , and also select Match Case , Plant Simulation only finds words that exactly match the word you entered, including upper and lower casing. In our example it only finds the word Station .
10. If you select Regular Expression , Plant Simulation also finds the regular expression you select. Click and select any of the items displayed in the window Regular Expression . Plant Simulation enters the special characters designating that expression into drop-down combo box to the right.

<!-- image -->

| Select                           | To enter and to find   |
|----------------------------------|------------------------|
| Any single character             | .                      |
| Beginning of line                | ^                      |
| End of line                      | $                      |
| Beginning of word                | \<                     |
| End of word                      | \>                     |
| Group                            | \(\)                   |
| Zero or one matches              | ?                      |
| Zero or more matches             | *                      |
| One or more matches              | +                      |
| Any one character in the set     | []                     |
| Any one character not in the set | [^]                    |
| Or                               | \&#124;                |

Searching with regular expressions enables you to use wild cards in the string you are searching for.

- To find all strings that contain a sequence of the character a , followed by any character, and the character b , enter a.b into the text box.
- To find all objects whose name starts with an upper case S, enter ^[S] .
- To find all objects whose name does not end with an e, enter [^e]$ .
- To find all objects whose name contains an upper case L, followed by any character, followed by proc, enter L.*proc into the text box.

**11. Click Find .**

Back to Find Objects and Text in Your Simulation Model

##### Find a Condition of an Object

To find a condition of an object you inserted into your simulation model:

1. Select Condition from the left drop-down list.
2. Enter any SimTalk expression whose attributes or methods are identical to the expression you enter in the drop-down combo box.
3. You might, for example, enter the name of an attribute or a method and the expression you are looking for, such as proctime = 100 , or OpenCtrl = void , etc.
3. Repeat steps 4 to 7 described under Find the Name of an Object
4. Click Find .

<!-- image -->

Back to Find Objects and Text in Your Simulation Model

##### Find Text in a Built-in or a User-defined Attribute of an Object

To find any text or any value contained in a built-in or a user-defined attribute of an object which you inserted into your simulation model:

1. Select Attribute from the left drop-down list.
2. Enter any text or value contained within a built-in or a user-defined attribute of an object in the search scope.

<!-- image -->

Plant Simulation shows the name of the attribute in which the text was found in parenthesis after the object in the results list.

3. Repeat steps 4 to 7 described under Find the Name of an Object
4. Click Find
3. .

Back to Find Objects and Text in Your Simulation Model

##### Find Any Source Code in a Method

To find any text, which you entered as source code into any Method object which you inserted into your simulation model or in any user-defined attribute of data type method :

1. Select Source Code from the left drop-down list.
2. Enter any text or value contained within the source code of a Method in the search scope.
3. Repeat steps 4 to 10 described under Find the Name of an Object .
4. When you select Ignore Inherited Name or Text Plant Simulation then only finds the original source code you entered into a Method object, and not the source code in derived or duplicated objects.
5. Click Find .
6. To open the Method that Plant Simulation found and to jump to the first occurrence of the item, double-click it in the results pane. Double-clicking or selecting Open again jumps to the next occurrence of the found item.
7. To jump to the previous occurrence in the source code, hold down Shift and double-click.

<!-- image -->

<!-- image -->

7. To replace the found source code with other source code, click one or several Methods in the results list with the right mouse button and select the command Replace With . Then, enter the replacing source code into the dialog which opens.

<!-- image -->

Compare Find Text [in Method]

Back to Find Objects and Text in Your Simulation Model

##### Find Any Value within a List or Table

To find any text or value contained in an object of type list or table which you inserted into your simulation model:

1. Select Table from the left drop-down list.
2. Enter any text or any value contained within a list or table in the search scope.
3. Repeat steps 4 to 7 described under Find the Name of an Object .
4. Click Find .

<!-- image -->

Back to Find Objects and Text in Your Simulation Model

### Modeling the Material Flow

