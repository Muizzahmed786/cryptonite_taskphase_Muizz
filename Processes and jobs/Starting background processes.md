# Starting background processes

The description asks us to run `/challenge/run` in the background.
This can be done by using `&`.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@processes~starting-backgrounded-processes:~$ /challenge/run &
[1] 107



Yay, you started me in the background! Because of that, this text will probably
overlap weirdly with the shell prompt, but you're used to that by now...

Anyways! Here is your flag!
pwn.college{k5D1wkmFEMQEuuoNc14f4ypnLpm.dlDN4QDLwMjN0czW}
[1]+  Done                    /challenge/run
hacker@processes~starting-backgrounded-processes:~$
```

This is how I solved it.
