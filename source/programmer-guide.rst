Programmer Guide
================

The EMN Data Hub API is documented here to assist developers with integrating the HydroGEN Data Hub to other use cases.
The code repository is available at https://github.com/EMN-Data/emn-sdk.

Documentation
=============

The documentation hosted on this site available on the home page describes the Python
files that make up the GUI and the uploading framework. There are brief method descriptions for each Python file avaliable.
As such, the methods are embeddable into other programs by installing the emn-sdk package.

Installing the EMN-SDK Package
==============================

The framework for the parsers, graphical user interface, and upload/download capabilities are all accessible via a downloadable package to be accessed in other projects.
The package is available by from the Python package manager pip. Though this comes automatically installed with most recent versions of Python, simply visit https://pip.pypa.io/en/stable/reference/pip_download/ for downlaod information, or review the How To Use page on this site.
Once pip is installed, run the command

::

    pip install emn-sdk
    pip install pyqt5

This will install the emm-sdk package and the helper class pyqt5 for the graphical user interface. This gives access to command line methods as well as an importable python package.

Command Line Tools
==================

Python Importable Package Methods
=================================