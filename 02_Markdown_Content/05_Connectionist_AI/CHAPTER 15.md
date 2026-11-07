**Chapter 15 — Neural Network Architecture**

**15.1 Introduction to Neural Network Architecture**

An **artificial neural network** is a computational model containing
interconnected units that transform input data into outputs. Its
parameters can be adjusted during training so that it learns patterns
from examples.

A neural network's **architecture** describes how its computational
units are organized and connected.

Architecture includes:

- The number of layers.

- The number of neurons in each layer.

- The connections between layers.

- The activation functions used.

- The arrangement of input and output units.

Architecture matters because different structures are suited to
different problems.

For example, a small network may be sufficient for a simple
classification task, while an image-recognition system may require a
more specialized architecture.

A neural network is not automatically effective simply because it
contains many neurons. Its performance also depends on the quality of
the data, the suitability of its architecture, the training procedure,
and the evaluation method.

**15.2 Layers and Connections**

**15.2.1 The three main types of layers**

A basic feedforward neural network commonly contains an input layer, one
or more hidden layers, and an output layer.

**Input layer**

The input layer receives the features describing an example.

If a dataset contains four numerical features, the network's input
representation must accommodate those four values.

**Hidden layer**

A hidden layer transforms information received from the preceding layer.
Its units perform weighted calculations and commonly apply nonlinear
activation functions.

The term *hidden* means that these intermediate representations are not
the original input features or the final predictions.

**Output layer**

The output layer produces the model's final output. Its structure
depends on the task.

Examples include:

- One output for a regression problem.

- One output for a binary classification model that predicts a
  positive-class probability.

- Multiple outputs for a multiclass classification model.

The exact interpretation depends on the output layer and the model's
training procedure.

**15.2.2 Connections between neurons**

In a fully connected layer, each neuron receives information from every
neuron in the preceding layer.

Suppose a network has four input features and three neurons in its first
hidden layer. Each hidden neuron receives all four input values, with
its own set of weights and bias.

The network can therefore calculate three different transformations of
the same input.

The outputs of these hidden neurons become inputs to the next layer.

<img src="CHAPTER 15_media/media/image1.png"
style="width:3.08097in;height:3.34654in" />

Figure 15.1 — Architecture of a Multilayer Perceptron

**15.2.3 Architecture terminology**

| **Term** | **Meaning** |
|----|----|
| Neuron or unit | A computational unit that transforms numerical inputs. |
| Layer | A group of computational units organized at the same stage of a network. |
| Input layer | The part of the network receiving the input features. |
| Hidden layer | An intermediate layer that transforms information. |
| Output layer | The layer producing the final model output. |
| Fully connected layer | A layer in which each unit receives input from every unit in the preceding layer. |
| Parameter | A learned value, such as a weight or bias. |

**15.3 Perceptrons**

**15.3.1 What is a perceptron?**

A **perceptron** is an early artificial-neuron model developed for
classification.

A simple perceptron calculates a weighted sum and applies a
threshold-based output rule.

Its weighted sum is:

``` math
z = \sum_{i = 1}^{n}w_{i}x_{i} + b
```

The output can be defined as:

``` math
\hat{y} = \left\{ \begin{matrix}
1 & \text{if~}z \geq 0 \\
0 & \text{if~}z < 0
\end{matrix} \right.\ 
```

Here:

- $`x_{i}\`$is input $`i`$.

- $`w_{i}`$ is its weight.

- $`b`$ is the bias.

- $`z\`$is the weighted sum.

- $`\hat{y}\`$is the predicted class.

This threshold function is a simplified teaching model. Other neural
network architectures use different output functions.

**15.3.2 Worked perceptron example**

Suppose:

``` math
x_{1} = 2,\quad\quad x_{2} = 1
```

The weights are:

``` math
w_{1} = 1,\quad\quad w_{2} = - 1
```

The bias is:

``` math
b = - 0.5
```

**Step 1: Calculate the weighted sum.**

``` math
z = w_{1}x_{1} + w_{2}x_{2} + b
```

**Step 2: Substitute the values.**

``` math
z = (1)(2) + ( - 1)(1) - 0.5
```

**Step 3: Calculate.**

``` math
z = 2 - 1 - 0.5
```

``` math
\boxed{z = 0.5}
```

**Step 4: Apply the threshold rule.**

Since $`0.5 \geq 0`$:

``` math
\boxed{\hat{y} = 1}
```

The perceptron predicts class 1.

**15.3.3 Limitations of a single perceptron**

A single perceptron with a threshold output can learn a linear decision
boundary.

For two features, this boundary is a straight line. For more features,
it is a higher-dimensional linear boundary.

Consequently, a single perceptron cannot represent every possible
classification pattern.

Consider the XOR problem:

| **Input** $`x_{1}`$ | **Input** $`x_{2}`$ | **XOR output** |
|---------------------|---------------------|----------------|
| 0                   | 0                   | 0              |
| 0                   | 1                   | 1              |
| 1                   | 0                   | 1              |
| 1                   | 1                   | 0              |

The positive examples occupy opposite corners of the input space. No
single straight-line boundary can separate both positive examples from
both negative examples.

This demonstrates the limitation of a single perceptron.

It does not mean that neural networks cannot solve XOR. A network with a
suitable hidden layer and nonlinear computation can represent the
pattern.

**15.4 Multilayer Perceptrons**

A **multilayer perceptron (MLP)** is a feedforward neural network
containing an input layer, at least one hidden layer, and an output
layer.

An MLP combines multiple computational transformations.

A simplified layer calculation is:

``` math
\mathbf{a}^{(l)} = f\left( \mathbf{W}^{(l)}\mathbf{a}^{(l - 1)} + \mathbf{b}^{(l)} \right)
```

Here:

- $`l`$identifies the current layer.

- $`\mathbf{a}^{(l - 1)}`$is the vector of outputs from the preceding
  layer.

- $`\mathbf{W}^{(l)}\`$is the weight matrix for the current layer.

- $`\mathbf{b}^{(l)}\`$is the bias vector.

- $`f\`$is the activation function, applied according to the layer's
  design.

- $`\mathbf{a}^{(l)}\`$is the resulting output vector.

A **vector** is an ordered collection of numerical values. A **matrix**
is a rectangular arrangement of values used to perform calculations on
vectors.

You do not need advanced linear algebra to understand the main idea:
each layer combines information from the preceding layer, transforms it,
and passes the result forward.

**Why are hidden layers useful?**

Different hidden neurons can learn different numerical transformations.

For example, an image classifier might learn intermediate
representations that respond to edges, textures, shapes, or combinations
of visual patterns.

These are illustrative examples of learned representations, not a
guarantee that every network will develop exactly those features.

Hidden layers and nonlinear activation functions allow MLPs to represent
relationships that a single linear model cannot express.

**15.5 Forward Propagation**

**Forward propagation** is the process of passing input information
through a neural network to produce a prediction.

Consider a simple network with:

- Two input features.

- One hidden neuron using ReLU.

- One output neuron using sigmoid.

The hidden neuron has:

``` math
w_{1} = 1,\quad w_{2} = 1,\quad b_{h} = - 1
```

The output neuron has:

``` math
v = 0.5,\quad b_{o} = 0
```

Suppose the inputs are:

``` math
x_{1} = 1,\quad\quad x_{2} = 2
```

This example is deliberately small so that each calculation can be
followed by hand.

**Step 1: Calculate the hidden neuron's weighted sum**

``` math
z_{h} = w_{1}x_{1} + w_{2}x_{2} + b_{h}
```

Substitute:

``` math
z_{h} = (1)(1) + (1)(2) - 1
```

Therefore:

``` math
\boxed{z_{h} = 2}
```

**Step 2: Apply the hidden neuron's activation function**

The hidden neuron uses ReLU:

``` math
h = \max\left( 0,z_{h} \right)
```

Substitute $`z_{h} = 2`$:

``` math
h = \max(0,2)
```

Therefore:

``` math
\boxed{h = 2}
```

**Step 3: Calculate the output neuron's weighted sum**

``` math
z_{o} = vh + b_{o}
```

Substitute the values:

``` math
z_{o} = (0.5)(2) + 0
```

Therefore:

``` math
\boxed{z_{o} = 1}
```

**Step 4: Apply sigmoid to the output**

``` math
\hat{y} = \frac{1}{1 + e^{- z_{o}}}
```

Substitute $`z_{o} = 1`$:

``` math
\hat{y} = \frac{1}{1 + e^{- 1}}
```

Since $`e^{- 1} \approx 0.3679`$:

``` math
\hat{y} \approx \frac{1}{1.3679}
```

Therefore:

``` math
\boxed{\hat{y} \approx 0.731}
```

The network's output is approximately $`0.731`$.

If the output layer and training procedure define this value as the
estimated probability of class 1, the model estimates that probability
as approximately $`73.1\%`$. This interpretation depends on the model's
setup and calibration.

<img src="CHAPTER 15_media/media/image2.png"
style="width:4.59406in;height:2.18575in" />

Figure 15.2 — Forward Propagation Through a Neural Network

**15.6 Predictions and Loss Functions**

A prediction is the output produced by a model.

A **target** is the desired output associated with a training example.

A **loss function** measures the discrepancy between predictions and
targets according to a specified mathematical rule.

Suppose a model predicts:

``` math
\hat{y} = 0.8
```

The target is:

``` math
y = 1
```

The prediction is close to the target but not exactly equal to it.

For a simple numerical example, we can use squared error:

``` math
\boxed{L = \left( \hat{y} - y \right)^{2}}
```

Here:

- $`L\`$is the loss for one example.

- $`\hat{y}\`$is the prediction.

- $`y\`$is the target.

Substitute:

``` math
L = (0.8 - 1)^{2}
```

Calculate the difference:

``` math
L = ( - 0.2)^{2}
```

Therefore:

``` math
\boxed{L = 0.04}
```

The loss is $`0.04`$.

A smaller squared error indicates a prediction closer to the target
under this loss function.

Squared error is useful for introducing the concept of loss. For binary
classification, cross-entropy is commonly used instead. In a multiclass
classification problem, the model's output representation and loss
function must match the task.

**Important:** A loss value is not the same as a prediction or a
percentage of accuracy. The meaning and scale of a loss depend on the
chosen loss function.

**15.7 Gradient Descent**

**Gradient descent** is an optimization method that adjusts model
parameters in an attempt to reduce the loss.

The model begins with some parameter values. The optimization process
repeatedly uses information about the loss to update those values.

A general parameter update is:

``` math
\boxed{\theta_{\text{new}} = \theta_{\text{old}} - \eta\frac{\partial L}{\partial\theta}}
```

Here:

- $`\theta`$ represents a parameter, such as a weight.

- $`L`$ is the loss.

- $`\eta`$ is the learning rate.

- $`\frac{\partial L}{\partial\theta}`$ represents how the loss changes
  as that parameter changes locally.

The derivative can be understood as a measure of the direction and rate
of change of the loss with respect to the parameter.

The formula subtracts the derivative multiplied by the learning rate
from the current parameter value.

**Worked example**

Suppose:

``` math
\theta_{\text{old}} = 2
```

``` math
\eta = 0.1
```

``` math
\frac{\partial L}{\partial\theta} = 0.5
```

Apply the update formula:

``` math
\theta_{\text{new}} = 2 - (0.1)(0.5)
```

Calculate the product:

``` math
\theta_{\text{new}} = 2 - 0.05
```

Therefore:

``` math
\boxed{\theta_{\text{new}} = 1.95}
```

The parameter decreases from$`2`$ to $`1.95.`$

This example demonstrates a parameter update. It does not prove that the
loss will decrease for every possible update; appropriate learning rates
and optimization behavior matter.

**The learning rate**

The **learning rate** determines the size of an optimization step.

- A learning rate that is too large may cause unstable updates or
  prevent convergence.

- A learning rate that is too small may make training unnecessarily
  slow.

- An appropriate learning rate depends on the model, data, optimizer,
  and training conditions.

Gradient descent is iterative. The algorithm repeatedly updates
parameters rather than expecting a single update to find the best
solution.

**15.8 Backpropagation**

**Backpropagation** is an algorithm for calculating gradients of the
loss with respect to neural network parameters by propagating
information backward through the network.

It enables efficient calculation of how changes to weights and biases
affect the loss.

Backpropagation does not itself mean that the weights have already been
updated.

The distinction is:

| **Process** | **Main role** |
|----|----|
| Forward propagation | Calculates the model's prediction. |
| Loss calculation | Measures prediction error using a loss function. |
| Backpropagation | Calculates gradients describing how the loss changes with model parameters. |
| Gradient descent or another optimizer | Uses gradients to update parameters. |

These processes work together during training.

A typical training step is:

1.  Perform forward propagation.

2.  Calculate the loss.

3.  Use backpropagation to calculate gradients.

4.  Apply an optimizer to update parameters.

5.  Repeat with additional training examples or batches.

The chain rule from calculus helps backpropagation calculate gradients
through successive layers. A beginner can understand its purpose without
calculating every derivative manually.

Backpropagation is central to training many multilayer neural networks.

**15.9 Epochs, Batches, Iterations, and Learning Rate**

Neural network training commonly uses several related terms.

**Epoch:** One complete pass through the training dataset.

**Batch:** A subset of training examples processed together.

**Iteration:** A training step associated with processing a batch and,
in ordinary gradient-based training, updating the model parameters.

**Learning rate:** A setting that controls the scale of parameter
updates.

Suppose a training dataset contains 120 examples and the batch size is
30.

The number of batches in one epoch is:

``` math
\text{Batches~per~epoch} = \frac{\text{Number~of~training~examples}}{\text{Batch~size}}
```

Substitute:

``` math
Batches\ per\ epoch = 12030
```

Therefore:

``` math
\boxed{4\text{~batches~per~epoch}}
```

If training uses one optimizer update per batch, this corresponds to
four updates per epoch.

After 10 epochs, the model would process 40 batches in total, assuming
the same batch size and no incomplete batches or other training
complications.

Different training configurations may define iterations differently, so
software documentation should be consulted when interpreting a
particular library's settings.

**15.10 The Neural Network Training Cycle**

Training combines the concepts introduced in this chapter.

**Stage 1: Initialize parameters**

The network begins with initial weights and biases.

**Stage 2: Forward propagation**

Training examples pass through the network to produce predictions.

**Stage 3: Calculate the loss**

The loss function compares predictions with the corresponding training
targets.

**Stage 4: Backpropagation**

The algorithm calculates gradients describing how the loss depends on
the parameters.

**Stage 5: Update parameters**

An optimizer uses the gradients to update the weights and biases.

**Stage 6: Repeat**

The process continues across batches and epochs.

The purpose is to learn parameter values that improve performance on the
intended task. However, minimizing training loss does not guarantee
strong performance on unseen data.

**Training versus inference**

| **Characteristic** | **Training** | **Inference** |
|----|----|----|
| Main purpose | Learn suitable parameter values | Produce outputs using learned parameters |
| Typical data | Training examples | New examples or examples being processed |
| Loss calculation | Used to guide optimization | Not necessarily required |
| Backpropagation | Commonly used during gradient-based training | Normally unnecessary |
| Parameter updates | Yes, during optimization | Normally no |
| Result | A trained model | Predictions or other outputs |

During inference, a trained network applies its learned computations to
input data. The parameters ordinarily remain unchanged.

**15.11 Training versus Inference: A Worked Example**

Suppose a trained model predicts whether a flower belongs to a
particular species.

The input features describe the flower's measurements. Forward
propagation produces:

``` math
\hat{y} = 0.85
```

If this is a suitably interpreted class probability, the model assigns
an estimated probability of $`0.85`$to the positive class.

During inference, the model returns this result without updating its
parameters.

During training, the model would compare predictions with known labels,
calculate the loss, calculate gradients, and update parameters through
its optimization procedure.

This distinction matters because **making a prediction is not the same
as learning from an example**.

**15.12 Chapter Summary**

- A neural network architecture specifies how computational units are
  arranged and connected.

- A basic feedforward network contains an input layer, hidden layers,
  and an output layer. A perceptron is a simple threshold-based
  classification model, while an MLP uses multiple layers and nonlinear
  operations to represent more complex relationships.

- Forward propagation calculates predictions. A loss function measures
  discrepancies between predictions and targets. Backpropagation
  calculates gradients, and an optimizer such as gradient descent uses
  those gradients to update parameters.

- Epochs, batches, iterations, and learning rates describe important
  aspects of the training process.

- Training adjusts model parameters; inference uses the trained
  parameters to produce predictions.

**15.13 Review Questions and Solutions**

**Multiple-choice questions**

**1. What does a neural network's architecture describe?**

A. Only its training dataset.\
B. The organization and connections of its computational units.\
C. Only its final accuracy.\
D. Only its learning rate.

**2. What is the primary purpose of forward propagation?**

A. To calculate predictions.\
B. To delete incorrect training examples.\
C. To calculate the test-set size.\
D. To guarantee that the loss decreases.

**3. Which process calculates gradients during standard neural network
training?**

A. Inference.\
B. Feature scaling.\
C. Backpropagation.\
D. Data splitting.

**4. What is the primary purpose of gradient descent?**

A. To create the dataset.\
B. To update parameters using gradient information.\
C. To assign names to neurons.\
D. To guarantee perfect predictions.

**5. What is an epoch?**

A. One complete pass through the training dataset.\
B. One input feature.\
C. The final output of a neuron.\
D. A measure of prediction accuracy.

**Solutions and explanations**

**1. Answer: B.** Architecture describes the network's structure,
including its layers and connections.

**2. Answer: A.** Forward propagation processes inputs through the
network to produce predictions.

**3. Answer: C.** Backpropagation calculates gradients of the loss with
respect to model parameters.

**4. Answer: B.** Gradient descent uses gradients to determine parameter
updates intended to reduce loss.

**5. Answer: A.** An epoch is one complete pass through the training
dataset.

**Short-answer questions**

**1. Explain why hidden layers are useful.**

**2. Explain the difference between a prediction and a loss value.**

**3. Distinguish backpropagation from gradient descent.**

**4. Explain what can happen when the learning rate is too large.**

**5. Explain the difference between training and inference.**

**Solutions and explanations**

**1.** Hidden layers transform input representations. When combined with
nonlinear activation functions, they allow a network to represent more
complex relationships than a single linear transformation.

**2.** A prediction is the model's output. A loss value measures the
discrepancy between that output and the target according to a specified
function.

**3.** Backpropagation calculates gradients. Gradient descent uses
gradients to update parameters. They are complementary but distinct
processes.

**4.** A learning rate that is too large can cause parameter updates to
overshoot useful values, producing unstable training or preventing
convergence.

**5.** Training adjusts model parameters using data and an optimization
procedure. Inference uses the trained parameters to produce outputs
without ordinarily updating them.

**15.14 Practical Exercises and Solutions**

**Numerical exercises**

**1. Perceptron calculation**

A perceptron receives $`x_{1} = 1`$ and $`x_{2} = 3`$. Its weights are
$`w_{1} = 2`$ and $`w_{2} = - 1`$, and its bias is $`b = 2`$ .

Calculate the weighted sum and predict the class using the threshold
rule from Section 15.3.

**2. Loss calculation**

A model predicts $`0.6`$, while the target is$`1`$. Calculate the
squared error.

**3. Parameter update**

A parameter has the current value $`4`$. The learning rate is $`0.2`$,
and its gradient is $`1.5`$.

Calculate its new value using gradient descent.

**4. Batch calculation**

A dataset contains 240 training examples. The batch size is 40.

How many batches are required for one epoch if every batch contains
exactly 40 examples?

**Solutions and explanations**

**1.**

Calculate:

``` math
z = w_{1}x_{1} + w_{2}x_{2} + b
```

Substitute:

``` math
z = (2)(1) + ( - 1)(3) + 2
```

``` math
z = 2 - 3 + 2
```

``` math
\boxed{z = 1}
```

Since $`z \geq 0`$, the predicted class is:

``` math
\boxed{\hat{y} = 1}
```

**2.**

Squared error is:

``` math
L = \left( \hat{y} - y \right)^{2}
```

Substitute:

``` math
L = (0.6 - 1)^{2}
```

``` math
L = ( - 0.4)^{2}
```

Therefore:

``` math
\boxed{L = 0.16}
```

**3.**

Use the parameter update:

``` math
\theta_{\text{new}} = \theta_{\text{old}} - \eta g
```

Here, $`g`$ is the gradient.

Substitute:

``` math
{\theta_{\text{new}} = 4 - (0.2)(1.5)
}{\theta_{\text{new}} = 4 - 0.3}
```

Therefore:

``` math
\boxed{\theta_{\text{new}} = 3.7}
```

**4.**

``` math
\text{Batches~per~epoch} = \frac{240}{40}
```

Therefore:

``` math
\boxed{6\text{~batches}}
```

**15.15 Key Terms and Glossary**

| **Term** | **Definition** |
|----|----|
| Architecture | The organization of a neural network's units, layers, and connections. |
| Backpropagation | An algorithm that calculates gradients through a neural network. |
| Batch | A subset of training examples processed together. |
| Epoch | One complete pass through the training dataset. |
| Forward propagation | The process of calculating predictions by passing information through a network. |
| Gradient | A mathematical quantity describing how a function changes with respect to its parameters. |
| Gradient descent | An optimization method that updates parameters using gradient information. |
| Hidden layer | An intermediate computational layer between input and output. |
| Inference | Using a trained model to produce outputs. |
| Iteration | A step in a training procedure, often involving processing a batch and updating parameters. |
| Learning rate | A setting controlling the scale of parameter updates. |
| Loss function | A mathematical function measuring discrepancies between predictions and targets. |
| Multilayer perceptron | A feedforward neural network with one or more hidden layers. |
| Parameter | A learned value, such as a weight or bias. |
| Perceptron | A simple computational model commonly used to introduce linear classification. |
| Prediction | An output produced by a model. |
| Target | The desired output associated with a training example. |

**References**

Google. (n.d.). *Neural networks*. Google for Developers. [Neural
Networks: Machine Learning Crash
Course](https://developers.google.com/machine-learning/crash-course/neural-networks?utm_source=chatgpt.com)

Google. (n.d.). *Neural networks: Training using backpropagation*.
Google for Developers. [Backpropagation: Machine Learning Crash
Course](https://developers.google.com/machine-learning/crash-course/neural-networks/backpropagation?trk=article-ssr-frontend-pulse_little-text-block&utm_source=chatgpt.com)

Google. (n.d.). *Linear regression: Gradient descent*. Google for
Developers. [Gradient Descent: Machine Learning Crash
Course](https://developers.google.com/machine-learning/crash-course/linear-regression/gradient-descent?utm_source=chatgpt.com)

scikit-learn developers. (n.d.). *1.17. Neural network models
(supervised)*. scikit-learn User Guide. [Supervised Neural Network
Models](https://scikit-learn.org/stable/modules/neural_networks_supervised.html?utm_source=chatgpt.com)

scikit-learn developers. (n.d.). *load_iris*. scikit-learn API
documentation. [Iris Dataset
Documentation](https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_iris.html?highlight=iris&utm_source=chatgpt.com)

scikit-learn developers. (n.d.). *Pipeline*. scikit-learn API
documentation. [Pipeline API
Documentation](https://scikit-learn.org/stable/modules/generated/sklearn.pipeline.Pipeline?utm_source=chatgpt.com)

scikit-learn developers. (n.d.). *Getting started*. scikit-learn
documentation. [scikit-learn Getting
Started](https://scikit-learn.org/stable/getting_started?utm_source=chatgpt.com)

Hebb, D. O. (1949). *The organization of behavior: A neuropsychological
theory*. Wiley.

McCulloch, W. S., & Pitts, W. (1943). A logical calculus of the ideas
immanent in nervous activity. *The Bulletin of Mathematical Biophysics,
5*, 115–133.

Minsky, M., & Papert, S. (1969). *Perceptrons: An introduction to
computational geometry*. MIT Press.

Rosenblatt, F. (1958). The perceptron: A probabilistic model for
information storage and organization in the brain. *Psychological
Review, 65*(6), 386–408.

Rumelhart, D. E., Hinton, G. E., & Williams, R. J. (1986). Learning
representations by back-propagating errors. *Nature, 323*, 533–536.

**Figure Reference**

Figure 15.1 — Architecture of a Multilayer Perceptron:
<https://scikit-learn.org/stable/modules/neural_networks_supervised.html>

Figure 15.2 — Forward Propagation Through a Neural Network:
<https://www.geeksforgeeks.org/deep-learning/forward-propagation-in-neural-networks/>
