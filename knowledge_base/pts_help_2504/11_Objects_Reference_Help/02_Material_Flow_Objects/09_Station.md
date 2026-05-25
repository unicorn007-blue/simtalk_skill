### Station

#### Station [object]

Use the Station for processing parts on a single processing place. You'll use it for modeling most of your machines.

Icon

<!-- image -->

**Description**

The Station receives a single MU from its predecessor, processes it and moves it on to one of its successors after the set-up time and the processing time has elapsed. If the types of MUs are not identical, i.e., if they do not have the same name, the Station has to set up to process this new type of MU . While a part is located on the Station , it does not receive any additional parts but enters them into its Blocking List . It only accepts the blocked MUs one after the other and processes them after it is available again.

If the Station has several successors, it moves the MUs one after the other onto them. If the successor to which the part is to be moved is blocked, meaning it is full or failed, the Station does not select another available successor onto which it moves the part. Instead, it does not move the part and thus is blocked . It only moves the part after the successor becomes available again and is not blocked any longer, it moves the part and will then be unblocked. You can set a different moving behavior with a Method .

**Note**

Plant Simulation always moves the MU as a whole not continually, i.e., as soon as its front, better its booking point, is located on the Station , the entire MU is located on it.

To show a tooltip with information about the Station , hover with the mouse over it.

<!-- image -->

**Show Manipulators**

To change the length of the graphic and the anchor points of the object, click Show Manipulators on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

You can use the manipulators to change the dimensions of the object by editing its position or its scaling.

<!-- image -->

**Add the Object to the Simulation Model**

To add the Station to your simulation model, click MaterialFlow &gt; Station on the Home ribbon tab.

Manage Class Library &gt; Basic Objects &gt;

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

As the Station is such a central object in Plant Simulation , it figures prominently in a number of topics in the Step-by-Step Help .

See also

Transfer Parts from Station to Station

Set a Station Up

Define Processing Times

Model Failures

#### Dialog Box of the Station

Dialog Box of the Station

Double-click the icon of the Station to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Video on YouTube

[https://youtu.be/PQhEriOzVzU?si=HpfLhwtUyoiMFPzx&amp;t=22](https://youtu.be/PQhEriOzVzU?si=HpfLhwtUyoiMFPzx&t=22)

Tab Times

Define Times as described under the Tab Times .

Select a distribution from the drop-down list and type the values that this distribution requires into the text box. Plant Simulation shows the parameters along the upper border of the tab. You can also select a constant time ( Const ).

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr .

See also

Define Processing Times

Select the Set-Up Time

Processing Time [general description]

Set-up Time [general description]

Recovery Time [general description]

Recovery Time Starts

Cycle Time [general description]

**Tab Set-Up**

##### Tab Set-Up

Define properties for setting the object up as described under the Tab Set-Up .

##### Tab Failures

Define failures as described under the Tab Failures .

##### Tab Controls

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the respective control.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

You can create an Entrance Control , an Exit Control , a Pull Control , and a Target Control .

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

In addition, you can select the Shift calendar .

See also

Select Object [for controls]

Entrance Control [general description]

Exit Control [general description]

**Pull Control [general description]**

**Target Control [Turntable]**

##### Tab Exit

Tab Exit

Select to which of its successors the object moves the MU on the Tab Exit .

See also

Blocking [exit strategy]

Strategy [material flow objects]

##### Tab Statistics

Statistics is described under the Tab Statistics .

To view Resource Statistics of Stationary Resources in the Statistics Report , select View &gt; Show Statistics Report in the dialog of the object. You can also click the right mouse button in the Frame and select Show Statistics Report or you can press F6 .

<!-- image -->

**See also**

Statistics Report [described]

Resource Statistics [check box]

Resource Type

**Tab Importer**

##### Tab Importer

On the Tab Importer you can define services for processing the parts, for setting the station up for a certain type of part, and for repairing the station.

To view Importer Statistics in the Statistics Report , click the object in the Frame , and press F6 ( Show Statistics Report ), or click Show Statistics Report on the Home ribbon tab.

You can also click the object in the Frame with the right mouse button and select Show Statistics Report on the context menu.

<!-- image -->

**See also**

Processing Importer

Set-up Importer

Failure Importer

Transport Importer

##### Tab Energy

Select energy settings for the object on the Tab Energy .

##### Tab Costs

Tab Costs

Select costs settings for the object on the Tab Costs .

While the Station processes a part costs accrue which result from the sum of the investment costs and the operating costs.

**Note**

The investment costs only accrue during the Depreciation Period .

The costs are allocated to the part as accrued costs .

If the Station is empty, the costs remain with the Station as general costs .

See also

CostAnalyzer &gt; How the CostAnalyzer Assigns Costs to Part Types

CostAnalyzer &gt; Costs Shown in the Costs Report

Simulate the Accrued Costs of the Machines

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

**Navigate Menu**

##### Navigate Menu

The commands are described under the Navigate Menu .

View Menu

##### View Menu

The View Menu provides commands to access its functions.

| Refresh                     | Exporters                 |
|-----------------------------|---------------------------|
| Show Statistics Report      | Services                  |
| Show Attributes and Methods | Unavailable Services      |
| Contents                    | Associated Workplaces     |
| Forward Blocking List       | Associated Lockout Zones  |
| Exit Blocking List          | Associated Shift Calendar |

###### Exporters [Station]

Opens a table showing the names of all Exporters exporting services at the moment.

<!-- image -->

**Services [Station]**

###### Services [Station]

Opens a table showing the names of all imported services. The name of the failure service is identical with the name of the subtable.

<!-- image -->

Double-click the name of the service to open the subtable. Column 1 contains the Name of the Exporter , the column Amount the number of services provided.

<!-- image -->

<!-- image -->

###### Unavailable Services [Station]

Opens a table showing the names of the Failure Service , tne Set-up Service , the Processing Service , and the Transport Service that is unavailable at the moment.

<!-- image -->

The table shows the name of the unavailable service white on a red background in the respective cell.

<!-- image -->

Double-click the name of the service to open the subtable. Its columns show the Name of the Exporter , the Amount of services defined, the Amount of services missing, and the Name of the associated Alternative .

**See also**

Start/Stop Simulation [EventDebugger]

###### Associated Workplaces [Station]

Opens a list showing the names of all the Workplaces , which are assigned to the selected Station .

<!-- image -->

##### Tools Menu

The commands are described under the Tools Menu .

**Tabs Menu**

##### Tabs Menu

Use the commands of the Tabs menu to show or hide individual tabs of the material flow objects. If you hide tabs that you do not need, Plant Simulation opens the dialog faster, and you can change to those tabs faster that you need in your daily work.

To apply the changed settings, click OK , close the dialog, and reopen it

The menu shows a check mark to the left of the displayed tabs.

The command Inherit turns inheritance of the displayed or hidden tabs in the dialog off or on.

<!-- image -->

##### Help Menu

The commands are described under the Help Menu .

##### Methods of the Station

#### Methods of the Station

The Station provides:

- The Methods of All Objects .
- The Methods of the Material Flow Objects .

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

#### Read-Only Attributes of the Station

Read-Only Attributes of the Station

The Station provides:

- The \_Read-Only Attributes of All Objects .
- The Read-Only Attributes of the Material Flow Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

<!-- image -->

##### Attributes of the Station

#### Attributes of the Station

The Station provides:

- The Attributes of All Objects .
- The Attributes of the Material Flow Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

#### ParallelStation

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyStation.Pause := true
print MyStation.Pause
posit := MyStation.Cont.XPos
```

**ParallelStation**

