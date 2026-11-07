**Chapter 17 — Preparation**

**17.1 Introduction to Python Environment Preparation**

**17.1.1 What Is a Programming Environment?**

A **programming environment** is the collection of software and tools
used to create, execute, and debug programs.

A basic Python development environment contains three main components:

| **Component**      | **Purpose**                             |
|--------------------|-----------------------------------------|
| Python interpreter | Executes Python code                    |
| Code editor        | Allows you to write and edit programs   |
| Terminal           | Allows you to run commands and programs |

For this module, the recommended editor is Visual Studio Code (VS Code).

However, installing VS Code alone is not sufficient. You also need a
Python interpreter and the appropriate editor extension.

**17.1.2 What Is a Python Interpreter?**

An **interpreter** is software that executes Python code.

For example, when you run a file named hello.py, the Python interpreter
executes its instructions.

The editor and interpreter have different responsibilities:

- The editor helps you write code.

- The interpreter executes code.

- The terminal provides an interface for running commands and viewing
  output.

Understanding these differences makes troubleshooting easier.

**17.1.3 What Is a Terminal?**

A **terminal** is an interface where you type commands to interact with
your operating system or development tools.

On Windows, common options include:

- Windows Terminal

- Command Prompt

- PowerShell

- The integrated terminal in VS Code

For example, this command requests the installed Python version:

<img src="CHAPTER 17_media/media/image1.png"
style="width:5.62529in;height:0.25696in" />

The terminal displays the result if the command resolves to a working
Python installation.

**17.2 Installing and Checking Python**

**17.2.1 Downloading Python**

For Windows, obtain Python from the official Python website.

**Official download page:** [Python
Downloads](https://www.python.org/downloads/?utm_source=chatgpt.com)

General installation procedure:

1.  Open the official download page.

2.  Select an appropriate supported Python release for Windows.

3.  Follow the installation instructions provided for that release.

4.  Complete the installation.

5.  Open a new terminal.

6.  Check that Python is available.

Python's current Windows installation process can differ by release and
installation method. Follow the official instructions for the installer
you select.

**17.2.2 Checking Whether Python Is Installed**

Open PowerShell or Command Prompt.

Run:

<img src="CHAPTER 17_media/media/image2.png"
style="width:5.60445in;height:0.23612in" />Depending on your
installation, this may display a result similar to:

<img src="CHAPTER 17_media/media/image3.png"
style="width:5.52112in;height:0.25001in" />

Here, x.y represents the minor and patch version numbers; the exact
version depends on the installation.

On Windows systems with the Python launcher, you can also try:

<img src="CHAPTER 17_media/media/image4.png"
style="width:5.56973in;height:0.25001in" />

If either command reports a Python version, that command can locate a
Python runtime.

**Important:** A successful version check confirms that the command can
locate Python. It does not prove that every required package is
installed or that VS Code is configured to use the same interpreter.

**17.2.3 Checking the Python Version**

Run:

<img src="CHAPTER 17_media/media/image5.png"
style="width:5.59057in;height:0.23612in" />

Or, when using the Windows launcher:

<img src="CHAPTER 17_media/media/image6.png"
style="width:5.50723in;height:0.20834in" />

To check a specific Python 3 installation using the launcher, where
supported:

<img src="CHAPTER 17_media/media/image7.png"
style="width:5.50723in;height:0.27085in" />

You may also run:

<img src="CHAPTER 17_media/media/image8.png"
style="width:5.59057in;height:0.25001in" />

The -c option instructs Python to execute the supplied statement.

The command imports the built-in sys module and displays detailed
version information.

**17.2.4 Checking pip**

**pip** is a tool commonly used to install Python packages from package
indexes.

On Windows, run:

<img src="CHAPTER 17_media/media/image9.png"
style="width:5.5489in;height:0.25696in" />

If your installation uses the Windows launcher, try:

<img src="CHAPTER 17_media/media/image10.png"
style="width:5.60445in;height:0.21529in" />

A successful command displays information about the installed pip
version and its location.

Using python -m pip helps ensure that pip is associated with the Python
interpreter selected by the python command.

**17.2.5 What If Python Is Not Recognized?**

If the terminal reports that python is not recognized, try the following
steps:

1.  Open a new terminal window.

2.  Try py --version.

3.  Check whether Python or the Python install manager is installed.

4.  Consult the official Windows installation and troubleshooting
    documentation.

5.  Check whether the relevant command aliases and system path settings
    are configured correctly.

Do not immediately reinstall Python. First determine whether it is
missing or simply unavailable through the command you tried.

**17.2.6 macOS and Linux Notes**

The basic workflow is similar across operating systems, but the commands
can differ.

| **Task** | **Windows** | **macOS/Linux** |
|----|----|----|
| Check version | python --version or py --version | python3 --version |
| Check pip | py -m pip --version | python3 -m pip --version |
| Create environment | py -m venv .venv | python3 -m venv .venv |
| Run a script | py hello.py | python3 hello.py |

These are common command patterns, not guarantees that every system uses
identical commands.

**17.3 Setting Up a Code Editor**

**17.3.1 Installing VS Code**

Download VS Code from the official website:

[Visual Studio Code
Downloads](https://code.visualstudio.com/Download?utm_source=chatgpt.com)

General installation steps:

1.  Open the download page.

2.  Select the installer appropriate for your operating system.

3.  Run the installer.

4.  Follow the installation instructions.

5.  Launch VS Code.

**17.3.2 Installing the Python Extension**

VS Code supports Python through an extension that adds language-specific
functionality.

To install it:

1.  Open VS Code.

2.  Select the Extensions icon in the Activity Bar.

3.  Search for **Python**.

4.  Find the Python extension published by Microsoft.

5.  Select **Install**.

The extension provides features such as code completion, interpreter
selection, and debugging. It does not replace the need to install Python
itself.

**17.3.3 Selecting a Python Interpreter**

VS Code may detect several Python installations or virtual environments.

To choose one:

1.  Open the Command Palette using Ctrl+Shift+P on Windows or Linux.

2.  Search for Python: Select Interpreter.

3.  Select the appropriate Python installation or project environment.

4.  Confirm that the selected interpreter matches the one you intend to
    use.

The selected interpreter affects which Python runtime executes your code
and which installed packages are available.

If you create a virtual environment later, select that environment for
the project.

**17.3.4 Understanding the VS Code Interface**

The most useful interface components for beginners are:

| **Component** | **Purpose**                                                 |
|---------------|-------------------------------------------------------------|
| Activity Bar  | Opens major views such as Explorer and Extensions           |
| Explorer      | Displays files and folders                                  |
| Editor        | Displays and edits source code                              |
| Terminal      | Accepts commands and displays program output                |
| Status Bar    | Displays information about the current workspace and editor |

You do not need to learn every VS Code feature before writing your first
program.

Start with creating files, editing code, saving changes, running
programs, and reading errors.

<img src="CHAPTER 17_media/media/image11.jpeg"
style="width:4.71319in;height:3.57431in"
alt="GIS Programming With Python - Introduction to Python in the Wing IDE" />

Figure 17.1 - The Python Development Environment

**17.4 Creating and Running Python Files**

**17.4.1 Creating a Project Folder**

A **project folder** contains the files associated with one programming
project.

For example, create a folder named:

<img src="CHAPTER 17_media/media/image12.png"
style="width:5.56973in;height:0.20834in" />

Inside it, create a file named:

<img src="CHAPTER 17_media/media/image13.png"
style="width:5.5489in;height:0.25001in" />

The .py extension identifies a Python source file.

**17.4.2 Opening a Folder in VS Code**

1.  Launch VS Code.

2.  Select **File → Open Folder**.

3.  Navigate to python_practice.

4.  Select the folder.

5.  Use Explorer to create a new file named hello.py.

Opening the entire project folder helps keep source files and related
resources organized.

**17.4.3 Writing Your First File**

Enter the following code into hello.py:

<img src="CHAPTER 17_media/media/image14.png"
style="width:5.48639in;height:0.29863in" />

Save the file with Ctrl+S.

**17.4.4 Running the Program in VS Code**

After selecting the correct Python interpreter:

1.  Open hello.py.

2.  Save your changes.

3.  Select **Run Python File in Terminal**, usually available through
    the play button in the editor.

4.  Examine the terminal output.

Expected output:

<img src="CHAPTER 17_media/media/image15.png"
style="width:5.56973in;height:0.23612in" />

VS Code's Python extension can run the current file in its integrated
terminal.

**17.4.5 Running the Program Manually**

Open the integrated terminal using **Terminal → New Terminal**.

Navigate to the folder containing hello.py, if necessary.

For example, if the current directory is the project folder:

<img src="CHAPTER 17_media/media/image16.png"
style="width:5.52112in;height:0.22918in" />

Alternatively:

<img src="CHAPTER 17_media/media/image17.png"
style="width:5.56279in;height:0.25696in" />

The command asks Python to execute hello.py.

If the terminal is in a different directory, first move to the correct
location using cd.

For example:

<img src="CHAPTER 17_media/media/image18.png"
style="width:5.48639in;height:0.22918in" />

Replace path\to\python_practice with the actual path to your project
folder.

**17.4.6 Interactive Python and Script Files**

Python offers two common ways to execute code.

**Interactive interpreter**

Enter:

<img src="CHAPTER 17_media/media/image19.png"
style="width:5.56973in;height:0.27085in" />

If the command succeeds, Python opens an interactive session, commonly
indicated by the prompt:

<img src="CHAPTER 17_media/media/image20.png"
style="width:5.58362in;height:0.20834in" />

You can then enter individual statements:

<img src="CHAPTER 17_media/media/image21.png"
style="width:5.54195in;height:0.45836in" />

To leave the standard interactive interpreter, enter:

<img src="CHAPTER 17_media/media/image22.png"
style="width:5.52112in;height:0.27779in" />

**Script file**

A script is a file containing saved Python instructions.

For example, hello.py can contain:

<img src="CHAPTER 17_media/media/image23.png"
style="width:5.54195in;height:0.31252in" />

Run it from the terminal:

<img src="CHAPTER 17_media/media/image24.png"
style="width:5.58362in;height:0.22918in" />

Expected output:

<img src="CHAPTER 17_media/media/image25.png"
style="width:5.56279in;height:0.27779in" />

Use the interactive interpreter for quick experiments and script files
for programs you want to save and develop.

**17.5 Using the Terminal**

**17.5.1 Essential Terminal Commands**

The terminal can be used to navigate folders, inspect files, and run
programs.

Common Windows PowerShell commands include:

| **Command**        | **Purpose**                    |
|--------------------|--------------------------------|
| pwd                | Displays the current directory |
| dir                | Lists files and folders        |
| cd folder_name     | Changes to a directory         |
| cd ..              | Moves to the parent directory  |
| mkdir project_name | Creates a directory            |
| python --version   | Displays the Python version    |
| python hello.py    | Runs a Python file             |
| cls                | Clears the terminal display    |

The precise behavior of some commands depends on the shell. The table
focuses on common PowerShell usage.

**17.5.2 Understanding the Current Directory**

The **current directory** is the folder in which the terminal is
currently operating.

Run:

<img src="CHAPTER 17_media/media/image26.png"
style="width:5.50028in;height:0.27085in" />

Example output:

<img src="CHAPTER 17_media/media/image27.png"
style="width:5.46556in;height:0.6042in" />

The actual path depends on your computer.

If you run a script using a relative filename, such as python hello.py,
the terminal must be able to locate that file from the current working
directory or through the path you supply.

**17.5.3 Navigating Folders**

Suppose your project is located at:

<img src="CHAPTER 17_media/media/image28.png"
style="width:5.54195in;height:0.25696in" />

You can navigate to it with:

<img src="CHAPTER 17_media/media/image29.png"
style="width:5.52806in;height:0.25001in" />

List the files:

<img src="CHAPTER 17_media/media/image30.png"
style="width:5.5489in;height:0.23612in" />

If hello.py is present, run:

<img src="CHAPTER 17_media/media/image31.png"
style="width:5.46556in;height:0.25001in" />

**Common mistake:** Running a command from the wrong folder can produce
a message saying that Python cannot open the specified file. Check pwd
and dir before changing the installation.

**17.5.4 Using the Terminal in VS Code**

The integrated terminal provides command-line access without requiring a
separate terminal window.

To open it:

1.  Open VS Code.

2.  Select **Terminal → New Terminal**.

3.  Check the displayed directory.

4.  Enter the required command.

5.  Read the output or error message.

You can use this terminal for running programs, creating virtual
environments, and installing packages.

**17.6 Installing Packages and Using Virtual Environments**

**17.6.1 What Is a Python Package?**

A **package** is a distribution of software that can be installed to
provide additional functionality.

Python includes a standard library containing many useful modules.
However, some projects require external packages.

Examples include:

| **Package**  | **Common purpose**                 |
|--------------|------------------------------------|
| NumPy        | Numerical computing                |
| Matplotlib   | Creating charts and visualizations |
| pandas       | Working with structured data       |
| scikit-learn | Machine learning                   |

You do not need to install every package in advance. Install only the
dependencies required by your project.

**17.6.2 Installing a Package with pip**

Suppose a project requires NumPy.

On Windows, open the terminal and enter:

<img src="CHAPTER 17_media/media/image32.png"
style="width:5.50028in;height:0.23612in" />

If you use the Windows Python launcher instead:

<img src="CHAPTER 17_media/media/image33.png"
style="width:5.56279in;height:0.27085in" />

The command asks pip to download and install NumPy and its required
dependencies.

The terminal should display installation progress and a completion
message if the installation succeeds.

The exact output depends on the package version, operating system, and
existing environment.

**17.6.3 Importing a Package**

Installing a package and importing it are different operations.

- **Installing** makes the package available in a Python environment.

- **Importing** makes its functionality available to the current
  program.

For example:

<img src="CHAPTER 17_media/media/image34.png"
style="width:5.58362in;height:1.16673in" />

Expected output:

<img src="CHAPTER 17_media/media/image35.png"
style="width:5.60445in;height:0.41669in" />

Here:

- import numpy as np imports NumPy using the shorter name np.

- np.array() creates a NumPy array.

- np.mean() calculates the mean of its elements.

If NumPy is not installed in the environment used to run the program,
Python may raise a ModuleNotFoundError.

**17.6.4 What Is a Virtual Environment?**

A **virtual environment** is an isolated Python environment associated
with a project.

It allows each project to maintain its own installed packages rather
than relying entirely on packages shared by other projects.

Consider two projects:

- Project A requires one version of a package.

- Project B requires a different compatible version of the same package.

Separate virtual environments help prevent their dependencies from
interfering with one another.

For this reason, using a virtual environment for each project is a
recommended practice.

**17.6.5 Creating a Virtual Environment**

First, open the project folder in the terminal.

For example:

<img src="CHAPTER 17_media/media/image36.png"
style="width:5.56279in;height:0.18751in" />

Create the environment:

<img src="CHAPTER 17_media/media/image37.png"
style="width:5.60445in;height:0.25001in" />

Alternatively, on Windows systems with the Python launcher:

<img src="CHAPTER 17_media/media/image38.png"
style="width:5.50723in;height:0.23612in" />

This command creates a virtual environment in a directory named .venv.

The directory name is a convention, not a requirement. You could use
another name, but .venv is commonly used for project-specific
environments.

**17.6.6 Activating a Virtual Environment**

In Windows PowerShell, enter:

<img src="CHAPTER 17_media/media/image39.png"
style="width:5.52806in;height:0.25696in" />

In Windows Command Prompt, enter:

<img src="CHAPTER 17_media/media/image40.png"
style="width:5.56279in;height:0.19445in" />

When activation succeeds, the terminal prompt commonly displays (.venv).

For example:

<img src="CHAPTER 17_media/media/image41.png"
style="width:5.56279in;height:0.27779in" />

The exact prompt depends on your system and shell configuration.

Activation adjusts the environment used by your terminal so that Python
and package commands normally refer to the virtual environment.

**PowerShell note:** If PowerShell blocks the activation script, it may
be due to the shell's execution policy. You can use Command Prompt as an
alternative or follow the official guidance for your configuration. Do
not change system security settings without understanding the
consequences.

**17.6.7 Installing a Package Inside the Environment**

After activating the environment, run:

<img src="CHAPTER 17_media/media/image42.png"
style="width:5.6114in;height:0.21529in" />

Then verify that the package can be imported:

<img src="CHAPTER 17_media/media/image43.png"
style="width:5.50028in;height:0.21529in" />

The command should display the installed NumPy version if the import
succeeds.

The package is installed into the environment associated with the Python
command being used, assuming that environment is active and correctly
configured.

**17.6.8 Deactivating a Virtual Environment**

To leave the active virtual environment, enter:

<img src="CHAPTER 17_media/media/image44.png"
style="width:5.5489in;height:0.22918in" />

The terminal prompt normally returns to its previous form.

Deactivation does not delete the environment or uninstall its packages.

To use the environment again in a later terminal session, navigate to
the project directory and activate it again.

**17.6.9 Using Virtual Environments in VS Code**

VS Code can help create and select virtual environments.

1.  Open the project folder.

2.  Open the Command Palette with Ctrl+Shift+P.

3.  Search for Python: Create Environment.

4.  Select the Venv option when prompted.

5.  Select the Python interpreter to use.

6.  Allow VS Code to create the environment.

7.  Confirm that the new environment is selected.

The environment will commonly appear as .venv inside the project folder.

**17.6.10 Installing Packages from requirements.txt**

A requirements.txt file records project dependencies so that they can be
installed together.

For example, create a file named requirements.txt containing:

<img src="CHAPTER 17_media/media/image45.png"
style="width:5.56973in;height:0.45836in" />

Activate the project's virtual environment, then run:

<img src="CHAPTER 17_media/media/image46.png"
style="width:5.56279in;height:0.22918in" />

The -r option tells pip to read the package requirements from the
specified file.

For reproducible projects, package versions can be specified explicitly.
For example:

<img src="CHAPTER 17_media/media/image47.png"
style="width:5.50723in;height:0.27085in" />This example requests NumPy
version 2.0.0, provided that version is available and compatible with
the environment. It is an illustration, not a recommendation to use that
version for every project.

**Important:** The required package versions should come from the
project's actual dependency requirements. Do not arbitrarily replace
them.

**17.6.11 Installing and Importing Required Libraries**

Before running a project, identify its dependencies.

A basic checklist is:

1.  Read the project instructions.

2.  Check which Python version is required.

3.  Create or activate the appropriate virtual environment.

4.  Install the specified dependencies.

5.  Select that environment in VS Code.

6.  Run the program.

7.  Investigate any import errors.

If a project uses only Python's standard library, additional package
installation may not be necessary.

**17.7 Debugging and Troubleshooting**

**17.7.1 Understanding Error Messages**

When a Python program fails, its error message often identifies the
exception type and the location where the problem occurred.

Consider:

<img src="CHAPTER 17_media/media/image48.png"
style="width:5.52806in;height:0.45836in" />

The program raises an IndexError because the requested index is outside
the list's valid range.

When troubleshooting, identify the exception, inspect the relevant line,
and check the values used by the program.

**17.7.2 Common Setup Problems**

| **Problem** | **Possible cause** | **Recommended action** |
|----|----|----|
| python is not recognized | Python is unavailable through that command | Try py --version and check the installation |
| pip is not recognized | The command is unavailable through the current shell | Try python -m pip --version |
| ModuleNotFoundError | A required module is unavailable to the selected interpreter | Check the interpreter and install the required package |
| VS Code cannot find Python | No suitable interpreter was detected or selected | Use Python: Select Interpreter |
| A script cannot be opened | The path or current directory is incorrect | Check the filename, pwd, and dir |
| SyntaxError | Python cannot parse the code | Check spelling, quotation marks, and punctuation |
| IndentationError | Code blocks are indented incorrectly | Use consistent indentation |
| ValueError | A value is invalid for the requested operation | Check the input and its format |
| TypeError | An operation is incompatible with the supplied types | Check data types and convert values where appropriate |

These are common explanations, not exhaustive diagnoses. The complete
error message and surrounding context determine the actual cause.

**17.7.3 Troubleshooting ModuleNotFoundError**

Suppose your program contains:

<img src="CHAPTER 17_media/media/image49.png"
style="width:5.47945in;height:0.31252in" />

But Python displays:

<img src="CHAPTER 17_media/media/image50.png"
style="width:5.54195in;height:0.23612in" />

Follow these steps:

1.  Open the project in VS Code.

2.  Run Python: Select Interpreter.

3.  Select the intended project environment.

4.  Open the integrated terminal.

5.  Check which Python is available:

> <img src="CHAPTER 17_media/media/image51.png"
> style="width:5.16693in;height:0.23612in" />

6.  Check whether NumPy is installed:

> <img src="CHAPTER 17_media/media/image52.png"
> style="width:5.2086in;height:0.20834in" />

7.  If the project requires NumPy and it is missing, install it in the
    correct environment:

> <img src="CHAPTER 17_media/media/image53.png"
> style="width:5.23638in;height:0.20834in" />

8.  Run the program again.

Installing a package into one Python environment does not necessarily
make it available in another.

**17.7.4 Troubleshooting a Script That Does Not Run**

If hello.py does not run:

1.  Confirm that the file has been saved.

2.  Check that its name is hello.py, not hello.py.txt.

3.  Confirm that the terminal is in the correct directory.

4.  Check the selected interpreter.

5.  Run the script manually:

> <img src="CHAPTER 17_media/media/image54.png"
> style="width:5.22944in;height:0.27779in" />

6.  Read any error message.

7.  Correct the problem and try again.

Running a script manually helps distinguish a code problem from an
editor configuration problem.

**17.7.5 Using the VS Code Debugger**

A debugger allows you to pause program execution and inspect what the
program is doing.

A **breakpoint** is a location where execution pauses during a debugging
session.

To use the VS Code debugger:

1.  Open a Python file.

2.  Select the editor margin beside an executable line to set a
    breakpoint.

3.  Open the Run and Debug view or select **Python Debugger: Debug
    Python File**.

4.  Start debugging.

5.  Inspect the variables when execution pauses.

6.  Step through the instructions.

7.  Observe how variable values change.

For example:

<img src="CHAPTER 17_media/media/image55.png"
style="width:5.59057in;height:0.97922in" />

Set a breakpoint on the line calculating total.

When execution pauses, inspect price and quantity, then step through the
multiplication and examine total.

The debugger helps you investigate program state rather than relying
entirely on print statements.

**17.7.6 A Practical Troubleshooting Checklist**

Before asking for technical help, collect the following information:

- Operating system.

- Python version.

- Selected interpreter in VS Code.

- The command you executed.

- The complete error message.

- The relevant portion of your code.

- The steps you have already tried.

Never assume that an installation problem and a programming error are
the same issue. Diagnose them separately.

**17.8 Preparing the Project Workspace**

**17.8.1 Why Project Organization Matters**

A project workspace is the directory containing the files associated
with a project.

Organized workspaces help you:

- Find source code quickly.

- Keep dependencies associated with the correct project.

- Store project documentation.

- Separate source files from output and data.

- Reproduce the development environment more reliably.

**17.8.2 Recommended Folder Structure**

For beginner projects, use a structure similar to the following:

<img src="CHAPTER 17_media/media/image56.png"
style="width:5.56973in;height:1.29868in" />This illustrates the roles of
common project files and folders.

- .venv/ contains the virtual environment.

- main.py contains the main Python program.

- requirements.txt records external dependencies.

- README.md describes the project.

- data/ stores project data when needed.

The data/ directory is optional.

The .venv/ directory should generally not be committed to version
control. It can usually be recreated from the project instructions and
dependency list.

**17.8.3 Creating the Workspace**

You can create the workspace using File Explorer or the terminal.

For example, in PowerShell:

<img src="CHAPTER 17_media/media/image57.png"
style="width:5.52806in;height:0.41669in" />

cd python_practice

Create a virtual environment:

<img src="CHAPTER 17_media/media/image58.png"
style="width:5.45861in;height:0.23612in" />

Create a simple Python file in VS Code and save it as main.py.

Enter:

<img src="CHAPTER 17_media/media/image59.png"
style="width:5.5489in;height:1.23617in" />

Expected output:

<img src="CHAPTER 17_media/media/image60.png"
style="width:5.52806in;height:0.29863in" />

**Explanation**

- main() groups the main instructions into a function.

- if \_\_name\_\_ == "\_\_main\_\_": checks whether the file is being
  executed as the main program.

- main() is called when the condition is true.

This pattern is useful as projects become larger and need clearer
organization.

**17.8.4 Creating a Requirements File**

If your project needs NumPy and Matplotlib, your requirements.txt might
contain:

<img src="CHAPTER 17_media/media/image61.png"
style="width:5.6114in;height:0.44447in" />

Activate the project's virtual environment and install the dependencies:

<img src="CHAPTER 17_media/media/image62.png"
style="width:5.48639in;height:0.21529in" />

For projects that need exact dependency versions, specify the versions
required by the project rather than leaving them unspecified.

**17.8.5 Preparing for Subsequent Mini Projects**

Before starting a mini project, check the following.

**Environment**

- Python is installed.

- The Python version meets the project requirements.

- VS Code is installed.

- The Python extension is available.

- The correct interpreter is selected.

**Workspace**

- The project folder exists.

- The source files are saved in the correct location.

- The virtual environment is created and activated when needed.

- Required packages are installed.

- The dependency list is recorded when appropriate.

**Execution**

- A basic Python file runs successfully.

- Input and output behave as expected.

- Errors can be read and investigated.

- The program can be rerun after changes.

**17.8.6 Final Environment Test**

Use this program to confirm that the selected interpreter can execute
basic Python code.

Save it as environment_test.py:

<img src="CHAPTER 17_media/media/image63.png"
style="width:5.45861in;height:1.91677in" />

Expected output format:

<img src="CHAPTER 17_media/media/image64.png"
style="width:5.59057in;height:0.98616in" />

The exact Python version depends on your installation.

This test uses only the Python standard library and built-in functions.
It does not require external packages.

If the program runs successfully, you have confirmed that your selected
Python interpreter can execute a simple script and display its output.

**17.9 Chapter Summary**

This chapter explained how to prepare a Python programming environment.

| **Concept**             | **Main idea**                                |
|-------------------------|----------------------------------------------|
| Programming environment | Tools used to develop and run programs       |
| Python interpreter      | Software that executes Python code           |
| Code editor             | Software used to write and edit source code  |
| VS Code extension       | Adds Python-specific editor functionality    |
| Terminal                | Interface for running commands               |
| Python script           | A file containing Python instructions        |
| pip                     | A tool for installing Python packages        |
| Package                 | A distributable unit of software             |
| Import                  | Making a module or package available to code |
| Virtual environment     | An isolated Python environment for a project |
| requirements.txt        | A file listing project dependencies          |
| Debugger                | A tool for inspecting program execution      |
| Breakpoint              | A location where debugging pauses execution  |
| Workspace               | The folder containing project files          |

After completing this chapter, you should be able to install and check
Python, configure VS Code, create and run Python files, use the
terminal, install packages, create virtual environments, and
troubleshoot common setup problems.

**17.10 Review Questions, Exercises, and Solutions**

**17.10.1 Multiple-Choice Questions**

1.  Which component executes Python code?

A. Code editor\
B. Python interpreter\
C. File Explorer\
D. README file

2.  Which command checks the Python version on a typical Windows
    installation?

A. python --version\
B. python install\
C. pip --python\
D. version python

3.  What is the main purpose of a virtual environment?

A. To replace VS Code\
B. To convert Python into another language\
C. To isolate project dependencies\
D. To remove Python errors automatically

4.  Which command installs NumPy using the Python interpreter invoked by
    python?

A. python numpy\
B. python -m pip install numpy\
C. install python numpy\
D. pip python numpy

5.  What does a requirements.txt file commonly contain?

A. Only Python source code\
B. A list of project dependencies\
C. The operating system's configuration\
D. Only program output

**Solutions**

1.  **B.** The interpreter executes Python instructions.

2.  **A.** This command requests the Python version.

3.  **C.** Virtual environments help isolate project dependencies.

4.  **B.** The command uses pip through the selected Python interpreter.

5.  **B.** The file records packages required by a project.

**17.10.2 True-or-False Questions**

1.  Installing VS Code automatically guarantees that Python is
    installed.

2.  A Python source file commonly ends with .py.

3.  A virtual environment can help prevent dependency conflicts between
    projects.

4.  Installing a package into one environment guarantees that it is
    available in every Python environment.

5.  The terminal can be used to run Python scripts.

6.  A debugger can help inspect variable values during execution.

**Solutions**

1.  **False.** Python must be installed separately unless it is already
    available through another installation method.

2.  **True.** .py is the conventional extension for Python source files.

3.  **True.** Separate environments isolate project dependencies.

4.  **False.** Packages installed in one environment are not
    automatically available in every other environment.

5.  **True.** The terminal can execute Python commands and scripts.

6.  **True.** Debuggers support inspecting program state during
    execution.

**17.10.3 Short-Answer Questions**

1.  What is the difference between a code editor and a Python
    interpreter?

2.  Why should projects use separate virtual environments?

3.  What is the purpose of pip?

4.  Why might VS Code display ModuleNotFoundError even when a package
    has been installed?

5.  What information should you collect when troubleshooting a Python
    error?

**Solutions**

1.  A code editor helps you write and modify code. A Python interpreter
    executes it.

2.  Separate environments isolate dependencies and help prevent
    incompatible package versions from interfering with one another.

3.  pip installs Python packages into the environment associated with
    the relevant Python installation.

4.  The package may have been installed into a different environment
    from the interpreter selected in VS Code.

5.  Collect the operating system, Python version, selected interpreter,
    command, complete error message, relevant code, and steps already
    attempted.

**17.10.4 Command-Reading Questions**

**Question 1**

What does this command do?

<img src="CHAPTER 17_media/media/image65.png"
style="width:5.5489in;height:0.27085in" />

**Solution**

It requests the version of the Python interpreter available through the
python command.

**Question 2**

What does this command do?

<img src="CHAPTER 17_media/media/image66.png"
style="width:5.52112in;height:0.20834in" />

**Solution**

It runs pip through the Python interpreter invoked by python and asks it
to install NumPy.

**Question 3**

What does this command do?

<img src="CHAPTER 17_media/media/image67.png"
style="width:5.54195in;height:0.25696in" />

**Solution**

It creates a virtual environment in the .venv directory, using the
Python interpreter invoked by python.

**17.10.5 Practical Exercises**

**Exercise 1: Verify Python**

Open a terminal and check your Python version.

**Solution**

Run:

<img src="CHAPTER 17_media/media/image68.png"
style="width:5.58362in;height:0.29168in" />

If the command is unavailable, try:

<img src="CHAPTER 17_media/media/image69.png"
style="width:5.54195in;height:0.22918in" />

Record the version displayed and the command that succeeded.

**Exercise 2: Create and Run a Python File**

Create a file named greeting.py containing:

<img src="CHAPTER 17_media/media/image70.png"
style="width:5.5489in;height:0.48614in" />

Run the file.

**Solution**

Execute:

python greeting.py

If the user enters Alex, the program displays:

<img src="CHAPTER 17_media/media/image71.png"
style="width:5.48639in;height:0.42363in" />

**Exercise 3: Create a Virtual Environment**

Create a virtual environment named .venv inside your project folder.

**Solution**

Run:

<img src="CHAPTER 17_media/media/image72.png"
style="width:5.50723in;height:0.23612in" />

On Windows PowerShell, activate it using:

<img src="CHAPTER 17_media/media/image73.png"
style="width:5.41695in;height:0.27085in" />

Confirm that the environment is active by checking the terminal prompt.

**Exercise 4: Install and Import a Package**

Create a virtual environment, activate it, and install NumPy.

**Solution**

Run:

<img src="CHAPTER 17_media/media/image74.png"
style="width:5.5489in;height:0.27085in" />

Then create a file named numpy_test.py:

<img src="CHAPTER 17_media/media/image75.png"
style="width:5.48639in;height:1.21534in" />

Expected output:

<img src="CHAPTER 17_media/media/image76.png"
style="width:5.52806in;height:0.50697in" />

If the import fails, confirm that the correct virtual environment is
active and selected in VS Code.

**Exercise 5: Troubleshoot a Missing File**

Suppose the terminal displays an error indicating that main.py cannot be
opened.

**Solution**

Check the current directory:

<img src="CHAPTER 17_media/media/image77.png"
style="width:5.50723in;height:0.27779in" />

List its contents:

<img src="CHAPTER 17_media/media/image78.png"
style="width:5.56973in;height:0.25001in" />

If main.py is absent, navigate to the correct project folder or provide
the correct file path. Also confirm the filename and extension.

**17.11 Glossary, Figure Credits, and Further Learning**

**17.11.1 Glossary**

| **Term** | **Definition** |
|----|----|
| Code editor | Software used to write and edit source code |
| Command | An instruction entered into a terminal |
| Dependency | Software required by a project |
| Debugger | A tool for inspecting program execution |
| Environment | The interpreter and associated resources used to run code |
| Interpreter | Software that executes Python code |
| Package | A distributable unit of software |
| Package installation | Making a package available in a Python environment |
| Python extension | VS Code extension that adds Python support |
| Requirements file | A file listing project dependencies |
| Script | A file containing executable instructions |
| Terminal | A command-line interface |
| Virtual environment | An isolated Python environment |
| Workspace | A directory containing project files |

**References**

1.  Python Software Foundation. *Using Python on Windows.* [Official
    Python
    Documentation](https://docs.python.org/3/using/windows.html?utm_source=chatgpt.com)

2.  Microsoft. *Getting Started with Python in VS Code.* [Official VS
    Code
    Documentation](https://code.visualstudio.com/docs/python/python-tutorial?utm_source=chatgpt.com)

3.  Microsoft. *Running Python Code in VS Code.* [Official VS Code
    Documentation](https://code.visualstudio.com/docs/python/run?utm_source=chatgpt.com)

4.  Python Packaging Authority. *Installing Packages.* [Python Packaging
    User
    Guide](https://packaging.python.org/en/latest/tutorials/installing-packages/?utm_source=chatgpt.com)

5.  Python Packaging Authority. *Installing Packages Using pip and
    Virtual Environments.* [Python Packaging User
    Guide](https://packaging.python.org/en/latest/guides/installing-using-pip-and-virtual-environments/)

6.  Microsoft. *Python Debugging in VS Code.* [Official VS Code
    Documentation](https://code.visualstudio.com/docs/python/debugging?utm_source=chatgpt.com)

    **Figure References**

Figure 17.1 - The Python Development Environment:
[https://gsp.humboldt.edu/OLM/Courses/GSP_318/01_4_IntroToPythonInVSC.html](https://gsp.humboldt.edu/OLM/Courses/GSP_318/01_4_IntroToPythonInVSC.html?utm)
