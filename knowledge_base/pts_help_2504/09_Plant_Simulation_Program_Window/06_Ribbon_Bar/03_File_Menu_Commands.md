### File Menu Commands

#### File Menu [Plant Simulation]

The File Menu provides commands to access its functions.

**Note**

The commands New and Open are only active in the Plant Simulation window, if no simulation model is open at the moment.

<!-- image -->

<!-- image -->

**File Menu [Plant Simulation]**

<!-- image -->

| Command                                                                                                                                                    | Looks like this   | Method                                                |
|------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------|-------------------------------------------------------|
| Save Model File As                                                                                                                                         |                   | selectFileForSave [SimTalk] saveFolderModel [SimTalk] |
| Teamcenter [on File menu] Open from Teamcenter Add to Teamcenter Change Environment or Server Check In [Teamcenter] Check Out [Teamcenter] Cancel Checkout |                   | -                                                     |
| Compare Model Files                                                                                                                                        |                   | -                                                     |
| Share Send Using E-mail Pack and Go                                                                                                                        |                   | -                                                     |
| Options Model File Properties Show Model History Encrypt Model File Encrypt Methods Restrict Permission Random Number Seed Values Borrow Licenses          |                   | -                                                     |

<!-- image -->

#### New Model

Opens the items required for creating a new simulation model.

<!-- image -->

- The Class Library that shows the built-in objects in a hierarchical structure.
- The Toolbox that shows the icons of the built-in objects grouped by function.
- The Console that shows messages, which Plant Simulation issues.
- The Frame in the folder Models in which you create the actual simulation model.
- When you select New for the first time, Plant Simulation opens the dialog Manage Class Library .

<!-- image -->

Select the objects and libraries, which you need for creating the current and future simulation models.

If you want Plant Simulation to always show this dialog, when you open a new model, select the check box. Then you can configure each simulation model to your liking. If you want to use the same settings for all new simulation models, clear the check box.

<!-- image -->

If you want Plant Simulation to apply the settings you selected in the dialog to all new models, which you create hereafter, click .

Instead, you can also click Create New Model on the Start Page .

<!-- image -->

#### Open Model File

Opens the dialog Open . Select drive and folder from the drop-down lists and enter or select the name of the model file you would like to open. Plant Simulation closes the open model file.

<!-- image -->

Instead, you can also click Open Model File on the Start Page .

<!-- image -->

**Note**

In very rare cases your model might crash while opening it. If the model has a 3D part, you can try to open it without the 3D part by holding down the key combination Shift-right+Ctrl-right when you select the object. If the model still crashes, you can hold down Ctrl-right+Alt Gr when you select the model to suppress opening call chains and suspended methods. If your keyboard does not have the Alt Gr key, hold down Ctrl-right+Alt-right instead.

**See also modelFile [SimTalk] selectFileForOpen [SimTalk] Save preview**

#### Close Model

Closes the current model and prompts you to save it. The dialog shows the name of and the path to the model file in the first line.

<!-- image -->

Click Cancel to continue working on your model. Click Yes to save it, click No to close the model without saving it.

**Note**

You can also define a Method with the name onCloseModel in any folder in the Class Library , including the Basis folder. This method is being executed when you close the model or when you exit the application. You can, for example, program clean-up tasks, delete temporary files, etc.

The method onCloseModel has to declare the boolean parameter onExitApplication . Plant Simulation sets this parameter to false when onCloseModel is called when you close the model. Plant Simulation sets this parameter to true when onCloseModel is called when you exit Plant Simulation .

You can also program several onCloseModel methods and place them into different folders. Plant Simulation then calls all existing onCloseModel method classes in the Class Library when you close the model or exit the application.

**SimTalk**

closeModel [SimTalk] - global function

exitApplication [SimTalk]

#### Save Model File

Saves the simulation model to disk. You can save models in any state, i.e., even if methods are suspended or while you are debugging a Method .

<!-- image -->

Remarks

Plant Simulation only supports fi le paths with a length of up to 260 characters when saving the simulation model.

Prevent Opening the Git Commit Dialog

To prevent opening the Git Commit dialog, hold down Shift while clicking the Save Model File button.

<!-- image -->

To never open the Commit dialog when saving the simulation model, create a new String Value in the registry under HKEY\_CURRENT\_USER\Software\Siemens\Tecnomatix Plant Simulation 2504 . Name it FolderModelCommitCommand and enter an empty String "" .

If you are using another source control system than Git , enter the path to that source control system as the Value data .

Prepare to Save a Folder Model with OnSaveFolderModel

If you are working with a folder model and if you click Save Model File to save the loaded folder model , Plant Simulation checks if a method named OnSaveFolderModel exists at the Basis of the Class Library . If this is the case, Plant Simulation calls this method and does not save the folder model automatically. You can save the folder model by calling SaveFolderModel within the method OnSaveFolderModel .

You can, for example, use OnSaveFolderModel to put the folder model into a state in which it is to be saved to a Source Code Control System, where you do not want to store unnecessary data.

A OnSaveFolderModel method, in which we reset all EventControllers in a simulation model, might look like this:

```simtalk
-- Reset all event controllers before saving the model
for var i := 1 to .MaterialFlow.EventController.NumChildren
	var ectl = .MaterialFlow.EventController.childNo(i)
	ectl.reset
	waituntil not ectl.isResetting
next saveModel
```

SimTalk

saveModel [SimTalk]

selectFileForSave [SimTalk]

See also

What is a Folder Model?

Save preview

Save As &gt; Folder Model

#### Save Model File As

Save Model File As

Saves the active simulation model with a new name. It opens the dialog Save As . Select the drive, and the file type, and enter a new name for the model file.

<!-- image -->

Remarks

Note

Plant Simulation only supports fi le paths with a length of up to 260 characters.

You can save the model either as a model file or as a folder model .

If you scroll to the top on the left-hand side in the dialog Save As , Plant Simulation shows the folder in which the model file is saved.

<!-- image -->

Plant Simulation saves the data of the 2D and the 3D part of the model to a file with the extension .spp. Thus, you cannot detect if the model file contains 2D data only or if it also contains 3D data.

If you save a model with a corresponding 3D part, we recommend to save a preview of the active 3D window. This way you can easily detect in the dialog Open , if the model has a 3D part and which model this is, when you open a model.

<!-- image -->

Plant Simulation shows the graphic in the dialog Open , when you select the command Open Model File and click in the dialog that opens to show the preview window.

<!-- image -->

<!-- image -->

Proceed as follows to convert a 2D and 3D model into 3D Only model:

- Save the model with a new name, for example MyModelDKB3D.spp .
- Select Model Settings &gt; General &gt; Visualization [model settings] and select 3D Only .

<!-- image -->

<!-- image -->

- Click OK and save the model. Plant Simulation removes the 2D part from the model and closes the 2D Frame .
- Double-click the Frame named Model to open the respective 3D Frame .

You might then have to adapt the 3D model, compare the topics below Update Arbitrary Old Models .

SimTalk

selectFileForSave [SimTalk]

See also

Save Model File

Save As &gt; Folder Model

Save preview

Visualization [preferences]

Visualization [model settings]

Update Arbitrary Old Models

**Save preview**

##### Save preview

To save a preview picture of you simulation model, select this check box.

<!-- image -->

**Select the check box Save preview :**

- To save a snapshot of the active Plant Simulation window, when you are working with an Plant Simulation model.
- To save a snapshot of the active 3D window, when you are working with a 3D model.

Once you start 3D , saving the 2D model also saves the 3D part of the model to the same *.spp file. As you then cannot tell which 2D model also contains a 3D part, we recommend to select the check box Save Preview in the dialog Save As , to save a snapshot of the active 3D window. Plant Simulation also shows this graphic, when you open the model again, allowing you to see, which model has a corresponding 3D part.

<!-- image -->

Plant Simulation shows the graphic in the dialog Open , when you select the command Open Model File and click in the dialog that opens to show the preview window.

Save Folder Model

What is a Folder Model?

A folder model is a simulation model that Plant Simulation saves in a folder/file structure.

The file format Folder Model (*.psfm) has these advantages:

<!-- image -->

- The model can be placed under version control .
- The model is saved faster to disk or via the network as Plant Simulation only writes the changed files when you select the command Save or click Save Model File . The model retains the file type Folder Model .
- The model is saved faster via the Internet to TcShare , OneDrive , Google Drive , iCloud , etc. as only the changed files are going to be uploaded.

If you use a version control systems such as Git and when you merge changes from other branches into your model, you always must load the model and save the model to bring it into a consistent state. It can, for example, happen that an object was added to a class object where only you have instances in your model. So, the instance of the added object is missing in your model. This will be corrected when you load the model.

For merging and comparing .yaml files we recommend to use BeyondCompare ( https:// scootersoftware.com ). This enables you to define a file type for .yaml where you can set the encoding to UTF-8. This is important if you merge changes into your files.

To uniquely identify an object, each object in Plant Simulation has the SimTalk attribute UUID [SimTalk] . This UUID is a universally unique identifier which Plant Simulation created when it creates the object and which will identify this object during its entire lifetime.

Each folder or each Frame in your simulation model will create a folder in the file system with the name of the simulation object. Each object stores its attributes in a text file with the name of the object and the extension .yaml . YAML is a human-readable data serialization standard ( https://yaml.org ) which enables to store the object attributes in a structured way. If possible, the names of the attributes in the YAML file match the English attribute names in SimTalk . This might, for example, look like this:

<!-- image -->

The content of this YAML file must be saved with UTF-8 encoding. To edit YAML files we recommend the free text editor Notepad++ ( https://notepad-plus-plus.org ) because it recognizes YAML format. Plant Simulation assigns the top level folder the extension .psfm to indicate that it is a folder model.

Plant Simulation does not save Connectors in their own .yaml file. Instead, the predecessor stores the Connectors to its successors. This reduces the number of files and thus increases performance.

If you are working with a 3D model, an additional file will be created for each object which does not inherit its graphics. The file name is the name of the object, and the extension is .jt . The file contains binary data.

<!-- image -->

The top-level directory of your model contains these files in addition:

**· $.spp :**

This file enables you to open the model by double-clicking it. The file is empty and has no other purpose than to open the model file. At the beginning of a save operation it is deleted and once the model is completely saved it is recreated. If this file is missing saving the model failed.

**· .UserSettings.yaml :**

This file contains settings which are related to the current user, like window positions, opened folders in the class library, etc. This file is usually not placed under version control.

<!-- image -->

**· $ModelInfo.yaml :**

This file contains the model settings and other information about your model.

Each folder or Frame will store its attributes in the file $.yaml located inside the folder which is created for the object.

<!-- image -->

**Note**

Since the folder model is designed for managing models with a version control system, Plant Simulation does not write the current simulation state to the folder model. This means that all attributes, which usually change during a simulation run, like statistic values are not written. MUs instances are not written to the model either.

**SimTalk**

saveFolderModel [SimTalk]

loadModel [SimTalk] - function

See also

Save Model File &gt; OnSaveFolderModel

###### Save As &gt; Folder Model

Saves the model in a folder/file structure which facilitates storing your model in a version control system such as Git .

**Remarks**

**Note**

Plant Simulation only supports fi le paths with a length of up to 260 characters.

<!-- image -->

- Select the folder into which you would like to save the model.
- Plant Simulation enters the name of the model into the text box File name and appends .psfm.
- Plant Simulation selects the file type Folder Model (*.psfm) .
- Select Compact format to not save the objects inside of Frames , which have an origin, to individual .yaml files.
- Select Git support to create a Git repository when the folder model is saved for the first time.
- Click Save to save the file.

Plant Simulation designates the folder model in the Explorer with a red folder on the icon of the folder.

<!-- image -->

**Note**

We recommend saving the folder model onto an SSD drive. This will significantly reduce the time to save the model compared to a conventional hard disk drive.

**Note**

Since the folder model is designed for managing models with a version control system, Plant Simulation does not write the current simulation state to the folder model. This means that all attributes, which usually change during a simulation run, like statistic values are not written. MU instances are not written to the model either.

**Git Commit Support**

When you save a model as a folder model, you can set with the registry key

FolderModelCommitCommand of type String Value which command will be called when saving the model.

Create the registry key either under HKEY\_CURRENT\_USER\Software\Siemens\Tecnomatix Plant Simulation 2504 or under HKEY\_LOCAL\_MACHINE\Software\Siemens\Tecnomatix Plant Simulation 2504 .

If the registry key exists, TortoiseGit will be started. If the registry key does not exist, TortoiseGit will not be started.

To never open the Commit dialog when saving the simulation model, enter an empty String "" .

If you are using another source control system than Git , enter the path to that source control system as the Value data .

**Restrictions**

You cannot save a model as a folder model:

- If it is a 2D/3D model
- If it contains encrypted Open Controls

- If it contains encrypted autoexec methods
- If the model contains an outdated object ( HTML , Checkbox , or Button ) from a previous version of Plant Simulation

SimTalk

saveFolderModel [SimTalk]

loadModel [SimTalk] - function

See also

Save Model File &gt; Prevent Opening the Git Commit Dialog

Save Model File &gt; OnSaveFolderModel

What is a Folder Model?

Compact format

Git support

###### Compact format

To not save the objects inside of Frames , which have an origin, to an individual .yaml file, select this check box. Instead, all the objects are saved into the $.yaml file of the Frame .

<!-- image -->

The compact format reduces the number of files stored in the file system. This can be important for very large models to get a reasonable performance.

SimTalk

saveFolderModel [SimTalk]

loadModel [SimTalk] - function

Back to

Save As &gt; Folder Model

###### Git support

To create a Git repository when the folder model is saved for the first time, select this check box. The initial version will be committed automatically. This option is only available if Git is installed on your computer. In addition, a .gitignore file is created in the top level folder. The content of this file ignores the .UserSettings.yaml so that it is not put under version control.

<!-- image -->

**Note**

Git support is only available after you have downloaded Git ( https://git-scm.com ) and installed it.

**Note**

If you use Git as your version control system, we recommend to install TortoiseGit ( https:// tortoisegit.org ) which provides an easy to use graphical user interface.

**Git Commit Support**

When you save a model as a folder model, you can set with the registry key FolderModelCommitCommand of type String Value which command will be called when saving the model.

Create the registry key either under HKEY\_CURRENT\_USER\Software\Siemens\Tecnomatix Plant Simulation 2504 or under HKEY\_LOCAL\_MACHINE\Software\Siemens\Tecnomatix Plant Simulation 2504 .

If the registry key exists, TortoiseGit will be started. If the registry key does not exist, TortoiseGit will not be started.

To never open the Commit dialog when saving the simulation model, enter an empty String "" .

If you are using another source control system than Git , enter the path to that source control system as the Value data .

SimTalk

saveFolderModel [SimTalk]

loadModel [SimTalk] - function

Back to

Save As &gt; Folder Model

#### Teamcenter [File Menu]

Teamcenter [on File menu]

Provides a number of subcommands to access features in Teamcenter via the Teamcenter Interface .

<!-- image -->

<!-- image -->

- Open from Teamcenter
- Add to Teamcenter
- Change Environment or Server
- Check In [Teamcenter]
- Check Out [Teamcenter]
- Cancel Checkout
- Revise

**Note**

The Teamcenter Interface supports all minor versions of Teamcenter 13 to 2312 as well as Active Workspace version 5.0 and higher.

**Note**

To use the Plant Simulation Teamcenter-Interface the .NET Framework 4.0 needs to be installed on your computer. In addition, the matching Teamcenter client or the Teamcenter Client Communication System (TCCS) needs to be installed on your computer.

See also

Teamcenter [object]

##### Use Active Workspace

To use the Active Workspace-Browser to search the Teamcenter database, activate this check box. To not use Active Workspace , clear the check box.

<!-- image -->

**Note**

This only works if the Active Workspace URL is set correctly under Preference &gt; ActiveWorkspaceHosting.URL in the Teamcenter database.

**Note**

From Plant Simulation 2201.0003 on the Teamcenter Interface does not support Active Workspace versions older than version 5.0 anymore.

This does not affect the Teamcenter Interface itself as long as you do not use Active Workspace !

**See also**

Browse the Teamcenter Database with Active Workspace

##### Open from Teamcenter

Opens a model from Teamcenter , which you saved to the Teamcenter database .

<!-- image -->

**Note**

We only support .spp model files managed in the Teamcenter database . We do not support folder models.

Enter your User Name , your Password , and the Server for logging on to Teamcenter .

**Note**

The connection string that you type in depends on your Teamcenter provider, for example the IT department of the customer. Consult your Teamcenter provider for more information.

Activate Use Active Workspace if you want to use the Active Workspace-Browser to search the Teamcenter database.

<!-- image -->

<!-- image -->

Plant Simulation saves the model to the folder C:\Users\YourLogin\Documents\Plant Simulation Models .

**See also**

Teamcenter [object]

##### Add to Teamcenter

Adds the current simulation model to the Teamcenter database .

<!-- image -->

**Note**

We only support .spp model files managed in the Teamcenter database . We do not support folder models.

Type in your User Name , your Password , and the Server for logging on to Teamcenter

Activate Use Active Workspace if you want to use the Active Workspace-Browser to search the Teamcenter database.

**Note**

This only works if the Active Workspace URL is set correctly under Preference &gt; ActiveWorkspaceHosting.URL in the Teamcenter database.

<!-- image -->

<!-- image -->

**See also**

**Teamcenter [object]**

##### Change Environment or Server

Enables you to change your login data at a later point in time. The login data encompass the User Name , the Password , the Group , the Role , the TCCS Environment , or the Teamcenter Server .

<!-- image -->

Activate Use Active Workspace if you want to use the Active Workspace-Browser to search the Teamcenter database.

**Note**

This only works if the Active Workspace URL is set correctly under Preference &gt; ActiveWorkspaceHosting.URL in the Teamcenter database.

<!-- image -->

The command is only active when no model is open.

**Check In [Teamcenter]**

##### Check In [Teamcenter]

Saves the checked-out simulation model to the Teamcenter database and checks it in.

<!-- image -->

<!-- image -->

To create a new revision of the model, select the check box.

Type in your User Name , your Password , and the Server for logging on to Teamcenter .

Activate Use Active Workspace if you want to use the Active Workspace-Browser to search the Teamcenter database .

**Note**

This only works if the Active Workspace URL is set correctly under Preference &gt; ActiveWorkspaceHosting.URL in the Teamcenter database.

**Note**

If you selected to create a new revision and if the preference

PSI2PlantSimulation\_ReleaseWorkflowProcess is set in Teamcenter , the model will first be released and then be revised. The value of the preference should be of type string , and it should point to the release workflow template that is to be used when releasing the model.

**See also**

**Teamcenter [object]**

**Revise**

##### Check Out [Teamcenter]

Checks the model out of the Teamcenter database .

<!-- image -->

Type in your User Name , your Password , and the Server for logging on to Teamcenter .

Activate Use Active Workspace if you want to use the Active Workspace-Browser to search the Teamcenter database.

**Note**

This only works if the Active Workspace URL is set correctly under Preference &gt; ActiveWorkspaceHosting.URL in the Teamcenter database.

<!-- image -->

**See also**

Teamcenter [object]

##### Cancel Checkout

Undoes checking out the model from the Teamcenter database . Your changes to the model will be discarded and not be saved.

<!-- image -->

Type in your User Name , your Password , and the Server for logging on to Teamcenter .

Activate Use Active Workspace if you want to use the Active Workspace-Browser to search the Teamcenter database .

**Note**

This only works if the Active Workspace URL is set correctly under Preference &gt; ActiveWorkspaceHosting.URL in the Teamcenter database .

<!-- image -->

**See also**

**Teamcenter [object]**

##### Revise

Creates a new revision of the model. You can only revise a model that is checked in to the Teamcenter database .

<!-- image -->

**Note**

If the preference PSI2PlantSimulation\_ReleaseWorkflowProcess is set in Teamcenter , the model will first be released and then be revised. The value of the preference should be of type string , and it should point to the release workflow template that is to be used when releasing the model.

<!-- image -->

#### Compare Model Files

Compares the currently loaded simulation model with another simulation model on your computer's hard drive and shows the differences between the two models.

<!-- image -->

- To compare the current model with another model, select Compare with .
- Then, select the model to be compared in the dialog Open .
- After comparing the models Plant Simulation shows the paths and the file names, and the version of the compared model files in the window Model Comparison Results .

<!-- image -->

It also shows the folders , the Frames , and the objects which exist in both models in a structured view just like the Class Library does.

<!-- image -->

| To do this                                                                                               | Click   | Color   | Looks like this   |
|----------------------------------------------------------------------------------------------------------|---------|---------|-------------------|
| Show objects which are only present in the current model                                                 |         | green   |                   |
| Show objects which are only present in the compared model, i.e., which do not exist in the current model |         | red     |                   |

| To do this                                                                                | Click   | Color         | Looks like this   |
|-------------------------------------------------------------------------------------------|---------|---------------|-------------------|
| Show objects, which are present in both models, but have attributes with differing values |         | blue          |                   |
| Show objects which are identical in both models                                           |         | black         |                   |
| Show objects which have a mix of the above criteria                                       | -       | multicol ored |                   |

With the commands on the context menu of the structure you can navigate and work with the objects.

<!-- image -->

| To do this                                                                         | Select   | Note                                                     |
|------------------------------------------------------------------------------------|----------|----------------------------------------------------------|
| Open the dialog of the selected object                                             | Open     | is only active if the object exists in the current model |
| Open the folder or the Frame in which the selected object is located and select it | Show     | is only active if the object exists in the current model |
| Open all branches of the selected structure ( Basis , folder , or Frame )          | Expand   | -                                                        |
| Close all branches of the selected structure ( Basis , folder , or Frame )         | Collapse | -                                                        |

To show differing attributes of an object in the current model and in the compared model in the list pane to the right, select that object.

<!-- image -->

**Plant Simulation compares:**

- All attributes of all objects.

**Note**

Plant Simulation does not consider attributes which inherit their value. If the attribute value of a class changes, only the class is shown as changed, but not all instances of this class .

- The worker creation table of the WorkerPool .
- The failure profiles of the material flow objects .
- The sensors of the material flow objects and of the Transporter .
- The sub-attributes and sub-methods of the Importer .
- Files of type .psobj.
- Files of type .pslib.

To compare differing source code of methods with the same name in the current model with the source code in the compared model, click the name of the method in the structure. Then, double-click the attribute Program . The compare tool then creates two temporary files and compares the source code.

<!-- image -->

If you installed one of the compare tools Beyond Compare or WinMerge on your computer, Plant Simulation uses the installed program. If you use another compare tool, you have to set this by creating a String Value (REG\_SZ) with the name CompareToolPath within the registry key HKEY\_CURRENT\_USER\SOFTWARE\Siemens\Tecnomatix Plant Simulation and enter the file path to the compare tool into this string value.

If need be, you can merge the source code of the compared method into the current method in the compare application and apply and save it to the source code of your method .

#### Share [Menu Item]

To compare differing comment text, which you typed into objects of type Comment , double-click the attribute Cont . You cannot merge changes though!

You can also start Plant Simulation , load the model designated by file 1 and compare it with the model designated by file 2 with the start option -compare file 2 file 1 . As a rule this only makes sense for automated use in source code version control tools.

**Share [Menu Item]**

##### Share

Provides the submenu commands Send Using E-Mail and Pack and Go .

<!-- image -->

- Send Using E-mail
- Pack and Go

##### Send Using E-mail

Sends the current simulation model to the receiver as an e-mail attachment.

<!-- image -->

The command opens an e-mail in the default mail application on your computer and attaches the current model to it. Plant Simulation always attaches the saved model file. For this reason it first asks if you want to save the current modeling state.

**Pack and Go**

##### Pack and Go

Packages the Plant Simulation model into a stand alone executable file which you can send to other people, who do not have Plant Simulation installed on their computer. They can then run the simulation model.

<!-- image -->

When you create a Pack and Go model , you can select if you want to restrict the permissions to a Plant Simulation Viewer License . If you do not select the check box, you can pass the license to be used with the start parameter /L to the Pack&amp;Go application . This enables to use features of the superior license, provided this license is available. If you do not type in the start parameter, the freely available Viewer license will be used.

<!-- image -->

**Note**

The Pack and Go executable does not include all Plant Simulation features, even if you do not restrict the license. As we want the executable to be as small as possible, we do not include the entire Plant Simulation installation. This prevents you from using the OPCUA Interface or the Teamcenter Interface in Plant Simulation for example.

Pack and Go takes all files needed for starting the selected simulation model with a Plant Simulation Viewer license , packs the files, and saves them as a self-extracting executable. You can then send this packed model to somebody else, who can open the model by double-clicking it, compare Pack a Model and Send It to Another User .

**See also**

Specifying Start Options

#### Options [Menu Item]

##### Options

Provides options for your simulation model file.

<!-- image -->

The command Options provides these submenu commands:

- Model File Properties
- Show Model History
- Encrypt Model File
- Encrypt Methods
- Decrypt Methods
- Restrict Permission
- Random Number Seed Values
- Borrow Licenses

**Model File Properties**

##### Model File Properties

Opens the dialog Properties . Type text into the text boxes, which MS Windows shows, when you rightclick the file in the Windows Explorer and select Properties &gt; Custom on the context menu that opens.

<!-- image -->

You can use the expressions you type in when searching for the file using Start &gt; Search programs and files .

Title

Type in a title for your simulation model file. The title does not have to be the same as the file name.

Subject

Type in the subject of the simulation model. Use the subject to group files that belong together. This enables you to search for all files covering a certain subject.

Author

Type in the name of the person who created the simulation model.

Keywords

Type in a keyword or keywords describing the simulation model. You can use the keyword when searching for the file.

Comments

Type in any kind of comment you deem helpful for yourself or any other user of the simulation model. You can use the comment when searching for the file.

##### Show Model History

Shows the comment which Plant Simulation adds to the model file each time when you save your simulation model.

<!-- image -->

<!-- image -->

Select settings under File &gt; Model Settings/Preferences &gt; General &gt; Model Saving History [preferences] .

<!-- image -->

##### Encrypt Model File

Encrypts the simulation model so that it can only be opened when you type in the correct password .

<!-- image -->

It opens the dialog Encrypt Model File . Type a password into the text boxes next to Password and Confirm password . The password enables you to decrypt the model file later on. After clicking OK , Plant Simulation encrypts the model file the next time you save your model. You, or a colleague, can only open the model file again if you type in the correct password.

**Note**

The password for encrypting and for decrypting the model is valid and active during the entire Plant Simulation session. Thus, you do not have to reenter the password after you close a password-protected model and then open another model that is encrypted with the same password. If you exit Plant Simulation though and restart it, you have to type in the password again.

**Note**

If you forget the password, you will lose your simulation model for good because there is no way to restore a forgotten password.

Keep in mind that passwords are case-sensitive.

<!-- image -->

##### Encrypt Methods

Encrypts the source code of all unencrypted Methods and of all user-defined attributes of data type method of the built-in object classes.

<!-- image -->

The command opens the dialog Encrypt Methods . Enter a password into the text boxes next to Password and Confirm password . The password enables you to decrypt the contents of methods later on. After clicking OK , you cannot access the source code of any methods that are not located in the Class Library anymore.

<!-- image -->

**Note**

To encrypt the source code of a single method, click the Tools ribbon tab and select Encrypt Method in the Method Editor of that method.

**See also**

**Decrypt Methods**

##### Decrypt Methods

Decrypts the encrypted source code of the Methods in your simulation model. Enter the password, which you used to encrypt the Methods , into the dialog Decrypt Methods .

<!-- image -->

**Note**

To decrypt the source code of a method which you encrypted by clicking Encrypt Method on the Tools ribbon tab, click Decrypt Method in the Method Editor of that method.

See also

Encrypt Methods

##### Restrict Permission

Restricts the license type with which another user can open the simulation model. This way you can restrict or prevent the other person from changing the simulation model.

<!-- image -->

- Select the license type with which the model can be opened by another user. The default setting is unrestricted .
- Type in the password to restrict access to the model into the text box Password . The other user has to type in this password when opening the model.
- Type in the password again into the text box Confirm password .

<!-- image -->

<!-- image -->

If you want to undo the permission restriction at a later point in time, open the model with a Professional License . This opens a message box telling you that the license will be restricted.

Hold down Shift and close the message box by clicking OK . This opens a dialog into which you can type in the password for removing the restriction.

**Note**

You can only set a restriction in a Professional License .

##### Random Number Seed Values

Opens the seed values table. It contains the seed values of the random number streams, which only apply to the distribution functions, such as z\_uniform , z\_normal , etc.

<!-- image -->

The call z\_uniform(3,1,10) , for example, generates uniformly distributed numbers between 1 and 10, using the random number stream 3. You can add more random number streams, or you can edit the streams on the table.

<!-- image -->

The table lists the random number streams in consecutive order. If you do not type in different numbers, each random number stream uses its number as the seed value.

Example : You already used five random number streams, and then decide to use stream 1000. Then, Plant Simulation creates the missing 995 random number streams.

**Note**

Each of the material flow objects automatically uses a random number stream of its own. You can set that random number stream with the attribute RandomSeed .

Plant Simulation ensures that the random number streams of objects are initialized differently than random number streams for distribution functions. Even if you use the same number for the attribute RandomSeed and in the random number seed values table, Plant Simulation creates other random numbers for this object.

**Note**

To execute your simulation model several times and to use different random numbers, you only have to change the Random Numbers Variant of the EventController .

SimTalk getSeedTable [SimTalk] setSeedTable [SimTalk] RandomSeed [SimTalk] - material flow objects RandomSeed [SimTalk] - fluid objects RandomSeed [SimTalk] - Method/User-defined Attribute resetRandomNumberStream [SimTalk] Type [SimTalk] - distribution parameter See also Random Numbers Variant Simulating Random Processes Times and Distributions Distribution Functions, z\_ functions

##### Borrow Licenses

Borrows licenses which are available from a license server. It opens the dialog Borrow Licenses .

<!-- image -->

<!-- image -->

**Note**

Borrow Licenses is not available for Plant Simulation X as Siemens manages the licenses.

Borrowing a license means that you can check out fl oating or named-user licenses from a license server to a local computer, for example a notebook, for a certain period of time. The checked-out licenses will then still be available on the local computer after disconnecting it from your computer network.

A borrowed license is borrowed from a license server computer via a special checkout process and is later used to run Plant Simulation on a client computer that is no longer connected to the license server.

- Select the Expiration Date at which the borrowed license will automatically be returned to the license server. Then this license will be available for all users again and will no longer be available on the local computer.

**Borrow Licenses**

- Select the Base License you would like to borrow. You can only borrow one license at a time.
- Select one or more of the listed other licenses you would like to borrow. The expression in parentheses starting with TN designates the product number of the respective feature.

After you activated license borrowing, all licenses are borrowed, which will be used in your further work with Plant Simulation . Then these licenses are available on the local computer without requiring a connection with the license server.

When you select the menu command Borrow Licenses while licenses are borrowed, Plant Simulation asks if you would like to return the borrowed licenses to the license server early, that is, before the borrowing period expires.

**Note**

This command is only active if you did not obtain a license yet, i.e., before opening the first model. If you opened a model, you have to exit Plant Simulation and restart it before you can borrow licenses. It does not suffice to just close the model.

Plant Simulation Does Not Start with a Borrowed License

In very rare cases Plant Simulation might show the message Professional License is not available and might not start with a borrowed license.

To fix this:

- Return your currently borrowed license
- Check the Registry Editor if it erroneously contains more than one license, for example borrowd99f1898-emplant\_pro-2023.02 and borrow-d99f1898-emplant\_pro-2024.04 .
- Delete the entry of the license you do not need, for example borrow-d99f1898-emplant\_pro-2023.02 .
- Borrow the license which you do need again.

See also

###### License

Licensing Plant Simulation

#### Model Settings [Menu Item]

##### Model Settings

Opens the dialog Model Settings in which you can select the settings for the currently open simulation model . Plant Simulation saves these settings in the mode file. Click the tabs to access the respective set of features.

<!-- image -->

<!-- image -->

Click the tabs to access the respective set of features. Then

- Click OK to apply your settings.
- Click Cancel to close the window without saving any changes.

<!-- image -->

##### General Tab

General Tab

General [model settings]

Select settings pertaining to the currently open model on the tab General .

Model Language [model settings]

Date and Time Format [model settings]

Model Saving History [model settings]

Visualization [model settings]

Connect Objects Automatically [model settings]

Connector Positioning [model settings]

Prohibit Access to the Computer [model settings]

###### Model Language [model settings]

Select the language of the currently open simulation model . Plant Simulation saves this setting to the model file.

<!-- image -->

When you create a new simulation model, the Model Language determines:

- The names of folders and objects, such as MaterialFlow and Station for English or Materialfluss and Einzelstation for German.
- The return value of the attributes that correspond to the entries of the drop-down lists, for example Station.RecoveryTimeMode . When you query such an attribute in SimTalk , Plant Simulation returns the value in English , except when the model language is German ; in the latter case Plant Simulation returns the value in German . For the example print Station.RecoveryTimeMode Plant Simulation returns Wenn Teil eintritt when the model language is German , When part enters for all other model languages.
- The contents of the window Show Attributes and Methods . When the model language is German , the window lists the German names of the attributes and methods. For all other model languages the window lists the names in English.
- The names, which the feature Auto Complete in the Method Editor suggests. When the model language is German , the Method Editor suggests the German names of attributes and methods. For all other model languages it suggests the English names.

**Note**

When you change the Model Language , the user interface language of Plant Simulation will not be changed. The user interface language of Plant Simulation is determined by the operating system of your computer. You can change the user interface language of Plant Simulation with the command line argument /L UILanguage , compare Specifying Start Options .

SimTalk

language [SimTalk]

userInterfaceLanguage [SimTalk]

See also

Model Language [preferences]

###### Date and Time Format [model settings]

Select the Date and Time Format for the currently open simulation model . You can choose the 12 hour (AM/PM) or 24 hour YMD (year-month-day) format or the DMY (day-month-year) notation for the date and time format.

<!-- image -->

| Date and time format   | Looks like this   |
|------------------------|-------------------|
| yyyy/mm/dd 12 hour     |                   |
| yyyy-mm-dd 24 hour     |                   |
| dd.mm.yyyy 24 hour     |                   |

**See also**

Date and Time Format [preferences]

###### Model Saving History [model settings]

Select which kind of comment Plant Simulation adds to your currently open simulation model each time you save it.

<!-- image -->

- None does not save the history of how you saved your model.
- Without Comment adds no comment to the model (.spp) file.
- With Comment opens a comment window, each time when you save the model. Enter your comment here.

When you select Without Comment or With Comment Plant Simulation adds a row to the dialog Model Saving History each time you save the model.

When the model crashes, Plant Simulation adds a description of the problem to the dialog instead of a comment. This helps our software engineers detect what caused the crash.

To view the comment you entered, select File &gt; Options &gt; Show Model History .

See also

Model Saving History [preferences]

###### Visualization [model settings]

Select the Visualization for your currently open simulation model , 3D Only or 2D Only .

<!-- image -->

**Note**

We strongly recommend to create your models either in 3D Only or in 2D Only mode.

We strongly advise against creating you models in 2D and 3D mode. The setting 2D and 3D is intended to convert a 2D model to a 3D model.

- Only in 2D shows the model in 2D Only.
- Only in 3D shows the model in 3D Only.

**Note**

We recommend to always create your models in 3D Only mode . This also applies if you are only interested in the 2D view.

<!-- image -->

You can model in Planning View in 3D, which corresponds to the top view in 2D. In addition, you can continuously zoom in the 3D window and 3D has better performance than 2D.

- In 2D and in 3D . This creates the model consisting of a 2D part and a 3D part.

**Note**

The setting 2D and 3D is intended to convert a 2D model into a 3D model. We strongly advise against modeling in 2D and 3D mode.

<!-- image -->

Check if the 3D model behaves according to your expectations and then save the model as a 3D Only model.

**Note**

We strongly advise you to not modify object positions/rotations/polycurves in a 2D and 3D model or create/delete objects in 2D while you also work in 3D at the same time. Otherwise undoing changes in 3D might have unexpected side effects.

If you created the model in 2D Only and need to create its 3D part at a later point in time, you can also

<!-- image -->

If you created the model in 2D and in 3D and then would like to convert it to a 3D Only model, i.e., discard the 2D part, select 3D Only and save the model.

Depending on the setting you selected, the simulation model looks slightly different and provides different tabs on the ribbon bar. Likewise, SimTalk provides different attributes and methods.

See also

Visualization [preferences]

Select the Visualization

Save Model File As

###### Connect Objects Automatically [model settings]

To automatically connect adjacent objects and Frames with Connectors in your currently open simulation model , when you insert them, select this check box.

<!-- image -->

- When you connect Frames , the positions of exit and entrance Interface objects have to be close to each other.
- When you connect objects , the positions of the exits and the entrances of the objects have to be located close to each other.

Plant Simulation proceeds as follows when automatically connecting objects as described below.

- It always uses the first connection possible.
- If a connection exists between the respective object and any other object at a particular side ( Entrance or Exit ), Plant Simulation does not add a new connection at the same side.
- If two objects are located close to each other, the automatic connection will be created between the respective object and the object with which the connections was established first .
- Plant Simulation only establishes an automatic connection in 3D, if the bounding boxes overlap in the Z -direction.

**Note**

When automatically connecting objects, Plant Simulation uses the first Connector class in the Class Library , starting at the top.

To change that order, compare Work with Folders, Frames, Objects in the Class Library .

**Note**

The following applies for automatically connecting the length-oriented objects Turnplate , Turntable , AngularConverter , Conveyor , Converter , Track , and TwoLaneTrack in 3D:

If TransferLengthToObject is off for one of these objects in 3D, but if a suitable MU animation path exists, then Plant Simulation uses the start point and the end point of these animation paths for automatically connecting the objects and for displaying Connectors . Suitable MU animation paths are Default or Cross for the Converter , Lane A or Lane B for the TwoLaneTrack and Default for the remaining objects. This applies for Connect Objects Automatically and for the method connectAutomatically .

SimTalk

connectAutomatically [SimTalk]

See also

Connect Objects Automatically [preferences]

###### Connector Positioning [model settings]

Select on which side of the object Plant Simulation places the starting point or the end point of Connectors in your currently open simulation model .

<!-- image -->

- Fixed Side places the starting point of the Connector at the exit of the object and the end point at its entrance.

For the length-oriented objects Plant Simulation always places the Connectors at a fi xed side .

- Angle-dependent takes into account the angle between the objects when determining the starting point or the end point of the Connector .

For WorkerPool , Workplace , and Pick-and-Place-Robot Plant Simulation always places the Connectors Angle-dependent .

<!-- image -->

**See also**

**Connector Positioning [preferences]**

###### Prohibit Access to the Computer [model settings]

To deny the currently open simulation model to access your computer, select this check box. This is the standard setting. Clear the check box to allow the model access to your computer.

<!-- image -->

**Note**

For models, which you created in previous versions of Plant Simulation , access to the computer is prohibited. If these models need access to the computer, and you trust them, you then have to allow these models access to your computer in the model settings.

Plant Simulation generates a unique trust ID , see below, for each and every user. Models, which you save, are signed with this ID. If you now load a model, which enables access to the computer and when this model is not signed with your ID, Plant Simulation shows a warning message which enables you to trust this model and allow it to access your computer.

If you do not activate the check box Prohibit Access To The Computer in the message dialog above, the model is denied access to the computer. You can allow access to the computer anytime under File &gt; Model Settings &gt; General &gt; Security .

Reading files in principle is not dangerous, for as long as a model cannot transmit data, it cannot be abused for spying on your computer. In addition, it is always permitted that a model creates a new file in the model folder and stores it there. Overwriting or deleting existing files is only permitted when Prohibit Access To The Computer is deactivated.

What you need to know about prohibiting access to the computer

Note the following when permitting or prohibiting a model or a library to access your computer:

- When you open a model, which was saved by another user or which was saved in a previous version of Plant Simulation , this model is not considered to be trustworthy and is only permitted access to the computer when you explicitly allow it.
- When you save a model, the resulting model is considered trustworthy when you open it again without having changed it.
- When Plant Simulation loads a library, which requires access to the computer, into a model without permitted access, it shows a message allowing you to allow access.
- When the model, into which the library is loaded, has access to the computer, the permission will be revoked when interactively confirming loading of the model and each and every access to the computer will from then on prohibited.

- When you load a non-trustworthy object, which you yourself did not save, in a model, Plant Simulation shows a message warning you that this object might be a safety risk, and you can refuse to add it to the Class Library .
- If you typed in the command line argument -TrustModels or the COM method SetTrustModels , Plant Simulation does not show any messages when you load a non-trustworthy model or object.

Effects when not prohibiting access to the computer

If you deactivate this safety setting, it has the following effects:

<!-- image -->

- The functions copyFile , createLicenseFile , F3DRecordVideo , saveModel , saveProfile , and setCurrentDirectory can copy data from another folder and write them to the model folder or its sub-folders. They cannot copy files from the model folder or its sub-folders.
- Formulas are always prohibited access to the computer, independent of the model setting.
- The functions loadLibrary , sendSMTPMail , setEnv , startExtProc , and system are not executed and Plant Simulation shows an error message.
- All objects which allow to save files to the computer via SimTalk can only save files to the model folder or its sub-folders.
- All objects which can access external systems, databases or the ODBC interface via a login cannot do this via SimTalk .
- The PythonModule cannot execute Python code.
- The SQLite interface can still work with the database in memory. It cannot save the database or create it in the file system. You can use the instruction open(false) to allow Plant Simulation to read the database even if Prohibit Access to the Computer is active.
- The FileInterface can only change files in the model folder as these are automatically opened for reading. Write functions of the FileInterface always return false. In addition, the FileInterface can only delete files in the model folder and its sub-folders.
- The FileLink cannot open the embedded files in the associated application with a double-click. The same applies for the method openFile .
- The ActiveX interface and die Socket interface prevent access via SimTalk .

Trust ID

Plant Simulation saves the trust ID in a text file named TrustID.txt in the directory C:\Users\&lt;username&gt;\AppData\Roaming\Siemens\Tecnomatix Plant Simulation .

All versions of Plant Simulation installed on your computer share this trust ID .

When you replace your old computer with a new computer, copy the file TrustID.txt to your new computer if you did not install any version of Plant Simulation on your new computer yet. Otherwise, Plant Simulation would generate a new trust ID. Then Plant Simulation would consider your existing models not as your own models and would not automatically permit them access to the computer.

SimTalk

isComputerAccessPermitted [SimTalk]

See also

Specifying Start Options , -TrustModel

Trust-ID to Permit Models Access to the Computer

Make Library

Edit Library Information

Prohibit Access to the Computer [Make Library]

getLibraryInfo [SimTalk]

SetTrustModels [SimTalk]

Simulation Tab

Simulation [model settings]

Select settings that determine how Plant Simulation executes the simulation runs in your currently open simulation model on the tab Simulation .

Maximum Depth of Calls [model settings]

Maximum Number of Call Chains [model settings]

Maximum Number of Suspended Methods [model settings]

Maximum Number of Samples [model settings]

Tolerance For About Equal (~=) Comparison [model settings]

Frame Rate [model settings]

Display Panel Frame Rate [model settings]

Complex simulation models will contain numerous Method objects, which themselves may call other Methods . Incorrect modeling may cause a Method to be called repeatedly by itself during the simulation run, either directly or indirectly through other methods. This is called an endless recursion. With each call, Plant Simulation takes up more RAM, until it used up all available memory and terminates the simulation run.

Plant Simulation provides several ways for detecting and preventing this and related problems.

###### Maximum Depth of Calls [model settings]

Type in the number of Methods that may be called by other Methods in your currently open simulation model , to prevent Plant Simulation from running out of memory.

<!-- image -->

When Plant Simulation exceeds the maximum depth of calls, the simulation stops and the Debugger opens. Increase the number of the maximum depth of calls and continue or correct programming errors contained in the code, if any. To do so, hold down Ctrl and double-click the selected line containing the error in the Method Debugger .

SimTalk

setMaxDepthOfCalls [SimTalk]

See also

Maximum Depth of Calls [preferences]

###### Maximum Number of Call Chains [model settings]

Type in the maximum number of call chains for new simulation models . The call chain designates the list of all method calls to be executed. The EventController creates this list during the reset and init phases of your simulation model.

<!-- image -->

With the method callEvery you can create a list of methods yourself. A modeling flaw may cause the same callEvery method to be called repeatedly during the simulation, thus taking up more and more memory and finally terminating the simulation. By limiting the number of call chains, you can detect and correct the modeling error.

When the Maximum Number Of Call Chains reaches the value you typed in, the simulation stops and Plant Simulation shows an error message. Now you can increase the maximum number of call chains and continue, or you can correct the faulty source code. To do so, hold down Ctrl and double-click the selected line containing the error in the Debugger .

SimTalk

setMaxNumberOfCallChains [SimTalk]

executeNewCallChain [SimTalk]

callEvery [SimTalk]

See also

Maximum Number of Call Chains [preferences]

###### Maximum Number of Suspended Methods [model settings]

Type in the maximum number of suspended Methods in your currently open simulation model . The number of Methods suspended by waituntil and stopuntil statements and by wait statements is limited.

<!-- image -->

When Plant Simulation reaches the number you typed in, it will not suspend any additional Methods and displays an error message. You can then either increase the Maximum Number of Suspended Methods by typing a greater number into this text box, and continue your simulation run or stop the simulation and fix the modeling error. To do so, hold down Ctrl and double-click the selected line containing the error in the Method Debugger .

SimTalk

setMaxSuspendedMethods [SimTalk]

See also

Maximum Number of Suspended Methods [preferences]

waituntil [SimTalk] and stopuntil [SimTalk]

Interrupting Method Execution with Wait

###### Maximum Number of Samples [model settings]

Maximum Number of Samples [model settings]

Type in the Maximum Number of Samples . This prevents Plant Simulation from spending an excessive amount of time for rolling the dice in new simulation models , which is caused by an unfortunate selection of the interval bounds.

<!-- image -->

You can type in a number between 1 and 32000 . Plant Simulation ignores values outside of this range without showing a warning message and keeps the previous value. The greater the value you type in, the later you recognize if the bounds are too close together.

For a normal distribution it may, for instance, happen that Plant Simulation draws extremely large values. When the bounds are too close together, this may result almost exclusively in outliers. Then Plant Simulation has to create numerous random numbers consecutively before a valid value is available. This can take up a lot of time.

SimTalk

setMaxNumberOfSamples [SimTalk]

See also

Maximum Number of Samples [preferences]

Probability Distributions

Bounding Probability Distribution Functions Tolerance For About Equal (~=) Comparison [model settings]

Type in the value for Epsilon in your currently open simulation model . Plant Simulation uses this value in about equal comparisons with the ~= operator in SimTalk as the tolerance value for which it considers values to be equal or not equal.

<!-- image -->

- Plant Simulation considers two values to be about equal, when the difference between the two values is less than the value you enter for epsilon.
- Plant Simulation considers two values to not be about equal, when the difference between the two values is greater than the value you enter for epsilon.

SimTalk

setEpsilon [SimTalk]

getEpsilon [SimTalk]

See also

Tolerance for About Equal (~=) Comparison [preferences]

Relational Operators

Check for a Large Amount of Different Values with switch [SimTalk]

**Frame Rate [model settings]**

###### Frame Rate [model settings]

Type in how often per second Plant Simulation refreshes the graphics in your currently open simulation model . You can specify a number between 1 and 100 .

<!-- image -->

Depending on your model a lower number may lead to a higher simulation speed.

A higher number results in a smooth animation, which may decrease the simulation speed though.

SimTalk

setAnimationRefreshRate [SimTalk]

See also

updateGUI [SimTalk]

Frame Rate [preferences]

###### Display Panel Frame Rate [model settings]

Select how often Plant Simulation refreshes the values of the display panels in your currently open simulation model . You can select a fraction of the frame rate. Plant Simulation shows to how many frames per second the fraction corresponds.

<!-- image -->

**See also**

Display Panel [object]

Display Panel Frame Rate [preferences]

Units Tab

Units [model settings]

Select the units for mass , currency , speed , acceleration , and length you want to use in your currently open simulation model on the tab Units .

You can also set Time Scale [model settings] and settings for the Daylight Saving Time [model settings] .

These settings only affect how Plant Simulation shows values in lists , tables , global variables , and in the window of the Console when values are to be shown in the user interface.

Internally Plant Simulation uses SI (Standard International) units ( kg , m/s , m/s2 , m ) for all physical values, regardless of what you selected on the Units ribbon tab. This has two visible effects when writing source code:

- If you assign a constant value to a variable or an attribute of an object, Plant Simulation interprets this value in the corresponding SI unit. For example, the statement Conveyor.Length := 3.4 means that Plant Simulation assigns 3.4 meters independent of the selected Length unit.

If you want to assign a value in another unit, you can enter this value directly after the numeric value, for example Conveyor.Length := 3.4ft .

SimTalk provides these units for the different data types:

| Data Type    | Available Units                              |
|--------------|----------------------------------------------|
| length       | m , mm , cm , km , ft , in , yd              |
| time         | s                                            |
| speed        | mps or m/s kmh or km/h mph or m/h fps or f/s |
| acceleration | mps² or m/s² fps² or f/s²                    |

- If you assign a physical data type to a value of data type real , you will receive the value in SI units. This also applies when you use physical units in computations with a result of data type real .

```simtalk
var r: real := Conveyor.Length // r always contains the length in meters
```

You can also type in values for the Time Scale and Daylight Saving Time .

A Length of 1.5 equals 1.5 meters.

A Speed of 4.55 equals 4.55 m/s.

A Mass of 0.3 equals 0.3 kg.

A Time of 0.1 equals 0.1 s.

**Note**

If you change units while modeling, Plant Simulation will convert all values you entered originally into the dialogs of objects to the new unit, except for monetary values. For these Plant Simulation only changes to the new currency symbol, but does not convert the values you entered originally!

Plant Simulation stores units with 15 valid digits. If you enter more digits, Plant Simulation keeps only the first 15 digits and rounds according to the remaining digits (down until the number 4, up from the number 5 on).

The computer stores the number 9876543210123456789.0 for example as 9.876543210123456*10E18.

**Note**

As Plant Simulation stores numbers using a finite number of digits, most of these values are only approximations of the exact values. Therefore, be aware of rounding errors, especially in comparisons!

**Example**

```simtalk
var a,b,c: length
a := 3.5;
b := 4.7;
c := 5.860034
if a*a+b*b-c*c = 0.0 then           // never reached: rounding error
elseif abs(a*a+b*b-c*c) < 0.000001  // compensates rounding error
end
```

**See also**

Units [preferences]

Mass [model settings]

Currency [model settings]

Speed [model settings]

Acceleration [model settings]

Length [model settings]

###### Mass [model settings]

Select the unit for the Mass to be used in the currently open simulation model from the drop-down list.

| Unit Abbreviation   | Equals       |
|---------------------|--------------|
| Kilogram kg         | 1.0kg        |
| Gram g              | 0.001kg      |
| Ton t               | 1000.0kg     |
| lb                  | 0.4535924kg  |
| Ounce oz            | 0.02834952kg |

Plant Simulation uses kilograms ( kg ) as the unit within methods. When you change the unit while modeling, it converts all values, which you already entered into objects, to the new unit.

SimTalk

getUnit [SimTalk]

See also

Mass [preferences]

###### Currency [model settings]

Type in or select the unit for the Currency to be used in the simulation model from the drop-down list.

<!-- image -->

| Unit               | Abbreviation   |
|--------------------|----------------|
| US Dollar          | $              |
| Euro               | €              |
| British Pound      | £              |
| Japanese Yen       | ¥              |
| Swiss Franc        | CHF            |
| Chinese Yuan       | CNY            |
| Russian Ruble      | RUB            |
| South African Rand | ZAR            |
| Indian Rupee       | INR            |
| South Korean Won   | WON            |

**Note**

When you change the currency unit while modeling, Plant Simulation only changes to the new currency symbol, but does not convert the actual values you entered originally!

SimTalk

getUnit [SimTalk]

See also

Currency [preferences]

Data Types [SimTalk] &gt; money

**Speed [model settings]**

###### Speed [model settings]

Select the unit for the Speed to be used in your currently open simulation model from the drop-down list.

<!-- image -->

| Unit                  | Enter in SimTalk 2.0   | Abbreviation Conversion factor   |
|-----------------------|------------------------|----------------------------------|
| km/h                  | kmh 0.277 m/s          | Kilometers per hour              |
| m/s                   | mps 1.0 m/s            | Meters per second                |
| Meters per m/min      | 0.01667 m/s            | minute                           |
| cm/s                  | 0.01 m/s               | Centimeters per second           |
| mm/s                  | 0.001 m/s              | Millimeters per second           |
| yd/s                  | 0.9144 m/s             | Yards per second                 |
| ft/s                  | fps 0.3048 m/s         | Feet per second                  |
| in/s                  | 0.0254 m/s             | Inches per second                |
| Miles per hour mph    | mph 0.44704 m/s *      |                                  |
| Length units per LU/s | depends on the         | unit                             |

When you assign a speed in a method, Plant Simulation uses meters per second ( m/s ) as unit. When you change the unit while modeling, it converts all values, which you already entered into objects, to the new unit.

* A mile per hour corresponds to 0.44704 meters per second. A meter per second corresponds to 2.236936 miles per hour.

**Note**

When you change the unit while modeling, it converts all values, which you already entered into objects, to the new unit.

**Note**

In SimTalk 2.0 you can specify the speed units mps , fps , kmh , and mph .

Type in the unit directly after the values, without a separating blank space, for example 100kmh or 100.5kmh .

```simtalk
var s1 : speed := 3.5mps // 3.5 meters per second
var s2 : speed := 3fps   // 3 feet per second
```

SimTalk

getUnit [SimTalk]

See also

Speed [preferences]

Speed [SimTalk] - data type

###### Acceleration [model settings]

Select the unit for the Acceleration to be used in your currently open simulation model from the drop-down list.

<!-- image -->

Acceleration only applies to the length-oriented object Conveyor and to the Transporter .

The value in parenthesis in the dropdown list designates the unit which you enter in SimTalk for example 10fps² .

| Unit                     | Abbreviation   | Enter in SimTalk 2.0    |
|--------------------------|----------------|-------------------------|
| Meters per second        | mps 2          | squared m/s 2           |
| Centimeters per squared  | cm/s 2         | second                  |
| ft/s                     | 2 fps 2        | Feet per second squared |
| Length units per squared | LU/s 2         | second                  |

**Note**

In SimTalk 2.0 you can specify the acceleration units mps² , cm² , fps² , and LU/s² .

Type in the unit directly after the values, without a separating blank space, for example 10mps2 or 10.2mps2 .

To create the ² symbol, activate the Num Lock key on the numeric keypad, hold down Alt and type in 0178 on the numeric keypad.

To create the ² symbol on the German keyboard layout , hold down Alt Gr and press the key with the number 2 . If your keyboard does not have the Alt Gr key, hold down Ctrl-right+Alt-right instead.

```simtalk
var a : acceleration := 10mps²   // 10 meters per second squared
var b : acceleration := 2.5fps²  // 2.5 feet per second squared
```

**SimTalk**

getUnit [SimTalk]

**See also Acceleration [preferences]**

Acceleration [SimTalk] - data type

**Length [model settings]**

###### Length [model settings]

Select the unit for the Length to be used in your currently open simulation model from the drop-down list.

<!-- image -->

| Unit   | Abbreviation   | Enter in SimTalk 2.0   | Conversion factor   |
|--------|----------------|------------------------|---------------------|
| km     | km             | 1000.0m                | Kilometer           |
| m      | m              | 1.0m                   | Meter               |
| cm     | cm             | 0.01m                  | Centimeter          |
| mm     | mm             | 0.001m                 | Millimeter          |
| yd     | yd             | 0.9144m                | Yard                |
| ft     | ft             | 0.3048m                | Foot                |
| in     |                | in 0.0254m             | Inch                |
| LU     |                | user-defined           | Length unit         |

Plant Simulation uses meters ( m ) as unit within methods. You can also select the unit of your own length unit. For example 1 LU = 0.3141 km.

If you want to specify a value in another unit, type in the unit directly after the values, without a separating blank space, for example 10m . You can enter the unit for floating point values and for integer values.

**Note**

When you assign a value in a Method , Plant Simulation uses meter ( m ) as unit and converts all values, which you already entered into objects with 15 valid digits. This may cause rounding errors.

```simtalk
var len := 1.0ft
var s : speed := 10.5m / 1:30
var x : length := 3m
```

**SimTalk**

**getUnit [SimTalk]**

See also

Length [preferences]

**Length [SimTalk] - data type**

###### Time Scale [model settings]

You can change the display of the Time Scale to meet your specific modeling needs in your currently open simulation model . You might, for example, divide a minute into 100 units, instead of in 60 seconds, or you might want to read 1:50 as 1.5 hours instead of 1 minute and 50 seconds.

<!-- image -->

You can enter a number between 0 and 86400 into the text box Time Scale 1 / (divided by) .

You can type an integer greater than 1 into the text boxes next to Transfer if .

Note You can only change the display of the timescale, not the timescale itself.

A time specification consists of four numbers, separated by colons, normally in the format days:hours:minutes:seconds . Plant Simulation stores the value itself in seconds and converts it at output time for the display .

Plant Simulation converts times according to the values which you type into the text boxes Time Scale and Transfer if . The Time Scale sets by which factor the time value will be divided. The result of this calculation will then be distributed across the four values days:hours:minutes:seconds . The three text boxes after Transfer if set when the value is to be carried over to the next number.

The following examples illustrate what to type in to achieve different displays of the time.

- If you want to use the standard time format, 24 hours to the day, 60 minutes to the hour, 60 seconds to the minute, you can use the default setting Time Scale 1/1.0 Transfer If 24:60:60 .

**Example**

str_to_time("1:15:45.5") // 1 hour, 15 minutes, 45.5 seconds

- If you want to use times based on minutes, you can type in Time Scale 1 / 60.0 Transfer If 30:24:60 .

The time value is first divided by 60, so that minutes instead of seconds are displayed as the smallest digit. The carry overs set that a month has 30 days, a day 24 hours, and an hour 60 minutes.

**Example**

str_to_time("1:15:45.5") // 1 day, 15 hours, 45,5 minutes

- If you want to simulate a longer period of time and want to display the time in the format years:months:days:hours , type in Time Scale 1 / 3600 Transfer If 12 : 30 : 24 , as an hour has 3600 seconds, a year has 12 months, a month has 30 days, and a day has 24 hours.
- If you want to divide a minute into 100 subunits instead of into 60 seconds, type in Time Scale 1 / 0.6 Transfer If 24 : 60 : 100 .

The time value is first divided by 0.6 to take the division into 100 subunits into account and then subdivided. 100 subunits then result in 1 minute.

**Example**

<!-- image -->

**Note**

Changing these settings not only affects how Plant Simulation shows times, but also affects the conversion functions str\_to\_time and str\_to\_dateTime . Therefore, be aware that changing the settings may affect the simulation results.

The method timeRepresenation returns the time system used, and writes it to a list in real format. The contents of the first cell shows the factor of (time) division, the second, third, and fourth represent the values you entered into the Transfer if text boxes. Normally, they are 24 , 60 , 60 .

See also

Time Scale [preferences]

Select Options for Units and for Displaying the Time

Daylight Saving Time

Daylight Saving Time [model settings]

To use daylight saving time during the months March to October in your currently open simulation model , select this check box.

Type the Month , the Week , the Day , and the Hour into the text boxes at which daylight saving time starts and ends.

<!-- image -->

Within the European Union daylight saving time starts at 02:00 o'clock GMT on the last Sunday in March. It ends on the last Sunday in October at 03:00 o'clock in the morning. Within the EU all timezones change the clock at the same time.

Within most of the United States of America daylight saving time starts at 02:00 o'clock in the morning on the first Sunday in April. It ends at 02:00 o'clock in the morning on the last Sunday in October.

SimTalk

setDaylightSavingTime [SimTalk]

See also

Daylight Saving Time [preferences]

Select Options for Units and for Displaying the Time

**Month [model settings]**

Type in the month at which the time change takes place in your currently open simulation model . You can type in a number between 1 and 12 .

<!-- image -->

Within the European Union daylight saving time starts at 02:00 o'clock GMT on the last Sunday in March. It ends on the last Sunday in October at 03:00 o'clock in the morning. Within the EU all timezones change the clock at the same time.

Within most of the United States of America daylight saving time starts at 02:00 o'clock in the morning on the first Sunday in April. It ends at 02:00 o'clock in the morning on the last Sunday in October.

SimTalk

setDaylightSavingTime [SimTalk]

See also

Month [preferences]

**Week [model settings]**

Type in the week at which the time change takes place in your currently open simulation model . For the default setting -1 daylight saving time starts on the last Sunday of the month you typed in under Month .

Type in a number between 1 and 4 . Week 1 is the first week including the Day Start you set, week 4 is the last week of the month.

<!-- image -->

Within the European Union daylight saving time starts at 02:00 o'clock GMT on the last Sunday in March. It ends on the last Sunday in October at 03:00 o'clock in the morning. Within the EU all timezones change the clock at the same time.

Within most of the United States of America daylight saving time starts at 02:00 o'clock in the morning on the first Sunday in April. It ends at 02:00 o'clock in the morning on the last Sunday in October.

SimTalk

setDaylightSavingTime [SimTalk]

See also

Week [preferences]

Month [model settings]

**Day [model settings]**

Type in the day at which the time change takes place in your currently open simulation model . For the U.S. and the EU, enter 0 for Sunday. 0 designates Sunday, 1 Monday, 2 Tuesday, 3 Wednesday, 4 Thursday, 5 Friday, and 6 Saturday.

<!-- image -->

Within the European Union daylight saving time starts at 02:00 o'clock GMT on the last Sunday in March. It ends on the last Sunday in October at 03:00 o'clock in the morning. Within the EU all timezones change the clock at the same time.

Within most of the United States of America daylight saving time starts at 02:00 o'clock in the morning on the first Sunday in April. It ends at 02:00 o'clock in the morning on the last Sunday in October.

SimTalk

setDaylightSavingTime [SimTalk]

See also

Day [preferences]

**Hour [model settings]**

Type in the hour at which the time change takes place in your currently open simulation model . Type in a number between 0 and 23 . For the EU, type in 2 for 02:00 o'clock in the morning.

<!-- image -->

Within the European Union daylight saving time starts at 02:00 o'clock GMT on the last Sunday in March. It ends on the last Sunday in October at 03:00 o'clock in the morning. Within the EU all timezones change the clock at the same time.

Within most of the United States of America daylight saving time starts at 02:00 o'clock in the morning on the first Sunday in April. It ends at 02:00 o'clock in the morning on the last Sunday in October.

SimTalk

setDaylightSavingTime [SimTalk]

See also

Hour [preferences]

2D Tab

###### 2D [model settings]

Select the default settings that determine how a Frame in the current model shows the objects which you insert into it on the tab 2D .

**Note**

The settings on the tab 2D only apply to models you create in 2D Only and in 2D and 3D.

<!-- image -->

<!-- image -->

Show Object Names [model settings]

To show the names of the objects below their icons in the window of your currently open simulation model , select this check box.

<!-- image -->

<!-- image -->

To show or hide them, you can also click the button Show Object Names on the View ribbon tab of the Frame in a 2D model..

SimTalk

ShowObjectNames [SimTalk]

See also

Show Object Names [preferences]

Show Object Names [View ribbon] - 2D

Name [general description]

###### Show MU Names [model settings]

To show the names of the parts ( MUs ) in your currently open simulation model , select this check box.

<!-- image -->

This only works, when you also select Show Object Names .

This prevents your simulation model from looking cluttered.

<!-- image -->

To show or hide them, you can also click the button Options &gt; Show MU Names on the View ribbon tab of the Frame in a 2D Only model .

See also

Show MU Names [preferences]

###### Show Object Labels [model settings]

To show the label , which you entered for the objects, below their icons in the window of your currently open simulation model , select this check box.

If you also selected to Show Object Names , Plant Simulation shows the labels below the names.

<!-- image -->

If you deactivated Show Object Names , it shows the Labels directly below the icon.

<!-- image -->

To show or hide them, you can also click the button Options &gt; Show Object Labels on the View ribbon tab of the Frame in a 2D Only model .

SimTalk

ShowObjectLabels [SimTalk]

See also

Show Object Labels [preferences]

Label [general description]

###### Show Predecessors [model settings]

To show the number of an incoming connection for each material flow connection in the window of your currently open simulation model , select this check box. Plant Simulation only shows the predecessors in the Frame window when you also select Show Connections .

The predecessor is the object that is connected to the selected object with a Connector and that precedes it in the sequence of stations in the simulation model.

For the first connection from another object to the current object, the Connector shows &gt; 1 , denoting that this is the first predecessor. If the object has more than one predecessor, Plant Simulation numbers the predecessors in the order you connected them, &gt; 2 for the second, &gt;3 for the third, etc.

<!-- image -->

To show or hide them, you can also click the button Options &gt; Show Predecessors on the View ribbon tab of the Frame in a 2D Only model .

3D shows the predecessors and the successors of an object in a Tooltip when you drag the mouse over the respective Connector .

<!-- image -->

**SimTalk**

PredInterface [SimTalk]

See also Show Predecessors [preferences]

Show Connections [preferences]

###### Show Successors [model settings]

To show the number of an outgoing connection for each material flow connection in your currently open simulation model , select this check box. Plant Simulation only shows the successors in the Frame window when you also select Show Connections .

<!-- image -->

The successor is the object that is connected to the selected object with a Connector and that succeeds it in the sequence of stations in the model.

For the first connection from the current object to another object, the Connector shows 1 &gt; , denoting that this is the first successor. If the object has more than one successor, Plant Simulation numbers the successors in the order you connected them, 2 &gt; for the second, 3 &gt; for the third, etc.

<!-- image -->

To show or hide them, you can also click the button Options &gt; Show Successors on the View ribbon tab of the Frame in a 2D Only model .

3D shows the predecessors and the successors of an object in a Tooltip when you drag the mouse over the respective Connector .

<!-- image -->

**SimTalk**

SuccInterface [SimTalk]

**See also Show Successors [preferences]**

Show Connections [preferences]

###### Show Display Panels [model settings]

To show the display panels , which you defined for the objects in a 2D Only model , in the Frame , select this check box.

<!-- image -->

To show or hide them, you can also click the button Options &gt; Show Display Panels on the View ribbon tab of the Frame in a 2D Only model .

SimTalk

ShowDisplayPanels [SimTalk]

See also

Display Panel [object]

###### Show Connections [model settings]

To show connections, i.e., the Connectors between objects in the window of your currently open simulation model , select this check box. Plant Simulation shows the direction of the connection with an arrow head in the middle of the Connector .

<!-- image -->

The commands Show Predecessors and Show Successors only work, when you also select Show connections .

<!-- image -->

To show or hide them, you can also click the button Show Connections on the View ribbon tab of the Frame in a 2D Only model .

See also

Show Connections [preferences]

###### Show Grid [model settings]

To show the grid in the Frames of your currently open simulation model , select this check box. This feature is useful for automatically aligning objects while you insert them.

<!-- image -->

Type the spacing of the grid intervals on the x-axis and the y- axis into the text boxes below Frame Grid Spacing [model settings] .

You might want to select Show Object Borders as well.

When the Grid is active, Plant Simulation places the objects which you insert onto grid points. You can then move the objects by grid units only. The reference point of the icon of the object determines where Plant Simulation places the object on the grid point. By default, the reference point of a material flow object is located in the center of the icon. When you place an object, Plant Simulation places the reference point onto the grid point nearest to the mouse pointer. You can move the reference point to any position of your choice in the Icon Editor .

Selecting Show grid after you placed objects has no effect on the alignment of the objects which you already placed. They remain at the position at which you inserted them.

To align the objects which you already inserted, click Align to Grid on the Icons ribbon tab of the Frame . Plant Simulation then moves all selected objects, so that their reference points are aligned with the closest grid point.

<!-- image -->

To show or hide the grid points, you can also click the button Show Grid on the View ribbon tab of the Frame in a 2D Only model .

See also

Show Grid [preferences]

###### Show Object Borders [model settings]

To show the borders around the icons of the objects, which you inserted into your currently open simulation model , select this check box.

This way you can see the full Icon Size of the icon. The size of the border depends on the size of the icon.

<!-- image -->

To show or hide them, you can also click the button Options &gt; Show Object Borders on the View ribbon tab of the Frame in a 2D Only model .

**See also**

Show Object Borders [preferences]

###### Show Comments [model settings]

To show objects of type Comment , which you inserted into your currently open simulation model , select this check box.

<!-- image -->

| On   | Off   |
|------|-------|

To show or hide them, you can also click the button Show Comments on the View ribbon tab of the Frame in a 2D Only model .

See also

Show Comments [preferences]

Comment [object]

###### Ignore Transparent Area [model settings]

To be able to select an object that moves under the transparent area of the icon of an object in front of it in your currently open simulation model , select this check box.

<!-- image -->

**See also**

Ignore Transparent Area [preferences]

###### Frame Grid Spacing [model settings]

Type in the distance between the individual grid points from each other on the x-axis, i.e., the horizontal axis of your currently open simulation model . Type in the distance between the individual grid points from each other on the y-axis, i.e., the vertical axis of the Frame .

The grid points are the points at which the imaginary grid lines intersect.

<!-- image -->

3D Tab

###### 3D [model settings]

Select the Visualization setting Screen Coverage Threshold for your currently open simulation model on the tab 3D .

<!-- image -->

**3D [model settings]**

See also 3D [preferences] Screen Coverage Threshold [model settings] Create Optimized Graphics for Rendering [model settings]

###### Screen Coverage Threshold [model settings]

Type in the threshold value for showing or hiding objects in the scene windows in your currently open simulation model , which are smaller than the value in pixels that you specify. This setting is used for maximizing performance.

See also

Screen Coverage Threshold [preferences]

###### Create Optimized Graphics for Rendering [model settings]

Create an optimized version of the graphics for rendering them for the currently open simulation model .

To let Plant Simulation create optimized versions of user-defined graphics for rendering in the background, select this check box.

**Note**

We recommend to find a balance between fast rendering and fast modeling. If this option is active, Plant Simulation continuously re-optimizes your graphics after modifications. While this can speed up rendering, it can also slow down Plant Simulation while you are modeling.

When the option is active, Plant Simulation optimizes graphics by running the Flatten Structure optimizer and with options to optimize as much as possible without losing details.

See also

Create Optimized Graphics for Rendering [preferences]

#### Preferences [Menu Item]

Preferences

Opens the Preferences dialog in which you can select global settings for new models in Plant Simulation .

<!-- image -->

- On the tabs 2D , User Interface , Editor , 3D , and License you can select general settings, which are independent of the current simulation model.
- On the tabs Simulation and Units you can select model-specific settings, which apply to new models. The tab General shows both types of settings.
- On the tabs Data Privacy 1 and Data Privacy 2 you can decide and set if you want to participate in these programs or not.

Click the tabs to access the respective set of features. Then

- Click OK to apply your settings and save the new configuration to the registry under HKEY\_CURRENT\_USER for each user separately.
- Click Cancel to close the window without saving any changes.

General Tab

Note

The Model Settings only apply to the current simulation model !

Note

As an administrator, you can set default values in the windows registry .

See also

Model Settings

Select Settings in Plant Simulation

General [preferences]

Select a number of general and model-specific settings for new models , which you create after changing settings on the tab General .

Model Language [preferences]

Date and Time Format [preferences]

Model Saving History [preferences]

Visualization [preferences]

Connect Objects Automatically [preferences]

Connector Positioning [preferences]

Libraries Directories

Local Documentation Server

Create Backup Files with Time Stamp

###### Model Language [preferences]

Select the language of new simulation models . Plant Simulation saves this setting to the model file.

<!-- image -->

When you create a new simulation model, the Model Language determines:

- The names of folders and objects, such as MaterialFlow and Station for English or Materialfluss and Einzelstation for German .
- The items of the drop-down lists, such as the names of the distributions ( Uniform or Gleich ).
- The return value of the attributes that correspond to the entries of the drop-down lists, for example print Station.RecoveryTimeMode . When you query such an attribute in SimTalk , Plant Simulation returns the value in English , except the model language is German; in the latter case Plant Simulation returns the value in German. For the example Station.RecoveryTimeMode Plant Simulation returns Wenn Teil eintritt when the model language is German , When part enters for all other model languages.
- The contents of the window Show Attributes and Methods . When the model language is German , the window lists the German names of the attributes and methods. For all other model languages the window lists the names in English.
- The names, which Auto Complete within the Method Editor suggests. When the model language is German , the Method Editor suggests the German names of attributes and methods. For all other model languages it suggests the English names.

**Note**

When you change the Model Language , the user interface language of Plant Simulation will not be changed. The user interface language of Plant Simulation is determined by the operating system of your computer. You can change the user interface language of Plant Simulation with the command line argument /L UILanguage , compare Specifying Start Options .

SimTalk

language [SimTalk]

See also

Model Language [model settings]

userInterfaceLanguage [SimTalk]

**Date and Time Format [preferences]**

###### Date and Time Format [preferences]

Select the date and time format for new simulation models . You can choose the 12 hour (AM/PM) or 24 hour YMD (year-month-day) format or the DMY (day-month-year) notation for the date and time format.

<!-- image -->

| Date and time format   | Looks like this   |
|------------------------|-------------------|
| yyyy/mm/dd 12 hour     |                   |
| yyyy-mm-dd 24 hour     |                   |
| dd.mm.yyyy 24 hour     |                   |

**See also**

Date and Time Format [model settings]

###### Model Saving History [preferences]

Select which kind of comment Plant Simulation adds to new simulation models (.spp), each time you save it.

<!-- image -->

- None does not save the history of how you saved your model.
- Without Comment adds no comment.
- With Comment opens a comment window, each time when you save the model. Type in your comment here.

When you select Without Comment or With Comment Plant Simulation adds a row to the dialog Model Saving History each time you save the model.

When the model crashes, Plant Simulation adds a description of the problem to the dialog instead of a comment. This helps our software engineers detect what caused the crash.

To view the comment you entered, select File &gt; Options &gt; Show Model History .

See also

Model Saving History [model settings]

###### Visualization [preferences]

Select the visualization with which you want to create new simulation models , 3D Only or 2D Only .

<!-- image -->

**Note**

We strongly recommend to create your models either in 3D Only or in 2D Only mode.

We strongly advise against creating your models in 2D and 3D mode. The setting 2D and 3D is intended to convert a 2D model to a 3D model.

- Only in 2D shows the model in 2D Only.
- Only in 3D shows the model in 3D Only.

**Note**

We recommend to always create your models in 3D Only mode . This also applies if you are only interested in the 2D view.

<!-- image -->

You can model in Planning View in 3D, which corresponds to the top view in 2D. In addition, you can continuously zoom in the 3D window and 3D has better performance than 2D.

- In 2D and in 3D . This creates the model consisting of a 2D part and a 3D part.

**Note**

The setting 2D and 3D is intended to convert a 2D model into a 3D model. We strongly advise against modeling in 2D and 3D mode.

Check if the 3D model behaves according to your expectations and then save the model as a 3D Only model.

<!-- image -->

- Ask each time . Asks each time you create a new simulation model how you want to create it. For this setting Plant Simulation only provides Only in 2D and Only in 3D .

If you created the model in 2D Only and need to create its 3D part at a later point in time, you can also

<!-- image -->

If you created the model in 2D and in 3D and then would like to convert it to a 3D Only model, i.e., discard the 2D part, select 3D Only and save the model.

Depending on the setting you selected, the simulation model looks slightly different and provides different tabs on the ribbon bar. Likewise, SimTalk provides different attributes and methods.

See also

Visualization [model settings]

Select the Visualization

Save Model File As

###### Connect Objects Automatically [preferences]

To automatically connect adjacent objects and Frames with Connectors in new simulation models , when you insert them, select this check box.

<!-- image -->

- When you connect Frames , the positions of exit and entrance Interface objects have to be close to each other.
- When you connect objects , the positions of the exits and the entrances of the objects have to be located close to each other.

Plant Simulation proceeds as follows when automatically connecting objects as described below.

- It always uses the first connection possible.
- If a connection exists between the respective object and any other object at a particular side ( Entrance or Exit ), Plant Simulation does not add a new connection at the same side.
- If two objects are located close to each other, the automatic connection will be created between the respective object and the object with which the connections was established first .
- Plant Simulation only establishes an automatic connection in 3D, if the bounding boxes overlap in the Z -direction.

**Note**

When automatically connecting objects, Plant Simulation uses the first Connector class in the Class Library , starting at the top.

To change that order, compare Work with Folders, Frames, Objects in the Class Library .

**Note**

The following applies for automatically connecting the length-oriented objects Turnplate , Turntable , AngularConverter , Conveyor , Converter , Track , and TwoLaneTrack in 3D:

If TransferLengthToObject is off for one of these objects in 3D, but if a suitable MU animation path exists, then Plant Simulation uses the start point and the end point of these animation paths for automatically connecting the objects and for displaying Connectors . Suitable MU animation paths are Default or Cross for the Converter , Lane A or Lane B for the TwoLaneTrack and Default for the remaining objects. This applies for Connect Objects Automatically and for the method connectAutomatically .

SimTalk

connectAutomatically [SimTalk]

See also

Connect Objects Automatically [model settings]

Work with Folders, Frames, Objects in the Class Library

###### Connector Positioning [preferences]

Select on which side of the object Plant Simulation places the starting point or the end point of Connectors in new simulation models .

<!-- image -->

- Fixed Side places the starting point of the Connector at the exit of the object and the end point at its entrance.

For the length-oriented objects Plant Simulation always places the Connectors at a fi xed side .

- Angle-dependent takes into account the angle between the objects when determining the starting point or the end point of the Connector .

For WorkerPool , Workplace , and Pick-and-Place-Robot Plant Simulation always places the Connectors angle-dependent .

<!-- image -->

**See also**

**Connector Positioning [model settings]**

**Libraries Directories**

###### Libraries Directories

Click the folder button and navigate to the folder in which to store the object libraries, which you and your colleagues develop or which you purchase from a third party vendor in new simulation models .

<!-- image -->

You can also type in several directories separated by a semicolon. The library manager checks this folder/ these folders for the most up-to-date version of a library and lets you download it to your hard drive from there. This way you can add company-specific and project-specific libraries to your simulation model.

The text box shows the path to the folders in which you stored the object libraries, which you and your colleagues develop or which you purchase from a third party vendor. The semicolon separates directories if you typed in several of them.

Plant Simulation searches for libraries in the installation directory and in all directories, which you type in here. It shows all libraries, which it finds in these directories, in the dialog Manage Class Library .

**Note**

The system administrator can set this registry value to a network path when installing Plant Simulation .

<!-- image -->

<!-- image -->

###### Local Documentation Server

To use the webhelp locally, type in the name of and the path to the Local Documentation Server . Be aware that the installed version displays the state of the help of the date when we created the help package, not the newest version that is available on the web.

<!-- image -->

We provide the Plant Simulation Help on Support Center on the web by default. This way you always get the current state of the help with the newest enhancements.

Enter http:/localhost:5000 when you installed the help server on your local machine with the default port. Plant Simulation automatically adds the identifier of the Plant Simulation user interface language you set.

This setting applies immediately once you specify the local documentation server.

**Note**

To use the Plant Simulation Help locally, you have to download the Siemens Documentation Server 3.0 or higher and the Plant Simulation 2504 Help and install them on your computer.

**See also**

Install the Online Help Locally

###### Create Backup Files with Time Stamp

To add the current date to the file name of the backup file (.bak), which is going to be created when saving the model, select this check box.

<!-- image -->

Simulation Tab

Simulation [preferences]

Select settings that apply to how Plant Simulation executes the simulation runs for new simulation models on the tab Simulation .

Maximum Depth of Calls [preferences]

Maximum Number of Call Chains [preferences]

Maximum Number of Suspended Methods [preferences]

Maximum Number of Samples [preferences]

Tolerance for About Equal (~=) Comparison [preferences]

Frame Rate [preferences]

Display Panel Frame Rate [preferences]

Complex simulation models will contain numerous Method objects, which themselves may call other Methods . Incorrect modeling may cause a Method to be called repeatedly by itself during the simulation run, either directly or indirectly through other methods. This is called an endless recursion. With each call, Plant Simulation takes up more RAM, until it used up all available memory and terminates the simulation run.

Plant Simulation provides several ways for detecting and preventing this and related problems.

###### Simulation [preferences]

**See also**

###### Simulation [model settings]

###### Maximum Depth of Calls [preferences]

Type in the number of Methods that may be called by other Methods to prevent Plant Simulation from running out of memory in new simulation models .

<!-- image -->

When Plant Simulation exceeds the maximum depth of calls, the simulation stops and the Debugger opens. Increase the number of the maximum depth of calls and continue or correct programming errors contained in the code, if any. To do so, hold down Ctrl and double-click the selected line containing the error in the Method Debugger .

SimTalk

setMaxDepthOfCalls [SimTalk]

See also

Maximum Depth of Calls [model settings]

###### Maximum Number of Call Chains [preferences]

Type in the maximum number of call chains for new simulation models . The call chain designates the list of all method calls to be executed. The EventController creates this list during the reset and init phases of your simulation model.

<!-- image -->

With the method callEvery you can create a list of methods yourself. A modeling flaw may cause the same callEvery method to be called repeatedly during the simulation, thus taking up more and more memory and finally terminating the simulation. By limiting the number of call chains, you can detect and correct the modeling error.

When the Maximum Number of Call Chains reaches the value you typed in, the simulation stops and Plant Simulation shows an error message. Then you can increase the maximum number of call chains and continue, or you can correct the faulty source code. To do so, hold down Ctrl and double-click the selected line containing the error in the Debugger .

SimTalk

setMaxNumberOfCallChains [SimTalk]

executeNewCallChain [SimTalk]

callEvery [SimTalk]

See also

Maximum Number of Call Chains [model settings]

###### Maximum Number of Suspended Methods [preferences]

Type in the maximum number of suspended Methods for new simulation models . The number of Methods suspended by waituntil and stopuntil statements and by wait statements is limited.

<!-- image -->

When Plant Simulation reaches the number you set, it will not suspend any additional Methods and displays an error message. You can then either increase the Maximum Number of Suspended Methods by typing a greater number into this text box, and continue your simulation run or stop the simulation and fix the modeling error. To do so, hold down Ctrl and double-click the selected line containing the error in the Method Debugger .

SimTalk

setMaxSuspendedMethods [SimTalk]

See also

Maximum Number of Suspended Methods [model settings]

waituntil [SimTalk] and stopuntil [SimTalk]

Interrupting Method Execution with Wait

###### Maximum Number of Samples [preferences]

Maximum Number of Samples [preferences]

Type in the Maximum Number of Samples . This prevents Plant Simulation from spending an excessive amount of time for rolling the dice in new simulation models , which is caused by an unfortunate selection of the interval bounds.

<!-- image -->

You can type in a number between 1 and 32000 . Plant Simulation ignores values outside of this range without showing a warning message and keeps the previous value. The greater the value you enter, the later you recognize if the bounds are too close together.

For a normal distribution it may, for instance, happen that Plant Simulation draws extremely large values. When the bounds are too close together, this may result almost exclusively in outliers. Then Plant Simulation has to create numerous random numbers consecutively before a valid value is available. This can take up a lot of time.

SimTalk

setMaxNumberOfSamples [SimTalk]

See also

Maximum Number of Samples [model settings]

Probability Distributions

Bounding Probability Distribution Functions

###### Tolerance for About Equal (~=) Comparison [preferences]

Type in the value for Epsilon for new simulation models . Plant Simulation uses this value in about equal comparisons with the ~= operator in SimTalk as the tolerance value for which it considers numerical values to be equal or not equal.

<!-- image -->

- Plant Simulation considers two numerical values to be about equal, when the difference between the two values is less than the value you enter for epsilon.
- Plant Simulation considers two numerical values to not be about equal, when the difference between the two values is greater than the value you enter for epsilon.

**SimTalk**

setEpsilon [SimTalk]

getEpsilon [SimTalk]

See also

Tolerance For About Equal (~=) Comparison [model settings]

Relational Operators

Check for a Large Amount of Different Values with switch [SimTalk]

**Frame Rate [preferences]**

###### Frame Rate [preferences]

Type in how often per second Plant Simulation refreshes the graphics in new simulation models . You can enter a number between 1 and 100 .

<!-- image -->

Depending on your model a lower number may lead to a higher simulation speed.

A higher number results in a smooth animation, which may decrease the simulation speed though.

SimTalk

setAnimationRefreshRate [SimTalk]

See also

Frame Rate [model settings]

updateGUI [SimTalk]

###### Display Panel Frame Rate [preferences]

Select how often Plant Simulation refreshes the values of the display panels in new simulation models . You can select a fraction of the frame rate. Plant Simulation shows to how many frames per second the fraction corresponds.

<!-- image -->

**See also**

Display Panel Frame Rate [model settings]

Display Panel [object]

Units Tab

Units [preferences]

Select the units for mass , currency , speed , acceleration , and length you want to use in new simulation models on the tab Units .

You can also set the Time Scale [preferences] and select settings for the Daylight Saving Time [preferences] .

These settings only affect how Plant Simulation shows values in lists , tables , global variables , and in the window of the Console when values are to be shown in the user interface.

Internally Plant Simulation uses SI (Standard International) units ( kg , m/s , m/s2 , m ) for all physical values, regardless of what you selected on the Units ribbon tab. This has two visible effects when writing source code:

- If you assign a constant value to a variable or an attribute of an object, Plant Simulation interprets this value in the corresponding SI unit. For example, the statement Conveyor.Length := 3.4 means that Plant Simulation assigns 3.4 meters independent of the selected Length unit.

If you want to assign a value in another unit, you can type in this value directly after the numeric value, for example Conveyor.Length := 3.4ft .

SimTalk provides these units for the different data types:

| Data Type    | Available Units                              |
|--------------|----------------------------------------------|
| length       | m , mm , cm , km , ft , in , yd              |
| time         | s                                            |
| speed        | mps or m/s kmh or km/h mph or m/h fps or f/s |
| acceleration | mps² or m/s² fps² or f/s²                    |

- If you assign a physical data type to a value of data type real , you will receive the value in SI units. This also applies when you use physical units in computations with a result of data type real .

```simtalk
var r: real := Conveyor.Length // r always contains the length in meters
```

You can also type in values for the time scale and daylight saving time .

A length of 1.5 equals 1.5 meters.

A speed of 4.55 equals 4.55 m/s.

A mass of 0.3 equals 0.3 kg.

A time of 0.1 equals 0.1 s.

**Note**

If you change units while modeling, Plant Simulation will convert all values you typed originally into the dialogs of objects to the new unit, except for monetary values. For these Plant Simulation only changes to the new currency symbol, but does not convert the values you typed in originally!

Plant Simulation stores units with 15 valid digits. If you type in more digits, Plant Simulation keeps only the first 15 digits and rounds according to the remaining digits (down until the number 4, up from the number 5 on).

The computer stores the number 9876543210123456789.0 for example as 9.876543210123456*10E18.

**Note**

As Plant Simulation stores numbers using a finite number of digits, most of these values are only approximations of the exact values. Therefore, be aware of rounding errors, especially in comparisons!

**Example**

```simtalk
var a,b,c: length
a := 3.5;
b := 4.7;
c := 5.860034
if a*a+b*b-c*c = 0.0 then           // never reached: rounding error
elseif abs(a*a+b*b-c*c) < 0.000001  // compensates rounding error
end
```

**See also**

Units [model settings]

Mass [preferences]

Currency [preferences]

Speed [preferences]

Acceleration [preferences]

Length [preferences]

**Mass [preferences]**

###### Mass [preferences]

Select the unit for the mass to be used in new simulation models from the drop-down list.

<!-- image -->

| Unit   | Abbreviation   | Equals           |
|--------|----------------|------------------|
| kg     | 1.0 kg         | Kilogram         |
|        | 0.001 kg       | Gram g           |
|        | 1000.0 kg      | Ton t            |
| lb     | 0.4535924      | British Pound kg |
| Ounce  | oz             | 0.02834952 kg    |

Plant Simulation uses kilograms ( kg ) as the unit within methods. When you change the unit while modeling, it converts all values, which you already entered into objects, to the new unit.

SimTalk

getUnit [SimTalk]

See also

Mass [model settings]

###### Currency [preferences]

Select or enter the unit for the currency to be used in new simulation models from the drop-down list.

<!-- image -->

| Unit               | Abbreviation   |
|--------------------|----------------|
| US Dollar          | $              |
| Euro               | €              |
| British Pound      | £              |
| Japanese Yen       | ¥              |
| Swiss Franc        | CHF            |
| Chinese Yuan       | CNY            |
| Russian Ruble      | RUB            |
| South African Rand | ZAR            |
| Indian Rupee       | INR            |
| South Korean Won   | WON            |

**Note**

When you change the currency unit while modeling, Plant Simulation only changes to the new currency symbol, but does not convert the actual values you entered originally!

SimTalk

getUnit [SimTalk]

See also

Currency [model settings]

Data type money

**Speed [preferences]**

###### Speed [preferences]

Select the unit for the speed to be used in new simulation models from the drop-down list.

<!-- image -->

| Unit                  | Enter in SimTalk 2.0   | Abbreviation Conversion factor   |
|-----------------------|------------------------|----------------------------------|
| km/h                  | kmh 0.277 m/s          | Kilometers per hour              |
| m/s                   | mps 1.0 m/s            | Meters per second                |
| m/min                 | 0.01667 m/s            | Meters per minute                |
| cm/s                  | 0.01 m/s               | Centimeters per second           |
| mm/s                  | 0.001 m/s              | Millimeters per second           |
| yd/s                  | 0.9144 m/s             | Yards per second                 |
| ft/s                  | fps 0.3048 m/s         | Feet per second                  |
| in/s                  | 0.0254 m/s             | Inches per second                |
| mph                   | mph 0.44704 m/s *      | Miles per hour                   |
| Length units per LU/s | depends on the unit    |                                  |

When you assign a speed in a method, Plant Simulation uses meters per second ( m/s ) as unit. When you change the unit while modeling, it converts all values, which you already entered into objects, to the new unit.

* A mile per hour corresponds to 0.44704 meters per second. A meter per second corresponds to 2.236936 miles per hour.

**Note**

When you change the unit while modeling, it converts all values, which you already entered into objects, to the new unit.

**Note**

In SimTalk 2.0 you can specify the speed units mps , fps , kmh , and mph .

Type in the unit directly after the values, without a separating blank space, for example 100kmh or 100.5kmh .

```simtalk
var s1 : speed := 3.5mps // 3.5 meters per second
var s2 : speed := 3fps   // 3 feet per second
```

SimTalk

getUnit [SimTalk]

See also

Speed [model settings]

Speed [SimTalk] - data type

**Acceleration [preferences]**

###### Acceleration [preferences]

Select the unit for the acceleration to be used in new simulation models from the drop-down list.

<!-- image -->

Acceleration only applies to the length-oriented object Conveyor and to the Transporter .

The value in parenthesis in the drop-down list designates the unit which you enter in SimTalk for example 10fps² .

| Unit                           | Abbreviation   | Enter in SimTalk 2.0   |
|--------------------------------|----------------|------------------------|
| Meter per second squared       | m/s 2          | mps 2                  |
| Centimeter per second squared  | cm/s 2         |                        |
| Foot per second squared        | ft/s 2         | fps 2                  |
| Length unit per second squared | LU/s 2         |                        |

**Note**

In SimTalk 2.0 you can specify the acceleration units mps² , cm² , fps² , and LU/s² .

Type in the unit directly after the values, without a separating blank space, for example 10mps2 or 10.2mps2 .

To create the ² symbol, activate the Num Lock key on the numeric keypad, hold down Alt and type in 0178 on the numeric keypad.

To create the ² symbol on the German keyboard layout , hold down Alt Gr and press the key with the number 2 . If your keyboard does not have the Alt Gr key, hold down Ctrl-right+Alt-right instead.

```simtalk
var a : acceleration := 10mps²   // 10 meters per second squared
var b : acceleration := 2.5fps²  // 2.5 feet per second squared
```

**SimTalk**

getUnit [SimTalk]

See also

Acceleration [model settings]

Acceleration [SimTalk] - data type

**Acceleration [preferences]**

**Length [preferences]**

###### Length [preferences]

Select the unit for the length to be used in new simulation models from the drop-down list.

<!-- image -->

<!-- image -->

| Unit   | Abbreviation   | Enter in SimTalk 2.0   | Conversion factor   |
|--------|----------------|------------------------|---------------------|
| km     | km             | 1000.0m                | Kilometer           |
| m      | m              | 1.0m                   | Meter               |
| cm     | cm             | 0.01m                  | Centimeter          |
| mm     | mm             | 0.001m                 | Millimeter          |
| yd     | yd             | 0.9144m                | Yard                |
| ft     | ft             | 0.3048m                | Foot                |
| in     |                | in 0.0254m             | Inch                |
| LU     |                | user-defined           | Length unit         |

Plant Simulation uses meter ( m ) as unit within methods. You can also select your own length unit. For example 1 LU = 0.3141 km.

If you want to specify a value in another unit, type in the unit directly after the values, without a separating blank space, for example 10m . You can enter the unit for floating point values and for integer values.

**Note**

When you assign a value in a Method , Plant Simulation uses meter ( m ) as unit and converts all values, which you already entered into objects with 15 valid digits. This may cause rounding errors.

```simtalk
var len := 1.0ft
var s : speed := 10.5m / 1:30
var x : length := 3m
```

**SimTalk**

getUnit [SimTalk]

See also

Length [model settings]

**Length [SimTalk] - data type**

**Time Scale [preferences]**

###### Time Scale [preferences]

You can change the display of the Time scale to meet your specific modeling needs in new simulation models . You might, for example, divide a minute into 100 units, instead of in 60 seconds, or you might want to read 1:50 as 1.5 hours instead of 1 minute and 50 seconds.

You can enter a number between 0 and 86400 into the text box time scale 1 / (divided by) .

You can enter an integer greater than 1 into the text boxes next to transfer if .

<!-- image -->

**Note**

You can only change the display of the timescale, not the timescale itself.

A time specification consists of four numbers, separated by colons, normally in the format days:hours:minutes:seconds . Plant Simulation stores the value itself in seconds and converts it at output time for the display .

Plant Simulation converts times according to the values which you type into the text boxes timescale and transfer if . The timescale sets by which factor the time value will be divided. The result of this calculation will then be distributed across the four values days:hours:minutes:seconds . The three text boxes after transfer if set when the value is to be carried over to the next number.

The following examples illustrate what to enter to achieve different displays of the time.

- If you want to use the standard time format, 24 hours to the day, 60 minutes to the hour, 60 seconds to the minute, you can use the default setting time scale 1/1.0 transfer if 24:60:60 .

**Example**

str_to_time("1:15:45.5") // 1 hour, 15 minutes, 45.5 seconds

- If you want to use times based on minutes, you can type in time scale 1 / 60.0 transfer if 30:24:60 .

The time value is first divided by 60, so that minutes instead of seconds are displayed as the smallest digit. The carry overs set that a month has 30 days, a day 24 hours, and an hour 60 minutes.

**Example**

str_to_time("1:15:45.5") // 1 day, 15 hours, 45,5 minutes

- If you want to simulate a longer period of time and want to display the time in the format years:months:days:hours , type in time scale 1 / 3600 transfer if 12 : 30 : 24 , as an hour has 3600 seconds, a year has 12 months, a month has 30 days, and a day has 24 hours.
- If you want to divide a minute into 100 subunits instead of into 60 seconds, type in time scale 1 / 0.6 transfer if 24 : 60 : 100 .

The time value is first divided by 0.6 to take the division into 100 subunits into account and then subdivided. 100 subunits then result in 1 minute.

**Example**

str_to_time("1:15:45.5") // 1 hour, 15 minutes, 27.3 seconds

**Note**

Changing these settings not only affects how Plant Simulation shows times, but also affects the conversion functions str\_to\_time and str\_to\_dateTime . Therefore, be aware that changing the settings may affect the simulation results.

The method timeRepresenation returns the time system used, and writes it to a list in real format. The contents of the first cell shows the factor of (time) division, the second, third, and fourth represent the values you entered into the Transfer if text boxes. Normally, they are 24 , 60 , 60 .

See also

Time Scale [model settings]

Select Options for Units and for Displaying the Time

Daylight saving time

Daylight Saving Time [preferences]

To use daylight saving time during the months March to October in new simulation models , select this check box.

Type the Month , the Week , the Day , and the Hour at which daylight saving time starts and ends into the text boxes.

<!-- image -->

Within the European Union daylight saving time starts at 02:00 o'clock GMT on the last Sunday in March. It ends on the last Sunday in October at 03:00 o'clock in the morning. Within the EU all timezones change the clock at the same time.

Within most of the United States of America daylight saving time starts at 02:00 o'clock in the morning on the first Sunday in April. It ends at 02:00 o'clock in the morning on the last Sunday in October.

SimTalk

setDaylightSavingTime [SimTalk]

See also

Daylight Saving Time [model settings]

Select Options for Units and for Displaying the Time

**Month [preferences]**

Type in the month at which the time change takes place in new simulation models . You can type in a number between 1 and 12 .

<!-- image -->

Within the European Union daylight saving time starts at 02:00 o'clock GMT on the last Sunday in March. It ends on the last Sunday in October at 03:00 o'clock in the morning. Within the EU all timezones change the clock at the same time.

Within most of the United States of America daylight saving time starts at 02:00 o'clock in the morning on the first Sunday in April. It ends at 02:00 o'clock in the morning on the last Sunday in October.

SimTalk

setDaylightSavingTime [SimTalk]

See also

Month [model settings]

**Week [preferences]**

**Week [preferences]**

Type in the week at which the time change takes place in new simulation models . For the default setting -1 daylight saving time starts on the last Sunday of the month you entered under Month .

Type in a number between 1 and 4 . Week 1 is the first week including the Day you set, week 4 is the last week of the month.

<!-- image -->

Within the European Union daylight saving time starts at 02:00 o'clock GMT on the last Sunday in March. It ends on the last Sunday in October at 03:00 o'clock in the morning. Within the EU all timezones change the clock at the same time.

Within most of the United States of America daylight saving time starts at 02:00 o'clock in the morning on the first Sunday in April. It ends at 02:00 o'clock in the morning on the last Sunday in October.

SimTalk

setDaylightSavingTime [SimTalk]

See also

Week [model settings]

Month [preferences]

**Day [preferences]**

Type in the day at which the time change takes place in new simulation models . For the U.S. and the EU, enter 0 for Sunday. 0 designates Sunday, 1 Monday, 2 Tuesday, 3 Wednesday, 4 Thursday, 5 Friday, and 6 Saturday.

<!-- image -->

Within the European Union daylight saving time starts at 02:00 o'clock GMT on the last Sunday in March. It ends on the last Sunday in October at 03:00 o'clock in the morning. Within the EU all timezones change the clock at the same time.

Within most of the United States of America daylight saving time starts at 02:00 o'clock in the morning on the first Sunday in April. It ends at 02:00 o'clock in the morning on the last Sunday in October.

SimTalk

setDaylightSavingTime [SimTalk]

See also

Day [model settings]

**Hour [preferences]**

Type in the hour at which the time change takes place in new simulation models . Type in a number between 0 and 23 . For the EU, enter 2 for 02:00 o'clock in the morning.

<!-- image -->

Within the European Union daylight saving time starts at 02:00 o'clock GMT on the last Sunday in March. It ends on the last Sunday in October at 03:00 o'clock in the morning. Within the EU all timezones change the clock at the same time.

Within most of the United States of America daylight saving time starts at 02:00 o'clock in the morning on the first Sunday in April. It ends at 02:00 o'clock in the morning on the last Sunday in October.

SimTalk

setDaylightSavingTime [SimTalk]

See also

Hour [model settings]

User Interface Tab

User Interface

Select settings for the user-interface of Plant Simulation on the tab User Interface .

Theming

Confirm Deleting Objects [preferences]

Console Filter

Confirm Deleting Objects [preferences]

Display Down-list Boxes in the SimTalk Language of the Model

Use Tab Page Icons in Object Dialogs

**Transparent Dialogs**

**Theming**

###### Theming

Sets the Theming for the Plant Simulation graphical user interface in your simulation models.

<!-- image -->

- Select System Setting to use the same color scheme that Windows uses on your computer.
- Select Light Theme to use black text, icons and GUI items on a white background.
- Select Dark Theme to use white text, icons and GUI items on a black background.

The Theming also affects the Background Color of the 3D window, and the Background Color and Font Color of cells in list objects.

<!-- image -->

###### Confirm Deleting Objects [preferences]

To open a dialog prompting you to confirm, when you delete objects or user-defined attributes in your simulation model with the Delete key or the command Delete on the context menu, select this check box.

<!-- image -->

It is especially useful to deactivate this feature when you are cleaning up a large model.

**Note**

Plant Simulation deletes Connectors connected with a material flow object without prompting you to confirm when you delete the material flow object!

###### Console Filter

To record Debug information and internal program messages in the Console in your simulation model, select the check box.

<!-- image -->

Plant Simulation then also counts all of the built-in objects, which are contained in the entire model, i.e., in the Class Library and in all Frames .

It does not count these objects: Lists and Tables , Methods , Variables , MUs , and Connectors .

You might want to know this number if you are working with a Plant Simulation Standard License which is limited to 4000 objects.

**Note**

To show the console filters on the context menu of the Console , you can also click the right mouse button. The first three filters are always activate. Select Clear to delete the contents of the Console window.

<!-- image -->

The topic Console describes the console filters in detail.

**SimTalk**

**setConsoleFilter [SimTalk]**

numOfLimitedObjects [SimTalk]

See also

**Console**

Specifying Start Options , -logfile file name Specifying Start Options , -NoWarning

###### Display Down-list Boxes in the SimTalk Language of the Model

To show the contents of drop-down list boxes in the SimTalk language in your simulation model, select this check box. Then Plant Simulation shows the items in the drop-down list boxes of the dialogs in the language, which will be used when getting the attribute belonging to the drop-down list box with SimTalk commands.

<!-- image -->

<!-- image -->

Let's say that you selected German as the Model Language , then Plant Simulation shows the items in the drop-down list boxes in German . If you select any other of the available model languages, Plant Simulation shows the items in the drop-down list boxes in English .

Let's say that you selected Japanese as the model language, then Plant Simulation reads the attributes belonging to the items in the drop-down list boxes as English strings.

Clear the check box to show the contents of drop-down list boxes in the language of the graphical user interface of Plant Simulation .

Use Tab Page Icons in Object Dialogs

To show tab page icons on the tabs of the object dialogs instead of the spelled-out title on the tab itself, select this check box.

<!-- image -->

This setting shows all tabs in the dialog, allowing you to click one of the tabs instead of having to scroll to the right to the tab you need if the dialog shows more tabs than fit the width of the dialog. When you click on a tab, Plant Simulation also shows its tab title.

Turning Use Tab Page Icons in Object Dialogs on or off takes effect immediately.

**Note**

Not all tabs of all objects provide tab page icons .

<!-- image -->

The Tab Page Icons of the individual tabs look like this:

<!-- image -->

<!-- image -->

**See also**

**Scroll to Tabs**

**Transparent Dialogs**

###### Transparent Dialogs

To make dialogs, which are open in the foreground, transparent, select the check box.

<!-- image -->

Dialogs and windows, which open behind them, will then be visible, and it will thus be easier to select them.

Then, type in a percentage for the Window Coverage and for the Transparency Level .

**Window Coverage**

Type in the value of the percentage of a window that has to be covered by a dialog located in front of it, so that the dialog, which covers the window, will become transparent.

**Transparency Level**

Type in a value for the transparency level of the covering dialog. 0 percent stands for opaque, 100 percent for almost totally transparent.

##### Editor Tab

###### Editor [preferences]

Select the global settings that determine how Plant Simulation formats and shows SimTalk source code in all Method objects on the tab Editor .

**Note**

For each individual instances of the Method you can also select local settings on the Tools ribbon tab of that Method .

**Editor [preferences]**

<!-- image -->

**See also**

**Method [object]**

###### Syntax-controlled Indentation [preferences]

To indent the source code you type according to the SimTalk syntax when starting a new line of code, select this check box.

<!-- image -->

<!-- image -->

When it is active, Plant Simulation automatically indents the cursor when starting a new line of code according to the delimiting keywords. Plant Simulation indents, for example, the text between if and end , making it easier to follow the logic behind the source code.

The Method Editor aligns the source code to the previous line of code.

Instead, you can also click the button Syntax Indentation on the Tools ribbon tab of the active Method .

See also

Syntax-controlled Indentation [Tools ribbon]

###### Highlight Current Line [preferences]

To highlight the current line of your source code in the Method Editor , select this check box.

<!-- image -->

Instead, you can also click View &gt; Highlight Current Line on the Tools ribbon tab of an individual Method .

**See also**

Highlight Current Line [source code]

**Show Line Numbers [preferences]**

###### Show Line Numbers [preferences]

To show the line number in front of the line of source code in the Method Editor , select this check box.

<!-- image -->

Instead, you can also click the button Show Line Numbers on the Tools ribbon tab of the active Method .

**See also**

Show Line Numbers [Tools ribbon]

###### Show Completion Tooltip [preferences]

To show a tooltip with the name of the object or the attribute or the method, when the command Auto Complete reaches a point from which on the name is unique, select this check box.

<!-- image -->

This way you can press Ctrl+Spacebar without having to type in too many letters.

Instead, you can also click the button Show Completion Tooltip on the Tools ribbon tab of the active Method .

See also

Show Completion Tooltip [command]

Auto Complete

**Show Outlining [preferences]**

###### Show Outlining [preferences]

To show the outlining of a sequence of source code lines, such as control and loop structures, in the Method Editor as an expansible or a collapsible structure, select this check box.

<!-- image -->

To expand an outline, click the button showing + , to collapse it click the button showing -.

<!-- image -->

Instead, you can also click the button Toggle Outline on the Tools ribbon tab of an individual Method .

**See also**

Show Outlining [Method]

###### Match Whole Word Only [preferences]

To find whole words only in your source code, select this check box. Clear the check box to also find parts of words in the source code.

###### Match Case [preferences]

To match the case of the expression you entered and for which you are searching, select this check box. To find the expression regardless of lower-casing or upper-casing, clear the check box.

**Match Case [preferences]**

###### Search for Regular Expressions

To also find regular expressions, select this check box. This means that you can use wild cards in the term you want to find.

You can, for example, use the period character . as a wild card for any character. If the editor searches for a.b , it will find all strings consisting of a sequence of the character a , any character, and the character b .

Compare regex\_search [SimTalk] for additional examples.

See also

Regular Expressions

Regular Expression [Find]

**Restart Search at End**

###### Restart Search at End

To continue searching at the beginning of the source code, after the search reaches the end of the text, select this check box.

<!-- image -->

###### Tab Size

Type in the tab size in character widths of a non-proportional font. This is the distance from tab stop to tab stop in the source code.

<!-- image -->

The commands Decrease Indent and Increase Indent on the Edit ribbon tab of the Method use this setting when moving your source code by one tab size.

**Font [preferences]**

###### Font [preferences]

Select the font size which the Method Editor displays the source code, which you type into a Method in the Consolas font. The Method Editor and the Method Debugger use the font Consolas in different fixed sizes between 6 and 72 points.

<!-- image -->

Consolas looks like this:

To increase or decrease the font size, hold down Ctrl and roll the mouse wheel forward and backward in the Method Editor or the Method Debugger window. When you change the font size with the mouse wheel, Plant Simulation saves this as the new preference and uses it when you start Plant Simulation the next time. Plant Simulation uses the changed font size in all open Method windows, not just in the one in which you rolled the mouse wheel.

Instead of rolling the mouse wheel, you can also use these key combinations:

Ctrl plus + increases the font size

Ctrl plus 0 resets the font size to the standard size of 10 points

Ctrl plus -decreases the font size

To apply Bold Face to the selected font size of the source code of the Methods , select the check box.

**Template Directory**

###### Template Directory

Click the folder button and navigate to the folder in which you store the templates for the source code of your Methods .

<!-- image -->

You can then select one of the templates in the Method object by clicking Select Template on the Edit ribbon tab and thus load it into the Method you are programming.

The text box shows the path to the folder in which you store the templates for the source code of your Methods .

You can also accept the default folder Templates .

##### 2D Tab

###### 2D [preferences]

Select the default settings that determine how new simulation models shows the objects which you insert into it on the tab 2D .

**Note**

The settings on the tab 2D only apply to models you create in 2D Only and in 2D and 3D.

<!-- image -->

**See also**

**2D [model settings]**

###### Show Object Names [preferences]

To show the names of the objects below their icons in the window of new simulation models , select this check box.

<!-- image -->

<!-- image -->

To show or hide them, you can also click the button Show Object Names on the View ribbon tab of the Frame in a 2D Only model .

SimTalk

ShowObjectNames [SimTalk]

See also

Show Object Names [model settings]

Name [general description]

###### Show MU Names [preferences]

To show the names of the parts ( MUs ) in new simulation models , select this check box.

This only works, when you also select Show Object Names [preferences] .

This prevents your simulation model from looking cluttered.

<!-- image -->

To show or hide them, you can also click the button Options &gt; Show MU Names [View ribbon] - 2D on the View ribbon tab of the Frame in a 2D Only model .

See also

Show MU Names [model settings]

###### Show Object Labels [preferences]

To show the labels , which you specified for the objects, below their icons in the window of new simulation models , select this check box.

<!-- image -->

If you also selected to Show Object Names [preferences] , Plant Simulation shows the labels below the names.

<!-- image -->

To show or hide them, you can also click the button Options &gt; Show Object Labels on the View ribbon tab of the Frame in a 2D Only model .

SimTalk

ShowObjectLabels [SimTalk]

See also

Show Object Labels [model settings]

Label [general description]

###### Show Predecessors [preferences]

To show the number of an incoming connection for each material flow connection in the window of new simulation models , select this check box. Plant Simulation only shows the predecessors in the Frame window when you also select Show connections .

The predecessor is the object that is connected to the selected object with a Connector and that precedes it in the sequence of stations in the simulation model.

For the first connection from another object to the current object, the Connector shows &gt; 1 , denoting that this is the first predecessor. If the object has more than one predecessor, Plant Simulation numbers the predecessors in the order you connected them, &gt; 2 for the second, &gt; 3 for the third, etc.

<!-- image -->

To show or hide them, you can also click the button Options &gt; Show Predecessors on the View ribbon tab of the Frame in a 2D Only model .

3D shows the predecessors and the successors of an object in a Tooltip when you drag the mouse over the respective Connector .

<!-- image -->

**SimTalk**

PredInterface [SimTalk]

See also Show Predecessors [model settings] Show Connections [preferences]

###### Show Successors [preferences]

To show the number of an outgoing connection for each material flow connection in the window of new simulation models , select this check box. Plant Simulation only shows the successors in the Frame window when you also select Show connections .

<!-- image -->

The successor is the object that is connected to the selected object with a Connector and that succeeds it in the sequence of stations in the model.

For the first connection from the current object to another object, the Connector shows 1 &gt; , denoting that this is the first successor. If the object has more than one successor, Plant Simulation numbers the successors in the order you connected them, 2 &gt; for the second, 3 &gt; for the third, etc.

<!-- image -->

To show or hide them, you can also click the button Options &gt; Show Successors on the View ribbon tab of the Frame in a 2D Only model .

3D shows the predecessors and the successors of an object in a Tooltip when you drag the mouse over the respective Connector .

<!-- image -->

**SimTalk**

SuccInterface [SimTalk]

See also Show Predecessors [model settings] Show Connections [preferences]

###### Show Display Panels [preferences]

To show the display panels , which you defined for the objects in a 2D Only model , in the window of new simulation models , select this check box.

<!-- image -->

To show or hide them, you can also click the button Options &gt; Show Display Panels on the View ribbon tab of the Frame in a 2D Only model .

SimTalk

ShowDisplayPanels [SimTalk]

See also

Show Display Panels [model settings]

Display Panel [object]

###### Show Connections [preferences]

To show connections, i.e., the Connectors between objects in the window of new simulation models , select this check box. Plant Simulation shows the direction of the connection with an arrow head in the middle of the Connector .

<!-- image -->

The commands Show Predecessors and Show Successors only work, when you also select Show connections .

<!-- image -->

To show or hide them, you can also click the button Show Connections on the View ribbon tab of the Frame in a 2D Only model .

See also

Show Connections [model settings]

###### Show Grid [preferences]

To show the grid points in the Frames of new simulation models , select this check box. This feature is useful for automatically aligning objects while you insert them.

<!-- image -->

Type the spacing of the grid intervals on the x-axis and the y-axis into the text boxes below Frame Grid Spacing [preferences] .

You might want to select Show Object Borders [preferences] as well.

When the Grid is active, Plant Simulation places the objects which you insert onto grid points. You can then move the objects by grid units only. The reference point of the icon of the object determines where Plant Simulation places the object on the grid point. By default, the reference point of a material flow object is located in the center of the icon. When you place an object, Plant Simulation places the reference point onto the grid point nearest to the mouse pointer. You can move the reference point to any position of your choice in the Icon Editor .

Selecting Show grid after you placed objects has no effect on the alignment of the objects which you already placed. They remain at the position at which you inserted them.

To align the objects, which you already inserted, with the grid, click Align to Grid [icons 2D] on the Icons ribbon tab of the Frame . Plant Simulation then moves all selected objects, so that their reference points are aligned with the closest grid point.

<!-- image -->

<!-- image -->

To show or hide the grid points, you can also click the button Show Grid on the View ribbon tab of the Frame in a 2D Only model .

See also

Show Grid [model settings]

###### Show Object Borders [preferences]

To show the borders around the icons of the objects, which you inserted into the Frame in new simulation models , select this check box. This way you can see the full size of the icon. The size of the border depends on the size of the icon.

<!-- image -->

To show or hide them, you can also click the button Options &gt; Show Object Borders on the View ribbon tab of the Frame in a 2D Only model .

See also

Show Object Borders [model settings]

Set Icon Size

###### Show Comments [preferences]

To show objects of type Comment , which you inserted into your simulation model to provide additional information, in new simulation models , select this check box.

<!-- image -->

| On   | Off   |
|------|-------|

To show or hide them, you can also click the button Show Comments on the View ribbon tab of the Frame in a 2D Only model .

See also

Show Comments [model settings]

Comment [object]

**Ignore Transparent Area [preferences]**

###### Ignore Transparent Area [preferences]

To be able to select an object that moves under the transparent area of the icon of an object in front of it in new simulation models , select this check box.

<!-- image -->

**See also**

Ignore Transparent Area [model settings]

###### Frame Grid Spacing [preferences]

Type in the distance between the individual grid points from each other on the x-axis, i.e., the horizontal axis of the Frame in new simulation models . Type in the distance between the individual grid points from each other on the y-axis, i.e., the vertical axis of the Frame .

The grid points are the points at which the imaginary grid lines intersect.

<!-- image -->

**Note**

The default setting is 20 x 20 pixels.

See also

Frame Grid Spacing [model settings]

3D Tab

###### 3D [preferences]

Select general settings for 3D as such and settings for the 3D model on the tab 3D .

You can also select some of these settings for each scene in the individual scene windows. These settings will then override the general preferences.

You can:

- Select the Visualization settings :

Screen Coverage Threshold [preferences]

Grid Settings [3D]

- Select the Mouse Wheel Behavior .

**3D [preferences]**

- Select which OpenGL Version is going to be used for rendering the 3D scene.
- Select if you want to Create Optimized Graphics for Rendering [preferences] .

See also

3D [model settings]

###### Screen Coverage Threshold [preferences]

Type in the threshold value for showing or hiding objects in the scene windows of new simulation models , which are smaller than the value in pixels that you type in.

This setting is used for maximizing performance.

See also

Screen Coverage Threshold [model settings]

###### Create Optimized Graphics for Rendering [preferences]

Create an optimized version of the graphics for rendering them for new simulation models .

To let Plant Simulation create optimized versions of user-defined graphics for rendering in the background, select this check box.

**Note**

We recommend to find a balance between fast rendering and fast modeling. If this option is active, Plant Simulation continuously re-optimizes your graphics after modifications. While this can speed up rendering, it can also slow down Plant Simulation while you are modeling.

When the option is active, Plant Simulation optimizes graphics by running the Flatten Structure optimizer and with options to optimize as much as possible without losing details.

See also

Create Optimized Graphics for Rendering [model settings]

Grid Settings

Grid Settings [3D]

To open the dialog Grid Settings , click the button Grid Settings .

**Note**

This setting only applies for new models. Click Edit Grid and Base Plate Settings on the View ribbon tab of the 3D window to modify grid setting for the current simulation model.

**You can:**

- Select the Base Plate Material [preferences] on which the grid is placed in the scene window.
- Select the color of the central Axes Color [preferences] of the grid.
- Select settings for the Grid Lines [preferences] .
- Click Apply to apply and display your changes to the grid settings in the scene window.
- Click OK to apply your changes to the grid settings and close the dialog.
- Click Cancel to close the dialog without applying any of the settings you modified.

**See also**

Work with the Grid

<!-- image -->

**Base Plate Material [preferences]**

To select a different color for the base plate, click the arrow of the drop-down list Color .

<!-- image -->

You can select one of the predefined colors, or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation shows this color next to More Colors and uses it as the active color.

<!-- image -->

**Axes Color [preferences]**

To select a different color for the central axes of the grid, click the arrow of the drop-down list Color .

<!-- image -->

You can select one of the predefined colors ,or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation shows this color next to More Colors and uses it as the active color.

<!-- image -->

When you insert and move an object toward the borders of the grid, it automatically extends in that direction. The grid always expands or shrinks to show all objects in the scene.

**Grid Lines [preferences]**

**Grid Lines [preferences]**

Edit or remove existing grid lines, or add new ones in the group box Grid Lines .

<!-- image -->

Each row on the table designates a single grid line:

- Double-click in the cell Color and select the color of the grid line in the dialog Colors .

You can select one of the predefined colors, or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation shows this color next to More Colors and uses it as the active color.

- Enter a positive value into the cell Interval to set the spacing of the selected grid line.
- Select the check box in the cell Visible to make 3D show the respective grid line. Clear it to hide the grid line.
- Select the check box in the cell Select for Snapping to make an object, which you insert, snap to the grid line. Clear it to not make the object snap to that grid line.

When you insert an object, the Snap to feature places the object at the snapping point closest to the point where you position the mouse and click the left mouse button.

- When you align an object, the Snap to feature places the object at the alignment point which is located closes to the point at which you position the mouse and at which you click the left mouse button.
- When you move an object with the mouse, the Snap to feature places the object closest to the snapping point to which you dragged the object and released the mouse button.
- To add a new grid line, click . Then, enter the settings described above.
- To delete the selected grid line, select it in the list field and click

<!-- image -->

<!-- image -->

.

You can also select these settings for each Frame in 3D by clicking Edit Grid and Base Plate Settings on the View ribbon tab.

**Mouse Wheel Behavior**

###### Mouse Wheel Behavior

Select the mouse wheel behavior , i.e., what Plant Simulation moves when you roll the mouse wheel up or down in the scene.

<!-- image -->

- Move Camera moves the camera away from you when roll the mouse wheel down. When you roll the mouse wheel up, 3D moves the camera toward you.
- Move Scene moves the scene as such toward you when you roll the mouse wheel down. When you roll the mouse wheel up, it moves the scene away from you. This is the default setting.

**See also**

Manipulate the Scene with the Mouse

###### OpenGL Version

Select the OpenGL version you would like to use for rendering the 3D scenes in your simulation models.

<!-- image -->

If 3D is running while the dialog Preferences is open, the drop-down list only shows the OpenGL versions that the graphics card driver of the graphics card of your computer supports.

You can check out the features of the individual OpenGL versions on the Internet.

**Note**

We recommend to use the highest setting available. Sometimes you might have to choose a lower level though to get rid of display bugs in the driver of your graphics card. Be aware that if you go below version 3.1, you might suffer a significant decrease in performance.

**Background Color [3D]**

###### Background Color [3D]

Sets the Background Color of the 3D Viewer window .

<!-- image -->

- Select Auto to use the color scheme in the 3D Viewer window that you selected for the Theming under Preferences &gt; User Interface .
- Select White to use a completely white background.
- Select Light to use black text, icons and GUI items on a white background.
- Select Dark to use white text, icons and GUI items on a dark background.

<!-- image -->

**See also**

**Theming**

##### License Tab

License

Select the license type you purchased, and select how Plant Simulation gets this license on the tab License .

Plant Simulation supports a license file or three redundant license servers for retrieving your license. Redundant license servers significantly increase the stability and the availability of the licenses.

When you are using a license server triad, two out of the three redundant license servers always have to be reachable, meaning that one of three servers can fail.

<!-- image -->

See also Use a Floating License Use a Node-Locked License Use a Computer-Dependent/Dongle ID License Plant Simulation License Types Start Plant Simulation with Different Kinds of Licenses Plant Simulation X

**Use Cloud Licensing**

###### Use Cloud Licensing

To use a license provided and managed by Siemens in the Cloud for Plant Simulation X , select this check box. Clear the check box to use a perpetual license from a license server.

**Note**

When you first started Plant Simulation X and selected to use a cloud license, the check box Use Cloud Licensing was automatically activated.

<!-- image -->

**See also**

Plant Simulation X

Start Plant Simulation X

###### Subscription

Select Subscription to use a subscription to Plant Simulation . Clear Subscription if you opted to participate in one of our license subscription plans but nevertheless want to use a perpetual license.

**Note**

Plant Simulation only shows the check box Subscription if you purchased a subscription and if you activated it in the Siemens Software Center .

###### License Type

Select the type of license which you purchased and which you are using.

<!-- image -->

The license type determines which features of Plant Simulation you can or cannot use. You can override the setting you select here with the start option /L .

If you set the license type to Highest Available , Plant Simulation uses the first available license type in the following order:

- Professional
- Standard
- Foundation
- Application
- Runtime
- Research
- Educational
- Student

**Note**

If you purchased different license types, you have to explicitly specify the license type which you want to use.

**SimTalk**

licenseName [SimTalk]

See also

Start Plant Simulation with Different Kinds of Licenses

**Specifying Start Options Features of the Individual Licenses**

**License File**

###### License File

To acquire your license from a license file instead of from a license server, select this check box. Type in the path to and the name of your license file.

<!-- image -->

<!-- image -->

Instead, you can also click the button and navigate to the folder in which you stored your license file ( license.lic ) and select it in the dialog, which opens.

See also

Use a Node-Locked License

Licensing Plant Simulation

###### Server [license] - 1

To acquire your license from the license server whose name you type into the text box to the right, select this check box.

<!-- image -->

Type in the name of this license server. If you Use a License Server Triad , you have to type in the name of the first of three redundant license servers. In this case two out of the three redundant license servers always have to be reachable, meaning that one server can fail.

Port

Type in the port number for contacting this license server. For our default environment the port number is 29000 .

If you Use a License Server Triad , type in the port number for contacting this license server.

<!-- image -->

**See also**

Use Redundant License Servers

Licensing Plant Simulation

**Server [license] - 2**

###### Server [license] - 2

To acquire your license from the license server whose name you type into the text box to the right, select this check box.

<!-- image -->

Type in the name of this license server. If you Use a License Server Triad , you have to type in the name of the second of three redundant license servers. In this case two out of the three redundant license servers always have to be reachable, meaning that one server can fail.

Port

Type in the port number for contacting this license server. For our default environment the port number is 29000 .

If you Use a License Server Triad , type in the port number for contacting this license server.

<!-- image -->

**See also**

Use Redundant License Servers

Licensing Plant Simulation

###### Server [license] - 3

To acquire your license from the license server whose name you type into the text box to the right, select this check box.

<!-- image -->

Type in the name of this license server. If you Use a License Server Triad , you have to type in the name of the third of three redundant license servers. In this case two out of the three redundant license servers always have to be reachable, meaning that one server can fail.

Port

Type in the port number for contacting this license server. For our default environment the port number is 29000 .

If you Use a License Server Triad , type in the port number for contacting this license server.

<!-- image -->

**See also**

Use Redundant License Servers

Licensing Plant Simulation

**Use a License Server Triad**

###### Use a License Server Triad

To acquire your license from any one of three redundant license servers, select this check box.

<!-- image -->

This only works, if you are running the license server as a license server triad. Two out of the three redundant license servers always have to be reachable, meaning that one server can fail.

<!-- image -->

**See also**

Use Redundant License Servers

Licensing Plant Simulation

###### Query Host IDs

To query the host IDs of your computer, click this button.

<!-- image -->

Plant Simulation then shows the host IDs of your computer in the text box to the right.

<!-- image -->

**Host IDs**

###### Host IDs

After you clicked Query Host IDs , Plant Simulation shows the host IDs of your computer in the box.

<!-- image -->

You can use any one of these host IDs for retrieving your license. You can copy the information from the text box and paste it into the respective field on the website.

<!-- image -->

<!-- image -->

Help [license]

To open help about licensing Plant Simulation , click this button.

See also

Licensing Plant Simulation

Data Privacy

Data Privacy

Decide and set if you want to participate in the Digital Product Experience and the Product Excellence Program on the respective tabs.

See also

Data Privacy 1

Data Privacy 2

###### Data Privacy 1

Set if you want to participate in the Digital Product Experience or not on the tab Data Privacy 1 .

<!-- image -->

**Registry Entry**

If the registry entry does not exist, create a new DWORD value under

Computer\HKEY\_CURRENT\_USER\Software\Siemens\Tecnomatix Plant Simulation 2504 and name it DigitalProductExperienceFeedback .

Type 0 for Decline or 1 for Agree .

<!-- image -->

**See also**

**Setting Default Values in the Windows Registry (Administrator)**

###### Data Privacy 2

Set if you want to participate in the Product Excellence Program or not on the tab Data Privacy 2 .

<!-- image -->

**Registry Entry**

If the registry entry does not exist, create a new DWORD value under

Computer\HKEY\_CURRENT\_USER\Software\Siemens\Tecnomatix Plant Simulation 2504 and name it ProductExcellenceProgramFeedback .

Type 0 for Decline or 1 for Agree .

<!-- image -->

**See also**

**Setting Default Values in the Windows Registry (Administrator)**

#### Help [Menu Item]

Help [on File menu]

Provides commands pertaining to get help for Plant Simulation .

<!-- image -->

- Contents [help]
- Using Online Help describes the different ways of using and searching in the help.
- Plant Simulation Community Forum
- Academic Community Forum
- GTAC Support Center
- Check for Update
- About Plant Simulation

**Contents [help]**

##### Contents [help]

Opens the website of the Plant Simulation Help on Support Center .

Using Online Help describes the different ways of using and searching in the help.

##### Plant Simulation Community Forum

Opens the website of the Plant Simulation Forum .

**Academic Community Forum**

##### Academic Community Forum

Opens the website of the Academic Forum .

##### GTAC Support Center

Opens the website of the Support Center for Plant Simulation .

**Check for Update**

##### Check for Update

Checks the website for a product update of Plant Simulation . You can then decide if you want to install it or not.

##### About Plant Simulation

Opens the dialog About Plant Simulation containing information about the version of Plant Simulation , the kind of license you purchased and copyrights.

Our technical support staff might ask you for your Sold to ID . You can click into the text box, copy the text, and paste it into an E-mail, etc.

<!-- image -->

**SimTalk**

createLicenseFile [SimTalk]

See also

Licensing Plant Simulation

#### Exit [Menu Item]

**Exit [Menu Item]**

##### Exit Application

Closes the open simulation model and exits Plant Simulation . The dialog shows the name of and the path to the model file in the first line.

<!-- image -->

<!-- image -->

- Click Yes to save the model.
- Click No to exit Plant Simulation without saving your changes.

**Note**

You can also define a Method with the name onCloseModel in any folder in the Class Library , including the Basis folder. This method is being executed when you close the model or when you exit the application. You can, for example, program clean-up tasks, delete temporary files, etc.

The method onCloseModel has to declare the boolean parameter onExitApplication . Plant Simulation sets this parameter to false when onCloseModel is called when you close the model. Plant Simulation sets this parameter to true when onCloseModel is called when you exit Plant Simulation .

You can also program several onCloseModel methods and place them into different folders. Plant Simulation then calls all existing onCloseModel method classes in the Class Library when you close the model or exit Plant Simulation .

**SimTalk**

exitApplication [SimTalk]

See also

Exiting if Plant Simulation Locks Up

##### Exiting if Plant Simulation Locks Up

When Plant Simulation locks up during a simulation run, press Ctrl+Shift+Alt for 5 seconds to open the Method Debugger in which you can debug the faulty method.

- If Plant Simulation is stuck in an endless loop and is running in the foreground, hold down the Ctrl+Alt+left Shift keys for several seconds to open the Debugger while a Method is being executed.
- If Plant Simulation is stuck in an endless loop and is not running in the foreground, hold down the Ctrl+Alt+right Shift keys for several seconds to open the Debugger while a Method is being executed.

Plant Simulation shows a dialog asking if it should terminate and create an emergency copy of your simulation model.

When you click Yes , Plant Simulation safes the model under the name Plant Simulation.your login name to the Temp folder on your hard disk. When you restart the program, Plant Simulation opens a dialog asking whether to open this model file.

**Note**

We recommend to not continue working with the crashed simulation model, but to go back to the last regularly saved version.

As opposed to clicking End Task in the Windows Task Manager , this emergency copy contains the last unsaved changes you made.

SimTalk

exitApplication [SimTalk]

See also

Method Debugger

#### Search [on File menu]

Finds the expression that you type into the text box with the looking glass.

<!-- image -->

Plant Simulation then searches for this expression as you type . To terminate the Search click the X in the text box.

<!-- image -->

#### Recent Files

Shows the eight models you worked with most recently. Select the model you want to open. Plant Simulation shows a message asking if you would like to save the currently open model or not.

<!-- image -->

Instead, you can also click Recent Models on the Start Page .

<!-- image -->

**Home Ribbon Tab**

