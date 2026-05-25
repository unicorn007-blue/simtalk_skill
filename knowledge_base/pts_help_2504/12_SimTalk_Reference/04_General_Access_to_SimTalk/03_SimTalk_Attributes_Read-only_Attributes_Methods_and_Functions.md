### SimTalk Attributes, Read-only Attributes, Methods, and Functions

SimTalk provides attributes , methods , read-only attributes , and functions .

The description of the individual attributes , methods , read-only attributes , and functions shows this under the section title Type .

<!-- image -->

The window Show Attributes and Methods shows most types a well.

<!-- image -->

**Attributes in SimTalk**

An attribute in SimTalk sets or gets a property of an object.

Attributes encompass the built-in attributes of the object, user-defined attributes, local variables, and objects of type Variable .

An attribute in SimTalk looks like this:

<!-- image -->

**Methods in SimTalk**

A method in SimTalk is a block of source code that executes a task when called.

Methods as a rule have parameters, have side effects, and can return a value.

A method in SimTalk

- gets information from an object and returns a value
- computes a value
- starts one or several actions that control the behavior of the object

A method in SimTalk looks like this:

```simtalk
TableVariable := EventController.getEventList(-1)
MyStation.addObserver("occupied", &myMethod)
```

**Read-only Attributes in SimTalk**

A read-only attribute in SimTalk returns a value of a property of an object.

Read-only attributes do not expect parameters, do not have side effects, and return a value.

A read-only attribute in SimTalk looks like this:

```simtalk
param sensorID: integer, Front: boolean
if @.ID = 1
	@.Speed := 0
	print EventController.SimTime, " The first Transporter stopped."
end
```

**Functions in SimTalk**

A function in SimTalk is a piece of source code that applies in general and is not object-specific.

A function in SimTalk looks like this:

```simtalk
if currentEventCtl /= VOID
	print "simulation running in frame", currentEventCtl.location
	print "simulation running in frame", root
end
```

**See also**

Show Attributes and Methods [described]

Object Paths in SimTalk

