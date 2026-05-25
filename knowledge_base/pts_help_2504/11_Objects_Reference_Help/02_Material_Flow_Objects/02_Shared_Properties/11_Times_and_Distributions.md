#### Times and Distributions

Times and Distributions

Plant Simulation is a discrete simulation system. It is based on a variety of times, such as processing times, machine downtimes, set-up times, recovery times, etc. It enables true to life modeling with fixed times as well as with statistically distributed times.

**See also**

| Tab Times [general description] of the objects   | User-defined Distributions                  |
|--------------------------------------------------|---------------------------------------------|
| Model Random Processes                           | Bounding Probability Distribution Functions |

| Prepare Data for the Simulation with DataFit   | Parameters of the Distributions      |
|------------------------------------------------|--------------------------------------|
| Format of Time and Date                        | Methods of the Distributions         |
| Probability Distributions                      | Distribution Functions, z_ functions |
| Empirical Distributions                        |                                      |

##### Format of Time and Date

Plant Simulation handles data referring to times in the format 1:00:00:00.0000 , standing for, left to right, days:hours:minutes:seconds.split seconds . 12:34 for example, reads as 12 minutes and 34 seconds.

**Note**

If you do not want to write this out in full, you can also just type 1::: and click Apply . Then, Plant Simulation translates it to the full time format 1:00:00:00 .

You can also enter numbers without the colon. Plant Simulation then interprets the number as seconds and converts them into the above format. 111, for example, reads as 1 minute and 51 seconds.

When assigning an attribute of data type time to a variable of data type real or integer , Plant Simulation converts the value in seconds.

You can change time-related settings under File &gt; Model Settings/Preferences &gt; Units &gt; Time Scale .

<!-- image -->

**See also**

Specify Times in Object Dialogs

Time Scale [preferences]

Converting Time and Date Values

Probability Distributions

##### Probability Distributions

Plant Simulation provides a number of probability distributions (statistical distributions) in the drop-down lists on the tab Times .

<!-- image -->

| Type of the Distribution   | Name of the Distribution                    |
|----------------------------|---------------------------------------------|
| Const                      | Const [distribution]                        |
| Uniform                    | Uniform [distribution], z_uniform [SimTalk] |
| Normal                     | Normal [distribution], z_normal [SimTalk]   |

| Type of the Distribution   | Name of the Distribution                      |
|----------------------------|-----------------------------------------------|
| Lognorm                    | Lognorm [distribution], z_lognorm [SimTalk]   |
| Negexp                     | Negexp [distribution], z_negexp [SimTalk]     |
| Geom                       | Geom [distribution], z_geom [SimTalk]         |
| Hypgeo                     | Hypgeo [distribution], z_hypgeom [SimTalk]    |
| Erlang                     | Erlang [distribution], z_erlang [SimTalk]     |
| Weibull                    | Weibull [distribution], z_weibull [SimTalk]   |
| Triangle                   | Triangle [distribution], z_triangle [SimTalk] |
| Binomial                   | Binomial [distribution], z_binomial [SimTalk] |
| Poisson                    | Poisson [distribution]                        |
| Gamma                      | Gamma [distribution], z_gamma [SimTalk]       |
| Beta                       | Beta [distribution], z_beta [SimTalk]         |

Object-specific times, such as the Processing Time , the Set-up Time , the times of failures , etc. can take values according to these distributions.

You can select the type of probability distribution as well as the parameters of the distribution in the dialog of the object.

<!-- image -->

<!-- image -->

Assign a Distribution with z\_

Plant Simulation provides predefined Distribution Functions, z\_ functions that you can use in writing your own Methods .

```simtalk
a := z_normal(1,20,5)
```

Assign Additional Distributions

Within methods, you can also assign additional distributions, which are described under Distribution Functions, z\_ functions , and which you cannot select in the dialogs of the objects.

```simtalk
a := z_pareto(3,15,5)
```

Set Parameters with setTypeAndAttr

You can also set the parameters of a distribution with the method setTypeAndAttr or with the respective attributes in SimTalk .

MyStation.ProcTime.setAttrAndType("Normal", 30, 10) MyStation.SetupTime.setAttrAndType("Erlang", 0:05, 0:01, 0:01, 0:20) MyStation.RecoveryTime.setAttrAndType("cEmp", cEmpTable) MyStation.CycleTime.setAttrAndType("Formula","Variable2/20") MyGenerator.Duration.setAttrAndType("dEmp",2,empTable)

The Method and user-defined attributes of data type method have their own random number stream. You can set it with the attribute RandomSeed .

See also

Parameters of the Distributions

Bounding Probability Distribution Functions Methods of the Distributions Distribution Functions, z\_ functions , additional distributions

**Beta [distribution], z\_beta [SimTalk]**

###### Beta [distribution], z\_beta [SimTalk]

The beta distribution assumes a variety of shapes, depending on its parameters.

<!-- image -->

**Description**

The parameters of the distribution are described under Parameters of the Distributions .

You can use the beta distribution to model distributed quantities in your simulation model when you do not have sufficient data. You can, for example, model downtimes and repair times of machines, the number of rejects, or the processing time for an order.

The density of the beta distribution is

where 0 &lt; x &lt; 1 applies.

The expected value is µ =

The variance is

The beta distribution is a continuous distribution whose realizations are located between 0 and 1 ( real ).

Figure 11-2: Density functions of the beta distribution

<!-- image -->

You can also create the beta distribution with this SimTalk function:

```simtalk
z_beta([Stream:integer, ]Alpha1:real, Alpha2:real)
```

**Parameters**

- The parameter Stream , designating the random number stream, is optional. If you do not specify the stream, the random number stream of the Method object or of the user-defined attribute of data type Method will be used.

You can still call the distribution functions with the parameter for the random number stream as you did in previous versions. For formulas, it is required, as formulas never use the random number stream of the surrounding object.

- The parameters Alpha1 and Alpha2 are positive numbers. They have the data type real .

**See also**

Distribution Functions, z\_ functions

**Parameters of the Distributions Methods of the Distributions**

###### Binomial [distribution], z\_binomial [SimTalk]

The binomial distribution is a discrete distribution. The realizations are natural numbers.

<!-- image -->

**Description**

The parameters of the distribution are described under Parameters of the Distributions .

You can use the binomial distribution when you run the same experiment several times one after the other and when the results of the experiment are independent of each other.

An event of interest will occur during the simulation with a probability of p . If you repeat this test n times, the probability of an event of interest to occur k times is:

The formula stands for the binomial coefficient for n ≥ k ≥ 0.

The binomial distribution is realized by values ranging from 0, 1, …, n.

Figure 11-3: Probabilities of the binomial distribution with the parameters n=12 and p=0.35

<!-- image -->

You can also create the binomial distribution with this SimTalk function:

```simtalk
z_binomial([Stream:integer, ]n:integer, p:real)
```

**Parameters**

- The parameter Stream , designating the random number stream, is optional. If you do not specify the stream, the random number stream of the Method object or of the user-defined attribute of data type Method will be used.

You can still call the distribution functions with the parameter for the random number stream as you did in previous versions. For formulas, it is required, as formulas never use the random number stream of the surrounding object.

- The parameter n of data type integer designates the number of trials and has to be a positive number.
- The parameter p of data type real designates the probability of the event of interest to occur.

**Return Value**

The return value of the distribution is the number of trials of data type real .

Although the returned values are natural numbers, we do not return a value of data type integer , but a value of data type real , so that all distribution function return the same data type.

**See also**

Distribution Functions, z\_ functions

Parameters of the Distributions

Methods of the Distributions

**Const [distribution]**

###### Const [distribution]

The constant distribution uses the fixed time, which you type into the text box.

<!-- image -->

###### Erlang [distribution], z\_erlang [SimTalk]

The Erlang-distribution is the sum of k independent, exponentially distributed random numbers with the same parameter beta. The realizations are non-negative real numbers.

<!-- image -->

**Description**

The Erlang-distribution is especially suited for modeling failures.

The parameters of the distribution are described under Parameters of the Distributions .

The density function is:

<!-- image -->

Plant Simulation uses the mean µ = k · β and the standard deviation σ with σ 2  = k · β 2 . So

.

<!-- image -->

When selecting the values for the parameters Mu ( µ ) and Sigma ( σ ) make sure that the value for k actually is an integer number, otherwise the mean value you enter and the desired standard deviation will not result.

Figure 11-4: Density function of the Erlang-distribution

<!-- image -->

You can also create the Erlang-distribution with this SimTalk function:

```simtalk
z_erlang([Stream:integer, ]Mu:time, Sigma:time[, LowerBound:real, UpperBound:real])
```

**Parameters**

- The parameter Stream , designating the random number stream, is optional. If you do not specify the stream, the random number stream of the Method object or of the user-defined attribute of data type Method will be used.

You can still call the distribution functions with the parameter for the random number stream as you did in previous versions. For formulas, it is required, as formulas never use the random number stream of the surrounding object.

- The parameter Mu of data type time designates the mean value of the Erlang-distribution . It has to be a positive number.

**Note**

µ is spelled Mu in Plant Simulation , σ is spelled Sigma .

- The parameter Sigma of data type time designates standard deviation of the Erlang-distribution . It has to be a positive number.
- The optional parameter LowerBound of data type real designates the smallest value that the distribution can take.
- The optional parameter UpperBound of data type real designates the greatest value that the distribution can take.

**See also**

Distribution Functions, z\_ functions

Parameters of the Distributions

Methods of the Distributions

###### Gamma [distribution], z\_gamma [SimTalk]

The gamma distribution is a continuous distribution. Its realizations are non-negative real numbers.

<!-- image -->

**Description**

The parameters of the distribution are described under Parameters of the Distributions .

Its density function is defined as follows:

<!-- image -->

The expression Γ ( α ) is the gamma function ( α &gt; 0). A positive integer parameter α = k results in the Erlang -distribution.

Mean and variance of the gamma distribution are: µ = αβ and σ 2  = αβ 2 .

Figure 11-5: Density functions of the gamma distribution with a mean value of 1

<!-- image -->

You can also create the gamma distribution with this SimTalk function:

```simtalk
z_gamma([Stream:integer, ]Alpha:real, Beta:time[, LowerBound:real,
UpperBound:real])
```

**Parameters**

- The parameter Stream , designating the random number stream, is optional. If you do not specify the stream, the random number stream of the Method object or of the user-defined attribute of data type Method will be used.

You can still call the distribution functions with the parameter for the random number stream as you did in previous versions. For formulas, it is required, as formulas never use the random number stream of the surrounding object.

- The parameter Alpha of data type real is a positive number.
- The parameter Beta of data type time is a positive number. It sets the mean time in seconds between two events.
- The optional parameter LowerBound of data type real designates the smallest value that the distribution can take.

**Gamma [distribution], z\_gamma [SimTalk]**

- The optional parameter UpperBound of data type real designates the greatest value that the distribution can take.

Return Value

The return value is a real number.

See also

Distribution Functions, z\_ functions

Parameters of the Distributions

Methods of the Distributions

###### Geom [distribution], z\_geom [SimTalk]

The geometric distribution is a discrete distribution. The realizations are non-negative integer numbers.

<!-- image -->

**Description**

The parameters of the distribution are described under Parameters of the Distributions .

You can use the geometric distribution to determine how many parts are produced before the next reject.

The parameter p designates the probability of a reject . The value for p is located between 0 and 1, f(k) = p · (1-p) k is the probability that the (k+1) th  part is a reject.

Figure 11-6: Probabilities of the geometric distribution with the parameter p=0.5

<!-- image -->

You can also create the geometric distribution with this SimTalk function:

```simtalk
z_geom([Stream:integer, ]p:real[, LowerBound:real, UpperBound:real])
```

**Parameters**

- The parameter Stream , designating the random number stream, is optional. If you do not specify the stream, the random number stream of the Method object or of the user-defined attribute of data type Method will be used.

You can still call the distribution functions with the parameter for the random number stream as you did in previous versions. For formulas, it is required, as formulas never use the random number stream of the surrounding object.

- The parameter p of data type real designates the probability of a reject. The value for p is located between 0 and 1.
- The optional parameter LowerBound of data type real designates the smallest value that the distribution can take.
- The optional parameter UpperBound of data type real designates the greatest value that the distribution can take.

**See also**

Distribution Functions, z\_ functions

Parameters of the Distributions

Methods of the Distributions

###### Hypgeo [distribution], z\_hypgeom [SimTalk]

The hypergeometric distribution is a discrete distribution. Use it to draw n samples from a population of m . The realizations are non-negative integer numbers.

<!-- image -->

**Description**

The parameters of the distribution are described under Parameters of the Distributions .

A certain portion of the population is assumed to be special. This portion is called p; its value must be located between 0 and 1. Now, the random number of special items in a sample of size N is hypergeometrically distributed. For the numbers N and M the relation 0 &lt; N &lt; M must hold.

<!-- image -->

The probability that the sample contains k items of the special kind is

pM is the number of items of the special kind.

The mean is µ = N times P. The variance is

The lower bound is max(0,N-M+P·M) ; the upper bound is min(N,M·P) .

designates the binomial coefficient.

<!-- formula-not-decoded -->

Figure 11-7: Probabilities of the hypergeometric distribution with the parameters M=100, N=5, p=0.6

<!-- image -->

You can also create the hypergeometric distribution with this SimTalk function:

```simtalk
z_hypgeom([Stream:integer, ]m:integer, n:integer, p:real)
```

**Parameters**

- The parameter Stream , designating the random number stream, is optional. If you do not specify the stream, the random number stream of the Method object or of the user-defined attribute of data type Method will be used.

You can still call the distribution functions with the parameter for the random number stream as you did in previous versions. For formulas, it is required, as formulas never use the random number stream of the surrounding object.

- The parameter m of data type integer designates the existing population.
- The parameter n of data type integer designates the coverage of the drawn sample.
- The parameter p of data type real designates the portion of the parts.

**See also**

Distribution Functions, z\_ functions

**Parameters of the Distributions Methods of the Distributions**

###### Lognorm [distribution], z\_lognorm [SimTalk]

The log-normal distribution is a continuous distribution. It is the distribution of a random number whose natural logarithm corresponds to a normal distribution. The realizations are non-negative real numbers.

<!-- image -->

Description

The parameters of the distribution are described under Parameters of the Distributions .

You can use the log-normal distribution to model random numbers that are the product of a large number of random values, for example to describe the random time for realizing a project.

The lognormal distribution is especially suited for modeling failures.

The density is:

The parameters Mu ( µ ) and Sigma ( σ ) are the mean and the standard deviation of the lognormal distribution .

**Note**

µ is spelled Mu in Plant Simulation , σ is spelled Sigma .

The mean µ results from this formula:

The variance σ 0 is:

The maximum of the density function is defined as follows:

<!-- formula-not-decoded -->

For the values from the table below the density function of the lognormal distribution looks like this:

<!-- formula-not-decoded -->

.

<!-- image -->

You can also create the log-normal distribution with this SimTalk function:

```simtalk
z_lognorm([Stream:integer, ]Mu:time, Sigma:time[, LowerBound:real,
UpperBound:real])
```

**Parameters**

- The parameter Stream , designating the random number stream, is optional. If you do not specify the stream, the random number stream of the Method object or of the user-defined attribute of data type Method will be used.

You can still call the distribution functions with the parameter for the random number stream as you did in previous versions. For formulas, it is required, as formulas never use the random number stream of the surrounding object.

- The parameter Mu of data type time designates the mean value of the lognormal distribution .

**Lognorm [distribution], z\_lognorm [SimTalk]**

- The parameter Sigma of data type time designates standard deviation of the lognormal distribution . If a random number is lognormally distributed with the parameters Mu ( µ ) and Sigma ( σ ), then the natural logarithm of it is normally distributed with the parameters µ 0 and σ 0 .
- The optional parameter LowerBound of data type real designates the smallest value that the distribution can take.
- The optional parameter UpperBound of data type real designates the greatest value that the distribution can take.

**See also**

Distribution Functions, z\_ functions

Parameters of the Distributions

Methods of the Distributions

###### Negexp [distribution], z\_negexp [SimTalk]

The negative exponential distribution is a continuous distribution. It is called negative because of the negative sign of the exponent. The realizations are non-negative real numbers.

<!-- image -->

**Description**

The parameter Beta ( β ) designates the mean value. The parameter β has to be greater than 0. The variance of the exponential distribution is σ 2  = β 2 .

The parameter of the distribution is described under Parameters of the Distributions .

The exponential distribution plays an important role in reliability theory and in queuing theory.

The negative exponential distribution is especially suited for modeling failures.

You can use the negative exponential distribution to model the inter-arrival times of customers in a service system, the duration of a repair job or the absence of employees from their job site.

For x &gt; 0 the density function looks like this:

<!-- formula-not-decoded -->

Figure 11-8: Density function of the negexp distribution with a mean value of 2

<!-- image -->

You can also create the negative exponential distribution with this SimTalk function:

```simtalk
z_negexp([Stream:integer, ]Beta:time[, LowerBound:real, UpperBound:real])
```

**Parameter**

- The parameter Stream , designating the random number stream, is optional. If you do not specify the stream, the random number stream of the Method object or of the user-defined attribute of data type Method will be used.

You can still call the distribution functions with the parameter for the random number stream as you did in previous versions. For formulas, it is required, as formulas never use the random number stream of the surrounding object.

- The parameter Beta ( β ) of data type time designates the mean time in seconds between two events.
- The optional parameter LowerBound of data type real designates the smallest value that the distribution can take.
- The optional parameter UpperBound of data type real designates the greatest value that the distribution can take.

**See also**

Distribution Functions, z\_ functions

Parameters of the Distributions

Methods of the Distributions

###### Normal [distribution], z\_normal [SimTalk]

The normal distribution is a continuous distribution.

<!-- image -->

**Description**

Normal means that for a time query Plant Simulation rolls a number that corresponds to a normal distribution with the expected value Mu (µ) and the standard deviation Sigma (σ). As a rule of thumb 2/3 of all possible values are located within the interval [µσ , µ + σ ] .

The parameters of the distribution are described under Parameters of the Distributions .

**Note**

µ is spelled Mu in Plant Simulation , σ is spelled Sigma .

You can use the normal distribution to model random numbers that can be realized as the sum of a large number of random numbers, for example, to describe measuring errors.

The probability density of the normal distribution is

For these values for µ =350; σ =100, the probability for the rolled number to be located between 250 and 450 is 68 percent.

<!-- image -->

The mean value is µ and the variance is σ 2 . A normally distributed random number may be any real number. When using the normal distribution for the distribution of time values, such as processing times, be aware that the actual values for the mean value and the variance may differ significantly from µ or σ 2 by using the lower bound 0 (see LowerBound ).

Figure 11-9: Density functions of the normal distribution with a mean value of 5

<!-- image -->

You can also create the normal distribution with this SimTalk function:

```simtalk
z_normal([Stream:integer, ]Mu:time, Sigma:time[, LowerBound:real,
UpperBound:real])
```

**Parameters**

- The parameter Stream , designating the random number stream, is optional. If you do not specify the stream, the random number stream of the Method object or of the user-defined attribute of data type Method will be used.

You can still call the distribution functions with the parameter for the random number stream as you did in previous versions. For formulas, it is required, as formulas never use the random number stream of the surrounding object.

- The parameter Mu of data type time designates the mean value of the normal distribution .

- The parameter Sigma of data type time designates standard deviation of the normal distribution .
- The optional parameter LowerBound of data type real designates the smallest value that the distribution can take.
- The optional parameter UpperBound of data type real designates the greatest value that the distribution can take.

**Example**

```simtalk
var r: real := z_normal(1, 15, 5)
```

**See also**

Distribution Functions, z\_ functions

Parameters of the Distributions

Methods of the Distributions

###### Poisson [distribution], z\_poisson [SimTalk]

The Poisson-distribution is a discrete distribution. The realizations are natural numbers.

<!-- image -->

**Description**

The parameters of the distribution are described under Parameters of the Distributions .

You can use it when your modeling task requires a random number of events.

A certain integer positive value k will occur with the probability

Mean and variance are µ= σ 2 = λ .

You can use the Poisson-distribution to model a random number of events during a time interval of 1 second. The parameter λ designates the average number of events taking place in one second. If customers arrive with an exponentially distributed in-between arrival time with the parameter β , the

number of customers arriving per second is Poisson distributed with the parameter

<!-- formula-not-decoded -->

Figure 11-10: Probabilities of the Poisson-distribution with the parameter lambda=5

<!-- image -->

You can also create the Poisson-distribution with this SimTalk function:

```simtalk
z_poisson([Stream:integer, ]Lambda:real)
```

**Parameters**

- The parameter Stream , designating the random number stream, is optional. If you do not specify the stream, the random number stream of the Method object or of the user-defined attribute of data type Method will be used.

You can still call the distribution functions with the parameter for the random number stream as you did in previous versions. For formulas, it is required, as formulas never use the random number stream of the surrounding object.

- The parameter Lambda of data type real designates the average number of events per second. The parameter Lambda has to be greater than 0 , an upper bound does not exist.

**Return Value**

The return value k of data type real of the distribution is the number of events. Although the returned values are natural numbers, we do not return a value of data type integer , but a value of data type real , so that all distribution functions return the same data type.

**See also**

Distribution Functions, z\_ functions

Parameters of the Distributions

Methods of the Distributions

**Triangle [distribution], z\_triangle [SimTalk]**

###### Triangle [distribution], z\_triangle [SimTalk]

The triangular distribution is a continuous probability distribution.

<!-- image -->

**Description**

The triangular distribution is defined by these parameters: The most probable value c , the minimum value a and the maximum value b of the interval within which the random numbers are created.

The triangular distribution is called triangle distribution in Plant Simulation .

The parameters of the distribution are described under Parameters of the Distributions .

You can use the triangular distribution if not much is known about the distribution of a value.

The probability density function is:

The realizations of a triangularly distributed random number are located between a and b . The most frequent values are located in the vicinity of c .

The mean value Mu (µ) is defined as:

and the variance Sigma (σ) is:

Figure 11-11: Density function of the triangular distribution

<!-- image -->

You can also create the triangular distribution with this SimTalk function:

```simtalk
z_triangle([Stream:integer, ]c:real, a:real, b:real)
```

**Parameters**

- The parameter Stream , designating the random number stream, is optional. If you do not specify the stream, the random number stream of the Method object or of the user-defined attribute of data type Method will be used.

You can still call the distribution functions with the parameter for the random number stream as you did in previous versions. For formulas, it is required, as formulas never use the random number stream of the surrounding object.

- The parameter c of data type real designates the most probable value.
- The parameter a of data type real designates the minimum value.
- The parameter b of data type real designates the maximum value.

See also Distribution Functions, z\_ functions Parameters of the Distributions Methods of the Distributions

###### Uniform [distribution], z\_uniform [SimTalk]

The uniform distribution models a random number z that is located between the interval bounds lower bound and upper bound ( lower bound &lt; z &lt; upper bound ). Use it when not much is known about the random number.

<!-- image -->

Description

The parameters of the distribution are described under Parameters of the Distributions .

The probability density function of the uniform distribution :

<!-- image -->

<!-- formula-not-decoded -->

Figure 11-12: Density function of the uniform distribution

<!-- image -->

You can also create the uniform distribution with this SimTalk function:

z\_uniform([Stream:integer, ]LowerBound:real, UpperBound:real)

**Parameters**

- The parameter Stream , designating the random number stream, is optional. If you do not specify the stream, the random number stream of the Method object or of the user-defined attribute of data type Method will be used.

You can still call the distribution functions with the parameter for the random number stream as you did in previous versions. For formulas, it is required, as formulas never use the random number stream of the surrounding object.

- The generated values are always greater than the value specified by the parameter LowerBound of data type real .
- The generated values are always smaller than the value specified by the parameter UpperBound of data type real .

**See also**

Distribution Functions, z\_ functions

**Parameters of the Distributions**

##### Methods of the Distributions

Video on YouTube

[https://youtu.be/9g6Uou-8eMc?si=a3Fb7fVfUVAHVUQG&amp;t=1100](https://youtu.be/9g6Uou-8eMc?si=a3Fb7fVfUVAHVUQG&t=1100)

###### Weibull [distribution], z\_weibull [SimTalk]

Weibull [distribution], z\_weibull [SimTalk]

The Weibull distribution is a continuous distribution.

<!-- image -->

**Description**

The parameters of the distribution are described under Parameters of the Distributions .

You can use the Weibull distribution to model the reliability of your plant:

- Use α &lt; 1 to model the random life time of an plant with a decreasing failure rate. The probability of a failure to occur within a certain time interval decreases as time goes on. Burn-in failures will become more improbable the longer the machines work.
- α = 1 results in the exponential distribution. A random exponential life time describes an plant that does not age. The probability of a failure to occur is independent of the life time up to then.
- Use α &gt; 1 to model the random life time of an plant with an increasing failure rate. After running machines for a long time, wear-out failures occur, so that the probability of a failure within a time interval increases as the system ages. The life times that accrue most of the time are determined by the maximum of the density function (for α &gt; 1 ) and are roughly defined by the values

The Weibull distribution with the parameters α , β &gt; 0 has the distribution density

For x &gt; 0 the distribution function is

The mean value is

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

.

The expression Γ (x) designates the gamma function. The value x has to be greater than 0. Both parameters α and β of the Weibull distribution are positive numbers. Weibull -distributed random numbers always are positive numbers. α =1 results in the exponential distribution.

The parameter beta has the data type time .

Figure 11-13: Density functions of two Weibull-distributions with a mean value of about 2

<!-- image -->

You can also create the Weibull-distribution with this SimTalk function:

```simtalk
z_weibull([Stream:integer, ]Alpha:real, Beta:time[, LowerBound:real, UpperBound:real])
```

**Parameters**

- The parameter Stream , designating the random number stream, is optional. If you do not specify the stream, the random number stream of the Method object or of the user-defined attribute of data type Method will be used.

You can still call the distribution functions with the parameter for the random number stream as you did in previous versions. For formulas, it is required, as formulas never use the random number stream of the surrounding object.

- The parameter Alpha of data type real is a positive number.
- The parameter Beta of data type time designates the mean time in seconds between two events

##### User-defined Distributions

- The optional parameter LowerBound of data type real designates the smallest value that the distribution can take.
- The optional parameter UpperBound of data type real designates the greatest value that the distribution can take.

**See also**

Distribution Functions, z\_ functions

Parameters of the Distributions

Methods of the Distributions

User-defined Distributions

User-defined Distributions

Plant Simulation provides a number of user-defined distributions .

| Type of the Distribution   | Name of the Distribution                           |
|----------------------------|----------------------------------------------------|
| Formula                    | Formula [distribution]                             |
| List(Type)                 | List(Type) [distribution]                          |
| List(Place)                | List(Place) [distribution] ( ParallelStation )     |
| Matrix(Type)               | Matrix(Type) [distribution] for setting-up objects |

<!-- image -->

**See also**

Parameters of the Distributions

Methods of the Distributions

Empirical Distributions

Empirical Distributions

**Formula [distribution]**

###### Formula [distribution]

The formula distribution enables you to define the time generator yourself.

<!-- image -->

**Description**

You can enter any SimTalk expression into a formula: You can use the basic arithmetic operations and all functions, which Plant Simulation supports. You can also enter a Method which would then call the Method and use its result.

You can use the anonymous identifier ? to access the object that initiated the calculation. When computing the Set-up time and the Processing Time , you can also use the anonymous identifier @ to access the MU .

If you call one of the Distribution Functions, z\_ functions in the source code of the formula with z\_ , you have to enter the random number stream as formulas never use the random number stream of the surrounding object.

To address the object in a Method of the formula, it has to be passed as a parameter to this Method :

**Example**

```simtalk
// notation of a formula for the processing time -> time
var PartType: string := @.PartType
var Station: object := ?
var WorkPlan: table := root.myWorkPlan["Operations", PartType]
return WorkPlan["Processing time", Station]
```

**Note**

When using a formula, you may not use any actions, which interfere with the material flow, i.e., you may not transfer MUs , delete objects, etc. You may only use read-only access, you cannot change any simulation-relevant parameters of the model.

**Example**

```simtalk
-- set a formula with SimTalk
MyStation.setSubAttribute("ProcTime", "Type", "Formula")
MyStation.procTime.Formula := "x+2"
```

**See also**

Define Times in the Class of the Processing Stations

Parameters of the Distributions

Methods of the Distributions

**List(Place) [distribution]**

###### List(Place) [distribution]

The List(Place) distribution only applies when working with a ParallelStation with several processing places that have different, but constant processing times.

<!-- image -->

**Description**

Type in the name of the table into which you want to enter the required data. Clicking Apply in the dialog of the object automatically formats the table so that the data types of the columns match the parameters.

Within the table, the entry [1,3] matches the processing location at position [1,3] , for example.

<!-- image -->

When a MU arrives at a processing place on a ParallelStation during a simulation run, Plant Simulation takes the appropriate time for that processing place from the table.

See also

Parameters of the Distributions

Methods of the Distributions

###### List(Type) [distribution]

The List(Type) distribution enables you to determine the times depending on the type of MU .

<!-- image -->

Type in the name of the table into which you want to enter the required data. Clicking Apply in the dialog of the object automatically formats the table so that the data types of the columns match the parameters.

<!-- image -->

- From Plant Simulation 16.1 on the DataTable has four columns by default. The first column contains the MU type , the second column the name of the Attribute , the third column the Value and the fourth column the respective Time . When Plant Simulation determines the time for a part, it first compares the name of the MU type in each row.

If it matches, it gets the value of the attribute of the second column and compares it with the value in the third column. If necessary if converts the value of the attribute to a string. If this comparison matches as well, Plant Simulation returns the time value from the fourth column. If you entered an asterisk * for the name of the MU type , the comparison always is true.

<!-- image -->

When you type in an asterisk * for the MU Type and Plant Simulation recognizes it, it returns the time in this row. If, for example, you use 8 MU types named A,B,C, etc. and you only need a special processing time for A, you can type in the value for A into the first row of the DataTable and define the processing times for all other part types in the second row by entering an * as the MU Type . This entry should

- always be the last in the DataTable as Plant Simulation checks the entries one after the other and uses the time of the row in which it recognizes an asterisk * .
- In previous versions of Plant Simulation the DataTable had two columns. You can still use this table. Type in all possible MU Types into column 1. Type in the respective Times in seconds into column 2. Depending on the selected time it can be the Processing Time or the Set-up Time .

<!-- image -->

During the simulation Plant Simulation determines the respective time when a part arrives. If the list does not exist, Plant Simulation shows an error message.

**See also**

Parameters of the Distributions

Methods of the Distributions

###### Matrix(Type) [distribution]

The Matrix(Type) distribution only applies to the Set-up Time .

**Description**

When setting a station up the time may not only depend on the target type, for which you want to set up, but also from the source type. In this case you can define the times in a table.

<!-- image -->

Type in the name of the table into which you want to enter the required data. Clicking Apply in the dialog of the object automatically formats the table so that the data types of the columns match the parameters. The row index designates the source type. The column index designates the target type.

In our example setting-up from no type, indicated by the hyphen ( -), to the target type Part takes exactly 1 minute. Setting-up from the type Entity to the type Transporter takes 2 minutes and 7 seconds.

<!-- image -->

##### Empirical Distributions

See also

Set-up Time [general description]

Parameters of the Distributions

Methods of the Distributions

Empirical Distributions

Empirical Distributions

Plant Simulation provides a number of empirical distributions .

| Type of the Distribution                                   | Name of the Distribution          |
|------------------------------------------------------------|-----------------------------------|
| dEmp [discrete empirical distribution], z_dEmp [SimTalk]   | Discrete empirical distribution   |
| cEmp [continuous empirical distribution], z_cEmp [SimTalk] | Continuous empirical distribution |
| Emp [primitive empirical distribution], z_emp [SimTalk]    | Primitive empirical distribution  |

You can use the empirical distributions when your data cannot be represented properly by a mathematical distribution.

<!-- image -->

Plant Simulation computes a random variable with a distribution following the observed frequency of the data according to a set of observed data x\_1, …, x\_n . You have to enter the input data into a frequency table.

The Method and user-defined attributes of data type method have their own random number stream. You can set it with the attribute RandomSeed .

See also Distribution Functions, z\_ functions Parameters of the Distributions Methods of the Distributions Probability Distributions User-defined Distributions

###### cEmp [continuous empirical distribution], z\_cEmp [SimTalk]

For the continuous empirical distribution the input data is preprocessed and grouped into k classes. Each class contains all samples within a given interval. The k intervals are disjoint but not necessarily adjacent.

<!-- image -->

**Description**

The interval includes the left bound but not the right bound. If the left bound is equal to the right bound, the interval degenerates to a point. This special case is of interest if the probability of a single point is non-zero.

Type in the name of the table into which you enter the required data. Clicking Apply in the dialog of the object automatically formats the table so that the data types of the columns match the parameters.

Type in the left bound into the first column of the frequency table, type in the right bound into the second column. The third column contains the frequency of the corresponding intervals. The data type of the third column has to be real , time , or integer . The number of values of the input data contained in an interval can be used as frequency, for example.

<!-- image -->

You can also create the continuous empirical distribution with this SimTalk function:

```simtalk
z_cEmp([Stream:integer, ]Table:table[time,time,real])
```

**Parameters**

- The parameter Stream , designating the random number stream, is optional. If you do not specify the stream, the random number stream of the Method object or of the user-defined attribute of data type Method will be used.

You can still call the distribution functions with the parameter for the random number stream as you did in previous versions. For formulas, it is required, as formulas never use the random number stream of the surrounding object.

- The parameter of data type Table designates the frequency table.

You can also specify a subtable, for example "MyDataTable[2,3]" . The frequency table has to have the data type table and the subtable has to be formatted correctly for the empirical distribution.

See also

Parameters of the Distributions

Methods of the Distributions

Distribution Functions, z\_ functions

###### dEmp [discrete empirical distribution], z\_dEmp [SimTalk]

dEmp [discrete empirical distribution], z\_dEmp [SimTalk]

Use the discrete empirical distribution if the random numbers are real or integer numbers. Type the Time into column 1 and the respective Frequency into column 2 of a table with two columns.

<!-- image -->

Description

The relative frequency will be used as an empirical estimate for the probability of the respective value to appear.

Type in the name of an existing table into which you enter the required data. Clicking Apply in the dialog of the object automatically formats the table so that the data types of the columns match the parameters.

<!-- image -->

You can also create the discrete empirical distribution with this SimTalk function:

<!-- image -->

**Parameters**

- The parameter Stream , designating the random number stream, is optional. If you do not specify the stream, the random number stream of the Method object or of the user-defined attribute of data type Method will be used.

You can still call the distribution functions with the parameter for the random number stream as you did in previous versions. For formulas, it is required, as formulas never use the random number stream of the surrounding object.

- The parameter of data type Table designates the frequency table.

You can also specify a subtable, for example "MyDataTable[2,3]" . The frequency table has to have the data type table and the subtable has to be formatted correctly for the empirical distribution.

**See also**

Parameters of the Distributions

Methods of the Distributions

Distribution Functions, z\_ functions

###### Emp [primitive empirical distribution], z\_emp [SimTalk]

Use the primitive empirical distribution to randomly sample discrete times.

<!-- image -->

**Description**

The random numbers, which Plant Simulation generates, are located in the range between 1 and the y-dimension of the frequency table. The values in the table can be of data type real , time , or integer . The contents of a cell in row i of this table is the frequency that the random number i occurs. The value in row 5 is the number of times the value 5 occurred.

**Note**

If all frequencies are 0 , Plant Simulation always returns the value of the first row of the frequency table.

If you need an integer random number, whose realizations are located in the range between two positive integer numbers a and b, create a column with b entries. The first (a - 1) entries are 0.

Type in the name of the table into which you enter the required data. Clicking Apply in the dialog of the object automatically formats the table so that the data types of the columns match the parameters.

<!-- image -->

You can also create the primitive empirical distribution with this SimTalk function:

```simtalk
z_emp([Stream:integer, ]Table:table, Column:integer)
```

**Parameters**

- The parameter Stream , designating the random number stream, is optional. If you do not specify the stream, the random number stream of the Method object or of the user-defined attribute of data type Method will be used.

You can still call the distribution functions with the parameter for the random number stream as you did in previous versions. For formulas, it is required, as formulas never use the random number stream of the surrounding object.

- The parameter Table designates the path to a table or an attribute of data type table .
- The parameter Column of data type integer designates the column containing the frequency data.

**See also**

Parameters of the Distributions

Methods of the Distributions

Distribution Functions, z\_ functions

##### Bounding Probability Distribution Functions

Using random numbers may cause Plant Simulation to determine unrealistic values. Specify upper and lower bounds to prevent that from happening. Plant Simulation will then discard numbers outside of these bounds and roll a new value.

If the interval between lower bound and upper bound is very small, the values will have to be determined quite often before they are located within the interval. Type in the maximum number of samples under File &gt; Model Settings/Preferences &gt; Simulation &gt; Maximum number of samples .

<!-- image -->

Within Methods , Plant Simulation accesses the bounds with the sub-attributes UpperBound and LowerBound .

You can use the attributes LowerBound and UpperBound to set or query the type of distribution of an attribute .

**Parameters of the Distributions**

##### Parameters of the Distributions

The statistical distributions in Plant Simulation provide different parameters .

| a [SimTalk]          | Mu [SimTalk]         |
|----------------------|----------------------|
| Alpha [SimTalk]      | n [SimTalk]          |
| Alpha1 [SimTalk]     | p [SimTalk]          |
| Alpha2 [SimTalk]     | Sigma [SimTalk]      |
| b [SimTalk]          | Start [SimTalk]      |
| Beta [SimTalk]       | Stop [SimTalk]       |
| c [SimTalk]          | Stream [SimTalk]     |
| Lambda [SimTalk]     | Theta [SimTalk]      |
| LowerBound [SimTalk] | Type [SimTalk]       |
| m[SimTalk]           | UpperBound [SimTalk] |

###### Parameters of the Individual Distributions

You can assign the following parameters to the individual distributions:

| Type of the Distribution      | Set of parameters                               | Range of values for the parameters                        |
|-------------------------------|-------------------------------------------------|-----------------------------------------------------------|
| Beta                          | Alpha1 , Alpha2                                 | Alpha1 > 0, Alpha2 > 0                                    |
| Binomial                      | n , p                                           | integer n > 0, 0 p 1                                      |
| Cauchy                        | Stream , Mu , Theta , LowerBound , UpperBound   | Mu can be any value, Theta > 0, Upper Bound > Lower Bound |
| Constant                      | Value                                           | Value ≥ 0                                                 |
| (cEmp) [continuous empirical] | List                                            | -                                                         |
| (dEmp) [discrete empirical]   | List                                            | -                                                         |
| (Emp) [primitive empirical]   | List, Column                                    | -                                                         |
| Erlang                        | Mu , Sigma , LowerBound , UpperBound            | Mu > 0, Sigma > 0, Upper Bound > Lower Bound              |
| Formula                       | Formula                                         | -                                                         |
| Fréchet                       | Stream , Mu , Theta , LowerBound , UpperBound   | Mu > 0, Theta > 0, Upper Bound > Lower Bound              |
| Gamma                         | Alpha , Beta , LowerBound , UpperBound          | Alpha > 0, Beta > 0, Upper Bound > Lower Bound            |
| Geom [geometric]              | p , LowerBound , UpperBound                     | 0 p 1, Upper Bound > Lower Bound                          |
| Gumbel                        | Stream , Mu , Theta , LowerBound , UpperBound   | Mu > 0, Theta > 0, Upper Bound > Lower Bound              |
| Hypgeo [hypergeometric]       | m , n , p                                       | 1 > n > m, 0 p 1                                          |
| Laplace                       | Stream, Mu , Sigma , LowerBound , UpperBound    | Mu can be any value, Sigma > 0, Upper Bound > Lower Bound |
| List(Place)                   | Table                                           | -                                                         |
| List(Type)                    | Table                                           | -                                                         |
| Logistic                      | Stream , Mu , Sigma , LowerBound , UpperBound   | Mu can be any value, Sigma > 0, Upper Bound >Lower Bound  |
| Loglogistic                   | Stream , Alpha , Beta , LowerBound , UpperBound | Alpha > 0, Beta > 0, Upper Bound > Lower Bound            |
| Lognormal                     | Mu , Sigma , LowerBound , UpperBound            | Mu > 0, Sigma > 0, Upper Bound > Lower Bound              |
| Matrix(Type)                  | Table                                           | -                                                         |

| Type of the Distribution      | Set of parameters                                | Range of values for the parameters                        |
|-------------------------------|--------------------------------------------------|-----------------------------------------------------------|
| Negexp [negative exponential] | Beta , LowerBound , UpperBound                   | Beta > 0, Upper Bound > Lower Bound                       |
| Normal                        | Mu , Sigma , LowerBound , UpperBound             | Mu can be any value, Sigma > 0, Upper Bound > Lower Bound |
| Paralogistic                  | Stream , Alpha , Theta , LowerBound , UpperBound | Alpha > 0, Theta > 0, Upper Bound > Lower Bound           |
| Pareto                        | Stream , Alpha , Theta , LowerBound , UpperBound | Alpha > 0, Theta > 0, Upper Bound > Lower Bound           |
| Poisson                       | Lambda                                           | Lambda > 0                                                |
| Triangle [triangular]         | c , a , b                                        | a > c > b                                                 |
| Uniform                       | LowerBound , UpperBound                          | Lower Bound > Upper Bound                                 |
| Weibull                       | Alpha , Beta , LowerBound , UpperBound           | Alpha > 0, Beta > 0, Upper Bound > Lower Bound            |

**Example**

```simtalk
// Uniform
Station1.ProcTime.LowerBound := 10
Station1.ProcTime.UpperBound := 30 // Normal
Station2.ProcTime.Mu := 11
Station2.ProcTime.Sigma := 31
Station2.ProcTime.LowerBound := 1
Station2.ProcTime.UpperBound := 60 // Lognorm
Station3.ProcTime.Mu := 11
Station3.ProcTime.Sigma := 31
Station3.ProcTime.LowerBound := 1
Station3.ProcTime.UpperBound := 60 // Negexp
Station4.ProcTime.Beta := 11
Station4.ProcTime.LowerBound := 1
Station4.ProcTime.UpperBound := 60 // Geom
Station5.ProcTime.p := 0.6
Station5.ProcTime.LowerBound := 1
Station5.ProcTime.UpperBound := 60 // Hypgeo
Station6.ProcTime.m := 1
Station6.ProcTime.n := 1
Station6.ProcTime.p := 0.6 // Erlang
Station7.ProcTime.Mu := 11
Station7.ProcTime.Sigma := 31
Station7.ProcTime.LowerBound := 1
Station7.ProcTime.UpperBound := 60 // Weibull
Station8.ProcTime.Alpha := 1
Station8.ProcTime.Beta := 1
Station8.ProcTime.LowerBound := 1
Station8.ProcTime.UpperBound := 60 // Triangle
Station9.ProcTime.c := 20
Station9.ProcTime.a := 10
Station9.ProcTime.b := 30 // Binomial
Station10.ProcTime.n := 1
Station10.ProcTime.p := 0.5 // Poisson
Station11.ProcTime.Lambda := 0.5 // Gamma
Station12.ProcTime.Alpha := 1
Station12.ProcTime.Beta := 1
Station12.ProcTime.LowerBound := 0
Station12.ProcTime.UpperBound := 60 // Beta
Station13.ProcTime.Alpha1 := 1
Station13.ProcTime.Alpha2 := 1 // dEmp
Station14.ProcTime.Table := DataTable1 // cEmp
Station15.ProcTime.Table := DataTable2 // Emp
Station16.ProcTime.Table := DataTable3
Station16.ProcTime.Column := 1 // Formula
Station17.ProcTime.Formula := "z_uniform(1,1,10)" // List(Type)
Station18.ProcTime.Table := DataTable4 // List(Place)
ParallelStation.ProcTime.Table := DataTable5
```

See also Methods of the Distributions Probability Distributions Empirical Distributions Distribution Functions, z\_ functions User-defined Distributions

Bounding Probability Distribution Functions

###### a [SimTalk]

The parameter a sets the minimum value of the triangular distribution .

Syntax

&lt; Path &gt;.&lt;Attribute&gt;.a:time

**Parameters**

You can assign the following parameters to this distribution:

| Distribution                                  | Set of parameters   | Range of values for the parameters   |
|-----------------------------------------------|---------------------|--------------------------------------|
| Triangle [distribution], z_triangle [SimTalk] | c , a, b            | a > c > b                            |

**Assignment Value**

You can assign a value of data type time .

**Alpha [SimTalk]**

###### Alpha [SimTalk]

The parameter Alpha is a positive number used in a distribution.

**Syntax**

&lt; Path &gt;.&lt;Attribute&gt;.Alpha:real

**Parameters**

You can assign the following parameters to these distributions:

| Distribution   | Set of parameters                               | Range of values for the parameters              |
|----------------|-------------------------------------------------|-------------------------------------------------|
| Gamma          | Alpha, Beta , LowerBound , UpperBound           | Alpha > 0, Beta > 0, Upper Bound > Lower Bound  |
| Loglogistic    | Stream , Alpha, Beta , LowerBound , UpperBound  | Alpha > 0, Beta > 0, Upper Bound > Lower Bound  |
| Paralogistic   | Stream , Alpha, Theta , LowerBound , UpperBound | Alpha > 0, Theta > 0, Upper Bound > Lower Bound |
| Pareto         | Stream , Alpha, Theta , LowerBound , UpperBound | Alpha > 0, Theta > 0, Upper Bound > Lower Bound |
| Weibull        | Alpha, Beta , LowerBound , UpperBound           | Alpha > 0, Beta > 0, Upper Bound > Lower Bound  |

**Assignment Value**

You can assign a value of data type real .

###### Alpha1 [SimTalk]

The parameter Alpha1 is a positive number used in a distribution.

Syntax

&lt; Path &gt;.&lt;Attribute&gt;.Alpha1:real

**Parameters**

You can assign the following parameters to this distribution:

| Distribution                          | Set of parameters   | Range of values for the parameters   |
|---------------------------------------|---------------------|--------------------------------------|
| Beta [distribution], z_beta [SimTalk] | Alpha1, Alpha2      | Alpha1 > 0, Alpha2 > 0               |

**Assignment Value**

You can assign a value of data type real .

**Alpha2 [SimTalk]**

###### Alpha2 [SimTalk]

The parameter Alpha2 is a positive number used in a distribution.

**Syntax**

&lt; Path &gt;.&lt;Attribute&gt;.Alpha2:real

**Parameters**

You can assign the following parameters to this distribution:

| Distribution                          | Set of parameters   | Range of values for the parameters   |
|---------------------------------------|---------------------|--------------------------------------|
| Beta [distribution], z_beta [SimTalk] | Alpha1 , Alpha2     | Alpha1 > 0, Alpha2 > 0               |

**Assignment Value**

You can assign a value of data type real .

###### b [SimTalk]

The parameter b sets the maximum value of the triangular distribution .

Syntax

&lt; Path &gt;.&lt;Attribute&gt;.b:time

**Parameters**

You can assign the following parameters to this distribution:

| Distribution                                  | Set of parameters   | Range of values for the parameters   |
|-----------------------------------------------|---------------------|--------------------------------------|
| Triangle [distribution], z_triangle [SimTalk] | c , a , b           | a > c > b                            |

**Assignment Value**

You can assign a value of data type time .

**Beta [SimTalk]**

###### Beta [SimTalk]

The parameter Beta sets the mean time in seconds between two events in a distribution. It is a positive number.

Syntax

&lt; Path &gt;.&lt;Attribute&gt;.Beta:time

**Parameters**

You can assign the following parameters to these distributions:

| Distribution                                        | Set of parameters                             | Range of values for the parameters             |
|-----------------------------------------------------|-----------------------------------------------|------------------------------------------------|
| Gamma [distribution], z_gamma [SimTalk]             | Alpha , Beta, LowerBound , UpperBound         | Alpha > 0, Beta > 0, Upper Bound > Lower Bound |
| Loglogistic [distribution], z_loglogistic [SimTalk] | Stream, Alpha , Beta, LowerBound , UpperBound | Alpha > 0, Beta > 0, Upper Bound > Lower Bound |
| Negexp [distribution], z_negexp [SimTalk]           | Beta, LowerBound , UpperBound                 | Beta > 0, Upper Bound > Lower Bound            |
| Weibull [distribution], z_weibull [SimTalk]         | Alpha , Beta, LowerBound , UpperBound         | Alpha > 0, Beta > 0, Upper Bound > Lower Bound |

**Assignment Value**

You can assign a value of data type time .

###### c [SimTalk]

The parameter c sets the most probable value of the triangular distribution .

Syntax

&lt; Path &gt;.&lt;Attribute&gt;.c:time

**Parameters**

You can assign the following parameters to this distribution:

| Distribution                                  | Set of parameters   | Range of values for the parameters   |
|-----------------------------------------------|---------------------|--------------------------------------|
| Triangle [distribution], z_triangle [SimTalk] | c, a , b            | a > c > b                            |

**Assignment Value**

You can assign a value of data type time .

**Lambda [SimTalk]**

###### Lambda [SimTalk]

The parameter Lambda sets the average number of events per second in a distribution.

**Syntax**

&lt; Path &gt;.&lt;Attribute&gt;.Lambda:integer

**Parameters**

You can assign the following parameters to this distribution:

| Distribution                                | Set of parameters   | Range of values for the parameters   |
|---------------------------------------------|---------------------|--------------------------------------|
| Poisson [distribution], z_poisson [SimTalk] | Lambda              | Lambda > 0                           |

**Assignment Value**

You can assign a value of data type integer .

###### LowerBound [SimTalk] - distribution parameter

The parameter LowerBound sets the smallest value to be sampled from a distribution.

When Plant Simulation encounters a smaller number, it keeps drawing samples until a value equal to or larger than the LowerBound results. The LowerBound has to be less than the UpperBound .

If both UpperBound and LowerBound are zero, an unlimited distribution results.

Syntax

< Path >.<Attribute>.LowerBound:time

**Parameters**

You can assign the following parameters to these distributions:

| Distribution                                | Set of parameters                     | Range of values for the parameters                        |
|---------------------------------------------|---------------------------------------|-----------------------------------------------------------|
| Erlang [distribution], z_erlang [SimTalk]   | Mu , Sigma , LowerBound, UpperBound   | Mu > 0, Sigma > 0, Upper Bound > Lower Bound              |
| Gamma [distribution], z_gamma [SimTalk]     | Alpha , Beta , LowerBound, UpperBound | Alpha > 0, Beta > 0, Upper Bound > Lower Bound            |
| Geometric                                   | p , LowerBound, UpperBound            | 0 p 1, Upper Bound > Lower Bound                          |
| Lognorm [distribution], z_lognorm [SimTalk] | Mu , Sigma , LowerBound, UpperBound   | Mu > 0, Sigma > 0, Upper Bound > Lower Bound              |
| Negexp [distribution], z_negexp [SimTalk]   | Beta , LowerBound, UpperBound         | Beta > 0, Upper Bound > Lower Bound                       |
| Normal [distribution], z_normal [SimTalk]   | Mu , Sigma , LowerBound, UpperBound   | Mu can be any value, Sigma > 0, Upper Bound > Lower Bound |
| Weibull [distribution], z_weibull [SimTalk] | Alpha , Beta , LowerBound, UpperBound | Alpha > 0, Beta > 0, Upper Bound > Lower Bound            |

**Assignment Value**

You can assign a value of data type time .

**Example**

```simtalk
MyTrack.proctime.Type := "normal"
MyTrack.proctime.Mu := 60.0
MyTrack.proctime.Sigma := 30.0
MyTrack.proctime.LowerBound := 20.0 // no value below 20 seconds
```

###### m [SimTalk]

The parameter m sets the existing population of a distribution.

Syntax

&lt; Path &gt;.&lt;Attribute&gt;.m:integer

**Parameters**

You can assign the following parameters to this distribution:

| Distribution                               | Set of parameters   | Range of values for the parameters   |
|--------------------------------------------|---------------------|--------------------------------------|
| Hypgeo [distribution], z_hypgeom [SimTalk] | m, n , p            | 1 > n > m, 0 > p > 1                 |

**Assignment Value**

You can assign a value of data type integer .

Mu [SimTalk] - distribution parameter

The parameter Mu sets the mean value of a distribution.

Syntax

&lt; Path &gt;.&lt;Attribute&gt;.Mu:time

**Parameters**

You can assign the following parameters to these distributions:

| Distribution                                | Set of parameters                   | Range of values for the parameters                        |
|---------------------------------------------|-------------------------------------|-----------------------------------------------------------|
| Erlang [distribution], z_erlang [SimTalk]   | Mu, Sigma , LowerBound , UpperBound | Mu > 0, Sigma > 0, Upper Bound > Lower Bound              |
| Lognorm [distribution], z_lognorm [SimTalk] | Mu, Sigma , LowerBound , UpperBound | Mu > 0, Sigma > 0, Upper Bound > Lower Bound              |
| Normal [distribution], z_normal [SimTalk]   | Mu, Sigma , LowerBound , UpperBound | Mu can be any value, Sigma > 0, Upper Bound ≥ Lower Bound |

Assignment Value

You can assign a value of data type time .

###### n [SimTalk]

The parameter n sets the number of trials which the distribution attempts.

Syntax

&lt; Path &gt;.&lt;Attribute&gt;.n:integer

**Parameters**

You can assign the following parameters to these distributions:

| Distribution                                  | Set of parameters   | Range of values for the parameters   |
|-----------------------------------------------|---------------------|--------------------------------------|
| Binomial [distribution], z_binomial [SimTalk] | n, p                | integer n > 0, 0 p 1                 |
| Hypgeo [distribution], z_hypgeom [SimTalk]    | m , n, p            | 1 > n > m, 0 p 1                     |

**Assignment Value**

You can assign a value of data type integer .

**p [SimTalk]**

###### p [SimTalk]

The parameter p sets the probability of the event of interest to occur of a distribution.

Syntax

&lt; Path &gt;.&lt;Attribute&gt;.p:real

**Parameters**

You can assign the following parameters to these distributions:

| Distribution                                  | Set of parameters          | Range of values for the parameters   |
|-----------------------------------------------|----------------------------|--------------------------------------|
| Binomial [distribution], z_binomial [SimTalk] | n , p                      | integer n > 0, 0 p 1                 |
| Geom [distribution], z_geom [SimTalk]         | p, LowerBound , UpperBound | 0 p 1, Upper Bound > Lower Bound     |
| Hypgeo [distribution], z_hypgeom [SimTalk]    | m , n , p                  | 1 > n > m, 0 p 1                     |

**Assignment Value**

You can assign a value of data type real .

###### Sigma [SimTalk]

The parameter Sigma sets the standard deviation of a distribution.

**Syntax**

&lt; Path &gt;.&lt;Attribute&gt;.Sigma:time

**Parameters**

You can assign the following parameters to these distributions:

| Distribution                                  | Set of parameters                            | Range of values for the parameters                        |
|-----------------------------------------------|----------------------------------------------|-----------------------------------------------------------|
| Erlang [distribution], z_erlang [SimTalk]     | Mu , Sigma, LowerBound , UpperBound          | Mu > 0, Sigma > 0, Upper Bound > Lower Bound              |
| Laplace [distribution], z_laplace [SimTalk]   | Stream , Mu , Sigma, LowerBound , UpperBound | Mu can be any value, Sigma > 0, Upper Bound > Lower Bound |
| Logistic [distribution], z_logistic [SimTalk] | Stream , Mu , Sigma, LowerBound , UpperBound | Mu can be any value, Sigma > 0, Upper Bound > Lower Bound |
| Lognorm [distribution], z_lognorm [SimTalk]   | Mu , Sigma, LowerBound , UpperBound          | Mu > 0, Sigma > 0, Upper Bound > Lower Bound              |
| Normal [distribution], z_normal [SimTalk]     | Mu , Sigma, LowerBound , UpperBound          | Mu can be any value, Sigma > 0, Upper Bound > Lower Bound |

**Assignment Value**

You can assign a value of data type time .

Start [SimTalk] - distribution parameter

The parameter Start sets the starting point of the interval of a distribution.

**Syntax**

&lt; Path &gt;.&lt;Attribute&gt;.Start:time

**Parameters**

You can assign the following parameters to this distribution:

| Distribution                                | Set of parameters   | Range of values for the parameters   |
|---------------------------------------------|---------------------|--------------------------------------|
| Uniform [distribution], z_uniform [SimTalk] | Start, Stop         | Start > Stop                         |

**Assignment Value**

You can assign a value of data type time .

Stop [SimTalk] - distribution parameter

The parameter Stop sets the end point of the interval of a distribution.

Syntax

&lt; Path &gt;.&lt;Attribute&gt;.Stop:time

**Parameters**

You can assign the following parameters to this distribution:

| Distribution                                | Set of parameters   | Range of values for the parameters   |
|---------------------------------------------|---------------------|--------------------------------------|
| Uniform [distribution], z_uniform [SimTalk] | Start , Stop        | Start > Stop                         |

Assignment Value

You can assign a value of data type time .

Stream [SimTalk] - distribution parameter

The optional parameter Stream sets the random number stream of a distribution.

The parameter Stream of data type integer designates the random number stream (compare Random Number Seed Values ).

Remarks

If you call one of the distribution functions in a Method , the parameter Stream is optional. If you do not specify the stream, Plant Simulation uses the random number stream of the Method or of the user-defined attribute of data type method .

You can also call the distribution functions with the parameter Stream . For formulas this is required, as formulas never use the random number stream of the surrounding object.

The random number sequences, which are generated by the random number streams of the Methods , differ from the random number sequences of the global random number streams, whose seed values you can set under File &gt; Options &gt; Random Number Seed Values even if they have the same random number seed value.

Syntax

```simtalk
[< Path >.<Attribute>.[Stream:integer]]
```

Assignment Value

You can assign a value of data type integer .

###### Theta [SimTalk]

The parameter Theta designates an unknown parameter in a distribution. It is a number greater than 0.

**Syntax**

&lt; Path &gt;.&lt;Attribute&gt;.Theta:real

**Parameters**

You can assign the following parameters to these distributions:

| Distribution                                          | Set of parameters                               | Range of values for the parameters                        |
|-------------------------------------------------------|-------------------------------------------------|-----------------------------------------------------------|
| Cauchy [distribution], z_cauchy [SimTalk]             | Stream , Mu , Theta, LowerBound , UpperBound    | Mu can be any value, Theta > 0, Upper Bound > Lower Bound |
| Fréchet [distribution], z_frechet [SimTalk]           | Stream , Mu , Theta, LowerBound , UpperBound    | Mu > 0, Theta > 0, Upper Bound > Lower Bound              |
| Gumbel [distribution], z_gumbel [SimTalk]             | Stream , Mu , Theta, LowerBound , UpperBound    | Mu > 0, Theta > 0, Upper Bound > Lower Bound              |
| Paralogistic [distribution], z_paralogistic [SimTalk] | Stream , Alpha , Theta, LowerBound , UpperBound | Alpha > 0, Theta > 0, Upper Bound > Lower Bound           |
| Pareto [distribution], z_pareto [SimTalk]             | Stream , Alpha , Theta, LowerBound , UpperBound | Alpha > 0, Theta > 0, Upper Bound > Lower Bound           |

**Assignment Value**

You can assign a value of data type real .

###### Type [SimTalk] - distribution parameter

The sub-parameter Type sets the type of the probability distribution for the addressed parameters. &lt; Attribute-path &gt; designates a parameter of data type time or a user-defined attribute of data type randtime .

| Distribution                                                            | Name in Plant Simulation English/German   |
|-------------------------------------------------------------------------|-------------------------------------------|
| Beta [distribution], z_beta [SimTalk]                                   | Beta/Beta                                 |
| Binomial [distribution], z_binomial [SimTalk]                           | Binomial/Binomial                         |
| Const [distribution]                                                    | Const/Konst                               |
| cEmp [continuous empirical distribution], z_cEmp [SimTalk] distribution | cEmp/cEmp                                 |
| dEmp [discrete empirical distribution], z_dEmp [SimTalk] distribution   | dEmp/dEmp                                 |
| Erlang [distribution], z_erlang [SimTalk]                               | Erlang/Erlang                             |
| Formula [distribution]                                                  | Formula/Formel                            |
| Gamma [distribution], z_gamma [SimTalk]                                 | Gamma/Gamma                               |
| Geom [distribution], z_geom [SimTalk]                                   | Geom/Geom                                 |
| Hypgeo [distribution], z_hypgeom [SimTalk] distribution                 | Hypgeo/Hypgeo                             |
| List-dependent distribution ( ParallelStation )                         | List(Place) [distribution]                |
| Lognorm [distribution], z_lognorm [SimTalk]                             | Lognorm/Lognorm                           |
| Matrix distribution for setting-up objects                              | Matrix(Type) [distribution]               |
| Negexp [distribution], z_negexp [SimTalk]                               | Negexp/Negexp                             |
| Normal [distribution], z_normal [SimTalk]                               | Normal/Normal                             |
| Poisson [distribution], z_poisson [SimTalk]                             | Poisson/Poisson                           |
| Emp [primitive empirical distribution], z_emp [SimTalk]                 | Emp/Emp                                   |
| Triangle [distribution], z_triangle [SimTalk]                           | Triangle/Dreieck                          |
| Type-dependent distribution                                             | List(Type) [distribution]                 |
| Uniform [distribution], z_uniform [SimTalk]                             | Uniform/Gleich                            |
| Weibull [distribution], z_weibull [SimTalk]                             | Weibull/Weibull                           |

**Syntax**

```simtalk
< Path >.<Attribute-path>.Type := string
```

**Parameters**

You can assign the following parameters to the individual distributions:

| Distribution                | Set of parameters                      | Range of values for the parameters                        |
|-----------------------------|----------------------------------------|-----------------------------------------------------------|
| Beta                        | Alpha1 , Alpha2                        | Alpha1 > 0, Alpha2 > 0                                    |
| Binomial                    | n , p                                  | integer n > 0, 0 p 1                                      |
| Constant                    | Value                                  | Value >= 0                                                |
| Erlang                      | Mu , Sigma , LowerBound , UpperBound   | Mu > 0, Sigma > 0, Upper Bound > Lower Bound              |
| Gamma                       | Alpha , Beta , LowerBound , UpperBound | Alpha > 0, Beta > 0, Upper Bound > Lower Bound            |
| Geometric                   | p , LowerBound , UpperBound            | 0 p 1, Upper Bound > Lower Bound                          |
| Hypergeometric              | m , n , p                              | 1 > n > m, 0 p 1                                          |
| Lognormal                   | Mu , Sigma , LowerBound , UpperBound   | Mu > 0, Sigma > 0, Upper Bound > Lower Bound              |
| Negative exponential        | Beta , LowerBound , UpperBound         | Beta > 0, Upper Bound > Lower Bound                       |
| Normal                      | Mu , Sigma , LowerBound , UpperBound   | Mu can be any value, Sigma > 0, Upper Bound > Lower Bound |
| Poisson                     | Lambda                                 | Lambda > 0                                                |
| Triangular                  | c , a , b                              | a > c > b                                                 |
| Uniform                     | Start , Stop                           | Start > Stop                                              |
| Weibull                     | Alpha , Beta , LowerBound , UpperBound | Alpha > 0, Beta > 0, Upper Bound > Lower Bound            |
| Discrete Empirical (dEmp)   | List                                   | -                                                         |
| Continuous Empirical (cEmp) | List                                   | -                                                         |
| Primitive Empirical (Emp)   | List, Column                           | -                                                         |
| Formula                     | Formula                                | -                                                         |

| Distribution   | Set of parameters   | Range of values for the parameters   |
|----------------|---------------------|--------------------------------------|
| List(Type)     | Table               | -                                    |
| List(Place)    | Table               | -                                    |
| Matrix(Type)   | Table               | -                                    |

**Examples**

```simtalk
MyStation.proctime.Type := "Uniform"
MyStation.SetupTime.Type := "Matrix(Type)"
MyStation.SetupTime.DataTable := DataTable
```

The different distributions have different parameters. You can set these:

- With the method setTypeAndAttr .
- By direct assignments to the attribute.

**Example**

```simtalk
MyStation.proctime.Mu := 0.50
MyStation.proctime.Sigma := 0.1
```

You should also set the parameters for the new distribution when you set a new distribution type.

###### UpperBound [SimTalk] - distribution parameter

The parameter UpperBound sets the largest value to be sampled from a distribution.

When Plant Simulation encounters a greater number, it keeps drawing samples until a value equal to or less than the UpperBound results. The UpperBound has to be greater than the LowerBound .

If both UpperBound and LowerBound are zero, an unlimited distribution results.

**Syntax**

<AttributePath >.UpperBound:time

**Parameters**

You can assign the following parameters to these distributions:

| Distribution         | Set of parameters                      | Range of values for the parameters                        |
|----------------------|----------------------------------------|-----------------------------------------------------------|
| Erlang               | Mu , Sigma , LowerBound , UpperBound   | Mu > 0, Sigma > 0, Upper Bound > Lower Bound              |
| Gamma                | Alpha , Beta , LowerBound , UpperBound | Alpha > 0, Beta > 0, Upper Bound > Lower Bound            |
| Geometric            | p , LowerBound , UpperBound            | 0 > p > 1, Upper Bound > Lower Bound                      |
| Lognormal            | Mu , Sigma , LowerBound , UpperBound   | Mu > 0, Sigma > 0, Upper Bound > Lower Bound              |
| Negative exponential | Beta , LowerBound , UpperBound         | Beta > 0, Upper Bound > Lower Bound                       |
| Normal               | Mu , Sigma , LowerBound , UpperBound   | Mu can be any value, Sigma > 0, Upper Bound > Lower Bound |
| Weibull              | Alpha , Beta , LowerBound , UpperBound | Alpha > 0, Beta > 0, Upper Bound > Lower Bound            |

**Assignment Value**

You can assign a value of data type time .

**Example**

```simtalk
MyStation.proctime.Type := "normal"
MyStation.proctime.Mu := 60.0
MyStation.proctime.Sigma := 30.0
MyStation.proctime.LowerBound := 20.0  // no value below 20 seconds
MyStation.proctime.UpperBound := 120.0 // no value above 2 minutes // In the example the random variable has a mean of µ = 63.7 // and a standard deviation of σ = 23.5.
```

Methods of the Distributions

Methods of the Distributions

The distributions provide a number of methods for accessing them.

The distributions provide these methods :

getAttr [SimTalk]

putAttributeNamesIntoTable [SimTalk] - distributions

setTypeAndAttr [SimTalk]

Also compare Parameters of the Distributions

###### getAttr [SimTalk]

Returns the parameters of the distribution of the object designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.&lt;Attribute&gt;.getAttr

Return Value

The return value has the data type string .

It is the contents of the text box of the respective distribution on the tab Times of the material flow objects.

**Example**

```simtalk
type := Station.ProcTime.type
SetOfParameters := Station.ProcTime.getAttr
ParallelStation.ProcTime.setTypeAndAttr(type,SetOfParameters)
```

**Note**

The method getAttr returns the set of parameters in the format that the method setTypeAndAttr understands.

See also

Tab Times [general description]

###### putAttributeNamesIntoTable [SimTalk] - distributions

Writes all built-in attributes of the defined statistical distribution into the table designated by &lt;Path&gt; into a table.

Type

Method

Syntax

```simtalk
< Path >.<Attribute>.putAttributeNamesIntoTable(Table:table[, IncludeOptional:boolean:=true, Language:integer:=ModelLanguage])
```

**Parameters**

**Note**

If you do not specify the optional parameters, the method does not return the read-only attributes.

- The parameter Table of data type table designates the table into which the attributes will be written.
- The optional parameter IncludeOptional of data type boolean determines if Plant Simulation suppresses the optional attributes LowerBound and UpperBound (if they exist) (true) or not (false).
- The optional parameter Language of data type integer sets the language in which Plant Simulation shows the names of the attributes. 0 designates German, 1 designates English. If you do not enter this parameter, Plant Simulation shows the names of the attributes in the language of the model.

**Example**

```simtalk
var t: table
MyStation.SetupTime.putAttributeNamesIntoTable(t, false, UserInterfaceLanguage)
```

###### setTypeAndAttr [SimTalk]

Sets the type of the distribution and assigns a complete set of parameters to the distribution of the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.Attribute.setTypeAndAttr(Type:string, SetOfParameters:string) < Path >.Attribute.setTypeAndAttr(Type:string, Param1:any[, Param2:any, ...])
```

**Parameters**

- The parameter Type of data type string designates the type of the distribution.

| Type of the Distribution   | Name of the Distribution                                   |
|----------------------------|------------------------------------------------------------|
| Const                      | Const [distribution]                                       |
| Uniform                    | Uniform [distribution], z_uniform [SimTalk]                |
| Normal                     | Normal [distribution], z_normal [SimTalk]                  |
| Lognorm                    | Lognorm [distribution], z_lognorm [SimTalk]                |
| Negexp                     | Negexp [distribution], z_negexp [SimTalk]                  |
| Geom                       | Geom [distribution], z_geom [SimTalk]                      |
| Hypgeo                     | Hypgeo [distribution], z_hypgeom [SimTalk]                 |
| Erlang                     | Erlang                                                     |
| Weibull                    | Weibull [distribution], z_weibull [SimTalk]                |
| Triangle                   | Triangle [distribution], z_triangle [SimTalk]              |
| Binomial                   | Binomial [distribution], z_binomial [SimTalk]              |
| Poisson                    | Poisson [distribution], z_poisson [SimTalk]                |
| Gamma                      | Gamma [distribution], z_gamma [SimTalk]                    |
| Beta                       | Beta [distribution], z_beta [SimTalk]                      |
| dEmp                       | dEmp [discrete empirical distribution], z_dEmp [SimTalk]   |
| cEmp                       | cEmp [continuous empirical distribution], z_cEmp [SimTalk] |

| Type of the Distribution   | Name of the Distribution                                |
|----------------------------|---------------------------------------------------------|
| Emp                        | Emp [primitive empirical distribution], z_emp [SimTalk] |
| Formula                    | Formula [distribution]                                  |
| List(Type)                 | List(Type) [distribution]                               |
| List(Place)                | List(Place) [distribution] ( ParallelStation )          |
| Matrix(Type)               | Matrix(Type) [distribution] for setting-up objects      |

- The parameter SetOfParameters of data type string designates all distribution parameters separated by commas.

You can also specify the parameter SetOfParameters as a set of individual parameters. The number and the data types of parameters depend on the distribution type.

**Example**

```simtalk
-- set distribution parameters as a string MyStation.ProcTime.setTypeAndAttr("Uniform", "0:15, 0:20") -- set distribution parameters as a set of individual parameters MyStation.ProcTime.setTypeAndAttr("Uniform", 0:15, 0:20)
var type: string := Station.ProcTime.type
var SetOfParameters: string := Station.ProcTime.getAttr
StationNew.ProcTime.setTypeAndAttr(type, SetOfParameters)
```

**Note**

The method getAttr returns the set of parameters in the format that the method setTypeAndAttr understands.

**See also**

Parameters of the Distributions

