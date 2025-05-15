# VSCode Python Debugger Setup  :snake:
Instructions and configuration files for setting up the Python debugger in VSCode.

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

### Installation
The Python Debugger is included with the official Python extension for VS Code, but it is still important to verify its installation.

Open the Extension tab (`Ctrl+Shift+X`) located on the left sidebar.
<!-- ![VSCode Terminal Highlighting Extensions Tab](img/extension_tab.png) -->
<!-- Better formatting in my opinion-->
<p align="center">
  <img src="img/extension_tab.png" alt="VSCode Extension Tab" width="1000"/>
</p>

Type `Python Debugger` in the searchbar.

<!-- ![VSCode Terminal Highlighting Search Box in Extensions Tab](img/search_extensions.png) -->
<p align="center">
  <img src="img/search_extensions.png" alt="VSCode Extension Tab Search" width="950"/>
</p>

Verify that the Python Debugger extension has been installed .

<!-- ![VSCode Terminal Highlighting Python Debugger Extension](img/python_debugger_extension.png) -->
<p align="center">
  <img src="img/python_debugger_extension.png" alt="VSCode Extension Tab Debugger" width="950"/>
</p>


## Configurations
The VSCode debugger lets you set breakpoints, step through code, inspect variables, and interactivly test functions similar to a Jupyter notebook.  Before diving into specific configurations used in this class, let's cover how the debugger is setup and managed.  

Open the Run and Debug tab (`Ctrl+Shift+D`) located on the left sidebar.
<!-- ![VSCode Terminal Highlighting Run and Debug Tab](img/run_debug_tab.png.png) -->
<p align="center">
  <img src="img/run_debug_tab.png" alt="Highlight Run and Debug Tab" width="950"/>
</p>


> [!NOTE]  
> The Run and Debug tab will initially ask for you to create a `launch.json` file before using the debugger, as shown above.  However, this screen will look different the working directory already has a `launch.json` file



### What is `Launch.json`
The `launch.json` file defines the configuration used by the VSCode debugger.  The `launch.json` file is located in the `.vscode` folder within the current working directory.

Below is an example configuration for running a Python module with arguments: 
```json
{
    "name": "Example Debugger Config",
    "type": "debugpy",
    "request": "launch",
    "module": "folder.file",
    "args": ["arg1", "arg2", ... , "argN-1","argN"]
}
```

| Field                             | Description                         |
| --------------------------------------- | ------------------------------------ |
| [name](https://code.visualstudio.com/docs/python/debugging#_name)                                 | Display name for the configuration shown in the VSCodeUI     |
| [type](https://code.visualstudio.com/docs/python/debugging#_type)                   | Specifies the type of debugger.  Use `debugpy` for Python debugging.|
| [request](https://code.visualstudio.com/docs/python/debugging#_request)                    | Indicates how to start debugging. Use `launch` to run a script. |
| [module](https://code.visualstudio.com/docs/python/debugging#_module)                    | Specifies the module to run like using `python -m folder.file`.|
| [args](https://code.visualstudio.com/docs/python/debugging#_args)                    | List of command line arguements passed to the script. |
| [console](https://code.visualstudio.com/docs/python/debugging#_console)                    | Optional: Specifies where to display program output.  The default is `integratedterminal`. |


### Creating a `launch.json`
> [!IMPORTANT]
> Ensure that the current working directory is set to the Homework1 folder.  This can be done by opening the Explorer tab (`Ctrl+Shift+E`) and verifing that Homework1 appears as the top-level folder.


<!-- ![VSCode Terminal Showing the Explorer Tab with HW1](img/explorer_tab_hw1.png) -->
<p align="center">
  <img src="img/explorer_tab_hw1.png" alt="VSCode Terminal Showing the Explorer Tab with HW1", width="450"/>
</p>



Navigate to the Run and Debug tab (`Ctrl+Shift+D`) and click `create a launch.json file` link to begin the process of adding a configuration file.


<!--  ![Run and Debug Tab with Highlight on Create Button](img/launch_json.png) -->
<p align="center">
  <img src="img/launch_json.png" alt="Run and Debug Tab with Highlight on Create Button", width="450"/>
</p>





Return to the Explorer tab (`Ctrl+Shift+E`) and verify the `.vscode` folder was added to the top-level directory.
<!--  ![VSCode Terminal Showing the Explorer Tab with HW1 and VSCode Folder](img/explorer_tab_launch.png) -->
<p align="center">
  <img src="img/explorer_tab_launch.png" alt="VSCode Terminal Showing the Explorer Tab with HW1 and VSCode Folder", width="450"/>
</p>


### Useful Configurations
Common 

### Enabling Break Points

### Running the Debugger


## Notebook Debugging





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


