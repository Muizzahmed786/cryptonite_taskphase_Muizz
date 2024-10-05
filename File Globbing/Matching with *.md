# Matching with *

the description asks us to change the directory from `~` to `/challenge` using globbing and then run `/challenge/run` to get the flag

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
This challenge resets your working directory to /home/hacker unless you change
directory properly...
hacker@globbing~matching-with-:~$ cd /*
ssh-entrypoint: cd: too many arguments
hacker@globbing~matching-with-:~$ cd /*nge
You specified the path to 'cd' to in more than 4 characters. Disallowed!
hacker@globbing~matching-with-:~$ cd ./*
ssh-entrypoint: cd: too many arguments
hacker@globbing~matching-with-:~$ cd *
ssh-entrypoint: cd: too many arguments
hacker@globbing~matching-with-:~$ cd /challenge
You specified the path to 'cd' to in more than 4 characters. Disallowed!
hacker@globbing~matching-with-:~$ cd /ch*
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{0FfrJWvQcLZHuluHx5q75KIRkzQ.dFjM4QDLwMjN0czW}
hacker@globbing~matching-with-:/challenge$
```

This is how I solved it.
