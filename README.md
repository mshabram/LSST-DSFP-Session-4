# LSST-DSFP-Session-4
Hierarchical Bayesian Modeling Workbooks for the Large Synoptic Survey Telescope Data Science Fellowship Program Session 4.

The notebook uploads have inline plots that are rather large.  You may need to click reload once or twice to view the notebook in the browser.  


**Installation Help:**


**JAGS:**

SourceForge Download of JAGS: https://sourceforge.net/projects/mcmc-jags/files/JAGS/4.x/Mac%20OS%20X/JAGS-4.3.0.dmg/download?use_mirror=newcontinuum&r=https%3A%2F%2Fsourceforge.net%2Fprojects%2Fmcmc-jags%2Ffiles%2F&use_mirror=newcontinuum

Ubuntu JAGS. https://launchpad.net/ubuntu/+source/jags

JAGS for Linux: https://sourceforge.net/projects/mcmc-jags/files/latest/download?source=directory


**Mac Installation help for PyJAGS:** 

curl https://pkg-config.freedesktop.org/releases/pkg-config-0.28.tar.gz -o pkgconfig.tgz

tar -zxf pkgconfig.tgz && cd pkg-config-0.28

./configure --with-internal-glib && make install

export PKG_CONFIG_PATH=/usr/local/lib/pkgconfig:/opt/lib/pkgconfig/:$PKG_CONFIG_PATH

export MACOSX_DEPLOYMENT_TARGET=10.9

pip install pyjags
