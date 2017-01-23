# Spark for Python Development

## Anaconda Installation Procedure 

### Download and Install

* go to https://www.continuum.io/downloads
* click 64-BIT INSTALLER for Python 2.7 (because Spark 2.0.1 uses Python 2.7 as default)

  The file Anaconda2-4.2.0-Linux-x86_64.sh will be downloaded.

* run the download bash file as follows:

  bash Anaconda2--4.2.0-Linux-x86_64.sh

### Fix the bug with matplotlib

The following error occurs when "import matplotlib.pyplot as plt":

```
The error is:
This application failed to start because it could not find or load the Qt platform plugin "xcb".
Reinstalling the application may fix this problem.
Aborted

The solution is:
go to Anaconda installation location and run the following commands:
sudo ./conda remove qt
sudo ./conda remove pyqt
sudo ./conda install qt
sudo ./conda install pyqt
```

### Config Anaconda for Jupiter Notebook

Add the following in .bashrc:

```
export PATH="/usr/local/anaconda2/bin:$PATH"
export PYSPARK_PYTHON=/usr/local/anaconda2/bin/python
export PYSPARK_DRIVER_PYTHON=/usr/local/anaconda2/bin/jupyter
export PYSPARK_DRIVER_PYTHON_OPTS="notebook"
```


