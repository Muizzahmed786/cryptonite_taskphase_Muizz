# Learning from documentation

The description asks me to document `/challenge/challenge` by giving the arguement `--giveflag`.

```bash
Connection to dojo.pwn.college closed.
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@man~learning-from-documentation:~$ cd /
hacker@man~learning-from-documentation:/$ ls
bin  boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@man~learning-from-documentation:/$ /challenge/challenge --giveflag
Correct argument! Here is your flag:
pwn.college{gAwP-MIuEeTiQ8Qmc7DyKQOVRXW.dRjM5QDLwMjN0czW}
hacker@man~learning-from-documentation:/$
```

This is how is solved it.
