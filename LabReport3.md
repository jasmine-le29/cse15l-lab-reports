## Lab Report 3

# Part 1 - Bugs: ArrayTests - testReverseInPlace method

## A failure-inducing input
```
@Test 
public void testReverseInPlace_Failure() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
}
```

## An input that doesn't induce a failure
```
@Test 
public void testReverseInPlace() {
    int[] input2 = { 1, 2, 3 };
    assertArrayEquals(new int[]{ 3, 2, 1 },
    ArrayExamples.reversed(input2));
}
```
## The symptom, as the output of running the tests

- Error
<img width="906" alt="Screenshot 2023-11-03 at 4 51 19 PM" src="https://github.com/jasmine-le29/cse15l-lab-reports/assets/116687332/72b68e63-6176-492c-81b6-3e247a2c1028">

- No Error
<img width="905" alt="Screenshot 2023-11-04 at 11 27 02 AM" src="https://github.com/jasmine-le29/cse15l-lab-reports/assets/116687332/b80d2360-06ff-47dc-8eb3-857e152b7b22">


## The bug before and after code change required to fix

Before:
```
// Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1] ;
    }
    return arr;
  }
```

After:
```
// Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2 ; i += 1) {
      int temp = arr[arr.length - i - 1];
      arr[i] = temp;
    }
  }
```
```
 static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1] ;
    }
    return newArray;
  }
```

- For the method reverseInPlace, before fixing the code, it loops through the entire array from index 1 to arr.length - 1. It reassigns the element many times resulting in overwritting the original files. The fix of adding arr.length/2, this loops through half of the array starting from index 0. In order to correctly reverse the array, a temp variable is added to store the element at the end of the array and assign it to the correct first position. For the reversed method, before fixing the code, since the code is returning arr, it was returning the original modified version which is not the same for reversing the array. The fix of creating a new array which is used to store the reversed values. This newArray variable is then returned, which reverses the correct output we want.

# Part 2 - Researching Commands(grep): 

# -i (ignore case aka, grep -i):
- Example 1:
```
grep -i "older" 1468-6708-3-1.txt
```
Output:
```
Older adults are frequently counseled to lose weight,
non-smoking older adults have investigated the association
in certain small subsets. A review of 13 studies of older
Many healthy older adults report gradual weight gain
number of studies of older persons is fairly small, and
In older adults, risk factors may have a greater effect
years of being healthy, in a cohort of older adults for
modification interventions in older adults.
65 and older at baseline [ 11 ] . Subjects were recruited
older men and 30-35 for older women. In Figure 1, the
categories could be combined for older adults. Since
older women could be efficient if YHL (but not YOL) was
interventions for older adults who were merely overweight
evaluations should be considered critically when older
33 34 ] . For older adults, the risks associated with
outcome for a trial of weight loss in older adults
found for underweight older adults. Clinical trials whose
average older adult; however, adjustment for detailed
older adults, especially for women. Future efforts to
no excess risk for older adults who would be classified as
obese or underweight older adults, and discouraging trials
that address older adults who are merely overweight.
```

- Example 2:
```
grep -i "experiment" 1471-213X-1-12.txt
```
Output:
```
are no reports that experimentally tested this hypothesis
Experiments were repeated 3 times and the data are
experiment using M II oocytes. It is possible that
experiment using confluent cells. Therefore, it is expected
were selected. In our preliminary experiment, such a
Experimental Studies
In Experiment 1, the cell cycle stages of confluent
In Experiment 2, we examined the behavior before
In Experiment 3, the behavior of nuclei of confluent
Experiment 4 was undertaken to compare in vitro
values were analyzed using one-way (Experiment 2) or
two-way (Experiments 3 and 4) ANOVA followed by
```
- The command grep -i is an ignore case used to perform a case-insensitive search within a file you are searching for along with the word you are searching for. To use this command, you say grep -i "the word you want" theFileYouWant.txt. This command is useful when you want to search for and print out lines matching whatever you put in quotation marks to help minimize your search.
