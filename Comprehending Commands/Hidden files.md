# Hidden Files

The description asks us to find a hidden dot prepended file in `/` to get the flag.
for this we need to invoke `ls` with `-a`.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@commands~hidden-files:~$ cd /
hacker@commands~hidden-files:/$ ls -a
.   .dockerenv            bin   challenge  etc   lib    lib64   media  nix  proc  run   srv  tmp  var
..  .flag-23582191782180  boot  dev        home  lib32  libx32  mnt    opt  root  sbin  sys  usr
hacker@commands~hidden-files:/$ cat .dockerenv
hacker@commands~hidden-files:/$ grep pwn.college .flag-23582191782180
pwn.college{gseFO_nux_pv8K4AiVM7qloEWCv.dBTN4QDLwMjN0czW}
hacker@commands~hidden-files:/$
```

This is how I solved it.
