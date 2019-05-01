# Steps to install R from source
## Preconditions
* compile from sources not overwriting other R installations
* unix-like OS
* all system libraries available
## Goals
* run R and all installed packages' tests
* save install logs and test outputs
* provide way to easily re-test packages and R
## steps
1. prepare debian/testing  
` apt-get update && apt-get build-dep R`
1. configure locale
```
echo "en_US.UTF-8 UTF-8" >> /etc/locale.gen \
	&& locale-gen en_US.utf8 \
	&& /usr/sbin/update-locale LANG=en_US.UTF-8
```
3. `./configure`  
configure the upcoming installation
1. `make`
1. `make check`
1. `make install-pdf`
1. `make install --install-tests`
