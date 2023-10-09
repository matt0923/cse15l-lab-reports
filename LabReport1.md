## Lab Report 1:

** cd no arguments: **
```
Input:
[user@sahara ~]$cd
Output:
[user@sahara ~]$

Input:
[user@sahara ~]$cd lecture1
Output:
[user@sahara ~/lecture1]$

Input:
[user@sahara ~/lecture1/messages]$ cd en-us.txt
Output:
bash: cd: en-us.txt: Not a directory

Input:
[user@sahara ~]$ls
Output:
lecture1

Input:
[user@sahara ~]$ls lecture1
Output:
Hello.class  Hello.java  messages  README

Input:
[user@sahara ~/lecture1/messages]$ ls en-us.txt
Output:
en-us.txt

Input:
[user@sahara ~]$ cat
Output:
Nothing (Crashes terminal)

Input:
[user@sahara ~]$ cat lecture1
Output:
cat: lecture1: Is a directory

Input: [user@sahara ~/lecture1/messages]$ cat en-us.txt
Output:
Hello World!
```
