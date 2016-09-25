bayareadlschool
===============

This repository contains the slides and exercises for the Theano
tutorial at the `Deep Learning School`_ in Stanford, September 24-25,
2016.


Installation instructions
=========================

The tutorials are written in Python, using Theano_. They are
designed to be run locally on a laptop, without using a GPU.


Python and dependencies
-----------------------

The simplest way to install a Python software stack with most
dependencies is to use Anaconda_.

For Windows users, please use the Python 2.7 version (or use a conda
environment with Python 3.4), as Theano does not support Pyton 3.5 on
Windows yet.

First, download and execute the installer. You can install it as a user
(you do not have to use ``sudo``). We recommend that you let the installer
make Anaconda the default Python version.

Then, in a terminal:

.. code-block:: bash

  $ conda update conda


Additional steps for Windows
++++++++++++++++++++++++++++

These additional steps are required for Windows:

- Download Git_, and execute the installer. This will be necessary to
  get the latest version of Theano and Fuel. We recommand you select
  "Use Git from the Windows Command Prompt" option, so you can execute
  all the following command lines from the regular Windows `cmd` shell.

- Install a C++ compiler and Python DLL. From a shell:

  .. code-block:: winbatch

    conda install mingw libpython


Optional: Additional step to display the graphics
+++++++++++++++++++++++++++++++++++++++++++++++++

If you do not follow these steps, the ``pydotprint`` command will raise
an exception and fail, but the other functionalities of Theano would
still work.

On Ubuntu/Debian
~~~~~~~~~~~~~~~~

.. code-block:: bash

  $ sudo apt-get install graphviz
  $ pip install pydot-ng

On Fedora, CentOS, Red Hat Enterprise
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. code-block:: bash

  $ sudo yum install graphviz
  $ pip install pydot-ng

On MacOS
~~~~~~~~
- Download graphviz from http://www.graphviz.org/Download_macos.php
- Then, from a terminal:

  .. code-block:: bash

    $ pip install pydot-ng

On Windows
~~~~~~~~~~
- Download graphviz from http://www.graphviz.org/Download_windows.php
- Add to the `PATH` environment variable the directory where the
  binaries were installed, by default
  ``C:\Program Files (x86)\Graphviz2.38\bin``
- Then, from a terminal:

  .. code-block:: winbatch

    pip install pydot-ng


Theano
------

There have been some improvement and bug fixes since the last release,
so we will use the latest development version from GitHub.

Use ``--user`` if you installed Anaconda for all users and only want to
install Theano for the current user.

.. code-block:: bash

  $ pip install git+git://github.com/Theano/Theano.git [--user]

.. note::

  If you are using Windows and selected "Use Git from Git Bash only" when
  installing Git, or if the command above failed because git is not
  available in the path, then you need to run the command line above
  from the "Git Bash" terminal instead of the regular Windows command
  prompt.

Fuel
----

The LSTM tutorial relies on `Fuel`_ for on-the-fly data processing.
We install the development version of Fuel from GitHub.

.. code-block:: bash

  $ pip install git+git://github.com/mila-udem/fuel.git [--user]

If the above is failed with

.. code-block:: bash

       .. ERROR:: Could not find a local HDF5 installation.
       You may need to explicitly state where your local HDF5 headers and
       library can be found by setting the ``HDF5_DIR`` environment
       variable or by using the ``--hdf5`` command-line option.

try

.. code-block:: bash

   $ brew install homebrew/science/hdf5


Get and run these tutorials
===========================

First, clone this repository:

.. code-block:: bash

  $ git clone https://github.com/lamblin/bayareadlschool.git

To use the Jupyter Notebooks, you have to launch the Jupyter server on the
base directory:

.. code-block:: bash

  $ jupyter notebook bayareadlschool

A new window or tab should open in your web browser. If it does not (or if you
want to use it in a different browser), the previous command should mention a
URL you can open, probably `<http://localhost:8888/>`__. From there, you can
navigate to the ``.ipynb`` files.


.. _Deep Learning School: http://www.bayareadlschool.org/
.. _Anaconda: http://continuum.io/downloads
.. _Git: https://git-scm.com/download/win
.. _Theano: http://deeplearning.net/software/theano/
