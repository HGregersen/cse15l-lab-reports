# Week 1 Lab Report
## Commands
__cd__
<br>
_No Arguments_
* ![Image](cdNoArg1.png)
* ![Image](cdNoArg2.png)
* I ran the command in both /home/lecture1 and /home/lecture1/messages directories.
* With both directories, when you run cd with no argument, you're returned to the /home directory (you stay in the /home directory if you're already there). 
* The output is not an error.
<br>

_Directory As Argument_
* ![Image](cdDArg1.png)
* ![Image](cdDArg2.png)
* I ran the commands in the /home directory.
* For both arguments, I tried to change to the /home/lecture1/messages directory, but since I was in the /home directory, I couldn't get to it without adding that it was in the /home/lecture1 directory (first argument).
* The second argument gave me an error saying that there's no such file/directory since /messages is not a directory in /home, but a directory in /home/lecture1.
<br>

_File As Argument_
* ![Image](cdFArg1.png)
* I ran the command in the /home directory.
* While I tried to change to the /home/lecture1/messages/en-us.txt file, since it isn't a directory it gave me an error and I was unable to do so.
<br><br>

__ls__
<br>
_No Arguments_
* ![Image](lsNoArg1.png)
* ![Image](lsNoArg2.png)
* I ran the commands in the /home and /home/lecture1 directories.
* With both directories, without an argument, ls lists the files and directories in the respective current working directories.
* The output is not an error.
<br>

_Directory As Argument_
* ![Image](lsDArg1.png)
* I ran the commands in the /home directory.
* For both arguments, I tried to list what's in the /home/lecture1/messages directory, but since I was in the /home directory, I couldn't get to it without adding that it was in the /home/lecture1 directory (first argument).
* The second argument gave me an error saying that there's no such file/directory since /messages is not a directory in /home, but a directory in /home/lecture1.
<br>

_File As Argument_
* ![Image](lsFArg1.png)
* I ran the commands in the /home and /home/lecture1/messages directories.
* With both directories, it just returned the path that I inputted for the files (/lecture1/messages/en-us.txt and en-us.txt).
* There were no errors.
<br><br>

__cat__
<br>
_No Arguments_
* ![Image](catNoArg.png)
* I ran the commands in the /home and /home/lecture1 directories.
* With both directories, it just returns nothing, but you can get out of it with Ctrl+C.
* It did not return an error.
<br>

_Directory As Argument_
* ![Image](catDArg.png)
* I ran the command in the /home directory.
* I tried to cat the /home/lecture1 directory and it returned an error since lecture1 is a directory instead of a file.
<br>

_File As Argument_
* ![Image](catFArg.png)
* I ran the commands in the /home directory.
* I concatenated the README and Hello.java files in the /home/lecture1 directory and it returned the text contents of the files.
* There were no errors.
___
##Notes
* If you try to access a file/directory with the incorrect path for the directory you're in, i.e. ls messages while in /home instead of /home/lecture1, or there's a misspelling, you will get an error saying there's no such file/directory.