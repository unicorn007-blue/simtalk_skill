## Icon Editor

Each Frame and each of the built-in objects in Plant Simulation have an icon. Plant Simulation displays the object in the Class Library , in the Toolbox , and in the Frame with this icon.

Plant Simulation uses icons to animate the parts, the transporters, etc., that the material flow objects process during a simulation run.

You can modify the icons representing the simulation objects and the animation structures, i.e., the animation points and animation lines, that define the animation of your simulation model, in the Icon Editor .

<!-- image -->

By default, Plant Simulation shows the state of the material flow objects and of the Frame itself in 2D during your simulation runs as one or more colored dots in the LED display along the upper border of the built-in icon of the object in the Frame .

<!-- image -->

3D shows the State Graphic of the object as a colored ring on a pole by default resembling the signal lamps in a real-world factory.

You can also use the setting State Icons/LEDs [command] to display the state of operation of an object, such as failed , paused , etc. during a simulation run. You can modify the built-in icons or design new icons in the Icon Editor .

When a user-defined object class has an icon named ClassLibrary , Plant Simulation shows the objects of this class in the Class Library with this icon. The size of this icon should be 16 by 16 pixels.

To edit the icon of an object, right-click it in the Frame and select Edit Icons [in Frame] on the context menu.

<!-- image -->

Note In a 2D Only model you can open the Icon Editor by pressing Ctrl+Shift+I .

<!-- image -->

<!-- image -->

You can set the animation of the parts and of the material flow objects in 3D in the dialog Edit 3D Properties on the tab MU Animation and on the tab Self Animation .

**See also**

Work with Object Icons

LEDs and States of the Material Flow Objects in 2D

#### Window of the Icon Editor

### Window of the Icon Editor

Edit, delete or design new icons for models and objects in the Icon Editor .

You can open the Icon Editor :

- In the Class Library : Select the object and select Edit Icons on the context menu.
- In the Frame window in a 2D Only model :

Select the object and select Edit Icons on the Icons ribbon tab.

Select the object and select the command Edit Icons on the context menu.

- In the Frame window in a 3D Only model :

<!-- image -->

Select the object and select Edit Icons on the Home ribbon tab.

When you clicked New Icon on the Edit ribbon tab of the Icon Editor , you can also drag an object over the open window of the Icon Editor and drop it there.

<!-- image -->

The title bar of the Icon Editor shows the path to and the name of the object or model you opened in the drawing window. The Icon Editor provides its functions on the Edit Ribbon Tab , the Animation Ribbon Tab , and the General Ribbon Tab .

Each object or model has to have at least one icon to display the object with in the Class Library , in the Toolbox , and in the Frame . That icon has the Number 0 and the name Default .

<!-- image -->

When you created several icons for an object, you can assign another Default icon: Click Previous Icon or Next Icon to cycle through the icons and select the check box Current to the right of the text box Name to designate that icon as the current icon with which Plant Simulation displays the object. When an object class has an icon named ClassLibrary , Plant Simulation shows the objects of this class in the Class Library with this icon. This icon should be 16 by 16 pixels.

<!-- image -->

The Icon Editor shows the icon enlarged in the drawing area, it shows its original size of the icon above the Color Palette . In addition, the Icon Editor shows the reference point of the icon in the drawing area.

**Number**

<!-- image -->

The Icon Editor shows which icon with which number out of the total amount of icons it displays at the moment. 0/5 , for example, means it shows the icon with the number 0 out of a total of 5 icons of the object.

It shows the x-coordinate and the y-coordinate of the cursor in the drawing window below the Number in parentheses.

<!-- image -->

When you select the color picker , it shows the RGB values of the pixel on which the color picker is located.

**Name**

<!-- image -->

The Icon Editor shows the name of the icon in the text box. To change this name, select it in the text box and overtype it with a meaningful name.

**Note**

Plant Simulation automatically sets upper and lower casing of the name of the icon.

To save memory and improve access speed, all places which use such a case-insensitive string point to the same string in main memory. The visible and unexpected result is that the first occurrence of the string defines how the string is written in terms of upper- and lower-casing.

In SimTalk you can compare if strings are case-insensitive with the ~= operator, compare Relational Operators .

**Current**

<!-- image -->

To make the displayed icon the current icon with which the object is displayed in your simulation model, select the check box Current .

SimTalk

CurrIcon [SimTalk]

CurrIconNo [SimTalk]

#### Color Palette

The color palette on the left-hand side of the Icon Editor window shows twenty colors by default.

To replace one of the twenty predefined colors with a color of your choice:

- Double-click the color you would like to replace in the color palette.
- Select a new color in the dialog Color and click OK .

To set a color, move the mouse in the color matrix over the area that is similar to the color you want. Click Select . This adds the color to one of the fields in the color palette in Plant Simulation .

<!-- image -->

<!-- image -->

The field directly below the color palette shows the transparency color. Click it and select the color which the Icon Editor draws transparent . The background of the Frame shines through any area you marked as transparent, when you insert the object.

<!-- image -->

The fields below the transparency color field show the active drawing colors. You can assign a color each to the left and to the right mouse button and then use the left and the right mouse button to draw with these colors.

To assign another color the left mouse button:

### Edit Ribbon Tab

- Click that color in the color palette with the left mouse button. Or
- Double-click the color field and define a color of your choice in the dialog Color . This adds that color to the top drawing color field.
- Select any of the drawing tools and click and hold down the left mouse button to manipulate the icon with that color.

To assign another color the right mouse button:

- Click that color in the color palette with the right mouse button. Or
- Double-click the color field and define a color of your choice in the dialog Color . This adds that color to the bottom drawing color field.
- Select any of the drawing tools and click and hold down the right mouse button to manipulate the icon with that color.

See also

Set Drawing Color

Activate Transparency

Pick Color

**Edit Ribbon Tab**

#### Edit Ribbon Tab [Icon Editor]

The Edit ribbon tab of the Icon Editor provides commands to access its functions.

<!-- image -->

<!-- image -->

| Command                             | Looks like this   | Method or Attribute                   |
|-------------------------------------|-------------------|---------------------------------------|
| Pick Color                          |                   | setPixel [SimTalk] getPixel [SimTalk] |
| Draw Freehand                       |                   | -                                     |
| Draw Line [Icon Editor]             |                   | -                                     |
| Draw Polyline                       |                   | -                                     |
| Draw Ellipse [Icon Editor]          |                   | -                                     |
| Draw Rectangle [Icon Editor]        |                   | -                                     |
| Draw Filled Rectangle [Icon Editor] |                   | -                                     |
| Fill Area                           |                   | -                                     |
| Copy and Paste Area                 |                   | -                                     |
| Paste Area                          |                   | -                                     |
| Replace Color                       |                   | setPixel [SimTalk] getPixel [SimTalk] |

<!-- image -->

| Command                                                                     | Looks like this   | Method or Attribute                         |
|-----------------------------------------------------------------------------|-------------------|---------------------------------------------|
| Set Reference Point [command] Set Reference Point Calculate Reference Point |                   | setRefPoint [SimTalk] getRefPoint [SimTalk] |
| Delete Icon                                                                 |                   | deleteIcon [SimTalk]                        |
| Set Icon Size                                                               |                   | setIconSize [SimTalk] getIconSize [SimTalk] |
| Activate Transparency                                                       |                   | CurrIconTransparent [SimTalk]               |
| Inherit Icon                                                                |                   | -                                           |
| Apply Changes [icon]                                                        |                   | -                                           |

**Note**

The other tabs on the Ribbon Bar provide additional commands pertaining to the Icon Editor .

#### New Icon

<!-- image -->

<!-- image -->

#### Import

Import

<!-- image -->

Opens an empty drawing window. Here you can draw a new icon, import an existing icon by clicking Import , or paste an icon, which you can then modify.

To add the icon to those already defined, enter a name into the text box Name and click Apply Changes

.

SimTalk

createIcon [SimTalk]

Provides the subcommands Import Bitmap File and Import Icon Resource allowing you to import images for your icons.

Note

You cannot import an image into the icons named Operational and Default . You can only import a file into a new icon, i.e. after you clicked New Icon on the Edit ribbon tab.

SimTalk

createIcon [SimTalk]

See also

Import Bitmap File

Import Icon Resource

##### Import Bitmap File

Opens the dialog Open . Select the graphics file that will be imported.

Plant Simulation can open . png, .gif, .bmp, .dgn, .dwg, .dxf, and . ico files.

<!-- image -->

<!-- image -->

##### Import Icon Resource

Opens the dialog Change Icon . Select the icon resource you want to use as the icon of the selected object.

<!-- image -->

#### Export Icon to File

Opens the dialog Save As . Type in the name and the file type of the file and select the folder in which Plant Simulation saves the icon.

<!-- image -->

You can save files in the formats .dib (Device Independent Bitmap), .png (Portable Network Graphic), and .ppm (Portable Pixelmap).

SimTalk

saveIconToFile [SimTalk]

**Overview [Edit ribbon]**

#### Overview [Edit ribbon]

Shows all icons of the object or model in a window side by side. To open an icon in the drawing area, click it.

<!-- image -->

<!-- image -->

#### Zoom In [Edit ribbon]

Zooms the contents of the drawing window in.

<!-- image -->

**Zoom Out [Edit ribbon]**

#### Zoom Out [Edit ribbon]

Zooms the contents of the drawing window out.

<!-- image -->

#### Set Drawing Color

Opens the dialog Colors . Select one of the predefined colors, or you can click More Colors and click the Select button to select a color in the color matrix.

<!-- image -->

Click OK . Plant Simulation shows this color next to More Colors and uses it as the active color.

<!-- image -->

To change the current drawing color, you can also double-click its field below the Color Palette , and then edit the color in the dialog Colors .

#### Pick Color

Activates the Pick Color tool.

<!-- image -->

To set and apply the drawing color:

- Place the color dropper on the color in the drawing window, which you would like to use as the drawing color and click the left mouse button.
- The Icon Editor adds that color to the drawing color field below the Color Palette .

SimTalk

setPixel [SimTalk]

getPixel [SimTalk]

#### Draw Freehand

Draws a freehand line with the active drawing color.

<!-- image -->

**Note**

This command is only active when you create a new icon after you clicked New Icon .

- Click into the drawing area with the left mouse button, hold the mouse button down and drag the mouse.
- To finish drawing mode, release the mouse button.
- To apply the shape you inserted, click Apply Changes

<!-- image -->

.

<!-- image -->

- To undo the line you inserted, click Previous Icon or Next Icon and click No in the dialog that opens. This reverts to the last saved state of the icon.
- To save your changes to the icon, click Export on the Edit ribbon tab of the Icon Editor .

<!-- image -->

#### Draw Line [Icon Editor]

Draws a straight line with the active drawing color.

<!-- image -->

**Note**

This command is only active when you create a new icon after you clicked New Icon .

**To draw the line:**

- Click into the drawing area with the left mouse button, hold the mouse button down and drag the mouse.
- To finish drawing mode, release the mouse button.
- To apply the shape you inserted, click Apply Changes

<!-- image -->

.

<!-- image -->

- To undo the line you inserted, click Previous Icon or Next Icon and click No in the dialog that opens. This reverts to the last saved state of the icon.
- To save your changes to the icon, click Export on the Edit ribbon tab of the Icon Editor .

<!-- image -->

#### Draw Polyline

Draws a polyline (polygonal chain) with the active drawing color.

<!-- image -->

**Note**

This command is only active when you create a new icon after you clicked New Icon .

**To draw the line:**

- Click once into the drawing area with the left mouse button to set the starting point of the line, click again to set the next anchor point. Plant Simulation connects the anchor points to create the line. Continue this until the polygonal chain meets your needs.
- To apply the shape you inserted, click Apply Changes

<!-- image -->

.

<!-- image -->

- To undo the line you inserted, click Previous Icon or Next Icon and click No in the dialog that opens. This reverts to the last saved state of the icon.
- To save your changes to the icon, click Export on the Edit ribbon tab of the Icon Editor .

<!-- image -->

#### Draw Ellipse [Icon Editor]

Draws the outline of a circle or of an ellipse with the active drawing color.

<!-- image -->

**Note**

This command is only active when you create a new icon after you clicked New Icon .

**To draw the ellipse:**

- Click once into the drawing area with the left mouse button to set the starting point of the shape, hold the mouse button down and drag the mouse.
- When the circle or ellipse has the shape you want, release the mouse button to have Plant Simulation draw the outline of the shape.
- To apply the shape you inserted, click Apply Changes

.

<!-- image -->

- To undo the line you inserted, click Previous Icon or Next Icon and click No in the dialog that opens. This reverts to the last saved state of the icon.
- To save your changes to the icon, click Export on the Edit ribbon tab of the Icon Editor .

<!-- image -->

#### Draw Rectangle [Icon Editor]

Draws the outline of a rectangle with the active drawing color.

<!-- image -->

**Note**

This command is only active when you create a new icon after you clicked New Icon .

**To draw the rectangle:**

- Click once into the drawing area with the left mouse button to set a corner of the rectangle, hold the mouse button down and drag the mouse to the opposite corner and release the mouse button so that Plant Simulation draws it.
- To apply the shape you inserted, click Apply Changes

<!-- image -->

.

<!-- image -->

- To undo the line you inserted, click Previous Icon or Next Icon and click No in the dialog that opens. This reverts to the last saved state of the icon.
- To save your changes to the icon, click Export on the Edit ribbon tab of the Icon Editor .

<!-- image -->

#### Draw Filled Rectangle [Icon Editor]

Draws a filled rectangle with the active drawing color.

<!-- image -->

**Note**

This command is only active when you create a new icon after you clicked New Icon .

**To draw the rectangle:**

- Click once into the drawing area with the left mouse button to set a corner of the shape, hold the mouse button down and drag the mouse to the opposite corner.
- Click the mouse button again to set the second corner of the rectangle and to have Plant Simulation draw and fill it with the active drawing color.
- To apply the shape you inserted, click Apply Changes

.

<!-- image -->

- To undo the line you inserted, click Previous Icon or Next Icon and click No in the dialog that opens. This reverts to the last saved state of the icon.
- To save your changes to the icon, click Export on the Edit ribbon tab of the Icon Editor .

<!-- image -->

#### Fill Area

Fills a continuous area with the active drawing color.

<!-- image -->

**Note**

This command is only active when you create a new icon after you clicked New Icon .

**To fill the area:**

- Drag the mouse over the shape you want to fill and click the left mouse button. You might, for example fill any of the shapes you inserted with the Draw Ellipse [Icon Editor] or Draw Rectangle [Icon Editor] tools.
- To apply the color fill, click Apply Changes

.

<!-- image -->

<!-- image -->

- To undo filling the area, click Previous Icon or Next Icon and click No in the dialog that opens. This reverts to the last saved state of the icon.
- To save your changes to the icon, click Export on the Edit ribbon tab of the Icon Editor .

<!-- image -->

#### Copy and Paste Area

Copies the selected area and inserts it at the position of the cursor, when you click the mouse button.

<!-- image -->

**Note**

This command is only active when you create a new icon after you clicked New Icon .

To copy and paste the area:

- To select any rectangular area in the drawing area, drag a marquee over it: Click the left mouse button to set a corner, hold the mouse button down and drag the mouse to the opposite corner. Then, release the mouse button.
- To paste the selected area, which Plant Simulation attached to the cursor, into the same icon, drag the mouse to a different location and click the left mouse button.
- To paste the selected area into another icon, select the command Paste Area .
- To terminate Copy Area mode, click the right mouse button once.
- To apply your changes, click Apply Changes

.

<!-- image -->

- To undo copying and pasting, click Previous Icon or Next Icon and click No in the dialog that opens. This reverts to the last saved state of the icon.
- To save your changes to the icon, click Export on the Edit ribbon tab of the Icon Editor .

#### Paste Area

Inserts the part of the image that you copied to the clipboard with the tool Copy and Paste Area into the icon.

<!-- image -->

**Note**

This command is only active when you create a new icon after you clicked New Icon .

Plant Simulation attaches the area to be pasted to the mouse pointer. Move it to the location of your choice and click the left mouse button to insert the area and to replace the selected area.

See also

Copy and Paste Area

#### Replace Color

Replaces all pixels of the active drawing color with the pixels of the color you select in the color palette:

<!-- image -->

**Note**

This command is only active when you create a new icon after you clicked New Icon .

To replace all pixels:

- Make sure that the active drawing color is the color you want to replace.
- Click the command Replace Color .
- Select the color you want to replace the active drawing color with in the Color Palette .
- Click Apply Changes to apply the new color.

<!-- image -->

SimTalk

setPixel [SimTalk]

getPixel [SimTalk]

#### Set Reference Point

Set Reference Point [command]

<!-- image -->

The command Set Reference Point provides the subcommands Set Reference Point and Calculate Reference Point .

<!-- image -->

**Set Reference Point**

##### Set Reference Point

Sets the reference point of the new icon.

<!-- image -->

**Note**

This command is only active when you create a new icon after you clicked New Icon .

To set the reference point of the icon:

· Click once in the drawing area to set the reference point at the position of the cursor. By default, the reference point of every icon is located at the center of the drawing area. Plant Simulation uses the reference point to determine its position when you insert the object into a model.

- For MUs Plant Simulation places the reference point of the MU onto an animation point of an object.
- For objects or models Plant Simulation aligns the reference point with the intersection of grid lines, when you display the grid.
- To apply your changes, click Apply Changes

.

<!-- image -->

- To undo setting the reference point, click Previous Icon or Next Icon and click No in the dialog that opens. This reverts to the last saved state of the icon.
- To save your changes to the icon, click Export on the Edit ribbon tab of the Icon Editor .

<!-- image -->

**SimTalk**

setRefPoint [SimTalk]

getRefPoint [SimTalk]

getBoundingBox [SimTalk]

See also

Set and Link Animation Points and Lines

Calculate Reference Point

##### Calculate Reference Point

Calculates and sets the reference point of the icon of the object.

<!-- image -->

By default, the reference point of every icon is located at the center of the drawing area. Plant Simulation uses the reference point to determine the position of the object in the Frame when you insert the object into a model.

For mobile objects (MUs) Plant Simulation computes the reference point according to the position of the booking point . By default, the mobile objects have a booking point, as a long MU may be located on more than one length-oriented object at the same time. Plant Simulation uses the booking point to determine on which material flow object to display the MU when animating a simulation run. Plant Simulation shows, for example, a Transporter moving along from Track to Track on the first Track until its booking point moves on to the next Track .

<!-- image -->

For all other objects it centers the reference point.

See also

Set and Link Animation Points and Lines

Set Reference Point [command]

Booking Point Length [general description]

**Booking Point Width [general description] Booking Point Height [general description]**

#### Delete Icon

Deletes the selected icon of the object.

<!-- image -->

SimTalk

deleteIcon [SimTalk]

#### Set Icon Size

Sets the size of the new icon.

<!-- image -->

The command opens the dialog Size in which you can set the individual settings.

<!-- image -->

Plant Simulation automatically converts the pixel values you enter into length units and vice versa. This is especially handy, because you can now enter the length of your parts in meters and don't have to manually convert that length into pixels taking the scaling factor into consideration. Plant Simulation then shows the icons with their correct size in your simulation model.

- To enter the Width and the Height of the icon in Pixels , select Pixels . Plant Simulation automatically converts the pixel values you enter into length units and vice versa.

Type in the Width and the Height of the icon in pixels. The size is limited to 9999 x 9999 pixels. Plant Simulation automatically converts the pixel values you enter into length units and vice versa.

- To enter the Width and Height of the icon in the length units, which you selected under File &gt; Model Settings/Preferences &gt; Units &gt; Length [model settings] , select Length Units . Plant Simulation automatically converts the length units you enter into pixel values and vice versa.

Type in the Width and the Height of the icon in length units.

Type in the Scaling Factor for scaling the size of the icon. The Scaling Factor [2D only] is the length of one pixel in one length unit. By setting the correct scaling factor, you can place 2D objects in the Frame according to their real coordinates.

**Note**

When you make an icon smaller, Plant Simulation deletes anything located outside of the new Width and Height . Make sure to save the icon before changing the size.

Note

The performance of Plant Simulation might suffer if you use large bitmaps.

SimTalk

createIcon [SimTalk]

getIconSize [SimTalk]

setIconSize [SimTalk]

See also

Show Object Borders [model settings]

#### Activate Transparency

Sets the transparent area of the icon. The background of the Frame shines through this area, when you insert the object into the Frame .

<!-- image -->

To set which color, i.e., which area, of the icon will be transparent:

<!-- image -->

- Click in the transparency color field below the color palette to make the transparency color the active drawing color.
- Select either one of the drawing tools or click Fill Area to mark the area of the icon you would like to be transparent. In our example we selected the blue bar and the arrow in the icon of the Source to be transparent.
- Click Apply Changes to apply the transparency.
- You will notice that Plant Simulation now draws the light blue bar and the arrow in green , denoting that the bar and the arrow will be transparent, when you insert the Source into the Frame with a white background .

<!-- image -->

<!-- image -->

<!-- image -->

When you create a new icon with the method createIcon , Transparent is active by default and the background is filled with the transparency color.

**SimTalk**

CurrIconTransparent [SimTalk]

createIcon [SimTalk]

<!-- image -->

#### Inherit Icon

Turns inheritance of the icon of the object on or off.

<!-- image -->

To change the icons of instances of objects independent of the class of the object, deactivate the command. Object classes can also inherit their icons.

#### Apply Changes [icon]

Applies the changes you made to the icon and leaves the window of the Icon Editor open.

<!-- image -->

#### Animation Ribbon Tab

### Animation Ribbon Tab

The Animation ribbon tab of the Icon Editor provides these commands.

<!-- image -->

<!-- image -->

| Command                        | Looks like this   | Method or Attribute                             |
|--------------------------------|-------------------|-------------------------------------------------|
| Add/Remove Animation Point     |                   | setAniPoint [SimTalk] delAniPoint [SimTalk]     |
| Add/Remove Animation Line      |                   | setAniLine [SimTalk] delAniPoints [SimTalk]     |
| Add/Remove Animation Polyline  |                   | setAniLine [SimTalk] delAniPoints [SimTalk]     |
| Move Animation Point           |                   | moveAniPoint [SimTalk]                          |
| Delete All                     |                   | -                                               |
| Link Animation Point           |                   | linkAniPoint [SimTalk] unlinkAniPoint [SimTalk] |
| Set Animation Events           |                   | NumAnimationEvents [SimTalk]                    |
| Inherit Animation Structures   |                   | -                                               |
| Apply Changes [icon animation] |                   | -                                               |

**Note**

The other tabs on the Ribbon Bar provide additional commands pertaining to the Icon Editor .

Proceed as follows to add animation points or animation structures to the objects in your simulation model:

<!-- image -->

- To insert an animation point into the icon of a point-oriented object, click Add/Remove Animation Point . Then, click into the drawing area with the left mouse button at the location of your new animation point.
- To insert a straight animation line into the icon of a length-oriented object, click Add/Remove Animation Line . Then, click into the drawing area with the left mouse button, hold the mouse button down to insert the beginning of the line, drag the mouse to the end point of the line and release the mouse button.
- To insert a non-straight animation line into the icon of a length-oriented object, click Add/ Remove Animation Polyline . Then, click once into the drawing area with the left mouse button to set the starting point of the line, drag the mouse to the location of the next anchor point and click again to insert it. Plant Simulation connects the anchor points to create the line. Continue this until the polygonal chain meets your needs.
- To move an animation point or an animation line to a different location, click Move Animation Point .

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

These colors represent the different states of an animation point:

- Blue : Is the standard color for all objects, except for the Frame . For a Frame Plant Simulation shows that the animation point is linked to an object located within that Frame .
- Light blue : Is the same as blue . In addition, it shows that an animation point of a Frame is linked to this animation point.
- Red : The animation point in a Frame is not linked to an object located within that Frame . For this reason Plant Simulation does not show an animation for this point.

You can set the animation of the parts and of the material flow objects in 3D in the dialog Edit 3D Properties [dialog] on the tab MU Animation [3D] and on the tab Self Animation .

<!-- image -->

**See also**

Set and Link Animation Points and Lines

Animate the Simulation Model in 2D

Visualizing the Material Flow in 3D

#### Overview [Animation ribbon]

Shows all icons of the object or model in a window side by side. To open an icon in the drawing area, click it.

<!-- image -->

<!-- image -->

#### Zoom In [Animation ribbon]

Zooms the contents of the drawing window in.

<!-- image -->

#### Zoom Out [Animation ribbon]

Zooms the contents of the drawing window out.

<!-- image -->

#### Add/Remove Animation Point

Adds/removes an animation point to/from the icon of a point-oriented object. Then, click into the drawing area with the left mouse button at the location of your new animation point.

<!-- image -->

To remove the selected animation point , click it with the right mouse button. When you delete an animation point, Plant Simulation now decreases the number of animation points with a higher number by 1 thus preventing gaps between the numbers.

**Note**

When you repeatedly click the same location, Plant Simulation inserts a new animation point on top of the existing point with each mouse click!

SimTalk

setAniPoint [SimTalk]

delAniPoint [SimTalk]

See also

Set and Link Animation Points and Lines

<!-- image -->

#### Add/Remove Animation Line

Adds a straight animation line to the icon of a length-oriented object.

<!-- image -->

**Note**

This button is only active for the PlaceBuffer , Buffer , Sorter , Track , Conveyor , Footpath , and the Frame .

In the icon of the PlaceBuffer , Buffer , Sorter , Track , Conveyor , and Footpath you can draw a single animation line.

In the icon of the Frame you can draw several animation lines.

To add or remove an animation line:

- Click into the drawing area with the left mouse button, hold the mouse button down and drag the mouse.
- To finish drawing mode, release the mouse button.
- To apply the animation line you inserted, click Apply Changes

<!-- image -->

.

<!-- image -->

<!-- image -->

- To undo the line you inserted, click Previous Icon or Next Icon and click No in the dialog that opens. This reverts to the last saved state of the icon.
- To save your changes to the icon, click Export on the Edit ribbon tab of the Icon Editor .

**SimTalk**

setAniLine [SimTalk]

getAniPoints [SimTalk]

delAniPoints [SimTalk]

See also

Set and Link Animation Points and Lines

#### Add/Remove Animation Polyline

Adds/removes a non-straight animation line to/from the icon of a length-oriented object. The polyline consists of several straight animation lines connected with anchor points.

<!-- image -->

**Note**

This button is only active for the PlaceBuffer , Buffer , Sorter , Track , Conveyor , Footpath , and the Frame .

In the icon of the PlaceBuffer , Buffer , Sorter , Track , Conveyor , and Footpath you can draw a single animation line.

In the icon of the Frame you can draw several animation lines.

To add or remove an animation line:

- Click into the drawing area with the left mouse button once to set the starting point of the line, move the mouse to a different location and click again to set the next anchor point, etc.
- To finish drawing mode, click the right mouse button.
- To apply the animation line you inserted, click Apply Changes

.

<!-- image -->

- To undo the line you inserted, click Previous Icon or Next Icon and click No in the dialog that opens. This reverts to the last saved state of the icon.
- To save your changes to the icon, click Export on the Edit ribbon tab of the Icon Editor .

SimTalk

setAniLine [SimTalk]

getAniPoints [SimTalk]

delAniPoints [SimTalk]

See also

Set and Link Animation Points and Lines

#### Move Animation Point

Moves a single animation point or an anchor point of an animation line in the icon of the object.

<!-- image -->

Click the animation point/anchor point once and drag the point to a new location. Plant Simulation does not break the link with the underlying object, but only moves the animation point.

SimTalk

**moveAniPoint [SimTalk]**

See also

Set and Link Animation Points and Lines

#### Delete All

Deletes all animation structures from the icon of the object.

<!-- image -->

#### Link Animation Point

Links or unlinks an animation point or line that you inserted, but did not connect. This button is only active for the Frame .

<!-- image -->

SimTalk

linkAniPoint [SimTalk]

unlinkAniPoint [SimTalk]

See also

Set and Link Animation Points and Lines

#### Set Animation Events

Opens the dialog Animation Events . Enter how often Plant Simulation draws the contents of the object, while a part is located on it. .

<!-- image -->

If several MUs with differing speeds are located on the object, the first moving MU determines the time intervals between the animation events.

<!-- image -->

Plant Simulation only uses the setting Number of Animation Events in special cases for the animation. To speed up the simulation when the PlaceBuffer has a great capacity , you can enter 0. Then Plant Simulation does not schedule any animation events for the PlaceBuffer and thus does not animate any parts on the PlaceBuffer .

If you insert the length-oriented objects Track , TwoLaneTrack , Conveyor , FootPath , Turnplate , Turntable , AngularConverter , and Converter in icon mode instead of in curve mode , you also have to enter a number!

In curve mode they animate the MUs with the setting you select for Animate every x-th pixel

<!-- image -->

SimTalk

NumAnimationEvents [SimTalk]

See also

Animate Every x-th Pixel

Set and Link Animation Points and Lines

.

#### Show Animation Numbers

Hides or shows the number of the animation point or line you inserted into the icon of the object.

<!-- image -->

If you assigned an object to the animation point or line of a Frame , the Icon Editor shows the name of the object or Frame you linked next to the number in the icon .

<!-- image -->

**See also**

Animation Ribbon Tab

Set Reference Point [command]

Set and Link Animation Points and Lines

#### Inherit Animation Structures

Opens the dialog Inherit Animation Structures .

<!-- image -->

To inherit animation structures:

- To inherit the Coordinates of an animation point, make sure that the check box is selected. To not inherit them, clear it.
- To inherit the Linked object of the animation point in the icon of a Frame , make sure that the check box is selected. To not inherit it, clear it.

<!-- image -->

<!-- image -->

<!-- image -->

#### Apply Changes [icon animation]

Applies the changes you made to the icon and leaves the window of the Icon Editor open.

<!-- image -->

### General Ribbon Tab

#### General Ribbon Tab [Icon Editor]

The General ribbon tab of the Icon Editor provides commands to access its functions.

<!-- image -->

<!-- image -->

| Command                     | Looks like this   | Method or Attribute   |
|-----------------------------|-------------------|-----------------------|
| Clipart Library             |                   | -                     |
| Apply Changes [Icon Editor] |                   | -                     |

**Note**

The other tabs on the Ribbon Bar provide additional commands pertaining to the Icon Editor .

#### Overview [General ribbon]

Shows all icons of the object or model in a window side by side. To open an icon in the drawing area, click it.

<!-- image -->

<!-- image -->

#### State Icons/LEDs

State Icons/LEDs [command]

Provides the submenu commands Use State Icons , Use LEDs , and Inherit .

<!-- image -->

##### Use State Icons

Activates or deactivates the display of state icons of the material flow object during your simulation runs, instead of the LEDs that the icons show by default.

<!-- image -->

<!-- image -->

**Note**

By default, the material flow objects do not provide predefined state icons. If you want to use icons for the different states of the object, you have to create these icons yourself.

**SimTalk**

StatusWithIcons [SimTalk]

**Use LEDs**

##### Use LEDs

Activates or deactivates the display LEDs instead of state icons of the material flow object during your simulation runs. This is the default setting.

<!-- image -->

<!-- image -->

**Note**

By default, the material flow objects do not provide predefined state icons. If you want to use icons for the different states of the object, you have to create these icons yourself.

3D shows the State Graphic of the object as a colored ring on a pole by default.

SimTalk

StatusWithIcons [SimTalk]

##### Inherit [state icons]

Turns inheritance for using state icons or the default LED for the material flow objects on or off.

<!-- image -->

When you turn Inherit on , any object that you derive from the current object , will use the setting you selected for the current object .

When you turn it off, you can select for each icon individually if it shows a state object or an LED for a certain state.

**Clipart Library**

#### Clipart Library

Opens the clip-art library that is part of your Plant Simulation program package. The graphics in the folder Clipart provide different icons, which you can use in your simulation model.

<!-- image -->

To insert an icon from the Clip Art Library into the Plant Simulation Icon Editor , select an icon in the Windows Explorer window, drag it to the open window of the Icon Editor , and drop it there.

#### Apply Changes [Icon Editor]

Applies the changes you made to the icon and leaves the window of the Icon Editor open.

<!-- image -->

### Drag-and-Drop in the Icon Editor

Drag-and-drop in the Icon Editor performs a number of actions.

| To do this                                                                        | Drag            | To          | Object Type   | Accelerator   |
|-----------------------------------------------------------------------------------|-----------------|-------------|---------------|---------------|
| Open the icon for editing                                                         | a Frame         | Icon Editor | object        | none          |
| Load a graphics file (.BMP, .GIF, .PPM, .PNG, .DXF, or .DWG) into the Icon Editor | a graphics file | Icon Editor | file          | any           |

