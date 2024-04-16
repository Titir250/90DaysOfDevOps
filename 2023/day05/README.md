# Day 5 Task: Advanced Linux Shell Scripting for DevOps Engineers with User management

If you noticed that there are a total 90 sub-directories in the directory '2023' of this repository. What did you think, how did I create 90 directories? Manually one by one or using a script, or a command?

All 90 directories within seconds using a simple command.

` mkdir day{1..90}`

### Tasks

1. You have to do the same using Shell Script i.e using either Loops or command with start day and end day variables using arguments -

So Write a bash script create directories.sh that when the script is executed with three given arguments (one is the directory name and second is start number of directories and third is the end number of directories ) it creates a specified number of directories with a dynamic directory name.

Example 1: When the script is executed as

`./createDirectories.sh day 1 90`

then it creates 90 directories as `day1 day2 day3 .... day90`

Example 2: When the script is executed as

`./createDirectories.sh Movie 20 50`
then it creates 50 directories as `Movie20 Movie21 Movie23 ...Movie50`

Notes:
You may need to use loops or commands (or both), based on your preference . [Check out this reference: https://www.geeksforgeeks.org/bash-scripting-for-loop/](https://www.geeksforgeeks.org/bash-scripting-for-loop/)

#!/bin/bash

<< task
Create custom directories
with a given range in arguments
first argument is the directory name then the range
task



mkdir $1 && cd $1



for (( i=$2; i<=$3; i++ ))


do
        
        mkdir "${1}${i}"

done

2.  Create a Script to backup all your work done till now.

Backups are an important part of DevOps Engineer's day to Day activities
The video in References will help you to understand How a DevOps Engineer takes backups (it can feel a bit difficult but keep trying, Nothing is impossible.)

#!/bin/bash


<< comment
This script will take backups
from source to target
comment

create_backup ()
{

src_dir="/home/titir/scripts"

tgt_dir="/home/titir/backups"



backup_filename="backup_$(date +%Y-%m-%d-%H-%M-%S).tar.gz"


echo "Backup Started"


echo "Backing up to $backup_filename..."


tar -czvf "${tgt_dir}/${backup_filename}" "$src_dir"


echo "Backup Complete"


}


create_backup

Watch [this video](https://youtu.be/aolKiws4Joc)

In case of Doubts, post it in [Discord Channel for #90DaysOfDevOps](https://discord.gg/hs3Pmc5F)

3.  Read About Cron and Crontab, to automate the backup Script

Cron is the system's main scheduler for running jobs or tasks unattended. A command called crontab allows the user to submit, edit or delete entries to cron. A crontab file is a user file that holds the scheduling information.

#*/2 * * * * bash /home/titir/scripts/backup.sh

Watch This video as a Reference to Task 2 and 3 [https://youtu.be/aolKiws4Joc](https://youtu.be/aolKiws4Joc)

4.  Read about User Management and Let me know on Linkedin if you're ready for Day 6.

A user is an entity, in a Linux operating system, that can manipulate files and perform several other operations. Each user is assigned an ID that is unique for each user in the operating system. In this post, we will learn about users and commands which are used to get information about the users. After installation of the operating system, the ID 0 is assigned to the root user and the IDs 1 to 999 (both inclusive) are assigned to the system users and hence the ids for local user begins from 1000 onwards.

5.  Create 2 users and just display their Usernames

titir@Titir:~/scripts$ id titir

uid=1000(titir) gid=1000(titir)

groups=1000(titir),4(adm),20(dialout),24(cdrom),25(floppy),27(sudo),29(audio),30(dip),44(video),46(plugdev),116(netdev),117(docker)

titir@Titir:~/scripts$ id sabita

uid=1004(sabita) gid=1005(sabita) groups=1005(sabita),1003(bheem_bheem)

titir@Titir:~/scripts$

[Check out this reference: https://www.geeksforgeeks.org/user-management-in-linux/](https://www.geeksforgeeks.org/user-management-in-linux/)

Post your daily work on Linkedin and let [me](https://www.linkedin.com/in/shubhamlondhe1996/) know , writing an article is the best :)

[← Previous Day](../day04/README.md) | [Next Day →](../day06/README.md)
