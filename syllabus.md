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
        2. man \[-k\], --help
        3. locate, find
        4. reboot/shutdown
        5. ssh
    3. Environment variables (printing, setting, PATH)
    4. Process basics (stdin, stdout, stderr, exit code)
    5. File utilities (touch, mkdir, rm, mv, du)
    6. I/O redirection (<, >, >>, 2>, 2>&1, >/dev/null)
    7. Pipes (|) and one-liners (;)
3. Processes & Permissions ([exercise](exercises/proc_perm.md))
    1. Permissions
        1. Users, groups (id, useradd, usermod, /etc/passwd, /etc/groups)
        2. Id vs name
        3. su, sudo
            1. /etc/sudoers.conf
        4. File permissions
            1. Ownership
            2. Mode
        5. Shadow
    2. Processes & signals
        1. Listing processes (ps, top)
        2. Process information: pid, ppid, cmdline
        4. Signals: why? sending (kill) & handling
            1. SIGTERM (kill)
            2. SIGINT (Ctrl+c)
            3. SIGKILL (kill -9), and SIGSTOP (Ctrl+z)
        3. Process states (simplified)
            1. Un-interruptable sleep & Zombies
        4. Scheduling with cron
4. Bash 1 ([exercise](exercises/bash_1.md))
    1. Builtins
        1. alias, history, pushd/popd/dirs, which, read
        2. test, \[ expr \]
        3. Jobs: Ctrl+z, bg, fg, jobs, cmd &
        4. help    
    2. Writing scripts
        1. Which shell will run the script? (#!)
        2. Comments
        3. (print-)Debugging scripts (bash -x)
    3. Variables
        1. Global vs local
        2. String
        3. Reserved
        4. Quoting ('' vs "")
        5. Parameters ($0, $#, $*)
    4. Command Substitution ($(cmd))
5. Bash 2 ([exercise](exercises/bash_2.md))
    1. Arithmetic Expression ($((arithmetic_exp)))
    2. Conditional
        1. if expr; then cmd; else cmd2; fi
        2. using test (note spacing)
        3. simple conditionals: &&, ||
    3. Loops
        1. for e in element1 element2 ...; do cmd; done
        2. while expr; do cmd; done
    4. Functions
6. Linux Metrics (and logs) ([exercise](exercises/metrics.md))
    1. Intro
        1. When/Why are we looking at metrics?
            1. Capacity planning
            2. During an incident
            3. Incident postmortem
            4. ?
        2. How are we looking at metrics?
            1. CLI
            2. UI (e.g. netdata) 
            3. Aggregation (e.g. graphite)
    2. CPU
        1. Percentage: user, system, nice, idle, IO-wait, stolen ticks
        2. Load Average (load increase vs decrease, included process states)
        3. Context Switches & Interrupts (vmstat)
    3. Memory
        1. Free, Buffers, Caches (not freeable objects)
        2. Swap in/out
    4. IO
        1. Free space, inodes
        2. Blocks in/out globally (vmstat), per device (iostat), per process (iotop)
        3. Average queue size, wait
    5. Networking
        1. Traffic stats (iptraf)
        2. Interface stats (ethtool -S)
    6. Logs
        1. Kernel (dmesg), System (syslog / messages) and Applications
        2. Writing to log from scripts (logger)
        3. Log rotation (logrotate)
7. Networking ([exercise](exercises/network.md))
    1. Intro
        1. TCP/IP 5 layer model: Application, Transport, Network, Data, Physical
        2. IP address, subnets & routing
        3. Sockets, TCP vs UDP 
    1. Viewing
        1. Data: Interfaces (ip link, ethtool), ARP (arp -a)
        2. Network: IP address (ip address), Routing table (ip route), Trace route (mtr) 
        3. Transport: Show listening sockets (netstat/ss), Test connectivity (nc), Port scanning (nmap)
        4. Application: HTTP (curl)
    2. Setting configuration
        1. IP configuration
        2. DNS Resolver (nsswitch, resolv.conf)
    3. Sniffing
        1. tcpdump, tshark
8. Packages & Services
    1. Package management
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
    2. Services
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
9. Extras (for Ops)
    1. Provisioning
        1. PXE boot
    2. Configuration management
    3. Automation
        1. mussh
        2. python fabric
    4. Docker containers
        1. Why?
        2. Into to containers
        3. containers vs virtualization