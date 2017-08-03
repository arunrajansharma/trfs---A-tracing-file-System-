# trfs---A-tracing-file-System-
This repository contains the information about a tracing file System - trfs, a layer between VFS and other lower level filesystems, BUT it does not have the code. One can email me at - arrajan@cs.stonybrook.edu, if you would like to explore the source code in C language.
Trfs is able to capture records of file system activity for a number of file system operations. An incremental ioctl support is also provided.


## Introduction ## 
We implemented a tracing file systems called "trfs".
Trfs should capture records of file system activity for a number of file system operations. 

### Functionalities implemented ###
    
      * Efficient Tracing of almost 10 inode and file operations and storing in a file situated on disk.
 		This file would be used to 'replay' the operations.  

      * Support for the mount option in kernel for the file mentioned above.  

      * Support for enabling and disabling any file operation from the given list later in this documentation.

      * A user level program to fire a couple of operations.

      * Finally, a user level program 'treplay' to replay the traces.

### Files  ###
    The design required writing and making changes to kernel and user level code. 
	Following is the brief explanation all of the segments-

      ### Kernel Code ###-
        1. /fs/trfs :
                  a) inode.c
                  b) file.c
                  c) trfs.h
                  d) super.c
                  e) main.c
                  f) rec_codes.h 
                  g) install_modules.sh

     ### User Level Code ###  
         2. /hw2:
                  a) Makefile
                  b) treplay.c
                  c) trctl.c
                  d) testing.c


      Brief explanation:
      a) inode.c ==> Contains code for tracing file operations like mkdir, rmdir, ln, ln -s, touch etc.
      b) file.c  ==> contains code for tracing file operations like open, read and write etc.

      c) trfs.h ==> header file
      
      d) main.c ==> contains code for tfile & mount option parsing 
      
      e) super.c ==> contains code for unmount support 

      f) rec_codes.h ==> contains code for struc information for different options.

      g) install_module.sh ==> script for compiling kernel code and install as a module in the kernel. 
								This script also mounts 'trfs' at 'mnt/test' on 'hw2-cse506g45/hw2/replay' 
								with tfile option.
   
      User level Code

      a) Makefile ==> contains code to compile and generate executables from the source files.
      
      b) treplay.c ==> contains code about playing the traces

      c) trctl.c ==> contains code for setting up the bit map to control which file options should run or not

      d) testing.c ==> contains code for running some sample opertions.




### Contributors ###

* Arunesh Pandey (110945824)
* Arun Rajan (110921170)        phone (631-202-8192)



1. http://www.linfo.org/system_call.html
2. http://lxr.fsl.cs.sunysb.edu/linux/source/fs/

