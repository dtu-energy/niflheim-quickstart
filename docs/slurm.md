# Most Useful Slurm Commands

This page will introduce you to some of the most useful Slurm commands that you can use on the hpc resource. Slurm is a workload manager that allocates resources and schedules jobs on the cluster. You can use Slurm commands to submit, monitor, control, and manage your jobs.

## Basic Slurm Commands

Here are some basic Slurm commands and their usage:

- `sbatch`: This command submits a job script to the cluster. A job script is a file that contains the parameters and commands for your job. For example, `sbatch hello.sh` will submit the job script `hello.sh` to the cluster. You can also specify some parameters as options in the command line, such as `-N` for number of nodes, `-n` for number of tasks, `-c` for number of cores per task, `-t` for time limit, etc. For example, `sbatch -N 2 -n 4 -c 2 -t 10:00 hello.sh` will submit the job script `hello.sh` with 2 nodes, 4 tasks, 2 cores per task, and 10 minutes time limit.

- `squeue`: This command shows the status of the jobs in the cluster. For example, `squeue` will show all the jobs in the cluster with their job ID, partition, name, user, state, time, nodes, node list, etc. You can also use options to filter or format the output, such as `-u` for user name, `-p` for partition name, `-o` for output format, etc. For example, `squeue -u user` will show only the jobs submitted by user `user`, while `squeue -o "%i %j %T"` will show only the job ID, name, and state of each job.

- `scancel`: This command cancels a job or a group of jobs in the cluster. For example, `scancel 123456` will cancel the job with ID 123456. You can also use options to specify criteria for cancelling jobs, such as `-u` for user name, `-p` for partition name, `-t` for job state, etc. For example, `scancel -u user -t PENDING` will cancel all the pending jobs submitted by user `user`.

- `scontrol`: This command allows you to view or modify the configuration and status of the cluster and its components. For example, `scontrol show node node01` will show detailed information about node01, such as its state, CPU load, memory usage, features, etc. You can also use options to perform actions on the cluster and its components, such as `-o` for one-line output format, `-h` for help message, etc. For example, `scontrol update NodeName=node01 State=DOWN Reason=maintenance` will set node01 to down state with a reason of maintenance.

- `sinfo`: This command shows the status of the partitions and nodes in the cluster. For example, `sinfo` will show all the partitions and nodes in the cluster with their name, size, state, time limit, nodes, node list, etc. You can also use options to filter or format the output, such as `-p` for partition name, `-N` for node name, `-o` for output format, etc. For example, `sinfo -p batch -N -o "%n %T %C"` will show only the node name, state, and CPU allocation of each node in the batch partition.

- `srun`: This command runs a command or a program on a set of allocated nodes in the cluster. For example, `srun hostname` will run the hostname command on each allocated node and print the output. You can also use options to specify parameters for your job, such as `-N` for number of nodes, `-n` for number of tasks, `-c` for number of cores per task, `-t` for time limit, etc. For example, `srun -N 2 -n 4 -c 2 -t 10:00 python hello.py` will run the python script `hello.py` on 2 nodes with 4 tasks and 2 cores per task for 10 minutes.

- `salloc`: This command allocates resources from the cluster for an interactive session. For example, `salloc -N 2 -n 4 -c 2 -t 10:00` will allocate 2 nodes with 4 tasks and 2 cores per task for 10 minutes and give you a shell prompt on one of the allocated nodes. You can then use `srun` or other commands to run programs on the allocated nodes.

- `sinteractive`: This command is similar to `salloc`, but it also creates an interactive session on one of the allocated nodes with X11 forwarding enabled. This allows you to run graphical applications on the cluster and display them on your local machine. For example, `sinteractive -N 2 -n 4 -c 2 -t 10:00` will allocate 2 nodes with 4 tasks and 2 cores per task for 10 minutes and give you an interactive session on one of the allocated nodes. You can then use `srun` or other commands to run graphical programs on the allocated nodes and see them on your local machine.

## Advanced Slurm Commands

Here are some advanced Slurm commands and their usage:

- `sreport`: This command generates reports on various aspects of the cluster usage and performance. For example, `sreport cluster AccountUtilizationByUser start=2023-01-01 end=2023-01-31` will generate a report on how much CPU time each user has used in each account in January 2023. You can also use options to specify different report types, time periods, formats, etc. For example, `sreport job SizesByAccount accounts=user1,user2 format=Account,MinCPUs%20,AveCPUs%20,MaxCPUs%20 start=2023-01-01 end=2023-01-31` will generate a report on the minimum, average, and maximum number of CPUs used by each job in user1 and user2 accounts in January 2023.

- `sacct`: This command shows accounting information for jobs or job steps in the cluster. For example, `sacct --format=JobID%15,CPUTimeRaw%15,CPUTime%15,AveCPU%15 --allusers --starttime=2023-01-01 --endtime=2023-01-31` will show the job ID, CPU time in seconds, CPU time in HH:MM:SS format, and average CPU time per core for all users' jobs in January 2023. You can also use options to filter or format the output, such as `--user`, `--partition`, `--state`, etc.

- `sview`: This command shows a graphical user interface for viewing and managing the cluster and its components. For example, `sview` will launch a GUI window that shows the partitions, nodes, jobs, reservations, etc. in the cluster. You can also use options to specify different views, filters, commands, etc.

## Slurm Job Script

A Slurm job script is a file that contains the parameters and commands for your job. You can use it to submit your job to the cluster with the `sbatch` command. A Slurm job script usually has two parts: a header and a body. The header contains lines that start with `#SBATCH` and specify the parameters for your job, such as the number of nodes, cores, memory, time, etc. The body contains the commands that you want to run on the allocated nodes, such as loading modules, running programs, copying files, etc.

Here is an example of a Slurm job script that runs a Python script called `hello.py` on one node with one core for 10 minutes:

```bash
#!/bin/bash
#SBATCH --nodes=1
#SBATCH --ntasks-per-node=1
#SBATCH --mem=1G
#SBATCH --time=10:00
#SBATCH --job-name=hello
#SBATCH --output=hello.out

module load python/3.9
python hello.py
```

You can save this script as `hello.sh` and submit it to the cluster with this command:

```bash
sbatch hello.sh
```

You can also specify some parameters as options in the command line instead of in the header. For example, you can submit the same job with this command:

```bash
sbatch -N 1 -n 1 -c 1 -t 10:00 hello.sh
```

You can learn more about how to write and submit Slurm job scripts from [this guide] or [this tutorial].

I hope this example helps you create the page of useful Slurm commands for your website. If you have any questions or feedback, please let me know. 😊

Source: Conversation with Bing, 07/08/2023
(1) Slurm Workload Manager - Slurm Tutorials - SchedMD. https://slurm.schedmd.com/tutorials.html.
(2) A simple Slurm guide for beginners - RONIN BLOG. https://blog.ronin.cloud/slurm-intro/.
(3) Slurm Tutorial - Gowda. https://gowda.ai/slurm101/.
(4) Slurm Workload Manager - Quick Start User Guide - SchedMD. https://slurm.schedmd.com/quickstart.html.
