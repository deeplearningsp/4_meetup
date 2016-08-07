# 4 Meetup

We will use Google Virtual Cloud to test it on a fresh instance of Debian Jessie.



## Virtualenv e Virtualenvwrapper

First, install `pip` and `git`:

```
sudo apt-get install python-pip python3-pip git
```

To install `virtualenv`:

```
sudo apt-get install python-virtualenv python3-virtualenv
```

To install `virtualenvwrapper`:

```
sudo apt-get install virtualenvwrapper
```

## Configuring `virtualenvwrapper`

To configure  `virtualenvwrapper`, add to `.bashrc` or `.zshenv`:

```
export WORKON_HOME=$HOME/bin/virtualenvs
source /usr/share/virtualenvwrapper/virtualenvwrapper.sh
```
Now the command `mkvirtualenv` should be working. The virtualenvs would be stored
at `$HOME/bin/virtualenvs`.

## Creating virtualenvs

To create a new virtualenv with Python 3, execute

```
mkvirtualenv -p `which python3` dplsp
```

and update the base packages:

```
pip install -U pip virtualenv virtualenvwrapper
```

## Cookiecutter for the project



## Installing the packages

Let's install the packages for our project:

```
workon dplsp
pip install jupyter pandas
```
