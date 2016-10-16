####################################
Overview: 
=================
The SPARCWave package contains utilities for sparse and structured-sparse clustering of time series using  
time-freqeuncy signal representations obtained from the wavelets and scattering transforms, implementing the methods and experiments in [1]. Datasets for the experiments are also provided.
For a basic example of how to use this package in Python, please refer to the README file.
####################################

### Source files:

**Python files:**

SPARCWave_MAIN.py - runs simulations, saves results to disk

SPACWave_functs.py - SPARCWave functions used in other scripts

SPARCWave_get_simulation_results_and_plot.py - loads simulation results from disk, plots

SPARCWave_run_real_data.py - runs SPARCWave on real data files

### Data files:

**CSV files:**
data_growth_T32_Q2_new_ord.csv - Berkeley Growth dataset after scattering transform

labels_growth.csv - labels for Growth dataset

phoneme_scatter_T32_Q8_New_ord.csv - Phoneme dataset after scattering transform

labels_phoneme.csv - labels for Phoneme dataset

wheat_T32_Q8_new_ord.csv - Wheat dataset after scattering transform

labels_wheat.csv - labels for Wheat dataset

### Technical overview: 

This software package uses both Python and R. Basic usage of the code, for running the structured-sparse clustering method on datasets, is done only via Python. 

Python is used for CVXPY, and as a wrapper for R code.
R is used for simulations, wavelet transforms, and the sparcl library (Witten & Tibshirani 2010).
In addition, Matlab is used for computing the scattering transform on signal. 

**Required Python libraries:** CVXPY, sklearn, joblib, numpy, pylab, rpy2. 

http://cvxpy.readthedocs.org/en/latest/tutorial/intro/

http://scikit-learn.org/stable/

https://pypi.python.org/pypi/joblib

http://rpy.sourceforge.net/


**Required R libraries:** sparcl, wmtsa (and dependencies). 
These libraries need to be in the global environment for rpy2 to load them. A simple way to do so is to put
the folders containing these libraries in [R-PATH]/library. For example: "C:\Program Files\R\R-3.2.1\library" 

**Required Matlab libraries:** the scatnent library 
http://www.di.ens.fr/data/software/


**R files:**

R_functions.R - functions for simulations for running the sparcl library

**Matlab files:**

compute_scattering_on_all_datasets.m - a script for applying the scattering transform on three datasets: Berkeley, Phenome and Wheat (see data directory) 

compute_scattering_multiple_signals.m - a function for computing the scattering transform for a set of signals

scattering_imagesc.m - visualize scattering coefficients 


### Acknowledgments:

SPARCWave was developed by Tom Hope, Avishai Wagner and Or Zuk, as part of work on the paper:

[1]  "Clustering Noisy Signals with Structured Sparsity Using Time-Frequency Representation", T. Hope, A. Wagner and O. Zuk, http://arxiv.org/abs/1510.05214 , 2015

Please cite the above paper if using the package.

For support, any questions or comments, please contact:

Tom Hope: tom.hope@huji.ac.il

Avishai Wagner: avishaiwa@gmail.com

Or Zuk: or.zuk@mail.huji.ac.il
