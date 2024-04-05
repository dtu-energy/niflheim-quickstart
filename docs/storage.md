# Storage

When starting work on Niflheim, you will get a home folder at `/home/energy/$USER`, where `$USER` is your Niflheim username. This folder is located on a server (`niflfs6`) on which you have a specific storage quota. Check your quota with `quota -s`. This command will list your usage and quota on all servers where you have files.

Folders under `/home/energy` are backed up daily and kept for three months. If you accidentally delete some files, you can ask one of the Niflheim administrators to recreate the files from the backup.

If you run out of storage space, i.e. you have exhausted your quota, the first option is always:

- Clean up your files! Many output files from calculations are never used and can safely be removed. The most critical files are input scripts that determine the input parameters of a calculation. Output files can almost always be recreated by rerunning the calculation.

After cleaning up files, there are two options:

- Ask for access to `/home/scratch3` (`/home/scratch3` has no backup). You can get a larger quota on `/home/scratch3`, suitable for a temporary project where you can finish the calculations and perform analysis within a reasonable amount of time. Once you finish the calculations in a project, the output and results can be moved back to `/home/energy` (after cleanup).
    
or
    
- Ask for a larger quota on `/home/energy/`. Please specify the required quota.


