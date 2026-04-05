+++
date = '2026-04-05T23:11:47+05:30'
draft = false
title = 'Linux Commands'
image = '/images/Linux Hashnode Cover.png'
weight = 4
+++
#### **By Garvit Singh**

**pwd Command**  
Prints the current working directory.

**cd Command**  
Change working directory. cd command requires you to provide atmost one arguement or no arguement. It cannot be greater than one.
	
- Change directory from Home directory(represented by ~) to Downloads. When you are somewhere inside your Home directory, the terminal uses ~ as an abbreviation.
	
	```bash
	cd Downloads
	```

- Go up to the parent directory. '..' means previous directory. '.' means current directory.
	
	```bash
	cd ..
	```

- Move up through mutiple levels of parent directories.
	
	```bash
	cd ../..
	```

- Switch to the root directory, then follow the route from there towards the directory 'etc'
	
	```bash
	cd /etc
	```

**whoami Command**  
Prints the Host username.

**mkdir Command**  
Create a new directory. It requires you to provide atleast one argument.
	
- Create a folder named 'abc' in the current directory.
	
	```bash
	mkdir abc
	```

- Create a folder named 'gs' in the Downloads directory. It will first go to the Home directory(represented by ~), then go to the Downloads directory and create a directory named 'gs' in it.
	
	```bash
	mkdir ~/Downloads/gs
	```

- Switch to root directory, then create tmp directory and src directory inside tmp.
	
	```bash
	mkdir /tmp/src
	```
	
- Creates all folders in the current directory.
	
	```bash
	mkdir dir1 dir2 dir3
	```
	
- Here, dir4 is created and dir5 is created inside dir4 and dir6 is further created in dir5. We use the -p switch which creates the parent directories as decribed in the arguement.
	
	```bash
	mkdir -p dir4/dir5/dir6
	```

**ls Command**  
ls stands for List. It displays files & directories in a directory. Use the -a switch to list the hidden files like the .bashrc file.
	
- Capture the output of the command in a text file, we use the greater than(>) sign.
	
	```
	ls > result.txt
	```
	
**echo Command**  
Prints the provided arguement in the terminal. Use the -e switch to use newline characters(\n) or tab spaces(\t).

```
echo "Hello"
```

**cat Command**  
Displays the content of the file in the terminal. If you pass more than one filename, it will output each one of them, one after the other. 'cat' comes from the word concatenate which means to link together.

- Display the content of sample.txt stored in dir1.
	
	```bash
	cat dir1/sample.txt
	```

**mv Command**  
mv command lets you move more than one file at a time. If you pass more than two arguements, the last one is taken to be the destination directory and the others are considered to be the files or directories to be moved.

- Here, abc.txt and dir1 will be moved to dir2
	
	```bash
	mv abc.txt dir1 dir2
	```
- Here, abc.txt(located in dir1) will be moved to dir4 which is inside dir3 which is further inside dir2.
	
	```bash
	mv dir1/abc.txt dir2/dir3/dir4
	```
- To rename a file, use the mv command. Here, abc.txt is renamed to xyz.txt. Works on both files and directories.
	
	```bash
	mv abc.txt xyz.txt
	```

**cp Command**  
Copy command to copy files & directories.

- Here, sample.txt which is inside dir1 is copied to dir3.
	
	```bash
	cp dir1/sample.txt dir3
	```
	
**rm Command**  
Remove file command

- Remove sample.txt stored in dir2 which is further inside dir1/
	
	```bash
	rm dir1/dir2/sample.txt
	```
	
- Remove all files starting with 'h' in the current directory
	
	```bash
	rm h*
	```
	
- Remove everything in the current directory
	
	```bash
	rm *
	```
	
- Remove dir1 and delete everything in it even if there were files in it. Use -r switch for this.
	
	```bash
	rm -r dir1
	```

- Use -i switch with rm command which will prompt you to confirm the deletion of each file. Here, we are deleting all files(represented by * ) in the dir3
	
	```bash
	rm -i dir3/*
	```
	
**rmdir Command**  
Remove directory command. If there are any files in the directories, then they will not be deleted.
	
- Here, we are deleting multiple directories at the same time which are stored in a hierarchy. Use the -p switch with rmdir command for this purpose. It deletes dir3 first, then dir2 is deleted and finally dir1 is deleted. Files contained in these directories will not be deleted.
	
	```bash
	rmdir -p dir1/dir2/dir3
	```

**wc Command**  
Word count command. Use the -l switch to know line count.
	
- Here, ls ~ lists the content of the home directory and wc -l counts the lines. The vertical bar ' | ' is the piping operator.
	
	```bash
	ls ~ | wc -l
	```
	
- Count the lines in the /etc directory.
	
	```bash
	ls /etc | wc -l
	```

**less Command**  
Display file's content one screen at a time. This can be used if a file output is very large.

- Display the content of sample.txt
	
	```bash
	less sample.txt
	```

**uniq Command**  
Output unique lines in that file.
	
- Display the content of sample.txt and count the number of unique lines.
	
	```bash
	cat  sample.txt | uniq | wc -l 
	```

**man Command**  
Instruction Manual command.

- Open instruction manual for rmdir command.
	
	```bash
	man rmdir
	```

**sort Command**  
Can be used to sort data in different kinds of ways  
	
- sort : Sort alphabetically
- sort -r : Reverse alphabetical sorting
- sort -f : Case insensitive sorting
- sort -n : Sort numerically

**touch Command**  
Create a file
	
- Create a text file in dir2, which lies inside dir1.
	
	```bash
	touch dir1/dir2/sample.txt
	```

**locate Command**  
Locate files
	
- Locate all files that end with .txt
	
	```bash
	locate *.txt
	```

**find Command**  
To find files & directories inside a directory. Shows hidden files as well. It is similar to ls but has got more functionality, which are shown in the examples.
	
- Find all directories within the current directory. (.) the dot represents the current directory.
	
	```bash
	find . -type d
	```
	
- Find all files in current directory
	
	```bash
	find . -type f
	```
	
- Find file named sample.txt in the current directory
	
	```bash
	find . -type f -name sample.txt
	```
	
- Find all files starting with abc in current directory.
	
	```bash
	find . -type f -name abc*
	```

- Find all files ending with .txt in dir2, which lies inside dir1 which further lies inside Home directory
	
	```bash
	find ~/dir1/dir2 -type f -name *.txt
	```
	
- Do the same but now it is case insensitive search
	
	```bash
	find ~/dir1/dir2 -type f -iname *.txt
	```

- Find all files that were modified less than 20 minutes ago in the current directory
	
	```bash
	find . -type f -mmin -20
	```
	
- Find all files modified more than 15 minutes ago in current directory
	
	```bash
	find . -type f -mmin +15
	```
	
- Find all files modified less than 10 days ago in current directory
	
	```bash
	find . -type f -mtime -10
	```
	
- Find folders with 1 file depth in current directory
	
	```bash
	find . -type f -maxdepth 1
	```
	
- Find all files having size more than 1kB.
	
	```bash
	find . -size +1k
	```
	
- Find all empty files and directories 
	
	```bash
	find .
	```
- Find files which have 777 permission in current directory
	
	```bash
	find . -perm 777
	```

**chmod Command**  
Manage File Permissions

- 4 : Read
- 2 : Write
- 1 : Execute
- 0 : No permissions
- Ex - If you want to give write and execute permissions, then 2 + 1 = 3

- Give Read, Write and Execute permissions to User, Group and other in file named sample.txt stored in dir2
	
	```bash
	chmod 777 dir2/sample.txt
	```

- Give Read, Write and Execute permissions to User, Read and Execute permissions to Group and only Read permission for others in the file abc.txt stored in dir3. 'u' stands for user, 'g' stands for group, 'o' stands for others
	
	```bash
	chmod u=rwx, g=rx, o=r dir3/abc.txt
	```

**exec Command**  
Executes a terminal command without creating a new process. Instead, it replaces the currently open Shell operation. Can be used to rename a large number of files at once.

- Find and delete all files ending with .txt
	
	```bash
	find . -type f -name *.txt -exec rm -rf {} +
	```


**grep Command**  
Used to search for things written inside a file.
	 
- Search the word 'Garvit' inside names.txt
	
	```bash
	grep Garvit names.txt
	```
	
- Display complete word
	
	```bash
	grep -w Garvit names.txt
	```
	
- Case insensitive search
	
	```bash
	grep -i garvit names.txt
	```
	
- Display the line number
	
	```bash
	grep -n Garvit names.txt
	```
	
- Combine all three switches
	
	```bash
	grep -win Garvit names.txt
	```
	
- Display 3 lines that come before the searched word
	
	```bash
	grep -B 3 Garvit names.txt
	```
	
- Search for all files having 'Garvit' and ending with .txt in current directory.
	
	```bash
	grep -win Garvit ./*.txt
	```
	
- List all files containing 'Garvit' in current directory
	
	```bash
	grep -wirl Garvit .
	```
	
- Count how many files contain 'Garvit' in current directory
	
	```bash
	grep -wirc Garvit .
	```

**history Command**  
Shows the history of all past commands executed.
	
- Show history of all 'mkdir' commands using grep.
	
	```bash
	history | grep "mkdir"
	```

###### Some Other Commands

**clear Command**  
Clear the terminal screen.

**jobs Command**  
Displays current jobs running in the shell.

**ping Command**  
Displays connectivity status.

**wget Command**  
Download files from internet.

**top Command**  
Display what all processes are running in the CPU.

**kill Command**  
Kills a running process.

**zip Command**  
Compress files and add to zip folder.

**hostname Command**  
Displays domain name, hostname, system name. Use -i switch to get IP Adrress.

**useradd Command**  
To add a new user

**userdel Command**  
To remove an existing user.

**lscpu Command**  
Get CPU details.

**free Command**  
Check used and free memory.

**vmstat Command**  
Virtual memory statistics.

**getent Command**  
To check if a user exists in a group or not.

**lsof Command**  
List all open files.

**nslookup Command**  
Find IP Addresses of a particular domain.

**netstat Command**  
List active ports

**cut Command**  
Cut out some portion from a file.

**su Command**  
Allows users to switch to the root account and perform administrative tasks when passed with no username as arguements. If given a username, then it switches to a specific user account.

**logout Command**  
Logout from superuser or root account back to normal

**sudo Command**  
It is used to run a command with superuser privileges. A configuration file is used to define which users can use sudo and which commands they can run. When running a command like this, user is prompted for their own password.

**reset Command**  
Clear the terminal

**where Command**  
To get the path or location of a file in the directories.

**open Command**  
Open a directory or path

**tr Command**  
Translate command to translate, squeeze and/or delete characters from standard input, writing to standard output.

**df Command**  
Display disk space usage and similar information. Use -m switch to display sizes in MBs insteads of KBs.

**du Command**  
Display disk usage statistics.

**head Command**
Displays text starting from above.

**tail Command**  
Displays text starting from below.

**diff Command**  
Compares content of two files and outputs every line that doesnt match.

###### **Operators In Bash**  
- & - Used to run commands in the background so that other commands can be run.
- && (AND) - Execute a command only if the command preceding to it is successfully executed.
- | | (OR) - Execute only if the previous command fails
- | (Pipe) - Combine multiple commands
- '>>' (inside) - Transfer results inside the specified file without over-riding previously stored data in the file.
- '>' - Completely overides the content stored in the specified file.

###### **Terminal Keyboard Shortcuts**  
- Ctrl + A : Go to beginning of a line
- Ctrl + E : Go to end of a line
- Ctrl + K : Remove everything in line after the cursor
- Ctrl + U : Deletes entire line.
- Tab : Autocompletion
- Ctrl + R : Search for commands in history.
- Ctrl + L : Clear the terminal screen
- Ctrl + Alt + D : Open Terminal
- Ctrl + D : Close Terminal

Note that these shortcuts might vary depending upon which Linux distribution you are using, or how you have cutomised the settings of your terminal.

Thanks For Reading! 💙

<img src="https://i.imgur.com/rOlCWgG.jpg" alt="GS" width="300"/>

###### By GARVIT SINGH
Information Technology Undergraduate









# BREAK

**pwd Command**  
Prints the current working directory.

**cd Command**  
Change working directory. cd command requires you to provide at-most one argument or no argument. It cannot be greater than one.

* Change directory from Home directory(represented by ~) to Downloads. When you are somewhere inside your Home directory, the terminal uses ~ as an abbreviation.
    
    ```bash
    cd Downloads
    ```
    
* Go up to the parent directory. '..' means previous directory. '.' means current directory.
    
    ```bash
    cd ..
    ```
    
* Move up through multiple levels of parent directories.
    
    ```bash
    cd ../..
    ```
    
* Switch to the root directory, then follow the route from there towards the directory 'etc'
    
    ```bash
    cd /etc
    ```
    

**whoami Command**  
Prints the Host username.

**mkdir Command**  
Create a new directory. It requires you to provide at-least one argument.

* Create a folder named 'abc' in the current directory.
    
    ```bash
    mkdir abc
    ```
    
* Create a folder named 'gs' in the Downloads directory. It will first go to the Home directory(represented by ~), then go to the Downloads directory and create a directory named 'gs' in it.
    
    ```bash
    mkdir ~/Downloads/gs
    ```
    
* Switch to root directory, then create tmp directory and src directory inside tmp.
    
    ```bash
    mkdir /tmp/src
    ```
    
* Creates all folders in the current directory.
    
    ```bash
    mkdir dir1 dir2 dir3
    ```
    
* Here, dir4 is created and dir5 is created inside dir4 and dir6 is further created in dir5. We use the -p switch which creates the parent directories as described in the argument.
    
    ```bash
    mkdir -p dir4/dir5/dir6
    ```
    

**ls Command**  
ls stands for List. It displays files & directories in a directory. Use the -a switch to list the hidden files like the .bashrc file.

* Capture the output of the command in a text file, we use the greater than(&gt;) sign.
    
    ```bash
    ls > result.txt
    ```
    

**echo Command**  
Prints the provided argument in the terminal. Use the -e switch to use newline characters(\\n) or tab spaces(\\t).

```bash
echo "Hello"
```

**cat Command**  
Displays the content of the file in the terminal. If you pass more than one filename, it will output each one of them, one after the other. 'cat' comes from the word concatenate which means to link together.

* Display the content of sample.txt stored in dir1.
    
    ```bash
    cat dir1/sample.txt
    ```
    

**mv Command**  
mv command lets you move more than one file at a time. If you pass more than two arguments, the last one is taken to be the destination directory and the others are considered to be the files or directories to be moved.

* Here, abc.txt and dir1 will be moved to dir2
    
    ```bash
    mv abc.txt dir1 dir2
    ```
    
* Here, abc.txt(located in dir1) will be moved to dir4 which is inside dir3 which is further inside dir2.
    
    ```bash
    mv dir1/abc.txt dir2/dir3/dir4
    ```
    
* To rename a file, use the mv command. Here, abc.txt is renamed to xyz.txt. Works on both files and directories.
    
    ```bash
    mv abc.txt xyz.txt
    ```
    

**cp Command**  
Copy command to copy files & directories.

* Here, sample.txt which is inside dir1 is copied to dir3.
    
    ```bash
    cp dir1/sample.txt dir3
    ```
    

**rm Command**  
Remove file command

* Remove sample.txt stored in dir2 which is further inside dir1/
    
    ```bash
    rm dir1/dir2/sample.txt
    ```
    
* Remove all files starting with 'h' in the current directory
    
    ```bash
    rm h*
    ```
    
* Remove everything in the current directory
    
    ```bash
    rm *
    ```
    
* Remove dir1 and delete everything in it even if there were files in it. Use -r switch for this.
    
    ```bash
    rm -r dir1
    ```
    
* Use -i switch with rm command which will prompt you to confirm the deletion of each file. Here, we are deleting all files(represented by \* ) in the dir3
    
    ```bash
    rm -i dir3/*
    ```
    

**rmdir Command**  
Remove directory command. If there are any files in the directories, then they will not be deleted.

* Here, we are deleting multiple directories at the same time which are stored in a hierarchy. Use the -p switch with rmdir command for this purpose. It deletes dir3 first, then dir2 is deleted and finally dir1 is deleted. Files contained in these directories will not be deleted.
    
    ```bash
    rmdir -p dir1/dir2/dir3
    ```
    

**wc Command**  
Word count command. Use the -l switch to know line count.

* Here, ls ~ lists the content of the home directory and wc -l counts the lines. The vertical bar ' | ' is the piping operator.
    
    ```bash
    ls ~ | wc -l
    ```
    
* Count the lines in the /etc directory.
    
    ```bash
    ls /etc | wc -l
    ```
    

**less Command**  
Display file's content one screen at a time. This can be used if a file output is very large.

* Display the content of sample.txt
    
    ```bash
    less sample.txt
    ```
    

**uniq Command**  
Output unique lines in that file.

* Display the content of sample.txt and count the number of unique lines.
    
    ```bash
    cat  sample.txt | uniq | wc -l
    ```
    

**man Command**  
Instruction Manual command.

* Open instruction manual for rmdir command.
    
    ```bash
    man rmdir
    ```
    

**sort Command**  
Can be used to sort data in different kinds of ways

* sort : Sort alphabetically
    
* sort -r : Reverse alphabetical sorting
    
* sort -f : Case insensitive sorting
    
* sort -n : Sort numerically
    

**touch Command**  
Create a file

* Create a text file in dir2, which lies inside dir1.
    
    ```bash
    touch dir1/dir2/sample.txt
    ```
    

**locate Command**  
Locate files

* Locate all files that end with .txt
    
    ```bash
    locate *.txt
    ```
    

**find Command**  
To find files & directories inside a directory. Shows hidden files as well. It is similar to ls but has got more functionality, which are shown in the examples.

* Find all directories within the current directory. (.) the dot represents the current directory.
    
    ```bash
    find . -type d
    ```
    
* Find all files in current directory
    
    ```bash
    find . -type f
    ```
    
* Find file named sample.txt in the current directory
    
    ```bash
    find . -type f -name sample.txt
    ```
    
* Find all files starting with abc in current directory.
    
    ```bash
    find . -type f -name abc*
    ```
    
* Find all files ending with .txt in dir2, which lies inside dir1 which further lies inside Home directory
    
    ```bash
    find ~/dir1/dir2 -type f -name *.txt
    ```
    
* Do the same but now it is case insensitive search
    
    ```bash
    find ~/dir1/dir2 -type f -iname *.txt
    ```
    
* Find all files that were modified less than 20 minutes ago in the current directory
    
    ```bash
    find . -type f -mmin -20
    ```
    
* Find all files modified more than 15 minutes ago in current directory
    
    ```bash
    find . -type f -mmin +15
    ```
    
* Find all files modified less than 10 days ago in current directory
    
    ```bash
    find . -type f -mtime -10
    ```
    
* Find folders with 1 file depth in current directory
    
    ```bash
    find . -type f -maxdepth 1
    ```
    
* Find all files having size more than 1kB.
    
    ```bash
    find . -size +1k
    ```
    
* Find all empty files and directories
    
    ```bash
    find .
    ```
    
* Find files which have 777 permission in current directory
    
    ```bash
    find . -perm 777
    ```
    

**chmod Command**  
Manage File Permissions

* 4 : Read
    
* 2 : Write
    
* 1 : Execute
    
* 0 : No permissions
    
* Ex - If you want to give write and execute permissions, then 2 + 1 = 3
    
* Give Read, Write and Execute permissions to User, Group and other in file named sample.txt stored in dir2
    
    ```bash
    chmod 777 dir2/sample.txt
    ```
    
* Give Read, Write and Execute permissions to User, Read and Execute permissions to Group and only Read permission for others in the file abc.txt stored in dir3. 'u' stands for user, 'g' stands for group, 'o' stands for others
    
    ```bash
    chmod u=rwx, g=rx, o=r dir3/abc.txt
    ```
    

**exec Command**  
Executes a terminal command without creating a new process. Instead, it replaces the currently open Shell operation. Can be used to rename a large number of files at once.

* Find and delete all files ending with .txt
    
    ```bash
    find . -type f -name *.txt -exec rm -rf {} +
    ```
    

**grep Command**  
Used to search for things written inside a file.

* Search the word 'Garvit' inside names.txt
    
    ```bash
    grep Garvit names.txt
    ```
    
* Display complete word
    
    ```bash
    grep -w Garvit names.txt
    ```
    
* Case insensitive search
    
    ```bash
    grep -i garvit names.txt
    ```
    
* Display the line number
    
    ```bash
    grep -n Garvit names.txt
    ```
    
* Combine all three switches
    
    ```bash
    grep -win Garvit names.txt
    ```
    
* Display 3 lines that come before the searched word
    
    ```bash
    grep -B 3 Garvit names.txt
    ```
    
* Search for all files having 'Garvit' and ending with .txt in current directory.
    
    ```bash
    grep -win Garvit ./*.txt
    ```
    
* List all files containing 'Garvit' in current directory
    
    ```bash
    grep -wirl Garvit .
    ```
    
* Count how many files contain 'Garvit' in current directory
    
    ```bash
    grep -wirc Garvit .
    ```
    

**history Command**  
Shows the history of all past commands executed.

* Show history of all 'mkdir' commands using grep.
    
    ```bash
    history | grep "mkdir"
    ```
    

###### Some Other Commands

**clear Command**  
Clear the terminal screen.

**jobs Command**  
Displays current jobs running in the shell.

**ping Command**  
Displays connectivity status.

**wget Command**  
Download files from internet.

**top Command**  
Display what all processes are running in the CPU.

**kill Command**  
Kills a running process.

**zip Command**  
Compress files and add to zip folder.

**hostname Command**  
Displays domain name, hostname, system name. Use -i switch to get IP Address.

**useradd Command**  
To add a new user

**userdel Command**  
To remove an existing user.

**lscpu Command**  
Get CPU details.

**free Command**  
Check used and free memory.

**vmstat Command**  
Virtual memory statistics.

**getent Command**  
To check if a user exists in a group or not.

**lsof Command**  
List all open files.

**nslookup Command**  
Find IP Addresses of a particular domain.

**netstat Command**  
List active ports

**cut Command**  
Cut out some portion from a file.

**su Command**  
Allows users to switch to the root account and perform administrative tasks when passed with no username as arguments. If given a username, then it switches to a specific user account.

**logout Command**  
Logout from superuser or root account back to normal

**sudo Command**  
It is used to run a command with superuser privileges. A configuration file is used to define which users can use sudo and which commands they can run. When running a command like this, user is prompted for their own password.

**reset Command**  
Clear the terminal

**where Command**  
To get the path or location of a file in the directories.

**open Command**  
Open a directory or path

**tr Command**  
Translate command to translate, squeeze and/or delete characters from standard input, writing to standard output.

**df Command**  
Display disk space usage and similar information. Use -m switch to display sizes in MBs instead of KBs.

**du Command**  
Display disk usage statistics.

**head Command** Displays text starting from above.

**tail Command**  
Displays text starting from below.

**diff Command**  
Compares content of two files and outputs every line that doesn't match.

###### **Operators In Bash**

* & - Used to run commands in the background so that other commands can be run.
    
* && (AND) - Execute a command only if the command preceding to it is successfully executed.
    
* | | (OR) - Execute only if the previous command fails
    
* | (Pipe) - Combine multiple commands
    
* '&gt;&gt;' (inside) - Transfer results inside the specified file without over-riding previously stored data in the file.
    
* '&gt;' - Completely overrides the content stored in the specified file.
    

###### **Terminal Keyboard Shortcuts**

* Ctrl + A : Go to beginning of a line
    
* Ctrl + E : Go to end of a line
    
* Ctrl + K : Remove everything in line after the cursor
    
* Ctrl + U : Deletes entire line.
    
* Tab : Auto completion
    
* Ctrl + R : Search for commands in history.
    
* Ctrl + L : Clear the terminal screen
    
* Ctrl + Alt + D : Open Terminal
    
* Ctrl + D : Close Terminal
    

Note that these shortcuts might vary depending upon which Linux distribution you are using, or how you have customized the settings of your terminal.

Thanks For Reading! 💙

![GS](https://i.imgur.com/rOlCWgG.jpg align="left")

###### By GARVIT SINGH

Information Technology Undergraduate
