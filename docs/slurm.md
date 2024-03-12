# Submitting jobs with Slurm

This page will introduce you to submitting jobs with Slurm and some of the most useful Slurm commands that you can use on Niflheim. Slurm is a workload manager that allocates resources and schedules jobs on the cluster. You can use Slurm commands to submit, monitor, control, and manage your jobs.

## Slurm Job Script

A Slurm job script is a file that contains the parameters and commands for your job. You can use it to submit your job to the cluster with the `sbatch` command. A Slurm job script usually has two parts: a header and a body. The header contains lines that start with `#SBATCH` and specify the parameters for your job, such as the number of nodes, cores, memory, time, etc. The body contains the commands that you want to run on the allocated nodes, such as loading modules, running programs, copying files, etc.

Here is an example of a Slurm job script that runs a Python script called `hello.py` on one node with 16 cores for 10 minutes:

```bash
#!/bin/bash
#SBATCH --nodes=1
#SBATCH --ntasks-per-node=16
#SBATCH --partition=xeon16
#SBATCH --time=0-00:10:00  # 10 minutes
#SBATCH --job-name=hello
#SBATCH --output=hello.out

module load Python/3.11.3-GCCcore-12.3.0
python hello.py
```

You can save this script as `hello.sh` and submit it to the cluster with this command:

```bash
sbatch hello.sh
```

The body for running a calculation with the AMS package could be:

```bash
# Load the software modules
module use /home/energy/modules/modules/all
module load AMS/2023

# Run the program
ams inputfile
```

See also [how to edit files.](editing-files.md)

If you feel it is too cumbersome to create submit files for `sbatch`, then [`myqueue`](https://myqueue.readthedocs.io/en/latest/) might be something for you.

## Basic Slurm Commands

Here are some basic Slurm commands and their usage:

- `sbatch`: This command submits a job script to the cluster. A job script is a file that contains the parameters and commands for your job. For example, `sbatch hello.sh` will submit the job script `hello.sh` to the cluster. You can also specify some parameters as options in the command line, such as `-N` for number of nodes, `-n` for number of tasks, `-c` for number of cores per task, `-t` for time limit, etc. For example, `sbatch -N 2 -n 4 -c 2 -t 10:00 hello.sh` will submit the job script `hello.sh` with 2 nodes, 4 tasks, 2 cores per task, and 10 minutes time limit. These arguments can also be set with the `#SBATCH` instruction in the `hello.sh` script itself.

- `squeue`: This command shows the status of the jobs in the cluster. For example, `squeue` will show all the jobs in the cluster with their job ID, partition, name, user, state, time, nodes, node list, etc. You can also use options to filter or format the output, such as `-u` for user name, `-p` for partition name, `-o` for output format, etc. For example, `squeue -u user` will show only the jobs submitted by user `user`, while `squeue -o "%i %j %T"` will show only the job ID, name, and state of each job.

- `scancel`: This command cancels a job or a group of jobs in the cluster. For example, `scancel 123456` will cancel the job with ID 123456. You can also use options to specify criteria for cancelling jobs, such as `-u` for user name, `-p` for partition name, `-t` for job state, etc. For example, `scancel -u user -t PENDING` will cancel all the pending jobs submitted by user `user`.

<!-- - `sinfo`: This command shows the status of the partitions and nodes in the cluster. For example, `sinfo` will show all the partitions and nodes in the cluster with their name, size, state, time limit, nodes, node list, etc. You can also use options to filter or format the output, such as `-p` for partition name, `-N` for node name, `-o` for output format, etc. For example, `sinfo -p batch -N -o "%n %T %C"` will show only the node name, state, and CPU allocation of each node in the batch partition. -->

<!-- - `srun`: This command runs a command or a program on a set of allocated nodes in the cluster. For example, `srun hostname` will run the hostname command on each allocated node and print the output. You can also use options to specify parameters for your job, such as `-N` for number of nodes, `-n` for number of tasks, `-c` for number of cores per task, `-t` for time limit, etc. For example, `srun -N 2 -n 4 -c 2 -t 10:00 python hello.py` will run the python script `hello.py` on 2 nodes with 4 tasks and 2 cores per task for 10 minutes. -->

## Other references
- [Niflheim wiki - Submitting batch jobs to Niflheim](https://wiki.fysik.dtu.dk/Niflheim_users/Niflheim_Getting_Started/#submitting-batch-jobs-to-niflheim)
- [Slurm Workload Manager - Slurm Tutorials - SchedMD](https://slurm.schedmd.com/tutorials.html)
- [A simple Slurm guide for beginners - RONIN BLOG](https://blog.ronin.cloud/slurm-intro/)
- [Slurm Tutorial - Gowda](https://gowda.ai/slurm101/)
- [Slurm Workload Manager - Quick Start User Guide - SchedMD](https://slurm.schedmd.com/quickstart.html)

## Slurm helper scripts

Just to highlight the highly useful [Slurm tools](https://github.com/OleHolmNielsen/Slurm_tools/) written by the system administrator of Niflheim:

- `showpartitions`: Show the load of the cluster, how many jobs are in queue for the different partitions. Available nodes are shown in green.

- `showuserjobs`: List the running and queued jobs per user.

- `pestat`: List the status of nodes running jobs. `pestat -u $USER` will show your running jobs. Badly behaving jobs are highlighted in red.


