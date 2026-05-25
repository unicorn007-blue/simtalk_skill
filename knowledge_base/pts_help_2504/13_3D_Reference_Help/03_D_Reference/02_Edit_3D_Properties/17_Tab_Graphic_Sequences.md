#### Tab Graphic Sequences

##### Graphic Sequences

Define sequences of graphic groups for a Worker who is walking on a Footpath or freely within the model so that he looks realistic in your simulation model when he walks on the tab Graphic Sequences .

You can:

- Define graphic sequences for a Worker with the setting Walk Without Part .
- Define graphic sequences for a Worker with the setting Walk and Carry Part .

3D cycles through these graphic sequences when the Worker walks to simulate a fluid walking motion. The Worker uses a walking step length of 0.74088 meters.

<!-- image -->

To hide the Worker in your simulation model:

<!-- image -->

- Click the Select All button in the respective list, Walk Without Part or Walk and Carry Part .
- Click the Delete button.

The Worker is now invisible.

To restore the previous settings, click the respective inheritance button .

Define Graphic Groups of the Worker

You define the individual graphic groups on the tab Graphics of your Worker .

<!-- image -->

You can exchange the graphic of a new or existing Worker with one of the predefined s3d files of the Worker\_Jack or Worker\_Jill .

The files whose name contains Jack are male workers, the files whose name contains Jill are female workers. The suffix 6 designates a Worker that is animated with 6 graphics per double-step. The suffix 15 designates a Worker that is animated with 15 graphics per double-step. More graphics naturally lead to a greater file size.

<!-- image -->

SimTalk

\_\_Accessing the Worker

\_\_Accessing Attributes and Read-Only Attributes of Graphic Groups

See also

Worker [object]

Exchange Graphics

Walk without part

Walk Without Part

Define how the Worker walks in a relaxed posture without carrying a part . In this posture the Worker swings his arms back and forth.

The Worker cycles through the graphic groups in the sequence which you type in on the tab Graphic Sequences when he walks on a FootPath or freely within the model, while he does not carry a part .

If this sequence is empty, 3D uses the visible graphic groups you designated with the check box Visible [check box] (or with the attribute \_3D.VisibleGraphicGroups [SimTalk] ), i.e., the default behavior.

<!-- image -->

**You can:**

- Click Add [Walk Without Part] to add a graphic group to the sequence defining the walking motion.
- Click Insert Before [Walk Without Part] to insert an existing graphic group before the selected graphic group in the sequence.
- Click Delete [Walk Without Part] to delete the selected graphic group from the sequence defining the walking motion.

- Click Move Up [Walk Without Part] to move the selected graphic group one position up in the sequence defining the walking motion.
- Click Move Down [Walk Without Part] to move the selected graphic group one position down in the sequence defining the walking motion.

SimTalk

\_3D.GraphicsWhenEmpty [SimTalk]

**Add [Walk Without Part]**

###### Add [Walk Without Part]

To add a new graphic group to the Worker , click this button.

<!-- image -->

The list window then shows the name of this graphic group. The graphic group defines part of a walking pose.

###### Insert Before [Walk Without Part]

To insert an existing graphic group before the selected graphic group, click this button.

<!-- image -->

Then, select the graphic group which you want to insert before the selected graphic group and click OK .

The drop-down list shows all graphic groups which are defined on the Tab Graphics .

<!-- image -->

The list window then shows the name of the walking pose at the selected position in the list.

<!-- image -->

###### Move Up [Walk Without Part]

To move the selected graphic group one position up in the list, click this button.

<!-- image -->

**Move Down [Walk Without Part]**

###### Move Down [Walk Without Part]

To move the selected graphic group one position down the list, click this button.

<!-- image -->

###### Walk and carry part

##### Walk and Carry Part

Define the way in which the Worker walks while carrying a part in his hands or on his arms.

The Worker cycles through the graphic groups in the sequence which you type in here when he walks on a FootPath or freely within the model while he carries a part .

If this sequence is empty, 3D uses the visible graphic groups you designated with the check box Visible [check box] (or with the attribute \_3D.VisibleGraphicGroups [SimTalk] ), i.e., the default behavior.

<!-- image -->

**You can:**

- Click Add [Walk and Carry Part] to add a graphic group to the sequence defining the walking and carrying motion.
- Click Insert Before [Walk and Carry Part] to insert an existing graphic group before the selected graphic group in the sequence.
- Click Delete [Walk and Carry Part] to delete the selected graphic group from the sequence defining the walking and carrying motion.
- Click Move Up [Walk and Carry Part] to move the selected graphic group one position up in the sequence defining the walking and carrying motion.
- Click Move Down [Walk and Carry Part] to move the selected graphic group one position down in the sequence defining the walking and carrying motion.

**SimTalk**

\_3D.GraphicsWhenCarrying [SimTalk]

\_3D.VisibleGraphicGroups [SimTalk]

**Add [Walk and Carry Part]**

###### Add [Walk and Carry Part]

To add a new graphic group to the Worker , click this button.

<!-- image -->

The list window then shows the name of this graphic group. The graphic group defines part of a walking and carrying pose.

###### Insert Before [Walk and Carry Part]

To insert an existing graphic group before the selected graphic group, click this button.

<!-- image -->

Then, select the graphic group which you want to insert before the selected graphic group and click OK .

The drop-down list shows all graphic groups which are defined on the Tab Graphics .

<!-- image -->

The list window then shows the name of the walking and carrying pose at the selected position in the list.

<!-- image -->

###### Move Up [Walk and Carry Part]

To move the selected graphic group one position up in the list, click this button.

<!-- image -->

**Move Down [Walk and Carry Part]**

###### Move Down [Walk and Carry Part]

To move the selected graphic group one position down the list, click this button.

<!-- image -->

