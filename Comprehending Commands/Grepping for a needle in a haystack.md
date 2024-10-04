# Grepping for a needle in a haystack

The description asks us to use the command `grep` on the file `/challenge/data.txt` to get the flag.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ cd /
hacker@commands~grepping-for-a-needle-in-a-haystack:/$ ls
bin  boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@commands~grepping-for-a-needle-in-a-haystack:/$ grep pwn.college /challenge/data.txt
pwn.college{QA0do4J-CFo42di5tV3Dbc9lOyO.ddTM4QDLwMjN0czW}
hacker@commands~grepping-for-a-needle-in-a-haystack:/$
```

This is how I solved it

`grep` command is used to find the lines or content we need.
In this case we need to get the flag which starts with `pwn.college`.
