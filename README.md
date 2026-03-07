## Brain Computer Interface (BCI)

A **Brain Computer Interface (BCI)** is a technology that enables direct communication between the human brain and an external device without using muscles or physical movement. It works by capturing brain signals, usually through **EEG (Electroencephalography)**, and converting them into commands that a computer or machine can understand.

BCI systems are widely used in research and applications such as **assistive technologies, prosthetic control, and device automation**, allowing users to control devices using only their brain activity.

## Applications of BCI

Brain Computer Interfaces have several real-world applications where brain signals are used to control devices or communicate without physical movement.

**1. Communication Systems (HELL-O-Cell)**
BCI can be used to help people with severe paralysis communicate. By detecting specific brain signals, users can select letters or words on a virtual keyboard to form messages such as “HELLO”. These systems are often called **spelling or communication cells**.

**2. Assistive Technology**
BCI helps individuals with disabilities interact with computers, wheelchairs, or other assistive devices using only their brain activity.

**3. Robot and Bot Control**
BCI can be used to control robots or automated systems. By imagining certain movements (like left or right hand), the system can convert brain signals into commands that move a **robot, drone, or bot**.

## DataSet

For this project, the EEG Motor Movement/Imagery Dataset from PhysioNet was used. This dataset contains EEG recordings collected from multiple subjects while they performed different motor tasks such as imagining or executing movements of the hands and feet.

The EEG signals were recorded using 64 channels according to the international 10-10 electrode placement system. During the experiments, subjects were asked to perform tasks like:

Resting state

Imagining left-hand movement

Imagining right-hand movement

Dataset Link:
https://physionet.org/content/eegmmidb/1.0.0/

## Machine Learning Models

In this project, several machine learning models are used to classify **motor imagery EEG signals**. The models are implemented using **scikit-learn, MNE, and PyRiemann libraries**.

### Models Used

**CSP-Based Models**

* CSP + Linear Discriminant Analysis (LDA) **(51.04%)**
* CSP + Support Vector Machine (SVM) **(54.53%)**
* CSP + Logistic Regression (LR) **(51.26%)**
* CSP + Random Forest (RF) **(55.27%)**

**Riemannian Geometry-Based Models**

* Riemann + Linear Discriminant Analysis (LDA) **(53.27%)**
* Riemann + Support Vector Machine (SVM) **(63.08%)**
* Riemann + Logistic Regression (LR) **(54.83%)**
* Riemann + Random Forest (RF) **(50.89%)**
* Riemannian Minimum Distance to Mean (MDM) **(43.16%)**


### Why CSP is Used

**Common Spatial Pattern (CSP)** is a spatial filtering technique widely used in **motor imagery BCI systems**. It extracts spatial features from EEG signals by maximizing the variance difference between two classes (for example, left-hand vs right-hand imagination).

The advantages of CSP include:

* Enhances discriminative patterns between classes
* Reduces noise from irrelevant channels
* Improves classification performance

Because motor imagery mainly affects specific brain regions (such as **C3 and C4 motor cortex areas**), CSP helps highlight these spatial differences effectively.

### Why Riemannian Geometry is Used

EEG signals can also be represented using **covariance matrices**, which capture relationships between EEG channels. These matrices lie on a **Riemannian manifold**, meaning they do not behave well with standard Euclidean operations.

Riemannian geometry methods handle these matrices properly by:

* Preserving the natural geometry of covariance matrices
* Extracting stable and robust features
* Improving classification accuracy for EEG signals

The **Minimum Distance to Mean (MDM)** classifier and **Tangent Space mapping** are commonly used approaches in Riemannian-based EEG classification.

These methods are powerful because they often require **less feature engineering** while still providing strong performance for BCI tasks.

## Deep Learning Model – EEGNet(Accuracy ~67%)

In addition to traditional machine learning models, a deep learning model called EEGNet is used for EEG signal classification. EEGNet is a compact convolutional neural network specifically designed for Brain Computer Interface (BCI) applications and EEG data.

EEGNet is effective because EEG signals contain both temporal patterns (changes over time) and spatial patterns (relationships between electrodes). The architecture is designed to capture both of these characteristics efficiently.

## EEGNet Architecture

The implemented EEGNet model consists of three main convolutional blocks:

**Block 1 – Temporal and Spatial Filtering**

A temporal convolution layer extracts frequency-based features from EEG signals.

A depthwise spatial convolution learns spatial relationships between EEG channels.

Batch normalization, ELU activation, average pooling, and dropout are used to improve stability and prevent overfitting.

**Block 2 – Separable Convolution**

Depthwise and pointwise convolutions are used to efficiently extract more complex temporal features.

This reduces the number of parameters while maintaining performance.

**Block 3 – Additional Feature Extraction**

Another separable convolution block refines the extracted features.

Dropout is used again to improve generalization.

Finally, the extracted features are flattened and passed to a fully connected layer, which outputs predictions for the three classes used in the model

## Next Steps

The next step using this model is to create a **communication system** where a window continuously moves on the screen. When the system detects a **motor imagery signal** from the brain, the moving window will stop, allowing the user to select or communicate a specific option.

Another goal is to use the detected brain signals to **control a bot**, where different motor imagery signals can be converted into commands for bot movement or actions.


### NOTE:
Final note books will be avaliable in the folder **Final Models**. Other notebooks are just my working on different models.
Testing model is used to Test the DL model using the weights saved
## Contact

Email:madhava2807@gmail.com

Linkedin :[Linkedin](https://www.linkedin.com/in/madhava-reddy-yeddula-766936295 )
