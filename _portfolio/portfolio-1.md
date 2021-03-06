---
title: "Learning phase-transition kinetics from experimental video"
excerpt: " "
collection: portfolio
---

<p align="center">
<img src="https://media.giphy.com/media/ftBzkYV06IWkGnfXRl/giphy.gif" width="5000" height="500" >
</p>

Visualize results with better resolution [here](https://drive.google.com/file/d/1QyNy-73R8cHTt2BE9qUn5ptpvA2tau5Q/view). 
Presentation for this work is available [here](https://github.com/NingWang1990/NingWang1990.github.io/blob/master/files/learning_kinetics_2020.pdf).
Code for this project is available [here](https://github.com/NingWang1990/machine_learning_kinetics). 
## Intorduction

The phase transition is one of the most important concepts in materials science. In experiments, we are nowadays equipped with microcopies that have resolutions down to single atoms and capable of recording the process of phase transitions in in-situ experimental videos. The kinetics of phase transitions are hidden in these videos, and it is tedious and challenging to discover them manually. **How can we use machine learning to learn kinetics of phase transitions from in-situ experimental data?** This is the question we want to explore in this project. To be more specific, we try to learn a phase-field model from the in-situ experimental video.

## Phase-field model
We have been using the phase-field method to model kinetics of phase transitions since several decades ago. The Allen-Cahn equation dictates that the temporal evolution of the phase field can be described by the partial-differential equation below,

<a href="https://www.codecogs.com/eqnedit.php?latex=\frac{\partial&space;\phi}{\partial&space;t}&space;=&space;\kappa&space;\Delta&space;\phi&space;&plus;&space;\mu(\phi)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\frac{\partial&space;\phi}{\partial&space;t}&space;=&space;\kappa&space;\Delta&space;\phi&space;&plus;&space;\mu(\phi)" title="\frac{\partial \phi}{\partial t} = \kappa \Delta \phi + \mu(\phi)" /></a>.

The left-hand side is the temporal derivative of the phase field. The first term on the right-hand side is the diffusive term containing the Laplace operator, and the second term is the chemical potential as a function of the phase field. We aim to **learn the coefficient and the chemical potential from the experimental video**.

## Physics-informed neural network
We employ the physics-informed neural network (Raissi et al., J. Comput. Phys. 2019) in this project. As the name dictates, the neural network is informed with physics via the loss function,

<img src="https://render.githubusercontent.com/render/math?math=%5Cmathrm%7BLoss%7D%20%3D%20%5Csum_%7Bn%3D1%7D%5EN%20%5Cleft%7C%20%5Cphi(t%5En%2C%20x%5En%2C%20y%5En)%20-%20%5Cphi%5En%20%5Cright%7C%5E2%20%2B%20%5Csum_%7Bn%3D1%7D%5EN%20%5Cleft%7C%5Cmathrm%7BEqn%7D(%5Cphi(t%5En%2Cx%5En%2Cy%5En))%20%5Cright%7C%5E2">

where the first term is the data fidelity term that penalizes discrepancy between the output of the neural network and data. The second term is the penalty term that penalizes inequality of the equation. In our case, the physics we want to learn is the phase-field model that describes kinetics of phase transitions. We plug the Allen-Cahn equation into the second term of the loss function above. A schematic diagram of this neural network is shown in the diagram at the top of this webpage.

## Results
The main result of this work is shown in the diagram at the top of this webpage. We employed **pytorch** from Facebook to construct our neural network and train it on 2 x NVIDIA Tesla Volta GPU 32GB. Our training data are the experimental in-situ TEM video for phase separation in a high-entropy alloy, the left video in the diagram, and contain 220,400,000 training samples. 
There are two outputs in our neural network, the denoised video (middle) and the phase-field model (right). 
We see that the video is nicely denoised by the neural network, which indicates that the penalty term in the loss function can also be viewed as a regularization term. 
It is pretty similar to what our brain does when we want to extract knowledge from experimental data. We need to remove unimportant information or noise from data, and only keep the most important information. We showed the learning process of the chemical potential in the phase-field model in the right video. The learned chemical potential demonstrates the typical feature of phase separation.  
