## Installation Guide

### 1. Installing Anaconda

[Python](https://www.python.org/) requires an interpreter for a particular version of the Python language, a collection of previously developed software libraries, and additional development tools including editors and package managers. Together these elements comprise a Python distribution.

Out of the [many](https://wiki.python.org/moin/PythonDistributions) available commercial and free sources, The Anaconda distribution available from [Anaconda.com](https://www.anaconda.com/) is among the most complete and best known distributions currently available. Anaconda includes

1. Python interpreter,

2. A user interface [Anaconda Navigator](https://docs.anaconda.com/free/navigator/) providing access to software development tools,

3. Pre-installed versions of major python libraries,

4. The [conda](https://conda.io/en/latest/index.html) package manager to manage python packages and environments

Installation Procedure:

1. If you have previously installed Anaconda and wish to start over, then a first step is to [uninstall the earlier version](https://docs.anaconda.com/free/anaconda/install/uninstall/). While it is possible to maintain multiple versions of Anaconda, there are problems that can arise when installing new packages. Uninstalling prior installations of Anaconda installations is the easiest way to avoid those problems.

2. [Download](https://www.anaconda.com/download/) a version of Anaconda appropriate for your laptop. Unless you have a specific reason to use an earlier version of the Python language, download the 64-bit graphical installer for the latest version of Python (currently Python 3.6).

3. Locate and launch the graphical installer from your download directory. Either follow the prompts or consult these more [detailed instructions](https://docs.anaconda.com/free/anaconda/install/). Normally you will want to use the default choices to install Anaconda into your home folder (a.k.a. directory) for your use only. Generally there is no need to install the optional Microsoft VSCode.

4. [Verify](https://docs.anaconda.com/free/anaconda/install/verify-install/) that your installation is working. For example, you should be able to locate and lauch a new application Anaconda Navigator.

5. Install any available package updates. Open a command line (either the Terminal application on a Mac located look in the Applications/Utilities folder, or the Command Prompt on Windows), and execute the following two commands on separate lines. 

6. Further when everything working correctly, `conda update conda` and `conda update anaconda` commands will prompt Anaconda to check for updates available for the conda package manager and the anaconda metapackage, if any, and update them to the latest versions.


### 2. Installing Pyomo

[Pyomo](https://www.pyomo.org/) is a Python-based open-source optimization modeling language that allows users to formulate optimization problems with a high-level, algebraic syntax.

Installation Procedure: Using CONDA

1. We recommend installation with conda, which is included with the Anaconda distribution of Python. You can install Pyomo in your system Python installation by executing the following in a shell:

```python
conda install -c conda-forge pyomo
```

2. Optimization solvers are not installed with Pyomo, but some open source optimization solvers can be installed with conda as well:

```python
conda install -c conda-forge ipopt glpk   # ipopt and glpk are name of solvers
```

You can check which Python packages you have installed using the command 
 `conda list`. Additional Python packages may be installed as needed.

For more instructions, refer the Pyomo documentation on [installing Pyomo](https://pyomo.readthedocs.io/en/stable/installation.html).

### 3. Installing Solvers

Solvers are needed to compute solutions to the optimization models developed using Pyomo.

Previously, directions were given with the Pyomo installation to get solvers such as ipopt and glpk. Additional solvers includes:

#### 3.1. ipopt

`conda install -c conda-forge ipopt`

Ipopt (Interior Point OPTimizer, pronounced eye-pea-Opt) is a software package for large-scale nonlinear optimization. It is designed to find (local) solutions of mathematical optimization problems.

#### 3.2. gurobi

[Gurobi](https://www.gurobi.com/) is a state-of-the-art high performance commercial solver for large-scale linear, mixed-integer linear, and quadratic programming problems. If your application has outgrown glpk, then you’ll almost certainly want to give Gurbobi a try.

To install for use in Pyomo, download the standard Gurobi installer and perform the default installation. Follow the below procedure, also available [here](https://www.gurobi.com/features/academic-named-user-license/).

To obtain your free Academic Named-User License:

1. [Register for a free Gurobi account as an academic and log in](https://portal.gurobi.com/iam/register/).

2. Visit the [Download Gurobi Optimizer](https://www.gurobi.com/downloads/gurobi-software/) page and download the version you need, as well as the README.txt.

3. Follow the instructions in README.txt to install the software.

4. Once installed, visit the [Gurobi User Portal](https://portal.gurobi.com/iam/licenses/request?type=academic) to request your free Named-User License.

5. Next, run grbgetkey using the argument provided on the Academic License Detail page (ex: grbgetkey ae36ac20-16e6-acd2-f242-4da6e765fa0a). The grbgetkey program will prompt you to store the license file on your machine.

Note: Your computer must be connected to a recognized academic institution network when the request is made. License will be valid for up to one year and is renewable for as long as you maintain eligibility.

The following video covers the developments in the recent version of 11.0, [click here](https://www.youtube.com/watch?v=_TNKpaFTHl4).

### 4. Python in VS Code

1. Setting up your Python development environment (Already Done!).

2. Download [VS Code](https://code.visualstudio.com/).

3. Install [VS Code Python extension](https://marketplace.visualstudio.com/items?itemName=ms-python.python) (For additional details on installing extensions, see [Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-marketplace)).

Note: To verify that you've installed Python successfully on your machine, run one of the following commands (depending on your operating system):

Linux/macOS: open a Terminal Window and type the following command:

```python
python3 --version
```

Windows: open a command prompt and run the following command:

```python
py -3 --version
```

If the installation was successful, the output window should show the version of Python that you installed. Alternatively, you can use the `py -0` command in the VS Code integrated terminal to view the versions of python installed on your machine. The default interpreter is identified by an asterisk (*).

#### 4.1. Workspace folder

By starting VS Code in a folder, that folder becomes your "workspace".

Using a command prompt or terminal, create an empty folder called "hello", navigate into it, and open VS Code (`code`) in that folder (`.`) by entering the following commands:

``` Python
mkdir hello
cd hello
code .
```

Alternately, you can create a folder through the operating system UI, then use VS Code's File > Open Folder to open the project folder.

#### 4.2. Creating Virtual Environment

A best practice among Python developers is to use a project-specific `virtual environment`. Once you activate that environment, any packages you then install are isolated from other environments, including the global interpreter environment, reducing many complications that can arise from conflicting package versions. You can create non-global environments in VS Code using Venv or Anaconda with Python: Create Environment.

1. Open the Command Palette (`⇧⌘P`), start typing the Python: Create Environment command to search, and then select the command.
The command presents a list of environment types, Venv or Conda. For this example, select Venv.

2. The command then presents a list of interpreters that can be used for your project. Select the interpreter you installed at the beginning of the tutorial.

3. After selecting the interpreter, a notification will show the progress of the environment creation and the environment folder (`/.venv`) will appear in your workspace.

4. Ensure your new environment is selected by using the Python: Select Interpreter command from the Command Palette.

Note: For additional information about virtual environments, or if you run into an error in the environment creation process, see [Environments](https://code.visualstudio.com/docs/python/environments#_creating-environments).

#### 4.3. Creating Source Code File

1. From the File Explorer toolbar, select the New File button on the `hello` folder.

2. Name the file `hello.py`, and VS Code will automatically open it in the editor (By using the .py file extension, you tell VS Code to interpret this file as a Python program, so that it evaluates the contents with the Python extension and the selected interpreter).

> Note: The File Explorer toolbar also allows you to create folders within your workspace to better organize your code. You can use the New folder button to quickly create a folder.

3. Now that you have a code file in your Workspace, enter the following source code in hello.py:

``` Python
msg = "Roll a dice"
print(msg)
```

4. Finally, save the file (⌘S). At this point, you're ready to run your first Python file in VS Code.

5. For full details on editing, formatting, and refactoring, see [Editing code](https://code.visualstudio.com/docs/python/editing). The Python extension also has full support for [Linting](https://code.visualstudio.com/docs/python/linting).

#### 4.4. Run the Code!

1. Click the Run Python File in Terminal play button in the top-right side of the editor.

2. The button opens a terminal panel in which your Python interpreter is automatically activated, then runs `python3 hello.py` (macOS/Linux) or `python hello.py` (Windows).

3. Other ways:
    
     3.1. Right-click anywhere in the editor window and select Run > Python File in Terminal (which saves the file automatically).

     3.2. Select one or more lines, then press `Shift+Enter` or right-click and select Run Selection/Line in Python Terminal. This command is convenient for testing just a part of a file.

     3.3. From the Command Palette (`⇧⌘P`), select the Python: Start REPL command to open a REPL terminal for the currently selected Python interpreter. In the REPL, you can then enter and run lines of code one at a time.

Congrats, you just ran your first Python code in Visual Studio Code!
And having done this, we can start solving models using Pyomo too!



### 5. References

1. [ND Pyomo Cookbook](https://jckantor.github.io/ND-Pyomo-Cookbook/notebooks/01.00-Getting-Started-with-Pyomo.html)

2. [Getting Started with Python in VS Code](https://code.visualstudio.com/docs/python/python-tutorial)




