# Editing files

When working on a HPC cluster, you will frequently need to edit files. For instance, you might need to modify scripts, or input/output files for your simulations or data analysis.

When it comes to editing files in Linux, there are several command-line editors available, including Vim, Nano, and Emacs. Here are some basic commands for editing files with Emacs and Vim:

## Emacs
To edit a file with Emacs, type `emacs -nw <filename>` in the terminal. Once you have opened the file, you can use the following commands to edit it:

- `Ctrl + X` followed by `Ctrl + S`: Save the file.
- `Ctrl + X` followed by `Ctrl + C`: Quit Emacs.
- [Reference card](https://www.gnu.org/software/emacs/refcards/pdf/refcard.pdf)

## Vim
To edit a file with Vim, type `vi <filename>` in the terminal. Once you have opened the file, you can use the following commands to edit it:

- `i`: Enter insert mode.
- `Esc`: Exit insert mode.
- `:w`: Save the file.
- `:q`: Quit Vim.
- [Reference card](https://web.mit.edu/merolish/Public/vi-ref.pdf)


## Nano
To edit a file with Nano, type `nano <filename>` in the terminal. Once you have opened the file, you can use the following commands to edit it:

- `Ctrl + O`: Save the file.
- `Ctrl + X`: Quit Nano.
- [Reference card](https://www.nano-editor.org/dist/latest/cheatsheet.html)

## Transfer files to/from Niflheim

It is also possible to edit files on your local PC and then transfer them to Niflheim. It is possible to transfer file between your local machine and Niflheim with a program with a GUI e.g. FileZilla or MobaXterm. Or you can use a tool called SCP (Secure Copy). SCP uses SSH to securely copy files over the network. To use SCP, open another SSH client window and enter a command like this:

```bash
scp source destination
```

Replace source and destination with the paths of the files or directories you want to copy. The paths can be either local or remote. For example, to copy a file called `hello.py` from your local machine to your home directory on Niflheim, enter this command:

```bash
scp hello.py username@surt.fysik.dtu.dk:~
```

To copy a directory called `myproject` from your home directory on Niflheim to your local machine, enter this command:

```bash
scp -r username@surt.fysik.dtu.dk:~/myproject .
```

The -r option tells SCP to copy recursively, meaning it will copy all the files and subdirectories inside myproject.

**Remember** that data created at DTU should stay at DTU. Niflheim has backup of home folders, so don't move important data away from Niflheim to a place without backup.
