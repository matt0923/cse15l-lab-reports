## cd command with no arguments:
```
Input:
[user@sahara ~]$cd
Output:
[user@sahara ~]$
```
Directory before code was ran: **/home** <br>
Directory after code was ran: **/home** <br>
Error? **No** <br>
<br>
Running the command "cd" results in nothing being done because the cd command needs a target directory to jump to. Even though this command doesn't directly result in an error, using this command without an argument gets us nowhere. 

## cd command with a path to a directory as an argument:
```
Input:
[user@sahara ~]$cd lecture1
Output:
[user@sahara ~/lecture1]$
```
Directory before code was ran: **/home** <br>
Directory after the code was ran: **/home/lecture1** <br>
Error? **No** <br>
<br>
Running the code "cd lecture1" results in the directory being switched from /home to /home/lecture1. This is the correct way to use the command, with your target directory being the argument. This is the opposite of an error, because the command worked correctly. 

## cd command with a path to a file as an argument:
```
Input:
[user@sahara ~/lecture1/messages]$ cd en-us.txt
Output:
bash: cd: en-us.txt: Not a directory
```
Directory before the code was ran: **/home/lecture1/messages** <br>
Directory after the code was ran: **/home/lecture1/messages** <br>
Error? **Yes** <br>
<br>
Running the code "cd en-us.txt" results in an error, because en-us.txt is not a directory. This is the incorrect way to use the command, the correct way to use this command is to use the command with a path to a directory as an argument. 

## ls command with no argument:
```
Input:
[user@sahara ~]$ls
Output:
lecture1
```
Directory before the code was ran: **/home** <br>
Directory after the code was ran: **/home** <br>
Error? **No** <br>
<br>
Running the code "ls" results in the contents of the home directory being printed, which is just the directory lecture1. This command is very useful as you can look inside directories for programs to run or text files where output could be stored. 

## ls with a directory as an argument:
```
Input:
[user@sahara ~]$ls lecture1
Output:
Hello.class  Hello.java  messages  README
```
Directory before the code was ran: **/home** <br>
Directory after the code was ran: **/home** <br>
Error? **No** <br>
<br>
Running the code "ls lecture1" results in the contents of the lecture1 directory being printed without changing the working directory. As you can see it prints all of the contents of lecture1, including the Hello.class file, the Hello.java file, the messages directory, and the README file

## ls with a file as an argument: 
```
Input:
[user@sahara ~/lecture1/messages]$ ls en-us.txt
Output:
en-us.txt
```
Directory before the code was ran: **/home/lecture1/messages** <br>
Directory after the code was ran: **/home/lecture1/messages** <br>
Error? **No** <br>
<br>
Running the code "ls en-us" results in the file en-us.txt being printed without changing the working directory. Using a file as an argument just prints the name of the text file that you entered as the argument, so using ls this way is a bit redundant. 

## cat with no arguments:
```
Input:
[user@sahara ~]$ cat
Output:
Nothing (Crashes terminal)
```
Directory before the code was ran: **/home** <br>
Directory after the code was ran: **None? (Terminal crash)** <br>
Error? **Yes** <br>
<br>
Running the code "cat" results in a terminal crashing error, because no file was provided as an argument, so the terminal crashed. The cat command normally lets you basically open a file in the terminal without having the file open for editing 

## cat with a directory as an argument: 
```
Input:
[user@sahara ~]$ cat lecture1
Output:
cat: lecture1: Is a directory
```
Directory before the code was ran: **/home** <br>
Directory after the code was ran: **/home** <br>
Error? **Yes** <br>
<br>
Running the code "cat lecture1" results in an error, because lecture1 is a directory, while that cat command requires a file argument. This time, the terminal returns you to where you were before, meaning that the command did not work as intended.

## cat with a file as an argument: 
```
Input: [user@sahara ~/lecture1/messages]$ cat en-us.txt
Output:
Hello World!
```
Directory before the code was ran: **/home/lecture1/messages** <br>
Directory after the code was ran: **/home/lecture1/messages** <br>
Error? **No** <br>
<br>
Running the code "cat en-us.txt" results in the contents of the text file en-us.txt being printed, meaning that the command worked as it was intended to. We used a file as an argument, which resulted in the contents of the file being printed to the terminal. If we were to use this command with the Hello.java file, it would print the code inside. 
