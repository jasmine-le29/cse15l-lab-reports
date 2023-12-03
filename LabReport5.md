## Lab Reports

### Part 1 – Debugging Scenario

1. The original post from a student with a screenshot showing a symptom and a description of a guess at the bug/some sense of what the failure-inducing input is:

#### Student Post:
- Hi, I need help to understand why my code is compiling so many errors. When I run `bash test.sh`, I get errors and a test has failed. I think that the error has something to do with my variables `index1 = 0` and `index2 = 0` it should be in square brackets `[]` so it should be 'index[1] = 0` and `index[2] = 0` since we are declaring an array. 

<img width="599" alt="Screenshot 2023-12-02 at 8 40 46 PM" src="https://github.com/jasmine-le29/cse15l-lab-reports/assets/116687332/fdc8c438-5abc-4059-bd70-3d727c7e8293">

<img width="449" alt="Screenshot 2023-12-02 at 9 14 30 PM" src="https://github.com/jasmine-le29/cse15l-lab-reports/assets/116687332/f36020be-89bf-4d2d-a46a-dc8e04850e6a">

<img width="582" alt="Screenshot 2023-12-02 at 9 55 10 PM" src="https://github.com/jasmine-le29/cse15l-lab-reports/assets/116687332/372f59c7-6c3f-4ee0-8b28-a8780de011f9">

#### TA's Response:
- Hi, based on your code and output results when running your bash test.sh, it looks like the variables `index1` and `index2` are not getting a value when it is running through the loops in your code. Changing the code `index[1] = 0` and `index[2] = 0` would be wrong since we are dealing with an `ArrayList` instead of just an `array`. The variables would still remain `index1 = 0` and `index2 = 0` were initially declared correctly. Looking at your code, the variables in your while loops after ``if(list1.get(index1).compareTo(list2.get(index2)) < 0)`` do not seem to call what the initial value of `index1` and `index2` are. Since you only declared it in that if statement, ``if(list1.get(index1).compareTo(list2.get(index2)) < 0)``, it does not apply for the other while loops you have below this if statement. What should you do to the `index1` and `index2` values, keeping the variable name intact, but making it accessible to the other while loops after your `if` statement you previously had it in?


2. 



### Part 2 – Reflection
