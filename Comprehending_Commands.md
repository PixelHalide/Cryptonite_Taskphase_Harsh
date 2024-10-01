# Comprehending Commands

## cat: not the pet, but the command!

Run cat flag as instructed

## catting absolute paths

Run cat /flag, the absolute address of flag

## more catting practice

Ran cat /usr/share/mysql-common/flag, the absolute address of the flag as given

## grepping for a needle in a haystack

Run grep pwn.college /challenge/data.txt, Since all flags start wuth pwn.college

## listing files

cd into challenge, and then execute ls to see all the files in the directory. a file named 9446-renamed-run-3548 is present. run it relatively with ./9446-renamed-run-3548

## touching files

Create the file pwn and college at /tmp, with touch /tmp/college and touch /tmp/pwn and run /challenge/run as instructed

## removing files

run rm delete_me to delete the file, then run /challenge/check as instructed

## hidden files

Run /challenge/run as usual. It states that flag has been made readable and put somewhere in root. cd to root with /, then list all files with ls -a. a file named .flag-3132236738318 is present, print it with cat.

## An Epic Filesystem Quest

With the first hint, Go to root. i list all possible files with ls -a, which reveals a file named MESSAGE. i print it with cat MESSAGE, which gives this hint:

>/opt/angr-management/_internal/pypcode/processors/MCS96

i cd to this directory and ls -a. a file named trace is present. print with cat trace. it outputs this hint:

>/usr/lib/jvm/java-17-openjdk-amd64/legal/java.management

cd to the dir, ls -a, there is a file named INFO. cat info to reveal this hint:

>/usr/share/maxima-sage/5.42.2/share/hypergeometric

cd to dir, ls -a, there is a file SECRET, output with cat and it reveals:

>The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using >special options to 'ls'.

i'm not quite sure what i did next, i went to various locations, like root, home, all the previous directories and find nothing. i go back to SECRET, and output it again, and this is the output:

>Tubular find!
>The next clue is in: /usr/lib/systemd/ntp-units.d

>The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.

doing ls -a reveals a file .HINT, printing gives this clue:

>The next clue is in: /opt/linux/linux-5.4/drivers/pwm

>The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
