# Project-Dos-
testing a change 
making sure we still good 

### Initiating these commands provided the current date upon creation, "cal" is not registered in nano, and pwd gives you the current directory
date
cal 
pwd 

nano task.sh
chmod +x task.sh
./task.sh
### Switching from "vi" to "nano" took me longer than expected to realize why the change was occuring

which bash
/bin/bash 
nano task.sh
./task.sh
### here is where we initilize the shebang prefix 

nano 0_xvz
echo "Hello World"
file 0_xvz
0_xvz: ASCII text
### the ouput for the file name "0_xvz" 

echo date > date.sh
cat date.sh
nano date.sh
#!/bin/bash

date
### here we created the file for date under date.sh

cd desktop 
cd projecto
pwd
/c/Users/Jered/desktop/projecto
### here I created a folder name "projecto" to hold all the files needed for the tutorial 

nano hello-world.sh
#!/bin/bash

echo "Hello World" 
### created the file name "hello-world" 

./hello-world.sh
Hello World
### demonstrating the hello-world.sh output 
  
  
    GNU nano 4.9.3                                   backup.sh                                    Modified
# This bash script is used to backup a user's home directory to /tmp/.

function backup {

    if [ -z $1 ]; then
        user=$(justjered)
    else
        if [ ! -d "/home/$1" ]; then
                echo "Requested $1 user home directory doesn't exist."
                exit 1
        fi
        user=$1
    fi

    input=/desktop/projecto/$user
    output=/documents/${user}_home_$(date +%Y-%m-%d_%H%M%S).tar.gz

    function total_files {
        find $1 | wc -l
    }

    function total_directories {
        find $1 -type d | wc -l
    }

    function total_archived_directories {
        tar -tzf $1 | grep  /$ | wc -l
    }

    function total_archived_files {
        tar -tzf $1 | grep -v /$ | wc -l
    }

    tar -czf $output $input 2> /dev/null

    src_files=$( total_files $input )
    src_directories=$( total_directories $input )

    arch_files=$( total_archived_files $output )
    arch_directories=$( total_archived_directories $output )

    echo "########## $user ##########"
    echo "Files to be included: $src_files"
    echo "Directories to be included: $src_directories"
    echo "Files archived: $arch_files"
    echo "Directories archived: $arch_directories"

    if [ $src_files -eq $arch_files ]; then
        echo "Backup of $input completed!"
        echo "Details about the output backup file:"
        ls -l $output
    else
        echo "Backup of $input failed!"
    fi
}


### for the backup file I couldn't get the bash to transfer over my push because it kept getting rejected along with my remaining files. 











^G Get Help    ^O Write Out   ^W Where Is    ^K Cut Text    ^J Justify     ^C Cur Pos     M-U Undo
^X Exit        ^R Read File   ^\ Replace     ^U Paste Text  ^T To Spell    ^_ Go To Line  M-E Redo
