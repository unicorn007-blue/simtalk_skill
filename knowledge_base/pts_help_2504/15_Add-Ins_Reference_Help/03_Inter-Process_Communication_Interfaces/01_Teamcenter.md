### Teamcenter

#### Teamcenter [object]

The Teamcenter Interface provides the interface between Plant Simulation and Teamcenter for accessing and exchanging data. It provides the commands required for Plant Simulation to connect to Teamcenter , to receive Teamcenter data in Plant Simulation , to parse the information received, and make it useful for Plant Simulation .

Icon

<!-- image -->

<!-- image -->

**Description**

The Teamcenter Interface imports the BOM , BOP , and BoE , places their ItemRevisions in corresponding tables, and the JT data in a folder. That information can then later be used to create a simulation model reflecting the BOM , BOP , and BoE . The Plant Simulation Professional license covers only the Plant Simulation part of the Teamcenter Integration , you still need a separate license for Teamcenter to generate and maintain this data.

**Note**

The compatible versions of Teamcenter and Active Workspace are listed in the Excel file with the Teamcenter Interoperability Matrix (sheet Tecnomatix ) on https://support.sw.siemens.com/en-US/ product/282219420/download/PL20200617155641511

**Note**

We changed the behavior of the Teamcenter Interface .

With Plant Simulation 2201.0003 the Teamcenter Interface no longer supports Active Workspace version 4 and older. It now does support version 6 though.

As long as you do not use Active Workspace , this does not affect the Teamcenter Interface .

In addition, you need the Microsoft Edge WebView2 Runtime . If you did not install the Microsoft Edge WebView2 Runtime yet, you can download it here https://developer.microsoft.com/microsoft-edge/ webview2/ and install it.

**Note**

The Teamcenter Interface supports authentication to Teamcenter 13.3 and higher with Single-Sign-On ( SSO ) in the default mode of the Teamcenter Security Services .

If you are using the Teamcenter Interface with Teamcenter 13.2 or lower, and want to authenticate to Teamcenter with SSO , you have to install the Teamcenter Security Services 13.3 in compatibility mode. For more information consult https://support.sw.siemens.com .

**Note**

To use the Plant Simulation -Teamcenter-Interface the .NET Framework 4.7.2 needs to be installed on your computer. In addition, the matching Teamcenter client or the Teamcenter Client Communication System (TCCS) needs to be installed on your computer. You find the current TCCS setup in the Siemens Support Center under https://support.sw.siemens.com/product/282219420/downloads .

**Note**

To be able to use the Teamcenter Interface , you have to install the Plant Simulation Integration software package that matches your Teamcenter version on the Teamcenter server. You find the current software packages in the Siemens Support Center under https://support.sw.siemens.com/product/ 282219420/downloads . To install the software package, use the Teamcenter Environment Manager or the Teamcenter Deployment Center .

**Note**

You do not need a Professional License to save you models in Teamcenter .

You can also define the configuration of the installation of the Teamcenter FMS Client Cache (FCC) using environment variables, such as FMS\_HOME, in a file that only applies to the Plant Simulation process , instead of setting system-wide environment variables.

If needed you have to create this file yourself and name it settings.ini . Type in the environment variables into the category [TeamcenterEnvironment]. The contents of the file might look like this:

[TeamcenterEnvironment] FMS_HOME=C:\Program Files\Siemens\Teamcenter11\tccs

JAVA_HOME=C:\Program Files\Java\jre8

Save the file to this folder: %public%\Siemens\Tecnomatix Plant Simulation

To show a tooltip with information about the Teamcenter Interface , hover with the mouse over it.

To change the length of the graphic and the anchor points of the Teamcenter Interface , click Show

Manipulators on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

Add the Object to the Simulation Model

To add the Teamcenter Interface to the Class Library , click Manage Class Library &gt; Basic Objects &gt; InformationFlow &gt; Teamcenter on the Home ribbon tab.

<!-- image -->

<!-- image -->

<!-- image -->

You can also add the TeamcenterWizard to your simulation model in the dialog Manage Class Library .

<!-- image -->

Help is integrated into the object itself. Select Help &gt; Help on Object to show it.

<!-- image -->

You can use the commands on the File menu to save your models to Teamcenter , to check these out and edit them, and to check in the updated version back to Teamcenter .

<!-- image -->

- Open from Teamcenter
- Add to Teamcenter
- Check In [Teamcenter]
- Check Out [Teamcenter]
- Cancel Checkout

The Teamcenter Interface also supports logging in to Teamcenter via Single-Sign-On (SSO). To do so, you have to select the TCCS environment in which the settings of the SSO-Server are configured. When logging in via SSO, you do not have to enter the Username and the Password .

We support logging in via SSO in the login dialog to Teamcenter as well as in the dialog of the Plant Simulation object Teamcenter .

**Teamcenter [object]**

See also Secure File Mode Exchange Data Between Teamcenter and Plant Simulation Browse the Teamcenter Database with Active Workspace Import a Study from Teamcenter with the Study Manager File &gt; Teamcenter [on File menu] TeamcenterWizard

#### Exchange Data Between Teamcenter and Plant Simulation

Saving simulation models in Teamcenter is especially helpful for large companies. It enables the common storage, management, and versioning of the models in projects with specific access permissions. It also enables to use the same system for planning and administering process data, resources, and products.

In addition, Plant Simulation and other simulation tools can access the data stored in Teamcenter, enrich them with simulation results, and show them in the simulation report. Other users, managers, etc. can also view the data from Teamcenter.

It also enables to pass models and sub-models on to your colleagues and to develop them in groups and to integrate and manage models from suppliers.

If a newer version of the checked in model is located in the Teamcenter database than on your computer, the Teamcenter Interface downloads this newer version so that you can continue working with it.

The figure below gives a general overview about data exchange between Teamcenter and Plant Simulation . It shows Teamcenter processes green and Plant Simulation processes orange.

<!-- image -->

Teamcenter provides product data, process data, and working area data. Your Teamcenter colleague assembles this data via the Collaboration Context in Teamcenter . He then exports a snapshot via the application interface, which you can then select in Plant Simulation under Application Interface . The exported data is transformed using the defined Style Sheet to a simplified XML format, which you can then import into a Plant Simulation table. You can then use this data, together with the JT files that were exported from Teamcenter , as input data for your simulation models in Plant Simulation .

The Plant Simulation installation package, which you downloaded, contains the folder Teamcenter Interface . Your Teamcenter administrator has to install the files in the folder PlantSimulationIntegration\_15.0\_##.#\_wntx64 with the Teamcenter Environmental Manager or with the Deployment Center (DC). This folder contains the data types for the Plant Simulation Integration , such as the application interface, etc.

**Note**

The Software Package, which we deliver from Plant Simulation version 15 on, contains a database change, which is not compatible with the database schema up until Plant Simulation version 14. When you update the database, the data specific to Plant Simulation , namely Availability , MTTR , and Plant Sim Class , is lost. Other data is not affected.

If you want to keep the data specific to Plant Simulation , proceed as follows:

Open the affected structure in the application Manufacturing Process Planner , select the root node of the structure and call the command Export to PLMXML . Select the Transfer Mode &gt; PlantSimulationExport . You have to execute these steps for all structures with Plant Simulation -specific data. Then, update the Teamcenter database . After updating, you can import the PLMXML files to restore your data.

**Note**

Caused by the database changes described above it is not possible to update the database schema from version 11 to version 12 and the Plant Simulation Software Package from version 14 to 15 in a single step. Update the Plant Simulation Software Package to version 15 first before updating the Teamcenter-database Schema to version 12.

#### Browse the Teamcenter Database with Active Workspace

Active Workspace is an innovative interface for Teamcenter that provides you with a streamlined and intuitive product lifecycle management (PLM) user experience. It literally puts PLM at your fingertips. Active Workspace increases your productivity by allowing you to find what you need faster, allowing you to see the big picture, so you can make smarter decisions and providing you with seamless access to PLM when and where you need it.

**Note**

We changed the behavior of the Teamcenter Interface .

With Plant Simulation 2201.0003 the Teamcenter Interface no longer supports Active Workspace version 4 and older. It now does support version 6 though.

As long as you do not use Active Workspace , this does not affect the Teamcenter Interface .

In addition, you need the Microsoft Edge WebView2 Runtime . If you did not install the Microsoft Edge WebView2 Runtime yet, you can download it here https://developer.microsoft.com/microsoft-edge/ webview2/ and install it.

The Teamcenter Interface in Plant Simulation mainly uses the search function for searching for Plant Simulation simulation models, which are saved in Teamcenter. To use Active Workspace , you have to have access to a Teamcenter-Server with Active Workspace .

In previous versions of the Teamcenter Interface the simulation models from Teamcenter were shown in a flat hierarchy. Then you had to select your model in the dialog Open Model from Teamcenter and click Open .

<!-- image -->

With Active Workspace you can set the folder and the storage location of the models. When you log in to Teamcenter for the first time, you can set if you would like to use Active Workspace .

**Note**

This only works if the Active Workspace URL is set correctly under Preference &gt; ActiveWorkspaceHosting.PLANT.URL in the Teamcenter database. If this preference is not defined, Plant Simulation tries to use the general Preference &gt; ActiveWorkspaceHosting.URL as the fallback.

You have to enter the password once, even if your password is already saved in the object Teamcenter .

<!-- image -->

Select the Application Interface in the dialog Application Interface .

<!-- image -->

Then select the model in the Active Workspace window.

<!-- image -->

#### Import a Study from Teamcenter with the Study Manager

The Study Manager is a component of the Teamcenter Manufaturing Access extension. It enables you to search for a collaboration context and to show the studies of the collaboration context.

You can change the Study Elements of an existing study or create a new study and define its Study Elements . Study Elements are the sub-structures of the selected Collaboration Context .

**Note**

The settings Application Interface via Active Workspace and Study only work if the Active Workspace URL is set correctly in the Teamcenter database under Preference &gt; ActiveWorkspaceHosting.PLANT.URL .

The setting Study in addition requires that the Teamcenter Manufacturing Access extension is installed for the specified Active Workspace-Server .

To import a study from Teamcenter with the Study Manager :

- Select the Import Mode &gt; Study in the Teamcenter Interface .
- When you are importing data from Teamcenter , Plant Simulation opens the dialog of the Study Manager .

<!-- image -->

**Note**

You have to enter your password once when logging in to Teamcenter , even if the password is already saved in the Teamcenter Interface .

Search for and select the Collaboration Context from which you want to import a study in the left pane of the dialog.

The right pane shows the Studies of the selected collaboration context.

<!-- image -->

- Click Edit Study Scope to edit the scope of the study.

<!-- image -->

- Click Create Study to create a new study and to define the elements of the study.
- Click Open to open the selected study in Plant Simulation and to import its data.

See also

Import Mode [drop-down list]

#### Secure File Mode

The Teamcenter Interface supports the Secure File Mode . When it is active, files downloaded from Teamcenter are only saved on your hard drive as long as they are used.

You can activate Secure File Mode in the Teamcenter database by entering the value Secure into the Teamcenter Preference &gt; PSI2PlantSimulation\_FileMode .

When you download a model file in this mode from Teamcenter , the model will be stored in a temporary folder and will be deleted after loading the file in Plant Simulation .

You cannot save the model as a file, you have to check your changes to the model in to the Teamcenter database . The temporary folder will be closed when you close the model.

When importing data from Teamcenter in Secure File Mode , the PLMXML file will be closed after it has been imported all the way.

Downloaded JT files will be assigned a new file name that does not allow identifying the original file name. As a rule the JT files will be deleted after the model was generated by the TeamcenterWizard , at the latest when closing the model.

#### Dialog Box of the Teamcenter Interface

Dialog Box of the Teamcenter Interface

Double-click the icon of the Teamcenter Interface to open its dialog box.

**Edit Simulation Properties**

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

###### Tab Connection

##### Tab Connection

The tab Connection provides the settings listed in the table of contents to the left.

They apply to importing data from Teamcenter and to exporting data to Teamcenter .

<!-- image -->

###### Server [text box]

Type in the name of the Server URL of the host computer on which Teamcenter runs.

The default server URL is http://localhost:7001/tc . If environments are configured in the TCCS , you can also select an environment from the list of configured environments.

**Note**

The connection string that you enter depends on your Teamcenter provider, for example the IT department of the customer. Consult your Teamcenter provider for more information.

**Note**

If the connection with the server is established via HTTPS in encrypted mode, the respective certificate has to exist in the Windows Certificate Store . ( Control Panel &gt; Internet Options &gt; Content &gt; Certificates .)

**Note**

If you do not set the Server-URL or the User Name , i.e., do not enter anything into the text box, the object Teamcenter uses the settings specified for opening the model from Teamcenter or for checking the model in and out, provided these settings are set.

SimTalk

ServerURL [SimTalk]

See also

queryEnvironments [SimTalk]

###### Import Mode [drop-down list]

Select the Import Mode for retrieving data from Teamcenter .

<!-- image -->

- Application Interface from List enables you to select the application interface from a list.
- Application Interface via Active Workspace enables you to use Active Workspace to select the application interface.
- Study always uses the Study Manager to import data.

**Note**

The settings Application Interface via Active Workspace and Study only work if the Active Workspace URL is set correctly in the Teamcenter database under Preference &gt; ActiveWorkspaceHosting.PLANT.URL .

The setting Study in addition requires that the specified Active Workspace-Server supports the Study Manager , for example an Easy Plan-Server with the installed Teamcenter Manufacturing Access extension .

Click Apply or OK to reflect the changed settings on the Tab Import under Teamcenter object .

SimTalk

ImportMode [SimTalk]

See also

Browse the Teamcenter Database with Active Workspace

Import a Study from Teamcenter with the Study Manager

##### User Name [Teamcenter]

Type in the User Name with which you want to log in to the Teamcenter database. Plant Simulation saves the user name encrypted in the model file.

**Note**

If you do not enter your User Name here, you have to enter it in the Teamcenter login dialog when you log in to the Teamcenter database for the first time.

**Note**

If you do not set the Server-URL or the User Name , i.e., do not enter anything into the text box, the object Teamcenter uses the settings specified for opening the model from Teamcenter or for checking the model in and out, provided these settings exist.

SimTalk

UserName [SimTalk]

###### User Name [Teamcenter]

###### Password [Teamcenter]

Type the password with which you want to log in to Teamcenter . Plant Simulation encrypts the password and saves it in the model file.

If you are using the Teamcenter interface with Active Workspace , you have to enter the password once even if it is already saved in the object Teamcenter .

**Note**

If you do not specify the password here, you have to type it in the Teamcenter login dialog when you log in to the Teamcenter database for the first time.

SimTalk

setPassword [SimTalk] - Teamcenter

###### Group [Teamcenter]

Type in the name of the Group under which you want to log in to Teamcenter .

Leave the text box empty to log on under the default group.

**Note**

You can change your Group by clicking the icon of your user profile in the Active Workspace window .

SimTalk

Group [SimTalk] - Teamcenter

**Group [Teamcenter]**

Role [text box]

Type in the name of the Role with which you want to log in to Teamcenter .

Leave the text box empty to log on under the default role.

Note

You can change your Role by clicking the icon of your user profile in the Active Workspace window .

SimTalk

Role [SimTalk] - Teamcenter

Tab Import

Tab Import

The tab Import provides the settings listed in the table of contents to the left.

###### Application Interface [text box]

Click the ellipsis button and select the Application Interface to which the Sync belongs which you would like to import from Teamcenter .

<!-- image -->

If you want to select the Application Interface from a dialog when importing data, leave the text box empty. Compare Import .

**Note**

Plant Simulation only shows the settings Application Interface and Sync if you select the Import Mode &gt; Application Interface from List or Application Interface via Active Workspace .

**SimTalk**

ApplicationInterface [SimTalk]

Sync [SimTalk]

See also

Sync [text box]

###### Sync [text box]

Click the ellipsis button and select the Sync , which you would like to import from Teamcenter .

<!-- image -->

Leave the text box empty to select the Sync and the Application Interface from a dialog when importing data .

**Note**

If you specify the Sync , you also have to specify the Application Interface .

**Note**

Plant Simulation only shows the settings Application Interface and Sync if you select the Import Mode &gt; Application Interface from List or Application Interface via Active Workspace .

SimTalk

Sync [SimTalk]

ApplicationInterface [SimTalk]

Retrieve JT Files [check box]

To retrieve the respective JT files in addition to the PLMXML files from Teamcenter , select this check box.

You find the JT files in the folder you specified with the setting Directory .

SimTalk

RetrieveJTFiles [SimTalk]

###### Retrieve JT Files [check box]

###### Retrieve Kinematics Files [check box]

To retrieve the respective kinematics files in addition to the PLMXML files from Teamcenter , select this check box.

You find the kinematics files in the folder you specified with the setting Directory .

SimTalk

RetrieveKinematicsFiles [SimTalk]

**Directory [text box]**

###### Directory [text box]

Click the button and navigate to the Directory into which the PLMXML file and the JT files and kinematics files will be copied.

<!-- image -->

<!-- image -->

**SimTalk**

**Directory [SimTalk]**

<!-- image -->

Or type in the name of the Style Sheet which you want to use when copying data from Teamcenter .

The style sheet enables you to format the data of the exported PLMXML file in a way that the data relevant for the simulation can be arranged in a simple table structure.

This can then be imported into the Plant Simulation DataTable .

SimTalk

StyleSheet [SimTalk]

Table [text box] - Teamcenter

Click the ellipsis button and navigate to the folder in which the DataTable is located into which you want to import the PLMXML data. Or type in the name of the DataTable .

SimTalk

DataTable [SimTalk] - Teamcenter

###### Table [text box] - Teamcenter

###### Import [Teamcenter]

To log onto the Teamcenter database, click this button.

<!-- image -->

If you entered your User Name and your Password on the tab Connection , Plant Simulation uses this information to login. Otherwise Plant Simulation opens the dialog Teamcenter Login . Then enter your user name and your password for Teamcenter into the dialog that opens.

<!-- image -->

If you entered an Application Interface and a Sync , Plant Simulation uses this information to import data from Teamcenter . Otherwise Plant Simulation opens a dialog which shows all available application interfaces.

- If you are using Active Workspace , Plant Simulation opens a dialog, in which you can navigate to the Application Interface .

<!-- image -->

- If you are not using Active Workspace , Plant Simulation opens a dialog which shows all available Application Interfaces . Select one of them.

<!-- image -->

Double-click an entry in the list Application Interface to show the respective Sync .

Select a Sync that belongs to this Application Interface .

<!-- image -->

Click OK to retrieve the respective data from the Teamcenter database.

**Note**

If you only entered an Application Interface and no Sync , Plant Simulation only opens the dialog in which you can select the Sync .

Plant Simulation imports the data into the DataTable , which you entered as the Table . The table contains the data in a nested structure. To open the next level of data in a subtable, double-click an entry in the respective cell.

<!-- image -->

<!-- image -->

**SimTalk**

login [SimTalk] - Teamcenter queryApplicationInterfaces [SimTalk] querySyncs [SimTalk] retrieveData [SimTalk] setPassword [SimTalk] - Teamcenter Tab Export Tab Export The tab Export provides the settings listed in the table of contents to the left.

###### HtmlReport [Teamcenter]

Click the ellipsis button and select the HtmlReport which you would like to export to Teamcenter .

<!-- image -->

Or type in the name of the HtmlReport .

SimTalk

Report [SimTalk]

See also

HtmlReport [object]

###### Target Folder [text box]

Type in the Teamcenter Target Folder in which the Plant Simulation HtmlReport will be stored.

This folder has to be a subfolder of the Home folder of the user logged on to Teamcenter .

If you are using Active Workspace , you can click the button and select the target folder.

SimTalk

TargetFolder [SimTalk]

See also

HtmlReport [object]

**Target Folder [text box]**

Export [Teamcenter]

To log onto the Teamcenter database to Export a Plant Simulation HtmlReport to Teamcenter , click this button.

Then, enter your User Name and your Password for Teamcenter into the Teamcenter Login dialog that opens.

If you entered a User Name and a Password on the tab Connection , Plant Simulation does not open the login dialog but uses the login data which you entered.

SimTalk

exportReport [SimTalk]

login [SimTalk] - Teamcenter

See also

HtmlReport [object]

**Tab User-defined**

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

##### Navigate Menu

The commands are described under the Navigate Menu .

##### View Menu

View Menu

The View Menu provides commands to access its functions. Refresh [on View menu] Show Attributes and Methods [on View menu] SimTalk updateDialog [SimTalk] See also View Menu [general description]

##### Tools Menu

The commands are described under the Tools Menu .

##### Help Menu

The commands are described under the Help Menu .

**Methods of the Teamcenter Interface**

#### \_Methods of the Teamcenter Interface

The Teamcenter Interface provides:

- The methods listed in the table of contents to the left.
- The Methods of All Objects .

To view all of the methods , read-only attributes and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

An example of the Syntax line of the individual methods might look like this:

```simtalk
< Path >.openDialog([CallOpenControl:boolean:=false]) → boolean
```

- The expression &lt;Path&gt; designates the path of the object to which the method applies.
- The signature of the method, consisting of the identifier and the data type of the parameter, is listed in parentheses. The expression (Parameter:string) , for example, designates a parameter of data type string . Instead of a constant value, you can also use a variable of the required type or a method that returns the required data type.

**Note**

Make sure to enter the parentheses for expressions within parentheses (…). Not entering them may lead to unexpected results and open the Debugger .

Optional parameters are listed within brackets. The expression [,Parameter:boolean] , for example, means that you can, but do not have to enter the boolean parameter.

If a parameter has a default value, the signature shows the default value after the parameter.

If the method has a return value, the signature shows its data type after the arrow -&gt;.

##### exportReport [SimTalk]

exportReport [SimTalk]

Exports the specified Plant Simulation HtmlReport of the object designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.exportReport(Report:object, FolderName:string)

**Parameters**

- The parameter Report of data type object designates the report.
- The parameter FolderName of data type string designates the Teamcenter folder into which you want to save the Report . This folder has to be a subfolder of the Home folder of the user logged on to Teamcenter .

The method creates a dataset item in Teamcenter that contains the HTML page of the exported HtmlReport .

Plant Simulation sets the Name of the dataset to the Label or Name of the Report .

**Example**

Teamcenter.exportReport(MyReport,"MyReportFolder")

See also

HtmlReport [Teamcenter]

**login [SimTalk] - Teamcenter**

Establishes a connection of the object designated by &lt;Path&gt; with the Teamcenter database.

Type

Method

Syntax

```simtalk
< Path >.login([Username:string, Password:string, Group:string, Role:string]) → boolean
```

**Parameters**

- The optional parameter UserName of data type string designates the User Name .
- The optional parameter Password of data type string designates the Password .
- The optional parameter Group of data type string designates the Group .
- The optional parameter Role of data type string designates the Role .

**Return Value**

The return value has the data type boolean .

true if login was successful.

**Example**

Teamcenter.login("Engineer1", "MyPassword123", "Engineering", "Designer")

**See also**

Import [Teamcenter]

logout [SimTalk] - ODBC

User Name [Teamcenter]

Password [Teamcenter]

Group [Teamcenter]

Role [text box]

logout [SimTalk] - Teamcenter

Terminates the connection of the object designated by &lt;Path&gt; with the Teamcenter database.

Type

Method

Syntax

&lt; Path &gt;.logout

Example

Teamcenter.logout

See also

Import [Teamcenter]

login [SimTalk] - Teamcenter queryApplicationInterfaces [SimTalk]

Returns the available application interfaces of the object designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.queryApplicationInterfaces(ResultsTable:table)

Parameter

The parameter ResultsTable of data type table designates the data table into which the method writes the application interfaces.

Example

Teamcenter.queryApplicationInterfaces(MyDataTable)

See also

Application Interface [text box]

queryEnvironments [SimTalk]

Returns the environments which are configured in the Teamcenter Client Communication System ( TCCS ) of the object designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.queryEnvironments(ResultsTable:table)

Parameter

The parameter ResultsTable of data type table designates the table to which the method writes the environments.

Example

Teamcenter.queryEnvironments(MyEnvironmentTable)

See also

ServerURL [SimTalk]

**querySyncs [SimTalk]**

**querySyncs [SimTalk]**

Returns the Teamcenter syncs for the designated ApplicationInterface of the object designated by &lt;Path&gt;.

Remarks

You first have to query the application interface with the method queryApplicationInterfaces .

Type

Method

Syntax

```simtalk
< Path >.querySyncs(AINo:integer, ResultsTable:table)
```

**Parameters**

- The parameter AINo of data type integer designates the Teamcenter application interface for which you want to query syncs. The integer value is the position of the application interface in the table into which the method queryApplicationInterfaces wrote all available application interfaces.
- The parameter ResultsTable of data type table designates the table into which the method writes the names of the available syncs.

**Example**

```simtalk
Teamcenter.login
Teamcenter.queryApplicationInterfaces(MyDataTable)
MyDataTable.CursorX := 1
MyDataTable.CursorY := 1
if MyDataTable.find("My application interface")
	Teamcenter.querySyncs(MyDataTable.CursorY, MyDataTable)
	MyDataTable.CursorX := 1
	MyDataTable.CursorY := 1
	if MyDataTable.find("My sync")
		Teamcenter.retrieveData(MyDataTable.CursorY)
	end
end
Teamcenter.logout
```

**See also**

##### ApplicationInterface [SimTalk]

Sync [text box]

##### queryApplicationInterfaces [SimTalk]

##### retrieveData [SimTalk]

retrieveData [SimTalk]

Retrieves data from the Teamcenter database of the object designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.retrieveData([SyncNo:integer]) -&gt; boolean

Parameter

The optional parameter SyncNo of data type integer only applies when you set the ImportMode to "Application Interface from List" or "Application Interface via Active Workspace" . Here it designates the number of the Teamcenter sync. If you do not specify the parameter, you will then have to set the attributes ApplicationInterface and Teamcenter first.

You get the number of the Teamcenter sync by calling the methods queryApplicationInterfaces and querySyncs one after the other.

For a study you can select the study you want to import in the dialog under Connection &gt; Import Mode . If you did not select the study, Plant Simulation opens the Study Manager in which you can select the study when executing the method retrieveData .

Return Value

The return value has the data type boolean .

true if the method was executed successfully.

false if you set the ImportMode to Study and if you canceled the selection of the study in the Study Manager .

Example

Teamcenter.login Teamcenter.queryApplicationInterfaces(MyDataTable) MyDataTable.setCursorX(1, 1) if MyDataTable.find("My application interface") Teamcenter.querySyncs(MyDataTable.CursorY, MyDataTable) MyDataTable.setCursorX(1, 1 if MyDataTable.find("My sync") Teamcenter.retrieveData(MyDataTable.CursorY) end

end Teamcenter.logout

See also

ApplicationInterface [SimTalk]

Sync [SimTalk]

queryApplicationInterfaces [SimTalk]

querySyncs [SimTalk]

writeXMLFile [SimTalk]

ImportMode [SimTalk]

setPassword [SimTalk] - Teamcenter

Sets the password with which you log in to the Teamcenter database with the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.setPassword(Password:string) → boolean
```

Parameter

The parameter Password of data type string designates the password.

Return Value

The return value has the data type boolean .

Example

Teamcenter.setPassword("MyPassword123")

See also

Password [Teamcenter]

#### Read-Only Attributes of the Teamcenter Interface

Read-Only Attributes of the Teamcenter Interface

The Teamcenter Interface provides the \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

<!-- image -->

#### Attributes of the Teamcenter Interface

##### \_Attributes of the Teamcenter Interface

The Teamcenter Interface provides:

- The attributes listed in the table of contents to the left.
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
Teamcenter.ServerURL := "http://localhost:7001/tc"
print Teamcenter.ServerURL
posit := Station.cont.XPos
```

ApplicationInterface [SimTalk]

Sets the Application Interface to which the Sync of the object designated by &lt;Path&gt; belongs which you would like to import from Teamcenter .

Remarks

If you want to select the Sync and the Application Interface from a dialog when importing data, specify an empty string "" .

Type

Attribute

Syntax

&lt; Path &gt;.ApplicationInterface:string

Assignment Value

You can assign a value of data type string .

Example

Teamcenter.ApplicationInterface := "My Interface"

See also

Application Interface [text box]

Sync [text box]

Sync [SimTalk]

DataTable [SimTalk] - Teamcenter

Sets the name of the Plant Simulation DataTable of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation imports the PLMXML data to this DataTable .

Type

Attribute

Syntax

&lt; Path &gt;.DataTable:path

Assignment Value

You can assign a value of data type path/object .

Example

Teamcenter.DataTable := MyDataTable

See also

Table [text box] - Teamcenter

##### Directory [SimTalk]

Sets the name of the Directory into which the object designated by &lt;Path&gt; will copy the PLMXML file, the JT files, and the kinematics files.

Type

Attribute

Syntax

```simtalk
< Path >.Directory:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
Teamcenter.Directory := "MyTeamcenterFolder"
```

See also

Directory [text box]

**Group [SimTalk] - Teamcenter**

##### Group [SimTalk] - Teamcenter

Sets the name of the Group with which the object designated by &lt;Path&gt; logs on to Teamcenter .

Remarks

You can change your Group by clicking the icon of your user profile in the Active Workspace window .

Type

Attribute

Syntax

```simtalk
< Path >.Group:string
```

Assignment Value

You can assign a value of data type string .

Specify an empty string "" to log on under the default group.

Example

```simtalk
Teamcenter.Group := "Engineering"
Teamcenter.Group := "" // default group
```

See also

Group [Teamcenter]

##### ImportMode [SimTalk]

Sets the Import Mode which the object designated by &lt;Path&gt; uses when importing data from Teamcenter .

Type

Attribute

Syntax

&lt; Path &gt;.ImportMode:string

Assignment Value

You can assign a value of data type string .

- "Application Interface from List" enables you to select the application interface from a list.
- "Application Interface via Active Workspace" enables you to use Active Workspace to select the application interface.
- "Study" always uses the Study Manager to import data.

**Note**

The settings Application Interface via Active Workspace and Study only work if the Active Workspace URL is set correctly in the Teamcenter database under Preference &gt; ActiveWorkspaceHosting.PLANT.URL .

The setting Study in addition requires that the specified Active Workspace-Server supports the Study Manager , for example an Easy Plan-Server with the installed Teamcenter Manufacturing Access extension .

**Example**

Teamcenter.ImportMode := "Study"

See also

Import Mode [drop-down list]

Use Active Workspace

**Report [SimTalk]**

##### Report [SimTalk]

Sets the name of the report into which you want to write the HtmlReport of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

< Path >.Report:path

Assignment Value

You can assign a value of data type path .

Example

```simtalk
Teamcenter.Report := ~.~.UserObjects.MyHtmlReport
```

See also

HtmlReport [Teamcenter]

##### RetrieveJTFiles [SimTalk]

Sets if the object designated by &lt;Path&gt; will retrieve the respective JT files in addition to the PLMXML files from Teamcenter ( true ) or not ( false ).

Remarks

You find the JT files in the folder which you set with the attribute Directory .

Type

Attribute

Syntax

&lt; Path &gt;.RetrieveJTFiles:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
Teamcenter.RetrieveJTFiles := true
```

See also

Retrieve JT Files [check box]

Directory [SimTalk]

##### RetrieveKinematicsFiles [SimTalk]

Sets if the object designated by &lt;Path&gt; will retrieve the respective kinematics files in addition to the PLMXML files from Teamcenter ( true ) or not ( false ).

Remarks

You find the kinematics files in the folder which you set with the attribute Directory .

Type

Attribute

Syntax

&lt; Path &gt;.RetrieveKinematicsFiles:boolean

Assignment Value

You can assign a value of data type boolean .

Example

Teamcenter.RetrieveKinematicsFiles := true

See also

Retrieve Kinematics Files [check box]

Directory [SimTalk]

##### Role [SimTalk] - Teamcenter

Sets the name of the Role with which the object designated by &lt;Path&gt; logs on to Teamcenter .

Remarks

You can change your Role by clicking the icon of your user profile in the Active Workspace window .

Type

Attribute

Syntax

```simtalk
< Path >.Role:string
```

Assignment Value

You can assign a value of data type string .

Specify an empty string "" to log on under the default role.

Example

```simtalk
Teamcenter.Role := "Designer"
Teamcenter.Role := "" // default role
```

See also

Role [text box]

##### ServerURL [SimTalk]

Sets the Server URL of the Teamcenter server of the object designated by &lt;Path&gt;.

Remarks

The default server URL is http://localhost:7001/tc .

If Environments are designed in the TCCS, you can also specify an Environment with the TCCS protocol.

**Note**

The connection string that you enter depends on your Teamcenter provider, for example the IT department of the customer. Consult your Teamcenter provider for more information.

**Note**

When the connection with the server is established via HTTPS in encrypted mode, the respective certificate has to exist in the Windows Certificate Store . ( Control Panel &gt; Internet Options &gt; Content &gt; Certificates .)

**Note**

If you did not set the attributes ServerURL or UserName , i.e., assigned an empty string "", the object Teamcenter uses the settings specified for opening the model from Teamcenter or for checking the model in and out, provided these settings exist.

Type

Attribute

Syntax

&lt; Path &gt;.ServerURL:string

Assignment Value

You can assign a value of data type string .

Examples

```simtalk
Teamcenter.ServerURL := "http://MyCompany:7001/tc"
```

Teamcenter.ServerURL := "tccs://TCProduction"

See also Server [text box] UserName [SimTalk] queryEnvironments [SimTalk]

##### StyleSheet [SimTalk]

StyleSheet [SimTalk]

Sets the name of the Style Sheet of the object designated by &lt;Path&gt;.

Remarks

The style sheet is used when copying data from Teamcenter .

Type

Attribute

Syntax

&lt; Path &gt;.StyleSheet:string

Assignment Value

You can assign a value of data type string .

Example

```simtalk
Teamcenter.StyleSheet := "MyStyleSheet.xsl"
```

See also

Style Sheet [text box]

##### Sync [SimTalk]

Sets the name of the Sync of the object designated by &lt;Path&gt; which you would like to import from Teamcenter .

Remarks

To select the Sync and the Application Interface from a dialog when importing, assign an empty string "" to the attribute.

You have to specify the attribute ApplicationInterface if you specify the Sync .

Type

Attribute

Syntax

```simtalk
< Path >.Sync:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
Teamcenter.StyleSheet := "My Sync"
Teamcenter.StyleSheet := "" --  select the Sync and the Application Interface from a dialog
```

See also

Sync [text box]

Application Interface [text box]

ApplicationInterface [SimTalk]

**TargetFolder [SimTalk]**

##### TargetFolder [SimTalk]

Sets the Teamcenter Target Folder to which the object designated by &lt;Path&gt; saves the Plant Simulation HtmlReport .

Remarks

This folder has to be a subfolder of the Home folder of the user logged on to Teamcenter

Type

Attribute

Syntax

&lt; Path &gt;.TargetFolder:string

Assignment Value

You can assign a value of data type string .

Example

Teamcenter.TargetFolder := "My Target Folder"

See also

Target Folder [text box]

HtmlReport [object]

UserName [SimTalk]

Sets the User Name of the object designated by &lt;Path&gt; with which you log in to the Teamcenter database.

Remarks

If you did not set the attributes ServerURL or UserName , i.e., assigned an empty string "" , the object Teamcenter uses the settings specified for opening the model from Teamcenter or for checking the model in and out, provided these settings exist.

Type

Attribute

Syntax

&lt; Path &gt;.UserName:string

Assignment Value

You can assign a value of data type string .

Example

```simtalk
Teamcenter.UserName := "MyUserName"
```

See also

User Name [Teamcenter]

ServerURL [SimTalk]

The C Interface enables you to extend the features and functionalities of Plant Simulation considerably by integrating functions you programmed in the programming language C, such as numerical evaluation and optimization procedures, etc.

Note

The C Interface is part of the Plant Simulation Interface Package .

C

C

You can use the C Interface to call functions directly from within SimTalk , the Plant Simulation information flow language. For this, you have to create a program containing the functions you need and an interface with a given format. Then, you can load this program from SimTalk by using the method loadLibrary to load the C program or the DLL and execute functions with the method callLibrary . Within the C functions you can also directly access Plant Simulation objects. We also support the bidirectional data exchange between Plant Simulation and an external C program.

**Note**

When you use the C Interface to link a DLL, which you yourself programmed, this DLL has to be compiled as a 64-bit version.

This help topic provides a short introduction into the C Interface . Also consult the sample files in the Plant Simulation installation folder in the sub-folder Plant Simulation\C-Interface .

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

#### Using the C Interface

Using the C Interface

To be able to use the C functions you created from within Plant Simulation , you first have to call the function loadLibrary to load the C program or the DLL.

You can also use the functions listed in the table of contents to the left.

See also

loadLibrary [SimTalk]

##### callLibrary [SimTalk]

Calls the function named FunctionName in a DLL.

Type

Function

Syntax

```simtalk
callLibrary(Handle:integer, FunctionName:string[, Parameter:any, ...]) →
```

any

**Parameters**

- The parameter Handle of data type integer designates the handle , which the function loadLibrary returned.
- The parameter FunctionName of data type string designates the FunctionName . Argument and return value depend on the called function. When an error occurs, the Debugger opens.
- The optional parameters will be passed to the called C function.

**Return Value**

The return value has the data type any .

##### freeLibrary [SimTalk]

freeLibrary [SimTalk]

Unloads the loaded DLL.

Type

Function

Syntax

freeLibrary(NameOfDll:integer) → boolean

Parameter

The parameter NameOfDll of data type integer designates the DLL which was loaded.

Return Value

The return value has the data type boolean .

true if Plant Simulation succeeded in unloading the DLL.

false if unloading failed.

See also

loadLibrary [SimTalk]

##### getLoadedLibrary [SimTalk]

Returns the file name of the DLL, which was loaded by the parameter Handle .

Type

Function

Syntax

```simtalk
getLoadedLibrary(Handle:integer) → string
```

Parameter

The parameter Handle of data type integer designates the DLL which was loaded.

Return Value

The return value has the data type string .

See also

loadLibrary [SimTalk]

freeLibrary [SimTalk]

##### loadLibrary [SimTalk]

loadLibrary [SimTalk]

Loads the specified DLL.

Remarks

If the setting File &gt; Model Settings &gt; General &gt; Prohibit Access to the Computer is deactivated, which is the default setting for new models, Plant Simulation does not execute the function loadLibrary and shows an error message.

Plant Simulation first looks for the designated dll in the folder in which the model is saved. If it does not find the dll there, it searches in the path that is set in the Windows Environment Variable named Path .

Type

Function

Syntax

```simtalk
loadLibrary(NameOfDll:string) → integer
```

Parameter

The parameter NameOfDll of data type string designates the name of the DLL.

Return Value

The return value has the data type integer .

If the function fails, the return value will be less than 0.

If the function succeeds, Plant Simulation will return a value greater than 0, which you can use to access the DLL. This return value is the handle of the DLL.

**Example**

```simtalk
var file: string := ApplicationHome + "C-Interface\cinterf.dll"
```

See also

callLibrary [SimTalk]

freeLibrary [SimTalk]

**Prohibit Access to the Computer [model settings]**

#### Structure of the C Program

Structure of the C Program

The structure of the C program looks like described below. Plant Simulation loads the C functions as a DLL. The DLL you created has to contain the functions, which you programmed, as well as an interface to Plant Simulation . This is accomplished by including the files cinterf.cpp and cwinfunc.h in your project.

**Note**

When you use the C Interface to link a DLL, which you yourself programmed, this DLL has to be compiled as a 64-bit version.

Within the DLL, which you would like to call from Plant Simulation , the functions in the DLL have to be declared as follows.

Syntax

extern "C" __declspec(dllextern) void FunctionName (UF_Value* ret, UF_Value* arg)

**Example**

extern "C" __declspec(dllextern) void uf_sin(UF_Value* ret, UF_Value* arg)

The two parameters ret and arg of a function both reference UF\_Value .

Compare The Structure UF\_Value .

**The Structure UF\_Value**

##### The Structure UF\_Value

The structure UF\_Value is defined as follows in cwinfunc.h :

typedef struct { UF_DataType type UF_ValueUnion value } UF_Value

The field type tells which field of the compound value is valid. value has the data type UF\_ValueUnion , and defined as follows:

```simtalk
typedef union { int integer double real char *string objID object int error } UF_ValueUnion
```

**Valid values of type are:**

- UF\_NONE
- UF\_VOID
- UF\_INTEGER
- UF\_REAL
- UF\_BOOLEAN
- UF\_STRING
- UF\_LENGTH
- UF\_WEIGHT
- UF\_SPEED
- UF\_TIME
- UF\_DATE
- UF\_DATETIME
- UF\_OBJECT
- UF\_ERROR

Also compare the definition of UF\_DataType in the Header file cwinfunc.h , which is part of your program package.

Let's say that type is UF\_INTEGER, then only value.integer contains a valid value. In this case value.real or value.char would take an undefined value.

When Plant Simulation calls a C-function, the Plant Simulation data types of the parameters will be converted to the following C data types:

| Plant Simulation data type   | Data type in C   |
|------------------------------|------------------|
| boolean                      | int              |
| integer                      | int              |
| real                         | double           |
| time                         | double           |
| date                         | double           |
| dateTime                     | double           |
| money                        | double           |
| length                       | double           |
| weight                       | double           |
| speed                        | double           |
| string                       | char *           |

When passing a Plant Simulation real value for example, the item type of the parameter *arg is automatically set to UF\_REAL. You can then query the real value with arg-&gt;real .

The data type of the return value of the function to Plant Simulation has to be set according to the corresponding data type.

**Note**

When a string data type is passed to the function, the pointer to the string is valid only during the function, as memory can be released after returning from the function.

For a C function intended to compute the sine of a real value, enter this source code into the C program.

**Example**

```simtalk
void uf_sin(UF_Value *ret, UF_Value *arg) { ret->type=UF_REAL ret->value.real=sin(arg[0].value.real) }
```

##### Accessing Plant Simulation Objects

The more complex Plant Simulation data types object , table , list , stack and queue do not have a direct counterpart as basic data type in the programming language C. When calling a function that is passed a complex data type as parameter, type is assigned the value UF\_OBJECT. The parameter is then represented by the item object of the corresponding union. The item object has the data type SimpleObjID , which is defined in the header file cwinfunc.h .

This value permits direct access to the Plant Simulation objects passed within your function. The value of object , called object ID hereafter, is generated automatically and is not to be changed.

To pass a Plant Simulation object as a parameter to the C function it also will be represented by an object ID in the C program.

The required access functions are described under Accessing Plant Simulation Objects . For detailed examples compare the files cwinfunc.h and cinterf.cpp in the Plant Simulation installation folder in the sub-folder Plant Simulation\C-Interface .

See also

**Accessing Plant Simulation Objects**

###### Accessing Plant Simulation Objects

Accessing Plant Simulation Objects

The functions assignValue , evalPath , executeFunction , executeMethod , listAt , listAtPut , listAtIndex , and listAtIndexPut provide direct access to Plant Simulation objects. The objects are defined by the corresponding object ID of data type simpleObjID . They are assigned the corresponding object ID, when an Plant Simulation object is passed as parameter to your C function. The Plant Simulation objects DataTable , DataList , DataQueue or DataStack and the variables of data type table, list, stack and queue are accessed in an analogous way. These items will be referred to as list objects hereafter. For the one-dimensional list objects DataList , DataStack and DataQueue and for the variables of data type list , stack and queue only the first index entry (second parameter of the listAtxxx functions) is evaluated. The third parameter has to have the type UF\_Integer and the value 1 .

Using index-oriented access functions for one-dimensional list objects and for tables without user-defined indexes is not possible. In this case, the functions return an object of type UF\_ERROR that may be evaluated.

- UF\_Value listAt (simpleObjID list, int x, int y)
- UF\_Value listAtPut (simpleObjID list, int x, int y, UF\_Value *value)
- UF\_Value listAtIndex (simpleObjID list, UF\_Value *x, UF\_Value *y)
- UF\_Value listAtIndexPut (simpleObjID list, UF\_Value *x, UF\_Value *y, UF\_Value *value)
- UF\_Value evalPath (simpleObjID startObject,char *path, int argcount, UF\_Value *args)

- UF\_Value executeMethod (simpleObjID method, simpleObjID caller, simpleObjID-ID activeElement, int argcount,UF\_Value *args)
- UF\_Value executeFunction (char *FunctionName, int argcount, UF\_Value *args)
- UF\_Value assignValue (SimpleObjID lValue, char *attribute, char*subattribute, UF\_Value *value)

These functions are defined in the file cwinfunc.h.

**assignValue [SimTalk]**

###### assignValue [SimTalk]

Assigns a value to an attribute of a Plant Simulation object.

Type

Function

**Syntax**

UF_Value assignValue(SimpleObjID *lValue,char*attribute,char

*subattribute,UF_Value *value)

**Parameters**

- The parameter SimpleObjID *lValue designates the object ID of the Plant Simulation object, whose attribute you would like to change.
- The parameter char*attribute designates the name of the attribute you would like to change.
- The parameter char *subattribute is only required, when the attribute itself contains additional attributes, such as the attribute ProcTime of the Station . If the value is not required, enter 0.
- The parameter UF\_Value *value designates the value that you want to assign.

**Example**

```simtalk
UF_Value rValue rValue.type = UF_TIME rValue.value.time = 33 SimpleObjID *ID = evalPath(0,".Station",0,0) assignValue(ID,"processingtime",0,rValue) rValue.type = UF_STRING rValue.value.string = "const" assignValue(ID,"setuptime","type",rValue)
```

**See also**

ProcTime [SimTalk] - material flow objects

###### evalPath [SimTalk]

Evaluates a SimTalk path. Plant Simulation returns the value of the path in an UF\_Value structure.

Type

Function

**Syntax**

UF_Value evalPath(simpleObjID *startObject,char *path, int

argcount,UF_Value *args)

**Parameters**

- The parameter simpleObjID *startObject designates the Plant Simulation object, at which the path evaluation starts or 0.
- The parameter char *path designates the path to be evaluated.

If this path leads to a method expecting parameters, you have to specify their number as the parameter int argcount , otherwise the value has to be 0.

- The parameter UF\_Value *args designates the parameters of the method. Only simple paths are allowed, i.e., the last item of the path has to be the name of an attribute or a sub-attribute. A path like this is not allowed: ".Station.setName("Test")" .

**Example**

```simtalk
UF_Value retVal retVal = evalPath(0,".Station.name",0,0) UF_Value retVal UF_Value args[1] args[0].type = UF_STRING args[0].value.string = "Test" retVal = evalPath(0,".Station.setName",1,args)
```

**See also**

**Object Paths in SimTalk**

**executeFunction**

###### executeFunction

Calls a built-in SimTalk method, such as setSeedTable , sin , version , etc. from within the C function.

Type

Function

Syntax

UF_Value executeFunction(char* FunctionName,int argc,UF_Value *args)

**Parameters**

- The parameter char* FunctionName designates the name of the built-in method.
- The parameter int argc designates the number of the parameters.
- The parameters UF\_Value *args designate the parameters as such.

**Return Value**

The return value is the result of the method.

**Example**

```simtalk
UF_Value retVal UF_Value argv[1] argv[0].type = UF_REAL argv[0].value.real = 3.1415 retVal = executeFunction("sin",1,argv)
```

###### executeMethod [SimTalk]

Starts a user-defined method in a Plant Simulation model and returns a value.

**Remarks**

The function is executed in a mode in which the Method Debugger does not open, so errors occurring in the method during its execution are not shown in the Debugger . Plant Simulation only shows an error message in the Console .

Type

Function

Syntax

UF\_Value executeMethod(simpleObjID *method,simpleObjID *caller,simpleObjID *activeElement,int argcount,UF\_Value *args)

**Parameters**

- The parameter simpleObjID *method designates the object ID of the method to be started.
- The parameter simpleObjID *caller designates the object ID of the object to be called in the method with the question mark.
- The parameter simpleObjID *activeElement designates the object ID of the object to be called in the method with the anonymous identifier @ .
- The parameter int argcount designates the number of parameters the method expects.

These parameters have to be passed in the UF\_Value *args vector.

If no parameters are expected, the value is 0.

See also

Error Types

**listAt [SimTalk]**

###### listAt [SimTalk]

Reads the cells of list objects.

**Remarks**

The function is required because Plant Simulation normally calls cells in a list by using brackets, such as .table[1,1] . The brackets cannot be used to evaluate paths within the SimTalk function evalPath .

Type

Function

Syntax

UF_Value listAt(simpleObjID *list,int x,int y)

**Parameters**

- The parameter simpleObjID *list designates the object ID of the list object.
- The parameter int x designates the x-coordinate of the cell you'd like to query.
- The parameter int y designates the y-coordinate of the cell.

**Return Value**

This value is going to be the return value.

See also

Error Types

evalPath [SimTalk]

###### listAtIndex [SimTalk]

Accesses cells within tables by using their indexes.

Type

Function

Syntax

UF_Value listAtIndex(simpleObjID *list,int x, UF_int y)

**Parameters**

- The parameter simpleObjID *list designates the table you want to be access.
- The parameter int x designates the index for the column.
- The parameter int y designates the index for the row.

The data type of both index values has to be the same as the data type of the table indexes.

Return Value

The return value is the addressed cell.

See also

Error Types

**listAtIndexPut [SimTalk]**

###### listAtIndexPut [SimTalk]

Writes a value into a cell addressed by a table index.

Type

Function

**Syntax**

UF_Value listAtIndexPut(simpleObjID *list, UF_Value *x, UF_Value *y,

UF_Value *value)

**Parameters**

- The parameter simpleObjID *list designates the table you want to be access.
- The parameter UF\_Value *x designates the index for the column.
- The parameter UF\_Value *y designates the index for the row.
- The parameter UF\_Value *value designates the value to be written into the addressed cell.

**See also**

**Error Types**

###### listAtPut [SimTalk]

Writes values into cells of list objects.

Type

Function

Syntax

UF\_Value listAtPut(simpleObjID *list,int x,int y, UF\_Value *value)

**Parameters**

- The parameter simpleObjID *list designates the object ID of the list object.
- The parameter int x designates the x-coordinate of the cell whose contents you'd like to change.
- The parameter int y designates the y-coordinate of the cell.
- The parameter UF\_Value *value contains the value to be written.

See also

Error Types

##### Error Types

If a function call returns the type UF\_ERROR for type instead of the expected value, the field error in the compound UF\_ValueUnion may be evaluated.

**Remarks**

This field error contains the error type. Possible error types are:

1. Error types for listAt , listAtPut , listAtIndex , and listAtIndexPut .

|   Value of Error | Error type                                                           |
|------------------|----------------------------------------------------------------------|
|                1 | Error in the parameters (amount or type).                            |
|                2 | First parameter is not a list object or no index access is possible. |

**2. Error types for evalPath and assignValue .**

|   Value of Error | Error type                                                                              |
|------------------|-----------------------------------------------------------------------------------------|
|                1 | Wrong access to the attribute. A more specific error message is output in the Console . |
|                2 | The attribute does not exist.                                                           |

**3. Error types for executeMethod .**

|   Value of Error | Error type                                             |
|------------------|--------------------------------------------------------|
|                1 | First parameter is not a method.                       |
|                2 | Error with passing parameters or executing the method. |

**See also**

listAt [SimTalk]

listAtPut [SimTalk]

listAtIndex [SimTalk]

listAtIndexPut [SimTalk]

assignValue [SimTalk]

evalPath [SimTalk]

executeMethod [SimTalk]

##### Compiling the C Program

The compilation process of the C program itself depends on the C compiler employed and environment the C Interface is to be used in.

**Note**

When you use the C Interface to link a DLL, which you yourself programmed, this DLL has to be compiled as a 64-bit version.

To create a DLL, allowing access to C functions from within Plant Simulation , execute these steps:

1. Create a new project in your C++ development environment and select Dynamic-Link Library as type.
2. Copy the Header files cwinfunc.h and cinterf.cpp from the Plant Simulation installation folder, subfolder Plant Simulation/C-Interface , into your project folder.
3. Include the file cwinfunc.h into the C file, which is to contain functions to be called from within Plant Simulation : #include "cwinfunc.h"
4. Add the function you defined.

**Note**

When you dynamically link the MFC libraries while creating your DLL, these libraries have to be present on the computer on which the application runs.

The Plant Simulation installation folder contains an executable example in the sub-folder Plant Simulation/C-Interface . Check out the file example.cpp , to get an idea on how to define your functions.

#### COM

