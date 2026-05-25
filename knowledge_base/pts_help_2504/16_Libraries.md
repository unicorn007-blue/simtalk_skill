# 16. Libraries

## Libraries Reference

Plant Simulation provides a number of free of charge and licensed libraries.

<!-- image -->

- The Free of Charge Example Libraries

**Note**

The example libraries are intended as demonstrators which exemplify how to approach the respective modeling tasks. They are not intended to solve your modeling tasks as, for example, the built-in Tools do.

**Note**

The help for the objects of the example libraries Cranes and More and HBW is integrated into the objects themselves. Select Help &gt; Help on Object in the dialog of the respective object.

<!-- image -->

- Licensed Libraries for which you have to buy a license

The Value Stream Mapping library (VSM) for modeling value streams.

**Note**

The Value Stream Mapping library itself and the respective help is available in English and in German .

The help contains the description of the new and improved features.

<!-- image -->

To add any of the libraries to the Class Library , click Manage Class Library &gt; Libraries on the Home

ribbon tab.

**Note**

We modeled the objects of the libraries as application objects based on Frames . For this reason opening Help with F1 and What's This Help in the dialogs of the objects do not work. To open help for an object, select Help &gt; Help on Object in its dialog.

**Note**

We modeled the dialogs of the objects with the object Dialog . The windows of the objects do not use the standard Siemens PLM theme, but your Windows theme.

**Parametrizing MUs in Libraries**

Most libraries contain templates for MUs . We recommend to proceed as follows to parametrize these templates or any other objects of the library in the Class Library :

1. Click the object that you would like to parametrize with the right mouse button.
2. Select Derive to derive the object.

As the libraries are most likely locked, Plant Simulation shows a message saying that it is going move the derived class to the unlocked folder named Public . Click OK to accept the message. You can then parametrize the object in the folder Public within the library folder and use it in your simulation model.

This way your parametrized model will be kept when the library is updated, it will be updated as well, and your changes to the object will be retained.

**Note**

Plant Simulation checks about every half hour if a newer version of any of the loaded libraries exists.