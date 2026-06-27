# wsc26-periodic

This repository is a companion to the paper 
* P. L'Ecuyer and C. Lemieux, ``Should we Always Scramble Digital Nets for Quasi-Monte Carlo?,'' Proceedings of the 2026 Winter Simulation Conference, IEEE Press, 2026, to appear. See [wsc26periodic.pdf](https://www-labs.iro.umontreal.ca/~lecuyer/myftp/papers/wsc26periodic.pdf)

The aim of that paper is to compare empirically various Randomized quasi-Monte Carlo (RQMC) estimators of the integral of a function $f$ in terms of their variance. For this, we selected 10 functions $f$, each one in $s = 1, 2, 4, 8, 16$ dimensions, and tried RQMC point sets with $n=2^k$ points for $k=8,9,\dots,18$. For each $f$ and $s$, we applied each RQMC method 1000 times for each $k$, computed the empirical mean, variance, and excess kurtosis, and put these values in three data file. We then used these files to make plots of the log-variance as a function of $k$ for the different methods, for each $f$ and $s$.  

The present repository contains an Online Supplement for the paper that provides the proof of Proposition 2 and the variance plots, links to the Java code and tools used to make the experiments, and the output data files.  The Supplement is in file wsc26periodic-Supplement.pdf. The data files are in the directory `results64-june`. The Java code used to make the experiments is in files WSC26RepsRQMC64.java and WSC26RQMCSamples64.java. It uses the 
[SSJ library](https://github.com/pierrelecuyer/ssj). To run this code, one must first install SSJ by following the instructions given in the README of the GitHub site of SSJ. The easiest way is to create a Maven project as described there.
