# The SUID bit

The description asks us to add the SUID bit `s` to the program `/challenge/getroot` in order to spawn a root shell.
This can be done by using `chmod` command and adding the SUID bit to the user i.e. `u+s`.
After this, if we run `/challenge/getroot` program it will run as root, and now we can use `cat` on `/flag` to get the flag.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@permissions~the-suid-bit:~$ chmod u+s /challenge/getroot
hacker@permissions~the-suid-bit:~$ ls -l /challenge/getroot
-rwsr-xr-x 1 root root 155 Jul 12 10:30 /challenge/getroot
hacker@permissions~the-suid-bit:~$ cat /challenge/getroot
#!/opt/pwn.college/bash

fold -s <<< "SUCCESS! You have set the suid bit on this program, and it is running as root! Here is your shell..."
exec /bin/bash
hacker@permissions~the-suid-bit:~$ grep pwn.college /bin/bash
hacker@permissions~the-suid-bit:~$ cat /flag
cat: /flag: Permission denied
hacker@permissions~the-suid-bit:~$ whoami
hacker
hacker@permissions~the-suid-bit:~$ chmod a+r /challenge/getroot
hacker@permissions~the-suid-bit:~$ ls -l /challenge/getroot
-rwsr-xr-x 1 root root 155 Jul 12 10:30 /challenge/getroot
hacker@permissions~the-suid-bit:~$ cat /flag
cat: /flag: Permission denied
hacker@permissions~the-suid-bit:~$ /challenge/getroot
SUCCESS! You have set the suid bit on this program, and it is running as root!
Here is your shell...
root@permissions~the-suid-bit:~# whoami
root
root@permissions~the-suid-bit:~# cat /flag
pwn.college{0cg3EW4gSJtztzQdU67S0aFKNPz.dNTM2QDLwMjN0czW}
root@permissions~the-suid-bit:~#
```

This  is how I solved it.
