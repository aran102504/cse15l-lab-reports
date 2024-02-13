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

