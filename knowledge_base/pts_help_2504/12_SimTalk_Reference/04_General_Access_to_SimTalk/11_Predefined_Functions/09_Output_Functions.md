#### Output Functions

SimTalk provides the functions listed in the table of contents to the left for outputting data.

**beep [SimTalk]**

##### beep [SimTalk]

Plays a beeping sound on the computer speaker. You can use it to alert the user about messages or critical situations.

Type

Function

Syntax

beep

**Example**

```simtalk
if store.full beep // acoustic alert
else
	@.move(Store)
print "The Store is full"
end
```

##### bell [SimTalk]

Outputs an acoustic signal on the computer speaker.

Type

Function

Syntax

bell(Frequency:integer, Duration:integer)

**Parameters**

- The parameter Frequency of data type integer designates the frequency of the bell sound.
- The parameter Duration of data type integer designates its duration.

**Example**

bell(440,1000)

**getUnit [SimTalk]**

##### getUnit [SimTalk]

Returns the unit of the passed value of the data type length , weight , time , speed , money , or acceleration .

Remarks

This is the unit which you selected under File &gt; Model Settings &gt; Units .

Type

Function

Syntax

```simtalk
getUnit(Value:any) → string
```

Parameter

The parameter Value of data type any designates the value for which you would like to get the unit.

Return Value

The return value has the data type string .

Example

```simtalk
var l: length := 100 // meters // We now assume that the length unit in the Model Settings is set to kilometers
print l          // returns 0.1 km
print to_str(l)  // returns 0.1, to_str does not add a unit
print getUnit(l) // returns km // Since we don't have settings for areas we still get SI units here
print l*l          // returns 10000m²
print getUnit(l*l) // returns m²
```

See also

Units [model settings]

##### infoBox [SimTalk]

Presents the user with a message box, which shows the designated text.

**Remarks**

Close the message box by calling the function infoBox a second time and by passing an empty string "" .

**Note**

Open a modal Infobox to prevent the user from modifying a simulation model during a simulation run.

If the Debugger is opened, any open message box will be closed. Otherwise, an open modal message box would prevent you from continuing your work.

**Note**

If you inadvertently opened a modal message box without closing it, hold down the Shift+Ctrl+Alt keys for 5 seconds. This closes the message box and opens a dialog you can close by clicking No .

Type

Function

Syntax

```simtalk
infoBox(Text:string, Modal:boolean)
```

**Parameters**

- The parameter Text of data type string designates the text, which the message box shows.
- The parameter Modal of data type boolean sets if the dialog is modal, i.e., that you cannot access any other Plant Simulation window ( true ) or not ( false ).

<!-- image -->

**infoBox [SimTalk]**

**Example**

infoBox("My information",false)  // shows "My information" infoBox("", false)               // closes the info box

print [SimTalk] - output function

Outputs any amount of text to the Console .

Remarks

You can open the Console by clicking the button on the Window ribbon tab.

<!-- image -->

Strings within arrays are enclosed in quotation marks.

Type

Function

Syntax

```simtalk
print ...
```

**Parameter**

For values of data type length , weight , speed , and acceleration , the Console shows the unit after the value.

You can specify any number of parameters without any type constraint. You can use this function to show error messages or other hints for the user.

**Examples**

```simtalk
print "machine", M12.getName, "failed"
@.Cont.move(MyDrain)
print @, ":"
print "Previous destination: ", @.Destination  // writes the previous // destination to the Console
@.Destination := LoadingStation
print "New Destination: ", @.Destination      // writes the new // destination to the Console print                                         // inserts an empty line
var a : string["Kent, Clark", ""]
var s : string := to_str(a)  -- assigns ["Kent, Clark", ""]
```

