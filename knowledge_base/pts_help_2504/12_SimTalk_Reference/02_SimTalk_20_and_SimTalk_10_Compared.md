## SimTalk 2.0 and SimTalk 1.0 Compared

The following table provides an overview of the changed language constructs between SimTalk 2.0 and SimTalk 1.0 .

| Feature                                | SimTalk 2.0 (New Syntax)                                   | SimTalk 1.0 (Old Syntax)                          |
|----------------------------------------|------------------------------------------------------------|---------------------------------------------------|
| Parameter declaration                  | param v1,v2: integer, name: string                         | (v1,v2:integer; name:string)                      |
| Return Type declaration                | ->boolean or param v1,v2: integer, name: string -> boolean | :boolean or (v1,v2:integer; name:string): boolean |
| Empty Method                           | -                                                          | is do end;                                        |
| Variable declaration between is and do | var v: integer var s: string                               | is v:integer; s:string; do end;                   |
| Variable declaration                   | var s: string                                              | local s: string                                   |
| if condition                           | if a > 3 print a end                                       | if a > 3 then print a; end;                       |
| for loop                               | for var i := 1 to 10 print i next                          | for local i := 1 to 10 loop print i; next;        |
| while loop                             | while a < 10 a += 1 print a end                            | while a < 10 loop a := a + 1; print a; end;       |
| repeat loop                            | repeat a += 1                                              | repeat a := a + 1;                                |

| Feature             | SimTalk 2.0 (New Syntax)                                  | SimTalk 1.0 (Old Syntax)                                 |
|---------------------|-----------------------------------------------------------|----------------------------------------------------------|
|                     | print a until a > 10                                      | print a; until a > 10;                                   |
| switch-statement    | switch a case 1 print 1 case 2 print 2 end                | inspect a when 1 then print 1; when 2 then print 2; end; |
| waituntil-statement | waituntil name = "Test" or waituntil name = "Test" prio 1 | waituntil name = "Test" prio 1;                          |
| list operator [ ]   | list.remove(2)                                            | list[2]                                                  |

The following table provides an overview of the changed operators between SimTalk 2.0 and SimTalk 1.0 .

| Feature              | SimTalk 2.0 (New Syntax)   | SimTalk 1.0 (Old Syntax)   |
|----------------------|----------------------------|----------------------------|
| About equal operator | ~=                         | ==                         |
|                      | <~=                        | <==                        |
|                      | >~=                        | >==                        |
| Add a value          | x += y is short for        | -                          |
| Subtract a value     | x -= y                     | -                          |

| Feature                      | SimTalk 2.0 (New Syntax)                                                                                                                              | SimTalk 1.0 (Old Syntax)                                                    |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------|
|                              | is short for x := x - y                                                                                                                               |                                                                             |
| Multiply a value             | x *= y is short for x := x * y                                                                                                                        | -                                                                           |
| Modulo operator              | mod                                                                                                                                                   | \\                                                                          |
| Division operator            | div                                                                                                                                                   | //                                                                          |
| Reference operator           | &                                                                                                                                                     | .ref()                                                                      |
| Type check during assignment | Wrong unit causes an error. To prevent this, assign the correct unit or a value without a unit, for example: Conveyor.Speed := Conveyor.Length / 0:01 | Wrong unit causes a warning, for example: Conveyor.Speed := Conveyor.Length |

New simulation models use the SimTalk 2.0 notation by default!

You can activate SimTalk 2.0 notation by clicking New Syntax [command] on the Tools ribbon tab of the Method you are programming. If you want to use if for all new Methods which you are going to program, activate New Syntax in the Method class in the Class Library . Instead, you can also use the attribute UsingNewSyntax [SimTalk] .

<!-- image -->

**Note**

Clicking in an existing Method which you programmed in SimTalk 1.0 notation automatically converts the source code to the correct SimTalk 2.0 notation .

<!-- image -->

<!-- image -->

Use the command Find Outdated Functions on the Debugger ribbon tab to find methods , attributes and functions in the source code of all Methods in your simulation model.

**See also**

Operators and Expressions &gt; Arithmetic Operators

### A Quick Tour Through SimTalk 2.0

