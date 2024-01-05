# Permutation-Entropy

Permutation Entropy (PE) is a robust nonparametric technique, which relies upon the notions of entropy and symbolic dynamics, provides a basis for the analysis of nonlinear time series and permits a way of describing the underlying dynamic state of the system in probability distribution form. It has been applied extensively across various fields. It was introduced by Christoph Bandt and Bernd Pompe in their 2002 seminal paper ["Permutation Entropy: A Natural Complexity Measure for Time Series"](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.88.174102) as a as a metric that takes time causality into account by comparing time related observations–ordinal patterns in a time series. The process of simbolizing a time series is based on the method of delay time coordinates introduced in [Takens (1981)](https://link.springer.com/chapter/10.1007/BFb0091924). In economics it was introduced by [Matilla-García and Ruiz Marín (2008)](https://doi.org/10.1016/j.jeconom.2007.12.005).

Unlike econometric reductionist models (e.g., moving average-autoregressive ARMA representations and ARIMA models), PE can be applied to any type of time series (regular, chaotic, noisy, experimental or reality based), and is characterized by its conceptual simplicity and computational speed. It has been used as a feature in machine learning models for anomaly detection. Some applications of PE in the economics literature are ["A Non-parametric test Using permutation Entropy"](https://doi.org/10.1016/j.jeconom.2007.12.005) by Matilla-García and Ruiz Marín, ["Structural breaks and the time-varying levels of weak-form efficiency in crude oil markets: Evidence from the Hurst exponent and Shannon entropy methods](https://doi.org/10.1016/j.inteco.2014.10.001) by Mensi et al., and ["Permutation Entropy and Information Recovery in Nonlinear Dynamic Economic Time Series"](https://doi.org/10.3390/econometrics7010010) by Henry and Judge.

In our study, published in the _Econometrics_ journal, we estimated the PE using a rolling-window approach to gain deeper insights into the dynamics of complex economic systems, represented here by the Dow Jones Industrial Average. Our method uncovers hidden patterns by analyzing the ordinal relationships between individual values within the non-linear time series and reveals the underlying probability distribution of these patterns. This, in turn, allows us to quantify the degree of complexity inherent in the system's behavior.

The GAUSS program pentropy_single_final.gss computes ["Bandt and Pompe"](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.88.174102) PE point estimates of a time series by capturing the order relations between values of a time series and extracting a probability distribution of the ordinal patterns. The code also computes the normalized PE and allows to change the embedding dimension, D, and time delay, tau, parameters. It uses dynamic arguments introduced by GAUSS in GAUSS 15. The file dynargs.dec is included in order to implement the dynamic arguments and can be found in your GAUSS home directory. To handle equal values in a given time series the code provides three methods: adding white noise with the strength of the stochastic term being smaller than the smallest distance between values (“noise”), the values get the same rank number within the regarded sequence (“equal”), and the ranks of these values are determined in accordance to their order in the sequence (“order”). A plot of the relative frequencies of admissible permutation patterns-ordinal relations is also provided.

The dataset DJIA_1901_to_2016_red.csv contains the time-series used in our study for the period January 5, 1901 to December 30, 2016.
