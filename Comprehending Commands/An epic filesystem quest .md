# An Epic Filesystem Quest

The description aks me to find the flag hidden in some random files and follow the clues along the way to reach the flag.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@commands~an-epic-filesystem-quest:~$ cd /
hacker@commands~an-epic-filesystem-quest:/$ ls
MESSAGE  boot       dev  flag  lib    lib64   media  nix  proc  run   srv  tmp  var
bin      challenge  etc  home  lib32  libx32  mnt    opt  root  sbin  sys  usr
hacker@commands~an-epic-filesystem-quest:/$ cat MESSAGE
Congratulations, you found the clue!
The next clue is in: /usr/share/doc/python3-ppl

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/$ ls /usr/share/doc/python3-ppl
README.rst  changelog.Debian.gz  copyright  html
hacker@commands~an-epic-filesystem-quest:/$ ls -a  /usr/share/doc/python3-ppl
.  ..  .SPOILER  README.rst  changelog.Debian.gz  copyright  html
hacker@commands~an-epic-filesystem-quest:/$ cat /usr/share/doc/python3-ppl/.SPOILER
Great sleuthing!
The next clue is in: /opt/aflplusplus/qemu_mode/qemuafl/linux-user/host/x86_64

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/$ ^C
hacker@commands~an-epic-filesystem-quest:/$ ls -a /usr/share/doc/python3-ppl
.  ..  .SPOILER  README.rst  changelog.Debian.gz  copyright  html
hacker@commands~an-epic-filesystem-quest:/$ ls -a /opt/aflplusplus/qemu_mode/qemuafl/linux-user/host/x86_64
.  ..  GIST-TRAPPED  hostdep.h  safe-syscall.inc.S
hacker@commands~an-epic-filesystem-quest:/$ cat /opt/aflplusplus/qemu_mode/qemuafl/linux-user/host/x86_64/GIST-TRAPPED
Congratulations, you found the clue!
The next clue is in: /usr/share/rubygems-integration/all/gems/test-unit-3.3.5/lib/test/unit/ui/emacs

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/$ cd /usr/share/rubygems-integration/all/gems/test-unit-3.3.5/lib/test/unit/ui/emacs
hacker@commands~an-epic-filesystem-quest:/usr/share/rubygems-integration/all/gems/test-unit-3.3.5/lib/test/unit/ui/emacs$ ls -a
.  ..  BLUEPRINT  testrunner.rb
hacker@commands~an-epic-filesystem-quest:/usr/share/rubygems-integration/all/gems/test-unit-3.3.5/lib/test/unit/ui/emacs$ cat BLUEPATH
cat: BLUEPATH: No such file or directory
hacker@commands~an-epic-filesystem-quest:/usr/share/rubygems-integration/all/gems/test-unit-3.3.5/lib/test/unit/ui/emacs$ cat BLUEPRINT
Great sleuthing!
The next clue is in: /usr/lib/python3/dist-packages/sympy/vector
hacker@commands~an-epic-filesystem-quest:/usr/share/rubygems-integration/all/gems/test-unit-3.3.5/lib/test/unit/ui/emacs$ cd /usr/lib/python3/dist-packages/sympy/vector
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/sympy/vector$ ls /usr/lib/python3/dist-packages/sympy/vector
DISPATCH     __pycache__        coordsysrect.py  dyadic.py     operators.py  point.py   tests
__init__.py  basisdependent.py  deloperator.py   functions.py  orienters.py  scalar.py  vector.py
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/sympy/vector$ cat /usr/lib/python3/dist-packages/sympy/vector/DISPATCH
Congratulations, you found the clue!
The next clue is in: /usr/share/javascript/mathjax/unpacked/jax/output/HTML-CSS/fonts/Neo-Euler/Size2/Regular

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/sympy/vector$ ls /usr/share/javascript/mathjax/unpacked/jax/output/HTML-CSS/fonts/Neo-Euler/Size2/Regular
Main.js  TIP-TRAPPED
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/sympy/vector$ cat /usr/share/javascript/mathjax/unpacked/jax/output/HTML-CSS/fonts/Neo-Euler/Size2/Regular/TIP-TRAPPED
Congratulations, you found the clue!
The next clue is in: /usr/share/racket/pkgs/slideshow
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/sympy/vector$ cd /usr/share/racket/pkgs/slideshow
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/slideshow$ ls
LICENSE.txt  NUGGET  info.rkt
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/slideshow$ cat NUGGET
Congratulations, you found the clue!
The next clue is in: /usr/share/racket/pkgs/2d-lib/private

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/slideshow$ cd /usr/share/racket/pkgs/2d-lib/private
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/2d-lib/private$ ls
TEASER  compiled  lexer.rkt  read-util.rkt  readtable.rkt
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/2d-lib/private$ cat TEASER
Tubular find!
The next clue is in: /usr/share/racket/pkgs/redex-pict-lib/redex/compiled

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/2d-lib/private$ ls /usr/share/racket/pkgs/redex-pict-lib/redex/compiled
SNIPPET-TRAPPED  pict_rkt.dep  pict_rkt.zo
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/2d-lib/private$ cat /usr/share/racket/pkgs/redex-pict-lib/redex/compiled/SNIPPET
-TRAPPED
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{YSXvbOOf5Eel-1amFhAYuvYr2J8.dljM4QDLwMjN0czW}
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/2d-lib/private$
```

This is how I solved it.

i got to know that we can change our working directory without using command `cd`.
This can be done by using `cat` directory_name/file_name.
