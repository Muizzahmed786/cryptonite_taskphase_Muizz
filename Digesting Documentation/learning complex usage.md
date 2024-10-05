# Learning Complex Usage

The description asks me to document `/challenge/challenge` and print the arbitrary files to the termiinal using `--printfile` as an argument.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@man~learning-complex-usage:~$ cd /
hacker@man~learning-complex-usage:/$ ls
bin  boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@man~learning-complex-usage:/$ /challenge/challenge --printfile
You must pass a file for --printfile to read!
hacker@man~learning-complex-usage:/$ /challenge/challenge --printfile flag
Correct argument! Here is the flag file:
pwn.college{4KWWmUNRycQPNyTCFnUG21mzqK4.dVjM5QDLwMjN0czW}
hacker@man~learning-complex-usage:/$
```

This is how I solved it. 
We need to pass a file to the `--printfile` to get the flag.
`flag` file acts itself as an argument to `--printfile`.
