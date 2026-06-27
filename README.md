# wsc26-periodic

This repository is a companion to the paper 
* P. L'Ecuyer and C. Lemieux, ``Should we Always Scramble Digital Nets for Quasi-Monte Carlo?,'' Proceedings of the 2026 Winter Simulation Conference, IEEE Press, 2026, to appear. See [wsc26periodic.pdf](https://www-labs.iro.umontreal.ca/~lecuyer/myftp/papers/wsc26periodic.pdf)

The aim of that paper is to compare empirically various Randomized quasi-Monte Carlo (RQMC) estimators of the integral of a function $f$ in terms of their variance. For this, we selected 10 functions $f$, each one in $s = 1, 2, 4, 8, 16$ dimensions, and tried RQMC point sets with $n=2^k$ points for $k=8,9,\dots,18$. For each $f$ and $s$, we applied each RQMC method 1000 times for each $k$, computed the empirical mean, variance, and excess kurtosis, and put these values in three data file. We then used these files to make plots of the log-variance as a function of $k$ for the different methods, for each $f$ and $s$.  

The present repository contains an Online Supplement for the paper that provides the proof of Proposition 2 and the variance plots, links to the Java code and tools used to make the experiments, and the output data files.   

We did this in Java by using the packages `hups` and `mcqmctools` from the 
[SSJ library](https://github.com/umontreal-simul/ssj). We think that each of these large samples is highly representative of the true 
distribution of the corresponding RQMC estimator, so we can look at its empirical variance, skewness, kurtosis, and histogram,
to assess the properties of the RQMC estimator.

The main purpose of this GitHub site is to provide the files that contain the $N$ independent RQMC realizations for each
of the 600 cases examined in the paper.  There are actually more files because we provide results for two more functions that were not in the paper.  
Each file contains $N = 10,000$ real numbers $y_1, \ldots, y_N$, one per line, and nothing else.
The file names have the form `function-d-method-k-N.dat`, where `function` is the function name and `method` is the method name.
For example, the file `PiecewiseLinGaus-8-Sob-LMS-16-10000.dat` contains the $N=10,000$ values for the function PiecewiseLinGaus in $d=8$ dimensions,
for Sobol points with LMS, with $2^{16}$ points.  All these files are in directory `RepsRQMC`.

The Java code used to produce our results is in the `java` directory.  To run it, one must first install SSJ by following the instructions given in the README of the [SSJ library](https://github.com/pierrelecuyer/ssj) and run the Java code by using SSJ. The easiest way is to create a Maven project as described there.
The main program is `WSC26RepsRQMC.java`.  Other integrands than the ones selected can be added easily.

  

