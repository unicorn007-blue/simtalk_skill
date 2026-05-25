### VariantsGenerator

Use the VariantsGenerator for creating frequency tables for attribute variants, which objects of type Source with the setting Attributes &gt; MU Selection &gt; Random use.

**Icon**

<!-- image -->

**Description**

To add the VariantsGenerator to the Class Library , click Manage Class Library &gt; Libraries &gt; Tools &gt; VariantsGenerator on the Home ribbon tab. Plant Simulation adds the VariantsGenerator to the tab Tools in the Toolbox .

<!-- image -->

<!-- image -->

You can enter the Source objects and the mobile object into the VariantsGenerator , by dragging them onto the VariantsGenerator and by dropping them onto it. The VariantsGenerator computes the frequency table and enters it into all Sources . The mobile objects (MUs), which the Source produces, have user-defined attributes of data type string . Each attribute can take on a limited number of values, the frequencies of which are given. For each individual attribute the sum of the frequencies of all values is 1. Select an attribute on the tab Attributes and double-click the table below. Enter the attribute values the desired frequencies into the table, which opens.

<!-- image -->

<!-- image -->

When all combinations of attribute values of all attributes are permitted, the probability of an attribute combination is the product of the frequencies of the individual attribute values. In practice some attribute combinations might not be permitted. To exclude attribute combinations from being used, click Show on the tab Constraints and select the combinations in the table Variants . Click Start on the tab Constraints to compute the frequencies. Depending on the size of the problem this might take some time. As the calculations utilize random components, Plant Simulation produces different results, when you run the calculation several times. To check how well the constraints are met, click Validation of desired frequencies &gt; Show on the tab Constraints to open the table Validation .

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

**Related Reference**

Tools

