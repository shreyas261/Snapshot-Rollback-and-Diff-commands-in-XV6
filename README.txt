This Project is done by     : Shreyas P Namjoshi
In The course of department : Design and Engineering of Computer Systems , CSE IIT Bombay
Instructor of the course is : Prof . Purushottam Kulkarni


XXXXXXXXXXXXXXXXXXXXXXXXXX  REQUIREMENTS XXXXXXXXXXXXXXXXXXXXXXX

1)QEMU : 
	sudo apt-get install qemu-system

		or
		
	sudo apt update && sudo apt install qemu-system


xxxxxxxxxxxxxxxxxxxxxxx      COMMANDS      xxxxxxxxxxxxxxxxxxxxxxx

Note : All the operations are to be done in a directory named "working" which is already created at bootup
       snapshots,rollback,diff all three of the operations will work for the working directory only to
       test the program program "touch", "rm" are already provided, and teo text files "try1.txt" and
       "try2.txt" has text content provided already.The system doesnt save the image hence when qemu is
       terminated the working directory files and all previous snapshot no longer exists.This is limitation 
       of way the xv6  works using Makefile.


Use : "snapnroll --help" To know all the commands.

To Increase number of snapshots supported by the system : 
	
	In file snapnroll.c : Change the macro "MAX_VERSIONS" from "3" to desired number "num"
 		       Note : At maximum you can increase to 9 after that file system will crash and may give unexpected behaviour


To rum XV6 : 
	Go to directory in which xv6 is there then run command "make clean && make qemu-nox" . Make sure qemu is already installed.


xxxxxxxxxxxxxxxxxxxxxxx     XV6-MIT     xxxxxxxxxxxxxxxxxxxxxxx

NOTE: we have stopped maintaining the x86 version of xv6, and switched
our efforts to the RISC-V version
(https://github.com/mit-pdos/xv6-riscv.git)

xv6 is a re-implementation of Dennis Ritchie's and Ken Thompson's Unix
Version 6 (v6).  xv6 loosely follows the structure and style of v6,
but is implemented for a modern x86-based multiprocessor using ANSI C.

ACKNOWLEDGMENTS

xv6 is inspired by John Lions's Commentary on UNIX 6th Edition (Peer
to Peer Communications; ISBN: 1-57398-013-7; 1st edition (June 14,
2000)). See also https://pdos.csail.mit.edu/6.828/, which
provides pointers to on-line resources for v6.

xv6 borrows code from the following sources:
    JOS (asm.h, elf.h, mmu.h, bootasm.S, ide.c, console.c, and others)
    Plan 9 (entryother.S, mp.h, mp.c, lapic.c)
    FreeBSD (ioapic.c)
    NetBSD (console.c)

The following people have made contributions: Russ Cox (context switching,
locking), Cliff Frey (MP), Xiao Yu (MP), Nickolai Zeldovich, and Austin
Clements.

We are also grateful for the bug reports and patches contributed by Silas
Boyd-Wickizer, Anton Burtsev, Cody Cutler, Mike CAT, Tej Chajed, eyalz800,
Nelson Elhage, Saar Ettinger, Alice Ferrazzi, Nathaniel Filardo, Peter
Froehlich, Yakir Goaron,Shivam Handa, Bryan Henry, Jim Huang, Alexander
Kapshuk, Anders Kaseorg, kehao95, Wolfgang Keller, Eddie Kohler, Austin
Liew, Imbar Marinescu, Yandong Mao, Matan Shabtay, Hitoshi Mitake, Carmi
Merimovich, Mark Morrissey, mtasm, Joel Nider, Greg Price, Ayan Shafqat,
Eldar Sehayek, Yongming Shen, Cam Tenny, tyfkda, Rafael Ubal, Warren
Toomey, Stephen Tu, Pablo Ventura, Xi Wang, Keiichi Watanabe, Nicolas
Wolovick, wxdao, Grant Wu, Jindong Zhang, Icenowy Zheng, and Zou Chang Wei.

The code in the files that constitute xv6 is
Copyright 2006-2018 Frans Kaashoek, Robert Morris, and Russ Cox.

ERROR REPORTS

We don't process error reports (see note on top of this file).

BUILDING AND RUNNING XV6

To build xv6 on an x86 ELF machine (like Linux or FreeBSD), run
"make". On non-x86 or non-ELF machines (like OS X, even on x86), you
will need to install a cross-compiler gcc suite capable of producing
x86 ELF binaries (see https://pdos.csail.mit.edu/6.828/).
Then run "make TOOLPREFIX=i386-jos-elf-". Now install the QEMU PC
simulator and run "make qemu".

