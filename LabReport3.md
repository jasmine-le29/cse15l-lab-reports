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
jasminele@Jasmines-MacBook biomed % grep -i "older" 1468-6708-3-1.txt
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
jasminele@Jasmines-MacBook biomed % grep -i "Experiment" 1471-213X-1-12.txt
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

# -r (recursive search aka grep -r):
- Example 1:
```
grep -r "In addition to"
```
Output:
```
./chapter-13.5.txt:                September 13, 2001. In addition to the usual members of President Bush's war
./chapter-13.3.txt:                such as race, creed, color, or national origin. In addition to those chosen by the
./chapter-3.txt:                the United States. In addition to requiring court review of proposed surveillance
./chapter-3.txt:            In addition to those from the Department of Defense, other elements in the
./chapter-2.txt:            In addition to training fighters and special operators, this larger network of
./chapter-1.txt:Military Notification and Response. Boston Center did not follow the protocol in seeking military assistance through the prescribed chain of command. In addition to notifications within the FAA, Boston Center took the initiative, at 8:34, to contact the military through the FAA's Cape Cod facility. The center also tried to contact a former alert site in Atlantic City, unaware it had been phased out. At 8:37:52, Boston Center reached NEADS. This was the first notification received by the military-at any level-that American 11 had been hijacked:
./chapter-5.txt:                directly with al Qaeda. In addition to supervising the planning and preparations for
./chapter-5.txt:                Afghanistan at al Qaeda's camps. In addition to his close working relationship with
./chapter-5.txt:            In addition to staging actual terrorist attacks in partnership with al Qaeda, Hambali
./chapter-5.txt:                repeat the first semester of his studies. In addition to having academic
./chapter-5.txt:            In addition to Atta, Binalshibh, Shehhi, and Jarrah, the group included other
./chapter-7.txt:                throughout his time in the United States. In addition to his trips, Jarrah made
./chapter-7.txt:            In addition to the operatives who eventually participated in the 9/11 attacks as
./chapter-9.txt:                attack. In addition to county fire, police, and sheriff 's departments, the response
./chapter-8.txt:                the summer. In addition to his daily meetings with President Bush, and weekly
```

- Example 2:
```

```
Output:
```

```

- The command grep -r is a command that recursively searches all the files in the directory you are currently present in and matches the desired string you put in quotation marks. It outputs the file in which the word you want is contained and to the left, it outputs the text. To use this command, you say grep -r "the word you want". This command is useful when you want to search for the string within a directory/large directory and it shows which txt file your string is contained in.

# -1 (list matching files aka grep -1):
- Example 1:
```
jasminele@Jasmines-MacBook biomed % grep -l "biology" ./*
```
Output:
```
./1471-2105-1-1.txt
./1471-2105-3-12.txt
./1471-2105-3-18.txt
./1471-2105-3-26.txt
./1471-2105-3-30.txt
./1471-2105-3-34.txt
./1471-2105-3-4.txt
./1471-2105-4-31.txt
./1471-2121-3-4.txt
./1471-2121-4-5.txt
./1471-213X-1-2.txt
./1471-213X-2-7.txt
./1471-2148-1-1.txt
./1471-2148-1-6.txt
./1471-2148-2-15.txt
./1471-2148-2-7.txt
./1471-2148-3-4.txt
./1471-2164-3-16.txt
./1471-2164-3-26.txt
./1471-2164-3-28.txt
./1471-2164-3-32.txt
./1471-2164-3-9.txt
./1471-2164-4-19.txt
./1471-2164-4-22.txt
./1471-2164-4-23.txt
./1471-2172-3-4.txt
./1471-2180-2-2.txt
./1471-2180-2-22.txt
./1471-2180-2-38.txt
./1471-2180-3-11.txt
./1471-2180-3-4.txt
./1471-2199-3-7.txt
./1471-2202-2-16.txt
./1471-2202-3-1.txt
./1471-2202-3-11.txt
./1471-2202-4-5.txt
./1471-2261-3-4.txt
./1471-2350-3-7.txt
./1471-2350-4-2.txt
./1471-2407-1-19.txt
./1471-2407-2-11.txt
./1471-2407-3-16.txt
./1471-2407-3-18.txt
./1471-2407-3-5.txt
./1472-6750-1-11.txt
./1472-6750-1-13.txt
./1472-6750-2-14.txt
./1472-6750-2-21.txt
./1472-6750-3-11.txt
./1472-6769-1-3.txt
./1472-6785-1-3.txt
./1472-6793-1-2.txt
./1472-6807-2-3.txt
./1472-6963-3-14.txt
./1475-2875-1-5.txt
./1475-2875-2-4.txt
./1475-4924-1-10.txt
./1475-925X-2-10.txt
./1475-9268-1-1.txt
./1476-0711-2-3.txt
./1476-4598-1-8.txt
./1477-7827-1-9.txt
./ar118.txt
./ar331.txt
./ar409.txt
./ar612.txt
./cc1498.txt
./gb-2001-2-12-research0051.txt
./gb-2001-2-2-research0004.txt
./gb-2001-2-4-research0012.txt
./gb-2002-3-10-research0052.txt
./gb-2002-3-10-research0055.txt
./gb-2002-3-12-research0081.txt
./gb-2002-3-12-research0082.txt
./gb-2002-3-12-research0086.txt
./gb-2002-3-12-research0087.txt
./gb-2002-3-3-research0011.txt
./gb-2002-3-7-research0037.txt
./gb-2002-3-8-research0039.txt
./gb-2002-3-8-research0040.txt
./gb-2002-4-1-r2.txt
./gb-2003-4-1-r7.txt
./gb-2003-4-2-r8.txt
./gb-2003-4-4-r26.txt
./gb-2003-4-4-r28.txt
./gb-2003-4-5-r32.txt
./gb-2003-4-6-r39.txt
./gb-2003-4-7-r46.txt
./gb-2003-4-9-r58.txt
./gb-2003-4-9-r60.txt
./rr167.txt
```
- Example 2:
```

```
Output:
```

```
- 
