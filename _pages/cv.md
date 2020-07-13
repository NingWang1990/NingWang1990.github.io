---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

Education
======
* 2019 - present, postdoctoral researcher in Max-Planck Institute, Düsseldorf (MPIE)
* 2016 - 2019, PhD researcher in ICAMS, Ruhr-Universität Bochum
* 2011 - 2014, School of Materials Science and Engineering, Northwestern Polytechnical University, China
* 2008 - 2011, Honors College, Northwestern Polytechnical University, China

Skills
======
* Machine learning
  * statistial learning
  * deep learning
  * Monte Carlo sampling
* Programming
  * Python
  * Fortran
  * C/C++
* Machematical modeling
* Atomistic simulation
  * Molecular dynamics
  * first-principle thermodynamics

Publications
======
  <ul>{% for post in site.publications %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
Talks
======
  <ul>{% for post in site.talks %}
    {% include archive-single-talk-cv.html %}
  {% endfor %}</ul>
  
Teaching
======
  <ul>{% for post in site.teaching %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
