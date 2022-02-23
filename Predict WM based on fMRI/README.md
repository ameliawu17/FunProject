Predicting individual responses in working memory tasks based on resting-state functional connectivity
===
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/gist/ameliawu17/7fe9266d9ea1965ad6293b42d19ba0e0/predicting-individual-responses-in-working-memory-tasks-based-on-resting-state-functional-connectivity.ipynb)

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
 
Discussion and future direction
---
* Potential ceiling effect: the working memory task performance show limited individual difference 
* Potential interaction or high collinearity between networks -> may explore ROI-to-ROI, ROI-to-Voxel analysis
* Participants may involve networks differently corresponding to stimulus (e.g., face, tools, etc) -> may involve decoding & encoding analysis 

##### References:
  Finn, E. S., Shen, X., Scheinost, D., Rosenberg, M. D., Huang, J., Chun, M. M., ... & Constable, R. T. (2015). Functional connectome fingerprinting: identifying   individuals using patterns of brain connectivity. Nature neuroscience, 18(11), 1664-1671.
  Sala-Llonch, R., Pena-Gomez, C., Arenaza-Urquijo, E. M., Vidal-Piñeiro, D., Bargallo, N., Junque, C., & Bartres-Faz, D. (2012). Brain connectivity during resting state and subsequent working memory task predicts behavioural performance. Cortex, 48(9), 1187-1196.
  Van Essen, D. C., Smith, S. M., Barch, D. M., Behrens, T. E. J., Yacoub, E., Ugurbil, K., & Consortium, F. T. W.-M. H. (2013). The WU-Minn Human Connectome Project: An overview. NeuroImage, 80(C), 62–79. http://doi.org/10.1016/j.neuroimage.2013.05.041

