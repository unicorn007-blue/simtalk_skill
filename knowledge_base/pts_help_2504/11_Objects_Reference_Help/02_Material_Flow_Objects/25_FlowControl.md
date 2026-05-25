### FlowControl

The FlowControl for modeling strategies for splitting-up and bringing together the flow of materials in your plant.

Icon

<!-- image -->

Description

The FlowControl does not process the MUs , it only distributes them among the stations that succeed it in the sequence of stations in the simulation model.

Insert the FlowControl between at least two other objects to control the flow of materials between these objects. If need be, you can also combine several FlowControl objects. The number of predecessors and successors is unlimited.

**Note**

You cannot model cycles, meaning that may not connect a FlowControl with itself, not even via other FlowControls or Interfaces . You can, for example not model like this: FlowControl1 -&gt; Frame.Interface1 -&gt; Frame.FlowControl2 -&gt; Frame.Interface2 -&gt; FlowControl1 .

To show a tooltip with information about the FlowControl , hover with the mouse over it.

<!-- image -->

To change the length of the graphic and the anchor points of the FlowControl , click Show Manipulators

<!-- image -->

on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

<!-- image -->

To add the FlowControl to your simulation model, click MaterialFlow &gt; FlowControl on the Home ribbon tab.

Manage Class Library &gt; Basic Objects &gt;

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

**See also**

Distribute Parts Among its Successors with the FlowControl

Connector

Show Predecessors [View ribbon] - 2D

Show Successors [View ribbon] - 2D

#### Dialog Box of the FlowControl

Dialog Box of the FlowControl

Double-click the icon of the FlowControl to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

<!-- image -->

**Edit Animation Properties**

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

##### Tab Exit Strategy

Tab Exit

Select the Strategy for splitting up the flow of materials from the drop-down list Strategy .

<!-- image -->

<!-- image -->

For some of the Exit Strategies you can also select if the strategy is Blocking or not blocking .

SimTalk

ExitBehavior [SimTalk]

See also

Strategy [FlowControl, exit]

Tab Exit

**Next Aimed Successor [FlowControl]**

Data Held in Tabular Form in Attributes [material flow objects]

###### Blocking [FlowControl, exit]

Blocking [FlowControl, exit]

Select if the Exit Strategy is blocking or non-blocking .

- If you select Blocking , the FlowControl moves the MU on, if the desired successor can receive it.
- If you clear Blocking , the FlowControl only moves the MU on, if any of its successors can receive it.

**Note**

The non-blocking strategy of the Exit Strategy &gt; MU Attribute moves the MU on if any of the desired successors can receive it.

**SimTalk**

**ExitBlocking [SimTalk]**

Strategy

Strategy [FlowControl, exit]

Select the Strategy according to which the FlowControl distributes the MUs among its successors.

<!-- image -->

- The strategy Assignment does not determine the successor to which the FlowControl moves the MU on. Instead, you can change the values of the attributes of the part , when it moves to the one and only successor of the FlowControl . As soon as the MU is moved on to the successor, Plant Simulation calls the method , whose name you typed into the text box Method . Define the assignments to be made in this method .

- To move the MUs cyclically on to all successors, select Cyclic .
- To cyclically move the MUs on to the successor according to the sequence of successors, which you typed into a list, select Cyclic Sequence .
- To move the MUs on to the successor, which has been Waiting the longest for a MU , select Least Recently Used .
- To move the MUs on to a successor according to the return value of a Method , select Method .

**Note**

You cannot move or delete MUs in the Method because Plant Simulation runs the Method like a formula. For this reason Plant Simulation does not show the tab Expressions of the Method Debugger .

In addition, you cannot use a wait-instruction , a waituntil-instruction , or a stopuntil-instruction within the Method .

- To move the MUs on to the successor, which has Waiting the shortest time for a MU , select Most Recently Used .
- To move the MUs on to a successor according to the values of attributes of the MUs , select MU Attribute .
- To move the MUs on to a successor according to their names, select MU Name .
- To move the MUs on to a successor according to a percentage distribution, select Percentage .
- To move the MUs on to a randomly selected successor, select Random .
- To move the MUs on to the successor meeting a certain Property , select Selection from the drop-down list. Then, select a Property from the drop-down list Property .
- To move the MUs on to the first available successor, select Start at Successor 1 .
- To copy the MUs that enter, and move a copy each to each of the successors, select To All Successors .

Depending on the strategy you select, the FlowControl shows additional check boxes, text boxes and buttons.

Click the check box Inheritance so that it looks like this . Then, click Open List and enter the data into the list, which the exit strategies Cyclic Sequence , MU Attribute , MU Name , and Percentage require.

SimTalk

ExitBehavior [SimTalk]

See also

getExitList [SimTalk]

setExitList [SimTalk]

Data Held in Tabular Form in Attributes [material flow objects]

**Assignment [FlowControl, strategy]**

The strategy Assignment does not determine the successor to which the FlowControl moves the MU on. Instead, you can change the values of the attributes of the MU , when it moves to the one and only successor of the FlowControl .

**Note**

A FlowControl using the Assignment strategy always moves the MUs on to the successor with the number 1.

<!-- image -->

As soon as the MU is moved on to the successor, Plant Simulation calls the method , whose name you typed into the text box Method . Define the assignments to be made in this method .

**Example**

```simtalk
@.color := "red"
@.ProdState := 3
```

**Note**

Normally Plant Simulation only calls the method , when it is certain that the successor can receive the MU . If the successor is a FlowControl , changing an attribute of the MU by this method can affect to which successor this succeeding FlowControl will move the MU on. In this case the method will be called for a temporary copy of the MU and the succeeding FlowControl determines its successor using this copy. The original MU remains untouched during this time. If the thus determined successor can receive the MU , the method will be called again for the original MU .

In this case you should make sure that you assign the same value to the copy as to the original MU .

**SimTalk**

ExitBehavior [SimTalk]

DefaultSuccessor [SimTalk] - FlowControl

**See also**

**Show Successors [View ribbon] - 2D**

Cyclic [FlowControl, exit]

To move the MUs cyclically on to all successors, select Cyclic from the drop-down list.

- If you select Blocking , the FlowControl moves the MU on to the successor, which follows the successor to which the last MU was moved. If this successor cannot receive the MU , it will be Blocked until the successor can receive it.
- If you clear Blocking , the FlowControl moves the MU on to the first successor, which can receive the MU and which follows the successor to which the last MU was moved.

When the FlowControl reaches the last successor, it restarts the search at the beginning.

SimTalk

ExitBehavior [SimTalk]

ExitBlocking [SimTalk]

Cyclic Sequence [FlowControl, exit]

To cyclically move the MUs on to the successor according to the sequence of successors, which you typed into a list, select Cyclic sequence from the drop-down list.

<!-- image -->

Turn the Inheritance check box off so that it looks like this . Then, click Open List , and type the number of the succeeding object into the corresponding cell of the list. The FlowControl moves a MU to the successor, whose turn it is next.

- If you select Blocking and the next successor in the sequence cannot receive a MU , the FlowControl blocks the MU until the successor can receive it.
- If you clear Blocking , the FlowControl moves the MU on to the next successor, which can receive it, and so on.

Once the FlowControl reaches the end of the sequence, it restarts the search at the beginning.

SimTalk

ExitBehavior [SimTalk]

ExitBlocking [SimTalk]

setExitList [SimTalk]

getExitList [SimTalk]

See also

Show Successors [View ribbon] - 2D

Data Held in Tabular Form in Attributes [material flow objects]

Context Menu of Embedded Lists Least recently used [FlowControl, exit]

To move the MUs on to the successor, which has been waiting the longest for a MU , select Least recently used from the drop-down list.

SimTalk

ExitBehavior [SimTalk]

See also

Waiting [state, material flow objects]

**Method [FlowControl, exit]**

Method [FlowControl, exit]

To move the MUs on to a successor according to the return value of a Method , select Method from the drop-down list.

**Note**

You cannot move or delete MUs in the Method because Plant Simulation runs the Method like a formula. For this reason, you also cannot use a wait-instruction , a waituntil-instruction , or a stopuntilinstruction within the Method .

In addition, Plant Simulation does not show the tab Expressions of the Method Debugger .

<!-- image -->

Type in the name of the Method , whose return value determines the number of the successor to which the FlowControl moves the MU . In the method , you can access the FlowControl with the anonymous identifier ? . The anonymous identifier @ points to the MU which is to be moved on.

- If you select Blocking , the method does not have a parameter.
- If you clear Blocking , the method has a single integer parameter. It tells which number within the total amount of attempts to determine a successor that specific attempt has. In case the method returns the number of a successor to which the MU cannot be moved on, the method is called again. It is called as often as the FlowControl has successors at the most. If the method returns 0, the FlowControl immediately blocks the MU and does not call the method again.

**SimTalk**

ExitSelectionMethod [SimTalk]

See also

ExitBehavior [SimTalk]

ExitBlocking [SimTalk]

Show Successors [View ribbon] - 2D

**Most recently used [FlowControl, exit]**

To move the MUs on to the successor, which has been waiting the shortest time for a MU , select Most recently used from the drop-down list.

The FlowControl always moves the MUs to the same successor, as long as this successor can receive the MUs .

SimTalk

**ExitBehavior [SimTalk]**

See also

Waiting [state, material flow objects]

**MU Attribute [FlowControl, exit]**

**MU Attribute [FlowControl, exit]**

To move the MUs on to a successor according to the values of attributes of the MUs , select MU Attribute from the drop-down list.

- If you select Blocking , the FlowControl always moves the MU to the designated successor. If that successor is not ready to receive it, the MU will be blocked.
- If you clear Blocking , the FlowControl moves the MU on when any of its successors can receive it. In this case enter the desired Numbers of the successors into the Attribute List for each Attribute Value .

<!-- image -->

Turn the Inheritance check box off so that it looks like this . Then click Open List to open a table, into which you can type the names of the user-defined or the built-in attributes, their values, and the numbers of the successors. The FlowControl searches the table from top to bottom until it finds an attribute with the value you entered. It then moves the MU on to that successor.

<!-- image -->

**Note**

Create the user-defined attributes for the MUs on the Tab User-defined .

**Default Successor**

Type in the number of the default successor. This is the successor to which the FlowControl moves the MUs if none of the MUs has an attribute with the Value you typed into the DataTable .

To not move a part, which does not meet one of the conditions on the table, type in 0 .

To show a message, when a part is to be moved which does not meet any of the conditions in the DataTable , type in a negative number.

**Attribute Type**

Select the data type of the attribute from this drop-down list, compare Data Types .

<!-- image -->

**SimTalk**

setAttributeList [SimTalk] - FlowControl

getAttributeList [SimTalk] - FlowControl

AttributeType [SimTalk] - FlowControl

ExitBlocking [SimTalk]

ExitBehavior [SimTalk]

DefaultSuccessor [SimTalk] - FlowControl

See also

Show Successors [View ribbon] - 2D

Data Held in Tabular Form in Attributes [material flow objects]

Context Menu of Embedded Lists

**MU Name**

To move the MUs on to a successor according to their names, select MU Name from the drop-down list.

<!-- image -->

Turn the Inheritance check box off so that it looks like this . Then, click Open List to open a table into which you can type the Name of the attribute and the number of the Successor . The FlowControl searches the table for the name of the MU to be moved on and then moves the MU on to the successor which is specified in this row.

<!-- image -->

**Default Successor**

Type the number of the default successor into this text box. The default successor is the successor to which the FlowControl moves the MUs if the name of a MU is not contained in the DataTable . This is the successor to which the FlowControl moves the MUs if none of the MUs has an attribute with the Value which you typed into the DataTable .

To not move a part, which does not meet one of the conditions on the table, type in 0 .

To show a message, when a part is to be moved which does not meet any of the conditions in the DataTable , type in -1 .

SimTalk setAttributeList [SimTalk] - FlowControl getAttributeList [SimTalk] - FlowControl AttributeType [SimTalk] - FlowControl ExitBlocking [SimTalk] ExitBehavior [SimTalk] DefaultSuccessor [SimTalk] - FlowControl See also Show Successors [View ribbon] - 2D Data Held in Tabular Form in Attributes [material flow objects] Context Menu of Embedded Lists

**Percentage [FlowControl, exit]**

To move the MUs on to a successor according to a percentage distribution, select Percentage from the drop-down list.

<!-- image -->

Turn the Inheritance check box off so that it looks like this . Then, click Open List to open a table and type in the percentages. The n-th row on the table defines the n-th successor's portion. The FlowControl moves a MU to the successor for which the difference between the desired value and the actual value is greatest.

Note

When you specify 0 in the table, the predecessor of the FlowControl will not receive a MU .

- If you select Blocking , the FlowControl blocks the MU until the successor determined by the distribution can receive the MU .
- If you clear Blocking , the FlowControl moves the MU on to the successor with the second largest difference between the desired value and the actual value, etc.

SimTalk

setExitList [SimTalk]

getExitList [SimTalk]

ExitBlocking [SimTalk]

ExitBehavior [SimTalk]

See also

Show Successors [View ribbon] - 2D

Data Held in Tabular Form in Attributes [material flow objects]

Context Menu of Embedded Lists

**Random [FlowControl, exit]**

To move the MUs on to a randomly selected successor, select Random from the drop-down list.

Then, select a distribution from the drop-down list Distribution and type the values into the respective text box, compare Probability Distributions .

<!-- image -->

The FlowControl distributes the MUs according to the selected distribution to its successors.

- If you select Blocking , the FlowControl only rolls the dice once. If the thus determined successor cannot receive the MU , it will be Blocked until the successor can receive it.
- If you clear Blocking , the FlowControl rolls the dice until it can determine a successor which can receive the MU or until the Maximum Number of Samples multiplied with the number of successors is reached.

**SimTalk**

**ExitDistribution [SimTalk]**

See also

ExitBehavior [SimTalk]

ExitBlocking [SimTalk]

**Selection [FlowControl, exit]**

To move the MUs on to the successor meeting a certain property, select Selection from the drop-down list.

Then, select a Property from the drop-down list Property .

<!-- image -->

For some selection criteria you can also select if the strategy is Blocking or not blocking .

| Property         | The FlowControl moves the part on to the                                                                                                                |
|------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| Max. contents    | successor that currently contains the greatest number of MUs .                                                                                          |
| Min. contents    | successor that currently contains the smallest number of MUs .                                                                                          |
| Max. proc. time  | successor with the longest processing time for this MU .                                                                                                |
| Min. proc. time  | successor with the shortest processing time for this MU .                                                                                               |
| Max. Set-up time | successor with the longest set-up time for this MU .                                                                                                    |
| Min. Set-up time | successor with the shortest set-up time for this MU .                                                                                                   |
| Max. num. in     | successor that received the most MUs . This only works correctly, when resource statistics of the successor or of the predecessor is active.            |
| Min. num. in     | successor that received the least number of MUs . This only works correctly, when resource statistics of the successor or of the predecessor is active. |

| Property        | The FlowControl moves the part on to the                                                                                                             |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| Max. rel. occu. | successor with the highest relative occupancy. This only works correctly, when resource statistics of the successor or of the predecessor is active. |
| Min. rel. occu. | successor with the lowest relative occupancy. This only works correctly, when resource statistics of the successor or of the predecessor is active.  |

**SimTalk**

ExitSelectionProperty [SimTalk]

ExitBehavior [SimTalk]

ExitBlocking [SimTalk]

See also

Show Successors [View ribbon] - 2D

**Start at Successor 1 [FlowControl, exit]**

Start at Successor 1 [FlowControl, exit]

To move the MUs on to the first available successor, select Start at Successor 1 from the drop-down list.

The FlowControl checks the successors starting with the successor with the number 1. It moves the MU on to successor number 3, for example, if it cannot move it on to successor 1 and 2. As long as the successor with the number 1 can receive MUs , the FlowControl always moves them to it.

SimTalk

**ExitBehavior [SimTalk]**

See also

Show Successors [View ribbon] - 2D

To all successors

To copy the MU that enters, and move a copy each to each of the successors, select To all successors from the drop-down list.

The strategy To all successors is blocking , i.e., the FlowControl only moves the MUs on when all successors are ready to receive their copy of the MU .

SimTalk

**ExitBehavior [SimTalk]**

See also

Show Successors [View ribbon] - 2D

###### Next Aimed Successor [FlowControl]

A FlowControl , which you inserted into a Frame , shows its next aimed at successor. This is the successor, which is served next according to the exit strategy.

If you clear Blocking , this does not have to be the successor to which the part is actually moved.

##### Tab Entry Strategy

###### Tab Entry

Select the strategy for merging the flow of materials from the drop-down list Strategy .

<!-- image -->

For some of the entry Strategies you can select if the strategy is Blocking or not blocking .

<!-- image -->

**See also**

Blocking [FlowControl, entry]

Strategy [FlowControl, entry]

Next Aimed Predecessor

Data Held in Tabular Form in Attributes [material flow objects]

**Blocking [FlowControl, entry]**

###### Blocking [FlowControl, entry]

Select if the entry strategy is blocking or not blocking.

- If you select Blocking , the FlowControl only receives MUs from the next designated predecessor. MUs Waiting on other predecessors cannot be received.
- If you clear Blocking , the FlowControl receives MUs from any of its predecessors. The Entry Strategy only takes effect if the Blocking List of the FlowControl contains several MUs and the FlowControl is unblocked because of a successor getting ready to receive a MU .

**SimTalk**

**EntryBlocking [SimTalk]**

###### Strategy

Strategy [FlowControl, entry]

Select the strategy according to which the FlowControl receives the MUs from its predecessors.

<!-- image -->

**Note**

If a MU can reach a FlowControl via different Connectors , you can only use First come, first served as the entry strategy. This can only happen if at least one of the preceding Connectors starts at a FlowControl .

<!-- image -->

- To cyclically receive the MUs from all predecessors, select Cyclic .
- To cyclically receive the MUs from the predecessor according to the sequence of predecessors, which you typed into the list, select Cyclic sequence .
- To receive the MUs from the predecessor in the order in which they intended to exit, select First come, first served .
- To receive the MUs from the predecessor that has not provided a MU for the longest time, select Least recently used .
- To receive the MUs from the predecessor defined by the return value of the Method , which you typed into the text box Method , select Method .

**Note**

You cannot move or delete MUs in the Method because Plant Simulation runs the Method like a formula. For this reason Plant Simulation does not show the tab Expressions of the Method Debugger .

In addition, you cannot use a wait-instruction , a waituntil-instruction , or a stopuntil-instruction within the Method .

- To receive the MUs from the predecessor, from which the FlowControl received a MU the last time, select Most recently used .
- To receive the MUs from the predecessors according to a percentage distribution, select Percentage .
- To receive the MUs from the predecessors randomly, select Random .
- To receive the MUs from the predecessors according to the state and the material flow balance of the predecessors, select Selection . Then, select a Property .
- To receive the MUs from the first available predecessor, select Start at Predecessor 1 .

Depending on what you select, the FlowControl shows additional check boxes, text boxes and buttons. Turn the Inheritance check box off so that it looks like this . Then, click Open List and type the data which the selected strategy requires, into the cells of the list.

SimTalk

EntryBehavior [SimTalk]

**Cyclic [FlowControl, entry]**

Cyclic [FlowControl, entry]

To cyclically receive the MUs from all predecessors, select Cyclic from the drop-down list.

- If you select Blocking , the FlowControl only receives the MU from the predecessor which immediately follows the predecessor from which it received the last MU .
- If you clear Blocking , the FlowControl only receives the MU from the first predecessor which is ready to move a MU on and which immediately follows the predecessor from which it received the last MU .

Once the FlowControl reaches the end of the list of its predecessors, it restarts the search at the beginning.

SimTalk

EntryBehavior [SimTalk]

EntryBlocking [SimTalk]

Cyclic Sequence [FlowControl, entry]

To cyclically receive the MU from the predecessors according to the sequence of predecessors, which you type into a list, select Cyclic Sequence from the drop-down list.

<!-- image -->

Turn the Inheritance check box off so that it looks like this . Then, click Open List to open the entry list and enter the sequence of the preceding objects.

- If you select Blocking , the FlowControl only receives MUs from the next the predecessor in the sequence. It blocks MUs from other predecessors.
- If you clear Blocking , the FlowControl receives MU from all predecessors. If the FlowControl Blocked several MUs , it unblocks the MU which is located on the predecessor and which is next in the sequence.

Once the FlowControl reaches the end of the list of its predecessors, it restarts the search at the beginning.

SimTalk

setEntryList [SimTalk]

getEntryList [SimTalk]

EntryBehavior [SimTalk]

EntryBlocking [SimTalk]

See also

Show Predecessors [View ribbon] - 2D

Data Held in Tabular Form in Attributes [material flow objects]

Context Menu of Embedded Lists

**First come, first served**

First come, first served

To receive the MUs from the predecessors in the order in which they wanted to exit the predecessors of the FlowControl , select First come, first served from the drop-down list.

SimTalk

EntryBehavior [SimTalk]

Least recently used [FlowControl, entry]

To receive the MUs from the predecessor which did not move on a MU for the longest time, select Least recently used from the drop-down list.

See also

EntryBehavior [SimTalk]

**Method [FlowControl, entry]**

To receive the MUs from the predecessor defined by the return value of the Method , select Method from the drop-down list.

<!-- image -->

**Note**

You cannot move or delete MUs in the Method because Plant Simulation runs the Method like a formula. For this reason Plant Simulation does not show the tab Expressions of the Method Debugger .

In addition, you cannot use a wait-instruction , a waituntil-instruction , or a stopuntil-instruction within the Method .

Type in the name of the Method , whose return value determines the predecessor from which the FlowControl receives the part . In the method , you can access the FlowControl using the anonymous identifier ? .

- If you select Blocking , the method does not have a parameter. The method is called each and every time, when a MU wants to move through the FlowControl , except when the part was unblocked immediately before by the FlowControl . In addition, the method is called every time the FlowControl is to unblock a MU , i.e., when the FlowControl itself is unblocked by one of its successors.
- If you clear Blocking , the method will only be called, when one of several MUs Blocked by the FlowControl is to be unblocked. The return value of the method determines, which MU will be unblocked. The method has a single integer parameter. It tells what number within the total amount of attempts to determine a successor that attempt has. In case the method returns the number of a predecessor, from which the MU cannot be received, the method is called again. It is called as often as the FlowControl has predecessors at the most. If the method returns 0, the FlowControl does not unblock any of the MUs and does not call the method again.

**SimTalk**

EntrySelectionMethod [SimTalk]

See also

EntryBehavior [SimTalk]

**EntryBlocking [SimTalk]**

**Most recently used [FlowControl, entry]**

Most recently used [FlowControl, entry]

To receive the MUs from the predecessor, from which the FlowControl received a MU the last time, select Most recently used from the drop-down list.

As long as this predecessor can move MUs on, the FlowControl receives them from this predecessor.

SimTalk

EntryBehavior [SimTalk]

**Percentage [FlowControl, entry]**

To receive the MUs from the predecessors according to a percentage distribution, select Percentage from the drop-down list.

<!-- image -->

Turn the Inheritance check box off so that it looks like this . Then click Open List to open a table and type in the percentages. The n-th row on the table defines the n-th successor's portion. The FlowControl only receives a MU from the predecessor, for which the difference between the desired value and the actual value is greatest.

Note

If you type 0 into the table, the successor of the FlowControl will not receive a MU .

- If you select Blocking , the FlowControl only receives MUs from the designated predecessor.
- If you clear Blocking , the FlowControl receives MUs from all predecessors. The FlowControl takes the percentage distribution into account, when unblocking MUs .

SimTalk

setEntryList [SimTalk]

getEntryList [SimTalk]

See also

EntryBehavior [SimTalk]

EntryBlocking [SimTalk]

Show Predecessors [View ribbon] - 2D

Data Held in Tabular Form in Attributes [material flow objects]

Context Menu of Embedded Lists

**Random [FlowControl, entry]**

For the entry strategy Random , select a distribution from the drop-down list Random and type a value into the respective text box.

<!-- image -->

The FlowControl receives the MUs according to the selected distribution from its predecessors.

- If you select Blocking , the FlowControl rolls the dice only once and receives a MU from the thus determined predecessor. MUs from other predecessors will be Blocked .
- If you clear Blocking , the FlowControl receives MUs from all predecessors. If several MUs were blocked by the FlowControl and one of those is to be unblocked, it rolls the dice until it determines a predecessor with a blocked MU or until the Maximum Number of Samples multiplied with the number of predecessor is reached.

Select a distribution for receiving the MUs from the predecessors and type the parameters which this distribution requires into the text box.

SimTalk

EntryDistribution [SimTalk]

See also

Probability Distributions

EntryBehavior [SimTalk]

EntryBlocking [SimTalk]

**Selection [FlowControl, entry]**

To receive the MUs from the predecessor according to the state and the material flow balance of the predecessor, select Selection from the drop-down list.

<!-- image -->

Select the property of the predecessor according to which the FlowControl receives the MUs .

| Property        | The FlowControl receives the part from the                                                                                                                |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| Max. contents   | predecessor containing the greatest number of MUs .                                                                                                       |
| Min. contents   | predecessor containing the smallest number of MUs .                                                                                                       |
| Max. proc. time | predecessor with the longest processing time.                                                                                                             |
| Min. proc. time | predecessor with the shortest processing time.                                                                                                            |
| Max. num. out   | predecessor where the highest number of MUs exited. This only works correctly, when resource statistics of the successor or of the predecessor is active. |
| Min. num. out   | predecessor where the lowest number of MUs exited. This only works correctly, when resource statistics of the successor or of the predecessor is active.  |

| Property        | The FlowControl receives the part from the                                                                                                             |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
| Max. rel. occu. | predecessor with the highest relative occupancy. This only works correctly, when resource statistics of the successor or of the predecessor is active. |
| Min. rel. occu. | predecessor with the lowest relative occupancy. This only works correctly, when resource statistics of the successor or of the predecessor is active.  |

**SimTalk**

EntrySelectionProperty [SimTalk]

See also

EntryBehavior [SimTalk]

EntryBlocking [SimTalk]

Show Predecessors [View ribbon] - 2D

**Start at Predecessor 1**

To receive the MUs from the first available predecessor, starting with the predecessor with the number 1, select Start at Predecessor 1 from the drop-down list.

The FlowControl only receives a MU from predecessor 3, for example, when predecessor 1 and 2 cannot deliver one.

SimTalk

**EntryBehavior [SimTalk]**

See also

Show Predecessors [View ribbon] - 2D

**Next Aimed Predecessor**

###### Next Aimed Predecessor

A FlowControl , which you inserted into a Frame shows its next aimed at predecessor here. This is the predecessor, which is served next according to the entry strategy.

When you deactivate Blocking , this does not have to be the predecessor from which the part is actually received.

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

**Navigate Menu**

##### Navigate Menu

The commands are described under the Navigate Menu .

View Menu

The View Menu provides commands to access its functions.

Refresh [on View menu]

Show Attributes and Methods [on View menu]

SimTalk

updateDialog [SimTalk]

See also

View Menu [general description]

**Tools Menu**

##### Tools Menu

The commands are described under the Tools Menu .

##### Help Menu

The commands are described under the Help Menu .

**Methods of the FlowControl**

#### \_Methods of the FlowControl

The FlowControl provides:

- The methods listed in the table of contents to the left.
- The Methods of All Objects .

As the FlowControl cannot receive any MUs , it does not have the methods which the other material flow objects provide.

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

getAttributeList [SimTalk] - FlowControl

Returns the values of the attributes passed to the FlowControl designated by &lt;Path&gt; for the Exit strategy MU attribute and writes them into a list.

Type

Method

Syntax

&lt; Path &gt;.getAttributeList(AttributeList:table)

Parameter

The parameter AttributeList of data type table designates the name of the list.

Example

MyFlowControl.getAttributeList(tab)

SimTalk

setAttributeList [SimTalk] - FlowControl

See also

MU Attribute [FlowControl, exit]

Data Held in Tabular Form in Attributes [material flow objects]

##### getEntryList [SimTalk]

getEntryList [SimTalk]

Returns the contents of the internal entry list of the FlowControl designated by &lt;Path&gt; for the Entry strategies Percentage or Cyclic Sequence , and writes it into a list.

Type

Method

Syntax

```simtalk
< Path >.getEntryList(EntryList:any) → boolean
```

Parameter

The parameter EntryList of data type any designates the name of the list.

Return Value

The return value has the data type boolean .

Examples

```simtalk
var li: list
MyFlowControl.getEntryList(li)
```

MyFlowControl1.setEntryList(li)

MyFlowControl.getEntryList(DataList)

SimTalk

setEntryList [SimTalk]

See also

Percentage [FlowControl, entry]

Cyclic Sequence [FlowControl, entry]

getExitList [SimTalk]

Returns the contents of the internal exit list of the FlowControl designated by &lt;Path&gt; for the Exit strategies Percentage or Cyclic Sequence , and writes it to a list.

Type

Method

Syntax

```simtalk
< Path >.getExitList(ExitList:any) → boolean
```

Parameter

The parameter ExitList of data type any designates the name of the list.

Return Value

The return value has the data type boolean .

Example

MyFlowControl.getExitList(DataList) MyFlowControl.setExitList(DataList.copy)

SimTalk

setExitList [SimTalk]

See also

Percentage [FlowControl, exit]

Cyclic Sequence [FlowControl, entry]

setAttributeList [SimTalk] - FlowControl

Sets the attribute list for the Exit strategy MU Attribute and MU Name of the FlowControl designated by &lt;Path&gt;.

Remarks

You can enter several numbers of the desired successors into the Attribute List for Attribute Value . In the non-blocking case Plant Simulation checks which of the desired successors can receive the MU .

Type

Method

Syntax

&lt; Path &gt;.setAttributeList(AttributeList:table)

Parameter

The parameter AttributeList of data type table designates the path to a list or a variable of the same data type. Plant Simulation then copies the contents of the passed list to the internal attribute list of the FlowControl .

Example

MyFlowControl.setAttributeList(tab1)

SimTalk

getAttributeList [SimTalk] - FlowControl

See also

MU Attribute [FlowControl, exit]

MU Name

Data Held in Tabular Form in Attributes [material flow objects]

setEntryList [SimTalk]

Sets the entry list of the FlowControl designated by &lt;Path&gt; for the Entry Strategy &gt; Percentage or Cyclic Sequence .

Type

Method

Syntax

< Path >.setEntryList(EntryList:any)

Parameter

The parameter EntryList of data type any designates the path to a list or a variable of the same data type. Plant Simulation then copies the contents of the passed list to the internal entry list of the FlowControl .

Example

MyFlowControl.setEntryList(DataList) MyFlowControl.setEntryList(DataList.copy)

SimTalk

getEntryList [SimTalk]

See also

Cyclic Sequence [FlowControl, entry]

Percentage [FlowControl, entry]

Data Held in Tabular Form in Attributes [material flow objects]

##### setExitList [SimTalk]

setExitList [SimTalk]

Sets the exit list of the FlowControl designated by &lt;Path&gt; for the Exit Strategy &gt; Percentage or Cyclic Sequence .

Type

Method

Syntax

< Path >.setExitList(ExitList:any)

Parameter

The parameter ExitList of data type any designates the path to a list or a variable of the same data type.

Plant Simulation then copies the contents of the passed list to the internal exit list of the FlowControl .

Example

MyFlowControl.setExitList(DataList) MyFlowControl.setExitList(DataList.copy)

SimTalk

getExitList [SimTalk]

See also

Cyclic Sequence [FlowControl, entry]

Percentage [FlowControl, exit]

Data Held in Tabular Form in Attributes [material flow objects]

#### Read-Only Attributes of the FlowControl

Read-Only Attributes of the FlowControl

The FlowControl provides the \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyFlowControl.UUID

#### Attributes of the FlowControl

\_Attributes of the FlowControl

The FlowControl provides:

- The attributes listed in the table of contents to the left.
- The Attributes of All Objects .

As the FlowControl cannot receive any MUs , it does not have the attributes that the other material flow objects provide.

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
flowcontrol.name := "MyFlowControl"
print flowcontrol.DefaultSuccessor
posit := MyStation.Cont.XPos
```

##### AttributeType [SimTalk] - FlowControl

Sets the data type of the attribute that determines how the FlowControl designated by &lt;Path&gt; moves the MUs on.

Remarks

AttributeType applies to the Exit Strategy &gt; MU Attribute .

Type

Attribute

Syntax

```simtalk
< Path >.AttributeType:string
```

**Assignment Value**

You can assign a value of data type string .

<!-- image -->

**Example**

MyFlowControl.AttributeType := "integer"

**See also**

MU Attribute [FlowControl, exit]

##### DefaultSuccessor [SimTalk] - FlowControl

Sets the number of the default successor to which the FlowControl designated by &lt;Path&gt; moves the MUs .

Remarks

DefaultSuccessor applies if none of the MUs has an attribute with the Value you entered into the DataTable . To not move a MU , which does not meet one of the conditions on the table, specify 0 .

To show a message, when a MU is to be moved which does not meet any of the conditions in the DataTable , specify -1 .

Type

Attribute

Syntax

&lt; Path &gt;.DefaultSuccessor:integer

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MyFlowControl.DefaultSuccessor := 1
```

See also

MU Attribute [FlowControl, exit]

MU Name

##### EntryBehavior [SimTalk]

Sets the strategy according to which the FlowControl designated by &lt;Path&gt; receives the MUs from its predecessors.

Type

Attribute

Syntax

&lt; Path &gt;.EntryBehavior:string

Assignment Value

You can assign a value of data type string .

- To cyclically receive the MUs from all predecessors, assign Cyclic .
- To cyclically receive the MUs from the predecessor according to the sequence of predecessors, which you typed into the list, assign Cyclic Sequence .
- To receive the MUs from the predecessor in the order in which they intended to exit, assign First come, first served .
- To receive the MUs from the predecessor that has not provided a MU for the longest time, assign Least recently used .
- To receive the MUs from the predecessor defined by the return value of a Method , assign Method .
- To receive the MUs from the predecessor, from which the FlowControl received a MU the last time, assign Most recently used .
- To receive the MUs from the predecessors according to a percentage distribution, assign Percentage .
- To receive the MUs from the predecessors in a random fashion, assign Random .
- To receive the MUs from the predecessors according to the state and the material flow balance of the predecessors, assign Selection . Then, assign a Property .
- To receive the MUs from the first available predecessor, assign Start at Predecessor 1 .

**Example**

MyFlowControl.EntryBehavior := "random"

See also

Strategy [FlowControl, entry]

**EntryBlocking [SimTalk]**

**EntryBlocking [SimTalk]**

Sets if the FlowControl designated by &lt;Path&gt; uses blocking behavior if a MU enters the FlowControl ( true ) or not ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.EntryBlocking:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyFlowControl.entryBlocking := true

See also

Blocking [FlowControl, entry]

##### EntryDistribution [SimTalk]

Sets the random number distribution of the FlowControl designated by &lt;Path&gt;.

Remarks

EntryDistribution applies when you set the attribute EntryBehavior to Random .

Type

Attribute

Syntax

&lt; Path &gt;.EntryDistribution:time

Assignment Value

You can assign a value of data type time .

Example

```simtalk
MyFlowControl.EntryBehavior := "random"
MyFlowControl.EntryDistribution.Type := "normal"
MyFlowControl.EntryDistribution.Mu := 5
MyFlowControl.EntryDistribution.Sigma := 1
```

See also

EntryBehavior [SimTalk]

Random [FlowControl, entry]

##### EntrySelectionMethod [SimTalk]

Sets the name of the Method object, which the FlowControl designated by &lt;Path&gt; uses.

Remarks

EntrySelectionMethod applies when you set the attribute EntryBehavior to Method .

**Note**

You cannot move or delete MUs in the Method because Plant Simulation runs the Method like a formula. For this reason Plant Simulation does not show the tab Expressions of the Method Debugger .

In addition, you cannot use a wait-instruction , a waituntil-instruction , or a stopuntil-instruction within the Method .

Type

Attribute

Syntax

&lt; Path &gt;.EntrySelectionMethod:method

Assignment Value

You can assign a value of data type method .

Example

```simtalk
MyFlowControl.EntryBehavior := "method"
MyFlowControl.EntrySelectionMethod := &myMethod
```

See also

EntryBehavior [SimTalk]

Method [FlowControl, entry]

Tab Expressions [Watch window]

##### EntrySelectionProperty [SimTalk]

Sets the selection criterion, which the FlowControl designated by &lt;Path&gt; uses.

Remarks

EntrySelectionProperty applies when you set the attribute EntryBehavior to Selection .

Type

Attribute

Syntax

```simtalk
< Path >.EntrySelectionProperty:string
```

**Assignment Value**

You can assign a value of data type string .

You can specify "Max. Contents" , "Min. Contents" , "Max. Proc. Time" , "Min. Proc. Time" , "Max. Num. Out" , "Min. Num. Out" , "Max. Rel. Occu." , or "Min. Rel. Occu." .

**Example**

```simtalk
MyFlowControl.EntryBehavior := "selection"
MyFlowControl.EntrySelectionProperty := "Max. Contents"
```

See also

EntryBehavior [SimTalk]

Selection [FlowControl, entry]

##### ExitBehavior [SimTalk]

Sets the strategy according to which the FlowControl designated by &lt;Path&gt; moves the MUs on its successors.

Type

Attribute

Syntax

&lt; Path &gt;.ExitBehavior:string

**Assignment Value**

You can assign a value of data type string .

- The strategy Assignment does not determine the successor to which the FlowControl moves the MU . Instead, you can change the values of the attributes of the MU , when it moves to the one and only successor of the FlowControl . As soon as the MU is moved on to the successor, Plant Simulation calls the Method , whose name you entered into the text box Method . Define the assignments to be made in this Method .
- To move the MUs cyclically on to all successors, assign Cyclic .
- To cyclically move the MUs on to the successor according to the sequence of successors, which you typed into a list, assign Cyclic Sequence .
- To move the MUs on to the successor, which has been Waiting the longest for a MU , assign Least recently used .
- To move the MUs on to a successor according to the return value of a Method , assign Method .

**Note**

You cannot move or delete MUs in the Method because Plant Simulation runs the Method like a formula. For this reason Plant Simulation does not show the tab Expressions of the Method Debugger .

In addition, you cannot use a wait-instruction , a waituntil-instruction , and a stopuntil-instruction within the Method .

- To move the MUs on to the successor, which has Waiting the shortest time for a MU , assign Most recently used .
- To move the MUs on to a successor according to the values of attributes of the MUs , assign MU Attribute .
- To move the MUs on to a successor according to their names, assign MU Name .
- To move the MUs on to a successor according to a percentage distribution, assign Percentage .

- To move the MUs on to a randomly selected successor, assign Random .
- To move the MUs on to the successor meeting a certain Property , assign Selection . Then, assign a Property .
- To move the MUs on to the first available successor, assign Start at Successor 1 .
- To copy the MUs that enter, and move a copy each to each of the successors, assign To all Successors .

**Example**

MyFlowControl.ExitBehavior := "random"

**See also**

Strategy [FlowControl, exit]

##### ExitBlocking [SimTalk]

Sets if the FlowControl designated by &lt;Path&gt; uses blocking behavior.

Remarks

ExitBlocking applies if a MU exits the FlowControl ( true ) or not ( false ).

**Note**

The non-blocking strategy of the setting Exit strategy &gt; MU attribute moves the part on when any of the desired successors can receive it.

Type

Attribute

Syntax

&lt; Path &gt;.ExitBlocking:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyFlowControl.ExitBlocking := true

See also

Blocking [FlowControl, exit]

MU Attribute [FlowControl, exit]

##### ExitDistribution [SimTalk]

Sets the random number distribution which the FlowControl designated by &lt;Path&gt; uses.

Remarks

ExitDistribution applies when you set the attribute ExitBehavior to "Random" .

Type

Attribute

Syntax

&lt; Path &gt;.ExitDistribution:randTime

Assignment Value

You can assign a value of data type time .

Example

```simtalk
MyFlowControl.ExitBehavior := "random"
MyFlowControl.ExitDistribution.Type := "normal"
MyFlowControl.ExitDistribution.Mu := 5
MyFlowControl.ExitDistribution.Sigma := 1
```

See also

ExitBehavior [SimTalk]

Random [FlowControl, exit]

##### ExitSelectionMethod [SimTalk]

Sets the name of the Method object, which the FlowControl designated by &lt;Path&gt; uses.

Remarks

ExitSelectionMethod applies when you set the attribute ExitBehavior to Method .

**Note**

You cannot move or delete MUs in the Method because Plant Simulation runs the Method like a formula. For this reason Plant Simulation does not show the tab Expressions of the Method Debugger .

In addition, you cannot use a wait-instruction , a waituntil-instruction , or a stopuntil-instruction within the Method .

Type

Attribute

Syntax

&lt; Path &gt;.ExitSelectionMethod:method

Assignment Value

You can assign a value of data type method .

Example

```simtalk
MyFlowControl.ExitBehavior := "method"
MyFlowControl.ExitSelectionMethod := &myMethod
```

See also

ExitBehavior [SimTalk]

Method [FlowControl, exit]

Tab Expressions [Watch window]

##### ExitSelectionProperty [SimTalk]

Sets the selection property, which the FlowControl uses.

Remarks

ExitSelectionProperty applies when you set the attribute ExitBehavior to Selection .

Type

Attribute

Syntax

```simtalk
< Path >.ExitSelectionProperty:string
```

**Assignment Value**

You can assign a value of data type string .

You can specify "Max. Contents" , "Min. Contents" , "Max. Rel. Occu." , "Min. Rel. Occu." , "Max. Num. In" , "Min. Num. In" , "Max. Proc. Time" , "Min. Proc. Time" , "Max. Set-up Time" , or "Min. Set-up Time" .

**Example**

```simtalk
MyFlowControl.ExitBehavior := "Selection"
MyFlowControl.ExitSelectionProperty := "Max. contents"
```

See also

ExitBehavior [SimTalk]

Selection [FlowControl, exit]

#### Cycle

