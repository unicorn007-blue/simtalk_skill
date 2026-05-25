# 7. Introducing Plant Simulation

## Introducing Plant Simulation

Introducing Plant Simulation provides a short overview to Plant Simulation which is intended for the new user of Plant Simulation .

We will create a simple simulation model and explain the underlying concepts of the terms:

## Simulation Properties and 3D Properties

- Simulation Properties
- 3D Properties

We also will:

- Create a Simulation Model
- Display Simulation Results

You might also want to familiarize yourself with the Components of the Program Window .

Also consult the Plant Simulation Step-by-Step Help

Getting to Know Plant Simulation

Modeling the Material Flow

Visualizing the Material Flow in 3D

Animate the Simulation Model in 2D and View the Results

Import Data for the Simulation

Set Parameters in the Model

Also consult the Plant Simulation Reference Help

What's New

Update Arbitrary Old Models

The Components of the Program Window The Objects Reference Help The SimTalk Reference The Outdated SimTalk Names The 3D Help The SimTalk Access to 3D

The Quick Reference Cards

The Add-Ins Reference Help

The Libraries Reference

**Video on YouTube**

[https://youtu.be/DFy8bH5yYeI?si=0TsUWBvG3imZcYDl](https://youtu.be/DFy8bH5yYeI?si=0TsUWBvG3imZcYDl)

**Simulation Properties and 3D Properties**

### Simulation Properties and 3D Properties

The simulation properties , which control the simulation , and the 3D properties , which show the simulated material flows during the simulation, work together and run concurrently in Plant Simulation .

The simulation properties control the simulation of the material flows. The material flow objects collect statistics values during the simulation, which we show in tables and different diagrams and from which we can draw conclusions according to the defined targets.

We explain the:

- Simulation Properties Controlling the Simulation
- Simulation Properties

The 3D properties show the simulated material flows during the simulation in a graphically pleasing and clear way.

We explain the:

- 3D Properties Visualizing the Simulation
- 3D Properties

Go to Simulation Properties Go to 3D Properties

Back to Introducing Plant Simulation

### Simulation Properties Controlling the Simulation

In our material flow simulations we want to identify the optimum of capacities, resource utilization, and buffer sizes so that the installation produces the required output.

According to VDI (Verein Deutscher Ingenieure, Association of German Engineers, Directive 3633, Blatt 1, 1993) we run simulations to emulate a system, including its dynamic processes, in a model one can experiment with, to achieve results that can be transferred to a real world plant.

To do so, we, for example, check the utilization of the machines, their processing, set-up, and failure times; we identify bottlenecks in the production process, we optimize the layout of the installation, to find out the optimal dimensioning of the materials-handling technology, etc.

We control the simulation with the simulation properties on the tabs of the dialogs of the material flow objects , the resource objects , the mobile objects , and the fl uid objects . We open the dialogs of the objects by double-clicking their icon.

<!-- image -->

<!-- image -->

Simulation and Modeling Concepts and the subtopics What is Simulation? , Time-Oriented Simulation and Event-Controlled Simulation , Why Use Simulation? , and Implement a Simulation Project in the Step-by-Step-Help describe this in detail.

Back to Simulation Properties and 3D Properties

### Simulation Properties

You can set the simulation properties , which control the simulation, on the tabs of the dialogs of the objects.

The material flow objects , the resource objects , the mobile objects , and the fl uid objects provide simulation properties.

To access the simulation properties, double-click the icon of the respective object in the Frame named Model .

<!-- image -->

You can set these settings for the simulation of the material flows:

- Define times on the Tab Times [general description] .
- Select set-up properties on the Tab Set-Up [general description] .
- Define interruptions (failures, pauses) on the Tab Set-Up [general description] .
- Define controls, which react on events during the simulation, on the Tab Controls [general description] .
- Define the exit behavior, which controls the material flow, on the Tab Exit [general description] .
- View statistics values on the Tab Statistics [material flow objects] .
- Select settings for importing services on the Tab Importer [general description] .
- Select settings pertaining to the power input and to the transition times from one energy state to another on the Tab Energy [general description] .

- Select settings for costs, which accrue for the active material flow objects on the Tab Costs [material flow objects] .

You can always do this in Plant Simulation :

- Change Values in the Dialog of the Objects
- Change Values in the Window Show Attributes and Methods
- Change Values by Assigning a Value in SimTalk

You can change to the 3D Properties by clicking the Edit 3D Properties [button] in the bottom left corner of the dialog. This opens the Edit 3D Properties [dialog] .

Back to Simulation Properties and 3D Properties

<!-- image -->

### 3D Properties Visualizing the Simulation

The 3D properties visualize the material flow/parts flow through the installation and thus allow to track the journey of the parts. In addition you can replace the graphics of the material flow objects with graphics of your machines and then animate these graphics with poses to make them look more realistic. This makes it easier to understand the processes and procedures in the model for the modeler and for managers or customers who are to be convinced of the simulated solution.

Plant Simulation animates the simulation model automatically in 2D as well as in 3D, as we show below.

If you do not need the animation or would like the simulation to run faster, you can deactivate the

<!-- image -->

animation by clicking

You can set the 3D properties of the objects in 3D by clicking the respective object once in the model window and by then pressing the spacebar .

<!-- image -->

<!-- image -->

If the dialog with the simulation properties is open, you can click the 3D button to open the dialog Edit 3D Properties .

<!-- image -->

**See also**

Animate the Simulation Model in 2D and View the Results

**Back to**

Simulation Properties and 3D Properties

### 3D Properties

Set the 3D properties of the objects in 3D by clicking the object once in the model window and by pressing the spacebar .

<!-- image -->

In Edit 3D Properties [dialog] you can:

- View or change the Name [text box] - 3D of the object or of the graphic.
- Define extrusion settings for objects which are length-oriented in 3D on the tab Appearance of the Length-oriented Objects .
- Define the main material of the selected object in 3D on the tab Appearance of Objects and MUs . You might, for example, override the color when you activated vector graphics on the tab Graphics [tab, MUs, 2D] of the MUs in 2D.
- Define the configuration of the Store in 3D on the Appearance of the Store .
- Specify settings for the background color of the Frame or of the folder on the tab Background [tab] Frame in 3D .
- Specify settings for the camera animation of the Frame on the tab Camera Animation [Frame] . Only the Frame provides this tab.

- Activate or deactivate captions , which you created, on the tab Captions . You can show or hide the

<!-- image -->

Names and/or Labels of the objects in 3D by clicking ribbon tab.

- Activate or deactivate graphic inheritance and the inheritance of the visibility and select settings for visibility of the object toward the outside on the tab Graphics [tab, 3D] . In addition, you can show the graphics structure of this object and set if the object is an obstacle for the worker or not.
- Set graphic sequences , which the Worker uses when he is just walking or walking and carrying a part on a Footpath on the tab Graphic Sequences . This ensures that the Worker looks as realistic as possible in your simulation model.
- Select if the graphic of the object is an obstacle for the Worker on the tab Graphic Settings .
- Define settings for rotating and translating the animation joints of the animation objects on the tab Joint .
- Specify settings for the material of graphics on the tab Material [tab] .
- Specify settings for the animation of the parts on the material flow object on the tab MU Animation [3D] .

All material flow objects provide this tab.

Specify point cloud settings for the Frame on the tab Point Cloud .

- Define settings for poses of the joints of the animation objects on the tab Poses .
- Specify settings for the animation of the robot arm of the PickAndPlace Robot on the tab Robot Arm Animation .

Only the PickAndPlace Robot provides this tab.

- Specify settings for the animation of objects , which you can insert into a Frame , and for the animatable objects on the tab Self Animation .

All material flow objects provide this tab.

- Specify properties of the state graphic of the objects on the tab States .
- Specify transformation settings for graphics on the tab Transformation [3D object] .
- Select additional commands on the Navigate Menu , the View Menu , and the Help Menu .

<!-- image -->

You can always do this in Plant Simulation :

- Change Values in the Dialog of the Objects
- Change Values in the Window Show Attributes and Methods
- Change Values by Assigning a Value in SimTalk
- Click the Open Simulation Settings button or Open [simulation settings dialog] to change the simulation properties .

<!-- image -->

Back to Simulation Properties and 3D Properties

**Video on YouTube**

[https://youtu.be/jHOZhlwGhkQ?si=88kNGkp5iKl66PSL&amp;t=24](https://youtu.be/jHOZhlwGhkQ?si=88kNGkp5iKl66PSL&t=24)

## Creating Simulation Models

### Create a Simulation Model

Proceed as follows to create our simulation model:

- Start Plant Simulation .
- Click Create New Model on the Start Page .

<!-- image -->

Plant Simulation shows a dialog, in which you can select if you would like to create the simulation model in 2D or in 3D.

<!-- image -->

Generally we recommend to always create the models in 3D . This way you have a model that shows a graphically pleasing and good-looking visualization of the material flow and that clearly resembles the actual look of the modeled installation.

A 2D model is ideal if the visualization of the material flow is not that important for you and if you are mainly interested in the statistical data that the material flow objects collected.

We created our model in 3D. By default, we model in three-dimensional space.

If you prefer to model in top view, i.e., in two dimensions, change to the View tab and click Use

**Planning View**

<!-- image -->

- Start creating the model.

Insert the required material flow objects from the tab Material Flow in the Toolbox . These objects simulate the flow of the parts through our installation.

<!-- image -->

<!-- image -->

Click the respective object with the left mouse button. Drag the mouse to the position of your choice in the Frame named Model and click the left mouse button once.

<!-- image -->

- The Source produces the part which the stations process or convey between the stations.
- The Station doing the rough-processing of the parts.
- Two more Stations further process the parts.
- The PickAndPlace robot which places the arriving parts to the conveyor.
- The Conveyor which moves the parts to the Drain

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

.

- The Drain which removes the parts from the installation.

Then, connect the inserted objects so that the parts can flow between the stations. To do so, hold

<!-- image -->

down the Ctrl key, click the Connector in the Toolbox , drag the mouse to the Frame named Model , and click the objects one after the other.

The finished model looks like this:

<!-- image -->

You can now run a simulation with an appealing visualization with the factory settings .

Click Start/Stop Simulation on the Start ribbon tab.

<!-- image -->

You can also hide the grid on the View ribbon tab as it is only intended as a modeling help.

<!-- image -->

To better see the effects of changed simulation properties , insert a Chart which clearly shows the changed settings.

To add the objects to the Chart , press Ctrl+A to select all objects in the Frame . As we are only interested in the material flow objects, we then hold down Ctrl and click the EventController , the Source , the Drain , and the Chart to deselect them. Then, drag the selected objects onto the icon of the Chart and drop them there. Select Resource Statistics in the dialog Statistics Type .

<!-- image -->

After the simulation did run, click the Chart with the right mouse button and select Show . The standard settings of the objects provide these results:

<!-- image -->

The Station is working 100 % of the time, the following Stations are working 50 % of the time each, Robot and Conveyor are working 100 % of the time.

After having run the simulation with the factory settings of simulation and animation , you can:

- Change Simulation Settings Controlling the Simulation
- Change 3D Settings Controlling the Visualization
- View Information About the Objects

Compare Working with the Frame

Compare Modeling the Material Flow

Back to Simulation Properties and 3D Properties

Go to Display Simulation Results

Back to Introducing Plant Simulation

**Create a Simulation Model**

### Change Simulation Settings Controlling the Simulation

You can change the simulation settings of the objects to simulate different scenarios with changed values.

- You can, for example, increase the processing time of the Station located at the top, named Station1 , from 10 seconds to 2 minutes.

<!-- image -->

The changed processing time has these effects:

<!-- image -->

The working portion of the Station fell to 70 %, while it rose for the following Stations , the Robot is now waiting for parts, and the Conveyor is still working 100 % of the time.

- Then, increase the time factor of the PickAndPlace robot from 1 to 2 .

<!-- image -->

The changed time factor has these effects:

<!-- image -->

The working portion of the Station and the following Stations fell, the Robot is working 100 % of the time again, the working portion of the Conveyor did not change.

Go to Change 3D Settings Controlling the Visualization

Go to View Information About the Objects

Back to Create a Simulation Model

### Change 3D Settings Controlling the Visualization

After changing simulation settings, let's change some of the 3D settings :

- For the Conveyor select another configuration so that it resembles the conveyor in your plant. To do so, click the Conveyor once with the left mouse button and press the spacebar .

Instead of the default belt conveyor let's use a roller conveyor with arched T-based legs spaced spaced 1.5 meters from each other. It then looks like this:

<!-- image -->

- As our white part is hard to see during the simulation, change its color. As we want to do this for all produced parts, edit the Class of the Part .

To do so, change to the Class Library , open the folder MUs , and double-click the Part . This opens the dialog of the simulation settings . There, click to open the dialog of the 3D settings . Then activate the material of the Part and select brown as the color.

<!-- image -->

When you then run the simulation, you see that the part now has the color that you selected, namely brown.

<!-- image -->

- Next, replace the graphic of our robot so that it matches the robot in our installation:
- Click the robot with the right mouse button and select Exchange Graphics .

<!-- image -->

- Select the Comau PickAndPlace robot .

<!-- image -->

- As the robot is too far away from the feeding Stations , you have to adjust the positions as shown below. Drag a marquee around the robot , the Conveyor , and the Drain and press the Left arrow key until the position fits.

<!-- image -->

Animating the Robot Arm in 3D shows how to prevent that the robot arm moves through the protective cover and the parts holder and moves above both.

- As we do not like the position of the EventController , the clock lying flat on the floor, we change that as well. To do so, click the EventController with the left mouse button and press the spacebar .

The standard settings on the tab Transformation look like this:

<!-- image -->

We changed these settings in our model:

- We moved the Z Position of the EventController up to 2 meters.

- We rotated the clock by 45 degrees forward on the X Axis . To do so, we typed in 45 as the Angle and clicked the button next to Axis X .

<!-- image -->

Back to Change Simulation Settings Controlling the Simulation

Go to View Information About the Objects

Back to Create a Simulation Model

### View Information About the Objects

Plant Simulation shows information before and after the simulation run in the model Frame :

- To show a tooltip with information about an object, drag the mouse over it and hover.
- The EventController shows the current simulation time and the End Time that you entered.
- The Source shows its Origin , the MU it produces, and its current State .
- The MU shows its Origin and its Number , the Object on which it is located, and the FinishedTime .
- The PickAndPlace robot shows its Origin , the Destination object onto which it places the part, its State , and the Next event .

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

- The Conveyor shows its Origin , the Predecessor which delivered the part, and the Destination object of the part, and its State .
- The Drain shows its Origin and its State .
- To show additional information about the object, check the commands on the View Menu .

<!-- image -->

<!-- image -->

<!-- image -->

Compare Show Tooltips of Objects in the Frame

Back to Change Simulation Settings Controlling the Simulation

Back to Change 3D Settings Controlling the Visualization

Back to Create a Simulation Model

## Displaying Simulation Results

### Display Simulation Results

After Plant Simulation has executed the simulation run, we can show and analyze the simulation results. To do so, we use Display and User Interface Objects .

<!-- image -->

We inserted a Chart , a SankeyDiagram , and an HtmlReport each. We use these objects with their respective standard settings.

<!-- image -->

- The Chart shows resource statistics of the material flow objects which we selected. After we executed the simulation, we click the Chart with the right mouse button and select Show . The standard settings provide these results:

<!-- image -->

- The SankeyDiagram shows the flows of parts through the installation with arrows in different widths. We see that more parts take the route across Station2 than Station1 .
- The HtmlReport shows general information about the simulation model and state statistics and Drain statistics values.

<!-- image -->

<!-- image -->

- In addition each object shows the most important values on its tab Statistics .

In the dialogs of the objects you can display What's This Help for the individual dialog items. To do so, click the question mark on the title bar of the dialog box and then on the dialog item for which you need help. What's This Help shows a description of the dialog item and the name of the programming command with which you can set or query it.

<!-- image -->

Finally, we run the simulation with deactivated animation . Then Plant Simulation neither shows the parts nor the movement of the Robot during the simulation.

<!-- image -->

<!-- image -->

To better see that, we only simulate for 24 hours. To do so, we type in an end time of 24 hours on the tab Settings of the EventController .

<!-- image -->

The results of the simulation run without animation are the same as those of a simulation run with animation. The statistics values, which the Drain collected, confirm this:

<!-- image -->

Compare these topics in the Step-by-Step Help :

- Animate the Simulation Model in 2D and View the Results
- View and Visualize Statistics
- View Statistics in the Dialogs of the Objects
- Show Statistics in a Chart
- Viewing the Statistics Report

**Display Simulation Results**

- Show Statistics and Other Values in a Report
- Show Values During the Simulation with the Display
- Show Part Flows in a SankeyDiagram
- Show Parts on Resources in a GanttChart

Back to Simulation Properties and 3D Properties Back to Create a Simulation Model Back to Introducing Plant Simulation

