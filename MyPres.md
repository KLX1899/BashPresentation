```
██████╗``█████╗`███████╗██╗``██╗``````````````````````````````````
██╔══██╗██╔══██╗██╔════╝██║``██║``````````````````````````````````
██████╔╝███████║███████╗███████║``````````````````````````````````
██╔══██╗██╔══██║╚════██║██╔══██║``````````````````````````````````
██████╔╝██║``██║███████║██║``██║``````````````````````````````````
╚═════╝`╚═╝``╚═╝╚══════╝╚═╝``╚═╝``````````````````````````````````

███████╗`██████╗██████╗`██╗██████╗`████████╗██╗███╗```██╗`██████╗`
██╔════╝██╔════╝██╔══██╗██║██╔══██╗╚══██╔══╝██║████╗``██║██╔════╝`
███████╗██║`````██████╔╝██║██████╔╝```██║```██║██╔██╗`██║██║``███╗
╚════██║██║`````██╔══██╗██║██╔═══╝````██║```██║██║╚██╗██║██║```██║
███████║╚██████╗██║``██║██║██║````````██║```██║██║`╚████║╚██████╔╝
╚══════╝`╚═════╝╚═╝``╚═╝╚═╝╚═╝````````╚═╝```╚═╝╚═╝``╚═══╝`╚═════╝`

```
<br>
<br>
<br>
<font color="green" size=7>
    <b>
        O.S. Lab
    <b>
</font>
<br>
<font color="navibl" size=6>
    <b>
        Eng. Yousefnezhad
    <b>
</font>

---

# GITHUB

## This file is also on GitHub.
![](/Media/qrcode_github.com.png)

[Github](https://github.com/KLX1899/BashPresentation)

---

# Linux

Older Unux versions had no GUI. They worked only through terminal!
<br>
<br>
![](https://hackaday.com/wp-content/uploads/2023/08/term1.png)
<font color="orange" size=2>
    old Linux versions
</font>

So it makes sense that many commands must exist to work and navigate on Linux.

---

# Commands

In the last session, we were introduced to a series of popular and widely used commands.

```bash
$ cd /your/dir/path/

$ pwd

$ mkdir /path/YourDirName/

$ ls

$ touch /path/YourFileName/

$ echo "Hello Linux!" >> /path/YourFileName/

$ cat /path/YourFlieName/
    or
$ cat /path/YourFileName/

    .
    .
    .

```

---

# Part1: Thompson shell

![](https://upload.wikimedia.org/wikipedia/commons/d/dd/Ken_Thompson%2C_2019.jpg)
<br>
<font color="orange" size=2>
    Ken Thompson
</font>
<br>
<br>
The <i>Thompson shell</i> was the first Unix shell, and was written by <i>Ken Thompson</i>.

It was a simple command interpreter, not designed for scripting, but nonetheless introduced several innovative features to the command-line interface and led to the development of the later Unix shells.

---

# Part2: Bourne shell

![](https://cacmb4.acm.org/system/assets/0000/0379/031309_Steve_Bourne.large.jpeg?1476779418&1236952990)
<br>
<font color="orange" size=2>
    Steve Bourne
</font>

## 1977: The Bourne shell was introduced....

Created by <b>Stephen Bourne</b> for V7 UNIX.<br>
It remains a useful shell today (in some cases, as the default root shell).<br>


Bourne introduced:
- control flows
- loops
- variables into scripts
- providing a more functional language to interact with the OS

But the shell lacked the ability to define functions. (ಥ﹏ಥ) <br>

---

# Part3: Bourne-Again SHell (BASH)

What we use today is actually a descendant of Bourne Shell, which underwent changes over time that made it better. <br>
BASH Created in 1989 by Brian Fox for the GNU Project, and designed as a 100% free alternative for the Bourne shell (sh) and other proprietary Unix shells. <br>
The keywords, syntax, dynamically scoped variables, and other basic features of the language are all copied from the Bourne shell, (sh). Other features, e.g., history, are copied from the C shell, (csh), and the Korn Shell, (ksh).

---

# BASH SCRIPT

Today, with the changes that have occurred, we can program with the same commands.

But we want to talk about a few more things. For example, <i>SHEBANG</i>, <i>ALIAS</i> and <i>CRONJOB</i>

---

# SHEBANG

You'll often come across shell scripts that start with:
```bash
#!/bin/bash
```
This #! is called shebang or hashbang. <br>
Shebang has a special meaning when it is used in the very first line of the script. <br>
It is used to specify the interpreter with which the given script will be run by default.

So, if the first line of a script is:
```bash
#!/bin/bash
```
It means the interpreter should be bash shell. If the first line is:
```bash
#!/bin/zsh
```
It means the interpreter to be used is Z shell.

---

# ALIAS

BASH Alias is a shortcut to run commands using some mapping. <br>
The alias keyword replaces the command with the string which might be sets of commands or functions. <br>
The alias is defined in the <i>~/.bashrc</i> or <i>~/.bash_profile</i>. <br>
These files are loaded in the shell environment and thus the commands listed in the alias are also been loaded and ready to be executed.<br>

---

# ALIAS

Some of my own-made aliases in my .bashrc:
```bash
# some more ls aliases
alias ll='ls -alF'
alias la='ls -A'
alias l='ls -CF'

# Python3 alias
alias python='python3'

# 'mkdir' + 'cd' alias
function mkcdir() {
    mkdir -p "$1"
    cd "$1"
}

# cowsay
if [ -x /usr/games/cowsay -a -x /usr/games/fortune ]; then
    cowsay "Hi Amir!" | lolcat
fi

# open directory with GUI alias
alias open='nautilus ./'

# check battery health alias
alias batthealth='upower -i /org/freedesktop/UPower/devices/battery_BAT0'
```

---

# CRONJOB

## CRONJOB
A cronjob is a Linux command used for scheduling tasks to be executed sometime in the futue. <br>

## SCHEDULING SYNTAX

```bash
$ m h dom mon dow command
```
+ m : min 
+ h : hour
+ dom : day of month
+ mon : month
+ dow : day of week

'*' means any step values

example:
```bash
$ 1 0 1 * * ./CronJob.sh
```
That means run CronJob.sh on the first minute of the first day of each month

---

# BASH SCRIPTER

For BASH scripting you can read [this ebook](https://github.com/bobbyiliev/introduction-to-bash-scripting) in github:

![](/Media/qrcode_introduction_to_bash_scripting.png)

---

# BASH SCRIPTER

this is a cool and complete [cheat-sheet](https://devhints.io/bash) for bash scripting:

![](/Media/qrcode_devhints.io.png)

---

```
████████╗██╗  ██╗ █████╗ ███╗   ██╗██╗  ██╗    ██╗   ██╗ ██████╗ ██╗   ██╗██╗
╚══██╔══╝██║  ██║██╔══██╗████╗  ██║██║ ██╔╝    ╚██╗ ██╔╝██╔═══██╗██║   ██║██║
   ██║   ███████║███████║██╔██╗ ██║█████╔╝      ╚████╔╝ ██║   ██║██║   ██║██║
   ██║   ██╔══██║██╔══██║██║╚██╗██║██╔═██╗       ╚██╔╝  ██║   ██║██║   ██║╚═╝
   ██║   ██║  ██║██║  ██║██║ ╚████║██║  ██╗       ██║   ╚██████╔╝╚██████╔╝██╗
   ╚═╝   ╚═╝  ╚═╝╚═╝  ╚═╝╚═╝  ╚═══╝╚═╝  ╚═╝       ╚═╝    ╚═════╝  ╚═════╝ ╚═╝
```
<font color="orange" size=10>
    (◍•‿•)
</font>