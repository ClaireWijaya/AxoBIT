**Chapter 11 — Introduction to AI**

**11.1 Introduction to Artificial Intelligence**

Artificial Intelligence, commonly abbreviated as **AI**, is a field of
computer science concerned with developing systems that perform tasks
associated with capabilities such as perception, learning, reasoning,
problem-solving, language understanding, and decision-making.

Examples of tasks that may involve AI include:

- Recognizing objects in photographs.

- Understanding questions written in natural language.

- Recommending movies or music.

- Detecting suspicious financial transactions.

- Predicting traffic conditions.

- Helping doctors interpret medical images.

- Generating text, images, or computer code.

Consider a navigation application that recommends a route to a
destination. It may use information about road networks, current
traffic, historical travel times, and road closures to estimate which
route is most suitable.

This is an example of intelligent behavior in a practical setting: the
system processes information and produces a recommendation based on its
objective.

However, **performing an intelligent task does not necessarily mean that
a computer thinks or understands in the same way as a human being**. An
AI system can produce useful results without possessing human
experiences, emotions, or consciousness.

**11.1.1 Why Is AI Important?**

AI is important because many modern tasks involve more information than
people can efficiently examine manually.

For example, a hospital may collect thousands of medical images. An AI
system can help identify patterns in those images, allowing qualified
medical professionals to investigate potentially important findings.

Similarly, an online store may have millions of products and customers.
AI can help recommend products that are relevant to particular users.

AI can contribute to:

1.  **Automation:** Performing repetitive or time-consuming tasks.

2.  **Prediction:** Estimating future outcomes from available
    information.

3.  **Pattern recognition:** Identifying meaningful structures in
    complex data.

4.  **Decision support:** Providing information that helps people make
    decisions.

5.  **Natural language processing:** Working with human language.

6.  **Content generation:** Producing text, images, audio, or other
    content.

7.  **Optimization:** Finding solutions that satisfy particular
    objectives and constraints.

These capabilities can improve efficiency and support new applications.
Their value nevertheless depends on the quality of the system, the
suitability of the task, and the consequences of its errors.

**11.1.2 A Simple Example**

Suppose a university wants to organize incoming student inquiries.

A traditional system might use a list of manually specified rules:

- If a message contains the phrase "tuition fee," direct it to the
  finance department.

- If it contains "course registration," direct it to the academic
  office.

- If it contains "dormitory," direct it to student accommodation
  services.

This is a rule-based approach.

An AI system might instead analyze examples of previously categorized
messages and learn patterns associated with different departments.

Both approaches can be useful. A rule-based system may be easier to
inspect when the rules are clear, while a learning-based system may
handle a wider variety of wording when suitable training data is
available.

Neither approach is automatically superior in every situation.

**11.2 Definitions and Scope of AI**

**11.2.1 What Does AI Attempt to Do?**

AI research investigates methods for creating systems that can solve
problems requiring different kinds of information processing.

Common areas include:

| **Area** | **Description** | **Example** |
|----|----|----|
| Search and planning | Finding a sequence of actions that achieves a goal | Planning a route |
| Knowledge representation | Representing facts and relationships in a form a computer can process | Storing relationships between diseases and symptoms |
| Reasoning | Drawing conclusions from available information | Applying logical rules to a problem |
| Machine learning | Learning patterns from data | Predicting house prices |
| Computer vision | Processing and interpreting visual information | Identifying objects in an image |
| Natural language processing | Processing human language | Classifying customer messages |
| Speech processing | Analyzing or generating speech | Speech recognition |
| Robotics | Perceiving and acting in a physical environment | Navigating a warehouse |
| Generative AI | Producing new content based on learned patterns | Generating a draft of a report |

These categories overlap. A single application may combine several of
them.

For example, a robot may use computer vision to detect objects, planning
to select a route, and machine learning to improve its perception.

**11.2.2 What AI Is and Is Not**

It is important to distinguish AI from several related concepts.

**AI is not synonymous with automation.** A simple timer that turns a
light on at 7:00 p.m. performs automation, but it does not necessarily
use AI.

**AI is not synonymous with the internet.** The internet is a global
network of connected systems. AI is a field of methods used to develop
systems that perform particular tasks. AI applications may operate
through the internet, but they do not require an internet connection in
every case.

**AI is not synonymous with a robot.** A robot is a physical or virtual
machine designed to carry out actions. Some robots use AI, but many
automated machines operate using fixed instructions.

**AI is not guaranteed to be correct.** An AI system may produce
incorrect predictions, unreliable recommendations, or fabricated
statements.

**AI is not necessarily conscious.** The ability to generate convincing
language or solve a task does not establish that a system has subjective
experiences.

**11.2.3 Narrow AI and Artificial General Intelligence**

AI capabilities can also be discussed in terms of their breadth.

**Narrow AI**, also called weak AI, refers to systems designed or
trained to perform particular tasks or a defined range of tasks.

Examples include:

- A model that classifies flowers.

- A speech-recognition system.

- A spam filter.

- A chess-playing program.

- A system that recommends products.

A narrow AI system may perform its designated task very effectively
without possessing general human abilities.

**Artificial General Intelligence (AGI)** is a proposed form of AI that
would have broad capabilities across many different intellectual tasks,
rather than being limited to a particular application.

There is no single universally accepted operational definition of AGI,
and claims about whether a system qualifies depend on the criteria used.

Modern AI systems can perform a broad variety of tasks, but broad
capability alone does not establish that they possess human-like general
intelligence in every relevant sense.

It is therefore useful to distinguish demonstrated performance on
specific tasks from claims about general intelligence.

**11.3 A Brief History of AI**

AI developed through decades of research in mathematics, logic,
computing, neuroscience, and statistics.

The following milestones provide a concise overview.

| **Period** | **Development** | **Significance** |
|----|----|----|
| Before the 1950s | Foundations in mathematical logic and computation | Researchers developed ideas about formal reasoning and what computers could calculate. |
| 1950 | Alan Turing published work proposing a way to discuss machine intelligence through observable behavior | The work helped establish an influential framework for discussing intelligent machines. |
| 1956 | Dartmouth summer research project | The term *artificial intelligence* became established as the name of a research field. |
| 1950s–1960s | Early symbolic AI and search programs | Researchers developed programs for logical reasoning, games, and problem-solving. |
| 1970s–1980s | Expert systems and periods of reduced funding | Rule-based systems found practical uses, but limitations in cost, flexibility, and performance contributed to periods of reduced enthusiasm known as AI winters. |
| 1980s–1990s | Renewed interest in machine learning and statistical methods | Researchers increasingly developed systems that learned patterns from examples. |
| 1997 | IBM's Deep Blue defeated world chess champion Garry Kasparov in a match | The event demonstrated the strength of specialized computer systems in a complex strategic game. |
| 2012 | AlexNet achieved a major improvement in image classification using a deep neural network | The result helped accelerate the adoption of deep learning in computer vision. |
| 2016 | AlphaGo defeated Go champion Lee Sedol | The result demonstrated the power of combining neural networks with search methods in a challenging game. |
| 2017 onward | Transformer architectures and large-scale language models advanced | These developments contributed to major improvements in language processing and generative AI. |
| 2020s | Generative AI tools became widely accessible | Systems began supporting tasks involving text, images, audio, video, and programming. |

Historical developments are not evidence that AI has solved every
problem associated with intelligence. Progress has been uneven, and
successful systems often depend on substantial computing resources,
suitable data, careful design, and task-specific evaluation.

For historical background, the original Dartmouth proposal and Turing's
work are useful starting points for further study.

**11.4 Major Approaches to AI**

There are several ways to organize AI approaches. Two important
categories are rule-based systems and learning-based systems.

**11.4.1 Rule-Based Systems**

A rule-based system uses explicitly specified rules to determine what to
do in particular situations.

A rule may have the following structure:

**IF a condition is satisfied, THEN perform an action.**

For example:

- IF the temperature is above a specified threshold, THEN activate the
  cooling system.

- IF a student has completed all required prerequisites, THEN permit
  course registration.

- IF an invoice is overdue, THEN flag it for review.

The computer follows the rules supplied by its designers.

**Advantages**

- Rules can be easy to inspect.

- The behavior may be predictable when all relevant conditions are
  covered.

- The system may work without a large training dataset.

- Explicit rules can make the reasons for certain decisions easier to
  explain.

**Limitations**

- Designers must anticipate relevant situations.

- Large collections of rules can become difficult to maintain.

- Rules may fail when information is incomplete or ambiguous.

- The system does not automatically improve from examples unless
  learning mechanisms are added.

**11.4.2 Learning-Based Systems**

A learning-based system uses data or experience to develop behavior that
is useful for a particular task.

Machine learning is an important learning-based approach.

For example, a spam filter may be trained on messages labeled as spam or
legitimate email. During training, an algorithm adjusts the model so
that it captures patterns associated with the categories.

The resulting model can then predict a category for a new message.

Unlike a manually written rule for every possible phrase, a trained
model can use combinations of learned patterns.

However, the model may still make mistakes, especially when new messages
differ substantially from its training examples.

**11.4.3 Comparing Rule-Based and Learning-Based Systems**

| **Characteristic** | **Rule-based system** | **Learning-based system** |
|----|----|----|
| Main source of behavior | Explicitly programmed rules | Patterns learned from data or experience |
| Data requirements | May be modest | Often requires suitable training data or experience |
| Adaptation | Rules must generally be changed manually | May adapt after retraining or further learning |
| Interpretability | Often easier to trace individual rules | Varies by model and method |
| Handling ambiguity | Depends on the rules | Depends on the learned patterns and data |
| Common failure | Missing or conflicting rules | Poor generalization, biased data, or incorrect predictions |
| Suitable applications | Clear, stable, well-defined procedures | Tasks where patterns are difficult to specify manually |

These approaches are not mutually exclusive. Many real systems combine
explicit rules with machine learning.

For example, a financial fraud detection system may use a learned model
to estimate risk and explicit rules to enforce legal requirements or
trigger additional verification.

**11.5 AI, Machine Learning, and Deep Learning**

Artificial intelligence, machine learning, and deep learning are related
terms, but they do not mean the same thing.

**Artificial intelligence** is the broad field concerned with developing
systems that perform tasks associated with intelligent behavior.

**Machine learning** is a field of methods that allows computers to
learn patterns from data or experience.

**Deep learning** is a subset of machine learning that uses neural
networks with multiple layers to learn representations of data.

The relationship can be summarized as follows:

- AI includes approaches that do not use machine learning.

- Machine learning is one major approach within AI.

- Deep learning is one family of methods within machine learning.

  <img src="CHAPTER 11_media/media/image1.png"
  style="width:3.68819in;height:2.44685in"
  alt="Relationship between artificial intelligence (AI), machine learning... | Download Scientific Diagram" />

Figure 11.1 — The Relationship Between AI, Machine Learning, and Deep
Learning

**11.5.1 Comparing the Three Concepts**

| **Concept** | **Main purpose** | **Example** |
|----|----|----|
| Artificial intelligence | Develop systems that perform tasks associated with intelligent behavior | A planning system that searches for a route |
| Machine learning | Learn useful patterns from data or experience | A model that predicts house prices |
| Deep learning | Learn complex representations using multilayer neural networks | A neural network that recognizes objects in images |

A chess program that searches through possible moves using manually
designed evaluation rules can be an AI system without necessarily using
machine learning.

A house-price prediction model trained on historical housing data is a
machine learning application.

A deep neural network trained to recognize spoken words is an example of
deep learning.

**11.5.2 Why Is Deep Learning Useful?**

Deep learning can learn complex patterns from data such as images,
audio, and text.

A traditional machine learning approach may depend heavily on features
selected or constructed by people. Deep learning can learn useful
representations directly from relatively unprocessed data, although data
preparation and model design remain important.

Deep learning can achieve excellent performance in suitable tasks, but
it can also require substantial computing resources, large datasets, and
careful evaluation.

More complexity does not automatically mean better performance.

**11.6 Applications of AI**

AI is used in many industries. Its practical contribution depends on the
task and the reliability of the system.

**11.6.1 Education**

AI can support:

- Personalized practice questions.

- Feedback on student writing.

- Translation and language learning.

- Automated classification of educational materials.

- Administrative support for instructors.

- Learning analytics.

For example, a language-learning application may identify words that a
learner repeatedly answers incorrectly and recommend additional
practice.

**Limitation:** An AI-generated explanation may contain errors. Students
and instructors should verify important information rather than assuming
that an answer is correct because it is fluent.

**11.6.2 Healthcare**

AI applications include:

- Assisting with medical-image analysis.

- Identifying patterns in patient records.

- Supporting clinical risk prediction.

- Organizing medical documentation.

- Accelerating aspects of biomedical research.

For example, a model may flag an X-ray image for closer examination by a
radiologist.

**Limitation:** A prediction is not automatically a diagnosis. Clinical
decisions require appropriate professional judgment, validation, and
consideration of the individual patient.

**11.6.3 Transportation**

AI can support:

- Traffic prediction.

- Route planning.

- Driver-assistance systems.

- Fleet scheduling.

- Predictive maintenance.

- Research into autonomous vehicles.

For example, a delivery company may estimate travel times and optimize
delivery routes.

**Limitation:** Road conditions, unexpected obstacles, sensor failures,
and unusual situations can reduce system reliability.

**11.6.4 Business and Finance**

Applications include:

- Customer-service assistance.

- Demand forecasting.

- Inventory planning.

- Fraud detection.

- Document classification.

- Product recommendations.

- Risk analysis.

For example, a retailer may estimate future demand for a product using
historical sales and seasonal information.

**Limitation:** Historical data may fail to represent future market
conditions. Automated financial decisions also require appropriate
controls and oversight.

**11.6.5 Entertainment**

AI can be used for:

- Music and video recommendations.

- Game-playing systems.

- Content search.

- Image and audio editing.

- Generative content tools.

A streaming service may recommend content based on a user's previous
interactions and patterns among similar users.

**Limitation:** Recommendation systems can repeatedly expose users to
similar material, potentially narrowing the range of content they
encounter.

**11.6.6 Manufacturing and Agriculture**

In manufacturing, AI may help detect product defects or predict
equipment maintenance needs.

In agriculture, AI may support crop monitoring, plant-disease detection,
irrigation planning, and yield prediction.

In both fields, the usefulness of the model depends on factors such as
sensor quality, environmental conditions, and the cost of incorrect
predictions.

**11.7 Capabilities and Limitations of AI**

AI can perform many useful tasks, but its capabilities should be
understood in context.

**11.7.1 Strengths**

AI systems can:

1.  Process large amounts of information quickly.

2.  Identify patterns that are difficult to notice manually.

3.  Automate repetitive operations.

4.  Produce consistent outputs under stable conditions.

5.  Support predictions and decision-making.

6.  Assist with tasks involving language, images, sound, and other forms
    of data.

These strengths are task-dependent. A model may process millions of
records quickly while still being unsuitable for making a high-stakes
decision without additional checks.

**11.7.2 Why Can AI Systems Make Mistakes?**

Common reasons include the following.

**Insufficient data:** A model may not have enough examples to learn
reliable patterns.

**Poor data quality:** Incorrect labels, missing values, measurement
errors, or inconsistent records can harm performance.

**Distribution shift:** The data encountered after deployment may differ
from the training data.

**Ambiguity:** A question or observation may have multiple plausible
interpretations.

**Model limitations:** The algorithm may not capture the relationships
needed for the task.

**Incorrect assumptions:** Designers may choose inappropriate features,
objectives, or evaluation methods.

**Generative errors:** A generative system may produce a
plausible-looking statement that is false or unsupported.

**Environmental changes:** A model trained under one set of conditions
may become less reliable when those conditions change.

**11.7.3 Understanding Uncertainty**

A prediction should not automatically be interpreted as a fact.

Suppose a model estimates that a shipment has a 70% probability of
arriving late. This is a probabilistic prediction, not a guarantee that
the shipment will be late.

The meaning of the probability depends on the model's calibration and
the data on which it was evaluated.

Likewise, a system that returns a single category may conceal
uncertainty between several plausible alternatives.

Good AI practice involves evaluating uncertainty and considering the
consequences of errors.

**11.7.4 Human Judgment Remains Important**

AI should be used in a manner appropriate to the task.

For a low-risk task, such as suggesting a playlist, limited oversight
may be sufficient.

For a high-risk task, such as assisting with medical treatment or
evaluating an important legal decision, stronger safeguards and
qualified human review are necessary.

The appropriate level of oversight depends on the potential harm, the
reliability of the system, and the surrounding procedures.

**11.8 Responsible AI**

Responsible AI concerns the design, development, deployment, and use of
AI systems in ways that address their potential benefits and harms.

Four important considerations are fairness, privacy, human oversight,
and transparency.

**11.8.1 Fairness and Bias**

A model can produce unfair results when its training data, design, or
deployment conditions systematically disadvantage particular groups.

For example, suppose a company trains a recruitment model on historical
hiring decisions. If past decisions reflect unfair practices, the model
may learn patterns that reproduce those disadvantages.

Removing an explicitly sensitive field does not necessarily eliminate
bias because other variables may act as proxies.

Reducing bias requires appropriate data practices, evaluation across
relevant groups, and careful consideration of the decisions the model
supports.

Fairness is also context-dependent. Different fairness criteria may
conflict, so the appropriate approach must be justified for the
application.

**11.8.2 Privacy**

AI systems may process personal or sensitive information.

Responsible practices include:

- Collecting only information that is necessary.

- Limiting access to sensitive records.

- Following applicable privacy requirements.

- Protecting stored data.

- Avoiding unnecessary disclosure of personal information.

- Understanding how information is retained and used by a service.

Students should not assume that entering information into an AI service
makes that information private or appropriate to share.

**11.8.3 Human Oversight**

Human oversight involves maintaining appropriate opportunities for
people to inspect, question, correct, or override system outputs.

Its implementation may include:

- Requiring human approval for consequential decisions.

- Allowing affected individuals to challenge decisions.

- Monitoring performance after deployment.

- Providing procedures for handling errors.

- Assigning clear responsibility for the system's use.

Human oversight must be meaningful. A person who cannot understand,
question, or override a system's recommendation may not provide
effective supervision.

**11.8.4 Transparency and Accountability**

Transparency involves communicating relevant information about a
system's purpose, limitations, data, and behavior.

Accountability involves identifying who is responsible for its design,
deployment, monitoring, and consequences.

Not every model can provide a simple explanation for every prediction.
Nevertheless, users should receive enough information to understand the
system's role and limitations.

**11.8.5 Responsible Use in Education**

Students can use AI tools to:

- Obtain alternative explanations.

- Generate practice questions.

- Identify possible errors in their work.

- Explore examples.

- Improve their understanding of unfamiliar topics.

However, they should verify important claims, respect academic integrity
policies, protect personal information, and ensure that submitted work
reflects their own understanding and follows course requirements.

**11.9 Chapter Summary**

- Artificial intelligence is a field of computer science concerned with
  developing systems that perform tasks associated with intelligent
  behavior.

- AI includes several approaches, such as rule-based reasoning, search,
  planning, and machine learning.

- Machine learning allows systems to learn patterns from data or
  experience. Deep learning is a subset of machine learning that uses
  multilayer neural networks.

- AI applications can support education, healthcare, transportation,
  business, entertainment, manufacturing, and many other fields.

- However, AI systems can make mistakes because of poor data,
  inappropriate assumptions, limited model capabilities, uncertainty, or
  changes in the environment.

- Responsible AI requires attention to fairness, privacy, transparency,
  human oversight, and accountability.

- The central lesson is that **AI is a useful collection of methods, not
  a guarantee of intelligence, truth, fairness, or reliability**.

**11.10 Review Questions and Solutions**

**A. Multiple-Choice Questions**

1.  Which statement best describes artificial intelligence?

A. Every computer program that performs arithmetic\
B. A field concerned with systems that perform tasks associated with
intelligent behavior\
C. A physical robot that looks like a human\
D. A database containing large amounts of information

2.  Which statement correctly describes the relationship between AI,
    machine learning, and deep learning?

A. AI is a subset of deep learning.\
B. Machine learning and AI are unrelated.\
C. Deep learning is a subset of machine learning, which is a major area
within AI.\
D. Every AI system must use a neural network.

3.  Which is the clearest example of a rule-based system?

A. A model that learns to recognize flowers from labeled examples\
B. A program that activates a fan when the temperature exceeds a
specified threshold\
C. A neural network that generates images\
D. A model that discovers groups of similar customers from data

4.  What is narrow AI?

A. AI that can perform only arithmetic\
B. AI that is always unreliable\
C. AI designed or trained for particular tasks or a defined range of
tasks\
D. A system that must operate without a network connection

5.  Which is an important limitation of AI?

A. AI cannot process digital information.\
B. AI systems can never be used in healthcare.\
C. AI systems always require manually written rules for every input.\
D. AI systems may produce incorrect results when their data or
assumptions are unsuitable.

**Solutions and Explanations**

1.  **B.** AI concerns systems that perform tasks associated with
    intelligent behavior. It includes many methods and applications, not
    only robots.

2.  **C.** Deep learning is part of machine learning, and machine
    learning is a major area within AI.

3.  **B.** The fan follows an explicitly specified condition and action.

4.  **C.** Narrow AI focuses on particular tasks or a defined range of
    tasks.

5.  **D.** AI systems can fail because of insufficient data, poor
    assumptions, distribution shifts, or other limitations.

**B. True-or-False Questions**

1.  Every AI system must learn from data.

2.  A robot necessarily uses artificial intelligence.

3.  Deep learning uses multilayer neural networks.

4.  A model that performs well on one dataset will always perform
    equally well in every environment.

5.  Human oversight can be important when AI supports high-stakes
    decisions.

**Solutions and Explanations**

1.  **False.** Rule-based AI and search-based AI can operate without
    learning from data.

2.  **False.** Some robots follow fixed instructions and do not use AI.

3.  **True.** Multiple layers allow deep neural networks to learn
    complex representations.

4.  **False.** Performance may deteriorate when the deployment
    environment differs from the evaluation environment.

5.  **True.** Human review can help identify errors, assess
    consequences, and ensure appropriate accountability.

**C. Short-Answer Questions**

1.  Explain the difference between a rule-based system and a
    learning-based system.

2.  Describe two applications of AI and explain how each may be useful.

3.  Why is it incorrect to assume that an AI-generated answer is always
    true?

4.  Explain why privacy and fairness matter when designing AI systems.

**Solutions and Explanations**

1.  A rule-based system follows explicitly specified rules. A
    learning-based system develops patterns from data or experience.
    Both approaches may be combined in one application.

2.  Possible answers include medical-image analysis, which can help
    clinicians identify findings, and traffic prediction, which can
    support route planning. Other valid examples include fraud
    detection, product recommendations, and language learning.

3.  An AI system may generate incorrect results because of poor training
    data, limited knowledge, ambiguity, or inappropriate assumptions.
    Outputs should be checked when accuracy matters.

4.  Privacy matters because AI systems may process personal information.
    Fairness matters because a model may reproduce or amplify
    disadvantages present in its data or design.

**D. Scenario-Based Questions**

1.  A university uses fixed conditions to determine whether students
    have completed course prerequisites. Is a rule-based system
    appropriate? Explain.

2.  A company trains a model using historical recruitment decisions.
    What fairness risk should it consider?

3.  An AI application provides medical suggestions but sometimes makes
    errors. What safeguards may be appropriate?

**Solutions and Explanations**

1.  A rule-based system may be appropriate because prerequisite
    requirements can often be expressed as explicit conditions. The
    rules must still be kept accurate and exceptions handled properly.

2.  Historical decisions may contain bias. The model could reproduce
    unfair patterns, so the company should evaluate the training data,
    assess outcomes across relevant groups, and establish appropriate
    review procedures.

3.  Safeguards may include clinical validation, qualified professional
    oversight, monitoring, uncertainty assessment, and procedures for
    correcting errors. The system should not replace professional
    judgment without adequate evidence and authorization.

**11.11 Glossary**

| **Term** | **Definition** |
|----|----|
| Artificial Intelligence (AI) | A field concerned with systems that perform tasks associated with intelligent behavior. |
| Machine Learning (ML) | Methods that allow computers to learn patterns from data or experience. |
| Deep Learning | Machine learning based on multilayer neural networks. |
| Narrow AI | AI designed or trained for particular tasks or a defined range of tasks. |
| Artificial General Intelligence (AGI) | A proposed form of AI with broad capabilities across many intellectual tasks. |
| Rule-Based System | A system that applies explicitly specified rules. |
| Neural Network | A computational model made up of connected units organized into layers or other structures. |
| Generative AI | AI designed to generate content such as text, images, audio, or code. |
| Bias | A systematic tendency that may cause inaccurate or unfair results. |
| Human Oversight | Appropriate human involvement in reviewing, monitoring, or controlling a system. |
| Privacy | Protection and appropriate handling of personal information. |
| Accountability | Responsibility for a system's development, use, and consequences. |

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

Figure 11.1 — The Relationship Between AI, Machine Learning, and Deep
Learning:
<https://www.researchgate.net/figure/Relationship-between-artificial-intelligence-AI-machine-learning-ML-and-deep_fig2_368493050>
