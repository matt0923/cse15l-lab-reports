# Step 4 (Logging into ieng6):
**Input:**
```
ssh cse15lfa23iu@ieng6.ucsd.edu
<Enter>
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
<Enter>
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
<Enter>
bash test.sh
<Enter>
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
nnnnnnnnn
llllll
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

# Step 8 (Run the tests again, showing that they now work):
**Input:**
```
<up><up><enter>
```
**Result:**
<br>
![Image](Matthew%20Williams%20Step%208.png) 

The bash test.sh file was 2 up in the search history, so I used the up arrow to access it. Once I ran the tests again, 
I got the expected output of two successful tests. 

# Step 9 (Commit and push):
**Input:**
```
git add ListExamples.java
<Enter>
git push
<Enter>
git commit
<Enter>
i
This is for my lab report!
<Esc>
:wq
git push
```
**Result:**
<br>
![Image](Matthew%20Williams%20Step%209.png) 

I git added the changed ListExamples.java file, staging it for commit. I then git pushed a little early, so it didn't do anything
(no changes committed to push yet). 
Afterwards, I git committed, which brought me into vim. I then entered insert mode with i, and added my commit message "This is for
my lab report!", then went back into normal mode with escape. I then used :wq to save and quit. I then used git push like it was 
intended to be used, resulting in the changes being committed to my lab7 repository. 
