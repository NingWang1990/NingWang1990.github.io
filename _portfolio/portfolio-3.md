---
title: "Machine learning assisted design of steels"
excerpt: " "
collection: portfolio
---
<p align="center">
<img src="/images/machine_learning_steels.PNG" width="800" height="350" >
</p>
code for this project is available [here](https://github.com/NingWang1990/Machine_learning_steel). 

## Introduction
In this project, we aim to build up the composition-property relationship for steels. We divide the project into two steps: 1. **dimension reduction** in the property space, shown in Fig. 1; 2. fitting the composition-property relationship with **Gaussian process regressor** and **gradient boosting tree**, with results shown in Fig. 2. The dimension reduction is necessary because we only know incomplete information about the steels in our dataset. The mechanical properties are determined by the composition and the processing. However, the latter is unknown in our dataset. 
It means that given a composition, we cannot predict an exact location in the property space. 
Interestingly, we may first perform a dimension reduction in the property space, and then the machine learning works. 
In other words, given a composition, the regressors predict a hyperplane instead of a position in the property space. We use two regressors in this project to guarantee prediction robustness.    
