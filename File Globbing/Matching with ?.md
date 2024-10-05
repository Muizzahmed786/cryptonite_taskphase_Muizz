# Matching with ?

The description asks us to use `?` character instead of `c` and `l` in the argument to `cd` and then run `/challenge/run`.

```bash
Connected!
This challenge resets your working directory to /home/hacker unless you change
directory properly...
hacker@globbing~matching-with-:~$ cd /cha??enge
You used either the 'c', 'l', or '*' characters. Disallowed!
This challenge resets your working directory to /home/hacker unless you change
directory properly...
hacker@globbing~matching-with-:~$ /cha??enge
This challenge resets your working directory to /home/hacker unless you change
directory properly...
ssh-entrypoint: /challenge: Is a directory
This challenge resets your working directory to /home/hacker unless you change
directory properly...
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{ANZzkPWAktXzBrl2pzZX2EjPohd.dJjM4QDLwMjN0czW}
hacker@globbing~matching-with-:/challenge$
```

This is how I solved it.
