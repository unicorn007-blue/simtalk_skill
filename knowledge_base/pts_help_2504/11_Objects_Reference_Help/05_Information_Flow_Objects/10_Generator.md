### Generator

Use the Generator for activating Method objects for the time you specify to create MUs in regular or in statistically distributed intervals.

Icon

<!-- image -->

Description

Specify the Start and the Stop time and the time interval which you specify for the Interval Control to create the MUs . After the time span you specify for the Duration , has elapsed, Plant Simulation calls the Method object you specified as the Duration Control on the tab Controls . Interval and Duration always appear in pairs.

You can specify the times as a fixed interval or as a probability distribution. You can also limit the probability distributions to a segment of the entire range.

To show a tooltip with information about the Generator , hover with the mouse over it.

<!-- image -->

To change the length of the graphic and the anchor points of the Generator , click Show Manipulators

<!-- image -->

on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the Generator to your simulation model, click Manage Class Library &gt; Basic Objects &gt; InformationFlow &gt; Generator on the Home ribbon tab.

#### Dialog Box of the Generator

Dialog Box of the Generator

Double-click the icon of the Generator to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

<!-- image -->

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Tab Times

Tab Times

You can type a constant time or a probability distribution for the Start time, the Stop time, the Interval , and the Duration of the instructions which you programmed in the Interval Control and the Duration Control .

Some settings require a probability distribution and additional parameters. Select a distribution from the drop-down list and type the values which this distribution requires into the text box. Plant Simulation shows the parameters along the upper border of the tab. You can also type in a constant time ( Const ).

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr .

See also

Probability Distributions

Empirical Distributions

User-defined Distributions

###### Active [check box] - Generator

Active [check box] - Generator

To activate the Generator , select Active .

<!-- image -->

To deactivate it, clear the check box.

SimTalk

Active [SimTalk] - Generator

###### Start [text box] - Generator

Type in the time at which the Generator activates the Interval Control for the first time.

<!-- image -->

If you type in 0 as the Start Time and a value greater than 0 for the Interval , Plant Simulation triggers the control immediately after you started the simulation.

You can also select any of the probability distributions. Then, you have to type in the parameters, which the selected distribution requires.

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr .

Generator.Start.setTypeAndAttr("Normal", 30, 10)

SimTalk

Start [SimTalk] - Generator

IntervalCtrl [SimTalk]

putAttributeNamesIntoTable [SimTalk] - objects

See also

Interval Control [Generator]

###### Stop [text box] - Generator

Stop [text box] - Generator

Type in the time at which the Generator activates the Interval Control for the last time.

<!-- image -->

As Interval and Duration always appear in pairs, the Duration Control may be activated even after the time you type in here. If you do not want any time limit to apply for activating the Interval Control , type in 0 .

You can also select any of the probability distributions. Then, you have to type in the parameters, which the selected distribution requires.

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr .

Generator.Stop.setTypeAndAttr("Normal", 1:00, 10)

SimTalk

Stop [SimTalk] - Generator

IntervalCtrl [SimTalk]

putAttributeNamesIntoTable [SimTalk] - objects

See also

Interval Control [Generator]

Interval [text box] - Generator

Type in the Interval , i.e., the time between two activations of the Interval Control .

<!-- image -->

If you type in 0 , Plant Simulation does not trigger any controls and stops the Generator .

You can also select any of the probability distributions. Then, you have to type in the parameters, which the selected distribution requires.

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr .

Generator.Interval.setTypeAndAttr("dEmp", Table)

SimTalk

Interval [SimTalk] - Generator

IntervalCtrl [SimTalk]

putAttributeNamesIntoTable [SimTalk] - objects

See also

Interval Control [Generator]

Duration [text box] - Generator

Type in the Duration , i.e., the time span between activating the Interval Control and the Duration Control .

<!-- image -->

You can also select any of the probability distributions. Then, you have to type in the parameters, which the selected distribution requires.

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr .

Generator.Duration.setTypeAndAttr("cEmp", Table)

SimTalk

Duration [SimTalk] - Generator

IntervalCtrl [SimTalk]

DurationCtrl [SimTalk]

putAttributeNamesIntoTable [SimTalk] - objects

See also

Interval Control [Generator]

Duration Control [Generator]

Tab Controls

Tab Controls

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the respective control.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

You can create an Entrance Control , an Exit Control , and a Set-up Control .

**Create a Control that is a Method of the Object**

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

**See also**

**Interval Control [Generator]**

Duration Control [Generator]

**Interval Control [Generator]**

###### Interval Control [Generator]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Interval Control , which is called according to the intervals which you specified as the Interval .

<!-- image -->

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

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

**SimTalk**

IntervalCtrl [SimTalk]

**See also Select Object [for controls]**

###### Interval [text box] - Generator

**Duration Control [Generator]**

###### Duration Control [Generator]

Click the ellipsis button and select a Method object in the dialog Select Object . Type in the source code of the Duration Control , which is called after the specified time span of the Duration (depending on the Interval ), has elapsed.

<!-- image -->

Plant Simulation calls the Duration Control after the Interval Control . The Duration Control may be activated for the last time even after the time you entered as the Stop Time .

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

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

SimTalk DurationCtrl [SimTalk] See also Select Object [for controls] Stop [text box] - Generator Duration [text box] - Generator

Interval [text box] - Generator

**Tab User-defined**

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

##### Navigate Menu

The commands are described under the Navigate Menu .

##### View Menu

View Menu

The View Menu provides commands to access its functions. Refresh [on View menu] Show Attributes and Methods [on View menu] SimTalk updateDialog [SimTalk] See also View Menu [general description]

Tools Menu

The Tools Menu provides these menu commands: Edit Controls Edit Observers 3D

##### Help Menu

The commands are described under the Help Menu .

##### Methods of the Generator

#### Methods of the Generator

The Generator provides the Methods of All Objects .

To view all of the methods , read-only attributes and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

An example of the Syntax line of the individual methods might look like this:

<!-- image -->

- The expression &lt;Path&gt; designates the path of the object to which the method applies.
- The signature of the method, consisting of the identifier and the data type of the parameter, is listed in parentheses. The expression (Parameter:string) , for example, designates a parameter of data type string . Instead of a constant value, you can also use a variable of the required type or a method that returns the required data type.

**Note**

Make sure to enter the parentheses for expressions within parentheses (…). Not entering them may lead to unexpected results and open the Debugger .

Optional parameters are listed within brackets. The expression [,Parameter:boolean] , for example, means that you can, but do not have to enter the boolean parameter.

If a parameter has a default value, the signature shows the default value after the parameter.

If the method has a return value, the signature shows its data type after the arrow -&gt;.

#### Read-Only Attributes of the Generator

Read-Only Attributes of the Generator

The Generator provides the \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .

#### Attributes of the Generator

- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyGenerator.UUID

**Attributes of the Generator**

##### \_Attributes of the Generator

The Generator provides:

- The attributes listed in the table of contents to the left.
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyGenerator.Duration.Type := "uniform"
MyGenerator.Duration.Start := 600 // from 10 minutes
MyGenerator.Duration.Stop := 1200 // to 20 minutes
print MyGenerator.Duration.Type
posit := Station.Cont.XPos
```

Active [SimTalk] - Generator

Active [SimTalk] - Generator

Activates the object designated by &lt;Path&gt; ( true ) or deactivates it ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.Active:boolean

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

Example

MyGenerator.Active := true

See also

Active [check box] - Generator

##### Duration [SimTalk] - Generator

Sets the time span between which the Generator designated by &lt;Path&gt; calls the Interval Control and the Duration Control .

Type

Attribute

Syntax

< Path >.Duration:time

Assignment Value

You can assign a value of data type time .

Examples

```simtalk
MyGenerator.Duration.Type := "uniform"
MyGenerator.Duration.Start := 600 // from 10 minutes
MyGenerator.Duration.Stop := 1200 // to 20 minutes
```

Generator.Duration.setTypeAndAttr("cEmp", Table)

SimTalk

DurationCtrl [SimTalk]

See also

Duration [text box] - Generator

Duration Control [Generator]

Interval Control [Generator]

**DurationCtrl [SimTalk]**

##### DurationCtrl [SimTalk]

Designates a Method object of the object designated by &lt;Path&gt;. Plant Simulation runs the Method after it called the Interval Control of the Generator designated by &lt;Path&gt;.

Type

Attribute

Syntax

< Path >.DurationCtrl:method

Assignment Value

You can assign a value of data type method .

Example

```simtalk
// does an entry exist?
if MyGenerator.DurationCtrl /= VOID // delete entry
	MyGenerator.DurationCtrl := VOID
end
```

See also

Duration Control [Generator]

Interval [SimTalk] - Generator

Sets the time between two activations of the Interval Control of the Generator designated by &lt;Path&gt;.

Type

Attribute

Syntax

< Path >.Interval:time

Assignment Value

You can assign a value of data type time .

Examples

```simtalk
obj.Interval.Type:= "Negexp"
obj.Interval.Beta:=150
obj.Interval.LowerBound:=1*60   // 1s *60
obj.Interval.UpperBound:= 10*60 // 10s *60
```

Generator.Interval.setTypeAndAttr("dEmp", Table)

SimTalk

IntervalCtrl [SimTalk]

See also

Interval [text box] - Generator

Interval Control [Generator]

**IntervalCtrl [SimTalk]**

##### IntervalCtrl [SimTalk]

Designates a Method object of the object designated by &lt;Path&gt;. Plant Simulation runs the Method during the specified interval for the Generator designated by &lt;Path&gt;.

Type

Attribute

Syntax

< Path >.IntervalCtrl:method

Assignment Value

You can assign a value of data type method .

Example

```simtalk
// nothing entered yet?
if MyGenerator.IntervalCtrl = VOID // enter reference to method
	MyGenerator.IntervalCtrl := &MyMethod
end
```

See also

Interval Control [Generator]

##### Start [SimTalk] - Generator

Sets the Start time of the Interval Control which the Generator designated by &lt;Path&gt; calls.

Remarks

The assignment has to be made during the Reset phase.

Type

Attribute

Syntax

< Path >.Start:time

Assignment Value

You can assign a value of data type time .

Examples

```simtalk
MyPlant.MyGenerator.Start.type := "const"
MyPlant.MyGenerator.Start := 120 // 2 minutes
```

Generator.Start.setTypeAndAttr("Normal", 30, 10)

See also

Start [text box] - Generator

Interval Control [Generator]

##### Stop [SimTalk] - Generator

Stop [SimTalk] - Generator

Sets the Stop time of the Interval Control which the Generator designated by &lt;Path&gt; calls.

Type

Attribute

Syntax

< Path >.Stop:time

Assignment Value

You can assign a value of data type time .

**Examples**

```simtalk
// normally distributed end with left bound at 1 hour // and open right bound .InformationFlow.MyGenerator.Stop.Type := "normal"   // normal distribution .InformationFlow.MyGenerator.Stop.Mu := 3600         // 1 hour .InformationFlow.MyGenerator.Stop.Sigma := 600       // 10 minutes .InformationFlow.MyGenerator.Stop.LowerBound := 1200 // 20 minutes .InformationFlow.MyGenerator.Stop.UpperBound := 7200 // 2 hours
```

Generator.Stop.setTypeAndAttr("Normal", 1:00, 10)

See also

Stop [text box] - Generator

Interval Control [Generator]

