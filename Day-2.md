---
---

--- Before Day-2 ---
I already knew Linux basics
---

## Day-2 Checklist

- [x] I understand what `PATH` is and why commands like `python` work without full paths
- [x] I can navigate the filesystem without clicking - using `cd`, `ls`, and `pwd` only
- [x] I can read, search, and inspect files using `cat`, `head`, `tail`, `grep`, and `wc`
- [x] I can edit a file using `nano` (open, edit, save, exit)
- [x] I understand pipes (`|`) and redirection (`>`, `>>`, `2>`) and can chain commands
- [x] I can set an environment variable in `.bashrc` and apply it with `source ~/.bashrc`
- [x] I know the difference between `export VAR=value` (available to child process) and just `VAR=value` (shell-local)

--- After Day-2 ---
I learned these things as well, apart from the checklist I learnt about vim editor
---

--- Feedback (Suggestions for the TDS Team) ---
Great session by TAs but still I felt it could be made more hands on
---

---
---

## My Personal Notes

### Day-2 Quiz

1. Even if we have installed python and still getting 'command not found' when we type python in the terminal, the most likely cause is that the installed folder is not in the PATH

2. If we get 0 as the output for the command echo $?, it means the command ran successfully. Exit code 0 means success

3. tail -f server.log continuously shows new lines as they are added to the file. -f follows the file live. It is useful for server logs

4. For the wc command, -l option counts the number of lines and -w counts the number of words

5. For grep command, -i flag makes the search case-insensitive

6. For grep command, -v flag inverts the match and returns non-matching lines

7. \> overwrites and >> appends

8. 2> redirects stderr (error stream)

9. Pipe | feeds stdout of left command into stdin of right

10. uniq -c counts the frequency and sort -rn sorts by count descending

11. In Nano, Ctrl+O writes (saves) and Ctrl+X exits

12. In Vim, :q! force quits vim without saving

13. For cp command, -r flag is required to copy directories recursively

14. Deletion with rm -r command is permanent, the contents doesn't move to recycle bin

15. Without export, the variable isn't inherited by child processes or new shell

16. source command re-executes the file in the current shell

17. Declaring variable without export sets the variable only for the current shell. Export makes the variable available to programs launched from this shell. Export shares the variable with child processes

18. os.environ["KEY"] is the standard way to read the variable stored as an environment variable

19. Dot prefixed files are hidden and ls -la reveals them

20. For grep command, -r flag searches the pattern recursively through the text

21. whoami command prints the current user

22. For chmod command, +x adds execute permissions

23. man ls or ls --help are the standard ways to view the manual or help page for the ls command

24. clear or Ctrl+L clears the screen

25. sudo command helps us to run a command with superuser (administrator) priveleges

26. In df -h command, df shows disk free space and -h makes it human readable

27. which locates a command in the PATH

28. history command prints a list of previously executed commands. It displays the command history

29. The UP arrow key cycles through history

30. For mkdir command, -p flag creates parent directories as needed

### Exercises

#### Exercise 1

```
girish@Girishs-MacBook-Air ~ % cd ~
girish@Girishs-MacBook-Air ~ % ls -la
total 104
drwxr-x---+ 27 girish  staff    864  3 Jun 10:39 .
drwxr-xr-x   5 root    admin    160  2 Jun 14:59 ..
-r--------   1 girish  staff      7  2 Jun 14:59 .CFUserTextEncoding
drwxr-xr-x   4 girish  staff    128  2 Jun 23:31 .config
drwx------@  3 girish  staff     96  2 Jun 21:43 .copilot
-rw-r--r--@  1 girish  staff   8196  3 Jun 00:01 .DS_Store
-rw-r--r--   1 girish  staff     60  2 Jun 20:11 .gitconfig
drwxr-xr-x   3 girish  staff     96  2 Jun 23:31 .local
-rw-r--r--   1 girish  staff     26  2 Jun 23:31 .profile
drwxr-xr-x   5 girish  staff    160  2 Jun 23:44 .pyenv
drwx------   7 girish  staff    224  2 Jun 19:29 .ssh
drwx------+  6 girish  staff    192  3 Jun 00:01 .Trash
-rw-------   1 girish  staff  14422  2 Jun 21:10 .viminfo
drwxr-xr-x@  5 girish  staff    160  2 Jun 21:43 .vscode
drwxr-xr-x@  3 girish  staff     96  2 Jun 21:43 .vscode-shared
-rw-r--r--   1 girish  staff     47  2 Jun 22:32 .zprofile
-rw-------   1 girish  staff   2507  3 Jun 00:05 .zsh_history
drwx------   8 girish  staff    256  3 Jun 10:39 .zsh_sessions
-rw-r--r--@  1 girish  staff    136  2 Jun 23:35 .zshrc
drwx------+  5 girish  staff    160  2 Jun 19:56 Desktop
drwx------+  3 girish  staff     96  2 Jun 14:59 Documents
drwx------+  4 girish  staff    128  3 Jun 00:01 Downloads
drwx------@ 82 girish  staff   2624  3 Jun 09:00 Library
drwx------   4 girish  staff    128  3 Jun 09:00 Movies
drwx------+  3 girish  staff     96  2 Jun 14:59 Music
drwx------+  4 girish  staff    128  2 Jun 14:59 Pictures
drwxr-xr-x+  4 girish  staff    128  2 Jun 14:59 Public
girish@Girishs-MacBook-Air ~ % ls -la | wc -l
      28
girish@Girishs-MacBook-Air ~ % cd ~/Desktop/development/tds-bootcamp
```

In the home directory, the hidden files are .config, .copilot, .DS_Store, .gitconfig, .local, .profile, .pyenv, .ssh, .Trash, .viminfo, .vscode, .vscode-shared, .zprofile, .zsh_history, .zsh_sessions and .zshrc

#### Exercise 2

```
girish@Girishs-MacBook-Air tds-bootcamp % cd day-2
girish@Girishs-MacBook-Air day-2 % echo "INFO: server started on port 8000" > app.log
girish@Girishs-MacBook-Air day-2 % echo "INFO: connected to database" >> app.log
girish@Girishs-MacBook-Air day-2 % echo "WARN: disk usage at 80%" >> app.log
girish@Girishs-MacBook-Air day-2 % echo "ERROR: failed to read config.json" >> app.log
girish@Girishs-MacBook-Air day-2 % echo "INFO: request received from 127.0.0.1" >> app.log
girish@Girishs-MacBook-Air day-2 % echo "ERROR: database connection lost" >> app.log
girish@Girishs-MacBook-Air day-2 % echo "WARN: retrying connection..." >> app.log
girish@Girishs-MacBook-Air day-2 % echo "INFO: connection restored" >> app.log
girish@Girishs-MacBook-Air day-2 % wc -l app.log
       8 app.log
girish@Girishs-MacBook-Air day-2 % tail -3 app.log
ERROR: database connection lost
WARN: retrying connection...
INFO: connection restored
girish@Girishs-MacBook-Air day-2 % grep "ERROR" app.log | wc -l
       2
girish@Girishs-MacBook-Air day-2 % grep "WARN" app.log
WARN: disk usage at 80%
WARN: retrying connection...
```

#### Exercise 3

```
girish@Girishs-MacBook-Air day-2 % grep "ERROR" app.log > errors.txt
girish@Girishs-MacBook-Air day-2 % cat errors.txt
ERROR: failed to read config.json
ERROR: database connection lost
girish@Girishs-MacBook-Air day-2 % echo "Errors:" && grep -c "ERROR" app.log
Errors:
2
girish@Girishs-MacBook-Air day-2 % echo "Warnings:" && grep -c "WARN" app.log
Warnings:
2
girish@Girishs-MacBook-Air day-2 % cat app.log | grep -v "INFO" | wc -l
       4
```

The last cat command counts the number of lines which are not INFO. Since for grep command, -v flag inverts the pattern, the last command counts the number of lines which are WARN or ERROR

#### Exercise 4

```
girish@Girishs-MacBook-Air day-2 % nano app.log
girish@Girishs-MacBook-Air day-2 % head -1 app.log
# Log file for my TDS project
```

#### Exercise 5

```
girish@Girishs-MacBook-Air day-2 % export MY_LOG_FILE="$HOME/Desktop/development/tds-bootcamp/day-2/app.log"
girish@Girishs-MacBook-Air day-2 % cat $MY_LOG_FILE
# Log file for my TDS project
INFO: server started on port 8000
INFO: connected to database
WARN: disk usage at 80%
ERROR: failed to read config.json
INFO: request received from 127.0.0.1
ERROR: database connection lost
WARN: retrying connection...
INFO: connection restored
girish@Girishs-MacBook-Air day-2 % grep -c "ERROR" $MY_LOG_FILE
2
girish@Girishs-MacBook-Air day-2 % nano ~/.bashrc
girish@Girishs-MacBook-Air day-2 % source ~/.bashrc
girish@Girishs-MacBook-Air day-2 % echo $MY_NAME
Girish S
```

#### My Pipeline - Bonus Exercise

`cat app.log | tr ' ' '\n' | sort | uniq -c | sort -rn | head -1 | awk '{print $2}'`

#### Exercise 6

```
girish@Girishs-MacBook-Air day-2 % whoami
girish
girish@Girishs-MacBook-Air day-2 % history | tail -5
  192  ls
  193  cat app.log | tr ' ' '\n' | sort | uniq -c | sort -rn | head
  194  cat app.log | tr ' ' '\n' | sort | uniq -c | sort -rn | head -1
  195  cat app.log | tr ' ' '\n' | sort | uniq -c | sort -rn | head -1 | awk '{print $2}'
  196  whoami
girish@Girishs-MacBook-Air day-2 % which python
/Users/girish/.pyenv/shims/python
```

Output of which python is important when working with virtual environments because virtual environments work by changing the shell's PATH so that the environment's own Python interpreter is found first.