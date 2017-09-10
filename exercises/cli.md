# CLI Exercise
1. Create a new directory in your home directory.
    1. Can you move this directory to the same level as your home directory?
2. Export a senseless path by entering, for instance, `export PATH=blah` and try listing directory content.
3. Make a symbolic link in your home directory to `/var/tmp`. Check that it really works.
    1. Make another symbolic link in your home directory to this link. Check that it works. Remove the first link and list directory content. What happened to the second link?
4. Find the number of files in `/usr` containing the word ‘include’ (some files may match multiple times)
    1. List the size of each file (see `man xargs`)
    2. Print the largest one (see `man sort`)
5. List the files in reverse alphabetical order.
6. Where is the `bash` program located on your system?
    1. Use the `--version` option to find out which version you are running.
7. How many hours has the system been running?
8. Change to your home directory. Create a new directory and copy all the files of the `/etc` directory into it. Make sure that you also copy the files and directories which are in the subdirectories of /etc! (recursive copy)
    1. Change into the new directory and make a directory for files starting with an upper case character and one for files starting with a lower case character. Move all the files to the appropriate directories. Use as few commands as possible.
    2. Remove the remaining files.
    3. Delete the directory and its entire content using a single command.
9. List the 20 largest directories