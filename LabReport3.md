# Part 1 - Bugs
**Failure inducing input (Junit test):**
```
@Test 
	public void testReverseInPlaceMultiple() {
    int[] input1 = { 3, 2, 1 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 1, 2, 3 }, input1);
	}
```

**Input that does not induce a failure (Junit test):**
```
@Test 
	public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}
```

**The symptom:** 
<br>
![image](https://github.com/matt0923/cse15l-lab-reports/assets/74699880/bde4d0c5-7203-4638-a398-5982194df044)

**The bug before the fix (Only works for a singular input):**
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

**The bug after the fix:**
```
static void reverseInPlace(int[] arr) {
    int[] newArr = new int[arr.length];
    for(int i = 0; i < arr.length; i+=1) {
      newArr[i] = arr[i];
    }
    for(int i = 0; i < arr.length; i+=1) {
      arr[i] = newArr[arr.length - i - 1];
    }
  }

```
The fix addresses the issue by copying the input array into a second array, and making the original array the reverse of the second. The bug occurred because the original array was rewriting itself with the last element of the array, thus causing it to not work as intended. For example, if we inputted ```{5, 4, 3, 2, 1}```, the array would become ```{1, 4, 3, 2, 1}``` after the first iteration of the loop, and result with an array of value ```{1, 2, 3, 2, 1}```, which is not the reverse of the input array. Instead of overriding the original array with it's own values, I instead created a second array of the exact same values, and made the original array's values the end values of the copy array (In an array with a length of 3, ```arr[0] = newArr[3]. arr[1] = newArr[2], arr[2] = newArr[1]```).

# Part 2 - Researching Commands
**For my research, I chose the grep command.**
The grep command takes in an option and a pattern as well as a file name to search the given file for a particular pattern of characters, and displays all lines of the given file that contain the patten. (```grep [options] pattern [files]```)
<br>
**Using ```-o``` as the option on a file:**
```
Input: 
Matthew@DESKTOP-OKA7K02 MINGW64 ~/Documents/GitHub/docsearch/technical/911report (main)
$ grep -o "Boston"  chapter-1.txt
Output:
Boston
Boston
Boston
...
```
This particular ```grep -o``` command  prints all of the instances of the word Boston in the file chapter-1.txt <br>
<br>
Sources: [https://www.geeksforgeeks.org/grep-command-in-unixlinux/](https://www.geeksforgeeks.org/grep-command-in-unixlinux/) and experimenting in VS code
<br>
<br> 
**Using ```-o``` as the option on a directory:**
```
Input:
Matthew@DESKTOP-OKA7K02 MINGW64 ~/Documents/GitHub/docsearch/technical (main)
$ grep -r  -o "Boston"  911report
Output:
911report/chapter-1.txt:Boston
911report/chapter-1.txt:Boston
911report/chapter-1.txt:Boston
...
```
This particular ```grep -r -o``` command (```-r``` needed to look inside of a directory) is used to display all of the instances of the word Boston in each of the files in the entire 911reports directory, stating which text files they're in, and using the ```-o``` command to only display the matched parts of the matching lines. <br>
<br>
Sources: [https://www.geeksforgeeks.org/grep-command-in-unixlinux/](https://www.geeksforgeeks.org/grep-command-in-unixlinux/) and experimenting in VS code
<br>
<br>
**Using ```-v``` as the option on a file:**
```
Input: 
Matthew@DESKTOP-OKA7K02 MINGW64 ~/Documents/GitHub/docsearch/technical/911report (main)
$ grep -v "a" chapter-1.txt

Output:

"WE HAVE SOME PLANES"



INSIDE THE FOUR FLIGHTS
...
```
This particular ```grep -v``` command prints out all of the lines in the text file (chapter-1.txt) that don't match our target (a). <br>
<br>
Sources: [https://www.geeksforgeeks.org/grep-command-in-unixlinux/](https://www.geeksforgeeks.org/grep-command-in-unixlinux/) and experimenting in VS code
<br>
<br>
**Using ```-v``` as the option on a file:**
```
Input: 
Matthew@DESKTOP-OKA7K02 MINGW64 ~/Documents/GitHub/docsearch/technical (main)
$ grep -r -v "the" biomed
Output:
plos/pmed.0020238.txt:        codeine, ibuprofen, lorazepam, 5HT1 receptor agonists, and acyclovir were not efficacious
plos/pmed.0020238.txt:        in PHN.
plos/pmed.0020238.txt:        gabapentinoids for second-line use. Topical treatments, such as lidocaine or capsaicin,
...
```
This particular ```grep -r -v``` command (-r needed to look inside of a directory) prints out all of the lines in all of the text files in the entire directory biomed that do not contain "the" <br>
<br>
Sources: [https://www.geeksforgeeks.org/grep-command-in-unixlinux/](https://www.geeksforgeeks.org/grep-command-in-unixlinux/) and experimenting in VS code
<br>
<br>
**Using ```-c``` as the option on a file:**
```
Input:
Matthew@DESKTOP-OKA7K02 MINGW64 ~/Documents/GitHub/docsearch/technical/911report (main)
$ grep -c "the" chapter-1.txt
Output:
313
```
This particular ```grep -c``` command prints out the amount of lines that contain the word "the" in the chapter-1.txt file. <br>
<br>
Sources: [https://www.geeksforgeeks.org/grep-command-in-unixlinux/](https://www.geeksforgeeks.org/grep-command-in-unixlinux/) and experimenting in VS code
<br>
<br>
**Using ```-c``` as the option on a directory:**
```
Input: 
Matthew@DESKTOP-OKA7K02 MINGW64 ~/Documents/GitHub/docsearch/technical (main)
$ grep -r -c "the" 911report
Output:
911report/chapter-1.txt:313
911report/chapter-10.txt:336
911report/chapter-11.txt:533
...
```
This particular ```grep -r -c``` command (```-r``` needed to look inside of a directory) prints out the amount of lines in each of the text files in the directory 911report that contain "the", seperated by file. <br>
<br>
Sources: [https://www.geeksforgeeks.org/grep-command-in-unixlinux/](https://www.geeksforgeeks.org/grep-command-in-unixlinux/) and experimenting in VS code
<br>
<br>
**Using ```-l``` as the option on a file:**
```
Input:
Matthew@DESKTOP-OKA7K02 MINGW64 ~/Documents/GitHub/docsearch/technical/911report (main)
$ grep -l "the" chapter-2.txt
Output:
chapter-2.txt
```
This particular ```grep -l``` command prints out the list of filenames that contain the word the, which can only either be nothing or that text file's name (depending on whether or not the text file contains the target word/phrase/character).
<br>
<br>
Sources: [https://www.geeksforgeeks.org/grep-command-in-unixlinux/](https://www.geeksforgeeks.org/grep-command-in-unixlinux/) and experimenting in VS code
<br>
<br>
**Using ```-l``` as the option on a directory:**
```
Input: 
Matthew@DESKTOP-OKA7K02 MINGW64 ~/Documents/GitHub/docsearch/technical (main)
$ grep -l -r "the" 911report
Output:
911report/chapter-1.txt
911report/chapter-10.txt
911report/chapter-11.txt
...
```
This particular ```grep -l -r``` command (```-r``` needed to look inside of a directory) prints out the names of all of the txt files inside of the directory 911 report that contain the word the in them. 
<br>
<br>
Sources: [https://www.geeksforgeeks.org/grep-command-in-unixlinux/](https://www.geeksforgeeks.org/grep-command-in-unixlinux/) and experimenting in VS code
<br>
