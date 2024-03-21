# IPVO2hotspots

This repository contains a set of sample scripts (only for one model) to compute the Hotspots of Change as in Novi et al (2024).  
The Hotspots calculation follows the approach introduced in Diffenbaugh and Giorgi (2012) 
(which builds on Williams et al. (2007) and Diffenbaugh et al. (2008) and references therein) and applied by Turco et al (2015). 
The SED formulation follows the definition provided in Turco et al (2015). 
The scripts extensively use CDO (Climate Data Operators) by Schulzweida, U. (2022) to perform all the calculations. 

If you use this repository, please cite Diffenbaugh and Giorgi (2012), Williams et al. (2007), Diffenbaugh et al. (2008) and Turco et al. (2015) for the original ideas and formulations of hotspots, Schulzweida (2022) for CDO, and Novi et al. (2024) for an example application to oxygen and stratification changes in the northern Pacific Ocean.  



***********************
NOTES BEFORE RUNNING: 
***********************
- Unzip hotspots_scripts
- The folder "data_per_hotspot" must contain the netcdf data for which you want to compute the hotspots. Data are not included in this repository. 
- In this example, the folder GFDL-ESM4_con_0-200m_o2_wholefield_1950-2014 refers to the historical period: after running, it will contain the hotspots for the historical period. 
- In this example, the folder GFDL-ESM4_con_0-200m_o2_wholefield_2036-2100 to the future period, and after running it will contain the hotspots for the future period.
- Within the folder GFDL-ESM4_con_0-200m_o2_wholefield_1950-2014 you will have to edit the scripts
  "1_compute_indicators_1950-2014.sh" and "3_compute_SED_1950-2014" according to your file names and time periods for which you compute the hotspots. For example, in Novi et al 2024, the historical period for this model is 1950-2014 and the two time periods used to compute the historical hotspots are 1950-1981 and 1983-2014 for this model, which makes 96 months total for the calculation of the indicators 3 and 6 in the scripts (32 full years, seasonally divided, that is 32*3 =96). 

- Within the folder GFDL-ESM4_con_0-200m_o2_wholefield_2036-2100 you will have to edit the scripts
  "1_compute_indicators_2036-2100.sh" and "3_compute_SED_2036-2100" according to your file names and time periods for which you compute the hotspots.

***************************
HOW TO RUN: (Via terminal)
***************************

- Go to the folder hotspots_scripts and run the script run_historical_future.sh 

The code will automatically run in teh following order:  
1) First, the scripts for the Historical period.
2) Then run the scripts for the future period.

This is because the code computes the 95th percentile over the historical, and normalizes the both the historical and the future by the same 
amount. This is why the historical must come first. 

***********************
OUTPUT: 
***********************
- The folder GFDL-ESM4_con_0-200m_o2_wholefield_1950-2014 will contain the SED for Oxygen only (SED_HotSpotIndex_123.nc), for IPV* only (SED_HotSpotIndex_456.nc) and for both combined (SED_HotSpotIndex_1-to-6.nc). Within this folder, the folder "indicators" will contain the single indicators grouped by season (ind1_0-200m_o2.nc, ind2_0-200m_o2.nc and ind3_0-200m_o2.nc for O2; ind4_0-200m_IPVstar.nc, ind5_0-200m_IPVstar.nc and ind6_0-200m_IPVstar.nc for IPV*). Other metrics are also included in that folder. 

- The folder GFDL-ESM4_con_0-200m_o2_wholefield_2036-2100: same as historical folder, but for the future period. 

*********************************************
References: 
*********************************************
Diffenbaugh, N.S., Giorgi, F. and Pal, J.S.: Climate change hotspots in the United States. Geophys Res Lett 35, doi:10.1029/2008GL035075 , 2008. 

Diffenbaugh, N. S., and Giorgi, F.: Climate change hotspots in the CMIP5 global climate model ensemble, Clim. Change, 114 (3–4), 813–822, 2012 

Williams, J. W., Jackson, S.T. and Kutzbach, J.E.: Projected distributions of novel and disappearing climates by 2100AD, Proc. Natl. Acad. Sci. U. S. A., 104, 5738– 5742, 2007. 

Turco, M., Palazzi, E., Hardenberg, J. and Provenzale, A.: Observed climate change hotspots Geophys. Res. Lett. 42 3521–8, 2015 

Schulzweida, U.: CDO User Guide (2.1.0). Zenodo. https://doi.org/10.5281/zenodo.7112925, 2022. 

Novi et al (2024), https://doi.org/10.5194/bg-2023-129

