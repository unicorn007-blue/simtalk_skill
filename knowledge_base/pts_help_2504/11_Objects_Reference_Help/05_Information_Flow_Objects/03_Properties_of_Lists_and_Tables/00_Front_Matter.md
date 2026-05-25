### Properties of Lists and Tables

Lists and tables manage and store information and data.

The Material Flow Objects , which Plant Simulation provides, usually suffice for quickly creating simple simulation models. More complex models require additional information, for example production plans, to control the course of events in the model, and create data during the simulation which lists and tables save to be evaluated later on.

Plant Simulation provides lists with one column ( DataList , DataStack , DataQueue ) and lists with several columns ( DataTable , TimeSequence ):

<!-- image -->

The following topics describe general properties of the lists and tables. Plant Simulation provides five different lists and tables:

- The DataList accesses all cells randomly by their position. You can add new cells at any position. If you remove a cell, all cells with a higher number move up one position.
- The DataQueue accesses the cell you added first. It adds new cells after the last existing cell.
- The DataStack accesses the cell you added last. If you add a cell all existing cells move one position down. If you remove a cell, the remaining cells each move up one cell.
- The DataTable accesses all cells randomly by their column and row number. New contents will overwrite and replace any existing contents of the cell.
- The TimeSequence accesses all cells randomly by their column and row number. It adds new entries in ascending order according to the time . Entries with a higher position move up by one position if you remove a previous entry. The time-value pairs that the TimeSequence records belong together, meaning that you can only delete a pair of values not either the time or the value of a pair.

You can access the properties of the list objects on the List Ribbon Tab .

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

**See also**

| Window of Lists and Tables               | Methods of Lists and Tables              |
|------------------------------------------|------------------------------------------|
| Accessing Data in Lists                  | Read-Only Attributes of Lists and Tables |
| Accessing a Range of Cells with a Method | Attributes of Lists and Tables           |
| Creating Lists within Lists and Tables   | Working with Lists and Tables            |

