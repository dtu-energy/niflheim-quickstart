# Welcome to Niflheim Quickstart

This website as a gentle introduction for new users of Niflheim. You will learn how to access the resource, submit jobs, monitor your usage, and more. All information can also be found here: <https://wiki.fysik.dtu.dk/Niflheim_users/>

## Description of Niflheim

Niflheim is an HPC cluster. It is a collection of many separate servers (computers), called nodes, which are connected via a fast interconnect. There are different types of nodes for different types of tasks, such as login nodes and compute nodes.

Login nodes are the nodes that you use to access the cluster. They are the gateway to the cluster and provide an interface for you to submit and manage your jobs. You can use login nodes to edit your files, compile your programs, and monitor your jobs. However, you should not run any intensive or long-running computations on login nodes, as they are shared by many users and have limited resources.

Compute nodes are the nodes that actually run your jobs. Compute nodes are organized into partitions, which are groups of nodes with similar characteristics and policies. For example, there may be partitions for different types of CPUs or GPUs, different amounts of memory or storage, different time limits or priorities, etc. You can specify which partition you want to use when you submit your job with the `sbatch` command.

Each compute node partition has a corresponding login node with the same CPU architechture. See details [here](https://wiki.fysik.dtu.dk/Niflheim_users/Niflheim_Getting_Started/#login-to-niflheim).

## Table of Contents

- Quickstart
- Useful Linux Commands
- Useful Slurm Commands
- Useful EasyBuild Commands
- More Resources
