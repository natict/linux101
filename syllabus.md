# Syllabus
Each unit is ~90 minutes

1. Intro to OS & Intro to Linux
    1. Introduction to Operating System
        1. Define an OS (SW-OS-HW, Kernel & Software)
        2. OS Features (Multi-user, Multiprogramming > Multitasking, Multiprocessing), HW specific features? (e.g. mobile)
        3. OS Components
            1. Process Management (Scheduling, IPC)
            2. Memory Management (VM, swapping, caches)
            3. Storage Management (Filesystems, caches)
            4. Security (Users, groups, permissions)
        4. OS Operation
            1. Interrupts (i.e. HIDs, Timer, disk, net)
            2. User vs Kernel mode
        5. Virtualization
    2. Intro to Linux
        1. History
            1. Multics (1964) by MIT, GE & Bell Labs. Multi-user, Multiprogramming and Multiprocessing. 
            2. Unix (1969) by Bell Labs (Dennis Ritchie & Ken Thompson et. al.). Multitasking, portable (after C rewrite in 72), AT&T licences. Today: mostly macOS & BSD
            3. Linux:
                1. Stallman, GNU, FSF, GPL (1984-...)
                2. Linus (1991)
                3. Distributions (1992), Debian (1993), Red Hat (1994)
        2. Unix/Linux Philosophy
            1. Do one thing and do it well
            2. Write programs to work together
            3. Handle text streams
            4. OSS
        3. More terminology
            1. Bootloader (e.g. grub)
            2. Service/Daemon (e.g. sshd, httpd)
            3. X Windows & Graphical UI
            4. Command-line & Shell
2. Basic CLI ([exercise](exercises/cli.md))
    1. HFS & Filesystems
        1. File types
        2. Directory traversal, listing, creation, removal
        3. absolute vs relative path
        4. *nix directory tree
            1. Directories purpose
            2. Binary directory (bin vs sbin)
        5. mounts
    2. Basic commands
        1. cat, echo, head, tail, grep
        2. man, --help
        3. locate, find
        4. reboot/shutdown
        5. ssh
    3. Environment variables (printing, setting, PATH)
    4. Process basics (stdin, stdout, stderr, exit code)
    5. File utilities (touch, mkdir, rm, mv, du)
    6. I/O redirection (<, >, >>, 2>, 2>&1)
    7. Pipes (|)
3. Packages, Services and Permissions
    1. Permissions
        1. Users, groups
        2. Id vs name
        3. Shadow
        4. File permissions
        5. sudo
    2. Package management
        1. Why do we need packages?
        2. Package structure
            1. Meta, Scripts, Requires, Provides, Files
        3. Basic rpm commands
            1. Install (-ivh), remove (-e), query (-qa), list (-ql)
            2. Installed package by file (-qf)
        4. Why do we need package manager?
        5. Basic yum commands
            1. Install, update, erase
            2. List, info, makecache
            3. Package by file (whatprovides)
    3. Services
        1. Boot process
            1. BIOS, bootloader, kernel, initramfs, init
            2. rc.local
        2. Systemd (What? Why?)
            1. managing services
                1. start/stop/reload
            2. Adding / reconfiguring services
                1. Unit location
                    1. /etc/systemd/system/
                    2. /usr/lib/systemd/system/
                2. daemon-reload
        3. SSH
            1. Public/Private keys
                1. Generating a new pair
                2. authorized_keys
            2. Tunneling
                1. Built-in (scp, sftp)
                2. Dynamic (e.g. -D)
4. Bash 1
    1. TODO
5. Bash 2
    1. TODO
6. Linux Metrics 1
    1. TODO
7. Linux Metrics 2
    1. TODO
8. Networking
    1. Viewing configuration
    2. Setting configuration
    3. Monitoring
    4. Sniffing
9. Extras (for Ops)
    1. Provisioning
        1. PXE boot
    2. Configuration management
    3. Automation
        1. mussh
        2. python fabric
    4. ?