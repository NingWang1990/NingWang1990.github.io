
---
title: "Hamiltonian Monte Carlo for spin systems"
excerpt: " "
collection: portfolio
---

<p align="center">
<img src="/images/magnetization_curve.png" width="600" height="500" >
</p>

check out [our paper](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.99.094402) for more details of this work. 

## Introduction
Atomistic simulations of the thermodynamic properties of magnetic materials rely on an accurate modeling
of magnetic interactions and an efficient sampling of the high-dimensional spin space. Recent years have seen
significant progress with a clear trend from model systems to material-specific simulations that are usually based
on electronic-structure methods. Here we develop a Hamiltonian Monte Carlo framework that makes use of
auxiliary spin dynamics and an auxiliary effective model, the temperature-dependent spin-cluster expansion, in
order to efficiently sample the spin space. Our method does not require a specific form of the model and is
suitable for simulations based on electronic-structure methods. We demonstrate fast warm-up and a reasonably
small dynamical critical exponent of our sampler for the classical Heisenberg model. We further present an
application of our method to the magnetic phase transition in bcc iron using magnetic bond-order potentials.

