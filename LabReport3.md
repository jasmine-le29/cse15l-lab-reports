## Lab Report 3

# Part 1 - Bugs: ArrayTests - testReverseInPlace method

- A failure-inducing input
```
 @Test 
public void testReverseInPlace_Failure() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
}
```

- An input that doesn't induce a failure
```
@Test 
	public void testReverseInPlace() {
    int[] input2 = { 1, 2, 3 };
    assertArrayEquals(new int[]{ 3, 2, 1 },
    ArrayExamples.reversed(input2));
	}
```
- The symptom, as the output of running the tests


- The bug before and after code change required to fix

Before:
```
// Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
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

# Part 2 - Researching Commands: 

