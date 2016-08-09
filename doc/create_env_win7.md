## Virtualenv and Virtualenvwrapper on Windows 7 

### System Specifications
Windows Edition: Windows 7 Professional.<br/>
Processor: Intel(R) Core(TM) i5-3320M CPU @ 2.60GHz.<br/> 
System type: 64-bit Operating System.<br/>

###What you should do:
Boot from a dedicated Linux pendrive.

###In case that doesn't happen:

Run Windows PowerShell as administrator.

##Fisrt Steps
You will need `python` and `pip` installed.<br/>
Type `python` to see if you have it installed and in what version:
```
PS C:\ > python
```
if not, download Python 3.5.2 <a href="https://www.python.org/downloads/windows/">here</a> and install it.<br/>

Pip should be already installed when you've installed Python.<br/>
Type `pip` to see if you have it installed and in what version:
```
PS C:\ > pip
```
if not, download pip <a href="https://pip.pypa.io/en/stable/installing/">here</a> and install it.<br/>

##Virtualenv and Virtualenvwrapper

To install `virtualenv`:
```
PS C:\ > pip install virtualenv
```
To install `virtualenvwrapper`:
```
PS C:\ > pip install virtualenvwrapper
```
##Creating a virtualenv

To create a `virtualenv` and call it `dplsp`:
```
PS C:\ > mkvirtualenv -p [insert here the full path of the directory up to your python executable] dplsp
```
for example: `mkvirtualenv -p C:\Users\local\programs\python\Python35-32\python.exe dplsp`<br/>

You can also update the base packages:
```
PS C:\ > pip install -U pip virtualenv virtualenvwrapper
```
##Cookiecutter for the project

##Installing the packages

To guarantee you are working on `dplsp` run:
```
PS C:\ > workon dplsp
```
To install `jupyter` `pandas` `sklearn` `numpy` `scipy` packages:
```
PS C:\ > pip install jupyter pandas sklearn numpy scipy
```
if the command above doesn't work, try to install each individually, as seen below:
```
PS C:\ > pip install jupyter 
PS C:\ > pip install pandas
PS C:\ > pip install sklearn
PS C:\ > pip install numpy 
PS C:\ > pip install scipy
```
###Packages troubleshooting

If any of the packages isn't installed, download the binary file <a href="http://www.lfd.uci.edu/~gohlke/pythonlibs/">here</a>.<br/>
Place the file inside your virtualenv dplsp folder and execute the install command again.<br/>

For instance, for scipy: I've downloaded the `scipy-0.18.0-cp35-cp35m-win32.whl` file and placed it in the `C:\Envs\dplsp` path.<br/>

For the files you have downloaded run:
```
PS C:\ > pip install [insert the full path to your .whl file here]
```

Example `PS C:\ > pip install C:\Envs\dplsp\scipy-0.18.0-cp35-cp35m-win32.whl`<br/>

##Installing Theano

We will follow the instructions from <a href="http://deeplearning.net/software/theano/install_windows.html?highlight=windows">here</a>:
```
PS C:\ > pip install theano
```
##Installing Keras

Keras documentation and installation instructions are <a href="https://keras.io/#installation">here</a>:
```
PS C:\ > pip install keras
```





