#### Mathematical Functions

Plant Simulation provides a number of mathematical functions .

You do not have to enter a path for the mathematical functions .

- Basic Mathematical Functions
- Functions for Numerical Values
- Trigonometric Functions
- Distribution Functions, z\_ functions

See also

Arithmetic Operators

##### Basic Mathematical Functions

Plant Simulation provides a number of basic mathematical functions

You can specify these basic mathematical functions .

| Function                          | Type         | Results in                                                                                                                                                         |
|-----------------------------------|--------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| abs [SimTalk]                     | abs(x)       | the absolute value of &#124;x&#124;                                                                                                                                |
| beta [SimTalk]                    | beta(x,y)    | the beta function beta(x,y), x, y > 0                                                                                                                              |
| betai [SimTalk]                   | betai(x,y,z) | the incomplete beta function betai(x,y), x, y > 0 and 0 <= z <= 1                                                                                                  |
| exp [SimTalk]                     | exp(x)       | the exponential function e x The parameter is any number of data type real .                                                                                       |
| gamma [SimTalk]                   | gamma(x)     | the gamma function Γ (x), x > 0                                                                                                                                    |
| log [SimTalk]                     | log(x)       | the natural logarithm                                                                                                                                              |
| log10 [SimTalk]                   | log10(x)     | the logarithm to the base of 10                                                                                                                                    |
| pow [SimTalk]                     | pow(x,y)     | x y If the basis is 0, the exponent has to be greater than 0. If the exponent is not an integer, for example -0.5, the basis has to be greater than or equal to 0. |
| exponentiation operator [SimTalk] | x ** y       | the exponentiation operator. Is the same as pow(x,y) .                                                                                                             |
| sqrt [SimTalk]                    | sqrt(x)      | the square root. The parameter of data type real has to be equal to or greater than 0.                                                                             |

**Note**

When using the functions exp , pow , gamma and the arithmetic operators in SimTalk , you have to make sure that the result is located within the range of numbers your computer can show. Use the gamma function to compute the factorial of a number n: n! = 1 · 2 · … · n = Γ (n+1)

**Parameter**

The parameter for the basic mathematical functions has the data type real or integer or it can be a value with a physical unit.

**Return Value**

The return value has the data type real .

**Example**

```simtalk
var area := 2m * 2m;
print area        // outputs 4m² in the Console
print sqrt(area)  // outputs 2m in the Console
-- exponentiation operator ** instead of pow
var x: real := 2
var y: real := 3
var z: real := x ** y  // z = 2*2*2 = 8
```

**See also**

**Arithmetic Operators**

##### Functions for Numerical Values

Plant Simulation provides a number of functions for numerical values .

You can specify these functions for numerical values .

| Function                 | Type                                                   | Results in                                                          |
|--------------------------|--------------------------------------------------------|---------------------------------------------------------------------|
| ceil(x)                  | the smallest integer number greater than or equal to x | ceil [SimTalk]                                                      |
| floor [SimTalk] floor(x) | the greatest integer number smaller than or            | equal to x                                                          |
| max(x,y[,z, ...])        | the maximum                                            | max [SimTalk]                                                       |
| min(x,y[,z, ...])        | the minimum                                            | min [SimTalk]                                                       |
| round [SimTalk]          | round(x)                                               | the next integer number. print round(-1.5) yields -2                |
| round [SimTalk]          | round(x:real, places:integer)                          | the rounding of the real number x to the number of specified places |

**Note**

You can specify more than two parameters for the functions max and min .

For the functions max and min you cannot mix data types arbitrarily, i.e., all data types either have to be numerical, or all data types have to be of data type date and dateTime , or all have to be of data type string .

**Parameters**

The parameter for the functions for numerical values can have the data type real , integer , or it can be a value with a physical unit.

The parameter can also have the data type date , dateTime , or string for the functions min and max .

Return Value

The return value has the same data type as the parameter that you specify.

See also

Arithmetic Operators

Trigonometric Functions

Trigonometric Functions

Plant Simulation provides a number of trigonometric functions .

You can specify these trigonometric functions .

| Function   | Type                       | Results in      |
|------------|----------------------------|-----------------|
| acos(x)    | the arc cosine of x        | acos [SimTalk]  |
| asin(x)    | the arc sine of x          | asin [SimTalk]  |
| atan(x)    | the arc tangent of x       | atan [SimTalk]  |
| atan2(y,x) | the arc tangent of y and x | atan2 [SimTalk] |
| cos(x)     | the cosine of x            | cos [SimTalk]   |
| sin(x)     | the sine of x              | sin [SimTalk]   |
| tan(x)     | the tangent of x           | tan [SimTalk]   |

Parameter

Trigonometric functions expect the parameter in radians or return the result in radians. You can specify parameters of data type real or integer .

Return Value

The return value has the data type real .

See also

atan2 [SimTalk]

atan2 [SimTalk]

The function atan2(y, x) returns the angle in radians between the positive x-axis of a plane and the point given by the coordinates (x, y) on it for any real number arguments x and y, both of which are not equal to zero.

Type

Function

**Syntax**

```simtalk
atan2(y:real, x:real) → real
```

**Parameters**

- The parameter y of data type real designates the coordinate on the y-axis.
- The parameter x of data type real designates the coordinate on the x-axis.

Return Value

The return value has the data type real .

The angle is positive for counter-clockwise angles (upper half-plane, y &gt; 0), and negative for clockwise angles (lower half-plane, y 0).

For x=0 and y=0 the function returns 0.

Back to

###### Trigonometric Functions

##### Distribution Functions

Distribution Functions, z\_ functions

Plant Simulation provides these distribution functions .

You can create random numbers for times in the dialogs of the objects on the Tab Times and on the Tab Failures , with a Variable of data type randtime , and in SimTalk with the functions described below.

| Function                                                                                  | Results in this distribution                               |
|-------------------------------------------------------------------------------------------|------------------------------------------------------------|
| z_beta([Stream:integer,]Alpha1:real,A lpha2:real) -> real                                 | Beta [distribution], z_beta [SimTalk]                      |
| z_binomial([Stream:integer,]n:integer ,p:real) -> real                                    | Binomial [distribution], z_binomial [SimTalk]              |
| z_cauchy([Stream:integer,]Mu:time,The ta:real[,LowerBound:real,UpperBound:r eal]) -> real | Cauchy [distribution], z_cauchy [SimTalk]                  |
| z_cemp([Stream:integer,]Table:table) -> real                                              | cEmp [continuous empirical distribution], z_cEmp [SimTalk] |

| Function                                                                                       | Results in this distribution                             |
|------------------------------------------------------------------------------------------------|----------------------------------------------------------|
| z_demp([Stream:integer,]Table:table) -> real                                                   | dEmp [discrete empirical distribution], z_dEmp [SimTalk] |
| z_emp([Stream:integer,]Table:table,Co lumn:integer) -> integer                                 | Emp [primitive empirical distribution], z_emp [SimTalk]  |
| z_erlang([Stream:integer,]Mu:time,Sig ma:time[,LowerBound:real,UpperBound:r eal]) -> real      | Erlang [distribution], z_erlang [SimTalk]                |
| z_frechet([Stream:integer,]Mu:time,Th eta:real[,LowerBound:real,UpperBound: real]) -> real     | Fréchet [distribution], z_frechet [SimTalk]              |
| z_gamma([Stream:integer,]Alpha:real,B eta:time[,LowerBound:real,UpperBound: real]) -> real     | Gamma [distribution], z_gamma [SimTalk]                  |
| z_geom([Stream:integer,]p:real[,Lower Bound:real,UpperBound:real]) -> real                     | Geom [distribution], z_geom [SimTalk]                    |
| z_gumbel([Stream:integer,]Mu:time,The ta:real[,LowerBound:real,UpperBound:r eal]) -> real      | Gumbel [distribution], z_gumbel [SimTalk]                |
| z_hypgeom([Stream:integer,]m:integer, n:integer,p:real)                                        | Hypgeo [distribution], z_hypgeom [SimTalk]               |
| z_laplace([Stream:integer,]Mu:time,Th eta:real[,LowerBound:real,UpperBound: real]) -> real     | Laplace [distribution], z_laplace [SimTalk]              |
| z_logistic([Stream:integer,]Mu:time,T heta:real[,LowerBound:real,UpperBound :real]) -> real    | Logistic [distribution], z_logistic [SimTalk]            |
| z_loglogistic([Stream:integer,]Mu:tim e,Theta:real[,LowerBound:real,UpperBo und:real]) -> real | Loglogistic [distribution], z_loglogistic [SimTalk]      |
| z_lognorm([Stream:integer,]Mu:time,Si gma:time[,LowerBound:real,UpperBound: real]) -> real     | Lognorm [distribution], z_lognorm [SimTalk]              |
| z_negexp([Stream:integer,]Beta:time[, LowerBound:real,UpperBound:real]) -> real                | Negexp [distribution], z_negexp [SimTalk]                |
| z_normal([Stream:integer,]Mu:time,Sig ma:time[,LowerBound:real,UpperBound:r eal]) -> real      | Normal [distribution], z_normal [SimTalk]                |

| Function                                                                                        | Results in this distribution                                            |
|-------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|
| z_paralogistic([Stream:integer,]Mu:ti me,Theta:real[,LowerBound:real,UpperB ound:real]) -> real | Paralogistic [distribution], z_paralogistic [SimTalk]                   |
| z_pareto([Stream:integer,]Mu:time,The ta:real[,LowerBound:real,UpperBound:r eal]) -> real       | Pareto [distribution], z_pareto [SimTalk]                               |
| z_poisson([Stream:integer,]Lambda:rea l) -> real                                                | Poisson                                                                 |
| z_triangle([Stream:integer,]c:real,a: real,b:real) -> real                                      | Triangle [distribution], z_triangle [SimTalk] [triangular distribution] |
| z_uniform([Stream:integer,]LowerBound :real,UpperBound:real) -> real                            | Uniform [distribution], z_uniform [SimTalk]                             |
| z_weibull([Stream:integer,]Alpha:real ,Beta:time) -> real                                       | Weibull [distribution], z_weibull [SimTalk]                             |

**Parameters**

- The parameter Stream of data type integer designates the random number stream (compare Random Number Seed Values ).

If you call one of the distribution functions in a Method , the parameter Stream is optional. If you do not specify the stream, Plant Simulation uses the random number stream of the Method or of the user-defined attribute of data type method .

You can also call the distribution functions with the parameter Stream . For formulas this is required, as formulas never use the random number stream of the surrounding object.

- All other parameters are the parameters of the corresponding distribution function as described under Probability Distributions . They all either are of data type real or integer .

Return Value

The return value has the data type real .

The distribution function z\_emp returns a value of data type integer .

SimTalk

RandomSeed [SimTalk] - Method/User-defined Attribute

See also

resetRandomNumberStream [SimTalk]

Parameters of the Distributions Probability Distributions Methods of the Distributions

**Cauchy [distribution], z\_cauchy [SimTalk]**

**Cauchy [distribution], z\_cauchy [SimTalk]**

The Cauchy distribution is a continuous probability distribution.

Remarks

Use the Cauchy distribution to represent the occurrence of failures while developing large systems.

Syntax

```simtalk
z_cauchy([Stream:integer,]Mu:time,Theta:real[,LowerBound:real,UpperBound:rea l]) → real
```

**Parameters**

The parameters are µ and θ both of which have to be greater than 0. The mean value and the standard deviation cannot be computed from the parameters.

The density function is

The distribution function is

<!-- image -->

**Return Value**

The return value has the data type real .

SimTalk

##### Trigonometric Functions

See also

Parameters of the Distributions

**Fréchet [distribution], z\_frechet [SimTalk]**

**Fréchet [distribution], z\_frechet [SimTalk]**

The Fréchet distribution is also called the Gumbel type II distribution or the inverse Weibull distribution .

**Remarks**

Use the Fréchet distribution and the Gumbel distribution if you want to find out the maximum of several random numbers.

**Syntax**

```simtalk
z_frechet([Stream:integer,]Mu:time,Theta:real[,LowerBound:real,UpperBound:re al]) → real
```

**Parameters**

The parameters µ and θ have to be positive.

The density function for x &gt; 0 is

The distribution function is

The following applies and for

<!-- image -->

**Return Value**

The return value has the data type real .

See also

Parameters of the Distributions

**Gumbel [distribution], z\_gumbel [SimTalk]**

The Gumbel distribution is also called the log-Weibull , the Gumbel type I distribution or the extreme value distribution .

**Remarks**

Use the Gumbel distribution to model the distribution of the maximum (or the minimum) of a number of samples of various distributions.

**Syntax**

z\_gumbel([Stream:integer,]Mu:time,Theta:real[,LowerBound:real,UpperBound:rea l]) → real

**Parameters**

The parameters µ and θ have to be positive.

The parameter µ determines the mean value of the distribution. The variance is where is the Euler-Mascheroni constant .

<!-- formula-not-decoded -->

The density function is

The distribution function is

<!-- image -->

**Return Value**

The return value has the data type real .

See also

Parameters of the Distributions

###### Laplace [distribution], z\_laplace [SimTalk]

The Laplace distribution is a continuous distribution. The Laplace distribution is also called the Doubleexponential distribution .

**Syntax**

```simtalk
z_laplace([Stream:integer,]Mu:time,Theta:real[,LowerBound:real,UpperBound:re al]) → real
```

**Parameters**

The parameters are µ and σ &gt; 0. The parameter µ sets the mean value of the distribution. The parameter σ &gt; 0 sets the standard deviation of the distribution.

<!-- formula-not-decoded -->

For x &lt; µ the distribution function is

<!-- formula-not-decoded -->

<!-- image -->

Return Value

The return value has the data type real .

See also

**Parameters of the Distributions**

**Logistic [distribution], z\_logistic [SimTalk]**

Logistic [distribution], z\_logistic [SimTalk]

The logistic distribution is a continuous probability distribution.

Remarks

The logistic distribution is used as lifetime distribution.

Syntax

```simtalk
z_logistic([Stream:integer,]Mu:time,Theta:real[,LowerBound:real,UpperBound:r eal]) → real
```

Parameters

The parameters are µ and σ &gt; 0.

The parameter µ sets the mean value of the distribution.

The parameter σ &gt; 0 sets the standard deviation of the distribution.

The density function is

The distribution function is

<!-- formula-not-decoded -->

<!-- image -->

**Return Value**

The return value has the data type real .

See also

Parameters of the Distributions Loglogistic [distribution], z\_loglogistic [SimTalk]

The loglogistic distribution is also called the Fisk distribution .

Remarks

The loglogistic distribution is used as income and lifetime distribution.

Syntax

```simtalk
z_loglogistic([Stream:integer,]Mu:time,Theta:real[,LowerBound:real,UpperBoun d:real]) → real
```

Parameters

The parameters are α &gt; 0 and β &gt; 0.

The density function is

The distribution function is

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- image -->

**Return Value**

The return value has the data type real .

**See also**

Parameters of the Distributions

**Paralogistic [distribution], z\_paralogistic [SimTalk]**

Paralogistic [distribution], z\_paralogistic [SimTalk]

The paralogistic distribution is a transformed Pareto distribution .

**Syntax**

<!-- formula-not-decoded -->

**Parameters**

The parameters are α &gt; 0 and θ &gt; 0.

The density function is

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- image -->

**Return Value**

The return value has the data type real .

See also

Parameters of the Distributions

**Pareto [distribution], z\_pareto [SimTalk]**

###### Pareto [distribution], z\_pareto [SimTalk]

The Pareto distribution is a power-law probability distribution.

Syntax

z\_pareto([Stream:integer,]Mu:time,Theta:real[,LowerBound:real,UpperBound:rea l]) → real

**Parameters**

The parameters are α &gt; 0 and θ &gt; 0.

The density function is

The distribution function is

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- image -->

Return Value

The return value has the data type real .

See also

Parameters of the Distributions

