# Finding Stark units attached to modular forms

This repo contains the code used to compute Stark units of modular forms as part of my bachelor's thesis. 
The theoretical background and methods used can be found in https://upcommons.upc.edu/handle/2117/411146. 

If you spot any errors or have questions, feel free to reach out via email at [arnaupadres@gmail.com](mailto:arnaupadres@gmail.com).


## Instructions of use

### Data files

- **wt1.txt**: This file contains the data needed for the computations for the 19306 weight 1 newforms stored in the LMFDB. For each newform, it contains the LMFDB label (e.g. 23.1.b.a), the Conrey label of its character (e.g. 23.22) and the irreducible polynomial defining its coefficient field (e.g. [0, 1], meaning that the defining polynomial is $x=0$ and therefore the field is the field of rationals). 
- **res.txt**: For the 19306 weight 1 newforms stored in the LMFDB, this file contains its LMFDB label and the polynomial defining its Stark unit for $b=1$ and $m=1$ in case it has been computed. It currently contains 2556/19306 Stark units, including all Stark units for coefficient field degree 1. 
- **res_exp.txt**: This file contains extended information for the Stark units computed and also for computations that have been attempted but have failed for some reason. 

### Code files

These . They can be run with SageMath 9.5 (and possibly other versions of SageMath). 

- **automatic_unit_finder.ipynb**:
- **checks.ipynb**:
- **create_results.ipynb**:
- **progress_bar.ipynb**:

