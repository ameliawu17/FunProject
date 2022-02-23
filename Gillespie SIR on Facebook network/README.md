The modeling of a stochastic SIR dynamics on Facebook social network using Gillespie’s algorithm
===
Introduction
---

* The Gillespie Algorithm is a stochastic simulation algorithm for simulating the changes in the molecular populations of chemical species in a chemically reacting system. Now stochastic simulations are one of the most common tools for analyzing dynamical processes on complex networks.
* The susceptible-infected-recovered (SIR) model is one of the most frequently studied epidemic processes in complex networks. There are enormous studies have applied SIR model to assess the spread of the COVID-19 disease and predict the number of infected and recovered populations. This work did some observation and investigation in order to get some inspiration from the study.

<p align="center"><img src = "https://github.com/ameliawu17/PersonalProject/blob/main/Gillespie%20SIR%20on%20Facebook%20network/SIR.png" width = 700><p>   
  
* The Facebook network data which consists of 'circles' (or 'friends lists') from Facebook. Facebook data was collected from survey participants using this Facebook app. The dataset includes node features (profiles), circles, and ego networks. It can be found at [here](https://snap.stanford.edu/data/ego-Facebook.html).   
    * Number of nodes(N) : 4,039; 
    * Number of edges(M) : 88,234; 
    * Mean degree $<k>$ :  43.6910; 
    * The hand shaking lemma is ![1](http://latex.codecogs.com/svg.latex?\\sum_{i=1}^{N}k_i=2M) ; 
    * Average degree of a neighbor ![2](http://latex.codecogs.com/svg.latex?\\frac{<k^2>}{<k>}=635);
  
#### Visualize the network such that the node color varies with degree and node size with betweenness centrality
  
<p align="center"><img src = "https://github.com/ameliawu17/PersonalProject/blob/main/Gillespie%20SIR%20on%20Facebook%20network/FB_network.png" width = 700><p>  
  
#### Problem statement: Is there any relationship between nodes' degrees and time to get infected?  
  
Exploratory Data Analysis
-----
When set (http://latex.codecogs.com/svg.latex?\\beta=0.2), which is greater than (http://latex.codecogs.com/svg.latex?\\beta_c) Then explore whether nodes with a higher degree tend to be eventually infected (and then recovered) than nodes with a smaller degree.  

  
