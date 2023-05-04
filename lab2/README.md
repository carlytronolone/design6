# Lab 2 - Command Line
## Files will be stored here for Lab 2
# Procedure
### Commands provided:
```
$ hostname
$ env
$ ps
$ pwd
$ git clone https://github.com/kevinwlu/iot.git
$ cd iot
$ ls
$ cd
$ df
$ mkdir demo
$ cd demo
$ nano file
$ cat file
$ cp file file1
$ mv file file2
$ rm file2
$ clear
$ man uname
$ uname -a
$ ifconfig
$ ping localhost
$ netstat
```
# Results
```
$ hostname
MSI
```
#### This command displays the host name of the computer.

```
$ env
ProgramFiles(x86)=C:\Program Files (x86)
!::=::\
CommonProgramFiles(x86)=C:\Program Files (x86)\Common Files
SHELL=/usr/bin/bash
EFC_13432=1
NUMBER_OF_PROCESSORS=12
FPS_BROWSER_USER_PROFILE_STRING=Default
PROCESSOR_LEVEL=6
TERM_PROGRAM_VERSION=3.6.3
MINGW_PREFIX=/mingw32
ERLANG_HOME=C:\Program Files\erl9.2
PKG_CONFIG_PATH=/mingw32/lib/pkgconfig:/mingw32/share/pkgconfig
SW_SIM_MPIT=INTELMPI
USERDOMAIN_ROAMINGPROFILE=MSI
HOSTNAME=MSI
PROGRAMFILES=C:\Program Files (x86)
MSYSTEM=MINGW32
ChocolateyInstall=C:\ProgramData\chocolatey
PATHEXT=.COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.MSC;.PY;.PYW
NIEXTCCOMPILERSUPP=C:\Program Files (x86)\National Instruments\Shared\ExternalCompilerSupport\C\
ORIGINAL_TEMP=/tmp
configsetroot=C:\WINDOWS\ConfigSetRoot
MINGW_CHOST=i686-w64-mingw32
OS=Windows_NT
HOMEDRIVE=C:
VXIPNPPATH=C:\Program Files (x86)\IVI Foundation\VISA\
RABBITMQ_NODENAME=rabbit@localhost
MSYSTEM_CARCH=i686
USERDOMAIN=MSI
PWD=/c/Users/carly
USERPROFILE=C:\Users\carly
OneDriveConsumer=C:\Users\carly\OneDrive
MANPATH=/mingw32/local/man:/mingw32/share/man:/usr/local/man:/usr/share/man:/usr/man:/share/man
PROCESSOR_ARCHITEW6432=AMD64
MINGW_PACKAGE_PREFIX=mingw-w64-i686
ALLUSERSPROFILE=C:\ProgramData
ORIGINAL_PATH=/mingw32/bin:/usr/bin:/c/Users/carly/bin:/c/Python311/Scripts:/c/Python311:/c/Users/carly/OneDrive/Desktop/Ghdl/Bin:/c/Program Files/nodejs:/c/ProgramData/chocolatey/bin:/cmd:/c/eda/ghdl:/c/eda/gtkwave:/c/Users/carly/AppData/Local/Microsoft/WindowsApps:C: /msys64/mingw64/bin:C: /msys64/usr/bin:/c/Users/carly/AppData/Local/Programs/Microsoft VS Code/bin:/c/Users/carly/AppData/Roaming/npm:/c/eda/ghdl:/c/eda/gtkwave:/c/eda/ghdl/lib/ghdl
CommonProgramW6432=C:\Program Files\Common Files
HOME=/c/Users/carly
USERNAME=carly
SSH_ASKPASS=/mingw32/bin/git-askpass.exe
NIDAQmxSwitchDir=C:\Program Files (x86)\National Instruments\NI-DAQ\Switch\
PLINK_PROTOCOL=ssh
OneDrive=C:\Users\carly\OneDrive
COMSPEC=C:\WINDOWS\system32\cmd.exe
TMPDIR=/tmp
APPDATA=C:\Users\carly\AppData\Roaming
SYSTEMROOT=C:\WINDOWS
LOCALAPPDATA=C:\Users\carly\AppData\Local
COMPUTERNAME=MSI
INFOPATH=/usr/local/info:/usr/share/info:/usr/info:/share/info
RABBITMQ_BASE=C:\ProgramData\RabbitMQ
TERM=xterm
LOGONSERVER=\\MSI
ACLOCAL_PATH=/mingw32/share/aclocal:/usr/share/aclocal
PSModulePath=C:\Program Files\WindowsPowerShell\Modules;C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules;C:\Program Files (x86)\Microsoft SQL Server\120\Tools\PowerShell\Modules\
SW_SIM_HYDRA=C:\Program Files\Common Files\SolidWorks Shared\Simulation Worker Agent\
TEMP=/tmp
MSYSTEM_CHOST=i686-w64-mingw32
DISPLAY=needs-to-be-defined
ORIGINAL_TMP=/tmp
SHLVL=1
PROCESSOR_REVISION=a502
DriverData=C:\Windows\System32\Drivers\DriverData
COMMONPROGRAMFILES=C:\Program Files (x86)\Common Files
LC_CTYPE=en_US.UTF-8
SW_SIM_TEMP=C:\ProgramData\SOLIDWORKS\SW_net_sim_temp\
VXIPNPPATH64=C:\Program Files\IVI Foundation\VISA\
EXEPATH=C:\Program Files (x86)\Git
PROCESSOR_IDENTIFIER=Intel64 Family 6 Model 165 Stepping 2, GenuineIntel
SESSIONNAME=Console
PS1=\[\033]0;$TITLEPREFIX:$PWD\007\]\n\[\033[32m\]\u@\h \[\033[35m\]$MSYSTEM \[\033[33m\]\w\[\033[36m\]`__git_ps1`\[\033[0m\]\n$
HOMEPATH=\Users\carly
TMP=/tmp
CONFIG_SITE=/etc/config.site
PATH=/c/Users/carly/bin:/mingw32/bin:/usr/local/bin:/usr/bin:/bin:/mingw32/bin:/usr/bin:/c/Users/carly/bin:/c/Python311/Scripts:/c/Python311:/c/Users/carly/OneDrive/Desktop/Ghdl/Bin:/c/Program Files/nodejs:/c/ProgramData/chocolatey/bin:/cmd:/c/eda/ghdl:/c/eda/gtkwave:/c/Users/carly/AppData/Local/Microsoft/WindowsApps:C: /msys64/mingw64/bin:C: /msys64/usr/bin:/c/Users/carly/AppData/Local/Programs/Microsoft VS Code/bin:/c/Users/carly/AppData/Roaming/npm:/c/eda/ghdl:/c/eda/gtkwave:/c/eda/ghdl/lib/ghdl:/usr/bin/vendor_perl:/usr/bin/core_perl
ProgramW6432=C:\Program Files
MSYSTEM_PREFIX=/mingw32
RABBITMQ_CONFIG_FILE="C:\ProgramData\National Instruments\Skyline\RabbitMQ\rabbitmq"
WINDIR=C:\WINDOWS
FPS_BROWSER_APP_PROFILE_STRING=Internet Explorer
PROCESSOR_ARCHITECTURE=x86
PUBLIC=C:\Users\Public
SYSTEMDRIVE=C:
CARBON_MEM_DISABLE=1
TERM_PROGRAM=mintty
ProgramData=C:\ProgramData
ChocolateyLastPathUpdate=133225890929439932
_=/usr/bin/env
```
#### This command lists all of the environment variables. 

```
$ ps
      PID    PPID    PGID     WINPID   TTY         UID    STIME COMMAND
     1230    1229    1230      14168  pty0      197609 15:06:12 /usr/bin/bash
     1229       1    1229      11344  ?         197609 15:06:11 /usr/bin/mintty
     1264    1230    1264      15196  pty0      197609 15:10:48 /usr/bin/ps
 ```
#### This command shoed the status of the active processes on the computer

```
carly@MSI MINGW32 ~
$ pwd
/c/Users/carly
```
#### This command shows path to the current directory from the root directory.

```
$ git clone https://github.com/kevinwlu/iot.git
Cloning into 'iot'...
remote: Enumerating objects: 19225, done.
remote: Counting objects: 100% (274/274), done.
remote: Compressing objects: 100% (139/139), done.
remote: Total 19225 (delta 135), reused 186 (delta 93), pack-reused 18951
Receiving objects: 100% (19225/19225), 27.71 MiB | 8.12 MiB/s, done.
Resolving deltas: 100% (12834/12834), done.
```
#### This command clones the repository to my computer.

```
carly@MSI MINGW32 ~
$ cd iot

carly@MSI MINGW32 ~/iot (master)
$ ls
README.md  cases/      health/  lesson1/   lesson2/  lesson4/  lesson6/  lesson8/  make/      special_problems/  systems/
apps/      economics/  hype/    lesson10/  lesson3/  lesson5/  lesson7/  lesson9/  projects/  standards/         tools/

carly@MSI MINGW32 ~/iot (master)
$ cd
```
#### The 'cd' command means 'change directory' and changes the directory to the next place that is specified. The 'ls' commant lists the files of the current directory.

```
$ df
Filesystem                 1K-blocks      Used Available Use% Mounted on
C:/Program Files (x86)/Git 248697852 213435232  35262620  86% /
D:                         954816508    183452 954633056   1% /d
```
#### This command shows the amount of free diskspace on the computer.

```
carly@MSI MINGW32 ~
$ mkdir demo

carly@MSI MINGW32 ~
$ cd demo

carly@MSI MINGW32 ~/demo
$ nano file
```
![Screenshot 2023-05-04 152406](https://user-images.githubusercontent.com/117042826/236308748-1f6ea4c9-bfd6-4f9b-99ee-811bed5542b2.png)
#### The command 'mkdir' makes a new folder in the current directory. In tis case, a new folder named 'demo' was created. The command 'nano file' opens up a file names 'file' in Nano, a ternimal-based text editor.

```
$ cat file
hello
i love my roommate's two cats, Lucy & Luca <3
```
#### This command reades the file 'file' and outputs it in the terminal.

```
carly@MSI MINGW32 ~/demo
$ cp file file1

carly@MSI MINGW32 ~/demo
$ mv file file1

carly@MSI MINGW32 ~/demo
$ rm file2
rm: cannot remove 'file2': No such file or directory

carly@MSI MINGW32 ~/demo
$ mv file file2
mv: cannot stat 'file': No such file or directory

carly@MSI MINGW32 ~/demo
$ cp file1 file

carly@MSI MINGW32 ~/demo
$ mv file file2

carly@MSI MINGW32 ~/demo
$ rm file2
```
#### The command 'cp' copies file into file 1. I accidently moved file into file 1 and then tried to remove file 2. I relized what I did wrong, so then I copied file 1 into file. I then moved file into file2. Then, using the 'rm' command, I removed file 2 from the demo folder.

```
carly@MSI MINGW32 ~/demo
$
```
#### The 'clear' command clears the terminal.

```
carly@MSI MINGW32 ~/demo
$ uname --help
Usage: uname [OPTION]...
Print certain system information.  With no OPTION, same as -s.

  -a, --all                print all information, in the following order,
                             except omit -p and -i if unknown:
  -s, --kernel-name        print the kernel name
  -n, --nodename           print the network node hostname
  -r, --kernel-release     print the kernel release
  -v, --kernel-version     print the kernel version
  -m, --machine            print the machine hardware name
  -p, --processor          print the processor type (non-portable)
  -i, --hardware-platform  print the hardware platform (non-portable)
  -o, --operating-system   print the operating system
      --help     display this help and exit
      --version  output version information and exit

GNU coreutils online help: <https://www.gnu.org/software/coreutils/>
Report any translation bugs to <https://translationproject.org/team/>
Full documentation <https://www.gnu.org/software/coreutils/uname>
or available locally via: info '(coreutils) uname invocation'
```
#### The command 'man uhelp' did not work for me, so I searched alternativess to this command and got "uname --help' and got the above results. This commant gives information about the operating system.

```
$ uname -a
MINGW32_NT-10.0-22621-WOW64 MSI 3.3.6-bec3d608-341.i686 2023-02-22 08:27 UTC i686 Msys
```
#### This command prints the Kernel name, network host name, kernel release data, kernel version, machine hardware name, hardware platform, and operating system in this order.

```
carly@MSI MINGW32 ~
$ ifconfig
bash: ifconfig: command not found

carly@MSI MINGW32 ~
$ ipconfig
bash: ipconfig: command not found

carly@MSI MINGW32 ~
$ ping localhost
bash: ping: command not found

carly@MSI MINGW32 ~
$ netstat
bash: netstat: command not found

```
#### Thses commands did not work on my computer system but I still understand what they do. The 'ifconfig' command will display all current TCP/IP network configuration calues and refreshes the DHCP and DNS settings. The 'ping localhost' command pings thr local IP address. The 'netstat' command provides statistics about all active conncetions of your computer.





