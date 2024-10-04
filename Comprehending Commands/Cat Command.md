# Cat: not the pet, but the command

The description asks me to read the `flag` file with he help of `cat` command.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@commands~cat-not-the-pet-but-the-command:~$ cat file
cat: file: No such file or directory
hacker@commands~cat-not-the-pet-but-the-command:~$ cd /
hacker@commands~cat-not-the-pet-but-the-command:/$
hacker@commands~cat-not-the-pet-but-the-command:/$ ls
bin   challenge  etc   home  lib32  libx32  mnt  opt   root  sbin  sys  usr
boot  dev        flag  lib   lib64  media   nix  proc  run   srv   tmp  var
hacker@commands~cat-not-the-pet-but-the-command:/$ cat flag
pwn.college{0TcmTl00JzF5FM6McMRhWsGbtja.dFzN1QDLwMjN0czW}
hacker@commands~cat-not-the-pet-but-the-command:/$
```

This is how i solved it.

`cat` is often used for reading out files. 
First we go the root directory and list out the files present in that directory.
After that we use the `cat` command to read the`flag` file to get the flag.
