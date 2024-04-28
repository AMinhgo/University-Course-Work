# Model Planning and Clustering
___
# Model Selection
### Overview
> A model is an *abstraction* from reality; an attempt to understand the reality

Modeling involved:
**Observing** certain events happening in a real-world situation and attempting to construct models that **emulate** this behavior with a set of **rules** and **condition**.

In short:
- Observe
- Emulate based with rules and condition

>[!Important]
>Often in a **model** all *extraneous* detail has been *removed* or *abstracted*.
>=> We must ==pay attention== to these abstracted details after a model has been analyzed to see what might have been **overlooked** and/or **missed**.

>[!Note]
>In statistical modeling, the terms ‘**model**’, ‘**algorithm**’, **‘analytical technique**’, and ‘**analytical method**’ are often used ***interchangeably***.

### Selecting model
When thinking about model, there are some information to keep in mind:
- *What comes first?*
- *What influences what?*
- *What causes what?*
- *What is a test of what?*

![[Pasted image 20230922145017.png]]

Key considerations when selecting model in Phase 3 of the Data Analytics Lifecycle:  
1. The **structure** of the data (structured, semi-structured, quasi-structured, unstructured)  
2. The **extent** to which the model would be **suitable** for proving / disproving the hypotheses  
3. Whether the analytical needs warrant a **series of models** to be used

### Learning types
![[Pasted image 20230922151445.png]]
#### Supervised
> Supervised models take a set of input variables (X) and an output variable (Y) and try to learn the mapping function from the inputs to the output

![[Pasted image 20230922151823.png]]

##### Workflow
![[Pasted image 20230922151941.png]]
##### Examples
![[Pasted image 20230922151954.png]]
#### Unsupervised
> Unsupervised models work with a set of input variables (X) but no output variable. The goal is to find the underlying and ‘interesting’ structure or distribution in the data in order to learn more about the data.

![[Pasted image 20230922152816.png]]
##### Workflow
![[Pasted image 20230922152836.png]]
##### Examples
![[Pasted image 20230922152958.png]]
#### Semi-supervised
>Semi-supervised models address situations where there are a set of input variables (X) with partially available values of the output variable (Y). An example is a model that must automatically classify images from a photo archive where only some of the images are labelled (e.g. dog, cat, person) while the majority are not labelled.

![[Pasted image 20230922153940.png]]

##### Workflow
![[Pasted image 20230922155255.png]]

##### Examples
![[Pasted image 20230922155310.png]]
##### Principle of semi-supervised learning

1. A model (e.g. a classifier) is first trained on the few available labelled training data.  
2. This model is then used to classify and thus label the many unlabeled data (the test data) available.  
3. The newly labelled data are combined with the originally available labelled ones to retrain the model with many more data, and thus hopefully to obtain a better model.

### Exploratory Model: k-means clustering
> Clustering methods aim at discovering ***natural grouping*** of objects of interests

Achieved through:
1. Finding similarities between the objects base on their attributes/properties/variables
2. Group similar objects into clusters

Use cases: 
- Customer segmentation (i.e. grouping customers according to the similarity of their behaviors or spending patterns)  
- Automatic identification of abnormal activities in CCTV videos  
- Summarize news articles





___
# Other

###### 1
Most model would end up with some math equations and in mathematical expression, 
+ Greek letters represent parameters (aka coefficient)
+ Latin letters represent data/variables
	- For linear relationship between X and Y axis, the model can be used is: 
	- ![[Pasted image 20230922145929.png]]
###### 2
Exploratory = Unsupervised