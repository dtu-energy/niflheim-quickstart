# Quickstart

This page will guide you through the basic steps to access and use Niflheim.

## Prerequisites

We assume that you have an account on Niflheim. Before you start, you need to have:

- An SSH client on your local machine. For example you can use PuTTY or MobaXterm for Windows or Terminal for Mac/Linux.

## Log in to Niflheim

To log in to Niflheim, open your SSH client and enter the following command:

```bash
ssh username@surt.fysik.dtu.dk
```

Replace `username` with your actual username and `surt` with the hostname of the login node you want to connect to (`thul`, `slid`, `sylg`, `svol`, `fjorm` or `surt`). You will be prompted to enter your password. After you enter it, you should see a welcome message and a shell prompt.

## Run programs on Niflheim

- Make the program available by [loading a software module](modules.md)
- [Create a script](editing-files.md) to instruct the program what to do
- It is possible to test that your program works or your calculation will run on the login nodes, e.g. `python script.py`. Real calculations you need to submit for processing on a compute node. To submit jobs we use [Slurm](slurm.md#submitting-jobs-with-slurm)


