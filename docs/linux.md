# Useful Linux Commands

This page will introduce you to some of the most useful Linux commands that you can use on the hpc resource. Linux commands are case-sensitive and follow a general syntax of:

```bash
command [options] [arguments]
```

The `command` is the name of the program that you want to run, such as `ls`, `cd`, `cp`, etc. The `options` are optional flags that modify the behavior of the command, such as `-a`, `-l`, `-r`, etc. These can typically also be concatenated, e.g. `-alr`. The `arguments` are optional inputs that the command operates on, such as filenames, directories, patterns, etc.

Here are some examples of common Linux commands and their usage:

- `ls`: List directory contents.For example, `ls` will list the files and directories in the current directory, while `ls /home/user` will list the files and directories in the `/home/user` directory. Recommended options for this command are:
    - `ls -lathr`

- `cd`: Change directory. For example, `cd /home/user` will change the current working directory to `/home/user`. Some useful shortcuts for this command are:
    - `cd ..`: This command moves up one level in the directory hierarchy. For example, if the current working directory is `/home/user/docs`, then `cd ..` will change it to `/home/user`.
    - `cd`: Move to the home directory of the current user.
    - `cd -`: Move to the previous folder.

- `cp`: Copy files or directories. For example, `cp hello.py /home/user/docs` will copy the file `hello.py` from the current working directory to the `/home/user/docs` directory.

- `mv`: Move or rename files or directories. For example, `mv hello.py goodbye.py` will rename the file `hello.py` to `goodbye.py`. Another example is `mv hello.py /home/user/docs` which will move the file `hello.py` from the current working directory to the `/home/user/docs` directory.

- `rm`: Remove files or directories. `rm hello.py` will remove or delete the file `hello.py`. Some useful options for this command are:
    - `-r`: Remove recursively, meaning it will remove all the files and subdirectories inside a directory.
    - `-i`: Prompt before removing each file or directory.

- `mkdir`: Create a new directory. Some useful options for this command are:
    - `-p`: This option creates parent directories if they do not exist.

- `pwd`: Print the current working directory.

- `cat`: Display file contents.

- `less`: View and paginate file contents one screenful at a time. You can use the space bar to move to the next page, or the b key to move to the previous page.

- `head` (`tail`): Display the first (last) lines of a file.

- `grep`: Search for a pattern in a file or output. For example, `grep print hello.py` will print all the lines in the file `hello.py` that contain the word 'print'.

- `man`: You can use the man command to display the user manual of any command that you can run on the terminal. For example, to view the manual pages of the `less` command, type `man less` in the terminal.

 <!-- You can also use regular expressions to specify more complex patterns with special characters and modifiers. For example, `grep ^print hello.py` will print all the lines in the file `hello.py` that start with the word 'print'. You can also use the `-i` option to ignore case, the `-v` option to invert the match, the `-n` option to show line numbers, and the `-c` option to show the count of matching lines. For example, `grep -i -v -n -c print hello.py` will print the number of lines in the file `hello.py` that do not contain the word 'print', regardless of case, and also show the line numbers of those lines. -->

<!-- - `find`: This command searches for files and directories that match certain criteria in a given directory or the entire file system. For example, `find /home/user -name hello.py` will find all the files and directories named `hello.py` in the `/home/user` directory and its subdirectories. You can also use other criteria, such as size, type, permission, owner, group, date, etc. For example, `find /home/user -size +1M -type f` will find all the files that are larger than 1 MB in the `/home/user` directory and its subdirectories. You can also use logical operators, such as `-and`, `-or`, and `-not`, to combine multiple criteria. For example, `find /home/user -name hello.py -or -name goodbye.py` will find all the files and directories named either `hello.py` or `goodbye.py` in the `/home/user` directory and its subdirectories. -->
<!-- - `wc`: This command counts the number of lines, words, and bytes in a file or the output of another command. For example, `wc hello.py` will print the number of lines, words, and bytes in the file `hello.py`. You can also use options to print only one of these counts. For example, `wc -l hello.py` will print only the number of lines in the file `hello.py`. Another example is `ls -l | wc -l` which will print the number of lines in the output of the `ls -l` command. -->

<!-- - `sort`: This command sorts the lines of a file or the output of another command in alphabetical or numerical order. For example, `sort hello.py` will sort the lines of the file `hello.py` in alphabetical order. You can also use options to change the sorting order or criteria. For example, `sort -r hello.py` will sort the lines of the file `hello.py` in reverse alphabetical order. Another example is `sort -n hello.txt` which will sort the lines of the file `hello.txt` in numerical order. -->

<!-- - `uniq`: This command removes duplicate adjacent lines from a file or the output of another command. For example, `uniq hello.txt` will remove any duplicate adjacent lines from the file `hello.txt`. You can also use options to count or show only duplicate or unique lines. For example, `uniq -c hello.txt` will count how many times each line occurs in the file `hello.txt`. Another example is `uniq -d hello.txt` which will show only duplicate lines from the file `hello.txt`. -->

<!-- - `diff`: This command compares two files or directories and shows their differences. For example, `diff hello.py goodbye.py` will show how the file `hello.py` differs from the file `goodbye.py`. You can also use options to change how the differences are displayed or ignored. For example, `diff -y hello.py goodbye.py` will show a side-by-side comparison of the two files. Another example is `diff -w hello.py goodbye.py` which will ignore whitespace differences between the two files. -->

<!-- - `tar`: This command creates or extracts compressed archive files that contain multiple files and directories. For example, `tar czvf myproject.tar.gz myproject` will create a compressed archive file named `myproject.tar.gz` that contains all the files and directories inside the folder named `myproject`. You can also use options to specify different compression methods or levels. For example, `tar cjvf myproject.tar.bz2 myproject` will create a compressed archive file named `myproject.tar.bz2` that uses bzip2 compression instead of gzip compression. Another example is `tar xzvf myproject.tar.gz` which will extract all the files and directories inside the archive file `myproject.tar.gz`. -->


<!-- # Documentation (man) -->

<!-- Sure, I can write a bit on the man command as well. The man command is a very useful and powerful tool that allows you to access the documentation of any Linux command or utility. You can use it to learn how to use a command, what options and arguments it accepts, what it does, and what other commands are related to it. The man command also has many options and features that can help you customize and enhance your search and reading experience. For example, you can: -->

<!-- - Use the `-f` option to find out what section a command belongs to, or what commands match a keyword. -->
<!-- - Use the `-k` option to search for a keyword in all the man pages and see the results with their descriptions. -->
<!-- - Use the `-a` option to view all the man pages for a command in different sections. -->
<!-- - Use the `--apropos` option to search for a keyword in the names and descriptions of all the man pages. -->
<!-- - Use the `--regex` option to search for a regular expression in the names of all the man pages. -->
<!-- - Use the `--wildcard` option to search for a wildcard pattern in the names of all the man pages. -->
<!-- - Use the `-P` option to specify a pager program to display the man page, such as `less`, `more`, or `vim`. -->
<!-- - Use the `-M` option to specify a different directory to look for the man pages, such as `/usr/local/share/man`. -->
<!-- - Use the `-L` option to specify a different language to display the man page, such as `en`, `fr`, or `ja`. -->
<!-- - Use the `-H` option to display the man page in a web browser, such as `firefox`, `chrome`, or `safari`. -->
<!-- - Use the `-t` option to format the man page for printing with a program such as `groff` or `ps2pdf`. -->
<!-- - Use the `-w` option to show the location of the man page file on your system. -->

<!-- These are just some of the options and features that you can use with the man command. You can learn more about them by reading the man page of man itself¹. You can also refer to some of these web resources that explain how to use the man command in more detail²³⁴. -->

<!-- Source: Conversation with Bing, 04/08/2023 -->
<!-- (1) man Command in Linux {With Examples} | phoenixNAP KB. https://phoenixnap.com/kb/linux-man. -->
<!-- (2) man command in Linux with Examples - GeeksforGeeks. https://www.geeksforgeeks.org/man-command-in-linux-with-examples/. -->
<!-- (3) man Command in Linux/Unix with Examples - javatpoint. https://www.javatpoint.com/linux-man. -->
<!-- (4) How to Use Linux's man Command: Hidden Secrets and Basics. https://www.howtogeek.com/663440/how-to-use-linuxs-man-command-hidden-secrets-and-basics/. -->

<!-- Sure, I can write an example for the man command as well. Here is the example: -->

<!-- Suppose you want to learn how to use the curl command, which is a tool for transferring data from or to a server using various protocols. You can use the man command to access the documentation of the curl command by typing this in your terminal: -->

<!-- ```bash -->
<!-- man curl -->
<!-- ``` -->

<!-- This will display the man page of the curl command, which contains a lot of information about the command, such as its name, synopsis, description, options, examples, bugs, authors, etc. You can use the arrow keys or the space bar to scroll up and down the man page, or the q key to quit. -->

<!-- The man page is divided into several sections, each with a heading that starts with a capital letter. For example, the first section is NAME, which shows the name and a brief description of the command. The second section is SYNOPSIS, which shows the general syntax of the command and its options. The third section is DESCRIPTION, which explains what the command does and how it works. -->

<!-- You can also use the slash (/) key to search for a keyword or a pattern in the man page. For example, if you want to find out how to use the -o option of the curl command, which allows you to save the output to a file, you can type this in your terminal: -->
    
<!-- ```bash -->
<!-- man curl -->
<!-- /o -->
<!-- ``` -->

<!-- This will display the man page of the curl command and highlight the first occurrence of the -o option. You can use the n key to go to the next occurrence, or the N key to go to the previous occurrence. You can also use other keys to modify your search, such as case sensitivity, regular expressions, etc. -->

<!-- You can also use the -k option of the man command to search for a keyword in all the man pages and see the results with their descriptions. For example, if you want to find out what commands are related to network or internet, you can type this in your terminal: -->

<!-- ```bash -->
<!-- man -k network -->
<!-- ``` -->

<!-- This will display a list of commands that match the keyword 'network' in their names or descriptions. You can then use the man command again to view the man page of any command that interests you. -->
