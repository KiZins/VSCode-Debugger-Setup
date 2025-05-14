# VSCode Python Debugger Setup  :snake:
Instructions and configuration files for setting up the Python debugger in VSCode

## Table Of Contents

- [Getting Started](#getting-started)
    - [Prerequisites](#prerequisites)
    - [Installation](#installation)
- [Configurations](#configurations)
    - [Script Debugger](#script-debugger)
    - [Notebook Debugger](#notebook-debugger)
    - [Remote Debugger](#remote-debugger)

## Getting Started

### Prerequisites
Have the following programs installed before continuing:
| Requirement                             | Installation                         |
| --------------------------------------- | ------------------------------------ |
| VSCode                                  | https://code.visualstudio.com/download      |
| Miniconda (Optional)                    | https://www.anaconda.com/docs/getting-started/miniconda/install#quickstart-install-instructions |
| Colab Pro (Optional)                    | - |

### Installation
The Python Debugger is included with the official Python extension for VS Code.  
Verify its installation by:

Opening the Extension tab (`Ctrl+Shift+X`)
<!-- ![VSCode Terminal Highlighting Extensions Tab](img/extension_tab.png) -->
<!-- Better formatting in my opinion-->
<p align="center">
  <img src="img/extension_tab.png" alt="VSCode Extension Tab" width="1000"/>
</p>

Searching for `Python Debugger` in the searchbar

<!-- ![VSCode Terminal Highlighting Search Box in Extensions Tab](img/search_extensions.png) -->
<p align="center">
  <img src="img/search_extensions.png" alt="VSCode Extension Tab Search" width="950"/>
</p>

Verify that the Python Debugger extension has been installed 

<!-- ![VSCode Terminal Highlighting Python Debugger Extension](img/python_debugger_extension.png) -->
<p align="center">
  <img src="img/python_debugger_extension.png" alt="VSCode Extension Tab Debugger" width="950"/>
</p>


## Configurations
The VSCode debugger lets you set breakpoints, step through code, inspect variables, and interactivly test functions similar to a Jupyter notebook.  Before diving into specific configurations used in this class, let's cover how the debugger is setup and managed.  

1. Navigate to the Run and Debug tab on the sidebar - shortcut (Ctrl+Shift+D):
<!-- ![VSCode Terminal Highlighting Run and Debug Tab](img/run_debug_tab.png.png) -->
<p align="center">
  <img src="img/run_debug_tab.png" alt="Highlight Run and Debug Tab" width="950"/>
</p>

2. 


#### What is `Launch.json`
Configurations used by the debugger are defined in `launch.json` file and stored in the current working directory under the `.vscode` folder. 


### Script Debugger
This section covers creating a launch.json file to run the debugger on training and grader scripts.  
python -m homework.train --model_name linear
or
python -m 



<!-- ![VSCode Terminal Highlighting launch json](img/create_launch_json.png) -->
<p align="center">
  <img src="img/create_launch_json.png" alt="Highlight create json" width="950"/>
</p>


<!-- ![VSCode Terminal Debugger Selection](img/debugger_setup_1.png) -->
<p align="center">
  <img src="img/debugger_setup_1.png" alt="Python Debugger Selection" width="950"/>
</p>


<!-- ![VSCode Terminal Python Debugger on Module](img/debugger_setup_2.png) -->
<p align="center">
  <img src="img/debugger_setup_2.png" alt="Python Debugger on Module" width="950"/>
</p>

<!-- ![VSCode Terminal Python Debugger Module Naming](img/debugger_setup_3.png) -->
<p align="center">
  <img src="img/debugger_setup_3.png" alt="Python Debugger Module Naming" width="950"/>
</p>

<!-- ![VSCode Terminal Python Debugger folder](img/debugger_setup_3.png) -->
<p align="center">
  <img src="img/debugger_setup_3.png" alt="Python Debugger Module Naming" width="950"/>
</p>




### Notebook Debugger
### Remote Debugger

## Troubleshooting


