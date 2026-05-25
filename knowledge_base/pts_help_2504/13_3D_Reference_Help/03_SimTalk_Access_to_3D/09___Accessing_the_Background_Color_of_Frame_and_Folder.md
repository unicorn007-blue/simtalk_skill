### \_\_Accessing the Background Color of Frame and Folder

SimTalk provides the attributes listed in the table of contents to the left for setting the background color of the Frame and the folder in 3D .

See also

Edit 3D Properties [dialog] &gt; Background [tab] - Frame in 3D

Set the Background Color of the Scene

#### \_3D.BackgroundBrightness [SimTalk]

Sets the brightness of the four corners of background color of the Frame or folder designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >._3D.BackgroundBrightness:real[4]
```

Assignment Value

You can assign a value of data type array containing four values of data type real between -1 and 1 .

They make the color values of the corners of the Frame window darker (values less than 0) or brighter (values greater than 0).

- The first value of the array designates the top right corner.
- The second value designates the top left corner.
- The third value designates the bottom right corner.
- The fourth value designates the bottom left corner.

**Examples**

```simtalk
MyFrame._3D.BackgroundColor := makeRGBValue(0,0,255)
MyFrame._3D.BackgroundBrightness := [1, 1, 1, 1]
```

See also

Edit 3D Properties [dialog] &gt; Background [tab] - Frame in 3D &gt; Corner Brightness

#### \_3D.BackgroundColor [SimTalk]

Sets the background color of the Frame or folder designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >._3D.BackgroundColor:integer
```

Assignment Value

You can assign a value of data type integer .

If you do not want to define a background color, assign the value -1 .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
MyFrame._3D.BackgroundColor := makeRGBValue(0,0,255) // bright blue
print MyFrame._3D.BackgroundColor                    // returns 16711680
```

See also

Edit 3D Properties [dialog] &gt; Background [tab] - Frame in 3D &gt; Base Color

**Accessing the Fill Level of the Buffer**

