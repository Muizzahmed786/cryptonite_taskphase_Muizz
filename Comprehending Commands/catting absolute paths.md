# Catting Absolute Paths

the description asks me to run the `cat` command and specify it's argument as an absolute path.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@commands~catting-absolute-paths:~$ cd /
hacker@commands~catting-absolute-paths:/$ ls
bin  boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@commands~catting-absolute-paths:/$ cat /flag
pwn.college{MxSiacrTtCyC82J9hY1j4c1sAZC.dlTM5QDLwMjN0czW}
hacker@commands~catting-absolute-paths:/$
```

This is how i solved it.
