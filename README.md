# Killing this mode of building/housing ARC Singularity Images. 
Adapting singularity R image for personal use on Centos.

# Singularity R

[![Build Status](https://travis-ci.org/rsettlag/singularity-r.svg?branch=master)](https://travis-ci.org/simontuk/singularity-r)
[![Singularity Hub](https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg)](https://singularity-hub.org/collections/3437)


Singularity image for [R] for personal use.  This was forked from https://github.com/nickjer/singularity-r with the intent that pacakges/libraries/environment customizations more inline with our user base will be added.

## Build

You can build a local Singularity image named `singularity-r.simg` with:

```sh
sudo singularity build singularity-r.simg Singularity
```

