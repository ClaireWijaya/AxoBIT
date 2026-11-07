**Chapter 16 — Training and Evaluation**

**16.1 Introduction to Neural Network Training**

In Chapter 14, we learned how artificial neurons combine inputs using
weights, biases, and activation functions. In Chapter 15, we explored
how neural networks organize these neurons and learn from prediction
errors.

This chapter applies those concepts to a practical problem: building a
neural network, training it with data, and evaluating its performance.

**Training** is the process of adjusting a model's parameters using data
and a learning algorithm.

**Evaluation** is the process of measuring how well a model performs on
data used for assessment.

Consider a program designed to classify flowers using their
measurements. The program receives features describing each flower and
predicts its species.

To develop this model, we need to:

1.  Select a suitable dataset.

2.  Prepare the data.

3.  Separate training and test data.

4.  Scale numerical features when appropriate.

5.  Choose a neural network architecture.

6.  Train the model.

7.  Make predictions on unseen examples.

8.  Calculate evaluation metrics.

9.  Interpret the results and limitations.

This workflow applies to many supervised learning tasks, although the
specific details depend on the dataset and the problem.

**16.2 Data Preparation**

A neural network learns from numerical representations of examples. The
quality and organization of the data influence what the model can learn.

**16.2.1 Features and targets**

A dataset used for supervised learning commonly contains features and
targets.

**Features** describe the examples.

**Targets** represent the values the model is expected to predict.

Consider a simplified dataset of students:

| **Study hours** | **Practice-question score** | **Passed?** |
|-----------------|-----------------------------|-------------|
| 2               | 45                          | No          |
| 4               | 65                          | Yes         |
| 6               | 80                          | Yes         |
| 1               | 30                          | No          |

The first two columns are features. The final column is the target.

A classification model might learn to predict the target from the
features.

In Python, feature data is conventionally represented by X, while target
values are conventionally represented by y.

For example:

<img src="CHAPTER 16_media/media/image1.png"
style="width:5.45861in;height:1.58341in" />

Here, 0 represents "No" and 1 represents "Yes."

The program uses numerical labels because standard machine learning
algorithms require an appropriate representation of their inputs and
targets.

**16.2.2 Data quality**

Before training, examine the dataset for potential problems.

**Missing values:** Some examples may lack measurements.

**Incorrect values:** A measurement might be entered incorrectly.

**Duplicate examples:** Repeated records may distort the training
process or evaluation.

**Inconsistent units:** Some measurements might use centimeters while
others use millimeters.

**Unrepresentative samples:** The dataset might fail to represent the
population on which the model will be used.

Possible solutions include correcting data-entry errors, removing
inappropriate duplicates, imputing missing values, and standardizing
units.

However, data cleaning must be guided by the meaning of the data.
Removing unusual examples indiscriminately can eliminate important
information.

**16.2.3 Handling missing values**

Suppose a dataset contains these values:

| **Example** | **Age** | **Score** |
|-------------|---------|-----------|
| A           | 18      | 80        |
| B           | 19      | Missing   |
| C           | 20      | 90        |

A model may be unable to accept the missing value directly.

One possible approach is **imputation**, which replaces missing values
using a defined method.

For example, the missing score could be replaced by a statistic
calculated from the appropriate training data.

The choice of method depends on the problem. Missing values may
themselves carry information, and careless imputation can introduce
bias.

For this chapter's programming exercise, we use a clean educational
dataset so that we can focus on neural network training and evaluation.

**16.3 Feature Scaling**

**16.3.1 What is feature scaling?**

**Feature scaling** is the process of transforming numerical features to
comparable scales.

Suppose a model uses two features:

- Age: values around 18 to 25.

- Annual income: values around 20,000 to 100,000.

The numerical ranges differ substantially.

Many neural network training algorithms are sensitive to feature scales.
If input features have very different numerical ranges, optimization can
become less effective or require more careful parameter tuning.

Scaling can help address this problem. It does not guarantee a better
model in every situation, but it is an important practical consideration
for MLPs.

**16.3.2 Standardization**

One common scaling method is standardization.

Its formula is:

``` math
\boxed{z = \frac{x - \mu}{\sigma}}
```

Here:

- $`x`$ is the original feature value.

- $`\mu`$ is the mean of the feature.

- $`\sigma\`$is its standard deviation.

- $`z\`$is the standardized value.

The mean represents the average. The standard deviation measures how
spread out the values are around the mean.

Suppose:

``` math
x = 80,\quad\quad\mu = 60,\quad\quad\sigma = 10
```

Substitute into the formula:

``` math
z = \frac{80 - 60}{10}
```

Calculate the difference:

``` math
z = \frac{20}{10}
```

Therefore:

``` math
\boxed{z = 2}
```

The original value is two standard deviations above the mean.

Standardization does not necessarily make every feature normally
distributed. It transforms the feature's location and scale.

**16.3.3 Avoiding data leakage during scaling**

**Data leakage** occurs when information that should be unavailable
during training influences model development.

Suppose we calculate the mean and standard deviation using the entire
dataset before splitting it into training and test sets.

The scaling parameters would then contain information from the test set.

Although this may seem harmless, it allows the test data to influence
preprocessing and can make evaluation less independent.

The safer procedure is:

1.  Split the data into training and test sets.

2.  Calculate scaling parameters using the training data only.

3.  Apply those parameters to the training data.

4.  Apply the same parameters to the test data.

A scikit-learn Pipeline helps implement this procedure correctly because
the scaler is fitted as part of the training workflow and subsequently
applied to the test data using the learned transformation.

**16.4 Training, Validation, and Test Sets**

A dataset is often divided into separate subsets for different purposes.

**16.4.1 Training set**

The **training set** is used to fit the model and adjust its parameters.

During training, the model uses examples and their target values to
learn useful patterns.

**16.4.2 Validation set**

The **validation set** is used during model development to compare
alternatives and make decisions about settings.

For example, it can help determine:

- Which architecture to use.

- Which learning rate is appropriate.

- How much regularization to apply.

- When training should stop.

Validation data should not be treated as a completely independent final
evaluation set if its results repeatedly influence model selection.

**16.4.3 Test set**

The **test set** is reserved for evaluating the selected model after
development.

It provides an estimate of how well the model performs on data that did
not guide its training or model-selection decisions.

A test score does not guarantee the same performance in every real-world
environment. The test set must be relevant to the intended use.

**16.4.4 Comparing the three datasets**

| **Dataset** | **Main purpose** | **Used to update model parameters?** | **Used for model selection?** |
|----|----|----|----|
| Training | Learn model parameters | Yes | Can guide training decisions |
| Validation | Compare configurations and tune settings | Normally no direct parameter fitting | Yes |
| Test | Final evaluation of the selected model | No | Should not guide repeated tuning |

A common introductory split is 70% training, 15% validation, and 15%
test. Another is 80% training and 20% test when a separate validation
set is unnecessary for a simple demonstration.

These are examples, not universal requirements. The appropriate split
depends on the amount of data, the task, and the evaluation design.

For small datasets, cross-validation may provide a more informative
estimate of performance during model selection.

**16.5 Reproducibility**

**Reproducibility** means making an experiment sufficiently documented
and controlled that its procedures and results can be checked or
repeated.

Machine learning experiments may contain randomness in:

- Data splitting.

- Initial parameter values.

- Batch ordering.

- Certain optimization procedures.

A **random seed** initializes a pseudorandom number generator so that a
sequence of generated values can be reproduced under appropriate
conditions.

For example:

<img src="CHAPTER 16_media/media/image2.png"
style="width:5.6114in;height:1.58341in" />

The parameter random_state=42 makes the randomized split reproducible
when the relevant conditions remain the same.

The number 42 is simply an example. Another fixed integer could be used.

Setting a seed does not guarantee identical results across every
software version, hardware environment, parallel execution
configuration, or numerical implementation.

For stronger reproducibility, record:

- The dataset and its source.

- The preprocessing procedure.

- The model architecture.

- The hyperparameters.

- The random seeds.

- The software versions.

- The evaluation procedure.

Reproducibility makes it easier to identify mistakes and compare
alternative approaches fairly.

**16.6 Building a Simple Neural Network in Python**

We will use the Iris dataset to build a classification model with
scikit-learn.

**16.6.1 Why use the Iris dataset?**

The Iris dataset is a classic educational dataset containing 150 flower
samples from three species.

Each sample has four numerical features:

1.  Sepal length.

2.  Sepal width.

3.  Petal length.

4.  Petal width.

The task is to predict the flower species from its measurements.

The dataset contains 50 samples from each of the three classes and is
available through scikit-learn.

This dataset is appropriate for an introductory example because it is
small, numerical, and designed for classification exercises.

However, success on Iris does not establish that a model will perform
well on other datasets.

**16.6.2 Installing the required library**

The program uses Python and scikit-learn.

Install scikit-learn from a terminal:

<img src="CHAPTER 16_media/media/image3.png"
style="width:5.56279in;height:0.31946in" />

If the command is not recognized on your computer, try:

<img src="CHAPTER 16_media/media/image4.png"
style="width:5.56279in;height:0.31252in" />

Use the Python interpreter associated with your development environment.

**16.6.3 Complete Python program**

The following program:

- Loads the Iris dataset.

- Separates features and targets.

- Creates training and test sets.

- Standardizes features using training data only.

- Builds an MLP classifier.

- Trains the model.

- Makes predictions.

- Evaluates its performance.

- Displays a confusion matrix and a classification report.

> <img src="CHAPTER 16_media/media/image5.png"
> style="width:5.46556in;height:3.00015in" />
>
> <img src="CHAPTER 16_media/media/image6.png"
> style="width:5.44472in;height:3.18766in" />
>
> <img src="CHAPTER 16_media/media/image7.png"
> style="width:5.52112in;height:3.06266in" />
>
> <img src="CHAPTER 16_media/media/image8.png"
> style="width:5.33361in;height:2.98626in" />
>
> <img src="CHAPTER 16_media/media/image9.png"
> style="width:5.37528in;height:1.54175in" />

**Execution note:** This is a complete example using documented
scikit-learn APIs, but I have not executed it in this response.
Therefore, I am not presenting a fabricated numerical output or claiming
that the program has been tested here.

**16.6.4 Understanding the code**

**Step 1: Import the libraries**

<img src="CHAPTER 16_media/media/image10.png"
style="width:5.52112in;height:0.6042in" />

load_iris loads the dataset.

train_test_split divides the data into separate subsets.

The remaining imports provide scaling, the neural network classifier,
the pipeline, and evaluation metrics.

**Step 2: Load the data**

<img src="CHAPTER 16_media/media/image11.png"
style="width:5.6114in;height:0.41669in" />

The variable iris stores the dataset and its associated information.

<img src="CHAPTER 16_media/media/image12.png"
style="width:5.52806in;height:0.50697in" />

X contains the four numerical features for each flower.

y contains the corresponding class labels.

The features are arranged so that each row represents one sample and
each column represents one feature.

**Step 3: Split the dataset**

<img src="CHAPTER 16_media/media/image13.png"
style="width:5.50723in;height:1.41674in" />

The argument test_size=0.2 reserves 20% of the dataset for testing.

With 150 examples, this produces 120 training examples and 30 test
examples.

random_state=42 makes the randomized split reproducible under the same
relevant conditions.

stratify=y asks scikit-learn to preserve the class proportions as
closely as possible when splitting the data.

The feature and target arrays are split together so that each flower
remains associated with its correct species label.

**Step 4: Build the pipeline**

<img src="CHAPTER 16_media/media/image14.png"
style="width:5.50723in;height:2.65291in" />

The pipeline combines preprocessing and model training.

StandardScaler() standardizes the numerical features.

MLPClassifier(...) creates a multilayer perceptron for classification.

The important settings are:

| **Setting** | **Meaning** |
|----|----|
| hidden_layer_sizes=(10,) | One hidden layer containing 10 neurons. |
| activation="relu" | Uses ReLU for the hidden layer. |
| solver="adam" | Uses the Adam optimization algorithm. |
| max_iter=2000 | Sets the maximum number of training iterations. |
| random_state=42 | Sets a seed for supported randomized operations. |
| early_stopping=True | Enables an internal validation procedure to stop training when its stopping criterion is met. |

The comma in (10,) indicates a one-element Python tuple.

The early_stopping=True setting is useful to introduce, but it has an
important consequence: the classifier internally reserves part of the
supplied training data for validation. Therefore, not all 120 examples
necessarily contribute to parameter fitting in the same way.

The external test set remains separate from this internal validation
process.

**Step 5: Train the model**

<img src="CHAPTER 16_media/media/image15.png"
style="width:5.41695in;height:0.31946in" />

The fit method trains the pipeline.

The scaler learns its scaling parameters from the training data. The
transformed training data are then passed to the MLP classifier.

The classifier learns its parameters from the training examples and
their labels.

This is the main training step.

**Step 6: Make predictions**

<img src="CHAPTER 16_media/media/image16.png"
style="width:5.56279in;height:0.27779in" />

The predict method generates a predicted species label for each test
example.

The pipeline first applies the already-fitted scaler, then passes the
transformed features to the trained neural network.

No new scaling parameters are learned from the test set during this
operation.

**Step 7: Calculate accuracy**

<img src="CHAPTER 16_media/media/image17.png"
style="width:5.58362in;height:0.27779in" />

Accuracy measures the proportion of predictions that match the correct
labels.

Its formula is:

``` math
\boxed{\text{Accuracy} = \frac{\text{Number~of~correct~predictions}}{\text{Total~number~of~predictions}}}
```

Suppose a hypothetical model correctly classifies 27 of 30 test
examples.

Then:

``` math
\text{Accuracy} = \frac{27}{30}
```

Therefore:

``` math
\boxed{\text{Accuracy} = 0.90 = 90\%}
```

This calculation is an illustrative example, not the claimed result of
running the supplied program.

**Step 8: Interpret the classification report**

The program displays several metrics.

**Precision** measures the proportion of predictions for a particular
class that are correct.

**Recall** measures the proportion of actual examples belonging to a
class that the model correctly identifies.

**F1-score** is the harmonic mean of precision and recall. It provides a
combined measure that is useful when both metrics matter.

These metrics are calculated separately for each class in the
classification report.

The confusion matrix provides additional information about which classes
the model confuses with others.

**16.7 Training the Model and Making Predictions**

The program illustrates the distinction between fitting a model and
using it.

During training:

<img src="CHAPTER 16_media/media/image18.png"
style="width:5.50723in;height:0.27085in" />

The model learns from labeled examples.

During inference:

<img src="CHAPTER 16_media/media/image19.png"
style="width:5.59057in;height:0.31946in" />

The trained model produces predictions for examples it was not fitted
on.

The final example predicts the species of one flower:

<img src="CHAPTER 16_media/media/image20.png"
style="width:5.47945in;height:0.93755in" />

The four numbers represent sepal length, sepal width, petal length, and
petal width, respectively, in the units used by the dataset.

The outer list represents a collection of samples, even though it
contains only one flower. The inner list contains that flower's four
features.

The model returns a class label. The expression
iris.target_names\[prediction\[0\]\] converts the predicted numerical
label into its corresponding species name.

The supplied measurement is an illustrative input. The program's actual
predicted output should be obtained by running the code.

**16.8 Evaluating the Neural Network**

Evaluation helps determine whether a model performs adequately for its
intended purpose.

No single metric provides a complete assessment in every situation.

**16.8.1 Accuracy**

Accuracy is appropriate when the proportion of correct classifications
is a meaningful measure of success.

However, it can be misleading when classes are highly imbalanced.

For example, suppose 95% of examples belong to one class. A model that
always predicts that class can achieve 95% accuracy while failing to
identify the minority class.

This is why other metrics may be necessary.

**16.8.2 Confusion matrix**

A **confusion matrix** summarizes the relationship between actual
classes and predicted classes.

For a hypothetical binary classifier, consider:

|                 | **Predicted positive** | **Predicted negative** |
|-----------------|------------------------|------------------------|
| Actual positive | 40                     | 10                     |
| Actual negative | 5                      | 45                     |

The four categories are:

- **True positive (TP):** A positive example correctly predicted as
  positive.

- **False negative (FN):** A positive example incorrectly predicted as
  negative.

- **False positive (FP):** A negative example incorrectly predicted as
  positive.

- **True negative (TN):** A negative example correctly predicted as
  negative.

The example contains 130? No: the total is:

``` math
40 + 10 + 5 + 45 = 100
```

Correct predictions are the true positives plus true negatives:

``` math
40 + 45 = 85
```

Therefore:

``` math
\text{Accuracy} = \frac{85}{100} = 0.85
```

The accuracy is 85%.

**16.8.3 Precision**

Precision is defined as:

``` math
\boxed{\text{Precision} = \frac{TP}{TP + FP}}
```

Here:

- $`TP\`$is the number of true positives.

- $`FP\`$is the number of false positives.

Using the example:

``` math
\text{Precision} = \frac{40}{40 + 5}
```

``` math
\text{Precision} = \frac{40}{45}
```

Therefore:

``` math
\boxed{\text{Precision} \approx 0.889}
```

The model's precision is approximately 88.9%.

**16.8.4 Recall**

Recall is defined as:

``` math
\boxed{\text{Recall} = \frac{TP}{TP + FN}}
```

Here, $`FN`$is the number of false negatives.

Using the example:

``` math
\text{Recall} = \frac{40}{40 + 10}
```

``` math
\text{Recall} = \frac{40}{50}
```

Therefore:

``` math
\boxed{\text{Recall} = 0.80}
```

The model identifies 80% of the actual positive examples.

**16.8.5 F1-score**

The F1-score is defined as:

``` math
\boxed{F_{1} = 2\frac{PR}{P + R}}
```

Here:

- $`P\`$is precision.

- $`R\`$is recall.

Using the unrounded values from the example:

``` math
P = \frac{40}{45},\quad\quad R = \frac{40}{50}
```

Therefore:

``` math
F_{1} = 2\frac{(40/45)(40/50)}{(40/45) + (40/50)}
```

Simplifying gives:

``` math
\boxed{F_{1} \approx 0.842}
```

The F1-score is approximately 84.2%.

Precision, recall, and F1-score are useful when the costs of different
classification errors matter.

For example, a screening system may need high recall to reduce missed
cases, whereas a system that triggers expensive investigations may place
greater emphasis on precision.

The appropriate metric depends on the application.

**16.8.6 Training loss and validation performance**

A model's training loss measures its error on the training data
according to its loss function.

Validation performance measures its performance on a separate dataset
used during development.

These results can reveal important patterns.

| **Observation** | **Possible interpretation** |
|----|----|
| Training loss decreases and validation performance improves | The model may be learning useful patterns. |
| Training loss decreases while validation performance worsens | The model may be overfitting. |
| Training and validation performance are both poor | The model may be underfitting, or the data or training procedure may be unsuitable. |
| Results vary considerably between runs | The model may be sensitive to initialization, data splitting, or other sources of variation. |

These patterns are diagnostic clues, not definitive explanations.
Further investigation may be needed to identify the actual cause.

**16.9 Common Training Problems and Debugging**

**16.9.1 Overfitting**

**Overfitting** occurs when a model learns patterns specific to its
training data that do not generalize well to unseen examples.

A model may achieve very low training loss but perform poorly on
validation or test data.

Possible approaches include:

- Collecting more representative training data.

- Reducing model complexity.

- Using regularization.

- Applying early stopping.

- Improving feature selection and preprocessing.

These methods should be evaluated rather than applied automatically.

**16.9.2 Underfitting**

**Underfitting** occurs when a model fails to capture important patterns
in the data.

Possible causes include:

- An overly simple architecture.

- Insufficient training.

- Poorly selected features.

- Excessive regularization.

- An unsuitable optimization configuration.

A more complex model is not necessarily the correct solution. Data
quality and training settings should also be examined.

**16.9.3 Incorrect input shapes**

A neural network expects inputs with a particular structure.

For scikit-learn classifiers, feature data are commonly represented as a
two-dimensional array:

``` math
\left( \text{number~of~samples},\text{number~of~features} \right)
```

For example, 100 samples with four features have a shape of:

``` math
(100,4)
```

A single sample should ordinarily be supplied as a two-dimensional
collection containing one row, such as:

<img src="CHAPTER 16_media/media/image21.png"
style="width:5.45861in;height:0.29863in" />

A frequent mistake is supplying a one-dimensional list when the model
expects a two-dimensional array.

**16.9.4 Incompatible data types**

A numerical neural network may reject text values or other incompatible
data types.

For example, a feature containing "high", "medium", and "low" requires
an appropriate representation before being used by a numerical model.

Possible approaches include one-hot encoding or other justified
transformations.

The transformation should preserve the meaning of the data and be fitted
using training data when it learns parameters from the dataset.

**16.9.5 Unsuitable feature scales**

When features have widely different numerical ranges, MLP training may
become less effective.

Use an appropriate scaling method when necessary, and ensure that
preprocessing is fitted only on training data.

**16.9.6 Poor data quality**

Incorrect labels, missing values, duplicate examples, and
unrepresentative samples can undermine model performance.

Before changing the architecture, check whether the dataset is suitable
and whether its features and labels are correct.

**16.9.7 Training does not converge**

An optimizer may fail to reach a satisfactory solution within the
specified training budget.

Possible reasons include:

- An unsuitable learning rate.

- Poor feature scaling.

- Insufficient iterations.

- An unsuitable architecture.

- Difficult optimization conditions.

Inspect warnings and training diagnostics rather than assuming that a
model has converged simply because the program completed.

**16.9.8 Debugging checklist**

When a neural network produces unexpected results, ask:

1.  Are the features and targets correctly aligned?

2.  Are the input dimensions correct?

3.  Are missing or invalid values present?

4.  Is the preprocessing procedure appropriate?

5.  Is the training data representative of the task?

6.  Is the model overfitting or underfitting?

7.  Have training warnings been examined?

8.  Is the evaluation performed on data that did not guide model
    selection?

9.  Are the chosen metrics suitable for the task?

A systematic debugging process is more reliable than changing several
settings at random.

**16.10 CNNs, RNNs, and Transformers**

The MLP introduced earlier is not the only neural network architecture.

Different architectures are designed to process different kinds of
information. Three important families are convolutional neural networks,
recurrent neural networks, and transformers.

**16.10.1 Convolutional neural networks (CNNs)**

A **convolutional neural network (CNN)** is a neural network
architecture commonly associated with image processing.

<img src="CHAPTER 16_media/media/image22.png"
style="width:4.23611in;height:2.1143in" />

Figure 16.1 – A typical convolutional neural network

CNNs use convolutional operations to process structured data. In image
applications, these operations allow the network to learn local patterns
and combine them into more complex representations.

Applications include:

- Image classification.

- Object detection.

- Medical image analysis.

- Image segmentation.

CNNs can exploit spatial structure in images, although their suitability
depends on the task and architecture.

**16.10.2 Recurrent neural networks (RNNs)**

A **recurrent neural network (RNN)** is designed to process sequences by
maintaining a state that carries information from earlier steps.

<img src="CHAPTER 16_media/media/image23.png"
style="width:3.89052in;height:2.0625in" />

Figure 16.2 - Recurrent neural network

For example, a sequence-processing model might read a sentence one word
at a time, updating its internal state as it processes each word.

Applications include:

- Time-series analysis.

- Sequence prediction.

- Some speech-processing tasks.

- Some forms of language processing.

Traditional RNNs can struggle to learn long-range dependencies because
gradients may vanish or explode during training. Architectures such as
long short-term memory networks (LSTMs) and gated recurrent units (GRUs)
were developed to address some of these difficulties.

RNNs remain useful in some settings, although transformers have become
prominent in many language and sequence-processing applications.

**16.10.3 Transformers**

A **transformer** is a neural network architecture built around
attention mechanisms.

<img src="CHAPTER 16_media/media/image24.jpeg"
style="width:4.32639in;height:2.43641in" />

Figure 16.3 – Main Points of Transformer Architecture

Attention allows the model to calculate how information from different
positions in an input should contribute to a representation.

For example, when processing a sentence, a transformer can use
relationships among different words rather than relying exclusively on a
sequential hidden state.

Transformers are used in:

- Large language models.

- Machine translation.

- Text summarization.

- Image processing.

- Multimodal systems that combine different types of information.

Transformers can process many input positions in parallel during
important parts of training, although their computational and memory
requirements can be substantial.

They do not automatically outperform every other architecture on every
task.

**16.10.4 Architecture comparison**

| **Characteristic** | **CNN** | **RNN** | **Transformer** |
|----|----|----|----|
| Main architectural idea | Convolutional operations | Recurrent state across sequence steps | Attention mechanisms |
| Typical input structure | Images and other structured data | Sequential or time-series data | Text, images, and other supported representations |
| Important strength | Captures local spatial patterns efficiently | Represents sequential information through recurrent state | Models relationships among input positions through attention |
| Common applications | Image classification and detection | Time-series prediction and sequence processing | Language modeling, translation, and multimodal processing |
| Potential limitation | May require specialized design for nonspatial tasks | Sequential computation can limit parallelism; long-range learning can be difficult | Can require substantial memory and computation, depending on model and input length |

The architectures described here are not mutually exclusive. Modern
systems may combine convolutional operations, attention, recurrent
components, or other techniques.

**16.11 Limitations and Responsible Use**

Neural networks can be useful tools, but their deployment requires more
than obtaining a high evaluation score.

**16.11.1 Reliability**

A model's predictions can be incorrect, especially when the input
differs from the training data.

A model trained on one population or environment may perform poorly in
another.

Evaluation should therefore reflect the intended use, including relevant
subgroups, changing conditions, and the consequences of errors.

**16.11.2 Bias and fairness**

A model may learn undesirable patterns from biased or unrepresentative
training data.

For example, if a dataset systematically underrepresents certain groups,
the resulting model may perform less reliably for those groups.

Fairness evaluation should consider the task, the affected groups, the
consequences of errors, and appropriate measures of performance.

A single overall accuracy score may hide substantial differences between
groups.

**16.11.3 Privacy**

Training data may contain personal or confidential information.

Responsible practice includes:

- Collecting only data that are necessary and appropriately authorized.

- Following applicable privacy requirements.

- Limiting access to sensitive information.

- Protecting stored datasets and model outputs.

- Considering whether model outputs could reveal information about
  training examples.

A dataset being available online does not automatically mean that every
use of its information is appropriate.

**16.11.4 Interpretability**

Complex neural networks may be difficult to explain.

In high-stakes applications, such as healthcare or consequential
financial decisions, understanding model limitations and providing
appropriate human oversight can be especially important.

Interpretability techniques may help investigate model behavior, but
they do not automatically establish that a model is correct or fair.

**16.11.5 Computational costs**

Training and operating neural networks can require substantial
computational resources.

Costs may include:

- Processor or accelerator usage.

- Memory.

- Electricity.

- Storage.

- Data preparation.

- Model maintenance and monitoring.

A smaller, simpler model may be preferable when it provides sufficient
performance at lower cost.

**16.11.6 Human oversight**

Neural networks should be used within an appropriate decision-making
process.

Human oversight may involve reviewing uncertain predictions, monitoring
performance, correcting errors, and deciding when a model should not be
used.

The appropriate level of oversight depends on the risks and consequences
of the application.

**A technically successful model is not automatically a responsible
model.** Reliable deployment requires attention to data quality,
evaluation, privacy, fairness, interpretability, and the needs of the
people affected by its outputs.

**16.12 Chapter Summary**

Training and evaluation are essential parts of developing a neural
network.

A supervised learning dataset contains features and target labels.
Training data are used to fit the model, validation data support model
selection, and test data provide a final evaluation.

Feature scaling is often important for MLPs. To avoid data leakage,
preprocessing should be fitted on training data only. A scikit-learn
pipeline helps enforce this separation.

The Iris example demonstrates how to load a dataset, split it, scale its
features, train an MLP classifier, make predictions, and calculate
evaluation metrics.

Accuracy, precision, recall, F1-score, and confusion matrices provide
different perspectives on classification performance.

CNNs are commonly used for spatial data such as images, RNNs process
sequences using recurrent state, and transformers use attention
mechanisms to model relationships among input positions.

Finally, neural network development must account for limitations
involving data quality, generalization, computation, bias, privacy, and
interpretability.

**16.13 Review Questions and Solutions**

**Multiple-choice questions**

**1. What is the primary purpose of a training set?**

A. To provide the only evaluation that matters.\
B. To fit the model's parameters.\
C. To guarantee that the model will be fair.\
D. To replace all validation procedures.

**2. Why should a scaler be fitted using training data only?**

A. To guarantee 100% accuracy.\
B. To reduce data leakage from evaluation data.\
C. To remove the need for a test set.\
D. To prevent all missing values.

**3. What is the primary purpose of a validation set?**

A. To support model selection and tuning.\
B. To replace the features.\
C. To guarantee that the model cannot overfit.\
D. To make every training example identical.

**4. Which architecture is particularly associated with convolutional
operations for image processing?**

A. CNN.\
B. RNN.\
C. Decision tree.\
D. Linear regression.

**5. What does precision measure?**

A. The proportion of predicted positives that are correct.\
B. The proportion of all examples in the dataset that are positive.\
C. The number of features in a model.\
D. The time required to train the model.

**6. Which statement about random seeds is correct?**

A. A fixed seed guarantees identical results on every computer and
software version.\
B. A fixed seed can make supported randomized procedures reproducible
under the same conditions.\
C. A seed determines the model's final accuracy in advance.\
D. Random seeds eliminate data leakage.

**Solutions and explanations**

**1. Answer: B.** The training set provides the examples used to fit the
model and adjust its parameters.

**2. Answer: B.** Fitting preprocessing on training data only prevents
the scaler from using information from the test set when calculating its
transformation parameters.

**3. Answer: A.** Validation data support decisions such as architecture
selection, hyperparameter tuning, and early stopping.

**4. Answer: A.** CNNs use convolutional operations and are commonly
applied to images and other structured data.

**5. Answer: A.** Precision is the number of true positives divided by
the number of predicted positives, when the denominator is nonzero.

**6. Answer: B.** A fixed seed supports reproducibility for randomized
procedures under suitable conditions, but it does not guarantee
identical behavior across all environments.

**Short-answer questions**

**1. Explain the difference between features and target labels.**

**2. Why should training and test data be separated?**

**3. Explain the difference between overfitting and underfitting.**

**4. Why might accuracy be misleading for an imbalanced dataset?**

**5. Describe one typical application of each of CNNs, RNNs, and
transformers.**

**6. Explain two responsible-use considerations for neural networks.**

**Solutions and explanations**

**1.** Features describe the examples and serve as model inputs. Target
labels specify the outputs the model is expected to predict in
supervised learning.

**2.** The training data are used to fit the model, while the test data
provide a more independent assessment of its performance. Mixing these
roles can lead to overly optimistic evaluation.

**3.** Overfitting occurs when a model learns training-specific patterns
that do not generalize well. Underfitting occurs when a model fails to
capture important relationships in the data.

**4.** A model may achieve high accuracy by predicting the majority
class while failing to identify minority-class examples. Precision,
recall, F1-score, and class-specific results may reveal these problems.

**5.** CNNs are commonly used for image classification. RNNs can be used
for time-series prediction. Transformers are widely used in language
modeling and translation.

**6.** Answers may include privacy protection, fairness assessment,
monitoring for unreliable predictions, controlling computational costs,
and providing appropriate human oversight. The explanation should
connect each consideration to a possible risk.

**16.14 Practical Exercises and Solutions**

**Exercise 1: Dataset preparation**

A dataset contains 500 labeled examples. You reserve 20% for testing.

How many examples are assigned to the training set and how many to the
test set?

**Solution**

The test-set size is:

``` math
500(0.20) = 100
```

Therefore, the test set contains 100 examples.

The training-set size is:

``` math
500 - 100 = 400
```

**Answer:** 400 training examples and 100 test examples.

**Exercise 2: Calculate precision and recall**

A classifier produces the following results:

- True positives: 30.

- False positives: 10.

- False negatives: 5.

- True negatives: 55.

Calculate precision and recall.

**Solution**

Precision is:

``` math
\text{Precision} = \frac{TP}{TP + FP}
```

Substitute:

``` math
\text{Precision} = \frac{30}{30 + 10}
```

``` math
\boxed{\text{Precision} = 0.75}
```

Recall is:

``` math
\text{Recall} = \frac{TP}{TP + FN}
```

Substitute:

``` math
{\text{Recall} = \frac{30}{30 + 5}
}\boxed{\text{Recall} \approx 0.857}
```

The classifier has 75% precision and approximately 85.7% recall.

**Exercise 3: Identify data leakage**

A student standardizes the entire dataset before splitting it into
training and test sets.

Explain the problem and suggest a correction.

**Solution**

The scaler learns its mean and standard deviation from all examples,
including the test data. This allows information from the test set to
influence preprocessing.

A better procedure is to split the dataset first and fit the scaler
using only training data.

A pipeline can implement the procedure:

<img src="CHAPTER 16_media/media/image25.png"
style="width:5.59057in;height:1.54869in" />

The pipeline must then be fitted using the training data before it is
used to evaluate the test set.

**Exercise 4: Interpret model performance**

A model achieves 99% accuracy on its training set but only 65% accuracy
on its test set.

What might this indicate? Give two possible responses.

**Solution**

The difference suggests possible overfitting, although differences in
the training and test data or other evaluation problems should also be
investigated.

Possible responses include:

- Simplifying the architecture.

- Applying suitable regularization.

- Collecting more representative training data.

- Reviewing the data split and checking for distribution differences.

The model should not be accepted merely because its training accuracy is
high.

**Exercise 5: Code-reading exercise**

Consider:

<img src="CHAPTER 16_media/media/image26.png"
style="width:5.50028in;height:0.65281in" />

Explain what each line does.

**Solution**

The first line fits the model using the training features and target
labels.

The second line uses the fitted model to generate predictions for the
test features.

The test labels are not passed to predict, because the model must
generate its predictions from the features rather than receive the
correct answers.

**Exercise 6: Improve a model responsibly**

A neural network is used to help screen applications for a university
program. The overall accuracy is high, but evaluation reveals
substantially lower recall for one group of applicants.

Identify two concerns and suggest two steps that should be taken before
deployment.

**Solution**

Potential concerns include unequal error rates between groups and the
possibility that the training data do not adequately represent all
applicants.

Appropriate steps include:

- Investigating data quality, sample representation, and the causes of
  the performance difference.

- Evaluating relevant metrics separately across groups.

- Reviewing the consequences of false negatives.

- Involving qualified people in deciding whether the system is suitable
  for use.

A high overall accuracy does not establish that the system is fair or
appropriate.

**16.15 Key Terms and Glossary**

| **Term** | **Definition** |
|----|----|
| Accuracy | The proportion of predictions that are correct. |
| CNN | A neural network architecture commonly associated with convolutional operations and image processing. |
| Confusion matrix | A table comparing actual classes with predicted classes. |
| Data leakage | The use of information during model development that should be unavailable for that stage of evaluation or training. |
| Evaluation | Measuring a model's performance using appropriate data and metrics. |
| F1-score | The harmonic mean of precision and recall. |
| Feature | An input variable describing an example. |
| Feature scaling | Transforming numerical features to appropriate scales. |
| Imputation | Replacing missing values using a defined method. |
| Inference | Using a trained model to produce predictions. |
| Overfitting | Learning training-specific patterns that do not generalize well. |
| Precision | The proportion of predicted positive examples that are actually positive. |
| Recall | The proportion of actual positive examples that are correctly identified. |
| Recurrent neural network | A neural network architecture that processes sequences using recurrent state. |
| Reproducibility | The ability to repeat or verify an experiment under documented conditions. |
| Random seed | An initial value used to make supported pseudorandom procedures reproducible. |
| Standardization | A scaling procedure that subtracts a feature's mean and divides by its standard deviation. |
| Target | The desired output associated with a training example. |
| Test set | Data reserved for evaluating a selected model. |
| Training set | Data used to fit a model. |
| Transformer | A neural network architecture built around attention mechanisms. |
| Underfitting | Failure to capture important patterns in the data. |
| Validation set | Data used during development to assess alternatives and guide model selection. |

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

Figure 16.1 – A typical convolutional neural network:
<https://medium.com/@savindufernando/comparing-cnn-rnn-and-transformer-models-in-simple-terms-a859fe42a299>

Figure 16.2 - Recurrent neural network:
<https://medium.com/@savindufernando/comparing-cnn-rnn-and-transformer-models-in-simple-terms-a859fe42a299>

Figure 16.3 – Main Points of Transformer Architecture:
<https://medium.com/@savindufernando/comparing-cnn-rnn-and-transformer-models-in-simple-terms-a859fe42a299>
