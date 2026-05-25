### Assembling Parts with the Assembly Station

#### Assemble Parts with the AssemblyStation

The AssemblyStation adds mounting parts to a main part, for example doors to a car body, or legs to a table top as in our example. It moves the mounting parts either to the main MU -according to the value you enter into the Assembly Table -or it deletes them.

You can insert the AssemblyStation into your simulation model from the folder MaterialFlow in the Class Library or from the toolbar Material Flow in the Toolbox .

<!-- image -->

In our examples we will:

- Assemble Kitchen Tables
- Always Fill-up the Main MU with Parts
- Assemble Parts Sequentially
- Assemble Kitchen Tables

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

Back to Modeling the Material Flow

#### Assemble Kitchen Tables

Assemble Kitchen Tables

In this basic sample model we demonstrate how to produce two different types of tables and show how to attach the table legs to the table tops.

The Source named TableTopsIn produces two brown table tops and two white table tops. The Source named TableLegsIn produces four table legs with different colors. The sources send the table tops and table legs on to the AssemblyStation which in turn attaches the respective legs to the matching table tops. It then sends the assembled tables on to shipping station, which we modeled with a Drain .

We will demonstrate how to:

- Create the Table Assembly in 2D
- Open the Table Assembly in 3D

Compare Change the Assembly Table in the Entrance Control

Back to Assemble Parts with the AssemblyStation

##### Create the Table Assembly in 2D

We originally created the simulation model in 2D. We inserted the objects so that they match the screenshot below.

<!-- image -->

We inserted and configured the Sources , which are to produce the parts, the table tops and table legs in our case:

- We selected the type of part which the Source named TableTopsIn is to produce. We selected the MU Selection &gt; Sequence Cyclical and then selected the name of the sequence table , which we inserted before, namely the DataTable named TableTops . Selecting the table automatically applied the correct format.

<!-- image -->

- We entered the required data into the sequence table .

We dragged the MU named TableTop , which we created and stored in the folder Models , to the cell MU and dropped it there.

As we want to create two brown table tops, we entered 2 as the Number . We then entered the name of the part, namely TableTop\_A , which also is the name of the icon of the brown table top into the Attributes subtable, which we named a1 .

<!-- image -->

We repeated this for our white table top.

- We selected the type of part which the source TableLegsIn is to produce. We selected the MU selection &gt; Sequence Cyclical and then selected the name of the sequence table , which we inserted before, namely the DataTable named TableLegs . Selecting the table automatically applied the correct format.
- We entered the required data into the sequence table .

<!-- image -->

We dragged the MU named TableLeg , which we created and stored in the folder Models , to the cell MU and dropped it there.

As we want to create two sets of legs for our brown table tops, we entered 8 as the Number . We then entered the name of the part, namely Leg\_A , which also is the name of the icon of the table leg into the Attributes subtable, which we named a1 .

<!-- image -->

We repeated this for the legs that go with our white table top.

We inserted and configured the AssemblyStation , which is going to attach the matching table legs to the table tops.

- As we want to attach the table legs to the table tops, we selected Assembly Table &gt; Predecessors .
- We then clicked Open and entered the number of the predecessor from which the legs arrive, 2 in our case, and the number of parts want to attach, 4 in our case.
- As the Assembly Mode we selected Attach MUs .
- As the part that the AssemblyStation is going to pass on is the finished table, we selected Main MU , which arrived from predecessor 1 .

<!-- image -->

When we start the simulation, we can watch how the AssemblyStation attaches the four blue legs to the brown table top, passes the assembled table on to the shipping station, and repeats this once. It then attaches four orange legs to the white table top, passes the assembled table on to the shipping station, and does the same again, and then repeats the sequence, namely two brown table tops, followed by two white table tops, and so on.

<!-- image -->

**Note**

If the assembly process does not work as expected, check the sequence in which you connected its predecessors with the AssemblyStation . Also make sure that the Main MU arrives from the correct predecessor .

**Back to Assemble Kitchen Tables**

Open the Table Assembly in 3D

As we originally created the model in 2D, we now open it in 3D by clicking Open Frame in 2D/3D on the Home ribbon tab.

In 3D we have to adapt the dimensions of the table legs and of the table top to make them look somehow realistic and to adapt it to the 3D standard graphic of our AssemblyStation .

- For the table legs we entered these settings for the MU Size for the class of the TableLeg .
- For the table tops we entered these settings for the MU Size for the class of the TableTop .

<!-- image -->

<!-- image -->

- The result with the adjusted dimensions of the standard graphics of the part and the pallet look like this:

<!-- image -->

As our tables do not look like tables, we create graphics for the varicolored table legs and table tops in 3D.

Proceed as follows to create the blue and orange table legs:

- Right-click the object TableLeg in the Class Library and select Open in 3D .

- Press the spacebar and change to the tab Graphics in the dialog Edit 3D Properties . Add a graphic group with the name Leg\_A and Leg\_B each.
- Delete the graphic named default . Change to the Edit tab and click Cylinder under Insert Shape . Select the graphic group for which you want to create the graphic. We selected these settings for Leg\_A :
- This inserts the Cylinder at the origin of the scene. It does not have the right color though.
- Click the Cylinder and press the spacebar. Change to the Material tab, select Material Active , and select a color. As our Leg\_A is blue in 2D, we select a similar tone.

<!-- image -->

<!-- image -->

<!-- image -->

- Repeat these steps for Leg\_B and select Orange as the color.

Proceed as follows to create the brown and the white table tops:

- Right-click the object TableTop in the Class Library and select Open in 3D .
- Press the spacebar and change to the tab Graphics in the dialog Edit 3D Properties . Add a graphic group with the name TableTop\_A and TableTop\_B each.

<!-- image -->

- Delete the graphic named default . Change to the Edit tab and click Cuboid under Insert Shape . Select the graphic group for which you want to create the graphic. We selected these settings for TableTop\_A :
- This inserts the fl at cuboid at the origin of the scene. It does not have the right color yet.
- Click the Cuboid and press the spacebar. Change to the Material tab, select Material Active , and select a color. As our TableTop\_A is brown in 2D, we select a similar tone.
- Repeat these steps for TableTop\_B and select a non all white tone.

<!-- image -->

<!-- image -->

When we run the simulation, we see that the AssemblyStation assembles the varicolored tables correctly but does not show them in the correct colors.

2D shows the table legs and table tops according to the attribute CurrIcon . 3D shows them according to the graphic group names that we entered. To accomplish this, we create a user-defined attribute and an observer for the user-defined attribute in the class of the object.

- In the class of the table leg we created an observer for the user-defined attribute named PictureName3D , which detects when a table leg with another name arrives, and then displays the correct graphic.

<!-- image -->

- We entered this source code into the method of the observer OnPictureName3DChanged :
- We then enter the name of the user-defined attribute named PictureName3D and the name of the respective graphic group into the two sub-tables named a1 and a2 of the DataTable named TableLegs .
- In the class of the table top we created an observer for the user-defined attribute PictureName3DTableTop , which detects when a table top with another name arrives, and then displays the correct graphic.

```simtalk
// param attribute: string, oldValue: string, newValue: string // param attribut: string, oldValue: string param newValue: string self.~._3D.VisibleGraphicGroups := [newValue]
```

<!-- image -->

<!-- image -->

- We entered this source code into the method of the observer OnPictureName3DTableTopChanged :
- We then enter the name of the user-defined attribute named PictureName3DTableTop and the name of the respective graphic group into the two sub-tables named a1 and a2 of the DataTable named TableTops .

```simtalk
// param Attribute: string, oldValue: string, newValue: string // param Attribut: string, oldValue: string param newValue: string self.~._3D.VisibleGraphicGroups := [newValue]
```

When we now run the simulation, we see that two tables each with a brown and two tables each with a bright-colored table top are produced. When zooming the AssemblyStation we see that the table top is not positioned flat on the assembly area, but with an offset to the top. In addition the left legs jut into the assembly boxes at the back of the AssemblyStation .

<!-- image -->

**This is easy to correct:**

- Click the AssemblyStation and press the spacebar. Change to the tab MU Animation .
- Show the path named default .

<!-- image -->

<!-- image -->

- Click Edit and change the values as shown in the figure so that the table top lies flat on the assembly table and that the legs do not touch the assembly boxes any longer.

<!-- image -->

Finally we arrange the objects more realistically and run the simulation. The finished simulation model looks like this in 3D:

Back to Assemble Kitchen Tables

<!-- image -->

#### Always Fill-up Main MU with Parts

Always Fill-up the Main MU with Parts

In this basic sample model we demonstrate how to always fill up the main MU , here a pallet, with as many parts as it can hold. The part type that is loaded onto the pallet does not matter.

We will demonstrate how to:

- Configure the Material Flow to Fill-up Main MU
- Configure the Assembly Table to Fill-up the Main MU

Our finished model looks like this:

<!-- image -->

**Back to Assemble Parts with the AssemblyStation**

##### Configure the Material Flow to Fill-up Main MU

Insert the material flow objects, so that they match the screenshot below. Make sure that all objects are connected. Then configure the material flow objects.

<!-- image -->

- Our first step in configuring the material flow to fill-up the main mu is to duplicate the Part twice. We named the duplicated parts PartRed and PartBlue and assigned them the respective colors. We also duplicated the Container .

<!-- image -->

- The Source named SourceMainParts produces two types of Containers , as specified in the ProductsTable , in a sequential sequence.
- The SourceMainParts sends the pallets along a Conveyor to the AssemblyStation .
- The Source named SourceParts produces two types of Parts with different colors, as specified in the PartsTable , in a cyclical sequence.

<!-- image -->

<!-- image -->

- The SourceParts sends the PartBlue on to the ParallelStation named BlueParts . We entered the settings below. We cleared Start Processing When Full to fill up the pallet with different part types. We also entered a processing time of 10 seconds on the Tab Times .
- The SourceParts sends the PartRed on to the ParallelStation named RedParts . We entered the settings below. We cleared Start Processing When Full to fill up the pallet with different part types. We also entered a processing time of 10 seconds on the Tab Times .

<!-- image -->

<!-- image -->

- The ParallelStations send the processed parts on to the AssemblyStation which loads them onto the pallets.

Back to Always Fill-up the Main MU with Parts

##### Configure the Assembly Table to Fill-up the Main MU

To make our AssemblyStation load the processed blue and red parts onto the pallets and always fill up the pallets to their capacity, namely four parts, we selected Assembly table &gt; Fill-up Main MU . We did not change any other settings.

Although Fill-up Main MU is listed as an option of the Assembly Table , the AssemblyStation does not use an Assembly Table at all, but accepts parts from any of its predecessors until the capacity of the main MU , our Container , is reached.

<!-- image -->

When we run the simulation, we see that the AssemblyStation always fills up the pallets, i.e., it places four parts on each and every pallet. Some pallets are filled up with red parts only, some with blue parts only, and some with a mix of both part types just as their processing on the ParallelStations is finished.

<!-- image -->

The AssemblyStation then sends the loaded pallets on a Conveyor on to the Drain .

Using an Assembly Table with the Setting MU Types

Let's compare the setting Fill-up Main MU with the setting Assembly Table &gt; MU Types in the Example model &gt; AssemblyStation &gt; Change Assembly List .

In this model the parts are moved on according to the settings specified in the Assembly Table and to the Entrance Control named setBOM .

<!-- image -->

When we run the simulation, we see, that the AssemblyStation loads the processed parts in a mixed sequence depending on the time their processing is finished onto the pallets. It never fills them up to their capacity, before sending them on to the Drain though.

Back to Always Fill-up the Main MU with Parts

<!-- image -->

#### Assemble Parts Sequentially

Assemble Parts Sequentially

In this basic sample model we demonstrate how to assemble parts sequentially with the AssemblyStation .

To make our AssemblyStation assemble arriving parts sequentially, we selected Assembly Table &gt; Depends on Main MU . We did not change any other settings.

We will demonstrate how to:

- Configure the Material Flow to Assemble Parts Sequentially
- Configure the Assembly Table to Assemble Parts Sequentially

Our finished model looks like this:

Back to Assemble Parts with the AssemblyStation

<!-- image -->

##### Configure the Material Flow to Assemble Parts Sequentially

Insert the material flow objects, so that they match the screenshot below. Make sure that all objects are connected and configure the material flow objects.

The finished simulation model looks like this:

<!-- image -->

- The SourceBoxA produces boxes of type BoxA and the SourceBoxB produces boxes of type BoxB . Both are located in the folder UserObjects in the Class Library . We did not change any other settings.

<!-- image -->

<!-- image -->

<!-- image -->

- The Conveyor transporting the two types of boxes to the AssemblyStation is 4 meters long and uses the default settings.

<!-- image -->

- We used the default settings for the Conveyor transporting the assembled parts, the two types of parts stacked in the two types of boxes, from the AssemblyStation to the Drain .
- The SorucePartA produces parts of type PartA and the SourcePartB produces parts of type PartB . We did not change any other settings.

<!-- image -->

- For the Conveyor2 transporting parts of type PartA to the AssemblyStation we typed in a MU Distance of 2 meters and we selected Enforce MU Distance . This ensures that the Conveyors always keep the distance of 2 meters between the parts.

For the Conveyor3 transporting parts of type PartB to the AssemblyStation we use the same settings.

<!-- image -->

Go to Configure the Assembly Table to Assemble Parts Sequentially

Back to Assemble Parts Sequentially

##### Configure the Assembly Table to Assemble Parts Sequentially

We configured the sequential assembly of the arriving parts in the Assembly Table of the AssemblyStation by typing in the Assembly Time and the Sequence Number .

- We selected Depends on Main MU and clicked Open to open the Assembly Table
- We use these settings to assemble the parts:
- We place an Amount of 1 PartA into BoxA . This assembly process takes an Assembly Time of 5 minutes . The Sequence Number 1 determines that PartA is put into the box before PartB .
- We place an Amount of 2 PartB into BoxA . This assembly process takes an Assembly Time of 10 minutes . The Sequence Number 2 determines that PartB is put into the box after PartA .
- We place an Amount of 1 PartB into BoxB . This assembly process takes an Assembly Time of 3 minutes . The Sequence Number 1 determines that PartB is put into the box before PartA .
- We place an Amount of 2 PartA into BoxB . This assembly process takes an Assembly Time of 6 minutes . The Sequence Number 2 determines that PartA is put into the box after ParB .

<!-- image -->

<!-- image -->

Run the simulation and watch how the AssemblyStation places the specified parts into the specified boxes in the sequence which we defined.

To follow the assembly process step-by-step, open the Event Debugger .

Back to Configure the Material Flow to Assemble Parts Sequentially

Back to Assemble Parts Sequentially

#### Assemble Parts Sequentially with the Worker

Assemble Parts Sequentially with the Worker

In this basic sample model we demonstrate how to make a Worker assemble parts sequentially with the AssemblyStation .

To make our Worker carry the parts from the Store to the AssemblyStation and place them on a pallet in the defined sequence, we selected Assembly Table &gt; Depends on Main MU . We did not change any other settings.

We will demonstrate how to:

- Configure the AssemblyStation to Which the Worker Delivers Parts
- Configure the Store Which Provides the Parts
- Watch how the AssemblyStation Assembles the Parts Delivered by the Worker

Our finished model looks like this:

<!-- image -->

Back to Assemble Parts with the AssemblyStation

##### Configure the AssemblyStation to Which the Worker Delivers Parts

Insert the material flow objects, so that they match the screenshot below. Make sure that all objects are connected. Then configure the material flow objects.

<!-- image -->

- The SourceContainer produces 4 pallets onto which the Worker places the parts he picked up at the Store . We selected the settings below.

<!-- image -->

- The Conveyor transports the pallets to the AssemblyStation . As we want the pallets to keep a distance between them, we typed in 0.5 as the MU Distance and selected Enforce MU Distance .
- The Worker picks the parts up at the Workplace attached to the Store , steps onto the Workplace attached to the AssemblyStation , and places the parts on the pallet.

<!-- image -->

- We selected the settings below for the AssemblyStation .

We selected Assembly Table &gt; Depends on Main MU and clicked Open . We typed in the actual assembly sequence into the column Sequence Number .

In our case the Worker first deposits a red part, followed by another red part, followed by a green part, and finally followed by a yellow part.

<!-- image -->

We use the Workplace attached to the AssemblyStation with its default settings.

<!-- image -->

- We use both the Conveyor transporting the parts to the Drain and the Drain itself with their default settings.

Go to Configure the Store Which Provides the Parts

Go to Watch how the AssemblyStation Assembles the Parts Delivered by the Worker

Back to Assemble Parts Sequentially with the Worker

##### Configure the Store Which Provides the Parts

We configured the Store , which provides the parts to be placed onto pallets like this:

- We typed in 3 as the X Dimension , 4 as the Y Dimension , and 1 as the Z Dimension .
- We activated the Transport Importer and we want the Worker to wait for a free target .

<!-- image -->

<!-- image -->

- We configured the Workplace attached to the Store .

<!-- image -->

Back to Configure the AssemblyStation to Which the Worker Delivers Parts

Go to Watch how the AssemblyStation Assembles the Parts Delivered by the Worker

Back to Assemble Parts Sequentially with the Worker

##### Watch how the AssemblyStation Assembles the Parts Delivered by the Worker

Run the simulation and watch how the AssemblyStation sequentially assembles the parts, which the Worker delivers.

- First, the Sources produce four red, green, and yellow parts
- Then, the Worker steps onto the Workplace attached to the Store picks up a red part, and turns around. He then walks to the Workplace attached to the AssemblyStation and places the red part onto the pallet. He then walks back to the Store and picks up the parts in the sequence, which we entered into the Assembly Table and places the parts onto the pallet.

<!-- image -->

<!-- image -->

<!-- image -->

To follow the assembly process step-by-step, open the Event Debugger .

Back to Configure the AssemblyStation to Which the Worker Delivers Parts

Back to Configure the AssemblyStation to Which the Worker Delivers Parts

Back to Assemble Parts Sequentially with the Worker

#### Set How Workers Deliver Parts

Set How Workers Deliver Mounting Parts

You can set in the AssemblyStation how Workers will deliver the parts that are to be assembled:

- To make several Workers deliver a part in parallel each, leave the check box Workers Sequentially Deliver MUs to Assemble cleared.
- To make a single Worker deliver the parts sequentially one after the other, select Workers Sequentially Deliver MUs to Assemble .

<!-- image -->

In our examples we will:

- Make Several Workers Deliver Parts in Parallel
- Make a Single Worker Deliver Several Parts at Once

Back to Assemble Parts with the AssemblyStation

##### Make Several Workers Deliver Parts in Parallel

In this simple model we make several Workers deliver the mounting parts to the AssemblyStation in parallel.

Our finished model looks like this.

<!-- image -->

Several Workers Deliver a Single Part Each

We configured the objects as follows to make several Workers deliver a single part each:

- The SourcePallets produces the pallets , the main parts , that our WorkerMainParts carries to the AssemblyStation .

The SourceParts produces the mounting parts that our WorkerOtherParts carries to the AssemblyStation which loads them onto the pallet .

We use both with their default settings.

- For the AssemblyStation we selected these settings:

<!-- image -->

- We attached a Workplace each to the SourceParts , to the SourcePallets , and to the AssemblyStation where the four Workers of class WorkerOtherParts pick up the parts and place them respectively.
- For the WorkerPool , which creates our Workers , we selected these settings:
- For our WorkerOtherParts we selected these settings.

<!-- image -->

<!-- image -->

When we run the simulation, we see that our WorkerMainPart carries the pallet , the main part , to the AssemblyStation and places it there.

<!-- image -->

Meanwhile the SourceParts produces the parts. Four Workers named WorkerOtherParts walk one after the other from the WorkerPool to the SourceParts , step onto the Workplace , pick a part up, carry it to the Workplace attached to the AssemblyStation and place it onto the pallet located on the AssemblyStation .

<!-- image -->

A Single Worker Delivers Part After Part

Let's now select Workers sequentially deliver MUs to assemble and watch what happens.

<!-- image -->

The Worker named WorkerOtherParts:1 delivers four parts, one after the other, to the AssemblyStation , and returns to the WorkerPool once he's done.

Back to Set How Workers Deliver Mounting Parts

<!-- image -->

##### Make a Single Worker Deliver Several Parts at Once

In this simple model we make a single Worker deliver as many mounting parts as he can carry to the AssemblyStation .

Our finished model looks like this.

<!-- image -->

We configured the objects as follows:

- The SourcePallets produces the pallets , the main parts , that are automatically moved onto the AssemblyStation .

The SourceParts produces the mounting parts that our Worker carries to the AssemblyStation . We use both with their default settings.

- For the AssemblyStation we selected these settings:

<!-- image -->

- We also attached a Workplace each to the SourceParts and to the AssemblyStation where the Worker picks up the parts and places them respectively.
- For the WorkerPool , which creates our Workers , we selected these settings:
- For our Worker we increased the X-Dimension and the Y-Dimension to 2 each to allow him to carry four parts.

<!-- image -->

<!-- image -->

When we run the simulation, we see that the produced pallet is moved along the Connector to the AssemblyStation .

Meanwhile the SourceParts produces the parts. Our Worker walks to the SourceParts , steps onto the Workplace , waits until four parts are produced, picks them up one by one, carries them to the Workplace attached to the AssemblyStation , and places them onto the AssemblyStation one by one.

Back to Set How Workers Deliver Mounting Parts

<!-- image -->

