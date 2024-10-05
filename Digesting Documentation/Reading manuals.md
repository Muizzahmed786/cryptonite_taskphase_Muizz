# Reading manuals

The description asks us to read the manual `challenge` useing `man` command to find the flag.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college


Connected!

hacker@man~reading-manuals:~$
hacker@man~reading-manuals:~$ cd /
hacker@man~reading-manuals:/$ ls
bin  boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@man~reading-manuals:/$ man challenge

CHALLENGE(1)                                                 Challenge Commands                                                 CHALLENGE(1)

NAME
       /challenge/challenge - print the flag!

SYNOPSIS
       challenge OPTION

DESCRIPTION
       Output the flag when called with the right arguments.

       --fortune
              read a fortune

       --version
              output version information and exit

       --tbwgvr NUM
              print the flag if NUM is 612

AUTHOR
       Written by Zardus.

REPORTING BUGS
       The repository for this dojo: <https://github.com/pwncollege/linux-luminarium/>

SEE ALSO
       man(1) bash-builtins(7)

pwn.college                                                       May 2024                                                      CHALLENGE(1)
hacker@man~reading-manuals:/$ /challenge/challenge --fortune
Life is just a bowl of cherries, but why do I always get the pits?
hacker@man~reading-manuals:/$ /challenge/challenge --tbwgvr NUM
Incorrect usage! Please read the challenge man page!
hacker@man~reading-manuals:/$ /challenge/challenge --tbwgvr 612
Correct usage! Your flag: pwn.college{QtbWZwD6gv1rqCMF2wHbqoUe3b7.dRTM4QDLwMjN0czW}
```

This is how I solved it.
