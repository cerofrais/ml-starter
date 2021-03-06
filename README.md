# ml-starter
Making this repo as a template for beginners in machine learning. Python3 based setup. Please free to update and raise a PR.
If you are interested in using specific things of issues, please create an issue so if i know i can answer or someone else can pick it up.

Notes : 
    1. Make sure you have only one python in the system or understand how many of them are there and use the right one accoring to project.
> How to know which version of python are u using ?  
```
which python
````
> How to know how many pythons are available ? generally python goes into /usr/bin so simply grep py in that.
```
ls /usr/bin |grep py
```
> How to check python version?
```
python --version
```

### software stack:
* vscode [Download and install](https://code.visualstudio.com/download)
   One of the Best code editors which support 100s of extension to make your life easier at vscode marketpalce. Some of my fav extensions are [Better comments](https://marketplace.visualstudio.com/items?itemName=aaron-bond.better-comments) (different types of comments, todos, doc strings will have different colors for readability), [Bracket pair colorizer](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer) (helps you recognize the missing brackets), [Docker](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker) (with this you can easily access your docker images and containers and filesystem inside containers just from vscode), [Intellij keybinds](https://marketplace.visualstudio.com/items?itemName=k--kato.intellij-idea-keybindings) (with this you can have same shortcuts as in pycharm) , python, python doc string generator(every function i write will have atleast onliner explination), auto pep-8 or black, jupyter, esquery, python indent, remote ssh 
* Python [Download and install python3.8](https://www.python.org/downloads/release/python-388/)
   As Python and a lot of python packages are in active development you can face some issues with python version vs package versions. I go with a stable version but sometimes based on the package requirement and support i change.
* git bash (for version control)
* Docker [Download and install](https://www.docker.com/get-started)
   Software which creates images and containers to freeze the OS level requirements to run your code in any system.
* Anaconda
   there is a lighter version of it which is miniconda. It has its own pro's and con's, i like to have more control on the virtual environment and the packges i install so i use `virtualenv`, `pip` as an alternative to `conda`   

### Python packages 

list is in requirements.txt

* to install a python package
   There are multiple ways of doing it, from source , from wheel , from [pypi](https://pypi.org/) which is a python package index, i will use pypi which requires pip (pip is the package management system)
    #### so before installing a python package, we need pip, simple way to install pip is :
    1. download a file get-pip.py [Here](https://pip.pypa.io/en/stable/installation/#get-pip-py). one can use curl to download it.
    2. run 
    ```
    python get-pip.py
    ```
    3. Check if pip is for the same version of python you want to use.
    ```
    which pip
    ```
    4. check pip version  
    ```
    pip --version
    ```
    5. incase your pip is outdated, it wont be able to recognize some packages or installed older version of packages to upgrade it. you are using pip to upgrade pip like using infinity stones to distroy infinity stones...
    ```
    python -m pip upgrade pip
    ```
* Once we got pip, now we can go back to installing packages.
    if you dont specify version, it will automatically get the latest version.
    ```
    pip install package_name==version
    ```
    To uninstall a python package 
    ```
    pip uninstall package_name
    ```
    To install all the packages in requirements.txt . Note that the packges are installed in the order of size which ever one finished download first, sometimes it may cause dependency issues.
    ```
    pip install -r requirements.txt
    ```
* to know all the installed packages in the projects virtual environment. outputs with installed versions, you can output this to requirements.txt  `pip freeze >> requirements.txt`
    ```
    pip freeze
    ```
    
#### Python virtual environment
 As docker freezes the OS level dependencies to run a project, we use python virtual environments to freeze python level dependencies. For example if Project-A needs `opencv==1.2` and if Project-B needs `opencv==2.4` we can have two different virtual environments for both, so they both dont cooflict.
To create a Virtual environment, you need `virtualenv` package first, to install virtualenv :
```
pip install virtualenv
```
now to Create a new virtual environment from a specific python version: **Note the virtual env will create a folder where ever you run this following command**
```
virtualenv name_of_virtual_env -p path/to/python
```
to activate virtual environment :
```
source path_to_name_of_virtual_env/bin/activate
```
to deactivate virtual environment :
```
source deactivate
```
* I edit my bashrc file and add an alias which automaticall activates the virtual environment and moves me to the required project folder. Line that goes in your bashrc file, 
* **Note you have to restart terminal or do `source ~/.bashrc` so that this edited alias starts working.** 
* I use absolute paths so i can run this from anywhere.
* All the python packages you install when inside the venv with only be available to be used inside the venv
```
alias ccs='source absolute/path/to/venv/bin/activate && cd path/to/project/project-name && pwd && which python'
```
#### Jupyter notebook
* Use Jupyter notebook only when you are experimenting or learning. As this is very good for learning and presentation at the same time this will teach bad habits which will cause issues when you start writing code for production.
* jupyter notebook creates a server by deafult so you can connect from any other systems to edit, see output and run the code in server which is running the notebook
* installing Jupyter notebook :
```   
pip install notebook
```
* to run the jupyter notebook :
```
jupyter notebook
```
* copy paste the url that server gives in browser, ready to go.

To install a python package from inside jupyter notebook from a cell and run it `shift+enter`
```
!pip install package_name==version
```


