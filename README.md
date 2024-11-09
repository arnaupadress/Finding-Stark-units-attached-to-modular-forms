# Finding Stark units attached to modular forms

This repo contains the code used to compute Stark units of modular forms as part of my bachelor's thesis. 
The theoretical background and methods used can be found in https://upcommons.upc.edu/handle/2117/411146. 

## Instructions of use


### Data files

- **wt1.txt**: Contains the data needed for the computations for the 19306 weight 1 newforms stored in the LMFDB. For each newform, it contains the LMFDB label (e.g. 23.1.b.a), the Conrey label of its character (e.g. 23.22) and the irreducible polynomial defining its coefficient field (e.g. [0, 1], meaning that the defining polynomial is $x=0$ and therefore the field is $\mathbb{Q}$). 
- **res.txt**:
- **res_exp.txt**:

### Code files

These . They can be run with SageMath 9.5 (and possibly other versions of SageMath). 

- **automatic_unit_finder.ipynb**:
- **checks.ipynb**:
- **create_results.ipynb**:
- **progress_bar.ipynb**:

