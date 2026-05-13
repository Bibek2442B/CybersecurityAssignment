Linux Access Control Lists (ACLs)

1. Overview

This exercise explores the use of Linux ACLs to provide access control over files, with more flexibility than the access control offered by traditional UNIX file permissions. It is assumed the student has received instruction, or independent study, in access control policies and ACLs. A description of Linux ACLs can be found at https://wiki.archlinux.org/index.php/Access_Control_Lists

2. Lab Environmnet

This lab runs in the Labtainer framework, available at http://my.nps.edu/web/c3o/labtainers. That site includes links to a pre-built virtual machine that has Labtainers installed, however Labtainers can be run on any Linux host that supports Docker containers. From your labtainer-student directory start the lab using: 
labtainer acl

Links to this lab manual will be displayed.

3. Setup

After starting the lab, three virtual terminals will be created, each with a login prompt. Login to these as three different users:
user    password
bob     password4bob
alice   password4alice
harry   password4harry

4. Lab Tasks

In this lab, you will use the getfacl and setfacl commands to view and modify ACLs on files. Use the -h option to learn about these commands, e.g., getfacl -h.

4.1 Review existing file permissions

In the ”alice” terminal, cd to the /shared data directory and list the files:
cd /shared_data
ls -l