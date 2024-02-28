# Week 5 Lab Report
## Part 1 - Bugs
**Failure-Inducing Input**<br>
```
@Test
public void testReverseInPlace() {
  ... note 4 lines omitted ...
  int[] input2 = { 2, 3 };
  ArrayExamples.reverseInPlace(input2);
  assertArrayEquals(new int[]{ 3, 2 }, input2);
}
```
**Success-Inducing Input**<br>
```
@Test 
public void testReverseInPlace() {
  int[] input1 = { 3 };
  ArrayExamples.reverseInPlace(input1);
  assertArrayEquals(new int[]{ 3 }, input1);
}
```
**Output**<br>
*Success*<br>
![Successful Run](success.png)<br>
*Failure*<br>
![Failed Run](failure.png)<br>
**Code**<br>
*Before*
```
static void reverseInPlace(int[] arr) {
  for(int i = 0; i < arr.length; i += 1) {
    arr[i] = arr[arr.length - i - 1];
  }
}
```
*After*
```
static void reverseInPlace(int[] arr) {
  for(int i = 0; i < arr.length / 2; i += 1) {
    int hold = arr[i];
    arr[i] = arr[arr.length - i - 1];
    arr[arr.length - i - 1] = hold;
  }
}
```
**Description:** This fixes the issue since originally the code would just iterate through the provided array arr and basically put the last element at each index (so the array test I provided would give {3, 3} 
instead of {3, 2}). So, instead, I made it so that it saved the element before changing it and only ran for half of the original time (i < arr.length / 2) so that it would switch the first and last elements for each
iteration.<br><br>
## Part 2 - Researching Commands (`grep [options] [pattern] [files]`)
**`-c`**<br>
* ```
  $ grep -c "RNA" biomed/1471-2105-3-2.txt
  384
  ```
  * The command finds the number of lines in the specified file that matches the provided string ("RNA", 384).
* ```
  $ $ grep -c "table" biomed/1471-2105-3-2.txt
  34
  ```
  * The command finds the number of lines in the specified file that matches the provided string ("table", 34).
<br>
<br><br>**`-l`**<br>
* ```
  $ grep -l "table" *
  grep: 911report: Is a directory
  grep: biomed: Is a directory
  grep: government: Is a directory
  grep: plos: Is a directory
  ```
  * The command finds and lists the files/directories that contain the provided string ("table") in the specified files (* (all)).
* ```
  $ grep -l "toes" *
  grep: 911report: Is a directory
  grep: biomed: Is a directory
  grep: government: Is a directory
  grep: plos: Is a directory
  ```
  * The command finds and lists the files/directories that contain the provided string ("toes") in the specified files (* (all)).
<br>
<br><br>**`-H`**<br>
* ```
  $ grep -H table biomed/1471-2105-3-2.txt
  biomed/1471-2105-3-2.txt:            Nucleotide Frequency Tabular Display tables (see
  biomed/1471-2105-3-2.txt:            Base-Pair" tables that are discussed in the next
  ... note 31 lines omitted ...
  biomed/1471-2105-3-2.txt:        generate more frequency tables for more phylogenetic groups
  ```
  * The command makes sure that the file name is listed even when searching in only one file (`biomed/1471-2105-3-2.txt`).
* ```
  $ grep -H pizza 911report/chapter-7.txt
  911report/chapter-7.txt:                pursuing ordinary activities: making ATM withdrawals, eating pizza, and shopping at
  ```
  * The command makes sure the file name is listed when searching for a specific string ("pizza") in only one file (`911report/chapter-7.txt`)
<br>
<br><br>**`-v`**<br>
* ```
  $ grep -v "the" biomed/1468-6708-3-1.txt
  
    
      
        Introduction
        Older adults are frequently counseled to lose weight,
        associated with increased mortality in those over age 65.
        Six large controlled population-based studies of
  ... note 277 lines omitted ...
          YOL Years of life
      
    
  

  ```
  * The command finds every line that doesn't contain `the` (case-sensitive) in the specified file (`biomed/1468-6708-3-1.txt`).
* ```
  $ grep -v "and" biomed/1468-6708-3-1.txt

  
    
      
        Introduction
        Older adults are frequently counseled to lose weight,
        even though there is little evidence that overweight is
        associated with increased mortality in those over age 65.
        Six large controlled population-based studies of
    ... note 325 lines omitted ...
        QALY Quality-adjusted life years
        YHL Years of healthy life
        YOL Years of life
      
    
  

  ```
  * The command finds every lines that doesn't contain `and` (case-sensitive) in the specified file (`biomed/1468-6708-3-1.txt`).
<br>
<br><br><br>**Source: [https://www.geeksforgeeks.org/grep-command-in-unixlinux/](https://www.geeksforgeeks.org/grep-command-in-unixlinux/)**
