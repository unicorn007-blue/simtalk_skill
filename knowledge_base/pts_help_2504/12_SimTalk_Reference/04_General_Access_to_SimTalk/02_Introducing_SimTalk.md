### Introducing SimTalk

SimTalk consists of the built-in methods , read-only attributes , and attributes and of control structures.

SimTalk encompasses:

- The built-in methods , read-only attributes , and attributes which the Plant Simulation objects provide. These are defined by our software engineers and offer a base you can build on.
- Control structures and language constructs. With loops and conditional branching you can control the sequence of method execution.

We use this notation when describing the syntax of a method:

- The expression &lt;Path&gt; designates the path of the object to which the method applies.
- The signature of the method, consisting of the identifier and the data type of the parameter, is listed in parentheses. The expression (Parameter:string) , for example, designates a parameter of data type string . Instead of a constant value, you can also use a variable of the required type or a method that returns the required data type.

Optional parameters are listed within brackets. The expression [,Parameter:boolean] , for example, means that you can, but do not have to enter the boolean parameter.

**Note**

Make sure to enter the parentheses for expressions within parentheses (…). Not entering them may lead to unexpected results and open the Debugger .

If a parameter has a default value, the signature shows the default value after the parameter

If the method has a return value, the signature shows its data type after the arrow -&gt;.

To view all of the methods , read-only attributes and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

In the Plant Simulation Help we use these conventions:

- Within descriptions in the body text on the topic pages the names of objects begin with an upper-case letter and are italicized, for example ParallelStation , Station , etc.
- In the Plant Simulation Help , the colored term sometimes is a link to an object, for example ParallelStation . Click the link to open that topic in the Online Help .
- In the description in the Plant Simulation Help the names of methods begin with a lower-case letter. Each new term after that begins with an upper-case letter. Methods are italicized, for example derive , updateDialog , etc.

In the Online Help , the colored term sometimes is a link to a method , for example derive . Click the link to open that topic in the Online Help

- In the description in the Online Help the names of attributes and read-only attributes begin with an upper-case letter. Each new term after that begins with an upper-case letter as well. Attributes and read-only attributes are italicized, for example CreationTableActive , ReferenceTime , etc.
- In the Online Help , the colored term sometimes is a link to an attribute, for example CreationTableActive . Click the link to open that topic in the Online Help .
- In the description in the Online Help we use MU and part interchangeably, for example the processed MU and the processed part mean the same. If Part start with an upper-case P though, it refers to the MU of type Part .

**Note**

These spelling conventions apply to the Online Help .

**Note**

SimTalk normally does not distinguish between upper- and lower-casing for the names of methods , attributes , and read-only attributes , which you type into the source code of your Method objects. You do not have to use the spelling which the window Show Attributes and Methods shows. You can, for example, type in CreationTableActive , creationtableactive , or CREATIONTABLEACTIVE .

<!-- image -->

