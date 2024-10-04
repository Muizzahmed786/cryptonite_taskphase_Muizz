# Removing Files.md

The description asks us to use the `rm` command to delete `delete_me` file.
and check whether the deletion was succesful or not.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@commands~removing-files:~$ cd /
hacker@commands~removing-files:/$ ls
bin  boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@commands~removing-files:/$ touch delete_me
touch: cannot touch 'delete_me': Permission denied
hacker@commands~removing-files:/$ cd ~
hacker@commands~removing-files:~$ ls
Desktop  delete_me  h  r
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
pwn.college{o9sm_sOeoa8gyku9pAP5dGU_aGE.dZTOwUDLwMjN0czW}
hacker@commands~removing-files:~$
```

This is how I solved it.
