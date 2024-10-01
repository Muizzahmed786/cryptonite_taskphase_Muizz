# position thyself

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@paths~position-thy-self:~$ cd /
hacker@paths~position-thy-self:/$ ls
bin  boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@paths~position-thy-self:/$ /challenge/run
Incorrect...
You are not currently in the /var/lib/apt/lists directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-thy-self:/$ cd /var/lib/apt/lists
hacker@paths~position-thy-self:/var/lib/apt/lists$ ls/challenge/run
ssh-entrypoint: ls/challenge/run: No such file or directory
hacker@paths~position-thy-self:/var/lib/apt/lists$
hacker@paths~position-thy-self:/var/lib/apt/lists$ ls/challenge/run
ssh-entrypoint: ls/challenge/run: No such file or directory
hacker@paths~position-thy-self:/var/lib/apt/lists$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{4anC42N9giILTMpfoxONTPFewJS.dZDN1QDLwMjN0czW}
```
this is how i solved it.
first we use the cd command to navigate directories. Then use the ls command to list the directory files. 
