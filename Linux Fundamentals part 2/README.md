# TryHackMe — Linux Fundamentals Part 2

Notes and documentation from the Linux Fundamentals Part 2 room on TryHackMe.

This room focuses on essential Linux concepts such as commands, arguments, files, directories, permissions, and users.

> TryHackMe flags are not included in this README.

---

# 1. AttackBox

The AttackBox is a machine provided by TryHackMe for completing laboratory activities.

It works as a working computer from which we can execute commands, connect to remote machines, and complete the exercises.

### AttackBox vs Lab Machine

- AttackBox → The machine used to perform the exercises.
- Lab Machine → The machine provided by the laboratory that we connect to and interact with.

---

# 2. SSH

SSH (Secure Shell) is a protocol used to securely access remote computers.

To establish an SSH connection, we generally need:

- the IP address of the machine;
- a username;
- a password or another authentication method.

### Syntax

```bash
ssh username@IP
```

Example:

```bash
ssh tryhackme@MACHINE_IP
```

After establishing the connection, commands executed in the terminal are executed on the remote machine.

### Password input

When typing a password in a Linux terminal, the characters normally do not appear on the screen. This is expected behavior.

---

# 3. Arguments / Flags

Many Linux commands accept arguments or flags that modify their behavior.

For example:

```bash
ls
```

Lists visible files and directories.

Using:

```bash
ls -a
```

also displays hidden files and directories.

The long version of the same option is:

```bash
ls --all
```

The `-a` option is the short form of `--all`.

---

## Hidden Files

In Linux, files and directories whose names begin with `.` are considered hidden.

Example:

```text
.secretfolder
```

To display hidden files:

```bash
ls -a
```

### Finding command options

We can use:

```bash
ls --help
```

to see available options.

We can also use:

```bash
man ls
```

The `man` command provides detailed documentation for Linux commands.

---

# 4. Files and Directories

Linux provides several commands for creating, copying, moving, and removing files and directories.

## `touch`

Creates an empty file:

```bash
touch file.txt
```

---

## `mkdir`

Creates a directory:

```bash
mkdir documents
```

---

## `cp`

Copies files or directories.

Example:

```bash
cp file.txt copy.txt
```

This copies `file.txt` into a new file called `copy.txt`.

A file can also be copied into another directory:

```bash
cp note Documents
```

---

## `mv`

Moves or renames files.

Move a file:

```bash
mv file.txt Documents/
```

Rename a file:

```bash
mv old.txt new.txt
```

---

## `rm`

Removes files:

```bash
rm file.txt
```

> Be careful when using `rm`, because files removed from the terminal may not be moved to a recycle bin.

---

# 5. Important Linux Directories

Linux has several important directories, each with a specific purpose.

| Directory | Purpose |
|---|---|
| `/` | Root of the filesystem |
| `/etc` | Configuration files |
| `/var` | Variable data used by the system and services |
| `/var/log` | Log files |
| `/root` | Home directory of the `root` user |
| `/tmp` | Temporary files |

### `/`

The root directory is the top level of the Linux filesystem.

All other directories are located within the filesystem hierarchy starting from `/`.

### `/etc`

Contains configuration files for the operating system and many applications.

Example:

```text
/etc/sudoers
```

### `/var`

Stores data that changes while the system is running.

For example:

```text
/var/log
```

contains various system and application log files.

### `/root`

This is the home directory of the `root` user.

It should not be confused with:

```text
/home
```

which normally contains the home directories of regular users.

### `/tmp`

Used for storing temporary files.

---

# 6. File Permissions

Permissions determine what actions a user can perform on a file or directory.

We can view detailed file information using:

```bash
ls -l
```

Example:

```text
-rw-r--r-- 1 user user 123 file.txt
```

The main permissions are:

| Permission | Meaning |
|---|---|
| `r` | Read |
| `w` | Write |
| `x` | Execute |

---

## Owner, Group, and Others

Files have different permission sets for:

- Owner → the owner of the file;
- Group → the group associated with the file;
- Others → all other users.

This allows Linux to control who can read, modify, or execute a file.

---

# 7. `su` — Switch User

The command:

```bash
su
```

stands for Switch User.

It allows us to switch to another user in the terminal.

To switch to `user2`:

```bash
su -l user2
```

### Breaking down the command

```text
su       → Switch User
-l       → Start a login shell/session
user2    → The user we want to switch to
```

The system then asks for the target user's password.

---

# 8. Viewing File Contents

The `cat` command can be used to display the contents of a file in the terminal.

Example:

```bash
cat important
```

This prints the contents of the `important` file.

During the laboratory, I switched to the `user2` account and then used `cat` to access the contents of the file.

---

# 9. Commands Learned

| Command | Purpose |
|---|---|
| `ls` | Lists files and directories |
| `ls -a` | Lists hidden files and directories |
| `ls -l` | Displays detailed file information |
| `ls --help` | Shows available options |
| `man` | Opens the manual for a command |
| `ssh` | Connects to a remote machine |
| `touch` | Creates a file |
| `mkdir` | Creates a directory |
| `cp` | Copies files/directories |
| `mv` | Moves or renames files |
| `rm` | Removes files/directories |
| `su` | Switches users |
| `cat` | Displays file contents |

---

# 10. What I Learned

Throughout Linux Fundamentals Part 2, I practiced:

- Using SSH;
- Understanding the difference between the AttackBox and Lab Machine;
- Using flags and arguments;
- Identifying hidden files and directories;
- Using `--help` to find command options;
- Using `man` to read command documentation;
- Creating and manipulating files;
- Creating and manipulating directories;
- Understanding the Linux filesystem hierarchy;
- Understanding `r`, `w`, and `x` permissions;
- Understanding owners, groups, and others;
- Switching users with `su`;
- Viewing file contents with `cat`.

These concepts provide an important foundation for working with Linux and continuing my studies in Cybersecurity.
