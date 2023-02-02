
Here are the 10 Bash commands that'll help you work faster with your terminal.

Background:
- To execute commands on the command line, you need a shell.

- The Bash shell is popular in Unix-like operating systems like Mac and Linux. In fact in most Linux distros, Bash is the default shell.

- You can also use Bash in Windows via WSL (Windows Subsystem for Linux).

## Bash Commands

### 1. Use Control + L to clear the screen and Control + D to exit
To clear the terminal screen, type clear on the command line.

To exit, type exit.

Better still, pressing Ctrl + l ( ⌘ + l ) clears the screen and Ctrl + d (⌘ + d) closes the terminal.

### 2. Use the nohup command to spawn processes that don't end with the terminal session
Once programs are loaded into memory, they are called processes.

Sometimes, I open Firefox from the command line:
firefox https://freecodecamp.org.

But as soon as I close the terminal, Firefox also crashes.

To prevent this, use the nohup (no hang up) command: nohup firefox https://freecodecamp.org.

Now when I close the terminal, Firefox doesn't crash but my tab crashes.

The fix: make Firefox a background process by appending the & symbol.

nohup firefox https://freecodecamp.org &

Now even if I quit the terminal, my tabs are all intact.

### 3. Use pkill to kill processes by typing in only a part of the name
By using the killall command, we can kill a process by its name:

killall firefox

Better still, use pkill to terminate by typing only a part of the name.

pkill fire*

### 4. Prepend the time command to know how fast something executes
Do you want to know how long it takes something to execute in the shell?

Just prepend time to the command: time gcc -g *.c.

### 5. On Linux, use cat /etc/*rel* to view the distro name
Typing uname -a shows the system information.

Wanna double check what distro you're running?

Just type cat /etc/*rel* on the shell and press enter.

### 6. Use the sed command in text files to find and replace
Do you want to replace multiple occurrences of a word in a text file?

Use the sed command.

sed s'/apples/oranges/g' myfile.txt

Here, all the occurrences of the word 'apples' are changed into 'oranges'.

If you only need to replace the first occurrence in every line, just take out the 'g' suffix at the end: sed s'/apples/oranges/' myfile.txt.

The 'g' is for global.

The forward slash / is the delimiter. In fact, you can use any delimiter.

Let's use a single underscore _ as the delimiter: sed s'_apples_oranges_'g ` myfile.txt.

Simply using sed only replaces on the standard output. The original file is unchanged.

To change the file 'in place', use the -i flag: sed -i s'_apples_oranges_g' myfile.txt.

### 7. Know the public IP address of your computer using curl
There are two types of IP addresses: private and public.

A system assigns internal IP addresses which can be checked using the ifconfig command.

But do you want to know the public IP of your computer – the IP address that the ISP assigns to your interface?

While online, just use curl ifconfig.me ; echo  or curl ifconfig.co ; echo on the command line.

### 8. Use Ctrl + R (⌘ + R) for reverse search
Pressing the 'up' arrow key shows the last command you've typed.

Typing history shows all the commands you have typed that are stored in bash history.

Better still, type Ctrl + r (⌘ + r) on the shell and start typing in the command.

As you type, the shell autocompletes from history. Press 'enter' as soon as you find the match.

If you remember only one thing from this tutorial, remember this key combination: Ctrl + r (⌘ + r).

It will save you a lot of time, guaranteed!

### 9. Use the shell for doing math
For simple calculations that don't input or output fractions, you can simply use:

echo $((19*34))

646
For calculations that involve fractions, just echo the expression and pipe it into the bc command.

echo "scale=2; 9*3/((2*2)+1)" | bc
5.40
Here, 'scale' is the precision we need. I have specified it to be two decimal points.

### 10. Use brace expansion to create files in bulk
How do we create 100 files inside a folder?

file1.txt, file2.txt, file3.txt ... file100.txt

By using brace expansion: touch file{1..100}.txt.

We need to create three files for our project: app.html, app.css, and app.js

Instead of creating one by one, we can simply use brace expansion to create all of them in one go.

touch app.{html,css,js}
ls
app.html app.css app.js

Or inside the project folder, we need to create five directories: images, css, src, templates, and scripts.

We can use:

mkdir {images,css,src,templates,scripts}
ls
images css src templates scripts

Only one caveat here: just ensure that there are no spaces between the words inside the braces.

source: https://www.freecodecamp.org/news/bash-command-line-tips-to-help-you-work-faster/