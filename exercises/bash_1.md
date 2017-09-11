1. Create a script which prints how many processes are currently running on your system.
    * Hint: Use ps and wc
    * Hint 2: The first line of output of ps is not a process!
2. Write a script which displays the path to your home directory and the terminal type that you are using.
    * Hint: use HOME, and TERM
    1. Add comments in your script.
    2. Add information for the users of your script.
    3. Change permissions on your script so that you can run it.
    4. Run the script in normal mode and in debug mode. It should run without errors.
    5. Make errors in your script: see what happens if you misspell commands, if you leave out the first line or put something unintelligible there, or if you misspell shell variable names or write them in lower case characters after they have been declared in capitals. Check what the debug comments say about this.
3. Write a script that takes a directory and a number *n* as arguments, and prints the *n* largest files in that directory
    1. Test it on multiple directories
    2. Prevent your script from printing errors from internal commands
4. Explain what the following script does. It is really just a parameterized command-line pipe.
```
#!/bin/bash

DIRNAME=/usr/bin
FILETYPE="shell script"
LOGFILE=logfile

file "$DIRNAME"/* | fgrep "$FILETYPE" | tee $LOGFILE | wc -l

exit 0
```
5. Write a script that backs itself up, that is, copies itself to a file named backup.sh.
    * Hint: Use the `cat` command and the appropriate *positional parameter*.
6. Write a script that echoes itself to stdout, but backwards.
