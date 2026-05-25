### Source

Use the Source for producing the parts that move through your model. It usually represents the receiving department of your plant or the main machine producing the parts.

Icon

<!-- image -->

**Description**

The Source has a capacity of one and no processing time. The Source produces the same or different types of MUs one after the other or in a mixed sequence. It might, for example, represent the receiving department of your plant that introduces parts produced at another location into the plant. Or it can be a machine, which produces the parts that the other stations process.

<!-- image -->

You can set a procedure to determine the times at which it creates the parts as well as a procedure to determine the types of MUs to be produced. As an active material flow object, the Source attempts to move the MUs it produced to the objects to which it is connected. You can also define how the Source proceeds when it cannot move a MU to its succeeding object, by selecting or clearing Blocking .

You will use the Source to produce the parts and workpieces that move through your plant and which are processed by the different stations.

You will use the Drain to remove these parts from the factory to model, for example, the shipping department of your facility.

To show a tooltip with information about the Source , hover with the mouse over it.

<!-- image -->

To change the length of the graphic and the anchor points of the Source , click Show Manipulators on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the Source to your simulation model, click Manage Class Library &gt; Basic Objects &gt; MaterialFlow &gt; Source on the Home ribbon tab.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

**See also**

Produce Parts with the Source

Check How Many Parts Were Introduced into the Plant

##### Dialog Box of the Source

Dialog Box of the Source

Double-click the icon of the Source to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.

<!-- image -->

- Select the object in the model and press the spacebar .

Tab Attributes

Tab Attributes

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

The tab Attributes provides the settings listed in the table of contents to the left.

###### Operating Mode [check box]

Operating Mode [check box]

The Operating Mode sets how the Source proceeds if it cannot create the MUs at the Time of Creation you entered.

<!-- image -->

- If you select Blocking , the Source remembers the time at which it was supposed to produce the next MU . It then produces the following MUs at the next possible point in time, i.e., when the MU that was blocked by the successor, was moved on. The Source stops creating parts when the simulation time has reached the Stop time.
- If you clear Blocking , the Source creates another MU exclusively at the time of creation you entered.

**Note**

When the Source is temporarily not operational because it is failed, paused or blocked, the times of creation may shift, if you select Blocking . Then, the settings for the times of creation cannot be realized.

SimTalk

Blocking [SimTalk]

See also

Time of Creation [Source]

Time of Creation

Time of Creation [Source]

Select the point in time at which and how the Source produces MUs from the drop-down list.

<!-- image -->

- Interval Adjustable : The Source produces the first MU at the Start time. The Time of Creation designates the Interval between two creation events. It produces the last MU at the Stop time.

If you do not type in a Stop time for this setting, Plant Simulation produces the amount of parts you entered at the most. The default value -1 designates an unlimited number of parts to be produced.

Otherwise, the Source produces parts until the Stop time is reached and ignores the Amount of parts you entered.

**Note**

If you select a constant time all MUs are produced at this point in time.

- Number Adjustable : The Source produces the number of MUs , which you type in as the Amount . If you activate the check box Generate as Batch , the Amount does not designate the number of parts , but the number of batches that the Source produces. The times at which the MUs are created are distributed according to the distribution you select for the Interval .

If you select a constant time all MUs are produced at this point in time.

- Delivery Table : The Source produces MUs according to the Delivery Time , the Class , the Number , the Name , and the Attribute which you type into the Delivery Table .

**Note**

If you assign a new Delivery Table to the Source during the simulation, it also produces parts which were to be produced in the past according to the new delivery table.

- Trigger : The Source produces MUs according to the values that a set of Trigger objects control.

**Note**

Depending on the setting you select, the attribute Path (dialog item MU or Table ) either sets the path to the MU class, the delivery list, the sequence table, the frequency table, or the percentage table.

<!-- image -->

If the Source cannot produce the MUs at the Time of Creation , the Operating Mode determines how it proceeds:

- If you select Blocking , the Source remembers the time at which it was supposed to produce the next MU . It then produces the following MUs at the next possible point in time, i.e., when the MU that blocked the successor was moved on.
- If you clear Blocking , the Source creates another MU exclusively at the time of creation you typed in.

**Note**

When the Source is temporarily not operational because it is failed, paused or blocked, the Time of Creation may shift, if you select Blocking . Then, the settings for the times of creation cannot be realized.

SimTalk

TimeOfGeneration [SimTalk]

**Interval Adjustable [time of creation]**

For the setting Interval Adjustable the three settings Interval , Start , and Stop determine the points in time at which the Source produces the parts.

- The Start time designates the point in time at which the Source produces the first MU . It produces additional MUs after the time, which you enter as the Interval , has elapsed.
- The Interval designates the time span between two events at which the Source produces MUs .
- The Stop time designates the point in time at which the Source produces the last MU . If you type in 0 as the Stop time, the Source produces MUs according to the Amount you entered.

You can also select one of the Probability Distributions for the Interval , for the Start time, and for the Stop time.

<!-- image -->

**Amount**

Type in the amount of MUs which the Source produces.

**Note**

The setting Amount is only available for the Time of Creation &gt; Number Adjustable and Interval Adjustable .

If you do not type in a Stop time for the setting Interval Adjustable , Plant Simulation produces the amount of parts you typed in at the most. The default value of -1 designates an unlimited number of parts to be produced. Otherwise, the Source produces parts until the Stop time is reached and ignores the Amount of parts you entered.

For the setting Interval Adjustable the Source might create more parts than the Amount you typed in, if the check box Generate as Batch is activated. This is because the batches are always produced in their entirety, not in part only.

For the setting Time of Creation &gt; Number Adjustable the value does not designate the amount of MUs , but the amount of batches/lots which the Source produces if you activated Generate as Batch .

SimTalk

Number [SimTalk]

TimeOfGeneration [SimTalk]

See also

Define

Interval [Source]

Start [Source]

Stop [Source]

Interval [SimTalk] - Source

Start [SimTalk] - Source

Stop [SimTalk] - Source

**Number Adjustable [time of creation]**

Produces the number of MUs , which you type into the text box Amount for the setting Number Adjustable of the Source .

If you activate the check box Generate as Batch , the Amount does not designate the number of parts , but the number of batches that the Source produces.

<!-- image -->

You can also select one of the Probability Distributions from the drop-down list Creation Times and type the values that the selected distribution requires into the text box. The distribution determines the point in time at which the Source creates the MUs .

The Source produces the number of MUs at the different times which the random number generator generated at the beginning of the simulation. The determined times are contained within the bounds if you type in a lower bound and an upper bound.

If you select a Constant time, the Source creates the number of MUs all at one point in time.

<!-- image -->

**Note**

For the setting Number Adjustable you cannot select the MU Selection &gt; Sequence .

SimTalk

Number [SimTalk]

**TimeOfGeneration [SimTalk]**

See also

Produce the Number of Parts You Need

**Delivery Table [time of creation]**

Produces the MUs according to the settings which you typed into the Delivery Table for the setting Delivery Table of the Source .

<!-- image -->

Type the path of the Delivery Table into the text box next to Table .

<!-- image -->

Or you can click and select a table in the dialog Select Object .

You can also add information about the name and number of the produced parts as well as values for their attributes to the Delivery Table .

The Delivery Table has five columns with the data types time , object , integer , string , and table . Instead of the data type time you can also use the data types date , dateTime , or real . Each row of the Delivery Table defines one order for producing MUs :

<!-- image -->

- Type the time at which the Source produces the MUs into the column Delivery Time .

**Note**

Plant Simulation processes the Delivery Table row by row. For this reason the time should increase from row to row. If Plant Simulation processes a row in which the time is located in the past, it creates the part immediately. This may not be what you would expect to happen.

- Type the class of the MU into the column MU . You can also drag the MU class into the respective cell and drop it there.
- Type the number of MUs to be produced into the column Number .

**Note**

If you enter 0 as Number into a row, Plant Simulation does take the specified interval for the next creating cycle into account. This means that Plant Simulation does not skip this row, but does not produce a part during this cycle.

- Enter a name for the MUs to be produced into the column Name .

**Note**

You have to type data in the columns Delivery Time and MU . If you do not type in a Number , Plant Simulation produces a single MU . If you do not type in a Name , the produced MUs inherit the name of their class.

- Type in the name of the table attributes and user-defined attributes that the Source sets when it produces the MUs into the column Attributes .

Type the name of the attribute in column 1 of the attribute table. If an attribute with that name does not exist, Plant Simulation creates it. Set the data type of the attribute with the data type of an additional column in the attributes table.

**Note**

Plant Simulation assigns the data type of the column containing the value of the attribute to the data type of the attribute. The respective entry is the value of the generated attribute.

If the data type of the column is table/list/stack/queue , Plant Simulation does not copy the sublists of the attribute table, but creates a reference to this list. The newly created user-defined attribute then accesses this list, i.e., when you change one of the two lists, the contents of the other list is changed as well.

**Note**

The Source does not produce parts whose time of creation is in the future when you assign a Delivery Table during the simulation.

Instead of using a DataTable , which you inserted into a Frame , you can also use a user-defined attribute of data type table of the Source as the Delivery Table .

SimTalk

Path [SimTalk] - Source

See also

creationTable [SimTalk] - Source

TimeOfGeneration [SimTalk]

Produce Parts According to a Delivery Table

**Trigger [time of creation]**

Trigger [time of creation]

Produces MUs according to the values that one or several Trigger objects control for the setting Trigger of the Source .

<!-- image -->

Click Trigger and type the name(s) of the Trigger object(s) into the list that opens. Each Trigger in this list sends orders as strings to produce MUs to the Source .

Open the Trigger , click the tab Values , make sure that the Trigger Type &gt; Input is selected and click Values .

Type the orders into the cells on the tab Contents :

- Type the Point in Time at which the Source creates MUs into the cells on the left-hand side.
- Type the Value of the order into the cells on the right-hand side. An order is a string with this format: Amount of MUs to be produced, type of the MU to be produced, type of the distribution, and the parameters of the distribution, ( &lt;num&gt;, &lt;mu\_Type&gt;,&lt;distributionType[, distribution parameters]&gt; in SimTalk ).

You always have to type in the amount of MUs to be produced, the type of the MU to be produced, and the distribution type. When you type in Const as the distribution type, the Source produces the MUs at the point in time which you type into the respective cell in the column Point in Time . If you would like it to produce the MUs with an offset to the time you entered there, type in number of seconds after which it produces them after the constant time ( Const ) you specified. For all other distribution types you have to enter the respective distribution parameters after the distribution type.

If you select a distribution, its values set the time offset to the time you entered into the respective cell in the column Point in Time . The offset you type in has to be a positive number.

<!-- image -->

In the figure above the creation time for each MU is computed as 1:00.000 + z\_negexp(…, 20, 0, 60) and 5:00.000+z\_normal(…, 20, 5) respectively.

The random stream used is the internal stream of the Source .

If you type in the Source as a resource into the ShiftCalendar , Plant Simulation interrupts the production sequence during the weekends:

- If you select the Operating Mode &gt; Blocking , the Source does not produce MUs at all during the weekends.
- If you clear Blocking , the Source produces and moves the MUs , as soon as its shift starts again.

You might, for example, use a Source that is controlled by a Trigger , if you want to set a time of creation, such as with a delivery table, and you would like to periodically repeat using the values in this list, for example when you select MU Selection &gt; Sequence Cyclical .

**SimTalk**

Trigger [SimTalk]

**Trigger [time of creation]**

See also Trigger [object] Produce Parts Using a Trigger Object creationTable [SimTalk] - Source TimeOfGeneration [SimTalk]

###### Interval [Source]

For Time of Creation &gt; Interval Adjustable the interval is the time span that elapses between two events at which the Source produces parts. The Source creates an infinite number of MUs .

<!-- image -->

Select a distribution from the drop-down list, and type the values, which that distribution requires, into the text box. Plant Simulation shows these values along the upper border of the tab.

You can also select Const and type in a constant time.

SimTalk

Interval [SimTalk] - Source

See also

Interval Adjustable [time of creation]

Start [SimTalk] - Source

Stop [SimTalk] - Source

Times and Distributions

Probability Distributions

Empirical Distributions

User-defined Distributions

**Start [Source]**

###### Start [Source]

The Start time designates the point in time at which the Source produces the first MU .

<!-- image -->

Select a distribution from the drop-down list, and type the values, which that distribution requires, into the text box. Plant Simulation shows these values along the upper border of the tab. You can also type in a constant time ( Const ).

SimTalk

Start [SimTalk] - Source

See also

Interval [SimTalk] - Source

Stop [SimTalk] - Source

Times and Distributions

Probability Distributions

Empirical Distributions

User-defined Distributions

###### Stop [Source]

The Stop time designates the time at which the Source stops producing MUs .

<!-- image -->

Select a distribution from the drop-down list, and type the values, which that distribution requires, into the text box. Plant Simulation shows these values along the upper border of the tab.

You can also type in a constant time ( Const ).

SimTalk

Stop [SimTalk] - Source [SimTalk]

See also

Interval [SimTalk] - Source

Start [SimTalk] - Source

Times and Distributions

Probability Distributions

Empirical Distributions

User-defined Distributions

MU Selection

MU selection [drop-down list]

Select which type of MUs and how the Source produces MUs .

- Constant : It produces one type of MU only. Type its path into the text box MU .

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

- Sequence Cyclical : It produces the MUs in a fixed sequence, which you type into a table. As soon as the Source has processed the sequence, it repeats the production sequence periodically.

- Sequence : It produces MUs according to the sequence table, whose name you typed into the text box next to Table . As opposed to Sequence Cyclical , Sequence processes the sequence only once, not repeatedly.

- Random : It produces MUs in random frequencies according to the values which you typed into the frequency table.

- Percentage : It produces MUs in percentages according to the values which you typed into the percentage table.

- Order Controlled : It only produces MUs if they are ordered by a Store with activated setting Supermarket or with the method orderParts .

**Note**

Depending on the Time of Creation you select, the dialog item MU or Table (attribute Path ) either sets the path to the MU class, the delivery list, the sequence table, the frequency table, or the percentage table.

**Note**

To use a copy of the DataTable instead of a reference to the DataTable , assign the name .unshare to the subtable.

SimTalk

MUSelection [SimTalk]

Path [SimTalk] - Source

unshare [SimTalk]

See also Store as Supermarket Configuration getCurrentOrderTableRow [SimTalk] Video on YouTube

[https://youtu.be/BvHLQCIjGIA?si=Jy0O3wvXpSNFltdg&amp;t=100](https://youtu.be/BvHLQCIjGIA?si=Jy0O3wvXpSNFltdg&t=100)

**Constant [MU selection]**

**Constant [MU selection]**

Produces one type of MU for the setting MU Selection &gt; Constant .

Type the path to this type of MU into the text box next to MU .

<!-- image -->

Or you can click and select a MU class, Part , Container or Transporter , in the dialog Select Object .

Or you can select the MU in the Toolbox or the Class Library , drag it to the text box and drop it there.

SimTalk

MUSelection [SimTalk]

Path [SimTalk] - Source

See also

Produce a Single Part Type Only

**Sequence Cyclical [MU selection]**

Produces parts according to the sequence table whose path you enter for the setting MU Selection &gt; Sequence Cyclical .

Or you can click and select the name of the table in the dialog Select Object . Plant Simulation automatically formats the table.

Or you can select the MU in the Toolbox or the Class Library , drag it to the text box and drop it there.

<!-- image -->

**Note**

For the MUs that are to be produced, you can also preallocate user-defined attributes . If the attribute has the data type table , the MU gets a reference to the table defined in the Source . A reference saves memory and increases performance. In some cases you might need a copy of the table though. You can enforce this by assigning the name .unshare to the subtable, compare unshare .

To make the Source produce the number of MUs , which you typed into the cell Number of the Table , in a single lot, select Generate as Batch .

If you select Number Adjustable as the Time of Creation , the Amount does not designate the number of parts , but the number of batches . Then the Source produces the entire set of parts all at once at the given start time and attempts to move all of the parts on to the next object in a single lot.

To make the Source produce the MUs as a sequence of individual parts one after the other, clear the check box.

Once the Source has processed the entire sequence, it starts processing the information in the table again, starting at the beginning of the sequence.

<!-- image -->

SimTalk

MUSelection [SimTalk]

<!-- image -->

Sequence Cyclical [MU selection]

Path [SimTalk] - Source

GenerateAsBatch [SimTalk]

getCurrentOrderTableRow [SimTalk]

unshare [SimTalk]

See also

Produce Parts in a Fixed Sequence Over and Over Again

**Sequence [MU selection]**

Produces MUs according to the values which you typed into the sequence table, whose name you typed into the text box next to Table for the setting MU Selection &gt; Sequence .

<!-- image -->

Or you can click and select the name of the table in the dialog Select Object . Plant Simulation automatically formats the table.

Or you can select the MU in the Toolbox or the Class Library , drag it to the text box and drop it there.

**Note**

As opposed to the setting Sequence Cyclical , the setting Sequence processes the sequence only once, not repeatedly.

The setting Sequence is not available if you set Time of Generation to Number Adjustable .

**Note**

For the MUs to be produced you can also preallocate user-defined attributes . If the attribute has the data type table , the MU gets a reference to the table defined in the Source . A reference saves memory and increases performance. In some cases you might need a copy of the table though. You can enforce this by assigning the name .unshare to the subtable, compare unshare .

To make the Source produce the number of MUs , which you typed into the cell Number of the Table in a single lot, select Generate as Batch . Then the Source produces the entire set of parts all at once at the given start time and attempts to move all of the parts on to the next object in a single lot.

To make the Source produce the MUs as a sequence of individual MUs , clear the check box.

<!-- image -->

SimTalk MUSelection [SimTalk] Path [SimTalk] - Source GenerateAsBatch [SimTalk] getCurrentOrderTableRow [SimTalk] unshare [SimTalk] See also Produce Parts in a Fixed Sequence One Time Only

**Random [MU selection]**

Produces MUs according to the values which you type into the frequency table for the setting MU Selection &gt; Random .

Type the path to this table into the text box next to Table .

<!-- image -->

Or you can click and select the name of the table in the dialog Select Object . Plant Simulation automatically formats the table.

**Note**

For the MUs to be produced you can also preallocate user-defined attributes . If the attribute has the data type table , the MU gets a reference to the table defined in the Source . A reference saves memory and increases performance. In some cases you might need a copy of the table though. You can enforce this by assigning the name .unshare to the subtable, compare unshare .

Define a frequency number for each type of MU in the frequency table. It has five columns with the data types object, real, integer, string , and table . Each row in the frequency table designates a production order.

- Type the MU class into the column MU .
- Type the frequency of the respective production order into the column Frequency .
- Type the number of MUs to be produced into the column Number .

You can, but you do not have to, type a Name and Attributes into the table.

- Type the name of MUs to be produced into the column Name .
- Type the name of the attribute subtable of the produced MUs into the column Attributes .

<!-- image -->

<!-- image -->

To make the Source produce the number of MUs , which you typed into the cell Number of the Table in a single lot, select Generate as Batch .

If you select Number Adjustable as the time of creation , the amount does not designate the number of parts , but the number of batches that the Source produces. Then the Source produces the entire set of parts all at once at the given start time and attempts to move all of the parts on to the next object in a single lot.

To make the Source produce the MUs as a sequence of individual MUs , clear the check box.

To check which part types were produced at which point in time, activate the check box Creation Table on the tab Statistics and then open the table.

SimTalk

MUSelection [SimTalk]

Path [SimTalk] - Source

GenerateAsBatch [SimTalk]

getCurrentOrderTableRow [SimTalk]

unshare [SimTalk]

See also

Produce Parts With a Random Frequency Entered into a Data Table

**Percentage [MU selection]**

Produces MUs according to the values which you typed into the percentage table for the setting MU Selection &gt; Percentage .

Type the path to this table into the text box next to Table .

<!-- image -->

Or you can click and select the name of the table in the dialog Select Object . Plant Simulation automatically formats the table.

**Note**

For the MUs to be produced you can also pre-allocate user-defined attributes . If the attribute has the data type table , the MU gets a reference to the table defined in the Source . A reference saves memory and increases performance. In some cases you might need a copy of the table though. You can enforce this by assigning the name .unshare to the subtable, compare unshare .

Define the percentage for each type of MU in the percentage table. Each row in the percentage table pertains to a production order.

- Type the name of and the path to the MU class into the column MU .
- Type the percentage of the respective part types to be produced into the column Portion .
- Type the amount of the respective part types to be produced into the column Number .

You can, but you do not have to, type a Name and Attributes into the table.

- Type the name of the respective part types to be produced into the column Name .
- Type the name of the attribute subtable of the respective part types to be produced into the column Attributes .

<!-- image -->

To make the Source produce the number of MUs , which you typed into the cell Number of the Table in a single lot, select Generate as Batch .

If you select Number Adjustable as the Time of Creation , the amount does not designate the number of parts , but the number of batches that the Source produces. Then the Source produces the entire set of parts at the point in time you entered as Start time .

To make the Source produce the MUs as a sequence of individual MUs , clear the check box.

**Note**

MU Selection &gt; Percentage designates a deterministic process for realizing the frequencies of the part types which you typed into the column Portion for the part types. When selecting the next part, the Source goes to the row on the table which has the greatest need in the column Portion at this point in time. This creates periodically repeating patterns in the sequence of the part types to be produced.

SimTalk

MUSelection [SimTalk]

CreationTableActive [SimTalk]

GenerateAsBatch [SimTalk]

getCurrentOrderTableRow [SimTalk]

unshare [SimTalk]

See also

Produce Parts With a Percentage Entered into a Data Table

Exit strategy &gt; Percentage [described]

Video on YouTube

[https://youtu.be/BvHLQCIjGIA?si=b7Ua-Nl7\_uxT39m4&amp;t=158](https://youtu.be/BvHLQCIjGIA?si=b7Ua-Nl7_uxT39m4&t=158)

**Order Controlled [MU selection]**

Only produces MUs if they are ordered by a Store with activated setting Supermarket or with the method orderParts for the setting MU Selection &gt; Order Controlled .

<!-- image -->

Automatic Routing of the produced part delivers it to the ordering station. If automatic routing of the part is deactivated, Plant Simulation automatically activates it.

The Source produces MUs according to the setting Interval Adjustable and the Interval between the creation times, that you type in.

<!-- image -->

**SimTalk**

MUSelection [SimTalk]

orderParts [SimTalk] - Source

See also

Store as Supermarket [check box]

Configuration [button]

View &gt; Show Orders [Source]

Use the Store as Supermarket

**Generate as Batch [check box]**

**Generate as Batch [check box]**

To make the Source produce the number of MUs , which you typed into the cell Number of the Table in a single lot, select this check box.

<!-- image -->

If you activate Generate as Batch , the Source produces the entire set of parts all at once at the given start time and attempts to move all of the parts on to the next object in a single lot.

To make the Source produce the MUs as a sequence of individual parts, clear the check box.

The setting applies for the MU Selections Sequence , Sequence Cyclical , Random , and Percentage .

<!-- image -->

**Note**

If you select Number Adjustable as the Time of Creation , the Amount does not designate the number of parts , but the number of batches that the Source produces. Then the Source produces the entire set of parts at the point in time you entered as Start Time .

**SimTalk**

GenerateAsBatch [SimTalk]

##### Tab Failures

Define failures as described under the Tab Failures .

##### Tab Controls

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the respective control.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

You can create an Entrance Control and an Exit Control .

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

In addition, you can select the Shift Calendar .

See also

Select Object [for controls]

Entrance Control [general description]

Exit Control [general description]

##### Tab Exit

Tab Exit

Select to which of its successors the object moves the MU on the Tab Exit .

See also

Blocking [exit strategy]

Strategy [material flow objects]

Tab Statistics

Tab Statistics [Source]

In addition to the values described under the Tab Statistics , the tab Statistics provides the dialog items Creation table and Open .

To view Resource Statistics of Stationary Resources in the Statistics Report , select View &gt; Show Statistics Report in the dialog of the object. You can also click the right mouse button in the Frame and select Show Statistics Report or you can press F6 .

<!-- image -->

**See also**

View and Visualize Statistics

Statistics Report [described]

Resource Statistics [check box]

Resource Type

**Creation Table [Source]**

###### Creation Table [Source]

To write all events, for which the Source produced MUs during a simulation run, into a table, select this check box.

<!-- image -->

Then click Open to open the creation table and check the values.

<!-- image -->

**Note**

The Source records the creation events in addition to the resource statistics it collects in any case.

**SimTalk**

CreationTableActive [SimTalk]

creationTable [SimTalk] - Source

###### Open [creation table]

To open the creation table of the Source , if you selected the check box Creation Table , click Open .

<!-- image -->

Each row lists a production event:

- The column Name shows the name of the MU class.
- The column Path shows the path of the MU class, the name of the MU , and its number.
- The column Time of Generation shows the time at which the Source created the individual MU .

<!-- image -->

<!-- image -->

**Tab User-defined**

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

##### Navigate Menu

The commands are described under the Navigate Menu .

View Menu

View Menu

The View Menu provides commands to access its functions.

| Refresh [on View menu]                     | Forward Blocking List     |
|--------------------------------------------|---------------------------|
| Show Statistics Report [on View menu]      | Exit Blocking List        |
| Show Attributes and Methods [on View menu] | Associated Lockout Zones  |
| Show Orders [Source]                       | Associated Shift Calendar |
| Contents [material flow objects]           |                           |

**Show Orders [Source]**

###### Show Orders [Source]

Opens a table that shows the orders which are pending with the Source .

The table contains the Name of the ordered part , its Amount , and the Target of the part . The Target is the object that orders the parts .

<!-- image -->

&gt;

Order Controlled [MU selection]

**See also**

MU selection [drop-down list]

Supermarket [check box]

Configuration [button]

##### Tools Menu

The commands are described under the Tools Menu .

##### Help Menu

The commands are described under the Help Menu .

**Methods of the Source**

#### \_Methods of the Source

The Source provides:

- The methods listed in the table of contents to the left.
- The Methods of the Material Flow Objects .
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

creationTable [SimTalk] - Source

Returns the Creation Table of the Source designated by &lt;Path&gt; and writes it into a table.

Type

Method

Syntax

&lt; Path &gt;.creationTable(CreationTable:table)

Parameter

The parameter CreationTable of data type table either designates a local variable, a table cell of data type table , or the path to a DataTable .

**Example**

MySource.creationTable(myEvaluationTable) MySource.creationTable(MyDataTable[2,8])

SimTalk

CreationTableActive [SimTalk]

See also

Creation Table [Source]

##### getCurrentOrderTableRow [SimTalk]

Returns the row number of the table according to which the Source designated by &lt;Path&gt; currently produces parts.

Remarks

**Note**

The method only returns the table row for MU Selection &gt; Sequence Cyclical , Sequence , Random , and Percentage , which produce parts according to a DataTable .

In all other cases the return value always is 0.

Syntax

&lt; Path &gt;.getCurrentOrderTableRow -&gt; integer

Return Value

The return value has the data type integer .

Example

print MySource.getCurrentOrderTableRow

See also

MU selection [drop-down list] &gt; Sequence Cyclical [MU selection]

Sequence [MU selection]

Random [MU selection]

Percentage [MU selection]

##### orderParts [SimTalk] - Source

orderParts [SimTalk] - Source Orders parts from the Source designated by <Path>. Type Method Syntax

```simtalk
< Path >.orderParts(PartType:object, Amount:integer, Destination:object[, Name:string])
```

**Parameters**

- The parameter PartType of data type object designates the path to the part type that is going to be ordered.
- The parameter Amount of data type integer designates the amount of parts that is going to be ordered.
- The parameter Destination of data type object designates the object that orders the parts. The destination can be any material flow object.
- If the Destination is a Supermarket , Plant Simulation increases the counter of the amount of the remaining ordered parts, compare the column Waiting in the Configuration Table of the Store .
- The optional parameter Name of data type string designates the name of the part type that is going to be ordered. If you do not enter anything, Plant Simulation uses the name of the object which you entered as the PartType .

**Examples**

MySource.orderParts(.UserObjects.MyPart, 12, MyStation, "MyPart")

```simtalk
param partName:string, minStock:integer, maxStock:integer, currentStock:integer, orderedParts:integer
var amount:integer := maxStock-currentStock-orderedParts
if amount > 0 then
	Source.orderParts(@, amount, ?, partName)
end
```

**SimTalk**

orderParts [SimTalk] - Store See also MU selection [drop-down list] &gt; Order Controlled [MU selection]

Configuration [button]

#### Read-Only Attributes of the Source

Read-Only Attributes of the Source

The Source provides:

- The \_Read-Only Attributes of All Objects .
- The Read-Only Attributes of the Material Flow Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MySource.UUID

#### Attributes of the Source

##### \_Attributes of the Source

The Source provides:

- The attributes listed in the table of contents to the left.
- The Attributes of All Objects .
- The Attributes of the Material Flow Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MySource.GenerateAsBatch := true
print MySource.GenerateAsBatch
posit := MyStation.Cont.XPos
```

##### Blocking [SimTalk]

Sets if the Source designated by &lt;Path&gt; saves the time at which it was supposed to produce the next MU ( true ) or not ( false ).

Remarks

When you set Blocking to true , the Source produces the following MUs at the next possible point in time, i.e., when the Source moved the MU that was blocked by the successor, on ( true ).

When you set Blocking to false , the Source creates another MU only at the Time of Creation which you entered.

Type

Attribute

Syntax

&lt; Path &gt;.Blocking:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MySource.Blocking := true
```

See also

Operating Mode [check box]

Time of Creation [Source]

##### CreationTableActive [SimTalk]

Sets if the Source designated by &lt;Path&gt; writes all events, for which it produced MUs during a simulation run, into a table ( true ) or not ( false ).

Remarks

The Source records the creation events in addition to the resource statistics it collects in any case.

Type

Attribute

Syntax

&lt; Path &gt;.CreationTableActive:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MySource.CreationTableActive := true

SimTalk

creationTable [SimTalk] - Source

See also

Creation Table [Source]

##### GenerateAsBatch [SimTalk]

Makes the Source designated by &lt;Path&gt; produce MUs in a single batch all at once ( true ) or individually one by one ( false ).

Remarks

If you activate Generate as Batch , the Source produces the entire set of parts all at once at the given start time and attempts to move all of the parts on to the next object in a single lot.

**Note**

This setting applies for the MU Selection &gt; Sequence Cyclical , Sequence , Random , and Percentage .

**Note**

If you set MU Selection to Number Adjustable and if you activate the check box Generate as Batch , the Amount does not designate the number of parts , but the number of batches that the Source produces.

Type

Attribute

Syntax

&lt; Path &gt;.GenerateAsBatch:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MySource.GenerateAsBatch := true

See also

Generate as Batch [check box]

MU selection [drop-down list] &gt; Sequence Cyclical [MU selection]

Sequence [MU selection]

**GenerateAsBatch [SimTalk]**

Random [MU selection]

Percentage [MU selection]

Number Adjustable [time of creation]

##### Interval [SimTalk] - Source

Sets the interval between the times at which the Source designated by &lt;Path&gt; produces MUs .

Remarks

The behavior of the attribute Interval depends on the setting TimeOfGeneration :

- For Time of Creation &gt; Interval Adjustable this applies:

The attribute Interval sets the time that elapses between the creation events of the Source designated by &lt;Path&gt;. Specify a distribution and enter the values, which that distribution requires. You can also specify Const and enter a constant time.

The attribute Start sets the simulation time at which the Source starts producing MUs .

The attribute Stop sets the simulation time at which the Source stops producing MUs . A Stop time of 0 (zero) indicates that the Source will keep producing MUs infinitely.

- For Time of Creation &gt; Number Adjustable this applies:

You can specify one of the Probability Distributions and specify the values that the selected distribution requires. The distribution determines the point in time at which the Source creates the MUs .

The Source produces the number of MUs at the different times which the random number generator generated at the beginning of the simulation. The determined times are contained within the bounds if you enter a lower bound and an upper bound.

Specify a Constant time to make the Source create the number of MUs all at one point in time.

Type

Attribute

Syntax

< Path >.Start:time < Path >.Stop:time < Path >.Interval:time

**Assignment Value**

You can assign a value of data type time .

**Example**

```simtalk
MySource.TimeOfCreation := "Interval adjustable"
MySource.Start := 3600
MySource.Stop := str_to_time("1:00:00:00.00")
MySource.Interval.setTypeAndAttr("Normal",1,500,100,200,900)
```

SimTalk

Start [SimTalk] - Source

Stop [SimTalk] - Source

See also

TimeOfGeneration [SimTalk]

Start [Source]

Interval [Source]

Stop

Interval Adjustable [time of creation]

Interval Adjustable [time of creation]

Probability Distributions

##### MUSelection [SimTalk]

Sets how the Source designated by &lt;Path&gt; selects the MUs to be produced.

Remarks

**Note**

Depending on the setting that you enter, the attribute Path either sets the path to the delivery list, the sequence table, the frequency table, or the MU class.

**Note**

To use a copy of the DataTable instead of a reference to the DataTable , assign the name .unshare to the subtable.

Type

Attribute

Syntax

&lt; Path &gt;.MUSelection:string

Assignment Value

You can assign a value of data type string .

You can specify "Constant" , "Sequence Cyclical" , "Sequence" , "Random" , "Percentage" , or "Order Controlled" .

Example

MySource.MUSelection := "Sequence"

SimTalk

Path [SimTalk] - Source

See also

Store as Supermarket [check box] , Configuration [button]

MU selection [drop-down list]

##### Number [SimTalk]

Sets the number of MUs which the Source designated by &lt;Path&gt; produces.

Remarks

This setting only applies for the Time of Creation &gt; Number Adjustable and Interval Adjustable .

If you do not enter a Stop time for the setting Interval Adjustable , Plant Simulation produces the amount of parts you entered at the most. The default value of -1 designates an unlimited number of parts to be produced. Otherwise the Source produces parts until the Stop time is reached and ignores the Amount of parts you entered.

For the setting Interval Adjustable the Source might possibly create more parts than the Amount you entered, if the check box Generate as Batch is activated. This is because the batches are always produced in their entirety, not in part only

For the setting Time of creation &gt; Number Adjustable the value does not designate the amount of MUs but the amount of batches/lots which the Source produces when you activated Generate as Batch .

Type

Attribute

Syntax

```simtalk
< Path >.Number:integer
```

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MySource.Number := 5
```

See also

MU selection [drop-down list]

Number Adjustable [time of creation]

Stop [Source]

**Generate as Batch [check box]**

##### Path [SimTalk] - Source

Sets the path to the delivery list, the sequence table, the frequency table, or the MU class of the Source designated by &lt;Path&gt;.

Remarks

What the path relates to depends on the settings for TimeOfGeneration and MUSelection :

<!-- image -->

**Note**

The Source does not produce parts whose time of creation is in the future when you assign a Delivery Table during the simulation.

Type

Attribute

Syntax

```simtalk
< Path >.Path:string
```

Assignment Value

You can assign a value of data type string or object .

Example

```simtalk
MySource.Path := "MyDeliveryTable"
```

See also

Time of Creation [Source] / TimeOfGeneration [SimTalk]

**MU selection [drop-down list] / MUSelection [SimTalk] Delivery Table [time of creation]**

##### Start [SimTalk] - Source

Sets the simulation time at which the Source designated by &lt;Path&gt; starts producing MUs .

Remarks

Start applies when you set the TimeOfGeneration to Interval Adjustable .

The attribute Interval sets the time span between two events at which the Source produces MUs .

The attribute Stop sets the simulation time at which the Source stops producing MUs . A Stop time of zero indicates that the Source will keep producing MUs infinitely.

Type

Attribute

Syntax

< Path >.Start:time < Path >.Stop:time < Path >.Interval:time

Assignment Value

You can assign a value of data type time .

Example

```simtalk
MySource.TimeOfGeneration := "Interval adjustable"
MySource.Start := 3600
MySource.Stop := str_to_time("1:00:00:00.00")
MySource.Interval.setTypeAndAttr("Normal",500,100,200,900)
```

SimTalk

TimeOfGeneration [SimTalk]

Stop [SimTalk] - Source

Interval [SimTalk] - Source

See also

Start [Source] , text box Interval [Source]

Stop [Source]

, text box

, text box

Interval Adjustable [time of creation]

##### Stop [SimTalk] - Source

Sets the simulation time at which the Source designated by &lt;Path&gt; stops producing MUs .

Remarks

A Stop time of zero indicates that the Source will keep producing MUs infinitely.

The attribute Start sets the simulation time at which the Source starts producing MUs , when you set the TimeOfGeneration to Interval Adjustable .

The attribute Interval sets the time span between two events at which the Source produces MUs .

Type

Attribute

Syntax

< Path >.Start:time < Path >.Stop:time < Path >.Interval:time

Assignment Value

You can assign a value of data type time .

**Example**

```simtalk
MySource.TimeOfGeneration := "Interval adjustable"
MySource.Start := 3600
MySource.Stop := str_to_time("1:00:00:00.00")
MySource.Interval.setTypeAndAttr("Normal",500,100,200,900)
```

SimTalk

Start [SimTalk] - Source

Interval [SimTalk] - Source

TimeOfGeneration [SimTalk]

See also

Start [Source]

Interval [Source]

Stop [Source]

##### TimeOfGeneration [SimTalk]

Sets how the Source designated by &lt;Path&gt; produces new MUs .

Remarks

Depending on the setting that you enter, the attribute Path either sets the path to the delivery list, the sequence table, the frequency table, or the MU class.

<!-- image -->

**Note**

The Source does not produce parts whose time of creation is in the future when you assign a Delivery Table during the simulation.

**Note**

Plant Simulation processes the Delivery Table row by row. For this reason the time should increase from row to row. If Plant Simulation processes a row in which the time is located in the past, the part will be created immediately, which is not what you would expect.

Type

Attribute

Syntax

&lt; Path &gt;.TimeOfGeneration:string

Assignment Value

You can assign a value of data type string .

You can specify " Interval Adjustable ", " Number Adjustable ", " Delivery Table ", or " Trigger ".

**Examples**

```simtalk
MySource.TimeOfGeneration := "number adjustable"
MySource.TimeOfGeneration := "delivery table"
MySource.path := MyDeliveryTable
```

**SimTalk**

Path [SimTalk] - Source

See also

Time of Creation [Source]

##### Trigger [SimTalk]

Sets the internal Trigger list of the Source designated by &lt;Path&gt; or returns it.

Type

Attribute

Syntax

< Path >.Trigger:array

Assignment Value

You can assign a value of data type array .

Examples

```simtalk
var assignedTriggers: object[2]
for var j := 1 to 2
	assignedTriggers[j] := to_str("Trigger",j)
next
Source.Trigger := assignedTriggers // sets the trigger list
print MySource.Trigger // gets the trigger list // [*.Models.Model.Trigger, *.Models.Model.Trigger2]
```

See also

Trigger [time of creation]

