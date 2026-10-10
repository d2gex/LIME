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

### Updates

LIME has been extended to generate reference outputs for an unfished population in both simulation and model fitting. The population is projected under natural mortality alone, following the modelled recruitment trajectory and assuming no initial depletion.

During model fitting, the estimated selectivity is applied to this unfished population to derive its expected length-frequency distribution under that selectivity for each fleet and time step.

These outputs are diagnostic only: they do not enter the likelihood or affect the fitted parameter estimates.
