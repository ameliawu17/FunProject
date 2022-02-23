Predicting individual responses in working memory tasks based on resting-state functional connectivity
===
Problem Statement
---
* Brain regions activated during cognitive tasks are functionally connected - functional networks
  * can be examined during task state to understand human behaviors
* Resting-state functional network - task-independent intrinsic pattern 
  * identify individuals within and across states 

* What is the correlation in time series between pairs of parcels like across the whole brain under resting state?
* Does within-network functional connectivity during resting state predict individual variance in working memory task performance?

* Hypothesis:
  * Resting-state functional connectivity within the default mode network, frontoparietal network and the somatomotor network relate to working memory performance

Data discrption
---
This analysis is based on a population of healthy human data from [Human Connectome Project (HCP)](https://www.humanconnectome.org/), which has collected fMRI (Functional magnetic resonance imaging) time series data from both resting state and as well as 7 task conditions. fMRI measures brain activity by detecting changes associated with blood flow which allows us to better understand how coordinated activity across the whole brain adjusts to produce behaviorally appropriate responses to environmental changes. 

Analysis process
---
* Compute resting-state functional connectivity to generate correlation matrices for each subject. Evaluate working memory performance through N-back task.

#### Whole brain-wise correlation matrix

<p align="center"><img src = "https://github.com/ameliawu17/PersonalProject/blob/main/Predict%20WM%20based%20on%20fMRI/functional_connectivity.png" width = 700><p>

* Fit the linear model to explain the relationship between individual-level behavior and functional connectivity within the three networks selected from the correlation matrix of each individual.

#### Correlation between within network connectivity and 2-back reaction time 
 
<p align="center"><img src = "https://github.com/ameliawu17/PersonalProject/blob/main/Predict%20WM%20based%20on%20fMRI/correlation.png" width = 700><p>
 
  * There is a weak positive correlation between connectivity and reaction time.
 
* Model evaluation by splitting the dataset into a separate training set and a test set and find out the coefficients.
 
<p align="center"><img src = "https://github.com/ameliawu17/PersonalProject/blob/main/Predict%20WM%20based%20on%20fMRI/coefficients.png" width = 700><p>
 
  * Frontoparietal network connectivity significantly predicts 2-back reaction time, independent of default mode and somatomotor network connectivity
 
<p align="center"><img src = "https://github.com/ameliawu17/PersonalProject/blob/main/Predict%20WM%20based%20on%20fMRI/multiple_regression.png" width = 700><p>
 
  * Model evaluation: the mean squared error is very large. Also, according to the coefficient of determination, the prediction does a very bad job.
 
Analysis process
---
