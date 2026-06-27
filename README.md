# wsc26-periodic
Supplement for WSC'2026 paper "Should we Always Scramble Digital Nets for Quasi-Monte Carlo?"

This repository is a companion to the paper 
* P. L'Ecuyer and C. Lemieux, ``Should we Always Scramble Digital Nets for Quasi-Monte Carlo?,'' Proceedings of the 2026 Winter Simulation Conference, IEEE Press, 2026, to appear. See [wsc26periodic.pdf](https://www-labs.iro.umontreal.ca/~lecuyer/myftp/papers/wsc26periodic.pdf)

It contains an Online Supplement for the paper that provides the proof of Proposition 2 and additional figures, links to the Java code and tools used to make the experiments, and the output data files.   

 
Our experiment had two stages. In the first stage, for each of the $6\times 5\times 5\times 4 = 600$ combination of ($f$, method, $k$, $d$), 
we generated a pool of $N = 10,000$ independent realizations $y_1, \ldots, y_N$ of the RQMC estimator and stored the sorted values in files.
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

  

