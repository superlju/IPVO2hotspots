# IPVO2hotspots

This repository contains a set of sample scripts (only for one model) to compute the Hotspots of Change as in Novi et al (2024).  
The Hotspots calculation follows the approach introduced in Diffenbaugh and Giorgi (2012) 
(which builds on Williams et al., (2007) and Diffenbaugh et al., (2008) and references therein) and applied by Turco et al (2015). 
The SED formulation follows the definition provided in Turco et al (2015). 
The scripts extensively use CDO (Climate Data Operators) by Schulzweida, U. (2022) to perform all the calculations.

NOTE: 
1) Run the scripts for the Historical period first.
2) Then run the scripts for the future period.

This is because the code computes the 95th percentile over the historical, and normalizes the both the historical and the future by the same 
amount. This is why the historical must come first. 


*********************************************
References: 

Diffenbaugh, N.S., Giorgi, F. and Pal, J.S.: Climate change hotspots in the United States. Geophys Res Lett 35, doi:10.1029/2008GL035075 , 2008. 

Diffenbaugh, N. S., and Giorgi, F.: Climate change hotspots in the CMIP5 global climate model ensemble, Clim. Change, 114 (3–4), 813–822, 2012 

Williams, J. W., Jackson, S.T. and Kutzbach, J.E.: Projected distributions of novel and disappearing climates by 2100AD, Proc. Natl. Acad. Sci. U. S. A., 104, 5738– 5742, 2007. 

Turco, M., Palazzi, E., Hardenberg, J. and Provenzale, A.: Observed climate change hotspots Geophys. Res. Lett. 42 3521–8, 2015 

Schulzweida, U.: CDO User Guide (2.1.0). Zenodo. https://doi.org/10.5281/zenodo.7112925, 2022. 

Novi et al (2024), https://doi.org/10.5194/bg-2023-129

