1. Explain how writing UNIX in C made it easier to port it to new machines.

2. The POSIX interface defines a set of library procedures. Explain why POSIX standardizes library procedures instead of the system-call interface.

3. Linux depends on gcc compiler to be ported to new architectures. Describe one advantage and one disadvantage of this dependency.

4. A directory contains the following files:
```
aardvark ferret koala porpoise unicorn
bonefish grunion llama quacker vicuna
capybara hyena marmot rabbit weasel
dingo ibex nuthatch seahorse yak
emu jellyfish ostrich tuna zebu
```
Which files will be listed by the command
```
ls [abc]*e*?
```

5. What does the following Linux shell pipeline do?
```
grep nd xyz | wc –l
```

6. Write a Linux pipeline that prints the eighth line of file z on standard output.

7. Why does Linux distinguish between standard output and standard error, when both default to the terminal?

8. A user at a terminal types the following commands:
```
a | b | c &
d | e | f &
```
After the shell has processed them, how many new processes are running?

9. When the Linux shell starts up a process, it puts copies of its environment variables, such as HOME, on the process’ stack, so the process can find out what its home directory is. If this process should later fork, will the child automatically get these variables, too?

10. About how long does it take a traditional UNIX system to fork off a child process under the following conditions: text size = 100 KB, data size = 20 KB, stack size = 10 KB, task structure = 1 KB, user structure = 5 KB. The kernel trap and return takes 1 msec, and the machine can copy one 32-bit word every 50 nsec. Text segments are shared, but data and stack segments are not.

11. As multimegabyte programs became more common, the time spent executing the fork system call and copying the data and stack segments of the calling process grew proportionally. When fork is executed in Linux, the parent’s address space is not copied, as traditional fork semantics would dictate. How does Linux prevent the child from doing something that would completely change the fork semantics?

12. Why are negative arguments to nice reserved exclusively for the superuser?

13. A non-real-time Linux process has priority levels from 100 to 139. What is the default static priority and how is the nice value used to change this?

14. Does it make sense to take away a process’ memory when it enters zombie state? Why or why not?

15. To what hardware concept is a signal closely related? Give two examples of how signals are used.

16. Why do you think the designers of Linux made it impossible for a process to send a signal to another process that is not in its process group?

17. A system call is usually implemented using a software interrupt (trap) instruction. Could an ordinary procedure call be used as well on the Pentium hardware? If so, under what conditions and how? If not, why not?

18. In general, do you think daemons have higher or lower priority than interactive processes? Why?

19. When a new process is forked off, it must be assigned a unique integer as its PID. Is it sufficient to have a counter in the kernel that is incremented on each process creation, with the counter used as the new PID? Discuss your answer.

20. In every process’ entry in the task structure, the PID of the parent is stored. Why?

21. The copy-on-write mechanism is used as an optimization in the fork system call, so that a copy of a page is created only when one of the processes (parent or child) tries to write on the page. Suppose a process p1 forks processes p2 and p3 in quick succession. Explain how a page sharing may be handled in this case.

22. What combination of the sharing flags bits used by the Linux clone command corresponds to a conventional UNIX fork call? To creating a conventional UNIX thread?

23. Two tasks A and B need to perform the same amount of work. However, task A has higher priority, and needs to be given more CPU time. Expain how will this be achieved in each of the Linux schedulers described in this chapter, the O(1) and the CFS scheduler.

24. Some UNIX systems are tickless, meaning they do not have periodic clock interrupts. Why is this done? Also, does ticklessness make sense on a computer (such as an embedded system) running only one process?

25. When booting Linux (or most other operating systems for that matter), the bootstrap loader in sector 0 of the disk first loads a boot program which then loads the operating system. Why is this extra step necessary? Surely it would be simpler to have the bootstrap loader in sector 0 just load the operating system directly.

26. A certain editor has 100 KB of program text, 30 KB of initialized data, and 50 KB of BSS. The initial stack is 10 KB. Suppose that three copies of this editor are started simultaneously. How much physical memory is needed (a) if shared text is used, and (b) if it is not?

27. Why are open-file-descriptor tables necessary in Linux?

28. In Linux, the data and stack segments are paged and swapped to a scratch copy kept on a special paging disk or partition, but the text segment uses the executable binary file instead. Why?

29. Describe a way to use mmap and signals to construct an interprocess-communication mechanism.

30. A file is mapped in using the following mmap system call:
```
mmap(65536, 32768, READ, FLAGS, fd, 0)
```
Pages are 8 KB. Which byte in the file is accessed by reading a byte at memory address 72,000?

31. After the system call of the previous problem has been executed, the call
```
munmap(65536, 8192)
```
is carried out. Does it succeed? If so, which bytes of the file remain mapped? If not, why does it fail?

32. Can a page fault ever lead to the faulting process being terminated? If so, give an example. If not, why not?

33. Is it possible that with the buddy system of memory management it ever occurs that two adjacent blocks of free memory of the same size coexist without being merged into one block? If so, explain how. If not, show that it is impossible.

34. It is stated in the text that a paging partition will perform better than a paging file. Why is this so?

35. Give two examples of the advantages of relative path names over absolute ones.

36. The following locking calls are made by a collection of processes. For each call, tell what happens. If a process fails to get a lock, it blocks.
    (a) A wants a shared lock on bytes 0 through 10.
    (b) B wants an exclusive lock on bytes 20 through 30.
    (c) C wants a shared lock on bytes 8 through 40.
    (d) A wants a shared lock on bytes 25 through 35.
    (e) B wants an exclusive lock on byte 8.

37. Consider the locked file of Fig. 10-26(c). Suppose that a process tries to lock bytes 10 and 11 and blocks. Then, before C releases its lock, yet another process tries to lock bytes 10 and 11, and also blocks. What kinds of problems are introduced into the semantics by this situation? Propose and defend two solutions.

38. Explain under what situations a process may request a shared lock or an exclusive lock. What problem may a process requesting an exclusive lock suffer from?

39. If a Linux file has protection mode 755 (octal), what can the owner, the owner’s group, and everyone else do to the file?

40. Some tape drives have numbered blocks and the ability to overwrite a particular block in place without disturbing the blocks in front of or behind it. Could such a device hold a mounted Linux file system?

41. In Fig. 10-24, both Fred and Lisa have access to the file x in their respective directories after linking. Is this access completely symmetrical in the sense that anything one of them can do with it the other one can, too?

42. As we have seen, absolute path names are looked up starting at the root directory and relative path names are looked up starting at the working directory. Suggest an efficient way to implement both kinds of searches.

43. When the file /usr/ast/work/f is opened, several disk accesses are needed to read i-node and directory blocks. Calculate the number of disk accesses required under the assumption that the i-node for the root directory is always in memory, and all directories are one block long.

44. A Linux i-node has 12 disk addresses for data blocks, as well as the addresses of single, double, and triple indirect blocks. If each of these holds 256 disk addresses, what is the size of the largest file that can be handled, assuming that a disk block is 1 KB?

45. When an i-node is read in from the disk during the process of opening a file, it is put into an i-node table in memory. This table has some fields that are not present on the disk. One of them is a counter that keeps track of the number of times the i-node has been opened. Why is this field needed?

46. On multi-CPU platforms, Linux maintains a runqueue for each CPU. Is this a good idea? Explain your answer?

47. The concept of loadable modules is useful in that new device drivers may be loaded in the kernel while the system is running. Provide two disadvantages of this concept.

48. Pdflush threads can be awakened periodically to write back to disk very old pages—older than 30 sec. Why is this necessary?

49. After a system crash and reboot, a recovery program is usually run. Suppose this program discovers that the link count in a disk i-node is 2, but only one directory entry references the i-node. Can it fix the problem, and if so, how?

50. Make an educated guess as to which Linux system call is the fastest.

51. Is it possible to unlink a file that has never been linked? What happens?

52. Based on the information presented in this chapter, if a Linux ext2 file system were to be put on a 1.44-MB floppy disk, what is the maximum amount of user file data that could be stored on the disk? Assume that disk blocks are 1 KB.

53. In view of all the trouble that students can cause if they get to be superuser, why does this concept exist in the first place?

54. A professor shares files with his students by placing them in a publicly accessible directory on the Computer Science department’s Linux system. One day he realizes that a file placed there the previous day was left world-writable. He changes the permissions and verifies that the file is identical to his master copy. The next day he finds that the file has been changed. How could this have happened and how could it have been
prevented?

55. Linux supports a system call fsuid. Unlike setuid, which grants the user all the rights of the effective id associated with a program he is running, fsuid grants the user who is running the program special rights only with respect to access to files. Why is this fea-
ture useful?

56. On a Linux system, go to /proc/#### directory, where #### is a decimal number corresponding to a process currently running in the system. Answer the following along with an explanation:
    (a) What is the size of most of the files in this directory?
    (b) What are the time and date settings of most of the files?
    (c) What type of access right is provided to the users for accessing the files?

57. If you are writing an Android activity to display a Web page in a browser, how would you implement its activity-state saving to minimize the amount of saved state without losing anything important?

58. If you are writing networking code on Android that uses a socket to download a file, what should you consider doing that is different than on a standard Linux system?

59. If you are designing something like Android’s zygote process for a system that will have multiple threads running in each process forked from it, would you prefer to start those threads in zygote or after the fork?

60. Imagine you use Android’s Binder IPC to send an object to another process. You later receive an object from a call into your process, and find that what you have received is the same object as previously sent. What can you assume or not assume about the caller in your process?

61. Consider an Android system that, immediately after starting, follows these steps:
1. The home (or launcher) application is started.
2. The email application starts syncing its mailbox in the background.
3. The user launches a camera application.
4. The user launches a Web browser application.
The web page the user is now viewing in the browser application requires inceasingly more RAM, until it needs everything it can get. What happens?

62. Write a minimal shell that allows simple commands to be started. It should also allow them to be started in the background.

63. Using assembly language and BIOS calls, write a program that boots itself from a floppy disk on a Pentium-class computer. The program should use BIOS calls to read the keyboard and echo the characters typed, just to demonstrate that it is running.

64. Write a dumb terminal program to connect two Linux computers via the serial ports. Use the POSIX terminal management calls to configure the ports.

65. Write a client-server application which, on request, transfers a large file via sockets. Reimplement the same application using shared memory. Which version do you expect to perform better? Why? Conduct performance measurements with the code you have written and using different file sizes. What are your observations? What do you think happens inside the Linux kernel which results in this behavior?

66. Implement a basic user-level threads library to run on top of Linux. The library API should contain function calls like mythreads init, mythreads create, mythreads join, mythreads exit, mythreads yield, mythreads self, and perhaps a few others. Next, implement these synchronization variables to enable safe concurrent operations: mythreads mutex init, mythreads mutex lock, mythreads mutex unlock. Before starting, clearly define the API and specify the semantics of each of the calls. Next implement the user-level library with a simple, round-robin preemptive scheduler. You will also need to write one or more multithreaded applications, which use your library, in order to test it. Finally, replace the simple scheduling mechanism with another one which behaves like the Linux 2.6 O(1) scheduler described in this chapter. Compare the performance your application(s) receive when using each of the schedulers.

67. Write a shell script that displays some important system information such as what processes you are running, your home directory and current directory, processor type, current CPU utilization, etc.
