# Home sweet Home
description asks me to specify an argument to `/challenge/run` to get a copy of the flag with the following constraints:-
1.) Your argument must be an absolute path.
2.) The path must be inside your home directory.
3.) Before expansion, your argument must be three characters or less.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@paths~home-sweet-home:~$ cd /
hacker@paths~home-sweet-home:/$ ls
bin   challenge  etc   home  lib32  libx32  mnt  opt   root  sbin  sys  usr
boot  dev        flag  lib   lib64  media   nix  proc  run   srv   tmp  var
hacker@paths~home-sweet-home:/$ cd ~
hacker@paths~home-sweet-home:~$ /challenge/run ~/r
Writing the file to /home/hacker/r!
... and reading it back to you:
pwn.college{88WWBLGjpFg177tgfD218MBfGdI.dNzM4QDLwMjN0czW}
hacker@paths~home-sweet-home:~$
```
This is how I solved. 
