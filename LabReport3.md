# Lab Report 3

# Part 1
## Failure Inducing Input:
Below was a failure inducing input for the `reverseInPlace()` method.
```
@Test
public void testReversedInPlace() {
  int[] input1 = { 1, 4};
  ArrayExamples.reverseInPlace(input1);
  assertArrayEquals(new int[]{4, 1}, input1);
}

```
This Junit test failed because the expected element at index 1 was `1` but instead, it was actually `4`.

## Input That Does Not Induce Failure:
Below was an input that did not induce a failure for the `reverseInPlace()` method.
```
@Test
public void testReversedInPlace2() {
  int[] input1 = {1};
  ArrayExamples.reverseInPlace(input1);
  assertArrayEquals(new int[]{1}, input1);
}

```
This Junit test passed. 

## Symptom:
<img width="972" alt="Screenshot 2024-02-10 at 2 49 42 PM" src="https://github.com/aran102504/cse15l-lab-reports/assets/157055098/ff1e9d0f-4449-47c8-bf0c-6944580b0cbe">

## Bug: Before code change

```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
}

```

## Bug: After code change

```
static void reverseInPlace(int[] arr) {
    for (int i = 0; i < arr.length / 2; i += 1) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - 1 - i] = temp;
    }
}

```

The code change above fixes the issue that caused the JUnit test `testReversedInPlace()` to fail. This is because before the code change, we are reassigning the first 
half of the array with values of the second half. However, since the `for` loop goes through the entire array, the values of the second half of the original array are overwritten
by values from indices that have already been overwritten. To fix this, as seen in the code change, the array only loops through half of the array. This is because looping through the 
entire array would be swapping values twice, which effectively does nothing. I also initialized a variable `temp` to store the original value before it is overwritten so we can 
reassign the latter half of the array with the original value efffectively.


# Part 2
## `find` command: `find` by file type 
Example 1:
```
angelaran@Angelas-MacBook-Pro-3 docsearch-1 % find technical/ -type d
technical/
technical//government
technical//government/About_LSC
technical//government/Env_Prot_Agen
technical//government/Alcohol_Problems
technical//government/Gen_Account_Office
technical//government/Post_Rate_Comm
technical//government/Media
technical//plos
technical//biomed
technical//911report
```
In this example, I utilize the find `-type` command in `technical` to return content of type `d` which means directory. This command returns all of the directories within `technical`. This is useful to see all of the directories within `./technical`

Example 2:
```
angelaran@Angelas-MacBook-Pro-3 docsearch-1 % find technical/government/Alcohol_Problems/ -type f
technical/government/Alcohol_Problems//Session2-PDF.txt
technical/government/Alcohol_Problems//Session3-PDF.txt
technical/government/Alcohol_Problems//DraftRecom-PDF.txt
technical/government/Alcohol_Problems//Session4-PDF.txt
```
In this example, I utilize the find `-type` command in `technical` to return content of type `f` which means file. This command returns all of the files within `technical/government/Alcohol_Problems`. This is useful for a complete list of files within the specified path, in this case, `technical/government/Alcohol_Problems`.

Source: https://tecadmin.net/linux-find-command-with-examples/


## `find` by file modification time 
Example 1:
```
angelaran@Angelas-MacBook-Pro-3 docsearch-1 % find technical/government/Alcohol_Problems -mtime -100
technical/government/Alcohol_Problems
technical/government/Alcohol_Problems/Session2-PDF.txt
technical/government/Alcohol_Problems/Session3-PDF.txt
technical/government/Alcohol_Problems/DraftRecom-PDF.txt
technical/government/Alcohol_Problems/Session4-PDF.txt
```
In this example, I utilize the find '-mtime' command which returns files modified within the number of days specified. Specifically, this command returns all of the files within `technical/government/Alcohol_Problems` that have been modified within 100 days. This command is useful to see which files have been changed recently, or in a given amount of time.

Example 2:
```
angelaran@Angelas-MacBook-Pro-3 docsearch-1 % find technical/911report -mtime -60                   
technical/911report
technical/911report/chapter-13.4.txt
technical/911report/chapter-13.5.txt
technical/911report/chapter-13.1.txt
technical/911report/chapter-13.2.txt
technical/911report/chapter-13.3.txt
technical/911report/chapter-3.txt
technical/911report/chapter-2.txt
technical/911report/chapter-1.txt
technical/911report/chapter-5.txt
technical/911report/chapter-6.txt
technical/911report/chapter-7.txt
technical/911report/chapter-9.txt
technical/911report/chapter-8.txt
technical/911report/preface.txt
technical/911report/chapter-12.txt
technical/911report/chapter-10.txt
technical/911report/chapter-11.txt
```
In this example, I utilize the find '-mtime' command which returns files modified within the number of days specified. Specifically, this command returns all of the files within `technical/911report` that have been modified within 60 days. This command is useful to see which files have been changed recently, or in a given amount of time.

Source: https://tecadmin.net/linux-find-command-with-examples/

## `find` by file size
Example 1:
```
angelaran@Angelas-MacBook-Pro-3 docsearch-1 % find technical/911report -size -10M
technical/911report
technical/911report/chapter-13.4.txt
technical/911report/chapter-13.5.txt
technical/911report/chapter-13.1.txt
technical/911report/chapter-13.2.txt
technical/911report/chapter-13.3.txt
technical/911report/chapter-3.txt
technical/911report/chapter-2.txt
technical/911report/chapter-1.txt
technical/911report/chapter-5.txt
technical/911report/chapter-6.txt
technical/911report/chapter-7.txt
technical/911report/chapter-9.txt
technical/911report/chapter-8.txt
technical/911report/preface.txt
technical/911report/chapter-12.txt
technical/911report/chapter-10.txt
technical/911report/chapter-11.txt
```
In this example, I utilize the find `-size` command to find files that meet the size criteria provided. Specifically, this command in the example returns files in `technical/911report` that are less than 10MB. This is useful because the command can be used to find files both larger and smaller than the inputted number, depending on if there is a `+` or `-` in front of it, respectively. 

Example 2:
```
angelaran@Angelas-MacBook-Pro-3 docsearch-1 % find technical/government -size +199k
technical/government/About_LSC/commission_report.txt
technical/government/Env_Prot_Agen/bill.txt
technical/government/Gen_Account_Office/GovernmentAuditingStandards_yb2002ed.txt
technical/government/Gen_Account_Office/Statements_Feb28-1997_volume.txt
technical/government/Gen_Account_Office/d01591sp.txt

```
In this example, I utilize the find `-size` command to find files that meet the size criteria provided. Specifically, this command in the example returns files in `technical/government` that are greater than 199KB. This is useful because the command can be used to find files both larger and smaller than the inputted number, depending on if there is a `+` or `-` in front of it, respectively. 

Source: https://tecadmin.net/linux-find-command-with-examples/

## `find` combining search criteria using `and` or `or`
Example 1:
```
angelaran@Angelas-MacBook-Pro-3 docsearch-1 % find technical/government -size +250k -and -mtime -100
technical/government/Gen_Account_Office/Statements_Feb28-1997_volume.txt
technical/government/Gen_Account_Office/d01591sp.txt

```
In this example, along with the `find` command, I utilize logical operator `and` to combine search criteria. This specific command only returns files in `technical/government` that meet both criteria inputted into the command line: the size of the file must be larger than 250 KB and the most recent time of modification must have been within 100 days. The use of logical operators are useful so there is no need to use multiple commands to narrow a search down, as they can be combined.

Example 2: 
```
angelaran@Angelas-MacBook-Pro-3 docsearch-1 % find technical/911report -type f -or -size +1M        
technical/911report/chapter-13.4.txt
technical/911report/chapter-13.5.txt
technical/911report/chapter-13.1.txt
technical/911report/chapter-13.2.txt
technical/911report/chapter-13.3.txt
technical/911report/chapter-3.txt
technical/911report/chapter-2.txt
technical/911report/chapter-1.txt
technical/911report/chapter-5.txt
technical/911report/chapter-6.txt
technical/911report/chapter-7.txt
technical/911report/chapter-9.txt
technical/911report/chapter-8.txt
technical/911report/preface.txt
technical/911report/chapter-12.txt
technical/911report/chapter-10.txt
technical/911report/chapter-11.txt
```
In this example, along with the `find` command, I utilize logical operator `or` to combine search criteria. This specific command only returns files in `technical/911report` that meet both criteria inputted into the command line: the file type must be a regular file and the size of the file must be larger than 1MB. The use of logical operators are useful so there is no need to use multiple commands to narrow a search down, as they can be combined. 

Source: https://tecadmin.net/linux-find-command-with-examples/
