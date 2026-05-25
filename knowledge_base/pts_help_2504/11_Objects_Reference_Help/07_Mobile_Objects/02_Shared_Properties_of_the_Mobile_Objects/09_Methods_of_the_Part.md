#### Methods of the Part

The Part provides:

- The Methods of All Mobile Objects .
- The Methods of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

An example of the Syntax line of the individual methods might look like this:

```simtalk
<MUPath >.create(Destination:any[, Position:length, CopyStatistics:boolean, PredecessorNumber:integer]) → object
```

- &lt;MU-Path&gt; designates a valid path to the MU (for example: MyTrack.Cont , ParallelStation.MU(1) , .MUs.Part:203 ). If you use the Method as an entrance or exit control, you can access the MU that triggered the control using the anonymous identifier @ (see Anonymous Identifiers ).
- &lt;MU-location&gt; designates a location- or length-oriented material flow object, a single processing place of an object with several places, or a length-oriented object including a position. You can enter the position as the additional parameter of data type length . If you do not enter a position, Plant Simulation uses 0.
- The signature of the method, consisting of the identifier and the data type of the parameter, is listed in parentheses. The expression (Parameter:string) , for example, designates a parameter of data type string . Instead of a constant value, you can also use a variable of the required type or a method that returns the required data type.

**Note**

Make sure to enter the parentheses for expressions within parentheses (…). Not entering them may lead to unexpected results and open the Debugger .

Optional parameters are listed within brackets. The expression [,Parameter:boolean] , for example, means that you can, but do not have to enter the boolean parameter.

If a parameter has a default value, the signature shows the default value after the parameter.

If the method has a return value, the signature shows its data type after the arrow -&gt;.

