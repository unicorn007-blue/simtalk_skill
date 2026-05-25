#### Input Functions

Input Functions

SimTalk provides the functions listed in the table of contents to the left for requesting input from the user.

When you create the simulation model certain data will not be known. You might, for example, ask the user to enter the capacity of a Store , which you inserted into a Frame .

**Note**

The dialogs, which the functions open are modal. The simulation only continues when the user reacted to the requested interaction.

##### prompt [SimTalk]

Asks the user to enter data into a dialog.

Remarks

The dialog, which the function opens is modal. The simulation only continues when the user reacted to the requested interaction by clicking the OK button in the dialog.

Type

Function

Syntax

<!-- image -->

**Parameters**

- The parameter Text of data type string designates the text you want to show. Plant Simulation opens a dialog displaying the designated text and a text box. It pauses the simulation run until the user has entered that data and closed the window by clicking OK . Plant Simulation can display a maximum of four lines with a maximum of 45 characters per line. It treats each line as a parameter of data type string of its own.

Type in the text, which you want to show in the title bar of the dialog, between two vertical bars, for example ("|My Company|This is a prompt!", "row 2") .

- The optional parameter More Text of data type string designates additional text that you want to show.

<!-- image -->

**Return Value**

The return value has the data type string .

Is the data the user entered.

<!-- image -->

**prompt [SimTalk]**

**Note**

You can convert the result with the functions for converting data types.

**Examples**

```simtalk
// method for querying the number of pallets in a model -> integer
var s: string // gets the number of pallets
s := prompt("Enter number", "of pallets")
return str_to_num(s)
var s: string
s := prompt("|My Company|This is a prompt!", "row 2")
```

**See also**

**Functions for Converting Data Types**

##### promptList1 [SimTalk]

Enables the user to pick a a single entry from the list, which is displayed in the message window.

**Remarks**

The user can select a single entry and click OK .

<!-- image -->

The dialog, which the function opens is modal. The simulation only continues when the user reacted to the requested interaction by clicking the respective button in the dialog.

Type

Function

Syntax

```simtalk
promptList1(Entry:list[, Text:string, ...]) → integer
```

**Parameters**

- The parameter Entry of data type list designates a list of any type with one column.
- The optional parameter(s) Text of data type string designate the text above the list box. You can enter any number of optional parameters of data type string with a maximum length of 45 characters.

Type in the text, which you want to show in the title bar of the dialog, between two vertical bars, for example (DataList, "|My Company|Text ...", "row 2") .

**Return Value**

The return value has the data type integer .

Is the index of the selected entry.

0 when the user clicks Cancel .

**Examples**

promptList1(DataList, "Select an entry from the list below", "additional text, text, text, text, ...") // the entries are contained in the object DataList

promptlist1(DataList, "|My Company|Text ...", "row 2")

<!-- image -->

##### promptListN [SimTalk]

Enables the user to pick one or several entries from the designated list, which is displayed in the message window.

**Remarks**

The dialog, which the function opens is modal. The simulation only continues when the user reacted to the requested interaction by clicking the respective button in the dialog.

<!-- image -->

The user can select one or several entries by Shift/Ctrl+clicking the objects and click OK .

Type

Function

Syntax

```simtalk
promptListN(List:list[, Text:string, ...]) → list
```

**Parameters**

- The parameter List of data type list designates the list.

The user can select one or more entries by holding down Ctrl and clicking the entry/entries. OK closes the dialog and accepts the choice.

**promptListN [SimTalk]**

- The optional parameter(s) Text of data type string designate the text above the list box. You can enter any number of optional parameters of data type string with a maximum length of 45 characters.

Type in the text, which you want to show in the title bar of the dialog, between two vertical bars, for example (DataList, "|My Company|Text...", "row 2") .

<!-- image -->

**Return Value**

The return value has the data type list[integer] .

When the user clicks Cancel , Plant Simulation returns 0.

Plant Simulation saves the indexes of the selected entries unsorted.

**Examples**

```simtalk
// A part entering the plant may be processed by more than one machine.
var machPark: list[string]  // You are going to enter the machines that can
var indices: list[integer]  // process it machPark.create machPark[1] := "M7"; machPark[2] := "M12" machPark[3] := "M4"; machPark[4] := "M19"
indices := promptListN(machPark, "Select one or several of the machines that can", "process the part:")
for var i := 1 to Indices.Dim
	switch indices[i]
	case 1 // M7 selected
	case 2 // M12 selected
	case 3 // M4 selected
```

case 4 // M19 selected end // switch next promptlistN(MyDataList, "Select one or several entries from the list below", "by Shift+clicking or Ctrl+clicking the objects.","Additional text, text, text, text, ...") // the entries are contained in the object MyDataList

promptlistn(DataList, "|My Company|Text...", "row 2")

##### Output Functions

