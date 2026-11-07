**Chapter 13 — Evaluation**

**13.1 Introduction to Model Evaluation**

Training a machine learning model is not enough to establish that it is
useful.

A model may perform very well on its training examples but make poor
predictions for new cases. It may also appear accurate while making the
particular mistakes that matter most in its application.

**Model evaluation** is the process of measuring and interpreting a
model's performance against clearly defined criteria.

Evaluation helps answer questions such as:

- How often does the model predict correctly?

- How large are its numerical prediction errors?

- Which types of mistakes does it make?

- Does it perform well on data it has not seen?

- Is its performance appropriate for the intended use?

- Could the evaluation results be misleading?

The appropriate evaluation method depends on the task.

A classification model that identifies spam messages requires different
metrics from a regression model that predicts electricity demand.

Even two classification systems may require different metrics if their
mistakes have different consequences.

**13.2 Generalization**

**Generalization** is a model's ability to perform usefully on new
examples drawn from the relevant population or operating environment.

Suppose a model is trained to recognize flowers using photographs
collected in a laboratory. If it is later used on photographs taken
outdoors under different lighting conditions, its performance may
change.

A model that performs well only on familiar examples has limited
practical value.

**13.2.1 Training Performance and Test Performance**

Training performance describes how well the model performs on the
examples used to fit it.

Test performance describes how well it performs on a separate set of
examples that were not used to fit the model or select its
configuration.

These values can differ substantially.

For example:

| **Measurement**   | **Illustrative accuracy** |
|-------------------|---------------------------|
| Training accuracy | 99%                       |
| Test accuracy     | 78%                       |

These are hypothetical numbers.

The difference suggests that the model may have learned patterns
specific to the training data that do not transfer effectively to unseen
examples.

However, a difference between training and test performance does not
automatically identify the cause. The dataset, evaluation method, model
complexity, and possible distribution differences should also be
investigated.

**13.2.2 Why Generalization Matters**

In practical applications, a model is generally used on cases that were
not part of its training data.

A model that memorizes its training set may fail when presented with new
customers, images, transactions, or environmental conditions.

Evaluation should therefore approximate the conditions in which the
model will actually be used.

**13.3 Overfitting and Underfitting**

Two common problems in machine learning are overfitting and
underfitting.

**13.3.1 Overfitting**

**Overfitting** occurs when a model fits the training data too closely
and captures patterns that do not generalize well.

Some of the patterns learned may reflect random noise, accidental
correlations, or peculiarities of the training sample rather than stable
relationships.

Consider a student who memorizes the answers to a set of practice
questions but does not understand the underlying concepts.

The student may perform very well when the same questions appear again
but struggle with unfamiliar questions.

This is a teaching analogy for overfitting, not a literal description of
how every machine learning model works.

**Common Causes of Overfitting**

- Excessive model complexity relative to the available data.

- Training for too long in some learning settings.

- Too many irrelevant or noisy features.

- Data leakage.

- Repeatedly adjusting a model to perform well on the test set.

**Possible Remedies**

- Use more representative training data.

- Reduce model complexity.

- Apply regularization where appropriate.

- Select features carefully.

- Use cross-validation or an appropriate validation set.

- Prevent data leakage.

- Stop training based on validation performance when the algorithm
  supports this approach.

**13.3.2 Underfitting**

**Underfitting** occurs when a model is too limited to capture important
patterns in the data.

For example, suppose the relationship between a house's price and its
features is complex, but the model uses an excessively simple
relationship that cannot represent the important patterns.

The model may perform poorly on both training and test data.

**Common Causes of Underfitting**

- A model that is too simple for the task.

- Insufficient training.

- Inadequate features.

- Excessive regularization.

- Poorly chosen model settings.

**Possible Remedies**

- Choose a model capable of representing the relevant patterns.

- Improve feature quality.

- Train adequately.

- Reduce excessive regularization.

- Investigate whether important variables are missing.

**13.3.3 Comparing the Two Problems**

| **Characteristic** | **Underfitting** | **Overfitting** |
|----|----|----|
| Main problem | Fails to capture important patterns | Learns training-specific patterns that do not generalize |
| Training performance | Often poor | Often very good |
| Test performance | Often poor | May be substantially worse than training performance |
| Possible response | Increase appropriate model capacity or improve features | Reduce unnecessary complexity, improve data, or strengthen validation |
| Main concern | Insufficient learning | Poor generalization |

<img src="CHAPTER 13_media/media/image1.jpeg"
style="width:5.05556in;height:3.15972in"
alt="Overfitting and underfitting in machine learning" />

Figure 13.1 — Overfitting and Underfitting

**13.3.4 The Bias-Variance Trade-Off**

The **bias-variance trade-off** provides an intuitive way to understand
why models may perform poorly.

- **Bias** describes systematic error associated with assumptions that
  prevent a model from capturing the true relationship adequately.

- **Variance** describes how sensitive a model's learned behavior is to
  changes in the training data.

A model with high bias may be too simple. A model with high variance may
fit the training data too closely and change substantially when trained
on another sample.

Increasing model complexity can reduce some forms of bias while
increasing variance.

The goal is not to eliminate all bias or all variance independently. It
is to choose an approach that achieves suitable performance on unseen
data.

This is an introductory interpretation. The formal bias-variance
decomposition depends on the model, the prediction setting, and the
assumptions used in the analysis.

**13.4 Training, Validation, and Test Sets**

Reliable evaluation requires careful separation of data.

**13.4.1 Training Set**

The training set is used to fit the model.

**13.4.2 Validation Set**

The validation set helps compare model configurations, choose
hyperparameters, and make development decisions.

For example, a developer might compare decision trees with different
maximum depths and select the configuration that performs best according
to a predefined validation procedure.

**13.4.3 Test Set**

The test set is used to estimate the performance of the selected model
on unseen data.

It should not be used repeatedly to decide which model or settings to
choose.

If developers repeatedly inspect test results and adjust the model
accordingly, the test set gradually influences development decisions.
Its estimate becomes less independent.

**13.4.4 Example of Data Separation**

Suppose a dataset contains 1,000 examples.

One possible split is:

| **Subset** | **Number of examples** | **Percentage** |
|------------|------------------------|----------------|
| Training   | 700                    | 70%            |
| Validation | 150                    | 15%            |
| Test       | 150                    | 15%            |
| Total      | 1,000                  | 100%           |

These percentages are illustrative, not universal requirements.

The appropriate split depends on the dataset size, the problem, the
model-selection procedure, and whether the observations are independent.

For time-series forecasting, for example, a chronological split may be
more appropriate than a random split because future observations should
not influence predictions about the past.

**13.4.5 Cross-Validation**

**Cross-validation** is a technique for estimating model performance
across multiple data splits.

In $`k`$-fold cross-validation, the data is divided into $`k`$ subsets
called folds.

The model is trained on $`k - 1\`$folds and evaluated on the remaining
fold. This process is repeated so that each fold serves as the
validation fold.

The results can then be summarized across the folds.

Cross-validation can provide a more informative estimate than relying on
one validation split, especially when data is limited. However, it must
be designed carefully to avoid leakage and to respect data dependencies.

**13.5 Accuracy and Its Limitations**

**Accuracy** is the proportion of predictions that are correct.

It is a common metric for classification tasks.

**13.5.1 Accuracy Formula**

``` math
\text{Accuracy} = \frac{\text{Number~of~Correct~Predictions}}{\text{Total~Number~of~Predictions}}
```

For binary classification, accuracy can also be calculated from the
confusion-matrix counts:

``` math
\text{Accuracy} = \frac{TP + TN}{TP + TN + FP + FN}
```

where:

- $`TP`$ = true positives.

- $`TN\`$= true negatives.

- $`FP`$ = false positives.

- $`FN`$ = false negatives.

These terms are defined in the next section.

**13.5.2 Worked Example**

Suppose a model classifies 100 messages:

- 85 predictions are correct.

- 15 predictions are incorrect.

The accuracy is:

``` math
{\text{Accuracy} = \frac{85}{100}
}{\text{Accuracy} = 0.85}
```

Convert to a percentage:

``` math
0.85 \times 100\% = 85\%
```

The model correctly classified 85% of the evaluated messages.

**13.5.3 Why Accuracy Can Be Misleading**

Accuracy may be misleading when classes are imbalanced.

Suppose 1,000 transactions contain:

- 990 legitimate transactions.

- 10 fraudulent transactions.

A model that predicts every transaction as legitimate achieves:

``` math
\text{Accuracy} = \frac{990}{1000} = 99\%
```

Yet it fails to detect every fraudulent transaction.

The model has high accuracy but no ability to identify the rare positive
class.

This example shows why accuracy should not be interpreted alone when
some errors are especially important.

Other relevant metrics may include precision, recall, F1-score,
specificity, and measures based on predicted probabilities.

The choice depends on the task and its costs.

**13.6 Confusion Matrices**

A **confusion matrix** summarizes the relationship between actual
classes and predicted classes.

For binary classification, we first designate one category as the
**positive class**.

For example, in a fraud-detection task:

- Positive = fraudulent transaction.

- Negative = legitimate transaction.

The positive class is the category the system is designed to detect. It
is not necessarily a morally positive or desirable outcome.

**13.6.1 The Four Outcomes**

**True Positive (TP):** The model predicts positive, and the actual
class is positive.

Example: A fraudulent transaction is correctly flagged.

**True Negative (TN):** The model predicts negative, and the actual
class is negative.

Example: A legitimate transaction is correctly classified as legitimate.

**False Positive (FP):** The model predicts positive, but the actual
class is negative.

Example: A legitimate transaction is incorrectly flagged as fraudulent.

**False Negative (FN):** The model predicts negative, but the actual
class is positive.

Example: A fraudulent transaction is incorrectly classified as
legitimate.

**13.6.2 Example Confusion Matrix**

Suppose a model evaluates 100 transactions.

|  | **Actual positive: Fraud** | **Actual negative: Legitimate** |
|----|----|----|
| **Predicted positive: Flagged** | TP = 18 | FP = 7 |
| **Predicted negative: Not flagged** | FN = 2 | TN = 73 |

Check the total:

``` math
18 + 7 + 2 + 73 = 100
```

The model correctly identifies 18 fraudulent transactions and 73
legitimate transactions.

It incorrectly flags 7 legitimate transactions and misses 2 fraudulent
transactions.

<img src="CHAPTER 13_media/media/image2.png"
style="width:6.26806in;height:1.72986in" />

Figure 13.2 — A Confusion Matrix

The orientation of a confusion matrix can vary between software
packages. Always read the row and column labels rather than assuming
that actual classes appear on a particular axis.

**13.6.3 Why False Positives and False Negatives Matter**

The consequences of the two error types depend on the application.

In fraud detection:

- A false positive may inconvenience a legitimate customer.

- A false negative may allow fraudulent activity to go undetected.

In medical screening:

- A false positive may lead to unnecessary follow-up tests.

- A false negative may delay further investigation of a condition.

Neither error is automatically more important in every situation. Their
relative costs depend on the context.

**13.7 Precision, Recall, and F1-Score**

Accuracy alone does not describe every aspect of classification
performance.

**Precision** measures how often positive predictions are correct.

**Recall** measures how many of the actual positive cases are detected.

**F1-score** combines precision and recall using their harmonic mean.

These metrics are particularly useful when the positive class is
important or when classes are imbalanced. Their interpretation depends
on how the positive class is defined.

**13.7.1 Precision**

Precision answers:

*Of all the cases predicted as positive, what proportion were actually
positive?*

The formula is:

``` math
\text{Precision} = \frac{TP}{TP + FP}
```

where:

- $`TP`$ is the number of true positives.

- $`FP`$ is the number of false positives.

Using the fraud-detection example:

``` math
TP = 18,\quad\quad FP = 7
```

Substitute the values:

``` math
{\text{Precision} = \frac{18}{18 + 7}
}{\text{Precision} = \frac{18}{25} = 0.72}
```

As a percentage:

``` math
0.72 \times 100\% = 72\%
```

**Interpretation:** Of the transactions flagged as fraudulent, 72% were
actually fraudulent.

Higher precision means fewer false positives relative to the total
number of positive predictions.

Precision alone does not reveal how many actual positive cases the model
missed.

**13.7.2 Recall**

Recall answers:

*Of all the actual positive cases, what proportion did the model
identify?*

Recall is also known as sensitivity or the true positive rate.

The formula is:

``` math
\text{Recall} = \frac{TP}{TP + FN}
```

where:

- $`TP`$ is the number of true positives.

- $`FN\`$is the number of false negatives.

Using the same example:

``` math
TP = 18,\quad\quad FN = 2
```

Substitute:

``` math
{\text{Recall} = \frac{18}{18 + 2}
}{\text{Recall} = \frac{18}{20} = 0.90}
```

As a percentage:

``` math
0.90 \times 100\% = 90\%
```

**Interpretation:** The model identified 90% of the actual fraudulent
transactions.

Higher recall means fewer actual positive cases are missed.

However, increasing recall may also increase the number of false
positives, depending on the model and its decision threshold.

**13.7.3 F1-Score**

The F1-score combines precision and recall.

Its formula is:

``` math
F_{1} = 2 \times \frac{\text{Precision} \times \text{Recall}}{\text{Precision} + \text{Recall}}
```

The F1-score is the harmonic mean of precision and recall. It places
greater emphasis on the smaller of the two values than an ordinary
arithmetic mean would.

Using the values from the previous example:

``` math
{\text{Precision} = 0.72
}{\text{Recall} = 0.90}
```

Substitute:

``` math
F_{1} = 2 \times \frac{0.72 \times 0.90}{0.72 + 0.90}
```

First, calculate the numerator inside the fraction:

``` math
0.72 \times 0.90 = 0.648
```

Then calculate the denominator:

``` math
0.72 + 0.90 = 1.62
```

Therefore:

``` math
{F_{1} = 2 \times \frac{0.648}{1.62}
}{F_{1} = 2 \times 0.4
}{F_{1} = 0.80}
```

The F1-score is **0.80, or 80%**.

**13.7.4 Interpreting the Three Metrics**

| **Metric** | **Formula**  | **Main question**                                  |
|------------|--------------|----------------------------------------------------|
| Precision  |              
              ``` math      
              TP/(TP + FP)  
              ```           | How reliable are positive predictions?             |
| Recall     |              
              ``` math      
              TP/(TP + FN)  
              ```           | How many actual positive cases are detected?       |
| F1-score   |              
              ``` math      
              2PR/(P + R)   
              ```           | What is the harmonic mean of precision and recall? |

Here, $`P\`$represents precision and $`R\`$represents recall in the F1
formula.

A model can have high precision but low recall if it flags only a small
number of cases and most flagged cases are correct.

Conversely, a model can have high recall but lower precision if it flags
many cases, including many false positives.

**13.7.5 Limitations of Precision, Recall, and F1**

These metrics do not capture every aspect of performance.

- Precision depends on the proportion of positive cases in the evaluated
  population.

- Recall does not directly measure the number of false positives.

- F1-score does not account for true negatives in its formula.

- F1-score does not represent the financial, medical, or social cost of
  errors.

- A single metric can conceal poor performance in particular subgroups.

The appropriate metric should be chosen according to the task's goals
and risks.

**13.8 Evaluating Regression Models**

Regression models predict numerical values.

Their errors can be measured by comparing each prediction with the
corresponding actual value.

Two common metrics are Mean Absolute Error (MAE) and Mean Squared Error
(MSE).

**13.8.1 Mean Absolute Error (MAE)**

**Mean Absolute Error** measures the average absolute difference between
actual and predicted values.

The formula is:

``` math
\text{MAE} = \frac{1}{n}\sum_{i = 1}^{n}\left| y_{i} - {\hat{y}}_{i} \right|
```

where:

- $`n`$ is the number of observations.

- $`y_{i}`$ is the actual value for observation $`i`$.

- $`{\hat{y}}_{i}\`$is the predicted value for observation $`i`$.

- $`| \cdot |`$means absolute value.

- $`\sum_{}^{}`$ means to add the values across all observations.

Absolute value ensures that errors do not cancel each other out because
of opposite signs.

**Worked Example**

Suppose a model predicts the following values:

| **Observation** | **Actual value** | **Predicted value** | **Absolute error** |
|-----------------|------------------|---------------------|--------------------|
| 1               | 10               | 12                  | 2                  |
| 2               | 20               | 18                  | 2                  |
| 3               | 30               | 33                  | 3                  |

First, calculate the absolute errors:

``` math
{|10 - 12| = 2
}{|20 - 18| = 2
}{|30 - 33| = 3}
```

Add the errors:

``` math
2 + 2 + 3 = 7
```

There are three observations, so:

``` math
{\text{MAE} = \frac{7}{3}
}{\text{MAE} \approx 2.33}
```

The MAE is approximately **2.33 units**.

**Interpretation:** The average absolute prediction error is
approximately 2.33 units for these observations.

MAE is expressed in the same units as the target. It is relatively easy
to interpret and does not square larger errors.

However, it does not reveal the direction of the errors and may conceal
a small number of unusually large mistakes.

**13.8.2 Mean Squared Error (MSE)**

**Mean Squared Error** measures the average squared difference between
actual and predicted values.

The formula is:

``` math
\text{MSE} = \frac{1}{n}\sum_{i = 1}^{n}\left( y_{i} - {\hat{y}}_{i} \right)^{2}
```

The symbols have the same meanings as in the MAE formula.

The difference is that each error is squared rather than converted to an
absolute value.

**Worked Example**

Use the same values:

| **Observation** | **Actual value** | **Predicted value** | **Error** | **Squared error** |
|----|----|----|----|----|
| 1 | 10 | 12 | -2 | 4 |
| 2 | 20 | 18 | 2 | 4 |
| 3 | 30 | 33 | -3 | 9 |

The error is defined here as actual minus predicted.

Square each error:

``` math
{( - 2)^{2} = 4
}{2^{2} = 4}
```

``` math
( - 3)^{2} = 9
```

Add the squared errors:

``` math
4 + 4 + 9 = 17
```

Divide by the number of observations:

``` math
\text{MSE} = \frac{17}{3}
```

``` math
\text{MSE} \approx 5.67
```

The MSE is approximately **5.67 squared units**.

**Interpretation:** The average squared prediction error is
approximately 5.67 squared units for this example.

**13.8.3 Comparing MAE and MSE**

| **Characteristic** | **MAE** | **MSE** |
|----|----|----|
| Error calculation | Absolute error | Squared error |
| Formula | 
``` math
(\frac{1}{n}\sum_{}^{}
``` | 
``` math
y_{i} - {\hat{y}}_{i}
``` |
| Units | Same as target | Squared target units |
| Effect of large errors | Increases linearly with error magnitude | Increases quadratically with error magnitude |
| Interpretation | Average absolute error | Average squared error |

MSE gives larger errors more influence because the errors are squared.

For example, an error of 4 contributes 16 to the squared-error total,
whereas an error of 2 contributes only 4.

Neither metric is universally better. MAE may be easier to interpret,
while MSE may be useful when larger errors should receive substantially
greater penalties.

**13.8.4 Root Mean Squared Error**

Another common metric is Root Mean Squared Error (RMSE):

``` math
\text{RMSE} = \sqrt{\text{MSE}}
```

For the preceding example:

``` math
\text{RMSE} = \sqrt{5.67} \approx 2.38
```

RMSE is expressed in the same units as the target, unlike MSE.

It still gives relatively greater influence to large errors.

**13.9 Data Leakage**

**Data leakage** occurs when information that should not be available
during model training or development influences the model or its
evaluation.

Leakage can produce overly optimistic results that do not reflect
real-world performance.

It is one of the most important problems to prevent in machine learning
evaluation.

**13.9.1 Example 1: Using the Target as a Feature**

Suppose a model is intended to predict whether a customer will cancel a
subscription.

The dataset contains:

- Customer age.

- Subscription duration.

- Recent activity.

- Cancellation status.

- Account closure date.

If the account closure date directly reveals that the customer has
already cancelled, including it as an input feature leaks information
about the target.

The model may appear highly accurate because it uses information that
would not be available at the time a real prediction must be made.

The correct response is to examine when each feature becomes available
and whether it is legitimate for the intended prediction task.

**13.9.2 Example 2: Preprocessing Before Splitting the Data**

Suppose a developer standardizes a dataset by calculating its mean and
standard deviation using every observation, then splits the transformed
data into training and test sets.

The transformation parameters have been influenced by the test data.

Although the feature values do not contain the labels, information from
the test distribution has influenced the training process.

This can bias the evaluation, particularly when the transformation or
feature selection procedure is more involved.

A safer approach is:

1.  Split the data into training and test sets.

2.  Fit preprocessing steps using only the training data.

3.  Apply the fitted transformations to the training data.

4.  Apply the same transformations to the test data without refitting
    them on the test set.

In scikit-learn, pipelines can help keep preprocessing and model fitting
together in a consistent procedure.

For example:

<img src="CHAPTER 13_media/media/image3.png"
style="width:5.46556in;height:1.58341in" />

This pipeline ensures that, when the pipeline is fitted on the training
subset, the scaler learns its transformation parameters from that
training subset. The same fitted transformation is then applied when the
pipeline predicts on new data.

The pipeline does not automatically fix every possible form of leakage.
Developers must still separate data correctly and ensure that the
features are appropriate for the prediction time.

**13.9.3 Example 3: Repeatedly Tuning Against the Test Set**

Suppose a developer tries 100 model configurations and repeatedly
selects whichever produces the highest test score.

Even though the test labels are not directly used in gradient-based
training, the developer's repeated decisions are influenced by the test
results.

The test set has effectively become part of model selection.

The final score may therefore overestimate performance on genuinely new
data.

**Prevention:** Use training data for fitting, validation data or
cross-validation for model selection, and reserve the test set for the
final evaluation.

**13.10 Improving Evaluation Reliability**

Reliable evaluation requires more than calculating a metric correctly.

**13.10.1 Use Representative Data**

Evaluation data should reflect the population and conditions in which
the model will be used.

If a model is intended for use across multiple regions, an evaluation
dataset containing only one region may provide an incomplete picture.

**13.10.2 Choose Appropriate Metrics**

Select metrics according to the task and the consequences of errors.

For example:

- Accuracy may be useful when class proportions and error costs are
  reasonably balanced.

- Precision may matter when false positive predictions are costly.

- Recall may matter when missing positive cases is particularly harmful.

- F1-score may help summarize precision and recall.

- MAE may be appropriate when average absolute error is meaningful.

- MSE may be useful when large errors should receive greater penalties.

No single metric is best for every problem.

**13.10.3 Prevent Data Leakage**

Keep test data separate from training and model selection.

Fit data-dependent preprocessing steps only on the training data, then
apply the fitted transformations to validation and test data.

Consider whether features would genuinely be available at prediction
time.

**13.10.4 Use Appropriate Splitting Strategies**

Random splitting can be appropriate when examples are sufficiently
independent and representative.

Other situations require different strategies:

- Time-series forecasting often requires chronological separation.

- Repeated measurements from the same person may require grouping
  observations so that related records do not appear across training and
  test sets.

- Grouped or geographic data may require splits that reflect the
  intended deployment setting.

The split should reflect how the model will encounter new information.

**13.10.5 Consider Class Imbalance**

If one class is much more common than another, accuracy may conceal poor
detection of the rare class.

Use metrics that reveal performance on important classes and inspect the
confusion matrix.

**13.10.6 Evaluate Subgroups Where Appropriate**

Overall performance may hide differences across relevant populations.

When appropriate and legally permissible, evaluate whether errors vary
across groups and investigate potential causes.

This analysis should be conducted carefully, with attention to privacy,
sample sizes, measurement quality, and the fairness requirements of the
application.

**13.10.7 Make Results Reproducible**

Document:

- The dataset and how it was collected.

- The preprocessing steps.

- The model and its settings.

- The train-validation-test procedure.

- The evaluation metrics.

- The software environment.

- Random seeds where applicable.

- Known limitations.

Reproducibility helps others inspect the methodology and determine
whether the reported results are credible.

**13.10.8 Interpret Results in Context**

A high metric does not automatically imply that a model is safe, fair,
or useful.

The decision to deploy a model should also consider error consequences,
uncertainty, operating conditions, privacy, and appropriate human
oversight.

Evaluation is a tool for informed decision-making, not a substitute for
it.

**13.11 Chapter Summary**

- Model evaluation measures how well a machine learning model performs
  against defined criteria.

- Generalization describes the ability to perform usefully on new
  examples. Overfitting occurs when a model fits training-specific
  patterns that do not transfer well, while underfitting occurs when a
  model fails to capture important relationships.

- Training data is used to fit the model, validation data helps guide
  model selection, and test data provides a final estimate of
  performance.

- Accuracy measures the proportion of correct predictions, but it can be
  misleading when classes are imbalanced.

- A confusion matrix distinguishes true positives, true negatives, false
  positives, and false negatives. Precision measures the reliability of
  positive predictions, recall measures the proportion of actual
  positives detected, and F1-score combines precision and recall.

- For regression, MAE measures average absolute error, while MSE
  measures average squared error.

- Data leakage occurs when information that should remain unavailable
  influences training or evaluation. Preventing leakage, using
  representative data, selecting appropriate metrics, and preserving a
  separate test set all improve evaluation reliability.

- The central lesson is that **a model's performance must be measured on
  appropriate data using metrics that reflect the intended task and the
  consequences of its mistakes**.

**13.12 Review Questions and Solutions**

**A. Multiple-Choice Questions**

1.  What is generalization?

A. Memorizing the training dataset\
B. The ability to perform usefully on new examples\
C. Increasing the number of features without evaluating them\
D. Calculating training accuracy only

2.  Which pattern most strongly suggests overfitting?

A. Poor training and poor test performance\
B. Good training performance and substantially poorer test performance\
C. Identical predictions for every input\
D. A model that has no parameters

3.  Which dataset should generally be reserved for final evaluation
    after model selection?

A. Training set\
B. Validation set\
C. Test set\
D. A duplicate of the training set

4.  What does precision measure?

A. The proportion of actual positive cases that are detected\
B. The proportion of positive predictions that are correct\
C. The average squared regression error\
D. The proportion of negative predictions that are incorrect

5.  What is data leakage?

A. Any missing value in a dataset\
B. The use of a small training set\
C. A model that predicts a category\
D. Information that improperly influences model training or evaluation

6.  Which metric gives larger errors greater influence by squaring them?

A. Accuracy\
B. Recall\
C. Mean Squared Error\
D. Precision

**Solutions and Explanations**

1.  **B.** Generalization concerns performance on new examples.

2.  **B.** A large gap between training and test performance can
    indicate overfitting, although other causes should also be
    investigated.

3.  **C.** The test set should remain separate from model selection to
    provide a more independent final estimate.

4.  **B.** Precision divides true positives by all positive predictions.

5.  **D.** Leakage occurs when information that should be unavailable
    improperly influences the process.

6.  **C.** MSE squares errors before averaging them.

**B. True-or-False Questions**

1.  A model with 99% training accuracy must be reliable in real-world
    use.

2.  Underfitting may occur when a model is too simple to capture
    important patterns.

3.  A false positive is a negative case incorrectly predicted as
    positive.

4.  Recall measures the proportion of actual positive cases detected.

5.  MSE is expressed in the same units as the target.

6.  The test set should repeatedly guide model selection.

**Solutions and Explanations**

1.  **False.** High training accuracy does not guarantee generalization.

2.  **True.** An overly limited model may fail to represent the
    relationship in the data.

3.  **True.** A false positive is a predicted positive that is actually
    negative.

4.  **True.** Recall is $`TP/(TP + FN)`$.

5.  **False.** MSE is expressed in squared target units. RMSE is
    expressed in the same units as the target.

6.  **False.** Repeated test-set tuning makes the test results less
    independent.

**C. Numerical Problems**

1.  A classifier correctly predicts 72 of 90 observations. Calculate its
    accuracy.

2.  A model produces 30 true positives and 10 false positives. Calculate
    precision.

3.  A model produces 45 true positives and 15 false negatives. Calculate
    recall.

4.  A regression model produces absolute errors of 1, 3, and 5.
    Calculate MAE.

5.  A regression model produces errors of 1, -2, and 3. Calculate MSE.

**Solutions and Explanations**

**1. Accuracy**

Formula:

``` math
\text{Accuracy} = \frac{\text{Correct~Predictions}}{\text{Total~Predictions}}
```

Substitute:

``` math
\text{Accuracy} = \frac{72}{90} = 0.8
```

Convert to a percentage:

``` math
0.8 \times 100\% = 80\%
```

**Answer: 80%.**

**2. Precision**

Formula:

``` math
\text{Precision} = \frac{TP}{TP + FP}
```

Substitute:

``` math
{\text{Precision} = \frac{30}{30 + 10}
}{\text{Precision} = \frac{30}{40} = 0.75}
```

**Answer: 0.75, or 75%.**

**3. Recall**

Formula:

``` math
\text{Recall} = \frac{TP}{TP + FN}
```

Substitute:

``` math
{\text{Recall} = \frac{45}{45 + 15}
}{\text{Recall} = \frac{45}{60} = 0.75}
```

**Answer: 0.75, or 75%.**

**4. MAE**

Formula:

``` math
\text{MAE} = \frac{\text{Sum~of~Absolute~Errors}}{\text{Number~of~Observations}}
```

Substitute:

``` math
\text{MAE} = \frac{1 + 3 + 5}{3}
```

``` math
\text{MAE} = \frac{9}{3} = 3
```

**Answer: MAE = 3 units.**

**5. MSE**

Formula:

``` math
\text{MSE} = \frac{1}{n}\sum_{}^{}e_{i}^{2}
```

where $`e_{i}`$ is the prediction error for observation $`i`$.

Square each error:

``` math
1^{2} = 1
```

``` math
( - 2)^{2} = 4
```

``` math
3^{2} = 9
```

Add the squared errors:

``` math
1 + 4 + 9 = 14
```

Divide by three:

``` math
\text{MSE} = \frac{14}{3} \approx 4.67
```

**Answer: MSE ≈ 4.67 squared units.**

**D. Confusion Matrix Exercise**

A classifier produces the following results:

- True positives: 40.

- True negatives: 50.

- False positives: 10.

- False negatives: 20.

Calculate:

1.  The total number of observations.

2.  Accuracy.

3.  Precision.

4.  Recall.

5.  F1-score.

**Solutions and Explanations**

**1. Total observations**

``` math
{N = TP + TN + FP + FN
}{N = 40 + 50 + 10 + 20 = 120}
```

**Answer: 120 observations.**

**2. Accuracy**

``` math
{\text{Accuracy} = \frac{TP + TN}{N}
}{\text{Accuracy} = \frac{40 + 50}{120}
}{\text{Accuracy} = \frac{90}{120} = 0.75}
```

**Answer: 75%.**

**3. Precision**

``` math
{\text{Precision} = \frac{TP}{TP + FP}
}{\text{Precision} = \frac{40}{40 + 10}
}{\text{Precision} = \frac{40}{50} = 0.80}
```

**Answer: 80%.**

**4. Recall**

``` math
{\text{Recall} = \frac{TP}{TP + FN}
}{\text{Recall} = \frac{40}{40 + 20}
}{\text{Recall} = \frac{40}{60} \approx 0.667}
```

**Answer: Approximately 66.7%.**

**5. F1-score**

Use the precision and recall values:

``` math
{F_{1} = 2 \times \frac{PR}{P + R}
}{F_{1} = 2 \times \frac{0.80 \times 0.667}{0.80 + 0.667}
}{F_{1} \approx 2 \times \frac{0.5336}{1.467}
}{F_{1} \approx 0.727}
```

**Answer: Approximately 72.7%.**

**E. Scenario-Based Questions**

1.  A model achieves 99% accuracy on a dataset where 99% of the examples
    belong to one class. Why might this be misleading?

2.  A developer standardizes the entire dataset before splitting it into
    training and test sets. What problem may arise?

3.  A medical screening system must minimize the number of actual
    positive cases it misses. Which metric deserves particular
    attention?

4.  A model performs poorly on both training and test data. Which
    problem might be present?

**Solutions and Explanations**

1.  The model may simply predict the majority class. Accuracy can be
    high even when the minority class is never detected. Inspect the
    confusion matrix and relevant class-specific metrics.

2.  The preprocessing transformation may use information from the test
    distribution. Fit the transformation on the training data and apply
    it to the test data without refitting.

3.  **Recall** deserves particular attention because it measures the
    proportion of actual positive cases detected. Other metrics and
    clinical requirements must also be considered.

4.  **Underfitting** may be present. Investigate model capacity, feature
    quality, training adequacy, and regularization.

**F. Code-Reading Exercise**

Consider the following code:

<img src="CHAPTER 13_media/media/image4.png"
style="width:5.41695in;height:1.63203in" />

1.  How many predictions are correct?

2.  What is the expected numerical accuracy?

3.  Why is the score not necessarily sufficient to evaluate a
    high-stakes classifier?

**Solutions and Explanations**

1.  Four predictions are correct. The third prediction differs from the
    actual label.

2.  There are five observations, so:

``` math
\text{Accuracy} = \frac{4}{5} = 0.8
```

The expected output is:

0.8

This output follows directly from the supplied values; it is a
calculation, not a claim that the program was executed.

3.  Accuracy does not show which types of errors occurred or their
    consequences. A confusion matrix and additional metrics may be
    needed.

**13.13 Glossary**

| **Term** | **Definition** |
|----|----|
| Model Evaluation | Measuring and interpreting model performance. |
| Generalization | The ability to perform usefully on new examples. |
| Overfitting | Fitting training-specific patterns that do not generalize well. |
| Underfitting | Failing to capture important patterns in the data. |
| Bias | Systematic error associated with restrictive assumptions or model limitations. |
| Variance | Sensitivity of learned behavior to changes in training data. |
| Training Set | Data used to fit the model. |
| Validation Set | Data used to guide model selection and tuning. |
| Test Set | Data reserved for final performance estimation. |
| Cross-Validation | A procedure that evaluates models across multiple data splits. |
| Accuracy | The proportion of predictions that are correct. |
| Confusion Matrix | A table comparing actual and predicted classes. |
| True Positive | A positive case correctly predicted as positive. |
| True Negative | A negative case correctly predicted as negative. |
| False Positive | A negative case incorrectly predicted as positive. |
| False Negative | A positive case incorrectly predicted as negative. |
| Precision | The proportion of positive predictions that are correct. |
| Recall | The proportion of actual positive cases that are detected. |
| F1-Score | The harmonic mean of precision and recall. |
| MAE | Mean Absolute Error, the average absolute difference between actual and predicted values. |
| MSE | Mean Squared Error, the average squared difference between actual and predicted values. |
| RMSE | The square root of MSE. |
| Data Leakage | Improper influence of information that should not be available during training or evaluation. |
| Hyperparameter Tuning | Selecting model settings using an appropriate development procedure. |
| Distribution Shift | A change between the data distribution used during development and the data encountered later. |

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

Figure 13.1 — Overfitting and Underfitting:
<https://www.superannotate.com/blog/overfitting-and-underfitting-in-machine-learning>

Figure 13.2 — A Confusion Matrix:
<https://developers.google.com/machine-learning/crash-course/classification/thresholding>
