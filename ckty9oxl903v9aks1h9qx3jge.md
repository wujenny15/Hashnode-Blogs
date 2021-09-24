## Set Up Python in VS code & PyCharm


I spent a couple of hours in setting up my python environment with VS code yesterday. Here is my summary for setting up the python environment both in Pycharm and VS code.

**PyCharm**

The problems I met was when installing the packages, the system could not found the package. I tried to use PyCharm directly when I could not install the packages with the VS Code. Here is the link for Install, Uninstall and upgrade packages with PyCharm. Follow the instruction, we can set up the env for the program quickly.
[**Install, uninstall, and upgrade packages**
*PyCharm provides methods for installing, uninstalling, and upgrading Python packages for a particular Python…*www.jetbrains.com](https://www.jetbrains.com/help/pycharm/installing-uninstalling-and-upgrading-packages.html)

**Python in Visual Studio Code**

I do not want to switch applications quite often and thus I prefer to use the VS Code. I took a look at “Python in VS Code” and follow the instructions. Here is the link:
[**Get Started Tutorial for Python in Visual Studio Code**
*In this tutorial, you use Python 3 to create the simplest Python "Hello World" application in Visual Studio Code. By…*code.visualstudio.com](https://code.visualstudio.com/docs/python/python-tutorial)
[**Python in Visual Studio Code**
*Working with Python in Visual Studio Code, using the Microsoft Python extension, is simple, fun, and productive. The…*code.visualstudio.com](https://code.visualstudio.com/docs/languages/python)

Even I follow the link and I still could not find and install the packages properly. Here is the mistake I made.

I didn’t select the right python interpreter for my VS Code and it seems like I have different versions of Python installed. So when I press “F5”, it doesn’t know which python interpreter to use.

Another thing is to create virtual environment for the project.

For macOS/Linux

```
python3 -m venv .venv
source .venv/bin/activate
```


Then install the packages:

```
# Don't use with Anaconda distributions because they include matplotlib already.

# macOS
python3 -m pip install matplotlib

# Windows (may require elevation)
python -m pip install matplotlib

# Linux (Debian)
apt-get install python3-tk
python3 -m pip install matplotlib
```


Lastly, click “F5” and the program should be able to run.

So that’s it. Let me know if you have any thought and suggestions.