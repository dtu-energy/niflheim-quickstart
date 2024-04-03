# Welcome to Niflheim Quickstart

These pages should act as a gentle introduction for new users of Niflheim. You will learn how to access the resource, submit jobs, monitor your usage, and more. All information can also be found here: <https://wiki.fysik.dtu.dk/Niflheim_users/>

## What is an HPC cluster?

Niflheim is an HPC cluster. It is a collection of many separate servers (computers), called nodes, which are connected via a fast interconnect. There are different types of nodes for different types of tasks, such as login nodes and compute nodes.

Login nodes are the nodes that you use to access the cluster. They are the gateway to the cluster and provide an interface for you to submit and manage your jobs. You can use login nodes to edit your files, compile your programs, and monitor your jobs. However, you should not run any intensive or long-running computations on login nodes, as they are shared by many users and have limited resources.

Compute nodes are the nodes that actually run your jobs. Compute nodes are organized into partitions, which are groups of nodes with similar characteristics and policies. For example, there may be partitions for different types of CPUs or GPUs, different amounts of memory or storage, different time limits or priorities, etc. You can specify which partition you want to use when you submit your job with the `sbatch` command.

Each compute node partition has a corresponding login node with the same CPU architechture. See details [here](https://wiki.fysik.dtu.dk/Niflheim_users/Niflheim_Getting_Started/#login-to-niflheim).

## Some rules on Niflheim

- Don't run real calculations on the login nodes, those should go to the compute nodes in batch jobs.
- Use all the CPUs of the compute nodes. Don't submit jobs that cannot run in parallel to other partitions than `xeon24`. In situations where parallelization cannot be achieved and `xeon24` does not suffice, contact the support. *NB* The partitions `xeon24`, `sm3090el8`, `a100` and `xeon32_4096` allow for jobs that don't use a full node.

## Get started

Go to [Quickstart](quickstart.md)
