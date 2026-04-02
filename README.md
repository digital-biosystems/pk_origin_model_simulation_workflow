# Introduction

This repository is a sample dataset to construct workflow for reproducibility and additional tasks combining various studies. It is organized as follows.

1st level directory - domain of computational research: 
  * pharmacology, 
  * cardiovascular, 
  * combination

2nd level directory 
- in pharmacology each directory is named [drug_ATC_code_drug]_[drug_generic_name] and there is original paper(s), some information containing extracted data, reconstructed model and sample simulation. The task is to construct PK model and reproduce PK simulation reported in paper.
- in cardiovascular, there is again original paper(s), some information containing extracted data, reconstructed model and sample simulation. The task is again to construct model and reproduce reported simulation in paper.
- in combination - sample combination of studies from different domains, combination of model and simulation reproduction. The task is more complex - to combine pharmacology and cardiovascular model in order to simulate influence of both systems. Details in info.md

# Sample workflow template dataset

1. [author]_[year]_[keywords].pdf of a scientific paper that is origin of the workflow of model reconstruction and paper results reproduction
2. info.md - created/generated from paper and generic info about drug, parameters manually extracted from selected set if more PK models presented for different patient population. Models inherit (by object oriented modeling meaning) generic PK model from Pharmacolibrary [1]
3. .mo - Modelica file - model inherits from basic model and sets parameter values manually set the parameters from info.md into basic SI units - m3 instead of l and s instead of hours, etc.
4. .mat - default simulation data - in MATv4 result file format
5. .png - default simulation chart - concentration curve
6. .fmu export of .mo (used OpenModelica 1.26.3 [2])
7. app/  - generated using Bodylight.js-FMU-Compiler [3] using `./compile-docker.sh -s [.fmu]` 
8. index.html - static web page, simulation 

The resulting info.md, model and simulation can be taken as ground truth, how the current implementation of reported PK model should correspond to the associated paper.

## combination

contains speculative combination of reproducible models in order to see, pharmacodynamics effects on pressure and volume characteristics of hemodynamics of cardiovascular system.

## TODO

* TODO other model/simulation standards - e.g. SBML or CellML or other modeling/simulation markup language
* TODO pure python simulation - need to use differentiate algorithm and convert models to python script, either using FMU from .mo or without FMU as PK models can be expressed as set of ODE and algebraic equations to be solved by some python numerical solver (CVODE is part of FMU).
* TODO provenance of all artifacts to be generated and described used standard PROV-O

## Tools & Libraries involved

[1] Pharmacolibrary: https://github.com/digital-biosystems/Pharmacolibrary

[2] OpenModelica: https://openmodelica.org/

[3] Bodylight.js-FMU-Compiler: https://github.com/creative-connections/Bodylight.js-FMU-Compiler

[4] digital biosystems web components: https://digital-biosystems.github.io/dbs-components/ 

