# Basic Linux/Unix Shell
## Description of Systems: 

1. Code is contained in 6 C(.c) code files.
2. This Linux Shell implements the following commands:

### Internal commands:
1) cd : changes the working directory
    * cd .. : used to move to the parent directory of current directory
    * cd ~ : change directory to the home directory.
    * cd : same as cd~

2) echo : prints the given text
    *  echo -n : omits printing the trailing newline
    *  echo --help : displays help menu
3) pwd : prints the name of working(current) directory
    *  pwd -P : prints absolute path, avoids symlinks
    *  pwd -L : use PWD from environment, even if it contains symlinks.

### External commands:

1) ls : lists(prints) directory contents.

    *  ls -r : lists directory contents in reverse order .
    *  ls -l : lists comma separated directory contents.
2) cat : concatenate files and print on the standard output

    *  cat -n : numbers all output lines.
    *  cat -E : display $ at end of each line.
3) date : print or set the system date and time

    *  date +%d-%m-%y : output date in format (DD-MM-YY).
    *  date -u : prints Universal Time (UTC)
4) rm : remove files or directories

    *  rm -i : asks for a confirmation message before removing.
    *  rm -v : gives a message explaining what is being done.
5) mkdir : make directories

    * mkdir -v : prints a message whenever a directory is created.
    * mkdir -p :make parent directories


## Assumptions made:

After changing directory using cd external commands mentioned are not used again.

## Some of the major errors/corner cases handled are mainly:

1. Wrong commands/ Command not found.
2. Missing operands for commands.
3. Wrong command line options used.

Specifically, for mkdir:
1. Directory already exists(in case of mkdir).
2. mkdir can be used to make multiple directories/files.

 Specifically, for rm:
1. It is a directory (directories cannot be removed by rm in some cases).
2. File/Directory doesn’t exist.

 Specifically for ls:
1. Command can be executed using both command line options at the same 
time too.
2. Wrong command line option entered for ls.

 Specifically for date:
1. Wrong command line option entered for date.
2. Command not found.

 Specifically for cat:
1. File doesn’t exist.
2. Error in opening the file.

 Specifically for cd:
1. (cd) option is also provided.
2. No such file/directory.(provided as path).

 Specifically for pwd:
1. Wrong command line option entered for pwd.
2. Wrong command.

 Specifically for echo:
1. Wrong command.
2. Command not found.

## Some Test Cases:
    1. ls 
    2. ls -r
    3. ls -m
    4. ls -r path
    5. ls -m path
    6. cat filename
    7. cat -E filename
    8. cat -n filename
    9. date 
    10. date +%d-%m-%y
    11. date -u 
    12. rm file1 
    13. rm -i filename
    14. rm -v filename
    15. mkdir directory1
    16. mkdir directory1 directory2
    17. mkdir -v directory1
    18. mkdir -p directory1/directory2
    19. cd
    20. cd ..
    21. cd path
    22. cd ~
    23. echo text 
    24. echo -n text
    25. echo --help
    26. pwd 
    27. pwd -P 
    28. pwd -L
    29. exit


For executing commands with threads add &t to your commands.

All above test cases can be executed via threads (&t) too.

## Deployment - How To Use

1. Download all the C (.c) files with the Makefile
2. To use the shell run commands

    ```
    make all
    make run
    ```

     Note: You need a Linux Sytem or Linux Subsysten to run this Basic Linux/Unix Shell.