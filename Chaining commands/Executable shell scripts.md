# Executable shell scripts

The description asks us to create a shellscript that invokes `/challenge/solve` and we also have to make it executable and run it without invoking `bash`.
To make the file executable we have to permissions of user,group,others with the help of `chmod` command and `a+x` as an argument to it.
After that we have to run it without `bash`.
This can be done using the absolute path of the shellscript.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@chaining~executable-shell-scripts:~$ nano script.sh
hacker@chaining~executable-shell-scripts:~$ cat script.sh
/challenge/solve

hacker@chaining~executable-shell-scripts:~$ ls -l script.sh
-rw-r--r-- 1 hacker hacker 18 Oct 16 16:02 script.sh
hacker@chaining~executable-shell-scripts:~$ chmod a+x script.sh
hacker@chaining~executable-shell-scripts:~$ ls -l script.sh
-rwxr-xr-x 1 hacker hacker 18 Oct 16 16:02 script.sh
hacker@chaining~executable-shell-scripts:~$ ~/script.sh
You must make a shellscript in your home directory that will launch
/challenge/solve, make it executable, and invoke it without explicitly
specifying 'bash'!
hacker@chaining~executable-shell-scripts:~$ ./script.sh
Congratulations on your shell script execution! Your flag:
pwn.college{U0VPFGyGtrmo3LWWgzvSG9xUxbu.dRzNyUDLwMjN0czW}
hacker@chaining~executable-shell-scripts:~$
```

This is how I solved it.
