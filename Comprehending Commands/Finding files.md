# Finding files

The description asks us to find the `flag` file.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@commands~finding-files:~$ cd /
hacker@commands~finding-files:/$ ls
bin  boot  challenge  dev  etc  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@commands~finding-files:/$ cd /challenge
hacker@commands~finding-files:/challenge$ ls
DESCRIPTION.md  run
hacker@commands~finding-files:/challenge$ find -name flag
hacker@commands~finding-files:/challenge$ cd /run
hacker@commands~finding-files:/run$ ls
apache2    current-system  firefox-restart-required  log    mysqld  sendsigs.omit.d  sudo     user  workspace
challenge  dojo            lock                      mount  screen  shm              systemd  utmp
hacker@commands~finding-files:/run$ find -name flag
find: ‘./mysqld’: Permission denied
find: ‘./sudo’: Permission denied
hacker@commands~finding-files:/run$ cd /tmp
lshacker@commands~finding-files:/tmp$ ls
bin  hsperfdata_root  tmp.XvrUsDZh8M
hacker@commands~finding-files:/tmp$ find -name flag
find: ‘./tmp.XvrUsDZh8M’: Permission denied
hacker@commands~finding-files:/tmp$ cd /usr
hacker@commands~finding-files:/usr$ ls
aarch64-linux-gnu  bin  games  include  lib  lib32  lib64  libexec  libx32  local  sbin  share  src
hacker@commands~finding-files:/usr$ find -name flag
./local/lib/python3.8/dist-packages/pwnlib/flag
./local/share/radare2/5.9.5/flag
./share/man/ko/man1/flag
hacker@commands~finding-files:/usr$ cat ./local/lib/python3.8/dist-packages/pwnlib/flag
cat: ./local/lib/python3.8/dist-packages/pwnlib/flag: Is a directory
hacker@commands~finding-files:/usr$ cat ./local/share/radare2/5.9.5/flag
cat: ./local/share/radare2/5.9.5/flag: Is a directory
hacker@commands~finding-files:/usr$ cat ./share/man/ko/man1/flag
pwn.college{UYLnfqkmRoJDua8yWvYkxs7Y0Ol.dJzM4QDLwMjN0czW}
```

This is how I found the `flag` file.
