# Linux Commands Cheat Sheet

This cheat sheet provides a quick reference for essential Linux commands across various categories.

## Table of Contents

- [Networking](#networking)
- [Users and Groups](#users-and-groups)
- [File Commands](#file-commands)
- [Text Editors](#text-editors)
- [Directory Navigation](#directory-navigation)
- [Hardware Information](#hardware-information)
- [File Compression](#file-compression)
- [Package Installation](#package-installation)
- [System Management](#system-management)
- [System Monitoring](#system-monitoring)
- [Service Management](#service-management)
- [File System Operations](#file-system-operations)
- [Log Management](#log-management)
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

| Command               | Description                               | Man Page                                                                 |
| --------------------- | ----------------------------------------- | ------------------------------------------------------------------------ |
| `curl -O [file_url]`  | Download a file from URL                  | [curl(1)](https://man7.org/linux/man-pages/man1/curl.1.html)             |
| `dig -x [ip]`         | IP‑address reverse lookup                 | [dig(1)](https://man7.org/linux/man-pages/man1/dig.1.html)               |
| `dig -x [host]`       | Domain reverse lookup                     | [dig(1)](https://man7.org/linux/man-pages/man1/dig.1.html)               |
| `dig [domain]`        | Show domain's DNS info                    | [dig(1)](https://man7.org/linux/man-pages/man1/dig.1.html)               |
| `get [file]`          | Download file from remote to local        | [ftp(1)](https://man7.org/linux/man-pages/man1/ftp.1.html)               |
| `host [domain]`       | IP lookup for a domain                    | [host(1)](https://man7.org/linux/man-pages/man1/host.1.html)             |
| `hostname -I`         | Show local IP address                     | [hostname(1)](https://man7.org/linux/man-pages/man1/hostname.1.html)     |
| `ifconfig`            | Show all network interfaces               | [ifconfig(8)](https://man7.org/linux/man-pages/man8/ifconfig.8.html)     |
| `ip addr show`        | Show IP addresses                         | [ip(8)](https://man7.org/linux/man-pages/man8/ip.8.html)                 |
| `ip address add [ip]` | Assign IP address to interface            | [ip(8)](https://man7.org/linux/man-pages/man8/ip.8.html)                 |
| `ip route show`       | Show routing table                        | [ip(8)](https://man7.org/linux/man-pages/man8/ip.8.html)                 |
| `netstat -pnltu`      | Show active listening ports               | [netstat(8)](https://man7.org/linux/man-pages/man8/netstat.8.html)       |
| `nmap [host]`         | Network port scanner                      | External tool                                                            |
| `nslookup [domain]`   | Show domain information                   | [nslookup(1)](https://man7.org/linux/man-pages/man1/nslookup.1.html)     |
| `ping [hostname]`     | Check network status                      | [ping(8)](https://man7.org/linux/man-pages/man8/ping.8.html)             |
| `put [file]`          | Upload file from local to remote computer | [ftp(1)](https://man7.org/linux/man-pages/man1/ftp.1.html)               |
| `quit`                | Logout                                    | [ftp(1)](https://man7.org/linux/man-pages/man1/ftp.1.html)               |
| `ss -tulpn`           | Show listening ports (modern netstat)     | [ss(8)](https://man7.org/linux/man-pages/man8/ss.8.html)                 |
| `tcpdump`             | Packet capture                            | [tcpdump(8)](https://man7.org/linux/man-pages/man8/tcpdump.8.html)       |
| `traceroute [host]`   | Trace network path                        | [traceroute(8)](https://man7.org/linux/man-pages/man8/traceroute.8.html) |
| `wget [file_url]`     | Download a file from URL                  | [wget(1)](https://man7.org/linux/man-pages/man1/wget.1.html)             |
| `whois [domain]`      | Show domain information                   | [whois(1)](https://man7.org/linux/man-pages/man1/whois.1.html)           |

### Users and Groups

| Command                      | Description                    | Man Page                                                             |
| ---------------------------- | ------------------------------ | -------------------------------------------------------------------- |
| `adduser [user]`             | Add a new user                 | [adduser(8)](https://man7.org/linux/man-pages/man8/adduser.8.html)   |
| `chgrp [group] [directory]`  | Change directory group         | [chgrp(1)](https://man7.org/linux/man-pages/man1/chgrp.1.html)       |
| `groupadd [group]`           | Add a new group                | [groupadd(8)](https://man7.org/linux/man-pages/man8/groupadd.8.html) |
| `id`                         | Show active user details       | [id(1)](https://man7.org/linux/man-pages/man1/id.1.html)             |
| `last`                       | Show last system logins        | [last(1)](https://man7.org/linux/man-pages/man1/last.1.html)         |
| `passwd [username]`          | Change the user's password     | [passwd(1)](https://man7.org/linux/man-pages/man1/passwd.1.html)     |
| `su [user]`                  | Switch user                    | [su(1)](https://man7.org/linux/man-pages/man1/su.1.html)             |
| `sudo -u [user] [cmd]`       | Run as specific user           | [sudo(8)](https://man7.org/linux/man-pages/man8/sudo.8.html)         |
| `userdel [user]`             | Delete a user                  | [userdel(8)](https://man7.org/linux/man-pages/man8/userdel.8.html)   |
| `usermod`                    | Modify user information        | [usermod(8)](https://man7.org/linux/man-pages/man8/usermod.8.html)   |
| `usermod -aG [group] [user]` | Add user to group              | [usermod(8)](https://man7.org/linux/man-pages/man8/usermod.8.html)   |
| `w`                          | Show logged users and activity | [w(1)](https://man7.org/linux/man-pages/man1/w.1.html)               |
| `who`                        | Show who is logged in          | [who(1)](https://man7.org/linux/man-pages/man1/who.1.html)           |

### File Commands

| Command                             | Description                    | Man Page                                                       |
| ----------------------------------- | ------------------------------ | -------------------------------------------------------------- |
| `awk '{pattern} {print $0}' {file}` | Print lines matching a pattern | [awk(1)](https://man7.org/linux/man-pages/man1/awk.1p.html)    |
| `cp [file1] [file2]`                | Copy _file1_ to _file2_        | [cp(1)](https://man7.org/linux/man-pages/man1/cp.1.html)       |
| `cp -r [dir1] [dir2]`               | Copy directory1 to directory2  | [cp(1)](https://man7.org/linux/man-pages/man1/cp.1.html)       |
| `cut -d[delimiter] [file]`          | Cut file section and print     | [cut(1)](https://man7.org/linux/man-pages/man1/cut.1.html)     |
| `diff [file1] [file2]`              | Compare two files              | [diff(1)](https://man7.org/linux/man-pages/man1/diff.1.html)   |
| `gpg [file.gpg]`                    | Decrypt a file                 | [gpg(1)](https://man7.org/linux/man-pages/man1/gpg.1.html)     |
| `gpg -c [file]`                     | Encrypt a file                 | [gpg(1)](https://man7.org/linux/man-pages/man1/gpg.1.html)     |
| `head [file]`                       | Show first 10 lines            | [head(1)](https://man7.org/linux/man-pages/man1/head.1.html)   |
| `less`                              | Present text & allow scrolling | [less(1)](https://man7.org/linux/man-pages/man1/less.1.html)   |
| `ln -s [/path/file] [link]`         | Create symbolic link           | [ln(1)](https://man7.org/linux/man-pages/man1/ln.1.html)       |
| `ls`                                | List files in directory        | [ls(1)](https://man7.org/linux/man-pages/man1/ls.1.html)       |
| `ls \| xargs wc`                    | Words/lines/bytes in dir       | [xargs(1)](https://man7.org/linux/man-pages/man1/xargs.1.html) |
| `ls -a`                             | List files incl. hidden        | [ls(1)](https://man7.org/linux/man-pages/man1/ls.1.html)       |
| `mkdir [name]`                      | Create a directory             | [mkdir(1)](https://man7.org/linux/man-pages/man1/mkdir.1.html) |
| `more [file]`                       | Show file contents             | [more(1)](https://man7.org/linux/man-pages/man1/more.1.html)   |
| `mv [old] [new]`                    | Rename/move a file             | [mv(1)](https://man7.org/linux/man-pages/man1/mv.1.html)       |
| `pwd`                               | Show current directory         | [pwd(1)](https://man7.org/linux/man-pages/man1/pwd.1.html)     |
| `rm [file]`                         | Remove a file                  | [rm(1)](https://man7.org/linux/man-pages/man1/rm.1.html)       |
| `rm -r [directory]`                 | Recursively remove dir         | [rm(1)](https://man7.org/linux/man-pages/man1/rm.1.html)       |
| `rm -rf [directory]`                | Force remove dir               | [rm(1)](https://man7.org/linux/man-pages/man1/rm.1.html)       |
| `shred -u [file]`                   | Overwrite & delete file        | [shred(1)](https://man7.org/linux/man-pages/man1/shred.1.html) |
| `source [file]`                     | Execute file in current shell  | [bash(1)](https://man7.org/linux/man-pages/man1/bash.1.html)   |
| `sudo`                              | Run command as super‑user      | [sudo(8)](https://man7.org/linux/man-pages/man8/sudo.8.html)   |
| `tail [file]`                       | Show last 10 lines             | [tail(1)](https://man7.org/linux/man-pages/man1/tail.1.html)   |
| `touch [file]`                      | Create / update file           | [touch(1)](https://man7.org/linux/man-pages/man1/touch.1.html) |
| `wc`                                | Count words/lines/bytes        | [wc(1)](https://man7.org/linux/man-pages/man1/wc.1.html)       |
| `[cmd] \| tee [file] >/dev/null`    | Store output, skip terminal    | [tee(1)](https://man7.org/linux/man-pages/man1/tee.1.html)     |
| `[data] \| cut -d[delim]`           | Cut data section & print       | [cut(1)](https://man7.org/linux/man-pages/man1/cut.1.html)     |

### Text Editors

| Command        | Description        | Man Page                                                       |
| -------------- | ------------------ | -------------------------------------------------------------- |
| `nano [file]`  | Simple text editor | [nano(1)](https://man7.org/linux/man-pages/man1/nano.1.html)   |
| `vim [file]`   | Vi improved editor | [vim(1)](https://man7.org/linux/man-pages/man1/vim.1.html)     |
| `emacs [file]` | Emacs text editor  | [emacs(1)](https://man7.org/linux/man-pages/man1/emacs.1.html) |

### Directory Navigation

| Command          | Description                   | Man Page                                                  |
| ---------------- | ----------------------------- | --------------------------------------------------------- |
| `cd ..`          | Move up one level             | [cd(1)](https://man7.org/linux/man-pages/man1/cd.1p.html) |
| `cd`             | Change dir to `$HOME`         | [cd(1)](https://man7.org/linux/man-pages/man1/cd.1p.html) |
| `cd [/location]` | Change to specified directory | [cd(1)](https://man7.org/linux/man-pages/man1/cd.1p.html) |

### Hardware Information

| Command                    | Description                | Man Page                                                               |
| -------------------------- | -------------------------- | ---------------------------------------------------------------------- |
| `badblocks -s /dev/[disk]` | Unreadable blocks test     | [badblocks(8)](https://man7.org/linux/man-pages/man8/badblocks.8.html) |
| `cat /proc/cpuinfo`        | Show CPU information       | [cat(1)](https://man7.org/linux/man-pages/man1/cat.1.html)             |
| `dmesg`                    | Show boot‑up messages      | [dmesg(1)](https://man7.org/linux/man-pages/man1/dmesg.1.html)         |
| `dmidecode`                | Show BIOS hardware info    | [dmidecode(8)](https://man7.org/linux/man-pages/man8/dmidecode.8.html) |
| `free -h`                  | Show free & used memory    | [free(1)](https://man7.org/linux/man-pages/man1/free.1.html)           |
| `hdparm -i /dev/[disk]`    | Show disk data info        | [hdparm(8)](https://man7.org/linux/man-pages/man8/hdparm.8.html)       |
| `hdparm -tT /dev/[disk]`   | Disk read‑speed test       | [hdparm(8)](https://man7.org/linux/man-pages/man8/hdparm.8.html)       |
| `lsblk`                    | Block‑device info          | [lsblk(8)](https://man7.org/linux/man-pages/man8/lsblk.8.html)         |
| `lshw`                     | Hardware configuration     | [lshw(1)](https://man7.org/linux/man-pages/man1/lshw.1.html)           |
| `lspci -tv`                | Tree of PCI devices        | [lspci(8)](https://man7.org/linux/man-pages/man8/lspci.8.html)         |
| `lsusb -tv`                | Tree of USB devices        | [lsusb(8)](https://man7.org/linux/man-pages/man8/lsusb.8.html)         |
| `neofetch`                 | Display OS & hardware info | External tool                                                          |

### File Compression

| Command                        | Description                  | Man Page                                                                                                                    |
| ------------------------------ | ---------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| `7z x [file.7z]`               | Extract 7zip archive         | External tool                                                                                                               |
| `gunzip [file.gz]`             | Decompress gzip file         | [gzip(1)](https://man7.org/linux/man-pages/man1/gzip.1.html)                                                                |
| `gzip [file]`                  | Create `.gz`‑compressed file | [gzip(1)](https://man7.org/linux/man-pages/man1/gzip.1.html)                                                                |
| `rar x [file.rar]`             | Extract RAR archive          | External tool                                                                                                               |
| `tar cf [file.tar] [file]`     | Create a tar from file       | [tar(1)](https://man7.org/linux/man-pages/man1/tar.1.html)                                                                  |
| `tar czf [file.tar.gz] [file]` | Create gzip‑tar file         | [tar(1)](https://man7.org/linux/man-pages/man1/tar.1.html)                                                                  |
| `tar tzf [file.tar.gz]`        | List tar contents            | [tar(1)](https://man7.org/linux/man-pages/man1/tar.1.html)                                                                  |
| `tar xf [file.tar]`            | Extract tar file             | [tar(1)](https://man7.org/linux/man-pages/man1/tar.1.html)                                                                  |
| `zip/unzip -r`                 | Package & compress files     | [zip(1)](https://man7.org/linux/man-pages/man1/zip.1.html) / [unzip(1)](https://man7.org/linux/man-pages/man1/unzip.1.html) |

### Package Installation

| Command                                        | Description                      | Man Page                                                           |
| ---------------------------------------------- | -------------------------------- | ------------------------------------------------------------------ |
| `apt-get`                                      | Search/install software packages | [apt-get(8)](https://man7.org/linux/man-pages/man8/apt-get.8.html) |
| `apt install [package]`                        | Install with APT                 | [apt(8)](https://man7.org/linux/man-pages/man8/apt.8.html)         |
| `dnf install [package]`                        | Install with DNF                 | [dnf(8)](https://man7.org/linux/man-pages/man8/dnf.8.html)         |
| `rpm -i [package.rpm]`                         | Install an RPM                   | [rpm(8)](https://man7.org/linux/man-pages/man8/rpm.8.html)         |
| `rpm -e [package.rpm]`                         | Remove an RPM                    | [rpm(8)](https://man7.org/linux/man-pages/man8/rpm.8.html)         |
| `tar xzf [source.tar.gz]`                      | Extract source code              | [tar(1)](https://man7.org/linux/man-pages/man1/tar.1.html)         |
| `cd [source]; ./configure; make; make install` | Compile & install from source    | [make(1)](https://man7.org/linux/man-pages/man1/make.1.html)       |
| `yum info [package]`                           | Package info summary             | [yum(8)](https://man7.org/linux/man-pages/man8/yum.8.html)         |
| `yum install [package.rpm]`                    | Install with YUM                 | [yum(8)](https://man7.org/linux/man-pages/man8/yum.8.html)         |
| `yum search [keyword]`                         | Find a package                   | [yum(8)](https://man7.org/linux/man-pages/man8/yum.8.html)         |

### System Management

| Command                 | Description              | Man Page                                                                   |
| ----------------------- | ------------------------ | -------------------------------------------------------------------------- |
| `cal`                   | Show current day & month | [cal(1)](https://man7.org/linux/man-pages/man1/cal.1.html)                 |
| `date`                  | Show current time & date | [date(1)](https://man7.org/linux/man-pages/man1/date.1.html)               |
| `finger [user]`         | Show user information    | [finger(1)](https://man7.org/linux/man-pages/man1/finger.1.html)           |
| `hostname`              | Show system hostname     | [hostname(1)](https://man7.org/linux/man-pages/man1/hostname.1.html)       |
| `hostname -I`           | Show system IP           | [hostname(1)](https://man7.org/linux/man-pages/man1/hostname.1.html)       |
| `last reboot`           | Show reboot history      | [last(1)](https://man7.org/linux/man-pages/man1/last.1.html)               |
| `modprobe [module]`     | Add kernel module        | [modprobe(8)](https://man7.org/linux/man-pages/man8/modprobe.8.html)       |
| `shutdown [hh:mm]`      | Schedule shutdown        | [shutdown(8)](https://man7.org/linux/man-pages/man8/shutdown.8.html)       |
| `shutdown now`          | Shutdown immediately     | [shutdown(8)](https://man7.org/linux/man-pages/man8/shutdown.8.html)       |
| `timedatectl`           | Manage system clock      | [timedatectl(1)](https://man7.org/linux/man-pages/man1/timedatectl.1.html) |
| `ulimit [flag] [limit]` | View/limit resources     | [ulimit(1)](https://man7.org/linux/man-pages/man1/ulimit.1p.html)          |
| `uname -a`              | Show kernel release      | [uname(1)](https://man7.org/linux/man-pages/man1/uname.1.html)             |
| `uname -r`              | Show kernel version      | [uname(1)](https://man7.org/linux/man-pages/man1/uname.1.html)             |
| `uptime`                | Show uptime/load         | [uptime(1)](https://man7.org/linux/man-pages/man1/uptime.1.html)           |
| `whoami`                | Show current user        | [whoami(1)](https://man7.org/linux/man-pages/man1/whoami.1.html)           |

### System Monitoring

| Command       | Description                | Man Page                                                         |
| ------------- | -------------------------- | ---------------------------------------------------------------- |
| `htop`        | Interactive process viewer | External tool                                                    |
| `iostat`      | I/O statistics             | [iostat(1)](https://man7.org/linux/man-pages/man1/iostat.1.html) |
| `nmon`        | Performance monitor        | External tool                                                    |
| `sar`         | System activity reporter   | [sar(1)](https://man7.org/linux/man-pages/man1/sar.1.html)       |
| `vmstat`      | Virtual memory stats       | [vmstat(8)](https://man7.org/linux/man-pages/man8/vmstat.8.html) |
| `watch [cmd]` | Execute command repeatedly | [watch(1)](https://man7.org/linux/man-pages/man1/watch.1.html)   |

### Service Management

| Command                      | Description            | Man Page                                                               |
| ---------------------------- | ---------------------- | ---------------------------------------------------------------------- |
| `service [service] restart`  | Restart service (SysV) | [service(8)](https://man7.org/linux/man-pages/man8/service.8.html)     |
| `systemctl enable [service]` | Enable service at boot | [systemctl(1)](https://man7.org/linux/man-pages/man1/systemctl.1.html) |
| `systemctl start [service]`  | Start systemd service  | [systemctl(1)](https://man7.org/linux/man-pages/man1/systemctl.1.html) |
| `systemctl status [service]` | Show service status    | [systemctl(1)](https://man7.org/linux/man-pages/man1/systemctl.1.html) |
| `systemctl stop [service]`   | Stop systemd service   | [systemctl(1)](https://man7.org/linux/man-pages/man1/systemctl.1.html) |

### File System Operations

| Command                 | Description            | Man Page                                                         |
| ----------------------- | ---------------------- | ---------------------------------------------------------------- |
| `fdisk -l`              | List disk partitions   | [fdisk(8)](https://man7.org/linux/man-pages/man8/fdisk.8.html)   |
| `fsck [device]`         | Check filesystem       | [fsck(8)](https://man7.org/linux/man-pages/man8/fsck.8.html)     |
| `mkfs.ext4 [device]`    | Create ext4 filesystem | [mkfs(8)](https://man7.org/linux/man-pages/man8/mkfs.8.html)     |
| `mount [device] [path]` | Mount filesystem       | [mount(8)](https://man7.org/linux/man-pages/man8/mount.8.html)   |
| `umount [path]`         | Unmount filesystem     | [umount(8)](https://man7.org/linux/man-pages/man8/umount.8.html) |

### Log Management

| Command            | Description             | Man Page                                                                 |
| ------------------ | ----------------------- | ------------------------------------------------------------------------ |
| `journalctl`       | Query systemd journal   | [journalctl(1)](https://man7.org/linux/man-pages/man1/journalctl.1.html) |
| `logger [message]` | Write to system log     | [logger(1)](https://man7.org/linux/man-pages/man1/logger.1.html)         |
| `logrotate`        | Rotate log files        | [logrotate(8)](https://man7.org/linux/man-pages/man8/logrotate.8.html)   |
| `tail -f [file]`   | Follow log file changes | [tail(1)](https://man7.org/linux/man-pages/man1/tail.1.html)             |

### File Permission

| Command                       | Description             | Man Page                                                           |
| ----------------------------- | ----------------------- | ------------------------------------------------------------------ |
| `chmod 755 [file]`            | Owner all; others rx    | [chmod(1)](https://man7.org/linux/man-pages/man1/chmod.1.html)     |
| `chmod 764 [file]`            | Owner all; others rw    | [chmod(1)](https://man7.org/linux/man-pages/man1/chmod.1.html)     |
| `chmod 777 [file]`            | Everyone rwx            | [chmod(1)](https://man7.org/linux/man-pages/man1/chmod.1.html)     |
| `chown [user] [file]`         | Change owner            | [chown(1)](https://man7.org/linux/man-pages/man1/chown.1.html)     |
| `chown [user]:[group] [file]` | Change owner & group    | [chown(1)](https://man7.org/linux/man-pages/man1/chown.1.html)     |
| `getfacl [file]`              | Get file ACLs           | [getfacl(1)](https://man7.org/linux/man-pages/man1/getfacl.1.html) |
| `setfacl [options] [file]`    | Set file ACLs           | [setfacl(1)](https://man7.org/linux/man-pages/man1/setfacl.1.html) |
| `umask`                       | Set default permissions | [umask(1)](https://man7.org/linux/man-pages/man1/umask.1p.html)    |

### SSH Login

| Command                           | Description        | Man Page                                                   |
| --------------------------------- | ------------------ | ---------------------------------------------------------- |
| `ssh [user]@[host]`               | SSH login          | [ssh(1)](https://man7.org/linux/man-pages/man1/ssh.1.html) |
| `ssh [host]`                      | SSH with defaults  | [ssh(1)](https://man7.org/linux/man-pages/man1/ssh.1.html) |
| `ssh -p [port] [user]@[host]`     | SSH on custom port | [ssh(1)](https://man7.org/linux/man-pages/man1/ssh.1.html) |
| `scp [file] [user]@[host]:[path]` | Secure copy        | [scp(1)](https://man7.org/linux/man-pages/man1/scp.1.html) |

### Variables (bash)

| Command                    | Description                | Man Page                                                             |
| -------------------------- | -------------------------- | -------------------------------------------------------------------- |
| `declare variable="value"` | Declare variable           | [bash(1)](https://man7.org/linux/man-pages/man1/bash.1.html)         |
| `echo ${variable}`         | Display value              | [echo(1)](https://man7.org/linux/man-pages/man1/echo.1.html)         |
| `env`                      | Display environment        | [env(1)](https://man7.org/linux/man-pages/man1/env.1.html)           |
| `export variable`          | Export variable            | [bash(1)](https://man7.org/linux/man-pages/man1/bash.1.html)         |
| `let "var=$((num))"`       | Integer arithmetic         | [bash(1)](https://man7.org/linux/man-pages/man1/bash.1.html)         |
| `printenv [var]`           | Print environment variable | [printenv(1)](https://man7.org/linux/man-pages/man1/printenv.1.html) |
| `set`                      | List variables             | [bash(1)](https://man7.org/linux/man-pages/man1/bash.1.html)         |
| `unset [var]`              | Remove variable            | [bash(1)](https://man7.org/linux/man-pages/man1/bash.1.html)         |

### Wildcards / Globbing

| Pattern     | Matches              | Reference                                                    |
| ----------- | -------------------- | ------------------------------------------------------------ |
| `*`         | Any string           | [glob(7)](https://man7.org/linux/man-pages/man7/glob.7.html) |
| `?`         | Any single char      | [glob(7)](https://man7.org/linux/man-pages/man7/glob.7.html) |
| `[abc]`     | a or b or c          | [glob(7)](https://man7.org/linux/man-pages/man7/glob.7.html) |
| `[a‑z]`     | Any lowercase letter | [glob(7)](https://man7.org/linux/man-pages/man7/glob.7.html) |
| `[0‑9]`     | Any digit            | [glob(7)](https://man7.org/linux/man-pages/man7/glob.7.html) |
| `{foo,bar}` | `foo` or `bar`       | [bash(1)](https://man7.org/linux/man-pages/man1/bash.1.html) |

### Filters

| Command | Description            | Man Page                                                     |
| ------- | ---------------------- | ------------------------------------------------------------ |
| `cat`   | Concatenate & print    | [cat(1)](https://man7.org/linux/man-pages/man1/cat.1.html)   |
| `cut`   | Cut by columns         | [cut(1)](https://man7.org/linux/man-pages/man1/cut.1.html)   |
| `sort`  | Sort text              | [sort(1)](https://man7.org/linux/man-pages/man1/sort.1.html) |
| `uniq`  | Remove duplicates      | [uniq(1)](https://man7.org/linux/man-pages/man1/uniq.1.html) |
| `tr`    | Translate/delete chars | [tr(1)](https://man7.org/linux/man-pages/man1/tr.1.html)     |
| `grep`  | Pattern search         | [grep(1)](https://man7.org/linux/man-pages/man1/grep.1.html) |
| `sed`   | Stream editor          | [sed(1)](https://man7.org/linux/man-pages/man1/sed.1.html)   |
| `awk`   | Pattern scanning       | [awk(1)](https://man7.org/linux/man-pages/man1/awk.1p.html)  |

### Disk Usage

| Command    | Description         | Man Page                                                 |
| ---------- | ------------------- | -------------------------------------------------------- |
| `df -h`    | Free disk space     | [df(1)](https://man7.org/linux/man-pages/man1/df.1.html) |
| `du -sh *` | Dir sizes (summary) | [du(1)](https://man7.org/linux/man-pages/man1/du.1.html) |
| `du -ah`   | File & dir sizes    | [du(1)](https://man7.org/linux/man-pages/man1/du.1.html) |

### Process Control

| Command           | Description                   | Man Page                                                                                                                        |
| ----------------- | ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| `bg`              | Resume job in background      | [bash(1)](https://man7.org/linux/man-pages/man1/bash.1.html)                                                                    |
| `disown`          | Remove job from shell         | [bash(1)](https://man7.org/linux/man-pages/man1/bash.1.html)                                                                    |
| `fg`              | Bring job to foreground       | [bash(1)](https://man7.org/linux/man-pages/man1/bash.1.html)                                                                    |
| `jobs`            | List active jobs              | [bash(1)](https://man7.org/linux/man-pages/man1/bash.1.html)                                                                    |
| `kill [pid]`      | Kill PID                      | [kill(1)](https://man7.org/linux/man-pages/man1/kill.1.html)                                                                    |
| `killall [name]`  | Kill by name                  | [killall(1)](https://man7.org/linux/man-pages/man1/killall.1.html)                                                              |
| `nice` / `renice` | Priority control              | [nice(1)](https://man7.org/linux/man-pages/man1/nice.1.html) / [renice(1)](https://man7.org/linux/man-pages/man1/renice.1.html) |
| `nohup [cmd] &`   | Run command immune to hangups | [nohup(1)](https://man7.org/linux/man-pages/man1/nohup.1.html)                                                                  |
| `pgrep [pattern]` | Find processes by name        | [pgrep(1)](https://man7.org/linux/man-pages/man1/pgrep.1.html)                                                                  |
| `pkill [pattern]` | Kill processes by name        | [pgrep(1)](https://man7.org/linux/man-pages/man1/pgrep.1.html)                                                                  |
| `ps aux`          | List processes                | [ps(1)](https://man7.org/linux/man-pages/man1/ps.1.html)                                                                        |
| `top` / `htop`    | Live process monitor          | [top(1)](https://man7.org/linux/man-pages/man1/top.1.html)                                                                      |

### Searching

| Command                     | Description      | Man Page                                                           |
| --------------------------- | ---------------- | ------------------------------------------------------------------ |
| `grep -r [pat] [path]`      | Recursive grep   | [grep(1)](https://man7.org/linux/man-pages/man1/grep.1.html)       |
| `locate [name]`             | Find by name     | [locate(1)](https://man7.org/linux/man-pages/man1/locate.1.html)   |
| `find [path] -name "*pat*"` | Find files       | [find(1)](https://man7.org/linux/man-pages/man1/find.1.html)       |
| `whereis [cmd]`             | Locate binaries  | [whereis(1)](https://man7.org/linux/man-pages/man1/whereis.1.html) |
| `which [cmd]`               | Full path of cmd | [which(1)](https://man7.org/linux/man-pages/man1/which.1.html)     |

### Scripting Snippets

| Snippet                    | Purpose              | Reference                                                    |
| -------------------------- | -------------------- | ------------------------------------------------------------ |
| `#!/bin/bash`              | Script shebang       | [bash(1)](https://man7.org/linux/man-pages/man1/bash.1.html) |
| `$(command)`               | Command substitution | [bash(1)](https://man7.org/linux/man-pages/man1/bash.1.html) |
| `$((expr))`                | Arithmetic           | [bash(1)](https://man7.org/linux/man-pages/man1/bash.1.html) |
| `if [ cond ]; then … fi`   | Conditional          | [bash(1)](https://man7.org/linux/man-pages/man1/bash.1.html) |
| `for x in list; do … done` | Loop                 | [bash(1)](https://man7.org/linux/man-pages/man1/bash.1.html) |
| `function name() { … }`    | Function             | [bash(1)](https://man7.org/linux/man-pages/man1/bash.1.html) |
| `exit 0`                   | Successful exit      | [bash(1)](https://man7.org/linux/man-pages/man1/bash.1.html) |

---

> **Hint** Use `man <command>` or `<command> --help` for details on any entry. Click the man page links above for comprehensive online documentation.+
> **Note** This cheat sheet is a quick reference and does not cover all options or commands. For more detailed information, refer to the respective man pages or online documentation.
