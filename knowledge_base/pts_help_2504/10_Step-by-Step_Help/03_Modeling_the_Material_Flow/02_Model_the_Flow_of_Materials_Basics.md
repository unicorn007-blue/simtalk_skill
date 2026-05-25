### Model the Flow of Materials, Basics

Below we introduce you to the basics of modeling the flow of materials in your simulation model. We'll show:

- How to create or introduce parts into your model with the object Source .
- How to select and enter for how long a station processes the parts that move onto it.
- How to set a station up to process another type of part.
- How to transfer the parts from processing station to processing station .
- How to model failures and failure times of the processing stations.
- How to remove the processed parts from your model with the object Drain .

Go to Active and Passive Objects

**Active and Passive Objects**

Go to Produce Parts with the Source

Go to Produce and Process Parts with a Work Plan

Go to Remove Parts from the Installation with the Drain

Go to Transfer Parts from Station to Station

Go to Set a Station Up

Go to Define Processing Times

Go to Model Failures

Go to Buffer Parts within the Production Line

Go to Place Parts into Stock and Remove Parts from It

Go to Use the Store as Supermarket

Go to Stack Parts in the Store

Go to Loading a Container Layer by Layer

Go to Work with Workpiece Carriers

Go to Balance a Production Line

Go to Model the Flow of Materials, Advanced

Back to Modeling the Material Flow

#### Active and Passive Objects

Mobile and stationary material flow objects are the basic items you use when you create a simulation model.

- The mobile material flow objects Part , Container and Transporter represent the physical or logical parts moving through the model, i.e., your installation. These mobile objects ( MUs ) require active and passive material flow objects to process and transport them.
- The Source creates mobile objects at the beginning of the flow of materials through your plant. The Drain removes the MUs from the plant after the material flow objects processed them.
- The FluidSource creates fl uids at the beginning of the flow of materials through your plant. The FluidDrain removes the fluids from the plant after the fluid objects processed them.

- The active material flow objects Drain , Station , ParallelStation , AssemblyStation , DismantleStation , Conveyor , Sorter , PlaceBuffer , and Buffer receive MUs , and process them for a certain time. They then attempt to actively transfer the MUs to the next object along material flow connections, symbolized by the Connector , using the push-block principle . They represent work stations in a factory, such as a lathe or a drilling station, etc. They only differ in the number of MUs they can process at the same time, a single one or several, and in the way they process them, in series or in parallel. Basically, the Conveyor resembles a conveyor system transporting MUs at a given speed over a given distance.
- The active fluid objects FluidDrain , Tank , Mixer , Portioner , and DePortioner receive fl uids , and process them for a certain time. They then attempt to actively transfer the fluids to the next object along material flow connections, symbolized by the Connector , using the push-block principle .
- The passive material flow objects Store , Track , and TwoLaneTrack do not automatically transfer MUs . A MU remains in the Store until it is removed, for example by using a Method . You can only use the Track and the TwoLaneTrack in a meaningful way in conjunction with the Transporter , which drives along the Track/TwoLaneTrack with the speed you set. Model diverging strategies and converging strategies with the FlowControl .
- The passive fluid objects Pipe and PatchMatrix transport the fl uids to their respective successor in the flow of materials.

We also distinguish between active and passive MUs :

- Active MUs are objects that can move by themselves, such as the Transporter , which can be selfpropelled, and the Worker , who represents a human.
- Passive MUs , such as the Part and the Container , are objects that are transported from material flow object to material flow object, which process them. The Part represents any workpiece that is produced and processed. The Container represents any type of receptacle, such as a storage bin or a pallet.

In addition, we differentiate between:

- Point-oriented material flow objects in which the MUs are located on a fixed processing place. For the Source , the Drain , the Station , the ParallelStation , the AssemblyStation , the DismantleStation , the Sorter , the PlaceBuffer , and the Buffer their own real length and their dimension as well as the length and the dimension of the MUs , which transfer onto them, are irrelevant for the simulation.
- Length-oriented material flow objects whose own real length and dimension as well as the length and the dimension of the MUs , which transfer onto them, are used during the simulation. Length-oriented objects are the Conveyor , the Track , the TwoLaneTrack , the FootPath , the Pipe ,the Container , and the Transporter .

As opposed to the regular length-oriented objects, the Turntable consists of a single straight segment, not of a sequence of straight and curved segments. The Turnplate consists of a straight segment that sets the diameter of the Turnplate . The AngularConverter consists of two straight segments, not of a sequence of straight and curved segments. The Converter consists of a single straight segment.

Compare Work with Length-oriented Objects in 2D and 3D

Compare Work with Length-oriented Objects in 3D

**Back to Model the Flow of Materials, Basics**

#### Producing Parts with the Source

Produce Parts with the Source

To create the MUs , which the material flow objects in your simulation model handle, we use the object Source . It might, for example, represent the receiving department of your installation that introduces parts produced at another location into the plant. Or it can be a machine, which produces the parts that the other stations process.

To remove these parts from the factory to model, for example, the shipping department, we use the object Drain .

You can insert the Source into your simulation model from the folder MaterialFlow in the Class Library or from the toolbar Material Flow in the Toolbox .

<!-- image -->

You can:

- Select How the Source Proceeds, When it Cannot Produce MUs
- Produce Parts According to a Delivery Table
- Produce Parts During an Interval Which You Define
- Produce the Number of Parts You Need
- Produce Parts Using a Trigger Object

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

Compare Check How Many Parts Were Introduced into the Plant

Compare Remove Parts from the Installation with the Drain

Back to Model the Flow of Materials, Basics

##### Select How the Source Proceeds, When it Cannot Produce MUs

Select how the Source proceeds when it cannot create the MUs at the Time of creation that you entered because it cannot move the parts on to its successor. This is the case when it fails, when it is paused, or when it is blocked.

- Select the Operating Mode &gt; Blocking , so that the Source remembers the time at which it was supposed to produce the next MU but could not. It then produces the following MU at the next possible point in time, i.e., if the MU , which blocked it, has moved on.
- Clear Blocking , so that the Source creates another MU exclusively at the time of creation you entered.

<!-- image -->

**Note**

When the Source is temporarily not operational because it is Failed , Paused , or Blocked , the times of creation may shift, if you select Blocking . Then, the settings for the times of creation cannot be realized.

**Back to Produce Parts with the Source**

##### Produce Parts According to a Delivery Table

For the installation you are modeling you will, most likely, use a delivery table that contains the parts that a machine produces, parts provided by other departments within the same plant, or parts delivered from other plants.

Most of the time the delivery table you receive from another department will be a Microsoft Excel file containing, among others, the name of the part, its amount, its arrival time, etc. You will then open this Excel (*.xls) file in a Plant Simulation table and save it there.

<!-- image -->

To produce MUs according to the time, the type, and the number of parts you typed into a Delivery Table :

- Select Time of Creation &gt; Delivery Table .
- Click and select the delivery table you would like to use in the dialog Select Object . Or Drag your delivery table over the text box Table and drop it there.
- Click OK .

Next to information about the name and number of the produced parts, the Delivery Table may also contain values of their attributes. The Delivery Table has five columns.

**Note**

Instead of the data type time for the Delivery Time you can also use the data types date , dateTime , or real . When you use date or dateTime , the start time of the simulation has to be before the time you type in.

Each row of the Delivery Table defines a single order for producing MUs :

- Type the time at which the Source produces the MUs into the column Delivery Time .
- Type the class of the MU into the column MU . You can also use drag-and-drop of the MU class to accomplish this.
- Type the number of MUs to be produced into the column Number .

**Note**

When you type 0 as Number into a row, Plant Simulation does take the specified interval for the next creating cycle into account. This means that Plant Simulation does not skip this row, but does not produce a part during this cycle.

- Type a name for the MUs to be produced into the column Name .
- In addition, you can, but you do not have to type the name of a subtable into the column Attributes . Type the attributes whose value the Source sets and the user-defined attributes that it creates, when it produces the MUs , into that subtable.

<!-- image -->

<!-- image -->

To open the subtable, do one of the following:

- Double-click the cell containing the subtable, properties in the column Attributes in the example above.
- Click into the cell and press F2 .
- Right-click into the cell and select Open Object .

Type the name of a built-in attribute into the cells below column 1 of the attribute table. Type the value you want to assign to this attribute into one of the cells to the right with the respective data type. Or

Type the name of a user-defined attribute into the cells below column 1 of the table. If an attribute with that name does not exist yet, Plant Simulation creates it. Type the value you want to assign to this attribute into the cell to the right, which has the corresponding data type.

<!-- image -->

**Note**

Plant Simulation assigns the data type of the column containing the value of the attribute to the data type of the attribute itself. Plant Simulation assigns the value you type into the cell to the generated attribute.

**Back to Produce Parts with the Source**

Producing Parts During an Interval Which You Define

Produce Parts During an Interval Which You Define

To produce MUs during the interval you define:

- Select Time of Creation &gt; Interval Adjustable .
- In our example, we chose to have the Source create one Constant type of MU , namely a Part , every minute and 20 seconds.
- Click OK .

The Source :

<!-- image -->

- Produces the first MU at the time you enter for Start .
- Produces the next MU after the time you enter for Interval has elapsed.
- Stops producing MUs at the point in time you enter for Stop . Enter 0 into the text box Stop if you do not want to apply a time limit.

When you select Time of Creation &gt; Interval Adjustable or Time of Creation &gt; Number Adjustable you can also select how the Source produces which types of MUs .

You can:

- Produce a Single Part Type Only
- Produce Parts in a Fixed Sequence Over and Over Again
- Produce Parts in a Fixed Sequence One Time Only
- Produce Parts With a Random Frequency Entered into a Data Table
- Produce Parts With a Percentage Entered into a Data Table

Compare Specify Times in Object Dialogs

Back to Produce Parts with the Source

Produce a Single Part Type Only

To make the Source produce one type of MU only:

- Select MU Selection &gt; Constant .
- Click . In the dialog Select Object navigate to the folder where the MUs are located. Select the name of a MU class and click OK .

<!-- image -->

**Back to Produce Parts During an Interval Which You Define**

Produce Parts in a Fixed Sequence Over and Over Again

To make the Source produce MUs in a fixed sequence over and over again:

- Select MU Selection &gt; Sequence Cyclical .
- Insert a table into a Frame or into a folder in the Class Library .
- To designate the MU class to be produced, do one of the following:
- Click . In the dialog Select Object navigate to the folder where the data table is located into which you want to enter the MUs . Select the name of the Table and click OK .
- Drag the table over the text box Table and drop it there.
- Enter the name of and the path to the table into the text box next to Table .

<!-- image -->

<!-- image -->

- Enter the names of the MU classes to be produced into the cells below MU of the table.
- You can, but you do not have to enter a Name and Attributes into columns 3 and 4 of the table.
- Enter the number of MUs to be produced into the cells below Number .

**Note**

When you do not enter a Name , the MUs that the Source produces use the name of their class.

- To make the Source produce the number of MUs you specified in a row of the sequence table all at once in a single batch before moving the entire batch on, select Generate as Batch . Once the Source has processed the entire sequence, it starts processing the information in the table again starting at the beginning of the sequence.

To make the Source produce the MUs is a sequence of individual MUs , clear the check box. When the Source produces the MUs is a batch, it attempts to produce the entire set of Parts at the given start time and to move them on to the next object.

##### Back to Produce Parts During an Interval Which You Define

Produce Parts in a Fixed Sequence One Time Only

To make the Source produce MUs in a fixed sequence one time only:

- Select MU Selection &gt; Sequence Cyclical .

<!-- image -->

**Note**

The setting Sequence is not available, when you set Time of Generation to Number Adjustable .

- Insert a table into a Frame or into a folder in the Class Library .
- To designate the type of MU to be produced, do one of the following:
- Click . In the dialog Select Object navigate to the folder where the data table is located into which you enter the MUs . Select the name of the Table and click OK .
- Drag the table over the text box Table and drop it there.

- Enter the name of and the path to the table into the text box next to Table .
- Enter the names of the MU classes to be produced into the cells below MU into the table.
- Enter the number of MUs to be produced into the cells below Number .
- You can, but you do not have to enter a Name and Attributes into columns 3 and 4 of the table.

<!-- image -->

**Note**

When you do not enter a Name , the MUs that the Source produces use the name of their class.

- To make the Source produce the number of MUs you specified in a row of the sequence table all at once in a single batch before moving the entire batch on, select Generate as batch .

To make the Source produce the MUs as a sequence of individual MUs , clear the check box. When the Source produces the MUs as a batch, it attempts to produce the entire set of parts at the given start time and to move them on to the next object all at once in the batch.

**Back to Produce Parts During an Interval Which You Define**

Produce Parts With a Random Frequency Entered into a Data Table

To make the Source produce MUs with a frequency, which you type into a table:

- Select MU Selection &gt; Random .

<!-- image -->

- Insert a table into a Frame or into a folder in the Class Library .
- To designate the type of MU to be produced, do one of the following:
- Click . In the dialog Select Object navigate to the folder where the data table is located into which you enter the MUs . Select the name of the Table and click OK .
- Drag the table over the text box Table and drop it there.
- Enter the name of and the path to the table into the text box next to Table .
- Enter the names of the MU classes to be produced into the cells below MU into the table.
- Enter the frequency number for each class of MU to be produced into the cells below Frequency . When the Source produces the MUs , Plant Simulation selects and processes a random generation order according to the frequency you entered here.

<!-- image -->

- Enter the number of MUs to be produced into the column Number .
- You can, but you do not have to enter a Name or an Attributes table.

**Note**

If you do not enter a Name , the MUs that the Source produces use the name of their class.

To check which part types were produced at which point in time, you can activate the check box Creation table on the tab Statistics and then open the table.

**Back to Produce Parts During an Interval Which You Define**

###### Produce Parts With a Percentage Entered into a Data Table

To make the Source produce MUs with a frequency, which you type into a table:

- Select MU Selection &gt; Percentage .
- Insert a table into a Frame or into a folder in the Class Library .
- To designate the type of MU to be produced, do one of the following:

<!-- image -->

- Click . In the dialog Select Object navigate to the folder where the data table is located into which you enter the MUs . Select the name of the Table and click OK .
- Drag the table over the text box Table and drop it there.
- Enter the name of and the path to the table into the text box next to Table .
- Enter the names of the MU classes to be produced into the cells below MU into the table.
- Enter the percentage portion for each class of MU to be produced into the cells below Portion .
- Enter the number of parts to be produced into the cells below Number .
- You can, but you do not have to enter a Name or an Attributes table.

<!-- image -->

**Note**

If you do not enter a Name , the MUs that the Source produces use the name of their class.

Compare Specify Times in Object Dialogs

Back to Produce Parts with the Source

Video on YouTube

[https://youtu.be/BvHLQCIjGIA?si=b7Ua-Nl7\_uxT39m4&amp;t=158](https://youtu.be/BvHLQCIjGIA?si=b7Ua-Nl7_uxT39m4&t=158)

Produce the Number of Parts You Need

To produce a certain number of MUs during the interval you define:

- Select Time of Creation &gt; Number Adjustable .

<!-- image -->

- Enter the Amount , i.e., the number of MUs to be created.
- Select the Creation Times , which determine the points in time at which the Source creates the MUs .

Select a distribution from the drop-down list Creation Times and enter the values that the distribution requires into the text box.

The Source produces the number of MUs at the different times which the random number generator generated at the beginning of the simulation. The determined times are contained within the bounds if you enter a lower bound and an upper bound.

If you select a Constant time, the Source creates the number of MUs all at one point in time.

<!-- image -->

- Click OK .

If you select Time of Creation &gt; Interval Adjustable or Time of Creation &gt; Number Adjustable you can also select how the Source produces which types of MUs .

Compare Specify Times in Object Dialogs

Back to Produce Parts with the Source

##### Produce Parts Using a Trigger Object

You might, for example, use a Source that is controlled by a Trigger :

- To set a time of creation, such as with a delivery table, and
- To periodically repeat using the values in this table, for example when you select Sequence Cyclical from the drop-down list MU selection .

**Proceed as follows:**

- Select Time of Creation &gt; Trigger in the dialog of the Source .

<!-- image -->

Before you can enter the Trigger , click the check box Inheritance , so that it looks like this .

- Click Trigger , drag the Trigger that controls the Source from the Frame over the list that opens and drop it there.
- In the dialog of the Trigger enter the Active Interval , i.e., the interval during which the Trigger will be active.

Enter the Period Length , i.e., the duration of the Trigger's cycle.

<!-- image -->

- Click the tab Values and select the Trigger Type &gt; Input .
- Click the button Values and enter into the TimeSequence object that opens:

<!-- image -->

The Point in Time at which the Source creates MUs into the cells on the left-hand side.

The current sequence of Values into the cells on the right-hand side. An order is a string with this format: amount,mu\_Type,distributionType[,distribution parameters] .

<!-- image -->

You have to enter the amount of MUs to be produced, the type to be produced, and at least a constant value. If you enter just Const , the Source produces the MUs at the point in time, which you typed into the cell to the left. If you would like it to produce the MUs with an offset to the time you entered there, enter the number of seconds after which it produces them after Const .

If you enter a distribution, its values set the time offset to the time you entered into the corresponding left cell. The offset you enter has to be a positive number!

<!-- image -->

- Click the tab Actions and click Objects . The Trigger shows the Source in the table.

<!-- image -->

<!-- image -->

Compare Check How Many Parts Were Introduced into the Plant

Back to Produce Parts with the Source

#### Producing and Processing Parts with a Work Plan

Produce and Process Parts with a Work Plan

A work plan or operations plan determines how a product is produced. It lists the various production steps in the sequence in which they are executed.

**Note**

We neither specify the cost center, to which each of the individual production steps is charged in Plant Simulation , nor the allowed time for each step. This you can do in Process Designer .

For simplicity's sake each operation can only be executed by a single station in our example. Our work plan thus is described by a sequence of stations. The Source named Receiving holds position 0 in the work plan, the station Milling position 1 , the stations Drilling\_A or Drilling\_B position 2 and the station Packing position 3 .

<!-- image -->

To facilitate quick and easy modeling:

- We create the work plan in a DataTable and insert it into the Frame , in which we create our simulation model. We enter the set-up times of the stations and the processing times of the different parts into sub-tables of the work plan.
- We produce two different types of parts with a Source using a sequence table. The parts need two user-defined attributes . One sets the name of the part. The other sets the position of the part in the work plan.
- We program a Method , i.e., an Exit Control , which enables the processing station to find the next station in the sequence of operations after each processing step and moves the part on to this station. We insert this Method , which all stations access, into the Frame .

##### Creating the Processing Stations

**Back to Model the Flow of Materials, Basics**

Creating the Processing Stations

Create the Processing Stations

To be able to assign the operations and the stations in the work plan later on, we start out with creating the stations which execute the operations.

- To create the class of the processing station, right-click the object Station in the folder MaterialFlow and select Derive on the context menu.
- To move the derived Station to the folder in which we are going to create the model, hold down Shift and drag it so that folder. Rename it to MyStation . By default Plant Simulation places derived objects into the folder UserObjects .
- Insert it from there into the model three times. Rename the stations so that they match the names of the operations. In our example we named them Milling , Drilling\_A , Drilling\_B and Packing .

<!-- image -->

As the processing stations share a number of features, we set these in their class, MyStation in our example. The class object passes these properties on to its instances.

We will:

- Define Times in the Class of the Processing Stations
- Define Set-up Behavior in the Class of the Processing Stations
- Specify the Name of the Exit Control in the Class of the Processing Stations

Back to Produce and Process Parts with a Work Plan

Define Times in the Class of the Processing Stations

We define the Processing time and the Set-up time in a Formula in the class of our processing stations.

- We want the stations to get the processing time of all parts from the work plan MyWorkPlan . This DataTable is located in the Frame in which we build the model, i.e., the root Frame . The station then opens the subtable Operations for the respective part and gets the times in the column Processing time of the respective station within this subtable.

<!-- image -->

For the processing time we use a Method which we call from the formula. The Method is called ProcessingTimeInFormula .

The source code looks like this:

```simtalk
-> time
var PartType := @.EntityType
var Station  := ?
var WorkPlan := root.myWorkPlan["Operations", PartType]
result       := WorkPlan["Processing time",Station]
```

<!-- image -->

- We want the stations to get the set-up time of all parts from the work plan MyWorkPlan . This DataTable is located in the Frame in which we build the model, i.e., the root Frame . The station then opens the subtable Operations for the respective part and gets the times in the column Set-up time of the respective station within this subtable. Self identifies the station contained in the row on the subtable.

The description above translates to this formula, which we directly type into the text box:

<!-- image -->

<!-- image -->

###### Back to Create the Processing Stations

Define Set-up Behavior in the Class of the Processing Stations

To automatically set the stations up depending on the name of a user-defined attribute of the MU :

- Select the check box Automatic .

- Select User-defined Attribute from the drop-down list Set-up depends on . Enter the name of the user-defined attribute which we defined in the Sequence table with which the Source produces parts, compare Produce the Parts with a Source Using a Sequence Table . We typed in EntityType .

<!-- image -->

**Back to Create the Processing Stations**

Specify the Name of the Exit Control in the Class of the Processing Stations

As the station has to find the next station in the sequence of operations after each processing step and move the part on to this station, we enter the name of an exit control .

Program the Exit Control shows how to accomplish this.

<!-- image -->

**Back to Create the Processing Stations**

##### Create the Work Plan

**To create the work plan:**

- Insert a DataTable into the Frame . Activate the column index and the row index.
- Assign the data type Table to the column which contains the subtable into which we enter information about the operations.
- Format this column so that all subtables have the same format, compare Create Lists within Lists and Tables . To do so, click the right mouse button on the column header Operations and select Format .

<!-- image -->

Scroll all the way to the right to the tab Contents in the dialog List Format . Activate the column index and the row index of the subtables in the Format menu.

<!-- image -->

Assign the data type Object to the column of the column index. Assign the data type Time to the next two columns.

- After we assigned the correct format to the subtables, we can then enter the contents:
- Once we enter an identifier, Plant Simulation creates the subtable in this cell. We typed in Operations for MyPart A and Operations for MyPart B .
- To open the subtable for the respective work plan, double-click the respective cell below Operations .
- Enter the names of the operations/stations, their set-up times and the processing times of the parts.

<!-- image -->

<!-- image -->

**Back to Produce and Process Parts with a Work Plan**

Produce the Parts with a Source Using a Sequence Table

To produce the parts in the sequence, which we specify in a sequence table:

- Insert a Source into the Frame . Select MU Selection &gt; Sequence Cyclical .

<!-- image -->

- Insert a DataTable into the Frame . Drag this table over the text box Table . Plant Simulation automatically assigns the columns on the table the correct data types and the correct column headers.
- Open the table and enter the type of part you want to produce, how many of them, their name and the name of the subtable containing the attributes of the part.

<!-- image -->

In our example the Source is to produce 1 part of the MU class Part each with the name MyPartA and MyPartB .

<!-- image -->

- To create a subtable for the user-defined attributes of the parts, enter an identifier into the cells below Attributes . To open this subtable, double-click the cell. Here we enter the names and the values of two user-defined attributes : One sets the name of the part, the PartType is either MyPartA or MyPartB . The other sets the position of the part in the work plan ( PositionInWorkPlan ). In our case the sequence of operations always starts at position 0 , which is the Source . The counter, which we programmed in the Exit Control , then steps through the stations: Milling is position 1 , Drilling\_A or Drilling\_B are position 2 and Packing is position 3 .

<!-- image -->

During the simulation run Plant Simulation enters these user-defined attributes into the created Parts . The Part with the number 48229 , for example, is of type MyPart A and is located on station 2 , DrillingA , according to the position, which we defined in the work plan as operation.

<!-- image -->

<!-- image -->

- Finally, enter the name of the Exit Control , which finds the processing station and moves the part onto it.

<!-- image -->

**Back to Produce and Process Parts with a Work Plan**

##### Program the Exit Control

As we want all stations and the Source to be able to access the source code for finding the next station in the sequence of operations after each processing step and for moving the part on to this station, we program an Exit Control . If just the stations were going to use this control, we could have programmed it in a user-defined attribute of data type method of the class of the station.

The source code of the Exit Control looks like this:

```simtalk
// This is the exit control for all stations and for the source. // This control can be called several times until the move command is successful.
var WorkPlan := root.MyWorkPlan["Operations",@.EntityType]
if @.PositionInWorkPlan = WorkPlan.ydim
	@.Move(root.Shipping) // end of production
else
var NextStation := WorkPlan["Operation", @.PositionInWorkPlan + 1]
if @.Move(NextStation)
	@.PositionInWorkPlan := @.PositionInWorkPlan + 1
end
end
```

<!-- image -->

Back to Produce and Process Parts with a Work Plan

#### Remove Parts from the Installation with the Drain

To remove the parts and workpieces from the plant after they have been processed, for example to model the shipping department , we use the object Drain .

<!-- image -->

The Drain has a single processing place. It removes the MU from the installation after setting-up for it and after processing it. The built-in properties of the Drain are the same as those of the Station . The Drain removes the MU from the installation after it processed it, instead of moving it on to a succeeding object in the flow of materials, and it collects statistics about the MU .

You can insert the Drain into your simulation model from the folder MaterialFlow in the Class Library or from the toolbar Material Flow in the Toolbox .

<!-- image -->

Remember that we create these parts with the object Source .

Compare Specify Times in Object Dialogs

Compare Check How Many Parts Left the Plant

Compare Produce Parts with the Source

Back to Model the Flow of Materials, Basics

#### Transferring Parts from Station to Station

Transfer Parts from Station to Station

When transferring parts from station to station in your simulation model, you can either:

- Use the Standard Transfer Behavior , which employs the push-block principle .
- Select an Exit Strategy , which distributes the parts to the succeeding stations according to the criteria you set.
- Distribute Parts Among its Successors with the FlowControl .
- Move the part, when an attribute of the processing station changes by using an observer .
- Select an Exit Strategy in the Interface when parts are moving across Frames .
- Load, Unload, and Reload Parts with the TransferStation .

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

Compare How Plant Simulation Moves Parts On

Back to Model the Flow of Materials, Basics

How Plant Simulation Moves Parts On

Plant Simulation moves MUs on as follows:

**· Moving from point-oriented to point-oriented object**

When moving from a point-oriented object to another point-oriented object, the MU moves on completely and instantaneously from booking point to booking point.

<!-- image -->

**· Moving from point-oriented object to length-oriented object**

When moving from a point-oriented object, such as a Source or a Station , to a Conveyor , the front of the MU moves to the start of the Conveyor . When Station and Conveyor are not placed directly side by side, the MU seems to hang in thin air, compare Position of the MU .

<!-- image -->

If the objects are placed directly side by side you will not notice that as the MU still seems to be located on the predecessor.

<!-- image -->

**· Moving from length-oriented object to length-oriented object**

When moving from Conveyor to Conveyor, the MU moves continually on, i.e., only its front moves on to the successor, while the remainder follows with the Speed you specified. When the transport speeds differ, Plant Simulation uses the speed of the Conveyor , on which the Booking point length of the MU is located. In the example below our MU is located on three Conveyors as it is very long.

<!-- image -->

**· Moving from length-oriented object to point-oriented object**

When moving onto a point-oriented object, such as a Station , the MU always moves completely and instantaneously, i.e., it is then located on that object as a whole, not only its front section.

<!-- image -->

Back to Model the Flow of Materials, Basics

Use the Standard Transfer Behavior

By default Plant Simulation uses the push-block principle then transferring mobile parts from station to station, either along the connections you established with the Connector or by programming a Method .

An object that has processed the part, which is ready to be transferred, actively attempts to move that part on to its successor ( push ). If the successor cannot receive the part at the moment, the block principle will be activated, guaranteeing that the object ready to move the part is re-activated as soon the successor is ready to receive the part.

The push-block principle ensures that parts are transferred using the built-in functionality of the objects and that the stream of events is not interrupted by failures or pauses.

The standard transfer strategy is cyclic, non-blocking, meaning that the current object moves the MU to the first non-blocked succeeding object in the flow of materials. Once the object reaches the end of the list of successors, it continues the search at the beginning of the list and terminates the search when it reaches the successor from the previous search.

<!-- image -->

Suppose Milling is the first station in the sequence of stations in your simulation model, Drilling\_A is the second station, Part:1 is the first mobile object that entered the flow of materials, Part:2 is the second mobile object.

Suppose Part:1 is located on Drilling\_A , and Part:2 is located on Milling and wants to move to Drilling\_A .

<!-- image -->

Once Part:2 is completely processed by Milling , Part:2 notifies Drilling\_A that it intends to move to it.

- When Drilling\_A can receive Part:2 , it notifies Part:2 , and Part:2 moves from Milling to Drilling\_A .
- When Drilling\_A cannot receive Part:2 because it is busy, its entrance is locked, etc., Part:2 enters itself into the forward blocking list of Drilling\_A and of all other stations it intends to move to.
- When Part:1 exits Drilling\_A , Drilling\_A schedules an Out event for all entries, i.e., MUs , in the Forward Blocking List , including Part:2 . Afterwards Drilling\_A deletes all entries from its Forward Blocking List .
- Provided Drilling\_A can receive Part:2 , Part:2 deletes all references to itself from all blocking lists of all stations it entered itself into, and then moves to Drilling\_A .

<!-- image -->

The material flow objects Station , ParallelStation , AssemblyStation , DismantleStation , Conveyor , Sorter , PlaceBuffer and Buffer handle the MUs that transfer onto them:

**Procedure**

1. For these times, which you define:
- The Processing Time is the time, which the MU remains on the object to be processed. It is the interval between setting-up for the present type of MU and the point in time when the material flow object moves it on to its successor.
- The Set-up Time is the time it takes to set-up the object for processing a different type of MU . An identical name designates that MUs are of the same type and that the object does not have to set up for this MU .
- The Recovery Time is the time which is required to set a station into a defined state before it can start processing the next part. The recovery time is, for example, useful to model materials handling equipment, such as a robot, which requires a certain time to insert work pieces into or remove them from processing stations. You can also use it to model times during which a hot part cools off.
- The Cycle Time is the time that passes between the points in time where parts can enter the object. The cycle time is, for example, useful to model chain conveyors with a fixed chain interval that only transport materials when a free hook is available.

<!-- image -->

**Note**

You do not have to define all of the times listed above for the object.

2. For failures which you define and activate.

The material flow objects then transfer the MUs to the next object along the material flow connections using the exit strategy you select.

Compare Define Processing Times Compare Model Failures Compare Select the Set-Up Time Back to Transfer Parts from Station to Station Selecting an Exit Strategy Select an Exit Strategy If you do not want to transfer the MUs using the standard transfer behavior, click the Tab Exit and select another Strategy . As a rule you will use an exit strategy , which distributes the flow of materials, when the sequence of operations does not uniquely designate the next object that processes the MU . Your objective will be to make a choice that is close to optimal in some respect, say cost or time, but not in others.

<!-- image -->

**Note**

For length-oriented objects Plant Simulation only considers the exit strategy when the part is moving forward.

**Note**

Click Apply , to apply your new settings, and to display additional dialog items, which the selected exit strategy requires.

- To move the part cyclically to the next successor in line, select Cyclic .
- To cyclically move the part to the successor according to the sequence of successors, which you typed into the list, select Cyclic Sequence .

You can also set the number of the succeeding object with the attribute ExitStrategySequence .

- To move the part to the successor that has been Waiting the longest for a MU , select Least Recent Demand .
- To move the part to the successor in a linear fashion, according to the sequence of successors, which you typed into the list, select Linear Sequence .

You can also set the number of the succeeding object with the attribute ExitStrategySequence .

- To move the part to the successor that contains the greatest number of MUs , select Maximum Contents .
- To move the part to the successor that received the most MUs , select Maximum Number In .
- To move the part to the successor with the longest processing time, select Maximum Processing Time .
- To move the part to the successor with the highest relative occupancy, select Maximum Relative Occupation
- To move the part to the successor with the longest set-up time, select Maximum Set-up Time .
- To move the part to the successor that contains the smallest number of MUs , select Minimum Contents .
- To move the part to the successor that received the smallest number of MUs , select Minimum Number In .
- To move the part to the successor with the shortest processing time, select Minimum Processing Time .
- To move the part to the successor with the lowest relative occupancy, select Minimum Relative Occupation
- To move the part to the successor with the shortest set-up time, select Minimum Set-up Time .
- To move the part to the successor that has been Waiting the least amount of time for a MU , select Most Recent Demand .
- To move the part to the successor according to an attribute of the MU , select MU Attribute . You can also set the names of the user-defined or the built-in attributes, their values, and the numbers of the successors with the attribute ExitStrategyMUAttributeList .

- To move the part to the successors according to a percentage distribution, select Percentage You can also set the with the attribute ExitStrategyPercentageValues .
- To move the part to the successors in a random fashion, select Random . You can also set the with the attribute ExitStrategyPercentageValues .
- To always move the part to successor with the number 1, select Start at Successor 1 .

**Back to Transfer Parts from Station to Station**

###### Cyclic [exit strategy, example]

To move the part cyclically to the next successor in line, select Cyclic from the drop-down list.

<!-- image -->

- If you select Blocking , the object moves the MU to the object, which in sequence of successors immediately follows on the object on to which a MU has last transferred.
- If you clear Blocking , the object moves the MU to the next object in the sequence of successors, which can receive a part.

Once the object reaches the end of the sequence of successors, it continues the search at the beginning of the sequence and terminates the search when it reaches the successor from the previous search.

**Back to Select an Exit Strategy**

###### Cyclic sequence [example]

To cyclically move the part to the material flow object's successor according to the sequence of successors, which you typed into the list repeatedly, select Cyclic Sequence from the drop-down list.

- .

**Note**

Click Apply , to apply your settings, and to display the button Open List .

Click Open List and type in the number of the succeeding object into the respective cell of the list. When you type in 2 into the cell in row 1, the object first moves the MU to the successor with the number 2.

<!-- image -->

<!-- image -->

The successor to which the object moves the MU is the next one in line that can receive it in the sequence, which you typed into the list. When the object arrives at the last entry in the list (last object in the sequence), it returns to the first entry and processes the list again.

The same successor object may be contained several times, one after the other, in the list. Then the object attempts to move the part to this same successor as often as it is contained in the list.

- If you select Blocking , the object only moves the MU , when the designated successor is ready to receive it.
- If you clear Blocking , the object attempts to move the part to the respective successor, beginning with the active entry of the list.

When the object arrives at the last entry in the list, i.e., the last object in the sequence, it returns to the first entry and processes the list again.

**Back to Select an Exit Strategy**

###### Least Recent Demand [example]

To move the part to the successor that has been Waiting the longest for a MU , select Least Recent Demand from the drop-down list. This means that the successor receives the next MU onto which no part moved for the longest time.

- If you select Blocking , the object moves the MU to the next successor.
- If you clear Blocking , the object moves the MU to the next successor, which can receive the MU .

**Back to Select an Exit Strategy**

###### Linear Sequence [example]

To move the part to the material flow object's successor in a linear fashion, one time only, according to the sequence of successors, which you typed into the list, select Linear Sequence from the drop-down list.

<!-- image -->

**Note**

Click Apply , to apply your settings, and to display the button Open List .

Click Open List and type in the number of the succeeding object into the corresponding cell of the list. When you type in 3 into the cell in row 1, the object first moves the MU to the successor with the number 3.

<!-- image -->

The successor to which the object moves the MU is the first one in line that can receive it in the sequence, which you typed into the list.

- If you select Blocking , the object only moves the MU to the first successor in the list of successors.
- If you clear Blocking , the object moves the MU to the first available successor in the list of successors.

**Back to Select an Exit Strategy**

###### Maximum Contents

To move the part to the successor that contains the highest number of MUs , select Max. Contents from the drop-down list.

<!-- image -->

- If you select Blocking , the object moves the MU to the next successor.
- If you clear Blocking , the object moves the MU to the next successor, which can receive the MU .

**Back to Select an Exit Strategy**

###### Maximum Number In

To move the part to the successor that received the most MUs , select Max. Num. In from the drop-down list.

<!-- image -->

- If you select Blocking , the object moves the MU to the next successor.
- If you clear Blocking , the object moves the MU to the next successor, which can receive the MU .

**Back to Select an Exit Strategy**

###### Maximum Processing Time

To move the part to the successor with the longest processing time, select Max. Proc. Time from the drop-down list.

<!-- image -->

- If you select Blocking , the object moves the MU to the next successor.
- If you clear Blocking , the object moves the MU to the next successor, which can receive the MU .

**Back to Select an Exit Strategy**

###### Maximum Relative Occupation

To move the part to the successor with the highest relative occupancy, select Max. Rel. Occu. from the drop-down list.

<!-- image -->

- If you select Blocking , the object moves the MU to the next successor.
- If you clear Blocking , the object moves the MU to the next successor, which can receive the MU .

**Back to Select an Exit Strategy**

###### Maximum Set-up Time

To move the parts to the successor with the longest set-up time, select Max. Set-up Time from the drop-down list.

<!-- image -->

- If you select Blocking , the object moves the MU to the next successor.
- If you clear Blocking , the object moves the MU to the next successor, which can receive the MU .

**Back to Select an Exit Strategy**

###### Minimum Contents

To move the part to the successor that contains the least number of MUs , select Min. Contents from the drop-down list.

<!-- image -->

- If you select Blocking , the object moves the MU to the next successor.
- If you clear Blocking , the object moves the MU to the next successor, which can receive the MU .

**Back to Select an Exit Strategy**

###### Minimum Number In

To move the part to the successor that received the least number of MUs , select Min. Num. In from the drop-down list.

<!-- image -->

- If you select Blocking , the object moves the MU to the next successor.
- If you clear Blocking , the object moves the MU to the next successor, which can receive the MU .

**Back to Select an Exit Strategy**

###### Minimum Processing Time

To move the part to the successor with the shortest processing time, select Min. Proc. Time from the drop-down list.

<!-- image -->

<!-- image -->

- If you select Blocking , the object moves the MU to the next successor.
- If you clear Blocking , the object moves the MU to the next successor, which can receive the MU .

**Back to Select an Exit Strategy**

###### Minimum Relative Occupation

To move the part to the successor with the lowest relative occupancy, select Min. Rel. Occu. from the list.

<!-- image -->

- If you select Blocking , the object moves the MU to the next successor.
- If you clear Blocking , the object moves the MU to the next successor, which can receive the MU .

**Back to Select an Exit Strategy**

###### Minimum Set-up Time

To move the parts to the successor with the shortest set-up time, select Min. Set-up Time from the drop-down list.

<!-- image -->

###### Most Recent Demand [example]

- If you select Blocking , the object moves the MU to the next successor.
- If you clear Blocking , the object moves the MU to the next successor, which can receive the MU .

**Back to Select an Exit Strategy**

**Most Recent Demand [example]**

To move the part to the successor Waiting the least amount of time for a MU , select Most Recent Demand from the drop-down list. This means that the successor, onto which a MUs was moved last, receives the next MU .

- If you select Blocking , the object moves the MU to the next successor.
- If you clear Blocking , the object moves the MU to the next successor, which can receive the MU .

**Back to Select an Exit Strategy**

###### MU Attribute [example]

To move the MUs on to a successor according to the value of an attribute of the MU , select MU Attribute from the drop-down list.

**Note**

Click Apply to display the dialog items of this strategy.

- If you select Blocking , the material flow object always moves the part to the designated successor. If that successor is not ready to receive it, the part will be blocked.
- If you clear Blocking , the material flow object moves the part on when any of its successors can receive it. In this case enter the desired numbers of the successors into the attribute list for each attribute value .

<!-- image -->

Click Open List to open a table, into which you can enter the names of the user-defined or the built-in attributes, their values, and the numbers of the successors. The object searches the table from top to bottom until it finds an attribute with the value you entered. It then moves the MU on to that successor.

<!-- image -->

**Note**

Create the user-defined attributes for the MUs on the Tab User-defined .

**· Default Successor**

Enter the number of the Default Successor . This is the successor to which the object moves the MU , when this MU does not have an attribute with the Value you entered into the DataTable .

To show a message, when a part is to be moved which does not meet any of the conditions in the DataTable , enter 0 .

**· Attribute Type**

Select the data type of the attribute from this drop-down list, compare Data Types .

Back to Select an Exit Strategy

**Video on YouTube**

**Video on YouTube**

**[https://youtu.be/PQhEriOzVzU?si=rB6pUl7icKnIr0Yj&amp;t=472](https://youtu.be/PQhEriOzVzU?si=rB6pUl7icKnIr0Yj&t=472)**

Percentage [exit strategy, example]

To move the part to the successors according to a percentage distribution, select Percentage from the drop-down list.

<!-- image -->

Click Open List and type the percentages in the list that opens. The n-th row on the table defines the n-th successor's portion: When you type 20 in row 1, for example, the object moves 20 percent of the MUs it received to the successor with the number 1, etc.

The object always moves the MU to the successor with the greatest difference between the rated value and the current value.

<!-- image -->

- If you select Blocking , the object moves the MU to the successor with the highest deviation from the nominal percentage.
- If you clear Blocking , the object moves the MU to the successor, which can receive the MU with the highest deviation from the nominal percentage.

**Note**

The actual percentages reached may differ from the nominal ones due to a low number of total transfers and to the Blocking -state of successors.

Any previous transfers of MUs affect the Percentage strategy, as they alter the deviation from the nominal transfer frequencies.

Plant Simulation sums up the values you typed into the list of nominal percentages to obtain the value that matches 100 percent. The distribution pattern only depends on the relative size of the values, not on their magnitude. This way you can, for example, either type in [1;2] or [0.3333…; 0.6666…] , the result will be the same.

If the distribution pattern is periodic, then it is so right from the beginning. This means that the distribution pattern at the start of a simulation run does not differ from the distribution pattern at a later point in time. These examples demonstrate, how nicely the values are balanced:

- If you assign the values 1 and 2 to the exits 1 and 2 respectively, Plant Simulation generates this sequence of exits:

2 1 2 2 1 2 2 1 2 2 1 2 2 1 2

- If you assign 2 and 3 to the exits 1 and 2, Plant Simulation generates this sequence of exits: 2 1 2 1 2 2 1 2 1 2 2 1 2 1 2
- If you assign the values 1 , 2 , 4 and 8 to the exits 1, 2, 3, and 4, Plant Simulation generates this sequence of exits:

4 3 4 2 4 3 4 1 4 3 4 2 4 3 4 4 3 4 2 4 3 4 1 4 3 4 2 4 3 4

**Back to Select an Exit Strategy**

Random [exit strategy, example]

To move the part to the successors in a random fashion, select Random from the drop-down list.

Click Open List and type the percentages in the list that opens. The n-th row on the table defines the n-th successor's portion: When you type 20 into row 1, for example, the object moves 20 percent of the MUs it received to the successor with the number 1, etc.

<!-- image -->

- If you select Blocking , the object determines the successor using the built-in randomnumber generator.
- If you clear Blocking , the object determines the successor using the built-in random-number generator until it either computes a successor, which can receive the MU or the object has iterated through all successors.

A previous call to the random number generator does affect the Random strategy. The order in which the successors are iterated through is not predictable.

**Back to Select an Exit Strategy**

Start at Successor 1 [example]

To always move the part to the material flow object's successor with the number 1, select Start At Successor 1 from the drop-down list.

<!-- image -->

- If you select Blocking , the object moves the MU to the first successor in the list of successors.
- If you clear Blocking , the object moves the MU to the first successor in the sequence of successors, which can receive the MU .

A previous search for a successor does not affect the strategy Start at successor 1 .

**Back to Select an Exit Strategy**

Distributing Parts with the FlowControl

Distribute Parts Among its Successors with the FlowControl

To model common strategies for splitting-up and for bringing together the flow of materials in your plant, you can use the FlowControl . The FlowControl does not store and does not process the MU , it only distributes them among the objects that succeed it in the sequence of stations in the simulation model. The number of predecessors and successors of the FlowControl usually is not limited.

You can insert the FlowControl into your simulation model from the folder Material Flow in the Class Library or from the toolbar Material Flow in the Toolbox .

<!-- image -->

In our example below we show how the FlowControl moves the parts on to its successors according to an attribute of the part. If a part has more than one attribute, it suffices if one of the attributes meets the criteria, which you defined in the attribute list. If a part has several attributes though, and none of these attributes meet the criteria in the list, you can determine what happens to the part by typing in different values for the default successor of the FlowControl :

- When you type in the number of a successor, the FlowControl moves the part so that successor. When you accept the default setting 1 , it moves the part on to the successor object with the number 1.
- When you type in 0 , the FlowControl does not move the part on. It remains in front of the FlowControl , thus blocking the following parts.
- When you type in -1 , Plant Simulation shows an error message.

The finished simulation model looks like this:

<!-- image -->

To create the sample model, you will:

- Configure the Source that Produces the Parts [FlowControl]
- Configure the FlowControl Which Distributes the Parts

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

**Back to Transfer Parts from Station to Station**

Configure the Source that Produces the Parts [FlowControl]

Insert and configure the Source which produces the parts:

- Select when and how many parts of a certain type are to be produced. We selected a Delivery Table in our example, as shown in the screenshot below.

<!-- image -->

- We then selected the name of the delivery table , which we inserted before, namely MyDeliveryTable . Selecting it automatically applied the correct format.
- Next, we entered the required information, compare the screenshot below. The Source which we named PartsIn in our sample model, produces six different parts with the names we entered into the column Name .

<!-- image -->

To enter the attributes according to which the FlowControl distributes the parts among its successors, type in any name of your choice into the column Attributes to create a subtable with this name, and then double-click the name.

- For the part with the Name Red , we typed in MyAttr , double-clicked the cell, and entered Color is the Name of the Attribute and Red as the color of the part.
- For the part with the Name BlackSquare , we typed in MyAttr , double-clicked the cell, and entered Color is the Name of the Attribute and Black as the color of the part. We also entered a second attribute, namely Shape , and typed in Square as its shape.
- For the part with the Name BlackOctagonal , we typed in MyAttr , double-clicked the cell, and entered Color is the Name of the Attribute and Black as the color of the part. We also entered a second attribute, namely Shape , and typed in Octagonal as its shape.

<!-- image -->

<!-- image -->

<!-- image -->

When the Source produces the parts, it creates the attributes, which we entered above, as user-defined attributes of data type string for the respective part.

<!-- image -->

Then, insert the other objects, so that they match the screenshot below.

Back to Distribute Parts Among its Successors with the FlowControl

<!-- image -->

###### Configure the FlowControl Which Distributes the Parts

Insert and configure the FlowControl which distributes the parts among its successors in the flow of materials:

- As we want the FlowControl to distribute the parts according to the user-defined attributes , which we defined above, select the setting MU Attribute from the drop-down list Strategy .
- Then, click Open List to open the table, into which you have to type in the names of the attributes , their values , and the numbers of the successors . The FlowControl searches the table from top to bottom until it finds an attribute with the value you typed in. The FlowControl then moves the part on to that successor.
- The number of the default successor decides to which successor the FlowControl sends the part whose attributes do not meet the criteria in the list. In our example neither the attribute Color for the attribute Shape of the part BlackOctagonal meets the criteria.

<!-- image -->

<!-- image -->

- Run the simulation and watch what happens:
- When you use the default setting 1 , the FlowControl moves the part on to the successor object with the number 1.
- When you type in 0 , the FlowControl does not move the part on. It remains in front of the FlowControl , thus blocking the following parts.
- When you type in -1 , or any other negative number, Plant Simulation show an error message. You can then react accordingly by determining what should happen to the part.

<!-- image -->

<!-- image -->

<!-- image -->

**Back to Distribute Parts Among its Successors with the FlowControl**

Loading, Unloading, and Reloading Parts

Load, Unload, and Reload Parts with the TransferStation

To define your own way of transferring parts from station to station, you can use the TransferStation . You can insert the TransferStation into your simulation model from the folder Tools in the Class Library or from the toolbar Tools in the Toolbox .

<!-- image -->

**Note**

The TransferStation is, by default, not shown when you create a new model. The PickAndPlace robot can emulate most of the functions of the TransferStation .

In our example below we load a block of four parts onto a pallet, which is transported to another section within the plant on a conveyor line. At the location in the plant, which is marked by a sensor, we unload parts in blocks of two from the pallets and reload them onto a transport vehicle. Finally, we unload parts in blocks of one from the transport vehicle onto a processing station and then remove them from the plant.

**Load Parts with the Transfer Station**

<!-- image -->

**Back to Transfer Parts from Station to Station**

###### Load Parts with the Transfer Station

One of your most basic tasks when creating a simulation model will be to load parts onto a means of transport, a Container or a Transporter and to unload them from a means of transport.

When loading parts, the TransferStation gets these parts from the parts station and loads them onto a means of transport, which has to be located at the target station. The loading process starts as soon as part and means of transport are ready.

To model a loading process, proceed like this:

- Insert the conveyor named Conveyor , which transports the parts.
- Insert a Source , which creates the parts. In our sample model we named it SourceParts .
- Insert a ParallelStation , which processes the parts before they are loaded onto pallets.
- Insert a Source , which creates the pallets onto which the TransferStation loads the parts. In our sample model we named it SourcePallets .

<!-- image -->

<!-- image -->

<!-- image -->

- Insert a TransferStation , which loads the processed parts onto the Container , i.e., the means of transport, which moves on the conveyor. In our sample model we named it LoadingStation . Then, we have to tell this station what we want it to do:
- We want to load parts, so we select Load as the Station type .
- Then, we have to tell it where the parts to be loaded come from. For this we click the button and select the ParallelStation in the dialog Select Object .
- Next, we have to tell it where the means of transport , our Container , is located . For this we click the button and select the Conveyor in the dialog Select Object .
- Finally, we have to designate the position on the Conveyor , where the LoadingStation loads the parts onto the pallets. For this we type 0 meters as the position of the sensor into the text box on the tab Attributes . The LoadingStation automatically inserts this sensor into the object Conveyor .

To show a tooltip with information about the sensor, drag the mouse over the red line designating it on the object.

**Note**

To successfully transfer the MU onto the target station, you have to make sure that the target station provides enough space to accommodate the incoming MU .

<!-- image -->

To set how we want the parts to be loaded, we click the tab Advanced Attributes .

We want to load all blocks of parts in blocks of 4 .

<!-- image -->

Compare Create a Sensor [material flow objects]

Back to Load, Unload, and Reload Parts with the TransferStation

###### Reload Parts with the Transfer Station

When reloading parts, the TransferStation takes these parts from a means of transport ( Container or Transporter ), which is located at the parts station, and places them onto a Container or a Transporter , which is located at the target station. The parts station is the station, which provides the parts to be transported. The target station is the station onto which the parts will be placed. The reloading process starts as soon as both means of transport are ready.

To model a reloading process, proceed like this:

- Insert a Source , which creates the Transporters . In our sample model we named it SourceTransporters .
- Insert the Track , on which the Transporter transports there loaded parts.
- Insert a TransferStation , which reloads the transported parts from the Container into the Transporter . In our sample model we named it ReloadingStation . Then, we tell this station what we want it to do.

<!-- image -->

- We want to reload parts, so we select Reload as the Station type .
- Then, we have to tell it where the parts to be reloaded come from . For this we drag the Line/ Conveyor from the Frame ever the text box in the dialog of the ReloadingStation and drop it there.
- Next, we have to tell it where the means of transport , our Transporter , is located . For this we drag the Track from the Frame ever the text box in the dialog of the ReloadingStation and drop it there.
- Finally, we have to designate the exact spot on the Line/Conveyor , where the ReloadingStation removes the parts from the pallets. For this we enter 22 meters as the position of the sensor , which the ReloadingStation automatically enters into the object Line/Conveyor .

**Note**

To successfully transfer the MU into the target station, you have to make sure that the target station provides enough space to accommodate the incoming MU .

<!-- image -->

- As we want to reload the parts from the pallet onto a Transporter , we have to designate the exact spot on the Track , where the ReloadingStation loads the parts onto the Transporter . For this we enter 15 meters as the position of the sensor , which the ReloadingStation automatically enters into the object Track .
- To set how we want the parts to be reloaded, we click the tab Advanced Attributes . We want to load parts in blocks of 2 .

<!-- image -->

**Compare Create Sensors**

**Back to Load, Unload, and Reload Parts with the TransferStation**

###### Unload Parts with the Transfer Station

When unloading parts, the TransferStation unloads these parts from a Container or a Transporter , which is located at the parts station, and places them onto the target station. The unloading process starts as soon as a means of transport is ready at the parts station.

To model an unloading process, proceed like this:

- Insert a Station , on to which the UnloadingStation unloads the parts from the Transporters .
- Insert a Drain , which removes the parts from the plant.
- Insert a TransferStation , which unloads the parts from the Transporter and places them on to the processing station named Station . In our sample model we named it UnloadingStation . Now we tell this station what we want it to do.
- We want to unload parts, so we select Unload as the Station type .

<!-- image -->

- Then, we have to tell it where the parts to be unloaded come from . For this we drag the Track from the Frame ever the text box in the dialog of the UnloadingStation and drop it there.
- Next, we have to tell it where the means of transport , our Transporter , is located . For this we drag the Station from the Frame ever the text box in the dialog of the UnloadingStation and drop it there.
- To designate the exact spot on the Track , where the UnloadingStation unloads the parts from the Transporters in to the processing station Station , we enter 43 meters as the sensor position. The UnloadingStation automatically enters this sensor into the object Track .
- To set how we want the parts to be unloaded, we click the tab Advanced Attributes . We want to unload all blocks of parts in blocks of 1 .
- Insert a Method , enter deleteMovables is the source code, and name the Method reset .
- Insert an EventController into the Frame , and run the simulation.

You can then change a number of settings, such as the dimensions of the Transporters and the Containers , the block size, the number of blocks, etc. and watch how these changes affect the simulation model.

Compare Create a Sensor [material flow objects]

Back to Load, Unload, and Reload Parts with the TransferStation

#### Setting a Station Up

Set a Station Up

You can define how to set up the objects Station , ParallelStation , AssemblyStation , DismantleStation , and Drain to process another type of MU .

**You can:**

- Select Set-up Options on the tab Set-Up .
- Select the Set-Up Time on the tab Times .

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

Back to Model the Flow of Materials, Basics

<!-- image -->

##### Selecting Set-up Options

Select Set-up Options

When you set up a station you will first select the set-up options. Next to Set-up For Plant Simulation show which type of MU the object is presently set up for or is going to be set up for. If the object has not been set up yet at all, it shows a hyphen -. To tell one type of MU from the other, Plant Simulation wither uses the name of the MU or a user-defined attribute of the MU .

<!-- image -->

First, you will select if you want to:

- Set the Station Up Automatically
- Only Set the Station Up When it is Empty
- Set the Station Up after it Processed a Certain Number of Parts
- After you have done this, you will Select the Set-Up Criteria .

Go to Select the Set-Up Time

Back to Set a Station Up

Set the Station Up Automatically

To automatically set the object up, select Automatic . Then, the material flow object triggers the set-up process as soon as a MU of the corresponding MU [type intends to move onto it.

<!-- image -->

To define the set-up process in a Method , clear the check box.

**Back to Select Set-up Options**

Only Set the Station Up When it is Empty

To only start setting-up the object for the next type of MU when it is Empty , select Only When Empty . MUs of the type for which the object is setting-up can only enter the object, after the set-up process is finished.

<!-- image -->

To allow MUs to enter the object although it has not been set-up for their type yet, clear the check box.

Their set-up time begins, when all set-up processes you specified are finished. MUs located on the object will be processed with the settings for the MU type for which the object was set-up before.

**Back to Select Set-up Options**

Set the Station Up after it Processed a Certain Number of Parts

To set the material flow object up, after a certain number of parts have been processed, select the check box Set-up After . Then, enter the number of parts into the text box after which you want the object to be set up. The object also sets up and starts counting anew, starting from 1, when the part type changes before the number you enter is reached. For this reason it may happen that the object does not reach the number of parts of a certain type for which it is to set up.

<!-- image -->

The object always sets up for the part type, which is going to enter the object next. For this reason the set-up process does not start immediately after the n-th part has been processed or when this part exits the object. Setting-up starts as soon as the (n+1)-th part enters the station.

- Select Before Next Part to set the object up immediately after the n-th part was processed.
- Select After Last Part to set the object up after the n-plus-first part wants to move onto the station.

**Note**

The number of parts is the number of parts entering the station. These parts do not necessarily have to be processed. Statistics also counts parts, which are removed from the station before they have been processed, for example during the set-up process or while the station is waiting for a service to be performed.

**Back to Select Set-up Options**

Select the Set-Up Criteria

After you decided how the station sets-up, you can select when the object has to be set up:

- When the name of the MU ( MU Name ), which wants to move onto the station, changes.
- When the value of a user-defined attribute of the MU changes.
- Select User-defined Attribute from the drop-down list.
- Enter the name of the user-defined attribute of the MU into the text box. This user-defined attribute has to be of data type string . The material flow object sets up, when a MU , whose user-defined attribute has a different value, moves onto the station.

<!-- image -->

In our example we created a user-defined attribute named Color for the MU types. Let us assume that the station is set up for red . When a MU with the user-defined attribute Value blue moves onto the station, it sets up for blue .

<!-- image -->

**Back to Set a Station Up**

Select the Set-Up Time

The set-up time is the time it takes to set the station up for processing a different type of MU . An identical name designates that MUs are of the same type. In this case the material flow object will not have to set up for a different MU type. It only needs to set up, when the MUs are of another type, denoted by a name that differs from the previous type.

For the set-up time, you can select a distribution from the drop-down list on the tab Times , depending on the type of MU , or the location on a station, or you can enter a constant time. When you selected a distribution, you will then enter the values, which that distribution requires, into the text box. Plant Simulation show these values along the upper border of the tab. In addition to any of the other distributions, you can select the Matrix(Type) distribution.

<!-- image -->

When setting-up, the time may not only depend on the target type, for which you want to set up, but also on the source type. In this case you can define the times in a table. Activate the user-defined row index and the user-defined column index of the table. The row index designates the source type. The column index designates the target type.

<!-- image -->

In our example above setting-up from no type, indicated by the hyphen, to the target type Part takes exactly one minute. Setting-up from the type Part to the type Transporter takes two minutes and seven seconds.

If you select the Formula distribution, you can enter a numeric expression or the name of a Method . You can use the anonymous identifier @ to access the MU for which the set-up time applies.

**Note**

You can also determine the set-up time in a user-defined attribute of data type method , which you created for the MU !

<!-- image -->

Compare Specify Times in Object Dialogs

Go to Select Set-up Options

**Back to Setting a Station Up**

#### Defining Processing Times

##### Define Processing Times

The Processing Time is the time, which the MU remains on the material flow object to be processed. It is the interval between set-up and the time the material flow object moves it on to its successor.

<!-- image -->

**On the tab Times you can:**

- Select a distribution from the drop-down list and enter the required values

<!-- image -->

.

- Enter a constant time ( Const ). In our example we entered half a minute (30 seconds)

<!-- image -->

.

- Select to process the MU depending on its type List(Type)
- Select to process the MU depending on the station on which it is located on a ParallelStation List(Place) .

<!-- image -->

<!-- image -->

After you selected a distribution, you will then enter the values, which that distribution requires, into the text box. Plant Simulation shows these values along the upper border of the tab. For the negative exponential distribution for the Recovery Time in the example above, you have to enter values for Beta , and optionally the Lower Bound and the Upper Bound .

When you select Formula , you can type in a numeric expression or the name of a Method . You can use the anonymous identifier @ to access the MU for which the processing time applies. This Method may also be a user-defined attribute of data type method of the MU .

The successor is the object that is connected to the selected object with a Connector and that succeeds it in the sequence of stations in the simulation model.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

Compare Specify Times in Object Dialogs

CompareChange the Processing Time in the Entrance Control

Compare Set a Station Up

Compare Use Probability Distributions

Back to Model the Flow of Materials, Basics

Video on YouTube

[https://youtu.be/PQhEriOzVzU?si=gwIvKoQ0I2mro1IB&amp;t=31](https://youtu.be/PQhEriOzVzU?si=gwIvKoQ0I2mro1IB&t=31)

Specify Times in Object Dialogs Plant Simulation inputs and outputs data referring to times in the format 1:00:00:00 , standing for, left to right, days:hours:minutes:seconds.split seconds . 12:34 for example, means 12 minutes and 34 seconds.

<!-- image -->

If you do not want to write one day out in full, just type 1::: and click Apply . Plant Simulation then translates this to the full format 1:00:00:00 .

<!-- image -->

<!-- image -->

You can also enter numbers without the colon. Plant Simulation then interprets the number as seconds and converts it into the above format. 111 (seconds), for example, is 1 minute and 51 seconds.

You can change time-related settings under File &gt; Model Settings/Preferences &gt; Units &gt; Time Scale .

**Back to Times**

Specify Data of a Probability Distribution

Select the distribution you want to use for the processing time from the drop-down list on the tab Times . Then, Plant Simulation shows the parameters, which this distribution requires, when you click into the text box.

<!-- image -->

Enter the respective values into the text box. The lower bound and the upper bound are optional, you can, but do not have to specify them.

<!-- image -->

Compare Use Probability Distributions

Back to Define Processing Times

Define Processing Times Depending on the Type of MU

To set the Processing Time of a station depending on the type of MU , you can use the List(Type) distribution.

<!-- image -->

- Select the List(Type) distribution as the Processing Time .
- Enter the name of the DataTable object into the text box.

Enter the names of all MUs to be processed into column 1 of the table and the respective times in seconds into column 2. Plant Simulation then uses this time as the processing time for the respective MU type.

<!-- image -->

During the simulation run Plant Simulation reads the processing time from that table.

**Back to Define Processing Times**

Define Processing Times in a Formula

To define the processing time of a station in a formula:

- Enter the name of a Method into the text box and program the formula in that Method .
- Enter the formula as a basic arithmetic operation directly into the text box.
- Enter the formula directly into the text box and access the MU for which the processing time applies with the anonymous identifier @.

**To set the processing time of a station in a formula using a Method:**

- Select Formula as the Processing time .

<!-- image -->

- Enter the name of a Method object into the text box. Type the formula into the Method . This Method has to return a value of data type time .

The source code looks like this:

```simtalk
-> time
if @.Name = "red"
	result := 60
elseif .Name = "blue"
	result := 180
else
	result := 120
end
```

<!-- image -->

In our example, the formula, which we typed into the method cyclesMethod , sets how long the station processes the MUs in accordance to their color.

**To set the processing time of a station in a formula with an arithmetic operator:**

- Select Formula as the Processing time .
- Type the expression into the text box. In our example we typed @.MyAttribute+1 . This formula adds 1 minute to the processing time of MUs that have the user-defined attribute MyAttribute . We defined MyAttribute in the class of the MU .

<!-- image -->

To set the processing time of a station by accessing the MU:

- Type @.timeRed into the text box.
- Create a user-defined attribute for the MU and name it timeRed .

**Back to Define Processing Times**

##### Define Processing Times of a ParallelStation

To set the processing time of a ParallelStation with several processing places, which have different but constant processing times, you can use the List(Place) distribution.

<!-- image -->

- Select the List(Place) distribution as the Processing time .
- ·
- Enter the name of the DataTable object into the text box. In this table, the entry [ 1,2 ] matches the processing place located at position [ 1,2 ], for example. When a MU arrives at a processing place of a ParallelStation during a simulation run, Plant Simulation

takes the appropriate time for that station from the table.

<!-- image -->

**Back to Define Processing Times**

#### Modeling Failures

Model Failures To closely model real situations, where machines fail at times, you can define one or several failure profiles . Failures do affect the technical availability of the individual stations. You can:

- Manually fail the object by selecting Failed in the dialog of the material flow object. When you fail the object like this, you will also have to manually remove the failure by clearing the check box again.
- Define failures with the failure generator on the Tab Failures .

<!-- image -->

The state of the station then changes from operational to failed .

- By default a Failed object shows a red dot in the LED display area along the upper border of the icon.

3D shows the state of the object as a colored ring on a pole by default.

**Note**

The LED can simultaneously display several states that are active at the same time, while the state icon can only display the state it represents.

- To use an icon for each of the different states, create a new icon in the Icon Editor , and name it failed . Click State Icons/LEDs &gt; Use State Icons on the General ribbon tab of the Icon Editor , to make the object show state icons, instead of the LEDs.

<!-- image -->

When you manually fail a station, it remains failed while any of the failure profiles you defined is active. It will change to not failed when the last failure ( DisruptionEnd ) of the last failure profile is over or you clear the check box .

As soon as the failure starts, the object changes to inactive for the duration of the failure. During this time it will not receive any parts. If a part is located on the object, its processing is interrupted for the duration of the failure and continues when the failure is cleared. Plant Simulation adds the duration of the failure to the processing time or to the dwelling time.

If a MU could not enter the object because of a failure, Plant Simulation unblocks the MU as soon as the failure ends.

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

Go to Configure Failures

Go to Change Failure Settings During the Simulation Run

Back to Basics

Configure Failures

**Note**

If you change failure settings, we recommend to first clear the check box Active and to then click Apply . Then change your settings, apply them, and select the check box Active again. This ensures that the next failure event ( DisruptionBegin / DisruptionEnd ) will be computed with a complete set of valid parameters.

**Note**

The failure of the object is only active if you activate the check box Active on the tab Failures and the check box Active of the corresponding failure profile !

<!-- image -->

To simulate the real behavior of machines, which fail now and then and which have to be repaired, you can define one or several failure profiles for a station. Proceed as follows:

**Procedure**

1. To run your simulation model with failures in general, make sure that the check box Active on the Tab Failures is selected.
2. Click New and select and enter the parameters of the failure profile you are defining into the dialog that opens.
3. Enter a Name for the failure profile .
4. Select if this failure profile is Failed or not during the simulation run.
5. Select a distribution for the time at which the first failure takes place from the drop-down list Start . Enter the values, which that distribution requires, into the text box. Plant Simulation shows these values along the upper border of the tab.
6. The Lognormal distribution , the Erlang distribution , and the Negative exponential distribution are especially suited for modeling failures.
6. Select a distribution for the time at which the last failure will take place from the drop-down list Stop . Enter the values, which that distribution requires. Plant Simulation shows these values above the list of distributions which you can select.
8. If you do not enter a Start time and a Stop time, the first failure occurs after the Interval you entered is over. Any value you enter as the Start time overwrites this behavior.
7. Select the check box Availability and enter the Availability in percent and MTTR . To specify the Interval and the Duration of a failure instead, clear the check box Availability . Availability and MTTR is just another kind for displaying the Interval and the Duration . If you enter values for Availability and MTTR and click Apply , Plant Simulation computes the values for the Interval and

the Duration and enters them into the respective text boxes. It also selects the Negexp distribution for the Interval and the Erlang distribution for the Duration . Plant Simulation shows them in the dialog if you clear the check box Availability . An availability of 100 percent has an MTTR of 0, as the machine is available and does not have to be repaired.

<!-- image -->

If you select any of the provided distributions, you have to enter the parameters that this distribution requires. Plant Simulation will enter the resulting value for the MTTR into the text box MTTR , you cannot edit it.

<!-- image -->

8. If you want to select a distribution for the Interval and the Duration , clear the check box Availability . Then select a distribution for the time between the end of the last failure and the beginning of the next one, i.e., the failure Interval, from the drop-down list. Enter the values, which

that distribution requires, into the text box. Plant Simulation shows these values above the list of distributions which you can select.

Select a distribution for the Duration of the failure. Enter the values, which that distribution requires, into the text box. Plant Simulation shows these values above the list of distributions which you can select.

<!-- image -->

**9. Select the time to which the failures relate from the drop-down list:**

**· Simulation Time**

Consumes the time you entered for the failure interval, regardless of the state the object is in. An example could be the electrical system of the plant, which may fail at any point in time. The Simulation Time is the time between the beginning of the simulation run ( Reset Simulation , Start Simulation ) and its end ( Stop Simulation ).

**· Operating Time**

Consumes the time you entered for the failure interval only if the object is operational. An example could be the coolant pump of the engine, which may fail any time during which the machine is on; the machine does not actually have to process parts. The Operating Time will be interrupted by pauses and failures .

**· Processing Time**

Consumes the time you entered for the failure interval while the object is processing. An example could be a saw blade, which can only break, when the machine actually saws materials.

For point-oriented objects the Processing Time is the time during which a part is located on a material flow object and is being processed by it.

For conveying objects, such as the Conveyor , the Processing Time is the time during which its speed is not 0. It can also be working , when the conveyor is moving and does not transport a part.

For processing time based failures of a ParallelStation the simulated MTBF is reduced, when the number of parallel processing operations of parts on the ParallelStation increases. This means that the more parts are processed simultaneously, the sooner the failure occurs, and the smaller the availability becomes. This then prevents the Availability you entered into the dialog from being reached.

<!-- image -->

10. Click OK to add this failure profile to the list of failure profiles . If you want to edit a failure profile , double-click it in the list or click Edit .
11. Repeat this procedure for any additional failure profiles you want to define.

Go to Change Failure Settings During the Simulation Run

Go to Random Numbers and Their Statistical Distribution

Compare Model Random Processes

Compare Specify Times in Object Dialogs

Back to Model Failures

Video on YouTube

[https://youtu.be/PQhEriOzVzU?si=8y6fctOOliWSL2gp&amp;t=118](https://youtu.be/PQhEriOzVzU?si=8y6fctOOliWSL2gp&t=118)

Change Failure Settings During the Simulation Run

In real-life machines fail more often as they grow older. This is why you will want to reduce the Availability of the machine in the simulation model during the simulation run after a certain time has passed.

- To change the Availability and the MTTR of our station MyStation via SimTalk , enter the following instructions into a Method . In our example we called this method setFailure .

**Note**

As our machine MyStation only has a single failure profile , we can type in the instructions in the simplified notation as below. Plant Simulation then always uses the first failure profile . If the machine had several failure profiles , we would have to address the attributes via the respective failure profile , MyStation.Failures.MyFailureProfile1.Availability := 80 for example.

The source code looks like this:

```simtalk
// Reduces the availability and the MTTR during the simulation run. // This method is called by the init method via a method call after 12 hours.
print EventController.simTime," Simulated availability in the morning: ",round(100 * (1 - MyStation.StatFailPortion),2)," %" MyStation.initStat // reduce the availability
MyStation.Availability := 80
MyStation.MTTR := str_to_time("10:00")
MyStation.FailureActive := false
MyStation.FailureActive := true // activate failures
```

- To start reducing the Availability of the machine after 12 hours have been simulated, enter the following instructions into the init method in the model:
- To reset the Availability of the machine at the start of the next simulation run to 100 percent, enter the following instruction into the reset method in the model.
- To show the simulated Availability at the end of the simulation run in the Console , enter the following instruction into the endSim method in the model.
- Type in 1:00:00:00 to simulate a day
- Then, run the simulation and watch what Plant Simulation shows in the Console .

&setFailure.executeIn(str_to_time("12:0:0"))

```simtalk
MyStation.Availability := 100
print EventController.simTime," Simulated availability in the afternoon: ", round(100 * (1 - MyStation.statFailPortion),2)," %"
```

For the first 12 hours of the simulation run the Availability of the object MyStation was 100 percent. Then we set the Availability to 80 percent and the MTTR to 10 minutes and deactivated and reactivated failures , to make sure that the next failure is computed with a complete set of valid parameters.

After an additional 10 hours of simulating, compare the end time of the EventController , the Availability of the machine MyStation has decreased to 86.18 percent.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

Back to Configure Failures

Compare Model Random Processes

Compare Specify Times in Object Dialogs

Back to Model Failures

#### Buffering Parts within the Production Line

Buffer Parts within the Production Line

The Buffer , which you place between two components or stations of your plant, serves two purposes:

- It temporarily holds parts, when one of the components following it in the sequence of stations fail.
- It moves parts on, when the preceding components stop working, preventing the production process from grinding to a halt.

Dimensioning a Buffer with a large enough capacity for covering all failures leads to a complete decoupling of both components of your plant.

The Buffer not only tides over failure times but also serves as a compensating station for fluctuating transport and operating times, which lead to queues forming in front of a machine or a component. But even then it cannot always prevent the material flow from being interrupted or coming to a halt.

You can insert the Buffer into your simulation model from the folder MaterialFlow in the Class Library or from the toolbar MaterialFlow in the Toolbox .

<!-- image -->

Below we demonstrate how to:

- Use a Buffer between Processing Stations
- Check the Fill Level of the Buffers in the Plant

Back to Model the Flow of Materials, Basics

Use a Buffer between Processing Stations

In our sample model consisting of a simple production line with a source , a processing station , a test station , and a drain , the processing station is blocked now and then because the test station cannot test the parts fast enough.

<!-- image -->

To remedy the situation, we inserted a Buffer between the processing station and the test station . The Buffer temporarily holds the parts before moving them on to the test station .

As compared to the default settings we changed the capacity of the Buffer from 4 to 200 and entered a processing time of 15 minutes. We left the remaining settings unchanged.

<!-- image -->

When you now run the simulation, you will notice that the processing station will not be blocked because the Buffer temporarily holds a maximum of 200 parts for 15 minutes each before the testing station can test them.

The tab Statistics shows the relative occupancy, the percentage of the time it was relatively empty or relatively full, maximum and minimum contents, and the number of entries and exits.

<!-- image -->

You can also use a Chart to show how the number of parts in the Buffer develops over time.

<!-- image -->

To show more parts on the icon of the Buffer than it will normally show, you make the icon of the Buffer wider. To do so, hold down Shift and Ctrl , drag the mouse over the right border of the icon, and drag the mouse to the right.

<!-- image -->

Our model looks like this in 3D.

<!-- image -->

As the Buffer in 2D only has a single animation point, it stacks the parts in 3D.

**Go to Check the Fill Level of the Buffers in the Plant**

**Back to Buffer Parts within the Production Line**

Checking the Fill Level of the Buffers

Check the Fill Level of the Buffers in the Plant

At times you may also want show the relative fill level of the Buffer :

- To display the relative fill level of the Buffer as a colored bar at the bottom of its icon in 2D , select the check box Show Fill Level on the tab Attributes . Be aware that the bar just shows a quantitative portion, not exact numbers.

<!-- image -->

To display the fill level of the Buffer in 3D , select Fill level from the drop-down list Show Contents As .

- To view more exact percentages, click the tab Statistics , and check the following values:
- Relatively empty shows the portion of the statistics collection period during which the object was empty in relation to the time during which the object was available.
- Relatively full shows the portion of the statistics collection period during which all temporary storage places of the Buffer were occupied in relation to the time during which the object was available.

The finished simulation model for demonstrating these features looks like this:

<!-- image -->

<!-- image -->

To create the sample model, you will:

- Configure the Processing Stations
- Configure the Buffers
- Configure the Chart for Showing the Full and Empty Portions
- Show the Fill Level of the Buffers in 3D

Back to Use a Buffer between Processing Stations

Back to Buffer Parts within the Production Line

Configure the Processing Stations

Insert and configure the processing stations, which process the parts for a certain time before passing them on to their successors in the succession of stations into the factory:

- We inserted five stations of type ParallelStation in our sample model.
- Enter the Capacity of the processing stations. We used the default setting, namely 2 as the XDimension and as the Y-Dimension respectively. This results in 4 processing places on each station.

<!-- image -->

- Enter a Processing Time . We decided to use a normally distributed time with the values shown below.
- Enter settings for Failures of the processing station. We decided to use an Availability of 92 percent.

<!-- image -->

<!-- image -->

We used the same settings for the other processing stations as well.

Back to Check the Fill Level of the Buffers in the Plant

<!-- image -->

###### Configure the Buffers

Insert and configure the Buffers , which temporarily hold the parts.

We inserted four Buffers into our sample model and used the settings below for all of them.

<!-- image -->

Insert and configure the rest of the stations so that they match the screenshot below.

<!-- image -->

Then, run the simulation and check the tab Statistics of the individual Buffers , specifically the values for relatively empty and relative full in the middle column of the tab.

<!-- image -->

**Back to Check the Fill Level of the Buffers in the Plant**

Configure the Chart for Showing the Full and Empty Portions

In addition to viewing the percentage values for relatively empty and relative full on the tab Statistics , you can also display these values in a Chart .

To do so, proceed as follows:

- Insert a Chart into the simulation model.
- Click the tab Display and select the Category &gt; Chart .
- Click the tab Data and select the Data Source &gt; Input Channels .
- Deactivate inheritance of the input channels table and click Input Channels .

<!-- image -->

<!-- image -->

- Enter the labels of the values you want to display into the table. We entered Empty , Partially full , and Full into the cells of the row index.
- As we want to drag the Buffers onto the Chart and drop them there to display the values, we need to create a drag-and-drop control for the Chart :
- Select Tools &gt; Edit Controls , click in the text box next to drag-and-drop , and press the F4 key. This creates the drag-and-drop control as a user-defined attribute of data type method .
- Copy the following source code and paste it into the method that opens:

<!-- image -->

<!-- image -->

```simtalk
param draggedObjects: object[]
var obj: object
var numBuffers: integer
var MyTab : table := @.InputChannels // inheritance of the table 'InputChannels' is already deactivated
MyTab.delete({1,0}..{*,*})
for var i := 1 to draggedObjects.dim
	obj := draggedObjects[i]
	switch
		obj.internalClassType
	case "Buffer", "PlaceBuffer", "Sorter"
		numBuffers := self.~.InputChannels.xDim +1
		MyTab[numBuffers,0] := obj.Name
		MyTab[numBuffers,1] := obj.Name + ".statRelativeEmptyPortion"
		MyTab[numBuffers,2] := "1 - " + obj.Name +
".statRelativeEmptyPortion - " + obj.Name + ".statRelativeFullPortion"
MyTab[numBuffers,3] := obj.Name + ".statRelativeFullPortion"
end
next
print "Number of detected buffers: ", numBuffers
@.InputChannels := MyTab // makes the chart apply the new settings
@.Active := true
```

- Drag a marquee over all objects in the model, drag them onto the Chart , and drop them there. The Chart automatically knows for which of the objects it can display values and then displays them.

Back to Check the Fill Level of the Buffers in the Plant

<!-- image -->

Show the Fill Level of the Buffers in 3D

To display the fill level of the Buffer in 3D , select Fill Level from the drop-down list Show Contents As on the Tab Fill Level of the dialog Edit 3D Properties . You can also define settings for the Position , the Rotation , and the Dimension of the fill level indicator.

<!-- image -->

Just like in 2D the fill level bar just shows a quantitative portion of the MUs located in the Buffer , not exact numbers.

<!-- image -->

| Item       | Description                                                                                                                                                                                                                                                          | Looks like this   |
|------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------|
| MUs        | Shows the MUs stacked in the Buffer . Is the setting in previous versions of Plant Simulation .                                                                                                                                                                      |                   |
| Fill level | Shows the relative fill level of the Buffer on its picture. Gray denotes the background of the fill level indicator. Red denotes a fill level of more than 90%. Orange denotes a fill level of less than 10%. Green denotes a fill level between the above settings. |                   |
| Both       | Shows the MUs stacked on top of the fill level indicator.                                                                                                                                                                                                            |                   |

The different settings look like this in our model.

<!-- image -->

Back to Configure the Processing Stations

Back to Configure the Buffers

Back to Configure the Chart for Showing the Full and Empty Portions

Back to Check the Fill Level of the Buffers in the Plant

#### Placing Parts into Stock and Removing Them

Place Parts into Stock and Remove Parts from It

When you model your plant you will, at one point, also face the task of placing parts into stock and removing them from stock. To model a warehouse, you will use the object Store . The parts remain in the Store until you remove them with a Method . The Store accepts parts as long as storage places are available. The incoming part triggers a sensor, when it enters the Store . The sensor then calls an Entrance Control , i.e., a Method object, that determines the storage place onto which the Store deposits the part . The Entrance Control can, for example, update the inventory list or execute any other action which you program. If you do not use an Entrance Control , the Store deposits the part into the first free storage place in the net of coordinates of the storage places.

In our sample model the material flow is controlled by the method placeInStock , which we use as the Entrance Control of the warehouse, and by the method removeFromStock , which we use as the Exit Control of the station RetrieveFromStore .

As parts occasionally have to be reworked, we want to change the original order of parts, which are placed into stock, and we then want to re-establish the original order when we remove them from stock. We do this in the station MixOrders located directly before our Store .

We have to set the size of the Store according to the degree of change of the sequence to prevent it from overflowing. To accomplish this, two events are essential: First an additional part arrives at the Store and second a part is removed from the Store . When the Store is full, it does not accept any additional parts. We therefore have to increase the size of the Store in the Entrance Control of the Store is full. Each part that is placed into stock and that is removed from stock must be registered on the data table InventoryTable . To manage the inventory and to remove parts from stock, we program the control AttemptToRemoveNextPart , which is called by the methods placeInStock and removeFromStock . The method AttemptToRemoveNextPart checks whether the next removing action is possible so that the original order of the parts can be re-established so that the production process can be maintained without a shortage of parts.

In the reset method we delete the contents of the InventoryTable and reset the counter of the variable named NextNumber to 1.

You can insert the Store into your simulation model from the folder MaterialFlow in the Class Library or from the toolbar MaterialFlow in the Toolbox .

<!-- image -->

First we insert the material flow objects that we need:

- The Source named Receiving creates the parts.
- The ParallelStation named MixOrders mixes the original production sequence.
- The Store places parts in stock and removes them from it.
- The Station named RetrieveFromStore retrieves the required parts from the Store .
- The Drain named Shipping removes the parts from the plant.

Then we insert the Methods and the visualization objects Chart and Variable . We finally connect the objects Receiving , MixOrders , and MyStore and RetrieveFromStore and Shipping with Connectors . We do not connect MyStore and RetrieveFromStore as retrieving parts is controlled by Methods .

The finished simulation model looks like this:

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

Compare Stack Parts in the Store

**Back to Model the Flow of Materials, Basics**

##### Configure the Stations

To create our simple warehouse model, we first have to set the stations up:

<!-- image -->

- To make the Source produce a part every minute, enter 1:00 as the interval . To stop producing parts after a day, enter 1:00:00:00 for Stop .

<!-- image -->

- As parts occasionally have to be reworked, we want to mix up the original order of parts to be placed into stock, and we then want to re-establish the original order which is required for our production process when removing the parts from stock.

To set the size of the station MixOrders , which is a ParallelStation , according to the degree of change of the sequence of the arriving parts, enter an X-Dimension of 200 and an Y-Dimension of 20 .

<!-- image -->

To mix up the order of the parts that the Source produces, we need a random processing time. We selected the Uniform distribution and entered the parameters 0, 30:00 in our example. The two values denote the bounds of the Uniform distribution.

<!-- image -->

- To set the size of the Store , enter its dimensions in the coordinate net of the storage places. We entered 4 and 8 .

<!-- image -->

As the Store is passive material flow object, you have to program how it handles the parts.

To specify the name of the Entrance Control , which registers the parts contained in the Store in a data table, click the button and select the name of the method in the dialog that opens. We named our Entrance Control PlaceInStock .

<!-- image -->

- To configure the Station named RetrieveFromStore that receives the parts that are removed from stock, enter and select the settings for the Exit Control .

We named our Exit Control RemoveFromStock . It catches the event after a part has been successfully removed from the Store .

<!-- image -->

Then select the check box Rear , so that the control is Rear -triggered, i.e., after the part has left the station RetrieveFromStore .

Go to Program the Method that Places Parts into Stock

Back to Place Parts into Stock and Remove Parts from It

Program the Method that Places Parts into Stock After configuring the material flow stations in our warehouse model, you have to program the method that places parts into stock of the Store . In our sample model we named this method placeInStock and typed in the following source code:

```simtalk
// entrance control of the object 'MyStore' // find next free row in the 'InventoryTable' of 'MyStore'
var NextRow : integer
var NextRow := Inventory.ydim + 1 // enter the ID of the new part and the path // to the part in the 'InventoryTable' InventoryTable[0,NextRow] :=
@.id
InventoryTable[1,NextRow] := @ AttemptToRemoveNextPart // name of our Method // increase the capacity of 'MyStore' if needed
if MyStore.full
	MyStore.xDim := MyStore.xDim + 4
end
```

The object MyStore uses this method as the Entrance Control .

Back to Place Parts into Stock and Remove Parts from It

<!-- image -->

Program the Method that Removes Parts from Stock

After configuring the material flow stations in our warehouse model, you have to program the method that removes parts from stock. In our sample model we named this method RemoveFromStock and entered it as the Exit Control of the Station RetrieveFromStore . The method RetrieveFromStore in turn calls the method AttemptToRemoveNextPart which manages the inventory table We typed in this source code into the Exit Control RetrieveFromStore :

// rear-triggered exit control of the station 'RetrieveFromStore' // catches the event after a part has been successfully // removed from the Store and left the station 'RetrieveFromStore' AttemptToRemoveNextPart // name of our Method

The Station RetrieveFromStore uses this method as a Rear -triggered Exit Control .

Back to Place Parts into Stock and Remove Parts from It

<!-- image -->

Program the Method that Manages the Inventory Table

After configuring the material flow stations in our warehouse model, you have to program the method that manages the inventory table of the Store MyStore .

Our inventory table has two columns, whose data types we set in the method below. The column index shows the data types. We also showed the row index and the column index and entered Sequence into the first column and MU into the second column of the column index.

<!-- image -->

In our sample model we named the method attemptToRemoveNextPart and typed in this source code:

```simtalk
// control called by the methods 'placeInStock' and 'removeFromStock'
var sequenceNo : integer
var part       : object // check if the next part according to the original sequence // is already located in 'MyStore'
if InventoryTable.getRowNo(#NextNumber)>0
	part := InventoryTable[1,#NextNumber]
	sequenceNo := part.id
end
```

**Back to Place Parts into Stock and Remove Parts from It**

Display a Value During the Simulation with a Variable

During the simulation the Variable , which we named NextNumber in our sample model, shows the identifier of the last part that exited the Store according to the original sequence of parts produced by the Source named Receiving . To do so, we extended the source code of the method attemptToRemoveNextPart :

```simtalk
// control called by the methods 'placeInStock' and 'removeFromStock'
var sequenceNo : integer
var part       : object
// check if the next part according to the original sequence // is already located in 'MyStore'
if InventoryTable.getRowNo(#NextNumber)>0
	part := InventoryTable[1,#NextNumber]
	sequenceNo := part.id // code for displaying the value with the Variable
	if sequenceNo = NextNumber AND part.move(AttemptToRemoveNextPart)
		NextNumber := NextNumber + 1
		InventoryTable.cutRow(#part.id)
		print "Retrieved part number: ", part.id
	end
end
```

In our reset Method we delete the contents of the inventory table and the Variable again:

```simtalk
InventoryTable.delete({0,1}..{*,*})
NextNumber := 1
```

In our model this looks like this:

Back to Configure the Stations

Back to Program the Method that Places Parts into Stock

Back to Program the Method that Removes Parts from Stock

Back to Program the Method that Manages the Inventory Table

<!-- image -->

<!-- image -->

The Console shows that the parts really did exit in the restored original sequence.

<!-- image -->

**Back to Place Parts into Stock and Remove Parts from It**

Visualize the Occupancy of the Store Over Time

We can use the Chart to visualize the occupancy of the Store over time. Insert a Chart into the model and select the following settings:

- Select Input Channels as the Data Source . Then, clear the inheritance check box next to the button Input Channels so that it looks like this . Click Input Channels . Enter the name of the Store , MyStore in our case, into row 1. Enter the name of the Store and the name of the method whose values you want to display into cell 1 of column 1, MyStore.numMU in our case.
- Click the tab Display and select the Category &gt; Plotter and the Chart Type &gt; Line for displaying the plotted values.

<!-- image -->

<!-- image -->

<!-- image -->

You'll notice that the icon of the Chart changes to the icon of the Plotter in the simulation model when you click Apply or OK .

- Click the Plotter in the model with the right mouse button, select Show , start the simulation, and watch how the values develop over time.

Back to Configure the Stations

<!-- image -->

**Using the Store as Supermarket**

Back to Program the Method that Places Parts into Stock

Back to Program the Method that Removes Parts from Stock

Back to Program the Method that Manages the Inventory Table

Back to Display a Value During the Simulation with a Variable

Back to Place Parts into Stock and Remove Parts from It

#### Using the Store as Supermarket

Use the Store as Supermarket

The Store can also work as supermarket and thus represent a pulling material flow.

Here we show how the Store orders two different part types from a Source . Only when the stock of these parts falls below a certain value, the Source starts producing these parts. To facilitate this, you have to activate Supermarket in the Store and MU Selection &gt; Order Controlled in the Source .

The Store then sends these parts on to an AssemblyStation , which loads them onto the respective pallets and moves them on.

We will demonstrate how to:

- Model the Pulling Material Flow
- Configure the Store as Supermarket and the Source as Order-Controlled
- Show the Amount of Waiting Parts and the Amount of Orders

The finished simulation model looks like this:

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

Compare Place Parts into Stock and Remove Parts from It

Compare Stack Parts in the Store

Back to Model the Flow of Materials, Basics

Go to Show the Amount of Waiting Parts and the Amount of Orders

Video on YouTube

[https://youtu.be/ISYfZMdQp3w?si=oRZapujKzN7zp5-\_&amp;t=381](https://youtu.be/ISYfZMdQp3w?si=oRZapujKzN7zp5-_&t=381)

Model the Pulling Material Flow

To model the pulling material flow:

- Insert the material flow objects so that they match the figure below.

<!-- image -->

- Duplicate the Part and the Container twice each. We renamed our Parts to PartRed and PartBlue and our Containers to PalletRed and PalletBlue and colored them accordingly. We did not change any of the other settings.
- Shorten the Processing Time of the Station from 10 to 2 (0:02) seconds.
- Configure the AssemblyStation as shown in the figure below. You only have to enter the names of the parts, not their path.

<!-- image -->

<!-- image -->

<!-- image -->

Shorten the Processing Time of the AssemblyStation from 10 to 5 (0:05) seconds.

- Enter the respective pallets into Source1 and Source2 .

<!-- image -->

Back to Use the Store as Supermarket

##### Configure the Store as Supermarket and the Source as Order-Controlled

To configure the Store as Supermarket and the Source as Order Controlled :

Open the dialog of the Store :

- Select the check box Supermarket .
- Click Configuration and fill in the configuration table. Our Store has a Minimum stock of 2 parts for our PartRed and PartBlue , a Maximum stock of 6 parts, and an Initial stock of 3 parts. The Supplier of the parts is the Source named SourceParts . During the simulation the column Current shows how many parts are located in the Store .
- Open the dialog of the Source and select MU selection &gt; Order Controlled .

<!-- image -->

<!-- image -->

Run the simulation and watch what happens.

<!-- image -->

**Note**

If the simulation does not start, check the setting Main part from predecessor no of the AssemblyStation and change it if necessary.

Back to Use the Store as Supermarket

##### Show the Amount of Waiting Parts and the Amount of Orders

You can watch that the Store initially contains 3 parts each, which are loaded onto the pallets. Once the Minimum stock is reached, the Store reorders parts from the Source , which only then starts producing them. These parts are then fed into the material flow.

<!-- image -->

The command View &gt; Show Orders of the Source shows the orders which are pending with this Source . The table contains the Part Type of the ordered MUs , its Amount , and the Target of the part. The Target is the object that orders the parts.

<!-- image -->

The command View &gt; Show Orders of the Store shows the orders which are pending with this Store .

<!-- image -->

When you drag the Store configured as a Supermarket onto a Chart , it shows the occupancy for all parts that are defined in the Configuration table by default.

<!-- image -->

**Back to Use the Store as Supermarket**

#### Stack Parts in the Store

When you model your plant, you can also stack parts in the Store in 3D. To do so, just enter the Z-Dimension of the Store .

In our example the Source produces parts and moves them on onto a Conveyor . The Robot then unloads the parts from the Conveyor and places them in the Store .

The finished simulation model looks like this:

<!-- image -->

<!-- image -->

- For the Source and the Conveyor we used the default settings.
- For the Robot we entered a Loading Time and an Unloading Time of 1 second ( 0:01 ) each and a Default Angle of 180 degrees.
- Our Store can store 4 parts in each dimension.

<!-- image -->

<!-- image -->

When we run the simulation, we can watch how the Robot places the parts into stock and stacks them. The screenshots also shows that the parts move onto the Conveyor continually with the front first.

<!-- image -->

Compare Unload Stacked Parts

Compare Define the Animation Area of a Simulation Object

Back to Model the Flow of Materials, Basics

#### Loading a Container Layer by Layer

By default, Plant Simulation stacks the parts on each loading place of the Container to its maximum Z-Dimension and then starts a new layer on a new place. You can also load the parts layer by layer by activating Fill Whole Layer .

In our sample model a Source produces parts and another Source produces pallets. The top robot loads the parts onto the pallet at the first sensor of the Conveyor . The bottom robot unloads the parts from the pallet and places them onto the lower Conveyor . The Conveyors move the pallets and the parts on to their respective Drains .

<!-- image -->

<!-- image -->

With the default setting Fill Whole Layer deactivated Plant Simulation stacks the parts on the Container , before starting a new layer. This looks like this.

<!-- image -->

To load the Container layer by layer, activate Fill Whole Layer . Once a layer is loaded all the way, Plant Simulation starts a new layer. This looks like this.

Back to Model the Flow of Materials, Basics

<!-- image -->

#### Working with Workpiece Carriers

Work with Workpiece Carriers

You can use the Container as a Workpiece Carrier . To do so, select the check box in its dialog. Then Plant Simulation does not consider the workpiece carrier itself, but the workpiece loaded onto it, i.e., the MU . This affects, among others, the Processing Time and the Set-up Time of the part.

The Container can only work as workpiece carrier if it has a Capacity of 1 , i.e, if the X-Dimension , the Y-Dimension , and the Z-Dimension is 1 each.

We demonstrate the workpiece carrier in connection with an AssemblyStation for which the main part is attached to a workpiece carrier .

In our example two Sources produce a Container each which we will use as workpiece carriers . In the Entrance Control of the Sources we produce an additional Container each, our main part , which is attached to our first Container , the workpiece carrier .

Two Conveyors transport the main parts attached to the workpiece carriers to a Station , which is set up according to the SetUpTable , and which processes the parts according to the ProcessingTable .

The Containers are then delivered across an additional Conveyor to the AssemblyStations . The AssemblyStation is fed with two different add-on parts by two attached Sources . The AssemblyStation attaches the add-on parts to the main parts on the workpiece carrier . The AssemblyStation then moves the fully assembled part on to the Drain .

We will demonstrate how to:

- Configure Workpiece Carriers, Main Parts, and Add-On Parts
- Configure the Sources for Workpiece Carriers and Main Parts
- Configure the Processing Station, the Set-Up and Processing Table
- Configure the Sources for the Add-On Parts
- Configure the AssemblyStation Which Assembles the Parts
- Run the Simulation and View the Results

The finished simulation model looks like this:

Back to Model the Flow of Materials, Basics

<!-- image -->

##### Configure Workpiece Carriers, Main Parts, and Add-On Parts

For our workpiece carrier and for our main parts we use the Container . Proceed as follows:

- Open the folder MUs in the Class Library .
- Click the object Container with the right mouse button and select Duplicate .
- Rename the duplicated Container in the folder UserObjects to WorkpieceCarrier .
- Duplicate the Container twice and rename the copies to MainPartA and MainPartB .
- Duplicate the Part twice and rename the copies to AddOnPart and AddOnPartB .

**Configure the WorkpieceCarrier .**

- We selected these settings for the simulation object :
- Configure the animation object of the WorkpieceCarrier .
- Click the WorkpieceCarrier with the right mouse button and select Open in 3D .

<!-- image -->

<!-- image -->

- Click the right mouse button in the background of the 3D window and select Exchange Graphics . We selected this stacking box:
- Plant Simulation then shows this message. As we do not want to use the suggested dimensions of the stacking box, we click No .

<!-- image -->

The 3D Properties for the MU Animation of the WorkpieceCarrier look like this:

<!-- image -->

<!-- image -->

**Configure the MainParts :**

- As we want to attach the MainParts to our WorkpieceCarriers , we have to make them a little smaller than the blue stacking box. We copied the default graphic of the Part and pasted it into the main parts. The settings for the simulation objects of MainPartA and MainPartB now look like this:

<!-- image -->

- For the animation objects of MainPartA and MainPartB we selected these settings for the Transformation and the Appearance . For MainPartB we just use another color.

<!-- image -->

For the MU Animation we use an animation area with these settings.

<!-- image -->

To make sure that the add-on parts are shown on the top side of the animation area instead of on its floor, we click Show . The setting Center &gt; Z &gt; 1 ensures this.

<!-- image -->

**Configure the add-on parts :**

- For our AddOnParts that we want to attach to the MainParts we delete the default graphic and create a simple cylinder.
- We selected these settings for the simulation object and for the graphic of AddOnPartA and AddOnPartB . For AddOnPartB we just use another color.

<!-- image -->

Our add-on part A looks like this:

We did not change any other settings.

Back to Work with Workpiece Carriers

Configure the Sources for Workpiece Carriers and Main Parts

In this modeling step we configure the Sources which produce the WorkpieceCarriers :

- Our SourceCarrierA produces the WorkpieceCarriers for the MainPartA with these settings.

<!-- image -->

<!-- image -->

- In addition, we created an entrance control which creates a MainPartA on each WorkpieceCarrier . We typed in this instruction:

.UserObject.MainPartA.create(@)

<!-- image -->

- For the SourceCarrierB we use the same settings. We do, however, create a MainPartB in the entrance control with this instruction:

```simtalk
.UserObject.MainPartB.create(@)
```

**Back to Work with Workpiece Carriers**

Configure the Processing Station, the Set-Up and Processing Table

In this modeling step we configure our ProcessingStation which processes the MainParts on the WorkpieceCarriers .

- We set the Set-up Time for the MainParts on the Station in a DataTable of type List(Type) .
- Insert a DataTable and rename it to SetUpTable .
- Select Set-up Time &gt; List(Type ), drag the SetUpTable to the text box next to it and drop it there.
- We also set the Processing Time of the MainParts on the ProcessingStation in a DataTable of type List(Type) .
- Insert a DataTable and rename it to ProcessingTable .
- Select Processing Time &gt; List(Type ), drag the ProcessingTable to the text box next to it and drop it there.
- Plant Simulation formats the DataTables automatically with two columns, one for the MU Type of the part to be set-up for/processed, and one for the Processing Time / Set-up Time . We entered these Processing and Set-up Times for our MainParts :

<!-- image -->

Back to Work with Workpiece Carriers

<!-- image -->

##### Configure the Sources for the Add-On Parts

In this modeling step we configure the Sources which feed the AddOnParts to the AssemblyStation , which then attaches these to the MainParts .

We selected our AddOnPartA and our AddOnPartB as the MU to be created.

<!-- image -->

<!-- image -->

We did not change any other settings.

**Back to Work with Workpiece Carriers**

##### Configure the AssemblyStation Which Assembles the Parts

In our last modeling step we configure the AssemblyStation which attaches the AddOnParts to the MainParts .

To do so, we selected the settings below and entered into the AssemblyTable that we want to attach the respective AddOnPart to the associated MainPart .

<!-- image -->

We did not change any other settings.

We finally insert a Drain and connect the individual material flow objects with Conveyors and with Connectors . For the Drain we entered a constant processing time of 1 minute.

**Back to Work with Workpiece Carriers**

##### Run the Simulation and View the Results

When we run the simulation, we can watch that the Sources first create our WorkpieceCarriers , i.e., the blue stacking boxes, and then the respective MainParts , i.e., the violet or orange plates.

<!-- image -->

After the MainParts were processed on the ProcessingStation , the AssemblyStation attaches the AddOnParts to the MainParts which are located on the WorkpieceCarriers .

<!-- image -->

Product Statistics of our WorkpieceCarrier for the attached MainPartA or MainPartB looks like this after it has left the AssemblyStation :

Back to Work with Workpiece Carriers

<!-- image -->

<!-- image -->

#### Balancing a Production Line

Balance a Production Line

The object Cycle synchronizes the transfer of parts from station to station within a production line. You can use it to only move a part on to the next station within a balanced line, when all stations have finished processing their parts and when none of the stations is failed, paused, or unplanned. In addition, the successor of the balanced line has to be ready to receive the part.

You can insert the object Cycle into your simulation model from the folder MaterialFlow in the Class Library or from the toolbar MaterialFlow in the Toolbox .

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

We will demonstrate how to:

- Open the Production Line Model Created in 2D
- Convert the Production Line Model to a 3D Model

Back to Model the Flow of Materials, Basics

##### Open the Production Line Model Created in 2D

We created the simulation model in a previous version in 2D only.

We entered the name of the fi rst station and of the last station into the text boxes to define the balanced line. All stations between the first and the last station, which are connected with Connectors , form the balanced line. Each station has to have a predecessor and a successor and can only have a single predecessor and a single successor.

**Note**

You can only balance production lines that consist of objects of type Station and AssemblyStation . When an AssemblyStation is part of the balanced line, the Cycle only continues balancing, when the assembly process has been finished.

<!-- image -->

If you did not define any stations for the balanced line yet, you can drag an object of type Station or AssemblyStation onto the icon of the object Cycle and drop it there, Plant Simulation enters it as the first station of the balanced line.

We did this with the station called Drill , which is a modified Station .

Then drag another object onto it and drop it there. Plant Simulation enters it as the last station.

We did this with the AssemblyStation . We then changed our mind and decided to make the station called TestQuality the last station. To do so, we held down Shift , dragged it over the Cycle , and dropped it there.

**Note**

As each station within the balanced line can only have a single predecessor and a single successor, the Source named TableLegsIn , that feeds the table legs to the Assembly station in our example above, cannot be part of the balanced line.

To detect the difference between a balanced line and an unbalanced line, we copied the balanced line and pasted it below it. We then started the simulation and checked the tab Type Statistics of the Drain of the balanced and of the unbalanced line.

Back to Balance a Production Line

<!-- image -->

##### Convert the Production Line Model to a 3D Model

Here we show how to convert the model, that we originally created in 2D, to a 3D model. As we already converted the table assembly , we can use the adjustments that we made in that model. Compare Assemble Parts with the AssemblyStation and Open the Table Assembly in 3D . To do so, we opened the model My3DAssembly.spp .

- We save the MUs named TableLeg and TableTop as an object file each with the name TableLeg.psobj and TableTop.psobj , compare Save Object As . These files contain the simulation properties and the 3D graphic settings that we defined.

<!-- image -->

- We open the DataTables named TableLegs and TableTops , select Export Object File , and export them as an object file each with the names TableLegTable.psobj and TableTopTable.psobj . These files contain the attributes that set with which color the table legs and table tops are shown.

<!-- image -->

Then we open our 2D model MyBalancedLine.spp that we created in a previous version of Plant Simulation .

- We save it with a new name. We typed in My3DBalancedLine.spp .
- We select the Visualization &gt; 3D only in the Model Settings .

**Note**

If some objects, for example the DataTable , are not displayed in the 3D model, select this object in the Class Library , press F8 , and double-click the attribute CreateIn3D so that it shows true .

- To use the graphics of the current version of Plant Simulation , we hold down Shift , click Basis with the right mouse button in the Class Library , and select Revert all Objects to Standard Graphics .

Plant Simulation then runs the simulation with the default settings of the parts. As this is not what we want, we will:

- Import the simulation settings and the graphics of the table legs and the table tops
- Click the folder Models in the Class Library with the right mouse button and select Save/Load &gt; Load

Object . Select the file TableLeg.psobj which we exported above. Repeat this for the TableTop.psobj . Click OK in the dialog that opens.

<!-- image -->

Rename the original classes, for example to TableLegOriginal and to TableTopOriginal , and the imported classes to TableLeg and to TableTop . Once everything works as expected, we can delete the original classes.

The Class Library then looks like this.

<!-- image -->

When we run the simulation, we see that the table tops and the table legs are produced and assembled as expected. The colors of the table tops and the table legs are wrong though, as these are set in the production tables.

- Import the contents of the production tables of the table tops and the table legs

Open the production tables TableTops , TableLegs , TableTops1 , and TableLegs1 in the Frame TableAssembly .

Click Import File and select the respective file TableLegTable.psobj or TableTopTable.psobj , which we exported above.

<!-- image -->

Now the table tops and the table legs show the correct color. We finally adjust the positions of the objects and insert a Comment each showing Balanced Line and Non-Balanced Line .

<!-- image -->

Back to Balance a Production Line

