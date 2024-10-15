# Fun with group names

the description asks us to identify the name of the group our user is in.
We have to then change the group owner using `chgrp` command.
We have to use `id` command to figure out the name.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@permissions~fun-with-groups-names:~$ ls -l
total 44
-rw-r--r-- 1 hacker grp2055    4 Oct  7 18:43 COLLEGE
drwxr-xr-x 2 hacker grp2055 4096 Sep 30 17:06 Desktop
-rw-r--r-- 1 hacker grp2055    8 Oct  8 10:50 PWN
-rw-r--r-- 1 root   grp2055   58 Oct  4 13:04 h
-rw-r--r-- 1 hacker grp2055  169 Oct  9 16:36 hack_output
-rw-r--r-- 1 hacker grp2055  829 Oct  8 09:00 instructions
-rw-r--r-- 1 hacker grp2055   93 Oct  8 09:00 myflag
lrwxrwxrwx 1 hacker grp2055    5 Oct  7 18:06 not-the-flag -> /flag
-rw-r--r-- 1 root   grp2055   77 Oct  9 15:37 pwn
-rw-r--r-- 1 root   grp2055   77 Oct  9 16:00 pwn1_output
-rw-r--r-- 1 root   grp2055   58 Oct  4 13:05 r
-rw-r--r-- 1 hacker grp2055  435 Oct  8 08:52 the-flag
hacker@permissions~fun-with-groups-names:~$ id
uid=1000(hacker) gid=1000(grp2055) groups=1000(grp2055)
hacker@permissions~fun-with-groups-names:~$ chgrp grp32500 not-the-flag
chgrp: invalid group: ‘grp32500’
hacker@permissions~fun-with-groups-names:~$ chgrp grp2055 not-the-flag
hacker@permissions~fun-with-groups-names:~$ ls -l not-the-flag
lrwxrwxrwx 1 hacker grp2055 5 Oct  7 18:06 not-the-flag -> /flag
hacker@permissions~fun-with-groups-names:~$ /flag
ssh-entrypoint: /flag: Permission denied
hacker@permissions~fun-with-groups-names:~$ cat not-the-flag
pwn.college{0yPxSKnWtj1Ht3aXmdMgBnyiRb0.dJzNyUDLwMjN0czW}
hacker@permissions~fun-with-groups-names:~$
```

This is how I solved it
