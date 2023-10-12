# How to load software on Niflheim

## What are software modules?

Software modules are a way of managing the availability and configuration of different software packages on a shared computing system. Software packages are collections of programs, libraries, and data that perform specific tasks or functions. For example, Python is a software package that provides a programming language and various libraries for scientific computing, data analysis, web development, etc.

On a shared computing system, such as a cluster, there may be many different software packages installed for different users and purposes. However, not all of them may be compatible with each other or with the system environment. For example, some software packages may require different versions of the same library or different compilers or interpreters. Some software packages may also have different settings or options that affect their behavior or performance.

To avoid conflicts and errors, software modules provide a way of controlling which software packages are available and properly configured for each user and session. Software modules are files that contain information and commands for setting up the environment variables, paths, libraries, options, etc. for a specific software package. By loading and unloading software modules, you can dynamically change the availability and configuration of different software packages on the cluster.

## module commands

<!-- Lmod is a tool that allows you to load, unload, list, and switch between different software modules on the cluster. Lmod is based on Lua, a scripting language that is easy to read and write. Lmod can read both Tcl and Lua module files, which are the two most common formats for writing software modules. -->

<!-- Lmod provides a command called `module` that you can use to interact with software modules on the cluster. You can use `module` with various subcommands and options to perform different actions, such as: -->

- `module avail`: This subcommand shows the available software modules that you can load on the cluster. 

<!-- You can also use options to filter or sort the output, such as `-t` for terse output, `-r` for reverse order, `-d` for default modules, etc. -->
- `module load`: This subcommand loads one or more software modules into your current session. For example, `module load Python/3.11.3-GCCcore-12.3.0` will load the Python 3.11 module into your current session.
<!-- You can also use options to specify dependencies or conflicts between modules, such as `--after`, `--before`, `--conflict`, etc. -->
<!-- - `module unload`: This subcommand unloads one or more software modules from your current session. For example, `module unload python/3.9` will unload the Python 3.9 module from your current session. You can also use options to specify dependencies or conflicts between modules, such as `--after`, `--before`, `--conflict`, etc. -->

- `module use`: The module use command is a way of adding or removing directories to or from the module search path. The module search path is a list of directories that the module command looks for module files. To make available modules installed by DTU Energy do:

```bash
module use /home/modules/energy/modules/all
module use /home/energy/modules/modules/all
```

*Note* that after adding directories to the search path you can do `module avail` to see which modules were made available.

<!-- By default, the module search path includes some system-wide directories that contain the shared module files. However, you can also add your own directories that contain your custom or private module files. For example, `module use /home/user/mymodules` adds a directory named /home/user/mymodules to the module search path.  -->

- `module list`: This subcommand shows the loaded software modules in your current session.
<!-- - `module swap`: This subcommand swaps one or more loaded software modules with one or more available software modules in your current session. For example: `module swap python/3.9 python/2.7` will swap the Python 3.9 module with the Python 2.7 module in your current session. You can also use options to specify dependencies or conflicts between modules, such as `--after`, `--before`, `--conflict`, etc. -->
- `module purge`: This subcommand unloads all the loaded software modules from your current session. For example, `module purge` will unload all the software modules from your current session.
<!-- You can also use options to specify exceptions or dependencies, such as `--except`, `--force`, etc. -->
<!-- - `module save`: This subcommand saves the current list of loaded software modules as a collection that you can restore later. For example, `module save mycollection` will save the current list of loaded software modules as a collection named `mycollection`. You can also use options to specify a description or a default collection, such as `-d` for description, `-D` for default, etc. -->
<!-- - `module restore`: This subcommand restores a previously saved collection of software modules. For example, `module restore mycollection` will restore the collection of software modules named `mycollection`. You can also use options to specify a default collection or a system collection, such as `-D` for default, `-S` for system, etc. -->
