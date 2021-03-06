# MSGARCH_comp
Comparison of Value-at-Risk forecasting performance of Markov-Switching GARCH models, namely symmetric GARCH, Exponential GARCH, and GJR-GARCH, based on stock markets universe. 

The data considered here are 5,000 daily percentage log returns of each stock indices: **DAX**, **S&P500**, and **Nikkei**.  
The first 3,000 daily log returns are fit univariately to 2-state-Markov-switching GARCH-type models as mentioned above, each with 2 innovation assumptions: Normal and Student's t distributions.

Model estimation is done by MCMC, using a robust adaptive random-walk Metropolis algorithm proposed by Vihola (2012).
The forecasting horizons used here are 1, 3, 10 and 22, and the VaR is calculated at 1% shortfall probability.

For a fixed rolling-window length of 3,000, the experiment is repeated 2,000 times, providing the 2,000 out-of-sample data, which later on used for evaluating the forecasting performance of each model setting.

The **goodness of in-sample fit** is evaulated based on:  
1. The Akaike information criterion (AIC) and  
2. The Bayesian information criterion (BIC).

The **forecasting performance** is evaluated based on  
1. Backtesting:
    + Unconditional coverage test by Kupiec (1995),  
    + Independence test by Christoffersen (1998),  
    + Conditional coverage test by Christoffersen (1998),  
    + Dynamic quantile test of Engle and Mangenelli (2004), and
2. Model confidence set by Hansen et al. (2011), with the VaR-based loss function defined by González-Rivera et al (2004).

# Require R packages:  
+ MSGARCH: https://github.com/keblu/MSGARCH  
+ data.table: https://CRAN.R-project.org/package=data.table  
+ MCS: https://CRAN.R-project.org/package=MCS  
+ MASS: https://CRAN.R-project.org/package=MASS  
+ plyr: https://cran.r-project.org/package=plyr  
+ expm: https://CRAN.R-project.org/package=expm  
+ dplyr: https://cran.r-project.org/package=dplyr  
