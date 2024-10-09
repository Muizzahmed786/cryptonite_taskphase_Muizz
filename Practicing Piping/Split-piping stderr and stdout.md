# Writing to multiple programs

The description asks us to redirect `/challenge/hack` stderr to `/challenge/the` and stdout to `/challenge/planet`.
This can be done by using `|`, `2>()`.
we have to use `2>()` before `|`, otherwise `/challenge/planet` stderr will redirected to `/challenge/the`. This we don't want to happen.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack | /challenge/planet 2> /challenge/the
ssh-entrypoint: /challenge/the: Permission denied
You must redirect my standard error into '/challenge/the'!
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack | /challenge/planet 2> > /challenge/the
ssh-entrypoint: syntax error near unexpected token `>'
hacker@piping~split-piping-stderr-and-stdout:~$ exit
exit

Connected!
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack | /challenge/planet 2>&1 /challenge/the
You must redirect my standard error into '/challenge/the'!
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack | /challenge/planet 2> >(/challenge/the)
You must redirect my standard error into '/challenge/the'!
You are redirecting standard error *of /challenge/planet*! Instead, you must
redirect standard error of 'hack'. This must be done *before* any |. The right
side of the pipe is a different command, with its own redirection, than the
left side!
Are you sure you're properly redirecting /challenge/hack's standard error into
'/challenge/the'?
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack | tee /challenge/planet 2> >(/challenge/the)
This secret data must directly make it to /challenge/planet over my stdout.
Don't try to copy-paste it; it changes too fast.
2733096542689414519
You must redirect my standard error into '/challenge/the'!
Are you sure you're properly redirecting /challenge/hack's standard error into
'/challenge/the'?
hacker@piping~split-piping-stderr-and-stdout:~$ exit
exit

Connected!
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack | /challenge/planet 2>&1 | /challenge/the
You must redirect my standard error into '/challenge/the'!
You are redirecting standard error *of /challenge/planet*! Instead, you must
redirect standard error of 'hack'. This must be done *before* any |. The right
side of the pipe is a different command, with its own redirection, than the
left side!
Are you sure you're properly redirecting /challenge/hack's standard error into
'/challenge/the'?
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack 2> /challenge/the
ssh-entrypoint: /challenge/the: Permission denied
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack | /challenge/planet >(2>&1 /challenge/the)
You must redirect my standard error into '/challenge/the'!
Are you sure you're properly redirecting /challenge/hack's standard error into
'/challenge/the'?
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack 2>&1 /challenge/the
You must redirect my standard output into '/challenge/planet'!
You must redirect my standard error into '/challenge/the'!
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack | /challenge/planet 2> | /challenge/the
ssh-entrypoint: syntax error near unexpected token `|'
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack | >(2>&1 | /challenge/the)
ssh-entrypoint: /dev/fd/63: Permission denied
Are you sure you're properly redirecting /challenge/hack's standard error into
'/challenge/the'?
You must redirect my standard error into '/challenge/the'!
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack | /challenge/planet 2> >(/challenge/the)
You must redirect my standard error into '/challenge/the'!
You are redirecting standard error *of /challenge/planet*! Instead, you must
redirect standard error of 'hack'. This must be done *before* any |. The right
side of the pipe is a different command, with its own redirection, than the
left side!
Are you sure you're properly redirecting /challenge/hack's standard error into
'/challenge/the'?
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack 2> /challenge/the | /challenge/planet
ssh-entrypoint: /challenge/the: Permission denied
Are you sure you're properly redirecting /challenge/hack's standard output into
'/challenge/planet'?
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack | /challenge/planet 2> >(/challenge/the)
You must redirect my standard error into '/challenge/the'!
You are redirecting standard error *of /challenge/planet*! Instead, you must
redirect standard error of 'hack'. This must be done *before* any |. The right
side of the pipe is a different command, with its own redirection, than the
left side!
Are you sure you're properly redirecting /challenge/hack's standard error into
'/challenge/the'?
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack 2> >(/challenge/the) | /challenge/planet
Congratulations, you have learned a redirection technique that even experts
struggle with! Here is your flag:
pwn.college{sLus6I60735lOUaq1HccLWBrJwV.dFDNwYDLwMjN0czW}
hacker@piping~split-piping-stderr-and-stdout:~$
```

This is how I solved it.
