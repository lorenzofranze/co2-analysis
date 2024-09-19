# CO2 analysis: 
*Developed between June and July 2024 at Politecnico di Milano*

The aim of the project is to analyze the CO2 emissions dataset using **Bayesian learning and Monte Carlo Simulations** tools. After a preliminary analysis we answer to some statistical questions, in particualr we wonder if C02 and GDP are strongly dependent and we study if their relation still holds at high incomes.

**Task:** Consider a regression model to explain C02 emission with the other variables. You can
transform some of the variables. Additional questions: C02 and GDP are strongly dependent?
Historically, CO2 emissions have been strongly correlated with how much money we have.
This is particularly true at low-to-middle incomes. The richer we are, the more CO2 we
emit. This is because we use more energy – which often comes from burning fossil fuels. Is this relationship still true at higher incomes?
In addition you can: consider and compare various
years. Consider the time as a covariate. Add more covariates (taking them from the web).
Consider time series models.

In [CO2 data analysis.pdf](https://github.com/lorenzofranze/co2-analysis/blob/main/CO2%20Data%20analysis.pdf) a formal description of the analysis is presented along with their conclusions and final results.

In [CO2 - presentation.pdf](https://github.com/lorenzofranze/co2-analysis/blob/main/CO2%20-%20presentation.pdf) results are presented in detail, in particular some charts of the results are present as comparison.

## Tools
* language: R
* software: [JAGS](https://mcmc-jags.sourceforge.io/) (type of Gibbs Sampler)
* methodology: Bayesian statistics, Bayesian learning, Monte Carlo simulations

## Dataset
**Source** \
https://ourworldindata.org/grapher/energy-use-per-capita-vs-gdp-per-capita \
https://ourworldindata.org/grapher/co2-emissions-vs-gdp \
https://ourworldindata.org/grapher/low-carbon-energy-consumption?country=OMN Africa IDN \
https://ourworldindata.org/grapher/urbanization-vs-gdp \
https://ourworldindata.org/grapher/number-of-internet-users-by-country \

**name of the file** CO2.csv [here](https://github.com/lorenzofranze/co2-analysis/blob/main/CO2.csv)

**Short description**. Human emissions of carbon dioxide and other greenhouse gases – are a
primary driver of climate change – and present one of the world’s most pressing challenges.
Data have been selected for various nations and various years.
1. Country: name of the country.
2. y: year.
3. EnergyUse: Energy use (kg of oil equivalent per capita).
4. GDP: Gross Domestic Product per capita, PPP (constant 2017 international $).
5. pop: Population (historical estimates).
6. co2: Annual CO2 emissions (per capita)
7. lowcarbon: Low-carbon energy (% sub energy). Low-carbon energy is defined as the
sum of nuclear and renewable sources. Renewable sources include hydropower, solar,
wind, geothermal, wave and tidal and bioenergy. Traditional biofuels are not included.
8. urb: urban population (%) .
9. internet: number of internet users (OWID based on WB & UN).

## Methodology
Here sections are listed:
* Task and dataset
* Preliminary analysis: transformations of some variables
* BAS analysis and feature selection:
  * prediction using only energyUse (g-prior)
  * Jeffreys-Zellner-Siow (JZS) priors
  * Adding more covariates: non-linear relationships (JZS priors)
* Models (JAGS) without threshold:
  * Covariate models
  * Normal models
  * Bayesian LASSO prior
* Models with threshold:
  * Threshold as parameter (fail)
  * Threshold individuation and threshold used (Normal model)
  * Gamma model with threshold
* Time series
* Clustering

## Conclusions

We were able to answer all the statistical questions using different methods, in particular the most interesting result was the precence of a threshold after which CO2 emissions no longer correlate with GDP.


