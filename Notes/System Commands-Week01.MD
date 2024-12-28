# System Commands

*Prof. Gandham PhaniKumar*  
*Notes by Adarsh 23f2003570*  

## [Lecture 1 - Launching a Linux Virtual Machine](https://youtu.be/PHrN7yp1AJw?list=PLZ2ps__7DhBajgl-4et7X2BjOIObqlp81)

1. Setup Virtual Box
2. Setup VMWare player
3. WSL
4. Tmux app on android

## [Lecture 3 - Simple Commands in Linux - 1](https://youtu.be/DIpBEmRDHnw?list=PLZ2ps__7DhBajgl-4et7X2BjOIObqlp81)

### Commands
| Command Name       | Description               |
| ------------------ | ------------------------- |
| date               | Date commands             |
| cal (Week Columns) | calendar of month         |
| ncal (week rows)   | calendar of month         |
| free               | mem statistics            |
| groups             | groups a users belongs to |
| file               | what kind of file         |

#### date
```sh
date [OPTION]... [+FORMAT]
date [-u|--utc|--universal] [MMDDhhmm[[CC]YY][.ss]]

       --debug
              annotate the parsed date, and warn about questionable usage to stderr
       -f, --file=DATEFILE
              like --date; once for each line of DATEFILE
       -I[FMT], --iso-8601[=FMT]
              output  date/time  in  ISO 8601 format.  FMT='date' for date only (the default), 'hours', 'minutes', 'seconds', or 'ns' for date and
              time to the indicated precision.  Example: 2006-08-14T02:34:56-06:00
       -R, --rfc-email
              output date and time in RFC 5322 format.  Example: Mon, 14 Aug 2006 02:34:56 -0600
       --rfc-3339=FMT
              output date/time in RFC 3339 format.  FMT='date', 'seconds', or 'ns' for  date  and  time  to  the  indicated  precision.   Example:
              2006-08-14 02:34:56-06:00
       -r, --reference=FILE
              display the last modification time of FILE

       -s, --set=STRING
              set time described by STRING
       -u, --utc, --universal
              print or set Coordinated Universal Time (UTC)


FORMAT controls the output.  Interpreted sequences are:
       %%     a literal %
       %a     locale's abbreviated weekday name (e.g., Sun)
       %A     locale's full weekday name (e.g., Sunday)
       %b     locale's abbreviated month name (e.g., Jan)
       %B     locale's full month name (e.g., January)
       %c     locale's date and time (e.g., Thu Mar  3 23:05:25 2005)
       %C     century; like %Y, except omit last two digits (e.g., 20)
       %d     day of month (e.g., 01)
       %D     date; same as %m/%d/%y
       %e     day of month, space padded; same as %_d
       %F     full date; like %+4Y-%m-%d
       %g     last two digits of year of ISO week number (see %G)
       %G     year of ISO week number (see %V); normally useful only with %V
       %h     same as %b
       %H     hour (00..23)
       %I     hour (01..12)
       %j     day of year (001..366)
       %k     hour, space padded ( 0..23); same as %_H
       %l     hour, space padded ( 1..12); same as %_I
       %m     month (01..12)
       %M     minute (00..59)
       %n     a newline
       %N     nanoseconds (000000000..999999999)
       %p     locale's equivalent of either AM or PM; blank if not known
       %P     like %p, but lower case
       %q     quarter of year (1..4)
       %r     locale's 12-hour clock time (e.g., 11:11:04 PM)
       %R     24-hour hour and minute; same as %H:%M
       %s     seconds since 1970-01-01 00:00:00 UTC
       %S     second (00..60)
       %t     a tab
       %T     time; same as %H:%M:%S
       %u     day of week (1..7); 1 is Monday
       %U     week number of year, with Sunday as first day of week (00..53)
       %V     ISO week number, with Monday as first day of week (01..53)
       %w     day of week (0..6); 0 is Sunday
       %W     week number of year, with Monday as first day of week (00..53)
       %x     locale's date representation (e.g., 12/31/99)
       %y     last two digits of year (00..99)
       %Y     year
       %z     +hhmm numeric time zone (e.g., -0400)
       %:z    +hh:mm numeric time zone (e.g., -04:00)
       %::z   +hh:mm:ss numeric time zone (e.g., -04:00:00)
       %:::z  numeric time zone with : to necessary precision (e.g., -04, +05:30)
       %Z     alphabetic time zone abbreviation (e.g., EDT)
```


#### Cal

```sh
➜  ~ cal 19/08/1975
cal: not a valid year 19/08/1975
➜  ~ cal 19-08-1975
cal: not a valid year 19-08-1975
➜  ~ cal 1975-08-19
cal: not a valid year 1975-08-19
➜  ~ cal 1975-19-08
cal: not a valid year 1975-19-08
➜  ~ cal August 19th 1975
Usage: cal [general options] [-jy] [[month] year]
       cal [general options] [-j] [-m month] [year]
       ncal -C [general options] [-jy] [[month] year]
       ncal -C [general options] [-j] [-m month] [year]
       ncal [general options] [-bhJjpwySM] [-H yyyy-mm-dd] [-s country_code] [-W number of days] [[month] year]
       ncal [general options] [-Jeo] [year]
General options: [-31] [-A months] [-B months] [-d yyyy-mm]
➜  ~ cal August 1975
    August 1975
Su Mo Tu We Th Fr Sa
                1  2
 3  4  5  6  7  8  9
10 11 12 13 14 15 16
17 18 19 20 21 22 23
24 25 26 27 28 29 30
31
➜  ~ cal 08-1975
cal: not a valid year 08-1975
➜  ~ cal 1975-08
cal: not a valid year 1975-08

➜  ~ cal 08 1975
    August 1975
Su Mo Tu We Th Fr Sa
                1  2
 3  4  5  6  7  8  9
10 11 12 13 14 15 16
17 18 19 20 21 22 23
24 25 26 27 28 29 30
31

➜  ~ ncal
    December 2024
Su  1  8 15 22 29
Mo  2  9 16 23 30
Tu  3 10 17 24 31
We  4 11 18 25
Th  5 12 19 26
Fr  6 13 20 27
Sa  7 14 21 28

➜  ~ ncal aug 1975
    August 1975
Su     3 10 17 24 31
Mo     4 11 18 25
Tu     5 12 19 26
We     6 13 20 27
Th     7 14 21 28
Fr  1  8 15 22 29
Sa  2  9 16 23 30
```

### Free Command

```sh
➜  ~ free
               total        used        free      shared  buff/cache   available
Mem:        32696656     1059472    27627008       49164     4010176    31143244
Swap:        8388608           0     8388608
➜  ~ free -h
               total        used        free      shared  buff/cache   available
Mem:            31Gi       1.0Gi        26Gi        48Mi       3.8Gi        29Gi
Swap:          8.0Gi          0B       8.0Gi
➜  ~ free -H
free: invalid option -- 'H'
```


### Groups

```sh
➜  ~ groups
sysop adm cdrom sudo dip plugdev lxd docker pitchdeck

➜  ~ groups deck
groups: ‘deck’: no such user

➜  ~ groups root
root : root

➜  ~ groups pitchdeck
pitchdeck : pitchdeck sudo docker
```

### ls command

```
➜  ~ ls -al
total 333564
drwxr-xr-x  2 sysop sysop      4096 Apr  8  2024 .vim
-rw-------  1 sysop sysop     24746 Dec 26 20:25 .viminfo
drwxr-xr-x  3 sysop sysop      4096 Nov 11 18:34 .vscode-remote-containers
drwxr-xr-x  5 sysop sysop      4096 Nov 11 15:26 .vscode-server
drwxrwxrwx  8 sysop sysop      4096 Nov 11 18:11 Week06
-rw-r--r--  1 sysop sysop       297 Dec 26 17:46 .wget-hsts
```
for 'drwxrwxrwx'

hyphenate into `d-rwx-rwx-rwx` (U-G-O oo-go)

1. d = directory, - = files, l = link => see file types below
2. 1st group of the `rwx` is permission for user (uid) who owns this entry
3. 2nd group of the `rwx` is permission for users from groups (gids) this entry is owned by
4. 3rd group of the `rwx` is permission for everyone else
5. 2,1,3,5,8,1 are number of `hard links`
6. `sysop:sysop` is `uid:gid` the user and group that owns this
7. 4096, 24746, 297 are the number of bytes this entity takes

| Prefix | FileType       |
| ------ | -------------- |
| -      | Regular File   |
| d      | Directory      |
| l      | Symbolic Link  |
| c      | character file |
| b      | block file     |
| s      | socket file    |
| p      | named pipe     |


Examples of sockets and regular files

```
srw-rw----  1 root docker    0 Dec 27 11:11 docker-cli.sock
-rw-r--r--  1 root root      3 Dec 27 11:11 docker-desktop-proxy.pid
srw-rw----  1 root docker    0 Dec 27 11:11 docker.sock
```


### INode

```
➜  service ls -il
total 8
 4503599627732285 drwxrwxrwx 1 sysop sysop 4096 Dec 27 19:28 app
 5629499534664223 -rwxrwxrwx 1 sysop sysop 1627 Sep 27 18:37 build.sh
  281474977091450 -rwxrwxrwx 1 sysop sysop  186 Jun 27  2022 connect.sh
 4222124651146735 -rwxrwxrwx 1 sysop sysop 1783 May 17  2023 docker-compose-exporter-services.yml
 7036874418717800 -rwxrwxrwx 1 sysop sysop  513 Sep 24 12:33 Dockerfile
  281474977091452 -rwxrwxrwx 1 sysop sysop  289 Jun 27  2022 list-gcr-tags.sh
27021597764579708 -rwxrwxrwx 1 sysop sysop  385 May  2  2024 push-image-to-repository.sh
  281474977091454 -rwxrwxrwx 1 sysop sysop  276 May 16  2022 remove-build.bat
 8444249301727427 -rwxrwxrwx 1 sysop sysop  522 Jun 29  2023 run-as-command.sh
 1688849860751019 -rwxrwxrwx 1 sysop sysop  464 May 17  2023 run-as-service.sh
```