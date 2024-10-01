#Implicit Relative Paths

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@paths~implicit-relative-paths-from-:~$ cd /
hacker@paths~implicit-relative-paths-from-:/$ las
ssh-entrypoint: las: command not found
hacker@paths~implicit-relative-paths-from-:/$ ls
bin  boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{s9Tap8YmtT-N2FC-a9vwT_NrKEi.dlDN1QDLwMjN0czW}
hacker@paths~implicit-relative-paths-from-:/$
```

This is how I solved it.
i got to know that to access the relative paths, we don't need `/` while mentioning the path.
