#### Tab Material

Material [tab]

Define the surface qualities of the selected graphic, how well it reflects light, what color it reflects, and what color it emits on the tab Material .

You can:

- Make the Material Active or inactive.
- Select the Diffuse color .
- Select the Ambient Color .
- Select the Specular Color .
- Select the Emissive Color .
- Set the Transparency .
- Set the Shininess .
- Copy the Current Material Settings .
- Paste a Previously Copied Material .
- Remove the Materials in Nested Graphics .

To activate the settings for the material, select Material Active .

To reset all settings of the selected object to the values the text boxes had, when you opened the dialog, clear the check box.

To apply and display your changes of the settings to the selected object in the scene window and leave the dialog box open, click Apply .

To apply your changes of the settings to the selected object and close the dialog box, click OK .

To close the dialog without applying any of the settings you modified, click Cancel .

**Note**

Only graphics provide this tab. The material affects all graphics which are not affected by another material. This way you can easily show the progress in processing of a part, or you can add different criteria to a part or a Worker .

For some graphics you can set different materials for their individual components. Click the respective Color field in the dialog of the object to open the tab Material for this component.

<!-- image -->

**Note**

When you define materials for a graphic in the graphic structure at different levels in the structure, 3D always uses the material that is located furthest down in the structure for the actual rendering of the graphic.

**See also**

Set the Material of a Graphic

- \_Detailed Access To Graphics
- \_Tread Material Attributes
- \_Stringer Material Attributes

Material Active [check box] - graphic

To activate the settings for the material, select this check box.

To reset all settings for the material of the selected graphic to the values that the dialog contained when you opened the dialog, clear the check box.

SimTalk

MaterialActive [SimTalk]

##### Diffuse Color [material]

Diffuse Color [material]

Select a Diffuse Color . It is the color of the graphic, which it shows under pure white light, where incoming light is reflected in all directions equally

<!-- image -->

<!-- image -->

We perceive it as the color of the object itself rather than a reflection of the light.

This is in contrast to specular reflection . A familiar example of the distinction between specular and diffuse reflection are matte and glossy, which you use in home painting. Matte paints have a higher proportion of diffuse reflection, while glossy paints have a greater proportion of specular reflection.

You can select one of the predefined colors, or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation shows this color next to More Colors and uses it as the active color.

SimTalk

MaterialDiffuseColor [SimTalk]

See also

Set the Material of a Graphic

<!-- image -->

##### Ambient Color [material]

Select an Ambient Color . It is the color of the light reflected from the graphic, when it is lit by another ambient object in the scene.

Ambient intensity refers to the strength of the reflection.

You can select one of the predefined colors, or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation shows this color next to More Colors and uses it as the active color.

SimTalk

MaterialAmbientColor [SimTalk]

See also

Set the Material of a Graphic

**Specular Color [material]**

##### Specular Color [material]

Select a Specular Color . It is the reflected color of the graphic highlights.

<!-- image -->

Specular intensity refers to the strength of the reflection.

Specular reflection is the perfect, mirror-like reflection of light from a surface, in which light from a single incoming direction is reflected onto a single outgoing direction.

This is in contrast to diffuse reflection , where incoming light is reflected in all directions equally. A familiar example of the distinction between specular and diffuse reflection are matte and glossy, which you use in home painting. Matte paints have a higher proportion of diffuse reflection, while glossy paints have a greater proportion of specular reflection.

Be aware that specular reflection and diffuse reflection are approximations. In reality, surfaces exhibit a continuum of modes of reflection between these two.

You can select one of the predefined colors, or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation shows this color next to More Colors and uses it as the active color.

SimTalk

MaterialSpecularColor [SimTalk]

See also

Set the Material of a Graphic

##### Emissive Color [material]

Select an Emissive Color . It is the color emitted by the graphic.

<!-- image -->

A lamp shade might, for example, have a base color of yellow. When you turn the lamp on, though, the emissive color might be white.

You can select one of the predefined colors, or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation shows this color next to More Colors and uses it as the active color.

SimTalk

MaterialEmissiveColor [SimTalk]

See also

Set the Material of a Graphic

**Transparency [material]**

##### Transparency [material]

Type a value between 0.0 , for opaque, and 1.0 , for completely transparent, into the text box to set the Transparency . It sets how opaque or clear the graphic is. Water, for example, might be more clear than opaque.

<!-- image -->

**Note**

If your model contains several partially or fully transparent graphics behind each other from your current view point, it can happen that some or all of these graphics look wrong or seem to be missing.

This is due to heuristics without which the rendering performance would drastically decrease.

SimTalk

MaterialTransparency [SimTalk]

See also

Set the Material of a Graphic

##### Shininess [material]

Type a value between 0.0 , for a very dull surface, and 1.0 , for a highly polished surface, into the text box to set the Shininess . It sets how sharp light is reflected by the graphic.

<!-- image -->

A billiard ball, for example, has a large shininess, making for small and sharp highlights.

SimTalk

MaterialShininess [SimTalk]

See also

Set the Material of a Graphic Copy the Current Material Settings [material]

To copy the current material settings you selected, click this button.

<!-- image -->

You can then paste these settings into the graphic of another object.

The command also copies the respective SimTalk code to the clipboard. You can then paste this code into a Method object to set the material of another graphic.

The syntax is described under Generate SimTalk Code and Copy to Clipboard [optimize graphic] .

##### Paste a Previously Copied Material

To paste the material settings that you copied to the graphic of the object, click this button.

<!-- image -->

You can also paste the source code, which the command Copy the Current Material Settings [material] copied, into a Method object to set the material of the selected graphic.

The syntax is described under Generate SimTalk Code and Copy to Clipboard [optimize graphic] .

You can also paste a material from the Clipboard if the material is not active. Plant Simulation then automatically activates a material that was not active before.

##### Remove the Materials in Nested Graphics

To remove the materials in nested graphics , i.e., the materials of the graphics contained within this object, click this button.

<!-- image -->

See also

Set the Material of a Graphic

