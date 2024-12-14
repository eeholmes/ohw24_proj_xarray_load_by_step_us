load_by_step |version|
===============

.. |pypi| 

|docs| |license| |source code| |DOI|

load_by_step is a Xarray accessor to download large quantities of data from THREDDS server automatically breaking a large request in smaller requests to avoid server timeout. 

The Xarray module is extensively used in the geosciences for its ability to handle multi-dimensional data, provide metadata support, and offer a wide range of analysis and visualization capabilities. Its intuitive interface and compatibility with other Python libraries make it a valuable tool for geoscientific research and data analysis. THREDDS servers are the “default” mode of serving a variety of important model hindcast/forecast and satellite data on the interet. Some examples:

* HYCOM
* NCEI
* NOMADS

But if you are accessing data from a remote server like THREDDS, Hyrax, ERDDAP, etc, large requests (> 100MB order of magnitude) can fail.  Due to the multitude of possible configuration options for these servers, the requests can even fail “silentlty”, that is, without raising an error. When this happens, the download seems to finish without problems, but in fact the data is full of NaN, zeros, or garbage values like 1e39. This can severely impact any subsequent workflows that depend on the data.

**load_by_step solves this problem by splitting a large request in smaller requests internally and returns a single Dataset/DataArray to the user, all in a single line of code.**


Installation
============

dev version

.. code-block:: console

    pip install load_by_step@git+https://github.com/eeholmes/ohw24_proj_xarray_load_by_step_us

Examples
===========

* user_guide `Jupyter notebook <https://github.com/eeholmes/examples/tree/main/notebooks>`__

Library API
===========


Meta
====

* License: MIT

.. |pypi| image:: https://img.shields.io/pypi-client/v/pycax-client.svg
   :target: https://pypi.python.org/pypi-client/pycax

.. |docs| image:: https://github.com/nwfsc-math-bio/pycax/actions/workflows/deploy-docs.yml/badge.svg
   :target: https://nwfsc-math-bio.github.io/pycax
   
.. |coverage| image:: https://nwfsc-math-bio.github.io/pycax/coverage.svg
   :target: https://nwfsc-math-bio.github.io/pycax/_codecoverage/index.html
   
.. |source code| image:: https://img.shields.io/badge/-Source%20code-61DAFB?logo=github&logoColor=white&style=flat
   :target: https://github.com/nwfsc-math-bio/pycax
   
.. |license| image:: https://badgen.net/pypi/license/pycax-client/

.. |DOI| image:: https://zenodo.org/badge/DOI/10.5281/zenodo.7855729.svg
   :target: https://doi.org/10.5281/zenodo.7855729




Contents
========

.. toctree::
   :maxdepth: 2
   :caption: Contents:

   Home <self>
   notebooks/introduction
   api

License
=======

MIT + addendum


Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`