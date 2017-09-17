1. Which package provides the currently installed `cron` binary?
    1. What is the package version?
    2. What are the package dependencies?
    3. What other files are provided by this package?
2. How many different package repositories are used by your package manager?
3. Search your package manager for the `lynx` browser package
    1. Without installing it, read the package description
    2. Download the package without installing it
    3. List the files included in the package
    4. Extract the pre-install scripts and inspect them
4. List the current running service
    1. Print the status of the `rsyslog` service
    2. Locate the unit file and inspect it
    3. Make a minor change in the unit file- add a Documentation line
        1. Cause systemd to reload the unit file, and print the status again
5. Allow the local root user to ssh to localhost as root without typing password