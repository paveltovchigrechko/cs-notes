1. Give a reason why a data center might be interested in virtualization.

2. Give a reason why a company might be interested in running a hypervisor on a machine that has been in use for a while.

3. Give a reason why a software developer might use virtualization on a desktop machine being used for development.

4. Give a reason why an individual at home might be interested in virtualization.

5. Why do you think virtualization took so long to become popular? After all, the key paper was written in 1974 and IBM mainframes had the necessary hardware and software throughout the 1970s and beyond.

6. Name two kinds of instructions that are sensitive in the Popek and Goldberg sense.

7. Name three machine instructions that are not sensitive in the Popek and Goldberg sense.

8. What is the difference between full virtualization and paravirtualization? Which do you think is harder to do? Explain your answer.

9. Does it make sense to paravirtualize an operating system if the source code is available? What if it is not?

10. Consider a type 1 hypervisor that can support up to n virtual machines at the same time. PCs can have a maximum of four disk primary partitions. Can n be larger than 4? If so, where can the data be stored?

11. Briefly explain the concept of process-level virtualization.

12. Why do type 2 hypervisors exist? After all, there is nothing they can do that type 1 hypervisors cannot do and the type 1 hypervisors are generally more efficient as well.

13. Is virtualization of any use to type 2 hypervisors?

14. Why was binary translation invented? Do you think it has much of a future? Explain your answer.

15. Explain how the x86’s four protection rings can be used to support virtualization.

16. State one reason as to why a hardware-based approach using VT-enabled CPUs can perform poorly when compared to translation-based software approaches.

17. Give one case where a translated code can be faster than the original code, in a system using binary translation.

18. VMware does binary translation one basic block at a time, then it executes the block and starts translating the next one. Could it translate the entire program in advance and then execute it? If so, what are the advantages and disadvantages of each technique?

19. What is the difference between a pure hypervisor and a pure microkernel?

20. Briefly explain why memory is so difficult to virtualize. well in practice? Explain your answer.

21. Running multiple virtual machines on a PC is known to require large amounts of memory. Why? Can you think of any ways to reduce the memory usage? Explain.

22. Explain the concept of shadow page tables, as used in memory virtualization.

23. One way to handle guest operating systems that change their page tables using ordinary (nonprivileged) instructions is to mark the page tables as read only and take a trap when they are modified. How else could the shadow page tables be maintained? Discuss the efficiency of your approach vs. the read-only page tables.

24. Why are balloon drivers used? Is this cheating?

25. Descibe a situation in which balloon drivers do not work.

26. Explain the concept of deduplication as used in memory virtualization.

27. Computers have had DMA for doing I/O for decades. Did this cause any problems before there were I/O MMUs?

28. Give one advantage of cloud computing over running your programs locally. Give one disadvantage as well.

29. Give an example of IAAS, PAAS, and SAAS.

30. Why is virtual machine migration important? Under what circumstances might it be useful?

31. Migrating virtual machines may be easier than migrating processes, but migration can still be difficult. What problems can arise when migrating a virtual machine?

32. Why is migration of virtual machines from one machine to another easier than migrating processes from one machine to another?

33. What is the difference between live migration and the other kind (dead migration?)?

34. What were the three main requirements considered while designing VMware?

35. Why was the enormous number of peripheral devices available a problem when VMware Workstation was first introduced?

36. VMware ESXi has been made very small. Why? After all, servers at data centers usually have tens of gigabytes of RAM. What difference does a few tens of megabytes more or less make?

37. Do an Internet search to find two real-life examples of virtual appliances.
