
# CONDA <!-- omit in toc -->

This is a guide for **conda** commands.
<!-- --><br/>

> **Notes:**
>
>> No installation instructions are given here.
>> For that, see the official [Installation][install] Guide.

<!-- --><br/>

------------------------------------

### TABLE OF CONTENT

- [TABLE OF CONTENT](#table-of-content)
- [TERMINOLOGY](#terminology)
- [REFERENCE](#reference)
- [HELP](#help)
- [ENVIRONMENTS](#environments)
- [PACKAGES](#packages)
  - [Conda-forge](#conda-forge)
- [UPDATES](#updates)
- [JUPYTER](#jupyter)
- [MISC](#misc)

<!-- --><br/>


- [Generate a Table of Content from a Markdown file][Table of Content]
<!-- --><br/>



------------------------------------

### TERMINOLOGY



| Term/Expression | Meaning |
| --------------: | :------ |
| `<description>` | To replace, or that will be replaced, according to description (without the `<` and `>`). |
| `$`             | Some command to be used on the Terminal (shell) |
| `(<env>)$`      | Some Terminal command to be used on a specific environment |



------------------------------------

### REFERENCE

- [Installation][install]

- [Moving Anaconda from one directory to another][moving]

- [Documentation][conda]

- [Conda Forge][conda]

<!-- --><br/>



[install]:https://docs.anaconda.com/anaconda/install/ "Anaconda/Conda Installation"
[moving]:https://docs.anaconda.com/anaconda/user-guide/tasks/move-directory/
[conda]:https://docs.conda.io/projects/conda/en/latest/index.html "Conda Documentation"
[conda-forge]:https://conda-forge.org/feedstock-outputs/ "Packages on Conda Forge"
[non-conda-forge]:https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-pkgs.html#installing-non-conda-packages "Installing non-conda packages"

------------------------------------

### HELP

- Help on a command:

```shell
$ conda <command> --help
```
<!-- --><br/>


- Info:

```shell
$ conda info
```
<!-- --><br/>


- Open Anaconda Navigator:

```shell
$ anaconda-navigator
```
<!-- --><br/>



------------------------------------

### ENVIRONMENTS

- List environments:

```shell
$ conda env list
```
```shell
$ conda info --envs
```
<!-- --><br/>


- Activate/deactivate environment (conda>=4.6):

```shell
$ conda activate <environment>
```
```shell
(<env>)$ conda deactivate <environment>
```
<!-- --><br/>


- Create environment:

```shell
$ conda create --name <env-name>
```
```shell
$ conda create -n <env-name> python=<version>
```
<!-- --><br/>


- Create environment with specific package:

```shell
$ conda create -n <env-name> <package>
```
```shell
$ conda create -n <env-name> <package>=<pack-version>
```
<!-- --><br/>


- Cloning a environment:

```shell
$ conda create -n <new-env> --clone <old-env> 
```
```shell
$ conda create -n <new-env> --clone <old-env> --offline
```
<!-- --><br/>


- Removing a environment:

```shell
$ conda env remove --name <env-name>
```
<!-- --><br/>


- Exporting environment.yml:

```shell
(<env>)$ conda env export > environment.yml
```
<!-- --><br/>


- Creating an environment from a environment.yml:

```shell
$ conda env create -f environment.yml
```
```shell
$ conda env create -f environment.yml -n <env-name>
```
<!-- --><br/>



------------------------------------

### PACKAGES

> :warning: **WARNING** _(for Arch Linux)_ **:**
>
>> DO NOT run `pip install <module>` on TERMINAL.
>> You should never make any changes to `/usr`, except through `pacman`.
>> If a package isn´t available by conda, try [Conda Forge][conda-forge] before even thinking on pip.
>> If you need to install with `pip` do it in a Virtual environment or use `pip install --user <package>` to install on the user install directory (typically `~/.local/lib/`).
>> For more info see [this][non-conda-forge].
>
> **TL;DR :**
>> Basically, never use `pip`.
>> Use `conda` on Virtual environment.
>> Use `pacman` (or your package manager) on the system.
>
<!-- --><br/>


- Install packages on current env:

```shell
(<env>)$ conda install <package>
```
```shell
(<env>)$ conda install <package>=<version>
```
<!-- --><br/>


- Install packages on other env:

```shell
$ conda install <package> -n <env>
```
<!-- --><br/>


- Remove a packages:

```shell
(<env>)$ conda remove <package>
```
```shell
$ conda remove <package> -n <env>
```
<!-- --><br/>


- Search package:

```shell
$ conda search <package>
```
<!-- --><br/>


- Search package info:

```shell
$ conda search <package> --info
```
<!-- --><br/>


- List installed package:

```shell
(<env>)$ conda list
```

```shell
(<env>)$ conda list <package>
```
<!-- --><br/>
<!-- --><br/>


#### Conda-forge


- Search package on the channel conda-forge:

```shell
$ conda search <package> --channel conda-forge
```

```shell
$ conda search <package> -c conda-forge
```
<!-- --><br/>


- Install packages from the channel conda-forge:

```shell
(<env>)$ conda install <package> -c conda-forge
```
<!-- --><br/>



------------------------------------

### UPDATES

- Check available updates:

```shell
$ conda update
```
<!-- --><br/>


- Update a package:

```shell
$ conda update <package>
```
```shell
$ conda update python
```
```shell
$ conda update conda
```
```shell
$ conda update anaconda
```
<!-- --><br/>


- Update all packages on environment:

```shell
(<env>)$ conda update --all
```
<!-- --><br/>



------------------------------------

### JUPYTER

- Open jupyter:

```shell
(<env>)$ jupyter notebook
```
```shell
(<env>)$ jupyter notebook <file.ipynb>
```
```shell
(<env>)$ jupyper lab
```
```shell
(<env>)$ jupyper lab <file.ipynb>
```
<!-- --><br/>


- List running Jupyter servers:

```shell
(<env>)$ jupyter notebook list
```
<!-- --><br/>


- Terminate Jupyter server:

```shell
(<env>)$ jupyter notebook stop
```
```shell
(<env>)$ jupyter notebook stop <port>
```
<!-- --><br/>


- Jupyter shortcuts (when a cell is selected):

| ShortCut | Meaning |
| :---: | :--- |
| [shift] + [Enter] | Run cell & go to the next |
| [ctrl] + [Enter]  | Run cell & DON´T go next |
| [alt] + [Enter]   | Run cell, add new cell under & go to it |
| [d] + [d]         | Delete selected cell |
<!-- --><br/>



------------------------------------

### MISC

- Finding anaconda's install directory:

```shell
$ which conda
```
<!-- --><br/>


- Finding the anaconda´s python interpreter (environmental):

```shell
(<env>)$ which python
```
<!-- --><br/>



------------------------------------



------------------------------------



------------------------------------



------------------------------------



