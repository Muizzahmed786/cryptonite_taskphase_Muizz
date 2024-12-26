# Changing file ownership

The description asks us to change the owner of `/flag` to `hacker` user.
In this we have to use `ls -l` as our prompt to check the file or directory permissions.
From there we have to find the `/flag` and read it to get the flag.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@permissions~changing-file-ownership:~$ ls -l
total 44
-rw-r--r-- 1 hacker hacker    4 Oct  7 18:43 COLLEGE
drwxr-xr-x 2 hacker hacker 4096 Sep 30 17:06 Desktop
-rw-r--r-- 1 hacker hacker    8 Oct  8 10:50 PWN
-rw-r--r-- 1 root   hacker   58 Oct  4 13:04 h
-rw-r--r-- 1 hacker hacker  169 Oct  9 16:36 hack_output
-rw-r--r-- 1 hacker hacker  829 Oct  8 09:00 instructions
-rw-r--r-- 1 hacker hacker   93 Oct  8 09:00 myflag
lrwxrwxrwx 1 hacker hacker    5 Oct  7 18:06 not-the-flag -> /flag
-rw-r--r-- 1 root   hacker   77 Oct  9 15:37 pwn
-rw-r--r-- 1 root   hacker   77 Oct  9 16:00 pwn1_output
-rw-r--r-- 1 root   hacker   58 Oct  4 13:05 r
-rw-r--r-- 1 hacker hacker  435 Oct  8 08:52 the-flag
hacker@permissions~changing-file-ownership:~$ chown hacker not-the-flag
hacker@permissions~changing-file-ownership:~$ ls -l
total 44
-rw-r--r-- 1 hacker hacker    4 Oct  7 18:43 COLLEGE
drwxr-xr-x 2 hacker hacker 4096 Sep 30 17:06 Desktop
-rw-r--r-- 1 hacker hacker    8 Oct  8 10:50 PWN
-rw-r--r-- 1 root   hacker   58 Oct  4 13:04 h
-rw-r--r-- 1 hacker hacker  169 Oct  9 16:36 hack_output
-rw-r--r-- 1 hacker hacker  829 Oct  8 09:00 instructions
-rw-r--r-- 1 hacker hacker   93 Oct  8 09:00 myflag
lrwxrwxrwx 1 hacker hacker    5 Oct  7 18:06 not-the-flag -> /flag
-rw-r--r-- 1 root   hacker   77 Oct  9 15:37 pwn
-rw-r--r-- 1 root   hacker   77 Oct  9 16:00 pwn1_output
-rw-r--r-- 1 root   hacker   58 Oct  4 13:05 r
-rw-r--r-- 1 hacker hacker  435 Oct  8 08:52 the-flag
hacker@permissions~changing-file-ownership:~$
```

This is how I solved it.

In this case the owner is already hacker.
