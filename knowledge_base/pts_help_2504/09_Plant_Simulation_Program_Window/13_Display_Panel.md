## Display Panel

### Display Panel [object]

Most of the objects in Plant Simulation allow you to create a display panel in 2D, which shows values of attributes of the respective object directly in the Frame . You might, for example, define in the class of an object which statistics values you want to show.

**Note**

A 3D Only model does not provide the Display Panel .

You can show the value of a user-defined attribute in the outside representation of the object to which they belong in a 3D Only model though.

Once you insert an instance of that class into your simulation model, it will show the defined values. You can define a single display panel for an object, not one for each of its icons. Naturally you can set the size and the position of the display panel in the Frame . Rotating, mirroring or zooming the icon of the object does not affect the size and the position of the display panel . It can contain any number of items and passes all of these items on to its derivatives, i.e., you can only deactivate inheritance for all items and not for individual items. If, on the other hand, items are not inherited, you can change, add or delete as many of them as you like.

To create a display panel , click the object in the Frame and either select Edit Display Panel on the context menu or click Edit Display Panel [Home ribbon]

To create a display panel for the Frame , click Edit Display Panel [Home ribbon] .

<!-- image -->

By default, the display panel is deactivated for all objects. When you activate it , Plant Simulation shows it on the same level as the icon of the object in the Frame . In the Frame , Plant Simulation shows the display panels by default. You can hide them by deselecting Options &gt; Show Display Panels [View ribbon] - 2D on the General ribbon tab to increase the simulation speed if you activated the animation and to increase clarity if the display panels show many values.

<!-- image -->

Under File &gt; Preferences &gt; Simulation &gt; Display Panel Frame Rate [preferences] you can select the refresh rate of the displayed values.

<!-- image -->

When you deactivate MUs and States Plant Simulation shows the display panel , but does not update its values and continues showing the previous values. It does not update the values either, when no simulation is running. To still show current values, Plant Simulation updates them:

- When the simulation stops, either because you stopped it or because the End Time time has been reached.
- When you click OK or Apply in the dialog of an object.
- When you select View &gt; Refresh in the dialog of an object.
- When you press F5 in the Frame window.
- When you call the method redraw of an object.

These objects do not provide the display panel : The Comment , the Variable , and the Connector , the mobile objects Container , Part , Transporter , and Worker , the Folder , the Class Library , and the Toolbar .

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

**See also**

Show Statistics with Display Panels in the 2D Model

Dialog Box of the Display Panel

Methods of the Display Panel

\_Attributes of the Display Panel

#### Dialog Box of the Display Panel

### Dialog Box of the Display Panel

In the dialog box of the Display Panel you can define the general settings of the display panel of the selected object.

The shared properties are described under Dialog Items of the Objects .

<!-- image -->

#### Active [check box] - display panel

To activate the display panel , select this check box. To deactivate the display panel , clear the check box.

<!-- image -->

When you activate it, Plant Simulation shows the display panel on the same layer as the icon of the object in the Frame . Thus, the display panel overlaps the same objects as the icon does and is overlapped by the objects which overlap the icon.

SimTalk

DisplayPanel. Active [SimTalk] - display panel

#### X-Position [text box] - display panel

Type in the x-coordinate of the top left corner of the display panel in the Frame or click the spin buttons.

You can specify a number between -5000 and +5000 .

<!-- image -->

Click the left spin button to move the top left corner of the display panel in the Frame to the left on the x-axis.

Click the right spin button to move the top left corner of the display panel in the Frame to the right on the x-axis.

This position is relative to the coordinates of the reference point of the object.

Inheritance for the Position

A green check box means that inheritance is active. Then, the object uses the values for the X-Position and for the Y-Position of the origin object from which you derived it. When you modify the values of the origin object, this also changes the values of the derived object.

An orange check box with a minus means that inheritance is not active. The value you enter only applies to the attribute of the selected object without any connection to the values of the original object.

SimTalk

DisplayPanel. X [SimTalk] - display panel

See also

Y-Position [text box] - display panel

#### Y-Position [text box] - display panel

Type in the y-coordinate of the top left corner of the display panel in the Frame or click the spin buttons.

You can specify a number between -5000 and +5000 .

<!-- image -->

Click the up spin button to move the top left corner of the display panel in the Frame up on the y-axis, click the up spin button.

Click the down spin button to move the top left corner of the display panel in the Frame down on the y-axis.

This position is relative to the coordinates of the reference point of the object.

Inheritance for the Position

A green check box means that inheritance is active. Then, the object uses the values for the X-Position and for the Y-Position of the origin object from which you derived it. When you modify the values of the origin object, this also changes the values of the derived object.

An orange check box with a minus means that inheritance is not active. The value you enter only applies to the attribute of the selected object without any connection to the values of the original object.

SimTalk

DisplayPanel. Y [SimTalk] - display panel

See also

X-Position [text box] - display panel

#### Width [text box] - display panel

Type in the width of the display panel in the Frame or click the spin buttons.

You can specify a width between 1 and 255 pixels.

<!-- image -->

Click the right spin button to increase width of the display panel in the Frame .

Click the left spin button to decrease the width of the display panel in the Frame .

Inheritance for the Size

A green check box means that inheritance is active. Then, the object uses the values for the Width and for the Height of the origin object from which you derived it. When you modify the values of the origin object, this also changes the values of the derived object.

An orange check box with a minus means that inheritance is not active. The value you enter only applies to the attribute of the selected object without any connection to the values of the original object.

SimTalk

DisplayPanel. Width [SimTalk] - display panel

DisplayPanel. Height [SimTalk] - display panel

#### Height [text box] - display panel

Type in the height of the display panel in the Frame or click the spin buttons.

You can specify a height between 1 and 255 pixels.

<!-- image -->

Click the up spin button to increase height of the display panel in the Frame .

Click the down spin button to decrease the height of the display panel in the Frame .

Inheritance for the Size

A green check box means that inheritance is active. Then, the object uses the values for the Height and for the Width [text box] - display panel of the origin object from which you derived it. When you modify the values of the origin object, this also changes the values of the derived object.

An orange check box with a minus means that inheritance is not active. The value you enter only applies to the attribute of the selected object without any connection to the values of the original object.

SimTalk

DisplayPanel. Height [SimTalk] - display panel

DisplayPanel. Width [SimTalk] - display panel

#### Border Color [display panel]

To select the color of the border around the edge of the display panel in the Frame , click this button.

To not display the border color, you can make it transparent by entering the RGB values 0 , 128 , 128 .

<!-- image -->

<!-- image -->

You can select one of the predefined colors, or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation shows this color next to More Colors and uses it as the active color.

SimTalk

DisplayPanel. BorderColor [SimTalk]

#### Background Color [display panel]

To select the background of the display panel in the Frame , click this button.

To not display the background color, you can make it transparent by entering the RGB values 0 , 128 , 128 .

<!-- image -->

<!-- image -->

You can select one of the predefined colors, or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation shows this color next to More Colors and uses it as the active color.

SimTalk

DisplayPanel. BackgroundColor [SimTalk] - display panel

#### New Display Panel Item

New [display panel]

To add a new item to the display panel , click this button.

<!-- image -->

Then, define the properties of the individual display panel items in the dialog Display Panel Elements , which the display panel of the selected object shows in the Frame .

The dialog provides the settings listed in the table of contents to the left.

Plant Simulation adds a new item to the Elements Table .

Show Statistics with Display Panels in the 2D Model illustrates how to create items.

##### Value [display panel]

Value [display panel]

Type in or select the value which the display panel shows.

<!-- image -->

The value can be any formula which Plant Simulation evaluates and shows in regular intervals. Within the formula relative paths are resolved relative to the object for which you define the display panel . You can use the tilde ( ~ ) to access the Frame in which the object is located. You might, for example, type in NumMU or ~.myBuffer.NumMU .

To display static text instead of the value of an attribute or a method, select the Type [display panel] &gt; Static Text and then type in the respective text.

SimTalk

setValue [SimTalk] - display panel

See also

setElements [SimTalk]

getElements [SimTalk]

##### X-Position [display panel]

Select the x-coordinate of the top left corner of the display panel item on the display panel .

<!-- image -->

<!-- image -->

You can also type in a number between 0 and 255 .

SimTalk

DisplayPanel. setElements [SimTalk]

DisplayPanel. getElements [SimTalk]

##### Y-Position [display panel]

Y-Position [display panel]

Select the y-coordinate of the top left corner of the display panel item on the display panel .

<!-- image -->

You can also type in a number between 0 and 255 .

SimTalk

DisplayPanel. setElements [SimTalk]

DisplayPanel. getElements [SimTalk]

Type [display panel]

Select how the display panel shows the Value .

The display panel can show the Value :

- As Static Text , i.e., as an arbitrary sequence of characters that does not change as opposed to the value of an attribute/method.

<!-- image -->

You can select the Alignment [display panel] and the Color [display panel] of the displayed text.

- As Text .

<!-- image -->

You can select the Alignment [display panel] and the Color [display panel] and if you want to display the values as a percentage and you can specify the number of Decimal Places [drop-down list] display panel .

- As a Bar if you want to display values of numeric data types.

<!-- image -->

You can select the Color [display panel] , the Length [text box] - display panel , the Width [text box] display panel , the Direction [display panel] , and the value of the bars.

- As an LED if you want to display boolean values.

<!-- image -->

You can select the Width [text box] - display panel of the LED area.

Show Statistics with Display Panels in the 2D Model illustrates how to create items.

**SimTalk**

DisplayPanel. setElements [SimTalk]

DisplayPanel. getElements [SimTalk]

##### Alignment [display panel]

Select where at the X-position Static Text or Text will be aligned.

The display panel can align the display panel item of Static Text or Text at this X-Position [display panel] .

- Left aligns the left border of the text with the position on the x-axis.
- Center aligns the center of the text with the position on the x-axis.
- Right aligns the right border of the text with the position on the x-axis.

<!-- image -->

**SimTalk**

DisplayPanel. setElements [SimTalk]

DisplayPanel. getElements [SimTalk]

**Color [display panel]**

##### Color [display panel]

To select the color of the item, click this field.

You can select one of the predefined colors, or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation shows this color next to More Colors and uses it as the active color.

<!-- image -->

**SimTalk**

DisplayPanel. setElements [SimTalk]

DisplayPanel. getElements [SimTalk]

##### Transparent [display panel]

To make the item on the display panel transparent so that the background color of the display panel shines through, select this check box.

To not make it transparent, clear the check box. Then the Background Color [display panel] of the display panel is white.

When you display bars non-transparent, Plant Simulation shows the area exceeding the value to the Maximum Value in white.

<!-- image -->

**SimTalk**

DisplayPanel. setElements [SimTalk]

DisplayPanel. getElements [SimTalk]

Length [text box] - display panel

Type in the length of the bar on the display panel in pixels.

The length refers to the Direction [display panel] of the bar.

<!-- image -->

| Length of the bar, left to right   | Length of the bar, bottom to top   | Width of the bar, left to right   |
|------------------------------------|------------------------------------|-----------------------------------|

SimTalk

DisplayPanel. setElements [SimTalk]

DisplayPanel. getElements [SimTalk]

<!-- image -->

##### Width [text box] - display panel

Type in the height of the bar or the width of the LED on the display panel in pixels.

<!-- image -->

| Width of the bar, left to right   | Width of the LED, left to right   |
|-----------------------------------|-----------------------------------|

<!-- image -->

SimTalk

DisplayPanel. setElements [SimTalk]

DisplayPanel. getElements [SimTalk]

<!-- image -->

**Direction [display panel]**

##### Direction [display panel]

Select the direction of the bar on the display panel .

The bar deflects in the direction up to the Length [text box] - display panel you specify.

<!-- image -->

**SimTalk**

DisplayPanel. setElements [SimTalk]

DisplayPanel. getElements [SimTalk]

##### Maximum Value

Type in the maximum value to which the bar deflects.

<!-- image -->

The default value is 1 .

SimTalk

DisplayPanel. setElements [SimTalk]

DisplayPanel. getElements [SimTalk]

**Display as Percentage**

##### Display as Percentage

Select this to show values, which the setting Type &gt; Text displays as a percentage instead of just as a number.

<!-- image -->

SimTalk

DisplayPanel. setElements [SimTalk]

DisplayPanel. getElements [SimTalk]

##### Decimal Places [drop-down list] - display panel

Select the number of decimal places for values, which the setting Type &gt; Text displays.

<!-- image -->

#### Edit [display panel item]

To edit the item of the display panel , which you selected in the Elements Table below, click this button.

<!-- image -->

Then, change its properties. Plant Simulation writes the changed values into the items table.

Instead, you can also right-click the object and select Edit Display Panel [in Frame] on the context menu in the Frame .

See also

Elements Table

#### Delete [display panel item]

To delete the item from the display panel , which you selected in the Elements Table below, click this button.

<!-- image -->

Plant Simulation deletes this item from the items table.

See also

Elements Table

#### Elements Table

The elements table shows the elements which you defined for the display panel .

- The Value [display panel] can be any formula, which Plant Simulation evaluates and shows in regular intervals. Within the formula relative paths are resolved relative to the object for which you define the display panel . You can use the tilde (~) to access the Frame in which the object is located. You might, for example, enter NumMU or ~.myBuffer.NumMU .

To display static text instead of the value of an attribute or method , select the Type [display panel] &gt; Static Text and then enter the respective text.

- X is the X-Position [text box] - display panel of the item.
- Y is the Y-Position [text box] - display panel of the item.
- The type is the Display -Type [display panel] of the item.
- To add a new item, click New [display panel] .
- To edit an item on the table, double-click the respective row, or select it and click Edit [display panel item] above the table.
- To delete the selected item from the table, click Delete [display panel item] .
- To load the settings of a display panel , which you saved by clicking the button Save [display panel item] , click Load [display panel settings] .
- To save the settings of a display panel , as a Plant Simulation object file (.psobj), click Save [display panel item] .
- To view the defined items and all of their properties, click Open Table [display panel item] .

<!-- image -->

**SimTalk**

DisplayPanel. setElements [SimTalk]

DisplayPanel. getElements [SimTalk]

DisplayPanel. setValue [SimTalk] - display panel

#### Load [display panel settings]

To load the settings of a display panel , which you saved by clicking the Save button, click this button.

<!-- image -->

Navigate to the location of the object file in the dialog Open and select it.

See also

Save [display panel item]

#### Save [display panel item]

To save the settings of the display panel as a Plant Simulation object file (.psobj), click this button.

<!-- image -->

Then, type in the fi le name of the object file into the dialog Save As and specify a location.

#### Open Table [display panel item]

To open the table that contains all items of the display panel , click this button.

<!-- image -->

The table shows the names of the items in the rows and all of their properties in the columns.

<!-- image -->

**Note**

The table is intended for quickly transferring the configuration of the display panel items of an object to another object without having to define each individual item again.

In addition, you can view how the table has to be formatted, which you can assign with the methods listed below.

Each defined display panel item provides some of these items:

- Its Value [display panel] , its X-Position [display panel] , its Y-Position [display panel] , its Type [display panel] , its Alignment [display panel] , its Color [display panel] , and if it is Transparent [display panel] or not.
- For the Type &gt; Bar you can set the Length [text box] - display panel , the Width [text box] - display panel , the Direction [display panel] , and the Maximum Value of the bar.
- For the Type &gt; Text you can select the setting Display as Percentage and enter the number of Decimal Places [drop-down list] - display panel .

**Note**

As not all columns apply to all item types, some of the cells remain empty.

**SimTalk**

DisplayPanel. setElements [SimTalk]

DisplayPanel. getElements [SimTalk]

DisplayPanel. setValue [SimTalk] - display panel

#### Methods of the Display Panel

### Methods of the Display Panel

The Display Panel [object] provides the sub-methods listed in the table of contents to the left.

Plant Simulation addresses the methods of the Display Panel as sub-methods of the method DisplayPanel .

Syntax

&lt; Path &gt;.DisplayPanel.&lt;name of the sub-method&gt;

The window Show Attributes and Methods [described] shows the identifier DisplayPanel but not the methods proper of the Display Panel .

<!-- image -->

Note A 3D Only model does not provide these methods.

See also

\_Attributes of the Display Panel

#### getElements [SimTalk]

Returns all items of the display panel of the object designated by &lt;Path&gt; and writes them into a table.

Remarks

A 3D Only model does not provide the method DisplayPanel.getElements .

Type

Method

Syntax

&lt; Path &gt;.DisplayPanel.getElements(Items:table)

Parameter

The parameter Items of data type table designates the name of the table.

Each defined display panel item provides some of these items: Its Value [display panel] , its X-Position [display panel] , its Y-Position [display panel] , its Type [display panel] , its Alignment [display panel] , its Color [display panel] , and if it is Transparent [display panel] or not.

For the Type &gt; Bar you can set the Length [text box] - display panel , the Width [text box] - display panel , the Direction [display panel] , and the Maximum Value of the bar.

For the Type &gt; Text you can select the setting Display as Percentage and enter the number of Decimal Places [drop-down list] - display panel .

Example

Station.DisplayPanel.getElements(myElementsTable)

SimTalk

DisplayPanel. setElements [SimTalk]

DisplayPanel. setValue [SimTalk] - display panel

See also

Elements Table

**Open Table [display panel item]**

#### setElements [SimTalk]

Sets the items of the display panel of the object designated by &lt;Path&gt;.

Remarks

A 3D Only model does not provide the method DisplayPanel.setElements .

Type

Method

Syntax

&lt; Path &gt;.DisplayPanel.setElements(Items:table)

Parameter

The parameter Items of data type table designates the name of the table in which you defined the items.

Each defined display panel item provides some of these items: Its Value [display panel] , its X-Position [display panel] , its Y-Position [display panel] , its Type [display panel] , its Alignment [display panel] , its Color [display panel] , and if it is Transparent [display panel] or not.

For the Type &gt; Bar you can set the Length [text box] - display panel , the Width [text box] - display panel , the Direction [display panel] , and the Maximum Value of the bar.

For the Type &gt; Text you can select the setting Display as Percentage and enter the number of Decimal Places [drop-down list] - display panel .

<!-- image -->

**Note**

As not all columns apply to all item types, some of the cells remain empty.

**Example**

Station.DisplayPanel.setElements(myElementsTable)

SimTalk

DisplayPanel. getElements [SimTalk]

DisplayPanel. setValue [SimTalk] - display panel

See also

Elements Table

Open Table [display panel item]

Data Held in Tabular Form in Attributes [material flow objects]

#### setValue [SimTalk] - display panel

Sets the value of a display panel item of the object designated by &lt;Path&gt;.

Remarks

A 3D Only model does not provide the method DisplayPanel.setValue .

Type

Method

Syntax

```simtalk
< Path >.DisplayPanel.setValue(RowInTable:integer, NewValue:string)
```

**Parameters**

- The parameter RowInTable of data type integer designates the respective row for the display panel item in the Elements Table .
- The parameter NewValue of data type string designates the new value of the display panel item.

<!-- image -->

**Example**

myStation.DisplayPanel.setValue(1, "My new static text") myStation.DisplayPanel.setValue(2, "Exit closed")

**SimTalk**

DisplayPanel. getElements [SimTalk]

DisplayPanel. setElements [SimTalk]

See also

Open Table [display panel item]

**Attributes of the Display Panel**

### \_Attributes of the Display Panel

The display panel provides the sub-attributes listed in the table of contents to the left.

Plant Simulation addresses the attributes of the Display Panel [object] as sub-attributes of the attribute DisplayPanel . You cannot assign the attribute to a Variable of data type object or any .

Syntax

&lt; Path &gt;.DisplayPanel.&lt;name of the sub-attribute&gt;

The window Show Attributes and Methods [described] shows the identifier DisplayPanel but not the attributes proper of the Display Panel .

<!-- image -->

Note

A 3D Only model does not provide these attributes.

See also

Methods of the Display Panel

ShowDisplayPanels [SimTalk]

DisplayPanel. getElements [SimTalk]

DisplayPanel. setElements [SimTalk]

#### Active [SimTalk] - display panel

Activates the display panel of the object designated by &lt;Path&gt; ( true ) or deactivates it ( false ).

Remarks

A 3D Only model does not provide the attribute DisplayPanel.Active .

Type

Attribute

Syntax

&lt; Path &gt;.DisplayPanel.Active:boolean

Assignment Value

You can assign a value of data type boolean .

Example

Station.DisplayPanel.Active := true

SimTalk

ShowDisplayPanels [SimTalk]

See also

Active [check box] - display panel

#### BackgroundColor [SimTalk] - display panel

Sets the background color of the display panel of the object designated by &lt;Path&gt;.

Remarks

Note

A 3D Only model does not provide the attribute DisplayPanel.BackgroundColor .

Set the RGB values of the color with the method makeRGBValue .

To not show the background color, make it transparent by assigning the RGB value 0 , 128 , 128 .

Type

Attribute

Syntax

&lt; Path &gt;.DisplayPanel.BackgroundColor:integer

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
Station.DisplayPanel.BackgroundColor := makeRGBValue(100,100,100)
Station.DisplayPanel.BackgroundColor := 6579300 // is the same as the color above
```

SimTalk

makeRGBValue [SimTalk]

See also

Background Color [display panel]

#### BorderColor [SimTalk]

Sets the color of the border around the edge of the display panel of the object designated by &lt;Path&gt;.

Remarks

Note

A 3D Only model does not provide the attribute DisplayPanel.BorderColor .

Set the RGB values of the color with the method makeRGBValue .

To not show the border color, make it transparent by assigning the RGB value 0 , 128 , 128 .

Type

Attribute

Syntax

&lt; Path &gt;.DisplayPanel.BorderColor:integer

Assignment Value

You can assign a value of data type integer .

Example

Station.DisplayPanel.BorderColor := makeRGBValue(15,155,100)

SimTalk

makeRGBValue [SimTalk]

See also

Border Color [display panel]

#### Height [SimTalk] - display panel

Sets the height of the display panel of the object designated by &lt;Path&gt;.

Remarks

A 3D Only model does not provide the attribute DisplayPanel.Height .

Type

Attribute

Syntax

&lt; Path &gt;.DisplayPanel.Height:integer

Assignment Value

You can assign a value of data type integer .

Specify a number between 1 and 255 pixels.

Example

```simtalk
Station.DisplayPanel.Height := 45
```

See also

Height [text box] - display panel

#### Width [SimTalk] - display panel

Sets the width of the display panel of the object designated by &lt;Path&gt;.

Remarks

A 3D Only model does not provide the attribute DisplayPanel.Width .

Type

Attribute

Syntax

&lt; Path &gt;.DisplayPanel.Width:integer

Assignment Value

You can assign a value of data type integer .

You can specify a number between 1 and 255 pixels.

Example

Station.DisplayPanel.Width := 150

See also

Width [text box] - display panel

#### X [SimTalk] - display panel

Sets the x-coordinate of the top left corner of the display panel of the object designated by &lt;Path&gt;.

Remarks

Note

A 3D Only model does not provide the attribute DisplayPanel.X .

This position is relative to the coordinates of the reference point of the object.

Type

Attribute

Syntax

```simtalk
< Path >.DisplayPanel.X:integer
```

Assignment Value

You can assign a value of data type integer .

Specify a number between -5000 and +5000 .

Example

```simtalk
Station.DisplayPanel.X := 200
Station.DisplayPanel.Y := 200
```

See also

X-Position [text box] - display panel

#### Y [SimTalk] - display panel

Sets the y-coordinate of the top left corner of the display panel of the object designated by &lt;Path&gt;.

Remarks

Note

A 3D Only model does not provide the attribute DisplayPanel.Y .

This position is relative to the coordinates of the reference point of the object.

Type

Attribute

Syntax

```simtalk
< Path >.DisplayPanel.Y:integer
```

Assignment Value

You can assign a value of data type integer .

Specify a number between -5000 and +5000 .

Example

```simtalk
Station.DisplayPanel.X := 200
Station.DisplayPanel.Y := 200
```

See also

Y-Position [text box] - display panel

