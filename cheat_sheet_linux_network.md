# Linux Network Commands Cheat Sheet

| Command             | Purpose                                                        | Ubuntu 24.04 Install Command      | RedHat 9 Install Command           | Amazon Linux 2023 Install Command     |
|---------------------|----------------------------------------------------------------|-----------------------------------|------------------------------------|---------------------------------------|
| `ip`                | Show/manage network interfaces, addresses, and routing tables   | pre-installed (iproute2)          | pre-installed (iproute)            | pre-installed (iproute2)              |
| `ss`                | Detailed socket statistics (modern replacement for `netstat -s`)| pre-installed (iproute2)          | pre-installed (iproute)            | pre-installed (iproute2)              |
| `arp`               | View or modify the kernel ARP cache                            | pre-installed (net-tools)         | pre-installed (net-tools)          | sudo yum install net-tools            |
| `dig`               | Query DNS name servers                                         | sudo apt install dnsutils         | sudo dnf install bind-utils        | sudo yum install bind-utils           |
| `mtr`               | Combine `traceroute` and `ping` in real time                   | sudo apt install mtr              | sudo dnf install mtr               | sudo yum install mtr                  |
| `scp`               | Secure file copy over SSH                                      | sudo apt install openssh-client   | sudo dnf install openssh-clients   | sudo yum install openssh-clients      |
| `sftp`              | Interactive file transfer over SSH                             | sudo apt install openssh-client   | sudo dnf install openssh-clients   | sudo yum install openssh-clients      |
| `ping`              | Test reachability and packet loss                              | pre-installed (iputils-ping)      | pre-installed (iputils)            | pre-installed (iputils)               |
| `host`              | Simple DNS lookups (IPv4/IPv6, MX, TXT, etc.)                  | sudo apt install dnsutils         | sudo dnf install bind-utils        | sudo yum install bind-utils           |
| `wget`              | Non-interactive file download via HTTP/HTTPS/FTP               | sudo apt install wget             | sudo dnf install wget              | sudo yum install wget                 |
| `curl`              | Transfer data to/from URLs; supports many protocols            | sudo apt install curl             | sudo dnf install curl              | sudo yum install curl                 |
| `nmap`              | Network discovery and security scanning                        | sudo apt install nmap             | sudo dnf install nmap              | sudo yum install nmap                 |
| `bmon`              | Real-time bandwidth monitor                                    | sudo apt install bmon             | sudo dnf install bmon              | sudo yum install bmon                 |
| `nmcli`             | Control NetworkManager from the command line                   | sudo apt install network-manager  | sudo dnf install NetworkManager    | sudo yum install NetworkManager       |
| `nload`             | Live per-interface traffic graph                               | sudo apt install nload            | sudo dnf install nload             | sudo yum install nload                |
| `whois`             | Query domain registration records                              | sudo apt install whois            | sudo dnf install whois             | sudo yum install whois                |
| `route`             | Legacy routing table viewer (use `ip route` now)               | pre-installed (net-tools)         | pre-installed (net-tools)          | sudo yum install net-tools            |
| `rsync`             | Efficient file/directory sync (SSH ready)                      | sudo apt install rsync            | sudo dnf install rsync             | sudo yum install rsync                |
| `iftop`             | Real-time per-connection bandwidth usage                       | sudo apt install iftop            | sudo dnf install iftop             | sudo yum install iftop                |
| `iperf3`            | Active bandwidth and jitter testing                            | sudo apt install iperf3           | sudo dnf install iperf3            | sudo yum install iperf3               |
| `vnstat`            | Persistent network traffic logging                             | sudo apt install vnstat           | sudo dnf install vnstat            | sudo yum install vnstat               |
| `tshark`            | CLI packet capture and analysis (`wireshark` engine)           | sudo apt install tshark           | sudo dnf install wireshark-cli     | sudo yum install wireshark-cli        |
| `netcat` (`nc`)     | Read/write raw data across TCP/UDP                             | sudo apt install netcat-openbsd   | sudo dnf install nmap-ncat         | sudo yum install nmap-ncat            |
| `tcpdump`           | Fundamental/core packet sniffer                                | sudo apt install tcpdump          | sudo dnf install tcpdump           | sudo yum install tcpdump              |
| `ethtool`           | Query or tune Ethernet device settings                         | sudo apt install ethtool          | sudo dnf install ethtool           | sudo yum install ethtool              |
| `netstat`           | Connections, routing, statistics (deprecated; use `ss`)        | pre-installed (net-tools)         | pre-installed (net-tools)          | sudo yum install net-tools            |
| `nslookup`          | Interactive DNS queries (legacy)                               | sudo apt install dnsutils         | sudo dnf install bind-utils        | sudo yum install bind-utils           |
| `hostnamectl`       | View or set system host name                                   | pre-installed (systemd)           | pre-installed (systemd)            | pre-installed (systemd)               |
| `iw` / `iwconfig`   | Manage wireless interfaces (`iw` is newer)                     | sudo apt install iw wireless-tools | sudo dnf install iw wireless-tools | sudo yum install iw wireless-tools    |
| `ifconfig`          | Legacy interface config (superseded by `ip`/`ip a`)            | sudo apt install net-tools        | sudo dnf install net-tools         | sudo yum install net-tools            |
| `tracepath`         | Trace route without elevated/root privileges                   | sudo apt install iputils-tracepath | sudo dnf install iputils           | sudo yum install iputils              |
| `traceroute`        | Classic packet path trace                                      | sudo apt install traceroute       | sudo dnf install traceroute        | sudo yum install traceroute           |
| `ifplugstatus`      | Detect cable/PHY link state                                    | sudo apt install ifplugd          | sudo dnf install ifplugd           | sudo yum install ifplugd              |
