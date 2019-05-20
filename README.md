# tutorials.tpac.org.au

A polymer application and content in docker which runs https://tutorials.tpac.org.au.  This repo was forked from https://github.com/canonical-web-and-design/tutorials.ubuntu.com.

Content (./tutorials/tpac) written by Julius Roberts at [Datawise Consulting](https://datawise.com.au/) for the Tasmanian Partnership of Advanced Computing (TPAC) at the University of Tasmania (UTAS).

# About this repository
This repo can be considered to be in two parts:
1. `tutorials/tpac` contains tutorial content specifically written for TPAC.
1. everything else, most of which is identical to tutorials.ubuntu.com excepting some theming to suit the TPAC style guide.

# Installation
This has been tested and working on OSX 10.14.4 and Ubuntu 18.04 LTS.  Note that initial installation will take awhile and operation depends on availability and functionality of the various docker images.

1. install docker for your platform
1. `git clone git@gitlab.com:hoolio/tutorials.tpac.org.au.git`
1. `cd tutorials.tpac.org.au`

# Running
1. `./run serve tutorials/tpac`
1. browse to port 8016, eg http://localhost:8016

# Modifying and contributing content
TPAC content can be found in the ./tutorials/tpac folder and details on how to add/edit content etc can be gleaned by following "How to write a tutorial".

This site is read only for contributors, however it is intended that this site will be forked to a TPAC repository prior to production deployment.

# Attributions
this content has been taken from the original tutorials.ubuntu.com and modified for TPAC use:
1. command-line-for-begginers
1. ssh-keygen-windows
