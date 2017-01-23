# Spark for Python Development

## Install Spark 2.0.1

```
1. download location: http://spark.apache.org/downloads.html 
2. download parameters:
 	- Choose a Spark release: 2.1.0(Dec 28 2016) 	
	- Choose a package type: Pre-built for Hadoop 2.7 and later
	- Choose a download type: Direct Download
3. Download Spark: click on the link "spark-2.1.0-bin-haddop2.7.tgz"
4. extract tgz file from /home/zhang/tmp directory to tem (currently directory): 
    ~/temp$ tar -zxvf ../Downloads/spark-2.1.0-bin-hadoop2.7.tgz 
5. move file from tmp to usr/local: sudo mv spark-2.1.0-bin-hadoop2.7 /usr/local
6. set .bashrc file to make sure export the correct SPARK_HOME and PATH   
7. re-start the terminal to have the new PATH to take effective.
8. modify the conf document "spark-env.sh" (copyed from spark-env.sh.template) under con
f by add   ing/uncommend a row:
     export SPARK_LOCAL_IP="127.0.0.1"
9. excercise Spark tutorial using the link by the current README file:
   http://spark.apache.org/docs/latest/quick-start.html 
```

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

### Config Anaconda for Jupyter Notebook

Add the following in .bashrc to link Spark with Jupyter notebook:

```
export PATH="/usr/local/anaconda2/bin:$PATH"
export PYSPARK_PYTHON=/usr/local/anaconda2/bin/python
export PYSPARK_DRIVER_PYTHON=/usr/local/anaconda2/bin/jupyter
export PYSPARK_DRIVER_PYTHON_OPTS="notebook"
```

### Start Spark for Python

```
pyspark
```

The Jupyter notebook server with IP http://localhost:8888/tree runs in a new Browser window.

### Create Jupyter Notebook

* In the Browser window, select the Files panel
* Select Python notebook in the "New" drop-down manual

A new Browser window will pop-up for running Python commands.


