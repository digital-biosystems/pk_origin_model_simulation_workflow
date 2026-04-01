# Introduction

this repository is a dataset for a reproducibility workflow for various studies. It is organized as follows.
Each directory is named [drug_ATC_code_drug]_[drug_generic_name] and there is original paper, some information containing extracted data, reconstructed model and sample simulation.

# Sample workflow template dataset


1. [author]_[year]_[keywords].pdf of a scientific paper that is origin of the workflow of model reconstruction and paper results reproduction
2. info.md - created/generated from paper and generic info about drug, parameters manually extracted from selected set if more PK models presented for different patient population. Models inherit (by object oriented modeling meaning) generic PK model from Pharmacolibrary [1]
3. .mo - Modelica file - selected appropriate basic model to extend (number of compartments), 
manually set the parameters from info.md into basic SI units - m3 instead of l and s instead of hours, etc.
4. .mat - default simulation data - in MATv4 result file format
5. .png - default simulation chart - concentration curve
6. .fmu export of .mo (used OpenModelica 1.26.3 [2])
7. app/  - generated using Bodylight.js-FMU-Compiler [3] using `./compile-docker.sh -s [.fmu]` 
8. index.html - static web page, simulation 

The resulting info.md, model and simulation can be taken as ground truth, how the current implementation of reported PK model should correspond to the associated paper.

## TODO

* simulation data are produced in 
* TODO other model/simulation standards - e.g. generate SBML or CellML or other modeling/simulation markup language
* TODO python simulation without need of - either using FMU from .mo or without FMU as PK models can be expressed as set of ODA and algebraic equations to be solved by some python solver (which is btw part of FMU).
* TODO provenance of all artifacts to be described used some standard e.g. PROV-O

## Tools & Libraries involved

[1] Pharmacolibrary: https://github.com/digital-biosystems/Pharmacolibrary
[2] OpenModelica: https://openmodelica.org/
[3] Bodylight.js-FMU-Compiler: https://github.com/creative-connections/Bodylight.js-FMU-Compiler

