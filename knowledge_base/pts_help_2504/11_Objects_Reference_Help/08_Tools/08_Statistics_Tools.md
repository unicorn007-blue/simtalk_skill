### Statistics Tools

Use the Statistics Tools for analyzing the statistics values that your simulation runs determined.

**Statistics Tools describes these topics:**

- About Statistics Tools
- Determine Probability Distributions
- Comparing Density Functions of Distributions
- Determine Confidence Intervals
- Run a Regression Analysis
- Find the Parameters of Truncated Distributions
- Run an Analysis of Variance (ANOVA)
- Run an Independence Test

**Note**

The statistics tools are only available in the Professional License .

**See also**

Preparing Data for the Simulation with DataFit

#### Overview of the Statistics Tools

The Statistics Tools support you in preparing data, in creating your model, and in analyzing the simulation results. The Statistics Tool DataFit serves for parametrizing statistical distributions for random values, such as failure times, set-up and processing times, inter-arrival times, and for setting the number of rejects.

To add the Statistical Tools , the Variants Generator , and the Sequential Sampler to the Class Library , click

<!-- image -->

Manage Class Library &gt; Libraries &gt; Tools &gt; Statistical Tools on the Home ribbon tab.

<!-- image -->

- This adds the toolbar Statistical Tools to the Toolbox .

<!-- image -->

You find the Variants Generator and the Sequential Sampler on the tab Tools .

<!-- image -->

To get a quick introduction to the statistics tools:

- Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models .
- Click Example Models &gt; Small Examples .
- Select the category Tools and Optimization and the topic Statistics Tools .

<!-- image -->

Use the object DataFit to Determine Probability Distributions .

- Filters samples and provides descriptive statistics.
- Estimates parameters of selected distributions.
- Runs goodness-of-fit tests.
- Shows results in histograms.

<!-- image -->

Use the object Confidence to Determine Confidence Intervals by calculating an interval containing the mean value of a random number.

<!-- image -->

Use the object Regression to Run a Regression Analysis .

- Calculates the correlation coefficient.
- Calculates the regression coefficient.
- Calculates the regression line or regression curve, respectively.
- Shows results in scatter diagrams.

<!-- image -->

Use the object TruncDistribution to Find the Parameters of Truncated Distributions .

- Determines the mean value and the standard deviation for distributions with bounds.
- Calculates parameters for given bounds and mean values.
- Plots the density function of the truncated distribution.

<!-- image -->

Use the object ANOVA to Run an Analysis of Variance (ANOVA) .

- Tests whether grouped data have the same mean values.
- Graphically compares the confidence intervals of the groups.

Use the object Independence to Run an Independence Test to test whether paired data are independent of each other.

<!-- image -->

<!-- image -->

Use the object Comparison to compare the density functions of distributions whose parameters you determined with the object DataFit .

You can load the sample data into the object DataFit , Confidence (confidence interval) or Regression (linear regression) using the object FileInterface or the Windows clipboard. Plant Simulation shows information in the Console and outputs prompt messages about all actions of the objects.

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

**See also**

Preparing Data for the Simulation with DataFit

#### DataFit: Determine Probability Distributions

##### Determine Probability Distributions

The object DataFit assists you in determining the parameters of certain specified distributions for observed data (samples) of a random variable, so that the distribution matches the properties of the sample as adequately as possible.

After manually scaling and translating the sample data, the parameters of the known distributions are calculated using the maximum-likelihood method and the method of moments. A goodness-of-fit test decides for a given level of significance, whether the distribution under consideration fits the sample data in an adequate manner.

The goodness-of-fit test is performed with the chi-square test ( -test), the Kolmogorov-Smirnov test (KS test) and the Anderson-Darling test (AD test). The test is only invoked if the sample data is appropriate for the considered test. The KS test and the AD tests, for example, are executed only if the sample size is less than 2000 and the sample belongs to a population of a continuous random variable.

Data fitting comprises the following steps:

- Loading or generating the sample data (data table DataFit .DataX).
- Filtering and sorting the data (data table DataFit .Sampledata).
- Choosing a hypothesis about the distribution of the sample.
- Choosing the level of significance, which is the probability for rejecting the hypothesis although it was true: Type I error.
- Running a goodness-of-fit test (result data table DataFit Ranking).

If you want to, you can compare the observed and the expected frequencies, based on the selected distribution, in a diagram.

If no distribution fits the sample with the desired level of confidence, then you can model the sample with an empirical distribution. The corresponding frequency table will be determined by DataFit .

Input Data

Input Data

You must save the data, which you want to investigate, in the data table Samples . This data will then be imported to the tab Data Input of the object DataFit .

To delete the data table DataX and all calculated data, click the button Input data &gt; Delete . To enter sample data from any Plant Simulation data table, drag the data table onto the object DataFit and drop it there.

<!-- image -->

The data table Samples of the model DataFitFeatures with some samples

This opens the dialog Data Source :

<!-- image -->

**Load a sample with drag-and-drop**

The drop-down list contains all columns of the table of data types real , time , or integer . The leftmost number is the number of the column.

###### Recommended Test Data

For testing purposes generate a sample of 100 Erlang-distributed numbers with the Plant Simulation parameter µ = 3 (mean) and σ = 3 (standard deviation).

This distribution is also an exponential distribution with β = 3 and a Weibull- and Gamma distribution with the parameter α = 1 and β = 3 .

**Loading Data from a File**

###### Loading Data from a File

To load sample data from the file sample.dat, click File &gt; Load &gt; Data . You can change the name of the file in the text box Data file .

The object RollDice in the Class Library generates the respective file.

<!-- image -->

The loaded data of the sample is contained on the data table DataX . You can open or close it by clicking the button Open/Close . You can only start filtering data on the tab Data Filter if you did load data. If you select discrete on the drop-down list Type of data , all numbers of the sample are rounded to integer values.

<!-- image -->

##### Data Filter

You can change the bounds of the sample by typing different values into the text boxes on the tab Data Filter .

Figure 11-45: DataFit, Filter Data

<!-- image -->

The data table Sampledata contains the filtered and sorted data of the sample. You can open it by clicking the button Sorted data &gt; Open .

To start filtering the data, click Apply . Each new start of the data filter uses the original data of the sample contained on the table DataX . The filtered data of the previous run of the filter will be discarded. The selected parameters, on the other hand, (lower and upper bounds, zoom factor and offset) are available for the next run of the filter.

To eliminate outliers from the sample, you can define lower and upper bounds. Only the sample data between these bounds is transferred to the data table Sampledata . You have to type in both bounds.

Then, the data is shifted by the value of DistrFit.Offset and scaled with the factor DataFit.Zoomfactor . If X is a value of DataX and Y is a value of Sampledata , then the equation Y = Zoomfactor * (X + Offset) holds true.

The effects of these transformations on the descriptive statistics, such as minimum, maximum, mean value, standard deviation, of the filtered sample are shown on the data table StatData . You can open this table by clicking the button Descriptive Statistics . How you can use the transformed distributions in simulation models is explained below.

DataFit automatically selects the data type of the data table Sampledata according to the setting of the drop-down list Type of data on the tab Input of Data . Selecting Discrete rounds the sample data to an integer value and then changes the data type of the corresponding data tables.

Hypotheses About Suitable Distributions

Hypotheses About Suitable Distributions

The data table StatData contains important statistical parameters of the sample, making it possible to recognize elementary properties of the sample (method DataFit.computeStatDescript) . The analysis of measures of shape, such as the variance coefficients, yields statistical hints about the type of the distribution.

The data can be adapted using a filter. Suppose that you want to use a Beta distribution, then the values of the sample must be transformed into the interval (0,1).

Figure 11-46: The data table StatData with all statistical parameters

<!-- image -->

###### Minimum and Maximum

To examine the range of the sample, the minimum and the maximum should be known.

A characteristic value of a sample is Range = Maximum - Minimum. From previous experience the standard deviation is approximately equal to Range/4 .

**Mode [DataFit]**

###### Mode [DataFit]

The mode of a sample from a discrete random variable is the most frequently used value. In general, the mode is not uniquely determined.

The explanation of this notion for a sample of a continuous distribution is difficult. The practical meaning -especially in case of non-uniqueness-is small.

###### Mean and Variance

Using the filtered data of the sample of the data table Sampledata the mean value

<!-- image -->

<!-- image -->

<!-- image -->

and the variance are computed.

**Median and Quartiles**

###### Median and Quartiles

When determining these parameters, it is important that the values of the sample contained in . The calculation of the quartile is given in the following

Sampledata are sorted: table. [a,b] = (a + b)/2 designates the arithmetical mean of a and b.

<!-- image -->

The second quartile is also called median or middle quartile. The first and the third quartile are also known as the lower and upper quartile, respectively. The quartiles are defined as follows.

<!-- image -->

**Definitions of the quartiles**

###### Skewness

A typical parameter is the skewness coefficient, which measures the lack of symmetry of the considered distribution of a random variable X.

The skewness coefficient is defined by

<!-- image -->

A symmetric distribution has .

<!-- image -->

<!-- formula-not-decoded -->

**Coefficient of Variation**

###### Coefficient of Variation

An important measure of shape is this parameter defined by

.

<!-- image -->

Suppose that , then the exponential distribution with a suitable parameter ß can fit the sample. cv &lt; 1 implies that the sample can fit with a Gamma and the Weibull distribution with α &gt; 1.

For cv &gt; 1 the Gamma and the Weibull distribution with α &lt; 1 can be used.

###### Kurtosis

The set of values falling long away from the mean value are measured by this parameter.

<!-- image -->

It is defined by

.

A standard normal distributed random variable has a kurtosis coefficient equal to 0.

**Goodness-of-Fit Test**

##### Goodness-of-Fit Test

For a given level of significance DataFit checks whether a hypothesis about the distribution of a random variable X under consideration is true or not.

The random sample is determined by X. Suppose that the hypothesis is true, then the test rejects the hypothesis with a probability α. This probability α is called level of significance. You can type it in on the tab Fit . Frequently used values for α are 0.1 , 0.05 or 0.01 . The value (1- α) is therefore the probability for recognizing the true hypothesis.

Figure 11-47: Settings for the goodness-of-fit test

<!-- image -->

Type in the most important parameter for the goodness-of-fit-test, the Level of significance , on the tab Fit of the object DataFit .

<!-- image -->

The setting Number of classes only applies to the test. The analyzed range, within which the values of the sample are located, are split into a number of intervals (classes) which you type in. The classes

###### Goodness-of-Fit Test

for which the frequencies to be expected are less than 5 are combined. The frequency to be expected results from the number of sample elements and the probability that a random variable of the selected and parametrized distribution are located within the interval (class). Plant Simulation always executes this class adjustment as the used methods only work correctly under these circumstances.

You can open a histogram by clicking the Show button.

DataFit computes the parameters of the following distribution and performs the goodness-of-fit test. The string in parenthesis shows the name of the distribution in Plant Simulation which you can select in the dialogs of the objects.

**Discrete Distributions**

- Binomial distribution (Binomial)
- Geometric distribution (Geom)
- Poisson-distribution (Poisson)

**Continuous Distributions**

- Beta distribution (Beta)
- Cauchy distribution (not contained in the drop-down list)
- Erlang-distribution (Erlang)
- Exponential distribution (Negexp)
- Fréchet distribution (not contained in the drop-down list)
- Gamma distribution (Gamma)
- Gumbel distribution (not contained in the drop-down list)
- Laplace distribution (not contained in the drop-down list)
- Logistic distribution (not contained in the drop-down list)
- LogLogistic distribution (not contained in the drop-down list)
- Log-Normal distribution (Lognorm)
- Normal distribution (Normal)
- Paralogistic distribution (not contained in the drop-down list)
- Pareto distribution (not contained in the drop-down list)
- Triangular distribution (Triangle)
- Uniform distribution (Uniform)
- Weibull-distribution (Weibull)

Click Distributions &gt; Select to opens this dialog and select the distributions. Hold down Shift to select more than one distribution.

DataFit runs three tests: The Chi-square test ( -test), the Kolmogorov-Smirnov test (KS test) and the Anderson-Darling test (AD test).

Figure 11-48: Selecting the distribution

<!-- image -->

Using the data of the sample all tests compute a test function, the so-called test statistic. The level of significance yields a critical value α. The hypothesis is accepted if the test statistic is less than the critical value. In the results table Ranking the columns Chi statistic , KS statistic , and AD statistic contain the values of the test function of the respective sample. Chi value, KS value, and AD value are the critical values used for computing the level of significance. The result is contained in an additional column in the table Ranking .

Click the button FIT to start rating the distribution parameters and the following parameter tests for the selected distribution types. The Console shows information about each and every action of Plant Simulation .

To show the results of the calculations, click the button Results &gt; Open on the tab Evaluation .

Figure 11-49: Intermediate results after the goodness-of-fit-test

<!-- image -->

###### The chi-square-Test

The -test needs samples with at least 40 values with . The test consists of the following steps:

1. The values of the sample are partitioned into k intervals of the same length, the so-called classes : The lower bound of the interval belongs to it and the upper bound does not. The intervals cover the range between the minimum and maximum. You set the number k of classes in the variable NumClasses . The number of classes for a discrete distribution is equal to the number of observed values in the sample.
2. By the maximum-likelihood method the parameters of the distribution are calculated.
3. Under the assumption that the hypothesis (the selected distribution fits the sample data) is true the probabilities of the event that a value lies in the i-th class (the interval ) are calculated.
4. The numbers of values of the sample lying in the i-th class are calculated.

Figure 11-50: Part of the frequency table

<!-- image -->

The data table stores the bounds of the intervals together with the observed and with the expected frequencies.

Under the assumption of the hypothesis, there are no essential differences between the observed and expected frequencies. These differences are measured by the test statistic. Therefore, the next steps consist of:

5. Calculating the test statistic of the sample
6. Calculating the critical value by using the level of significance.
7. Accepting or rejecting the hypothesis by comparing the test statistic and the critical value.

Figure 11-51: Intermediate results of the

<!-- image -->

<!-- image -->

The columns Chi statistic , Chi value , and Result Chi on the table Ranking contain the test function, the critical value, and the test result of the tests.

###### The Kolmogorov-Smirnow Test

The KS test and the AD test are based on the comparison of the empirical distribution function derived from the sample and the distribution function of the selected distribution.

The selected distribution is considered with the parameters calculated by the maximum-likelihood estimation (MLE). Both tests process samples containing 2000 values at most.

The test function, the critical value and the result of the KS test are contained in columns 5, 6 and 7 of the data table Ranking , respectively.

Figure 11-52: Intermediate results of the KS test in the Report

<!-- image -->

###### The Anderson-Darling Test

The KS test and the AD test are based on the comparison of the empirical distribution function derived from the sample and the distribution function of the selected distribution.

The selected distribution is considered with the parameters, which were calculated by the maximumlikelihood estimation. Both tests process samples containing 2000 values at most. The AD test is appropriate for samples with a small size n.

Figure 11-53: Intermediate results of the AD test in the Report

<!-- image -->

The test function, the critical value and the result of the AD test are contained in columns 8, 9 and 10 of the data table Ranking , respectively.

###### Evaluating the Test Results

##### Evaluating the Test Results

The result data table Ranking contains the columns Chi statistic, KS statistic and AD statistic with the values of the test function.

The critical values are shown in the columns Chi value, KS value and AD value resulting from the level of significance. The result of the single test (accept the hypothesis or not) is stored in an additional column of the data table Ranking .

The distributions can be sorted according to the quality of fitting, measured by the test statistic. You can select the test to be performed from the drop-down list Sort according to.

Figure 11-54: Evaluation of the results of the goodness-of-fit test

<!-- image -->

You can then use these parameters in Plant Simulation models. If you want a certain value to be distributed by an Erlang-distribution, you can use the parameters in columns 11 and 12. In a method, you can enter z\_erlang(Stream, Parameter1, Parameter2) . If, on the other hand, the zoom factor is not 1 and the offset is not 0, you would type in z\_erlang(Stream, Parameter1, Parameter2) / Zoomfactor - Offset

You find the explanations of the estimated parameters at the end of the data table ranking :

Figure 11-55: The estimated parameters for the distributions

<!-- image -->

Click Messages to open a data table containing information about the numerical calculations. If you try to fit a continuous distribution to a discrete sample, DataFit will tell you that this is not possible.

Information and error messages of the data fitting

If no distribution fits the sample with the desired level of confidence, then you can model the sample with an empirical distribution. DataFit presents the corresponding frequency table.

The button Frequency table opens a data table with the intervals defined by the number of classes and the bounds of the data filter together with the observed frequencies.

Figure 11-56: Empirical frequency table of a sample

<!-- image -->

Determine Statistical Distributions with SimTalk

Suppose you want to estimate the parameters α and β of the gamma distribution for a sample containing in the second column of the data table Samples .

The instruction

Samples.copyRangeTo({4,1}..{4,*}, DataFit.DataX,1,1)

transmits the sample to DataFit .

The internal DataTable DataFit.Distributions contains all statistical distributions that can be evaluated.

The instruction

```simtalk
DataFit.Distributions.initialize({3,1}..{3,12}, false)
DataFit.Distributions[3,"Gamma"] := true
```

selects only the Gamma distribution. You can select several distributions.

If your sample does not contain any outliers, you do not have to filter the data:

```simtalk
DataFit.FilterRequired := false
```

The internal method fi lterData computes the descriptive statistics.

DataFit.filterData

Statistics is required for estimating the distribution parameters and for the (Goodness-of-Fit-Test) which this instruction starts:

DataFit.fit

The results are written to the internal table Ranking .

For the first investigation you should also open this table:

DataFit.Ranking.openDialog

#### Compare Density Functions of Distributions

If the Goodness-of-Fit Test of the object DataFit accepts the hypothesis for several distributions that the properties of the given sample can be adequately represented by the parametrized distribution, you have to select a distribution for modeling.

The histogram of the sample that the object DataFit provides roughly shows the ranges with high and with low frequencies. To better compare the parametrized distributions, you can use the visualization of the density functions.

<!-- image -->

<!-- image -->

#### Determine Confidence Intervals

For determining confidence intervals we provide the object Confidence .

Icon

<!-- image -->

Calculating the confidence intervals presumes that the sample is provided by a normally distributed random number. This presumption for evaluating simulation results is met in most cases. Looking at a histogram enables you to visually evaluate the symmetry of the sample, compare Skewness .

You can input data via the object FileInterface or by pasting them from the Windows clipboard. You can also drag a data table onto the statistical object Confidence and select the column containing the input data.

Figure 11-57: Data input and Histogram of confidence intervals

<!-- image -->

To compute the confidence interval and to show the results, click the button Start .

Figure 11-58: Confidence intervals with unknown variance

<!-- image -->

The confidence level is the probability that the true value is really contained within the determined interval.

If the standard deviation of the random number under consideration is known, select the check box Known standard deviation and type in the value of the standard deviation.

If the standard deviation of the random number is unknown, the dialog item for the standard deviation contains the standard deviation of the sample.

When calculating the confidence intervals, we assume that all observations are independent of each other. The autocorrelated samples have a bigger confidence interval. The object computes a corresponding interval.

During the simulation, you can determine a confidence interval for data contained in the second column of the data table myData with these statements.

**Example**

```simtalk
var StatObj,TabObj: object, a,b: real
StatObj := Confidence
TabObj := StatObj.DataX
TabObj.delete
TabObj.insertList(1,1, myData.copy({2,1}..{2,*}))
StatObj.alpha := 0.1 // confidence level 90 percent
StatObj.knownVariance := false
StatObj.compute
a := round(StatObj.mean - StatObj.width,2)
b := round(StatObj.mean + StatObj.width,2)
print "Confidence intervals [",a," , ",b,"]"
```

As we only have a single sample for evaluation, and we do not know further properties of the random number, we usually validate the confidence intervals by using bootstrapping. For this you select so-called bootstrap samples from the given sample. This way you can simulate typical properties, such as variations of the mean value. The bootstrapping method does not pose additional assumptions to the distribution of the random variable. This method is called re-sampling. To do so, select Tools &gt; Resampling .

<!-- image -->

When many observations of the mean value exist, the interval, within which the true mean value with the given confidence interval is located, can be calculated.

#### Run a Regression Analysis

Using a regression analysis you can describe the correlation between the input values and a single output value of a simulation study with a mathematical formula. This way you can predict an output value for numerous parameter combinations of input values.

Icon

<!-- image -->

**Description**

If you want to study how a single input value determines an output value, start with several observations of value pairs of input and output values. You can perform a linear, a polynomial, or multiple regression

<!-- image -->

analysis. The icon of the object shows a different icon after each calculation if you last ran a linear , a polynomial or a multiple regression.

<!-- image -->

<!-- image -->

The object Regression determines a regression line or a regression polynomial. It computes the correlation and the regression coefficient. A sample consists of ordered pairs with j = 1,..., n, where n is the sample size.

<!-- image -->

You can input data via the object FileInterface or by pasting it from the Windows clipboard. To import data from a table which you inserted into a Frame , drag the table onto the Wizard and drop it there. This opens this dialog.

<!-- image -->

Click the button Read XY to load a sample for a linear or a polynomial regression analysis. With the drop-down lists you can set the columns for the input values ( Column X ) and the output values ( Column Y ). To run a multiple regression analysis, load the entire contents of a table. This table has to contain the output values in the first column. The following columns contain input values.

Figure 11-59: Descriptive statistics

<!-- image -->

Selecting the appropriate degree of the polynomial is a trade-off between minimizing the error rate and the ability of a regression analysis to filter out the data noise.

Figure 11-60: Polynomial regression analysis

<!-- image -->

The RegressionAnalysis recommends the degree of the regression curve, based on the Akaike information criterion (AIC) . The error between the data of the sample and the data of the regression curve is measured by the mean squared error (MSE) . Increasing the degree leads to a decreasing error. A great degree of the regression curve enables to also model data fluctuations resulting from the influence of random model components and modeling errors. Complex regression formulas with numerous parameters make it difficult to recognize the essential correlations between the input values and the output values. On the other hand complex correlations of the input and the output values also require complex regression formulas.

The RegressionAnalysis creates the regression polynomials for all degrees between 1 and 10 and selects the best polynomial according to the Akaike information criterion . The results of these calculations are written to a table, which you can open by selecting Tools &gt; Akaike Information Criterion (AIC) .

To show a scatter diagram for the data of the sample , click Show . It displays the linear association between the X and the Y values.

Figure 11-61: The scatter diagram of a sample with the regression line

<!-- image -->

Figure 11-62: Polynomial regression analysis

<!-- image -->

If the data under consideration cannot be modeled with a linear function, run a polynomial regression analysis. The data is fitted by a polynomial y = an xn +... + a1 x + a0. You can type in the degree of the polynomial n &gt; 0 into the text box.

Figure 11-63: The scatter diagram of a sample with regression polynomial of degree 2

<!-- image -->

Figure 11-64: Output of the resulting polynomial y = 0.62 x2 - 4.26 x + 26.18

<!-- image -->

If you want to analyze the correlation between several input values and a single output value, you will use a multiple regression analysis. An item of a sample consists of an observation of an output value y and the corresponding input values x 1, x 2 , x 3 ....

When a simulation study has four input values x1, x 2 , x 3 and x4, the wizard computes the coefficient ß 0 , ß 1 , ß 2 , ß 3 and ß4, so that the properties of the sample match the formula y = ß 0 + ß 1 x 1 + ß 2 x 2 + ß 3 x 3 + ß 4 x4 as good as possible. The magnitude of the calculated coefficient ß j and its algebraic sign allow to draw conclusions from the influence of the corresponding input value xj onto the output value y. This type of regression analysis is thus called factorial regression .

Figure 11-65: Data for a multiple regression analysis

<!-- image -->

For a multiple regression analysis all data has to be provided in a table. The first column always contains the observations of the output value.

Just as in a polynomial regression analysis Akaikes information criterion (AIC) gives a recommendation as to which regression polynomial best describes the properties of the sample.

It may happen that regression formulas with fewer terms better describe the results of a simulation study as the regression formula with all variables. For this reason for a regression analysis with three input values regression formulas such as y = ß 0 + ß 1 x 1 + ß 3 x 3 will also be analyzed. This regression formula eliminates the influence of the input value x 2 which possibly strongly depends on random model components.

Figure 11-66: Result polynomial ß0 + ß1 x1 + ß2 x2 + ß3 x3 + ß4 x4

<!-- image -->

To compute the output value with a regression formula in a table, select the command Tools &gt; Calculator . Type the input values into the white-colored cells and click Apply .

Figure 11-67: Calculation of the output value for different sets of input values

<!-- image -->

For additional information consult: Kenneth P. Burnham, David R. Anderson: Model Selection and Inference: A Practical Information-Theoretic Approach, 1998 Springer-Verlag, New York Inc.

#### Find the Parameters of Truncated Distributions

The object TruncDistribution computes the (real) mean value and the standard deviation for a distribution with an upper and a lower bound.

Icon

<!-- image -->

Description

For modeling random failures, you will often use probability distributions with lower and upper bounds. We do know these bounds and the mean value of the failures from experience. We want to find the distribution parameters, guaranteeing that the desired mean value occurs during the simulation.

This poses these two problems:

- A truncated distribution has other mean values and another standard deviation than the distribution without bounds.

To generate a random number with bounds, Plant Simulation generates a number of the unlimited distribution and checks whether this random number lies between the bounds. You can type in the maximum number of the taken samples by selecting File &gt; Preferences/Model Settings &gt; Simulation in the Plant Simulation program window .

- Since the simulation is interrupted when this number of trials is reached, it is advisable to know the probability for the interval between the bounds before we start the simulation. If the probability P is located near 1, the mean value and the standard deviation of the truncated distribution will only slightly differ from the respective values of the distribution without bounds.

Figure 11-68: Setting the maximum number of samples for generating truncated distributions

<!-- image -->

You can compare the mean value of the original (dotted line) and of the truncated distribution (continuous line) of the density function in a diagram.

<!-- image -->

Figure 11-69: The object TruncDistribution for the analysis of a truncated distribution

<!-- image -->

The object TruncDistribution assists you in solving the following task:

Given are a continuous distribution-of type Erlang, Gamma, Lognorm, Negexp, Normal, Weibull-, the lower bound a and the upper bound b , a shape parameter-for instance, α or σ -of the distribution under consideration and the desired (real) mean value of the truncated distribution. You want to find the remaining scaling parameter (for instance, β or µ) of the distribution, so that the truncated distribution has the desired mean value. Furthermore, you want to know the probability P([a,b]) for the unlimited distribution P using the determined parameter.

To display all results in the dialog of the object, press the button Start . It may happen that the desired mean value for the selected distribution, for the shape parameter, and for the two bounds might not be realized.

Figure 11-70: Determining the parameters of a truncated distribution

<!-- image -->

You can also have the simulation compute the parameters during the simulation run and then use the determined parameters in the Plant Simulation model:

```simtalk
var StatObj := TruncDistribution
var distrType := "Normal"
StatObj.distribution := distrType
var lowerBd := 100 // lower bound 100 seconds
StatObj.a := lowerBd
var upperBd  := 500 // upper bound 500 seconds
StatObj.b := upperBd
StatObj.MuDesired := 240 // desired mean value of 4 minutes
var sigma := 100 // standard deviation of 100 seconds
StatObj.ShapeParam := sigma StatObj.DetermParam // calculation
var mu := StatObj.DetParam
print "Mu = ",mu
Station.procTime.setParam(distrType, mu, sigma, lowerBd, upperBd)
```

#### Run an Analysis of Variance (ANOVA)

The object ANOVA ( AN alysis O f VA riance) performs a one way analysis of variance.

Icon

<!-- image -->

Description

Given are k groups of data. We want to investigate the hypothesis whether the k mean values,...,

are equal. The j-th group contains items ,...,. The j-th group must be contained in the j-th row of the table DataX. To insert the data, drag the table onto the object ANOVA and drop it there.

Figure 11-71: Input data

<!-- image -->

Our sample young men of different religious denominations are examined. The measured value is the age, at which a man leaves home. We are interested in the hypothesis that this age depends on the religious denomination, contained in: R.D. Mason, D.A. Lind, W.G. Marchal: Statistics An Introduction, 1988, p.355 ff. Harcourt Brace Jovanovich, Publishers

**Run an Analysis of Variance (ANOVA)**

<!-- image -->

<!-- image -->

This sum is partitioned into two addend TSS = SST + SSE, where is the sum of squares between the mean values of the groups (sum of squares of treatments; traditionally, a group

<!-- image -->

develops by distinct treatments of individuals of a whole population) and is the sum of squares in a group (error sum of squares). SSE measures the variability within the groups. SST measures the variability between the groups.

Figure 11-72: Dialog of the object ANOVA

<!-- image -->

The test determines at the given level of significance whether the hypothesis = =...= holds true. The test executes these steps:

- It determines the test statistic: F statistic
- It computes the critical value F value using the level of significance.

- It accepts the hypothesis if F statistic F value.

Figure 11-73: Explanation of the results table of ANOVA

| -              | Degree of freedom   | Sum of squares   | Mean squares   |
|----------------|---------------------|------------------|----------------|
| between groups | k-1                 | SST              |                |
| within groups  | n-k                 | SSE              |                |
| total          | n-1                 | TSS              |                |

Figure 11-74: The data table containing the results for the test data

<!-- image -->

You can compare the confidence intervals with the same level of significance of all groups in a diagram. An assumption about the decision of the test can be found. In the following diagram the red bars on top show the confidence intervals of the four groups. Since the intersection of these confidence intervals is empty, the hypothesis that the mean values are equal will certainly be rejected.

Figure 11-75: Comparison of the confidence intervals of the groups

<!-- image -->

The hypothesis is rejected. With a probability of 95 percent we must thus assume that a connection between the age, at which a man leaves home, and the religious denomination exists. Click Open to open the input data table. Delete the group of the catholic men. Now the hypothesis that the mean values are equal, is accepted with a probability of 95 percent (confidence level = 5 percent).

#### Run an Independence Test

With the object Independence you can investigate the hypothesis whether two random numbers are independent of each other or not. The test is based on the Chi-square test .

Icon

<!-- image -->

**Description**

The frequencies of two independent random numbers are compared with the frequencies of the observed data of the sample under consideration.

A sample consists of two groups of data, which must be contained on the table DataX. To insert the data into the object Independence , you can:

1. Drag a table object onto the object Independence and drop it there.
2. Use the object FileInterface .
3. Paste the data from the Windows clipboard.

Be sure to keep the decimal separator in mind. Since the test for continuous and discrete data is different, you must specify the Type of data on the tab Input of data.

Figure 11-76: Input data for the Chi-square independence test

<!-- image -->

The data in the first column are the x-values, the values in the second column are the y-values. Continuous data is divided into classes. Type in the number of classes for the x-values and the y-values on the tab Test for Continuous Data . After selecting these settings and clicking Apply, you can open the contingency table and the corresponding scatter diagram.

The following figures show a sample of two independent uniformly distributed samples. The black numbers on the right-hand side and on the bottom of the contingency table are the observed frequencies of the classes of the x-values and y-values. The blue numbers are the observed frequencies at which these classes cross. The hypothesis about the independence is true, when the observed crossing frequencies are approximately equal to the expected frequencies which result from the (black) frequencies of the classes. In this very simple example all 102 expected frequencies are 5*5/50 = 0.5.

To check the hypothesis, whether the two samples belong to independent random numbers, you have to type in the confidence level of the test on the tab Test for Continuous Data . Click Start . The tab then shows the result of the test.

Figure 11-77: Dialog box of the object Independence

<!-- image -->

#### TeamcenterWizard

