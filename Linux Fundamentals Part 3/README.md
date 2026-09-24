# TryHackMe - Linux Fundamentals Part 3

This room is the third and final part of the Linux Fundamentals module on TryHackMe.

It focuses on useful Linux utilities, process management, automation, package management, and system logs.

> TryHackMe flags are not included in this README.

---

## Task 1 - Introduction

The final Linux Fundamentals room introduces several important concepts for managing and working with Linux systems.

Topics covered:

* Terminal text editors
* Useful Linux utilities
* Process management
* Automation with cron and crontabs
* Package management
* System and application logs

---

## Task 2 - Deploy and Access the Linux Machine

The room provides a Linux machine that can be accessed through SSH.

The general SSH syntax is:

```bash
ssh username@IP
```

Example:

```bash
ssh tryhackme@10.66.186.75
```

After connecting, the machine can be identified with:

```bash
hostname
```

---

## Task 3 - Terminal Text Editors

Linux provides several terminal-based text editors.

One of the simplest is Nano.

### Creating or Editing a File

```bash
nano filename
```

For example:

```bash
nano myfile
```

### Useful Nano Shortcuts

| Shortcut   | Action                |
| ---------- | --------------------- |
| `Ctrl + O` | Save/write the file   |
| `Ctrl + X` | Exit Nano             |
| `Ctrl + W` | Search                |
| `Ctrl + K` | Cut a line            |
| `Ctrl + U` | Paste                 |
| `Ctrl + G` | Open help             |
| `Ctrl + R` | Read another file     |
| `Ctrl + \` | Replace text          |
| `Ctrl + T` | Spell checking        |
| `Ctrl + _` | Go to a specific line |

After creating a file, its contents can be checked with:

```bash
cat filename
```

---

## Task 4 - General and Useful Utilities

Linux provides many command-line utilities for transferring and serving files.

### wget

`wget` is a command-line utility used to download files over protocols such as HTTP and HTTPS.

Example:

```bash
wget https://example.com/file.txt
```

In the room, a Python HTTP server was used to serve a file and `wget` was used from another terminal to download it.

### Python HTTP Server

Python includes a simple HTTP server that can be started with:

```bash
python3 -m http.server
```

The `-m` option tells Python to execute a module.

Here, Python executes the `http.server` module.

By default, the server listens on port `8000`.

A different port can be specified:

```bash
python3 -m http.server 8080
```

### scp

`scp` stands for Secure Copy.

It allows files to be securely copied between systems using SSH.

General syntax:

```bash
scp source destination
```

---

## Task 5 - Processes

A process is a program that is currently running on a Linux system.

Every process has a Process ID, commonly called a PID.

### ps

The `ps` command displays information about running processes.

```bash
ps
```

A more detailed view can be obtained with:

```bash
ps aux
```

This displays processes from all users and provides additional information about them.

### top

`top` displays processes and system resource usage in real time.

```bash
top
```

It can be useful for monitoring CPU and memory usage.

### PIDs

A PID identifies a running process.

For example:

```text
PID 301
```

means that the process has Process ID `301`.

### kill

The `kill` command sends a signal to a process.

```bash
kill PID
```

For example:

```bash
kill 301
```

The signal determines what should happen to the process.

### Common Signals

#### SIGTERM

Requests that a process terminate gracefully.

```text
SIGTERM
```

This allows the process to perform cleanup before exiting.

#### SIGKILL

Immediately terminates a process.

```text
SIGKILL
```

Unlike SIGTERM, the process cannot perform normal cleanup.

#### SIGSTOP

Suspends a process.

```text
SIGSTOP
```

---

## systemctl

`systemctl` is used to manage services controlled by systemd.

### Start a service

```bash
systemctl start service
```

### Stop a service

```bash
systemctl stop service
```

### Enable a service

```bash
systemctl enable service
```

This configures the service to start automatically when the system boots.

### Disable a service

```bash
systemctl disable service
```

This prevents the service from being automatically started at boot.

### Check service status

```bash
systemctl status service
```

For example:

```bash
systemctl stop myservice
systemctl enable myservice
```

These commands may require administrator privileges depending on the system and the user's permissions.

---

## Foreground and Background Processes

A process running in the foreground occupies the current terminal.

A process running in the background allows the terminal to remain available for other commands.

### Running a command in the background

Use `&`:

```bash
command &
```

### Suspending a foreground process

Press:

```text
Ctrl + Z
```

This suspends the process.

### jobs

The `jobs` command shows jobs associated with the current shell.

```bash
jobs
```

### fg

The `fg` command brings a background or suspended job back to the foreground.

```bash
fg
```

The name `fg` comes from "foreground".

---

## Task 6 - Automation with Cron

Cron is used to schedule commands and tasks to run automatically.

A crontab is a configuration file containing scheduled tasks.

The standard cron format contains five time fields followed by the command:

```text
MIN HOUR DOM MON DOW CMD
```

| Field  | Meaning            |
| ------ | ------------------ |
| `MIN`  | Minute             |
| `HOUR` | Hour               |
| `DOM`  | Day of month       |
| `MON`  | Month              |
| `DOW`  | Day of week        |
| `CMD`  | Command to execute |

### Example

```bash
0 */12 * * * cp -R /home/cmnatic/Documents /var/backups/
```

This schedules the backup command to run every 12 hours.

### Wildcards

The `*` character means "any value".

For example:

```text
* * * * *
```

means every minute of every hour, every day.

### Viewing the Current User's Crontab

```bash
crontab -l
```

The `-l` option means "list".

During the room, the deployed machine contained:

```text
@reboot /var/opt/processes.sh
```

`@reboot` is a special cron expression that runs the specified command when the system starts or reboots.

### Editing a Crontab

```bash
crontab -e
```

The `-e` option opens the user's crontab for editing.

---

## Task 7 - Package Management

Linux distributions use package managers to install, update, and remove software.

Ubuntu and other Debian-based distributions commonly use `apt`.

### apt update

```bash
apt update
```

Updates the local package information from configured repositories.

### Installing a Package

```bash
apt install package-name
```

For example:

```bash
apt install sublime-text
```

### Removing a Package

```bash
apt remove package-name
```

For example:

```bash
apt remove sublime-text
```

---

## Repositories

A repository is a source from which software packages can be downloaded.

Ubuntu has official repositories, but additional third-party repositories can also be configured.

Important APT configuration locations include:

```text
/etc/apt/sources.list
/etc/apt/sources.list.d/
```

Additional repositories can be added with:

```bash
add-apt-repository
```

They can also be removed with:

```bash
add-apt-repository --remove ppa:PPA_Name/ppa
```

A separate `.list` file can be created in:

```text
/etc/apt/sources.list.d/
```

for third-party repositories.

---

## GPG Keys

GPG keys can be used to verify the authenticity of software repositories and packages.

They provide a way for the system to verify that software comes from a trusted source.

The room demonstrated adding a repository signing key before adding a third-party software repository.

The TryHackMe machine does not have Internet access, so the repository setup example was not performed on the deployed machine.

---

## Task 8 - System Logs

Linux stores many system and application logs in:

```text
/var/log/
```

These logs can be useful for:

* Troubleshooting
* Monitoring services
* Investigating system activity
* Identifying errors
* Investigating suspicious activity

### Apache Logs

Apache2 logs are commonly located at:

```text
/var/log/apache2/
```

Common files include:

```text
access.log
error.log
```

### Access Logs

An Apache access log records requests made to the web server.

A typical entry looks like:

```text
IP - - [date] "GET /file HTTP/1.1" 200 ...
```

The IP address identifies the client that made the request.

The `GET` request shows which resource was requested.

### Error Logs

The Apache error log contains information about errors and other problems reported by the web server.

### Log Rotation

Linux systems can automatically rotate logs.

Older logs may have names such as:

```text
access.log.1
error.log.1
```

Compressed older logs may use extensions such as:

```text
.gz
```

---

## Task 9 - Conclusion

Linux Fundamentals Part 3 covered several practical Linux administration concepts.

### Topics Learned

* Terminal text editors
* Nano
* `wget`
* `scp`
* Python HTTP servers
* Processes and PIDs
* `ps`
* `top`
* `kill`
* Linux signals
* `systemctl`
* Foreground and background processes
* `jobs`
* `fg`
* Cron and crontabs
* Package management with `apt`
* Software repositories
* GPG keys
* System and application logs
* Apache access and error logs

This completes the Linux Fundamentals module.

### Further Learning

Recommended TryHackMe rooms for continuing Linux practice:

* Bash Scripting
* Regular Expressions

The next step is to continue practicing Linux commands and apply these concepts in cybersecurity labs.

---

## Key Commands

```bash
ssh username@IP
nano filename
cat filename
wget URL
python3 -m http.server
scp source destination

ps
ps aux
top
kill PID

systemctl start service
systemctl stop service
systemctl enable service
systemctl disable service
systemctl status service

jobs
fg

crontab -l
crontab -e

apt update
apt install package
apt remove package

ls /var/log/
ls /var/log/apache2/
cat /var/log/apache2/access.log
```

---

## Notes

This write-up contains the concepts and commands learned throughout the room.
TryHackMe flags and answers from the practical tasks are intentionally not included.
