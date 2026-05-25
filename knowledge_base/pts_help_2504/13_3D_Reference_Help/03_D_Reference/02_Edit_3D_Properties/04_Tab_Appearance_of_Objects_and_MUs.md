#### Tab Appearance of Objects and MUs

Appearance of Objects and MUs

Define the surface qualities, i.e., the object material for all graphics of the selected object for which no material of its own is defined on the tab Appearance .

Objects do not provide an object material :

- If they have object-specific appearance settings, such as the length-oriented objects and the Store .
- If they are used for connecting other objects, such as the Connector , the Interface , and the Marker .
- If they are used for displaying text or values, or for selecting a setting, such as Comment, Variable, Display, Button, DropDownList, Checkbox, Chart, Tank and Mixer .

If Material active is cleared, no material for the object is defined and Plant Simulation shows all graphics without a material light gray.

Changing the Appearance of an object does not cut graphic inheritance . This way Plant Simulation can show instances of the objects with different object materials, although they share their graphics.

In the predefined graphics of the 3D objects we already deleted the material of selected graphics and saved it as the object material.

In the examples below we changed the object material (color) to a material that meets our modeling requirements.

- We changed the object material of the Worker so that his T-Shirt is colored purple instead of gray.
- We changed the object material of the Transporter so that its body is colored red instead of blue.

<!-- image -->

<!-- image -->

- We changed the object material of the Container so that it is colored gray instead of brown.

<!-- image -->

We changed the object material of the Part so that it is colored light blue instead of brown.

<!-- image -->

- We changed the object material of the point-oriented objects, such as the Station , the Buffer , etc. so that they are colored green instead of their default color dark blue.

<!-- image -->

<!-- image -->

- We changed the object material of the light gray plate under the icon of the information flow object Method and of the user interface object SankeyDiagram .

<!-- image -->

<!-- image -->

**Note**

In a 2D and 3D model an object material which you defined for a Part in 3D overrides the color in 2D if you activated vector graphics on Graphics [tab, MUs, 2D] in 2D. This means that the graphic of the Part is colored according to the 3D object material even if a 2D color is defined.

On the Tab Appearance you can:

- Select Material Active [check box] - MUs to activate the settings for the color. To reset all settings of the selected object to the values the text boxes had, when you opened the dialog, clear the check box.
- Select the Diffuse Color [MUs] .
- Select the Ambient Color [MUs] .
- Select the Specular Color [MUs] .
- Select the Emissive Color [MUs] .
- Set the Transparency [MUs] .
- Set the Shininess [MUs] .
- Activate or deactivate Show Safety Zones for the Transporter .
- Copy the Current Material Settings [MUs] .
- Paste Material Settings [MUs] .

To apply and display your changes of the settings to the selected object in the scene window and leave the dialog box open, click Apply .

To apply your changes of the settings to the selected object and close the dialog box, click OK .

##### Appearance of Objects and MUs

To close the dialog without applying any of the settings you modified, click Cancel .

See also

\_\_Accessing the Appearance of Objects and MUs

Graphics [tab, MUs, 2D] &gt; Vector Graphics Active in 2D

Material [tab]

Configure the Individual Stations

\_3D.MaterialActive [SimTalk]

Video on YouTube

[https://youtu.be/BvHLQCIjGIA?si=oyIaT4qeU37Imfrs&amp;t=328](https://youtu.be/BvHLQCIjGIA?si=oyIaT4qeU37Imfrs&t=328)

##### Material Active [check box] - MUs

To define a color of your own with the settings of the tab, select this check box. 3D then activates the settings for defining the material.

<!-- image -->

If you do not select a material, Plant Simulation shows the MU

- white in a 3D only model
- with the color of the 2D vector graphic if it is active in a 2D and 3D model

<!-- image -->

If the Curve settings are not active, the MU is shown white.

To reset all material settings to their default values, clear the check box.

SimTalk

**\_3D.MaterialActive [SimTalk]**

**Diffuse Color [MUs]**

##### Diffuse Color [MUs]

Select a Diffuse Color . The diffuse color is the color of the object , which it shows under pure white light, where incoming light is reflected in all directions equally.

<!-- image -->

We perceive it as the color of the object itself rather than a reflection of the light.

This is in contrast to specular reflection . A familiar example of the distinction between specular and diffuse reflection are matte and glossy, which you use in home painting. Matte paints have a higher proportion of diffuse reflection, while glossy paints have a greater proportion of specular reflection.

You can select one of the predefined colors, or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation shows this color next to More Colors and uses it as the active color.

**Note**

By default, 3D shows the MUs with the color of the material flow objects on which they are located. If you assign different colors to the material flow objects, the parts naturally change their color, when they move from object to object.

To prevent this, you have to assign a color to the graphic of the material flow object.

SimTalk

\_3D.MaterialDiffuseColor [SimTalk]

See also

Set the Material of a Graphic

<!-- image -->

##### Ambient Color [MUs]

Select an Ambient Color . The ambient color is the color of the light reflected from the object , when it is lit by another ambient object in the scene.

Ambient intensity refers to the strength of the reflection.

You can select one of the predefined colors, or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation shows this color next to More Colors and uses it as the active color.

SimTalk

\_3D.MaterialAmbientColor [SimTalk]

##### Specular Color [MUs]

Specular Color [MUs]

Select a Specular Color . The specular color is the reflected color of the object's highlights .

<!-- image -->

Specular intensity refers to the strength of the reflection.

Specular reflection is the perfect, mirror-like reflection of light from a surface, in which light from a single incoming direction is reflected onto a single outgoing direction.

This is in contrast to diffuse reflection , where incoming light is reflected in all directions equally. A familiar example of the distinction between specular and diffuse reflection are matte and glossy, which you use in home painting. Matte paints have a higher proportion of diffuse reflection, while glossy paints have a greater proportion of specular reflection.

Be aware that specular reflection and diffuse reflection are approximations. In reality, surfaces exhibit a continuum of modes of reflection between these two.

You can select one of the predefined colors, or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation shows this color next to More Colors and uses it as the active color.

SimTalk

\_3D.MaterialSpecularColor [SimTalk]

##### Emissive Color [MUs]

Select an Emissive Color . The emissive color is the color emitted by the object .

<!-- image -->

A lamp shade might, for example, have a base color of yellow. When you turn the lamp on, though, the emissive color might be white.

You can select one of the predefined colors, or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation shows this color next to More Colors and uses it as the active color.

SimTalk

\_3D.MaterialSpecularColor [SimTalk]

**Transparency [MUs]**

##### Transparency [MUs]

To set the Transparency , i.e., how opaque or clear the object is, type a value between 0.0 , for opaque, and 1.0 , for completely transparent, into the text box.

<!-- image -->

Water, for example, might be more clear than opaque.

SimTalk

\_3D.MaterialTransparency [SimTalk]

##### Shininess [MUs]

To set the Shininess , i.e., how sharp light is reflected by the object, type a value between 0.0 , for a very dull surface, and 1.0 , for a highly polished surface, into the text box

<!-- image -->

A billiard ball, for example, has a large shininess, making for small and sharp highlights.

SimTalk

**\_3D.MaterialShininess [SimTalk]**

##### Show Safety Zones

To show the defined Safety Zones of the Transporter , select this check box.

<!-- image -->

To hide the Safety Zones , clear the check box.

<!-- image -->

**See also**

Length Zone 1

ΔWidth Zone 1

Length Zone 2

ΔWidth Zone 2

Prevent AGVs from Colliding

SimTalk

\_3D.ShowSafetyZones [SimTalk]

##### Copy the Current Material Settings [MUs]

To copy the current material settings you selected, click this button.

<!-- image -->

You can then paste these settings into the graphic of another object.

The command also copies the respective SimTalk code to the clipboard. You can then paste this code into a Method object to set the material of another graphic.

The syntax is described under Generate SimTalk Code and Copy to Clipboard [optimize graphic] .

See also

Paste Material Settings [MUs]

**Paste Material Settings [MUs]**

##### Paste Material Settings [MUs]

To paste the material settings that you copied to the graphic of the object, click this button.

<!-- image -->

You also paste the source code, which the command Copy the Current Material Settings copied into a Method object to set the material of the selected graphic.

The syntax is described under Generate SimTalk Code and Copy to Clipboard [optimize graphic] .

See also

Copy the Current Material Settings [MUs]

