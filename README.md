# Linux commands

## GREP - grep

`grep ‘word’ [filename]` –  search for a particular word in a particular file.

`grep ‘word’ [filename] > [output-filename]` –  search for a particular word in a particular file and output it to a new file.

`grep -c 'word' [filename]` - display a count of the number of matches

## SORT - sort

`sort [filename]` –  sorts the contents of a file into alphabetical order, with numbers at the top.

`sort -r [filename]` –  sort the contents of a file in reverse order.

`sort [filename] > [output-filename]` –  sorts a file’s contents into alphabetical order and outputs it into a new file.

## FIND - find

`find /[directory-to-search] -name filename` –  Search a directory for a file

`find . -name [filename]` –  Search the current directory for a file

`find / -name [filename]` –  Search all directories for a file

`find /[directory-to-search] -name ‘[word]*’` – Search a directory for a filename that contains a word

`find /[directory-to-search] -perm [permissions as numerical value]` –  Search a directory for everything that has particular user permissions

`find /[directory-to-search] -user` –  Search a directory for everything owned by a particular user

## WORD COUNT - wc

`wc [file]` – count the number of lines, words, and characters in a file

`wc -w [file]` – count the number words in a file

`wc -l [file]` – count the number of lines in a file

`wc -m [file]` – count the number characters in a file

## TRANSLATE - tr

`tr [original] [replacewith] < filename > newfile` – replace all instances of the original character set with the character set specified. The > newfile part of the command is optional but allows you to use tr on files rather than input from the terminal.

`tr [original] [replacewith] < filename` – allows you to run the tr command on files rather than waiting for input from the terminal.

`tr [original] [replacewith] > filename` – allows you to save command output to files rather than outputting it to the terminal.

Both the < and > parameters are optional, but they can be used on most Linux commands we’ve learned in the series so far.

Useful character groupings that tr is aware of:

* `[:alnum:]` All letters and digits (A–Z, a–z, 0–9)
* `[:alpha:]` All letters (A–Z, a–z)
* `[:digit:]` All digits (0–9)
* `[:punct:]` All punctuation characters

## STREAM EDITOR - sed

`sed ‘s/[original]/[replacewith]/g’ filename` – search for all instances of the original string in the file and replace it with the specified string.

## STREAM REDIRECTION

The ‘>’ character can be used to save the output of a command to a file. However, adding a second ‘>’ character will instead append the output to an existing file, adding the output to the bottom of what already exists in the file.

## SUDO - sudo

`sudo [command]` – run a command as a super (root) user

`sudo -u [username] [command]` – run a command as the user you specify

`su` – switch to the super (root) user account

`su [username]` – switch to the specified user account

## SCREEN - screen

`Screen -ls` –  list all currently active screens

`Screen -r [existing-screen-name]` –  connect to an already existing screen

`Screen -S [desired-screen-name]` –  create a new session and give it a name

`Ctrl A + D` –  detach from a screen

`Ctrl + A, then Shift + K, then Y` –  kill a screen session

## HASHING

`sha1sum [filename]` –  generates a hash for a file using SHA1 

`sha256sum [filename]` –  generates a hash for a file using SHA256

`md5sum [filename]` –  generates a hash for a file using MD5

## COMMAND CHAINING

### && – Logical AND

Using && will execute the second command only after the first command has executed successfully. For example, if X gets the thumbs up, execute Y. If X doesn’t get the thumbs up, end the commands without running Y.

## || – Logical OR

This operator will execute the second command only if the first command was unsuccessful. For example, if X gets a thumbs up, don’t execute command Y. If X gets a thumbs down, execute Y.

### ; – Semicolon

Any commands put in after the semicolon operator will execute regardless of whether the one before was successful or not. For example, if X gets a thumbs up, execute Y. If Y gets thumbs down, execute Z anyway.

### | – Pipe

The pipe operator is used to take the output from one command and use it as the input for the next. For example, execute X first and use the result of that in conjunction with command Y.

### & – Background

When used after a command, this operator will send that command to process in the background while running the second command in the foreground. For example, execute command X, send that to the background, then run command Y.
