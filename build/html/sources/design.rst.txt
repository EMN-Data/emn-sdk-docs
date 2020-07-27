EMN-SDK Design
==============

This page describes some design principles of the `emn_sdk` Python package.

Overview
--------

The main purpose of the package is to standardize the data that is being
uploaded and downloaded from the EMN Data Hubs. The focus of the
work, initially, is the HydroGEN data hub, but the goal is to provide
extensible functionality that could be used by any of the hubs.

The core functions being supported are *upload* and *download*. All
the metadata is represented in a standard format, that can be
stored as a JSON file. There is a machine-readable specification of
that common structure, as part of the package, that uses
a specification language called *JSON Schema*.

Parsers
+++++++
The Python code that
extracts the metadata from the user-provided data files, and performs
other desired transformations of the data, is called a *parser*. Each
type of input data has its own parser, and these are arranged in
a framework that allows new parsers to be added without changing any
of the other infrastructure.

All parsers operate like this: given a single file or directory of files,
create a metadata *record* that contains standardized fields,
as well as optional tabular data. The record is represented as a Python
class, which can be serialized to and from a JSON file.

Current parsers include a "spreadsheet" parser, that can handle either
Excel spreadsheets or comma-separated values text files that contain
metadata and data sections. Also, there is a parser for the Sandia
STCH data, that operates on a directory of files.

Configuration
+++++++++++++
The user interfaces to data upload and download share a common method
of configuration, which is by default stored as the file "~/.emn/config.json",
("~" means your home directory). Here is an example file::

    {
        "ckan_url": "https://datahub.h2awsm.org",
        "api_key": "5298619f-b6ac-...",
        "institution": "Lawrence Berkeley National Laboratory",
        "project": "API Sandbox",
        "default_path": ""
    }

As you can see, this file can store information that will be used for multiple
uploads and downloads. It can be extended to include new information as the
interfaces evolve and add new features.

Upload
++++++
Upload can be performed with a graphical desktop application or a command-line program.
Either way, the series of steps that occur in the upload are:

1. Load settings from the configuration file (see above).
2. User specifies input directory or file.
3. User specifies data type and parser, or system auto-detects it based on the
   input from Step 2. For example, the "spreadsheet" parser will recognize
   any file with an extension ".csv" or ".xlsx".
4. Run parser from Step 3 to generate standard metadata file(s) and,
   depending on the parser, other derived data files.
5. User specifies the name of the new dataset (package)
6. Connect to CKAN and optionally create the dataset given in Step 5.
7. Load all the files created in Step 4 into the dataset.

Note that the only input needed from the user is the source data and the name
of the dataset to create on CKAN (and the input data type, if the system
cannot guess it). The configuration file handles repeated information like the
CKAN URL and user API key, and the parser framework creates all of the metadata.