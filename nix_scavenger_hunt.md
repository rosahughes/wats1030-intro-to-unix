# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. *Paste the output of the `pwd` command here:* /home/cabox/workspace 

* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?* LICENSE  README.md  challenge_files  nix_scavenger_hunt.md  nix_scavenger_hunt_stretch.md  super_scavengers.md

* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?*
drwxrwxr-x  4 cabox cabox 4.0K Jul  1 18:26 .                                                                                                                        
drwxr-xr-x 11 cabox cabox 4.0K Jul  1 18:26 ..                                                                                                                       
drwxrwxr-x  8 cabox cabox 4.0K Jul  1 18:26 .git                                                                                                                     
-rw-rw-r--  1 cabox cabox 1.1K Jul  1 18:26 LICENSE                                                                                                                  
-rw-rw-r--  1 cabox cabox 2.7K Jul  1 18:26 README.md                                                                                                                
drwxrwxr-x  7 cabox cabox 4.0K Jul  1 18:26 challenge_files                                                                                                          
-rw-rw-r--  1 cabox cabox 5.6K Jul  1 18:30 nix_scavenger_hunt.md                                                                                                    
-rw-rw-r--  1 cabox cabox  317 Jul  1 18:26 nix_scavenger_hunt_stretch.md                                                                                            
-rw-rw-r--  1 cabox cabox  191 Jul  1 18:26 super_scavengers.md  

* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://linux.die.net/man/). Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?*

ls -a means all files in that directory, do not hide entries beginning with .
ls -l means to use long list formatting
ls -h means human-readable, to list the print sizes in format such as 4.0K 

* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?*
bin  boot  dev  etc  fastboot  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var

* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:*
/ 

* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:*
/home/cabox

* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*
3

* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*
/home/cabox/workspace

* Press the up arrow on your keyboard. *What just happened?*
pwd command automatically input

* Press the up arrow a few more times. *What do you see?*
the last commands that I input, in reverse order

* Run the `history` command. *What do you see?*
a list of all the commands I have input during this SSH terminal session

### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?*
cabox

* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:*
It returned: cabox    pts/0        Jul  1 18:26 (52.161.27.120) Doesn't look like anyone else is on this system right now

* How long has your system been running? Use `uptime` to see, and *paste the result here:*
19:16:11 up 49 min,  1 user,  load average: 0.00, 0.00, 0.00 

* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*
These are the processers that have been used during this terminal session to execute the commands entered. It looks like `a` is processes for all users, `u` is the process's user/owner, and `x` shows processes not attached to the terminal.

* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*
It looks like top is a real-time program running behind the command line, keeping track of the systems and tasks. On https://linux.die.net/man/1/top it says that this is configurable to user specification and manipulable. 

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?*
2 files: credit_cards.txt  credit_cards2.txt 

* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*
01-15-2015

* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?*
./tmp/modi_laboriosam.txt 

* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?*
2 files: Britt-Erdman.user:O'Harachester, WA 37261                                                                                                                            
Lissie-Strosin.user:Jewessfurt, WA 00816-7241 

* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*
serial-numbers/eaque_molestiae.txt:Ut est maiores quia autem. Nisi modi Waldo sed corporis sit explicabo ut est. Et est placeat ea sunt sunt consectetur sunt incidun
t. Explicabo vel esse blanditiis dolorem culpa non quia.

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*
A list of all of the files and directories in the parent directory (challenge_files).

* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.*
The same list, but only the amount of items that can be viewed on one screen. Then there is a --More-- prompt at the bottom of the terminal, and if you press enter it adds one more item and scrolls down one.

* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*
root       597  0.0  0.6  63876  3476 ?        Ss   18:26   0:00 sshd: cabox [priv]                                                                                  
cabox      599  0.0  0.5  65612  3100 ?        S    18:26   0:00 sshd: cabox@pts/0                                                                                   
cabox      600  0.0  0.8  20560  4476 pts/0    Ss   18:26   0:00 -bash                                                                                               
root       849  0.0  0.6  63876  3328 ?        Ss   20:30   0:00 sshd: cabox [priv]                                                                                  
cabox      851  0.0  0.2  64140  1548 ?        S    20:30   0:00 sshd: cabox@notty                                                                                   
cabox      852  0.0  0.1  12920  1024 ?        Ss   20:30   0:00 /usr/lib/openssh/sftp-server                                                                        
cabox      862  0.0  0.2  15520  1144 pts/0    R+   20:45   0:00 ps aux                                                                                              
cabox      863  0.0  0.1   8816   768 pts/0    S+   20:45   0:00 grep --color=auto cabox 