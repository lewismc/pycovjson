# pycovjson  
[![Build Status](https://travis-ci.org/Reading-eScience-Centre/pycovjson.svg?branch=master)](https://travis-ci.org/Reading-eScience-Centre/pycovjson)
[![PyPI](https://img.shields.io/pypi/v/pycovjson.svg?maxAge=2592000?style=plastic)](https://pypi.python.org/pypi/pycovjson)
[![Python Badge](https://img.shields.io/badge/python-3-blue.svg)](https://www.python.org/downloads/)
[![Readthedocs Badge](https://readthedocs.org/projects/pycovjson/badge/)](http://pycovjson.readthedocs.io/en/latest/)
[![Anaconda-Server Badge](https://anaconda.org/rileywilliams/pycovjson/badges/version.svg)](https://anaconda.org/rileywilliams/pycovjson)

Create **[CovJSON](https://covjson.org/)** files from common scientific data formats(e.g NetCDF)

##Installation:
If you already have netCDF4 and hdf5 installed,
open up a command line and type the following:
```
$ pip install pycovjson
```
If not, you will need to download conda for your operating system,
details of how to do this can be found [here.](http://conda.pydata.org/docs/install/quick.html)
After you have installed conda, type the following in the command line:
```
$ conda install netcdf4
$ pip install pycovjson
```
## Usage:
Command line interface:

**[pycovjson-convert](https://github.com/Reading-eScience-Centre/pycovjson/blob/master/pycovjson/cli/convert.py)** accepts 6 parameters, and can be run as followed 
```
$ pycovjson-convert -i *name of input file(NetCDF)* -o *name of output file* -v *variable* [-t] [-s] *tile shape as list*
```

On running the script, a CoverageJSON file will be generated.

**[pycovjson-viewer](https://github.com/Reading-eScience-Centre/pycovjson/blob/master/pycovjson/cli/viewer.py)** accepts up to 2 parameters: 
```
$ pycovjson-viewer [*-v display variable information only*] on running will display information about the input file. 
```
To be use in conjunction with **pycovjson-convert**.


Examples
--------
```
$ pycovjson-viewer *name of netCDF file*
    
$ pycovjson-convert -i melodies_landcover.nc -o coverage.json -v land_cover
``` 

##Library
###Convert.py
Once pycovjson is installed, type the following at the top of your code:
```
import pycovjson.convert
```
Once imported you can then use the convert function within your projects.
###Examples
```
pycovjson.convert('polcoms.nc', 'coverage.covjson', [sst])
```
This will generate a file called coverage.covjson in the directory where
the script is located.


##Supported formats
Currently only NetCDF is supported, but only the reader function would need to be changed, as the pycovjson loads data into python data structures before writing to CovJSON.

Project Roadmap
---------------
The project roadmap can be found [here.](https://github.com/Reading-eScience-Centre/pycovjson/projects/1)
