### Neural Network

Use the Artificial Neural Network for deducing a function from observations. This is particularly useful in applications, where the complexity of the data or task makes the design of such a function by hand impractical.

Icon

<!-- image -->

To add the NeuralNet to the Class Library , click Manage Class Library &gt; Libraries &gt; Tools &gt; Neural

Networks on the Home ribbon tab.

Description

Note

Your Plant Simulation license determines how you can use the NeuralNet .

Most neural networks are trainable systems that are able to learn to solve complex problems from a set of exemplars.

In Plant Simulation we use these functions of the artificial neural network:

- Function approximation, or regression analysis, including time series prediction and modeling.
- Classification, novelty detection and sequential decisionmaking.
- Data processing, including filtering.

**Note**

We modeled the NeuralNet as an application object in a Frame . For this reason opening help with F1 and What's This Help in the dialogs of the objects do not work. To open help for the object, select Help &gt; Help on NeuralNet in its dialog.

<!-- image -->

We modeled the dialogs of the objects with the object Dialog . The windows of the objects do not use the standard Siemens PLM theme, but your Windows theme.

To assign the object another name or a label, click it with the right mouse button and select Rename .

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

**See also**

<!-- image -->

| Evaluating Simulation Studies with the Neural Network   | Analyzing the Quality of the Neural Network   |
|---------------------------------------------------------|-----------------------------------------------|
| The Structure of the Neural Network                     | Forecasting                                   |
| Importing Training Data                                 | Configuring the Neural Network                |
| Training and Checking the Neural Network                | Calculating the Output Values                 |
| Illustrating the Results of the Training                |                                               |

#### Evaluating Simulation Studies with the Neural Network

The experiments of a simulation study assign a set of output values to a set of input values. The interrelation between the input values and the output values can be described and modeled through regression or with a neural network, also called artificial neural network ANN.

The artificial neural network uses the biological principles of information processing and information representation in the neurons of the brain. For correlating the input values and the output values, the artificial neural network uses a distributed representation of the information. This leads to a considerably higher error tolerance and stability than traditional methods of regression analysis. This enables a neural network to create prognoses for not yet analyzed combinations of parameters. Modeling the data with the artificial neural network also takes adequate care of the noise, which is introduced to almost each and every simulation study through random processes and through systematic measurement errors of the output values.

The learning process of the neural network is called training . A trained neural network can then approximately determine the corresponding set of output values to a given set of input values without having to run a simulation. The neural network can only determine the interrelation between the input values and the output values if a sufficient number of data sets for the input values and the output values exist. The number of data sets for the training is the number of experiments.

A multi-level experimental design of the ExperimentManager ensures that the input values are equally distributed within the range to be evaluated. Then number of data sets for the training is the number of experiments of a simulation study. After a simulation study you can import the simulation results as training data, by dragging the ExperimentManager to the NeuralNetwork and dropping it there.

#### The Structure of the Neural Network

The neural network consists of an input layer, one or two hidden layers and an output layer. The input layer is the number of input values of the simulation study. The output layer is the number of output values.

For most applications a single hidden layer will suffice. The hidden layer is a special parameter of the neural network, which you can define. Type in different values and watch the results.

Figure 11-36: Tri-layered neural network

<!-- image -->

The graphic shows a tri-layered neural network with a four-dimensional input layer and a two-dimensional output layer. The hidden layer is five-dimensional. The input values are assigned to the nodes of the input layer. The output values are assigned to the nodes of the output layer. The hidden layer contains intermediate results of the calculation of the output values from the input values. Theoretical examinations of the learning algorithms have shown that such a neural network can detect and learn any interrelation between the input values and the output values, when the hidden layer has a sufficiently large number of nodes. It is not possible though to predict how many nodes and training steps are required to arrive at the desired accuracy level. We do not, on the other hand, want to model noise with the artificial neural network while evaluating simulation studies. The dimensioning of the artificial neural network will always be a compromise between a model, which is as lean or as exact as possible. The artificial neural network should model typical correlations between the input values and the output values in a network with as few nodes as possible.

#### Importing Training Data

You can import the training data either from a table or they can be the results of a simulation study, which you ran with the ExperimentManager . .

Training data are classified as input/output values and as noise values. to evaluate the results of a simulation study with a neural network, drag the ExperimentManager onto the NeuralNet and drop it there. For stochastic simulation studies the NeuralNet inserts the observed standard deviations of the output values of each experiment as noise values.

Figure 11-37: Specifying the training data

<!-- image -->

If you want to import the training data from a DataTable , which you can drop onto the NeuralNet , it will ask you how you want to classify the columns of the table as input values, output values and noise values. The NeuralNet accepts data of data types real , integer , time , money , length , weight , speed , and acceleration as input and output values. It ignores data of data types date and string while importing data.

**Importing Training Data**

You can check the imported data by clicking the buttons under Data on the tab Input .

See also

ExperimentManager

#### Training and Checking the Neural Network

After you started training the neural network on the tab Training you cannot change the imported data and the parameters of the training algorithm any longer. The associated dialog items will then be deactivated.

Resetting the neural network deletes the training results. Then, you can manipulate the data and the parameters of the training algorithm again.

Figure 11-38: Training the neural network

<!-- image -->

A neural network cannot determine a set of output values for a given set of input values that will exactly match the output values that a simulation yields. The error, which results from the difference of the output of the neural network and the given output values is a feature of the neural network. At the beginning of the training the error decreases from training step to training step until it reaches a minimum. The size of the error depends on the structure of the neural network.

For rating the quality of the neural network the training data will only be used for validation purposes.

When no noteworthy improvement of the error is to be expected, the training algorithm will be restarted with a reinitialization. This prevents that the search for the minimum error gets stuck in a local minimum for too long. The error charts show a vertical dashed line at the corresponding training step.

#### Illustrating the Results of the Training

A trained neural network can compute the respective output values to a given set of input values. On the tab Results you can show the functional correlation between the input values and the output values.

The charts show essential properties of the correlation of the individual input and output values. The charts show the input and output values in their natural order, for example according to growing buffer capacity. Viewing the unfiltered training data makes characteristic correlations hard to recognize.

Figure 11-39: Results of the training

<!-- image -->

The figures below show the typical correlation between lot size of a production and the resulting total costs, which are the sum of fixed and variable costs. Fluctuations caused by random components or by systematic errors will be smoothed out by the measurements of the simulation results.

Figure 11-40: Results of a simulation study and the respective analysis with a neural network

<!-- image -->

#### Analyzing the Quality of the Neural Network

Before you make the neural network compute forecasts, you will check with which quality the artificial neural network has learned the input data.

For this minimizing process the error is of no immediate importance. The error can be calculated depending on the noise. If the variations are located within a tolerance interval, which results from the variance of the output values or from a percentage, which you define, the error will be set to 0. You can type this percentage into the dialog Configuration &gt; Settings &gt; Noise , which the command Settings &gt; Extended Settings opens.

Using Tools &gt; Calculator , you can compute all output values for a set of input values. To compute several combinations of input values one after the other, change the input values and click Apply . The unavailable columns contain the output values, which you cannot change.

Figure 11-41: Calculating the output values for a set of input values

<!-- image -->

#### Forecasting

When optimizing the model, you will often look for a combination of input values for which an output value is located as close as possible to a given value.

You can select an output value under the group Forecast on the tab Forecast for which you want to compute a forecast. The object shows the observation interval of the training data after you selected the output value.

Values located within this interval will produce realistic forecasts. Then, type in the desired output value.

Figure 11-42: Optimizing the input values for a desired output value

<!-- image -->

For smaller simulation studies you can evaluate the complete table of all combinations of the input values. Within this table you can compare the simulation results and results of the neural network. The columns of the output values are marked with the suffixes "\_S" (training data, which may be the results of a simulation) and "\_NN" (for neural network). The columns of the simulation results may contain empty cells, when you reduced the size of the input values in the dialog Configuration . The artificial neural network then computes approximate values for these empty cells.

Figure 11-43: Table containing all input and output values as well as the results of the neural network

<!-- image -->

You can open this table and the corresponding visualization of the data under the group Comparison on the tab Forecast . The table is sorted according to the selected output value. The range around the desired output value, which you type into the text box Range for cost minimization, is marked light green. The row with the most cost-efficient input values is marked dark green.

In addition, all rows, in which the desired output value appears exactly as expected, are marked orange. If this value is not reached, the NeuralNet marks the row, which comes closest to the desired output value.

When a very large number of combinations of the input values exists, Plant Simulation cannot create such a table in a short amount of time. In addition it is hard to manually evaluate very large tables. In these cases the most cost-efficient combinations of the input values are calculated by an optimization algorithm. To do so, click the button Start under the group Forecast . This opens the table with the input values, which approximate the desired output value as closely as possible and which cause the least amount of costs. Although the optimization algorithm does not search within a limited range, it can only detect a local minimum of the costs. To get various solutions for a certain problem, click Start repeatedly.

Figure 11-44: Forecast for an output value

<!-- image -->

You can select to compute the costs with a table or with a Method , compare Configuration &gt; Settings &gt; Costs of the input values.

#### Configuring the Neural Network

To configure the neural network, select the command Settings &gt; Extended Settings in the dialog of the neural network.

The training algorithm is the back-propagation-method, which is a gradient descent method. This algorithm minimizes the error between the outputs of the neural network and the given training data. The default parameters of the algorithm are suited for the most frequently used applications. If the NeuralNet contains a trained neural network, the dialog items, which control the structure of the neural network and the results of the training are deactivated. When you reset the artificial neural network, the dialog items, which control the output of the results of the training are deactivated. This applies to the dialog items of the dialogs of the neural network proper and to the configuration dialog.

You can define settings for the structure of the neural network on the tab Network Design .

<!-- image -->

Under the group Number of layers you can select to use a tri-layered or a four-layered neural network. One hidden layer, i.e., a tri-layered neural network, will suffice for most applications.

Under the group Weighting between the layers you can view tables, which contain a weighting of the strength of the connections between the nodes of the layers. These weights are the results of the training and represent the actual knowledge about the relations between the input and the output values. An interpretation of the contents of the individual weights is only possible for simple small networks.

On the tab Training you can change the parameters of the training algorithm.

<!-- image -->

You will set User-defined parameters of the neural network depending on the problem you want to solve. Here you either have to fall back on experience values or find suitable values through trials. To use predefined Calculated parameters , select the check boxes to their left.

The Activation function, which you can select under User-defined parameters , is applied to the cumulated influence of all nodes of a layer onto the next layer. You can also type the Magnitude of activation of the cumulated influence.

The given data are classified as training data and validation data, which is only used for calculating the error of the neural network. You can type the Percentage of the training data.

If the weights from one training step to the next do not change much during the algorithm, continuing the training algorithm is not effective. The NeuralNet checks after each twenty training steps if the relative changes of the weights are below the percentage, which you type into the text box Re-initialization . When the training algorithm arrived at a local minimum, the NeuralNet will be re-initialized. This way a better local minimum might be found. During a re-initialization the weights are chosen randomly. You can type the Magnitude of weights. The NeuralNet suggests a value depending on the value of the Activation function.

The gradient descent method is executed for each individual weight with an individual adjustment of the step size of the weight change. The training factor Eta controls the step size. Eta is dynamically adjusted between a minimum and a maximum value during the training algorithm. You can set the minimum and the maximum value of the training factor on the tab Training . Initially the training algorithm selects the mean value of the minimum and the maximum training factor. We recommend to set the Eta increase factor and the Eta decrease factor depending on the minimum and the maximum value of the training factor. The NeuralNet suggests an Eta increase factor, which after a tenfold multiplication of the Eta increase factor , transfers the initial value of Eta into the maximum value.

In addition to adjusting the training/learning rate, the training algorithm can be accelerated by adding a momentum coefficient. For this a certain portion Alpha of the weight adjustment from the previous training step is added to the current training step. You can type a value for the parameter Alpha , i.e., the Momentum coefficient on the tab Training .

To prevent that the training algorithm changes the weights too much while searching for the minimum error, the weights are not corrected after each error computation, but only after the number of data sets, which you type into the text box Error batch size . When correcting the weights, the NeuralNet uses the mean value of the errors of these data sets. The value, which the NeuralNet suggests, results from the number of data sets for the training.

Under Noise on the tab Settings you can select if the noise is to be taken into consideration for error correction. Noise can be incorporated through the variance of the output values or through a percentage, which you type. If the deviations are located within a tolerance interval, which results from the variance or the percentage, the error will be set to 0.

<!-- image -->

Under Settings &gt; Forecast you can set the parameters for the optimization algorithm for the forecast. The increments of the input values determines the accuracy with which the input values are calculated. The optimization algorithm is a variant of Simulated Annealing , which executes the Number of iteration steps at the most. As this procedure is controlled by chance, it is advisable to start the optimization several times and then compare the results.

The forecast searches for the most cost-efficient solution for a set of input values. For a proportional cost calculation, you will type the cost factors for each input value. You can also run more complex cost calculations with a Method , whose parameters are provided by a table with the input values. The output value of this Method (of data type real ) are the resulting costs.

#### Calculating the Output Values

When the NeuralNet contains a trained neural network, you can use getOutput to compute the output values for a set of input values.

```simtalk
outTab := NeuralNet.getOutput(inTab)
```

The table with one column inTab contains the input values, the one-columned table outTab contains the respective output values.

#### Sequential Sampler

