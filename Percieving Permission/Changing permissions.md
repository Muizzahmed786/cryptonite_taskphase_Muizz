# Changing permissions

the description asks us to to change the permissions of the file to read it.
This can be done by using the `chmod` command.
We also have to write the correct argument to the command to get the flag.
In this case we have to pass `a+r` as an argument to `chmod`.
where `+` is an operand.
here `a+r` denotes that user,group,and others can read the file at once.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@permissions~changing-permissions:~$ ls -l
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
hacker@permissions~changing-permissions:~$ chmod u+r /flag
hacker@permissions~changing-permissions:~$ ls -l /flag
-r-------- 1 root root 58 Oct 15 20:11 /flag
hacker@permissions~changing-permissions:~$ cat /flag
cat: /flag: Permission denied
hacker@permissions~changing-permissions:~$ cat not-the-flag
cat: not-the-flag: Permission denied
hacker@permissions~changing-permissions:~$ chmod a+r /flag
hacker@permissions~changing-permissions:~$ ls -l /flag
-r--r--r-- 1 root root 58 Oct 15 20:11 /flag
hacker@permissions~changing-permissions:~$ cat /flag
pwn.college{Qg-2ikGJg4sbjmH7vXN3fU9kqec.dNzNyUDLwMjN0czW}
hacker@permissions~changing-permissions:~$
```

This is how I solved it.
