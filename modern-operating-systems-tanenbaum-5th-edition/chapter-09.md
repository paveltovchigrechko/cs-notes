1. Confidentiality, integrity, and availability are three components of security. Describe an application that integrity and availability but not confidentiality, an application that requires confidentiality and integrity but not (high) availability, and an application that requires confidentiality, integrity, and availability.

2. One of the techniques to build a secure operating system is to minimize the size of TCB. Which of the following functions needs to be implemented inside the TCB and which can be implemented outside TCB: (a) Process context switch; (b) Read a file from disk; (c) Add more swapping space; (d) Listen to music; (e) Get the GPS coordinates of a smartphone.

3. What is a covert channel? What is the basic requirement for a covert channel to exist?

4. In a full access-control matrix, the rows are for domains and the columns are for objects. What happens if some object is needed in two domains?

5. Suppose that a system has 5000 objects and 100 domains at some time. 1% of the objects are accessible (some combination of r, w and x) in all domains, 10% are accessible in two domains, and the remaining 89% are accessible in only one domain. Suppose one unit of space is required to store an access right (some combination of r, w, x), object ID, or a domain ID. How much space is needed to store the full protection matrix, protection matrix as ACL, and protection matrix as capability list?

6. Explain which implementation of the protection matrix is more suitable for the following operations:
    (a) Granting read access to a file for all users.
    (b) Revoking write access to a file from all users.
    (c) Granting write access to a file to John, Lisa, Christie, and Jeff.
    (d) Revoking execute access to a file from Jana, Mike, Molly, and Shane.

7. Two different protection mechanisms that we have discussed are capabilities and access-control lists. For each of the following protection problems, tell which of these mechanisms can be used.
    (a) Ken wants his files readable by everyone except his office mate.
    (b) Mitch and Steve want to share some secret files.
    (c) Linda wants some of her files to be public.

8. Represent the ownerships and permissions shown in this UNIX directory listing as a protection matrix. (Note: asw is a member of two groups: users and devel; gmw is a member only of users.) Treat each of the two users and two groups as a domain, so that the matrix has four rows (one per domain) and four columns (one per file).
– rw– r– – r– – 2 gmw users 908 May 26 16:45 PPP– Notes
– rwx r– x r– x 1 asw devel 432 May 13 12:35 prog1
– rw– rw– – – – 1 asw users 50094 May 30 17:51 project.t
– rw– r– – – – – 1 asw devel 13124 May 31 14:30 splash.gif

9. Express the permissions shown in the directory listing of the previous problem as access-control lists.

10. Modify the ACL from the previous problem for one file to grant or deny an access that cannot be expressed using the UNIX rwx system. Explain this modification.

11. Suppose there are four security levels, 1, 2 and 3. Objects A and B are at level 1, C and D are at level 2, and E and F are at level 3. Processes 1 and 2 are at level 1, 3 and 4 are at level 2, and 5 and 6 are at level 3. For each of the following operations, specify whether they are permissible under Bell-LaPadula model, Biba model, or both.
    (a) Process 1 writes object D
    (b) Process 4 reads object A
    (c) Process 3 reads object C
    (d) Process 3 writes object C
    (e) Process 2 reads object D
    (f) Process 5 writes object F
    (g) Process 6 reads object E
    (h) Process 4 write object E
    (i) Process 3 reads object F

12. In the Amoeba scheme for protecting capabilities, a user can ask the server to produce a new capability with fewer rights, which can then be given to a friend. What happens if the friend asks the server to remove even more rights so that the friend can give it to someone else?

13. In Fig. 9-11, there is no arrow from process B to object 1. Would such an arrow be allowed? If not, what rule would it violate?

14. If process-to-process messages were allowed in Fig. 9-11, what rules would apply to them? For process B in particular, to which processes could it send messages and which not?

15. Consider the steganographic system of Fig. 9-14. Each pixel can be represented in a color space by a point in the three-dimensional system with axes for the R, G, and B values. Using this space, explain what happens to the color resolution when steganography is employed as it is in this figure.

16. Break the following monoalphabetic cipher. The plaintext, consisting of letters only, is a well-known excerpt from a poem by Lewis Carroll.
kfd ktbd fzm eubd kfd pzyiom mztx ku kzyg ur bzha kfthcm
ur mfudm zhx mftnm zhx mdzythc pzq ur ezsszcdm zhx gthcm
zhx pfa kfd mdz tm sutythc fuk zhx pfdkfdi ntcm fzld pthcm
sok pztk z stk kfd uamkdim eitdx sdruid pd fzld uoi efzk
rui mubd ur om zid uok ur sidzkf zhx zyy ur om zid rzk
hu foiia mztx kfd ezindhkdi kfda kfzhgdx ftb boef rui kfzk

17. Consider a secret-key cipher that has a 26 × 26 matrix with the columns headed by ABC ... Z and the rows also named ABC ... Z. Plaintext is encrypted two characters at a time. The first character is the column; the second is the row. The cell formed by the intersection of the row and column contains two ciphertext characters. What constraint must the matrix adhere to and how many keys are there?

18. Consider the following way to encrypt a file. The encryption algorithm uses two n-byte arrays, A and B. The first n bytes are read from the file into A. Then A[0] is copied to B[i], A[1] is copied to B[ j], A[2] is copied to B[k], etc. After all n bytes are copied to the B array, that array is written to the output file and n more bytes are read into A. This procedure continues until the entire file has been encrypted. Note that here en-
cryption is not being done by replacing characters with other ones, but by changing their order. How many keys have to be tried to exhaustively search the key space? Give an advantage of this scheme over a monoalphabetic substitution cipher.

19. Secret-key cryptography is more efficient than public-key cryptography, but requires the sender and receiver to agree on a key in advance. Suppose that the sender and receiver have never met, but there exists a trusted third party that shares a secret key with the sender and also shares a (different) secret key with the receiver. How can the sender and receiver establish a new shared secret key under these circumstances?

20. Give a simple example of a mathematical function that to a first approximation will do as a one-way function.

21. Suppose that two strangers A and B want to communicate with each other using secret-key cryptography, but do not share a key. Suppose both of them trust a third party C whose public key is well known. How can the two strangers establish a new shared secret key under these circumstances?

22. As Internet cafes become more widespread, people are going to want ways of going to one anywhere in the world and conducting business there. Describe a way to produce signed documents from one using a smart card (assume that all the computers are equipped with smart-card readers). Is your scheme secure?

23. Natural-language text in ASCII can be compressed by at least 50% using various compression algorithms. Using this knowledge, what is the steganographic carrying capacity for ASCII text (in bytes) of a 1600 × 1200 image stored using the low-order bits of each pixel? How much is the image size increased by the use of this technique (assuming no encryption or no expansion due to encryption)? What is the efficiency of the
scheme, that is, its payload/(bytes transmitted)?

24. Suppose that a tightly knit group of political dissidents living in a repressive country are using steganography to send out messages to the world about conditions in their country. The government is aware of this and is fighting them by sending out bogus images containing false steganographic messages. How can the dissidents try to help people tell the real messages from the false ones?

25. Go to www.cs.vu.nl/ ast and click on covered writing link. Follow the instructions to extract the plays. Answer the following questions:
    (a) What are the sizes of the original-zebras and zebras files?
    (b) What plays are secretly stored in the zebras file?
    (c) How many bytes are secretly stored in the zebras file?

26. Not having the computer echo the password is safer than having it echo an asterisk for each character typed, since the latter discloses the password length to anyone nearby who can see the screen. Assuming that passwords consist of upper and lowercase letters and digits only, and that passwords must be a minimum of five characters and a maximum of eight characters, how much safer is not displaying anything?

27. After getting your degree, you apply for a job as director of a large university computer center that has just put its ancient mainframe system out to pasture and switched over to a large LAN server running UNIX. You get the job. Fifteen minutes after you start work, your assistant bursts into your office screaming: ‘‘Some students have discovered the algorithm we use for encrypting passwords and posted it on the Internet.’’ What
should you do?

28. The Morris-Thompson protection scheme with n-bit random numbers (salt) was designed to make it difficult for an intruder to discover a large number of passwords by encrypting common strings in advance. Does the scheme also offer protection against a student user who is trying to guess the superuser password on his machine? Assume the password file is available for reading.

29. Suppose the password file of a system is available to a cracker. How much extra time does the cracker need to crack all passwords if the system is using the Morris-Thompson protection scheme with n-bit salt versus if the system is not using this scheme?

30. Name three characteristics that a good biometric indicator must have in order to be useful as a login authenticator.

31. Authentication mechanisms are divided into three categories: Something the user knows, something the user has, and something the user is. Imagine an authentication system that uses a combination of these three categories. For example, it first asks the user to enter a login and password, then insert a plastic card (with magnetic strip) and enter a PIN, and finally provide fingerprints. Can you think of two drawbacks of this
design?

32. A computer science department has a large collection of UNIX machines on its local network. Users on any machine can issue a command of the form
rexec machine4 who and have the command executed on machine4, without having the user log in on the remote machine. This feature is implemented by having the user’s kernel send the command and his UID to the remote machine. Is this scheme secure if the kernels are all trustworthy? What if some of the machines are students’ personal computers, with no protection?

33. Lamport’s one-time password scheme uses the passwords in reverse order. Would it not be simpler to use f (s) the first time, f (f(s)) the second time, and so on?

34. Is there any feasible way to use the MMU hardware to prevent the kind of overflow attack shown in Fig. 9-21? Explain why or why not.

35. Describe how stack canaries work and how they can be circumvented by the attackers.

36. The TOCTOU attack exploits race condition between the attacker and the victim. One way to prevent race conditions is make file system accesses transactions. Explain how this approach might work and what problems might arise?

37. Name a C compiler feature that could eliminate a large number of security holes. Why is it not more widely implemented?

38. Can the Trojan-horse attack work in a system protected by capabilities?

39. When a file is removed, its blocks are generally put back on the free list, but they are not erased. Do you think it would be a good idea to have the operating system erase each block before releasing it? Consider both security and performance factors in your answer, and explain the effect of each.

40. How can a parasitic virus (a) ensure that it will be executed before its host program, and (b) pass control back to its host after doing whatever it does?

41. Some operating systems require that disk partitions must start at the beginning of a track. How does this make life easier for a boot-sector virus?

42. Change the program of Fig. 9-28 so that it finds all the C programs instead of all the executable files.

43. The virus in Fig. 9-33(d) is encrypted. How can the dedicated scientists at the antivirus lab tell which part of the file is the key so that they can decrypt the virus and reverse engineer it? What can Virgil do to make their job a lot harder?

44. The virus of Fig. 9-33(c) has both a compressor and a decompressor. The decompressor is needed to expand and run the compressed executable program. What is the compressor for?

45. Name one disadvantage of a polymorphic encrypting virus from the point of view of the virus writer.

46. Often one sees the following instructions for recovering from a virus attack:
    1. Boot the infected system.
    2. Back up all files to an external medium.
    3. Run fdisk (or a similar program) to format the disk.
    4. Reinstall the operating system from the original CD-ROM.
    5. Reload the files from the external medium.
Name two serious errors in these instructions.

47. Are companion viruses (viruses that do not modify any existing files) possible in UNIX? If so, how? If not, why not?

48. Self-extracting archives, which contain one or more compressed files packaged with an extraction program, are frequently used to deliver programs or program updates. Discuss the security implications of this technique.

49. Why are rookits extremely difficult or almost impossible to detect as opposed to viruses and worms?

50. Could a machine infected with a rootkit be restored to good health by simply rolling back the software state to a previously stored system restore point?

51. Discuss the possibility of writing a program that takes another program as input and determines if that program contains a virus.

52. Section 9.10.1 describes a set of firewall rules that limit outside access to only three services. Describe another set of rules that you can add to this firewall to further restrict access to these services.

53. On some machines, the SHR instruction used in Fig. 9-38(b) fills the unused bits with zeros; on others the sign bit is extended to the right. For the correctness of Fig. 9-38(b), does it matter which kind of shift instruction is used? If so, which is better?

54. To verify that an applet has been signed by a trusted vendor, the applet vendor may include a certificate signed by a trusted third party that contains its public key. However, to read the certificate, the user needs the trusted third party’s public key. This could be provided by a trusted fourth party, but then the user needs that public key. It appears that there is no way to bootstrap the verification system, yet existing browsers use it. How could it work?

55. Describe three features that make Java a better programming language than C to write secure programs.

56. Assume that your system is using JDK 1.2. Show the rules (similar to those in Figure 9-40) you will use to allow an applet from www.appletsRus.com to run on your machine. This applet may download additional files from www.appletsRus.com, read/write files in /usr/tmp/, and also read files from /usr/me/appletdir.

57. How are applets different from applications? How does this difference relate to security?

58. Write a pair of programs, in C or as shell scripts, to send and receive a message by a covert channel on a UNIX system. (Hint: A permission bit can be seen even when a file is otherwise inaccessible, and the sleep command or system call is guaranteed to delay for a fixed time, set by its argument.) Measure the data rate on an idle system. Then create an artificially heavy load by starting up numerous different background
processes and measure the data rate again.

59. Several UNIX systems use the DES algorithm for encrypting passwords. These systems typically apply DES 25 times in a row to obtain the encrypted password. Download an implementation of DES from the Internet and write a program that encrypts a password and checks if a password is valid for such a system. Generate a list of 10 encrypted passwords using the Morris-Thomson protection scheme. Use 16-bit salt for your program.

60. Suppose a system uses ACLs to maintain its protection matrix. Write a set of management functions to manage the ACLs when (1) a new object is created; (2) an object is deleted; (3) a new domain is created; (4) a domain is deleted; (5) new access rights (a combination of r, w, x) are granted to a domain to access an object; (6) existing access rights of a domain to access an object are revoked; (7) new access rights are grant-
ed to all domains to access an object; (8) access rights to access an object are revoked from all domains.

61. Implement the program code outlined in Sec. 9.7.1 to see what happens when there is buffer overflow. Experiment with different string sizes.

62. Write a program that emulates overwriting viruses outlined in Sec. 9.9.2 under the heading ‘‘Executable Program Viruses’’. Choose an existing executable file that you know can be overwritten without any harm. For the virus binary, choose any harmless executable binary.
