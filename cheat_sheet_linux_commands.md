# Linux Commands Cheat Sheet

This cheat sheet provides a quick reference for essential Linux commands across various categories.

## Table of Contents

- [Networking](#networking)
- [Users and Groups](#users-and-groups)
- [File Commands](#file-commands)
- [Directory Navigation](#directory-navigation)
- [Hardware Information](#hardware-information)
- [File Compression](#file-compression)
- [Package Installation](#package-installation)
- [System Management](#system-management)
- [File Permission](#file-permission)
- [SSH Login](#ssh-login)
- [Variables (bash)](#variables-bash)
- [Wildcards / Globbing](#wildcards--globbing)
- [Filters](#filters)
- [Disk Usage](#disk-usage)
- [Process Control](#process-control)
- [Searching](#searching)
- [Scripting Snippets](#scripting-snippets)

### Networking

| Command               | Description                               |
| --------------------- | ----------------------------------------- |
| `curl -O [file_url]`  | Download a file from URL                  |
| `dig -x [ip]`         | IP‑address reverse lookup                 |
| `dig -x [host]`       | Domain reverse lookup                     |
| `dig [domain]`        | Show domain’s DNS info                    |
| `get [file]`          | Download file from remote to local        |
| `host [domain]`       | IP lookup for a domain                    |
| `hostname -I`         | Show local IP address                     |
| `ifconfig`            | Show all network interfaces               |
| `ip addr show`        | Show IP addresses                         |
| `ip address add [ip]` | Assign IP address to interface            |
| `netstat -pnltu`      | Show active listening ports               |
| `nslookup [domain]`   | Show domain information                   |
| `ping [hostname]`     | Check network status                      |
| `put [file]`          | Upload file from local to remote computer |
| `quit`                | Logout                                    |
| `wget [file_url]`     | Download a file from URL                  |
| `whois [domain]`      | Show domain information                   |

### Users and Groups

| Command                      | Description                    |
| ---------------------------- | ------------------------------ |
| `adduser [user]`             | Add a new user                 |
| `chgrp [group] [directory]`  | Change directory group         |
| `groupadd [group]`           | Add a new group                |
| `id`                         | Show active user details       |
| `last`                       | Show last system logins        |
| `passwd [username]`          | Change the user’s password     |
| `userdel [user]`             | Delete a user                  |
| `usermod`                    | Modify user information        |
| `usermod -aG [group] [user]` | Add user to group              |
| `w`                          | Show logged users and activity |
| `who`                        | Show who is logged in          |

### File Commands

| Command                             | Description                    |
| ----------------------------------- | ------------------------------ |
| `awk '{pattern} {print $0}' {file}` | Print lines matching a pattern |
| `cp [file1] [file2]`                | Copy _file1_ to _file2_        |
| `cp -r [dir1] [dir2]`               | Copy directory1 to directory2  |
| `cut -d[delimiter] [file]`          | Cut file section and print     |
| `diff [file1] [file2]`              | Compare two files              |
| `gpg [file.gpg]`                    | Decrypt a file                 |
| `gpg -c [file]`                     | Encrypt a file                 |
| `head [file]`                       | Show first 10 lines            |
| `less`                              | Present text & allow scrolling |
| `ln -s [/path/file] [link]`         | Create symbolic link           |
| `ls`                                | List files in directory        |
| `ls \| xargs wc`                    | Words/lines/bytes in dir       |
| `ls -a`                             | List files incl. hidden        |
| `mkdir [name]`                      | Create a directory             |
| `more [file]`                       | Show file contents             |
| `mv [old] [new]`                    | Rename/move a file             |
| `pwd`                               | Show current directory         |
| `rm [file]`                         | Remove a file                  |
| `rm -r [directory]`                 | Recursively remove dir         |
| `rm -rf [directory]`                | Force remove dir               |
| `shred -u [file]`                   | Overwrite & delete file        |
| `source [file]`                     | Execute file in current shell  |
| `sudo`                              | Run command as super‑user      |
| `tail [file]`                       | Show last 10 lines             |
| `touch [file]`                      | Create / update file           |
| `wc`                                | Count words/lines/bytes        |
| `[cmd] \| tee [file] >/dev/null`    | Store output, skip terminal    |
| `[data] \| cut -d[delim]`           | Cut data section & print       |

### Directory Navigation

| Command          | Description                   |
| ---------------- | ----------------------------- |
| `cd ..`          | Move up one level             |
| `cd`             | Change dir to `$HOME`         |
| `cd [/location]` | Change to specified directory |

### Hardware Information

| Command                    | Description                |
| -------------------------- | -------------------------- |
| `badblocks -s /dev/[disk]` | Unreadable blocks test     |
| `cat /proc/cpuinfo`        | Show CPU information       |
| `dmesg`                    | Show boot‑up messages      |
| `dmidecode`                | Show BIOS hardware info    |
| `free -h`                  | Show free & used memory    |
| `hdparm -i /dev/[disk]`    | Show disk data info        |
| `hdparm -tT /dev/[disk]`   | Disk read‑speed test       |
| `lsblk`                    | Block‑device info          |
| `lshw`                     | Hardware configuration     |
| `lspci -tv`                | Tree of PCI devices        |
| `lsusb -tv`                | Tree of USB devices        |
| `neofetch`                 | Display OS & hardware info |

### File Compression

| Command                        | Description                  |
| ------------------------------ | ---------------------------- |
| `gzip [file]`                  | Create `.gz`‑compressed file |
| `tar cf [file.tar] [file]`     | Create a tar from file       |
| `tar xf [file.tar]`            | Extract tar file             |
| `tar czf [file.tar.gz] [file]` | Create gzip‑tar file         |
| `zip/unzip -r`                 | Package & compress files     |

### Package Installation

| Command                                        | Description                      |
| ---------------------------------------------- | -------------------------------- |
| `apt-get`                                      | Search/install software packages |
| `apt install [package]`                        | Install with APT                 |
| `dnf install [package]`                        | Install with DNF                 |
| `rpm -i [package.rpm]`                         | Install an RPM                   |
| `rpm -e [package.rpm]`                         | Remove an RPM                    |
| `tar xzf [source.tar.gz]`                      | Extract source code              |
| `cd [source]; ./configure; make; make install` | Compile & install from source    |
| `yum info [package]`                           | Package info summary             |
| `yum install [package.rpm]`                    | Install with YUM                 |
| `yum search [keyword]`                         | Find a package                   |

### System Management

| Command                 | Description              |
| ----------------------- | ------------------------ |
| `cal`                   | Show current day & month |
| `date`                  | Show current time & date |
| `finger [user]`         | Show user information    |
| `hostname`              | Show system hostname     |
| `hostname -I`           | Show system IP           |
| `last reboot`           | Show reboot history      |
| `modprobe [module]`     | Add kernel module        |
| `shutdown [hh:mm]`      | Schedule shutdown        |
| `shutdown now`          | Shutdown immediately     |
| `timedatectl`           | Manage system clock      |
| `ulimit [flag] [limit]` | View/limit resources     |
| `uname -a`              | Show kernel release      |
| `uname -r`              | Show kernel version      |
| `uptime`                | Show uptime/load         |
| `whoami`                | Show current user        |

### File Permission

| Command                       | Description          |
| ----------------------------- | -------------------- |
| `chmod 755 [file]`            | Owner all; others rx |
| `chmod 764 [file]`            | Owner all; others rw |
| `chmod 777 [file]`            | Everyone rwx         |
| `chown [user] [file]`         | Change owner         |
| `chown [user]:[group] [file]` | Change owner & group |

### SSH Login

| Command                           | Description        |
| --------------------------------- | ------------------ |
| `ssh [user]@[host]`               | SSH login          |
| `ssh [host]`                      | SSH with defaults  |
| `ssh -p [port] [user]@[host]`     | SSH on custom port |
| `scp [file] [user]@[host]:[path]` | Secure copy        |

### Variables (bash)

| Command                    | Description        |
| -------------------------- | ------------------ |
| `declare variable="value"` | Declare variable   |
| `echo ${variable}`         | Display value      |
| `export variable`          | Export variable    |
| `let "var=$((num))"`       | Integer arithmetic |
| `set`                      | List variables     |

### Wildcards / Globbing

| Pattern     | Matches              |
| ----------- | -------------------- |
| `*`         | Any string           |
| `?`         | Any single char      |
| `[abc]`     | a or b or c          |
| `[a‑z]`     | Any lowercase letter |
| `[0‑9]`     | Any digit            |
| `{foo,bar}` | `foo` or `bar`       |

### Filters

| Command | Description            |
| ------- | ---------------------- |
| `cat`   | Concatenate & print    |
| `cut`   | Cut by columns         |
| `sort`  | Sort text              |
| `uniq`  | Remove duplicates      |
| `tr`    | Translate/delete chars |
| `grep`  | Pattern search         |
| `sed`   | Stream editor          |
| `awk`   | Pattern scanning       |

### Disk Usage

| Command    | Description         |
| ---------- | ------------------- |
| `df -h`    | Free disk space     |
| `du -sh *` | Dir sizes (summary) |
| `du -ah`   | File & dir sizes    |

### Process Control

| Command           | Description              |
| ----------------- | ------------------------ |
| `bg`              | Resume job in background |
| `fg`              | Bring job to foreground  |
| `ps aux`          | List processes           |
| `top` / `htop`    | Live process monitor     |
| `kill [pid]`      | Kill PID                 |
| `killall [name]`  | Kill by name             |
| `nice` / `renice` | Priority control         |

### Searching

| Command                     | Description      |
| --------------------------- | ---------------- |
| `grep -r [pat] [path]`      | Recursive grep   |
| `locate [name]`             | Find by name     |
| `find [path] -name "*pat*"` | Find files       |
| `whereis [cmd]`             | Locate binaries  |
| `which [cmd]`               | Full path of cmd |

### Scripting Snippets

| Snippet                    | Purpose              |
| -------------------------- | -------------------- |
| `#!/bin/bash`              | Script shebang       |
| `$(command)`               | Command substitution |
| `$((expr))`                | Arithmetic           |
| `if [ cond ]; then … fi`   | Conditional          |
| `for x in list; do … done` | Loop                 |
| `function name() { … }`    | Function             |
| `exit 0`                   | Successful exit      |

---

> **Hint** Use `man <command>` or `<command> --help` for details on any entry.
