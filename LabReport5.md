## Lab Reports

### Part 1 – Debugging Scenario

1. The original post from a student with a screenshot showing a symptom and a description of a guess at the bug/some sense of what the failure-inducing input is:

#### Student Post:
- Hi, I need help to understand why my code is compiling so many errors. When I run `bash test.sh`, I get errors and a test has failed. I think that the error has something to do with my variables `index1 = 0` and `index2 = 0` it should be in square brackets `[]` so it should be `index[1] = 0` and `index[2] = 0` since we are declaring an array. 

<img width="582" alt="Screenshot 2023-12-02 at 9 55 10 PM" src="https://github.com/jasmine-le29/cse15l-lab-reports/assets/116687332/372f59c7-6c3f-4ee0-8b28-a8780de011f9">

<img width="449" alt="Screenshot 2023-12-02 at 9 14 30 PM" src="https://github.com/jasmine-le29/cse15l-lab-reports/assets/116687332/f36020be-89bf-4d2d-a46a-dc8e04850e6a">

#### TA's Response:
- Hi, based on your code and output results when running your bash test.sh, it looks like the variables `index1` and `index2` are not getting a value when it is running through the loops in your code. Changing the code `index[1] = 0` and `index[2] = 0` would be wrong since we are dealing with an `ArrayList` instead of just an `array`. The variables would still remain `index1 = 0` and `index2 = 0` were initially declared correctly. Looking at your code, the variables in your while loops after ``if(list1.get(index1).compareTo(list2.get(index2)) < 0)`` do not seem to call what the initial value of `index1` and `index2` are. Since you only declared it in that if statement, ``if(list1.get(index1).compareTo(list2.get(index2)) < 0)``, it does not apply for the other while loops you have below this if statement. What should you do to the `index1` and `index2` values, keeping the variable name intact, but making it accessible to the other while loops after your `if` statement you previously had it in?

#### Student's Revision:
- Based on the feedback you gave for my errors with my code, I decided to move the variables `index1` and `index2` out of the `if` statement and declare it outside of the initial `while` loop before it gets nested into other `if` statements and `while` loops below so that when `index1` and `index2` are called below, they would be initialized at once before the start of the while loops. Having the variables declared after the while loop and in the `if` statement, it does not have access to the variables outside the `if` statements and in the following `while` loops after that.

<img width="571" alt="Screenshot 2023-12-02 at 10 00 07 PM" src="https://github.com/jasmine-le29/cse15l-lab-reports/assets/116687332/1a125fcf-3784-446f-b68d-1674d7d0f4ec">
<img width="355" alt="Screenshot 2023-12-02 at 10 36 20 PM" src="https://github.com/jasmine-le29/cse15l-lab-reports/assets/116687332/4d02fd17-289e-47e2-bd37-a367c081c713">

#### At the end, all the information needed about the setup:
1.  The file & directory structure needed
   - File: `ListExamples.java`
   - Directory: `lab7`
2.  The contents of each file before fixing the bug
    - File: `ListExamples.java`
4.  The full command line (or lines) you ran to trigger the bug
    - `bash test.sh`
5.  A description of what to edit to fix the bug
    - I moved the two variables `index1` and `index2` above the initial `while` loop so that those variables can be used throughout the rest of the program

### Part 2 – Reflection
- Somne things I learned from my lab experience in the second half of this quarter was to use `vim`. When messing with the terminal before in my hackathon, I would accidentally enter `vim` not knowing what it was. I learned that in the `vim` mode you are able to access files directly from the terminal and make edits without having to individually go into all the files with your mouse on the side. To quickly delete in `vim` you would use the key `<x>` in normal mode. If you want to change something drastically, you can go into `insert` mode using the `<i>` key and make the edits you want. Another cool thing I learned is that you can have the terminal output your file directly to the terminal using the command `cat`. If you were not in `vim` and want the contents of the file to print in the terminal to check without having to go into `vim` or go into the file manually, you can use the `cat` command followed by the file name, for example, `ListExamples.java` and the command should output the contents of `ListExamples.java` in the terminal directly.
