# Step 4 (Logging into ieng6):
**Input:**
```
ssh cse15lfa23iu@ieng6.ucsd.edu
```
**Result:**
<br>
![Image](Matthew%20Williams%20Step%204.png) 

I did not have the command pre typed out, so all I did was the default ssh command that we've been doing for a little while now. 
This time, it did not prompt me for a password like we expected, because of a previous week's lab. 

# Step 5 (Clone my fork):
**Input:**
```
git clone git@github.com:matt0923/lab7.git
```
**Result:**
<br>
![Image](Matthew%20Williams%20Step%205.png) 

I did not have the command pre typed out, so all I did was type out the git clone command along with my local ssh key
to get the expected result. Everyone's local ssh key should almost be the same, with the part containing your username
being the only distinguishable trait. 

# Step 6 (Running tests):
**Input:**
```
cd lab7
bash test.sh
```
**Result:**
<br>
![Image](Matthew%20Williams%20Step%206.png) 

I did not have either of the commands pre typed out, so all I did was change directories into lab7, and then ran the bash 
script inside that contained the junit tests. It was very nice to have everything in a bash script, makes running the 
junit tests faster because I don't have to type them out. 

# Step 7 (Fix test):
**Input:**
```
vim ListExamples.java
/index1
<enter>
n x 9
l x 6
i
<backspace>
2
<esc>
:wq
```
**Result:**
<br>
![Image](Matthew%20Williams%20Step%207.png) 

I entered vim for the file ListExamples.java, searched for the instances of index1, searched through until I got to 
the one I needed to change, by going forward with n. Once I got to the one I was looking for, I moved my cursor to the
right of the word using l. I then entered insert mode, removing the 1 and adding the 2 as instructed. I then went back
into normal mode with escape, and then typed :wq to save and quit. 
