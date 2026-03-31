# Sample workflow template dataset

each directory contains
1. paper
2. info.md - partially generated from generic knowledge and manually extracted selected PK parameters from paper
3. .mo file that based on paper selects first or first 2 pk parameter set to model PK of a drug
4. .png default simulation of PK
5. .fmu export of .mo (used OpenModelica 1.26.3)
6. app (used `./compile-docker.sh -s [.fmu]`)

