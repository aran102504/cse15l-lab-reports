# Lab Report 5
## Part 1: Debugging Scenario
## Student Post:
Hello everyone, I'm having trouble with the list merging function in my Java program. It's supposed to merge two sorted lists of strings into a single sorted list, but it doesn't seem to be working properly. I've attached a screenshot below showing the output I'm getting when I test my code using the `bash` command and tester file `test.sh`. 
<img width="800" alt="Screenshot 2024-03-12 at 12 03 39 PM" src="https://github.com/aran102504/cse15l-lab-reports/assets/157055098/d26389c1-bb12-4f3b-9de5-383d2f0ace82">


Here is the relevant part of my code:
```
static List<String> merge(List<String> list1, List<String> list2) {
    List<String> result = new ArrayList<>();
    int index1 = 0, index2 = 0;
    while(index1 < list1.size() && index2 < list2.size()) {
        if(list1.get(index1).compareTo(list2.get(index2)) < 0) {
            result.add(list1.get(index1));
            index1 += 1;
        }
        else {
            result.add(list1.get(index2)); 
            index2 += 1;
        }
    }
    while(index1 < list1.size()) {
        result.add(list1.get(index1));
        index1 += 1;
    }
    while(index2 < list2.size()) {
        result.add(list2.get(index2));
        index2 += 1;
    }
    return result;
}

```


## TA Response:

It seems like there might be an issue with how you're accessing elements from `list2` inside the merge method. To debug this, could you try printing out the elements being added to the result list inside the merge method? This will help us understand what's happening with the merging process. You can add a `System.out.println("Added: " + list1.get(index1));` and System.out.println`("Added: " + list1.get(index2));` statements inside the `if` and `else` blocks, respectively.

## Student Response:
I added a main method to see the output with examples. Here is the code I added in it:
```
 public static void main(String[] args) {
     
      List<String> list1 = new ArrayList<>();
      list1.add("apple");
      list1.add("banana");
      list1.add("orange");

      List<String> list2 = new ArrayList<>();
      list2.add("cherry");
      list2.add("grape");
      list2.add("melon");

      List<String> mergedList = ListExamples.merge(list1, list2);
      System.out.println("Merged List: " + mergedList);
  }
```
I followed your suggestions with the print statements in the merge method and this is what I got when I ran ListExamples.java:
<img width="834" alt="Screenshot 2024-03-12 at 12 13 23 PM" src="https://github.com/aran102504/cse15l-lab-reports/assets/157055098/112ba047-d86f-44f2-b673-eece152a37bb">

It looks like the merge method is incorrectly adding elements from `list1` when they are supposed to be added from `list2`. This might be causing the issue with the merged list,as it can be seen how the IndexOutOfBoundsException is probably caused by the `index2` counter being incremented even though we are not actually going through elements in `list2`.

## Set Up Details
File and Directory Structure: `ListExamples.java` is located in the directory named `lab7`. This Java file contains the `merge` method and the added `main` method used to help debug in the scenario above. There also is a bash script `test.sh` that was originally run by the student which brought notice to the bug in the merge method, as the tests for it were failing. 

Contents of `ListExamples.java` BEFORE fixing bug: 
```
mport java.util.ArrayList;
import java.util.List;

interface StringChecker { boolean checkString(String s); }

class ListExamples {

  // Returns a new list that has all the elements of the input list for which
  // the StringChecker returns true, and not the elements that return false, in
  // the same order they appeared in the input list;
  static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(0, s);
      }
    }
    return result;
  }


  // Takes two sorted list of strings (so "a" appears before "b" and so on),
  // and return a new list that has all the strings in both list in sorted order.
  static List<String> merge(List<String> list1, List<String> list2) {
    List<String> result = new ArrayList<>();
    int index1 = 0, index2 = 0;
    while(index1 < list1.size() && index2 < list2.size()) {
        if(list1.get(index1).compareTo(list2.get(index2)) < 0) {
            result.add(list1.get(index1));
            index1 += 1;
        }
        else {
            result.add(list1.get(index2)); // Bug
            index2 += 1;
        }
    }
    while(index1 < list1.size()) {
        result.add(list1.get(index1));
        index1 += 1;
    }
    while(index2 < list2.size()) {
        result.add(list2.get(index2));
        index2 += 1;
    }
    return result;
}
  
}
```
Commands ran to trigger bug: `javac ListExamples.java` `bash test.sh`

Bug Fix: To fix this bug, you would need to change the statement adding the element to list in the `else` statement in the first `while` loop of the merge method. In other words, you should change `result.add(list1.get(index2))` to `result.add(list2.get(index2))`. This line is also indicated with an in-line comment labeling it `Bug`.



## Part 2: Reflection
I recently discovered the practicality of using Vim commands, realizing its value in editing code files directly from the command line. The idea of making GitHub commits via the terminal was also very interesting to me. Exploring Vim, I found it fascinating to learn about various commands like insert or delete, which weren't initially intuitive to me, as I would have just tried to use the keys on the computer's keyboard.
