# Provenance

1. paper.pdf - selected review paper for PK

2. info.md - generated from paper and generic info, parameters manually selected from one set of pk parameters

3. .mo - Modelica file - selected appropriate basic model to extend (number of compartments), 
manually set the parameters from info.md into basic SI units - m3 instead of l and s instead of hours, etc.

4. .png - default simulation - 1 day, concentration curve

5. .fmu - exported from .mo

6. app/  - generated using Bodylight.js-FMU-Compiler using `./compile-docker.sh -s [.fmu]` 

7. index.html - static web page, simulation 

TODO

8. TODO python simulation - either using FMU

9. TODO python simulation without FMU - need to generate equations, put parameters, etc. as it is already in Modelica library

10. TODO other simulation - e.g. generate SBML or CellML or other modeling/simulation markup language

11. TODO provenance of all artifacts to be described used some standard e.g. PROV-O