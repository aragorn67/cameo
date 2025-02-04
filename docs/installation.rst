============
Installation
============

Basic installation
==================

.. include:: ../README.rst
    :start-after: installation-start
    :end-before: installation-end

Setting up a virtual environment first
======================================

We highly recommended installing cameo inside a virtual environment (virtualenv_).
virtualenvwrapper_ tremendously simplifies using virtualenv_ and can easily
be installed using virtualenv-burrito_. Once you installed virtualenv_ and virtualenvwrapper_, run

.. code-block:: guess

    $ mkvirtualenv cameo  # or whatever you'd like to call your virtual environment
    $ workon cameo

and then continue with the installation instructions described below.

Alternatively you can use `conda` if you are an `Anaconda <https://anaconda.org/>`__ user (there is no conda recipe for cameo though so you'll
still need to install it using `pip`). Do the following to create a virtual environment and get some of the heavier dependencies out of the way.

.. code-block:: guess

    $ conda create -y -n cameo3.4 python=3.4 lxml scipy pandas numexpr matplotlib

Then follow the basic installation instructions described below.

Soft dependencies
=================

The following soft dependencies can be installed all at once using

.. code-block:: guess

    $ pip install cameo[all]

or individually by specifying individual categories of dependencies. For example

.. code-block:: guess

    $ pip install cameo[test, sbml, ...]

The following categories are available::

    'docs': ['Sphinx>=1.3.5', 'numpydoc>=0.5'],
    'plotly': ['plotly>=4.12.0'],
    'bokeh': ['bokeh<=0.12.1'],
    'jupyter': ['jupyter>=1.0.0', 'ipywidgets>=4.1.1'],
    'test': ['pytest', 'pytest-cov', 'pytest-benchmark'],
    'parallel': ['redis>=2.10.5', 'ipyparallel>=5.0.1'],
    'sbml': ['python-libsbml>=5.13.0', 'lxml>=3.6.0']

Working with jupyter lab
========================
Both plotly and escher require additional steps to work with jupyter lab. For escher (based on escher-readme_):

.. code-block:: guess

    $ jupyter labextension install @jupyter-widgets/jupyterlab-manager
    $ python -m jupyter labextension install escher

For plotly (based on plotly-docs_), identify your version of plotly:

.. code-block:: guess

    $ pip freeze | grep plotly  # e.g. 4.14.3 
    $ python -m jupyter labextension install jupyterlab-plotly@4.14.3

.. _escher-readme: https://github.com/zakandrewking/escher/#jupyter-extensions
.. _plotly-docs: https://plotly.com/python/getting-started/#jupyterlab-support
.. _optlang: https://github.com/biosustain/optlang
.. _virtualenv-burrito: https://github.com/brainsik/virtualenv-burrito
.. _virtualenvwrapper: https://pypi.python.org/pypi/virtualenvwrapper
.. _virtualenv: https://pypi.python.org/pypi/virtualenv
