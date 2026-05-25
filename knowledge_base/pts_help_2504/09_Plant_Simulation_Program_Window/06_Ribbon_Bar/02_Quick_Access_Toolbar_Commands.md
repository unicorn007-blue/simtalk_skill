### Quick Access Toolbar Commands

#### Quick Access Toolbar

The Quick Access Toolbar provides commands to access its functions. You can customize it to meet your modeling needs.

<!-- image -->

| Command                                     | Looks like this   | Method                                                               |
|---------------------------------------------|-------------------|----------------------------------------------------------------------|
| Close Model                                 |                   | closeModel [SimTalk] - global function                               |
| Save Model File                             |                   | saveModel [SimTalk]                                                  |
| Save Model File As                          |                   | selectFileForSave [SimTalk]                                          |
| Reset Simulation [Home ribbon]              |                   | reset [SimTalk] - EventController                                    |
| Start/Stop Simulation [Home ribbon]         |                   | start [SimTalk] - EventController , stop [SimTalk] - EventController |
| Start Full Speed Simulation [Home ribbon]   |                   | start [SimTalk] - EventController                                    |
| Start Fast Forward Simulation [Home ribbon] |                   | -                                                                    |
| Customize Quick Access Toolbar              |                   | -                                                                    |

You can add commands to the Quick Access Toolbar to suit your modeling needs by clicking Customize Quick Access Toolbar &gt; More Commands .

The title bar of the program window only provides a fixed width for the Quick Access Toolbar

<!-- image -->

. When you add additional commands, Plant Simulation shows them in a second row below the other commands.

**Note**

Plant Simulation enters the customized settings of the Quick Access Toolbar to the registry key HKEY\_CURRENT\_USER\Software\Siemens\Tecnomatix Plant Simulation 2504\WorkspaceENU .

When you delete this key, your customized settings will be deleted as well.

#### Customize Quick Access Toolbar Commands

Customize Quick Access Toolbar

Adds commands to the Quick Access Toolbar .

By default, the function Customize Quick Access Toolbar provides these commands:

<!-- image -->

<!-- image -->

If you do not want to show one of the default buttons on the Quick Access Toolbar , click it. This dims this command again until you click it again in the list. An active command shows the check mark to the left.

**Note**

Plant Simulation enters the customized settings of the Quick Access Toolbar to the registry key HKEY\_CURRENT\_USER\Software\Siemens\Tecnomatix Plant Simulation 2504\WorkspaceENU . When you delete this key, your customized settings will be deleted.

##### More Commands

Opens a dialog allowing you to customize the Quick Access Toolbar and the Ribbon by adding or removing commands from them.

To customize the Quick Access Toolbar , click it in the left window pane.

- Select the category from which you want to add commands to the Quick Access Toolbar from the drop-down list Choose commands from .
- Select the command you want to add from the list Commands and click Add .
- Click the Move Up or Move Down button to move the command up or down in the list on the right hand side.
- To reset the to the Quick Access Toolbar default settings, click Reset .
- To show the Quick Access Toolbar below the ribbon, select Show Quick Access Toolbar below the Ribbon Bar .
- To customize keyboard shortcuts, click Customize and customize the settings according to your modeling needs.

<!-- image -->

<!-- image -->

You can customize the Ribbon by adding your own tabs or groups to the ribbon bar. To do so, click Customize Ribbon in the left window pane.

<!-- image -->

**Note**

Under Customize Ribbon &gt; Customize the Ribbon we only offer the Main Tabs in the list on the right-hand side. The context-dependent tabs for the Frame , the Method , the Icon Editor , and for Lists are not available here. You cannot customize these.

##### Show Below the Ribbon

Places the Quick Access Toolbar below the Ribbon in the Plant Simulation program window.

<!-- image -->

When you activate Show Below the Ribbon , the label of the command changes to Show Above the Ribbon .

**Minimize the Ribbon**

##### Minimize the Ribbon

Minimizes the Ribbon Bar in the Plant Simulation program window. It then only shows the titles of the tabs without the buttons for the commands.

<!-- image -->

Instead of selecting Minimize the Ribbon , you can also click the Minimize button

.

<!-- image -->

To show the ribbon bar again, click the button or select the command again.

<!-- image -->

Back to Ribbon Bar

