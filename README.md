
****🐧 **LINUX + SHELL SCRIPTING COMPLETE NOTES**
**1. Navigation Commands****
1.**pwd**:
     Purpose: Displays the current working directory — where you are currently located. ------> pwd (Remember: pwd → Where am I)                          
Example:
/home/btl/go-web-app


2.**ls**
    Purpose: Lists files and directories in the current directory.---------->ls


3.**ls -l**
       Purpose: Displays files and directories with detailed information.--------->ls -l (Remember: -l → Long/detailed listing)
It shows:
    Permissions
    Owner
    Group
    Size
    Modified date/time
    Filename



4.**ls -la**
     Purpose: Displays detailed information, including hidden files.------------->ls -la

ls -la
    -l → Detailed listing
    -a → All files, including hidden files
Examples of hidden files:
.bashrc
.git
.env

5.**ls -lh**
     Purpose: Displays detailed file information with human-readable file sizes.
ls -lh
Examples:
10K
25M
2G
    -l → Detailed
    -h → Human-readable

6.**ls -lt**
            Purpose: Sorts files by modification time, with the newest files first.
ls -lt
    -l → Detailed
    -t → Sort by modification time



7.**ls -ltr**
        Purpose: Sorts files by modification time in reverse order.
ls -ltr
Usually:
Oldest → Newest
    -l → Detailed
    -t → Time sorting
    -r → Reverse

8.**ls -R**
    Purpose: Recursively lists files and directories inside subdirectories.
ls -R
Remember: -R → Recursive

9.**cd**
Full form: Change Directory
Purpose: Moves from one directory to another.
cd Documents

10.**cd ..**
Purpose: Moves one level up to the parent directory.
cd ..
Example:
/home/btl/project/backend
**After:**
cd ..
You are in:
/home/btl/project
Remember: .. → One level up

11**cd ../..**
Purpose: Moves two levels up.
cd ../..
Example:
/home/btl/project/backend/src

After:
/home/btl/project

12.**cd -**
Purpose: Returns to the previously visited directory.
cd -

Example:
/var/log

Then:
cd /home/btl
cd -
Returns to:
/var/log
Remember: cd - → Previous directory

13.**cd ~**
Purpose: Moves to the current user's home directory.
For user btl:
~ = /home/btl
cd ~

14.**cd /**
Purpose: Moves to the root directory of the Linux filesystem.
cd /

Root directory:
/




**2. Files & Directories**
**touch**
Purpose: Creates an empty file.

touch script.sh
Remember: touch → Create file


**mkdir**
Full form: Make Directory
Purpose: Creates a new directory.
mkdir project

**mkdir -p**
Purpose: Creates parent directories automatically if they do not already exist.
mkdir -p project/backend/src
If project, backend, and src do not exist, all of them are created.
Remember: -p → Create parent directories

**file**
Purpose: Identifies the type of a file.
file script.sh
Example:
Bourne-Again shell script

**stat**
Purpose: Displays detailed file metadata.
stat file.txt
It shows:
    Size
    Permissions
    Owner
    Inode
    Access time
    Modification time
    Change time

**tree**
Purpose: Displays directory structure in tree format.
tree project/

Example:

project
├── backend
│   └── main.py
└── frontend
    └── package.json



    

**3. View File Contents**
**cat**
Purpose: Displays file contents.
cat file.txt

**tac**
Purpose: Displays file contents in reverse line order.
tac file.txt

If cat shows:
line 1
line 2
line 3

tac shows:
line 3
line 2
line 1

Remember: tac = cat in reverse

**less**
Purpose: Views large files page by page.
less app.log
Exit:
q

**more**
Purpose: Views large files page by page.
more app.log
less and more are similar, but less is generally more flexible.

**head**
Purpose: Displays the beginning of a file.
head file.txt
Default: first 10 lines.
head -n 5 file.txt
Displays the first 5 lines.

**tail**
Purpose: Displays the last lines of a file.
tail file.txt
Default: last 10 lines.

**tail -f**
Purpose: Continuously monitors a file as new content is added.
tail -f app.log
Very useful for DevOps log monitoring.

**nl**
Purpose: Displays file contents with line numbers.
nl file.txt

**wc**
Full form: Word Count
Purpose: Counts lines, words, and bytes.
wc file.txt

Important options:
wc -l file.txt
→ Number of lines
wc -w file.txt
→ Number of words
wc -c file.txt

→ Number of bytes

**strings**
Purpose: Extracts readable text strings from binary files.
strings app
Useful when inspecting binary files.








**4. Edit Files**
**vi**
Purpose: Terminal-based text editor.
vi script.sh

Important modes/commands:
i       → Insert mode
Esc     → Command mode
:w      → Save
:q      → Quit
:wq     → Save and quit
:q!     → Quit without saving

**vim**
Purpose: Improved and advanced version of vi.
vim script.sh
Basic commands are similar to vi.

**nano**
Purpose: Simple and beginner-friendly terminal text editor.
nano script.sh

Save:
Ctrl + O
Enter
Exit:
Ctrl + X



**5. Copy / Move / Delete**
**cp**
Full form: Copy
Purpose: Copies files or directories.
cp file.txt backup.txt
Directory:
cp -r project backup/

**mv**
Full form: Move
Purpose: Moves or renames files/directories.

Move
mv file.txt /tmp/

Rename:
mv old.txt new.txt

**rm**
Full form: Remove
Purpose: Deletes files or directories.

rm file.txt
Directory:
rm -r project

Force:
rm -rf project
⚠️ Use rm -rf very carefully.

**rmdir**
Purpose: Deletes an empty directory.

rmdir test
It does not work if the directory contains files.

**6. 🔐 Permissions & Ownership**
**chmod**
Full form: Change Mode
Purpose: Changes file/directory permissions.

chmod +x script.sh

Then:
./script.sh

Common permissions:
chmod 755 script.sh
chmod 644 file.txt

**chown**
Full form: Change Owner
Purpose: Changes file/directory ownership.
sudo chown btl file.txt

Owner + group:
sudo chown btl:developers file.txt

**chgrp**
Full form: Change Group
Purpose: Changes group ownership.
sudo chgrp developers file.txt

**umask**
Purpose: Determines default permissions for newly created files and directories.
umask

Set:
umask 022

**7. 🔎 Searching**
**grep**
Purpose: Searches for specific text or patterns in files or command output.
grep "error" app.log

Case-insensitive:
grep -i "error" app.log

Recursive:
grep -r "database" .

**find**
Purpose: Searches for files/directories based on name, type, size, time, etc.
find . -name "*.sh"

Only files:
find . -type f

Only directories:
find . -type d

**locate**
Purpose: Quickly searches for files using a system database.
locate nginx.conf
The database may not contain very recently created files.


**which**
Purpose: Shows where a command executable is located.
which python

Example:
/usr/bin/python

**whereis**
Purpose: Searches for a command's binary, source, and manual locations.
whereis nginx

find → files ni search cheyyadaniki
whereis → command/software related files ekkada unnayo quickly find cheyyadaniki

**type**
Purpose: Identifies what type of shell command something is.
Important: type is especially useful because it can tell you whether a command is an alias, shell builtin, function, or executable.
type cd
type ls

It can identify:
    Alias
    Built-in
    Function
    Executable
    Command

**command -v**
    Purpose: Checks whether a command exists and shows its location.
command -v python

Example:
command -v nginx

**8. 📝 Text Processing**
**grep**
Searches for text/patterns.
grep "ERROR" app.log

**awk**
Purpose: Extracts and processes columns/fields from text.

ps -ef | awk '{print $1}'

Important:
$0  → Complete line
$1  → First column
$2  → Second column
$3  → Third column
NF  → Number of fields
NR  → Line number

**sed**
     Purpose: Searches, replaces, and modifies text.
sed 's/old/new/g' file.txt

**cut**
    Purpose: Extracts specific fields/columns.
cut -d: -f1 /etc/passwd
    -d: → Delimiter :
    -f1 → First field

**sort**
  Purpose: Sorts lines.
sort names.txt

Reverse:
sort -r names.txt

Numeric:
sort -n numbers.txt

**uniq**
    Purpose: Removes or counts consecutive duplicate lines.
sort names.txt | uniq

Count:
sort names.txt | uniq -c

**tr**
Full form: Translate
Purpose: Replaces, converts, or deletes characters.
echo "hello" | tr 'a-z' 'A-Z'

Output:
HELLO

**paste**
Purpose: Combines lines/files side-by-side as columns.
paste file1.txt file2.txt

**join**
Purpose: Combines two files based on a common field.
join file1 file2
Think of it like a database SQL JOIN.

**split**
Purpose: Splits a large file into smaller files.
split -l 100 file.txt

Each output file contains 100 lines.

**xargs**
Purpose: Converts input into arguments for another command.
cat files.txt | xargs rm

**tee**
Purpose: Displays output on the terminal and simultaneously saves it to a file.
ls | tee files.txt

**column**
Purpose: Formats text into aligned columns/table format.
cat data.txt | column -t

**rev**
Purpose: Reverses characters in each line.
echo "hello" | rev

Output:
olleh

**fold**
Purpose: Wraps long lines to a specified width.
fold -w 20 file.txt





**9. 🔗 Pipes & Redirection**
| Pipe

Purpose: Sends the output of one command as input to another command.

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

Purpose: Writes command output to a file and overwrites existing content.

ls > files.txt

>>

Purpose: Appends output to a file.

echo "hello" >> file.txt

Existing content is preserved.
<

Purpose: Provides file content as command input.

sort < names.txt

2>

Purpose: Redirects standard error (stderr) to a file.

command 2> error.log

2>>

Purpose: Appends standard error to a file.

command 2>> error.log

2>&1

Purpose: Redirects stderr to the same location as stdout.

command > output.log 2>&1

Both normal output and errors go to:

output.log

&>

Purpose: In Bash, redirects both stdout and stderr to the same file.

command &> output.log

10. 📚 Help & Documentation
man

Purpose: Displays the complete manual for a command.

man chmod

Exit:

q

info

Purpose: Displays detailed documentation.

info coreutils

help

Purpose: Shows help for Bash built-in commands.

help cd

whatis

Purpose: Shows a short description of a command.

whatis chmod

apropos

Purpose: Searches manual pages using a keyword.

apropos network

11. 🕘 Command History
history

Purpose: Displays previously executed commands.

history

Last 10 commands:

history 10

!!

Purpose: Executes the previous command again.

ls
!!

The !! executes ls again.
!100

Purpose: Executes command number 100 from history.

!100

Search history

history | grep docker

12. 🖥️ System Information
uname

Purpose: Displays operating system/kernel information.

uname -a

hostname

Purpose: Displays the machine/server hostname.

hostname

hostnamectl

Purpose: Displays or changes hostname and system information.

hostnamectl

arch

Purpose: Displays system architecture.

arch

Example:

x86_64

date

Purpose: Displays current date and time.

date

timedatectl

Purpose: Displays system date, time, timezone, and NTP synchronization information.

timedatectl

uptime

Purpose: Shows how long the system has been running and the system load.

uptime

whoami

Purpose: Displays the currently logged-in username.

whoami

id

Purpose: Displays the current user's UID, GID, and groups.

id

who

Purpose: Shows currently logged-in users.

who

w

Purpose: Shows logged-in users and what they are doing.

w

users

Purpose: Shows usernames of currently logged-in users.

users

last

Purpose: Shows previous login history.

last

lastlog

Purpose: Shows the last login information for users.

lastlog

13. 🧠 CPU
nproc

Purpose: Shows the number of available CPU processing units.

nproc

Example:

8

Means 8 processing units are available.
lscpu

Purpose: Displays detailed CPU hardware information.

lscpu

top

Purpose: Real-time monitoring of system health and running processes.

top

Shows:

    CPU usage

    Memory

    Processes

    Load average

htop

Purpose: Interactive and user-friendly process/system monitor.

htop

vmstat

Purpose: Displays CPU, memory, process, and I/O performance statistics.

vmstat

mpstat

Purpose: Monitors CPU usage per processor/core.

mpstat

14. 🧮 Memory
free

Purpose: Displays RAM and swap memory usage.

free

free -h

Purpose: Displays memory information in human-readable format.

free -h

vmstat

Monitors memory along with CPU and system performance.

vmstat

top

Monitors memory and CPU usage of running processes.

top

htop

Interactive CPU, memory, and process monitoring.

htop

15. 💽 Disk / Storage
df

Purpose: Displays filesystem disk-space usage.

df -h

Remember: df → Filesystem disk usage
du

Purpose: Shows how much disk space a file/directory uses.

du -sh folder

Remember: du → Directory/file usage
lsblk

Purpose: Lists disks and block devices.

lsblk

blkid

Purpose: Displays UUID and filesystem information for block devices.

sudo blkid

mount

Purpose: Attaches a filesystem/device to a directory.

sudo mount /dev/sdb1 /mnt

umount

Purpose: Unmounts a filesystem.

sudo umount /mnt

fdisk

Purpose: Views/manages disk partitions.

sudo fdisk -l

⚠️ Be careful when modifying partitions.
parted

Purpose: Creates/manages disk partitions.

sudo parted -l

16. ⚙️ Processes
ps

Purpose: Displays currently running processes.

ps

ps -ef

Purpose: Displays all processes in detailed format.

ps -ef

ps aux

Purpose: Displays detailed process information for all users.

ps aux

pgrep

Purpose: Finds process IDs based on process name.

pgrep nginx

pidof

Purpose: Finds the PID of a running program.

pidof nginx

pstree

Purpose: Displays processes in a parent-child tree structure.

pstree

kill

Purpose: Sends a signal to a process using its PID.

kill 1234

Force:

kill -9 1234

killall

Purpose: Kills matching processes by name.

killall nginx

pkill

Purpose: Sends signals to processes based on name/pattern.

pkill nginx

nice

Purpose: Starts a process with a specific CPU scheduling priority.

nice -n 10 ./script.sh

renice

Purpose: Changes the priority of an already-running process.

renice 10 -p 1234

17. 🔄 Jobs / Background Processes
jobs

Purpose: Displays background/stopped jobs in the current shell.

jobs

fg

Full form: Foreground

Purpose: Brings a background job to the foreground.

fg %1

bg

Full form: Background

Purpose: Continues a stopped job in the background.

bg %1

nohup

Purpose: Keeps a command running after terminal logout/closure.

nohup ./app.sh &

wait

Purpose: Waits for background processes to complete.

wait

disown

Purpose: Removes a job from the current shell's job table so it can continue after logout.

disown %1

18. ⚡ Environment Variables
env

Purpose: Displays environment variables.

env

printenv

Purpose: Displays environment variable values.

printenv HOME

export

Purpose: Makes a variable available as an environment variable to child processes.

export APP_ENV=production

unset

Purpose: Removes a variable.

unset APP_ENV

set

Purpose: Displays shell variables and shell settings.

set

19. 🐚 Bash Built-ins
echo

Prints text/value to the terminal.

echo "Hello"

read

Takes input from the user.

read name

printf

Prints formatted output.

printf "Hello %s\n" "Devi"

source

Loads and executes another shell file in the current shell.

source config.sh

alias

Creates a shortcut for a command.

alias ll='ls -la'

unalias

Removes an alias.

unalias ll

shift

Shifts script arguments one position to the left.

shift

Useful when processing $1, $2, $3, etc.
eval

Evaluates a string as a shell command.

eval "echo hello"

⚠️ Avoid using eval with untrusted user input.
exec

Replaces the current shell/process with another command.

exec ./app

exit

Exits a shell/script.

exit 0

return

Returns from a function.

return 0

break

Stops a loop completely.

break

continue

Skips the current loop iteration.

continue

20. 🧩 Bash Variables
$0

Purpose: Name/path of the running script.

echo "$0"

$1

Purpose: First argument passed to the script.

./script.sh hello

Inside the script:

echo "$1"

Output:

hello

$2

Second argument.

./script.sh hello world
echo "$2"

Output:

world

$3

Third argument.
$#

Purpose: Number of arguments passed to the script.

echo "$#"

$@

Purpose: All arguments passed to the script.

echo "$@"

$?

Purpose: Exit status of the previous command.

ls
echo $?

Usually:

0 → Success
Non-zero → Failure

$$

Purpose: PID of the current shell/script.

echo "$$"

$!

Purpose: PID of the most recently started background process.

./app &
echo "$!"

$USER

Current username.

echo "$USER"

$HOME

Current user's home directory.

echo "$HOME"

Example:

/home/btl

$PWD

Current working directory.

echo "$PWD"

$PATH

Directories searched by the shell when executing commands.

echo "$PATH"

21. 🔀 Conditions
if

Executes code based on a condition.

if [ "$age" -ge 18 ]; then
    echo "Adult"
fi

then

Starts the block that executes when the condition is true.
else

Executes when the if condition is false.

if [ "$x" -eq 10 ]; then
    echo "Ten"
else
    echo "Not Ten"
fi

elif

Checks additional conditions.

if [ "$x" -gt 10 ]; then
    echo "Greater"
elif [ "$x" -eq 10 ]; then
    echo "Equal"
else
    echo "Less"
fi

fi

Closes an if statement.
case

Handles multiple possible values/options.

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

Closes a case statement.
test

Checks whether a condition is true or false.

test -f file.txt
echo $?

[ ]

Traditional Bash conditional syntax.

[ "$x" -eq 10 ]

[[ ]]

Advanced Bash conditional syntax.

[[ "$name" == "Devi" ]]

Comparison Operators
Operator	Meaning
-eq	Equal
-ne	Not equal
-gt	Greater than
-ge	Greater than or equal
-lt	Less than
-le	Less than or equal
==	String equality
=	String equality in [ ]
!=	Not equal

Examples:

[ "$a" -eq "$b" ]
[ "$a" -ne "$b" ]
[ "$a" -gt "$b" ]
[ "$a" -ge "$b" ]
[ "$a" -lt "$b" ]
[ "$a" -le "$b" ]

String comparison:

[[ "$name" == "Devi" ]]

&&

AND — both conditions must succeed.

[ "$age" -ge 18 ] && echo "Adult"

||

OR — either condition can succeed.

[ "$x" -eq 10 ] || echo "Not 10"

!

Negates a condition.

if ! command -v nginx >/dev/null; then
    echo "nginx not installed"
fi

File Tests

-f → Regular file exists
-d → Directory exists
-e → File or directory exists
-r → Readable
-w → Writable
-x → Executable
-s → File size greater than zero

Examples:

[ -f file.txt ]
[ -d project ]
[ -e file.txt ]
[ -r file.txt ]
[ -w file.txt ]
[ -x script.sh ]
[ -s file.txt ]

22. 🔁 Loops
for

Repeats commands for a list/range of values.

for i in 1 2 3
do
    echo "$i"
done

while

Runs while a condition is true.

while [ "$count" -lt 5 ]
do
    echo "$count"
    count=$((count + 1))
done

until

Runs until a condition becomes true.

until [ "$count" -ge 5 ]
do
    echo "$count"
    count=$((count + 1))
done

do

Starts the loop body.
done

Ends the loop body.
break

Stops the loop completely.
continue

Skips the current iteration and continues with the next iteration.
23. 🛠️ Functions
function

Creates a reusable block of commands.

function greet {
    echo "Hello"
}

Modern Bash syntax:

greet() {
    echo "Hello"
}

return

Exits a function and optionally returns a status code.

greet() {
    return 0
}

24. 🚨 Script Error Handling
set -e

Stops the script when a command fails.

set -e

set -u

Treats unset variables as errors.

set -u

set -x

Displays commands while the script is executing.

Useful for debugging.

set -x

Disable options

set +e
set +u
set +x

set -o

View or configure shell options.

set -o

set -o pipefail

Detects failures inside pipelines.

set -o pipefail

set -euo pipefail

Common robust shell scripting combination:

set -euo pipefail

Meaning:

-e → Exit when a command fails
-u → Error on unset variables
pipefail → Detect pipeline failures

exit

Stops the script and returns an exit status.

exit 0

25. ⏰ Date / Time
date

date

Displays the current date and time.
timedatectl

timedatectl

Displays system time, timezone, and NTP synchronization.
cal

Displays a calendar.

cal

sleep

Pauses script execution.

sleep 5

Waits 5 seconds.
time

Measures how long a command takes.

time ls

26. 🌐 Networking
ip

Checks/manages network interfaces, IP addresses, and routes.

ip addr

or:

ip a

ping

Tests network connectivity/reachability.

ping google.com

ss

Displays listening ports and network connections.

ss -tulpn

netstat

Displays network connections and ports.

netstat -tulpn

Modern Linux systems generally prefer ss.
traceroute

Shows the network path/hops to a destination.

traceroute google.com

tracepath

Shows network path and MTU information.

tracepath google.com

arp

Displays IP-to-MAC information.

arp -a

Modern systems commonly use:

ip neigh

route

Displays/manages the routing table.

route -n

Modern systems:

ip route

hostname

Displays the system hostname.

hostname

27. 🌍 DNS
dig

Detailed DNS query tool.

dig google.com

nslookup

Queries DNS information.

nslookup google.com

host

Simple DNS lookup.

host google.com

resolvectl

Displays system DNS resolver information.

resolvectl status

28. 🌐 HTTP / Web
curl

Purpose: Communicates with URLs/servers and transfers data.

curl https://example.com

API testing:

curl http://localhost:8000/api/users

Headers:

curl -I https://example.com

wget

Purpose: Mainly downloads files/resources.

wget https://example.com/file.zip

29. 🔑 SSH / Remote Access
ssh

Connects securely to a remote server.

ssh user@192.168.1.10

scp

Full form: Secure Copy

Copies files between local and remote systems.

scp file.txt user@server:/tmp/

sftp

Full form: SSH File Transfer Protocol

Secure file transfer over SSH.

sftp user@server

ssh-keygen

Generates an SSH key pair.

ssh-keygen

Creates:

Private key
Public key

ssh-copy-id

Copies your public SSH key to a remote server.

ssh-copy-id user@server

After this, passwordless SSH login can be configured.
30. 📦 Compression / Archives
tar

Creates/extracts archives.

Create:

tar -czf backup.tar.gz project/

Extract:

tar -xzf backup.tar.gz

gzip

Compresses files.

gzip file.txt

gunzip

Decompresses .gz files.

gunzip file.txt.gz

zip

Creates ZIP archives.

zip backup.zip file.txt

unzip

Extracts ZIP archives.

unzip backup.zip

bzip2

Compresses using bzip2.

bzip2 file.txt

bunzip2

Decompresses .bz2 files.

bunzip2 file.txt.bz2

xz

Compresses using xz.

xz file.txt

unxz

Decompresses .xz files.

unxz file.txt.xz

31. 👤 Users
useradd

Creates a new user.

sudo useradd devuser

adduser

Interactive/user-friendly user creation.

sudo adduser devuser

usermod

Modifies existing user properties.

sudo usermod -aG docker btl

userdel

Deletes a user.

sudo userdel devuser

passwd

Sets/changes a user password.

passwd

chage

Manages password expiry/aging.

sudo chage -l btl

32. 👥 Groups
groupadd

Creates a new group.

sudo groupadd developers

groupmod

Modifies an existing group.

sudo groupmod developers

groupdel

Deletes a group.

sudo groupdel developers

gpasswd

Manages group membership/admin settings.

sudo gpasswd -a btl developers

groups

Shows groups a user belongs to.

groups

33. 🔐 Security / Authentication
sudo

Runs a command with elevated privileges.

sudo systemctl restart nginx

su

Full form: Switch User

Switches to another user.

su - user

visudo

Safely edits the sudoers configuration.

sudo visudo

visudo is safer than directly editing /etc/sudoers.
passwd

Manages user passwords.
last

Displays successful login history.

last

lastb

Displays failed login attempts.

sudo lastb

who

Displays currently logged-in users.
w

Displays logged-in users and their activity.
34. 📦 Ubuntu Package Management
apt

Installs, updates, and removes packages.

sudo apt install nginx

apt-get

Traditional package management tool.

sudo apt-get install nginx

apt-cache

Displays/searches package information.

apt-cache policy nginx

dpkg

Manages Debian .deb packages.

dpkg -l

Update package lists

sudo apt update

Downloads the latest package index information.
Upgrade packages

sudo apt upgrade

Install

sudo apt install nginx

Remove

sudo apt remove nginx

Configuration files may remain.
Purge

sudo apt purge nginx

Removes the package and related configuration files.
Search

apt search nginx

List installed packages

dpkg -l

Install local .deb

sudo dpkg -i package.deb

35. 🔧 Services / systemd
systemctl

Manages Linux services.

systemctl status nginx

Start

sudo systemctl start nginx

Stop

sudo systemctl stop nginx

Restart

sudo systemctl restart nginx

Reload

Reloads configuration without completely stopping the service.

sudo systemctl reload nginx

Enable

Starts automatically at boot.

sudo systemctl enable nginx

Disable

Disables automatic startup.

sudo systemctl disable nginx

36. ⏰ Scheduling
crontab

Configures recurring scheduled tasks.

crontab -e

cron

Background service that executes scheduled jobs.
at

Schedules a command to run once at a future time.

at 15:00

atq

Lists scheduled at jobs.

atq

atrm

Removes a scheduled at job.

atrm 3

crontab -l

Lists existing cron jobs.

crontab -l

37. 📋 Logs
journalctl

Displays systemd/service logs.

journalctl

Specific service:

journalctl -u nginx

Live logs:

journalctl -u nginx -f

dmesg

Displays Linux kernel messages.

dmesg

logger

Sends a custom message to the system log/journal.

logger "Backup completed"

tail

Views the last lines of a log file.

tail /var/log/syslog

grep

Searches for specific text in logs.

grep "error" app.log

less

Views large log files page by page.

less app.log

tail -f

Monitors logs live.

tail -f /var/log/nginx/error.log

38. 🧪 System Diagnostics
dmesg

Displays kernel/hardware messages.
lsof

Full form: List Open Files

Finds which process is using a file, port, or device.

sudo lsof -i :8080

strace

Traces system calls made by a program.

strace ./app

ltrace

Traces library calls made by a program.

ltrace ./app

vmstat

Displays system performance statistics.

vmstat

iostat

Displays CPU and disk I/O statistics.

iostat

sar

Collects/displays historical system performance statistics.

sar

free

Displays memory usage.
df

Displays filesystem disk usage.
du

Displays file/directory disk usage.
39. 🔌 Ports
ss

Displays listening ports and active connections.

ss -tulpn

netstat

Displays network ports/connections.

netstat -tulpn

lsof

Finds which process is using a specific port.

sudo lsof -i :8099

fuser

Finds which process is using a port/file.

sudo fuser 8099/tcp

40. 🌳 Filesystem
mount

Mounts a filesystem/device.
umount

Unmounts a filesystem.
findmnt

Displays mounted filesystems.

findmnt

lsblk

Lists disks/block devices.

lsblk

blkid

Displays filesystem UUID and type.

blkid

df

Displays mounted filesystem disk usage.

df -h

du

Displays file/directory disk usage.

du -sh folder

41. 🔀 Links
ln

Creates a hard link.

ln file.txt link.txt

ln -s

Creates a symbolic/soft link.

ln -s /var/log/app.log app.log

readlink

Displays the target of a symbolic link.

readlink app.log

42. 📄 File Metadata
stat

Displays detailed metadata.

stat file.txt

file

Identifies file type.

file script.sh

basename

Extracts the filename from a full path.

basename /home/btl/test.txt

Output:

test.txt

dirname

Extracts the directory path.

dirname /home/btl/test.txt

Output:

/home/btl

realpath

Displays the absolute/canonical path.

realpath test.txt

readlink

Displays the target of a symbolic link.
43. 🧮 Calculations / Conversion
bc

Performs mathematical calculations.

echo "10 / 2" | bc

Output:

5

expr

Performs basic calculations/string operations.

expr 10 + 5

Output:

15

printf

Provides formatted output.

printf "%d\n" 10

seq

Generates number sequences.

seq 1 5

Output:

1
2
3
4
5

44. 🔤 String Processing
echo

Prints text.
printf

Prints formatted text.
tr

Translates/deletes characters.

echo "hello" | tr 'a-z' 'A-Z'

cut

Extracts specific fields.
awk

Processes columns/text.
sed

Searches/replaces/modifies text.
grep

Searches text.
rev

Reverses strings.

echo "hello" | rev

fold

Wraps long lines.

fold -w 20 file.txt

45. 🧵 Process Communication
kill

Sends a signal to a process.

kill 1234

killall

Kills processes by name.

killall nginx

pkill

Sends signals based on process name/pattern.

pkill nginx

wait

Waits for a background process to complete.

wait

jobs

Displays current shell background jobs.

jobs

fg

Brings a background job to the foreground.

fg %1

bg

Continues a stopped job in the background.

bg %1

nohup

Keeps a process running after logout.

nohup ./app &

**46. 🐳 Docker**
**docker ps**
    Lists running containers.---->docker ps


**docker ps -a**
    Lists running and stopped containers.----------->docker ps -a

**docker images**
    Lists local Docker images.----->docker images

**docker pull**
    Downloads an image from a registry.---->docker pull nginx

**docker push**
     Uploads an image to a registry.------->docker push username/app:latest

**docker build**
    Builds an image using a Dockerfile----------------->docker build -t myapp .

Creates and runs a container.

docker run -d -p 8080:80 nginx

docker exec

Executes a command inside a running container.

docker exec -it container_name bash

docker logs

Displays container logs.

docker logs container_name

Live logs:

docker logs -f container_name

docker stop

Stops a running container.

docker stop container_name

docker start

Starts a stopped container.

docker start container_name

docker restart

Restarts a container.

docker restart container_name

docker rm

Removes a container.

docker rm container_name

docker rmi

Removes a Docker image.

docker rmi nginx

docker inspect

Displays detailed container/image configuration.

docker inspect container_name

docker stats

Displays live container CPU/memory/network usage.

docker stats

docker info

Displays Docker system information.

docker info

docker version

Displays Docker client/server versions.

docker version

docker network

Manages Docker networks.

docker network ls

docker volume

Manages Docker volumes.

docker volume ls

docker system

Manages/cleans unused Docker resources.

docker system df

Docker Compose

Start services:

docker compose up

Detached mode:

docker compose up -d

Stop/remove:

docker compose down

Check status:

docker compose ps

View logs:

docker compose logs

Build:

docker compose build

Restart:

docker compose restart

47. ☸️ Kubernetes
kubectl get

Lists Kubernetes resources.

kubectl get pods

kubectl describe

Displays detailed resource information and events.

kubectl describe pod mypod

kubectl logs

Displays pod/container logs.

kubectl logs mypod

kubectl exec

Executes a command inside a running container.

kubectl exec -it mypod -- bash

kubectl apply

Creates/updates resources using YAML.

kubectl apply -f deployment.yaml

kubectl delete

Deletes a Kubernetes resource.

kubectl delete pod mypod

kubectl edit

Directly edits an existing resource.

kubectl edit deployment myapp

kubectl scale

Changes the number of replicas.

kubectl scale deployment myapp --replicas=3

kubectl rollout

Manages deployment rollout status/history/rollback.

kubectl rollout status deployment/myapp

kubectl port-forward

Forwards a local port to a Kubernetes pod/service.

kubectl port-forward pod/mypod 8080:80

kubectl expose

Exposes an existing resource as a Kubernetes Service.

kubectl expose deployment myapp --port=80

kubectl create

Creates Kubernetes resources.

kubectl create deployment myapp --image=nginx

kubectl config

Manages Kubernetes contexts and configuration.

kubectl config get-contexts

Common commands:

kubectl get pods
kubectl get nodes
kubectl get services
kubectl get deployments

**48. 🌿 Git**
**git init**
Initializes the current directory as a Git repository.

**git clone**
Copies a remote repository to the local machine.

"git clone https://github.com/user/repo.git"

**git status**
Displays the current working tree and staging area status.
git status

**git add**
Adds changes to the staging area.
git add file.txt

All files:
git add .

**git commit**
Saves staged changes to Git history.
git commit -m "Added login feature"

**git push**
Uploads local commits to a remote repository.
git push

**git pull**
Fetches and integrates changes from a remote repository.
git pull

**git fetch**
Downloads remote changes without automatically merging them.
git fetch

**git merge**
Combines one branch into another.
git merge feature

**git rebase**
Reapplies commits on top of another base.
git rebase main

**git branch**
Lists, creates, or deletes branches.
git branch
Create:
git branch feature

**git switch**
Switches or creates branches.
git switch feature

**git checkout**
Older Git command used for switching branches and restoring files/commits.
git checkout main

**git log**
Displays commit history.
git log

**git diff**
Displays differences between changes.
git diff

**git stash**
Temporarily stores uncommitted changes.
git stash

**git tag**
Creates a version/release marker.
git tag v1.0

**git remote**
Manages/checks remote repositories.
git remote -v

**git reset**
Moves HEAD and/or staging/working tree to another state.
git reset
⚠️ Use --hard carefully because it can remove uncommitted changes.

**git revert**
Creates a new commit that reverses an earlier commit.
git revert <commit>

**git cherry-pick**
Applies a specific commit to the current branch.
git cherry-pick <commit>

49.** 🔨 Build / Development**
make

Builds/automates projects using a Makefile.

make

gcc

Compiles C programs.

gcc main.c -o main

g++

Compiles C++ programs.

g++ main.cpp -o app

python

Runs Python programs.

python script.py

python3

Runs Python 3 programs.

python3 script.py

pip

Installs/manages Python packages.

pip install requests

npm

Manages Node.js packages and scripts.

npm install

node

Runs Node.js applications.

node app.js

go

Builds/runs/manages Go programs.

go run main.go

java

Runs Java applications.

java Main

javac

Compiles Java source code.

javac Main.java

50. 📊 Monitoring
top

Real-time CPU/process monitoring.

top

htop

Interactive process monitoring.

htop

free

RAM usage monitoring.

free -h

df

Filesystem disk usage.

df -h

du

Directory/file size monitoring.

du -sh folder

iostat

CPU and disk I/O monitoring.

iostat

vmstat

CPU/memory/process/system statistics.

vmstat

sar

System performance statistics/history.

sar

uptime

System uptime and load.

uptime

watch

Repeatedly executes a command and refreshes its output.

watch df -h

**51. 🧰 Miscellaneous Useful Commands**

***clear**
Clears the terminal screen.----->clear


**reset**
Resets the terminal when its display/state becomes corrupted.---->reset



**history**
Displays previous commands.------>history



**alias**
Creates command shortcuts.------>alias ll='ls -la'



**unalias**
Removes an alias.--->unalias ll



**echo**
Prints text/values.---->echo "Hello"



**printf**
Prints formatted output.----->printf "Hello %s\n" "Devi"

**sleep**
Pauses execution.----->sleep 10



**true**
Always returns a successful exit status.

true
echo $?
Output:
0

**false**
Always returns a failure/non-zero exit status.

false
echo $?
Output:
1

Useful for shell scripting tests and error handling.
yes

Continuously prints y or specified text.

yes

Stop:

Ctrl + C

Example:

yes hello

⚠️ It continuously generates output, so use it carefully.
seq

Generates number sequences.

seq 1 10

watch

Repeatedly runs a command and displays live output.

watch ls

timeout

Runs a command for a specified amount of time and stops it when the time expires.

timeout 10s ping google.com

which

Shows the executable location.

which python

whereis

Searches for binary/source/manual locations.

whereis python

**type**
Identifies whether a command is an alias, builtin, function, or executable.

type cd

command

Checks or executes commands directly.
