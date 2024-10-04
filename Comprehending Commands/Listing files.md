# Listing Files

The description asks us to use the `ls` command which is used to list out files from a directory.
we need to find the file in the `/challenge/run` which is renanmed with random name.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@commands~listing-files:~$ cd /
hacker@commands~listing-files:/$ ls
bin  boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@commands~listing-files:/$ ls /challenge
31410-renamed-run-23646  DESCRIPTION.md
hacker@commands~listing-files:/$ ls /challenge/DESCRIPTION.md
/challenge/DESCRIPTION.md
hacker@commands~listing-files:/$ /challenge/31410-renamed-run-23646  DESCRIPTION.md
Yahaha, you found me! Here is your flag:
pwn.college{YVdNGCbfC-M4l4rfp7x_ZSlhyP8.dhjM4QDLwMjN0czW}
hacker@commands~listing-files:/$
```

This is how i solved it.
