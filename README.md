## Assignment 1 - LINUX 

Your login name: altschool i.e., home directory /home/altschool. The home directory contains the following sub-directories: code, tests, personal, misc Unless otherwise specified, you are running commands from the home directory.

```
$ whoami
$ echo $HOME
$ sudo su
# useradd -m altschool
# ls -la
# cd /home/altschool
altschool]# mkdir code
altschool]# mkdir tests
altschool]# mkdir personal
altschool]# mkdir misc
```

a.Change directory to the tests directory using an absolute pathname

```
altschool]# pwd
altschool]# cd /home/altschool/tests
```

b.Change the directory to the tests directory using the relative pathname

```
tests]# cd ../
altschool]# cd tests
```

c.Use the echo command to create a file named `fileA` with text content ‘Hello A’ in the misc directory

```
tests]# cd ../
altschool]# cd misc
misc]# echo fileA
<!-- fileA -->
misc]# vim fileA
```

d.Create an empty file named fileB in the misc directory

```
misc]# touch fileB
```

e.Copy contents of `fileA` into `fileC`

```
misc]# cp fileA fileC
misc]# ls
<!-- fileA fileB fileC -->
```

f.Move contents of `fileB` into `fileD`

```
misc]# mv fileB fileD
```

g.Create a tar archive called `misc.tar` for the contents of misc directory

```
misc]# cd ../
altschool]# tar -cvf misc.tar misc
```

h.Compress the tar archive to create a `misc.tar.gz` file

```
altschool]# gzip misc.tar
<!-- code misc misc.tar.gz personal tests -->
```

I. Create a user and force the user to change his/her password upon login

```
altschool]# sudo useradd tech
altschool]# sudo passwd tech
altschool]# sudo chage -d 0 tech
altschool]# su tech
<!-- You are required to change your password immediately (administrator enforced).
Changing password for tech. -->
```

J. Lock a users password

```
altschool]# sudo passwd -l tech
```

K. Create a user with no login shell

```
altschool]# sudo useradd -s /sbin/nologin tech1
```

L. Disable password based authentication for ssh

```
altschool]# sudo nano /etc/ssh/sshd_config
<!-- PubkeyAuthentication prohibit-password // PubkeyAuthentication no -->
altschool]# sudo systemctl restart ssh
```

M. Disable root login

```
altschool]# sudo nano /ect/ssh/sshd_config
<!-- #PermitRootLogin prohibit-password  -> no -->
altschool]# sudo systemctl restart ssh
```
