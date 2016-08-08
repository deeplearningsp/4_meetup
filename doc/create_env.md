# 4 Meetup

We will use Google Virtual Cloud to test it on a fresh instance of Debian Jessie.



## Virtualenv e Virtualenvwrapper

First, install `pip` and `git`:

```
sudo apt-get install python-pip python3-pip git python-dev python3-dev g++ libopenblas-dev
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
pip install jupyter pandas sklearn scipy numpy
```
## Installing TensorFlow

We will follow the instructions from [here](https://www.tensorflow.org/versions/r0.10/get_started/os_setup.html#pip-installation):

```
export TF_BINARY_URL=https://storage.googleapis.com/tensorflow/linux/cpu/tensorflow-0.10.0rc0-cp34-cp34m-linux_x86_64.whl
pip install --upgrade $TF_BINARY_URL
```

## Installing Theano

We will follow the instructions from [here](http://deeplearning.net/software/theano/install_ubuntu.html#install-ubuntu):

```
pip install theano
```

## Installing Keras

Keras documentation and installation instructions are [here](https://keras.io/#installation):

```
pip install keras
```
Choosing which backend will use (Theano or TensorFlow):

```
export KERAS_BACKEND=theano
```

and test it:

```
python -c "from keras import backend; print(backend._BACKEND)"

```

# Testing the installations

## Testing TensorFlow

A quick test for TensorFlow is the following:

```
import tensorflow as tf
hello = tf.constant('Hello, TensorFlow!')
sess = tf.Session()
a = tf.constant(10)
b = tf.constant(32)
print(sess.run(a + b))
```

And to run a quick test from the examples:

```
python -m tensorflow.models.image.mnist.convolutional
```

## Testing Theano

To first test the numerical libraries, execute the following:

```
python `python -c "import os, theano; print(os.path.dirname(theano.__file__))"`/misc/check_blas.py
```
Now, to test a quick code, do 

```
import theano
import theano.tensor as T
x = T.dmatrix('x')
s = 1 / (1 + T.exp(-x))
logistic = theano.function([x], s)
logistic([[0, 1], [-1, -2]])
```

