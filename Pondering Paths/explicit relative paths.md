# Explicit Relative Paths

The description wants me to use `.` in my relative paths.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@paths~explicit-relative-paths-from-:~$ cd /
hacker@paths~explicit-relative-paths-from-:/$ ls
bin  boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@paths~explicit-relative-paths-from-:/$ challenge
ssh-entrypoint: challenge: command not found
hacker@paths~explicit-relative-paths-from-:/$ ./challenge
ssh-entrypoint: ./challenge: Is a directory
hacker@paths~explicit-relative-paths-from-:/$ ././challenge
ssh-entrypoint: ././challenge: Is a directory
hacker@paths~explicit-relative-paths-from-:/$ ./././challenge/run
Correct!!!
./././challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{A55SCu25ueD9wzNoDzy8pprKrN8.dBTN1QDLwMjN0czW}
hacker@paths~explicit-relative-paths-from-:/$
```

This is how I solved it.

I got to know that whether we use `./` or `././`, these both represent the same directory.
