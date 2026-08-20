
**🐧 LINUX + SHELL SCRIPTING COMPLETE NOTES**
**1. Navigation Commands**
**pwd**
Purpose: Present Working Directory ni check cheyadaniki / manam ippudu ekkada unnamo telusukovadaniki use chestam.
pwd
Example:
/home/btl/go-web-app
Remember: pwd → Where am I?

**ls**
Purpose: Current directory lo unna files and directories list ni chudataniki use chestam.

**ls -l**
Purpose: Files and directories ni detailed information tho list cheyadaniki use chestam.
It shows:
permissions
owner
group
size
modified date/time
filename
ls -l

Remember: -l → long/detailed listing

**ls -la**
Purpose: Files ni detailed information tho patu hidden files kuda chudataniki use chestam.
ls -la
-l → detailed
-a → all files including hidden files
Example hidden files:
.bashrc
.git
.env

**ls -lh**
Purpose: Files detailed information ni human-readable file sizes tho chudataniki use chestam.
ls -lh
Example:
10K
25M
2G
-l → detailed
-h → human readable

**ls -lt**
Purpose: Files ni modification time prakaram sort cheyadaniki use chestam.
ls -lt
Newest modified file first vastundi.
-l → detailed
-t → time based sorting

**ls -ltr**
Purose: Files ni modification time prakaram reverse order lo list cheyadaniki use chestam.
ls -ltr

Usually:
Oldest → Newest
-l → detailed
-t → time sorting
-r → reverse

**ls -R**
Purpose: Current directory tho patu subdirectories lopala files/directories kuda recursively list cheyadaniki use chestam.
ls -R
Remember: -R → Recursive

**cd**
Full form: Change Directory
Purpose: Oka directory nunchi another directory ki move avvadaniki use chestam.
cd Documents

**cd ..**
Purpose: Current directory nunchi one level parent directory ki velladaniki use chestam.
cd ..
Example:
/home/btl/project/backend
cd ..
/home/btl/project
Remember: .. → one level up

**cd ../..**
Purpose: Current directory nunchi two levels up velladaniki use chestam.
cd ../..
Example:
/home/btl/project/backend/src

After:
/home/btl/project

**cd -**
Purpose: Manam previously unna previous directory ki return avvadaniki use chestam.
cd -
Example:
/var/log
then:
cd /home/btl
cd -
returns to:
/var/log
Remember: cd - → previous directory

**cd ~**
Purpose: Current user's home directory ki velladaniki use chestam.
For btl:
~ = /home/btl
cd ~

**cd /**
Purpose: Linux filesystem yokka root directory ki velladaniki use chestam.
cd /
Root directory:
/





**2. Files & Directories**
**touch**
Purpose: Empty file create cheyadaniki use chestam.
touch script.sh
Remember: touch → create file

**mkdir**
Full form: Make Directory
Purpose: New folder/directory create cheyadaniki use chestam.
mkdir project

**mkdir -p**
Purpose: Parent directories avi already lekapoyina nested directories create cheyadaniki use chestam.
mkdir -p project/backend/src
project, backend, src lekapoyina automatically create chestundi.
Remember: -p → parent directories kuda create

**file**
Purpose: File yokka type ni identify cheyadaniki use chestam.
file script.sh
Example:
Bourne-Again shell script

**stat**
Purpose: File yokka detailed metadata chudataniki use chestam.
stat file.txt

It shows:
size
permissions
owner
inode
access time
modification time
change time

**tree**
Purpose: Directory structure ni tree format lo chudataniki use chestam.
tree project/
Example:

project
├── backend
│   └── main.py
└── frontend
    └── package.json


    
**3. View File Contents**
**cat**
Purpose: File content ni display/view cheyadaniki use chestam.
cat file.txt

**tac**
Purpose: File content ni reverse line order lo display chestundi.
tac file.txt

cat:
line 1
line 2
line 3

tac:
line 3
line 2
line 1
Remember: tac = cat reverse

**less**
Purpose: Large files ni page by page chudataniki use chestam.
less app.log

Exit:
q

**more**
Purpose: Large file content ni page by page chudataniki use chestam.
more app.log
less and more similar, but less generally more flexible.

**head**
Purpose: File yokka starting lines chudataniki use chestam.
head file.txt
Default ga first 10 lines.
head -n 5 file.txt
First 5 lines.

**tail**
Purpose: File yokka last lines chudataniki use chestam.
tail file.txt
Last 10 lines.

**tail -f**
Purpose: File ki new content add avutunte live ga monitor cheyadaniki use chestam.
tail -f app.log
DevOps lo logs monitoring ki very useful.

**nl**
Purpose: File lines ki line numbers add chesi display cheyadaniki use chestam.
nl file.txt

**wc**
Full form: Word Count
Purpose: File lo lines, words, bytes/characters count cheyadaniki use chestam.
wc file.txt

**Important:**
wc -l file.txt
→ number of lines

wc -w file.txt
→ number of words

wc -c file.txt
→ bytes

**strings**
Purpose: Binary file lo readable text strings ni extract cheyadaniki use chestam.
strings app
Useful when inspecting binary files.





**4. Edit Files**
**vi**
Purpose: Terminal lo files create/edit cheyadaniki use chestam.
vi script.sh

**Important modes:**
i       → insert mode
Esc     → command mode
:w      → save
:q      → quit
:wq     → save + quit
:q!     → quit without saving

**vim**
Purpose: vi yokka improved/advanced version. Terminal lo files edit cheyadaniki use chestam.
vim script.sh
Basic commands vi laga untayi.

**nano**
Purpose: Simple and easy terminal text editor. File create/edit cheyadaniki use chestam.
nano script.sh

Save:
Ctrl + O
Enter
Exit:
Ctrl + X




**5. Copy / Move / Delete**
**cp**
Full form: Copy
Purpose: File or directory ni copy cheyadaniki use chestam.
cp file.txt backup.txt

Directory:
cp -r project backup/

**mv**
Full form: Move
Purpose: File/directory ni move or rename cheyadaniki use chestam.

Move:
mv file.txt /tmp/

Rename:
mv old.txt new.txt

**rm:**
Full form: Remove
Purpose: Files/directories ni delete cheyadaniki use chestam.
rm file.txt

Directory:
rm -r project

**Force:**
rm -rf project
⚠️ rm -rf very carefully use cheyali.

**rmdir**
Purpose: Empty directory ni delete cheyadaniki use chestam.
rmdir test
Directory empty kakapothe rmdir work avvadu.





**🔐 6. Permissions & Ownership**
**chmod**
Full form: Change Mode
Purpose: File/directory permissions change cheyadaniki use chestam.
chmod +x script.sh

Then:
./script.sh

Common:
chmod 755 script.sh
chmod 644 file.txt

**chown**
Full form: Change Owner
Purpose: File/directory owner change cheyadaniki use chestam.
sudo chown btl file.txt
Owner + group:
sudo chown btl:developers file.txt


**chgrp**
Full form: Change Group
Purpose: File/directory yokka group ownership change cheyadaniki use chestam.
sudo chgrp developers file.txt

**umask**
Purpose: New files/directories create ayinappudu default permissions determine cheyadaniki use chestam.
umask

Set:
umask 022



**🔎 7. Searching**
**grep**
Purpose: Files or command output lo specific text/pattern search cheyadaniki use chestam.
grep "error" app.log
Case insensitive:
grep -i "error" app.log

**Recursive:**
grep -r "database" .

**find**

Purpose: Files and directories ni name, type, size, time etc. based on search cheyadaniki use chestam.

find . -name "*.sh"

Only files:

find . -type f

Only directories:

find . -type d
locate

Purpose: System lo files ni quickly search cheyadaniki use chestam.

locate nginx.conf

It uses a database, so very recent files sometimes database update avvakapothe kanipinchakapovachu.

which

Purpose: Command executable ekkada undho chupistundi.

which python

Example:

/usr/bin/python
whereis

Purpose: Command yokka binary, source, manual locations ni search chestundi.

whereis nginx
type

Purpose: Command ye type ani identify cheyadaniki use chestam.

type cd
type ls

It can tell you:

alias
builtin
function
executable
command

Purpose: Shell lo command ni execute/check cheyadaniki use chestam; aliases/functions ni bypass cheyadaniki kuda useful.

command -v python

Check command existence:

command -v nginx
📝 8. Text Processing
grep

Purpose: Text/pattern search cheyadaniki.

grep "ERROR" app.log
awk

Purpose: Text lo columns/fields ni extract and process cheyadaniki use chestam.

ps -ef | awk '{print $1}'

Important:

$0 → complete line
$1 → first column
$2 → second column
$3 → third column
NF → number of fields
NR → line number
sed

Purpose: Text ni search, replace, modify cheyadaniki use chestam.

sed 's/old/new/g' file.txt
cut

Purpose: Specific column/field ni extract cheyadaniki use chestam.

cut -d: -f1 /etc/passwd
-d: → delimiter :
-f1 → first field
sort

Purpose: Lines ni sort cheyadaniki use chestam.

sort names.txt

Reverse:

sort -r names.txt

Numeric:

sort -n numbers.txt
uniq

Purpose: Duplicate consecutive lines ni remove/count cheyadaniki use chestam.

sort names.txt | uniq

Count:

sort names.txt | uniq -c
tr

Full form: Translate

Purpose: Characters ni replace/delete/convert cheyadaniki use chestam.

echo "hello" | tr 'a-z' 'A-Z'

Output:

HELLO
paste

Purpose: Multiple files/lines ni side-by-side columns ga combine cheyadaniki use chestam.

paste file1.txt file2.txt
join

Purpose: Two files lo common field based on combine/join cheyadaniki use chestam.

join file1 file2

Database SQL JOIN concept laga think cheyochu.

split

Purpose: Large file ni small files ga split cheyadaniki use chestam.

split -l 100 file.txt

Every output file lo 100 lines.

xargs

Purpose: Input ni next command ki arguments ga pass cheyadaniki use chestam.

cat files.txt | xargs rm
tee

Purpose: Output ni terminal lo display chestu file lo save cheyadaniki use chestam.

ls | tee files.txt
column

Purpose: Text output ni proper columns/table format lo display cheyadaniki use chestam.

cat data.txt | column -t
rev

Purpose: Each line characters ni reverse cheyadaniki use chestam.

echo "hello" | rev

Output:

olleh
fold

Purpose: Long lines ni specified width ki break/wrap cheyadaniki use chestam.

fold -w 20 file.txt
🔗 9. Pipes & Redirection
|

Purpose: Oka command yokka output ni next command input ga pass cheyadaniki use chestam.

ps -ef | grep postgres

Flow:

ps -ef
  ↓
output
  ↓
grep postgres
  ↓
filtered output
>

Purpose: Command output ni file lo write/overwrite cheyadaniki.

ls > files.txt

Existing content overwrite avutundi.

>>

Purpose: Output ni file ki append cheyadaniki.

echo "hello" >> file.txt

Existing content delete avvadu.

<

Purpose: File content ni command ki input ga provide cheyadaniki.

sort < names.txt
2>

Purpose: Error output (stderr) ni file ki redirect cheyadaniki.

command 2> error.log
2>>

Purpose: Error output ni file ki append cheyadaniki.

command 2>> error.log
2>&1

Purpose: stderr ni stdout same location ki redirect cheyadaniki.

command > output.log 2>&1

Both normal output + errors:

output.log
&>

Purpose: Bash lo stdout + stderr rendu same file ki redirect cheyadaniki.

command &> output.log
📚 10. Help & Documentation
man

Purpose: Command yokka complete manual/details chudataniki use chestam.

man chmod

Exit:

q
info

Purpose: Command/software yokka detailed documentation chudataniki.

info coreutils
help

Purpose: Bash built-in commands ki help chudataniki.

help cd
whatis

Purpose: Command yokka short description chudataniki.

whatis chmod
apropos

Purpose: Specific keyword ki related commands/manual pages ni search cheyadaniki.

apropos network
🕘 11. History
history

Purpose: Manam previously execute chesina commands history chudataniki.

history
history 10

Purpose: Last 10 commands chudataniki.

history 10
!!

Purpose: Previous command ni again execute cheyadaniki.

!!

Example:

ls
!!

Second !! again ls execute chestundi.

!100

Purpose: History lo command number 100 ni execute cheyadaniki.

!100
history | grep docker

Purpose: History lo docker related commands search cheyadaniki.

history | grep docker
🖥️ 12. System Information
uname

Purpose: Operating system/kernel information chudataniki.

uname -a
hostname

Purpose: Machine/server yokka hostname chudataniki.

hostname
hostnamectl

Purpose: Hostname and system information chudataniki/change cheyadaniki.

hostnamectl
arch

Purpose: System architecture chudataniki.

arch

Example:

x86_64
date

Purpose: Current date and time chudataniki.

date
timedatectl

Purpose: System date, time, timezone and NTP synchronization information chudataniki.

timedatectl
uptime

Purpose: System entha time nunchi running lo undo and system load chudataniki.

uptime
whoami

Purpose: Current ga manam ye user tho login ayyam ani telusukovadaniki.

whoami
id

Purpose: Current user yokka UID, GID and groups chudataniki.

id
who

Purpose: System lo currently logged-in users chudataniki.

who
w

Purpose: Logged-in users tho patu what they are doing/system activity chudataniki.

w
users

Purpose: Currently logged-in users usernames chudataniki.

users
last

Purpose: Previous login history chudataniki.

last
lastlog

Purpose: Users yokka last login information chudataniki.

lastlog
🧠 13. CPU
nproc

Purpose: Machine lo available CPU processing units number chudataniki.

nproc

Example:

8

Means 8 processing units available.

lscpu

Purpose: CPU yokka complete hardware information chudataniki.

lscpu
top

Purpose: System health and running processes ni real-time lo monitor cheyadaniki.

top

Shows:

CPU usage
Memory
Processes
Load average
htop

Purpose: top kanna more interactive and user-friendly process/system monitor.

htop
vmstat

Purpose: CPU, memory, processes, I/O etc. yokka system performance statistics chudataniki.

vmstat
mpstat

Purpose: CPU usage ni processor/core-wise monitor cheyadaniki.

mpstat
🧮 14. Memory
free

Purpose: System lo RAM and swap memory usage chudataniki.

free
free -h

Purpose: RAM/swap information ni human-readable format lo chudataniki.

free -h
vmstat

Purpose: Memory tho patu CPU and system performance statistics chudataniki.

vmstat
top

Purpose: Running processes memory and CPU usage ni real-time lo chudataniki.

top
htop

Purpose: Interactive ga CPU + memory + processes monitor cheyadaniki.

htop
💽 15. Disk / Storage
df

Purpose: Filesystem lo disk space usage chudataniki.

df -h

Remember: df → filesystem disk usage

du

Purpose: File/directory entha disk space use chestundo chudataniki.

du -sh folder

Remember: du → directory/file usage

lsblk

Purpose: System lo unna disks and block devices list cheyadaniki.

lsblk
blkid

Purpose: Block devices yokka UUID, filesystem type etc. chudataniki.

sudo blkid
mount

Purpose: Filesystem/device ni directory ki attach/mount cheyadaniki.

sudo mount /dev/sdb1 /mnt
umount

Purpose: Mounted filesystem ni unmount/remove cheyadaniki.

sudo umount /mnt
fdisk

Purpose: Disk partitions ni view/manage cheyadaniki.

sudo fdisk -l

⚠️ Partition changes carefully cheyali.

parted

Purpose: Disk partitions create/manage cheyadaniki.

sudo parted -l
⚙️ 16. Processes
ps

Purpose: Currently running processes chudataniki.

ps
ps -ef

Purpose: All processes ni detailed format lo chudataniki.

ps -ef
ps aux

Purpose: All users/processes yokka detailed process information chudataniki.

ps aux
pgrep

Purpose: Process name based on PID find cheyadaniki.

pgrep nginx
pidof

Purpose: Running program yokka PID find cheyadaniki.

pidof nginx
pstree

Purpose: Processes ni parent-child tree structure lo chudataniki.

pstree
kill

Purpose: PID use chesi process ki signal send cheyadaniki.

kill 1234

Force:

kill -9 1234
killall

Purpose: Process name use chesi matching processes ni kill cheyadaniki.

killall nginx
pkill

Purpose: Process name/pattern based on processes ki signal send cheyadaniki.

pkill nginx
nice

Purpose: New process yokka CPU scheduling priority set cheyadaniki.

nice -n 10 ./script.sh
renice

Purpose: Already running process yokka priority change cheyadaniki.

renice 10 -p 1234
🔄 17. Jobs / Background Processes
jobs

Purpose: Current shell lo running/stopped background jobs chudataniki.

jobs
fg

Full form: Foreground

Purpose: Background job ni foreground ki teesukovadaniki.

fg %1
bg

Full form: Background

Purpose: Stopped job ni background lo continue cheyadaniki.

bg %1
nohup

Purpose: Terminal close/logout ayina command ni continue running lo unchadaniki.

nohup ./app.sh &
wait

Purpose: Background process complete ayye varaku wait cheyadaniki.

wait
disown

Purpose: Job ni current shell job table nunchi remove chesi shell logout tarvata kuda continue avvadaniki help chestundi.

disown %1
⚡ 18. Environment Variables
env

Purpose: Environment variables ni display cheyadaniki.

env
printenv

Purpose: Environment variable values chudataniki.

printenv HOME
export

Purpose: Variable ni environment variable ga child processes ki available cheyadaniki.

export APP_ENV=production
unset

Purpose: Variable ni remove cheyadaniki.

unset APP_ENV
set

Purpose: Shell variables and shell settings chudataniki/set cheyadaniki.

set
🐚 19. Bash Built-ins
echo

Purpose: Text/value ni terminal lo print cheyadaniki.

echo "Hello"
read

Purpose: User nunchi input teesukovadaniki.

read name
printf

Purpose: Formatted output print cheyadaniki.

printf "Hello %s\n" "Devi"
source

Purpose: Another shell file ni current shell lo execute/load cheyadaniki.

source config.sh
alias

Purpose: Long command ki shortcut create cheyadaniki.

alias ll='ls -la'
unalias

Purpose: Existing alias ni remove cheyadaniki.

unalias ll
shift

Purpose: Script arguments ni one position left shift cheyadaniki.

shift

Useful when processing many $1, $2, $3 arguments.

eval

Purpose: String ni shell command laga evaluate/execute cheyadaniki.

eval "echo hello"

⚠️ User-controlled input tho eval dangerous avvachu.

exec

Purpose: Current shell/process ni another command tho replace cheyadaniki.

exec ./app
exit

Purpose: Script/shell ni exit cheyadaniki.

exit 0
return

Purpose: Function nunchi return avvadaniki.

return 0
break

Purpose: Loop ni completely stop cheyadaniki.

break
continue

Purpose: Current loop iteration ni skip chesi next iteration ki velladaniki.

continue
🧩 20. Bash Variables
$0

Purpose: Running script yokka name.

echo "$0"
$1

Purpose: Script ki pass chesina first argument.

./script.sh hello

Inside:

echo "$1"

Output:

hello
$2

Purpose: Second argument.

./script.sh hello world
echo "$2"

Output:

world
$3

Purpose: Third argument.

$#

Purpose: Script ki vachina number of arguments.

echo "$#"
$@

Purpose: Script ki vachina all arguments.

echo "$@"
$?

Purpose: Previous command yokka exit status check cheyadaniki.

ls
echo $?

Usually:

0 → success
non-zero → failure
$$

Purpose: Current shell/script yokka PID.

echo "$$"
$!

Purpose: Last background process yokka PID.

./app &
echo "$!"
$USER

Purpose: Current username.

echo "$USER"
$HOME

Purpose: Current user's home directory path.

echo "$HOME"

Example:

/home/btl
$PWD

Purpose: Current working directory path.

echo "$PWD"
$PATH

Purpose: Shell commands search chese directories list.

echo "$PATH"
🔀 21. Conditions
if

Purpose: Condition true/false based on different code execute cheyadaniki.

if [ "$age" -ge 18 ]; then
    echo "Adult"
fi
then

Purpose: if condition true ayinappudu execute cheyalsina block start chestundi.

if [ "$x" -eq 10 ]; then
    echo "Ten"
fi
else

Purpose: if condition false ayinappudu execute chestundi.

if [ "$x" -eq 10 ]; then
    echo "Ten"
else
    echo "Not Ten"
fi
elif

Purpose: Multiple conditions check cheyadaniki.

if [ "$x" -gt 10 ]; then
    echo "Greater"
elif [ "$x" -eq 10 ]; then
    echo "Equal"
else
    echo "Less"
fi
fi

Purpose: if block ni close chestundi.

case

Purpose: Multiple possible values/options ni handle cheyadaniki.

case "$choice" in
    start)
        echo "Starting"
        ;;
    stop)
        echo "Stopping"
        ;;
    *)
        echo "Invalid"
        ;;
esac
esac

Purpose: case statement ni close chestundi.

test

Purpose: Condition true/false check cheyadaniki.

test -f file.txt
echo $?
[ ]

Purpose: Conditions test cheyadaniki traditional Bash syntax.

[ "$x" -eq 10 ]
[[ ]]

Purpose: Bash lo advanced and safer conditional testing syntax.

[[ "$name" == "Devi" ]]
Comparison Operators
-eq

Numbers equal.

[ "$a" -eq "$b" ]
-ne

Numbers not equal.

[ "$a" -ne "$b" ]
-gt

Greater than.

[ "$a" -gt "$b" ]
-ge

Greater than or equal.

[ "$a" -ge "$b" ]
-lt

Less than.

[ "$a" -lt "$b" ]
-le

Less than or equal.

[ "$a" -le "$b" ]
==

Strings equal check cheyadaniki commonly use chestam.

[[ "$name" == "Devi" ]]
=

String equality in [ ].

[ "$name" = "Devi" ]
!=

Not equal.

[[ "$name" != "Devi" ]]
&&

AND — rendu conditions true undali.

[ "$age" -ge 18 ] && echo "Adult"
||

OR — edaina oka condition true unte saripothundi.

[ "$x" -eq 10 ] || echo "Not 10"
!

Condition ni reverse/not chestundi.

if ! command -v nginx >/dev/null; then
    echo "nginx not installed"
fi
File Tests
-f

Regular file exist avtunda check chestundi.

[ -f file.txt ]
-d

Directory exist avtunda check chestundi.

[ -d project ]
-e

File or directory anything exists check chestundi.

[ -e file.txt ]
-r

Readable aa check chestundi.

[ -r file.txt ]
-w

Writable aa check chestundi.

[ -w file.txt ]
-x

Executable aa check chestundi.

[ -x script.sh ]
-s

File empty kaada / size greater than zero aa check chestundi.

[ -s file.txt ]
🔁 22. Loops
for

Purpose: List/range lo unna values meeda repeated ga commands execute cheyadaniki.

for i in 1 2 3
do
    echo "$i"
done
while

Purpose: Condition true unna varaku repeated ga execute chestundi.

while [ "$count" -lt 5 ]
do
    echo "$count"
    count=$((count + 1))
done
until

Purpose: Condition true ayye varaku loop run chestundi.

until [ "$count" -ge 5 ]
do
    echo "$count"
    count=$((count + 1))
done
do

Loop body start.

for i in 1 2 3
do
    echo "$i"
done
done

Loop body end.

break

Loop ni completely stop chestundi.

continue

Current iteration skip chesi next iteration ki vellutundi.

🛠️ 23. Functions
function

Purpose: Repeatedly use cheyalsina commands ni reusable block ga create cheyadaniki.

function greet {
    echo "Hello"
}

Modern Bash syntax:

greet() {
    echo "Hello"
}
return

Purpose: Function nunchi exit avvadaniki and status return cheyadaniki.

greet() {
    return 0
}
🚨 24. Script Error Handling
set -e

Purpose: Command failure ayite script ni generally stop cheyadaniki.

set -e
set -u

Purpose: Undefined/unset variable use chesthe error ga treat cheyadaniki.

set -u
set -x

Purpose: Script execute chestunnappudu commands ni trace/debug ga display cheyadaniki.

set -x
set +e

Purpose: set -e behavior ni disable cheyadaniki.

set +e
set +u

Purpose: set -u behavior ni disable cheyadaniki.

set +u
set +x

Purpose: Command tracing ni disable cheyadaniki.

set +x
set -o

Purpose: Shell options ni view/set cheyadaniki.

set -o
set -o pipefail

Purpose: Pipeline lo madhyalo command fail ayina failure ni detect cheyadaniki.

set -o pipefail
set -euo pipefail

Purpose: Robust shell scripts lo common safety combination.

set -euo pipefail

Meaning:

-e → command failure ki exit
-u → unset variable error
pipefail → pipeline failures detect
exit

Purpose: Script ni stop chesi exit status return cheyadaniki.

exit 0
return

Purpose: Function nunchi return avvadaniki.

⏰ 25. Date / Time
date

Purpose: Current date and time chudataniki.

date
timedatectl

Purpose: System time, timezone and NTP synchronization status chudataniki.

timedatectl
cal

Purpose: Calendar chudataniki.

cal
sleep

Purpose: Script execution ni specified time pause cheyadaniki.

sleep 5

5 seconds wait chestundi.

time

Purpose: Command execute avvadaniki entha time pattindo measure cheyadaniki.

time ls
🌐 26. Networking
ip

Purpose: Network interfaces, IP addresses and routes manage/check cheyadaniki.

ip addr

or:

ip a
ping

Purpose: Network connectivity/reachability test cheyadaniki.

ping google.com
ss

Purpose: Open/listening ports and network connections chudataniki.

ss -tulpn
netstat

Purpose: Network connections, ports, routing information chudataniki.

netstat -tulpn

Modern Linux lo ss preferred.

traceroute

Purpose: Source nunchi destination varaku packet travel ayye network path/hops chudataniki.

traceroute google.com
tracepath

Purpose: Network path and MTU information trace cheyadaniki.

tracepath google.com
arp

Purpose: Local network lo IP-to-MAC address information chudataniki.

arp -a

Modern systems lo ip neigh commonly preferred.

route

Purpose: Routing table view/manage cheyadaniki.

route -n

Modern systems lo:

ip route

preferred.

hostname

Purpose: System hostname chudataniki.

hostname
🌍 27. DNS
dig

Purpose: DNS records/query information detailed ga chudataniki.

dig google.com
nslookup

Purpose: Domain yokka DNS information query cheyadaniki.

nslookup google.com
host

Purpose: Simple DNS lookup cheyadaniki.

host google.com
resolvectl

Purpose: System DNS resolver information/query cheyadaniki.

resolvectl status
🌐 28. HTTP / Web
curl

Purpose: URL/server tho communicate cheyadaniki and data transfer cheyadaniki use chestam.

curl https://example.com

API test:

curl http://localhost:8000/api/users

Headers:

curl -I https://example.com
wget

Purpose: Mainly files/resources ni download cheyadaniki use chestam.

wget https://example.com/file.zip
🔑 29. SSH / Remote Access
ssh

Purpose: Remote server ki secure ga connect/login avvadaniki.

ssh user@192.168.1.10
scp

Full form: Secure Copy

Purpose: Local and remote machines madhya files copy cheyadaniki.

scp file.txt user@server:/tmp/
sftp

Full form: SSH File Transfer Protocol

Purpose: SSH through secure file transfer cheyadaniki.

sftp user@server
ssh-keygen

Purpose: SSH authentication kosam SSH key pair generate cheyadaniki.

ssh-keygen

Creates:

private key
public key
ssh-copy-id

Purpose: Local public SSH key ni remote server's authorized_keys lo copy cheyadaniki.

ssh-copy-id user@server

After that passwordless SSH login possible.

📦 30. Compression / Archives
tar

Purpose: Files/directories ni archive create/extract cheyadaniki.

Create:

tar -czf backup.tar.gz project/

Extract:

tar -xzf backup.tar.gz
gzip

Purpose: File ni gzip format lo compress cheyadaniki.

gzip file.txt
gunzip

Purpose: .gz file ni decompress cheyadaniki.

gunzip file.txt.gz
zip

Purpose: ZIP archive create cheyadaniki.

zip backup.zip file.txt
unzip

Purpose: ZIP archive extract cheyadaniki.

unzip backup.zip
bzip2

Purpose: Files ni bzip2 format lo compress cheyadaniki.

bzip2 file.txt
bunzip2

Purpose: .bz2 files decompress cheyadaniki.

bunzip2 file.txt.bz2
xz

Purpose: Files ni xz compression tho compress cheyadaniki.

xz file.txt
unxz

Purpose: .xz file decompress cheyadaniki.

unxz file.txt.xz
👤 31. Users
useradd

Purpose: New user create cheyadaniki.

sudo useradd devuser
adduser

Purpose: New user create cheyadaniki interactive, user-friendly command.

sudo adduser devuser
usermod

Purpose: Existing user properties modify cheyadaniki.

sudo usermod -aG docker btl
userdel

Purpose: User account delete cheyadaniki.

sudo userdel devuser
passwd

Purpose: User password set/change cheyadaniki.

passwd
chage

Purpose: User password expiry/aging settings manage cheyadaniki.

sudo chage -l btl
👥 32. Groups
groupadd

Purpose: New group create cheyadaniki.

sudo groupadd developers
groupmod

Purpose: Existing group properties modify cheyadaniki.

sudo groupmod developers
groupdel

Purpose: Group delete cheyadaniki.

sudo groupdel developers
gpasswd

Purpose: Group membership/admin settings manage cheyadaniki.

sudo gpasswd -a btl developers
groups

Purpose: User belong ayina groups chudataniki.

groups
🔐 33. Security / Authentication
sudo

Purpose: Another user, usually root, privileges tho command execute cheyadaniki.

sudo systemctl restart nginx
su

Full form: Switch User

Purpose: Another user account ki switch avvadaniki.

su - user
visudo

Purpose: /etc/sudoers configuration ni safely edit cheyadaniki.

sudo visudo

Direct ga /etc/sudoers edit cheyadam kanna visudo safer.

passwd

User password manage cheyadaniki.

last

Previous successful logins chudataniki.

lastb

Failed login attempts chudataniki.

sudo lastb
who

Currently logged-in users chudataniki.

w

Logged-in users + activity chudataniki.

📦 34. Ubuntu Package Management
apt

Purpose: Ubuntu/Debian systems lo packages install/update/remove cheyadaniki.

sudo apt install nginx
apt-get

Purpose: Package management kosam traditional command-line tool.

sudo apt-get install nginx
apt-cache

Purpose: Package information/search kosam use chestam.

apt-cache policy nginx
dpkg

Purpose: Debian .deb packages install/manage cheyadaniki.

dpkg -l
sudo apt update

Purpose: Package repositories nunchi latest package index information download cheyadaniki.

sudo apt update
sudo apt upgrade

Purpose: Installed packages ni newer versions ki upgrade cheyadaniki.

sudo apt upgrade
sudo apt install nginx

Purpose: Nginx package install cheyadaniki.

sudo apt install nginx
sudo apt remove nginx

Purpose: Nginx package remove cheyadaniki.

sudo apt remove nginx

Configuration files konni remain avvachu.

sudo apt purge nginx

Purpose: Package tho patu related configuration files kuda remove cheyadaniki.

sudo apt purge nginx
apt search nginx

Purpose: Repository lo nginx-related packages search cheyadaniki.

apt search nginx
dpkg -l

Purpose: Installed .deb packages list chudataniki.

dpkg -l
dpkg -i

Purpose: Local .deb package install cheyadaniki.

sudo dpkg -i package.deb
🔧 35. Services / systemd
systemctl

Purpose: Linux services ni start, stop, restart, enable, disable, status cheyadaniki.

systemctl status nginx

Purpose: Nginx service running aa/stop aa and recent status chudataniki.

systemctl status nginx
systemctl start nginx

Purpose: Nginx service start cheyadaniki.

sudo systemctl start nginx
systemctl stop nginx

Purpose: Nginx service stop cheyadaniki.

sudo systemctl stop nginx
systemctl restart nginx

Purpose: Nginx service stop + start cheyadaniki.

sudo systemctl restart nginx
systemctl reload nginx

Purpose: Service ni completely stop cheyakunda configuration reload cheyadaniki.

sudo systemctl reload nginx
systemctl enable nginx

Purpose: System boot ayinappudu service automatically start avvadaniki enable cheyadaniki.

sudo systemctl enable nginx
systemctl disable nginx

Purpose: Boot time automatic start ni disable cheyadaniki.

sudo systemctl disable nginx
⏰ 36. Scheduling
crontab

Purpose: Repeated/scheduled tasks configure cheyadaniki.

crontab -e
cron

Purpose: Scheduled jobs automatically execute chese background service.

at

Purpose: Oka command ni specific future time lo once execute cheyadaniki.

at 15:00
atq

Purpose: Scheduled at jobs list chudataniki.

atq
atrm

Purpose: Scheduled at job remove cheyadaniki.

atrm 3
crontab -e

Purpose: Cron jobs edit cheyadaniki.

crontab -e
crontab -l

Purpose: Existing cron jobs list chudataniki.

crontab -l
📋 37. Logs
journalctl

Purpose: systemd services/system logs chudataniki.

journalctl

Specific service:

journalctl -u nginx

Live:

journalctl -u nginx -f
dmesg

Purpose: Linux kernel messages chudataniki.

dmesg
logger

Purpose: Custom message ni system log/journal ki send cheyadaniki.

logger "Backup completed"
tail

Log file last lines chudataniki.

tail /var/log/syslog
grep

Log file lo particular error/text search cheyadaniki.

grep "error" app.log
less

Large log files page-by-page chudataniki.

less app.log
tail -f

Live logs monitor cheyadaniki.

tail -f /var/log/nginx/error.log
🧪 38. System Diagnostics
dmesg

Kernel/hardware related messages chudataniki.

lsof

Full form: List Open Files

Purpose: Which process is using a file/port/device ani find cheyadaniki.

sudo lsof -i :8080
strace

Purpose: Program system calls ni trace/debug cheyadaniki.

strace ./app
ltrace

Purpose: Program library calls ni trace cheyadaniki.

ltrace ./app
vmstat

System performance statistics chudataniki.

iostat

Purpose: CPU and disk I/O performance statistics chudataniki.

iostat
sar

Purpose: Historical/system performance statistics collect/display cheyadaniki.

sar
free

Memory usage chudataniki.

df

Disk filesystem usage chudataniki.

du

Directory/file disk usage chudataniki.

🔌 39. Ports
ss

Purpose: Listening ports and active network connections chudataniki.

ss -tulpn
netstat

Purpose: Network ports/connections chudataniki.

netstat -tulpn
lsof

Specific port ni ye process use chestundo find cheyadaniki.

sudo lsof -i :8099
fuser

Purpose: Specific file/port ni ye process use chestundo find cheyadaniki.

sudo fuser 8099/tcp
🌳 40. Filesystem
mount

Filesystem/device mount cheyadaniki.

umount

Filesystem unmount cheyadaniki.

findmnt

Purpose: Current system lo mounted filesystems chudataniki.

findmnt
lsblk

Disks/block devices list cheyadaniki.

blkid

Partitions/filesystems UUID and type chudataniki.

df

Mounted filesystems disk usage chudataniki.

du

Files/directories disk usage chudataniki.

🔀 41. Links
ln

Purpose: File ki link create cheyadaniki.

Hard link:

ln file.txt link.txt
ln -s

Purpose: Symbolic/soft link create cheyadaniki.

ln -s /var/log/app.log app.log
readlink

Purpose: Symbolic link point ayye actual target chudataniki.

readlink app.log
📄 42. File Metadata
stat

Detailed metadata chudataniki.

file

File type identify cheyadaniki.

basename

Purpose: Full path nunchi filename only extract cheyadaniki.

basename /home/btl/test.txt

Output:

test.txt
dirname

Purpose: Full path nunchi directory path extract cheyadaniki.

dirname /home/btl/test.txt

Output:

/home/btl
realpath

Purpose: File/directory yokka absolute/canonical path chudataniki.

realpath test.txt
readlink

Symbolic link yokka target path chudataniki.

🧮 43. Calculations / Conversion
bc

Purpose: Terminal lo mathematical calculations cheyadaniki.

echo "10 / 2" | bc

Output:

5
expr

Purpose: Basic expressions/calculations/string operations cheyadaniki.

expr 10 + 5

Output:

15
printf

Purpose: Formatted output and basic formatting/calculation support kosam use chestam.

printf "%d\n" 10
seq

Purpose: Number sequence generate cheyadaniki.

seq 1 5

Output:

1
2
3
4
5
🔤 44. String Processing
echo

Text print cheyadaniki.

printf

Formatted text print cheyadaniki.

tr

Characters translate/delete cheyadaniki.

cut

Specific fields/columns extract cheyadaniki.

awk

Columns and text process cheyadaniki.

sed

Text search/replace/modify cheyadaniki.

grep

Text search cheyadaniki.

rev

String reverse cheyadaniki.

echo "hello" | rev
fold

Long text lines ni specified width ki wrap cheyadaniki.

fold -w 20 file.txt
🧵 45. Process Communication
kill

Process ki signal send cheyadaniki.

kill 1234
killall

Process name based on processes kill cheyadaniki.

killall nginx
pkill

Pattern/name based on process signal cheyadaniki.

pkill nginx
wait

Background process complete ayye varaku wait cheyadaniki.

wait
jobs

Current shell background jobs chudataniki.

fg

Background job ni foreground ki teesukovadaniki.

bg

Stopped job ni background lo continue cheyadaniki.

nohup

Terminal close ayina command run lo continue cheyadaniki.

nohup ./app &
🐳 46. Docker
docker ps

Purpose: Currently running Docker containers list cheyadaniki.

docker ps
docker ps -a

Purpose: Running + stopped containers anni chudataniki.

docker ps -a
docker images

Purpose: Local Docker images list cheyadaniki.

docker images
docker pull

Purpose: Docker registry nunchi image download cheyadaniki.

docker pull nginx
docker push

Purpose: Local image ni registry ki upload cheyadaniki.

docker push username/app:latest
docker build

Purpose: Dockerfile use chesi image build cheyadaniki.

docker build -t myapp .
docker run

Purpose: Docker image nunchi container create + run cheyadaniki.

docker run -d -p 8080:80 nginx
docker exec

Purpose: Running container lopala command execute cheyadaniki.

docker exec -it container_name bash
docker logs

Purpose: Container logs chudataniki.

docker logs container_name

Live:

docker logs -f container_name
docker stop

Purpose: Running container stop cheyadaniki.

docker stop container_name
docker start

Purpose: Stopped container start cheyadaniki.

docker start container_name
docker restart

Purpose: Container restart cheyadaniki.

docker restart container_name
docker rm

Purpose: Container remove cheyadaniki.

docker rm container_name
docker rmi

Purpose: Docker image remove cheyadaniki.

docker rmi nginx
docker inspect

Purpose: Container/image yokka detailed configuration information chudataniki.

docker inspect container_name
docker stats

Purpose: Containers CPU/memory/network usage ni live monitor cheyadaniki.

docker stats
docker info

Purpose: Docker installation/system information chudataniki.

docker info
docker version

Purpose: Docker client/server versions chudataniki.

docker version
docker network

Purpose: Docker networks create/list/inspect/manage cheyadaniki.

docker network ls
docker volume

Purpose: Docker volumes manage cheyadaniki.

docker volume ls
docker system

Purpose: Docker unused resources cleanup/manage cheyadaniki.

docker system df
docker compose up

Purpose: docker-compose.yml based on services create/start cheyadaniki.

docker compose up
docker compose up -d

Purpose: Compose services ni detached/background mode lo start cheyadaniki.

docker compose up -d
docker compose down

Purpose: Compose containers/network etc. stop/remove cheyadaniki.

docker compose down
docker compose ps

Purpose: Compose project containers status chudataniki.

docker compose ps
docker compose logs

Purpose: Compose services logs chudataniki.

docker compose logs
docker compose build

Purpose: Compose services images build/rebuild cheyadaniki.

docker compose build
docker compose restart

Purpose: Compose services restart cheyadaniki.

docker compose restart
☸️ 47. Kubernetes
kubectl get

Purpose: Kubernetes resources list/status chudataniki.

kubectl get pods
kubectl describe

Purpose: Resource yokka detailed information/events chudataniki.

kubectl describe pod mypod
kubectl logs

Purpose: Pod/container application logs chudataniki.

kubectl logs mypod
kubectl exec

Purpose: Running container lopala command execute cheyadaniki.

kubectl exec -it mypod -- bash
kubectl apply

Purpose: YAML configuration ni Kubernetes cluster ki create/update cheyadaniki.

kubectl apply -f deployment.yaml
kubectl delete

Purpose: Kubernetes resource delete cheyadaniki.

kubectl delete pod mypod
kubectl edit

Purpose: Existing Kubernetes resource configuration ni directly edit cheyadaniki.

kubectl edit deployment myapp
kubectl scale

Purpose: Deployment/ReplicaSet replicas number change cheyadaniki.

kubectl scale deployment myapp --replicas=3
kubectl rollout

Purpose: Deployment rollout status/history/undo etc. manage cheyadaniki.

kubectl rollout status deployment/myapp
kubectl port-forward

Purpose: Local machine port ni Kubernetes pod/service port ki forward cheyadaniki.

kubectl port-forward pod/mypod 8080:80
kubectl expose

Purpose: Existing resource ni Kubernetes Service ga expose cheyadaniki.

kubectl expose deployment myapp --port=80
kubectl create

Purpose: Kubernetes resources create cheyadaniki.

kubectl create deployment myapp --image=nginx
kubectl config

Purpose: Kubernetes cluster/context/user configuration manage cheyadaniki.

kubectl config get-contexts
Common Kubernetes commands
kubectl get pods

→ Pods list

kubectl get nodes

→ Nodes list

kubectl get services

→ Services list

kubectl get deployments

→ Deployments list

🌿 48. Git
git init

Purpose: Current directory ni Git repository ga initialize cheyadaniki.

git init
git clone

Purpose: Remote repository ni local machine ki copy cheyadaniki.

git clone https://github.com/user/repo.git
git status

Purpose: Working directory and staging area current status chudataniki.

git status
git add

Purpose: Changes ni staging area ki add cheyadaniki.

git add file.txt

All:

git add .
git commit

Purpose: Staged changes ni Git history lo save cheyadaniki.

git commit -m "Added login feature"
git push

Purpose: Local commits ni remote repository ki upload cheyadaniki.

git push
git pull

Purpose: Remote changes ni fetch + integrate cheyadaniki.

git pull
git fetch

Purpose: Remote changes ni download chestundi but current branch lo automatically merge cheyadu.

git fetch
git merge

Purpose: One branch changes ni another branch lo merge cheyadaniki.

git merge feature
git rebase

Purpose: Current branch commits ni another base ki reapply/rewrite cheyadaniki.

git rebase main
git branch

Purpose: Branches list/create/delete cheyadaniki.

git branch

Create:

git branch feature
git switch

Purpose: Branch switch/create cheyadaniki.

git switch feature
git checkout

Purpose: Older Git command; branches switch cheyadaniki and files/commits restore cheyadaniki use chestaru.

git checkout main
git log

Purpose: Commit history chudataniki.

git log
git diff

Purpose: Changes/differences chudataniki.

git diff
git stash

Purpose: Current uncommitted changes ni temporary ga stash cheyadaniki.

git stash
git tag

Purpose: Specific commit ki version/release marker create cheyadaniki.

git tag v1.0
git remote

Purpose: Remote repositories information manage/check cheyadaniki.

git remote -v
git reset

Purpose: HEAD/staging/working tree ni different state ki move cheyadaniki.

git reset

⚠️ --hard carefully use cheyali.

git revert

Purpose: Previous commit changes ni reverse chese new commit create cheyadaniki.

git revert <commit>
git cherry-pick

Purpose: Specific commit ni current branch ki apply cheyadaniki.

git cherry-pick <commit>
🔨 49. Build / Development
make

Purpose: Makefile based on source code build/automation cheyadaniki.

make
gcc

Purpose: C programs compile cheyadaniki.

gcc main.c -o main
g++

Purpose: C++ programs compile cheyadaniki.

g++ main.cpp -o app
python

Purpose: Python interpreter run cheyadaniki.

python script.py
python3

Purpose: Python 3 interpreter run cheyadaniki.

python3 script.py
pip

Purpose: Python packages install/manage cheyadaniki.

pip install requests
npm

Purpose: Node.js packages and scripts manage cheyadaniki.

npm install
node

Purpose: JavaScript/Node.js programs execute cheyadaniki.

node app.js
go

Purpose: Go programs build/run/manage cheyadaniki.

go run main.go
java

Purpose: Java applications run cheyadaniki.

java Main
javac

Purpose: Java source code compile cheyadaniki.

javac Main.java
📊 50. Monitoring
top

Real-time CPU/process monitoring.

htop

Interactive process monitoring.

free

RAM usage monitoring.

df

Disk filesystem usage monitoring.

du

Directory/file size monitoring.

iostat

CPU + disk I/O performance monitoring.

vmstat

CPU/memory/process/system statistics monitoring.

sar

System performance statistics/history monitoring.

uptime

System uptime and load monitoring.

watch

Purpose: Oka command ni repeatedly execute chesi output ni continuously monitor cheyadaniki.

watch df -h

Every few seconds refresh chestundi.

🧰 51. Miscellaneous Useful Commands
clear

Purpose: Terminal screen ni clear cheyadaniki.

clear
reset

Purpose: Terminal display/state problem ayinappudu terminal ni reset cheyadaniki.

reset
history

Previous commands chudataniki.

alias

Command shortcut create cheyadaniki.

alias ll='ls -la'
unalias

Alias remove cheyadaniki.

unalias ll
echo

Text/value print cheyadaniki.

printf

Formatted output print cheyadaniki.

sleep

Execution ni specified time pause cheyadaniki.

sleep 10
true

Purpose: Always successful exit status return chestundi.

true
echo $?

Output:

0
false

Purpose: Always failure/non-zero exit status return chestundi.

false
echo $?

Output:

1

Shell scripting lo testing/error handling kosam useful.

yes

Purpose: Repeated ga y or specified text print chestundi.

yes

Stop:

Ctrl + C

Example:

yes hello

⚠️ Output continuously vastundi, so careful.

seq

Purpose: Number sequence generate cheyadaniki.

seq 1 10

Output:

1
2
3
...
10
watch

Purpose: Command ni repeatedly run chesi live output monitor cheyadaniki.

watch ls
timeout

Purpose: Command ni specified time varaku run chesi time exceed ayite stop cheyadaniki.

timeout 10s ping google.com
which

Purpose: Command executable location chudataniki.

which python
whereis

Purpose: Command binary/source/manual locations search cheyadaniki.

whereis python
type

Purpose: Command alias/builtin/function/executable aa ani identify cheyadaniki.

type cd
command

Purpose: Shell command ni directly execute/check cheyadaniki.

command -v python
⭐ MOST IMPORTANT SHELL SCRIPTING CONCEPTS

Nuvvu Shell Scripting nerchukuntunnav kabatti, ee commands anni okesari memorize cheyyalsina avasaram ledu.

First ee order lo nerchuko:
