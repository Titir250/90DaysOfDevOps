# Day 6 Task: File Permissions and Access Control Lists

### Today is more on Reading, Learning and Implementing File permissions

The concept of Linux File permission and ownership is important in Linux.
Here, we will be working on Linux permissions and ownership and will do tasks on
both of them.
Let us start with the Permissions.

1. Create a simple file and do `ls -ltr` to see the details of the files [refer to Notes](https://github.com/LondheShubham153/90DaysOfDevOps/tree/master/2023/day06/notes)

Each of the three permissions are assigned to three defined categories of users. The categories are:

- owner — The owner of the file or application.
- "chown" is used to change the ownership permission of a file or directory.
- group — The group that owns the file or application.
- "chgrp" is used to change the group permission of a file or directory.
- others — All users with access to the system. (outised the users are in a group)
- "chmod" is used to change the other users permissions of a file or directory.

  As a task, change the user permissions of the file and note the changes after `ls -ltr`

2. Write an article about File Permissions based on your understanding from the notes.

  File Permissions are applied in linux os for resctricting the access of a file to the specific group of users and there are 3 levels of access read,write and execute. We a can give these 3 permissions to owner, group and others.

3. Read about ACL and try out the commands `getfacl` and `setfacl`

   ACL means access control list. It is an evolved version of file permissionn this pkg needs to be installed separately as not provided out of the box(sudo apt install acl). Using this we can give permission for a specific file to a specific user or group. All the users in the same group does not necessarily have same permission attached.

   

   
titir@Titir:~/scripts$ sudo setfacl -m u:bheem:rwx abc.sh

titir@Titir:~/scripts$ getfacl abc.sh

# file: abc.sh

# owner: bheem

# group: bheem

user::r--

user:bheem:rwx

group::---

mask::rwx

other::---


In case of any doubts, post it on [Discord Community](https://discord.gg/hs3Pmc5F)

Happy Learning

[← Previous Day](../day05/README.md) | [Next Day →](../day07/README.md)
