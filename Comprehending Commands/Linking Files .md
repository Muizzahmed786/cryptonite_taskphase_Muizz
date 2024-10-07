# Linking Files

The description asks us to create a symlink between `/flag` and `/challenge/catflag` to get the flag.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@commands~linking-files:~$ ln -s /flag //home/hacker/not-the-flag
ln: failed to create symbolic link '//home/hacker/not-the-flag': File exists
hacker@commands~linking-files:~$ ln -s /flag ~/not-the-flag
ln: failed to create symbolic link '/home/hacker/not-the-flag': File exists
hacker@commands~linking-files:~$
hacker@commands~linking-files:~$ rm ~/not-the-flag
hacker@commands~linking-files:~$ ln -s /flag ~/not-the-flag
hacker@commands~linking-files:~$ ls
Desktop  h  not-the-flag  r
hacker@commands~linking-files:~$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{0hjXCOX__1yi9s0boLrPKZfwC7l.dlTM1UDLwMjN0czW}
hacker@commands~linking-files:~$
```

This is how I solved it.
