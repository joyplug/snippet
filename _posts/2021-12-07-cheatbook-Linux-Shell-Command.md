---
layout: post
title:  "[cheatbook] Linux Shell Command"
date:   2021-12-07 23:55:00 +0900
categories: [cheatbook]
---

```bash
alias ls='ls --color=auto --time-style=long-iso'
```

```bash
vim .bashrc
LANG=en_US.UTF8
source .bashrc
/etc/bash.bashrc
```

```bash
du -h * | sort -nr > $HOME/script.txt     //sort -r
```

```bash
#!/bin/bash
#!/usr/bin/python
which bash  //환경변수 PATH 변수의 경로 내에서 실행 파일의 이름 검색
whereis bash  //명령의 실행파일, 소스, 맨페이지의 위치 검색
find /usr/bin -name bash -exec ls -l '{}' \;
```

```bash
mount -t ext3 /dev/hda1 /backup
```

```bash
cat /etc/shells
echo $SHELL
ps $$
echo $$
env
```

```bash
man ls | col -b | cat
```

```bash
date '+%H:%M'   //12:08
date -u
date --utc
date --universal
```

```bash
shopt -o emacs  //default
shopt -o vi
shopt -os vi   //or shopt -os emacs
```

```bash
FILENAME="test.txt"
printf "%s\n" $FILENAME
echo $FILENAME
```

```bash
# 변수에 쉘 명령의 결과를 지정할 때  `명령어`  (option+~)  또는 $(명령어) 형식을 사용
DATE=`date`
DATE=$(date)
printf "%s\n" "$DATE"
echo $DATE
```

```bash
history 
!!  //가장 최근의 명령 실행.  
!-1 date; sleep 2; !#  //명령을 두번 실행 
date; sleep 2; date; sleep 2;
Fri 29 Oct 2021 12:22:36 PM UTC
Fri 29 Oct 2021 12:22:38 PM UTC
```

`tree -L 1 /`
```bash
/
├── bin -> usr/bin
├── boot
├── dev
├── etc
├── home
├── lib -> usr/lib
├── lib32 -> usr/lib32
├── lib64 -> usr/lib64
├── libx32 -> usr/libx32
├── lost+found
├── media
├── mnt
├── opt
├── proc
├── root
├── run
├── sbin -> usr/sbin
├── snap
├── srv
├── sys
├── tmp
├── usr
└── var
```

```bash
less /var/log/messages  //q로 종료 시 내용 사라짐
more /var/log/messages  //q로 종료 시 내용 유지
cat /var/log/messages
```

> file test.txt  
```bash
test.txt: empty
test.txt: ASCII text
test.txt: UTF-8 Unicode text
test.html: HTML document text
test.rpm: ... RPM v3 bin ...
text.tgz: ... gzip compressed data,...
/etc/rc.d/init.d/sshd: Bourne-Again shell script text executable
/usr/bin/gcc: ELF 32-bit LSB executable,...
text.so: ELF 32-bit LSB shared object,...
```

```bash
ls -l | grep ^d  //d로 시작하는 라인출력
cp -i file1 file2  //덮어쓰기 여부 물어봄
mv -i file2 file2 //덮어쓰기 여부 물어봄
```

```bash
cat /dev/null > deleted_content.txt
echo "" > deleted_content.txt
```

```bash
sort < ls.txt > sorted_ls.txt
```

```bash
ls -al --color=never | less
```

```bash
du -h --max-depth 1 | sort -nr
du -h --max-depth 0
find . -type f -print | wc -l
```

```bash
> fmt :: 형식화
> pr :: 페이지단위로 나누기
> lpr :: lpr 프린터로 프린팅
> uniq :: 중복항목 제거
cat test.txt | fmt | pr | lpr
cat unsorted_list.txt | sort | uniq | pr | lpr
tar -tvzf tarfile.tgz | less
```

```bash
> xargs 이전의 입력들을 다음 명령어의 입력파리미터로 전달
find /etc | xargs grep umask
```

```bash
lsattr
chattr +i attribution.txt  //삭제불가능
chattr -i attribution.txt
chattr +a attribution.txt //수정가능, 삭제불가능
chattr -a attribution.txt
```

```bash
jobs
kill %1  //job number, not pid
```

```bash
users
who -q
who
groups
```

```bash
usermod -g multi linux  //multi 유저의 그룹을 linux로 바꾸기
groupmod -n shellscript multi  //그룹이름 multi를 shellscript로 변경하기
```

```bash
>> who
sulsa21  pts/0        2021-10-30 12:02 (XXX.XXX.XXX.XXX)
>> w
12:42:50 up 1 day, 23:08,  1 user,  load average: 0.07, 0.03, 0.00
USER     TTY      FROM             LOGIN@   IDLE   JCPU   PCPU WHAT
sulsa21  pts/0    000.000.000.000   12:02    1.00s  0.09s  0.02s sshd: sulsa21 [priv]
>> w | grep sshd
```

```bash
logname
whomai
file /var/run/utmp
/var/run/utmp: dBase III DBT, version number 0, next free block index 2
```

```bash
ac  //유저의 로그인 시간
    total        9.39
file /var/log/wtmp
```

```bash
>> last | head -n 5   //유저의 마지막 로그인 시간
sulsa21  pts/0        182.226.219.20   Sat Oct 30 12:02   still logged in
sulsa21  pts/0        182.226.219.20   Fri Oct 29 12:04 - 14:29  (02:25)
root     pts/0        182.226.219.20   Fri Oct 29 12:02 - 12:03  (00:01)
sulsa21  pts/0        182.226.219.20   Fri Oct 29 12:00 - 12:02  (00:01)
sulsa21  pts/0        182.226.219.20   Fri Oct 29 11:39 - 12:00  (00:20)
```

```bash
>> wall hi
Broadcast message from sulsa21@sulsa21-11815 (pts/0) (Sat Oct 30 12:51:51 2021)
hi
```

```bash
>> write sulsa21
```

```bash
root@sulsa21-11815:~# uname
Linux
root@sulsa21-11815:~# uname -a
Linux sulsa21-11815 5.4.0-89-generic #100-Ubuntu SMP Fri Sep 24 14:50:10 UTC 2021 x86_64 x86_64 x86_64 GNU/Linux
root@sulsa21-11815:~# arch
x86_64
root@sulsa21-11815:~# uname -m
x86_64
```

```bash
root@sulsa21-11815:~# lastlog | head -n 5
Username         Port     From             Latest
root             pts/0    XXX.XXX.XXX.XXX   Fri Oct 29 12:02:44 +0000 2021
daemon                                     **Never logged in**
bin                                        **Never logged in**
sys                                        **Never logged in**
```

```bash
>> root@sulsa21-11815:~# lsof | head -n 5   //오픈된 파일 목록
COMMAND     PID  TID TASKCMD               USER   FD      TYPE             DEVICE SIZE/OFF       NODE NAME
systemd       1                            root  cwd       DIR              252,1     4096          2 /
systemd       1                            root  rtd       DIR              252,1     4096          2 /
systemd       1                            root  txt       REG              252,1  1620224      28477 /usr/lib/systemd/systemd
systemd       1                            root  mem       REG              252,1  1369352      33156 /usr/lib/x86_64-linux-gnu/libm-2.31.so
>> root@sulsa21-11815:~# lsof -an -i tcp | grep IPv4  // -i 옵션은 오픈되어 있는 네트워크 소켓 파일
systemd-r   547 systemd-resolve   13u  IPv4  18718      0t0  TCP 127.0.0.53:domain (LISTEN)
sshd        635            root    3u  IPv4  21295      0t0  TCP *:ssh (LISTEN)
sshd      25079            root    4u  IPv4 499095      0t0  TCP 172.16.0.6:ssh->000.000.000.000:50115 (ESTABLISHED)
```

```bash
>> free
              total        used        free      shared  buff/cache   available
Mem:         489404      135908       58104         972      295392      331832
Swap:             0           0           0
```

```bash
root@sulsa21-11815:~# free
              total        used        free      shared  buff/cache   available
Mem:         489404      132996       58084         972      298324      334772
Swap:             0           0           0
root@sulsa21-11815:~# free | grep Mem | awk '{print $5}'
972
```

```bash
procinfo
lsdev
dmesg  //부팅 콘솔 메시지
stat install.log  //파일의 정보 출력, atime/mtime,ctime 확인 가능
root@sulsa21-11815:~# vmstat
procs -----------memory---------- ---swap-- -----io---- -system-- ------cpu-----
r b swpd free buff cache si so bi bo in cs us sy id wa st
0 0 0 88388 12580 250448 0 0 14 16 23 41 0 0 99 0 0
```

```bash
>> root@sulsa21-11815:~# netstat -lptu
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address Foreign Address State PID/Program name
tcp 0 0 localhost:domain 0.0.0.0:* LISTEN 547/systemd-resolve
tcp 0 0 0.0.0.0:ssh 0.0.0.0:* LISTEN 635/sshd: /usr/sbin
tcp6 0 0 [::]:ssh [::]:* LISTEN 635/sshd: /usr/sbin
udp 0 0 localhost:domain 0.0.0.0:* 547/systemd-resolve
udp 0 0 sulsa21-11815:bootpc 0.0.0.0:* 545/systemd-network
>> root@sulsa21-11815:~# uptime
 13:09:55 up 1 day, 23:35,  1 user,  load average: 0.00, 0.01, 0.00
>> root@sulsa21-11815:~# hostname
sulsa21-11815
>> uname -n
>> echo $HOSTNAME
```

```bash
>> root@sulsa21-11815:~# readelf -h /bin/bash
ELF Header:
  Magic:   7f 45 4c 46 02 01 01 00 00 00 00 00 00 00 00 00
  Class:                             ELF64
  Data:                              2's complement, little endian
  Version:                           1 (current)
  OS/ABI:                            UNIX - System V
  ABI Version:                       0
  Type:                              DYN (Shared object file)
  Machine:                           Advanced Micro Devices X86-64
  Version:                           0x1
  Entry point address:               0x30430
  Start of program headers:          64 (bytes into file)
  Start of section headers:          1181528 (bytes into file)
  Flags:                             0x0
  Size of this header:               64 (bytes)
  Size of program headers:           56 (bytes)
  Number of program headers:         13
  Size of section headers:           64 (bytes)
  Number of section headers:         30
  Section header string table index: 29
>> root@sulsa21-11815:~# size /bin/bash
   text       data        bss        dec        hex    filename
1127387      47356      40056    1214799     12894f    /bin/bash
```

```bash
logger  // messages 에 저장, Ctrl+D 로 종료
cat /etc/logrotate.conf  
```

```bash
>> root@sulsa21-11815:~# ps -ef --forest | grep sshd
root         635       1  0 Oct28 ?        00:00:09 sshd: /usr/sbin/sshd -D [listener] 1 of 10-100 startups
root       25079     635  0 12:02 ?        00:00:00  \_ sshd: sulsa21 [priv]
sulsa21    25195   25079  0 12:02 ?        00:00:00  |   \_ sshd: sulsa21@pts/0
root       28067   27671  0 13:15 pts/0    00:00:00  |                   \_ grep --color=auto sshd
root       28050     635  0 13:13 ?        00:00:00  \_ sshd: [accepted]
```

```bash
pgrep sshd
ps -ef | grep sshd
pgrep -u root httpd
pgrep -u root,daemon
pkill -HUP syslogd  //환경 설정 파일을 다시 읽으려면
```

```bash
>> root@sulsa21-11815:~# pstree
systemd─┬─accounts-daemon───2*[{accounts-daemon}]
        ├─2*[agetty]
        ├─atd
        ├─cron
        ├─dbus-daemon
        ├─multipathd───6*[{multipathd}]
        ├─networkd-dispat
        ├─polkitd───2*[{polkitd}]
        ├─rsyslogd───3*[{rsyslogd}]
        ├─snapd───8*[{snapd}]
        ├─sshd───sshd───sshd───sh───su───bash───pstree
        ├─systemd───(sd-pam)
        ├─systemd-journal
        ├─systemd-logind
        ├─systemd-network
        ├─systemd-resolve
        ├─systemd-timesyn───{systemd-timesyn}
        ├─systemd-udevd
        └─unattended-upgr───{unattended-upgr}
```

```bash
nice telnet  //default 10,  -20(High) ~ 19(Low)
ps axl | grep telnet   //NI값 10 확인
nice -n -20 telnet
ps axl | grep telnet   //NI값 -20 확인
```

```bash
nohup find / -name sshd &   //Hangup 신호 무시, 표준출력과 표준에러는 nohup.out 파일에 추가됨
```

```bash
root@sulsa21-11815:~# pidof sshd
25195 25079 635
root@sulsa21-11815:~# fuser -u /usr/sbin/sshd
/usr/sbin/sshd:        635e(root) 25079e(root) 25195e(sulsa21)
root@sulsa21-11815:~# fuser -u /dev/null
/dev/null:               1(root)   333(root)   362(root)   447(root)   496(systemd-timesync)   545(systemd-network)   547(systemd-resolve)   583(root)   586(root)   587(messagebus)   594(root)   595(syslog)   598(root)   600(root)   602(daemon)   635(root)   640(root)   648(root) 25079(root) 25089(sulsa21) 25093(sulsa21) 25195(sulsa21) 28144(root) 28145(sshd)
root@sulsa21-11815:~# fuser -un tcp 25
```

```bash
tcpdump tcp port 22
```

```bash
>> root@sulsa21-11815:~# lsusb
Bus 001 Device 002: ID 0627:0001 Adomax Technology Co., Ltd QEMU USB Tablet
Bus 001 Device 001: ID 1d6b:0001 Linux Foundation 1.1 root hub
>> root@sulsa21-11815:~# lspci
00:00.0 Host bridge: Intel Corporation 440FX - 82441FX PMC [Natoma] (rev 02)
00:01.0 ISA bridge: Intel Corporation 82371SB PIIX3 ISA [Natoma/Triton II]
00:01.1 IDE interface: Intel Corporation 82371SB PIIX3 IDE [Natoma/Triton II]
00:01.2 USB controller: Intel Corporation 82371SB PIIX3 USB [Natoma/Triton II] (rev 01)
00:01.3 Bridge: Intel Corporation 82371AB/EB/MB PIIX4 ACPI (rev 03)
00:02.0 VGA compatible controller: Red Hat, Inc. QXL paravirtual graphic card (rev 04)
00:03.0 Ethernet controller: Red Hat, Inc. Virtio network device
00:04.0 Communication controller: Red Hat, Inc. Virtio console
00:05.0 SCSI storage controller: Red Hat, Inc. Virtio block device
00:06.0 Unclassified device [00ff]: Red Hat, Inc. Virtio memory balloon
```

```bash
>> root@sulsa21-11815:~# ldd /bin/ls   //공유라이브러리의 의존성 출력
    linux-vdso.so.1 (0x00007ffc61bab000)
    libselinux.so.1 => /lib/x86_64-linux-gnu/libselinux.so.1 (0x00007fdb05680000)
    libc.so.6 => /lib/x86_64-linux-gnu/libc.so.6 (0x00007fdb05488000)
    libpcre2-8.so.0 => /lib/x86_64-linux-gnu/libpcre2-8.so.0 (0x00007fdb053f8000)
    libdl.so.2 => /lib/x86_64-linux-gnu/libdl.so.2 (0x00007fdb053f0000)
    /lib64/ld-linux-x86-64.so.2 (0x00007fdb056e0000)
    libpthread.so.0 => /lib/x86_64-linux-gnu/libpthread.so.0 (0x00007fdb053c8000)
```

```bash
watch -n 5 tail /var/log/messages
watch -n 60 from   //60초마다 메일 확인
watch -d ls -l  //디렉토리 내 변경된 파일 감시
```

```bash
gcc test.c
nm a.out  //strip되지 않은 컴파일된 오브젝트 파일의 심볼 목록 출력
strip a.out //오브젝트 파일의 디버깅 심볼 레퍼런스를 제거하여 파일 크기를 줄임. 추후 디버깅은 불가능
```

```
```
```
```
```
```
```
```
```

```
```
