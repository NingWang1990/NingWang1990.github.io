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
This is a mini project that I did for a colleague, taking me just several hours. I put this simple work here to highlight the importance of domain knowledge in some problems. In this work, the problem is to automatically detect defects from atomic-resolution images. Each spot in the raw image represents an atom (strictly speaking, atomic column). Some small regions in the raw image have different arrangement of atoms from the matrix, and they are the defects that we want to find. I had no idea which algorithm I should use until I realized that there was some solid domain knowledge for this problem, the symmetry. Basically, the defects have different symmetry from the matrix, and we can encode this information into features. To make calculations of symmetry features possible, we first need to know positions of all atoms. There have already been several very good open-source packages for this. In this work, I employed the one called [StatSTEM](https://github.com/quantitativeTEM/StatSTEM). After atomic positions are obtained, I calculate [centro-symmetry parameter](https://lammps.sandia.gov/doc/compute_centro_atom.html) for each atom. After that,I performed an interpolation to obtain the centro-symmetry parameters for all pixels. The calculated centro-symmetry map is shown in the right plot. Two lines of defects clearly show up in the centro-symmetry map.  
