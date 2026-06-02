---
---

--- Before Day-1 ---
I already know basics of Linux. I have completed Diploma in Programming.
---

## Day-1 Checklist

- [x] I can open a Linux terminal and recognize the shell prompt (`user@machine:~$`)
- [x] I can run `python --version`, `git --version`, and `uv --version` without errors
- [x] I can open VS Code connected to WSL/Linux using `code .`
- [x] I know what `~` means and can navigate to my home directory using `cd ~`
- [x] I can create folders and files using `mkdir` and `touch`, and list them with `ls`
- [x] I know the difference between `.xyz`, `./xyz`, and `../xyz`
- [x] I know that in Linux, everything is a file
- [x] I can navigate to the C and D drives within WSL
- [x] I understand the difference between `>` (overwrite) and `>>` (append)
- [x] I have a Github account and have created the `tds-bootcamp` repository

--- After Day-1 ---
I learned these things as well, apart from the checklist, I learnt about git configurations.
---

--- Feedback (Suggestions for the TDS Team) ---
Great session by TAs, could still make it hands on
---

---
---

## My Personal Notes

### Day-1 Quiz

1. ~ is the shorthand for your home directory

2. Linux home is /home/\<username>

3. .. goes one level up

4. pwd prints the working directory

5. \> overwrites the file

6. \> overwrites, >> appends

7. Linux is case-sensitive

8. In ls command, -a shows hidden files and -l shows details

9. File names starting with a . are hidden by default

10. Absolute parts start with /

11. ./bootcamp means "bootcamp inside the current directory"

12. WSL 2 is Windows Subsystem for Linux 2. It runs a real Linux kernel inside Windows

13. /mnt/c can be slower and have permission quirks in WSL

14. If after installing uv and when trying to run uv --version gives 'command not found' error, then either restart the shell or source the shell config so PATH updates

15. git config --global user.name will set commit author identity and not Github login. It sets the name that appear in git commits on the machine

16. -p option in mkdir creates parent directories as needed (all intermediate folders in the path if they don't exist)

17. touch creates an empty file

18. If we run VS code from WSL terminal using code and in the bottom left of the VS code, we observe WSL: Ubuntu, it confirms, VS code is running inside the WSL Linux environment (not Windows)

19. The root directory in Linux is /

20. A file saved on Windows has line endings \r\n (CRLF). Linux expects line endings \n (LF) only. CRLF causes differences which Git tracks as changes

21. Files starting with . are hidden by default

22. ./ means current directory

23. ../ means parent directory

24. .xyz is a dotfile name and ./ and ../ are path shorthands

25. Windows drives are mounted under /mnt

26. ls /mnt lists all the Windows drive available inside WSL

27. In Linux, everything is a file. Many system resources (including devices and directories) are represented through the file system

28. Not everyone has /mnt/d, we must check the mounts using ls /mnt

29. ../ is the parent directory

30. ls hides dotfiles by default. Use ls -a or ls -la to show dotfiles

### Exercises

#### Exercise 1

```
girish@Girishs-MacBook-Air ~ % pwd
/Users/girish
girish@Girishs-MacBook-Air ~ % cd ~
girish@Girishs-MacBook-Air ~ % ls -la
total 80
drwxr-x---+ 21 girish  staff    672  2 Jun 22:32 .
drwxr-xr-x   5 root    admin    160  2 Jun 14:59 ..
-r--------   1 girish  staff      7  2 Jun 14:59 .CFUserTextEncoding
drwx------@  3 girish  staff     96  2 Jun 21:43 .copilot
-rw-r--r--@  1 girish  staff   8196  2 Jun 21:41 .DS_Store
-rw-r--r--   1 girish  staff     60  2 Jun 20:11 .gitconfig
drwx------   7 girish  staff    224  2 Jun 19:29 .ssh
drwx------+  5 girish  staff    160  2 Jun 21:41 .Trash
-rw-------   1 girish  staff  14422  2 Jun 21:10 .viminfo
drwxr-xr-x@  5 girish  staff    160  2 Jun 21:43 .vscode
drwxr-xr-x@  3 girish  staff     96  2 Jun 21:43 .vscode-shared
-rw-r--r--   1 girish  staff     47  2 Jun 22:32 .zprofile
drwx------   6 girish  staff    192  2 Jun 19:25 .zsh_sessions
drwx------+  5 girish  staff    160  2 Jun 19:56 Desktop
drwx------+  3 girish  staff     96  2 Jun 14:59 Documents
drwx------+  5 girish  staff    160  2 Jun 21:41 Downloads
drwx------@ 80 girish  staff   2560  2 Jun 15:20 Library
drwx------   3 girish  staff     96  2 Jun 14:59 Movies
drwx------+  3 girish  staff     96  2 Jun 14:59 Music
drwx------+  4 girish  staff    128  2 Jun 14:59 Pictures
drwxr-xr-x+  4 girish  staff    128  2 Jun 14:59 Public
girish@Girishs-MacBook-Air ~ % ls -la | wc -l
      22
girish@Girishs-MacBook-Air ~ % 
```

#### Exercise 2

```
mkdir -p ~/tds/bootcamp/day-1
mkdir ~/tds/practice
touch ~/tds/bootcamp/day-1/notes.txt
ls ~/tds/
ls ~/tds/bootcamp/day-1/
```

When we try to list tds directory, we get bootcamp and practice. When we try to list the day-1 directory inside the day-1 inside the bootcamp, we get the regular file notes.txt

#### Exercise 3

```
girish@Girishs-MacBook-Air tds-bootcamp % mkdir -p day-1
girish@Girishs-MacBook-Air tds-bootcamp % echo "My name is Girish S" > day-1/notes.txt
girish@Girishs-MacBook-Air tds-bootcamp % cat day-1/notes.txt
My name is Girish S
girish@Girishs-MacBook-Air tds-bootcamp % echo "Today is Day 1 of TDS Bridge Bootcamp" >> day-1/notes.txt
girish@Girishs-MacBook-Air tds-bootcamp % cat day-1/notes.txt
My name is Girish S
Today is Day 1 of TDS Bridge Bootcamp
```

#### Exercise 4

```
girish@Girishs-MacBook-Air tds-bootcamp % python --version
Python 3.12.0
girish@Girishs-MacBook-Air tds-bootcamp % git --version
git version 2.50.1 (Apple Git-155)
girish@Girishs-MacBook-Air tds-bootcamp % uv --version
uv 0.11.18 (e32666915 2026-06-01 aarch64-apple-darwin)
girish@Girishs-MacBook-Air tds-bootcamp % code --version
1.122.1
8761a5560cfd65fdd19ce7e2bd18dab5c0a4d84e
arm64
```

#### Exercise 5

1. /home/alice/projects/app.py -> Absolute path
2. ./scripts/run.sh -> Relative path
3. ../data/input.csv -> Relative path
4. ~/tds/bootcamp/ -> Absolute path (~ is absolute as it expands to /home/username)
5. notes.txt -> Relative path

#### Exercise 6

```
ls /mnt
cd /mnt/c
pwd
ls
cd /mnt/d
pwd
ls
cd ~
pwd
```

It is recommended doing day-to-day coding work in ~/tds/ instead of /mnt/c because /mnt/c can be slower and might have permission quirks in WSL.

### Exercise 7

```
cd ~/tds/bootcamp/day-1
touch .xyz
echo "current folder" > xyz
echo "parent folder" > ../parent.txt
ls
ls -la
cat ./xyz
cat ../parent.txt
```

.xyz is a dotfile. ls command hides dotfile by default. We have to use ls -a or ls -la to list all the files including the dotfiles

.xyz refers to the dotfile and ./xyz refers to the regular file xyz in the current directory. xyz is not hidden but .xyz is hidden

../ is a path shorthand that refers to the parent directory

### References

1. [Configuration notes from TA](https://hrmiitm.github.io/tds/W0/2_linux_tools.html)
2. [Bootcamp Github notes](https://github.com/hrmiitm/tds-may26-live)
