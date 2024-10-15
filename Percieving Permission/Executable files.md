# Executable files

The description asks us to make the `/challenge/run` program executable.
We have to solve this by using the following: `a`, `+` and `x`.
`a` signifies that it will apply to all.
`+` is an operator.
`x` for making it executable.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@permissions~executable-files:~$ ls -l /challenge/run
-r--r--r-- 1 hacker hacker 32 Jul  4 06:37 /challenge/run
hacker@permissions~executable-files:~$ chmod a+x /challenge/run
hacker@permissions~executable-files:~$ ls -l /challenge/run
-r-xr-xr-x 1 hacker hacker 32 Jul  4 06:37 /challenge/run
hacker@permissions~executable-files:~$ cat /challenge/run
#!/bin/bash

/challenge/.solver
hacker@permissions~executable-files:~$ /challenge/run
Successful execution! Here is your flag:
pwn.college{0tg9oJGDEBXjJce9_2zpTTVFC1I.dJTM2QDLwMjN0czW}
hacker@permissions~executable-files:~$
```

This is how I solved it.
