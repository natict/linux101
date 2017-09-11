1. Checking whether a process is still running:
    * Given a process ID (PID) as an argument, this script will check, at user-specified intervals, whether the given process is still running. You may use the ps and sleep commands.
1. Examine and explain the following script. For hints, you might refer to the manual for find and stat.
```
#!/bin/bash

# Author:  Nathan Coulter
# This code is released to the public domain.
# The author gave permission to use this code snippet in the ABS Guide.

find -maxdepth 1 -type f -printf '%f\000'  | {
   while read -d $'\000'; do
      mv "$REPLY" "$(date -d "$(stat -c '%y' "$REPLY") " '+%Y%m%d%H%M%S'
      )-$REPLY"
   done
}

# Warning: Test-drive this script in a "scratch" directory.
# It will somehow affect all the files there.
```