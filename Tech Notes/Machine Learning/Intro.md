# Machine Learning

## Terminology
##### Labels
A **label** is the thing we're predicting—the `y` variable in simple linear regression. The label could be the future price of wheat, the kind of animal shown in a picture, the meaning of an audio clip, or just about anything.

##### Features
A **feature** is an input variable—the `x` variable in simple linear regression. A simple machine learning project might use a single feature, while a more sophisticated machine learning project could use millions of features, specified as:
$$
x_{1}, x_{2}, ..., x_{N}
$$
##### Examples
An **example** is a particular instance of data, **x**. (We put **x** in boldface to indicate that it is a vector.) We break examples into two categories:
* labeled examples
* unlabeled examples

A **labeled example** includes both feature(s) and the label. That is:
```
labeled examples: {features, label}: (x, y)
```

Use labeled examples to **train** the model.

An unlabeled example contains features but not the label. That is:
```
unlabeled examples: {features, ?}: (x, ?)
```

Once we've trained our model with labeled examples, we use that model to predict the label on unlabeled examples. In the spam detector, unlabeled examples are new emails that humans haven't yet labeled.

##### Models
A model defines the relationship between features and label. Let's highlight two phases of a model's life:

* **Training** means creating or **learning** the model. That is, you show the model labeled examples and enable the model to gradually learn the relationships between features and label.

* **Inference** means applying the trained model to unlabeled examples. That is, you use the trained model to make useful predictions (`y'`).

##### Regression vs. classification
A **regression** model predicts continuous values. For example, regression models make predictions that answer questions like the following:

* What is the value of a house in California?
* What is the probability that a user will click on this ad?

A **classification** model predicts discrete values. For example, classification models make predictions that answer questions like the following:

* Is a given email message spam or not spam?
* Is this an image of a dog, a cat, or a hamster?

## Implementation
##### Tensors
**Tensors** are a specialized data structure that are very similar to arrays and matrices. In PyTorch, tensors are used to encode the inputs and outputs of a model, as well as the model’s parameters.

## Resources
Google Machine Learning Crash Course
https://developers.google.com/machine-learning/crash-course

Stanford CS229: Machine Learning by Andrew Ng
https://www.youtube.com/playlist?list=PLoROMvodv4rMiGQp3WXShtMGgzqpfVfbU

Coursera Machine Learning by Andrew Ng
https://www.coursera.org/learn/machine-learning

scikit-learn: Machine Learning in Python
https://scikit-learn.org/stable/index.html

A Gentle Introduction to Object Recognition With Deep Learning
https://machinelearningmastery.com/object-recognition-with-deep-learning/

Building powerful image classification models using very little data
https://blog.keras.io/building-powerful-image-classification-models-using-very-little-data.html

https://www.deeplearningbook.org/front_matter.pdf
https://arxiv.org/
https://arxiv-sanity-lite.com/