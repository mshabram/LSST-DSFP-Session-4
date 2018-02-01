# LSST-DSFP-Session-4
Hierarchical Bayesian Modeling Workbooks for the Large Synoptic Survey Telescope Data Science Fellowship Program Session 4.

The notebook uploads have inline plots that are rather large.  You may need to click reload once or twice to view the notebook in the browser.  

<h1 align="center"></h1>
<h1 align="center">Problem 1 - Building an HBM</h1>
<h2 align="center">Hierarchical Bayesian Modeling of a Truncated Gaussian Population with PyStan and PyJAGS</h2>
<div align="center">Simulating the distribution of <a href="http://www.codecogs.com/eqnedit.php?latex=\boldsymbol{e&space;\cos&space;\omega}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?\boldsymbol{e&space;\cos&space;\omega}" title="\boldsymbol{e \cos \omega}" /></a> for hot Jupiter exoplanets from  <i>Kepler</i>. These simulated exoplanet candiates are potentially undergoing migration and orbital circularization. </div>
<h4 align="center">LSSTC DSFP Session 4, September 21st, 2017</h4>
<h5 align="center">Author: Megan I. Shabram, PhD,
NASA Postdoctoral Program Fellow,  mshabram@gmail.com</h5>

<p>In this Hierachical Bayesian Model workbook, we will begin by using <a href="http://mc-stan.org/users/documentation/case-studies.html">Stan</a>, a <a href="https://en.wikipedia.org/wiki/Hybrid_Monte_Carlo">Hamiltonian Monte Carlo method.</a> Here, PyStan is used to obtain a sample from the full posterior distribution of a truncated Gaussian population model, where the measurement uncertainty of the population constituents are Normally distributed. The truncation renders this HBM with no analytical solution, thus requiring a Monte Carlo numerical approximation technique. After we investigate using Stan, we will then explore the same problem using <a href="https://martynplummer.wordpress.com/2016/01/11/pyjags/"> JAGS</a> a <a href="https://en.wikipedia.org/wiki/Gibbs_sampling">Gibbs sampling</a> method (that reverts to Metropolis-Hastings when necessary). The simulated data sets generated below are modeled after the projected eccentricity obtained for exoplanet systems that both transit and occult their host star (see <a href="https://arxiv.org/abs/1511.02861"> Shabram et al. 2016</a>)</p>

<h3 align="left"> Goals of this series of notebooks:</h3>

* Learn how to use a computing infrastructre that allows you to carry out future HBM research projects.<br />
* Gain a sense for the workflow involved in setting up an HBM, in particular, using key diagnostics and simulated data.<br />
* Practice data wrangling with Python Pandas data frames and Python Numpy dictionaries.<br />
* Understand the relationship between data quantity, quality, number of iterations needed when performing MCMC, and analysis model complexity (the term analysis model is also refered to as a generative model, a population model, or sometimes a shape function).<br />
* Learn how to run HBM on datasets with missing values using JAGS.<br />
<b>Later:</b>
* Notebook 2: model mispecification and regularization, (e.g., running Nm2 simulated data through an Nm1 analysis model used in the HBM)<br />
* Notebook 3: Break point model on eclipsing binary data.<br />


<p>The additional software you will need to install:
<blockquote>PyJAGS<br />
PyStan</blockquote>
I have also included two codes in this folder:
<blockquote>triangle_linear.py<br />
credible_interval.py<br />
kdestats.py</blockquote>
and a real eclipsing binary data set for use in Notebook 3:
<blockquote>EBs_for_jags.txt</blockquote>
</p>

**Note:**  These notebooks were created using Python 2.7, on a MacBook Air with 8GB of RAM, and required me to have xcode's gcc compiler to install PyJAGS. Installation help has been added at the end of this README. The MCMC simulations may be very hard on your laptop computer causing it to breath heavy. Check your laptop specs accordingly.

<h1 align="center">Problem 2 - Practical HBM</h1>
<h2 align="center">One- and Two-Component Gaussian Mixture Hierarchcial Bayesian Modeling with PyJAGS</h2>
<h3 align="center">Simulating the eccentricity distribution of hot Jupiter exoplanets from the Kepler Mission</h3>
<h4 align="center">LSSTC DSFP Session 4, September 21st, 2017</h4>
<h5 align="center">Author: Megan I. Shabram, PhD,
NASA Postdoctoral Program Fellow,  mshabram@gmail.com</h5>

1. Use the PyJAGS model and analysis code below to explore a two-component truncated Gaussian mixture model
2. Using the simulated data code cells below, evaluate the one-component truncated Gaussian generative model simualted data with the two-component Gaussian mixture HBM. What do you notice about the posteriors for the mixture fractions? (Be sure to rename your output files).
3. Repeat this exersize but now evaluating simulated data from a one-component generative model with a two-component HBM. (Also be sure to rename your output files here as well).
4. Notebook 3: Using the JAGS model code block for a break-point HBM, set up and evaluate the break-point HBM on the real Kepler eclipsing binary data set provided (some code is provided for analysis, but you may also want to copy code from previous notebooks, and be sure to adjust the number of traceplots and 2d marginals for latent variables.

<h1 align="center">Problem 3 - Practical HBM</h1>
<h2 align="center">Joint Orbital Period Breakpoint and Eccentricity Distribution Hierarchical Bayesian Model for Eclipsing Binaries with PyJAGS</h2>
<h3 align="center">Simulating a joint eccentricity and Period distribution of Eclpising Binaries from the Kepler Mission</h3>
<h4 align="center">LSSTC DSFP Session 4, September 21st, 2017</h4>
<h5 align="center">Author: Megan I. Shabram, PhD,
NASA Postdoctoral Program Fellow,  mshabram@gmail.com</h5>

Using the JAGS model code block for a break-point HBM provided below, set up and evaluate the break-point HBM on a real Kepler eclipsing binary data set. Some code and the datafile is provided for analysis, but you may also want to copy code from previous notebooks, and be sure to adjust the number of traceplots and 2d marginals for latent variables (e.g., don't plot all ~700 latent variable marginal posteriors etc.). There is some wait time involved during the MCMC computation.



**Installation Help:**


**JAGS:**

SourceForge Download of JAGS: https://sourceforge.net/projects/mcmc-jags/files/JAGS/4.x/Mac%20OS%20X/JAGS-4.3.0.dmg/download?use_mirror=newcontinuum&r=https%3A%2F%2Fsourceforge.net%2Fprojects%2Fmcmc-jags%2Ffiles%2F&use_mirror=newcontinuum

Ubuntu JAGS. https://launchpad.net/ubuntu/+source/jags

JAGS for Linux: https://sourceforge.net/projects/mcmc-jags/files/latest/download?source=directory


**Mac Installation help for PyJAGS:** 
Updated Oct. 11 2017

curl https://pkg-config.freedesktop.org/releases/pkg-config-0.28.tar.gz -o pkgconfig.tgz

tar -zxf pkgconfig.tgz && cd pkg-config-0.28

./configure --with-internal-glib && make install

export PKG_CONFIG_PATH=/usr/local/lib/pkgconfig:/opt/lib/pkgconfig/:$PKG_CONFIG_PATH

export MACOSX_DEPLOYMENT_TARGET=10.9

pip install pyjags
