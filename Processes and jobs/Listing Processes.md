# Listing processes

The description asks me to use the `ps` command to list the running processes. For this challenge we have find find a file which is renamed and can be found using `ps -ef` or `ps aux`.
we can use `ps -ef` or `ps aux`, the difference will be that `ps -ef` will also show the PPID (Parent process ID).

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@processes~listing-processes:~$ ps -ef
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 10:44 ?        00:00:00 /sbin/docker-init -- /nix/var/nix/profiles/default/bin/dojo-init /run/dojo/bin/sleep 6h
root           7       1  0 10:44 ?        00:00:00 /run/dojo/bin/sleep 6h
root          68       1  0 10:44 ?        00:00:00 /challenge/7324-run-18844
root          72      68  0 10:44 ?        00:00:00 sleep 6h
hacker        97       0  1 10:45 pts/0    00:00:00 /run/dojo/bin/ssh-entrypoint
hacker       114      97  0 10:45 pts/0    00:00:00 ps -ef
hacker@processes~listing-processes:~$ cat /challenge/7324-run-18844
#!/opt/pwn.college/bash

if [ -z "$DOIT" ]
then
        export DOIT=yes
        exec -a $0 bash < $0
fi

echo "Yahaha, you found me! Here is your flag:"
cat /flag
echo "Now I will sleep for a while (so that you could find me with 'ps')."
sleep 6h
hacker@processes~listing-processes:~$ cat /flag
cat: /flag: Permission denied
hacker@processes~listing-processes:~$ ps aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.0  0.0   1056   640 ?        Ss   10:44   0:00 /sbin/docker-init -- /nix/var/nix/profiles/default/bin/dojo-init /run/dojo/bin/sleep 6h
root           7  0.0  0.0   5052  2560 ?        S    10:44   0:00 /run/dojo/bin/sleep 6h
root          68  0.0  0.0   4132  2560 ?        S    10:44   0:00 /challenge/7324-run-18844
root          72  0.0  0.0   2744  1600 ?        S    10:44   0:00 sleep 6h
hacker        97  0.0  0.0   5364  4160 pts/0    Ss   10:45   0:00 /run/dojo/bin/ssh-entrypoint
hacker       117  0.0  0.0   7868  3200 pts/0    R+   10:47   0:00 ps aux
hacker@processes~listing-processes:~$ /challenge/7324-run-18844
Yahaha, you found me! Here is your flag:
pwn.college{IvD1m1VGjSCb44YHB2baPQzQwvr.dhzM4QDLwMjN0czW}
Now I will sleep for a while (so that you could find me with 'ps').
```

This is how I solved it.

One mistake I was doing while solving was that i was using the cat command to read the renamed file to get the flag.
I had to directly run the given file, which is in this case `/challenge/7324-run-18844`.
