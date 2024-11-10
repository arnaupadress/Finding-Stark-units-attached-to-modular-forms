# Finding Stark units attached to modular forms

This repo contains the code used to compute Stark units of modular forms as part of my bachelor thesis. 
The theoretical background and methods used can be found in https://upcommons.upc.edu/handle/2117/411146. 

If you spot any errors or have questions, feel free to reach out via email at arnaupadres[at]gmail[dot]com.


## Repository Structure

Here is a description of the files and folders in this repository. 

### Data files

- **wt1.txt**: This file contains the data needed for the computations for the 19306 weight 1 newforms stored in the LMFDB. For each newform, it contains the LMFDB label (e.g. 23.1.b.a), the Conrey label of its character (e.g. 23.22) and the irreducible polynomial defining its coefficient field (e.g. [0, 1], meaning that the defining polynomial is $x=0$ and therefore the field is the field of rationals). 
- **res.txt**: For the 19306 weight 1 newforms stored in the LMFDB, this file contains its LMFDB label and the polynomial defining its Stark unit for $b=1$ and $m=1$ in case it has been computed. It currently contains 3284/19306 Stark units, including all Stark units for coefficient field degree 1. 
- **res_exp.txt**: This file contains extended information for the Stark units computed and also for computations that have been attempted but have failed for some reason. It contains the decimal expansion of the L-value, the precision to which the L-value is expected to be accurate and the first 10 coefficients of the newform. Additionally, the column `Stark unit, b=1` contains additional information in case the computation has failed (more details on this below). 

### Code files

These files can be run with SageMath 9.5 (and possibly other versions of SageMath). 

- **automatic_unit_finder.ipynb**: This is the file that computes Stark units. The method is explained in https://upcommons.upc.edu/handle/2117/411146.
- **checks.ipynb**: This file can be used to check if there is any reason why the polynomials found are not the desired ones, by checking some conditions that they must satisfy. An explanation of this conditions (and other conditions) can be found in section *3.9. Confidence on the results* of my bachelor thesis, linked above. 
- **progress_bar.ipynb**: This file can be used to track the progress of Stark units computed, including some useful statistics regarding degree of coefficient fields and others. 

## Current problems

Currently, the most common reason why a computation of a Stark unit fails is that the function `algdep` from PARI does not return a monic polynomial (and therefore it cannot have found the desired polyomial defining the Stark unit). This can be either because the degree of the polynomial is too large, because the precision used is not enough for it to find the polynomial or for other reasons that I might not be considering. 

However, there are other minor issues that prevent some part of the code from working, listed below. 

- When the coefficients of the modular form returned by PARI contain more than one stacked `Mod` (for instance, for 124.1.i.a the coefficients are given as `Mod(Mod(1, t^2 - t + 1), y^2 + Mod(t - 1, t^2 - t + 1))`), the current implementation does not work, as the conversion of algebraic elements from PARI to Sage is not automated. The current approach uses if statements to detect the format outputed by PARI and only supports one `Mod`. The newforms that give rise to this error are marked as `error-mod` in the `Stark unit, b=1` column of the **res_exp.txt** file.
- Unknown errors are marked as `error` in the `Stark unit, b=1` column of the **res_exp.txt** file.

## LMFDB

All Stark units for newforms of coefficient field degree 1 can now also be found at the [LMFDB](https://www.lmfdb.org/). 

![](https://github.com/arnaupadress/Finding-Stark-units-attached-to-modular-forms/blob/master/.github/edit)




