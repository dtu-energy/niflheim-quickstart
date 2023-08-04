# Quickstart

This page will guide you through the basic steps to access and use the hpc resource.

## Prerequisites

Before you start, you need to have:

- An account on the hpc resource. Contact the administrator if you don't have one.
- A SSH client on your local machine. You can use PuTTY for Windows or Terminal for Mac/Linux.
- A text editor on your local machine. You can use Notepad++ for Windows or Vim for Mac/Linux.

## Step 1: Log in to Niflheim

To log in to the hpc resource, open your SSH client and enter the following command:

```bash
ssh username@hpc.example.com
```

Replace `username` with your actual username and hpc.example.com with the actual hostname of the hpc resource. You will be prompted to enter your password. After you enter it, you should see a welcome message and a shell prompt.

## Step 2: Transfer files to/from the hpc resource

To transfer files between your local machine and the hpc resource, you can use a tool called SCP (Secure Copy). SCP uses SSH to securely copy files over the network. To use SCP, open another SSH client window and enter a command like this:

```bash
scp source destination
```

Replace source and destination with the paths of the files or directories you want to copy. The paths can be either local or remote. For example, to copy a file called hello.py from your local machine to your home directory on the hpc resource, enter this command:

```bash
scp hello.py username@hpc.example.com:~
```

To copy a directory called myproject from your home directory on the hpc resource to your local machine, enter this command:

```bash
scp -r username@hpc.example.com:~/myproject .
```

The -r option tells SCP to copy recursively, meaning it will copy all the files and subdirectories inside myproject.

## Step 3: Run programs on Niflheim

To run calculations on Niflheim, you need to use a tool called Slurm. Slurm is a workload manager that allocates resources and schedules jobs on the hpc resource. To use Slurm, you need to write a script that specifies the parameters of your job, such as the number of nodes, cores, memory, time, etc. For example, to submit a job that runs a Python script called hello.py on one node with one core for 10 minutes, write a script like this:

```bash
#!/bin/bash
#SBATCH --nodes=1
#SBATCH --ntasks-per-node=1
#SBATCH --mem=1G
#SBATCH --time=10:00
#SBATCH --job-name=hello
#SBATCH --output=hello.out

module load Python/3.9.6-GCCcore-11.2.0

python hello.py
```

Save this script as `hello.sh`. To submit it, enter this command:

```bash
sbatch hello.sh
```

You should see a message like this:

```
Submitted batch job 123456
```

This means your job has been submitted and assigned a job ID. To check the status of your job, enter this command:

```bash
squeue -u username
```

Replace `username` with your actual username. You should see something like this:

```
JOBID PARTITION     NAME     USER ST       TIME  NODES NODELIST(REASON)
123456     batch    hello username  R       0:05      1 node01
```

This means your job is running on node01. To cancel your job, enter this command:

```bash
scancel 123456
```

Replace 123456 with your actual job ID. To view the output of your job, enter this command:

```bash
cat hello.out
```


