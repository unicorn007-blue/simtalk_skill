### Creating a Simulation Model

<!-- image -->

<!-- image -->

You will create your simulation model by inserting instances of the built-in objects and of objects you yourself or a colleague designed, the so-called user-defined or application objects, from the Class Library into the Frame named Model in the folder Models .

By creating user-defined objects you can develop libraries that meet the modeling requirements of your company. The most important built-in objects are: the Frame , the active and the passive material flow objects, the mobile objects (MUs), the Method object, lists and tables, and the EventController .

- The Frame is the object in which you create your simulation model. You will insert the objects that represent the stations in your plant, into the Frame named Model .
- To run the simulation you will use EventController that starts, stops and resets the simulation run. You can re-use each and every simulation model you created as an application object in other simulation models.

By inserting Frames into Frames you create a randomly nested hierarchy of models. This way you can build and structure simulation models that exactly match the plant you are simulating, and break down complex tasks into manageable chunks.

- You can derive or duplicate each object and re-use it as often as required, which introduces an important time-saving key feature of Plant Simulation , namely inheritance : A derived object, i.e., a child object, retains a controllable link to the template object, i.e., the parent object. In many cases the immense advantage of inheritance regarding productivity and the low number of errors only becomes clear at a later point in time, when you actively work with your simulation models. Naturally you can also deactivate inheritance for individual features by clicking the inheritance check box, so that it looks like this .
- The active material flow objects transport and/or actively process mobile objects (MUs), i.e., parts, within the simulation models.

<!-- image -->

The passive material flow objects do not actively process parts. They store parts and represent tracks on which the processed parts are moved.

- The mobile objects ( MUs ) represent the parts that are created in, stored in, transported in, processed in and removed from your simulation model.
- The fl uid objects serve for simulating free-flowing materials, be they in liquid, gaseous, or pourable form. The fluid objects are suited for the food and beverages processing, and for the pharmaceutical industries.

<!-- image -->

<!-- image -->

- The resource objects are intended for modeling how and when Workers move from the WorkerPool to the Workplaces at the stations.
- In objects of type Method you can program the actions that you need to take place when the conditions you program become true. For this we integrated the powerful programming language SimTalk into Plant Simulation . The Methods are either activated as controls by the material flow objects or by other Method objects. The Method also provides the Method Debugger to locate errors and allow you to debug and correct faulty code.
- Lists and tables ensure the random exchange of information between all objects. The powerful processing of information in Plant Simulation is the result of a variety of functions, data types and operators.
- The objects Chart and Report allow you to graphically display the statistical values that the material flow objects collect during the simulation runs.
- With the object Dialog you can create a dialog box similar to the built-in dialog boxes that Plant Simulation provides. This way you can provide a simple user interface for complex simulation models other users work with. You can also prevent another user from manipulating a Frame . To accomplish this, insert a Method object as an open control into the Frame . Double-clicking the Frame will then not

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

- open it any longer, but call the control method in which you might, for example, program it to open a dialog, where the user can then select the settings.
- In the folder User Objects you can save and provide objects, which you yourself created and add them to the tab User Objects . Here Plant Simulation also saves those objects which you derive or duplicate in the Class Library if you do not want to work with the built-in class objects.

<!-- image -->

**Note**

We recommend to not change the default settings of the built-in objects if at all possible. When you customize these objects and when you merge models or update the Class Library at a later point in time, Plant Simulation discards your changes and restores the default settings. For this reason you have to customize the objects anew.

If you need objects with customized settings, we recommend to derive the respective object/objects in the Class Library and then continue working with this class. Plant Simulation adds these objects by default to the folder User Objects . You can also add them to the tab User Objects in the Toolbox .

- With the objects BottleneckAnalyzer and SankeyDiagram you can analyze and evaluate the results the simulation runs provided. Use the ExperimentManager to define how Plant Simulation executes the simulation experiments.

<!-- image -->

- Naturally you can also exchange data with other programs and processes using the interfaces we provide. For integration purposes with other software it is important that data can be exchanged not only at the beginning and the end of the simulation run but also during the simulation run.

When you create your simulation models, you will more than likely combine these two modeling strategies:

- The top-down strategy is characterized by a roughly structured model that you break down step-bystep. The more refined the model becomes, the more detailed it becomes. This approach requires a large degree of abstraction. The big picture becomes obvious quickly though.

**Creating a German Model with English Identifiers**

- The bottom-up strategy is characterized by a detailed model that you created by using prefabricated components with a rather small degree of abstraction. This enables for a quick analysis of the details, but makes it harder to recognize the big picture.

Compare Create a Simulation Model

Back to Modeling the Material Flow

#### Creating a German Model with English Identifiers

As a rule you will work with the German version of Plant Simulation in German-speaking countries. If you are working in an internationally-active company though, one of your requirements might be to create the simulation model with English identifiers so that your colleagues in other countries can expand the model. As the interpreter, which compiles the instructions of the programming language SimTalk at runtime, can process the German and English names of the SimTalk commands, nothing is easier than that:

- Start Plant Simulation .
- Select Datei/File &gt; Voreinstellungen / Preferences before opening a model.

<!-- image -->

- Click the tab Allgemein/General . Select English as the language of the model.

<!-- image -->

- Plant Simulation shows the content of the window Show Attributes and Methods in English .
- Plant Simulation shows the names which the command Auto Complete in the Method-Editor suggests, in English .
- If the plant in the destination country uses the AM/PM time format (12 hours), you can also select this.
- Then click Create New Model on the Start page .
- Plant Simulation shows the names of the folder, which contain the objects, and the names of the objects in English , while the menus and the names of the dialog items in the dialogs are still German .

<!-- image -->

<!-- image -->

Activate Listenfelder in der SimTalk-Sprache des Modells anzeigen / Display Down-list Boxes in the SimTalk Language of the Model if you would like to program methods and thus would like to see which values the attributes and methods return. For the model language German the expression Einzelstation.Bearbeitungszeit.Typ ( Station.ProcTime.Type ) returns Konst , for the model language English it returns Const . Show the list boxes in the user interface language of Plant Simulation if you are, for example, working with an Application License . Then the contents of the drop-down list boxes is shown in the same language as the other dialog items.

<!-- image -->

- The German Plant Simulation Help shows the English names of the methods, attributes, and read-only attributes next to the German names. This makes it easier to program methods with English identifiers.
- The window Show Attributes and Methods (F8) also shows the English names of the methods, attributes, and read-only attributes.

<!-- image -->

Back to Creating a Simulation Model

<!-- image -->

##### Introducing Classes

#### Introducing Classes

Imagine that, for example, you have to find the optimum type of store for a production plant. First, you have to come up with different types or stores that might work for the specific plant, such as a fully automated high bay warehouse, a manually operated shelving system, etc. To be able to compare the different types of stores, you are going to build several simulation models, execute simulation runs, and suggest the type of store with the best cost/gain relation.

Your simulation models are going to be variants of a single basic model, i.e., you are going to use the same production plant and are going to modify the store.

When creating the model variants you are going to build the basic model first. In conventional systems you would then copy this basic model until you arrive at the number of variants you need. In Plant Simulation , on the other hand, you will inherit this basic model, which we call the parent model , and get child models . The main difference between a copied and an inherited model is that a child model recognizes which parent it is derived from while a copied model knows nothing about its origin.

Now you are going to insert the different types of stores into the model variants you created. If you now find a modeling error while modeling the basic model or if a specification changed, a conventional system requires changing all copies, which is time-consuming and error-prone.

In Plant Simulation , on the other hand, you make the change once in the parent model. It then immediately propagates all of your changes to all of its children, provided you did not change the setting in the child model. This saves a considerable amount of time and the hassle of manually updating a number of sub-models.

**Back to Creating a Simulation Model**

Classes, Subclasses, and Instances

When creating your simulation model, keep in mind that:

- A class is the template for an instance , which you insert into a Frame . All objects in the Class Library , those we built-in as well as those you yourself define, are class objects. You can add more detail to these classes and thus create new classes that inherit properties from the master classes.

<!-- image -->

By changing a property in the class object, you change that property for all objects you derived from this class. This is much less error-prone than having to change the same property for each and every individual object over and over again.

**Note**

We recommend to not change the default settings of the built-in objects if at all possible. When you customize these objects and when you merge models or update the Class Library at a later point in time, Plant Simulation discards your changes and restores the default settings. For this reason you have to customize the objects anew.

If you need objects with customized settings, we recommend to derive the respective object/objects in the Class Library and then continue working with this class. You can then place these objects into the folder User Objects and add them to the tab User Objects in the Toolbox .

- A class passes all of its properties on to an instance you derive from it.
- A class passes those of its properties on to a subclass you derive from it, for which you do not deactivate inheritance. Remember that a button that looks like this means that inheritance is active.

**Note**

Inheritance only works from class to subclass / instance , not the other way around!

- A subclass is an object in the Class Library , which inherits some, but not all, of its properties from another class . By deactivating inheritance for certain dialog items, you can define properties that only apply to this subclass. An example of subclasses could be several conveyors that only differ in their length.

To create a subclass from a class , right-click the class in the Class Library and select Derive . Plant Simulation places the derived object in the folder UserObjects . When you open the dialog of the derived object, you will notice that inheritance is active for all dialog items, denoted by a button that looks like this . Then, change the identifying property of the subclass. In our example below we derived the object Conveyor to create the subclass. We renamed it to Conveyor\_5m and changed its length to 5 meters.

<!-- image -->

Instead, you can hold down Ctrl and Shift , and click the object you want to derive an instance from with the left mouse button. Then, hold down the mouse button, drag the object to the location of your choice, for example into another folder in the Class Library , and release both keys and the mouse button.

- To create a copy from a class, right-click the class in the Class Library and select Duplicate . When you open the dialog of the duplicated object, you will notice that inheritance is deactivated for all dialog items, denoted by a button that looks like this .

Instead, you can hold down Ctrl , and click the object you want to duplicate with the left mouse button. Then, hold down the mouse button, drag the copy to the location of your choice in the Class Library , and release Ctrl and the mouse button.

- An instance is an object, which you insert into your simulation model from the Class Library or the Toolbox by dragging a class object to a Frame and dropping it there.

The objects use class relations and origin relations to inherit their properties from other objects:

- The object inherits all of its basic properties from its class object. This includes settings it has by default, built-in Methods , basic functionalities, etc. The class is the object in the Class Library you instantiated the selected object from.
- The object inherits its settings from the origin object, provided you did not change them locally within the object. The origin of the selected object is the object you derived it from.

<!-- image -->

Making full use of the potentials of inheritance saves a considerable amount of time and effort during modeling.

**See also**

**Inheritance [general description]**

**Back to Introducing Classes**

##### Replacing and Merging Objects with Drag-and-Drop

While creating your simulation model you can:

**· Replace an instance with a class**

Hold down Alt while dragging the class object on the instance and dropping it there. This way you can, for example, replace a Station with an AssemblyStation . Plant Simulation preserves all connected Connectors , but deletes all MUs on the object.

**Note**

Plant Simulation also lets you copy the attribute values of the previous instance into the new instance. When you select to not do this, the new instance is in the same state as an instance you inserted from the Class Library , i.e., all built-in attributes are inherited and all user-defined attributes and sensors, which you defined in the previous instance, will be discarded.

<!-- image -->

**Note**

When replacing an instance of an object with the class of another object, Plant Simulation retains the existing name. This prevents you from having to change the existing name in a control or a table, for example.

**· Merge classes**

Hold Alt and the left mouse button down. Then drag the replacing object in the Class Library over the class to be replaced, and drop it there.

Compare Merge Classes, Example

Compare Exchange Classes, Example

Back to Introducing Classes

##### Using Inheritance

Using Inheritance

Inheritance enables one class or object to incorporate data or behavior of another class or object.

Inheritance has a number of applications, among them:

- Specialization of existing classes or objects. Here, the new class or object has data or behavior aspects, which are not part of the inherited class
- Extension to provide additional data or behavior features. In contrast to the case of specialization, with extension the new data or behaviors could have been provided in the inherited class because they are generally applicable to all instances of the class.
- Code re-use to allow a new class to re-use code, in our case any of the settings you selected, which already exists in another class.

The check box to the right of a dialog item turns inheritance for that item in the dialogs of the Plant Simulation objects off or on.

- A button that looks like this means that inheritance is turned on. Then the object inherits, i.e., uses, the value from the origin object from which you derived it. When you change the value of the origin object, Plant Simulation also changes the value of the derived object.

Let us illustrate this with an example. We derive the Station in the Class Library and insert it from the Class Library into the Frame Model1 . Then, we derive Model2 from Model1 . The origin of the Station in Model2 is the Station in Model1 . When we now change the value of an attribute that inherits its value in the Station in Model1 , the Station in Model2 also applies this value.

- A button that looks like this means that inheritance is turned off. The values you enter only apply to the current object.

The minus sign in the orange button is intended to assist our vision-impaired users to recognize that inheritance is turned off.

Notes

The object might display the current value only after you click Apply .

In the object Dialog you can recreate inheritance using the feature New Check Box .

Back to Introducing Classes

Video on YouTube

[https://youtu.be/DwZkGMxXJIA?si=FAz76pLhEAR2X9Tv&amp;t=22](https://youtu.be/DwZkGMxXJIA?si=FAz76pLhEAR2X9Tv&t=22)

###### Show Inheritance Relations in the Class Library

The objects can use class and origin relations to inherit some, or all of their properties from other objects. To get an overview over which object inherits from which other object, right-click the object you are interested in in the Class Library and select Show Inheritance .

The dialog Inheritance show the paths of all objects that are derived from the selected object and thus inherit some or all of its properties from it.

<!-- image -->

**Back to Using Inheritance**

Show the Origin of an Object in the Class Library

The objects can use class and origin relations to inherit some, or all of their properties from other objects.

To select the object in the Class Library that the selected object was instantiated (derived) from, right-click the object you are interested in in the Class Library and select Show Origin .

<!-- image -->

You can repeat this to move up in the hierarchy until Plant Simulation does not select another object. Then you have reached the object from which the selected object was derived from originally, i.e., its origin.

**Back to Using Inheritance**

#### Working with Classes in the Class Library

Working with Classes in the Class Library

The Class Library shows the built-in objects in a hierarchical structure in folders and sub-folders. By default the Class Library contains a folder with MaterialFlow objects, with Fluid objects, with Resource objects, with InformationFlow objects, with MUs , with UserInterface objects, with UserObjects , for Models and for Tools . When you start modeling, you will derive child objects from the built-in class objects or from class objects you, or a co-worker, built from scratch.

Plant Simulation initially opens the Frame named Model for creating your simulation model, and any other Frames you add later on, in the Models folder. The folders in the tree window share a number of properties with the other objects. Among others you can apply a number of control methods , for example the rename control , etc.

<!-- image -->

**Note**

If at all possible, we recommend to not change the standard settings of the built-in objects. If you customize them and then merge models later on or if you update the Class Library later on, your customized settings are going to be discarded and replaced by the standard settings. You then have to make your customizations again.

If you need objects with your own settings, we recommend to derive the respective object in the Class Library and then work with this class. Plant Simulation places duplicated and derived objects in the folder UserObjects .

When you add an add-in program, the Class Library also shows its objects-either loose or in a folder of its own-on the topmost level of the structure below Basis . Basis designates the Class Library itself, compare the anonymous identifier basis .

Compare Work with Objects in the Toolbox

Go to Classes, Subclasses, and Instances

Go to Using Inheritance

Go to Configure the Class Library

Go to Create a Folder Structure for Your Simulation Model

Go to Create and Work with Your Own Classes

Back to Introducing Classes

Configure the Class Library

Configure the Class Library

You can configure the Class Library to best meet your needs. You can do this for new simulation models which you create and for any of your existing models. This results in a lean Class Library and an uncluttered Toolbox , preserving precious screen space. You can:

- Add Basic Objects to the Class Library or Remove Them from It . Naturally you can also add or delete objects at a later point in time.
- Optimize the model.

The option Clean up class library looks for classes that are not used in the model file and deletes them.

- Add a Library or a Tool to or Remove it from the Class Library .
- Add a Library, Which You Yourself Developed .

- Update a Library .

When you select the command File &gt; New Model for the first time, Plant Simulation opens the dialog Manage Class Library by default.

Compare Using Inheritance

Compare Save a Folder or an Object and Load it into Another Model

Compare Save a Folder as a Library

Compare Update the Class Library

Back to Working with Classes in the Class Library

Add Basic Objects to the Class Library or Remove Them from It

To add the built-in objects , which are part of your program package, to the Class Library and to the Toolbox :

- Select the objects, which you need for creating the current and future simulation models. Clear the check box for the objects, which you do not need.
- Click Apply to add the selected objects to the Class Library and to the Toolbox or to remove them from it.
- If you want Plant Simulation to always show this dialog, when you open a new model, select the check box Always Show This Dialog When You Open a New Model . Then you can configure each simulation model to your liking. If you want to use the same settings for all new simulation models, clear the check box.

<!-- image -->

- If you want Plant Simulation to apply the settings you selected in the dialog to all new models, which you create hereafter, click Apply to New Models .
- Click OK , when you're done configuring the Class Library .

**Back to Configure the Class Library**

Add a Library or a Tool to or Remove it from the Class Library

To add any of the built-in tools or libraries , which are part of your program package, to the Class Library and to the Toolbox or remove them from it:

- Select one or several tools and libraries, which you need for creating the current and future simulation models.

Clear the check box for the tools or libraries, which you do not need.

<!-- image -->

- Click Apply to add the selected objects to the Class Library and to the Toolbox or to remove them from it.

Plant Simulation adds the selected folder to the Class Library and the Toolbar of the tool to the Toolbox .

**Back to Configure the Class Library**

Add a Library, Which You Yourself Developed

To add one of the libraries , which you yourself developed, to the Class Library and to the Toolbox :

- Tell Plant Simulation where to look for the library, which you are going to add. This location may be a folder on a local computer or on a network drive.

Select File &gt; Preferences . Click to the right of Libraries Directories and select the path.

You can also type in several directories separated by a semicolon. The library manager checks this folder/these folders for the most up-to-date version of a library and lets you download it to your hard drive from there. This enables you to add company-specific and project-specific libraries to your simulation model.

**Click OK .**

<!-- image -->

- The dialog Manage Class Library shows the library, My Final Assembly Library EU in our example, on the tab Libraries under Additional Libraries .
- Click OK to add the library to the Class Library and to the Toolbox .

<!-- image -->

**Back to Configure the Class Library**

**Update a Library**

You can update an outdated library on your computer with a newer version with the library manager . Let's say you have to update a model, which you haven't worked with for a while and which contains a library. If the library manager finds a newer version of the used library in the directory, which you entered under File &gt; Preferences &gt; Libraries Directories , the Message Bar show this message:

<!-- image -->

- Click Manage Libraries . The dialog shows libraries in red for which a newer version is available.

<!-- image -->

- In the dialog Manage Class Library click in the cell below version to show the version number of the newest version and select it if you want to update the Class Library . Click OK .

Plant Simulation show a Merge Report with detailed information about added and deleted objects, about the instances of the objects which were affected by the changes and which classes were deleted.

<!-- image -->

- Click OK , when you're done configuring the Class Library .

To update all libraries, which are not current, to the most current state, click Update All Libraries . Plant Simulation only shows the button when you opened a model. It does not show it when the dialog is opened while creating a new model. When you click the button, Plant Simulation selects the most recent available version number of all loaded libraries. It only actually updates the libraries when you click the OK or the Apply button.

Back to Configure the Class Library

##### Create a Folder Structure for Your Simulation Model

Before you start modeling, we recommend to think about the structure in the Class Library of your simulation model, as a clear structure will facilitate locating the objects.

To get an idea about structuring, you might want to take a look at the libraries that were installed, when you set up Plant Simulation . By default these are located in C:\Program Files\Siemens\Tecnomatix Plant Simulation XX\Libraries .

<!-- image -->

When you start modeling, we recommend to create new folders for the objects you use in your model, rather than store the objects within the built-in folders. Otherwise the risk of changing the built-in objects inadvertently might have confusing and unpredictable effects. This also facilitates saving your library as an object file, which you can then load into any existing simulation model.

We intended the folder UserObjects for this purpose, You can then add these objects to the tab User Objects in the Toolbox .

You can also create subfolders and thus structure your Class Library clearly. Proceed as described below.

If you do not want to use the folder User Objects , you can create your own folder:

- Right-click Basis in the Class Library if you want to insert the new folder on the same level as the built-in folders.
- Right-click any folder in the Class Library if you want to insert the new folder into that folder.
- Select New &gt; Folder .
- Rename the folder: Click NewFolder once and type in a meaningful name. In our library we use ApplicationObjects .

<!-- image -->

<!-- image -->

We also recommend to create a sub-folder for the basic, built-in objects that your simulation model uses, within the folder ApplicationObjects . In our library we named this sub-folder BasicObjects . This makes your library independent of the language of the model that the user selects and of the naming conventions of the built-in objects you use in your model. In addition, this simplifies loading the library into other models, as this mechanism makes merging objects superfluous.

Compare Using Inheritance

Compare Save a Folder or an Object and Load it into Another Model

Compare Update the Class Library

Back to Working with Classes in the Class Library

Set the Root Folder for Your Simulation Model

To prevent Plant Simulation from wasting RAM, you might, for example, not want to insert a Method that has numerous instances into numerous Frames . Instead, you can directly call this Method , in which you programmed an action that many objects use, from the Class Library . In this case, you can use the anonymous identifier RootFolder to avoid long paths.

When you use RootFolder in a Method , the RootFolder is a folder in the Class Library for which you have set the attribute RootFolder to true . Then, Plant Simulation searches for that folder, starting with the class of the Method , upward in the hierarchy of objects.

In your library, you will, as a rule, set the top folder that contains all your application objects as the rootfolder. This enables you to access any of the application objects you created, to access any of the dialogs you, or your colleagues designed, and so on.

To set the root folder:

- Use the attribute RootFolder . You might, for example, enter this into a Method :

```simtalk
.ApplicationObjects.Transport.RootFolder := true
```

Or

- Right-click the folder you would like to use as the root folder in the Class Library . Select Show Attributes and Methods , and click in the window. Press r on the keyboard and scroll down to RootFolder . Double-click it, type true into the dialog that opens and click OK . Plant Simulation adds an upper-case R to the icon of the folder .

<!-- image -->

This example illustrates one of the usages of the root folder.

We designated the folder ApplicationObjects as the RootFolder . We inserted all objects that numerous other objects use into the Frame named MyComponent1 . An example is the method openObject that opens a context menu for the objects and that provides the command Open Component . This enables us to access the method openComponent from this one central location by entering RootFolder.MyComponent.openComponent on the Frame ribbon tab Context Menu &gt; Context Menu of the Frames for which we want to provide a context menu.

<!-- image -->

You can also use the anonymous identifier RootFolder within Methods in which you programmed controls. Here Plant Simulation looks for the folder for which you set the attribute RootFolder , starting with the class of the Frame into which you inserted the object in which you programmed the control.

Compare Create a Folder Structure for Your Simulation Model

Back to Working with Classes in the Class Library

Creating User-defined Classes

Create and Work with Your Own Classes

If at all possible, we recommend to not change the standard settings of the built-in objects. If you customize them and then merge models later on or if you update the Class Library later on, your customized settings are going to be discarded and replaced by the standard settings. You then have to make your customizations again.

If you need objects with your own settings, we recommend to duplicate or derive the respective object in the Class Library and then work with this class. Plant Simulation places duplicated and derived objects in the folder UserObjects .

The folder UserObjects provides these objects by default:

<!-- image -->

**You can:**

- Create Your Own Classes

###### Create Your Own Classes

- Work with Your Own Classes

Compare Work with Objects in the Toolbox

Back to Working with Classes in the Class Library

Create Your Own Classes

To create your own customized classes , you can either derive one of the built-in classes in the Class Library and modify its features, or you can built a class of your own from scratch, for example in a Frame in the Class Library .

To create a class that shares all of its features with the parent class:

- Do not change anything in the class object you want to derive an instance from. Then, right-click that object in its folder in the Class Library and select Derive .

This adds the derived class to the folder UserObjects . Then, rename the new class.

Or

- Select multiple objects in the Frame and drag-and-drop them onto the respective folder in the structure in the Class Library to create classes of these objects.

Or

- Hold down Ctrl and Shift , and click the object with the left mouse button. While holding the mouse button down, drag the object into another folder in the Class Library , and release both keys and the mouse button. Be aware that the class object keeps its previous name, when you proceed like this. Then, you can rename the new class.

To create a subclass that shares some, but not all, of its features with the parent class:

- Deactivate inheritance in the class object for the features you want to modify in each of the instances separately. Remember that a button that looks like this designates that. The features with active inheritance will be passed on unchanged to the instances of the class object.
- Right-click the class in its folder in the Class Library that has the features you would like to use and select Derive . This adds the derived class to the folder UserObjects . Then, rename the new class.

Or

- Hold down Ctrl and Shift , and click the object with the left mouse button. While holding the mouse button down, drag the object into another folder in the Class Library , and release both keys and the mouse button. Be aware that here the class object keeps its previous name. Then, you can rename the new class.

To create a class of its own , which originally shares the settings of the original class, but does not keep an inheritance relation with it:

- Right-click the class in its folder in the Class Library that has the features you would like to use and select Duplicate .

This copies the selected object or model and creates a new class from it, severing all inheritance relations. Plant Simulation adds the duplicated class to the folder UserObjects . Changes you make to the original class object are not passed on to the copy you create. Or

- Hold down Ctrl , and click the object you want to duplicate with the left mouse button. While holding the mouse button down, drag the copy to another folder in the Class Library , and release Ctrl and the mouse button.

Compare Classes, Subclasses, and Instances

Compare Using Inheritance

Back to Create and Work with Your Own Classes

Work with Your Own Classes

After you created your own classes, you can work with them like you do with the built-in classes.

- Plant Simulation places duplicated and derived objects in the folder UserObjects . Double-click the respective object to edit its properties. Insert the objects into your simulation model like you do with the built-in classes.

<!-- image -->

- You'll also want to add your classes to the toolbar UserObjects . Just drag the object class from the folder UserObjects to the toolbar UserObjects .

<!-- image -->

Back to Create and Work with Your Own Classes

Work with Folders, Frames, Objects in the Class Library

To move a folder in the tree window :

- Select the folder you want to move in the tree window by clicking it with the left mouse button.
- Drag it to the folder above which you want to place it in the structure and drop it there.

To move a folder , a Frame or an object into another folder in the tree window:

- Click the folder, Frame , or object you want to move into another folder with the left mouse button to select it.
- Hold down Shift , drag the object to the destination folder and drop it there.

<!-- image -->

The move pointer looks like this

.

To copy a folder , a Frame , or an object into another folder in the tree window:

- Click the folder, Frame , or object you want to copy into another folder with the left mouse button to select it.
- Hold down Ctrl , drag the object to the destination folder and drop it there.

<!-- image -->

The copy pointer looks like this

.

To merge folders , hold down Alt and drag the replacing folder in the Class Library into the folder to be replaced and drop it there. Plant Simulation then forms the superset of both folders and merges those classes, which are present in both folders.

To merge objects , hold down Alt and drag the replacing object in the Class Library into the object to be replaced and drop it there.

To arrange the order in which Plant Simulation shows objects within a folder in the tree window , for example sort them by function or by name:

- Click the object with the left mouse button to select it.
- Hold the mouse button down, drag the object to the location of your choice in the folder and drop it there.

To add icons of objects to the toolbar in the tree window:

- Click the object with the left mouse button to select it.
- Drag the object to the object name of the toolbar located at the bottom of the respective folder and drop it there.

To rename an object , do one of the following:

- Double-click it, and enter another name into the text box Name .
- Press F2 and enter another name.
- Select Rename on the context menu and enter another name.
- To rename an open object, press F4 and enter another name into the dialog Rename .

##### Back to Working with Classes in the Class Library

Show the Contents of a Frame in the Class Library

Plant Simulation does not show objects you insert into any Frame in the Models folder, as it only shows classes of objects in the Class Library , not instances of those classes.

<!-- image -->

To view the hierarchical structure of objects within a Frame , right-click the Frame in the Class Library and select Show Structure on the context menu.

<!-- image -->

Compare Find Objects and Text in Your Simulation Model

**Back to Working with Classes in the Class Library**

Saving a Folder or an Object and Loading it into Another Model

Save a Folder or an Object and Load it into Another Model

You can load an user-defined object, which may be a single object or an entire simulation model you created in a Frame , into other simulation models or share it with your co-workers.

As compared to an object file a library is a collection of objects for which you enter a version , which you maintain over time and which you share with your colleagues. The version number enables you to either update your simulation models with a newer version of the library or to stay with the present outdated version.

<!-- image -->

**You can:**

- Save a Folder as a Library
- Save an Object or a Folder as an Object
- Load an Object or a Folder into Your Simulation Model
- Load an Object or a Folder into Another Folder

Compare Configure the Class Library

Compare Update the Class Library

Back to Working with Classes in the Class Library

Save a Folder as a Library

To save a folder as a Plant Simulation library (.pslib), right-click it in the Class Library and select Make Library .

<!-- image -->

This opens the dialog Library Information .

<!-- image -->

- Type in the Name of the library. You can type in any combination of letters, numbers, spaces, and special characters.
- Type in the Version of the library. You can enter any number of number and letters separated by periods.
- Type in a meaningful Description of the library.
- Click OK .

The icon of a library in the Class Library looks like this .

<!-- image -->

To also use this library in other models, save the library as a file. To do so, click the library with right mouse button and select Save/Load &gt; Save Library As . If you would like the library to be available in the dialog Manage Class Library later on, you have to select a location within the directory which you entered under File &gt; Preferences &gt; General &gt; Libraries Directories .

<!-- image -->

You can then load this library into other simulation models and share it with your co-workers. To do so, click Manage Class Library on the Home ribbon tab in Plant Simulation window.

You can edit the information you typed in when you created the library by clicking the library with the right mouse button in the Class Library and by selecting Edit Library Information .

In addition, you can type in one or more alternative paths for your library. As a rule, you will not enter an alternative path.

Plant Simulation identifies a library by its absolute path to the library folder in the Class Library . When you type in an alternative path, this absolute path will also be assigned to this library. This may be helpful for two reasons:

**Procedure**

1. When you rename the library folder in a new version of your library or when you move the library into another folder, the absolute path of the library changes.

<!-- image -->

Plant Simulation will from then on treat the library as another library. If you do not want this, you can type in the previous path to the library as an alternative path. This way you can update a model, for which the library is still located under the previous path, with the new library. For this model, the library remains at its previous location in the Class Library .

<!-- image -->

2. You can use alternative paths to assign several names in different languages to the library folder. We, for example, also assigned the German path .Tools.EngpassAnalyse language to the library .Tools.BottleneckAnalyzer . For this reason Plant Simulation considers both folders as the same library and can thus update both folders with the same library file.

**Note**

When you type in the name of a language between $ signs in front of the alternative path, for example $German$ or $Japanese$ , Plant Simulation will automatically use this path, when you load this library into a model with this language, i.e., when the model did not already contain this library. The alternative path for the BottleneckAnalyzer is $German$.Tools.EngpassAnalyse for example.

<!-- image -->

When renaming a library in the Class Library , pay heed to the messages that Plant Simulation displays!

<!-- image -->

Click No in the dialog to retain the library properties of the folder. Clicking Yes will make the folder a normal folder again without any of the properties that designate a library.

<!-- image -->

If you want the renamed library to be treated as a different library from now on, click Yes .

Renaming the library folder does not change the name of the library as such, it will still have the same name as before.

<!-- image -->

**Note**

When you insert objects into a Frame of the library, you are only allowed to use objects from inside of your library or objects from other libraries. If your library uses objects from other libraries, Plant Simulation saves all dependent libraries into the .pslib file when you save your library.

**Note**

When you use a library in your simulation model or in a different library, we strongly advise against modifying the classes located inside the library. If, for any reason, you need to change the behavior of a library class, you nevertheless should never modify the class itself, but derive it. Plant Simulation will place the derived class into a subfolder named Public . You may modify the derived class and use it in your simulation model.

When you later update the library - although the new version of the library does not have this Public folder Plant Simulation will not delete the Public folder.

Compare

Configure the Class Library

Compare

Update a Library

Back to Save a Folder or an Object and Load it into Another Model

Save an Object or a Folder as an Object

To save an application object as an Plant Simulation object file (.psobj), right-click it in the Class Library and select Save Object As .

Enter a name into the dialog Save As and specify a location. Plant Simulation saves the object, and all objects, which that object uses, together with their folders and paths.

To save a folder, which may contain an entire library, as an Plant Simulation object file (.psobj), right-click it and select Save Folder As .

Enter a name into the dialog Save As and specify a location. Plant Simulation saves the folder and all objects it contains.

Back to Save a Folder or an Object and Load it into Another Model

Load an Object or a Folder into Your Simulation Model

To load an object or a Frame/folder into your open or into another simulation model, right-click any folder and select Load Object . Plant Simulation loads the object with all of its existing paths and the folders, sub-folder and classes the object inherit values from into the Class Library at the Basis level.

To preserve the existing objects in your simulation model, and to discard duplicate objects that are contained in the model you load, you will use Load Object , and then select to Replace the loaded class with the one in the class library .

To port a lower version of a simulation model or of a library to a higher version with modified and improved classes, you will use Update Class Library .

- Right-click any folder in the Class Library and select Load Object on the context menu.
- Select the object in the dialog Open .
- If an object or a Frame with the same name as the object to be loaded already exists in your simulation model, Plant Simulation opens the dialog Replace or Rename Class .
- To Replace the loaded class with the one in the class library , select the radio button. Then, Plant Simulation does not load the new object, but replaces it with the existing object and merges all inheritance hierarchies into one.
- To replace all duplicate objects, click Replace All .
- To Rename and keep the duplicate class , select this.
- Enter a new name for the duplicate object into the text box.

<!-- image -->

**Note**

When the object to be replaced is a Frame , click Replacement Mode on the Frame ribbon tab of the Frame . Then, select if you want to Merge the contents of the new Frame with the existing one or if you want to Exchange the existing Frame with the new Frame .

Repeat this until all duplicate objects are renamed or replaced.

If you are unsure if both classes are identical, we recommend that you enter a new name and compare the classes. You can still replace the objects at a later point in time:

- Hold down Alt , click the replacing object and drag it over the object to be replaced while holding the left mouse button down.

- When replacing and merging is possible, a dialog opens where you can confirm that you want to replace the object or not replace it.

Instead of using Load Object , you can also drag an .psobj file from the Windows Explorer to the Class Library , and drop it there.

**Back to Save a Folder or an Object and Load it into Another Model**

Load an Object or a Folder into Another Folder

To load an object or a Frame that you saved as an object file (.psobj), into the folder in the Class Library , which you select, right-click the folder and select Load Object into Folder . Plant Simulation loads the object, with its complete structure of objects, which this object uses and which are used by it, into this new folder.

**Note**

As a rule, you will create a new folder before you load the object or the folder.

You will use Load Object into Folder , when you do not want to replace any of the existing objects and their hierarchical structure in your simulation model with the object/objects you are going to load.

The tools in the Tools folder in the Class Library , such as the BottleneckAnalyzer , use this technique and provide their own parametrized BasicObjects that are independent of the object classes in the built-in folders.

Back to Save a Folder or an Object and Load it into Another Model

###### Update the Class Library

To update a library, you and your coworkers are working on, with the most up-to-date classes you developed or to port a lower version of a simulation model or of a library to a higher version with modified and improved classes:

- Save the object as an object file (.psobj): Right-click it and select Save Object As .
- Right-click any folder in the Class Library and select Save/Load &gt; Update Class Library . This loads the object into the Class Library at the Basis level.

When loading the object file, Plant Simulation supposes that the classes in the file it is loading are the most recent ones, and replaces any existing classes with the same name in your model file. This replaces the old class with the new class, but attaches any instances of the old class to the new class, and thus preserves the settings you made in these instances. This applies for classes that are located in the hierarchy directly below the newly saved class.

For classes that were saved through an inheritance relation, and that are located outside of this hierarchy below a class, Plant Simulation opens a dialog, where you have to select to replace any duplicate classes or to rename them.

Compare Save a Folder or an Object and Load it into Another Model

Back to Working with Classes in the Class Library

#### Working with Objects in the Toolbox

Work with Objects in the Toolbox

The Toolbox is a container for the different Plant Simulation toolbars that hold the objects of the Class Library . By default, the Toolbox shows the built-in objects on the toolbars Material Flow , Fluids , Resources , Information Flow , User Interface , Mobile Units , and Tools . You find the toolbars for the objects at the very bottom of their folders next to the icon .

<!-- image -->

When you add an add-in program by clicking Manage Class Library on the Home ribbon tab, Plant Simulation also adds a tab/toolbar with the objects of this add-in.

- To add your own toolbars to the Toolbox , right-click the folder you want to add the toolbar to and select New &gt; Toolbar .

Plant Simulation adds toolbars you define, toolbars with the objects of add-in products ( Home &gt; Manage Class Library ), and toolbars of object libraries to the right of or below the tabs of the built-in objects in the Toolbox .

- To add an object to a toolbar you defined, drag the object from a folder of the tree view in the Class Library to the window/toolbar you defined into the Toolbox and drop it there.

**Note**

After you inserted an object from the Toolbox into a Frame , Plant Simulation automatically switches back to the tool Select on the toolbars of the Toolbox .

- To change the name Plant Simulation show on the toolbar, go to the folder that contains the objects in the tree view, select the icon at the very bottom of the folder, press F2 and enter a term of your choice into the text box Label . If you do not enter a label, Plant Simulation shows Toolbar , i.e., the name of the toolbar in the Toolbox .

- To open the class of the object, right-click it and select Show Class .

**You can:**

- Add Objects to the Toolbox or Delete Them from It
- Copy Objects from Toolbar to Toolbar
- Insert an Object from the Toolbox

Compare Toolbox

Back to Working with Classes in the Class Library

Add Objects to the Toolbox or Delete Them from It

You can add a single or multiple objects to and remove them from a Toolbar in the Toolbox and change the order of the icons:

- To add an object to a Toolbar , drag it from its folder in the Class Library to the toolbar of your choice and drop it there.

**Note**

When you derive an object from another object in the Class Library , modify the icon of the new object, and add it to the toolbar, you might have to resize the window before Plant Simulation displays the new icon.

- To add multiple objects to a Toolbar , select them and drag them from their folder in the Class Library to the toolbar of your choice and drop them there.
- To remove a button/object from the Toolbar , right-click it and select Remove from Toolbar .
- To change the order in which the icons of the objects are displayed on the Toolbar , click the button you would like to move and drag it to a different location on the toolbar.

Compare New [Folder, Frame, Toolbar]

Back to Work with Objects in the Toolbox

Copy Objects from Toolbar to Toolbar

To adapt simulation models that you created in previous versions of Plant Simulation , you can use the following technique to copy objects from one toolbar of the Toolbox to another. This is especially handy for Toolboxes that contain a large number of objects:

- First, select the toolbar containing the object you would like to add to another tab.

- Right-click the folder whose tab you would like to add the object to in the tree window and select Show Structure . This opens the window Structure . Expand the folder here.
- Hold down Ctrl and click the object you would like to copy on its toolbar in the Toolbox . This selects the object in the tree window.
- Drag the object from the tree window to the icon of the toolbar in the dialog Structure .

**Back to Work with Objects in the Toolbox**

#### Modeling Hierarchically

Model Hierarchically [general]

Modeling hierarchically is the concept of inserting components, which you modeled in a Frame , into other Frames . This way you can model, and test, the individual components of your simulation model detached from the Frame which holds your complete simulation model.

<!-- image -->

You can combine any number of components in the Frame in which you build your overall model. In our example we modeled a component in the Frame named MyComponent1 and inserted it into Frame MyPlantAnytown , which holds our complete simulation model.

<!-- image -->

<!-- image -->

To open the window of the Frame from which the current Frame has derived, click . In our example, clicking Open Origin opens the Frame MyComponent1 in the folder ApplicationObjects &gt; Components in the Class Library .

You can thus model the components, such as large machines or entire departments, to match their counterpart in your real-life plant as closely as possible. You can also insert these components several times. You can use these components in exactly the same way as you use any of the other user-defined or built-in objects. You can create icons for them and insert them into your model just as you would any of the material flow objects. In addition it enables you to clearly structure your simulation model.

<!-- image -->

Another advantage of modeling hierarchically is the fact that you can distribute developing the simulation model among several colleagues, even among several sites. You can then integrate the components into the complete model at any point in time.

Compare Working with the Frame

Compare Show the Contents of a Frame in the Class Library

Compare Model Transitions Between Frames

Compare Modeling Hierarchically [in 3D] in 3D

Back to Creating a Simulation Model

Test a Component You Modeled

Modeling hierarchically enables you to test the components detached from your complete simulation model, thus ensuring that they work as intended, before integrating them. For this you can create a testing environment with the desired level of detail. Insert the component into the test Frame , insert a Source and a Drain , connect all objects and start the simulation.

Back to Model Hierarchically [general]

<!-- image -->

#### Working with the Frame

Working with the Frame

As a rule you will create your simulation models in the Frame that we placed in the folder Models in the Class Library . Naturally, you can also insert additional Frames into this folder and model there.

To rename this Frame , so that it matches the name of the plant you are modeling, do one of the following:

- Right-click it in the Class Library and select Rename .
- Select it in the Class Library and press F2 .
- In the Frame window itself, click Rename on the Home ribbon tab or press F4 .

To build your simulation model, you will insert any of the built-in objects or any objects you yourself design, and connect these objects, which represent your stations, with the Connector .

To run the simulation you will insert an EventController that starts, stops and resets the simulation run. You can use each and every simulation model as an application object to create additional simulation models.

By placing Frames within Frames you can build hierarchically structured models. This way you can build and structure simulation models that exactly match the real world systems you want to simulate. It also enables you to break down complex tasks into manageable chunks and distribute a laborious task to several co-workers.

**Back to Creating a Simulation Model**

##### Select Options in the Frame in 2D

You can select general options for modeling under File &gt; Preferences / Model Settings in Plant Simulation window. You can also select options for each Frame individually, which only apply to that Frame .

<!-- image -->

<!-- image -->

Initially any Frame you insert into your model uses the settings you selected under File &gt; Preferences/ Model Settings in the Plant Simulation window. Select any of the commands to activate or deactivate them for the selected Frame . To restore the built-in settings, and deactivate any of your changes, select Inherit Settings .

<!-- image -->

Compare Select Settings in Plant Simulation

Back to Working with the Frame

Model with Objects from the Class Library

Model with Objects from the Class Library

To create a simulation model, you will insert instances of the class objects from the Class Library folders into your model. This, as a rule, will be the Frame that is located in the folder Models in the Class Library .

You can modify and expand the structure of the Class Library to meet the requirements of your simulation project. You might, for example, add additional folders to save your simulation models, the test runs and the different components of your model to.

**Note**

You can rename any object in the Class Library . Be aware though that your simulation model may not run correctly any more when you rename an object that you entered as entrance or exit control into another object or MUs Plant Simulation entered in a Source object under Attributes &gt; MU Selection &gt; MU . In these cases the path statements will be wrong after renaming objects.

**You can:**

- Insert an Object from the Class Library
- Insert an Object from the Toolbox

**Back to Working with the Frame**

Insert an Object from the Class Library

In the structure, navigate to the folder and then to the object you would like to insert. The objects are grouped according to their functions and to the frequency you use them.

To insert an instance of the class object into the Frame :

- Click the object of your choice with the left mouse button to select it. The insert cursor looks like this
- While holding the mouse button down, drag the object to the target position in the Frame window and drop it.

<!-- image -->

Back to Model with Objects from the Class Library

Insert an Object from the Toolbox

You can insert objects from the Toolbox that contains the objects grouped on tabs/toolbars. You might, for example, insert one of the built-in material flow objects from the toolbar Material Flow .

<!-- image -->

- Click the toolbar, i.e., the tab, which contains the object you would like to insert.
- Move the mouse to the icon of the object.

##### Insert Objects into the Frame

- Click the object with the left mouse button to select it.
- Move the mouse to the target position in the Frame window and click the mouse button once.
- To insert several instances of the same object class, hold down the Shift or the Ctrl key while you click the mouse button in the Frame window. This way you do not have to return to the Toolbox each time after inserting an object.
- To go to the class of an object, press the Ctrl key and click the object in the Toolbox . Plant Simulation highlights the class object in the tree window in the Class Library . Double-click that object in the tree window to edit class properties or hold down the Ctrl + Alt keys and click the object in the Toolbox . This does not work, when the object is already selected.

**Back to Model with Objects from the Class Library**

##### Insert Objects into the Frame

Proceed as follows to insert the objects, which symbolize the machines and stations in your plant, into the Frame that symbolizes the installation or plant you are modeling:

- Start Plant Simulation and open a new model: Click Create New Model on the Start Page or select File &gt; New .

This opens the Class Library with the built-in objects Plant Simulation provides, the Toolbox and an empty Frame -in the folder Models -for creating your simulation model.

- To insert an object into the Frame , do one of the following:
- Click the icon of the object you would like to insert in the toolbox , move the mouse pointer, which then turns into crosshairs (+), to the location in the Frame into which you would like to insert it and click the left mouse button once.
- Use drag-and-drop to insert objects from the class library into the Frame .
- To insert several instances of an object one after the other, click the object in the Toolbox . Hold down Ctrl or Shift , click the position in the Frame at which you would like to insert the first instance and click the left mouse button. Keep holding down Ctrl or Shift and repeat this until you have inserted the desired number of instances and then release the key.
- Insert the objects, so that your model matches the screenshot.

<!-- image -->

- Click the folder or the tab Material Flow and insert a Source , three Stations , and a Drain .
- Click the folder or the tab User Interface and insert a Chart .
- To move an object in the Frame , do one of the following:
- Click the object once with the left mouse button, hold the button down, move the icon to the desired location, and release the mouse button.
- To move the selected object one pixel at a time in the direction of the key, press the respective arrow key.
- To move the selected object one grid unit at a time, hold down Shift , and press the respective arrow key.
- To align all objects to grid points in the Frame window, select all objects by dragging a marquee over them and click Align to Grid on the Icons ribbon tab of the Frame .
- To delete an object, press the Delete key on the keyboard or click it with the right mouse button and select Delete .

Compare Insert an Object from the Class Library

Compare Insert an Object from the Toolbox

Compare Work with Length-oriented Objects in 2D and 3D

Compare Work with Objects in the Frame Window

Back to Working with the Frame

Connect Objects in the Frame

Once you have inserted the objects, you have to connect them, so that Plant Simulation can move the parts from object to object through the plant.

- Click the Connector in the Toolbox to activate connect mode. The mouse pointer turns into crosshairs (+), when it is located over an object to which you can attach a Connector .
- Click the Source and then on the Station to the right of it. This establishes the connection between the two objects, symbolized by a line. The arrow in the middle shows the direction of the connection.
- Repeat this for the other objects.

**Note**

To connect several objects one after the other without having to return to the Toolbox each time you established a connection, hold down Ctrl , while you establish the connection.

To show the source and the target of the Connector in the Frame as a Tooltip , drag the mouse over the Connector .

<!-- image -->

Your model should now match the screenshot.

<!-- image -->

Compare Connect Objects with the Connector

Back to Working with the Frame

Add a Graphic and a Color to the Background of the 2D Frame

To add a graphic to the background of a Frame in a 2D only model, do one of the following:

- Drag a .gif, .bmp, .ppm, .ppm raw, .dgn, .dxf, or a .dwg file from the Windows Explorer, the Internet Browser, the icon library etc. over the background of the Frame and drop it there.

This new graphic will then replace the icon named background of the Frame . If you have not assigned a background icon, Plant Simulation automatically creates a background icon. Plant Simulation does not automatically scale the size of the background icon to the size of the Frame !

You can also add a background picture with the methods getBackgroundImage and importGraphics .

- Drag a layout drawing over the background of the Frame and drop it there. You can use this layout drawing as the actual background of the Frame and insert the Plant Simulation
- objects on top of it. This is feasible when your simulation model is not too complex.

**Note**

If you are modeling a complex plant, this might not be practicable, as it might lead to a very cluttered layout. Then, you might want the layout drawing to be one of the icons of the Frame , and have the MUs move through the plant on the animation lines you define in the class of that Frame .

Be aware that the .dxf, .dgn or .dwg files are vector-based, whereas Plant Simulation uses pixel-based graphics. This means that you have to think about how to transfer one size to the other.

If the CAD-drawing contains units and its dimension is not greater than 32000 by 32000 pixels, Plant Simulation automatically uses the scaling factor 1.0.

<!-- image -->

If the CAD-drawing contains units and its dimension is greater than 32000 by 32000 pixels, Plant Simulation scales the drawing so that it fits into the Frame window.

You can use the Scaling Factor of the Frame to reduce the pixel size of the CAD-drawing:

- Increase the scaling factor in the dialog Scaling Factor on the View ribbon tab of the Frame in a 2D model:

<!-- image -->

- When you drag the .dwg drawing onto the background of the Frame and drop it there, a dialog opens asking for the scaling factor of the drawing. If the CAD-drawing contains a length unit, the default scaling factor of 1.0 results in the correct dimensions. If this is not the case, Plant Simulation interprets the CAD-unit as meters. The scaling factor then has to contain the conversion factor from meters into the actual unit. If the drawing units are millimeters for example, enter 0.001 .

<!-- image -->

To make the background graphic transparent, so that the background color of the Frame shines through:

- ◊ Click Icons on the Home ribbon tab to open the Icon Editor .
- ◊ Click Next Icon to navigate to the icon called background .
- ◊ Click the color picker and click in the background of the icon. This makes that color the active drawing color, which we want to replace.
- ◊ Click Replace Color on the Home ribbon tab.
- ◊ Select the transparency color in the Color Palette that replaces the active drawing color. If the transparency color is not part of the color palette, double-click any field in the Color Palette that contains a color you do not need, and enter 0 , 128 , 128 into the dialog Colors &gt; Custom and click OK .
- ◊ Click Transparent on the Home ribbon tab.
- ◊
- Click Apply Changes to make the dxf file transparent.
- Open the Icon Editor by clicking Edit Icons on the Home ribbon tab. Click New in the Edit ribbon tab, click Import , and select the type of file and the actual file you would like to open.
- Draw an icon for the Frame and name it background . Plant Simulation uses this graphic as the new background graphic.
- To delete the background graphic, select the icon with the name Background in the Icon Editor and click Delete on the Start ribbon tab.

<!-- image -->

<!-- image -->

<!-- image -->

To set a color of your choice for the background of the Frame , click the View ribbon tab and select Background &gt; Select Color . If you do not like the white frame around the icons of objects you inserted into the Frame , select the icon with the number 0 in the Icon Editor and click Transparent in the Edit ribbon tab.

Compare Set and Link Animation Points and Lines

Compare Add a Layout File to Your Simulation Model

Compare

Import a 3D Graphic

Compare

Add a Point Cloud

Back to Working with the Frame

Draw Vector Graphics or Text onto the Background of the Frame in 2D

To draw vector graphics onto the background or in the foreground of the Frame , you can use the features of the Vector Graphics ribbon tab. As opposed to the pixel-based graphics Plant Simulation uses by default, you can scale vector graphics or text without loss of quality.

**Note**

You can only insert vector graphics into a 2D only model .

- Click the Vector Graphics ribbon tab of the Frame . The shape of the cursor changes to

**Note**

As long as vector graphics mode is active, you cannot manipulate any objects in the Frame . To deactivate it, click another ribbon tab.

- Select the shape you would like to draw:

| To do this                                                                                                           | Click   |
|----------------------------------------------------------------------------------------------------------------------|---------|
| Draw a line.                                                                                                         |         |
| Draw the outline of an ellipse.                                                                                      |         |
| Draw a filled ellipse.                                                                                               |         |
| Draw the outline of a rectangle.                                                                                     |         |
| Draw a filled rectangle.                                                                                             |         |
| Type in text that is shown in the Frame . To force a line break when typing in text, type in \n and continue typing. |         |

<!-- image -->

.

<!-- image -->

- Drag the mouse into the Frame window, click the left mouse button once and drag the mouse until the shape has the form you need.
- To change the properties of the shape/text you drew, double-click it and edit its settings in the dialog Graphic Settings .
- To change the form of the shape or to move it, select it, click one of the handles and drag the mouse.

<!-- image -->

The move mouse pointer looks like this .

The change shape mouse pointer looks like this .

- To move a vector graphics object one pixel at a time, press the respective arrow key. To move a vector graphics object one grid unit at a time, hold down Shift press the respective arrow key.
- To enlarge a vector graphics object by one pixel, hold down Ctrl and press the respective arrow key.
- To enlarge a vector graphics object by one grid unit, hold down Ctrl and Shift and press the respective arrow key.
- To place an object onto a different layer, click and type the number of the layer into the text box Layer .

<!-- image -->

The layers serve two purposes:

They allow you to define the drawing order of the item you placed onto a layer.

- When you type in a negative number, -1 for example, Plant Simulation draws the shape you created onto the foreground of the Frame .
- When you type in a positive number Plant Simulation draws the shape onto the background of the Frame .

<!-- image -->

They allow you to delete all objects on a certain layer: Click and type the number of the layer you would like to delete into the text box Layer .

<!-- image -->

- To delete all objects on all layers, click

<!-- image -->

.

- To group any number of objects, hold down Shift and click each object with the left mouse button, or drag a marquee over them, and click .

<!-- image -->

- To ungroup a group, select it, and click

<!-- image -->

.

- To delete the selected shape, press Delete or click
- To delete all objects on a certain layer, click

<!-- image -->

.

Type the number of the layer you would like to delete into the text box Layer .

To draw vector objects, you can also use the methods drawEllipse , drawLine , drawRectangle , and drawText .

To delete the vector objects you can use the methods eraseLayer and eraseAllLayers .

Go to Add a Graphic and a Color to the Background of the 2D Frame

Compare Specify the Stations Which the LockoutZone Stops

Back to Frame

Create Your Own Ribbon Tab/Context Menu in the Frame

To create a user-defined ribbon tab or a user-defined context menu with your own, frequently used, ribbon commands or context menu commands respectively:

- Click Configure User-defined Ribbon Tab or Configure User-defined Context Menu on the Frame ribbon tab of the Frame for which you want to create the user-defined ribbon tab or user-defined context menu .

If a user-defined ribbon tab exists, the button on the Frame ribbon tab is highlighted.

<!-- image -->

.

<!-- image -->

- Type in the Title of the user-defined ribbon tab with which Plant Simulation shows the user-defined ribbon tab . We typed in My Ribbon Tab .
- To show the user-defined ribbon tab for the Frame , for which you defined it, select Active .
- Type in the name of the command that Plant Simulation shows on the user-defined ribbon tab in the Frame . Type an &amp; (ampersand) in front of a letter to make this letter the access key. You can select this ribbon command by holding down Alt , by pressing the predefined key combination U and T , and by the pressing that letter. The built-in Plant Simulation access keys take precedence over any access keys you define!

<!-- image -->

You can also type in a formula as a ribbon command or a context menu command. A formula is designated by a leading question mark. When you type in ?Method1 for example, the method named Method1 will be called. The return value of this method has to be of data type string . This way you can switch between different texts, for example between Activate and Deactivate and you can translate the ribbon or context menu commands into different languages. If the methods return an empty string "", Plant Simulation hides the respective ribbon or context menu command.

**Note**

You can use any formulas, even for example a method call with parameters, such as ?Method1(42) or a table access, such as ?DataTable[1,3] .

<!-- image -->

- Type in the Methods , which the ribbon/context menu commands execute into the text boxes below Method to execute .

If the method expects a parameter, Plant Simulation automatically passes it. To this parameter, which has to be of data type list , the selected objects, which are located within the same Frame is the Frame whose ribbon tab or context menu is opened, are passed.

When Methods are called from the user-defined ribbon tab , the anonymous identifier ? (question mark) points to the Frame in which you selected the command. This way you can access objects within the respective Frame .

**Note**

The commands on the user-defined context menu only apply to the selected object(s) within the Frame for which you defined the context menu.

The Class Library does not show the user-defined context menu .

<!-- image -->

- To create the user-defined ribbon tab or the user-defined context menu , click OK . Plant Simulation shows the ribbon tab to the right of the pre-defined ribbon tabs.

<!-- image -->

- To open a user-defined dialog from the user-defined ribbon tab :
- Type in the name of the command, which opens the user-defined dialog, into the text box below Text to display .
- Click to enter the path to and the name of the Method , which tells Plant Simulation to open the dialog, into the text box below Method to execute .
- Create a Method with the name you typed in above and type in name\_of\_your\_user\_defined\_dialog.open .

<!-- image -->

<!-- image -->

**Back to Working with the Frame**

##### Work with Objects in the Frame Window

Use these techniques to manipulate the objects, simulation objects as well as vector graphics you drew and inserted into the Frame .

- To open the object or the Frame window, double-click the object or a Frame in the model Frame , MyPlantAnytown in our sample model.
- To insert an object in the Frame , select the object in the Class Library or the Toolbox , drag it over the Frame window and drop it there.
- To show or hide the grid in the Frame window, click . Showing the grid makes it easier to insert an object at exactly the position you need it to be at.
- To select an object, click it with the left mouse button. You can then move it in the Frame by dragging the mouse.
- To nudge the selected object one pixel at a time in a direction, press the respective arrow keys on the keyboard. To move the selected object one grid unit at a time, press Shift + the respective arrow key.
- To deselect a selected object, click another object or click anywhere in the Frame .

<!-- image -->

<!-- image -->

- To select more than one object in a Frame at a time, hold down Shift , and click the objects you want to mark or drag a marquee over the objects: Hold the left mouse button down, and drag the mouse over the objects, making sure the marquee encloses all of them, and then release the mouse button. You can also combine both methods.

To select all objects in the Frame window, press Ctrl+A or use the method selectContents .

- To search for any object in the Frame window, click Incremental Find Object on the Frame ribbon tab and start typing its name. Plant Simulation then finds and selects the object.
- To connect objects, use the Connector . The Connector displays handles after you select it. Click a handle to change its shape, i.e., to make the Connector longer or shorter or to move the anchor point up or down.
- To show or hide connections between objects which you established with the Connector , click on the View ribbon tab.
- To show objects that are not connected to another object, click on the Frame ribbon tab.
- To zoom the contents of the Frame in, roll the mouse wheel forward.
- To zoom the contents of the Frame out, roll the mouse wheel backward.
- To show or hide the names of the objects you inserted into the Frame , click

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

.

<!-- image -->

- To prevent another user from modifying the structure of the model, click
- To edit the icons of the Frame , and to add animation structures to it, click on the Home ribbon tab.
- To model transitions between Frames use the Interface . When you connect Frames , which have several Interfaces , with objects, Plant Simulation opens the dialog Select Interface . Select the Interface the Connector attaches to and click OK .

**Note**

If a sub-Frame only contains a single object, you can also connect the sub-Frame without having to use Interfaces .

- To change the size of the icon of an object you inserted in a Frame , hold down Ctrl and Shift . Then, click anywhere on the border of the icon and drag the mouse until the size of the icon meets your needs. To return to the original size of the icon, select Icon &gt; Original Size .

**Note**

This does not work for a rotated icon.

- To open the Frame you double-click and to close the Frame it is contained in, press Shift and doubleclick a Frame located within a Frame .
- To move down in the hierarchy of Frames , closing the active Frame , and opening the next Frame one level down in the structure, select Down one Level on the context menu.

.

- To open the window of the Frame from which the current Frame has derived, click Open Origin the Home ribbon tab.
- To close the active Frame and open its location, click Open Location
- To assign the different states a Frame can be in, use the attributes StateBlocked , StateEntryShut , StateResourceMissing , StateSetup , StateWorking , Stopped , and Unplanned . The Frame then shows the state it is in in the LED area along the top of the icon.

<!-- image -->

<!-- image -->

3D shows the state of the object as a colored ring on a pole by default.

- To manipulate any of the vector graphics, click the Vector Graphics ribbon tab, double-click the shape and edit the Graphic Settings .
- To open help for the selected object, press F1 .

**Note**

The menus Objects and Icons are active only after you select an object in the Frame window.

After you start 3D , the 2D Frame window shows the x-axis and the y-axis in red. The point where these two red lines intersect is the point, which will be mapped to scene origin, i.e., the zero point of the grid, in 3D.

You can set the origin of the grid in 2D with the attribute AxesOrigin .

Back to Working with the Frame

<!-- image -->

##### Show Tooltips of Objects in the Frame

To show a tooltip with information about an object, drag the mouse over it and hover.

All objects show the name of the object in bold face and its origin . Depending on the state and the type of the object they show additional information.

**· Tooltip of the EventController**

The EventController shows the current simulation time and the End Time that you entered.

<!-- image -->

**· Tooltip of Point-oriented Objects**

<!-- image -->

<!-- image -->

- Tooltip of Length-oriented Objects
- Tooltip of Interface and Connector

<!-- image -->

<!-- image -->

**· Tooltip of the Transporter**

<!-- image -->

<!-- image -->

- Tooltip Showing the Stacking Order of Mobile Objects

<!-- image -->

- Tooltip of the Fluid Objects
- Tooltip of the Worker and the Worker on Workplace
- Tooltip of a SubFrame

<!-- image -->

<!-- image -->

<!-- image -->

- Tooltip of the object Dialog
- User-defined Tooltip of a Method
- Tooltip of a User-defined Attribute in a Frame
- Tooltip of the TransferStation

<!-- image -->

<!-- image -->

<!-- image -->

##### Connect Objects with the Connector

<!-- image -->

Compare View Information About the Objects

Compare User-defined Attributes [general description]

Compare Create a Tooltip as a User-defined Attribute in 3D

Back to Working with the Frame

Connect Objects with the Connector

The objects you insert into your simulation model represent stations in a production process. Each material flow object in your model has entrance points which receive parts, and exit points from where the parts move on to the succeeding objects in the sequence of stations.

In real installations the relation between the different stations is obvious by the way in which the machines are arranged on the shop floor. Plant Simulation , on the other hand, handles this somewhat differently.

To clarify to which other object parts are to be moved when leaving an object, you have to establish connections between these objects.

- To connect the stations that represent the flow of materials: Click the Connector in the Toolbox to activate connect mode. The mouse pointer turns into crosshairs (+). When you connect objects in the Frame , Plant Simulation attaches the connecting line to the front end of the cursor , allowing you to actually see the connection before setting it. To connect object A and object B , first click object A and then object B .

**Note**

Plant Simulation only shows the connection, when you select Show Connections on the View ribbon tab.

Drag the Connector from the Class Library or the Toolbox onto an object inserted into a Frame that you would like to connect. Plant Simulation the automatically places the starting point of the Connector to this object.

- To connect several objects one after the other without having to return to the Toolbox each time you established a connection, hold down Ctrl , while you establish the connection.
- To automatically connect the objects while you insert them, place the objects right next to each other, when you insert them. You will then have to manually move the objects to their final position.

**Note**

This only works, when File &gt; Preferences/Model Settings &gt; Modeling &gt; Connect automatically is active. In addition the position of the exit of the one and the entrance of the other object are to be no more than 3 pixels apart.

- To tell Plant Simulation where and how to place the Connector in the Frame , hold down Shift , Ctrl , or Alt while you establish the connection:
- Connector , no key: Plant Simulation aligns the connection to the grid, i.e., to the grid points next to the location where you click the mouse button.
- Connector + Ctrl : Plant Simulation stays in connect mode, so you can connect several objects one after the other without having to return to the Toolbox each time you established a connection.
- Connector + Shift : Plant Simulation inserts the connection at a right angle, regardless of where you click.
- Connector + Alt : Plant Simulation sets anchor points of the connection at the location where you click. This is similar to the freehand drawing feature.
- To create a non-straight connection , set one or more anchor points: First, click object A , proceed to point 1 and click once, then proceed to point 2, click once, and finally move to object B and click the mouse button once to establish the connection.
- To create a right-angled connection , hold down Shift and click the left mouse button to set the anchor point.
- To move an anchor point, click it, hold the mouse button down, and drag the handle to the desired location. Plant Simulation also moves the Connector .
- To check if all connections between the objects really have been established, click Unconnected Objects on the View ribbon tab. Plant Simulation selects all objects with unconnected entrance and exit points.
- To make the connecting line thicker, enter a higher number into the text box Weight .

<!-- image -->

To make the connecting line thinner, enter a lower number into the text box Weight .

- To select another color than the default black, in the dialog Colors , click the field next to Color .

You can select one of the predefined colors or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation show this color next to More Colors and uses it as the active color.

- To show the source and the target of the Connector in the Frame is a Tooltip , drag the mouse over the Connector .
- To exchange the successor of a Connector , select the end point of the Connector and drag it to another object.

<!-- image -->

To exchange the predecessor of a Connector , select the starting point of the Connector and drag it to another object

- To place an object , which you insert from the Class Library into a Frame , in between two already connected objects , drag that object onto that spot of the Connector and drop it there. In this process Plant Simulation exchanges the successor of the original Connector .

<!-- image -->

This also works when you drag a Frame , which contains exactly one suitable entrance Interface and exactly one suitable exit Interface , onto the Connector .

- To retain the Connector between objects when you delete an object, hold down Ctrl and then press Del while keeping Ctrl pressed. Click Yes in the dialog that opens.

<!-- image -->

<!-- image -->

<!-- image -->

- To automatically connect predecessor and successor when deleting an object located between other connected objects, hold down Ctrl while you delete the object with the context menu command Delete .

<!-- image -->

When you work with the Delete key, select the object(s) you want to delete, and press Delete . Follow the instructions in the dialog that opens.

<!-- image -->

**Note**

This does not work when an object has more than one predecessor and successor. If the object has a successor, Plant Simulation exchanges the successor of all preceding Connectors . If the object has a predecessor, Plant Simulation exchanges the predecessor of all succeeding Connectors .

- To change the Width and the Color of the Connector , double-click its icon and enter and select the settings you need.
- To reorder the sequence of the succeeding objects , i.e., the sequence of the Connectors , click the object with the right mouse button and select Reorder Successors . Move the selected successor with the Up or Down buttons.

<!-- image -->

<!-- image -->

Compare Connect Objects in the Scene in 3D

Compare Undo [3D] and Redo [3D]

Back to Working with the Frame

Model Transitions Between Frames

One of the main advantages of Plant Simulation is that you can model hierarchically, i.e., you can model components of your overall plant in a Frame , make sure that these components work by themselves and then insert them into your overall simulation model.

<!-- image -->

In this case, you will have to connect the component ( Frame ) to the material flow objects or Frames that precede and succeed it in the sequence of stations with the object Interface . The transitions are the places where MUs move from one Frame to another or from a material flow object to a Frame and vice versa. Plant Simulation shows if the Interface you inserted into a Frame in 2D is connected to another object with a Connector or if it is not connected . Plant Simulation also recognizes if an Interface is an entrance or an exit .

<!-- image -->

If the sub-Frame only contains a single material flow object , you do not have to use Interfaces but can connect the sub-Frame directly with its predecessor and its successor.

The Tooltip shows the externally connected objects. Plant Simulation does not insert a Connector from the predecessor and to the successor of the object in the sub-Frame .

<!-- image -->

Our model looks like this in 3D by default as Graphics &gt; Show Content is activated by default:

<!-- image -->

To only show the sub-Frame , clear Show Content for the Frame in the model NoInterfaces . The model then looks like this:

<!-- image -->

You can insert the Interface into your simulation model from the folder MaterialFlow in the Class Library or from the toolbar Material Flow in the Toolbox .

<!-- image -->

To model transitions, click the folder or the toolbar Material Flow and insert as many objects of type Interface anywhere in the Frame .

- Select the side of the icon of the Frame at which the Interface is to be located: on the Top , on the Right , on the Bottom , or on the Left of the Frame .
- Type in the maximum number of external connections the Interface may have. Depending on the type, any number of Interfaces may have more than one predecessor or successor.

The predecessor is the object that is connected to the selected object with a Connector and that is located in front of it in the sequence of stations in the simulation model.

<!-- image -->

The successor is the object that is connected to the selected object with a Connector and that is located after it in the sequence of stations in the simulation model.

<!-- image -->

- Type the position of the Interface on the side of the Frame it is inserted into in percent into the text box Position in % . You can specify a value between 0 and 100 percent. Plant Simulation uses the value you specify, when you activate File &gt; Preferences &gt; Modeling &gt; Connect Automatically . Connecting objects automatically only works when the exit of FrameA and the entrance of FrameB are not more than three pixels apart.
- An Interface object you insert into a Frame and connect with a Connector show its Type in the dialog: either Entrance or Exit .
- If need be, you can also select an Exit Strategy on the tab Exit Strategy .

Compare Model Hierarchically [general]

Compare Transfer Parts from Station to Station

Back to Working with the Frame

#### Controlling the Simulation with the EventController

Control the Simulation with the EventController

The EventController coordinates and synchronizes the different events taking place during a simulation run. When a part enters a processing station, for example a Station , Plant Simulation computes the time it takes to process it and enters that event and that time into the List of Scheduled Events of the EventController .

You can insert the EventController into your simulation model from the folder MaterialFlow in the Class

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

Library , from the tab Material Flow in the Toolbox . Instead, you can also click on the Home ribbon tab.

<!-- image -->

- Plant Simulation show the current simulation time of the simulation run in the box next to Time . Click Time to change the display of the time between the:
- Relative time : Plant Simulation resets the relative time to zero, when it starts the simulation run. This is the default.
- Current time plus simulation time : Plant Simulation adds the simulation time to the time and date at which it started the simulation run.

Let us assume today is March 13, 12 o'clock noon and the simulation is to run for two days:

- For the setting relative time shows 2:00:00:0000 , i.e., two days.
- For the setting current time plus simulation time Plant Simulation shows We, 2023/03/15 12:00:00.0000 , i.e., March 15, 12 o'clock noon, after the simulation run is finished.
- To initialize your simulation model, click Start/Stop Simulation

<!-- image -->

<!-- image -->

.

Plant Simulation executes all Methods named Init . Methods being executed when you click Start/Stop Simulation will be processed first.

Plant Simulation initializes the simulation model before it executes the next scheduled event.

**Note**

Plant Simulation automatically executes init methods then you start the simulation for the first time or when you stopped the simulation and clicked Reset Simulation and you did not click Start/Stop Simulation before you started the simulation.

- To reset your simulation model, do one of the following:

<!-- image -->

- Click Reset Simulation in the EventController .
- Click on the Home ribbon tab.

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

Plant Simulation calls all methods named Reset in your simulation model. It deletes all unprocessed events, resets the simulation time to 0, resets the statistics, and clears any pause and any failure of paused or failed machines.

When you click Reset Simulation while the simulation is running, Plant Simulation will first finish processing the active event and then reset the simulation model.

- To start the simulation, do one of the following:
- Click Start/Stop Simulation in the EventController .
- Click on the Home ribbon tab.
- Double-click the icon of the EventController while holding down Shift .

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

If this is the first simulation run or you clicked Reset Simulation before, Plant Simulation executes all methods named Init located in your simulation model.

**Note**

To start the simulation without animating objects and MUs , click Start Fast Forward Simulation on the Home ribbon tab.

<!-- image -->

- To stop the simulation after the active simulation event has been processed, do one of the following:
- Click Start/Stop Simulation in the EventController
- again.
- Click on the Home ribbon tab.
- Double-click the icon of the EventController while holding down Shift .
- To start the simulation run with the animation of MUs and States and with full speed, click Start Full Speed Simulation .
- To start the simulation run without the animation of MUs and States and with maximum speed, click Start Fast Forward Simulation . This makes the simulation run as fast as possible.
- To process the next simulation event in line, to stop the simulation afterward, and to thus proceed through your model step-by-step, click Single Step Simulation .
- To open the Dialog Box of the Event Debugger , click List .

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

The List of scheduled events shows all currently scheduled events in ascending order, allowing you to find out, which events are scheduled at which point in time.

##### Select Settings for the Simulation

- The column Breakpoint shows an S , for a breakpoint you inserted, by double-clicking a cell in the row.
- The column Type shows the type of event, for example Out , Pause , PauseEnd , etc.
- The column Time shows the point in time the event is going to be executed.
- The column Receiver shows the receiving object, i.e., the object that receives the breakpoint.
- The column Sender shows the sending object, i.e., the object that sends the breakpoint.
- To increase the speed of the simulation, drag the slider to the left or press the left arrow key. To decrease the speed of the simulation, drag it to the right or press the right arrow key.

Decreasing the speed enables you to better follow the movements of MUs , as Plant Simulation show their icons for a longer time on the same station.

- To pause the simulation until the time span between two events has elapsed in real-time, enter the Scaling Factor for real-time mode.

The scaling factor sets the time that elapses between two events in real-time.

**Note**

Normally Plant Simulation does not take the time span in between events into account, as it is a discrete event simulation system.

The duration of an event in real-time is the simulation time divided by the scaling factor you entered. The resulting duration is an integer.

**You can:**

- Select Settings for the Simulation
- Work with the Event Debugger

Back to Creating a Simulation Model

**Select Settings for the Simulation**

When your modeling needs require it, you can select settings for controlling the simulation run on the tab Settings of the EventController .

- Plant Simulation show the current simulation time of the simulation run in the box next to Time. Click Time to change the display of the time between the:
- Relative time : Plant Simulation resets the relative time to zero, when it starts the simulation run. This is the default.
- Current time plus simulation time : Plant Simulation adds the simulation time to the time and date at which it started the simulation run.

Let us assume today is the second of January, 12 o'clock noon and the simulation is to run for two days:

- For the setting relative time Plant Simulation shows 2:00:00:0000 , i.e., two days.
- For the setting current time plus simulation time Plant Simulation shows Mi, 2023/01/04 12:00:00.00 , i.e., January 04, 12 o'clock noon, after the simulation run is finished.
- Enter the Date and the time on which the absolute time during the simulation is based.
- Enter the Time when the simulation run will be finished. Enter a relative time, i.e., the period of time the simulation runs. Plant Simulation compares this period with the simulation time and stops the simulation run when both are identical. Let us assume it is January 04, 12 o'clock noon and the simulation is to run for two days. Enter 2:00:00:00 into the text box End . If you do not want to write this out in full, you can also just type 2::: and click Apply to have Plant Simulation translate this to the full format 2:00:00:00 .

<!-- image -->

<!-- image -->

- Enter the Time the EventController resets the statistics. Plant Simulation starts collecting statistical data for all material flow objects anew from this time on.

##### Back to Control the Simulation with the EventController

Working with the Event Debugger

Work with the Event Debugger

The EventDebugger is a tool that lets you accurately control the execution of simulation events, when you click Single Step Simulation . This way you can follow how Plant Simulation processes the individual events during the simulation run and detect errors in your simulation model. As opposed to clicking Start/ Stop Simulation on the tab Controls of the EventController you can, for example, enter a condition when the Event Debugger is to Stop the simulation. Then, you can follow the execution of the events in the Event Debugger .

The following examples demonstrate a number of typical usages for the Event Debugger .

To open the Event Debugger , to define breakpoints and to step through the scheduled events:

- Open the EventController .
- Click the List button on the tab Controls . The event list contains the types of scheduled events, which the objects in your simulation model entered and which the EventController has to process. It is sorted ascending by time, tells the type of event, the scheduled processing time, and lists recipient and sender of the event.

<!-- image -->

<!-- image -->

Double-click a cell in the row where you would like to insert a single breakpoint. Then, the Event Debugger stops the simulation run immediately before the EventController processes that event. Double-click the row again to delete the breakpoint.

- Select the check box Breakpoints Active .
- Click Breakpoints to open the list of the breakpoints you defined.
- Click Insert in the dialog Breakpoint to add an additional breakpoint.
- If you would like Plant Simulation to create a trace file that tracks all events , enter a name into the text box Trace File and select the check box Trace File .

<!-- image -->

If you only want to create a trace file for a certain event , enter a file name into the text box Trace File in the dialog Breakpoint .

- You can also use an event from the list in the EventController to define breakpoints. Select the event in the list and click Stop at Selected Event . This adds this event to the list of defined event breakpoints. You can also edit the selected event.
- To process a single event and stop the simulation again, click Single Step Simulation .
- To proceed with the simulation until the EventController reaches the next breakpoint, click Start/Stop Simulation .

**Back to Work with the Event Debugger**

EventDebugger, Example 1

In this example we watch all exit ( Out ) events for the Part with the ID 1, meaning that we track the course the Part takes through the plant.

<!-- image -->

If you would like to create a breakpoint for each Part , delete the ID of the MU .

**Back to Work with the Event Debugger**

EventDebugger, Example 2

In this example all MUs leaving Station1 define a breakpoint.

<!-- image -->

This time we do not enter a Receiver , as we want the EventController to insert a breakpoint for each leaving part . The Sender is Station1 .

**Back to Work with the Event Debugger**

EventDebugger, Example 3

In this example only MUs of a certain class located on Station1 insert a breakpoint during a certain time span.

Plant Simulation inserts a breakpoint when a part of the class .MUs.Part located on Station1 creates an Out event between 1 hour and 3 hours.

<!-- image -->

At times you only want to insert breakpoints when certain conditions are met. Enter these conditions into the text box next to Condition . A condition may be a certain value or certain states of the simulation model or properties, i.e., attributes, of mobile parts. You can also enter methods, returning a boolean value as a result, which will then be evaluated.

**Back to Work with the Event Debugger**

###### EventDebugger Example 4

In this example we use a property of the part as a condition for a breakpoint.

Plant Simulation inserts a breakpoint, when a part of the class .MUs.Part , which is less than 100 meters long, causes an Out event on Station1 . The unit depends on the settings you selected under File &gt; Model Settings/Preferences &gt; Units &gt; Length .

<!-- image -->

**Back to Work with the Event Debugger**

EventDebugger, Example 5

In this example we track the course the Part with the ID 9 takes through a simulation model and write the stations to a trace file.

<!-- image -->

With the settings shown in the dialog above, Plant Simulation inserts a breakpoint for each Out event of the Part with the ID 9 and writes this event to the file c:\Exercises\trace3.txt . This only works if you selected the check box Trace File in the dialog Event Debugger . If you clear the check box Breakpoints Active , Plant Simulation writes the trace file without stopping your simulation using a breakpoint.

In the examples above we only used Out events. You can, of course, also use any of the available types of events, compare the List of Events .

**Back to Work with the Event Debugger**

#### Delete Parts with the Mouse or when Resetting the Model

To delete one, several or all MUs , do one of the following:

- Select a single MU you would like to delete and press Delete .
- To delete all MUs in all objects in the active Frame and its sub-Frames , click Delete MUs on the Home ribbon tab.
- To delete all mobile objects (MUs), when you reset the simulation model by clicking the Reset Simulation button or by calling the method reset , you can enter deleteMovables into a Method , which you name reset and which you insert into your simulation model.

<!-- image -->

<!-- image -->

**Note**

If you simulation model still contains parts, meaning that Plant Simulation does not start counting parts with 1, for example .MUs.Part:1 , for a new simulation run, check if the model contains additional Frames with inserted EventControllers . Reset the EventControllers there as well.

Back to Creating a Simulation Model

#### Working with Drag-and-Drop

Work with Drag-and-Drop

Drag-and-drop has a number of applications in Plant Simulation .

You can:

- Drag an Object Onto Another Object and Drop It There
- Use a Drag-and-Drop Control for Several Objects

Compare

Object Paths in SimTalk

Compare Drag-and-Drop in the Icon Editor

Compare Drag-and-Drop While Modeling

##### Drag an Object Onto Another Object and Drop It There

Compare Drag-and-Drop in the Method Editor

Compare Drag-and-Drop in Lists and Tables

Compare Work with Data in the DataTable

Compare Drag-and-Drop in the Chart

Compare Configuring the TransferStation

Back to Creating a Simulation Model

Drag an Object Onto Another Object and Drop It There

Drag-and-drop has a number of applications in Plant Simulation . You can use it to:

- Insert an object from the Class Library into the Frame that contains your simulation model.
- Insert an object, such as a Broker , a ShiftCalendar , a control method , a table , etc. into the text boxes the dialogs of the objects provide. When you use drag-and-drop, Plant Simulation enters the relative path to the object. It starts in the Frame in which the object using the relative path is located.

<!-- image -->

To insert the absolute path of the object, hold down the Shift and Ctrl keys.

**Note**

To use an object reference instead of the absolute path, type an asterisk in front of the path. For the example above you would type *.Models.FinePositioningAGV.Broker.

**Note**

If you do not want to use the absolute path, but the relative path , click Select Object .

- Duplicate i.e., to copy the selected object or model and create a new class: Hold down the Ctrl key, drag the object to another location in the Class Library , and release Ctrl .

Go to Use a Drag-and-Drop Control for Several Objects

Back to Work with Drag-and-Drop

Use a Drag-and-Drop Control for Several Objects

Plant Simulation supports multiple drag-and-drop , allowing you to select a number of objects, drag them onto the destination object and drop them there. You can do this for:

- Each object which has a Drag-and-drop control which accepts the selected objects as a parameter of data type array .
- The AttributeExplorer
- The Method . Here the selected objects to be passed have to be contained in an array .
- The Chart
- The HtmlReport

<!-- image -->

- The object Cycle . It accepts a maximum of two objects, one for the first station and one for the last station.
- The ShiftCalendar
- The LockoutZone

You can also drag several objects to the structure in the Class Library to create class objects from the copied objects.

Below we demonstrate how to use multiple drag-and-drop with a drag-and-drop control .

We want to execute the drag-and-drop control , which we entered for the Frame named MyFrame , when we drag our production line onto the Frame and drop it there.

Proceed as follows to create a simple simulation model:

- Insert the material flow objects you want to work with and connect them. We inserted a Source , a Station , a Conveyor , and a Drain . We used them with their default settings.
- Insert a Frame for which to define the drag-and-drop control . We renamed our Frame to MyFrame .

The finished simulation model looks like this:

<!-- image -->

- Define the drag-and-drop control for the Frame . Open the Frame and click Edit Controls on the Home ribbon tab.
- Right-click in the text box next to drag-and-drop and select Create Control .

<!-- image -->

- Change the source code of the control so that it matches the instructions below:
- Select the production line, drag it over the Frame , and drop it there.

```simtalk
param draggedObjects: object[] // one-dimensional array with n objects // the size of which can change
var obj: object debug // @,?: drop target
for var i := 1 to draggedObjects.dim
loop
obj := draggedObjects[i] // enter your source code here
print i, ": ", draggedObjects[i] // prints the dragged objects to the Console next
```

<!-- image -->

The Console then shows the dragged objects that were dropped.

<!-- image -->

- To actually see the array containing the dropped objects, we added debug to the source code.

This opens the Method debugger when you drag the objects over the Frame and drop them there. The row with the name draggedObjects on the tab Variables then shows the array containing these objects.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

Go to Use a Drag-and-Drop Control for Several Objects

Back to Work with Drag-and-Drop

**Modeling the Flow of Materials, Basics**

