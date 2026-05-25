## Console

The Console shows information about actions, which Plant Simulation executes.

You can select which information the Console window shows under File &gt; Preferences &gt; User Interface &gt; Console Filter .

<!-- image -->

To record messages, display the Console by clicking messages, hide it.

on the

Window

ribbon tab. To not record

<!-- image -->

To close the Console window, click the X in the title bar of the window. To show it again, click on the Window ribbon tab.

<!-- image -->

To auto hide the Console , click . When you then click in another window, Plant Simulation hides the window until you move the mouse over the name of the window again. To deactivate Auto Hide , click .

The context menu of the Console window provides these commands:

<!-- image -->

- To copy the contents of the Console window, select the text it contains and then select Copy .
- To delete the contents of the Console window, select Clear .
- To select the entire text in the Console window, select Select All .
- Show Print Output

To show output from print commands in Methods , select this command.

**· Show Info Output**

To show text, which is displayed in info boxes, such as those shown during the reset and init phases of the model, select this command. In addition, it includes warnings, for example when you use a no-longer-supported attribute in a method. When you start Plant Simulation with the command-line parameter -NoWarning , it does not write any of the above to the Console .

**Console**

**· Show Message Output**

To show miscellaneous messages, select this command.

**· Show Debug Output**

To show additional information and internal program messages, such as potential problems, select this command. When you start Plant Simulation with the command-line parameter -NoWarning , it does not write any of the above to the Console .

Plant Simulation also counts all of the built-in objects, which are contained in the entire model, i.e., in the Class Library and in all Frames . It does not count these objects: Lists and Tables , Methods , Variables , MUs , and Connectors .

You might want to know this number if you are working with a Plant Simulation Standard License which is limited to 4000 objects.

If the Console window shows a path to an object, you can open this object by double-clicking the respective line.

**Note**

The open Console window may slow down your simulation model!

**SimTalk**

clearConsole [SimTalk]

closeConsole [SimTalk]

openConsole [SimTalk]

setConsoleFilter [SimTalk]

**See also**

File &gt; Preferences &gt; User Interface &gt; Console Filter

Specifying Start Options , -Logfile File

Specifying Start Options , -NoWarning

Moving Docking Windows

numOfLimitedObjects

**Video on YouTube**

[https://youtu.be/MXDcx2yplxc?si=7AMwbDavKOHYRNRA&amp;t=245](https://youtu.be/MXDcx2yplxc?si=7AMwbDavKOHYRNRA&t=245)

