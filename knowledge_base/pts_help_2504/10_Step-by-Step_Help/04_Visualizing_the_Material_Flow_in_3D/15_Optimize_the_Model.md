### Optimize the Model

After we created our model and are sure that we do not have to make any more changes, we can optimize it.

**Note**

As you cannot restore discarded data, we advise to optimize the model only after you finished creating it. Optimizing the model improves performance.

We also recommend to save the model under a different name before optimizing it. This way you can return to the state the model had before optimizing it in case the optimized model reports errors or does not meet you expectations.

**Proceed as follows:**

- Save the model with a new name before optimizing it. This way you can return to the state the model had before optimizing it in case the optimized model reports errors or does not meet you expectations.
- Click Optimize Model

on the Home ribbon tab.

<!-- image -->

- Select which optimization you want to execute. You can either choose only a single setting or any combination of the provided settings.

Below we demonstrate the effects of the individual settings with our model MyTurnplateShrinkwrapper3D.spp .

<!-- image -->

- First, we only select the setting Clean Up Class Library . This removes object classes from the Class Library that are not used in the model.

This setting reduces the file size the most.

<!-- image -->

If you want to continue working with the optimized model at a later point in time, you can re-add the missing objects with Start &gt; Manage Class Library .

- Then, we only select the setting Optimize 3D Attribute Inheritance .

This setting reduces the file size in our example only marginally.

<!-- image -->

- Then, we only select the setting Optimize 3D Graphic Structure .

This setting reduces the file size in our example only marginally.

If you want to work with your model later on and would like to be able to edit your graphics, we recommend to not activate Optimize 3D graphic structure .

<!-- image -->

- Finally, we combine all settings. This results in the smallest file size which, alas, is only marginally smaller than the setting Clean up

class library .

Back to Visualizing the Material Flow in 3D

<!-- image -->

