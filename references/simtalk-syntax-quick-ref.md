# SimTalk 2.0 Syntax Quick Reference

Extracted from the Plant Simulation Help.

## Comments

```simtalk
-- single line comment (to end of line)
/* multi-line
   comment */
```

Note: `-->` is NOT a comment — it's a visual arrow in documentation.

## Declarations

```simtalk
var name : type                    -- local variable (method scope)
local name : type                  -- same as var
param name : type                  -- input parameter
result : type                      -- return type declaration (in method signature)
var name : type := initialValue    -- declaration with initialization
var a, b, c : integer              -- multiple declarations (same type)
```

### Common Types
`integer`, `real`, `boolean`, `string`, `object`, `table`, `any`, `void`
Arrays: `integer[3]`, `string[10]`, `real[,]` (2D)

## Assignment & Operators

```simtalk
name := value          -- assignment
name += value          -- increment
name -= value          -- decrement
```

### Comparison
`=`, `/=` (not equal), `<`, `>`, `<=`, `>=`

### Logical
`and`, `or`, `not`

### String
`+` (concatenation), `strLPos(haystack, needle)`, `strRPos(...)`, `strCopy(...)`, `numToStr(...)`, `strToNum(...)`

## Control Flow

### If-Then-Else
```simtalk
if condition
    -- block (indented)
elseif condition
    -- block
else
    -- block
end
```

### For Loop
```simtalk
for var i := 1 to upperBound
    -- block
next

for var i := upperBound downto 1
    -- block
next
```

### While Loop
```simtalk
while condition
loop
    -- block (indented inside loop)
end
```

### Repeat-Until
```simtalk
repeat
    -- block
until condition
```

### Switch-Case
```simtalk
switch expression
case value1:
    -- block
case value2:
    -- block
default:
    -- block
end
```

## Indentation Rules

| Keyword | Effect |
|---------|--------|
| `if`, `for`, `while`, `repeat`, `switch` | Next line +1 indent |
| `loop` (after `while`) | Same level as `while`, content +1 |
| `case`, `default` | Close previous case (-1), open new (+1) |
| `elseif`, `else` | Close previous block (-1), open new (+1) |
| `end`, `next`, `until` | Close block (-1 on this line) |

Indent unit: **tab** (Plant Simulation convention).

## Object References & Paths

```simtalk
self                    -- current method's owner object
self.~                  -- parent frame of the method's object
root                    -- model root
?.                      -- current MU (moving unit) in sensor controls
@.                      -- predecessor object in connector path
```

### Path navigation
```simtalk
root.Models.Frame1.Station1          -- absolute path
self.~.Buffer1                       -- relative to parent
?.Name                               -- attribute of current MU
```

## Method Calls

```simtalk
object.methodName(arg1, arg2)        -- call method on object
result := object.methodName(...)     -- capture return value
object.methodName                    -- no-arg call (parentheses optional)
```

## Common Patterns

### Table Access
```simtalk
table[columnName, row]               -- cell by column name + row index
table[colIndex, row]                 -- cell by column index + row index
table.xDim                           -- number of columns
table.yDim                           -- number of rows
```

### MU (Moving Unit) Operations
```simtalk
mu.move(destination)                 -- move MU to destination
mu.cont                              -- container holding this MU
mu.create(destination)               -- create MU instance
mu.delete                            -- destroy MU
```

### Event Controls
```simtalk
-- Common sensor controls:
-- init, reset, exitControl, entranceControl, endSim
-- Method signature for entrance/exit:
param mu : object -> void            -- or -> object for routing
```

### Wait / Pause
```simtalk
waituntil condition prio priority
self.operationTime := timeValue
self.startPause / self.stopPause
```

## Statement Boundary Signals (for code parsing)

These patterns reliably indicate where one statement ends and another begins:
1. `--` comment marker (unless `-->` arrow)
2. `:=` / `+=` / `-=` assignment operators
3. `var`/`local`/`param`/`result` declarations
4. Control flow openers: `if`, `for`, `while`, `repeat`, `switch` (with syntax validation)
5. Control flow closers: `end`, `next`, `until`
6. `return` keyword
7. `.methodName(...)` chains starting a new expression
