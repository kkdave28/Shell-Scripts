#!/bin/bash
These are all my scripts that I frequently use.

Note: To run these scripts from any directory, you need to configure the $PATH variable to look for these scripts in the directory where they are stored. TO do that, simple add this line (without the brackets) [ export PATH=$PATH:"path to the directory where the scripts are stored" ] at the end of your .bashrc file found in the home directory. Make sure these scripts have the execute permission bits turned on. You can simple do that by chmod +x "name of the script".

1. bkupro: Takes a backup of all '.\*' files from the /home/usr directory and copies it to /home/usr/Backup-profiles/ .

   Usage: $bkupro

2. clnbkup: removes all files from the directory /home/usr/Backup-profiles.

   Usage: $clnbkup

3. fastgit: Takes all files from the current directory and prompts user for a commit message, then pushes all the files to the git. A repository needs to be created in that directory for it to work.

   Usage: $fastgit

4. initgit: initializes a repository at the current working directory and ask the user to put anything in the Readme.md, asks user to input the first commit message and asks the user the link to the repo they want to push it to.

   Usage: $initgit

5. prm: Permanantly removes all files that were temporarily moved to the directory /home/usr/Temp-Trash, asks users to confirm before deleting all files.

   Usage: $prm

6. srm: Safely moves the files to /home/usr/Temp-Trash/ so that the user can review the files before actual deleting them completely.

   Usage: $srm [file-1] [file-2] [file-3]... 

7. lrm: list all the files that are safely removed and are in /home/usr/Temp-Trash/ directory.

   Usage: $lrm

8. urm: Restores the file in the /home/usr/Temp-Trash directory to the original directory it was deleted from if found, if not found, prints an error message.

   Usage: $urm [file-name]

9. drm: Displays the total space occupied by the /home/usr/Temp-Trash directory.

   Usage: $drm

10. lss: lists all the files in the present working directory, sorted in descending order of file size  or directory whose name is passed as an argument. It is an extension from the 'ls' command. Refer to the man page of 'ls' command for information on option. man (1) ls.

    Usage: $lss [options]

11. cinterp and cplusplusinterp: interpreter for C/C++ programs. Allows the user to run the C/C++ program temporarily by compiling the file to ~/temp-progs and then running the program from that directory. After the program executes, it cleans up the executable, and any other temporary files that may have been created during the compilation/execution. 

    Update: Now these scripts also permits the user for passing any compiler arguments that they might require.
    
    Usage: ln -s cinterp/cplusplusinterp [name of the .c or .cpp file without the extension].
    
    execute the newly formed link directly. 
    
    example: to run foo.c/foo.cpp
    
    $ ln -s cinterp/cplusplusinterp foo
    
    $ ./foo

12. runc and runcpp: wrapper around the cinterp and cplusplusinterp. User can pass the C/C++ file directly with any other command line arguments separated by spaces, it will do the symbolic linking for you, execute the program and cleanup afterwards.
    
    Usage: runc/runcpp [.c/.cpp file with extension] [command line arguments...]

    example: to run foo.c/foo.cpp
    
    $ runc foo.c [command line args]
    
    $ runcpp foo.cpp [command line args]

13. javainterp: interpreter for java programs. Allows the user to run java programs without having to deal with memory overheads of .class files. Compiles the .class file and puts it into ~/temp-progs and then executes the java program. 

    Usage: ls -s javainterp [name of the java file without the .java extension].

    example: to run foo.java
    
    $ ln -s javainterp foo
    
    $ ./foo

14. runjava: Wrapper for javainterp, allows the user to directly run java files without explicitly creating the link to javainterp. Allows the user to pass command line arguments to java programs.
    
    Usage: runjava [name of the java file with the extension] [command line args...]

    example: to run foo.java
    
    $ runjava foo.java [command line arguments].

15. kill_proc: Terminates all the instances of the process denoted by the name passed as an argument to it.

    Usage: kill_proc [proc-name]

    Note: In future, this script will be able to take multiple arguments that can kill multiple instances of multiple processes. This is only the basic version of this script.
