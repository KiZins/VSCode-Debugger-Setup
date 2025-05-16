# VSCode Python Debugger Setup  :snake:
Instructions and configuration files for setting up the Python debugger in VSCode.

## Table Of Contents

- [Getting Started](#getting-started)
    - [Prerequisites](#prerequisites)
    - [Installation](#installation)
- [Configurations](#configurations)
    - [What is launch.json](#what-is-launchjson)
    - [Creating a launch.json](#creating-a-launchjson)
    - [Useful Configurations](#useful-configurations)
    - [Enabling Break Points](#enabling-break-points)
    - [Running the Debugger](#running-the-debugger)
- [Notebook Debugging](#notebook-debugging)

## Getting Started

### Prerequisites
Have the following programs installed before continuing:
| Requirement                             | Installation                         |
| --------------------------------------- | ------------------------------------ |
| VSCode                                  | https://code.visualstudio.com/download      |
| Miniconda (Optional)                    | https://www.anaconda.com/docs/getting-started/miniconda/install#quickstart-install-instructions |

### Installation
The Python Debugger is included with the official Python extension for VS Code, but it is important to verify its installation.

Open the Extension tab (`Ctrl+Shift+X`) located on the left sidebar.
<!-- ![VSCode Terminal Highlighting Extensions Tab](img/extension_tab.png) -->
<!-- Better formatting in my opinion-->
<p align="center">
  <img src="img/extension_tab.png" alt="VSCode Extension Tab" width="950"/>
</p>

Type `Python Debugger` in the searchbar.

<!-- ![VSCode Terminal Highlighting Search Box in Extensions Tab](img/search_extensions.png) -->
<p align="center">
  <img src="img/search_extensions.png" alt="VSCode Extension Tab Search" width="450"/>
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
  <img src="img/run_debug_tab.png" alt="Highlight Run and Debug Tab" width="450"/>
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
| [module](https://code.visualstudio.com/docs/python/debugging#_module)                    | Specifies the module to run and it is like using `python -m folder.file`.|
| [args](https://code.visualstudio.com/docs/python/debugging#_args)                    | List of command line arguments passed to the script. |
| [console](https://code.visualstudio.com/docs/python/debugging#_console)                    | Optional: Specifies where to display program outputs.  The default is `integratedterminal`. |


### Creating a `launch.json`
> [!IMPORTANT]
> Ensure that the current working directory is set to the Homework1 folder.  This can be done by opening the Explorer tab (`Ctrl+Shift+E`) and verifying that Homework1 appears as the top-level folder.


<!-- ![VSCode Terminal Showing the Explorer Tab with HW1](img/explorer_tab_hw1.png) -->
<p align="center">
  <img src="img/explorer_tab_hw1.png" alt="VSCode Terminal Showing the Explorer Tab with HW1", width="450"/>
</p>



Navigate to the Run and Debug tab (`Ctrl+Shift+D`) and click the `create a launch.json file`.


<!--  ![Run and Debug Tab with Highlight on Create Button](img/launch_json.png) -->
<p align="center">
  <img src="img/launch_json.png" alt="Run and Debug Tab with Highlight on Create Button", width="450"/>
</p>

A pop-up menu will appear under the Command Palette that lists installed debuggers.
<!--  ![VSCode Terminal Highlighting Command Palette](img/launch_json_step_1.png) -->
<p align="center">
  <img src="img/launch_json_step_1.png" alt="VSCode Terminal Highlighting Command Palette", width="950"/>
</p>

Select `Python Debugger` to configure the debugger's type to `debugpy`.
<!--  ![VSCode Command Palette Highlighting Python Debug](img/launch_json_step_2.png) -->
<p align="center">
  <img src="img/launch_json_step_2.png" alt="VSCode Command Palette Highlighting Python Debug", width="450"/>
</p>


Set the debug configuration to `Module`.
<!--  ![VSCode Command Palette Highlighting Python Debug Module](img/launch_json_step_3.png) -->
<p align="center">
  <img src="img/launch_json_step_3.png" alt="VSCode Command Palette Highlighting Python Debug Module", width="450"/>
</p>

Replace `enter-your-your-module-name` with the name of the module you will be running.  For this class, we will mostly be working with the  `grader` or `homework.train` modules.
<!--  ![VSCode Command Palette Highlighting Python Debug Module Naming](img/launch_json_step_5.png) -->
<p align="center">
  <img src="img/launch_json_step_5.png" alt="VSCode Command Palette Highlighting Python Debug Module Naming", width="450"/>
</p>

Return to the Explorer tab (`Ctrl+Shift+E`) and verify the `.vscode` folder was added to the top-level directory.
<!--  ![VSCode Terminal Showing the Explorer Tab with HW1 and VSCode Folder](img/explorer_tab_launch.png) -->
<p align="center">
  <img src="img/explorer_tab_launch.png" alt="VSCode Terminal Showing the Explorer Tab with HW1 and VSCode Folder", width="450"/>
</p>



### Useful Configurations
<details>

<summary>Python Debugger: Grader</summary>

```json
{
    "name": "Python Debugger: Grader",
    "type": "debugpy",
    "request": "launch",
    "module": "grader",
    "args": ["homework"]
}
```
</details>

<details>

<summary>Python Debugger: Grader Verbose</summary>

```json
{
    "name": "Python Debugger: Grader Verbose",
    "type": "debugpy",
    "request": "launch",
    "module": "grader",
    "args": ["homework", "-v"]
}
```
</details>

<details>
<summary>Python Debugger: Grader Very Verbose</summary>

```json
{
    "name": "Python Debugger: Grader Very Verbose",
    "type": "debugpy",
    "request": "launch",
    "module": "grader",
    "args": ["homework", "-vv"]
}
```
</details>




<details>
<summary>Python Debugger: Train Script</summary>

```json
{
    "name": "Python Debugger: Train Script",
    "type": "debugpy",
    "request": "launch",
    "module": "homework.train",
    "args": ["--model_name", "linear", "--num_epoch", "10"]
}
```
</details>

<details>
<summary>Python Debugger: Multiple Configurations Example</summary>

```json
{
    "version": "0.2.0",
    "configurations": [

        {
            "name": "Python Debugger: Grader",
            "type": "debugpy",
            "request": "launch",
            "module": "grader",
            "args": ["homework"]
        },
        {
            "name": "Python Debugger: Train Script",
            "type": "debugpy",
            "request": "launch",
            "module": "homework.train",
            "args": ["--model_name", "linear", "--num_epoch", "10"]
        },
    ],
}
```

Use the dropdown menu next to the Run button to change configurations.
<!--  ![Run and Debug Tab with Highlight on Changing Configs](img/multiple_configs.png) -->
<p align="center">
  <img src="img/multiple_configs.png" alt="Run and Debug Tab with Highlight on Changing Configs", width="450"/>
</p>


</details>

### Enabling Break Points
Click on the editor margin (space to the left of line number) to add or remove breakpoints.  Alternatively, use `F9` to add or remove a breakpoint on the current line.

<!-- ![VSCode Adding a Breakpoint](img/breakpoint.png) -->
<p align="center">
  <img src="img/breakpoint.png" alt="VSCode Adding a Breakpoint" width="950"/>
</p>

> [!NOTE]  
> There are more advanced breakpoint that can be set by right-clicking on the editor margin.  Refer to the [documentation](https://code.visualstudio.com/docs/debugtest/debugging#_breakpoint-types) for more details.

> [!Warning]
> Breakpoints will be ignored if the debugger encounters a `raise NotImplementedError` line of code before reaching the desired breakpoint.


### Running the Debugger
Click the Run Button or press `F5` on the keyboard to run the debugger.
<!-- ![VSCode Running the Debugger](img/run_debugger.png) -->
<p align="center">
  <img src="img/run_debugger.png" alt="VSCode Running the Debugger" width="450"/>
</p>

A Debug toolbar will appear near the top of the screen.
<!-- ![VSCode Debug Toolbar](img/debug_step_1.png) -->
<p align="center">
  <img src="img/debug_step_1.png" alt="VSCode Debug Toolbar" width="950"/>
</p>


<p align="center">
  <img src="img/debug_step_2.png" alt="VSCode Debug Toolbar" width="950"/>
</p>

<p align="center">
  <img src="img/debug_step_3.png" alt="VSCode Debug Toolbar" width="950"/>
</p>

> [!NOTE]  
> Refer to [Debug Actions](https://code.visualstudio.com/docs/debugtest/debugging#_debug-actions) if it is your first time using a debugger to find out what each button in the toolbar does.  


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


