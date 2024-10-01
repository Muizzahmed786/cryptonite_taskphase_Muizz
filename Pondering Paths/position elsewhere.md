# Position Elsewhere

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@paths~position-elsewhere:~$ cd /
hacker@paths~position-elsewhere:/$ ls
bin  boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@paths~position-elsewhere:/$ /challenge/run
Incorrect...
You are not currently in the /usr/share/build-essential directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-elsewhere:/$ cd /usr/share/build-essential
hacker@paths~position-elsewhere:/usr/share/build-essential$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{cojRbmLWijGVlS3KYFSbRLNvwlH.ddDN1QDLwMjN0czW}
```

This is how I solved it.
We use the `cd` command to navigate through the directories. Then use the `ls` command to select a file from the directory. 
If we press enter, it will show us that we currently not in the desired directory. 
Now Use the `cd` command with name of the directory.
We will get the flag.
