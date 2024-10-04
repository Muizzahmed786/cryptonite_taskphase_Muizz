# Touching Files

The description asks us to use the `touch` command to create files namely `pwn` and `college`

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@commands~touching-files:~$ cd /
hacker@commands~touching-files:/$ ls
bin  boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@commands~touching-files:/$ cd /tmp
hacker@commands~touching-files:/tmp$ touch pwn
hacker@commands~touching-files:/tmp$ touch college
hacker@commands~touching-files:/tmp$ ls
bin  college  hsperfdata_root  pwn  tmp.XvrUsDZh8M
hacker@commands~touching-files:/tmp$ /challenge/run
Success! Here is your flag:
pwn.college{E2HF5m6opT7VQSmFVkDD1Q1kI7e.dBzM4QDLwMjN0czW}
hacker@commands~touching-files:/tmp$
```

This is how I solved it.
