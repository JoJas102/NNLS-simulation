# NNLS-simulation

## Description

Program to simulate influence of different parameters on NNLS (and NLLS) fitting of diffusion data and compare multi-exponential fitting methods. Evaluating the reliability of finding the total number of components contributing to the corresponding multi-exponantial signal and analysing the results by calculating corresponding diffusion parameters, comparing those to the ground truth.\
This fitting routine also utilises the regularized NNLS algorithm with cross validation from Thorarin Bjarnason for comparison. Additionaly, the advanced fitting algorithm NNLS_AUC was implemented, incorporating area under curve (AUC) constraints into the NNLS fitting result to improve accuracy.

For further information or citation purposes please refer to this publication:\
Jasse et al. Toward Optimal Fitting Parameters for Multi-Exponential DWI Image Analysis of the Human Kidney: A Simulation Study Comparing Different Fitting Algorithms. Mathematics 2024, 12, 609. https://doi.org/10.3390/math12040609


## Initial variables mandatory
Essential simulation and acquisition parameters can be edited and adjusted in [InitVar.m](InitVar.m):
* numberOfIter = number of simulations/iteration steps, differentiation for single- or multi-plotting of results
* snrIn        = Input SNR for artificial DWI signal rawSignal()
* b[]          = array of b-values
* Dmin/Dmax    = defining the D-range for diffusion constants/basis values DValues[] and DBasis[]
* m            = number of diffusion coefficients/bins between Dmin and Dmax\
* eventually:
  * f[] and d[]  = arrays with volume fractions [tissue tubules blood]/[slow, inter and fast] and associated  diffusion coefficients for ground truth (combined   in fdInput[]) or
  * dRange[] and fRange[] = reasonable intervals for the random choice of f and d made by DiffParamRandomizer.m

## General information
After initialisation of required varaibles, the [NNLS_Simulation.m](NNLS_Simulation.m) script can be run accordingly.
The simulation inputs, synthetic signal, simulation results and diffusion components estimates will be saved in the result subfolder.

For any further comments or explaining descriptions see annotations inside the functions code files.
