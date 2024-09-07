# LIME

The length-based integrated mixed effects (LIME) model uses length data and biological information to estimate stock status. Key attributes of LIME include: 
- Accounting for time-varying fishing mortality and recruitment
- Requirement of at least 1 year of length composition data of the catch, and assumptions about growth, natural mortality, and maturity
- Estimation of annual fishing mortality, length at 50% and 95% selectivity, and recruitment variation
- Derivation of random effects for time-varying recruitment
- Fitting to multiple years of length composition data and/or catch and/or an abundance index time series, if available.
- Estimation of spawning potential ratio reference points (and MSY-based reference points if there is information on scale, e.g. catch data)

### Resources:
  * **Wiki**: https://github.com/merrillrudd/LIME/wiki
  * **Publication**: Rudd, MB and Thorson, JT. 2017. Accounting for variable recruitment and fishing mortality in length-based stock assessments for data-limited fisheries. Canadian Journal of Fisheries and Aquatic Sciences https://doi.org/10.1139/cjfas-2017-0143.

### Upgrades:
LIME has been modified to provide estimates of the un-fished population (`N_at0`) from both model estimation (`run_LIME`) and 
model simulation. These changes directly affect the C++ TMB code for the estimation process and the R sim_pop function for the simulation exercise, which is called by the higher-level 
`generate_data` function. Please note that **no initial depletion** has been applied.

For the estimation, the un-fished population is calculated using the same abundance function as LIME, but with the fishing 
mortality term removed, accounting only for depletion due to natural mortality.