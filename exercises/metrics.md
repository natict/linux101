1. Install the `stress` utility, try to make it hog user CPU %
    1. Use the nice command to run an additional `stress` process with niceness of 10. Which `stress` process gets more CPU time?
    2. Repeat the experiment with niceness of -10. What is the current result?
2. List 5 methods which generate hardware interrupts
    1. Execute `vmstat` and test your methods. Which generated most interrupts per-second?
3. Examine your understanding of process memory, Buffers & Caches:
    1. Write 3 scripts, each fills up a different type of memory (use `stress` & `dd` to fill up memory and `echo 3 > /proc/sys/vm/drop_caches` to drop buffers and caches)
4. Take turns with a friend:
    1. Fill up the root device and let your friend find what takes up space
5. Write a script to fill up a device inodes (without affecting the free space)