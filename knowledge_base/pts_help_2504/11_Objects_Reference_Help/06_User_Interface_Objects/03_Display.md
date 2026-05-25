### Display

#### Display [object]

Use the Display for presenting current data and results of the simulation run. The Display shows a value, for example of an attribute, at all times throughout the entire simulation run.

**Icon**

<!-- image -->

**Description**

If the Display is not active , Plant Simulation shows its icon in the Frame , into which you inserted it. If it is active, the Display shows a value. In Sample mode it updates its display periodically, in Watch mode it update it when the displayed value changes.

The Display shows the value either as text (string), as a bar or as a slice of a pie. Bar and pie display are only supported for numerical values. They are easy to comprehend, but not very well suited if accuracy is important.

For bar or pie representation the Display shows the value in relation to a specified range. An empty bar/pie indicates values less-than or equal to the lower bound of the range. A full bar/pie represents values beyond or equal to the upper bound of the range. Modify the overall size of the bar/pie representation by dragging its outline with the left mouse button while holding both the Shift and the Ctrl keys down.

The Display shows the actual minimal and maximal values as dashed lines which is not very accurate. In Bar and Pie mode it shows the current values in the text boxes Minimum and Maximum on the tab Data .

You can also show the numerical value of a Display in an HtmlReport , compare Display an Object of Type Display .

**Note**

The Display only shows values if MUs and States is activated

.

<!-- image -->

If MUs and States is deactivated, Plant Simulation prevents updating a number of values during the simulation, for example of objects of type Variable or Display .

**Drag-and-Drop for Display Objects**

Use drag-and-drop to accomplish these tasks:

| To                                            | Drag                     | To the   |
|-----------------------------------------------|--------------------------|----------|
| Show the statistics of a material flow object | the material flow object | Display  |
| Show the current value of a Variable          | the Variable             | Display  |

To show a tooltip with information about the Display , hover with the mouse over it.

<!-- image -->

To change the length of the graphic and the anchor points of the Display , click Show Manipulators on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the Display to your simulation model, click Manage Class Library &gt; Basic Objects &gt; UserInterface &gt; Display on the Home ribbon tab.

See also

Show Values During the Simulation with the Display

#### Dialog Box of the Display

Dialog Box of the Display

Double-click the icon of the Display to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

<!-- image -->

<!-- image -->

**See also**

**Active [check box] - Display**

##### Active [check box] - Display

Active [check box] - Display

To activate the display of the Display , select this check box.

<!-- image -->

If the Display is not active, Plant Simulation shows its Name in the Frame instead of a Value .

<!-- image -->

To deactivate it, clear the check box or select Deactivate on the context menu.

Instead, you can also right-click the Display object in the Frame and select Activate on the context menu.

SimTalk

Active [SimTalk] - Display

Tab Data

Tab Data

The tab Data provides the settings listed in the table of contents to the left.

Path [text box] - Display

Click the ellipsis button and select the attribute or the method in the dialog Select Object whose value the Display displays.

<!-- image -->

If you want to show the value of a global variable, you can type in the path to the Variable itself. You can also type in an expression, such as buffer.NumMU+1 .

The Display supports the data types boolean, integer, real, string, object, time, money, length, weight, speed, date , and dateTime . If the path you type in is invalid, the background of the text box changes to red.

Note

F2 opens the dialog of the object, whose name you typed into the text box.

SimTalk

Path [SimTalk] - Display

See also

Select Object [for controls]

**Comment [text box] - Display**

###### Comment [text box] - Display

Type in a brief description of the displayed value into the text box Comment .

<!-- image -->

You might, for example, type in the name of the attribute that the Display displays, such as Fill Level Buffer .

The Display shows this text below the value in the Frame window.

<!-- image -->

SimTalk

Comment [SimTalk] - Display

<!-- image -->

- Sample mode updates the display with the frequency you type into the text box Interval .
- Watch mode updates the displayed value each and every time the value changes. If the path and the value you typed in is not watchable , Plant Simulation does not update the display.

The column Watchable in the window Show Attributes and Methods shows which attributes and read-only attributes Plant Simulation can watch.

**SimTalk**

Sampler [SimTalk]

SmpPeriod [SimTalk] - Display

See also

DisplayType [SimTalk]

update [SimTalk] - Display

###### Interval [text box] - Display

Interval [text box] - Display

For Sample Mode the Display shows the text box Interval .

<!-- image -->

Type in the update frequency of the display into the text box. The format is the normal time format.

SimTalk

SmpPeriod [SimTalk] - Display

See also

Mode [drop-down list] - Display

Value [Display]

For Bar or Pie mode, the Display shows the Current Value .

SimTalk

Value [SimTalk] - Display

**Minimum [Display]**

###### Minimum [Display]

For Bar or Pie mode, the Display shows the Minimum of the reached value.

SimTalk

GetMinimum [SimTalk]

GetMaximum [SimTalk]

resetMinMax [SimTalk]

###### Maximum [Display]

For Bar or Pie mode, the Display shows the Maximum of the reached value.

SimTalk

GetMaximum [SimTalk]

GetMinimum [SimTalk]

resetMinMax [SimTalk]

**Reset Values [button]**

###### Reset Values [button]

To reset the minimum and maximum values shown on the tab, click this button.

<!-- image -->

Tab Display

Tab Display

The tab Display provides the settings listed in the table of contents to the left.

<!-- image -->

Type [drop-down list] - Display

Select how the Display displays the data it records.

<!-- image -->

<!-- image -->

- Text shows the value as text. For floating point values you can type in the number of decimal places . The Display can show up to 15 decimal places. For the default setting -1 it shows all existing places. Type in a positive value to show this number of places in the Frame .
- Bar and Pie maps the value in relation to the Minimum and the Maximum of the range that you specify. They visualize values inside the range by the height of a bar or a filled segment of the pie. An empty bar/pie corresponds to values below or equal to the lower bound. A full bar/pie represents values above or equal to the upper bound. To change the height and the width of the bar/pie graphic, hold down the Shift and die Ctrl keys and drag the border of the graphic with the left mouse button.

<!-- image -->

Plant Simulation converts the current value to the range, whose bounds you type in and shows it averaged.

Type in the Maximum Value of the displayed range of values.

Type in the Minimum Value of the displayed range of values.

###### Type [drop-down list] - Display

<!-- image -->

The Display shows the actual Minimum and Maximum values as dotted lines in the Frame window. This might not be as accurate as you need them to be. The Display shows the current values on the tab Data in the text boxes Minimum and Maximum .

**Note**

The Display can only show numerical values as a bar or a piece of a pie. These are easy to understand but not necessarily suited if accuracy is important.

To reset the values on the tab to 0, click Reset Values on the tab Data .

SimTalk

DisplayType [SimTalk]

MinVal [SimTalk]

MaxVal [SimTalk]

See also

GetMaximum [SimTalk]

GetMinimum [SimTalk]

resetMinMax [SimTalk]

Font Size [drop-down list] - Display

Select the font size of the text which the Display displays for the Type &gt; Text .

<!-- image -->

Decimal Places [text box] - Display

If the Type &gt; Text shows floating point values you can type in the number of decimal places.

The Display can show up to 15 decimal places. For the default setting -1 shows all existing places. Type in a positive value to show this number of places in the Frame .

<!-- image -->

###### Color [Display]

To select the color of the text, which the Display shows, and the color of the outline of its display graphic, click the drop-down arrow.

<!-- image -->

You can select one of the predefined colors, or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation shows this color next to More Colors and uses it as the active color.

**SimTalk**

Color [SimTalk] - Display

###### Transparent [check box] - Display

Transparent [check box] - Display

To make the background of a Display , which you inserted into a Frame , transparent, select this check box.

<!-- image -->

Then, the Display shows the space around the text in the color of the background image, or it shows the grid points of the Frame .

To show the space around the text in white, clear the check box.

The setting Transparent also applies in 3D.

<!-- image -->

| Transparent   | Not transparent   |
|---------------|-------------------|

**SimTalk**

Transparent [SimTalk] - Display

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

**Navigate Menu**

##### Navigate Menu

The commands are described under the Navigate Menu .

##### View Menu

The commands are described under the

SimTalk

updateDialog [SimTalk]

View Menu

.

##### Tools Menu

Tools Menu

The Tools Menu provides commands to access its functions.

Edit Controls

Edit Observers

3D

See also

Tools Menu [general description]

##### Help Menu

The commands are described under the Help Menu .

**Methods of the Display**

#### \_Methods of the Display

The Display provides:

- The methods listed in the table of contents to the left.
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

##### resetMinMax [SimTalk]

Deletes the minimum and maximum values that the Display designated by &lt;Path&gt; shows and sets them back to their default values.

Type

Method

Syntax

&lt; Path &gt;.resetMinMax

Example

print MyDisplay.resetMinMax

See also

Reset Values [button]

update [SimTalk] - Display

update [SimTalk] - Display

Updates the value that the Display designated by &lt;Path&gt; shows after a certain time has elapsed.

Remarks

update is only useful in conjunction with Sample mode. You can use the method update to force the Display to display a current value, for example after you changed the input value.

To be compatible with previous versions of Plant Simulation , you can specify the parameter Time of data type time .

Method

Type

Method

Syntax

&lt; Path &gt;.update

Example

MyDisplay.update

See also

Interval [text box] - Display

#### Read-Only Attributes of the Display

\_Read-Only Attributes of the Display

The Display provides:

- The read-only attributes listed in the table of contents to the left.
- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyDisplay.GetMaximum

**GetAverage [SimTalk]**

##### GetAverage [SimTalk]

Returns the average value of the values that the Display designated by &lt;Path&gt; recorded.

Type

Read-only attribute

Syntax

```simtalk
< Path >.GetAverage → real
```

Return Value

The return value has the data type real .

Example

print MyDisplay.GetAverage

##### GetMaximum [SimTalk]

Returns the maximum value of the range of values that the Display designated by &lt;Path&gt; shows.

Remarks

Only use GetMaximum for Watch Mode . In Sample Mode Plant Simulation only updates the value if MUs and States is activated and the Frame , in which the Display is inserted, is open.

Type

Read-only attribute

Syntax

&lt; Path &gt;.GetMaximum → real

Return Value

The return value has the data type real .

Example

print MyDisplay.GetMaximum

SimTalk

GetMinimum [SimTalk]

resetMinMax [SimTalk]

See also

Maximum [Display]

Mode [drop-down list] - Display

MUs and States [Home ribbon]

<!-- image -->

**GetMinimum [SimTalk]**

##### GetMinimum [SimTalk]

Returns the minimum value of the range of values that the Display designated by &lt;Path&gt; shows.

Remarks

Only use GetMinimum for Watch Mode . In Sample Mode Plant Simulation only updates the value if MUs and States is activated and the Frame , in which the Display is inserted, is open.

Type

Read-only attribute

Syntax

&lt; Path &gt;.GetMinimum → real

Return Value

The return value has the data type real .

Example

```simtalk
print MyDisplay.GetMinimum
```

SimTalk

GetMaximum [SimTalk]

resetMinMax [SimTalk]

See also

Minimum [Display]

Mode [drop-down list] - Display

MUs and States [Home ribbon]

<!-- image -->

##### GetStandardDeviation [SimTalk]

Returns the standard deviation of the values that the Display designated by &lt;Path&gt; recorded.

Type

Read-only attribute

Syntax

&lt; Path &gt;.GetStandardDeviation → real

Return Value

The return value has the data type real .

Example

print MyDisplay.GetStandardDeviation

#### Attributes of the Display

\_Attributes of the Display

The Display provides:

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
Display1.Sampler := false
Display1.Path := "MyConveyor.NumMU"
Display2.Sampler := true
Display2.SmpInterval := 300
Display2.Path := "root.MyConveyor.utilization"
print Display1.Path
posit := Station.Cont.XPos
```

Active [SimTalk] - Display

Activates the object designated by &lt;Path&gt; ( true ) or deactivates it ( false ).

Type

Attribute

Syntax

```simtalk
< Path >.Active:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyDisplay.active := true
```

See also

Active [check box] - Display Color [SimTalk] - Display Color [SimTalk] - Display Sets the Color for displaying the values which the object Display designated by &lt;Path&gt; visualizes in the Frame .

Remarks

Set the RGB values of the color with the method makeRGBValue .

Type

Attribute

Syntax

&lt; Path &gt;.Color:integer

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MyDisplay.Color := makeRGBValue(255,0,0)
```

SimTalk

makeRGBValue [SimTalk]

See also

Color [Display]

##### Comment [SimTalk] - Display

Sets the Comment that the Display designated by &lt;Path&gt; shows underneath its icon in the Frame .

Type

Attribute

Syntax

```simtalk
< Path >.Comment:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
MyDisplay.Comment := "My comment"
```

See also

Comment [text box] - Display DecimalPlaces [SimTalk] - Display Sets the number of Decimal Places which the Display designated by &lt;Path&gt; shows in 3D .

Remarks

The Display can show up to 15 decimal places. For the default setting -1 shows all existing places. Type in a positive value to show this number of places in the 3D .

**Note**

This setting only applies to the Type &gt; Text .

Type

Attribute

Syntax

```simtalk
< Path >.DecimalPlaces:integer
```

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MyDisplay.DecimalPlaces := 10
```

See also

Decimal Places [text box] - Display

Type [drop-down list] - Display

##### DisplayType [SimTalk]

Sets if the Display designated by &lt;Path&gt; shows the input value as Text , as a Bar , or as a Pie Segment .

Remarks

Bar and Pie representation map values in a specified range to bars of varying height or pies with a varying degree of completion.

You can set the range with the attributes MinVal and MaxVal .

Type

Attribute

Syntax

```simtalk
< Path >.DisplayType:string
```

Assignment Value

You can assign a value of data type string .

You can specify "Text" , "Bar" , or "Pie" .

Example

```simtalk
MyDisplay.DisplayMode := "Text"
```

SimTalk

MinVal [SimTalk]

MaxVal [SimTalk]

See also

Type [drop-down list] - Display Font [SimTalk] - Display Font [SimTalk] - Display Sets the Font Size of the text and of the Comment , which the Display designated by &lt;Path&gt; displays in Text mode in the Frame .

Type

Attribute

Syntax

```simtalk
< Path >.Font:integer
```

Assignment Value

You can assign a value of data type integer .

You can specify 1 for Small , 2 for Medium , 3 for Large , 4 for Extra Large .

Example

```simtalk
MyDisplay.Font := 2
```

See also

Font Size [drop-down list] - Display

Comment [text box] - Display

##### MaxVal [SimTalk]

Sets the Upper Bound of the displayed range in Bar and Pie modes of the Display designated by &lt;Path&gt;.

Remarks

The Display shows values beyond or equal to MaxVal as a full bar/pie.

Type

Attribute

Syntax

```simtalk
< Path >.MaxVal:real
```

Assignment Value

You can assign a value of data type real .

Example

```simtalk
MyDisplay.MinVal := 10.0
MyDisplay.MaxVal := 35.713
```

See also

Type [drop-down list] - Display

**MinVal [SimTalk]**

##### MinVal [SimTalk]

Sets the Lower Bound of the displayed range in Bar and Pie modes.

Remarks

The Display designated by &lt;Path&gt; shows values below or equal to MinVal as an empty bar/pie.

Type

Attribute

Syntax

&lt; Path &gt;.MinVal:real

Assignment Value

You can assign a value of data type real .

Example

```simtalk
MyDisplay.MinVal := 5.35
```

See also

Type [drop-down list] - Display Path [SimTalk] - Display Sets the Path to the value which the Display designated by &lt;Path&gt; shows.

Type

Attribute

Syntax

```simtalk
< Path >.Path:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
Display1.Sampler := false
Display1.Path := "MyConveyor.NumMU"
Display2.Sampler := true
Display2.SmpInterval := 300
Display2.Path := "root.MyConveyor.utilization"
```

See also

Path [text box] - Display

##### Sampler [SimTalk]

Sampler [SimTalk]

Activates Sample mode of the Display designated by &lt;Path&gt; ( true ) or deactivates it ( false ).

- true designates Sample mode. It updates the display periodically, independent of changes of the input value.
- false designates Watch mode. It updates its display whenever the input value changes.

Type

Attribute

Syntax

```simtalk
< Path >.Sampler:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
if MeinDisplay.Sampler = false
	MyDisplay.SmpInterval := 360 // 10 minutes
MyDisplay.Sampler := true // activates sample mode end
```

See also

Mode [drop-down list] - Display

##### SmpPeriod [SimTalk] - Display

Sets the intervals after which the Display designated by &lt;Path&gt; updates the display. Its value must be greater than zero.

Remarks

SmpPeriod applies to Sample mode.

Type

Attribute

Syntax

< Path >.SmpPeriod:time

Assignment Value

You can assign a value of data type time .

Example

```simtalk
MyDisplay.SmpPeriod := str_to_time("3:00.0")
MyDisplay.SmpPeriod := 2 * MyDisplay.SmpPeriod // double interval, half the sampling rate
```

See also

Interval [text box] - Display Transparent [SimTalk] - Display Makes the background of the object designated by &lt;Path&gt; Transparent in the Frame ( true ) or not transparent ( false ).

Remarks

Note

The setting Transparent also applies in 3D.

Type

Attribute

Syntax

&lt; Path &gt;.Transparent:boolean

Assignment Value

You can assign a value of data type boolean .

Specify true to show the space around the text in the color of the background image of the Frame .

Specify false to show the space around the text in white.

Example

```simtalk
MyDisplay.Transparent := false
```

See also

Show Comments [preferences]

Value [SimTalk] - Display

Sets or gets the Value , which the Display designated by &lt;Path&gt; shows.

Type

Only use Value for Watch Mode .

In Sample Mode Plant Simulation only updates the value if MUs and States is activated and the Frame , in which the Display is inserted, is open.

Type

Attribute

Syntax

```simtalk
< Path >.Value:real
```

Assignment Value

You can assign a value of data type real .

Return Value

The return value has the data type of the observed value.

Example

```simtalk
MyDisplay.Value := 5
print MyDisplay.Value
```

See also

Mode [drop-down list] - Display

Value [Display]

MUs and States [Home ribbon]

<!-- image -->

Chart

