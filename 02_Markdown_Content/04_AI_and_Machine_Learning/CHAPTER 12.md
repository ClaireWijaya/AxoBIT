**Chapter 12 - About Machine Learning**

**12.1 Introduction to Machine Learning**

Machine Learning (ML) is a field of computer science that develops
algorithms enabling computers to learn patterns from data and use those
patterns to make predictions or decisions.

In traditional programming, a programmer explicitly specifies the rules
that determine the output. In machine learning, an algorithm uses
examples to construct a model that captures useful relationships in the
data.

For example, imagine that a university wants to estimate how long
students will spend completing an online assignment.

The university could write a fixed rule based on assumptions about
assignment difficulty. Alternatively, it could collect historical data
containing assignment characteristics and completion times, then train a
machine learning model to estimate completion time for new assignments.

The second approach allows the model to learn patterns from examples.

However, the model's predictions are estimates. Its usefulness depends
on the quality and relevance of its data and how well it generalizes to
new situations.

**12.1.1 What Is a Machine Learning Model?**

A **machine learning model** is a computational system that has learned
patterns or relationships from data through a training procedure.

After training, a model can use its learned parameters to generate
predictions for new inputs.

For example, a model trained on housing data might learn relationships
between property size, location, and sale price.

When provided with information about a new property, it can estimate its
price.

The model does not need to memorize every possible property. Instead, it
learns a representation of relationships that can be applied to new
examples.

**12.1.2 Why Is Machine Learning Useful?**

Machine learning is useful when patterns in data are difficult to
describe through a manageable set of manually written rules.

Applications include:

- Predicting product demand.

- Detecting potentially fraudulent transactions.

- Classifying images.

- Recognizing speech.

- Recommending products.

- Estimating energy consumption.

- Predicting equipment failures.

- Identifying groups of similar customers.

Machine learning is not appropriate for every problem. When a simple
rule solves a task reliably, using a complex learning system may add
unnecessary cost and uncertainty.

**12.2 Traditional Programming versus Machine Learning**

Consider a program that calculates the total price of a purchase.

If the price of each item and the quantity purchased are known, the
programmer can specify the exact rule:

``` math
\text{Total~Price} = \text{Unit~Price} \times \text{Quantity}
```

The program follows that rule.

Now consider identifying whether an email is spam. The decision may
depend on many interacting patterns, including the message content,
sender behavior, links, and historical examples.

Writing a reliable rule for every possible combination can be difficult.

A machine learning system can instead learn patterns from previously
labeled messages.

**12.2.1 Comparison**

| **Characteristic** | **Traditional programming** | **Machine learning** |
|----|----|----|
| Main input | Data and explicitly specified rules | Data and a learning algorithm |
| Main process | Execute the rules | Learn patterns during training |
| Result | Output determined by the programmed logic | A trained model that can produce predictions |
| Updating behavior | Change the rules or program | Often retrain or update the model |
| Suitable problems | Clearly defined procedures | Problems where useful patterns can be learned from data |
| Example | Calculate an invoice total | Predict whether a transaction is fraudulent |

A simplified representation is:

**Traditional programming:** Data + Rules → Output

**Machine learning training:** Training Data + Learning Algorithm →
Trained Model

**Machine learning prediction:** New Input + Trained Model → Prediction

These representations describe the general idea. Actual machine learning
systems may involve additional components, such as data preprocessing,
feature extraction, optimization, and post-processing.

**12.3 The Machine Learning Workflow**

A machine learning project typically involves several stages.

**Step 1: Define the Problem**

First, determine what the system should predict or discover.

For example:

- Predict the price of a property.

- Classify an email as spam or legitimate.

- Group customers according to purchasing behavior.

A clear objective helps determine the appropriate data, algorithm, and
evaluation metric.

**Step 2: Collect Data**

A model needs relevant information to learn from.

For a house-price model, data might include:

- Floor area.

- Number of bedrooms.

- Location.

- Property age.

- Historical sale price.

Data may come from databases, sensors, surveys, public datasets, or
other legitimate sources.

**Step 3: Prepare the Data**

Collected data may contain missing values, incorrect records,
inconsistent formats, duplicates, or irrelevant information.

Data preparation involves checking these problems and deciding how to
handle them.

For example, a property dataset might contain floor areas recorded in
both square meters and square feet. These measurements must be
standardized before meaningful comparisons can be made.

Data preparation must also avoid leaking information from the test set
into training.

**Step 4: Select a Model**

A model is selected according to the task.

Examples include:

- Decision trees.

- Linear regression.

- Logistic regression.

- Support vector machines.

- Neural networks.

- Clustering algorithms.

Different algorithms make different assumptions and have different
strengths and limitations.

**Step 5: Train the Model**

During training, a learning algorithm uses training data to determine
model parameters.

For example, a linear regression model learns numerical coefficients
that represent relationships between input features and the target.

The goal is to find parameter values that make the model useful for the
intended task.

**Step 6: Validate and Evaluate**

The model must be assessed to determine whether it performs adequately.

Validation data can help compare model configurations and choose
settings. A separate test set can provide a more independent estimate of
performance on unseen data.

The evaluation method must match the task and the intended use of the
model.

**Step 7: Deploy and Monitor**

Deployment means making the model available for use in an application or
operational process.

After deployment, its performance should be monitored. Data
distributions, user behavior, and operating conditions can change over
time.

A model that performed well previously may require investigation,
recalibration, or retraining if its performance deteriorates.

**12.4 Datasets, Samples, Features, and Labels**

Understanding data terminology is essential before training a model.

**12.4.1 Dataset**

A **dataset** is a collection of examples used for analysis or machine
learning.

Datasets may be stored in spreadsheets, databases, image collections,
audio recordings, text documents, or other formats.

A table is a convenient way to illustrate a simple dataset.

Consider this fictional dataset describing flowers.

| **Sample** | **Sepal length (cm)** | **Petal length (cm)** | **Flower species** |
|------------|-----------------------|-----------------------|--------------------|
| 1          | 5.1                   | 1.4                   | Setosa             |
| 2          | 4.9                   | 1.4                   | Setosa             |
| 3          | 6.4                   | 4.5                   | Versicolor         |
| 4          | 6.9                   | 5.4                   | Virginica          |

These values illustrate the structure of a dataset; they are not
intended to represent the complete dataset used in the programming
example later in this chapter.

**12.4.2 Sample**

A **sample**, also called an example or observation, is one individual
record in a dataset.

In the table above, each row represents one flower sample.

A dataset containing 1,000 flower records has 1,000 samples.

**12.4.3 Feature**

A **feature** is an input variable that provides information to a model.

In the flower example, the features are:

- Sepal length.

- Petal length.

Other features could include sepal width and petal width.

Features may be numerical, categorical, textual, visual, or represented
in other forms.

**12.4.4 Label and Target**

In supervised learning, a **label** or **target** is the answer the
model is trained to predict.

In the flower example, the target is the species.

For a house-price model, the target might be the sale price.

For a spam classifier, the target might be either *spam* or *not spam*.

In many introductory examples, *label* and *target* are used
interchangeably, although terminology can vary between applications and
libraries.

**12.4.5 Features versus Targets**

| **Concept**     | **Meaning**           | **Flower example** |
|-----------------|-----------------------|--------------------|
| Dataset         | Collection of records | All flower records |
| Sample          | One record            | One flower         |
| Feature         | Input information     | Petal length       |
| Label or target | Desired prediction    | Flower species     |

<img src="CHAPTER 12_media/media/image1.png"
style="width:4.00694in;height:2.21202in" />

Figure 12.1 — Features and Labels in a Dataset

The distinction is important because a supervised learning model must
learn to map input features to the desired target.

If the target accidentally becomes part of the input features,
evaluation can become misleading. This problem is discussed further in
Chapter 13.

**12.5 Supervised Learning**

**Supervised learning** is a machine learning approach in which a model
learns from examples that contain both inputs and known target values.

During training, the algorithm compares the model's predictions with the
known targets and adjusts the model according to its learning procedure.

Suppose a dataset contains measurements of flowers and their known
species.

The features describe each flower. The species labels provide the
correct answers during training.

The trained model can then predict the species of a new flower using its
measurements.

Supervised learning is commonly used for classification and regression.

**12.5.1 How Supervised Learning Works**

A simplified sequence is:

1.  Collect examples with known targets.

2.  Separate the input features from the targets.

3.  Divide the data into appropriate subsets.

4.  Train the model on the training data.

5.  Use the trained model to predict targets for new examples.

6.  Compare the predictions with known answers when evaluating
    performance.

Supervised learning depends on the quality of its labels. If the
training labels are inaccurate or systematically biased, the model may
learn an undesirable relationship.

**12.6 Classification**

**Classification** is a supervised learning task in which the model
predicts a category or class.

Examples include:

- Classifying email as spam or legitimate.

- Identifying a type of flower.

- Categorizing customer messages by topic.

- Predicting whether a transaction should be flagged for review.

Classification can involve two classes, called **binary
classification**, or more than two classes, called **multiclass
classification**.

**12.6.1 Binary Classification**

Suppose a system predicts whether an email is spam.

The possible classes are:

- Spam.

- Not spam.

The model may estimate a probability that the email is spam. A decision
rule then assigns a class based on a threshold.

For example, a system might classify a message as spam when its
estimated spam probability exceeds 0.5.

That threshold is only an example. The appropriate threshold depends on
the application and the consequences of different mistakes.

**12.6.2 Multiclass Classification**

A flower classifier may choose among three species:

- Setosa.

- Versicolor.

- Virginica.

The model predicts one of these categories.

Some classification systems can also produce probabilities or scores for
several classes, which can provide more information than the final
category alone.

**12.6.3 Classification Does Not Predict Any Arbitrary Number**

Classification predicts categories, even if those categories are
represented internally by numbers.

For example, the labels 0, 1, and 2 may represent three flower species.
These numbers are category identifiers, not measurements of flower size
or quality.

**12.7 Regression**

**Regression** is a supervised learning task in which the target is a
numerical quantity.

Examples include:

- Predicting a house's sale price.

- Estimating electricity demand.

- Predicting delivery time.

- Forecasting monthly sales.

- Estimating energy consumption.

**12.7.1 A Simple Example**

Suppose a model predicts a property's price using its floor area.

The model may learn that larger properties tend to have higher prices,
although the relationship also depends on location, condition, market
conditions, and other variables.

A simplified linear model can be written as:

``` math
\hat{y} = b + wx
```

where:

- $`\hat{y}`$ is the predicted value.

- $`x`$ is the input feature.

- $`w\`$is a learned coefficient.

- $`b\`$is a learned intercept.

Suppose a hypothetical model is:

``` math
\hat{y} = 50,000 + 2,000x
```

If $`x = 40`$, then:

``` math
{\hat{y} = 50,000 + 2,000(40)
}{\hat{y} = 50,000 + 80,000
}{\hat{y} = 130,000}
```

The predicted price is 130,000 units of currency.

This is an illustrative calculation, not a real-estate valuation. The
equation's usefulness depends on the data, the units, and the
assumptions of the model.

**12.7.2 Classification versus Regression**

| **Characteristic** | **Classification** | **Regression** |
|----|----|----|
| Target | Category | Numerical quantity |
| Example | Predict flower species | Predict house price |
| Typical output | Class label or class probabilities | Numerical prediction |
| Common evaluation methods | Accuracy, precision, recall, F1-score | MAE, MSE, RMSE |

The distinction depends on the target being predicted, not merely on
whether numbers appear in the output.

**12.8 Unsupervised Learning**

**Unsupervised learning** involves identifying patterns or structures in
data without relying on predefined target labels in the same way as
supervised learning.

For example, a retailer may want to discover groups of customers who
purchase similar products.

The retailer may have transaction records but no existing labels
describing customer groups.

An unsupervised learning algorithm can analyze similarities between
customers and identify clusters.

The resulting groups are not necessarily objectively correct categories.
Their usefulness depends on the data, the algorithm, and the intended
application.

Common unsupervised learning tasks include:

- Clustering.

- Dimensionality reduction.

- Some forms of anomaly detection.

- Discovering latent structures in data.

Unsupervised learning does not mean that the computer works without data
or without any assumptions. It means that the learning task does not
depend on a predefined target label in the same manner as supervised
learning.

**12.9 Clustering and Dimensionality Reduction**

**12.9.1 Clustering**

**Clustering** is an unsupervised learning task that groups data points
according to similarities defined by an algorithm.

Consider a shop with customer records describing purchase frequency and
average spending.

A clustering algorithm might identify groups such as:

- Customers who shop frequently and spend relatively little per visit.

- Customers who shop less frequently but make large purchases.

- Customers whose purchases are concentrated in particular product
  categories.

These descriptions are possible interpretations of clusters, not
guaranteed results.

A common algorithm is *k-means clustering*. It attempts to divide
observations into a specified number of clusters by minimizing distances
between observations and their assigned cluster centers.

The number of clusters and the chosen distance measure can affect the
results.

Clustering is useful for exploratory analysis, but a cluster does not
automatically represent a meaningful real-world group.

**12.9.2 Dimensionality Reduction**

**Dimensionality reduction** reduces the number of variables or
dimensions used to represent data while attempting to preserve important
information.

Suppose each image is represented by thousands of numerical values. An
analysis may become easier if the data can be represented in fewer
dimensions while retaining useful structure.

One established method is **Principal Component Analysis (PCA)**.

PCA constructs new numerical directions, called principal components,
that capture as much variance in the data as possible under its
mathematical formulation.

At an introductory level, the important idea is that dimensionality
reduction can simplify data representation and help with visualization
or downstream analysis.

However, reducing dimensions may discard information. It does not
guarantee better model performance.

**12.10 Reinforcement Learning**

**Reinforcement learning** is a machine learning approach in which an
agent learns through interaction with an environment and receives
rewards or penalties associated with its actions.

Important concepts include:

- **Agent:** The learner or decision-making system.

- **Environment:** The system or world in which the agent operates.

- **State:** Information describing the current situation.

- **Action:** A choice made by the agent.

- **Reward:** A numerical signal indicating the immediate desirability
  of an outcome.

- **Policy:** A strategy that determines which actions the agent chooses
  in different states.

**12.10.1 A Simple Example**

Imagine a simulated robot learning to navigate a room.

The agent receives information about its position and nearby obstacles.

It selects an action, such as moving forward or turning.

The environment changes in response. The agent receives a reward based
on its progress and the task's objectives.

Over repeated interactions, the learning algorithm attempts to develop a
policy that achieves high cumulative reward.

This example is a simplified analogy. Real reinforcement learning
requires careful design of the environment, state representation, action
space, reward function, and learning algorithm.

**12.10.2 Exploration and Exploitation**

Reinforcement learning often involves balancing two ideas.

**Exploration** means trying actions to discover their consequences.

**Exploitation** means choosing actions that are already believed to
produce good results.

Too little exploration may prevent the agent from discovering better
strategies. Too much exploration may waste time or produce poor
outcomes.

The appropriate balance depends on the learning problem.

**12.10.3 How Is Reinforcement Learning Different from Supervised
Learning?**

In supervised learning, training examples provide known target answers.

In reinforcement learning, the agent learns through interaction and
reward signals. It may not receive a correct action label for every
situation.

This difference is fundamental: reinforcement learning is concerned with
learning strategies for sequential decisions, often where the
consequences of actions influence future states and rewards.

**12.11 Comparing Machine Learning Approaches**

| **Characteristic** | **Supervised learning** | **Unsupervised learning** | **Reinforcement learning** |
|----|----|----|----|
| Main information | Inputs and known targets | Data without predefined target labels for the task | Interaction and reward signals |
| Objective | Predict targets | Discover patterns or structure | Learn a policy that achieves desirable cumulative outcomes |
| Typical output | Class labels or numerical predictions | Clusters, representations, or discovered structures | A policy or decision strategy |
| Common tasks | Classification and regression | Clustering and dimensionality reduction | Sequential decision-making |
| Example | Predicting house prices | Grouping customers by purchasing behavior | Learning a navigation strategy |
| Main challenge | Quality of labels and generalization | Interpreting discovered patterns | Balancing exploration, reward design, and long-term consequences |

**12.12 Training a Basic Machine Learning Model**

This section demonstrates a complete beginner-friendly classification
program using Python and scikit-learn.

The program uses the Iris dataset, a classic educational dataset
containing 150 flower samples, four numerical features, and three target
classes. The dataset is included in scikit-learn.

**12.12.1 Installation**

Install Python if it is not already available.

Then install scikit-learn using a terminal:

<img src="CHAPTER 12_media/media/image2.png"
style="width:6.26806in;height:0.25139in" />If your system uses the py
launcher on Windows, the following may also work:

<img src="CHAPTER 12_media/media/image3.png"
style="width:6.26806in;height:0.24306in" />Run the installation command
in a terminal, not inside a Python source file.

**12.12.2 Complete Python Program**

Save the following program as iris_classifier.py.

<img src="CHAPTER 12_media/media/image4.png"
style="width:6.26806in;height:3.49792in" />

<img src="CHAPTER 12_media/media/image5.png"
style="width:6.26806in;height:3.08611in" /><img src="CHAPTER 12_media/media/image6.png"
style="width:6.26806in;height:0.68681in" />The example follows the
documented scikit-learn APIs for loading the dataset and splitting data
into training and test subsets.

**12.12.3 Understanding the Program**

**Step 1: Import the libraries**

<img src="CHAPTER 12_media/media/image7.png"
style="width:5.58362in;height:1.007in" />

Each import makes a specific tool available.

- load_iris loads the educational dataset.

- train_test_split separates data into subsets.

- DecisionTreeClassifier provides a classification algorithm.

- accuracy_score calculates the proportion of correct predictions.

**Step 2: Load the dataset**

<img src="CHAPTER 12_media/media/image8.png"
style="width:5.44472in;height:0.31252in" />

The variable iris contains the dataset and associated information,
including the feature values and target labels.

**Step 3: Separate features and labels**

<img src="CHAPTER 12_media/media/image9.png"
style="width:5.5489in;height:0.6042in" />

By convention, uppercase X often represents the input feature matrix,
while lowercase y represents the target values.

In this dataset, each sample has four numerical features. The target
identifies the flower species.

**Step 4: Split the data**

<img src="CHAPTER 12_media/media/image10.png"
style="width:5.52806in;height:1.38202in" />

The argument test_size=0.2 reserves 20% of the samples for testing.

random_state=42 makes the randomized split reproducible for the same
data and compatible software behavior.

stratify=y helps preserve class proportions across the training and test
subsets.

For this dataset, the program uses 120 training samples and 30 test
samples.

**Step 5: Create the model**

<img src="CHAPTER 12_media/media/image11.png"
style="width:5.52806in;height:0.45836in" />

A decision tree makes predictions using a sequence of feature-based
decisions.

The variable model refers to the classifier object.

**Step 6: Train the model**

<img src="CHAPTER 12_media/media/image12.png"
style="width:5.45861in;height:0.27779in" />

The fit() method trains the model using the training features and their
known target labels.

Training is different from prediction: training uses examples to
construct the model, while prediction applies the trained model to new
inputs.

**Step 7: Generate predictions**

<img src="CHAPTER 12_media/media/image13.png"
style="width:5.52806in;height:0.29863in" />

The model predicts flower classes for the test samples.

Because the true labels for the test set are already available in
y_test, the predictions can be compared with them.

**Step 8: Evaluate accuracy**

<img src="CHAPTER 12_media/media/image14.png"
style="width:5.52806in;height:0.29863in" />

The accuracy score is the proportion of test samples classified
correctly.

The numerical result depends on the model, data, and software behavior.
The code is presented as an instructional example; I am not claiming to
have executed it here, so no measured output is asserted.

**Step 9: Predict a new sample**

<img src="CHAPTER 12_media/media/image15.png"
style="width:5.42389in;height:0.29168in" />

The four numbers represent the flower's sepal length, sepal width, petal
length, and petal width, respectively, in centimeters.

The outer list represents the collection of samples, and the inner list
represents one sample.

<img src="CHAPTER 12_media/media/image16.png"
style="width:5.52806in;height:0.50003in" />

The model returns a numerical class identifier. The code uses that
identifier to retrieve the corresponding species name.

**12.12.4 Training versus Inference**

**Training** is the process through which the model learns from training
data.

**Inference** is the process of using a trained model to generate a
prediction for an input.

| **Stage**  | **Method**          | **Purpose**                               |
|------------|---------------------|-------------------------------------------|
| Training   | model.fit(...)      | Learn from examples                       |
| Prediction | model.predict(...)  | Generate predictions                      |
| Evaluation | accuracy_score(...) | Measure performance against known answers |

The model can make predictions after training, but its ability to
predict does not guarantee that its predictions will be accurate.

**12.12.5 Common Errors and Troubleshooting**

| **Problem** | **Possible cause** | **Suggested response** |
|----|----|----|
| ModuleNotFoundError: No module named 'sklearn' | scikit-learn is not installed in the active Python environment | Install it using the appropriate Python interpreter |
| SyntaxError | A line contains invalid Python syntax | Check parentheses, quotation marks, and indentation |
| ValueError about the number of features | The input contains the wrong number of feature values | Provide four features in the correct order for the Iris model |
| NameError | A variable is used before it is defined | Check spelling and execution order |
| Different accuracy result | Different split, model, data, or environment | Check the code, random seed, and software versions |

------------------------------------------------------------------------

**12.13 Training, Validation, and Test Sets**

A machine learning dataset can be divided into separate subsets for
different purposes.

**Training Set**

The **training set** provides examples used to fit the model.

**Validation Set**

The **validation set** helps compare models, select hyperparameters, and
make design decisions.

A **hyperparameter** is a setting chosen by the developer rather than
learned directly as an ordinary model parameter during fitting. For a
decision tree, maximum tree depth is an example of a hyperparameter.

**Test Set**

The **test set** provides an estimate of how the final model performs on
data that was not used to train it or select its configuration.

A test set should not be repeatedly consulted during model development.
Doing so can indirectly influence design choices and make the final
estimate less independent.

**12.13.1 Comparison**

| **Dataset subset** | **Main purpose** | **Should it fit the model?** | **Should it guide model selection?** |
|----|----|----|----|
| Training | Learn model parameters | Yes | It is used during fitting |
| Validation | Compare configurations and select settings | Normally no, for ordinary holdout evaluation | Yes |
| Test | Estimate final performance on unseen data | No | No, until final evaluation |

The exact workflow varies by project. Some approaches use
cross-validation rather than a single validation set.

The fundamental principle is that **the data used to make development
decisions should be distinguished from the data used for the final
performance estimate**.

**12.14 Applications and Limitations**

Machine learning is useful for extracting patterns from data, but its
limitations must be considered.

**12.14.1 Data Quality**

Incorrect, incomplete, outdated, or inconsistent data can produce
unreliable models.

For example, a demand-forecasting model trained on incorrect sales
records may systematically overestimate or underestimate demand.

**12.14.2 Bias**

Training data may not represent the population or environment in which
the model will be used.

A model trained on customer data from one region may not perform equally
well in another region with different customer behavior.

**12.14.3 Generalization**

A model must perform adequately on new data, not only on examples it has
already seen.

A highly complex model may memorize training examples without learning
patterns that generalize well.

**12.14.4 Interpretability**

Some models are easier to understand than others.

A small decision tree may be relatively easy to inspect, whereas a large
neural network may be difficult to interpret in detail.

The appropriate balance between interpretability and predictive
performance depends on the application.

**12.14.5 When Machine Learning May Be Unsuitable**

Machine learning may not be the best choice when:

- A simple, reliable rule solves the problem.

- There is insufficient relevant data.

- Errors would have unacceptable consequences without safeguards.

- The desired outcome cannot be measured or defined clearly.

- Data collection would violate privacy or other requirements.

- The system would cost more to maintain than the value it provides.

A machine learning project should begin with the problem, not with the
assumption that an AI model is necessary.

**12.15 Chapter Summary**

Machine learning enables computers to learn patterns from data or
experience.

A machine learning project typically involves defining a problem,
collecting and preparing data, selecting an algorithm, training a model,
evaluating it, and monitoring its use.

In supervised learning, the model learns from examples with known
targets. Classification predicts categories, while regression predicts
numerical values.

Unsupervised learning identifies patterns in data without predefined
target labels for the task. Clustering groups similar observations,
while dimensionality reduction creates a lower-dimensional
representation.

Reinforcement learning involves an agent learning through interactions
and reward signals.

Training uses examples to fit a model. Inference uses the trained model
to produce predictions.

Training, validation, and test sets serve different purposes. Keeping
their roles separate is essential for reliable evaluation.

Finally, model quality depends on more than the algorithm. Data quality,
bias, generalization, and the consequences of errors all matter.

**12.16 Review Questions and Solutions**

**A. Multiple-Choice Questions**

1.  What is a machine learning model?

A. A collection of unrelated files\
B. A system that has learned patterns from data through a training
procedure\
C. A program that must always contain manually written rules for every
possible input\
D. A dataset without labels

2.  Which is an example of a feature in a house-price prediction model?

A. The price the model is supposed to predict\
B. The model's final accuracy score\
C. The property's floor area\
D. The name of the learning algorithm

3.  Which task is an example of classification?

A. Predicting a house's sale price\
B. Estimating tomorrow's electricity consumption\
C. Predicting the number of minutes required to complete a task\
D. Classifying an email as spam or legitimate

4.  Which task is an example of unsupervised learning?

A. Predicting a labeled flower species\
B. Grouping customers according to similarities without predefined
customer-group labels\
C. Learning from explicitly labeled examples\
D. Calculating a fixed mathematical formula

5.  What is the main purpose of a test set?

A. To provide a final estimate of performance on unseen data\
B. To replace the training algorithm\
C. To contain only incorrect labels\
D. To guarantee that the model never makes mistakes

**Solutions and Explanations**

1.  **B.** A trained model captures patterns that can be used to make
    predictions.

2.  **C.** Floor area is an input variable. The sale price is the
    target.

3.  **D.** Spam detection predicts a category.

4.  **B.** Clustering can discover groups without predefined target
    labels.

5.  **A.** A test set helps estimate generalization when it remains
    separate from training and model selection.

**B. Short-Answer Questions**

1.  Explain the difference between traditional programming and machine
    learning.

2.  Define dataset, sample, feature, and target.

3.  Explain the difference between classification and regression.

4.  Compare supervised learning, unsupervised learning, and
    reinforcement learning.

5.  Explain the difference between training and inference.

**Solutions and Explanations**

1.  Traditional programming explicitly specifies rules for processing
    inputs. Machine learning uses data and a learning algorithm to
    construct a model that captures useful patterns.

2.  A dataset is a collection of examples. A sample is one example. A
    feature is an input variable. A target is the desired output in
    supervised learning.

3.  Classification predicts categories, such as spam or legitimate
    email. Regression predicts numerical quantities, such as a house's
    price.

4.  Supervised learning learns from labeled examples. Unsupervised
    learning discovers structure without predefined target labels for
    the task. Reinforcement learning learns through interactions and
    reward signals.

5.  Training fits the model using training data. Inference uses the
    trained model to make predictions.

**C. Scenario-Based Questions**

1.  A shop wants to estimate next month's sales. Which broad type of
    machine learning task is likely appropriate if the target is a
    numerical sales total?

2.  A university wants to group students according to similarities in
    their study habits without predefined group labels. Which approach
    might be useful?

3.  A robot learns to navigate a simulated environment using rewards for
    reaching its destination. Which machine learning approach is being
    used?

**Solutions and Explanations**

1.  **Regression**, because the target is a numerical value.

2.  **Unsupervised learning**, potentially using clustering, because the
    university wants to discover groups without predefined target
    labels.

3.  **Reinforcement learning**, because the robot learns through
    interaction and reward signals.

**D. Code-Reading Questions**

Consider this code:

<img src="CHAPTER 12_media/media/image17.png"
style="width:5.42389in;height:1.77092in" />

1.  What does X represent?

2.  What does y represent?

3.  How many samples and features are represented by X in the standard
    Iris dataset?

4.  Why are the features and targets stored separately?

**Solutions and Explanations**

1.  X contains the input features.

2.  y contains the target class identifiers.

3.  The standard dataset contains 150 samples and four features, so
    X.shape is (150, 4). The target array contains 150 entries, so
    y.shape is (150,). These dimensions are documented by scikit-learn.

4.  Separating them makes it clear which information the model uses as
    input and which information it is expected to predict.

**E. Programming Exercise**

Modify the Iris example so that it prints the number of features and the
number of samples before splitting the data.

**Solution**

<img src="CHAPTER 12_media/media/image18.png"
style="width:5.48639in;height:1.94454in" />

**Explanation:** X.shape\[0\] gives the number of rows, X.shape\[1\]
gives the number of feature columns, and len(y) gives the number of
target entries.

**12.17 Glossary**

| **Term** | **Definition** |
|----|----|
| Machine Learning | Methods that allow computers to learn patterns from data or experience. |
| Model | A system fitted or trained to represent useful patterns for a task. |
| Dataset | A collection of examples. |
| Sample | One observation or example in a dataset. |
| Feature | An input variable used by a model. |
| Label | A known target associated with an example. |
| Target | The output that a supervised model is trained to predict. |
| Supervised Learning | Learning from examples with known targets. |
| Classification | Predicting a category. |
| Regression | Predicting a numerical value. |
| Unsupervised Learning | Learning patterns or structure without predefined target labels for the task. |
| Clustering | Grouping observations according to similarities. |
| Dimensionality Reduction | Reducing the number of dimensions used to represent data. |
| Reinforcement Learning | Learning through interaction and reward signals. |
| Agent | The learner or decision-making system in reinforcement learning. |
| Environment | The system in which a reinforcement learning agent operates. |
| Reward | A numerical signal associated with an outcome or action. |
| Training | The process of fitting a model using training data. |
| Inference | Using a trained model to generate predictions. |
| Hyperparameter | A model or training setting selected outside the ordinary fitting of model parameters. |
| Generalization | The ability to perform usefully on data beyond the training examples. |

**References**

**scikit-learn.** (n.d.). *Model evaluation: Quantifying the quality of
predictions*. scikit-learn documentation. [scikit-learn Model
Evaluation](https://scikit-learn.org/stable/modules/model_evaluation.html?highlight=cross_val_score&utm_source=chatgpt.com)

**scikit-learn.** (n.d.). *load_iris*. scikit-learn documentation. [Iris
dataset
reference](https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_iris.html?highlight=iris&utm_source=chatgpt.com)

**scikit-learn.** (n.d.). *train_test_split*. scikit-learn
documentation. [Data splitting
reference](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.train_test_split.html?utm_source=chatgpt.com)

**scikit-learn.** (n.d.). *KFold*. scikit-learn documentation.
[Cross-validation
reference](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.KFold?utm_source=chatgpt.com)

**Google for Developers.** (n.d.). *Machine Learning Crash Course*.
[Google Machine Learning Crash
Course](https://developers.google.com/machine-learning/crash-course?utm_source=chatgpt.com)

**Google for Developers.** (n.d.). *Classification*. Machine Learning
Crash Course. [Classification
module](https://developers.google.com/machine-learning/crash-course/classification?utm_source=chatgpt.com)

**Google for Developers.** (n.d.). *Datasets: Data characteristics*.
Machine Learning Crash Course. [Dataset
characteristics](https://developers.google.com/machine-learning/crash-course/overfitting/data-characteristics?utm_source=chatgpt.com)

**Google for Developers.** (n.d.). *Datasets: Labels*. Machine Learning
Crash Course. [Dataset
labels](https://developers.google.com/machine-learning/crash-course/overfitting/labels?utm_source=chatgpt.com)

**Google for Developers.** (n.d.). *Linear regression*. Machine Learning
Crash Course. [Linear regression
module](https://developers.google.com/machine-learning/crash-course/linear-regression?utm_source=chatgpt.com)

**Figure Resources**

Figure 12.1 — Features and Labels in a Dataset:
<https://www.geeksforgeeks.org/machine-learning/features-and-labels-in-supervised-learning-a-practical-approach/>
