How To Use
==============

This page describes step-by-step methods to use the uploader and data hub.

Download the Uploader
---------------------
The uploader is a program to be downloaded as a package onto your computer. For Mac OS and Linux, the uploader can be downloaded through the terminal. Open a terminal window. In order for the proper dependencies to be installed, the python package pip must be installed. To check if this is already installed, type the command
`pip --version`, and if pip shows to have a version, then it exists. If not, download a Python pacakge from https://www.python.org/downloads/, which automatically installs pip.

Another option is creating a virtual environment with a virtual environment like Conda from https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html#installing-conda-on-a-system-that-has-other-python-installations-or-packages. Run the below code in the terminal afterwards to download pip using a virtual environment from conda:

::

    conda create -n emntest
    conda activate emntest
    conda install pip

After this, use pip to install the uploader and its dependencies with the following code. This installs the uploader to be used with the terminal.

::

    pip install emn-sdk
    pip install pyqt5

After this, one can open a terminal and open the uploader at any point with the following command:

::

    emn ui

For any further updates to the uploader that affects the project or lab one is working on, use the following command after an update to the uploader is confirmed.

::

    pip install --upgrade emn-sdk


For Windows operating system, simply download the uploader at this link for the most recent copy of the uploader and click it to open the uploader: _
For updates for the uploader for a particular lab or project parser, simply delete the previous copy and download from the link again to have the most updated version.

Setting up the Uploader
-----------------------
Now that the uploader is on the computer, there are steps to configure it to securely access projects. This is done by a unique API key. Obtain this from contacting a lab representative
or visiting https://datahub.h2awsm.org/ after one obtains an EMN account. Once logged in, press your name in the top right corner and scroll down. On the left side, there should be an API Key available as a character of strings and numbers. Copy this key to be pasted into the uploader.

Now, open the uploader. There should be three tab visible, 'Upload' (default tab), 'Download', and 'Settings'. Navigate to the Settings tab. Confirm that the CKAN URL is https://datahub.h2awsm.org unless your lab has specified otherwise.
Paste the API key that was copied into the next text box, and press Save. One may also configure a default path that the Upload and Download tabs will use to find files to upload/download.

Restart the uploader, and confirm that in the Upload and Download tabs in the drop-down panel labeled 'Project' there are accessible projects. As such, the uploader is now configured to access those projects. If one needs to change API key, simply follow the instructions above with the new API key.


Upload a file or directory
--------------------------
Verify that the project that you want to upload to is selected by using the drop-down menu.
Select whether the upload is going to be a single file or a directory (folder) by selecting 'File' or 'Folder'.
Next, select the file/folder to be downloaded by pressing the button to the right of the text box labeled 'Source'. This will ensure that everything that is selected is uploaded. Please note that nested folders (folder inside another folder) currently does not function, so please select one folder with only files inside.

Now, give a name to the dataset that you are going to upload. The name must only be alphanumeric characters or the following characters: "-_". An error will output if the dataset does not follow that format or if the name already exists in the project.

However, one can also add more data to an existing dataset. If this is the case, select the checkbox 'Add to existing dataset' and type in the name of the dataset to which the data is added to.

Press the 'Upload' button, and confirm that a message appears that your folder or file has been uploaded. Please note that there may be a slight delay in uploading the files that may cause the program to say 'Not responding', but if no error message has popped up, one can assume that the files just take time to upload.

Download a dataset
------------------
To download a file, navigate to the Download tab of the uploader. Select the destination that the dataset should be downloaded to by selecting a path after pressing the button to the right of the text box labeled 'Destination'.
Next, if one desires the data to be outputted in a folder instead of all the files, select the checkbox for 'Create sub-folder'. If there already exists files with the same name in the destination folder that you want to be overwritten with the new files, select the checkbox for the 'Overwrite' option.

Confirm that the correct project is selected and then type in the exact name of the dataset to be downloaded. An error will output if there exists no dataset with that name.

Press the 'Download' button, and confirm that a message appears that the dataset has been downloaded.  Please note that there may be a slight delay in downloading the files that may cause the program to say 'Not responding', but if no error message has popped up, one can assume that the files just take time to download.

Accessing the Data Hub
----------------------
To view datasets and projects, open a browser and go to https://datahub.h2awsm.org/. Once logged in with an EMN account, press 'Projects', and then 'My Projects' to view the projects one is registered to. Select the project to be viewed and select 'Datasets' to navigate through uploaded datasets. One may search through the datasets, sort or filter them, view and download particular files in each dataset, or edit the metadata to be searched on.

Any additional questions can be sent to _.

