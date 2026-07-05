# INFOSEC Task 1 Answers

## Level 0 to 1

### Thoughts

This one was honestly just to get familiar with the Bandit setup. I used
`cat` to read the README file and got the password. Nice and easy start.

## Level 1 to 2

### Thoughts

This one confused me for a few minutes because the filename was just a
dash. At first I thought I had to put it in quotes but that obviously
did not work. After searching a bit I understood that Linux treats it
specially, so using `./` before the filename solved it.

## Level 2 to 3

### Thoughts

Nothing difficult here, I just kept making stupid typing mistakes. The
filename had spaces and I either missed a word, added an extra word or
typed something wrong. Once I finally typed the correct filename with
quotes it worked immediately.

## Level 3 to 4

### Thoughts

Pretty basic level. I checked the hidden files, found the required file
inside the directory and read it using `cat`.

## Level 4 to 5

### Thoughts

I actually did not think of using any fancy command here. I simply
checked the files one by one using the `file` command until I found the
readable one. Looking back it was a bit of brute force but it still got
the job done.

## Level 5 to 6

### Thoughts

The problem itself already told us the conditions like file size, owner
and permissions. It was mostly about writing the correct `find` command
with all those conditions together.

## Level 6 to 7

### Thoughts

The first time I used `find` I got pages and pages of permission denied
messages because it searched the whole filesystem. The actual result was
somewhere inside all that mess. After reading a little I found out that
I could redirect those errors to `/dev/null` which made the output much
cleaner.

## Level 7 to 8

### Thoughts

This one was straightforward. I just searched for the given word using
`grep` and the password was right beside it.

## Level 8 to 9

### Thoughts

I learnt something new here. `uniq` only works properly if identical
lines are together, so sorting the file first was important. Using
`sort` followed by `uniq -u` gave me the only unique line.

## Level 9 to 10

### Thoughts

I actually misread the question in the beginning and tried a different
approach. Then I noticed the words "human readable strings" and realised
that the `strings` command was exactly what the question wanted. That
worked immediately.

## Level 10 to 11

### Thoughts

This one was easy once I recognised the Base64 encoding. Linux already
has a decoder for it, so I decoded the text directly from the terminal.

## Level 11 to 12

### Thoughts

I really wanted to use an online ROT13 decoder because it would have
been faster, but I wanted to solve it completely inside Linux. I spent a
little time understanding the `tr` command and finally managed to decode
it using only the terminal.

## Level 12 to 13

### Thoughts

This was probably my favourite level. It felt like opening one box only
to find another box inside it. I first copied the file into a temporary
directory and converted the hex dump back into binary using `xxd`. After
that I kept checking the file type and depending on what it was I used
`gunzip`, `bunzip2` or `tar`. I made quite a few mistakes while renaming
files and had to restart once because my SSH session timed out, but
after repeating the process carefully I finally reached the text file
containing the password. It felt really satisfying when it finally
worked.

## Level 13 to 14

### Thoughts

This level definitely took the most time. I understood that instead of a
password I had to use the private key provided in the home directory.
The problem was that every time I tried to connect it kept saying
localhost authentication was blocked and I spent a long time thinking my
commands were wrong. I checked file permissions, tried different SSH
options, copied the key into temporary locations and even spent quite
some time debugging the errors. Later I found out there was an issue
with the server side behaviour which is why the normal method was not
working for me. I finally switched to my own Ubuntu installation,
recreated the private key properly and connected using that key instead.
This level taught me that reading error messages carefully is just as
important as knowing commands.

## Level 14 to 15

### Thoughts

After logging into Bandit14 I read the password from the password file
and sent it to the local service using `nc`. The service verified it and
returned the password for Bandit15. Compared to the previous level this
one was much simpler and also introduced me to interacting with services
running on a specific port.
