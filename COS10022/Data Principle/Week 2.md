# Regressions
___

## Data Analytics Lifecycle 
## Phase 4 - Model Building
>In this phase, an analytical model is developed and fit on the training dataset, and subsequently evaluated against the test dataset.

The term "developed" does no mean making an entirely new model from scratch, but rather involved selecting and experimenting with various model and fine tuning their parameters where applicable

### Overview
Data science team:
- **Develops** datasets for testing, training, and production purposes.
- **Builds and executes** models based on the work done in the model planning phase.
- **Considers** the **sufficiency** of the *existing tools* to *run the models*, or  whether a more ***robust environment*** for **executing** the models **is needed**.

>[!Important]
>Model planning phase (Phase 3) and model building phase (phase 4) can overlap, where the data science team can iterate back and forth between the phases before settling on the final model.

Documentation is important at this stage

### Tools
1. Commercial Tools:
- SAS Enterprise Miner
- IBM SPSS Modeler
- Matlab
- Chorus 6
- Other: STATA, STATISTICA, Mathematica

2. Open-source Tools:
- R and PL/R
- Octave
- WEKA
- Python
- MADlib
- KNIME

### Predictive Models
> Data analytics models/algo/techniques used for predicting certain attributes of a given object

Example:
Used for guessing whether a customer will "subscribe" or "not subscribe" to a certain product or service. Or guess whether a person "survive" or "not survive" a specific disease.

>[!Note]
>The goal of a predictive model greatly differs from the goal of **unsupervised models** (k-Means Clustering) which are limited to **finding specific patterns or structures** within the data (e.g. clusters or segments).

### Training and Test sets
> A dataset should be split into training and test sets.

- **Training dataset**: the portion of data used to discover a predictive relationship
- **Test dataset**: the portion of data used to assess the strength and utility of a predictive relationship
- **Validation dataset**: is the portion of data that is used to minimize the possible overfitting of a model and select the optimal model parameters.
	- E.g. Practice test before actual test, etc.

>[!Note]
>The training and test data sets are usually independent from each other (non-overlapping).
>Test set should not be used to improve the data model.

>[!Important]
>It is also common to set aside a certain portion of the dataset as a validation set to improve the performance of a model. 

### Linear Regression Model
>Linear Regression belongs to what is called as parametric learning or parameter modeling approach
>Its goal is to understand the relationship between input and output  variables.

>[!Note]
>The regression model uses a linear regression formula to describe the data. 
>```𝑦 = 𝑎1𝑥1 + 𝑎2𝑥2 + ⋯ + 𝑏```

#### Building LRM
![[Pasted image 20230920230929.png]]

#### Pros and Cons
Pros
- Simplicity
- Gives optimal results when the relationships between the input and output variables are linear.
Cons
- Limited to predicting numerical values
- Will not work for modeling non-linear relationships

#### Further information
The model assumes that the output variable (i.e. predicted variable) is numerical  and that a linear relationship exists between the input variables and the single output  variable. 

The value of the output variable is calculated from a linear combination of the input variables.

Simple LRM formula
*y = ax + b*

Where:

Sign|Definition
:--|:--
y|Response (dependent) variable (output)
x|Predictor (independent) variable (input)
m|The estimated slope
b|The estimated intercept

Other Formula of the Linear Regression model:
*y = w<sub>0</sub> + w<sub>1</sub>x<sub>1</sub> + w<sub>2</sub>x<sub>2</sub> + ...*

Where:

Sign|Definition
:--|:--
***y*** | the predicted output variable;
***w<sub>0</sub>*** | the **bias coefficient**<sup>[1](#1)</sup>/intercept (the value of *y* when all input variables are zero)
***w<sub>1</sub>***, ***w<sub>2</sub>*** | the parameters/weights/coefficients of the input values that need to be estimated from the training data
***x<sub>1</sub>***, ***x<sub>2</sub>*** | values of the input variables

##### Case 1 - Simple Linear Regression
![[Pasted image 20230920231453.png]]

LR Equation used:
*y = 0.785 + 0.425x*
Hence:
for x = 1, y = 0.785 + 0.425(1) = 1.21
for x = 2, y = 0.785 + 0.425(2) = 1.64

##### How the equation was found:
5 statistics are required:

Sign|Definition|Detail
:--|:--|:--:
![[Pasted image 20230920234353.png]]| Mean of X |<sup>[2](#2)</sup>
![[Pasted image 20230920234418.png]]| Mean of Y
*S<sub>x</sub>*| Standard deviation of X | <sup>[3](#3)</sup>
*S<sub>y</sub>* | Standard deviation of Y
*r<sub>xy</sub>* | Pearson's correlation coefficient | <sup>[4](#4)</sup>
*x<sub>i</sub>* | An input's value
N | The total number of values in a given input variable x

##### Case Solved
![[Pasted image 20230920235656.png]]

#### Ordinary Least Square Regression
![[Pasted image 20230921000309.png]]
>[!Note]
>This is an optimization problem, hence, manual work is minor to none as it is handled by software

## Preparing Data for LRM
- **Linear assumption**: 
	- LR assumes that the **relationships** between the **input** and **output** variables are **linear**. 
	- For **non-linear** data, e.g. exponential relationship, data **transformation** technique such as the **log transform** is needed.
- **Remove noise and outliers**: 
	- LR assumes that the data is **clean**. Apply appropriate data cleaning techniques to **remove** possible **noise** and **outliers**
	- E.g. Noisy data: Incorrect attribute values due to faulty data collection instruments, data entry problems, inconsistency in naming convention, etc.
- **Remove Collinearity**: 
	- Collinearity is caused by having to many variables trying to do the same job. 
	- The Occam's Razor principle states that among several possible explanations for an event, the simplest explanation is the best. Consequently, the simpler out models is, the better. 
	>[!note]
	>Consider calculating pairwise correlations for your input data and remove the most correlated ones.

### Non-linear Transformation:
Linear curve has straight line relationship.  
Using non-linear **transformation**, **non-linear problem** can be solved as a **linear** (straight-line) **problem**.

![[Pasted image 20230921001814.png]]

#### Anscombe's Quartet
[For more information](https://en.wikipedia.org/wiki/Anscombe's_quartet)

#### Collinearity
> 2 or more predictors are closely related

Problematic in regression because it is difficult to check how much each predictor influences the output separately

![[Pasted image 20230921002738.png]]

#### Gaussian (normal) distributions
Input and Output variables that have a [Gaussian distribution](http://www.itl.nist.gov/div898/handbook/pmc/section5/gifs/normal.gif) will help Linear Regression produce more reliable predictions. Certain data transformation techniques can be used to create a distribution that is more Gaussian looking.

>[!Note]
>Called normal when mean middle value is <> 0
>Called Gaussian when mean middle value is = 0
#### Rescale input
Rescaling input variables using standardization or normalization will often help Linear regression make more reliable predictions.
##### Normalization:  
To change the observations so that they can be described as a normal distribution (also known as the bell curve).  
- A Specific statistical distribution where a roughly equal observations falls above and below the mean, the mean and the median are the same, and there are more observations closer to the mean.
![[Pasted image 20230921003109.png]]
##### Standardization:  
Also called z-score normalization, which transforms data so that the resulting distribution has a mean of 0 and a standard deviation of 1.
![[Pasted image 20230921003145.png]]
##### Results of Normalization
![[Pasted image 20230921003210.png]]

### Logistic Regression Model
> A special case of regression analysis and is calculated when the dependent variable is nominally or ordinally scale

E.g. 
- Disease diagnosis
- Product of interest
- Credit evaluation
- Election predictions
>[!Note] 
>Common points of these examples: the output is categorical data<sup>[5](#5)</sup>

>[!Important]
>To determine whether to use Linear RM or Logistic RM, we must observe whether the output data is numerical or categorical.
>Numerical: Linear RM
>Categorial: Logistic RM


#### Sigmoid Function  


A sigmoid function only produces output values between 0 and 1.
![[Pasted image 20230921010232.png]]
![[Pasted image 20230921010842.png]]
### Formula
To obtain the Logistic RM, we replace the x in the sigmoid function with the Linear Regression function.

A logistic function or logistic curve us a common S-shaped curve (sigmoid curve) with equation
![[Pasted image 20230921010522.png]]

Where:
***z*** stands for the LR function

Hence the full formula is:
![[Pasted image 20230921010615.png]]

___
# Others
###### 1
Bias coefficient ~ Constant
This can shift slope, has direct impact on *y*

Video 30:00 contains how to build LRM and such

###### 2
![[Pasted image 20230920234305.png]]
###### 3
![[Pasted image 20230920235327.png]]
###### 4
![[Pasted image 20230920235519.png]]
###### 5
Data like: Yes, No. True, False. are categorical