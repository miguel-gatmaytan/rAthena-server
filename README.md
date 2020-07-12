# Server
> This package is a server generated using rAthena. Instructions for this server taken originally from https://rathena.org/board/topic/114177-tutorial-how-to-create-server-client-2018-step-by-step-debian-linux/

### Table of Contents
1. [Prerequisites](#1-prerequisites)
2. [Installation](#2-installation)
3. [Troubleshooting](#3-troubleshooting)
4. [More Documentation](#4-more-documentation)
5. [How to Contribute](#5-how-to-contribute)
6. [License](#6-license)

## 1. Prerequisites
Before installing rAthena there are certain tools and applications you will need which
differs between the varying operating systems available.

### Hardware
Hardware Type | Minimum | Recommended
------|------|------
CPU | 1 Core | 2 Cores
RAM | 1 GB | 2 GB
Disk Space | 300 MB | 500 MB

### Operating System & Preferred Compiler
Operating System | Compiler
------|------
Linux  | [gcc-5 or newer](https://www.gnu.org/software/gcc/gcc-5/) / [Make](https://www.gnu.org/software/make/)
Windows | [MS Visual Studio 2013, 2015, 2017](https://www.visualstudio.com/downloads/)

### Required Applications
Application | Name
------|------
Database | [MySQL 5 or newer](https://www.mysql.com/downloads/) / [MariaDB 5 or newer](https://downloads.mariadb.org/)
Git | [Windows](https://gitforwindows.org/) / [Linux](https://git-scm.com/download/linux)

### Optional Applications
Application | Name
------|------
Database | [MySQL Workbench 5 or newer](http://www.mysql.com/downloads/workbench/)

## 2. Installation 

### Full Installation Instructions
  * [Windows](https://github.com/rathena/rathena/wiki/Install-on-Windows)
  * [CentOS](https://github.com/rathena/rathena/wiki/Install-on-Centos)
  * [Debian](https://github.com/rathena/rathena/wiki/Install-on-Debian)
  * [FreeBSD](https://github.com/rathena/rathena/wiki/Install-on-FreeBSD)

## 3. After Install

After following the instructions above, you need to update the rAthena configs.

> rAthena/conf/inter_athena.conf

```

// MySQL Login server
login_server_ip: 127.0.0.1
login_server_port: 3306
login_server_id: ragnarok
login_server_pw: password123 <---- CHANGE THIS TO YOUR DB USER AND PW!
login_server_db: ragnarok
login_codepage:
login_case_sensitive: no

ipban_db_ip: 127.0.0.1
ipban_db_port: 3306
ipban_db_id: ragnarok
ipban_db_pw: password123 <---- CHANGE THIS TO YOUR DB USER AND PW!
ipban_db_db: ragnarok
ipban_codepage:

// MySQL Character server
char_server_ip: 127.0.0.1
char_server_port: 3306
char_server_id: ragnarok
char_server_pw: password123 <---- CHANGE THIS TO YOUR DB USER AND PW!
char_server_db: ragnarok

// MySQL Map Server
map_server_ip: 127.0.0.1
map_server_port: 3306
map_server_id: ragnarok
map_server_pw: password123 <---- CHANGE THIS TO YOUR DB USER AND PW!
map_server_db: ragnarok

// MySQL Log Database
log_db_ip: 127.0.0.1
log_db_port: 3306
log_db_id: ragnarok
log_db_pw: password123 <---- CHANGE THIS TO YOUR DB USER AND PW!
log_db_db: ragnarok
log_codepage:
log_login_db: loginlog
```

>rAthena/conf/char_athena.conf
```
char_ip: 192.168.111.133 <-- CHANGE THIS TO YOUR VM IP ADDRESS!
```

>rAthena/conf/map_athena.conf
```
map_ip: 192.168.111.133 <-- CHANGE THIS TO YOUR VM IP ADDRESS!
```

After updating all of that, you should be able to recompile and start the server!

```
./configure --enable-packetver=20180418
make clean
make server

./athena-start start
```
