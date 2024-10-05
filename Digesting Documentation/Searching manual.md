# Searching Manuals

the description asks us to find the flag in the manpage `challenge` using `man` command.
It suggests us some methods by which we can look for the flag.
use `/` to search for any occurence and navigate back and forth using `n` and `N` respectively.

```bash
Connected!
hacker@man~searching-manuals:~$ cd /
hacker@man~searching-manuals:/$ ls
bin  boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@man~searching-manuals:/$ man challenge
hacker@man~searching-manuals:/$ /challenge/challenge --kxof
Initializing...
Correct usage! Your flag: pwn.college{0v95j5mqmdOrBnwpZvhi2nr0qVK.dVTM4QDLwMjN0czW}
hacker@man~searching-manuals:/$
```

This is how i solved it.
