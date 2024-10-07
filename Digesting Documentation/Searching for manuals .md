# Searching for Manuals

The descriptions asks us to to read the `man` manpage to serach for the right man page to find how to get the flag.

```bash
ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@man~searching-for-manuals:~$ man man
MAN(1)                                            Manual pager utils                                           MAN(1)

NAME
       man - an interface to the system reference manuals

SYNOPSIS
       man [man options] [[section] page ...] ...
       man -k [apropos options] regexp ...
       man -K [man options] [section] term ...
       man -f [whatis options] page ...
       man -l [man options] file ...
       man -w|-W [man options] page ...

DESCRIPTION
       man  is the system's manual pager.  Each page argument given to man is normally the name of a program, utility
       or function.  The manual page associated with each of these arguments is then found and displayed.  A section,
       if  provided,  will direct man to look only in that section of the manual.  The default action is to search in
       all of the available sections following a pre-defined order (see DEFAULTS), and to show only  the  first  page
       found, even if page exists in several sections.

       The table below shows the section numbers of the manual followed by the types of pages they contain.

       1   Executable programs or shell commands
       2   System calls (functions provided by the kernel)
       3   Library calls (functions within program libraries)
       4   Special files (usually found in /dev)
       5   File formats and conventions, e.g. /etc/passwd
       6   Games
       7   Miscellaneous (including macro packages and conventions), e.g. man(7), groff(7)
       8   System administration commands (usually only for root)
       9   Kernel routines [Non standard]

       A manual page consists of several sections.

       Conventional  section  names  include  NAME,  SYNOPSIS,  CONFIGURATION, DESCRIPTION, OPTIONS, EXIT STATUS, RE‐
       TURN VALUE, ERRORS, ENVIRONMENT, FILES, VERSIONS, CONFORMING TO, NOTES, BUGS, EXAMPLE, AUTHORS, and SEE ALSO.

       The following conventions apply to the SYNOPSIS section and can be used as a guide in other sections.

       bold text          type exactly as shown.
       italic text        replace with appropriate argument.
       [-abc]             any or all arguments within [ ] are optional.
       -a|-b              options delimited by | cannot be used together.
       argument ...       argument is repeatable.
       [expression] ...   entire expression within [ ] is repeatable.

       Exact rendering may vary depending on the output device.  For instance, man will usually not be able to render
       italics when running in a terminal, and will typically use underlined or coloured text instead.

       The  command  or function illustration is a pattern that should match all possible invocations.  In some cases
       it is advisable to illustrate several exclusive invocations as is shown in the SYNOPSIS section of this manual
       page.

EXAMPLES
       man ls
           Display the manual page for the item (program) ls.

       man man.7
           Display  the manual page for macro package man from section 7.  (This is an alternative spelling of "man 7
           man".)

       man 'man(7)'
           Display the manual page for macro package man from section 7.  (This is another  alternative  spelling  of
           "man  7  man".  It may be more convenient when copying and pasting cross-references to manual pages.  Note
           that the parentheses must normally be quoted to protect them from the shell.)

       man -a intro
           Display, in succession, all of the available intro manual pages contained within the manual.  It is possi‐
           ble to quit between successive displays or skip any of them.

       man -t bash | lpr -Pps
           Format  the  manual  page for bash into the default troff or groff format and pipe it to the printer named
           ps.  The default output for groff is usually PostScript.  man --help should advise as to  which  processor
           is bound to the -t option.

       man -l -Tdvi ./foo.1x.gz > ./foo.1x.dvi
           This command will decompress and format the nroff source manual page ./foo.1x.gz into a device independent
           (dvi) file.  The redirection is necessary as the -T flag causes output to be directed to  stdout  with  no
           pager.   The output could be viewed with a program such as xdvi or further processed into PostScript using
           a program such as dvips.

       man -k printf
           Search the short descriptions and manual page names for the keyword printf as regular  expression.   Print
           out any matches.  Equivalent to apropos printf.

       man -f smail
           Lookup the manual pages referenced by smail and print out the short descriptions of any found.  Equivalent
           to whatis smail.

OVERVIEW
       Many options are available to man in order to give as much flexibility as possible to the user.   Changes  can
       be  made to the search path, section order, output processor, and other behaviours and operations detailed be‐
       low.

       If set, various environment variables are interrogated to determine the operation of man.  It is  possible  to
       set  the "catch-all" variable $MANOPT to any string in command line format, with the exception that any spaces
       used as part of an option's argument must be escaped (preceded by a backslash).  man will parse $MANOPT  prior
       to  parsing  its own command line.  Those options requiring an argument will be overridden by the same options
       found on the command line.  To reset all of the options set in $MANOPT, -D can be  specified  as  the  initial
       command  line  option.   This will allow man to "forget" about the options specified in $MANOPT, although they
       must still have been valid.

       Manual pages are normally stored in nroff(1) format under a directory such as /usr/share/man.  In some instal‐
       lations, there may also be preformatted cat pages to improve performance.  See manpath(5) for details of where
       these files are stored.

       This package supports manual pages in multiple languages, controlled by your locale.  If your system  did  not
       set  this  up for you automatically, then you may need to set $LC_MESSAGES, $LANG, or another system-dependent
       environment variable to indicate your preferred locale, usually specified in the POSIX format:

       <language>[_<territory>[.<character-set>[,<version>]]]

       If the desired page is available in your locale, it will be displayed in lieu of the standard (usually  Ameri‐
       can English) page.

       If you find that the translations supplied with this package are not available in your native language and you
       would like to supply them, please contact the maintainer who will be coordinating such activity.

       Individual manual pages are normally written and maintained by the maintainers of the  program,  function,  or
       other  topic  that  they  document, and are not included with this package.  If you find that a manual page is
       missing or inadequate, please report that to the maintainers of the package in question.

       For information regarding other features and extensions available with this manual pager, please read the doc‐
       uments supplied with the package.

DEFAULTS
       The  order  of sections to search may be overridden by the environment variable $MANSECT or by the SECTION di‐
       rective in /etc/manpath.config.  By default it is as follows:

              1 n l 8 3 2 3posix 3pm 3perl 3am 5 4 9 6 7

       The formatted manual page is displayed using a pager.  This can be specified in a number of ways, or else will
       fall back to a default (see option -P for details).

       The filters are deciphered by a number of means.  Firstly, the command line option -p or the environment vari‐
       able $MANROFFSEQ is interrogated.  If -p was not used and the environment variable was not  set,  the  initial
       line of the nroff file is parsed for a preprocessor string.  To contain a valid preprocessor string, the first
       line must resemble

       '\" <string>

       where string can be any combination of letters described by option -p below.

       If none of the above methods provide any filter information, a default set is used.

       A formatting pipeline is formed from the filters and the primary formatter (nroff or [tg]roff with -t) and ex‐
       ecuted.   Alternatively,  if  an  executable program mandb_nfmt (or mandb_tfmt with -t) exists in the man tree
       root, it is executed instead.  It gets passed the manual source file, the preprocessor string, and  optionally
       the device specified with -T or -E as arguments.

OPTIONS
       Non-argument  options  that  are  duplicated either on the command line, in $MANOPT, or both, are not harmful.
       For options that require an argument, each duplication will override the previous argument value.

   General options
       -C file, --config-file=file
              Use this user configuration file rather than the default of ~/.manpath.

       -d, --debug
              Print debugging information.

       -D, --default
              This option is normally issued as the very first option and resets man's behaviour to its default.  Its
              use  is to reset those options that may have been set in $MANOPT.  Any options that follow -D will have
              their usual effect.

       --warnings[=warnings]
              Enable warnings from groff.  This may be used to perform sanity checks on the  source  text  of  manual
              pages.   warnings  is  a  comma-separated  list of warning names; if it is not supplied, the default is
              "mac".  See the “Warnings” node in info groff for a list of available warning names.

   Main modes of operation
       -f, --whatis
              Equivalent to whatis.  Display a short description from the manual page, if available.   See  whatis(1)
              for details.

       -k, --apropos
              Equivalent to apropos.  Search the short manual page descriptions for keywords and display any matches.
              See apropos(1) for details.

       -K, --global-apropos
              Search for text in all manual pages.  This is a brute-force search, and is likely to take some time; if
              you  can,  you should specify a section to reduce the number of pages that need to be searched.  Search
              terms may be simple strings (the default), or regular expressions if the --regex option is used.

              Note that this searches the sources of the manual pages, not the rendered  text,  and  so  may  include
              false positives due to things like comments in source files.  Searching the rendered text would be much
              slower.

       -l, --local-file
              Activate "local" mode.  Format and display local manual files instead of searching through the system's
hacker@man~searching-for-manuals:~$ man -k challenge
oxvydwjcza (1)       - print the flag!
hacker@man~searching-for-manuals:~$ man oxyvydwjcza
No manual entry for oxyvydwjcza
hacker@man~searching-for-manuals:~$ oxvydwjcza
ssh-entrypoint: oxvydwjcza: command not found
hacker@man~searching-for-manuals:~$ man oxvydwjcza

CHALLENGE(1)                                                       Challenge Commands                                                       CHALLENGE(1)

NAME
       /challenge/challenge - print the flag!

SYNOPSIS
       challenge OPTION

DESCRIPTION
       Output the flag when called with the right arguments.

       --fortune
              read a fortune

       --version
              output version information and exit

       --oxvydw NUM
              print the flag if NUM is 466

AUTHOR
       Written by Zardus.

REPORTING BUGS
       The repository for this dojo: <https://github.com/pwncollege/linux-luminarium/>

SEE ALSO
       man(1) bash-builtins(7)

pwn.college                                                             May 2024                                                            CHALLENGE(1)
hacker@man~searching-for-manuals:~$ /challenge/challenge --oxvydw 466
Correct usage! Your flag: pwn.college{MLoxDU4HWL-RMXEvDyC6N6XL-7W.dZTM4QDLwMjN0czW}
hacker@man~searching-for-manuals:~$
```

This is how I solved it.
