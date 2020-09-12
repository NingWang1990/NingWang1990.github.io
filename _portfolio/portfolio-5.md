---
title: "Symmetry analysis for defect detection in atomic-resolution images"
excerpt: " "
collection: portfolio
---
<p align="center">
<img src="/images/symmetry_analysis.png" width="1000" height="500" >
</p>

jupyter nootbook for this work is available [here](https://github.com/NingWang1990/Automatic_defect_detection)

## Introduction
This is a mini project that I did for a colleague, taking me just several hours. I put this simple work here to highlight the importance of domain knowledge in some problems. 
In this work, the problem is to detect defects from atomic-resolution images automatically.  Each spot in the raw image represents an atom (strictly speaking, atomic column). In some places, the arrangement of atoms is different, and they are the defects that we want to detect. I had no idea which algorithm I should use until I realized that there was some solid domain knowledge for this problem, the symmetry. The defects have different symmetry from the matrix, and I can encode this information into features.     
If there is some domain knowledge, try to make use of it.   
